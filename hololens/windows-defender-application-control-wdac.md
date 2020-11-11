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
# <span data-ttu-id="8e284-103">Controle de Aplicativos do Windows Defender - WDAC</span><span class="sxs-lookup"><span data-stu-id="8e284-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="8e284-104">O WDAC permite que um administrador de ti Configure seus dispositivos para bloquear a inicialização de aplicativos em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8e284-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="8e284-105">Isso é diferente dos métodos de restrição de dispositivo, como o modo de quiosque, em que o usuário recebe uma interface do usuário que oculta os aplicativos no dispositivo, mas ainda pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="8e284-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="8e284-106">Embora o WDAC seja implementado, os aplicativos ainda ficam visíveis na lista todos os aplicativos, mas o WDAC interrompe esses aplicativos e processos da capacidade de inicialização pelo usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8e284-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="8e284-107">Um dispositivo pode ter sido atribuído a mais de uma política WDAC.</span><span class="sxs-lookup"><span data-stu-id="8e284-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="8e284-108">Se várias políticas WDAC estiverem definidas em um sistema, a maioria delas entrará em vigor.</span><span class="sxs-lookup"><span data-stu-id="8e284-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="8e284-109">Quando os usuários finais tentam iniciar um aplicativo bloqueado pelo WDAC, o HoloLens não recebe uma notificação sobre não ser capaz de iniciar esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8e284-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="8e284-110">Veja a seguir um guia para que os usuários aprendam a [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em dispositivos do HoloLens 2 com o Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="8e284-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="8e284-111">Quando os usuários pesquisam aplicativos instalados em seu PC com Windows 10 usando o primeiro exemplo de etapa, talvez precisem fazer algumas tentativas para restringir os resultados.</span><span class="sxs-lookup"><span data-stu-id="8e284-111">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="8e284-112">Se você não souber o nome completo do pacote, talvez seja necessário executar ' Get-AppxPackage-Name \ \* YourBestGuess \ \* ' algumas vezes para encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="8e284-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="8e284-113">Depois que você tiver o nome executar ' $package 1 = Get-AppxPackage-Name real. PackageName '</span><span class="sxs-lookup"><span data-stu-id="8e284-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="8e284-114">Por exemplo, ao executar o seguinte para Edge retornará mais de um resultado, mas nessa lista, você pode identificar que o nome completo de que você precisa é o Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="8e284-114">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="8e284-115">Pacote de nomes de família para aplicativos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="8e284-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="8e284-116">No guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que são instalados somente no HoloLens com os nomes da família de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8e284-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="8e284-117">Às vezes, há aplicativos que você pode usar para usar que não estão no seu computador desktop que você deseja adicionar à política.</span><span class="sxs-lookup"><span data-stu-id="8e284-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="8e284-118">Aqui está uma lista dos aplicativos comumente usados e In-Box para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8e284-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="8e284-119">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="8e284-119">App Name</span></span>                   | <span data-ttu-id="8e284-120">Nome da família de pacotes</span><span class="sxs-lookup"><span data-stu-id="8e284-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="8e284-121">Visualizador 3D</span><span class="sxs-lookup"><span data-stu-id="8e284-121">3D Viewer</span></span>                  | <span data-ttu-id="8e284-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="8e284-123">Instalador de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8e284-123">App Installer</span></span>              | <span data-ttu-id="8e284-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="8e284-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="8e284-125">Calendário</span><span class="sxs-lookup"><span data-stu-id="8e284-125">Calendar</span></span>                   | <span data-ttu-id="8e284-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="8e284-127">Câmera</span><span class="sxs-lookup"><span data-stu-id="8e284-127">Camera</span></span>                     | <span data-ttu-id="8e284-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="8e284-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="8e284-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="8e284-129">Cortana</span></span>                    | <span data-ttu-id="8e284-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="8e284-131">Guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8e284-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="8e284-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="8e284-133">Assistência Remota do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8e284-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="8e284-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="8e284-135">Hub de Feedback</span><span class="sxs-lookup"><span data-stu-id="8e284-135">Feedback Hub</span></span>               | <span data-ttu-id="8e284-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="8e284-137">Explorador de Arquivos</span><span class="sxs-lookup"><span data-stu-id="8e284-137">File Explorer</span></span>              | <span data-ttu-id="8e284-138">c5e2524a-EA46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="8e284-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="8e284-139">Mail</span><span class="sxs-lookup"><span data-stu-id="8e284-139">Mail</span></span>                       | <span data-ttu-id="8e284-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="8e284-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8e284-141">Microsoft Store</span></span>            | <span data-ttu-id="8e284-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="8e284-143">Filmes e TV</span><span class="sxs-lookup"><span data-stu-id="8e284-143">Movies & TV</span></span>                | <span data-ttu-id="8e284-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="8e284-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="8e284-145">OneDrive</span></span>                   | <span data-ttu-id="8e284-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="8e284-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="8e284-147">Photos</span></span>                     | <span data-ttu-id="8e284-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="8e284-149">Configurações</span><span class="sxs-lookup"><span data-stu-id="8e284-149">Settings</span></span>                   | <span data-ttu-id="8e284-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="8e284-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="8e284-151">Dicas</span><span class="sxs-lookup"><span data-stu-id="8e284-151">Tips</span></span>                       | <span data-ttu-id="8e284-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="8e284-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="8e284-153">1 – o instalador do aplicativo de bloqueio só bloqueará o app Installer app e não os aplicativos instalados de outras fontes, como a Microsoft Store ou da solução MDM.</span><span class="sxs-lookup"><span data-stu-id="8e284-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="8e284-154">Como encontrar o nome da família de pacotes</span><span class="sxs-lookup"><span data-stu-id="8e284-154">How to find a Package Family Name</span></span>

<span data-ttu-id="8e284-155">Se um aplicativo não estiver nesta lista, um usuário poderá usar o Device portal, conectado a um HoloLens 2 que tenha instalado o aplicativo para ser bloqueado, para determinar o PackageRelativeID e de lá, acesse o PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="8e284-155">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="8e284-156">Instale o aplicativo em seu dispositivo do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8e284-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="8e284-157">Abra configurações-> atualizações & segurança-> para desenvolvedores e habilite o **modo de desenvolvedor** e o **Device portal**.</span><span class="sxs-lookup"><span data-stu-id="8e284-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="8e284-158">Mais instruções de detalhes Leia mais sobre [a configuração e o uso do Device portal aqui](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="8e284-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="8e284-159">Após a conexão do Device portal, navegue até **modos de exibição** e **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="8e284-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="8e284-160">No painel aplicativos instalados, use a lista suspensa para selecionar o aplicativo instalado.</span><span class="sxs-lookup"><span data-stu-id="8e284-160">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="8e284-161">Localize o PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="8e284-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="8e284-162">Copiar caracteres do aplicativo antes de!, este será o seu PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="8e284-162">Copy app characters before the !, this will be your PackageFamilyName.</span></span>


