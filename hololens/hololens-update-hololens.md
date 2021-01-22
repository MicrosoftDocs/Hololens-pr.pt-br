---
title: Atualizar o HoloLens
description: Saiba como verificar o número de build do HoloLens, se manter atualizado com as atualizações de dispositivo, ingressar no Programa Insiders e reverter as atualizações.
keywords: how-to, update, roll back, HoloLens, check build, build number
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283932"
---
# <span data-ttu-id="b7556-104">Atualizar o HoloLens</span><span class="sxs-lookup"><span data-stu-id="b7556-104">Update HoloLens</span></span>

<span data-ttu-id="b7556-105">O HoloLens usa o Windows Update, assim como outros dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b7556-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="b7556-106">O HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que estiver conectado à energia e conectado à Internet, mesmo quando estiver em modo de espera.</span><span class="sxs-lookup"><span data-stu-id="b7556-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="b7556-107">Este artigo passará pelas ferramentas do HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="b7556-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="b7556-108">exibindo sua versão atual do sistema operacional (número de com build)</span><span class="sxs-lookup"><span data-stu-id="b7556-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="b7556-109">verificando se há atualizações</span><span class="sxs-lookup"><span data-stu-id="b7556-109">checking for updates</span></span>
- <span data-ttu-id="b7556-110">atualizar manualmente o HoloLens</span><span class="sxs-lookup"><span data-stu-id="b7556-110">manually updating HoloLens</span></span>
- <span data-ttu-id="b7556-111">reverter para uma atualização mais antiga</span><span class="sxs-lookup"><span data-stu-id="b7556-111">rolling back to an older update</span></span>

## <span data-ttu-id="b7556-112">Verificar a versão do sistema operacional (número de build)</span><span class="sxs-lookup"><span data-stu-id="b7556-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="b7556-113">Você pode verificar o número de versão do sistema,(número da com build) abrindo o aplicativo Configurações e selecionando **System**  >  **About**.</span><span class="sxs-lookup"><span data-stu-id="b7556-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="b7556-114">Verificar se há atualizações e atualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="b7556-114">Check for updates and manually update</span></span>

<span data-ttu-id="b7556-115">Você pode verificar se há atualizações a qualquer momento nas configurações.</span><span class="sxs-lookup"><span data-stu-id="b7556-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="b7556-116">Para ver as atualizações disponíveis e verificar se há novas atualizações:</span><span class="sxs-lookup"><span data-stu-id="b7556-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="b7556-117">Abra o **aplicativo Configurações.**</span><span class="sxs-lookup"><span data-stu-id="b7556-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="b7556-118">Navegue até **Atualizar & Segurança**do Windows  >  **Update.**</span><span class="sxs-lookup"><span data-stu-id="b7556-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="b7556-119">Selecione **Verificar se há atualizações.**</span><span class="sxs-lookup"><span data-stu-id="b7556-119">Select **Check for updates**.</span></span>

