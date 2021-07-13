---
title: Reiniciar, redefinir ou recuperar HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como usar a Windows recuperação de dispositivo para piscar uma imagem para HoloLens 1ª geração.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635221"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="c55bd-104">Reiniciar, redefinir ou recuperar HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="c55bd-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="c55bd-105">Se você estiver tendo problemas com seu HoloLens, talvez você queira tentar reiniciar ou redefinir ou até mesmo reflashar o dispositivo usando a recuperação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="c55bd-106">Este artigo orienta você pelas etapas de recuperação recomendadas na ordem.</span><span class="sxs-lookup"><span data-stu-id="c55bd-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="c55bd-107">Se você estiver procurando recuperar um HoloLens 2, consulte Recuperando um HoloLens [2,](hololens-recovery.md)pois esse processo é diferente.</span><span class="sxs-lookup"><span data-stu-id="c55bd-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="c55bd-108">Este artigo se concentra no HoloLens software e dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="c55bd-109">Se os hologramas não parecem corretos, confira **[HoloLens de](hololens-environment-considerations.md)** ambiente para obter informações sobre fatores que melhoram a qualidade do holograma.</span><span class="sxs-lookup"><span data-stu-id="c55bd-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="c55bd-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="c55bd-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="c55bd-111">Faça uma reinicialização segura usando Cortana</span><span class="sxs-lookup"><span data-stu-id="c55bd-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="c55bd-112">A maneira mais segura de reiniciar o HoloLens é usando Cortana, que geralmente é a primeira coisa a tentar quando você tem um problema com HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c55bd-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="c55bd-113">Cortana está disponível em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c55bd-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="c55bd-114">Cortana está disponível em todos os HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="c55bd-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="c55bd-115">Cortana está disponível em HoloLens 2 dispositivos em builds anteriores à atualização Windows Holograpic, Versão 2004.</span><span class="sxs-lookup"><span data-stu-id="c55bd-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="c55bd-116">A turn on your HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c55bd-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="c55bd-117">Certifique-se de que um usuário está conectado e se o dispositivo não está aguardando uma senha desbloqueá-la.</span><span class="sxs-lookup"><span data-stu-id="c55bd-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="c55bd-118">Diga "Hey Cortana, reboot" ou "Hey Cortana, restart".</span><span class="sxs-lookup"><span data-stu-id="c55bd-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="c55bd-119">Cortana responderá e solicitará que você confirme.</span><span class="sxs-lookup"><span data-stu-id="c55bd-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="c55bd-120">Aguarde a reprodução de um som após a pergunta e, em seguida, diga "Sim".</span><span class="sxs-lookup"><span data-stu-id="c55bd-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="c55bd-121">O dispositivo será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="c55bd-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="c55bd-122">Usar o botão de energia para fazer uma reinicialização segura</span><span class="sxs-lookup"><span data-stu-id="c55bd-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="c55bd-123">Se você ainda não conseguir reiniciar o dispositivo, tente reiniciá-lo usando o **botão de** energia:</span><span class="sxs-lookup"><span data-stu-id="c55bd-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="c55bd-124">Pressione e mantenha o **botão de** energia pressionado por 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="c55bd-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="c55bd-125">Após 1 segundo, todos os cinco LEDs serão acesos e, em seguida, desligarão lentamente um por um da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="c55bd-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="c55bd-126">Após 5 segundos, todos os LEDs estarão desligados, indicando desligamento bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="c55bd-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="c55bd-127">Pare de pressionar o botão imediatamente depois que todos os LEDs foram desligados.</span><span class="sxs-lookup"><span data-stu-id="c55bd-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="c55bd-128">Aguarde 1 minuto para que o desligamento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c55bd-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="c55bd-129">O desligamento ainda pode estar em andamento mesmo depois que as exibições são desligadas.</span><span class="sxs-lookup"><span data-stu-id="c55bd-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="c55bd-130">A ligar o dispositivo novamente pressionando e mantendo o **botão de** energia pressionado por 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="c55bd-131">Faça uma reinicialização segura usando Windows Portal de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="c55bd-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="c55bd-132">Para esse processo, HoloLens precisa ser configurado como um dispositivo de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="c55bd-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="c55bd-133">Saiba mais em [Windows Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="c55bd-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="c55bd-134">Se o procedimento anterior não funcionou, tente reiniciar o dispositivo [usando](/windows/mixed-reality/using-the-windows-device-portal)Windows Portal de Dispositivos .</span><span class="sxs-lookup"><span data-stu-id="c55bd-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="c55bd-135">No canto superior direito, encontre a opção para reiniciar ou desligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="c55bd-136">Fazer uma reinicialização forçada não segura</span><span class="sxs-lookup"><span data-stu-id="c55bd-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="c55bd-137">Se os métodos anteriores não reiniciarem o HoloLens, force uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="c55bd-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="c55bd-138">Esse método é equivalente a remover e reinstalar a bateria.</span><span class="sxs-lookup"><span data-stu-id="c55bd-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="c55bd-139">É perigoso porque pode deixar seu dispositivo em um estado corrompido.</span><span class="sxs-lookup"><span data-stu-id="c55bd-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="c55bd-140">Se isso acontecer, você terá que piscar seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c55bd-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="c55bd-141">Esse é um método potencialmente prejudicial e só deverá ser usado se os métodos citados anteriormente não funcionarem.</span><span class="sxs-lookup"><span data-stu-id="c55bd-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="c55bd-142">Pressione e mantenha o **botão de** energia pressionado por pelo menos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="c55bd-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="c55bd-143">Não há problema em manter o botão por mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="c55bd-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="c55bd-144">É seguro ignorar qualquer atividade de LED.</span><span class="sxs-lookup"><span data-stu-id="c55bd-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="c55bd-145">Solte o botão e aguarde de 2 a 3 segundos.</span><span class="sxs-lookup"><span data-stu-id="c55bd-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="c55bd-146">Pressione e mantenha o **botão de** energia pressionado por 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="c55bd-147">Se você ainda tiver  problemas, pressione o botão de energia por 4 segundos, até que todos os indicadores de bateria esmaeçam e a tela pare de exibir hologramas.</span><span class="sxs-lookup"><span data-stu-id="c55bd-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="c55bd-148">Aguarde 1 minuto e pressione o botão **de** energia novamente para ativar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="c55bd-149">Go back para uma versão anterior – HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="c55bd-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="c55bd-150">Em alguns casos, talvez você queira voltar para uma versão anterior do HoloLens software.</span><span class="sxs-lookup"><span data-stu-id="c55bd-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="c55bd-151">Você pode fazer isso usando a ferramenta Windows recuperação de dispositivo para redefinir seu HoloLens para a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="c55bd-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="c55bd-152">Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.</span><span class="sxs-lookup"><span data-stu-id="c55bd-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="c55bd-153">Para voltar para uma versão anterior do HoloLens 1, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c55bd-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="c55bd-154">Certifique-se de que você não tenha telefones ou Windows conectados ao computador.</span><span class="sxs-lookup"><span data-stu-id="c55bd-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="c55bd-155">Em seu computador, baixe o [WDRT (Ferramenta Windows Recuperação](https://support.microsoft.com/help/12379)de Dispositivo) do .</span><span class="sxs-lookup"><span data-stu-id="c55bd-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="c55bd-156">Baixe o pacote [de recuperação HoloLens atualização de aniversário do .](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="c55bd-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="c55bd-157">Quando os downloads terminarem, abra Explorador **de arquivos**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="c55bd-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="c55bd-158">Clique com o botão direito do mouse na pasta recortada que você acabou de baixar e selecione **Extrair tudo**  >  **extrair** para descomplicá-la.</span><span class="sxs-lookup"><span data-stu-id="c55bd-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="c55bd-159">Conexão seu HoloLens no computador usando o cabo micro USB que ele veio.</span><span class="sxs-lookup"><span data-stu-id="c55bd-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="c55bd-160">(Mesmo que você tenha usado outros cabos para conectar seu HoloLens, esse funcionará melhor.)</span><span class="sxs-lookup"><span data-stu-id="c55bd-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="c55bd-161">O WDRT detectará automaticamente seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c55bd-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="c55bd-162">Selecione o **Microsoft HoloLens** de seleção.</span><span class="sxs-lookup"><span data-stu-id="c55bd-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="c55bd-163">Na próxima tela, selecione **Seleção manual de** pacotes e escolha o arquivo de instalação contido na pasta que você desempiou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="c55bd-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="c55bd-164">(Procure um arquivo com a extensão .ffu.)</span><span class="sxs-lookup"><span data-stu-id="c55bd-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="c55bd-165">Selecione **Instalar software** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="c55bd-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="c55bd-166">Se o WDRT não detectar seu HoloLens, tente reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="c55bd-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="c55bd-167">Se isso não funcionar, selecione **Meu dispositivo não** foi detectado, selecione Microsoft HoloLens e siga as instruções. </span><span class="sxs-lookup"><span data-stu-id="c55bd-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="c55bd-168">Redefinir para configurações de fábrica</span><span class="sxs-lookup"><span data-stu-id="c55bd-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="c55bd-169">A bateria precisa de pelo menos uma carga de 40% para redefinir.</span><span class="sxs-lookup"><span data-stu-id="c55bd-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="c55bd-170">Se o HoloLens ainda tiver um problema, tente redefini-lo para o estado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="c55bd-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="c55bd-171">Esta etapa mantém a versão do Windows software Holographic instalado nele e retorna todo o resto para as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="c55bd-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="c55bd-172">Se você redefinir seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição do TPM.</span><span class="sxs-lookup"><span data-stu-id="c55bd-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="c55bd-173">A redefinição instalará apenas a versão mais recente instalada do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="c55bd-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="c55bd-174">Você terá que refazer todas as etapas de inicialização (calibrar, conectar-se ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="c55bd-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="c55bd-175">Abra o Configurações aplicativo e, em seguida, selecione **Atualizar**  >  **Recuperação**.</span><span class="sxs-lookup"><span data-stu-id="c55bd-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="c55bd-176">Selecione a **opção Redefinir** dispositivo e leia a mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="c55bd-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="c55bd-177">Confirme a redefinição.</span><span class="sxs-lookup"><span data-stu-id="c55bd-177">Confirm the reset.</span></span> <span data-ttu-id="c55bd-178">O dispositivo reiniciará e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="c55bd-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="c55bd-179">Aguarde cerca de 30 minutos para que esse processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c55bd-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="c55bd-180">Quando terminar, o dispositivo será reiniciado para a experiência "pronta para uso".</span><span class="sxs-lookup"><span data-stu-id="c55bd-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="c55bd-181">Reinstalar o sistema operacional</span><span class="sxs-lookup"><span data-stu-id="c55bd-181">Reinstall the operating system</span></span>

<span data-ttu-id="c55bd-182">Se o dispositivo ainda estiver tendo um problema após a reinicialização e a redefinição, você poderá usar uma ferramenta de recuperação em seu computador para reinstalar o HoloLens operacional e firmware.</span><span class="sxs-lookup"><span data-stu-id="c55bd-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="c55bd-183">Os dados HoloLens necessários para a redefinição são empacotados em uma FFU (Atualização Flash Completa), que é semelhante a um arquivo .iso, .wim ou .vhd.</span><span class="sxs-lookup"><span data-stu-id="c55bd-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="c55bd-184">Saiba mais sobre formatos de arquivo de imagem FFU.</span><span class="sxs-lookup"><span data-stu-id="c55bd-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="c55bd-185">Você pode instalar um novo sistema operacional em seu HoloLens (1ª geração) usando a ferramenta Windows recuperação de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="c55bd-186">Antes de usar essa ferramenta, confira se reiniciar ou redefinir seu HoloLens corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="c55bd-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="c55bd-187">O processo de recuperação pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-187">The recovery process may take a while.</span></span> <span data-ttu-id="c55bd-188">Quando terminar, a versão mais recente do Windows holographic será instalada.</span><span class="sxs-lookup"><span data-stu-id="c55bd-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="c55bd-189">Para usar a ferramenta, você precisa de um computador executando Windows 10 ou posterior com pelo menos 4 GB de espaço de armazenamento livre.</span><span class="sxs-lookup"><span data-stu-id="c55bd-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="c55bd-190">Você não pode executar essa ferramenta em uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="c55bd-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="c55bd-191">Recuperar sua HoloLens</span><span class="sxs-lookup"><span data-stu-id="c55bd-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="c55bd-192">Baixe e instale a ferramenta [Windows recuperação de dispositivo em](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) seu computador.</span><span class="sxs-lookup"><span data-stu-id="c55bd-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="c55bd-193">Conexão o HoloLens (1ª geração) para seu computador usando o cabo Micro USB que veio com seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c55bd-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="c55bd-194">Abra a ferramenta Windows recuperação de dispositivo e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="c55bd-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="c55bd-195">Se a HoloLens (1ª geração) não for detectada automaticamente, selecione Meu dispositivo **não foi detectado.**</span><span class="sxs-lookup"><span data-stu-id="c55bd-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="c55bd-196">Em seguida, siga as instruções para colocar o dispositivo no modo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="c55bd-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="c55bd-197">Modo de flash manual</span><span class="sxs-lookup"><span data-stu-id="c55bd-197">Manual flashing mode</span></span>

<span data-ttu-id="c55bd-198">Se o dispositivo não for detectado, siga estas etapas para colocá-lo no modo de flash:</span><span class="sxs-lookup"><span data-stu-id="c55bd-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="c55bd-199">Desconectar o dispositivo de qualquer fonte de alimentação.</span><span class="sxs-lookup"><span data-stu-id="c55bd-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="c55bd-200">Se o dispositivo estiver conectado, mantenha pressionado o botão **de** energia até que ele seja completamente desligado.</span><span class="sxs-lookup"><span data-stu-id="c55bd-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="c55bd-201">Mantenha o botão do **volume** pressionado e toque brevemente no botão de **energia** .</span><span class="sxs-lookup"><span data-stu-id="c55bd-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="c55bd-202">O dispositivo deve iniciar e exibir apenas o LED do meio.</span><span class="sxs-lookup"><span data-stu-id="c55bd-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="c55bd-203">Conecte o dispositivo ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="c55bd-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="c55bd-204">abra a ferramenta de recuperação de dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="c55bd-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="c55bd-205">Selecione **meu dispositivo não foi detectado** e, em seguida, **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="c55bd-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="c55bd-206">Siga as instruções para recuperar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c55bd-206">Follow the instructions to recover your device.</span></span>
