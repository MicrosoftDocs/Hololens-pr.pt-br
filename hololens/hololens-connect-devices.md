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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385487"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="77818-103">Conectar-se a dispositivos Bluetooth e USB-C</span><span class="sxs-lookup"><span data-stu-id="77818-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="77818-104">Microfones externos não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="77818-104">External microphones cannot be used.</span></span> <span data-ttu-id="77818-105">O HoloLens 2 usa a[Matriz do microfone](hololens2-hardware.md#audio-and-speech) interno.</span><span class="sxs-lookup"><span data-stu-id="77818-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="77818-106">Emparelhar dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="77818-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="77818-107">O HoloLens 2 tem suporte para as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="77818-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="77818-108">Mouse</span><span class="sxs-lookup"><span data-stu-id="77818-108">Mouse</span></span>
- <span data-ttu-id="77818-109">Teclado</span><span class="sxs-lookup"><span data-stu-id="77818-109">Keyboard</span></span>
- <span data-ttu-id="77818-110">Dispositivos de saída de áudio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="77818-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="77818-111">O HoloLens 2 (1° gen) tem suporte para as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="77818-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="77818-112">Mouse</span><span class="sxs-lookup"><span data-stu-id="77818-112">Mouse</span></span>
- <span data-ttu-id="77818-113">Teclado</span><span class="sxs-lookup"><span data-stu-id="77818-113">Keyboard</span></span>
- [<span data-ttu-id="77818-114">Usar o clicador do HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="77818-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="77818-115">Outros tipos de dispositivos Bluetooth, como alto-falantes, fones de ouvido, smartphones e game pads, podem estar listados como disponíveis nas configurações do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="77818-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="77818-116">No entanto, esses dispositivos não têm suporte no HoloLens (1ª gen).</span><span class="sxs-lookup"><span data-stu-id="77818-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="77818-117">Para saber mais, confira [Configurações do HoloLens lista dispositivos como disponíveis, mas os dispositivos não funcionam](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="77818-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="77818-118">Emparelhar um teclado ou mouse Bluetooth</span><span class="sxs-lookup"><span data-stu-id="77818-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="77818-119">Ligue o teclado ou o mouse e torne-o localizável.</span><span class="sxs-lookup"><span data-stu-id="77818-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="77818-120">Para saber como tornar o dispositivo localizável, procure por informações sobre o dispositivo (ou sua documentação) ou visite o site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="77818-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="77818-121">Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="77818-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="77818-122">Selecione **Dispositivos**, e verifique se o Bluetooth está ativado.</span><span class="sxs-lookup"><span data-stu-id="77818-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="77818-123">Quando vir o nome do dispositivo, selecione **Emparelhar** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="77818-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="77818-124">Bluetooth desabilitado</span><span class="sxs-lookup"><span data-stu-id="77818-124">Disable Bluetooth</span></span>

<span data-ttu-id="77818-125">Esse procedimento desativa os componentes RF do rádio Bluetooth e desabilita toda a funcionalidade Bluetooth no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="77818-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="77818-126">Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida slecione **Configurações** > **de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="77818-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="77818-127">Mova o controle deslizante para **Bluetooth** para a posição **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="77818-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="77818-128">HoloLens 2: conectar dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="77818-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="77818-129">O HoloLens 2 tem suporte para as seguintes classes de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="77818-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="77818-130">Dispositivos de armazenamento em massa (como unidades Thumb)</span><span class="sxs-lookup"><span data-stu-id="77818-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="77818-131">Adaptadores de Ethernet (incluindo carregamento plus de Ethernet)</span><span class="sxs-lookup"><span data-stu-id="77818-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="77818-132">Adaptadores de áudio digital USB-C a 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="77818-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="77818-133">Fones de ouvido digital USB-C (incluindo os adaptadores de carregamento plus do headset)</span><span class="sxs-lookup"><span data-stu-id="77818-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="77818-134">Mouse com fio</span><span class="sxs-lookup"><span data-stu-id="77818-134">Wired mouse</span></span>
- <span data-ttu-id="77818-135">Teclado com fio</span><span class="sxs-lookup"><span data-stu-id="77818-135">Wired keyboard</span></span>
- <span data-ttu-id="77818-136">Hubs PD combinados ( carregamento USB A + PD)</span><span class="sxs-lookup"><span data-stu-id="77818-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="77818-137">Em resposta aos comentários do cliente, habilitamos o suporte limitado para conectividade celular diretamente ao HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="77818-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="77818-138">Confira [Conectar-se ao Celular e 5G](hololens-cellular.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="77818-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="77818-139">Hubs USB-C</span><span class="sxs-lookup"><span data-stu-id="77818-139">USB-C Hubs</span></span>

<span data-ttu-id="77818-140">Alguns usuários podem precisar conectar vários dispositivos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="77818-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="77818-141">Para usuários que desejam uma prévia do recurso Insider e [usar um microfone USB-C](hololens-insider.md#usb-c-external-microphone-support) junto com outro dispositivo conectado, os hubs USB-C podem atender às necessidades do cliente.</span><span class="sxs-lookup"><span data-stu-id="77818-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="77818-142">A Microsoft não testou esses dispositivos, nem podemos recomendar nenhuma marca específica.</span><span class="sxs-lookup"><span data-stu-id="77818-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="77818-143">Requisitos para hub USB-C e dispositivos conectados:</span><span class="sxs-lookup"><span data-stu-id="77818-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="77818-144">Os dispositivos conectados não devem exigir a instalação de um driver.</span><span class="sxs-lookup"><span data-stu-id="77818-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="77818-145">O consumo total de energia de todos os dispositivos conectados deve ser inferior a 4,5 Watts.</span><span class="sxs-lookup"><span data-stu-id="77818-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="77818-146">Conectar a Miracast</span><span class="sxs-lookup"><span data-stu-id="77818-146">Connect to Miracast</span></span>

<span data-ttu-id="77818-147">Para usar o Miracast, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="77818-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="77818-148">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="77818-148">Do one of the following:</span></span>  

   - <span data-ttu-id="77818-149">Abra o menu **Iniciar** e selecione o ícone exibição.</span><span class="sxs-lookup"><span data-stu-id="77818-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="77818-150">Diga "conectar" enquanto mira ao menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="77818-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="77818-151">Na lista de dispositivos exibida, selecione um dispositivo disponível.</span><span class="sxs-lookup"><span data-stu-id="77818-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="77818-152">Concluir o emparelhamento para começar a projetar.</span><span class="sxs-lookup"><span data-stu-id="77818-152">Complete the pairing to begin projecting.</span></span>
