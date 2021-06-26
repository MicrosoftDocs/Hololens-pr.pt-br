---
title: Atualizar HoloLens 2
description: Saiba como verificar seu número de Build do HoloLens, manter-se atualizado com as atualizações do dispositivo, ingressar no programa de pessoas e reverter atualizações.
keywords: como fazer, atualizar, reverter, HoloLens, verificar compilação, número de Build
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924104"
---
# <a name="update-hololens-2"></a><span data-ttu-id="7a198-104">Atualizar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7a198-104">Update HoloLens 2</span></span>

<span data-ttu-id="7a198-105">O HoloLens usa Windows Update, assim como outros dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7a198-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="7a198-106">Seu HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que ele estiver conectado à energia e conectado à Internet, mesmo quando ela estiver em espera.</span><span class="sxs-lookup"><span data-stu-id="7a198-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="7a198-107">Este artigo apresentará as ferramentas do HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="7a198-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="7a198-108">exibindo a versão atual do sistema operacional (número da versão)</span><span class="sxs-lookup"><span data-stu-id="7a198-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="7a198-109">verificando se há atualizações</span><span class="sxs-lookup"><span data-stu-id="7a198-109">checking for updates</span></span>
- <span data-ttu-id="7a198-110">atualizando manualmente o HoloLens</span><span class="sxs-lookup"><span data-stu-id="7a198-110">manually updating HoloLens</span></span>
- <span data-ttu-id="7a198-111">reverter para uma atualização mais antiga</span><span class="sxs-lookup"><span data-stu-id="7a198-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="7a198-112">Verificar a versão do sistema operacional (número da versão)</span><span class="sxs-lookup"><span data-stu-id="7a198-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="7a198-113">Você pode verificar o número de versão do sistema, (número da compilação) abrindo o aplicativo Configurações e selecionando **sistema**  >  **sobre**.</span><span class="sxs-lookup"><span data-stu-id="7a198-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="7a198-114">Verificar se há atualizações e atualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="7a198-114">Check for updates and manually update</span></span>

<span data-ttu-id="7a198-115">Você pode verificar se há atualizações a qualquer momento nas configurações.</span><span class="sxs-lookup"><span data-stu-id="7a198-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="7a198-116">Para ver as atualizações disponíveis e verificar se há novas atualizações:</span><span class="sxs-lookup"><span data-stu-id="7a198-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="7a198-117">Abra o aplicativo **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="7a198-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="7a198-118">Navegue até **Atualizar & segurança**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="7a198-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="7a198-119">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="7a198-119">Select **Check for updates**.</span></span>

<span data-ttu-id="7a198-120">Se uma atualização estiver disponível, ela começará a baixar a nova versão.</span><span class="sxs-lookup"><span data-stu-id="7a198-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="7a198-121">Após a conclusão do download, selecione o botão **reiniciar agora** para disparar a instalação.</span><span class="sxs-lookup"><span data-stu-id="7a198-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="7a198-122">Se o dispositivo estiver abaixo de 40% e não conectado, a reinicialização não iniciará a instalação da atualização.</span><span class="sxs-lookup"><span data-stu-id="7a198-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="7a198-123">Enquanto o seu HoloLens está instalando a atualização, ele exibirá engrenagens giratórias e um indicador de progresso.</span><span class="sxs-lookup"><span data-stu-id="7a198-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="7a198-124">Não desative seu HoloLens durante esse tempo.</span><span class="sxs-lookup"><span data-stu-id="7a198-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="7a198-125">Ele será reiniciado automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="7a198-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="7a198-126">O HoloLens aplica uma atualização por vez.</span><span class="sxs-lookup"><span data-stu-id="7a198-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="7a198-127">Se o seu HoloLens for mais de uma versão por trás do mais recente, talvez seja necessário executar o processo de atualização várias vezes para atualizá-lo completamente.</span><span class="sxs-lookup"><span data-stu-id="7a198-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="7a198-128">Voltar para uma versão anterior</span><span class="sxs-lookup"><span data-stu-id="7a198-128">Go back to a previous version</span></span>

