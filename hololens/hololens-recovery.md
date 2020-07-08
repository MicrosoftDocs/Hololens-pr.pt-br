---
title: Reiniciar, redefinir ou recuperar o HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857759"
---
# <span data-ttu-id="053e2-104">Reiniciar, redefinir ou recuperar o HoloLens</span><span class="sxs-lookup"><span data-stu-id="053e2-104">Restart, reset, or recover HoloLens</span></span>

## <span data-ttu-id="053e2-105">Carregando o dispositivo</span><span class="sxs-lookup"><span data-stu-id="053e2-105">Charging the device</span></span>

<span data-ttu-id="053e2-106">Antes de iniciar qualquer procedimento de solução de problemas, se possível, certifique-se de que seu dispositivo tenha sido cargado pelo menos entre 20% e 40%.</span><span class="sxs-lookup"><span data-stu-id="053e2-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="053e2-107">Verifique se você está usando o carregador e os cabos USB tipo C que vêm com o dispositivo HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="053e2-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="053e2-108">Caso não estejam disponíveis, certifique-se de que o carregador disponível possa oferecer suporte a pelo menos 15W de energia.</span><span class="sxs-lookup"><span data-stu-id="053e2-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="053e2-109">Se possível, não use um PC para carregar o dispositivo por USB, pois isso fornecerá uma carga muito lenta.</span><span class="sxs-lookup"><span data-stu-id="053e2-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="053e2-110">Se o dispositivo estiver inicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria.</span><span class="sxs-lookup"><span data-stu-id="053e2-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="053e2-111">No menu principal da interface de usuário do dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="053e2-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="053e2-112">Usando o LED próximo ao botão ligar (por 40%, você deve ver pelo menos dois LEDS sólidos).</span><span class="sxs-lookup"><span data-stu-id="053e2-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="053e2-113">No PC host, abra a janela do explorador de arquivos e procure seu dispositivo do HoloLens 2 no lado esquerdo, em "este computador".</span><span class="sxs-lookup"><span data-stu-id="053e2-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="053e2-114">a.</span><span class="sxs-lookup"><span data-stu-id="053e2-114">a.</span></span> <span data-ttu-id="053e2-115">Clique com o botão direito do mouse no nome do dispositivo e selecione Propriedades.</span><span class="sxs-lookup"><span data-stu-id="053e2-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="053e2-116">Aparecerá uma caixa de diálogo mostrando o nível da bateria para o seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="053e2-116">A dialog will appear showing the battery level for your device.</span></span>

![ResetRecovery do HoloLens 2](images/ResetRecovery2.png)

