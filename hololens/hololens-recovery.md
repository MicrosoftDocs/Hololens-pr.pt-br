---
title: Reiniciar, redefinir ou recuperar o HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Como usar o Advanced Recovery Companion para instalar uma imagem para o HoloLens 2.
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
ms.openlocfilehash: 7845a00d1141fb721683c4e3f2a884ed0c37c735
ms.sourcegitcommit: 33911e3b405732d0d31a27039c8f590d52b647c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "11254828"
---
# <span data-ttu-id="9140d-104">Reiniciar, redefinir ou recuperar o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9140d-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="9140d-105">Carregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9140d-105">Charge the device</span></span>

<span data-ttu-id="9140d-106">Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de 20 a 40% da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="9140d-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="9140d-107">Use o carregador e os cabos USB tipo C que vêm com o dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9140d-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="9140d-108">A fonte de alimentação e o cabo USB-C-to-C que acompanham o dispositivo são a melhor maneira de carregar seu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9140d-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="9140d-109">O carregador fornece 18W de potência (9V a 2A).</span><span class="sxs-lookup"><span data-stu-id="9140d-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="9140d-110">Usando o carregador de parede fornecido, os dispositivos HoloLens 2 podem carregar a bateria completamente em menos de 65 minutos quando o dispositivo está em espera.</span><span class="sxs-lookup"><span data-stu-id="9140d-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="9140d-111">Se esses acessórios não estiverem disponíveis, certifique-se de que o carregador que está disponível possa suportar pelo menos 15W de energia.</span><span class="sxs-lookup"><span data-stu-id="9140d-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="9140d-112">Se possível, evite usar um computador para carregar o dispositivo por USB, pois é lento.</span><span class="sxs-lookup"><span data-stu-id="9140d-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="9140d-113">Se o dispositivo for reinicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria:</span><span class="sxs-lookup"><span data-stu-id="9140d-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="9140d-114">No menu principal da interface de usuário do dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9140d-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="9140d-115">Exibir o LED próximo ao botão de energia (com 40% de carga, você deve ver pelo menos dois LEDS sólidos).</span><span class="sxs-lookup"><span data-stu-id="9140d-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="9140d-116">Quando o dispositivo estiver sendo carregado, o indicador de bateria acenderá para indicar o nível de carga atual.</span><span class="sxs-lookup"><span data-stu-id="9140d-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="9140d-117">A última luz acenderá e apagará para indicar o carregamento ativo.</span><span class="sxs-lookup"><span data-stu-id="9140d-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="9140d-118">Quando sua HoloLens estiver ligada, o indicador de bateria exibe o nível da bateria em cinco incrementos.</span><span class="sxs-lookup"><span data-stu-id="9140d-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="9140d-119">Quando somente uma das cinco luzes estiver acesa, o nível da bateria estará abaixo de 20%.</span><span class="sxs-lookup"><span data-stu-id="9140d-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="9140d-120">Se o nível da bateria estiver muito baixo e você tentar ligar o dispositivo, uma luz piscará rapidamente e apagará.</span><span class="sxs-lookup"><span data-stu-id="9140d-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="9140d-121">No computador host, abra o **Explorador de arquivos** e procure pelo seu dispositivo do HoloLens 2 no lado esquerdo, em **Este computador**.</span><span class="sxs-lookup"><span data-stu-id="9140d-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="9140d-122">Clique com o botão direito do mouse no arquivo e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9140d-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="9140d-123">Uma caixa de diálogo mostrará o nível de carga da bateria.</span><span class="sxs-lookup"><span data-stu-id="9140d-123">A dialog box will show the battery charge level.</span></span>

   ![Uma tela de propriedades do HoloLens 2 mostra o nível de mudança da bateria](images/ResetRecovery2.png)

