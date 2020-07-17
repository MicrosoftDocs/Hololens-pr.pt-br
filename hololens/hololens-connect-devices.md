---
title: Conectar-se a dispositivos Bluetooth e USB-C
description: Este guia acompanha a conexão com dispositivos e acessórios Bluetooth e USB-C.
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
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881241"
---
# <span data-ttu-id="deff0-103">Conectar-se a dispositivos Bluetooth e USB-C</span><span class="sxs-lookup"><span data-stu-id="deff0-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="deff0-104">Emparelhar dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="deff0-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="deff0-105">O HoloLens 2 tem suporte para as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="deff0-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="deff0-106">Mouse</span><span class="sxs-lookup"><span data-stu-id="deff0-106">Mouse</span></span>
- <span data-ttu-id="deff0-107">Teclado</span><span class="sxs-lookup"><span data-stu-id="deff0-107">Keyboard</span></span>
- <span data-ttu-id="deff0-108">Dispositivos de saída de áudio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="deff0-108">Bluetooth audio output (A2DP) devices</span></span>

> [!NOTE]
> <span data-ttu-id="deff0-109">Microfones externos não podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="deff0-109">External microphones cannot be used.</span></span> <span data-ttu-id="deff0-110">O HoloLens 2 usa a[Matriz do microfone](hololens2-hardware.md#audio-and-speech) interno.</span><span class="sxs-lookup"><span data-stu-id="deff0-110">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

<span data-ttu-id="deff0-111">O HoloLens 2 (1° gen) tem suporte para as seguintes classes de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="deff0-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="deff0-112">Mouse</span><span class="sxs-lookup"><span data-stu-id="deff0-112">Mouse</span></span>
- <span data-ttu-id="deff0-113">Teclado</span><span class="sxs-lookup"><span data-stu-id="deff0-113">Keyboard</span></span>
- <span data-ttu-id="deff0-114">Usar o clicador do HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="deff0-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="deff0-115">Outros tipos de dispositivos Bluetooth, como alto-falantes, fones de ouvido, smartphones e game pads, podem estar listados como disponíveis nas configurações do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="deff0-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="deff0-116">No entanto, esses dispositivos não têm suporte no HoloLens (1ª gen).</span><span class="sxs-lookup"><span data-stu-id="deff0-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="deff0-117">Para saber mais, confira [Configurações do HoloLens lista dispositivos como disponíveis, mas os dispositivos não funcionam](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="deff0-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="deff0-118">Emparelhar um teclado ou mouse Bluetooth</span><span class="sxs-lookup"><span data-stu-id="deff0-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="deff0-119">Ligue o teclado ou o mouse e torne-o localizável.</span><span class="sxs-lookup"><span data-stu-id="deff0-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="deff0-120">Para saber como tornar o dispositivo localizável, procure por informações sobre o dispositivo (ou sua documentação) ou visite o site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="deff0-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="deff0-121">Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="deff0-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="deff0-122">Selecione **Dispositivos**, e verifique se o Bluetooth está ativado.</span><span class="sxs-lookup"><span data-stu-id="deff0-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="deff0-123">Quando vir o nome do dispositivo, selecione **Emparelhar**e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="deff0-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="deff0-124">HoloLens (1º gen): Emparelhe o clicador</span><span class="sxs-lookup"><span data-stu-id="deff0-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="deff0-125">Use o gesto de abrir a mão para ir para **Iniciar** e, em seguida, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="deff0-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="deff0-126">Selecione **Dispositivos**, e verifique se o Bluetooth está ativado.</span><span class="sxs-lookup"><span data-stu-id="deff0-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="deff0-127">Use a ponta de uma caneta para pressionar e segurar o botão de emparelhamento do clicador até que o sinal luminoso de status do clicador piscar.</span><span class="sxs-lookup"><span data-stu-id="deff0-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="deff0-128">Mantenha pressionado o botão até que a luz comece a piscar.</span><span class="sxs-lookup"><span data-stu-id="deff0-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="deff0-129">O botão de emparelhamento fica na parte inferior do clicador, ao lado do loop Finger.</span><span class="sxs-lookup"><span data-stu-id="deff0-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![O botão de emparelhamento está ao lado do loop Finger](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="deff0-131">Na tela emparelhamento, marque **Emparelhamento** > **do Clicador**.</span><span class="sxs-lookup"><span data-stu-id="deff0-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="deff0-132">HoloLens 2: conectar dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="deff0-132">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="deff0-133">O HoloLens 2 tem suporte para as seguintes classes de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="deff0-133">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="deff0-134">Dispositivos de armazenamento em massa (como unidades Thumb)</span><span class="sxs-lookup"><span data-stu-id="deff0-134">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="deff0-135">Adaptadores de Ethernet (incluindo carregamento plus de Ethernet)</span><span class="sxs-lookup"><span data-stu-id="deff0-135">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="deff0-136">Adaptadores de áudio digital USB-C a 3,5 mm</span><span class="sxs-lookup"><span data-stu-id="deff0-136">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="deff0-137">Fones de ouvido digital USB-C (incluindo os adaptadores de carregamento plus do headset)</span><span class="sxs-lookup"><span data-stu-id="deff0-137">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="deff0-138">Mouse com fio</span><span class="sxs-lookup"><span data-stu-id="deff0-138">Wired mouse</span></span>
- <span data-ttu-id="deff0-139">Teclado com fio</span><span class="sxs-lookup"><span data-stu-id="deff0-139">Wired keyboard</span></span>
- <span data-ttu-id="deff0-140">Hubs PD de combinação (USB A, carregamento plus de PD)</span><span class="sxs-lookup"><span data-stu-id="deff0-140">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="deff0-141">Alguns dispositivos móveis com conexões USB-C se apresentam ao HoloLens como adaptadores de Ethernet, portanto, podem ser usados em uma configuração de compartilhamento de Internet, começando com o Windows Holographic, versão 2004.</span><span class="sxs-lookup"><span data-stu-id="deff0-141">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="deff0-142">Os modems USB LTE que exigem um driver separado e/ou aplicativo instalado para sua configuração não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="deff0-142">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

## <span data-ttu-id="deff0-143">Conectar a Miracast</span><span class="sxs-lookup"><span data-stu-id="deff0-143">Connect to Miracast</span></span>

<span data-ttu-id="deff0-144">Para usar o Miracast, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="deff0-144">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="deff0-145">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="deff0-145">Do one of the following:</span></span>  

   - <span data-ttu-id="deff0-146">Abra o menu **Iniciar** e selecione o ícone exibição.</span><span class="sxs-lookup"><span data-stu-id="deff0-146">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="deff0-147">Diga "conectar" enquanto mira ao menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="deff0-147">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="deff0-148">Na lista de dispositivos exibida, selecione um dispositivo disponível.</span><span class="sxs-lookup"><span data-stu-id="deff0-148">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="deff0-149">Concluir o emparelhamento para começar a projetar.</span><span class="sxs-lookup"><span data-stu-id="deff0-149">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="deff0-150">Bluetooth desabilitado</span><span class="sxs-lookup"><span data-stu-id="deff0-150">Disable Bluetooth</span></span>

<span data-ttu-id="deff0-151">Esse procedimento desativa os componentes RF do rádio Bluetooth e desabilita toda a funcionalidade Bluetooth no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="deff0-151">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="deff0-152">Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida slecione **Configurações** > **de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="deff0-152">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="deff0-153">Mova o controle deslizante para **Bluetooth** para a posição **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="deff0-153">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
