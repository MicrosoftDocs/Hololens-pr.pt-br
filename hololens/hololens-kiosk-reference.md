---
title: HoloLens de referência de quiosque
description: Informações e exemplos de quiosques em HoloLens dispositivos.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031944"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Informações de referência de quiosque

Esta página contém informações úteis para configurar o modo HoloLens quiosque do dispositivo. Essas referências incluem AUMIDs para aplicativos de caixa de entrada e localização do seu e vários exemplos xml para o modo de quiosque, que estão a apenas algumas edições de estarem prontos para uso para vários cenários diferentes. Para obter informações sobre como configurar um Quiosque, leia [a página Configurar um Quiosque.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens IDs de modelo de usuário do aplicativo (AUMIDs)  

Para obter informações gerais sobre como escolher aplicativos de quiosque, consulte Diretrizes para escolher um aplicativo para acesso atribuído [(modo de quiosque).](/windows/configuration/guidelines-for-assigned-access-app)

Se você usar um sistema MDM (Mobile Gerenciamento de Dispositivos) ou um pacote de provisionamento para configurar o modo de quiosque, use o CSP (Provedor de Serviços de Configuração) [AssignedAccess](/windows/client-management/mdm/assignedaccess-csp) para especificar aplicativos. O CSP usa [AUMIDs (IDs de](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) modelo de usuário de aplicativo) para identificar aplicativos. A tabela a seguir lista os AUMIDs de alguns aplicativos in-box que você pode usar em um quiosque de vários aplicativos.

<a id="aumids"></a>

|Nome do Aplicativo |AUMID |
| --- | --- |
|Visualizador 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendário |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Câmera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Aplicativo Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! |
|Se picker de dispositivo HoloLens (1ª geração) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Se picker de dispositivo HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DispositivosFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Hub de &nbsp; Comentários |Aplicativo Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Explorador de Arquivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Email |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Antigo Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Novo Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|Filmes e TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotos |Microsoft. Windows. Photos \_ 8wekyb3d8bbwe \! App |
|Antigo Configurações |HolographicSystemSettings_cw5n1h2txyewy! App |
|Novos Configurações |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Dicas |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Para habilitar a captura de fotos ou vídeos, você precisa habilitar o aplicativo Câmera como um aplicativo de quiosque.  
> <sup>2</sup> Ao habilitar o aplicativo Câmera, esteja ciente das seguintes condições:
> - O menu Ações Rápidas inclui os botões Foto e Vídeo.
> - Você também deve habilitar um aplicativo (como Fotos, Email ou OneDrive) que possa interagir ou recuperar imagens.  
>  
> <sup>3</sup> Mesmo se você não habilitar o Cortana como um aplicativo de quiosque, os comandos de voz integrados serão habilitados. No entanto, comandos relacionados a recursos desabilitados não têm nenhum efeito.  
> <sup>4</sup> Não é possível habilitar Miracast diretamente. Para habilitar Miracast como um aplicativo de quiosque, habilita o aplicativo Câmera e o aplicativo Seletor de Dispositivos.

Além disso, a Home da Realidade Misturada não pode ser definida como um aplicativo de quiosque.

Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Exemplos de código XML de quiosque

1. [Perfil de acesso atribuído global a vários aplicativos](#multiple-app-global-assigned-access-profile)
1. [Perfil de acesso atribuído global a vários aplicativos, exceto os proprietários do dispositivo](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Perfil de acesso atribuído a vários aplicativos para uma conta local ou conta de usuário do AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Vários perfis de acesso atribuídos a aplicativos para dois usuários do AAD ou mais](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Perfil de acesso atribuído a vários aplicativos para um grupo do AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Perfil de acesso atribuído a vários aplicativos para dois grupos do AAD ou mais](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Perfil de acesso atribuído a vários aplicativos para uma conta do AAD e um grupo do AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Perfil de acesso atribuído a vários aplicativos para visitantes](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Substitua as ações TODO de acordo com seus requisitos.

### <a name="multiple-app-global-assigned-access-profile"></a>Perfil de acesso atribuído global a vários aplicativos

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Perfil de acesso atribuído global a vários aplicativos, exceto os proprietários do dispositivo

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Perfil de acesso atribuído a vários aplicativos para uma conta local ou conta de usuário do AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Vários perfis de acesso atribuídos a aplicativos para dois usuários do AAD ou mais

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Perfil de acesso atribuído a vários aplicativos para um grupo do AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Perfil de acesso atribuído a vários aplicativos para dois grupos do AAD ou mais

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Perfil de acesso atribuído a vários aplicativos para uma conta do AAD e um grupo do AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Perfil de acesso atribuído a vários aplicativos para visitantes

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