<span data-ttu-id="053e2-118">Se o dispositivo não puder ser inicializado no menu Iniciar, anote os LEDs e a enumeração no PC host e siga o guia de solução de problemas (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="053e2-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="053e2-119">Caso o estado do dispositivo não se enquadrar em nenhum dos estados listados no guia de solução de problemas, execute o **procedimento de reinicialização forçada** sem reconectar o dispositivo ao PC host, mas conectá-lo à fonte de alimentação.</span><span class="sxs-lookup"><span data-stu-id="053e2-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="053e2-120">Aguarde pelo menos uma hora para o dispositivo ser carregado.</span><span class="sxs-lookup"><span data-stu-id="053e2-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="053e2-121">Redefina o dispositivo</span><span class="sxs-lookup"><span data-stu-id="053e2-121">Reset the device</span></span>

<span data-ttu-id="053e2-122">Em determinadas circunstâncias, o cliente pode ser solicitado a redefinir manualmente o dispositivo sem usar a IU do SW.</span><span class="sxs-lookup"><span data-stu-id="053e2-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="053e2-123">Procedimento padrão</span><span class="sxs-lookup"><span data-stu-id="053e2-123">Standard procedure</span></span>
1. <span data-ttu-id="053e2-124">Desconecte o dispositivo da fonte de alimentação ou PC host desconectando o cabo tipo-C.</span><span class="sxs-lookup"><span data-stu-id="053e2-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="053e2-125">Pressione e mantenha pressionado o **botão de energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="053e2-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="053e2-126">Todos os LEDs devem estar desativados.</span><span class="sxs-lookup"><span data-stu-id="053e2-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="053e2-127">Aguarde 2-3 segundos e pressione o **botão de energia**, os LEDs próximos ao botão de energia terão iluminação e o dispositivo começará a ser inicializado.</span><span class="sxs-lookup"><span data-stu-id="053e2-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="053e2-128">Conecte o dispositivo ao PC host, abra o Gerenciador de dispositivos (para Windows 10 pressione a **tecla "Windows"** e, em seguida, a **tecla “x”** e clique em "Gerenciador de dispositivos") e verifique se o dispositivo enumera corretamente como Microsoft HoloLens, conforme mostrado nas imagens a seguir:</span><span class="sxs-lookup"><span data-stu-id="053e2-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="053e2-130">Procedimento de redefinição de disco</span><span class="sxs-lookup"><span data-stu-id="053e2-130">Hard-reset procedure</span></span>

<span data-ttu-id="053e2-131">Se o procedimento de redefinição padrão não funcionar, você pode usar o procedimento de redefinição de disco.</span><span class="sxs-lookup"><span data-stu-id="053e2-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="053e2-132">Desconecte o dispositivo da fonte de alimentação ou PC host desconectando o cabo tipo-C.</span><span class="sxs-lookup"><span data-stu-id="053e2-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="053e2-133">Mantenha o **diminuir o volume + botão de energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="053e2-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="053e2-134">O dispositivo será reinicializado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="053e2-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="053e2-135">Conecte o dispositivo ao PC host, abra o Gerenciador de dispositivos (para Windows 10 pressione a **tecla "Windows"** e, em seguida, a **tecla “x”** e clique em "Gerenciador de dispositivos") e verifique se o dispositivo enumera corretamente como Microsoft HoloLens, conforme mostrado nas imagens a seguir.</span><span class="sxs-lookup"><span data-stu-id="053e2-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="053e2-137">Reflash limpo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="053e2-137">Clean reflash the device</span></span>

<span data-ttu-id="053e2-138">Em situações extraordinárias, talvez seja necessário limpar o flash no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="053e2-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="053e2-139">Há duas maneiras de refazer a pisca de um dispositivo HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="053e2-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="053e2-140">Para todos os procedimentos de intermitência, você será solicitado a [instalar o aplicativo Advanced Recovery Companion do Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="053e2-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="053e2-141">Se você reiniciar seu dispositivo, todos os seus dados, aplicativos e configurações pessoais serão apagados, incluindo a redefinição do TPM.</span><span class="sxs-lookup"><span data-stu-id="053e2-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="053e2-142">O complemento avançado de recuperação está configurado para descarregar a versão de lançamento do recurso para [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), se você quiser baixar a versão mais recente do HoloLens 2 para piscar seu dispositivo por meio do Advanced Recovery Companion, poderá baixá-lo da [aqui](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="053e2-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="053e2-143">Esse recurso é mantido atualizado e será redirecionado para o Build mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="053e2-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="053e2-144">Antes de iniciar o procedimento de flashação, certifique-se de que o aplicativo está instalado e em execução no PC com Windows 10 e está pronto para detectar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="053e2-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Reflash limpo 2 do HoloLens](images/ARC1.png)

### <span data-ttu-id="053e2-146">Procedimento normal</span><span class="sxs-lookup"><span data-stu-id="053e2-146">Normal procedure</span></span>

1. <span data-ttu-id="053e2-147">Enquanto o dispositivo do HoloLens estiver em execução, conecte-o ao seu PC com Windows 10, em que você já havia lançado o aplicativo Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="053e2-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="053e2-148">O dispositivo será detectado automaticamente e a IU do aplicativo Advanced Recovery Companion será atualizada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="053e2-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![Reflash limpo 2 do HoloLens](images/ARC2.png)

3. <span data-ttu-id="053e2-150">Selecione o dispositivo HoloLens2 na IU do aplicativo Advanced Recovery Companion e siga as instruções para concluir a intermitência.</span><span class="sxs-lookup"><span data-stu-id="053e2-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="053e2-151">Procedimento manual</span><span class="sxs-lookup"><span data-stu-id="053e2-151">Manual procedure</span></span>

<span data-ttu-id="053e2-152">Se o dispositivo não inicializar corretamente, talvez seja necessário colocar o dispositivo do HoloLens 2 no modo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="053e2-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="053e2-153">Desconecte o dispositivo da fonte de alimentação ou PC host desconectando o cabo tipo-C.</span><span class="sxs-lookup"><span data-stu-id="053e2-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="053e2-154">Pressione e mantenha pressionado o **botão de energia** por 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="053e2-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="053e2-155">Todos os LEDs devem se desligar.</span><span class="sxs-lookup"><span data-stu-id="053e2-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="053e2-156">Enquanto pressiona o botão **aumentar volume**, pressione e solte o **botão de energia** para iniciar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="053e2-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="053e2-157">Aguarde 15 segundos antes de liberar o botão aumentar volume.</span><span class="sxs-lookup"><span data-stu-id="053e2-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="053e2-158">De 5 LEDs no dispositivo, apenas o LED intermediário iluminará.</span><span class="sxs-lookup"><span data-stu-id="053e2-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="053e2-159">Conecte o dispositivo ao PC host, abra o Gerenciador de dispositivos (para Windows 10 pressione a **tecla "Windows"** e, em seguida, a **tecla “x”** e clique em "Gerenciador de dispositivos") e verifique se o dispositivo enumera corretamente como Microsoft HoloLens, conforme mostrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="053e2-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="053e2-161">O dispositivo será detectado automaticamente, e a IU do aplicativo Advanced Recovery Companion será atualizada da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="053e2-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![Reflash limpo 2 do HoloLens](images/ARC2.png)

6. <span data-ttu-id="053e2-163">Selecione o dispositivo Microsoft HoloLens 2 na IU do aplicativo Advanced Recovery Companion e siga as instruções para concluir a intermitência.</span><span class="sxs-lookup"><span data-stu-id="053e2-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="053e2-164">Baixando o ARC sem usar a Loja de aplicativos</span><span class="sxs-lookup"><span data-stu-id="053e2-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="053e2-165">Se um ambiente de TI impede o uso do aplicativo da Windows Store ou limita o acesso à loja de varejo, os administradores de TI podem disponibilizá-lo por meio de outros caminhos de implantação "offline".</span><span class="sxs-lookup"><span data-stu-id="053e2-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="053e2-166">Esse processo também pode ser usado para outros aplicativos, como visto na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="053e2-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="053e2-167">Este guia se concentrará no Advanced Recovery Companion, mas ele será modificado para outros aplicativos offline.</span><span class="sxs-lookup"><span data-stu-id="053e2-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="053e2-168">Esse caminho de implantação pode ser habilitado com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="053e2-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="053e2-169">Vá para o site do [Microsoft Store para Empresas](https://businessstore.microsoft.com) e entre com uma identidade do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="053e2-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="053e2-170">Vá para **Gerenciar – Configurações**e ative **Mostrar aplicativos offline** em **Experiência de compra** conforme descrito em https://businessstore.microsoft.com/manage/settings/shop</span><span class="sxs-lookup"><span data-stu-id="053e2-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="053e2-171">Vá para **Comprar para o meu grupo** e pesquise o aplicativo [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="053e2-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="053e2-172">Altere a caixa de **Tipo de licença** para offline e clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="053e2-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="053e2-173">Em Baixar o pacote para uso offline, clique no segundo botão azul **"Baixar"**.</span><span class="sxs-lookup"><span data-stu-id="053e2-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="053e2-174">Verifique se a extensão de arquivo é. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="053e2-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="053e2-175">Nessa etapa, se o PC tiver acesso à Internet, basta clicar duas vezes e instalar.</span><span class="sxs-lookup"><span data-stu-id="053e2-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="053e2-176">O administrador de TI também pode distribuir esse aplicativo por meio do SCCM (System Center Configuration Manager) ou do Intune.</span><span class="sxs-lookup"><span data-stu-id="053e2-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="053e2-177">Se o PC de destino não tiver conectividade com a Internet, serão necessárias algumas etapas adicionais:</span><span class="sxs-lookup"><span data-stu-id="053e2-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="053e2-178">Selecione a licença não codificada e clique em **"Gerar licença"** e em **"Estruturas necessárias"** clique em **"Baixar".**</span><span class="sxs-lookup"><span data-stu-id="053e2-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="053e2-179">Os PCs sem acesso à Internet precisarão usar o DISM para aplicar o pacote à dependência e à licença.</span><span class="sxs-lookup"><span data-stu-id="053e2-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="053e2-180">Em um aviso de comando do administrador, digite:</span><span class="sxs-lookup"><span data-stu-id="053e2-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="053e2-181">O número de versão neste exemplo de código pode não corresponder à versão disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="053e2-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="053e2-182">Você também pode escolher um local de download diferente do especificado no exemplo.</span><span class="sxs-lookup"><span data-stu-id="053e2-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="053e2-183">Certifique-se de fazer as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="053e2-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="053e2-184">Ao planejar usar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil baixar a imagem instalada para ser disponível, aqui está a [imagem atual para o Microsoft HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="053e2-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="053e2-185">Outros recursos:</span><span class="sxs-lookup"><span data-stu-id="053e2-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


