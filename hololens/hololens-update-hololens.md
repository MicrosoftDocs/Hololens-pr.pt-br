---
title: Atualizar o HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308141"
---
# <a name="update-hololens"></a><span data-ttu-id="3b679-104">Atualizar o HoloLens</span><span class="sxs-lookup"><span data-stu-id="3b679-104">Update HoloLens</span></span>

<span data-ttu-id="3b679-105">O HoloLens usa Windows Update, assim como outros dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3b679-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="3b679-106">Seu HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que ele estiver conectado à energia e conectado à Internet, mesmo quando ela estiver em espera.</span><span class="sxs-lookup"><span data-stu-id="3b679-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="3b679-107">Este artigo apresentará as ferramentas do HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="3b679-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="3b679-108">exibindo a versão atual do sistema operacional (número da versão)</span><span class="sxs-lookup"><span data-stu-id="3b679-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="3b679-109">verificando se há atualizações</span><span class="sxs-lookup"><span data-stu-id="3b679-109">checking for updates</span></span>
- <span data-ttu-id="3b679-110">atualizando manualmente o HoloLens</span><span class="sxs-lookup"><span data-stu-id="3b679-110">manually updating HoloLens</span></span>
- <span data-ttu-id="3b679-111">reverter para uma atualização mais antiga</span><span class="sxs-lookup"><span data-stu-id="3b679-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="3b679-112">Verificar a versão do sistema operacional (número da versão)</span><span class="sxs-lookup"><span data-stu-id="3b679-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="3b679-113">Você pode verificar o número de versão do sistema, (número da compilação) abrindo o aplicativo Configurações e selecionando **sistema**  >  **sobre**.</span><span class="sxs-lookup"><span data-stu-id="3b679-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="3b679-114">Verificar se há atualizações e atualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="3b679-114">Check for updates and manually update</span></span>

<span data-ttu-id="3b679-115">Você pode verificar se há atualizações a qualquer momento nas configurações.</span><span class="sxs-lookup"><span data-stu-id="3b679-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="3b679-116">Para ver as atualizações disponíveis e verificar se há novas atualizações:</span><span class="sxs-lookup"><span data-stu-id="3b679-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="3b679-117">Abra o aplicativo **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="3b679-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="3b679-118">Navegue até **Atualizar & segurança**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="3b679-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="3b679-119">Selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="3b679-119">Select **Check for updates**.</span></span>

<span data-ttu-id="3b679-120">Se uma atualização estiver disponível, ela começará a baixar a nova versão.</span><span class="sxs-lookup"><span data-stu-id="3b679-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="3b679-121">Após a conclusão do download, selecione o botão **reiniciar agora** para disparar a instalação.</span><span class="sxs-lookup"><span data-stu-id="3b679-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="3b679-122">Se o dispositivo estiver abaixo de 40% e não conectado, a reinicialização não iniciará a instalação da atualização.</span><span class="sxs-lookup"><span data-stu-id="3b679-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="3b679-123">Enquanto o seu HoloLens está instalando a atualização, ele exibirá engrenagens giratórias e um indicador de progresso.</span><span class="sxs-lookup"><span data-stu-id="3b679-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="3b679-124">Não desative seu HoloLens durante esse tempo.</span><span class="sxs-lookup"><span data-stu-id="3b679-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="3b679-125">Ele será reiniciado automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="3b679-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="3b679-126">O HoloLens aplica uma atualização por vez.</span><span class="sxs-lookup"><span data-stu-id="3b679-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="3b679-127">Se o seu HoloLens for mais de uma versão por trás do mais recente, talvez seja necessário executar o processo de atualização várias vezes para atualizá-lo completamente.</span><span class="sxs-lookup"><span data-stu-id="3b679-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="3b679-128">Voltar para uma versão anterior – HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3b679-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="3b679-129">Em alguns casos, talvez você queira voltar para uma versão anterior do software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3b679-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="3b679-130">Você pode fazer isso usando o complemento de recuperação avançada para redefinir o HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="3b679-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="3b679-131">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="3b679-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="3b679-132">Para voltar para uma versão anterior do HoloLens 2, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3b679-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="3b679-133">Certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="3b679-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="3b679-134">No seu computador, baixe o [complemento de recuperação avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="3b679-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="3b679-135">Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="3b679-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="3b679-136">Depois de concluir esses downloads, abra o **Explorador de arquivos**  >  **downloads**.</span><span class="sxs-lookup"><span data-stu-id="3b679-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="3b679-137">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.</span><span class="sxs-lookup"><span data-stu-id="3b679-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="3b679-138">Conecte seu HoloLens ao seu PC usando um USB-a para um cabo USB-C.</span><span class="sxs-lookup"><span data-stu-id="3b679-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="3b679-139">(Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="3b679-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="3b679-140">O complemento de recuperação avançada detecta automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3b679-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="3b679-141">Selecione o bloco **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="3b679-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="3b679-142">Na próxima tela, selecione **seleção de pacote manual** e, em seguida, selecione o arquivo de instalação contido na pasta que você descompactou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="3b679-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="3b679-143">(Procure um arquivo com a extensão. FFU.)</span><span class="sxs-lookup"><span data-stu-id="3b679-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="3b679-144">Selecione **instalar software** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="3b679-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="3b679-145">Voltar para uma versão anterior – HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="3b679-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="3b679-146">Em alguns casos, talvez você queira voltar para uma versão anterior do software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3b679-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="3b679-147">Você pode fazer isso usando a ferramenta de recuperação de dispositivo do Windows para redefinir o HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="3b679-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="3b679-148">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="3b679-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="3b679-149">Para voltar para uma versão anterior do HoloLens 1, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3b679-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="3b679-150">Certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="3b679-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="3b679-151">Em seu computador, baixe a [ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="3b679-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="3b679-152">Baixe o [pacote de recuperação de atualização de aniversário do HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="3b679-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="3b679-153">Quando o download for concluído, abra o **Explorador de arquivos**  >  **downloads**.</span><span class="sxs-lookup"><span data-stu-id="3b679-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="3b679-154">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.</span><span class="sxs-lookup"><span data-stu-id="3b679-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="3b679-155">Conecte seu HoloLens ao seu PC usando o cabo micro USB com o qual ele veio.</span><span class="sxs-lookup"><span data-stu-id="3b679-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="3b679-156">(Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="3b679-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="3b679-157">O WDRT detectará automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3b679-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="3b679-158">Selecione o bloco **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="3b679-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="3b679-159">Na próxima tela, selecione **seleção de pacote manual** e escolha o arquivo de instalação contido na pasta descompactada na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="3b679-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="3b679-160">(Procure um arquivo com a extensão. FFU.)</span><span class="sxs-lookup"><span data-stu-id="3b679-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="3b679-161">Selecione **instalar software** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="3b679-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="3b679-162">Se o WDRT não detectar seu HoloLens, tente reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="3b679-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="3b679-163">Se isso não funcionar, selecione **meu dispositivo não foi detectado**, selecione **Microsoft HoloLens** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="3b679-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="3b679-164">Programa Windows Insider no HoloLens</span><span class="sxs-lookup"><span data-stu-id="3b679-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="3b679-165">Deseja ver os recursos mais recentes no HoloLens?</span><span class="sxs-lookup"><span data-stu-id="3b679-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="3b679-166">Nesse caso, junte-se ao programa Windows Insider; Você terá acesso a versões prévias de atualizações de software do HoloLens antes que elas estejam disponíveis para o público geral.</span><span class="sxs-lookup"><span data-stu-id="3b679-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="3b679-167">[Obtenha o Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="3b679-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
