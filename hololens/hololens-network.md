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
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883145"
---
# <span data-ttu-id="7be87-104">Conectar o HoloLens a uma rede</span><span class="sxs-lookup"><span data-stu-id="7be87-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="7be87-105">Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="7be87-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="7be87-106">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="7be87-106">This guide will help you:</span></span>

- <span data-ttu-id="7be87-107">Conectar-se a uma rede usando Wi-Fi ou (somente para HoloLens 2) USB-C por Ethernet</span><span class="sxs-lookup"><span data-stu-id="7be87-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="7be87-108">Desabilitar e habilitar o Wi-Fi novamente</span><span class="sxs-lookup"><span data-stu-id="7be87-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="7be87-109">Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="7be87-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="7be87-110">Conectando pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="7be87-110">Connecting for the first time</span></span>

<span data-ttu-id="7be87-111">Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7be87-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="7be87-112">Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo.</span><span class="sxs-lookup"><span data-stu-id="7be87-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="7be87-113">Certifique-se de que a rede não exija o uso de um certificado para que você se conecte.</span><span class="sxs-lookup"><span data-stu-id="7be87-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="7be87-114">Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7be87-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="7be87-115">Conectando-se ao Wi-Fi após a configuração</span><span class="sxs-lookup"><span data-stu-id="7be87-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="7be87-116">Faça o **gesto de Iniciar** e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="7be87-116">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="7be87-117">O aplicativo Configurações será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7be87-117">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7be87-118">Selecione **Rede e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="7be87-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="7be87-119">Verifique se o Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="7be87-119">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="7be87-120">Se você não vir sua rede, role a lista para baixo.</span><span class="sxs-lookup"><span data-stu-id="7be87-120">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="7be87-121">Selecione uma rede e, em seguida, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-121">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="7be87-122">Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-122">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="7be87-123">O HoloLens contém um rádio Wi-Fi 2x2, com capacitação 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="7be87-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="7be87-124">Conectar o HoloLens a uma rede Wi-Fi é semelhante a conectar um dispositivo móvel ou computador Windows 10 a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7be87-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configurações de Wi-Fi do HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="7be87-126">Você também pode confirmar se está conectado a uma rede Wi-Fi ao verificar o status do Wi-Fi no menu **Iniciar**:</span><span class="sxs-lookup"><span data-stu-id="7be87-126">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="7be87-127">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-127">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7be87-128">Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-128">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="7be87-129">O estado do Wi-Fi e do SSID da rede conectada serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="7be87-129">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="7be87-130">Solução de problemas de conexão com Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7be87-130">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="7be87-131">Se você tiver problemas para se conectar à rede Wi-Fi, confira [Não consigo me conectar ao Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="7be87-131">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="7be87-132">Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="7be87-132">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="7be87-133">VPN</span><span class="sxs-lookup"><span data-stu-id="7be87-133">VPN</span></span>
<span data-ttu-id="7be87-134">Uma VPN pode ajudar a estabelecer uma conexão mais segura além de acesso à rede da sua empresa e a Internet.</span><span class="sxs-lookup"><span data-stu-id="7be87-134">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="7be87-135">O HoloLens 2 oferece suporte para cliente VPN interno e plug-in VPN da Plataforma Universal do Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="7be87-135">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="7be87-136">Protocolos VPN Interno suportados:</span><span class="sxs-lookup"><span data-stu-id="7be87-136">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="7be87-137">IKEv2</span><span class="sxs-lookup"><span data-stu-id="7be87-137">IKEv2</span></span>
- <span data-ttu-id="7be87-138">L2TP</span><span class="sxs-lookup"><span data-stu-id="7be87-138">L2TP</span></span>
- <span data-ttu-id="7be87-139">PPTP</span><span class="sxs-lookup"><span data-stu-id="7be87-139">PPTP</span></span>

