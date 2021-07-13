---
title: guia de implantação – corporativo conectado HoloLens 2 com guias do Dynamics 365 – implantar
description: saiba como configurar implantações de dispositivos HoloLens 2 em uma rede conectada corporativa com os guias do Dynamics 365.
keywords: HoloLens, gerenciamento, corporativo conectado, guias do Dynamics 365, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637054"
---
# <a name="deploy---corporate-connected-guide"></a>Implantar – guia conectado corporativo

Uma parte importante de cada implantação é garantir que sua implantação esteja configurada corretamente antes de testá-la para garantir uma experiência tranqüila para o usuário final.

como estamos implantando o certificado de Wi-Fi por meio do MDM, precisaremos configurar inicialmente HoloLens e registrar dispositivos em uma rede Wi-Fi aberta ou uma rede que não exija o certificado. depois que o HoloLens tiver concluído o OOBE e registrado, o dispositivo receberá o certificado de rede e o LOB configurados anteriormente e poderá validar ambos que foram recebidos pelo dispositivo.

Posteriormente, você poderá confirmar que pode criar e operar um guia de teste.

## <a name="enrollment-validation"></a>Validação de registro

Agora que tudo está configurado corretamente para o Azure AD e o registro de MDM, o restante agora deve ser um snap. você precisará de uma conexão Wi-Fi e do dispositivo HoloLens e uma das contas de usuário do Azure AD configuradas anteriormente.

Se seu dispositivo não estiver atualmente em um estado de configurações de fábrica, agora seria um bom momento para refazer [o flash do dispositivo](/hololens/hololens-recovery#clean-reflash-the-device).

1. Depois que o dispositivo estiver em OOBE, você precisará começar a interagir e seguir os prompts.

2. Conexão a uma rede aberta Wi-Fi que não requer certificados para ingressar no Wi-Fi. Isso permitirá que o dispositivo Baixe o certificado a ser usado no Wi-Fi da organização após a configuração inicial.

3. o aviso crítico será quando você for solicitado **Who a possuir este HoloLens?** Selecione **meu trabalho ou escola possui** e insira suas credenciais de conta do Azure AD.

4. Quando o registro for bem-sucedido, você será solicitado a configurar um PIN. Este PIN é exclusivo para este dispositivo para este usuário. Você também será solicitado a fornecer verificações de íris, dados de voz e configurações de telemetria e, por fim, poderá aprender a abrir o menu iniciar e concluir o OOBE.

5. depois de chegar à casa misturada na realidade, abra o menu Iniciar usando o **gesto de início** que você acabou de aprender.

6. selecione o aplicativo **Configurações** e selecione **sistema**. a primeira informação que você verá é o nome do dispositivo, que para o dispositivo HoloLens 2 será o &quot; HoloLens- &quot; seguido por uma cadeia de seis caracteres.

7. Anote esse nome.

    ![tela do HoloLens 2 Configurações](./images/hololens2-settings-about.jpg)

8. Verifique se o dispositivo ingressou no Azure AD com êxito. Há duas maneiras:

    1.  o aplicativo Configurações. em **Configurações** selecione **contas**  ->  **acesso corporativo ou de estudante**. Nessa tela, você pode verificar se está registrado com êxito ao ver &quot; conectado ao nameofAAD&#39;s do Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com* . Isso verificará se o dispositivo está associado à sua organização&#39;s do Azure AD.

    1. O [Portal do Azure](https://portal.azure.com/#home). vá para **Azure Active Directory**  ->  **dispositivos**  ->  **todos os dispositivos** e pesquise o nome do dispositivo. Em tipo de junção, ele aparecerá como "ingressado no Azure AD".
        ![Verificar tipo de junção no Azure AD](./images/hololens2-devices-all-devices.png)

9. Verifique se o dispositivo está registrado no MDM. Há duas maneiras:

    1. em **Configurações**, selecione **contas**  ->  **acesso corporativo ou de estudante**. Nessa tela, você pode verificar se está registrado com êxito ao ver &quot; conectado ao nameofAAD&#39;s do Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com* . Nessa conta corporativa ou de estudante do Access, selecionando &quot; conectado ao nameofAAD&#39;s AD do Azure. Conectado por yourusername@nameofAAD.onmicrosoft.com &quot; e selecione o botão **informações** .

    1. [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Faça logon e selecione  **dispositivos**  e, em seguida,  **todos os dispositivos**. a partir daqui, você pode pesquisar seu HoloLens dispositivo&#39;nome. você deve ser capaz de ver suas HoloLens listadas no Intune.

        ![Verificar gerenciado pelo Intune no Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi validação de certificado

Agora, o dispositivo deve ter recebido o certificado de Wi-Fi. A validação mais simples que você pode fazer é tentar se conectar à conexão de Wi-Fi para a qual você&#39;recebido o certificado. abra o aplicativo **Configurações** e navegue até **rede &amp; Internet**  ->  **wi-fi** e selecione a conexão wi-fi. uma vez conectado, abra o aplicativo Microsoft Edge e confirme que você pode navegar para um site.

Para confirmar que você recebeu o certificado no dispositivo, você pode usar o Gerenciador de [certificados](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Validar a instalação do aplicativo de LOB

para ver o progresso da instalação de um aplicativo gerenciado, você verá se o aplicativo está instalado ou verifica Configurações. ao configurar um aplicativo LOB como uma instalação necessária para nosso grupo, depois de registrar o HoloLens com um usuário no grupo atribuído, o aplicativo será baixado automaticamente para o HoloLens.

abra o menu Iniciar e selecione **todos os aplicativos**. Dependendo do número de aplicativos que você tem, talvez seja necessário usar os botões **Page Up** ou **Page Down** .

para validar a instalação do aplicativo no dispositivo, você pode fazer isso por meio de **Configurações**  ->  **contas**  ->  **acessar o trabalho ou a escola**; selecione a conta, em seguida, o botão **informações** e role para baixo para ver diferentes configurações e aplicativos aplicados ao dispositivo do MDM.

Para validar a instalação do Intune, navegue até a página aplicativos do [portal do mem](https://endpoint.microsoft.com/#home)  ->   – > todos os **aplicativos**  -> *TheNameOfYourApp* de  ->  **status de instalação do dispositivo** .

Veja mais: [implantação de aplicativo do Intune para HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Validar guias do Dynamics 365

há modos para o aplicativo de guias em HoloLens, criação e operação. Você precisará concluir a criação de um guia antes de operar.

### <a name="authoring-the-guide"></a>Criando o guia

Não precisamos fazer muito para essa validação rápida. Basta selecionar o guia que você preparou em seu computador. Você precisará [ancorar o guia](/dynamics365/mixed-reality/guides/hololens-app-anchor)para uma validação rápida, você pode usar uma âncora Holographic. Depois disso, você deve [posicionar suas etapas e modelos](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Você precisará da função de **criação** para fazer logon no PC e criar no HoloLens. A função operador é somente leitura e não tem acesso ao aplicativo de PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Operando o guia

Depois que os hologramas estiverem em vigor, você poderá testar a operação de seu guia. 
- Selecionar **modo de operador**
- Clique nas etapas do seu guia.

Para obter diretrizes mais detalhadas sobre como operar um guia, confira estes recursos:

[Visão geral da operação de um guia em guias do Dynamics 365](/dynamics365/mixed-reality/guides/operator-overview)

[Seja orientado com o cartão Step como um operador nos guias do Dynamics 365](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa-manter](hololens2-corp-connected-maintain.md)
