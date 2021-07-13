---
title: WDAC (Controle de Aplicativos do Windows Defender)
description: visão geral sobre o que Windows Defender o controle de aplicativo é e como usá-lo para gerenciar HoloLens dispositivos de realidade misturada.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639923"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="3bc29-103">WDAC (Controle de Aplicativos do Windows Defender)</span><span class="sxs-lookup"><span data-stu-id="3bc29-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="3bc29-104">O WDAC permite que um administrador de ti Configure seus dispositivos para bloquear a inicialização de aplicativos em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3bc29-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="3bc29-105">Isso é diferente dos métodos de restrição de dispositivo, como o modo de quiosque, em que o usuário recebe uma interface de usuário que oculta os aplicativos no dispositivo, mas eles ainda podem ser iniciados.</span><span class="sxs-lookup"><span data-stu-id="3bc29-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="3bc29-106">Embora o WDAC seja implementado, os aplicativos ainda estão visíveis na lista todos os aplicativos, mas o WDAC interrompe a inicialização desses aplicativos e processos pelo usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3bc29-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="3bc29-107">Um dispositivo pode ser atribuído a mais de uma política WDAC.</span><span class="sxs-lookup"><span data-stu-id="3bc29-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="3bc29-108">Se várias políticas WDAC estiverem definidas em um sistema, as mais restritivas entrarão em vigor.</span><span class="sxs-lookup"><span data-stu-id="3bc29-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="3bc29-109">quando os usuários finais tentarem iniciar um aplicativo que está bloqueado pelo WDAC, em HoloLens eles não receberão uma notificação sobre não conseguir iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3bc29-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="3bc29-110">veja a seguir um guia para os usuários aprenderem a [usar o WDAC e Windows PowerShell para permitir ou bloquear aplicativos em HoloLens 2 dispositivos com Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="3bc29-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="3bc29-111">quando os usuários pesquisam aplicativos instalados em seu computador Windows 10 usando a primeira etapa de exemplo, talvez precisem fazer algumas tentativas para restringir os resultados.</span><span class="sxs-lookup"><span data-stu-id="3bc29-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="3bc29-112">Se você não souber o nome completo do pacote, talvez seja necessário executar ' Get-AppxPackage-name \* YourBestGuess \* ' algumas vezes para encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="3bc29-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="3bc29-113">Depois de ter o nome, execute ' $package 1 = Get-AppxPackage-Name real. PackageName '</span><span class="sxs-lookup"><span data-stu-id="3bc29-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="3bc29-114">por exemplo, executar o seguinte para Microsoft Edge retornará mais de um resultado, mas nessa lista você pode identificar que o nome completo de que você precisa é Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="3bc29-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="3bc29-115">Nomes de família de pacotes para aplicativos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="3bc29-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="3bc29-116">no guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que são instalados apenas em HoloLens com seus nomes de família de pacotes.</span><span class="sxs-lookup"><span data-stu-id="3bc29-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="3bc29-117">Às vezes, há aplicativos que você pode usar para usar que não estejam no computador desktop que você deseja adicionar à política.</span><span class="sxs-lookup"><span data-stu-id="3bc29-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="3bc29-118">aqui está uma lista de aplicativos comumente usados e In-Box para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3bc29-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="3bc29-119">Nome do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="3bc29-119">App Name</span></span>                   | <span data-ttu-id="3bc29-120">Package Family Name</span><span class="sxs-lookup"><span data-stu-id="3bc29-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="3bc29-121">Visualizador 3D</span><span class="sxs-lookup"><span data-stu-id="3bc29-121">3D Viewer</span></span>                  | <span data-ttu-id="3bc29-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="3bc29-123">Instalador de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="3bc29-123">App Installer</span></span>              | <span data-ttu-id="3bc29-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3bc29-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="3bc29-125">Calendário</span><span class="sxs-lookup"><span data-stu-id="3bc29-125">Calendar</span></span>                   | <span data-ttu-id="3bc29-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="3bc29-127">Câmera</span><span class="sxs-lookup"><span data-stu-id="3bc29-127">Camera</span></span>                     | <span data-ttu-id="3bc29-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="3bc29-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="3bc29-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="3bc29-129">Cortana</span></span>                    | <span data-ttu-id="3bc29-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="3bc29-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="3bc29-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="3bc29-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="3bc29-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="3bc29-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="3bc29-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="3bc29-135">Hub de Feedback</span><span class="sxs-lookup"><span data-stu-id="3bc29-135">Feedback Hub</span></span>               | <span data-ttu-id="3bc29-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="3bc29-137">Explorador de Arquivos</span><span class="sxs-lookup"><span data-stu-id="3bc29-137">File Explorer</span></span>              | <span data-ttu-id="3bc29-138">c5e2524a-EA46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="3bc29-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="3bc29-139">Email</span><span class="sxs-lookup"><span data-stu-id="3bc29-139">Mail</span></span>                       | <span data-ttu-id="3bc29-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="3bc29-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="3bc29-141">Microsoft Store</span></span>            | <span data-ttu-id="3bc29-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="3bc29-143">Filmes e TV</span><span class="sxs-lookup"><span data-stu-id="3bc29-143">Movies & TV</span></span>                | <span data-ttu-id="3bc29-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="3bc29-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="3bc29-145">OneDrive</span></span>                   | <span data-ttu-id="3bc29-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="3bc29-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="3bc29-147">Photos</span></span>                     | <span data-ttu-id="3bc29-148">O. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="3bc29-149">Configurações</span><span class="sxs-lookup"><span data-stu-id="3bc29-149">Settings</span></span>                   | <span data-ttu-id="3bc29-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="3bc29-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="3bc29-151">Dicas</span><span class="sxs-lookup"><span data-stu-id="3bc29-151">Tips</span></span>                       | <span data-ttu-id="3bc29-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="3bc29-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="3bc29-153">1-o instalador do aplicativo de bloqueio só bloqueará o aplicativo instalador de aplicativos e não os aplicativos instalados de outras fontes, como o Microsoft Store ou a partir de sua solução de MDM.</span><span class="sxs-lookup"><span data-stu-id="3bc29-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="3bc29-154">Como localizar um nome de família de pacotes</span><span class="sxs-lookup"><span data-stu-id="3bc29-154">How to find a Package Family Name</span></span>

<span data-ttu-id="3bc29-155">se um aplicativo não estiver nessa lista, um usuário poderá usar o Portal do dispositivo, conectado a um HoloLens 2 que instalou o aplicativo desejado para ser bloqueado, a fim de determinar o PackageRelativeID e a partir daí, obtenha o PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="3bc29-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="3bc29-156">instale o aplicativo em seu dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3bc29-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="3bc29-157">abra atualizações de Configurações > & Security-> para desenvolvedores e habilite o **modo de desenvolvedor** e o portal do **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="3bc29-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="3bc29-158">Mais instruções detalhadas lêem mais sobre [a instalação e o uso do portal do dispositivo aqui](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="3bc29-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="3bc29-159">Depois que o portal do dispositivo estiver conectado, navegue até **exibições** e, em seguida, **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3bc29-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="3bc29-160">No painel aplicativos instalados, use a lista suspensa para selecionar o aplicativo instalado.</span><span class="sxs-lookup"><span data-stu-id="3bc29-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="3bc29-161">Localize o PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="3bc29-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="3bc29-162">Copie os caracteres do aplicativo antes do!, esses caracteres serão seus PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="3bc29-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


