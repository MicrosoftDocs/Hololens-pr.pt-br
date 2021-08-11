---
title: Guia de implantação – Aplicativos HoloLens 2 conectados com o Dynamics 365 Guides – Implantar
description: Saiba como configurar implantações de dispositivos HoloLens 2 em uma rede conectada corporativa com guias do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
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
ms.openlocfilehash: f9435ce94986a851bb7744eeea48fa6e411454f5090d7ae11c869ba6f27dc942
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660233"
---
# <a name="deploy---corporate-connected-guide"></a>Implantar – Guia conectado corporativo

Uma parte importante de cada implantação é garantir que sua implantação seja configurada corretamente antes de testá-la por conta própria para garantir uma experiência tranquila para o usuário final.

Como estamos implantando o certificado Wi-Fi via MDM, precisamos configurar inicialmente o HoloLens e registrar dispositivos em uma rede Wi-Fi aberta ou em uma rede que não exige o certificado. Depois que o HoloLens tiver concluído OOBE e Registrado, o dispositivo receberá o certificado de rede e o LOB configurados anteriormente e será possível validar se ambos foram recebidos pelo dispositivo.

Posteriormente, você poderá confirmar que pode tanto o autor quanto operar um Guia de teste.

## <a name="enrollment-validation"></a>Validação de registro

Agora que tudo está configurado corretamente para o Azure AD e o Registro de MDM, o restante agora deve ser um snap. Você precisará de uma conexão Wi-Fi dispositivo HoloLens e uma das contas de usuário do Azure AD configuradas anteriormente.

