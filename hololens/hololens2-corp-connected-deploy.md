---
title: Guia de Implantação – HoloLens 2 conectado corporativo com Guias do Dynamics 365 - Implantar
description: Saiba como configurar implantações de dispositivos HoloLens 2 em uma rede conectada corporativa com guias do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448503"
---
# <a name="deploy---corporate-connected-guide"></a>Implantar - Guia Conectado Corporativo

Uma parte importante de cada implantação é garantir que sua implantação seja configurada corretamente antes de testá-la por conta própria para garantir uma experiência suave para o usuário final.

Como estamos implantando o certificado Wi-Fi via MDM, precisamos configurar inicialmente o HoloLens e registrar dispositivos em uma rede aberta Wi-Fi ou em uma rede que não exige o certificado. Depois que o HoloLens terminar o OOBE e o Enrolled, o dispositivo receberá o certificado de rede e o LOB configurados anteriormente e podemos validar que ambos foram recebidos pelo dispositivo.

Posteriormente, você poderá confirmar se pode autor e operar um Guia de teste.

## <a name="enrollment-validation"></a>Validação de Registro

Agora que tudo está configurado corretamente para o Registro do Azure AD e MDM, o restante agora deve ser um snap. Você precisará de uma conexão Wi-Fi e o dispositivo HoloLens e uma das contas de usuário do Azure AD configuradas anteriormente.

Se o dispositivo não estiver atualmente sentado em um estado de configurações de fábrica, agora seria um bom momento para [reaflar o dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Depois que o dispositivo está em OOBE, você precisará começar a interagir e seguir os prompts.

2. Conecte-se a uma rede Wi-Fi aberta que não exige certificados para ingressar no Wi-Fi. Isso permitirá que o dispositivo baixe o certificado a ser usado no Wi-Fi da organização após a configuração inicial.

3. O prompt crítico será quando você for perguntado **Quem é o proprietário deste HoloLens?** Selecione **Meu trabalho ou escola possui e** insira suas credenciais de conta do Azure AD.

4. Quando o registro for bem-sucedido, você será solicitado a configurar um PIN. Esse PIN é exclusivo deste dispositivo para esse usuário. Você também será solicitado a fazer verificações de Íris, dados de voz e configurações de telemetria e, por fim, você poderá aprender como abrir o menu inicial e concluir o OOBE.

5. Depois de chegar na Casa da Realidade Misturada, abra o menu Iniciar usando o gesto **Iniciar** que você acabou de aprender.

6. Selecione o **aplicativo Configurações** e selecione **Sistema**. A primeira informação que você verá é o nome do dispositivo, que para o dispositivo HoloLens 2 será HOLOLENS, seguido por uma cadeia de caracteres de &quot; &quot; seis caracteres.

7. Anote esse nome.

    ![Tela Configurações do HoloLens 2](./images/hololens2-settings-about.jpg)

8. Verifique se seu dispositivo foi ingressado com êxito no Azure AD. Há duas maneiras;

    1.  O aplicativo Configurações. Em **Configurações,** selecione **Contas**  ->  **Acessar trabalho ou escola**. Nesta tela, você pode verificar se está inscrito com êxito ao ver Conectado ao &quot; nameofAAD&#39;do Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com*. Isso verificará se o dispositivo está ingressado na sua organização&#39;do Azure AD.

    1. O [portal do Azure](https://portal.azure.com/#home). Vá para **Dispositivos do Azure Active Directory**  ->  ****  ->  **Todos os dispositivos**e pesquise o nome do dispositivo. Em Tipo de Ingresso, ele mostrará como sendo 'Azure AD Joined'.
        ![Verificar o tipo de junção no Azure AD](./images/hololens2-devices-all-devices.png)

9. Verifique se seu dispositivo está inscrito no MDM. Há duas maneiras;

    1. Em **Configurações,** selecione **Contas**  ->  **Acessar trabalho ou escola.** Nesta tela, você pode verificar se está inscrito com êxito ao ver Conectado ao &quot; nameofAAD&#39;do Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com*. Nesta conta de estudante ou trabalho do Access &quot; selecionando Conectado ao nomedoAAD&#39;do Azure AD. Conectado por yourusername@nameofAAD.onmicrosoft.com &quot; e selecione o **botão Informações.**

    1. [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Faça logoff e selecione  **Dispositivos,**  **em seguida, Todos os dispositivos**. A partir daqui, você pode pesquisar seu dispositivo HoloLens&#39;nome. Você deve poder ver o HoloLens listado no Intune.

        ![Verificar gerenciado pelo Intune no Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi certificado

Até agora, o dispositivo já deve ter recebido o Wi-Fi certificado. A validação mais simples que você pode fazer é tentar se conectar à conexão Wi-Fi para a qual você&#39;recebeu o certificado. Abra o aplicativo **Configurações** e navegue até **Rede &amp; Wi-Fi**da Internet  ->  **** e selecione a conexão Wi-fi. Depois de conectado, abra o aplicativo do Microsoft Edge e confirme se você pode navegar até um site.

Para confirmar se você recebeu o certificado no dispositivo, você pode usar o [Gerenciador de Certificados](https://docs.microsoft.com/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Validar a instalação do aplicativo LOB

Para ver o andamento da instalação de um aplicativo gerenciado, você pode ver se o aplicativo está instalado ou verificar Configurações. Ao configurar um aplicativo LOB como uma instalação necessária para nosso grupo, depois de registrar o HoloLens com um usuário no grupo atribuído, o aplicativo será baixado automaticamente para o HoloLens.

Abra o menu Iniciar e selecione **Todos os aplicativos**. Dependendo do número de aplicativos que você **** tem, talvez seja necessário usar a página para cima ou **botões de** página para baixo.

Para validar a instalação do aplicativo no dispositivo, você pode fazer isso por meio de Configurações Contas acessar trabalho ou escola ; selecione a conta, em seguida, o botão Informações e role para baixo para ver configurações e aplicativos diferentes **aplicados**ao dispositivo a partir  ->  ****  ->  **** do MDM. ****

Para validar a instalação do Intune, navegue até o [portal de MEM](https://endpoint.microsoft.com/#home)Apps -> Página de status de instalação de todos os  ->  **** ****  -> aplicativos*TheNameOfYourApp*  ->  **Device.**

Confira mais: [Implantação de aplicativo do Intune para HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Validar guias do Dynamics 365

Há modos para o aplicativo Guias no HoloLens, criação e operação. Você precisará concluir a autoria de um guia antes de o operar.

### <a name="authoring-the-guide"></a>Autoria do Guia

Não precisamos fazer muito por essa validação rápida. Basta selecionar o guia que você preparou no computador. Você precisará ancorar [o guia](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor), para uma validação rápida, você pode usar uma âncora holográfica. Posteriormente, você deve [colocar suas etapas e modelos.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> Você precisará da **função Criação** para fazer logon no computador e no autor no HoloLens. A função Operador é somente leitura e não tem acesso ao aplicativo do computador.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Operando o Guia

Depois que seus hologramas estão no local, você pode testar o funcionamento do guia. 
- Selecionar **Modo de operador**
- Clique nas etapas do guia.

Para obter orientações mais detalhadas sobre como operar um guia, confira estes recursos:

[Visão geral da operação de um guia em Guias do Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Obter orientação com o cartão Step como operador em Guias do Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Próximas etapas 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa - Manter](hololens2-corp-connected-maintain.md)
