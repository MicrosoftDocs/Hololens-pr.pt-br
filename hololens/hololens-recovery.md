---
title: Reiniciar, redefinir ou recuperar o HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Como usar o Advanced Recovery Companion para instalar imagem no HoloLens 2.
keywords: como fazer, reinicializar, redefinir, recuperar, reinicializar disco, redefinição rápida, ciclo de energia, HoloLens, desligar, arco, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923628"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="e758b-104">Reiniciar, redefinir ou recuperar o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e758b-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e758b-105">Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de **20% a 40%** da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="e758b-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="e758b-106">As [luzes indicadoras de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas sob o botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e758b-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="e758b-107">Use o [carregador e o cabo USB Tipo-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) que veio com o HoloLens 2, pois essa é a melhor maneira de carregar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e758b-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="e758b-108">O carregador fornece 18 W de potência (9 V a 2 A).</span><span class="sxs-lookup"><span data-stu-id="e758b-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="e758b-109">Usando o carregador de parede fornecido, os dispositivos HoloLens 2 podem carregar a bateria completamente em menos de 65 minutos quando o dispositivo está em espera.</span><span class="sxs-lookup"><span data-stu-id="e758b-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="e758b-110">Se esses acessórios não estiverem disponíveis, verifique se o carregador que está disponível consegue suportar pelo menos 15 W de energia.</span><span class="sxs-lookup"><span data-stu-id="e758b-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="e758b-111">Se possível, evite usar um computador para carregar o dispositivo por USB, pois é lento.</span><span class="sxs-lookup"><span data-stu-id="e758b-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="e758b-112">Se o dispositivo for reinicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria:</span><span class="sxs-lookup"><span data-stu-id="e758b-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="e758b-113">No menu principal da interface de usuário do dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e758b-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="e758b-114">Exibir o LED próximo ao botão de energia (com 40% de carga, você deve ver pelo menos dois LEDS sólidos).</span><span class="sxs-lookup"><span data-stu-id="e758b-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="e758b-115">Quando o dispositivo estiver sendo carregado, o indicador de bateria acenderá para indicar o nível de carga atual.</span><span class="sxs-lookup"><span data-stu-id="e758b-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="e758b-116">A última luz acenderá e apagará para indicar o carregamento ativo.</span><span class="sxs-lookup"><span data-stu-id="e758b-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="e758b-117">Quando o HoloLens estiver ligado, o indicador de bateria exibe o nível da bateria em cinco incrementos.</span><span class="sxs-lookup"><span data-stu-id="e758b-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="e758b-118">Quando somente uma das cinco luzes estiver acesa, o nível da bateria estará abaixo de 20%.</span><span class="sxs-lookup"><span data-stu-id="e758b-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="e758b-119">Se o nível da bateria estiver muito baixo e você tentar ligar o dispositivo, uma luz piscará rapidamente e apagará.</span><span class="sxs-lookup"><span data-stu-id="e758b-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="e758b-120">No computador host, abra o **Explorador de Arquivos** e procure seu dispositivo HoloLens 2 no lado esquerdo em **Este Computador**.</span><span class="sxs-lookup"><span data-stu-id="e758b-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="e758b-121">Clique com o botão direito do mouse no dispositivo e escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e758b-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="e758b-122">Uma caixa de diálogo mostrará o nível de carga da bateria.</span><span class="sxs-lookup"><span data-stu-id="e758b-122">A dialog box will show the battery charge level.</span></span>

   ![Uma tela de propriedades do HoloLens 2 mostra o nível de mudança da bateria](images/ResetRecovery2.png)

