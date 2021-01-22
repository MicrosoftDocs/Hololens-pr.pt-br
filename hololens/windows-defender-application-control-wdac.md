---
title: Controle de Aplicativos do Windows Defender - WDAC
description: Visão geral sobre o que é o Windows Defender Application Control e como usá-lo para gerenciar dispositivos de realidade misturada do HoloLens.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284132"
---
# Controle de Aplicativos do Windows Defender - WDAC

O WDAC permite que um administrador de IT configure seus dispositivos para bloquear a iniciação de aplicativos em dispositivos. Isso é diferente dos métodos de restrição de dispositivo, como o modo quiosque, em que o usuário é apresentado a uma interface do usuário que oculta os aplicativos no dispositivo, mas ele ainda pode ser lançado. Enquanto o WDAC é implementado, os aplicativos ainda ficam visíveis na lista Todos os Aplicativos, mas o WDAC impede que esses aplicativos e processos sejam abertos pelo usuário do dispositivo.

Um dispositivo pode ser atribuído a mais de uma política do WDAC. Se várias políticas do WDAC são definidas em um sistema, as mais restritivas têm efeito. 

> [!NOTE]
> Quando os usuários finais tentarem iniciar um aplicativo bloqueado pelo WDAC, no HoloLens eles não receberão uma notificação sobre como não conseguir iniciar esse aplicativo.

Veja a seguir um guia para que os usuários aprendam a usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em [dispositivos HoloLens 2 com o Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Quando os usuários pesquisam aplicativos instalados em seu computador Windows 10 usando a primeira etapa de exemplo, talvez eles precisem fazer algumas tentativas de restringir os resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se você não sabe o nome completo do pacote, talvez seja necessário executar 'Get-AppxPackage -name \*YourBestGuess\*' algumas vezes para encontrá-lo. Em seguida, depois de executar o nome '$package 1 = Get-AppxPackage -name Actual.PackageName'

Por exemplo, executar o seguinte para o Microsoft Edge retornará mais de um resultado, mas nessa lista você pode identificar que o nome completo necessário é Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## Nomes de Família de Pacotes para aplicativos no HoloLens

No guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que só são instalados no HoloLens com seus nomes de família de pacotes. Às vezes, há aplicativos que você pode usar que não estão em seu computador desktop que você deseja adicionar à política.

Aqui está uma lista de aplicativos mais usados e In-Box para dispositivos HoloLens 2.

| Nome do aplicativo                   | Nome da Família de Pacotes                                |
|----------------------------|----------------------------------------------------|
| Visualizador 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalador de Aplicativo              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendário                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Câmera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Guias do Dynamics 365        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Assistência Remota do Dynamics 365 | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub de Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorador de Arquivos              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmes e TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Configurações                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Dicas                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - Bloquear o Instalador de Aplicativo bloqueará apenas o aplicativo Instalador de Aplicativo, e não os aplicativos instalados de outras fontes, como a Microsoft Store ou de sua solução MDM.

### Como encontrar um nome de família de pacotes

Se um aplicativo não estiver nessa lista, um usuário poderá usar o Device Portal, conectado a um HoloLens 2 que tenha instalado o aplicativo para ser bloqueado, para determinar PackageRelativeID e, de lá, obter o PackageFamilyName.

1. Instale o aplicativo em seu dispositivo HoloLens 2. 
1. Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**. 
    1. Mais instruções de detalhes leia mais sobre a [instalação e o uso do device portal aqui.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Depois que o Device Portal estiver conectado, navegue até **Exibições** e **Aplicativos.** 
1. No painel Aplicativos Instalados, use o menu suspenso para selecionar o aplicativo instalado. 
1. Localize PackageRelativeID. 
1. Copie os caracteres do aplicativo antes do !, esses caracteres serão seu PackageFamilyName.


