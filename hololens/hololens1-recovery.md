---
title: Reiniciar, redefinir ou recuperar o HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como usar a ferramenta de recuperação de dispositivo do Windows para atualizar uma imagem para 1ª gen de HoloLens.
keywords: instruções, reinicialização, redefinição, recuperação, redefinição de hardware, redefinição reversível, ciclo de energia, HoloLens, desligamento, wdrt, ferramenta de recuperação de dispositivo do Windows
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308111"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="6f8c0-104">Reiniciar, redefinir ou recuperar o HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="6f8c0-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="6f8c0-105">Se você estiver enfrentando problemas com o seu HoloLens, convém tentar uma reinicialização ou redefinição, ou até mesmo refazer o reflash do dispositivo usando a recuperação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="6f8c0-106">Este artigo orienta você pelas etapas de recuperação recomendadas na ordem.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="6f8c0-107">Se você pretende recuperar um HoloLens 2, consulte [recuperando um hololens 2](https://docs.microsoft.com/hololens/hololens-recovery), pois esse processo é diferente.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="6f8c0-108">Este artigo se concentra no dispositivo e software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="6f8c0-109">Se os hologramas não parecem corretos, consulte Considerações sobre o **[ambiente do HoloLens](hololens-environment-considerations.md)** para obter informações sobre fatores que melhoram a qualidade do holograma.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="6f8c0-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="6f8c0-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="6f8c0-111">Fazer uma reinicialização segura usando a Cortana</span><span class="sxs-lookup"><span data-stu-id="6f8c0-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="6f8c0-112">A maneira mais segura de reiniciar o HoloLens é usando a Cortana, que geralmente é a primeira coisa a ser tentada quando você enfrenta um problema com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="6f8c0-113">A Cortana não está disponível em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="6f8c0-114">A Cortana está disponível em todos os dispositivos de HoloLens (1º gen).</span><span class="sxs-lookup"><span data-stu-id="6f8c0-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="6f8c0-115">A Cortana está disponível em dispositivos de HoloLens 2 em builds anteriores ao holograpic do Windows, versão 2004 atualização.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="6f8c0-116">Ative seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="6f8c0-117">Verifique se um usuário está conectado e se o dispositivo não está aguardando uma senha para desbloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="6f8c0-118">Diga "Ei Cortana, reboot" ou "Ei Cortana, reiniciar".</span><span class="sxs-lookup"><span data-stu-id="6f8c0-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="6f8c0-119">O Cortana responderá e solicitará que você confirme.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="6f8c0-120">Aguarde a reprodução de um som após a pergunta e, em seguida, diga "Sim".</span><span class="sxs-lookup"><span data-stu-id="6f8c0-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="6f8c0-121">O dispositivo será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="6f8c0-122">Usar o botão de energia para fazer uma reinicialização segura</span><span class="sxs-lookup"><span data-stu-id="6f8c0-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="6f8c0-123">Se você ainda não conseguir reiniciar o dispositivo, tente reiniciá-lo usando o botão de **energia** :</span><span class="sxs-lookup"><span data-stu-id="6f8c0-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="6f8c0-124">Pressione e segure o botão de **energia** por 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="6f8c0-125">Depois de 1 segundo, todos os cinco LEDs se acenderão e desligarão lentamente um por um da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="6f8c0-126">Após 5 segundos, todos os LEDs estarão desativados, indicando o desligamento bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="6f8c0-127">Pare de pressionar o botão imediatamente depois que todos os LEDs estiverem desligados.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="6f8c0-128">Aguarde 1 minuto para a conclusão do desligamento.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="6f8c0-129">O desligamento ainda pode estar em andamento mesmo depois que as exibições estiverem desativadas.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="6f8c0-130">Ligue o dispositivo novamente pressionando e segurando o botão de **energia** por 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="6f8c0-131">Fazer uma reinicialização segura usando o portal de dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="6f8c0-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="6f8c0-132">Para esse processo, o HoloLens deve ser configurado como um dispositivo de desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="6f8c0-133">Saiba mais no [portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="6f8c0-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="6f8c0-134">Se o procedimento anterior não funcionou, tente reiniciar o dispositivo usando o [portal de dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="6f8c0-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="6f8c0-135">No canto superior direito, localize a opção para reiniciar ou desligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="6f8c0-136">Fazer uma reinicialização forçada não segura</span><span class="sxs-lookup"><span data-stu-id="6f8c0-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="6f8c0-137">Se os métodos anteriores não reiniciaram o HoloLens, Force uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="6f8c0-138">Esse método é equivalente a remover e reinstalar a bateria.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="6f8c0-139">É perigoso porque pode deixar seu dispositivo em um estado corrompido.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="6f8c0-140">Se isso acontecer, você precisará atualizar seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="6f8c0-141">Esse é um método potencialmente prejudicial e só deve ser usado se os métodos citados anteriormente não funcionaram.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="6f8c0-142">Pressione e mantenha pressionado o botão de **energia** por pelo menos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="6f8c0-143">Não há problema em manter o botão por mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="6f8c0-144">É seguro ignorar qualquer atividade de LED.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="6f8c0-145">Solte o botão e aguarde 2-3 segundos.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="6f8c0-146">Pressione e segure o botão de **energia** por 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="6f8c0-147">Se você ainda tiver problemas, pressione o botão de **energia** por 4 segundos até que todos os indicadores de bateria apareçam e a tela pare de exibir os hologramas.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="6f8c0-148">Aguarde um minuto e pressione o botão de **energia** novamente para ligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="6f8c0-149">Redefinir para as configurações de fábrica</span><span class="sxs-lookup"><span data-stu-id="6f8c0-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="6f8c0-150">A bateria precisa de pelo menos um encargo de 40% para ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="6f8c0-151">Se o seu HoloLens ainda tiver um problema, tente redefini-lo para o estado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="6f8c0-152">Esta etapa mantém a versão do software Holographic do Windows que está instalada e retorna todo o resto às configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="6f8c0-153">Se você redefinir seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição do TPM.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="6f8c0-154">A redefinição instalará apenas a versão mais recente instalada do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="6f8c0-155">Você precisará refazer todas as etapas de inicialização (calibrar, conectar-se ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="6f8c0-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="6f8c0-156">Abra o aplicativo Configurações e, em seguida, selecione **Atualizar**  >  **recuperação**.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="6f8c0-157">Selecione a opção **Redefinir dispositivo** e leia a mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="6f8c0-158">Confirme a redefinição.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-158">Confirm the reset.</span></span> <span data-ttu-id="6f8c0-159">O dispositivo será reiniciado e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="6f8c0-160">Aguarde cerca de 30 minutos para que esse processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="6f8c0-161">Quando terminar, o dispositivo será reiniciado na experiência "pronta para uso".</span><span class="sxs-lookup"><span data-stu-id="6f8c0-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="6f8c0-162">Reinstalar o sistema operacional</span><span class="sxs-lookup"><span data-stu-id="6f8c0-162">Reinstall the operating system</span></span>

<span data-ttu-id="6f8c0-163">Se o dispositivo ainda estiver tendo um problema após a reinicialização e a redefinição, você poderá usar uma ferramenta de recuperação no computador para reinstalar o sistema operacional e o firmware do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="6f8c0-164">Os dados que o HoloLens precisa para a redefinição são empacotados em uma atualização completa do flash (FFU), que é semelhante a um arquivo. ISO,. wim ou. vhd.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="6f8c0-165">Saiba mais sobre os formatos de arquivo de imagem FFU.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="6f8c0-166">Você pode instalar um novo sistema operacional em seu HoloLens (1ª gen) usando a ferramenta de recuperação de dispositivo do Windows.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="6f8c0-167">Antes de usar essa ferramenta, confira se a reinicialização ou a redefinição de seu HoloLens corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="6f8c0-168">O processo de recuperação pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-168">The recovery process may take a while.</span></span> <span data-ttu-id="6f8c0-169">Quando terminar, a versão mais recente do software Holographic do Windows será instalada.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="6f8c0-170">Para usar a ferramenta, você precisa de um computador com Windows 10 ou posterior com pelo menos 4 GB de espaço livre de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="6f8c0-171">Você não pode executar essa ferramenta em uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="6f8c0-172">Recuperar seu HoloLens</span><span class="sxs-lookup"><span data-stu-id="6f8c0-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="6f8c0-173">Baixe e instale a [ferramenta de recuperação de dispositivo do Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) em seu computador.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="6f8c0-174">Conecte o HoloLens (1º gen) ao seu computador usando o cabo micro USB que acompanha o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="6f8c0-175">Abra a ferramenta de recuperação de dispositivo do Windows e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="6f8c0-176">Se o HoloLens (1º gen) não for detectado automaticamente, selecione **meu dispositivo não foi detectado**.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="6f8c0-177">Em seguida, siga as instruções para colocar o dispositivo no modo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="6f8c0-178">Modo de intermitência manual</span><span class="sxs-lookup"><span data-stu-id="6f8c0-178">Manual flashing mode</span></span>

<span data-ttu-id="6f8c0-179">Se o dispositivo não for detectado, siga estas etapas para colocá-lo no modo flash:</span><span class="sxs-lookup"><span data-stu-id="6f8c0-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="6f8c0-180">Desconecte o dispositivo de qualquer fonte de energia.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="6f8c0-181">Se o dispositivo estiver ligado, mantenha o botão de **energia** pressionado até que ele seja completamente desligado.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="6f8c0-182">Mantenha o botão do **volume** pressionado e toque brevemente no botão de **energia** .</span><span class="sxs-lookup"><span data-stu-id="6f8c0-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="6f8c0-183">O dispositivo deve iniciar e exibir apenas a luz do LED do meio.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="6f8c0-184">Conecte o dispositivo ao seu PC.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="6f8c0-185">Abra a ferramenta de recuperação de dispositivo do Windows.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="6f8c0-186">Selecione **meu dispositivo não foi detectado** e, em seguida, **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="6f8c0-187">Siga as instruções para recuperar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f8c0-187">Follow the instructions to recover your device.</span></span>
