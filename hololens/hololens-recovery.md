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
ms.openlocfilehash: 8c028ed39cf0925ebff18ca69889de2d87f1e7eb
ms.sourcegitcommit: e3056a433aeebb8bc45dc3f6db9a75f212fdf53b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996409"
---
# <span data-ttu-id="cf397-104">Reiniciar, redefinir ou recuperar o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="cf397-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="cf397-105">Carregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="cf397-105">Charge the device</span></span>

<span data-ttu-id="cf397-106">Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de 20 a 40% da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="cf397-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="cf397-107">Use o carregador e os cabos USB tipo C que vêm com o dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cf397-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="cf397-108">A fonte de alimentação e o cabo USB-C-to-C que acompanham o dispositivo são a melhor maneira de carregar seu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cf397-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="cf397-109">O carregador fornece 18W de potência (9V a 2A).</span><span class="sxs-lookup"><span data-stu-id="cf397-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="cf397-110">Se esses acessórios não estiverem disponíveis, certifique-se de que o carregador que está disponível possa suportar pelo menos 15W de energia.</span><span class="sxs-lookup"><span data-stu-id="cf397-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="cf397-111">Se possível, evite usar um computador para carregar o dispositivo por USB, pois é lento.</span><span class="sxs-lookup"><span data-stu-id="cf397-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="cf397-112">Se o dispositivo for reinicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria:</span><span class="sxs-lookup"><span data-stu-id="cf397-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="cf397-113">No menu principal da interface de usuário do dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cf397-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="cf397-114">Exibir o LED próximo ao botão de energia (com 40% de carga, você deve ver pelo menos dois LEDS sólidos).</span><span class="sxs-lookup"><span data-stu-id="cf397-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="cf397-115">Quando o dispositivo estiver sendo carregado, o indicador de bateria acenderá para indicar o nível de carga atual.</span><span class="sxs-lookup"><span data-stu-id="cf397-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="cf397-116">A última luz acenderá e apagará para indicar o carregamento ativo.</span><span class="sxs-lookup"><span data-stu-id="cf397-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="cf397-117">Quando sua HoloLens estiver ligada, o indicador de bateria exibe o nível da bateria em cinco incrementos.</span><span class="sxs-lookup"><span data-stu-id="cf397-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="cf397-118">Quando somente uma das cinco luzes estiver acesa, o nível da bateria estará abaixo de 20%.</span><span class="sxs-lookup"><span data-stu-id="cf397-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="cf397-119">Se o nível da bateria estiver muito baixo e você tentar ligar o dispositivo, uma luz piscará rapidamente e apagará.</span><span class="sxs-lookup"><span data-stu-id="cf397-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="cf397-120">No computador host, abra o **Explorador de arquivos** e procure pelo seu dispositivo do HoloLens 2 no lado esquerdo, em **Este computador**.</span><span class="sxs-lookup"><span data-stu-id="cf397-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="cf397-121">Clique com o botão direito do mouse no arquivo e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="cf397-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="cf397-122">Uma caixa de diálogo mostrará o nível de carga da bateria.</span><span class="sxs-lookup"><span data-stu-id="cf397-122">A dialog box will show the battery charge level.</span></span>

   ![Uma tela de propriedades do HoloLens 2 mostra o nível de mudança da bateria](images/ResetRecovery2.png)

<span data-ttu-id="cf397-124">Se o dispositivo não conseguir reiniciar até o menu Iniciar, observe a aparência do LED e a enumeração do dispositivo no PC host.</span><span class="sxs-lookup"><span data-stu-id="cf397-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="cf397-125">Em seguida, siga o [guia de solução de problemas](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="cf397-125">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="cf397-126">Caso o estado do dispositivo não se enquadrar em nenhum dos estados listados no guia de solução de problemas, execute o [procedimento de reinicialização forçada](hololens-recovery.md#hard-reset-procedure) com o dispositivo conectado à fonte de energia, não ao computador host.</span><span class="sxs-lookup"><span data-stu-id="cf397-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="cf397-127">Aguarde pelo menos uma hora para o dispositivo ser carregado.</span><span class="sxs-lookup"><span data-stu-id="cf397-127">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="cf397-128">Redefina o dispositivo</span><span class="sxs-lookup"><span data-stu-id="cf397-128">Reset the device</span></span>