Se seu dispositivo não estiver atualmente em um estado de configurações de fábrica, agora seria um bom momento para [reflash o dispositivo](/hololens/hololens-recovery#clean-reflash-the-device).

1. Depois que o dispositivo está em OOBE, você precisará começar a interagir e seguir os prompts.

2. Conexão em uma rede Wi-Fi que não exige certificados para ingressar no Wi-Fi. Isso permitirá que o dispositivo baixe o certificado a ser usado no Wi-Fi da organização após a configuração inicial.

3. O prompt crítico será quando você for solicitado Who **possui esse HoloLens?** Selecione **Minha empresa ou escola possui e** insira suas credenciais de conta do Azure AD.

4. Quando o registro for bem-sucedido, você será solicitado a configurar um PIN. Esse PIN é exclusivo para esse dispositivo para esse usuário. Você também receberá uma solicitação para verificações de Íris, dados de voz e configurações de telemetria e, por fim, você poderá aprender a abrir o menu Iniciar e concluir o OOBE.

5. Depois de chegar à Página Inicial da Realidade Misturada, abra o menu Iniciar usando o **gesto Iniciar** que você acabou de aprender.

6. Selecione o **Configurações** aplicativo e selecione **Sistema**. A primeira informação que você verá é o Nome do dispositivo, que para o dispositivo HoloLens 2 será HOLOLENS, seguido por uma cadeia de caracteres &quot; &quot; de seis caracteres.

7. Anote esse nome.

    ![HoloLens tela de Configurações 2](./images/hololens2-settings-about.jpg)

8. Verifique se o dispositivo foi ingressado com êxito no Azure AD. Há duas maneiras;

    1.  O Configurações aplicativo. Na **Configurações** selecione **Contas Acessar trabalho** ou  ->  **escola.** Nessa tela, você pode verificar se está inscrito com êxito vendo Conectado ao &quot; nameofAAD&#39;do Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com* . Isso verificará se o dispositivo está ingressado em sua organização&#39;Azure AD.

    1. O [Portal do Azure](https://portal.azure.com/#home). Vá para **Azure Active Directory**  ->  **Dispositivos Todos** os  ->  **dispositivos** e pesquise o nome do dispositivo. Em Tipo de Junção, ele mostrará como sendo 'Ingressado no Azure AD'.
        ![Verificar o tipo de junção no Azure AD](./images/hololens2-devices-all-devices.png)

9. Verifique se o dispositivo está inscrito no MDM. Há duas maneiras;

    1. No **Configurações**, selecione **Contas Acessar trabalho** ou  ->  **escola.** Nessa tela, você pode verificar se está inscrito com êxito vendo Conectado ao &quot; nameofAAD&#39;do Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com* . Nessa conta de trabalho ou de estudante do Access, selecione &quot; Conectado ao nameofAAD&#39;do Azure AD. Conectado por yourusername@nameofAAD.onmicrosoft.com &quot; e selecione o **botão** Informações.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Faça logoff e selecione  **Dispositivos e,**  em  **seguida, Todos os dispositivos**. A partir daqui, você pode pesquisar seu HoloLens dispositivo&#39;nome. Você deve ser capaz de ver seus HoloLens listados no Intune.

        ![Verificar gerenciado pelo Intune no Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi de certificado

Agora, o dispositivo já deve ter recebido o Wi-Fi certificado. A validação mais simples que você pode fazer é tentar se conectar à Wi-Fi para a qual&#39;recebeu o certificado. Abra o aplicativo **Configurações,** navegue até Rede **&amp; Internet**  ->  **Wi-Fi** e selecione a conexão Wi-fi. Depois de conectado, abra o aplicativo Microsoft Edge e confirme se você pode navegar até um site.

Para confirmar que você recebeu o certificado no dispositivo, você pode usar o [Gerenciador de Certificados](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Validar a instalação do aplicativo LOB

Para ver o progresso da instalação de um aplicativo gerenciado, você pode ver se o aplicativo está instalado ou verificar Configurações. Ao configurar um aplicativo LOB como uma instalação necessária para nosso grupo, depois de registrar o HoloLens com um usuário no grupo atribuído, o aplicativo será baixado automaticamente para o HoloLens.

Abra o menu Iniciar e selecione **Todos os apps**. Dependendo do número de aplicativos que você tem, talvez seja necessário usar os botões de página para **cima** ou **para** baixo da página.

Para validar a instalação do aplicativo no dispositivo, você pode fazer isso por meio do trabalho ou escola do **Configurações** Accounts Access; selecione a conta e, em seguida, o botão Informações e role para baixo para ver diferentes configurações e aplicativos aplicados ao dispositivo no  ->    ->  MDM. 

Para validar a instalação do Intune, navegue até a página de status Aplicativos do [portal do MEM](https://endpoint.microsoft.com/#home)-> Todos os aplicativos  ->     -> *TheNameOfYourApp*  ->  **Device install.**

Confira mais: [Implantação de aplicativo do Intune para HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Validar guias do Dynamics 365

Há modos para o aplicativo Guides no HoloLens, na complicação e operação. Você precisará concluir a autorização de um guia antes de o operar.

### <a name="authoring-the-guide"></a>Como fazer o guia

Não precisamos fazer muito para essa validação rápida. Basta selecionar o guia que você preparou em seu computador. Você precisará ancorar [o guia](/dynamics365/mixed-reality/guides/hololens-app-anchor), para uma validação rápida, você pode usar uma âncora holográfica. Posteriormente, você deve [colocar suas etapas e modelos](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Você precisará da **função De autor** para fazer logon no COMPUTADOR e para o autor no HoloLens. A função Operador é somente leitura e não tem acesso ao aplicativo pc.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Como operar o guia

Depois que os hologramas estão em funcionamento, você pode testar a operação do guia. 
- Selecionar **modo de operador**
- Clique nas etapas do guia.

Para obter diretrizes mais detalhadas sobre como operar um guia, confira estes recursos:

[Visão geral da operação de um guia nos Guias do Dynamics 365](/dynamics365/mixed-reality/guides/operator-overview)

[Ser orientado com o cartão Etapa como operador nos Guias do Dynamics 365](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa – Manter](hololens2-corp-connected-maintain.md)
