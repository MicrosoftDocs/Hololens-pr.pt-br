---
title: Conectar o HoloLens a uma rede
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
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009519"
---
# <span data-ttu-id="75b38-104">Conectar o HoloLens a uma rede</span><span class="sxs-lookup"><span data-stu-id="75b38-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="75b38-105">Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="75b38-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="75b38-106">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="75b38-106">This guide will help you:</span></span>

- <span data-ttu-id="75b38-107">Conectar-se a uma rede usando Wi-Fi ou (somente para HoloLens 2) USB-C por Ethernet</span><span class="sxs-lookup"><span data-stu-id="75b38-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="75b38-108">Desabilitar e habilitar o Wi-Fi novamente</span><span class="sxs-lookup"><span data-stu-id="75b38-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="75b38-109">Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="75b38-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="75b38-110">Conectando pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="75b38-110">Connecting for the first time</span></span>

<span data-ttu-id="75b38-111">Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="75b38-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="75b38-112">Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo.</span><span class="sxs-lookup"><span data-stu-id="75b38-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="75b38-113">Certifique-se de que a rede não exija o uso de um certificado para que você se conecte.</span><span class="sxs-lookup"><span data-stu-id="75b38-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="75b38-114">Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="75b38-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="75b38-115">Em dispositivos do HoloLens 2, um usuário também pode [usar um adaptador USB-C para Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectar-se diretamente ao Wi-Fi e ajudar a configurar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75b38-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="75b38-116">Uma vez que o dispositivo foi configurado, um usuário pode continuar a usar o adaptador ou desconectá-lo do adaptador e [se conectar à uma rede Wi-Fi após a configuração](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="75b38-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="75b38-117">Conectando-se ao Wi-Fi após a configuração</span><span class="sxs-lookup"><span data-stu-id="75b38-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="75b38-118">Faça o **gesto de Iniciar** e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="75b38-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="75b38-119">O aplicativo Configurações será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="75b38-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="75b38-120">Selecione **Rede e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="75b38-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="75b38-121">Verifique se o Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="75b38-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="75b38-122">Se você não vir sua rede, role a lista para baixo.</span><span class="sxs-lookup"><span data-stu-id="75b38-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="75b38-123">Selecione uma rede e, em seguida, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="75b38-124">Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="75b38-125">O HoloLens contém um rádio Wi-Fi 2x2, com capacitação 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="75b38-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="75b38-126">Conectar o HoloLens a uma rede Wi-Fi é semelhante a conectar um dispositivo móvel ou computador Windows 10 a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="75b38-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configurações de Wi-Fi do HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="75b38-128">Você também pode confirmar se está conectado a uma rede Wi-Fi ao verificar o status do Wi-Fi no menu **Iniciar**:</span><span class="sxs-lookup"><span data-stu-id="75b38-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="75b38-129">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="75b38-130">Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="75b38-131">O estado do Wi-Fi e do SSID da rede conectada serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="75b38-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="75b38-132">Solução de problemas de conexão com Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="75b38-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="75b38-133">Se você tiver problemas para se conectar à rede Wi-Fi, confira [Não consigo me conectar ao Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="75b38-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="75b38-134">Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="75b38-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="75b38-135">VPN</span><span class="sxs-lookup"><span data-stu-id="75b38-135">VPN</span></span>
<span data-ttu-id="75b38-136">Uma VPN pode ajudar a estabelecer uma conexão mais segura além de acesso à rede da sua empresa e a Internet.</span><span class="sxs-lookup"><span data-stu-id="75b38-136">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="75b38-137">O HoloLens 2 oferece suporte para cliente VPN interno e plug-in VPN da Plataforma Universal do Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="75b38-137">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="75b38-138">Protocolos VPN Interno suportados:</span><span class="sxs-lookup"><span data-stu-id="75b38-138">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="75b38-139">IKEv2</span><span class="sxs-lookup"><span data-stu-id="75b38-139">IKEv2</span></span>
- <span data-ttu-id="75b38-140">L2TP</span><span class="sxs-lookup"><span data-stu-id="75b38-140">L2TP</span></span>
- <span data-ttu-id="75b38-141">PPTP</span><span class="sxs-lookup"><span data-stu-id="75b38-141">PPTP</span></span>

<span data-ttu-id="75b38-142">Ao usar o certificado para autenticação do cliente VPN interno, será necessário que o certificado do cliente seja adicionado ao armazenamento de certificados do usuário.</span><span class="sxs-lookup"><span data-stu-id="75b38-142">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="75b38-143">Para descobrir se um plug-in VPN de terceiros suporta o HoloLens 2, vá até à Loja e localize o aplicativo VPN, depois verifique se o HoloLens está listado como um dispositivo suportado e, na página Requisitos do Sistema, veja se o aplicativo suporta a arquitetura ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="75b38-143">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="75b38-144">O HoloLens suporta apenas aplicativos VPN de terceiros que estão na Plataforma Universal do Windows.</span><span class="sxs-lookup"><span data-stu-id="75b38-144">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="75b38-145">A VPN não está ativada por padrão, mas pode ser ativada manualmente, abrindo **Configurações** do aplicativo e navegando para  **Rede & Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="75b38-145">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="75b38-146">A VPN pode ser gerenciada pelo MDM via[Configurações/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), e definido através da  [política Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="75b38-146">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="75b38-147">Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [esses guias](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="75b38-147">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="75b38-148">Desabilitando o Wi-Fi no HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="75b38-148">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="75b38-149">Usando o aplicativo Configurações no HoloLens</span><span class="sxs-lookup"><span data-stu-id="75b38-149">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="75b38-150">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-150">Open the **Start** menu.</span></span>
1. <span data-ttu-id="75b38-151">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-151">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="75b38-152">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="75b38-152">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="75b38-153">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="75b38-153">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="75b38-154">Selecione o controle deslizante do Wi-Fi para movê-lo para a posição **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="75b38-154">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="75b38-155">Isso desativará os componentes de RF do rádio Wi-Fi e desabilitará toda a funcionalidade de Wi-Fi no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="75b38-155">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="75b38-156">Quando o rádio Wi-Fi estiver desativado, o HoloLens não poderá carregar automaticamente seus [espaços](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="75b38-156">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="75b38-157">Mova o controle deslizante para a posição **Ativado** para ativar o rádio Wi-Fi e restaurar a funcionalidade de Wi-Fi no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="75b38-157">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="75b38-158">O estado do rádio Wi-Fi selecionado (**Ativado** ou **Desativado**) persistirá nas reinicializações.</span><span class="sxs-lookup"><span data-stu-id="75b38-158">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="75b38-159">Identificando o endereço IP do seu HoloLens na rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="75b38-159">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="75b38-160">Ao usar o aplicativo Configurações</span><span class="sxs-lookup"><span data-stu-id="75b38-160">By using the Settings app</span></span>

1. <span data-ttu-id="75b38-161">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-161">Open the **Start** menu.</span></span>
1. <span data-ttu-id="75b38-162">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="75b38-162">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="75b38-163">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="75b38-163">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="75b38-164">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="75b38-164">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="75b38-165">Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="75b38-165">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriedades de hardware nas configurações de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="75b38-167">O endereço IP é exibido ao lado do **Endereço IPv4**.</span><span class="sxs-lookup"><span data-stu-id="75b38-167">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="75b38-168">Usando comandos de voz</span><span class="sxs-lookup"><span data-stu-id="75b38-168">By using voice commands</span></span>

<span data-ttu-id="75b38-169">Dependendo da versão do seu dispositivo, você pode usar comandos de voz internos ou a Cortana para exibir seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="75b38-169">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="75b38-170">Em versões posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) fale "Qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="75b38-170">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="75b38-171">e será exibido.</span><span class="sxs-lookup"><span data-stu-id="75b38-171">and it will be displayed.</span></span> <span data-ttu-id="75b38-172">Para versões anteriores ou o HoloLens (1ª geração), diga: "Ei Cortana, qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="75b38-172">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="75b38-173">e a Cortana exibirá e lerá seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="75b38-173">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="75b38-174">Ao usar o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="75b38-174">By using Windows Device Portal</span></span>

1. <span data-ttu-id="75b38-175">Em um navegador da Web em seu computador, abra o [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="75b38-175">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="75b38-176">Navegue até a seção **Rede**.</span><span class="sxs-lookup"><span data-stu-id="75b38-176">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="75b38-177">Essa seção exibe o endereço IP e outras informações de rede.</span><span class="sxs-lookup"><span data-stu-id="75b38-177">This section displays your IP address and other network information.</span></span> <span data-ttu-id="75b38-178">Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="75b38-178">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