<span data-ttu-id="cf397-129">Sob certas circunstâncias, você pode ter que reiniciar manualmente o dispositivo sem usar o software UI.</span><span class="sxs-lookup"><span data-stu-id="cf397-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="cf397-130">Procedimento padrão</span><span class="sxs-lookup"><span data-stu-id="cf397-130">Standard procedure</span></span>
1. <span data-ttu-id="cf397-131">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="cf397-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="cf397-132">Pressione e mantenha pressionado o botão de **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="cf397-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="cf397-133">Todos os LEDs devem estar desativados.</span><span class="sxs-lookup"><span data-stu-id="cf397-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="cf397-134">Aguarde 2-3 segundos e, em seguida, pressione rapidamente o botão de **energia**.</span><span class="sxs-lookup"><span data-stu-id="cf397-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="cf397-135">Os LEDs próximos ao botão de energia terão uma iluminação e o dispositivo executará a inicialização.</span><span class="sxs-lookup"><span data-stu-id="cf397-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="cf397-136">Conecte o dispositivo ao computador host e, em seguida, abra o Gerenciador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cf397-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="cf397-137">(Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Device Manager**.) Verifique se o dispositivo é identificado corretamente como  *Microsoft HoloLens* conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf397-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="cf397-139">Procedimento de redefinição de disco</span><span class="sxs-lookup"><span data-stu-id="cf397-139">Hard-reset procedure</span></span>

<span data-ttu-id="cf397-140">Se o procedimento padrão de redefinição não funcionar, use o procedimento de redefinição forçada:</span><span class="sxs-lookup"><span data-stu-id="cf397-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="cf397-141">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="cf397-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="cf397-142">Mantenha pressionada os botões **baixar volume** + **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="cf397-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="cf397-143">O dispositivo será reinicializado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cf397-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="cf397-144">Conecte o dispositivo ao computador host.</span><span class="sxs-lookup"><span data-stu-id="cf397-144">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="cf397-145">Abra o Gerenciador de Dispositivos (para Windows 10 pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Gerenciador de Dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="cf397-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="cf397-146">Verifique se o dispositivo está identificado corretamente conforme *Microsoft HoloLens* conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf397-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="cf397-148">Limpar a flash do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cf397-148">Clean-reflash the device</span></span>