<span data-ttu-id="7a198-129">Em alguns casos, talvez você queira voltar para uma versão anterior do software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7a198-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="7a198-130">As etapas recomendadas são:</span><span class="sxs-lookup"><span data-stu-id="7a198-130">The recommended steps are:</span></span>

1. <span data-ttu-id="7a198-131">Entre em contato com o suporte para ver se eles podem corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="7a198-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="7a198-132">Verifique se a telemetria **opcional** ou **completa** está habilitada-isso torna seu bug mais acionável e mais fácil para os engenheiros diagnosticarem.</span><span class="sxs-lookup"><span data-stu-id="7a198-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="7a198-133">Os [comentários de arquivo](hololens-feedback.md) são o mais descritivos possível.</span><span class="sxs-lookup"><span data-stu-id="7a198-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="7a198-134">Anote o título ou use o recurso de compartilhamento para que você possa compartilhar seu bug com o suporte.</span><span class="sxs-lookup"><span data-stu-id="7a198-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="7a198-135">Contate o [suporte](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="7a198-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="7a198-136">Se o problema for um que precisa ser resolvido retornando a uma versão anterior, eles podem fornecer a você o FFU para atualizar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a198-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="7a198-137">Se isso não funcionar, [redefina ou repisque o seu HoloLens 2 com o complemento de recuperação avançada](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="7a198-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="7a198-138">No seu computador, baixe o [complemento de recuperação avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7a198-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="7a198-139">Certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="7a198-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="7a198-140">Escolha qual versão você deseja atualizar:</span><span class="sxs-lookup"><span data-stu-id="7a198-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="7a198-141">Você pode baixar a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="7a198-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="7a198-142">Você pode usar a compilação padrão que os hosts ARC.</span><span class="sxs-lookup"><span data-stu-id="7a198-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="7a198-143">(Se você escolher essa opção, ignore a próxima etapa.)</span><span class="sxs-lookup"><span data-stu-id="7a198-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="7a198-144">Você pode usar um suporte de compilação fornecido com o.</span><span class="sxs-lookup"><span data-stu-id="7a198-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="7a198-145">Depois de concluir esses downloads, abra o **Explorador de arquivos**  >  **downloads**.</span><span class="sxs-lookup"><span data-stu-id="7a198-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="7a198-146">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.</span><span class="sxs-lookup"><span data-stu-id="7a198-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="7a198-147">Conecte seu HoloLens ao seu PC usando um USB-a para um cabo USB-C.</span><span class="sxs-lookup"><span data-stu-id="7a198-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="7a198-148">(Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="7a198-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="7a198-149">O complemento de recuperação avançada detecta automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7a198-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="7a198-150">Selecione o bloco **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="7a198-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="7a198-151">Na próxima tela, selecione **seleção de pacote manual** e, em seguida, selecione o arquivo de instalação contido na pasta que você descompactou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="7a198-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="7a198-152">(Procure um arquivo com a extensão. FFU.)</span><span class="sxs-lookup"><span data-stu-id="7a198-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="7a198-153">Selecione **instalar software** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="7a198-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="7a198-154">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="7a198-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="7a198-155">Além disso, se você quiser permanecer em sua versão atualmente instalada, também poderá [Pausar manualmente as atualizações](hololens-updates.md#pause-updates-via-device).</span><span class="sxs-lookup"><span data-stu-id="7a198-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="7a198-156">Isso dará ao time da equipe de engenharia que o problema será corrigido.</span><span class="sxs-lookup"><span data-stu-id="7a198-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="7a198-157">Programa Windows Insider no HoloLens</span><span class="sxs-lookup"><span data-stu-id="7a198-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="7a198-158">Deseja ver os recursos mais recentes no HoloLens?</span><span class="sxs-lookup"><span data-stu-id="7a198-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="7a198-159">Nesse caso, junte-se ao programa Windows Insider; Você terá acesso a versões prévias de atualizações de software do HoloLens antes que elas estejam disponíveis para o público geral.</span><span class="sxs-lookup"><span data-stu-id="7a198-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="7a198-160">[Obtenha o Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="7a198-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
