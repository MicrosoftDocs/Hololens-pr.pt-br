---
title: Controle de aplicativos do Windows Defender – WDAC
description: Visão geral sobre o que é o controle de aplicativos do Windows Defender e como usá-lo para gerenciar dispositivos de realidade misturada do HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308114"
---
# <a name="windows-defender-application-control---wdac"></a>Controle de aplicativos do Windows Defender – WDAC

O WDAC permite que um administrador de ti Configure seus dispositivos para bloquear a inicialização de aplicativos em dispositivos. Isso é diferente dos métodos de restrição de dispositivo, como o modo de quiosque, em que o usuário recebe uma interface de usuário que oculta os aplicativos no dispositivo, mas eles ainda podem ser iniciados. Embora o WDAC seja implementado, os aplicativos ainda estão visíveis na lista todos os aplicativos, mas o WDAC interrompe a inicialização desses aplicativos e processos pelo usuário do dispositivo.

Um dispositivo pode ser atribuído a mais de uma política WDAC. Se várias políticas WDAC estiverem definidas em um sistema, as mais restritivas entrarão em vigor. 

> [!NOTE]
> Quando os usuários finais tentarem iniciar um aplicativo que está bloqueado pelo WDAC, no HoloLens, eles não receberão uma notificação sobre não conseguir iniciar o aplicativo.

Veja a seguir um guia para os usuários aprenderem a [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em dispositivos do HoloLens 2 com o Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Quando os usuários pesquisam aplicativos instalados em seu PC com Windows 10 usando a primeira etapa de exemplo, eles podem precisar fazer algumas tentativas para restringir os resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se você não souber o nome completo do pacote, talvez seja necessário executar ' Get-AppxPackage-name \* YourBestGuess \* ' algumas vezes para encontrá-lo. Depois de ter o nome, execute ' $package 1 = Get-AppxPackage-Name real. PackageName '

Por exemplo, a execução do seguinte para o Microsoft Edge retornará mais de um resultado, mas nessa lista você pode identificar que o nome completo de que você precisa é Microsoft. MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Empacotar nomes de família para aplicativos no HoloLens

No guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que são instalados somente no HoloLens com seus nomes de família de pacotes. Às vezes, há aplicativos que você pode usar para usar que não estejam no computador desktop que você deseja adicionar à política.

Aqui está uma lista de aplicativos comumente usados e In-Box para dispositivos do HoloLens 2.

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
| Explorador de Arquivos              | c5e2524a-EA46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Email                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmes e TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Configurações                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Dicas                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-o instalador do aplicativo de bloqueio só bloqueará o aplicativo instalador de aplicativos e não os aplicativos instalados de outras fontes, como o Microsoft Store ou a partir de sua solução de MDM.

### <a name="how-to-find-a-package-family-name"></a>Como localizar um nome de família de pacotes

Se um aplicativo não estiver nessa lista, um usuário poderá usar o portal do dispositivo, conectado a um HoloLens 2 que instalou o aplicativo desejado para ser bloqueado, a fim de determinar o PackageRelativeID e daí obter o PackageFamilyName.

1. Instale o aplicativo em seu dispositivo de HoloLens 2. 
1. Abra configurações-> atualizações & Security-> para desenvolvedores e habilite o **modo de desenvolvedor** e o portal do **dispositivo**. 
    1. Mais instruções detalhadas lêem mais sobre [a instalação e o uso do portal do dispositivo aqui](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Depois que o portal do dispositivo estiver conectado, navegue até **exibições** e, em seguida, **aplicativos**. 
1. No painel aplicativos instalados, use a lista suspensa para selecionar o aplicativo instalado. 
1. Localize o PackageRelativeID. 
1. Copie os caracteres do aplicativo antes do!, esses caracteres serão seus PackageFamilyName.


