---
title: Conectar o HoloLens a uma rede
description: Saiba como configurar e se conectar à Internet com o HoloLens e como identificar o endereço IP do dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, sem fio, Internet, IP, endereço IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923594"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="7ffee-104">Conectar o HoloLens a uma rede</span><span class="sxs-lookup"><span data-stu-id="7ffee-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="7ffee-105">Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="7ffee-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="7ffee-106">O HoloLens contém uma rádio Wi-Fi 2x2 compatível com 802.11ac. Conectá-lo a uma rede é semelhante a conectar um dispositivo Windows 10 Desktop ou Mobile a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ffee-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="7ffee-107">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="7ffee-107">This guide will help you:</span></span>

- <span data-ttu-id="7ffee-108">Conectar-se a uma rede usando Wi-Fi ou, somente para o HoloLens 2, Wi-Fi Direct ou Ethernet por USB-C</span><span class="sxs-lookup"><span data-stu-id="7ffee-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="7ffee-109">Desabilitar e habilitar o Wi-Fi novamente</span><span class="sxs-lookup"><span data-stu-id="7ffee-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="7ffee-110">Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="7ffee-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="7ffee-111">Conectando pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="7ffee-111">Connecting for the first time</span></span>

<span data-ttu-id="7ffee-112">Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ffee-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="7ffee-113">Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo.</span><span class="sxs-lookup"><span data-stu-id="7ffee-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="7ffee-114">Além disso, verifique se a rede não exige o uso de um certificado para se conectar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="7ffee-115">Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ffee-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="7ffee-116">Em dispositivos HoloLens 2, um usuário também pode [usar um adaptador USB-C para Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para se conectar diretamente à Wi-Fi para ajudar a configurar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ffee-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="7ffee-117">Uma vez que o dispositivo foi configurado, o usuário pode continuar usando o adaptador ou desconectá-lo do adaptador e [conectar-se à Wi-Fi após a configuração](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="7ffee-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="7ffee-118">Conectar-se ao Wi-Fi após a configuração</span><span class="sxs-lookup"><span data-stu-id="7ffee-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="7ffee-119">Faça o **Gesto de iniciar** e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="7ffee-120">O aplicativo Configurações será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7ffee-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7ffee-121">Selecione **Rede e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="7ffee-122">Verifique se o Wi-Fi está ativado.</span><span class="sxs-lookup"><span data-stu-id="7ffee-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="7ffee-123">Se você não vir sua rede, role a lista para baixo.</span><span class="sxs-lookup"><span data-stu-id="7ffee-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="7ffee-124">Selecione uma rede e escolha **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="7ffee-125">Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Configurações de Wi-Fi do HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="7ffee-127">Para confirmar que você está conectado a uma rede Wi-Fi, verifique o status Wi-Fi no menu **Iniciar**:</span><span class="sxs-lookup"><span data-stu-id="7ffee-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="7ffee-128">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ffee-129">Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="7ffee-130">O estado do Wi-Fi e do SSID da rede conectada serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="7ffee-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="7ffee-131">Se o Wi-Fi não estiver disponível, você poderá [conectar-se a redes celular e 5G](hololens-cellular.md).</span><span class="sxs-lookup"><span data-stu-id="7ffee-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ffee-132">Por design, os usuários não podem ajustar o comportamento de roaming de Wi-Fi do HoloLens 2. **A única maneira de atualizar a lista de redes Wi-Fi é ligar e desligar a Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="7ffee-133">Isso evita vários problemas, como quando um dispositivo pode ficar "preso" a um PA ao estar fora de alcance.</span><span class="sxs-lookup"><span data-stu-id="7ffee-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="7ffee-134">Conectar o HoloLens à Rede Wi-Fi Corporativa</span><span class="sxs-lookup"><span data-stu-id="7ffee-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="7ffee-135">Os perfis de Wi-Fi Corporativo usam EAP (Protocolo de Autenticação Extensível) para autenticar conexões de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ffee-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="7ffee-136">O perfil de Wi-Fi Corporativo do HoloLens pode ser configurado por meio do pacote de provisionamento ou MDM criado pelo [Designer de Configuração do Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="7ffee-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="7ffee-137">Para o dispositivo gerenciado do Microsoft Intune, consulte o [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para obter instruções de configuração.</span><span class="sxs-lookup"><span data-stu-id="7ffee-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="7ffee-138">Para criar um pacote de provisionamento Wi-Fi em WCD, é necessário um arquivo .xml de perfil de Wi-Fi pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="7ffee-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="7ffee-139">Aqui está um exemplo de perfil Wi-Fi para WPA2-Enterprise com autenticação EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="7ffee-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="7ffee-140">O AC raiz do servidor e o certificado do cliente podem precisar ser provisionados no dispositivo, dependendo do tipo EAP.</span><span class="sxs-lookup"><span data-stu-id="7ffee-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="7ffee-141">Recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="7ffee-141">Additional resources:</span></span>

- <span data-ttu-id="7ffee-142">Esquema WLANv1Profile: [[MS-GPWL]: Esquema de Perfil de LAN Sem Fio v1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="7ffee-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="7ffee-143">Esquema EAP-TLS: [[MS-GPWL]: Esquema Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="7ffee-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="7ffee-144">Verifique nossa página de [Solução de problemas](hololens2-enterprise-troubleshooting.md#) se você tiver problemas para se conectar ao seu Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ffee-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="7ffee-145">Configurar o proxy de rede</span><span class="sxs-lookup"><span data-stu-id="7ffee-145">Configure Network Proxy</span></span>

<span data-ttu-id="7ffee-146">Esta seção aborda o proxy de rede para aplicativos do sistema operacional HoloLens e da UWP (Plataforma Universal do Windows) que usam a pilha HTTP do Windows.</span><span class="sxs-lookup"><span data-stu-id="7ffee-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="7ffee-147">Aplicativos que usam uma pilha HTTP que não é do Windows podem ter a própria configuração e manipulação de proxy.</span><span class="sxs-lookup"><span data-stu-id="7ffee-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="7ffee-148">Configurações de proxy</span><span class="sxs-lookup"><span data-stu-id="7ffee-148">Proxy Configurations</span></span> 

- <span data-ttu-id="7ffee-149">Script de PAC (configuração automática de proxy): um [arquivo PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (abre um site que não é da Microsoft) contém uma função JavaScript FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="7ffee-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="7ffee-150">Proxy estático: na forma de Servidor:Porta.</span><span class="sxs-lookup"><span data-stu-id="7ffee-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="7ffee-151">Protocolo WPAD (protocolo de descoberta automática de proxy da Web): forneça a URL do arquivo de configuração de proxy por DHCP ou DNS.</span><span class="sxs-lookup"><span data-stu-id="7ffee-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="7ffee-152">Métodos de provisionamento de proxy</span><span class="sxs-lookup"><span data-stu-id="7ffee-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="7ffee-153">Existem três maneiras de provisionar proxies:</span><span class="sxs-lookup"><span data-stu-id="7ffee-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="7ffee-154">**Interface do usuário de Configurações:**</span><span class="sxs-lookup"><span data-stu-id="7ffee-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="7ffee-155">Proxy por usuário (20H2 ou anterior):</span><span class="sxs-lookup"><span data-stu-id="7ffee-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="7ffee-156">Abra o menu Iniciar e selecione Configurações.</span><span class="sxs-lookup"><span data-stu-id="7ffee-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="7ffee-157">Selecione Rede e Internet e, depois, Proxy no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="7ffee-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="7ffee-158">Role para baixo até Configuração de proxy manual e alterne Usar um servidor proxy para Ativado.</span><span class="sxs-lookup"><span data-stu-id="7ffee-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="7ffee-159">Digite o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="7ffee-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="7ffee-160">Digite o número da porta.</span><span class="sxs-lookup"><span data-stu-id="7ffee-160">Enter the port number.</span></span>
        6. <span data-ttu-id="7ffee-161">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-161">Click Save.</span></span>
      1. <span data-ttu-id="7ffee-162">Proxy de Wi-Fi (21H1 ou superior):</span><span class="sxs-lookup"><span data-stu-id="7ffee-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="7ffee-163">Abra o menu Iniciar e vá para a página de Propriedades da rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="7ffee-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="7ffee-164">Role até Proxy</span><span class="sxs-lookup"><span data-stu-id="7ffee-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="7ffee-165">Altere para Configuração manual</span><span class="sxs-lookup"><span data-stu-id="7ffee-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="7ffee-166">Digite o endereço IP do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="7ffee-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="7ffee-167">Digite o número da porta.</span><span class="sxs-lookup"><span data-stu-id="7ffee-167">Enter the port number.</span></span>
          1. <span data-ttu-id="7ffee-168">Clique em Aplicar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="7ffee-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="7ffee-169">**MDM**</span></span> 
     1. <span data-ttu-id="7ffee-170">Intune: use estas [etapas](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para configurar o proxy no Intune.</span><span class="sxs-lookup"><span data-stu-id="7ffee-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="7ffee-171">Você precisará rolar até a parte inferior da seção.</span><span class="sxs-lookup"><span data-stu-id="7ffee-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="7ffee-172">Outras soluções de MDM de terceiros: use um [CSP de WiFi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="7ffee-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="7ffee-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="7ffee-173">**PPKG**</span></span> 
    1. <span data-ttu-id="7ffee-174">Abra o Designer de Configuração do Windows</span><span class="sxs-lookup"><span data-stu-id="7ffee-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="7ffee-175">Clique em Provisionamento avançado, insira o nome do novo Projeto e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="7ffee-176">Selecione Windows Holographic (HoloLens 2) e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="7ffee-177">Importe seu PPKG (opcional) e clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="7ffee-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="7ffee-178">Expanda Configurações de Runtime -> Perfis de Conectividade -> WLAN -> Proxy de WLAN.</span><span class="sxs-lookup"><span data-stu-id="7ffee-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="7ffee-179">Insira o SSID de sua rede Wi-Fi e clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="7ffee-180">Selecione a rede Wi-Fi na janela esquerda e insira as personalizações desejadas.</span><span class="sxs-lookup"><span data-stu-id="7ffee-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="7ffee-181">As personalizações habilitadas serão exibidas em negrito no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="7ffee-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="7ffee-182">Clique em Salvar e Encerrar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="7ffee-183">[Aplique](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) o pacote de provisionamento ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7ffee-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="7ffee-184">Os [CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) estão por trás de muitas das tarefas de gerenciamento e das políticas do Windows 10, no Microsoft Intune e nos provedores de serviço MDM que não são da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ffee-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="7ffee-185">Você também pode usar o [Designer de Configuração do Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) para criar um [pacote de provisionamento](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) e aplicá-lo ao HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7ffee-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="7ffee-186">Os CSPs com maior probabilidade de serem aplicados ao seu HoloLens 2 são:</span><span class="sxs-lookup"><span data-stu-id="7ffee-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="7ffee-187">[CSP de Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): proxy de Wi-Fi por perfil</span><span class="sxs-lookup"><span data-stu-id="7ffee-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="7ffee-188">Outros CSPs com suporte de dispositivos HoloLens</span><span class="sxs-lookup"><span data-stu-id="7ffee-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="7ffee-189">VPN</span><span class="sxs-lookup"><span data-stu-id="7ffee-189">VPN</span></span>
<span data-ttu-id="7ffee-190">Uma conexão VPN pode ajudar a estabelecer uma conexão mais segura além de acesso à rede da sua empresa e a Internet.</span><span class="sxs-lookup"><span data-stu-id="7ffee-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="7ffee-191">O HoloLens 2 dá suporte para cliente VPN interno e plug-in VPN da UWP (Plataforma Universal do Windows).</span><span class="sxs-lookup"><span data-stu-id="7ffee-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="7ffee-192">Protocolos de VPN Interno compatíveis:</span><span class="sxs-lookup"><span data-stu-id="7ffee-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="7ffee-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="7ffee-193">IKEv2</span></span>
- <span data-ttu-id="7ffee-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="7ffee-194">L2TP</span></span>
- <span data-ttu-id="7ffee-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="7ffee-195">PPTP</span></span>

<span data-ttu-id="7ffee-196">Ao usar o certificado para autenticação do cliente de VPN interno, será necessário que o certificado do cliente seja adicionado ao repositório de certificados do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ffee-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="7ffee-197">Para descobrir se um plug-in de VPN de terceiros dá suporte ao HoloLens 2, acesse a Store e localize o aplicativo VPN, depois verifique se o HoloLens está listado como um dispositivo compatível e, na página Requisitos do Sistema, veja se o aplicativo dá suporte à arquitetura ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="7ffee-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="7ffee-198">O HoloLens dá suporte apenas a aplicativos VPN de terceiros que estão na Plataforma Universal do Windows.</span><span class="sxs-lookup"><span data-stu-id="7ffee-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="7ffee-199">A VPN pode ser gerenciada pelo MDM via [Configurações/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) e definida por meio da [política Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="7ffee-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="7ffee-200">Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [estes guias](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="7ffee-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="7ffee-201">VPN via interface do usuário</span><span class="sxs-lookup"><span data-stu-id="7ffee-201">VPN via UI</span></span>

<span data-ttu-id="7ffee-202">A VPN não está habilitada por padrão, mas pode ser habilitada manualmente abrindo o aplicativo **Configurações** e navegando para **Rede e Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="7ffee-203">Selecione um provedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="7ffee-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="7ffee-204">Crie um nome de conexão.</span><span class="sxs-lookup"><span data-stu-id="7ffee-204">Create a connection name.</span></span> 
1. <span data-ttu-id="7ffee-205">Digite o nome ou o endereço do servidor.</span><span class="sxs-lookup"><span data-stu-id="7ffee-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="7ffee-206">Selecione o tipo de VPN.</span><span class="sxs-lookup"><span data-stu-id="7ffee-206">Select the VPN type.</span></span>
1. <span data-ttu-id="7ffee-207">Selecione o tipo de informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="7ffee-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="7ffee-208">Opcionalmente, adicione o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="7ffee-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="7ffee-209">Aplicar as configurações de VPN.</span><span class="sxs-lookup"><span data-stu-id="7ffee-209">Apply the VPN settings.</span></span> 

![Configurações de VPN do HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="7ffee-211">Conjunto de VPN via Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="7ffee-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="7ffee-212">Em nosso Windows Holographic versão 20H2, corrigimos um problema de configuração de proxy para conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="7ffee-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="7ffee-213">Considere a atualização de dispositivos para esse build se você pretende usar esse fluxo.</span><span class="sxs-lookup"><span data-stu-id="7ffee-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="7ffee-214">Inicie o Designer de Configuração do Windows.</span><span class="sxs-lookup"><span data-stu-id="7ffee-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="7ffee-215">Clique em **Provisionar dispositivos HoloLens**, selecione o dispositivo de destino e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="7ffee-216">Digite o nome e o caminho do pacote.</span><span class="sxs-lookup"><span data-stu-id="7ffee-216">Enter package name and path.</span></span>
1. <span data-ttu-id="7ffee-217">Clique em **Alternar para o editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="7ffee-218">Abra **Configurações de runtime** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="7ffee-219">Configurar o VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="7ffee-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="7ffee-220">Selecione o ProfileType: **Nativo** ou **Terceiros**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="7ffee-221">Para o perfil Nativo, selecione **NativeProtocolType**, em seguida, configurar servidor, política de roteamento, tipo de autenticação e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="7ffee-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="7ffee-222">Para o perfil de "Terceiros", configure a URL do servidor, o nome da família do pacote do aplicativo de plug-in de VPN (somente três predefinidos) e configurações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7ffee-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="7ffee-223">Exporte seu pacote.</span><span class="sxs-lookup"><span data-stu-id="7ffee-223">Export your package.</span></span>
1. <span data-ttu-id="7ffee-224">Conecte seu HoloLens e copie o arquivo .ppkg no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ffee-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="7ffee-225">No HoloLens, aplique o .ppkg da VPN abrindo o menu Iniciar e selecionando **Configurações** -> **Conta** -> **Acessar conta corporativa ou de estudante** -> **Adicionar ou remover pacote de provisionamento** -> Selecione seu pacote de VPN.</span><span class="sxs-lookup"><span data-stu-id="7ffee-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="7ffee-226">Configuração de VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="7ffee-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="7ffee-227">Basta seguir as documentações do Intune para começar.</span><span class="sxs-lookup"><span data-stu-id="7ffee-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="7ffee-228">Ao seguir estas etapas, lembre-se dos protocolos de VPN internos a que os dispositivos do HoloLens dão suporte.</span><span class="sxs-lookup"><span data-stu-id="7ffee-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="7ffee-229">[Criar perfis de VPN para se conectar a servidores VPN no Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="7ffee-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="7ffee-230">[Configurações de dispositivos Windows 10 e Windows Holographic para adicionar conexões VPN usando o Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="7ffee-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="7ffee-231">Quando terminar, lembre-se de [atribuir o perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="7ffee-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="7ffee-232">VPN por meio de soluções MDM de terceiros</span><span class="sxs-lookup"><span data-stu-id="7ffee-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="7ffee-233">Exemplo de conexão de VPN de terceiros:</span><span class="sxs-lookup"><span data-stu-id="7ffee-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="7ffee-234">Exemplo de VPN IKEv2 nativa:</span><span class="sxs-lookup"><span data-stu-id="7ffee-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="7ffee-235">Desabilitando o Wi-Fi no HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="7ffee-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="7ffee-236">Usando o aplicativo Configurações no HoloLens</span><span class="sxs-lookup"><span data-stu-id="7ffee-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="7ffee-237">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ffee-238">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os Aplicativos** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7ffee-239">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7ffee-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7ffee-240">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7ffee-241">Selecione o controle deslizante do Wi-Fi para movê-lo para a posição **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="7ffee-242">Isso desligará os componentes de RF do rádio Wi-Fi e desabilitará toda a funcionalidade de Wi-Fi no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7ffee-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7ffee-243">Quando o rádio Wi-Fi estiver desabilitado, o HoloLens não poderá carregar automaticamente seus [espaços](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="7ffee-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="7ffee-244">Mova o controle deslizante para a posição **Ativado** para ativar o rádio Wi-Fi e restaurar a funcionalidade de Wi-Fi no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7ffee-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="7ffee-245">O estado do rádio Wi-Fi selecionado (**Ativado** ou **Desativado**) persistirá nas reinicializações.</span><span class="sxs-lookup"><span data-stu-id="7ffee-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="7ffee-246">Identificando o endereço IP do seu HoloLens na rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7ffee-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="7ffee-247">Usando o aplicativo Configurações</span><span class="sxs-lookup"><span data-stu-id="7ffee-247">By using the Settings app</span></span>

1. <span data-ttu-id="7ffee-248">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ffee-249">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os Aplicativos** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7ffee-250">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7ffee-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7ffee-251">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7ffee-252">Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriedades de hardware nas configurações de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="7ffee-254">O endereço IP aparece ao lado do **endereço IPv4**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="7ffee-255">Usando comandos de voz</span><span class="sxs-lookup"><span data-stu-id="7ffee-255">By using voice commands</span></span>

<span data-ttu-id="7ffee-256">Dependendo do build dos seus dispositivos, você pode usar comandos de voz internos ou a Cortana para exibir seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="7ffee-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="7ffee-257">Em builds posteriores ao [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), fale "Qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="7ffee-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="7ffee-258">e ele será exibido.</span><span class="sxs-lookup"><span data-stu-id="7ffee-258">and it will be displayed.</span></span> <span data-ttu-id="7ffee-259">Para builds anteriores ou o HoloLens (1ª geração), diga: "Ei Cortana, qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="7ffee-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="7ffee-260">e a Cortana exibirá e lerá seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="7ffee-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="7ffee-261">Usando o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="7ffee-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="7ffee-262">Em um navegador da Web no PC, abra o [portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="7ffee-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="7ffee-263">Navegue até a seção **Rede**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="7ffee-264">Essa seção exibe o endereço IP e outras informações de rede.</span><span class="sxs-lookup"><span data-stu-id="7ffee-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="7ffee-265">Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="7ffee-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="7ffee-266">Alterar o endereço IP para um endereço estático</span><span class="sxs-lookup"><span data-stu-id="7ffee-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="7ffee-267">Usando Configurações</span><span class="sxs-lookup"><span data-stu-id="7ffee-267">By using Settings</span></span>
 
1. <span data-ttu-id="7ffee-268">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7ffee-269">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os Aplicativos** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7ffee-270">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="7ffee-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7ffee-271">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7ffee-272">Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="7ffee-273">Na janela **Editar configurações de IP**, altere o primeiro campo para **Manual**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="7ffee-274">Insira a configuração de IP desejada nos campos restantes e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="7ffee-275">Usando o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="7ffee-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="7ffee-276">Em um navegador da Web no PC, abra o [portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="7ffee-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="7ffee-277">Navegue até a seção **Rede**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="7ffee-278">Selecione o botão **Configuração do IPv4**.</span><span class="sxs-lookup"><span data-stu-id="7ffee-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="7ffee-279">Selecione **Usar o endereço IP a seguir** e insira a configuração TCP/IP desejada.</span><span class="sxs-lookup"><span data-stu-id="7ffee-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="7ffee-280">Selecione **Usar os endereços de servidor DNS a seguir** e insira os endereços de servidor DNS Preferencial e Alternativo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7ffee-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="7ffee-281">Clique em **Save** (Salvar).</span><span class="sxs-lookup"><span data-stu-id="7ffee-281">Click **Save**.</span></span> 