<span data-ttu-id="cf397-149">Em situações extraordinárias, talvez seja necessário "limpar a flash" no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cf397-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="cf397-150">Observe que não se espera que a limpeza-refluxo afete as seguintes questões:</span><span class="sxs-lookup"><span data-stu-id="cf397-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="cf397-151">Exibir a uniformidade de cor</span><span class="sxs-lookup"><span data-stu-id="cf397-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="cf397-152">Inicialização com som, mas sem saída</span><span class="sxs-lookup"><span data-stu-id="cf397-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="cf397-153">Padrão 1-3-5 LED</span><span class="sxs-lookup"><span data-stu-id="cf397-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="cf397-154">Superaquecimento</span><span class="sxs-lookup"><span data-stu-id="cf397-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="cf397-155">Ocorre um erro no OS (que é diferente do travamento do aplicativo)</span><span class="sxs-lookup"><span data-stu-id="cf397-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="cf397-156">Há duas maneiras de limpar a flash do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cf397-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="cf397-157">Para ambos, você deve primeiro instalar o [Advanced Recovery Companion na Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="cf397-157">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="cf397-158">Se você limpar a flash do seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição de TPM.</span><span class="sxs-lookup"><span data-stu-id="cf397-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="cf397-159">Por padrão, o Advanced Recovery Companion está definido atualmente para baixar a versão de lançamento do recurso para [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="cf397-159">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="cf397-160">Para obter o pacote mais recente da imagem no formato UFF (Full Flash Update) do HoloLens 2 para limpar a flash do seu dispositivo por meio da Advanced Recovery Companion, [baixe aqui](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="cf397-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="cf397-161">Esta versão é geralmente a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="cf397-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="cf397-162">Antes de iniciar o procedimento de limpeza da flash, certifique-se de que o aplicativo está instalado e em execução no PC com Windows 10 e está pronto para detectar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cf397-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Captura de tela de reflash limpa do HoloLens 2](images/ARC1.png)

### <span data-ttu-id="cf397-164">Procedimento normal</span><span class="sxs-lookup"><span data-stu-id="cf397-164">Normal procedure</span></span>

1. <span data-ttu-id="cf397-165">Enquanto o dispositivo do HoloLens estiver em execução, conecte-o ao seu PC com Windows 10, em que você já havia aberto o aplicativo Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="cf397-165">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="cf397-166">O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="cf397-166">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Tela inicial da limpeza da flash do HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="cf397-168">Selecione o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.</span><span class="sxs-lookup"><span data-stu-id="cf397-168">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="cf397-169">Procedimento manual</span><span class="sxs-lookup"><span data-stu-id="cf397-169">Manual procedure</span></span>

<span data-ttu-id="cf397-170">Se o HoloLens 2 não iniciar corretamente, talvez seja necessário colocar o dispositivo no Modo de recuperação:</span><span class="sxs-lookup"><span data-stu-id="cf397-170">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="cf397-171">Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.</span><span class="sxs-lookup"><span data-stu-id="cf397-171">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="cf397-172">Pressione e mantenha pressionado o botão de **energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="cf397-172">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="cf397-173">Todos os LEDs devem se desligar.</span><span class="sxs-lookup"><span data-stu-id="cf397-173">All LEDs should turn off.</span></span>

3. <span data-ttu-id="cf397-174">Enquanto pressiona o botão **aumentar o volume**, pressione e solte o botão **energia** para iniciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cf397-174">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="cf397-175">Aguarde 15 segundos e, em seguida, solte o botão **aumentar o volume**.</span><span class="sxs-lookup"><span data-stu-id="cf397-175">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="cf397-176">Apenas o LED central dos cinco LEDs se acenderá.</span><span class="sxs-lookup"><span data-stu-id="cf397-176">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="cf397-177">Conecte o dispositivo ao computador host e abra o Gerenciador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cf397-177">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="cf397-178">(Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Gerenciador de Dispositivos**.) Verifique se o dispositivo é identificado corretamente como Microsoft HoloLens conforme mostrado na imagem a seguir:</span><span class="sxs-lookup"><span data-stu-id="cf397-178">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="cf397-180">O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:</span><span class="sxs-lookup"><span data-stu-id="cf397-180">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Tela de limpeza do reflash do HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="cf397-182">Selecione o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.</span><span class="sxs-lookup"><span data-stu-id="cf397-182">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="cf397-183">Baixando o ARC sem usar a app store</span><span class="sxs-lookup"><span data-stu-id="cf397-183">Download ARC without using the app store</span></span>

<span data-ttu-id="cf397-184">Se um ambiente de TI impede o uso do aplicativo da Windows Store ou limita o acesso à loja, os administradores de TI podem disponibilizá-lo por meio de outros caminhos de implantação "offline".</span><span class="sxs-lookup"><span data-stu-id="cf397-184">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="cf397-185">O administrador de TI também pode distribuir esse aplicativo por meio do SCCM (System Center Configuration Manager) ou do Intune.</span><span class="sxs-lookup"><span data-stu-id="cf397-185">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="cf397-186">Este guia se concentrará no Advanced Recovery Companion, mas ele será modificado para outros aplicativos offline.</span><span class="sxs-lookup"><span data-stu-id="cf397-186">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="cf397-187">Siga estas etapas para habilitar o caminho da implantação:</span><span class="sxs-lookup"><span data-stu-id="cf397-187">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="cf397-188">Acesse a [Microsoft Store para Empresas](https://businessstore.microsoft.com) e entre usando uma identidade do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cf397-188">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="cf397-189">Vá para **Gerenciar – Configurações**.</span><span class="sxs-lookup"><span data-stu-id="cf397-189">Go to **Manage – Settings**.</span></span> <span data-ttu-id="cf397-190">Ative **Mostrar aplicativos offline** em **Experiência de compra**.</span><span class="sxs-lookup"><span data-stu-id="cf397-190">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="cf397-191">Vá para **comprar para o meu grupo** e procure por [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="cf397-191">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="cf397-192">Altere o **Tipo de Licença** para ***offline*** e clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="cf397-192">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="cf397-193">Em **Baixe o pacote para uso offline**, selecione o segundo botão azul **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="cf397-193">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="cf397-194">Verifique se a extensão de arquivo é *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="cf397-194">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="cf397-195">Nessa etapa, se o PC tiver acesso à Internet, basta clicar duas vezes para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cf397-195">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="cf397-196">Se o computador de destino não tiver conexão à Internet, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="cf397-196">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="cf397-197">Selecione a licença não codificada e, em seguida, selecione **Gerar licença**.</span><span class="sxs-lookup"><span data-stu-id="cf397-197">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="cf397-198">Em **Estruturas Necessárias**, marque **Baixar**.</span><span class="sxs-lookup"><span data-stu-id="cf397-198">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="cf397-199">Use o DISM para aplicar o pacote com a dependência e a licença.</span><span class="sxs-lookup"><span data-stu-id="cf397-199">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="cf397-200">Em um prompt de comando de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cf397-200">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="cf397-201">O número de versão neste exemplo de código pode não corresponder à versão disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="cf397-201">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="cf397-202">Você também pode escolher um local de download diferente do especificado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="cf397-202">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="cf397-203">Faça todas as alterações no comando conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cf397-203">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="cf397-204">Quando você planeja usar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil baixar a imagem flash.</span><span class="sxs-lookup"><span data-stu-id="cf397-204">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="cf397-205">[**Baixar a imagem atual para o HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="cf397-205">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="cf397-206">Outros recursos:</span><span class="sxs-lookup"><span data-stu-id="cf397-206">Other resources:</span></span>
- [<span data-ttu-id="cf397-207">Distribuir aplicativos offline</span><span class="sxs-lookup"><span data-stu-id="cf397-207">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="cf397-208">Pacote de aplicativos DISM (.appx ou .appxbundle) servindo opções de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="cf397-208">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
