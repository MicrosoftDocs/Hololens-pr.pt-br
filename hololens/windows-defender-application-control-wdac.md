---
title: WDAC (Controle de Aplicativos do Windows Defender)
description: Visão geral sobre o Windows Defender de aplicativos e como usá-lo para gerenciar HoloLens de realidade misturada.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032034"
---
# <a name="windows-defender-application-control---wdac"></a>WDAC (Controle de Aplicativos do Windows Defender)

## <a name="overview"></a>Visão geral

O WDAC permite que você configure HoloLens bloquear o lançamento de aplicativos. Ele é diferente do modo quiosque, em que a interface do usuário oculta os aplicativos, mas eles ainda podem ser lançados. Com o WDAC, você pode ver os aplicativos, mas eles não podem ser lançados.

> [!NOTE]
> Quando os usuários finais tentarem iniciar um aplicativo bloqueado pelo WDAC no HoloLens, eles não serão notificados sobre a não capacidade de iniciar o aplicativo.

Um dispositivo pode ser atribuído a mais de uma política WDAC. Se várias políticas WDAC são definidas em um sistema, a maioria das restritivas tem efeito. 

Veja a seguir um guia para os usuários aprenderem a usar o [WDAC](/mem/intune/configuration/custom-profile-hololens)e o Windows PowerShell para permitir ou bloquear aplicativos em HoloLens 2 dispositivos com Microsoft Intune .

Quando os usuários pesquisam aplicativos instalados em seu computador Windows 10 usando a primeira etapa de exemplo, talvez eles precisem fazer algumas tentativas para restringir os resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se você não sabe o nome completo do pacote, talvez seja necessário executar 'Get-AppxPackage -name \* YourPackGuess' algumas vezes para \* encontrá-lo. Em seguida, depois que o nome é executado '$package 1 = Get-AppxPackage -name Actual.PackageName'

Por exemplo, executar o código a seguir para Microsoft Edge retornará mais de um resultado, mas nessa lista você pode identificar que o nome completo de que você precisa é Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Nomes de família de pacotes para aplicativos HoloLens

No guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que são instalados apenas no HoloLens com seus nomes de família de pacotes. Às vezes, há aplicativos que você pode usar que não estão em seu computador desktop que você deseja adicionar à política.

Aqui está uma lista de aplicativos mais usados e In-Box para HoloLens 2 dispositivos.

| Nome do Aplicativo                   | Package Family Name                                |
|----------------------------|----------------------------------------------------|
| Visualizador 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalador de Aplicativo              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendário                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Câmera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub de Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorador de Arquivos              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Email                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmes e TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Configurações                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Dicas                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - Bloquear Instalador de Aplicativo bloqueará apenas o aplicativo Instalador de Aplicativo e não os aplicativos instalados de outras fontes, como o Microsoft Store ou da sua solução de MDM.

### <a name="how-to-find-a-package-family-name"></a>Como encontrar um nome de família de pacotes

Se um aplicativo não estiver nessa lista, um usuário poderá usar o Portal de Dispositivos conectado a um HoloLens 2 que instalou o aplicativo para determinar o PackageRelativeID e, de lá, obter o PackageFamilyName.

1. Instale o aplicativo em seu HoloLens 2. 
1. Abra Configurações -> atualizações & segurança -> para desenvolvedores e habilita o Modo de desenvolvedor e, em seguida, **o Portal do dispositivo**.  
    1. Mais instruções de detalhes leia mais sobre a [instalação e o uso do portal do dispositivo aqui.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Depois Portal de Dispositivos estiver conectado, navegue até **Exibições e,** em seguida, **Aplicativos**. 
1. No painel Aplicativos Instalados, use o menu suspenso para selecionar o aplicativo instalado. 
1. Localize PackageRelativeID. 
1. Copie os caracteres do aplicativo antes `!` do , esses caracteres serão o PackageFamilyName.

