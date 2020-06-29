---
title: Atualizar o HoloLens
description: Verifique o número do Build do seu HoloLens, atualize e Reverta as atualizações.
keywords: instruções, atualizar, reverter, HoloLens, verificar compilação, número da compilação
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827537"
---
# <span data-ttu-id="bc2d7-104">Atualizar o HoloLens</span><span class="sxs-lookup"><span data-stu-id="bc2d7-104">Update HoloLens</span></span>

<span data-ttu-id="bc2d7-105">O HoloLens usa o Windows Update, assim como outros dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="bc2d7-106">Seu HoloLens fará automaticamente o download e a instalação das atualizações do sistema sempre que estiver conectado à rede e conectado à Internet, mesmo quando estiver em standby.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="bc2d7-107">Este artigo examinará as ferramentas do HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="bc2d7-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="bc2d7-108">exibindo a versão do sistema operacional atual (número da compilação)</span><span class="sxs-lookup"><span data-stu-id="bc2d7-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="bc2d7-109">verificando se há atualizações</span><span class="sxs-lookup"><span data-stu-id="bc2d7-109">checking for updates</span></span>
- <span data-ttu-id="bc2d7-110">atualizando manualmente o HoloLens</span><span class="sxs-lookup"><span data-stu-id="bc2d7-110">manually updating HoloLens</span></span>
- <span data-ttu-id="bc2d7-111">reverter para uma atualização mais antiga</span><span class="sxs-lookup"><span data-stu-id="bc2d7-111">rolling back to an older update</span></span>

## <span data-ttu-id="bc2d7-112">Verificar a versão do sistema operacional (número da compilação)</span><span class="sxs-lookup"><span data-stu-id="bc2d7-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="bc2d7-113">Você pode verificar o número da versão do sistema (número do Build) abrindo o aplicativo Configurações e selecionando o **sistema**  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="bc2d7-114">Verificar se há atualizações e atualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="bc2d7-114">Check for updates and manually update</span></span>

<span data-ttu-id="bc2d7-115">Você pode verificar se há atualizações a qualquer momento em configurações.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="bc2d7-116">Para ver as atualizações disponíveis e verificar se há novas atualizações:</span><span class="sxs-lookup"><span data-stu-id="bc2d7-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="bc2d7-117">Abra o aplicativo **configurações** .</span><span class="sxs-lookup"><span data-stu-id="bc2d7-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="bc2d7-118">Navegue até **Atualizar &**  >  **atualização do Windows**Security.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="bc2d7-119">Selecione **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-119">Select **Check for updates**.</span></span>

<span data-ttu-id="bc2d7-120">Se houver uma atualização disponível, o download da nova versão será iniciado.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="bc2d7-121">Depois que o download for concluído, selecione o botão **reiniciar agora** para disparar a instalação.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="bc2d7-122">Se o seu dispositivo estiver abaixo de 40% e não estiver conectado, reiniciar não iniciará a instalação da atualização.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="bc2d7-123">Enquanto o HoloLens estiver instalando a atualização, ele exibirá as engrenagens giradas e um indicador de progresso.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="bc2d7-124">Não desative seu HoloLens durante esse período.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="bc2d7-125">Ele será reiniciado automaticamente quando concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="bc2d7-126">O HoloLens aplica uma atualização de cada vez.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="bc2d7-127">Se o seu HoloLens for mais de uma versão por trás do mais recente, talvez seja necessário executar o processo de atualização várias vezes para obtê-lo totalmente atualizado.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="bc2d7-128">Voltar para uma versão anterior-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bc2d7-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="bc2d7-129">Em alguns casos, talvez você queira voltar para uma versão anterior do software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="bc2d7-130">Você pode fazer isso usando o complemento de recuperação avançada para redefinir seu HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="bc2d7-131">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="bc2d7-132">Para voltar para uma versão anterior do HoloLens 2, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="bc2d7-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="bc2d7-133">Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao seu computador.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="bc2d7-134">Em seu computador, baixe o [complemento avançado de recuperação](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="bc2d7-135">Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="bc2d7-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="bc2d7-136">Quando tiver terminado esses downloads, abra o download do **Explorador de arquivos**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="bc2d7-137">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **Extrair tudo** > **Extrair** para descompactar.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="bc2d7-138">Conecte seu HoloLens ao PC usando um cabo USB-A para USB-C.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="bc2d7-139">(Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).</span><span class="sxs-lookup"><span data-stu-id="bc2d7-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="bc2d7-140">O complemento de recuperação avançada detecta automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="bc2d7-141">Selecione o bloco **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="bc2d7-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="bc2d7-142">Na tela seguinte, selecione **seleção de pacote manual** e, em seguida, selecione o arquivo de instalação contido na pasta descompactada na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="bc2d7-143">(Procure um arquivo com a extensão. FFU.)</span><span class="sxs-lookup"><span data-stu-id="bc2d7-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="bc2d7-144">Selecione **instalar software**e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="bc2d7-145">Voltar para uma versão anterior-HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="bc2d7-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="bc2d7-146">Em alguns casos, talvez você queira voltar para uma versão anterior do software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="bc2d7-147">Você pode fazer isso usando a ferramenta de recuperação de dispositivos do Windows para redefinir o HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="bc2d7-148">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="bc2d7-149">Para voltar para uma versão anterior do HoloLens 1, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="bc2d7-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="bc2d7-150">Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao seu computador.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="bc2d7-151">Em seu computador, baixe a [ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="bc2d7-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="bc2d7-152">Baixe o [pacote de recuperação de atualização de aniversários do HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="bc2d7-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="bc2d7-153">Quando o download for concluído, abra o download do **Explorador de arquivos**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="bc2d7-154">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  **extração** para descompactá-la.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="bc2d7-155">Conecte seu HoloLens ao PC usando o cabo micro USB com o qual ele veio.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="bc2d7-156">(Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).</span><span class="sxs-lookup"><span data-stu-id="bc2d7-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="bc2d7-157">O WDRT detectará automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="bc2d7-158">Selecione o bloco **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="bc2d7-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="bc2d7-159">Na tela seguinte, selecione **seleção de pacote manual** e escolha o arquivo de instalação contido na pasta descompactada na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="bc2d7-160">(Procure um arquivo com a extensão. FFU.)</span><span class="sxs-lookup"><span data-stu-id="bc2d7-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="bc2d7-161">Selecione **instalar software**e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="bc2d7-162">Se o WDRT não detectar o seu HoloLens, tente reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="bc2d7-163">Se isso não funcionar, selecione **meu dispositivo não foi detectado**, selecione **Microsoft HoloLens**e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="bc2d7-164">Programa Windows Insider no HoloLens</span><span class="sxs-lookup"><span data-stu-id="bc2d7-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="bc2d7-165">Deseja ver os recursos mais recentes do HoloLens?</span><span class="sxs-lookup"><span data-stu-id="bc2d7-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="bc2d7-166">Em caso afirmativo, participe do programa Windows Insider; Você obterá acesso às versões prévias das atualizações de software do HoloLens antes que elas estejam disponíveis para o público em geral.</span><span class="sxs-lookup"><span data-stu-id="bc2d7-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="bc2d7-167">[Obtenha o Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="bc2d7-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