<span data-ttu-id="7be87-140">Ao usar o certificado para autenticação do cliente VPN interno, será necessário que o certificado do cliente seja adicionado ao armazenamento de certificados do usuário.</span><span class="sxs-lookup"><span data-stu-id="7be87-140">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="7be87-141">Para descobrir se um plug-in VPN de terceiros suporta o HoloLens 2, vá até à Loja e localize o aplicativo VPN, depois verifique se o HoloLens está listado como um dispositivo suportado e, na página Requisitos do Sistema, veja se o aplicativo suporta a arquitetura ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="7be87-141">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="7be87-142">O HoloLens suporta apenas aplicativos VPN de terceiros que estão na Plataforma Universal do Windows.</span><span class="sxs-lookup"><span data-stu-id="7be87-142">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="7be87-143">A VPN não está ativada por padrão, mas pode ser ativada manualmente, abrindo **Configurações** do aplicativo e navegando para  **Rede & Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="7be87-143">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="7be87-144">A VPN pode ser gerenciada pelo MDM via[Configurações/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), e definido através da  [política Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="7be87-144">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="7be87-145">Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [esses guias](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="7be87-145">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="7be87-146">Desabilitando o Wi-Fi no HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="7be87-146">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="7be87-147">Usando o aplicativo Configurações no HoloLens</span><span class="sxs-lookup"><span data-stu-id="7be87-147">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="7be87-148">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-148">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7be87-149">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-149">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7be87-150">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7be87-150">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7be87-151">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7be87-151">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7be87-152">Selecione o controle deslizante do Wi-Fi para movê-lo para a posição **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="7be87-152">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="7be87-153">Isso desativará os componentes de RF do rádio Wi-Fi e desabilitará toda a funcionalidade de Wi-Fi no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7be87-153">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7be87-154">Quando o rádio Wi-Fi estiver desativado, o HoloLens não poderá carregar automaticamente seus [espaços](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="7be87-154">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="7be87-155">Mova o controle deslizante para a posição **Ativado** para ativar o rádio Wi-Fi e restaurar a funcionalidade de Wi-Fi no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7be87-155">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="7be87-156">O estado do rádio Wi-Fi selecionado (**Ativado** ou **Desativado**) persistirá nas reinicializações.</span><span class="sxs-lookup"><span data-stu-id="7be87-156">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="7be87-157">Identificando o endereço IP do seu HoloLens na rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7be87-157">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="7be87-158">Ao usar o aplicativo Configurações</span><span class="sxs-lookup"><span data-stu-id="7be87-158">By using the Settings app</span></span>

1. <span data-ttu-id="7be87-159">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-159">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7be87-160">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7be87-160">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7be87-161">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7be87-161">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7be87-162">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7be87-162">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7be87-163">Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="7be87-163">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriedades de hardware nas configurações de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="7be87-165">O endereço IP é exibido ao lado do **Endereço IPv4**.</span><span class="sxs-lookup"><span data-stu-id="7be87-165">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="7be87-166">Usando comandos de voz</span><span class="sxs-lookup"><span data-stu-id="7be87-166">By using voice commands</span></span>

<span data-ttu-id="7be87-167">Dependendo da versão do seu dispositivo, você pode usar comandos de voz internos ou a Cortana para exibir seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="7be87-167">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="7be87-168">Em versões posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) fale "Qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="7be87-168">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="7be87-169">e será exibido.</span><span class="sxs-lookup"><span data-stu-id="7be87-169">and it will be displayed.</span></span> <span data-ttu-id="7be87-170">Para versões anteriores ou o HoloLens (1ª geração), diga: "Ei Cortana, qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="7be87-170">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="7be87-171">e a Cortana exibirá e lerá seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="7be87-171">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="7be87-172">Ao usar o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="7be87-172">By using Windows Device Portal</span></span>

1. <span data-ttu-id="7be87-173">Em um navegador da Web em seu computador, abra o [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="7be87-173">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="7be87-174">Navegue até a seção **Rede**.</span><span class="sxs-lookup"><span data-stu-id="7be87-174">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="7be87-175">Essa seção exibe o endereço IP e outras informações de rede.</span><span class="sxs-lookup"><span data-stu-id="7be87-175">This section displays your IP address and other network information.</span></span> <span data-ttu-id="7be87-176">Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="7be87-176">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
