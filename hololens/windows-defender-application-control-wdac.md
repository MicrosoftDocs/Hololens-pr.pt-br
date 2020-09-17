---
title: Controle de aplicativo do Windows Defender-WDAC
description: Visão geral do que o WDAC é e como usar para gerenciar dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016754"
---
# <span data-ttu-id="6c897-103">Controle de aplicativo do Windows Defender-WDAC</span><span class="sxs-lookup"><span data-stu-id="6c897-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="6c897-104">O WDAC permite que um administrador de ti Configure seus dispositivos para bloquear a inicialização de aplicativos em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6c897-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="6c897-105">Isso é diferente dos métodos de restrição de dispositivo, como o modo de quiosque, em que o usuário recebe uma interface do usuário que oculta os aplicativos no dispositivo, mas ainda pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="6c897-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="6c897-106">Embora o WDAC seja implementado, os aplicativos ainda ficam visíveis na lista todos os aplicativos, mas o WDAC interrompe esses aplicativos e processos da capacidade de inicialização pelo usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6c897-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="6c897-107">Quando os usuários finais tentam iniciar um aplicativo bloqueado pelo WDAC, o HoloLens não recebe uma notificação sobre não ser capaz de iniciar esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6c897-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="6c897-108">Veja a seguir um guia para que os usuários aprendam a [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em dispositivos do HoloLens 2 com o Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="6c897-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="6c897-109">Quando os usuários pesquisam aplicativos instalados em seu PC com Windows 10 usando o primeiro exemplo de etapa, talvez precisem fazer algumas tentativas para restringir os resultados.</span><span class="sxs-lookup"><span data-stu-id="6c897-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="6c897-110">Se você não souber o nome completo do pacote, talvez seja necessário executar ' Get-AppxPackage-Name \ \* YourBestGuess \ \* ' algumas vezes para encontrá-lo.</span><span class="sxs-lookup"><span data-stu-id="6c897-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="6c897-111">Depois disso, você terá o nome "$package 1 = Get-AppxPackage-Name real. PackageName '</span><span class="sxs-lookup"><span data-stu-id="6c897-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="6c897-112">Por exemplo, ao executar o seguinte para Edge retornará mais de um resultado, mas nessa lista, você pode identificar que o nome completo de que você precisa é o Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="6c897-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="6c897-113">Pacote de nomes de família para aplicativos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="6c897-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="6c897-114">No guia vinculado acima, você pode editar manualmente newPolicy.xml e adicionar regras para aplicativos que são instalados somente no HoloLens com os nomes da família de pacotes.</span><span class="sxs-lookup"><span data-stu-id="6c897-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="6c897-115">Às vezes, há aplicativos que você pode usar para usar que não estão no seu computador desktop que você deseja adicionar à política.</span><span class="sxs-lookup"><span data-stu-id="6c897-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="6c897-116">Aqui está uma lista de aplicativos comumente usados e na caixa para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6c897-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="6c897-117">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="6c897-117">App Name</span></span>                   | <span data-ttu-id="6c897-118">Nome da família de pacotes</span><span class="sxs-lookup"><span data-stu-id="6c897-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="6c897-119">Visualizador 3D</span><span class="sxs-lookup"><span data-stu-id="6c897-119">3D Viewer</span></span>                  | <span data-ttu-id="6c897-120">Microsoft. Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="6c897-121">Calendário</span><span class="sxs-lookup"><span data-stu-id="6c897-121">Calendar</span></span>                   | <span data-ttu-id="6c897-122">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="6c897-123">Câmera</span><span class="sxs-lookup"><span data-stu-id="6c897-123">Camera</span></span>                     | <span data-ttu-id="6c897-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="6c897-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="6c897-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="6c897-125">Cortana</span></span>                    | <span data-ttu-id="6c897-126">Microsoft. 549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="6c897-127">Guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6c897-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="6c897-128">Microsoft. Dynamics365. Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="6c897-129">Assistência Remota do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6c897-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="6c897-130">Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="6c897-131">Hub de Feedback</span><span class="sxs-lookup"><span data-stu-id="6c897-131">Feedback Hub</span></span>               | <span data-ttu-id="6c897-132">Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="6c897-133">Explorador de Arquivos</span><span class="sxs-lookup"><span data-stu-id="6c897-133">File Explorer</span></span>              | <span data-ttu-id="6c897-134">c5e2524a-EA46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="6c897-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="6c897-135">Mail</span><span class="sxs-lookup"><span data-stu-id="6c897-135">Mail</span></span>                       | <span data-ttu-id="6c897-136">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="6c897-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6c897-137">Microsoft Store</span></span>            | <span data-ttu-id="6c897-138">Microsoft. WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="6c897-139">Filmes e TV</span><span class="sxs-lookup"><span data-stu-id="6c897-139">Movies & TV</span></span>                | <span data-ttu-id="6c897-140">Microsoft. ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="6c897-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6c897-141">OneDrive</span></span>                   | <span data-ttu-id="6c897-142">Microsoft. microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="6c897-143">Fotos</span><span class="sxs-lookup"><span data-stu-id="6c897-143">Photos</span></span>                     | <span data-ttu-id="6c897-144">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="6c897-145">Configurações</span><span class="sxs-lookup"><span data-stu-id="6c897-145">Settings</span></span>                   | <span data-ttu-id="6c897-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="6c897-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="6c897-147">Dicas</span><span class="sxs-lookup"><span data-stu-id="6c897-147">Tips</span></span>                       | <span data-ttu-id="6c897-148">Microsoft. HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="6c897-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="6c897-149">Se um aplicativo não estiver nesta lista, um usuário poderá usar o Device portal, conectado a um HoloLens 2 que tenha instalado o aplicativo para ser bloqueado, para determinar o PackageRelativeID e de lá, acesse o PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="6c897-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="6c897-150">Instale o aplicativo em seu dispositivo do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6c897-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="6c897-151">Abra configurações-> atualizações & equilibrar-> para desenvolvedores e habilite o **modo de desenvolvedor** e depois o **Device portal**.</span><span class="sxs-lookup"><span data-stu-id="6c897-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="6c897-152">Mais instruções de detalhes Leia mais sobre [a configuração e o uso do Device portal aqui](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="6c897-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="6c897-153">Após a conexão do Device portal, navegue até **modos de exibição** e **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="6c897-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="6c897-154">No painel aplicativos instalados, use a lista suspensa para selecionar o aplicativo instalado.</span><span class="sxs-lookup"><span data-stu-id="6c897-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="6c897-155">Localize o PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="6c897-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="6c897-156">Copiar caracteres do aplicativo antes de!, este será o seu PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="6c897-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

