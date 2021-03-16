---
title: Reiniciar, redefinir ou recuperar o HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como usar a Windows Device Recovery Tool para mostrar uma imagem para o HoloLens de 1ª geração.
keywords: como fazer, reinicializar, redefinir, recuperar, reinicialização forçada, reinicialização flexível, ciclo de energia, HoloLens, desligar, wdrt, windows device recovery tool
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
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439037"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="2c36d-104">Reiniciar, redefinir ou recuperar o HoloLens de 1ª geração</span><span class="sxs-lookup"><span data-stu-id="2c36d-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="2c36d-105">Se você estiver enfrentando problemas com o seu HoloLens, talvez queira tentar uma reinicialização ou redefinição, ou até mesmo refazer o flash do dispositivo usando a recuperação de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2c36d-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="2c36d-106">Este artigo o orientará pelas etapas de recuperação recomendadas.</span><span class="sxs-lookup"><span data-stu-id="2c36d-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="2c36d-107">Se você estiver tentando recuperar um HoloLens 2, confira [Recuperar um HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), pois esse processo é diferente.</span><span class="sxs-lookup"><span data-stu-id="2c36d-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="2c36d-108">Esse artigo se concentra no dispositivo HoloLens e no seu software.</span><span class="sxs-lookup"><span data-stu-id="2c36d-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="2c36d-109">Se o seu holograma não parecer correto, confira **[considerações sobre o ambiente do HoloLens](hololens-environment-considerations.md)** para saber mais sobre os fatores que melhoram a qualidade do holograma.</span><span class="sxs-lookup"><span data-stu-id="2c36d-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="2c36d-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="2c36d-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="2c36d-111">Executar uma reinicialização segura usando a Cortana</span><span class="sxs-lookup"><span data-stu-id="2c36d-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="2c36d-112">A maneira mais segura de reiniciar o HoloLens é usar a Cortana, que geralmente é a primeira coisa a fazer quando você se enfrenta um problema com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c36d-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="2c36d-113">A Cortana não está disponível em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2c36d-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="2c36d-114">A Cortana está disponível a todos os dispositivos do HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="2c36d-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="2c36d-115">A Cortana está disponível em dispositivos do HoloLens 2 em uma compilação anterior à atualização do Windows Holograpic, versão 2004.</span><span class="sxs-lookup"><span data-stu-id="2c36d-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="2c36d-116">Ativar o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c36d-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="2c36d-117">Certifique-se de que um usuário está conectado e o dispositivo não está aguardando que uma senha seja desbloqueada.</span><span class="sxs-lookup"><span data-stu-id="2c36d-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="2c36d-118">Diga "Ei Cortana, reinicializar" ou "Ei Cortana, reiniciar".</span><span class="sxs-lookup"><span data-stu-id="2c36d-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="2c36d-119">A Cortana responderá e solicitará que você confirme.</span><span class="sxs-lookup"><span data-stu-id="2c36d-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="2c36d-120">Aguarde um som ser tocado após a pergunta e, em seguida, diga "Sim".</span><span class="sxs-lookup"><span data-stu-id="2c36d-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="2c36d-121">O dispositivo será reiniciado agora.</span><span class="sxs-lookup"><span data-stu-id="2c36d-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="2c36d-122">Use o botão de energia para executar uma reinicialização segura</span><span class="sxs-lookup"><span data-stu-id="2c36d-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="2c36d-123">Se você ainda não conseguir reiniciar o dispositivo, experimente reiniciá-lo usando o botão de **energia**:</span><span class="sxs-lookup"><span data-stu-id="2c36d-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="2c36d-124">Pressione e mantenha pressionado o botão de **energia** por 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="2c36d-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="2c36d-125">Após 1 segundo, todos os cinco LEDs irão iluminar e, em seguida, desligar lentamente um por um da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="2c36d-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="2c36d-126">Após 5 segundos, todos os LEDs estarão desligados, indicando um desligamento bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="2c36d-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="2c36d-127">Pare de pressionar o botão imediatamente após todos os LEDs terem desligado.</span><span class="sxs-lookup"><span data-stu-id="2c36d-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="2c36d-128">Aguarde 1 minuto para concluir o desligamento.</span><span class="sxs-lookup"><span data-stu-id="2c36d-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="2c36d-129">O desligamento ainda pode estar em andamento, mesmo depois que os monitores estiverem desligados.</span><span class="sxs-lookup"><span data-stu-id="2c36d-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="2c36d-130">Ligue o dispositivo novamente pressionando e mantendo pressionado o botão de **energia** por 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="2c36d-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="2c36d-131">Reiniciar com segurança usando o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="2c36d-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="2c36d-132">Para fazer isso, o HoloLens deve ser configurado como um dispositivo desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="2c36d-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="2c36d-133">Saiba mais em [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="2c36d-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="2c36d-134">Se o procedimento anterior não funcionar, você pode tentar reiniciar o dispositivo usando [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="2c36d-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="2c36d-135">No canto superior direito, há uma opção para reiniciar ou desligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c36d-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="2c36d-136">Reinicialização forçada sem segurança</span><span class="sxs-lookup"><span data-stu-id="2c36d-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="2c36d-137">Se os métodos anteriores não reiniciarem o seu HoloLens, force uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="2c36d-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="2c36d-138">Esse método é equivalente a remover e reinstalar a bateria.</span><span class="sxs-lookup"><span data-stu-id="2c36d-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="2c36d-139">É perigoso porque pode deixar o seu dispositivo em um estado corrompido.</span><span class="sxs-lookup"><span data-stu-id="2c36d-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="2c36d-140">Se isso acontecer, você precisará ligar e desligar o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c36d-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="2c36d-141">Esse é um método potencialmente nocivo e só deve ser usado se os métodos mencionados anteriormente não funcionarem.</span><span class="sxs-lookup"><span data-stu-id="2c36d-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="2c36d-142">Pressione e mantenha pressionado o botão de **energia** por pelo menos dez segundos.</span><span class="sxs-lookup"><span data-stu-id="2c36d-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="2c36d-143">Não há problema em manter o botão por mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="2c36d-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="2c36d-144">É seguro ignorar qualquer atividade do LED.</span><span class="sxs-lookup"><span data-stu-id="2c36d-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="2c36d-145">Solte o botão e aguarde dois ou três segundos.</span><span class="sxs-lookup"><span data-stu-id="2c36d-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="2c36d-146">Pressione e mantenha pressionado o botão de **energia** por 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="2c36d-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="2c36d-147">Se você ainda estiver enfrentando problemas, pressione o botão de **energia** por quatro segundos até que todos os indicadores de bateria apareçam gradualmente e a tela pare de exibir os hologramas.</span><span class="sxs-lookup"><span data-stu-id="2c36d-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="2c36d-148">Aguarde um minuto e, em seguida, pressione o botão de **energia** novamente para ativar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c36d-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="2c36d-149">Redefinir para as configurações de fábrica</span><span class="sxs-lookup"><span data-stu-id="2c36d-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="2c36d-150">A bateria precisa de pelo menos 40% da carga para reiniciar.</span><span class="sxs-lookup"><span data-stu-id="2c36d-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="2c36d-151">Se o seu HoloLens ainda tiver um problema, tente redefini-lo para o estado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="2c36d-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="2c36d-152">Esta etapa mantém a versão do software do Windows Holographic que está instalada nela e retorna tudo para as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="2c36d-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="2c36d-153">Se você reiniciar seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo a redefinição do TPM.</span><span class="sxs-lookup"><span data-stu-id="2c36d-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="2c36d-154">A redefinição instalará apenas a versão mais recente do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="2c36d-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="2c36d-155">Será necessário refazer todas as etapas de inicialização (calibragem, conectar ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="2c36d-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="2c36d-156">Abra o aplicativo Configurações e, em seguida, selecione **Atualizar** > **Recuperação**.</span><span class="sxs-lookup"><span data-stu-id="2c36d-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="2c36d-157">Selecione a opção **Redefinir dispositivo** e leia a mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="2c36d-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="2c36d-158">Confirme a redefinição.</span><span class="sxs-lookup"><span data-stu-id="2c36d-158">Confirm the reset.</span></span> <span data-ttu-id="2c36d-159">O dispositivo será reiniciado e exibirá um conjunto de engrenagens giradas e uma barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="2c36d-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="2c36d-160">Aguarde cerca de trinta minutos para a conclusão desse processo.</span><span class="sxs-lookup"><span data-stu-id="2c36d-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="2c36d-161">Quando for concluído, o dispositivo será reiniciado para a experiência "inicial".</span><span class="sxs-lookup"><span data-stu-id="2c36d-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="2c36d-162">Re-instalar o sistema operacional</span><span class="sxs-lookup"><span data-stu-id="2c36d-162">Reinstall the operating system</span></span>

<span data-ttu-id="2c36d-163">Se o dispositivo ainda estiver com problemas após a reinicialização e redefinição, você pode usar uma ferramenta de recuperação no computador para reinstalar o firmware e o sistema operacional do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c36d-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="2c36d-164">Os dados necessários para a redefinição do HoloLens são fornecidos no formato UFF (Full Flash Update), que é semelhante a um arquivo .iso, .wim ou .vhd.</span><span class="sxs-lookup"><span data-stu-id="2c36d-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="2c36d-165">Saiba mais sobre os formatos de arquivo de imagem do FFU.</span><span class="sxs-lookup"><span data-stu-id="2c36d-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="2c36d-166">Você pode instalar um novo sistema operacional no seu HoloLens (1ª geração) usando a Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="2c36d-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="2c36d-167">Antes de usar essa ferramenta, confira se reiniciar ou redefinir o seu HoloLens corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="2c36d-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="2c36d-168">O processo de recuperação pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="2c36d-168">The recovery process may take a while.</span></span> <span data-ttu-id="2c36d-169">Quando terminar, a versão mais recente do software Windows Holographic será instalada.</span><span class="sxs-lookup"><span data-stu-id="2c36d-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="2c36d-170">Para usar a ferramenta, você precisará de um computador que esteja executando o Windows 10 ou posterior, com pelo menos 4 GB de espaço de armazenamento disponível.</span><span class="sxs-lookup"><span data-stu-id="2c36d-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="2c36d-171">Não é possível executar essa ferramenta em uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="2c36d-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="2c36d-172">Recuperar seu HoloLens</span><span class="sxs-lookup"><span data-stu-id="2c36d-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="2c36d-173">No computador, baixe e instale a [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)</span><span class="sxs-lookup"><span data-stu-id="2c36d-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="2c36d-174">Conecte o HoloLens (1ª geração) ao seu computador usando o cabo micro USB que veio com o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2c36d-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="2c36d-175">Execute a Windows Device Recovery Tool e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="2c36d-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="2c36d-176">Se o HoloLens (1ª geração) não for detectado automaticamente, selecione **Meu dispositivo não foi detectado**.</span><span class="sxs-lookup"><span data-stu-id="2c36d-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="2c36d-177">Em seguida, siga as instruções para colocar o dispositivo no modo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="2c36d-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="2c36d-178">Modo de flash manual</span><span class="sxs-lookup"><span data-stu-id="2c36d-178">Manual flashing mode</span></span>

<span data-ttu-id="2c36d-179">Se o seu dispositivo não for detectado, siga estas etapas para inseri-lo no modo flash:</span><span class="sxs-lookup"><span data-stu-id="2c36d-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="2c36d-180">Desconecte o dispositivo de qualquer fonte de alimentação.</span><span class="sxs-lookup"><span data-stu-id="2c36d-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="2c36d-181">Se o dispositivo estiver ativado, mantenha pressionado botão de **energia** até que ele seja completamente desligado.</span><span class="sxs-lookup"><span data-stu-id="2c36d-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="2c36d-182">Segure o botão **aumentar o volume** e toque brevemente no botão de **energia**.</span><span class="sxs-lookup"><span data-stu-id="2c36d-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="2c36d-183">O dispositivo deve ser iniciado e exibir apenas a luz LED central.</span><span class="sxs-lookup"><span data-stu-id="2c36d-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="2c36d-184">Conecte o dispositivo em seu PC.</span><span class="sxs-lookup"><span data-stu-id="2c36d-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="2c36d-185">Abra a ferramenta Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="2c36d-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="2c36d-186">Selecione **Meu dispositivo não foi detectado** e, então, **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="2c36d-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="2c36d-187">Siga as instruções para recuperar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c36d-187">Follow the instructions to recover your device.</span></span>
