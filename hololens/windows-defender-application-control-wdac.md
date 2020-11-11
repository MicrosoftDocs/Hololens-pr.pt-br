---
title: Controle de Aplicativos do Windows Defender - WDAC
description: Visão geral do que o WDAC é e como usar para gerenciar dispositivos HoloLens.
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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163122"
---
# Controle de Aplicativos do Windows Defender - WDAC

O WDAC permite que um administrador de ti Configure seus dispositivos para bloquear a inicialização de aplicativos em dispositivos. Isso é diferente dos métodos de restrição de dispositivo, como o modo de quiosque, em que o usuário recebe uma interface do usuário que oculta os aplicativos no dispositivo, mas ainda pode ser iniciado. Embora o WDAC seja implementado, os aplicativos ainda ficam visíveis na lista todos os aplicativos, mas o WDAC interrompe esses aplicativos e processos da capacidade de inicialização pelo usuário do dispositivo.

Um dispositivo pode ter sido atribuído a mais de uma política WDAC. Se várias políticas WDAC estiverem definidas em um sistema, a maioria delas entrará em vigor. 

> [!NOTE]
> Quando os usuários finais tentam iniciar um aplicativo bloqueado pelo WDAC, o HoloLens não recebe uma notificação sobre não ser capaz de iniciar esse aplicativo.

Veja a seguir um guia para que os usuários aprendam a [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em dispositivos do HoloLens 2 com o Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Quando os usuários pesquisam aplicativos instalados em seu PC com Windows 10 usando o primeiro exemplo de etapa, talvez precisem fazer algumas tentativas para restringir os resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Se você não souber o nome completo do pacote, talvez seja necessário executar ' Get-AppxPackage-Name \ * YourBestGuess \ * ' algumas vezes para encontrá-lo. Depois que você tiver o nome executar ' $package 1 = Get-AppxPackage-Name real. PackageName '

Por exemplo, ao executar o seguinte para Edge retornará mais de um resultado, mas nessa lista, você pode identificar que o nome completo de que você precisa é o Microsoft. MicrosoftEdge. 

```powershell
Get-AppxPackage -name *edge*
``` 

## Pacote de nomes de família para aplicativos no HoloLens

No guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que são instalados somente no HoloLens com os nomes da família de pacotes. Às vezes, há aplicativos que você pode usar para usar que não estão no seu computador desktop que você deseja adicionar à política. 

Aqui está uma lista dos aplicativos comumente usados e In-Box para dispositivos do HoloLens 2.

| Nome do aplicativo                   | Nome da família de pacotes                                |
|----------------------------|----------------------------------------------------|
| Visualizador 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalador de Aplicativo              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendário                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Câmera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Guias do Dynamics 365        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Assistência Remota do Dynamics 365 | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Hub de Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorador de Arquivos              | c5e2524a-EA46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmes e TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Configurações                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Dicas                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 – o instalador do aplicativo de bloqueio só bloqueará o app Installer app e não os aplicativos instalados de outras fontes, como a Microsoft Store ou da solução MDM.

### Como encontrar o nome da família de pacotes

Se um aplicativo não estiver nesta lista, um usuário poderá usar o Device portal, conectado a um HoloLens 2 que tenha instalado o aplicativo para ser bloqueado, para determinar o PackageRelativeID e de lá, acesse o PackageFamilyName.

1. Instale o aplicativo em seu dispositivo do HoloLens 2. 
1. Abra configurações-> atualizações & segurança-> para desenvolvedores e habilite o **modo de desenvolvedor** e o **Device portal**. 
    1. Mais instruções de detalhes Leia mais sobre [a configuração e o uso do Device portal aqui](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Após a conexão do Device portal, navegue até **modos de exibição** e **aplicativos**. 
1. No painel aplicativos instalados, use a lista suspensa para selecionar o aplicativo instalado. 
1. Localize o PackageRelativeID. 
1. Copiar caracteres do aplicativo antes de!, este será o seu PackageFamilyName.