<span data-ttu-id="b7556-120">Se uma atualização estiver disponível, ela começará a baixar a nova versão.</span><span class="sxs-lookup"><span data-stu-id="b7556-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="b7556-121">Depois que o download for concluído, selecione o **botão Reiniciar** Agora para disparar a instalação.</span><span class="sxs-lookup"><span data-stu-id="b7556-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="b7556-122">Se o dispositivo estiver abaixo de 40% e não estiver conectado, a reinicialização não começará a instalar a atualização.</span><span class="sxs-lookup"><span data-stu-id="b7556-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="b7556-123">Enquanto o HoloLens estiver instalando a atualização, ele exibirá engrenagens giradas e um indicador de progresso.</span><span class="sxs-lookup"><span data-stu-id="b7556-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="b7556-124">Não desligue o HoloLens durante esse período.</span><span class="sxs-lookup"><span data-stu-id="b7556-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="b7556-125">Ele será reiniciado automaticamente depois de concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="b7556-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="b7556-126">O HoloLens aplica uma atualização por vez.</span><span class="sxs-lookup"><span data-stu-id="b7556-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="b7556-127">Se o HoloLens estiver mais de uma versão atrás da mais recente, talvez seja necessário executar o processo de atualização várias vezes para que ele fique totalmente atualizado.</span><span class="sxs-lookup"><span data-stu-id="b7556-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="b7556-128">Voltar para uma versão anterior - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b7556-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="b7556-129">Em alguns casos, talvez você queira voltar a uma versão anterior do software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b7556-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="b7556-130">Você pode fazer isso usando o Advanced Recovery Companion para redefinir seu HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="b7556-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="b7556-131">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="b7556-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="b7556-132">Para voltar a uma versão anterior do HoloLens 2, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b7556-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="b7556-133">Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.</span><span class="sxs-lookup"><span data-stu-id="b7556-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="b7556-134">Em seu computador, baixe o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="b7556-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="b7556-135">Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="b7556-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="b7556-136">Quando terminar esses downloads, abra Downloads **do Explorador de**  >  **Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="b7556-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="b7556-137">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **Extrair tudo** > **Extrair** para descompactar.</span><span class="sxs-lookup"><span data-stu-id="b7556-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="b7556-138">Conecte seu HoloLens ao computador usando um cabo USB-A para USB-C.</span><span class="sxs-lookup"><span data-stu-id="b7556-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="b7556-139">(Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).</span><span class="sxs-lookup"><span data-stu-id="b7556-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="b7556-140">O Advanced Recovery Companion detecta automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b7556-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="b7556-141">Selecione o bloco **Microsoft HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="b7556-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="b7556-142">Na tela seguinte, selecione **Seleção manual** de pacote e, em seguida, selecione o arquivo de instalação contido na pasta que você desempiou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="b7556-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="b7556-143">(Procure um arquivo com a extensão .ffu.)</span><span class="sxs-lookup"><span data-stu-id="b7556-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="b7556-144">Selecione **Instalar software**e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="b7556-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="b7556-145">Voltar para uma versão anterior - HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="b7556-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="b7556-146">Em alguns casos, talvez você queira voltar a uma versão anterior do software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b7556-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="b7556-147">Você pode fazer isso usando a Ferramenta de Recuperação de Dispositivos windows para redefinir seu HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="b7556-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="b7556-148">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="b7556-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="b7556-149">Para voltar a uma versão anterior do HoloLens 1, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b7556-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="b7556-150">Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.</span><span class="sxs-lookup"><span data-stu-id="b7556-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="b7556-151">Em seu computador, baixe a Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="b7556-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="b7556-152">Baixe o [Pacote de recuperação de Atualização de Aniversário do HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="b7556-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="b7556-153">Quando os downloads terminarem, abra **Downloads do**  >  **Explorador de Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="b7556-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="b7556-154">Clique com o botão direito do mouse na pasta de recortar que você acabou de baixar e selecione **Extrair tudo**  >  **para** descompcompletá-la.</span><span class="sxs-lookup"><span data-stu-id="b7556-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="b7556-155">Conecte seu HoloLens ao computador usando o cabo micro USB que ele veio com ele.</span><span class="sxs-lookup"><span data-stu-id="b7556-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="b7556-156">(Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).</span><span class="sxs-lookup"><span data-stu-id="b7556-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="b7556-157">O WDRT detectará automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b7556-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="b7556-158">Selecione o bloco **Microsoft HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="b7556-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="b7556-159">Na tela seguinte, selecione **Seleção manual de** pacote e escolha o arquivo de instalação contido na pasta descortada na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="b7556-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="b7556-160">(Procure um arquivo com a extensão .ffu.)</span><span class="sxs-lookup"><span data-stu-id="b7556-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="b7556-161">Selecione **Instalar software**e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="b7556-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="b7556-162">Se o WDRT não detectar seu HoloLens, tente reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="b7556-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="b7556-163">Se isso não funcionar, selecione **Meu dispositivo não foi detectado**, selecione **Microsoft HoloLens** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="b7556-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="b7556-164">Programa Windows Insider no HoloLens</span><span class="sxs-lookup"><span data-stu-id="b7556-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="b7556-165">Deseja ver os recursos mais recentes no HoloLens?</span><span class="sxs-lookup"><span data-stu-id="b7556-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="b7556-166">Em caso sim, participe do Programa Windows Insider; você terá acesso às builds de visualização das atualizações de software do HoloLens antes que elas tenham acesso ao público em geral.</span><span class="sxs-lookup"><span data-stu-id="b7556-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="b7556-167">[Obter a visualização do Windows Insider para Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="b7556-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
