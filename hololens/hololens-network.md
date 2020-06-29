---
title: Conectar a uma rede
description: Instruções sobre como se conectar à Internet com o HoloLens e como identificar o endereço IP do dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, sem fio, internet, IP, endereço IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827722"
---
# <span data-ttu-id="7ad1a-104">Conectar a uma rede</span><span class="sxs-lookup"><span data-stu-id="7ad1a-104">Connect to a network</span></span>

<span data-ttu-id="7ad1a-105">Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="7ad1a-106">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="7ad1a-106">This guide will help you:</span></span>

- <span data-ttu-id="7ad1a-107">Conectar-se a uma rede usando Wi-Fi ou (somente para HoloLens 2) USB-C por Ethernet</span><span class="sxs-lookup"><span data-stu-id="7ad1a-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="7ad1a-108">Desabilitar e habilitar o Wi-Fi novamente</span><span class="sxs-lookup"><span data-stu-id="7ad1a-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="7ad1a-109">Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="7ad1a-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="7ad1a-110">Conectando pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="7ad1a-110">Connecting for the first time</span></span>

<span data-ttu-id="7ad1a-111">Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="7ad1a-112">Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="7ad1a-113">Certifique-se de que a rede não exija o uso de um certificado para que você se conecte.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="7ad1a-114">Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="7ad1a-115">Conectando-se ao Wi-Fi após a configuração</span><span class="sxs-lookup"><span data-stu-id="7ad1a-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="7ad1a-116">Selecione **Iniciar** > **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="7ad1a-117">*Somente para HoloLens (1ª geração)*: use seu foco para mover o aplicativo Configurações, depois feche e abra os dedos indicador e polegar para posicioná-lo ou diga "Place" (Posicionar).</span><span class="sxs-lookup"><span data-stu-id="7ad1a-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="7ad1a-118">Selecione **Rede e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="7ad1a-119">Se você não vir sua rede, role a lista para baixo.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="7ad1a-120">Selecione uma rede e, em seguida, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="7ad1a-121">Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="7ad1a-122">Conectando-se ao Wi-Fi no HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="7ad1a-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="7ad1a-123">O HoloLens contém um rádio Wi-Fi 2x2, com capacitação 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="7ad1a-124">Conectar o HoloLens a uma rede Wi-Fi é semelhante a conectar um dispositivo móvel ou computador Windows 10 a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configurações de Wi-Fi do HoloLens](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="7ad1a-126">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ad1a-127">Selecione o aplicativo Configurações em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7ad1a-128">O aplicativo Configurações será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7ad1a-129">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7ad1a-130">Verifique se o Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="7ad1a-131">Selecione uma rede Wi-Fi na lista.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="7ad1a-132">Se necessário, digite a senha da rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="7ad1a-133">Você também pode confirmar se está conectado a uma rede Wi-Fi ao verificar o status do Wi-Fi no menu **Iniciar**:</span><span class="sxs-lookup"><span data-stu-id="7ad1a-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="7ad1a-134">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ad1a-135">Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="7ad1a-136">O estado do Wi-Fi e do SSID da rede conectada serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="7ad1a-137">Solução de problemas de conexão com Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7ad1a-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="7ad1a-138">Se você tiver problemas para se conectar à rede Wi-Fi, confira [Não consigo me conectar ao Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="7ad1a-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="7ad1a-139">Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="7ad1a-140">Desabilitando o Wi-Fi no HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="7ad1a-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="7ad1a-141">Usando o aplicativo Configurações no HoloLens</span><span class="sxs-lookup"><span data-stu-id="7ad1a-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="7ad1a-142">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ad1a-143">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7ad1a-144">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7ad1a-145">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7ad1a-146">Selecione o controle deslizante do Wi-Fi para movê-lo para a posição **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="7ad1a-147">Isso desativará os componentes de RF do rádio Wi-Fi e desabilitará toda a funcionalidade de Wi-Fi no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7ad1a-148">Quando o rádio Wi-Fi estiver desativado, o HoloLens não poderá carregar automaticamente seus [espaços](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="7ad1a-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="7ad1a-149">Mova o controle deslizante para a posição **Ativado** para ativar o rádio Wi-Fi e restaurar a funcionalidade de Wi-Fi no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="7ad1a-150">O estado do rádio Wi-Fi selecionado (**Ativado** ou **Desativado**) persistirá nas reinicializações.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="7ad1a-151">Identificando o endereço IP do seu HoloLens na rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7ad1a-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="7ad1a-152">Ao usar o aplicativo Configurações</span><span class="sxs-lookup"><span data-stu-id="7ad1a-152">By using the Settings app</span></span>

1. <span data-ttu-id="7ad1a-153">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ad1a-154">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7ad1a-155">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7ad1a-156">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7ad1a-157">Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriedades de hardware nas configurações de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="7ad1a-159">O endereço IP é exibido ao lado do **Endereço IPv4**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="7ad1a-160">Ao usar a Cortana</span><span class="sxs-lookup"><span data-stu-id="7ad1a-160">By using Cortana</span></span>

<span data-ttu-id="7ad1a-161">Diga "Hey Cortana, What's my IP address?" (Ei, Cortana, qual é o meu endereço IP?)</span><span class="sxs-lookup"><span data-stu-id="7ad1a-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="7ad1a-162">e a Cortana exibirá e lerá seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="7ad1a-163">Ao usar o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="7ad1a-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="7ad1a-164">Em um navegador da Web em seu computador, abra o [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="7ad1a-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="7ad1a-165">Navegue até a seção **Rede**.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="7ad1a-166">Essa seção exibe o endereço IP e outras informações de rede.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="7ad1a-167">Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="7ad1a-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
