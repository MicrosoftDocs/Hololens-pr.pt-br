---
title: Conectar-se a dispositivos Bluetooth e USB-C
description: Comece a conectar aos dispositivos e acessórios Bluetooth e USB C a partir de seus dispositivos de realidade mista HoloLens.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639090"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="15120-103">Conectar-se a dispositivos Bluetooth e USB-C</span><span class="sxs-lookup"><span data-stu-id="15120-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="15120-104">Emparelhar dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="15120-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="15120-105">O HoloLens 2 é compatível com as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="15120-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="15120-106">[HID](/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="15120-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="15120-107">Mouse</span><span class="sxs-lookup"><span data-stu-id="15120-107">Mouse</span></span>
    - <span data-ttu-id="15120-108">Keyboard</span><span class="sxs-lookup"><span data-stu-id="15120-108">Keyboard</span></span>
- <span data-ttu-id="15120-109">Dispositivos de saída de áudio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="15120-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="15120-110">O HoloLens 2 é compatível com as seguintes APIs de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="15120-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="15120-111">[Servidor](/windows/uwp/devices-sensors/gatt-server) e [Cliente](/windows/uwp/devices-sensors/gatt-client) GATT</span><span class="sxs-lookup"><span data-stu-id="15120-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="15120-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="15120-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="15120-113">Talvez seja preciso instalar aplicativos complementares na Microsoft Store para realmente usar os dispositivos HID e GATT.</span><span class="sxs-lookup"><span data-stu-id="15120-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="15120-114">O HoloLens 2 (1ª geração) é compatível com as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="15120-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="15120-115">Mouse</span><span class="sxs-lookup"><span data-stu-id="15120-115">Mouse</span></span>
- <span data-ttu-id="15120-116">Keyboard</span><span class="sxs-lookup"><span data-stu-id="15120-116">Keyboard</span></span>
- [<span data-ttu-id="15120-117">Clicador do HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="15120-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="15120-118">Outros tipos de dispositivos Bluetooth, como alto-falantes, fones de ouvido, smartphones e game pads, podem estar listados como disponíveis nas configurações do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="15120-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="15120-119">No entanto, esses dispositivos não são compatíveis com o HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="15120-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="15120-120">Para obter mais informações, confira [Configurações do HoloLens listam os dispositivos disponíveis, mas os dispositivos não funcionam](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span><span class="sxs-lookup"><span data-stu-id="15120-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="15120-121">Emparelhar um Bluetooth ou mouse</span><span class="sxs-lookup"><span data-stu-id="15120-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="15120-122">Ligue o teclado ou o mouse e torne-o localizável.</span><span class="sxs-lookup"><span data-stu-id="15120-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="15120-123">Para saber como tornar o dispositivo localizável, procure por informações sobre o dispositivo (ou sua documentação) ou visite o site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="15120-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="15120-124">Use o gesto de abrir a mão [HoloLens (1ª geração)] ou o gesto de início (HoloLens 2) para ir até **Iniciar** e, em seguida, escolha **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="15120-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="15120-125">Escolha **Dispositivos** e verifique se o Bluetooth está ativado.</span><span class="sxs-lookup"><span data-stu-id="15120-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="15120-126">Quando vir o nome do dispositivo, escolha **Emparelhar** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="15120-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="15120-127">Desativar Bluetooth</span><span class="sxs-lookup"><span data-stu-id="15120-127">Disable Bluetooth</span></span>

<span data-ttu-id="15120-128">Esse procedimento desativa os componentes RF do rádio Bluetooth e desabilita toda a funcionalidade Bluetooth no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="15120-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="15120-129">Use o gesto de abrir a mão [HoloLens (1ª geração)] ou o gesto de início (HoloLens 2) para ir até **Iniciar** e, em seguida, escolha **Configurações** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="15120-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="15120-130">Mova a opção do controle deslizante **Bluetooth** para a posição **Desligado**.</span><span class="sxs-lookup"><span data-stu-id="15120-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="15120-131">HoloLens 2: conectar dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="15120-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="15120-132">O HoloLens 2 é compatível com as seguintes classes de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="15120-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="15120-133">Dispositivos de armazenamento em massa (como unidades Thumb)</span><span class="sxs-lookup"><span data-stu-id="15120-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="15120-134">Adaptadores de Ethernet (incluindo carregamento Ethernet Plus)</span><span class="sxs-lookup"><span data-stu-id="15120-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="15120-135">Adaptadores de áudio digital USB-C a 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="15120-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="15120-136">Fones de ouvido digital USB-C (incluindo os adaptadores de carregamento plus do headset)</span><span class="sxs-lookup"><span data-stu-id="15120-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="15120-137">Microfones externos USB-C ([Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e versões superiores)</span><span class="sxs-lookup"><span data-stu-id="15120-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="15120-138">Mouse com fio</span><span class="sxs-lookup"><span data-stu-id="15120-138">Wired mouse</span></span>
- <span data-ttu-id="15120-139">Teclado com fio</span><span class="sxs-lookup"><span data-stu-id="15120-139">Wired keyboard</span></span>
- <span data-ttu-id="15120-140">Hubs PD combinados ( carregamento USB A + PD)</span><span class="sxs-lookup"><span data-stu-id="15120-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="15120-141">Em resposta aos comentários do cliente, habilitamos o suporte limitado para conectividade celular diretamente ao HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="15120-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="15120-142">Confira [Conexão para Celular e 5G](hololens-cellular.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="15120-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="15120-143">Suporte para microfone externo USB-C</span><span class="sxs-lookup"><span data-stu-id="15120-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15120-144">Conectar **um microfone USB não o definirá automaticamente como o dispositivo de entrada**.</span><span class="sxs-lookup"><span data-stu-id="15120-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="15120-145">Ao conectar um conjunto de fones de ouvido USB-C, os usuários observarão que o áudio do fone de ouvido será redirecionado automaticamente para os fones de ouvido, mas o SO do HoloLens prioriza a matriz de microfone interno acima de qualquer outro dispositivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="15120-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="15120-146">**Para usar um microfone USB-C, siga as etapas abaixo.**</span><span class="sxs-lookup"><span data-stu-id="15120-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="15120-147">Microfones externos não podem ser usados em builds anteriores ao [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superiores.</span><span class="sxs-lookup"><span data-stu-id="15120-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="15120-148">Os usuários podem escolher microfones externos conectados por USB-C usando o painel de configurações de **Som**.</span><span class="sxs-lookup"><span data-stu-id="15120-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="15120-149">Os microfones USB-C podem ser usados para fazer chamadas, gravar etc.</span><span class="sxs-lookup"><span data-stu-id="15120-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="15120-150">Abra o aplicativo **Configurações** e escolha **Sistema** > **Som**.</span><span class="sxs-lookup"><span data-stu-id="15120-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Configurações de Som](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="15120-152">Para usar microfones externos com o **Remote Assist**, os usuários precisarão clicar no hiperlink "Gerenciar dispositivos de som".</span><span class="sxs-lookup"><span data-stu-id="15120-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="15120-153">Em seguida, use o menu suspenso para definir o microfone externo como **Padrão** ou **Padrão de Comunicações**.</span><span class="sxs-lookup"><span data-stu-id="15120-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="15120-154">Escolher **Padrão** significa que o microfone externo será usado em todos os lugares.</span><span class="sxs-lookup"><span data-stu-id="15120-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="15120-155">Escolher **Padrão de Comunicações** significa que o microfone externo será usado no Remote Assist e em outros aplicativos de comunicação, mas a matriz de microfones do HoloLens ainda pode ser usada para outras tarefas.</span><span class="sxs-lookup"><span data-stu-id="15120-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Gerenciar dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir o padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="15120-158">E quanto ao suporte para microfone Bluetooth?</span><span class="sxs-lookup"><span data-stu-id="15120-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="15120-159">Infelizmente, o Bluetooth ainda não oferece suporte para microfones no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="15120-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="15120-160">Hubs USB-C</span><span class="sxs-lookup"><span data-stu-id="15120-160">USB-C Hubs</span></span>

<span data-ttu-id="15120-161">Alguns usuários podem precisar conectar vários dispositivos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="15120-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="15120-162">Para usuários que desejam usar um [microfone USB-C](#usb-c-external-microphone-support) com outro dispositivo conectado, os hubs USB-C podem atender à necessidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="15120-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="15120-163">A Microsoft não testou esses dispositivos, nem podemos recomendar nenhuma marca específica.</span><span class="sxs-lookup"><span data-stu-id="15120-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="15120-164">**Requisitos para hub USB-C e dispositivos conectados:**</span><span class="sxs-lookup"><span data-stu-id="15120-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="15120-165">Os dispositivos conectados não devem exigir a instalação de um driver.</span><span class="sxs-lookup"><span data-stu-id="15120-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="15120-166">O consumo total de energia de todos os dispositivos conectados deve ser inferior a 4,5 Watts.</span><span class="sxs-lookup"><span data-stu-id="15120-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="15120-167">Conectar a Miracast</span><span class="sxs-lookup"><span data-stu-id="15120-167">Connect to Miracast</span></span>

<span data-ttu-id="15120-168">Para usar o Miracast, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="15120-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="15120-169">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="15120-169">Do one of the following:</span></span>  

   - <span data-ttu-id="15120-170">Abra o menu **Iniciar** e escolha o ícone **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="15120-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="15120-171">Diga "Conectar" enquanto foca o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="15120-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="15120-172">Na lista de dispositivos exibida, escolha um dispositivo disponível.</span><span class="sxs-lookup"><span data-stu-id="15120-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="15120-173">Concluir o emparelhamento para começar a projetar.</span><span class="sxs-lookup"><span data-stu-id="15120-173">Complete the pairing to begin projecting.</span></span>