<span data-ttu-id="e758b-124">Se o dispositivo não conseguir reiniciar pelo menu Iniciar, observe a aparência do LED e a enumeração do dispositivo no PC host.</span><span class="sxs-lookup"><span data-stu-id="e758b-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="e758b-125">Em seguida, siga o [guia de solução de problemas](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="e758b-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="e758b-126">Caso o estado do dispositivo não se enquadrar em nenhum dos estados listados no guia de solução de problemas, execute o [reinicialização forçada](hololens-recovery.md#hard-reset-procedure) com o dispositivo conectado à fonte de energia, não ao computador host.</span><span class="sxs-lookup"><span data-stu-id="e758b-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="e758b-127">Aguarde pelo menos uma hora para o dispositivo ser carregado.</span><span class="sxs-lookup"><span data-stu-id="e758b-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="e758b-128">Redefinir o dispositivo</span><span class="sxs-lookup"><span data-stu-id="e758b-128">Reset the device</span></span>

<span data-ttu-id="e758b-129">Sob certas circunstâncias, você pode ter que reiniciar manualmente o dispositivo sem usar o software UI.</span><span class="sxs-lookup"><span data-stu-id="e758b-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="e758b-130">Procedimento padrão</span><span class="sxs-lookup"><span data-stu-id="e758b-130">Standard procedure</span></span>

1. <span data-ttu-id="e758b-131">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="e758b-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="e758b-132">Pressione e mantenha pressionado o botão de **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="e758b-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="e758b-133">Todos os LEDs devem estar desativados.</span><span class="sxs-lookup"><span data-stu-id="e758b-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="e758b-134">Aguarde 2-3 segundos e, em seguida, pressione rapidamente o botão de **energia**.</span><span class="sxs-lookup"><span data-stu-id="e758b-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="e758b-135">Os LEDs próximos ao botão de energia terão uma iluminação e o dispositivo executará a inicialização.</span><span class="sxs-lookup"><span data-stu-id="e758b-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="e758b-136">Conecte o dispositivo ao computador host e, em seguida, abra o Gerenciador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e758b-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="e758b-137">(Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e escolha **Gerenciador de Dispositivos**.) Verifique se o dispositivo é identificado corretamente como *Microsoft HoloLens* conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="e758b-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gerenciador de dispositivos do HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="e758b-139">Procedimento de redefinição de disco</span><span class="sxs-lookup"><span data-stu-id="e758b-139">Hard-reset procedure</span></span>

<span data-ttu-id="e758b-140">Se o procedimento padrão de redefinição não funcionar, use o procedimento de redefinição forçada:</span><span class="sxs-lookup"><span data-stu-id="e758b-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="e758b-141">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="e758b-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="e758b-142">Mantenha os botões de **diminuir o volume** + **energia** pressionados por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="e758b-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="e758b-143">O dispositivo será reinicializado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e758b-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="e758b-144">Conecte o dispositivo ao computador host.</span><span class="sxs-lookup"><span data-stu-id="e758b-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="e758b-145">Abra Gerenciador de Dispositivos (para Windows 10, pressione a tecla **Windows**, a tecla **X** e, em seguida, escolha **Gerenciador de Dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="e758b-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="e758b-146">Verifique se o dispositivo está identificado corretamente conforme *Microsoft HoloLens*, conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="e758b-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gerenciador de dispositivos 2 MicrosoftHoloLensRecovery do HoloLens 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="e758b-148">Limpeza da reflash do dispositivo</span><span class="sxs-lookup"><span data-stu-id="e758b-148">Clean-reflash the device</span></span>

<span data-ttu-id="e758b-149">Em situações extraordinárias, talvez seja necessário "limpar a flash" no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e758b-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="e758b-150">Observe que não se espera que a limpeza da reflash afete as seguintes questões:</span><span class="sxs-lookup"><span data-stu-id="e758b-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="e758b-151">Exibir a uniformidade de cor</span><span class="sxs-lookup"><span data-stu-id="e758b-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="e758b-152">Inicialização com som, mas sem saída</span><span class="sxs-lookup"><span data-stu-id="e758b-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="e758b-153">Padrão de LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="e758b-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="e758b-154">Superaquecimento</span><span class="sxs-lookup"><span data-stu-id="e758b-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="e758b-155">Ocorre um erro no SO (que é diferente do travamento do aplicativo)</span><span class="sxs-lookup"><span data-stu-id="e758b-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="e758b-156">Há duas maneiras de limpar a reflash do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e758b-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="e758b-157">Para ambos, você deve primeiro [instalar o Advanced Recovery Companion pela Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="e758b-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="e758b-158">Se você limpar a flash do seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição de TPM.</span><span class="sxs-lookup"><span data-stu-id="e758b-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="e758b-159">Por padrão, o Complemento Avançado de Recuperação está configurado para baixar a compilação do recurso mais recente, confira aqui para ler nossas [notas sobre a versão](hololens-release-notes.md#) para saber mais sobre a versão mais recente do recurso.</span><span class="sxs-lookup"><span data-stu-id="e758b-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="e758b-160">Para obter o pacote HoloLens 2 FFU (Atualização Flash Completa) mais recente para fazer reflash do seu dispositivo por meio do Advanced Recovery Companion, [clique aqui para baixar a imagem HoloLens 2 mais recente](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="e758b-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="e758b-161">Esta versão é geralmente a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="e758b-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="e758b-162">Antes de iniciar o procedimento de limpeza da flash, o aplicativo deve está instalado e em execução no PC com Windows 10 e pronto para detectar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e758b-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="e758b-163">O HoloLens também deve estar carregado em um mínimo de 40%.</span><span class="sxs-lookup"><span data-stu-id="e758b-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Captura de tela de reflash limpa do HoloLens 2](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="e758b-165">Procedimento normal</span><span class="sxs-lookup"><span data-stu-id="e758b-165">Normal procedure</span></span>

1. <span data-ttu-id="e758b-166">Enquanto o dispositivo do HoloLens estiver em execução, conecte-o ao seu PC com Windows 10, em que você já havia aberto o aplicativo Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="e758b-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="e758b-167">O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="e758b-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Tela inicial da limpeza da flash do HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="e758b-169">Escolha o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.</span><span class="sxs-lookup"><span data-stu-id="e758b-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="e758b-170">Procedimento manual</span><span class="sxs-lookup"><span data-stu-id="e758b-170">Manual procedure</span></span>

<span data-ttu-id="e758b-171">Se o HoloLens 2 não iniciar corretamente ou se o Advanced Recovery Companion não conseguir detectar o dispositivo, talvez seja necessário colocar o dispositivo no modo de recuperação:</span><span class="sxs-lookup"><span data-stu-id="e758b-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="e758b-172">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="e758b-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="e758b-173">Pressione e mantenha pressionado o botão de **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="e758b-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="e758b-174">Todos os LEDs devem se desligar.</span><span class="sxs-lookup"><span data-stu-id="e758b-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="e758b-175">Ao pressionar o botão **aumentar volume**, pressione e solte o botão de **energia** para iniciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e758b-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="e758b-176">Aguarde 15 segundos e solte o botão **aumentar volume**.</span><span class="sxs-lookup"><span data-stu-id="e758b-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="e758b-177">Apenas o LED central dos cinco LEDs se acenderá.</span><span class="sxs-lookup"><span data-stu-id="e758b-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="e758b-178">Conecte o dispositivo ao computador host e abra o Gerenciador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e758b-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="e758b-179">(Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e escolha **Gerenciador de Dispositivos**.) Verifique se o dispositivo é identificado corretamente como Microsoft HoloLens conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="e758b-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="e758b-181">O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="e758b-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Tela de limpeza da reflash do HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="e758b-183">Escolha o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.</span><span class="sxs-lookup"><span data-stu-id="e758b-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="e758b-184">Solucionar problemas do Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="e758b-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="e758b-185">Verifique se o dispositivo é carregado em 40% ou mais antes de tentar instalar imagem.</span><span class="sxs-lookup"><span data-stu-id="e758b-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="e758b-186">Verifique se o dispositivo está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="e758b-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="e758b-187">Se o ARC não detectar seu dispositivo, verifique se você pode se conectar a ele por meio Explorador de Arquivos em seu computador.</span><span class="sxs-lookup"><span data-stu-id="e758b-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="e758b-188">Se não for possível:</span><span class="sxs-lookup"><span data-stu-id="e758b-188">If you cannot;</span></span>

    1.  <span data-ttu-id="e758b-189">É possível que seu dispositivo tenha políticas de USB que desabilitam essa conexão.</span><span class="sxs-lookup"><span data-stu-id="e758b-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="e758b-190">Em caso afirmativo, tente o [Modo de flash manual](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="e758b-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="e758b-191">Se não houver nenhuma política, tente um cabo USB diferente.</span><span class="sxs-lookup"><span data-stu-id="e758b-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="e758b-192">Verifique se o dispositivo não exibe um [padrão de LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).</span><span class="sxs-lookup"><span data-stu-id="e758b-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="e758b-193">Baixar o ARC sem usar a app store</span><span class="sxs-lookup"><span data-stu-id="e758b-193">Download ARC without using the app store</span></span>

<span data-ttu-id="e758b-194">Se um ambiente de TI impede o uso do aplicativo da Windows Store ou limita o acesso à loja, os administradores de TI podem disponibilizá-lo por meio de outros caminhos de implantação "offline".</span><span class="sxs-lookup"><span data-stu-id="e758b-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="e758b-195">O administrador de TI também pode distribuir esse aplicativo por meio do SCCM (System Center Configuration Manager) ou do Intune.</span><span class="sxs-lookup"><span data-stu-id="e758b-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="e758b-196">Este guia se concentrará no Advanced Recovery Companion, mas ele será modificado para outros aplicativos offline.</span><span class="sxs-lookup"><span data-stu-id="e758b-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="e758b-197">Siga estas etapas para habilitar o caminho da implantação:</span><span class="sxs-lookup"><span data-stu-id="e758b-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="e758b-198">Acesse o [Microsoft Store para Empresas](https://businessstore.microsoft.com) e entre usando uma identidade do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e758b-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="e758b-199">Vá para **Gerenciar – Configurações**.</span><span class="sxs-lookup"><span data-stu-id="e758b-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="e758b-200">Ative **Mostrar aplicativos offline** em **Experiência de compra**.</span><span class="sxs-lookup"><span data-stu-id="e758b-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="e758b-201">Acesse **Comprar para meu grupo** e procure [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="e758b-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="e758b-202">Mude o **Tipo de Licença** para **_offline_ *_ e escolha _* Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="e758b-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="e758b-203">Em **Fazer download do pacote para uso offline**, escolha o segundo botão de **Download** azul.</span><span class="sxs-lookup"><span data-stu-id="e758b-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="e758b-204">Verifique se a extensão de arquivo é *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="e758b-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="e758b-205">Nesse estágio, se o computador desktop tiver acesso à Internet, clique duas vezes no pacote para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e758b-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="e758b-206">Se o computador de destino não tiver conexão à Internet, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e758b-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="e758b-207">Escolha a licença não codificada e, em seguida, escolha **Gerar licença**.</span><span class="sxs-lookup"><span data-stu-id="e758b-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="e758b-208">Em **Estruturas necessárias**, escolha **Fazer download**.</span><span class="sxs-lookup"><span data-stu-id="e758b-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="e758b-209">Use o DISM para aplicar o pacote com a dependência e a licença.</span><span class="sxs-lookup"><span data-stu-id="e758b-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="e758b-210">Em um prompt de comando de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e758b-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="e758b-211">O número de versão neste exemplo de código pode não corresponder à versão disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="e758b-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="e758b-212">Você também pode escolher um local de download diferente do especificado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="e758b-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="e758b-213">Faça todas as alterações no comando conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e758b-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="e758b-214">Quando você planeja usar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil baixar a imagem flash.</span><span class="sxs-lookup"><span data-stu-id="e758b-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="e758b-215">[**Fazer download da imagem atual para HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="e758b-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="e758b-216">Outros recursos:</span><span class="sxs-lookup"><span data-stu-id="e758b-216">Other resources:</span></span>
- [<span data-ttu-id="e758b-217">Distribuir aplicativos offline</span><span class="sxs-lookup"><span data-stu-id="e758b-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="e758b-218">Pacote de aplicativos DISM (.appx ou .appxbundle) servindo opções de linha de comando</span><span class="sxs-lookup"><span data-stu-id="e758b-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
