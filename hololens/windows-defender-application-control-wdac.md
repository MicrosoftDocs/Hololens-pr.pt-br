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
# <span data-ttu-id="9e1ad-103">Controle de Aplicativos do Windows Defender - WDAC</span><span class="sxs-lookup"><span data-stu-id="9e1ad-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="9e1ad-104">O WDAC permite que um administrador de IT configure seus dispositivos para bloquear a iniciação de aplicativos em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="9e1ad-105">Isso é diferente dos métodos de restrição de dispositivo, como o modo quiosque, em que o usuário é apresentado a uma interface do usuário que oculta os aplicativos no dispositivo, mas ele ainda pode ser lançado.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="9e1ad-106">Enquanto o WDAC é implementado, os aplicativos ainda ficam visíveis na lista Todos os Aplicativos, mas o WDAC impede que esses aplicativos e processos sejam abertos pelo usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="9e1ad-107">Um dispositivo pode ser atribuído a mais de uma política do WDAC.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="9e1ad-108">Se várias políticas do WDAC são definidas em um sistema, as mais restritivas têm efeito.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="9e1ad-109">Quando os usuários finais tentarem iniciar um aplicativo bloqueado pelo WDAC, no HoloLens eles não receberão uma notificação sobre como não conseguir iniciar esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="9e1ad-110">Veja a seguir um guia para que os usuários aprendam a usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em [dispositivos HoloLens 2 com o Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)</span><span class="sxs-lookup"><span data-stu-id="9e1ad-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="9e1ad-111">Quando os usuários pesquisam aplicativos instalados em seu computador Windows 10 usando a primeira etapa de exemplo, talvez eles precisem fazer algumas tentativas de restringir os resultados.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="9e1ad-112">Se você não sabe o nome completo do pacote, talvez seja necessário executar 'Get-AppxPackage -name \*YourBestGuess\*' algumas vezes para encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="9e1ad-113">Em seguida, depois de executar o nome '$package 1 = Get-AppxPackage -name Actual.PackageName'</span><span class="sxs-lookup"><span data-stu-id="9e1ad-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="9e1ad-114">Por exemplo, executar o seguinte para o Microsoft Edge retornará mais de um resultado, mas nessa lista você pode identificar que o nome completo necessário é Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="9e1ad-115">Nomes de Família de Pacotes para aplicativos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="9e1ad-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="9e1ad-116">No guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que só são instalados no HoloLens com seus nomes de família de pacotes.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="9e1ad-117">Às vezes, há aplicativos que você pode usar que não estão em seu computador desktop que você deseja adicionar à política.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="9e1ad-118">Aqui está uma lista de aplicativos mais usados e In-Box para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="9e1ad-119">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9e1ad-119">App Name</span></span>                   | <span data-ttu-id="9e1ad-120">Nome da Família de Pacotes</span><span class="sxs-lookup"><span data-stu-id="9e1ad-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="9e1ad-121">Visualizador 3D</span><span class="sxs-lookup"><span data-stu-id="9e1ad-121">3D Viewer</span></span>                  | <span data-ttu-id="9e1ad-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="9e1ad-123">Instalador de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9e1ad-123">App Installer</span></span>              | <span data-ttu-id="9e1ad-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="9e1ad-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="9e1ad-125">Calendário</span><span class="sxs-lookup"><span data-stu-id="9e1ad-125">Calendar</span></span>                   | <span data-ttu-id="9e1ad-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="9e1ad-127">Câmera</span><span class="sxs-lookup"><span data-stu-id="9e1ad-127">Camera</span></span>                     | <span data-ttu-id="9e1ad-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="9e1ad-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="9e1ad-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="9e1ad-129">Cortana</span></span>                    | <span data-ttu-id="9e1ad-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="9e1ad-131">Guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9e1ad-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="9e1ad-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="9e1ad-133">Assistência Remota do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9e1ad-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="9e1ad-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="9e1ad-135">Hub de Feedback</span><span class="sxs-lookup"><span data-stu-id="9e1ad-135">Feedback Hub</span></span>               | <span data-ttu-id="9e1ad-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="9e1ad-137">Explorador de Arquivos</span><span class="sxs-lookup"><span data-stu-id="9e1ad-137">File Explorer</span></span>              | <span data-ttu-id="9e1ad-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="9e1ad-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="9e1ad-139">Mail</span><span class="sxs-lookup"><span data-stu-id="9e1ad-139">Mail</span></span>                       | <span data-ttu-id="9e1ad-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="9e1ad-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9e1ad-141">Microsoft Store</span></span>            | <span data-ttu-id="9e1ad-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="9e1ad-143">Filmes e TV</span><span class="sxs-lookup"><span data-stu-id="9e1ad-143">Movies & TV</span></span>                | <span data-ttu-id="9e1ad-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="9e1ad-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="9e1ad-145">OneDrive</span></span>                   | <span data-ttu-id="9e1ad-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="9e1ad-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="9e1ad-147">Photos</span></span>                     | <span data-ttu-id="9e1ad-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="9e1ad-149">Configurações</span><span class="sxs-lookup"><span data-stu-id="9e1ad-149">Settings</span></span>                   | <span data-ttu-id="9e1ad-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="9e1ad-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="9e1ad-151">Dicas</span><span class="sxs-lookup"><span data-stu-id="9e1ad-151">Tips</span></span>                       | <span data-ttu-id="9e1ad-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="9e1ad-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="9e1ad-153">1 - Bloquear o Instalador de Aplicativo bloqueará apenas o aplicativo Instalador de Aplicativo, e não os aplicativos instalados de outras fontes, como a Microsoft Store ou de sua solução MDM.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="9e1ad-154">Como encontrar um nome de família de pacotes</span><span class="sxs-lookup"><span data-stu-id="9e1ad-154">How to find a Package Family Name</span></span>

<span data-ttu-id="9e1ad-155">Se um aplicativo não estiver nessa lista, um usuário poderá usar o Device Portal, conectado a um HoloLens 2 que tenha instalado o aplicativo para ser bloqueado, para determinar PackageRelativeID e, de lá, obter o PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="9e1ad-156">Instale o aplicativo em seu dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="9e1ad-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="9e1ad-158">Mais instruções de detalhes leia mais sobre a [instalação e o uso do device portal aqui.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="9e1ad-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="9e1ad-159">Depois que o Device Portal estiver conectado, navegue até **Exibições** e **Aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="9e1ad-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="9e1ad-160">No painel Aplicativos Instalados, use o menu suspenso para selecionar o aplicativo instalado.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="9e1ad-161">Localize PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="9e1ad-162">Copie os caracteres do aplicativo antes do !, esses caracteres serão seu PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="9e1ad-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


