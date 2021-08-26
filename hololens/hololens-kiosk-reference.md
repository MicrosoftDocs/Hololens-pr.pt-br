---
title: informações de referência de HoloLens quiosque
description: informações e exemplos de quiosques em dispositivos HoloLens.
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
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863929"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Informações de referência do quiosque

esta página contém informações úteis para configurar o modo de quiosque do dispositivo HoloLens. Essas referências incluem o AUMIDs para aplicativos de caixa de entrada e a localização de seus e vários exemplos de XML para o modo de quiosque, que são apenas algumas edições longe de estarem prontos para uso em vários cenários diferentes. Para obter informações sobre como configurar um quiosque, leia a [página Configurar um quiosque.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens IDs de modelo de usuário de aplicativo (AUMIDs)  

Para obter informações gerais sobre como escolher aplicativos de quiosque, consulte [diretrizes para escolher um aplicativo para acesso atribuído (modo de quiosque)](/windows/configuration/guidelines-for-assigned-access-app).

Se você usar um sistema de MDM (gerenciamento de dispositivo móvel) ou um pacote de provisionamento para configurar o modo de quiosque, use o [provedor de serviços de configuração do AssignedAccess (CSP)](/windows/client-management/mdm/assignedaccess-csp) para especificar aplicativos. O CSP usa [AUMIDs (IDs de modelo de usuário do aplicativo)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar aplicativos. A tabela a seguir lista os AUMIDs de alguns aplicativos na caixa que você pode usar em um quiosque de vários aplicativos.

<a id="aumids"></a>

|Nome do Aplicativo |AUMID |
| --- | --- |
|Visualizador 3D |Microsoft. Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendário |Microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! Microsoft. windowslive. Calendar |
|Câmera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Aplicativo Microsoft. 549981C3F5F10 \_ 8wekyb3d8bbwe \! |
|seletor de dispositivo na HoloLens (1ª gen) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|seletor de dispositivos no HoloLens 2 |O. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. guias \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Hub de comentários &nbsp; |Aplicativo Microsoft. WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Explorador de Arquivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Email |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. windowslive. mail |
|Microsoft Edge antigo |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Novo Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|Filmes e TV |Microsoft. ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |aplicativo Microsoft. microsoftskydrive \_ 8wekyb3d8bbwe \! |
|Fotos |O. Windows. \_Aplicativo 8wekyb3d8bbwe de fotos \! |
|Configurações antigo |HolographicSystemSettings_cw5n1h2txyewy! Aplicação |
|novo Configurações |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicação |
|Dicas |Microsoft. HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> para habilitar a captura de foto ou de vídeo, você precisa habilitar o aplicativo de câmera como um aplicativo de quiosque.  
> <sup>2</sup> quando você habilitar o aplicativo de câmera, esteja ciente das seguintes condições:
> - O menu ações rápidas inclui os botões de foto e vídeo.
> - você também deve habilitar um aplicativo (como fotos, email ou OneDrive) que possa interagir com ou recuperar imagens.  
>  
> <sup>3</sup> mesmo se você não habilitar Cortana como um aplicativo de quiosque, os comandos de voz internos serão habilitados. No entanto, os comandos relacionados a recursos desabilitados não têm nenhum efeito.  
> <sup>4</sup> você não pode habilitar Miracast diretamente. Para habilitar Miracast como um aplicativo de quiosque, habilite o aplicativo de câmera e o aplicativo de seletor de dispositivo.

Além disso, a página inicial da realidade misturada não pode ser definida como um aplicativo de quiosque.

Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Exemplos de código XML do quiosque

1. [Perfil de acesso atribuído global de vários aplicativos](#multiple-app-global-assigned-access-profile)
1. [Perfil de acesso global atribuído a vários aplicativos, excluindo proprietários de dispositivo](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Perfil de acesso atribuído a vários aplicativos para uma conta local ou conta de usuário do AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Vários perfis de acesso atribuídos ao aplicativo para dois usuários do AAD ou mais](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Perfil de acesso atribuído a vários aplicativos para um grupo do AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Perfil de acesso atribuído a vários aplicativos para dois grupos do AAD ou mais](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Perfil de acesso atribuído a vários aplicativos para uma conta do AAD e um grupo do AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Perfil de acesso atribuído a vários aplicativos para visitantes](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Substitua as ações de tarefas pendentes de acordo com seus requisitos.

### <a name="multiple-app-global-assigned-access-profile"></a>Perfil de acesso atribuído global de vários aplicativos

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Perfil de acesso global atribuído a vários aplicativos, excluindo proprietários de dispositivo

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Perfil de acesso atribuído a vários aplicativos para uma conta local ou conta de usuário do AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Voltar para a lista](#kiosk-xml-code-samples) <br>
Retornar aos [cenários com suporte para o modo de quiosque com base no tipo de identidade](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Vários perfis de acesso atribuídos ao aplicativo para dois usuários do AAD ou mais

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