<span data-ttu-id="9140d-125">Se o dispositivo não conseguir reiniciar até o menu Iniciar, observe a aparência do LED e a enumeração do dispositivo no PC host.</span><span class="sxs-lookup"><span data-stu-id="9140d-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="9140d-126">Em seguida, siga o [guia de solução de problemas](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="9140d-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="9140d-127">Caso o estado do dispositivo não se enquadrar em nenhum dos estados listados no guia de solução de problemas, execute o [procedimento de reinicialização forçada](hololens-recovery.md#hard-reset-procedure) com o dispositivo conectado à fonte de energia, não ao computador host.</span><span class="sxs-lookup"><span data-stu-id="9140d-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="9140d-128">Aguarde pelo menos uma hora para o dispositivo ser carregado.</span><span class="sxs-lookup"><span data-stu-id="9140d-128">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="9140d-129">Redefina o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9140d-129">Reset the device</span></span>

<span data-ttu-id="9140d-130">Sob certas circunstâncias, você pode ter que reiniciar manualmente o dispositivo sem usar o software UI.</span><span class="sxs-lookup"><span data-stu-id="9140d-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="9140d-131">Procedimento padrão</span><span class="sxs-lookup"><span data-stu-id="9140d-131">Standard procedure</span></span>

1. <span data-ttu-id="9140d-132">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="9140d-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="9140d-133">Pressione e mantenha pressionado o botão de **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="9140d-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="9140d-134">Todos os LEDs devem estar desativados.</span><span class="sxs-lookup"><span data-stu-id="9140d-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="9140d-135">Aguarde 2-3 segundos e, em seguida, pressione rapidamente o botão de **energia**.</span><span class="sxs-lookup"><span data-stu-id="9140d-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="9140d-136">Os LEDs próximos ao botão de energia terão uma iluminação e o dispositivo executará a inicialização.</span><span class="sxs-lookup"><span data-stu-id="9140d-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="9140d-137">Conecte o dispositivo ao computador host e, em seguida, abra o Gerenciador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9140d-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="9140d-138">(Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Device Manager**.) Verifique se o dispositivo é identificado corretamente como  *Microsoft HoloLens* conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="9140d-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gerenciador de devive do HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="9140d-140">Procedimento de redefinição de disco</span><span class="sxs-lookup"><span data-stu-id="9140d-140">Hard-reset procedure</span></span>

<span data-ttu-id="9140d-141">Se o procedimento padrão de redefinição não funcionar, use o procedimento de redefinição forçada:</span><span class="sxs-lookup"><span data-stu-id="9140d-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="9140d-142">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="9140d-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="9140d-143">Mantenha pressionada os botões **baixar volume** + **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="9140d-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="9140d-144">O dispositivo será reinicializado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9140d-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="9140d-145">Conecte o dispositivo ao computador host.</span><span class="sxs-lookup"><span data-stu-id="9140d-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="9140d-146">Abra o Gerenciador de Dispositivos (para Windows 10 pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Gerenciador de Dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="9140d-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="9140d-147">Verifique se o dispositivo está identificado corretamente conforme *Microsoft HoloLens* conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="9140d-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery device maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="9140d-149">Limpar a flash do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9140d-149">Clean-reflash the device</span></span>

<span data-ttu-id="9140d-150">Em situações extraordinárias, talvez seja necessário "limpar a flash" no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9140d-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="9140d-151">Observe que não se espera que a limpeza-refluxo afete as seguintes questões:</span><span class="sxs-lookup"><span data-stu-id="9140d-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="9140d-152">Exibir a uniformidade de cor</span><span class="sxs-lookup"><span data-stu-id="9140d-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="9140d-153">Inicialização com som, mas sem saída</span><span class="sxs-lookup"><span data-stu-id="9140d-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="9140d-154">Padrão 1-3-5 LED</span><span class="sxs-lookup"><span data-stu-id="9140d-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="9140d-155">Superaquecimento</span><span class="sxs-lookup"><span data-stu-id="9140d-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="9140d-156">Ocorre um erro no OS (que é diferente do travamento do aplicativo)</span><span class="sxs-lookup"><span data-stu-id="9140d-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="9140d-157">Há duas maneiras de limpar a flash do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9140d-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="9140d-158">Para ambos, você deve primeiro [instalar o Complemento Avançado de Recuperação na Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="9140d-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="9140d-159">Se você limpar a flash do seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição de TPM.</span><span class="sxs-lookup"><span data-stu-id="9140d-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="9140d-160">Por padrão, o Complemento Avançado de Recuperação está configurado para baixar a compilação do recurso mais recente, confira aqui para ler nossas [Notas de lançamento](hololens-release-notes.md#) para saber mais sobre a versão mais recente do recurso.</span><span class="sxs-lookup"><span data-stu-id="9140d-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="9140d-161">Para obter o pacote mais recente do HoloLens 2 Ferramenta de Atualização de Imagens (FFU) para atualizar seu dispositivo por meio do Complemento Avançado de Recuperação, [clique aqui para baixar a última imagem mensal do HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="9140d-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="9140d-162">Esta versão é geralmente a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="9140d-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="9140d-163">Antes de iniciar o procedimento de limpeza da flash, certifique-se de que o aplicativo está instalado e em execução no PC com Windows 10 e está pronto para detectar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9140d-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="9140d-164">Certifique-se também de que seu HoloLens seja carregado em um mínimo de 40%.</span><span class="sxs-lookup"><span data-stu-id="9140d-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Captura de tela de reflash limpa do HoloLens 2](images/ARC1.png)

### <span data-ttu-id="9140d-166">Procedimento normal</span><span class="sxs-lookup"><span data-stu-id="9140d-166">Normal procedure</span></span>

1. <span data-ttu-id="9140d-167">Enquanto o dispositivo do HoloLens estiver em execução, conecte-o ao seu PC com Windows 10, em que você já havia aberto o aplicativo Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="9140d-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="9140d-168">O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="9140d-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Tela inicial da limpeza da flash do HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="9140d-170">Selecione o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.</span><span class="sxs-lookup"><span data-stu-id="9140d-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="9140d-171">Procedimento manual</span><span class="sxs-lookup"><span data-stu-id="9140d-171">Manual procedure</span></span>

<span data-ttu-id="9140d-172">Se o HoloLens 2 não iniciar corretamente, talvez seja necessário colocar o dispositivo no Modo de recuperação:</span><span class="sxs-lookup"><span data-stu-id="9140d-172">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="9140d-173">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="9140d-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="9140d-174">Pressione e mantenha pressionado o botão de **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="9140d-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="9140d-175">Todos os LEDs devem se desligar.</span><span class="sxs-lookup"><span data-stu-id="9140d-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="9140d-176">Enquanto pressiona o botão **aumentar o volume**, pressione e solte o botão **energia** para iniciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9140d-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="9140d-177">Aguarde 15 segundos e, em seguida, solte o botão **aumentar o volume**.</span><span class="sxs-lookup"><span data-stu-id="9140d-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="9140d-178">Apenas o LED central dos cinco LEDs se acenderá.</span><span class="sxs-lookup"><span data-stu-id="9140d-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="9140d-179">Conecte o dispositivo ao computador host e abra o Gerenciador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9140d-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="9140d-180">(Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Gerenciador de Dispositivos**.) Verifique se o dispositivo é identificado corretamente como Microsoft HoloLens conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="9140d-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="9140d-182">O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="9140d-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Tela de limpeza do reflash do HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="9140d-184">Selecione o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.</span><span class="sxs-lookup"><span data-stu-id="9140d-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="9140d-185">Baixando o ARC sem usar a app store</span><span class="sxs-lookup"><span data-stu-id="9140d-185">Download ARC without using the app store</span></span>

<span data-ttu-id="9140d-186">Se um ambiente de TI impede o uso do aplicativo da Windows Store ou limita o acesso à loja, os administradores de TI podem disponibilizá-lo por meio de outros caminhos de implantação "offline".</span><span class="sxs-lookup"><span data-stu-id="9140d-186">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="9140d-187">O administrador de TI também pode distribuir esse aplicativo por meio do SCCM (System Center Configuration Manager) ou do Intune.</span><span class="sxs-lookup"><span data-stu-id="9140d-187">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="9140d-188">Este guia se concentrará no Advanced Recovery Companion, mas ele será modificado para outros aplicativos offline.</span><span class="sxs-lookup"><span data-stu-id="9140d-188">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="9140d-189">Siga estas etapas para habilitar o caminho da implantação:</span><span class="sxs-lookup"><span data-stu-id="9140d-189">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="9140d-190">Acesse a [Microsoft Store para Empresas](https://businessstore.microsoft.com) e entre usando uma identidade do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9140d-190">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="9140d-191">Vá para **Gerenciar – Configurações**.</span><span class="sxs-lookup"><span data-stu-id="9140d-191">Go to **Manage – Settings**.</span></span> <span data-ttu-id="9140d-192">Ative **Mostrar aplicativos offline** em **Experiência de compra**.</span><span class="sxs-lookup"><span data-stu-id="9140d-192">Turn on **Show offline apps** under **Shopping experience**.</span></span>
1. <span data-ttu-id="9140d-193">Vá para **comprar meu grupo**e procure por [ \* *_Complemento Avançado de Recuperação_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="9140d-193">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="9140d-194">Altere o _ *Tipo de Licença*\* para \**_offline_*_ e selecione _ \*Manage\*\*.</span><span class="sxs-lookup"><span data-stu-id="9140d-194">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="9140d-195">Em **Baixe o pacote para uso offline**, selecione o segundo botão azul **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="9140d-195">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="9140d-196">Verifique se a extensão de arquivo é *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="9140d-196">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="9140d-197">Nesse estágio, se o computador Desktop tiver acesso à Internet, clique duas vezes no pacote para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9140d-197">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="9140d-198">Se o computador de destino não tiver conexão à Internet, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9140d-198">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="9140d-199">Selecione a licença não codificada e, em seguida, selecione **Gerar licença**.</span><span class="sxs-lookup"><span data-stu-id="9140d-199">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="9140d-200">Em **Estruturas Necessárias**, marque **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="9140d-200">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="9140d-201">Use o DISM para aplicar o pacote com a dependência e a licença.</span><span class="sxs-lookup"><span data-stu-id="9140d-201">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="9140d-202">Em um prompt de comando de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9140d-202">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="9140d-203">O número de versão neste exemplo de código pode não corresponder à versão disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="9140d-203">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="9140d-204">Você também pode escolher um local de download diferente do especificado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="9140d-204">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="9140d-205">Faça todas as alterações no comando conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9140d-205">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="9140d-206">Quando você planeja usar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil baixar a imagem flash.</span><span class="sxs-lookup"><span data-stu-id="9140d-206">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="9140d-207">[**Baixar a imagem atual para o HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="9140d-207">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>

<span data-ttu-id="9140d-208">Outros recursos:</span><span class="sxs-lookup"><span data-stu-id="9140d-208">Other resources:</span></span>
- [<span data-ttu-id="9140d-209">Distribuir aplicativos offline</span><span class="sxs-lookup"><span data-stu-id="9140d-209">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="9140d-210">Pacote de aplicativos DISM (.appx ou .appxbundle) servindo opções de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="9140d-210">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
