---
title: Conectar o HoloLens a uma rede
description: Saiba como configurar e se conectar à Internet com o HoloLens e como identificar o endereço IP do dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, sem fio, internet, IP, endereço IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 6d11ae0907aa82df71d7c86bb37996dcce71d845
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283972"
---
# <span data-ttu-id="0473d-104">Conectar o HoloLens a uma rede</span><span class="sxs-lookup"><span data-stu-id="0473d-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="0473d-105">Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="0473d-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="0473d-106">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="0473d-106">This guide will help you:</span></span>

- <span data-ttu-id="0473d-107">Conectar-se a uma rede usando Wi-Fi ou (somente para HoloLens 2) USB-C por Ethernet</span><span class="sxs-lookup"><span data-stu-id="0473d-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="0473d-108">Desabilitar e habilitar o Wi-Fi novamente</span><span class="sxs-lookup"><span data-stu-id="0473d-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="0473d-109">Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="0473d-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="0473d-110">Conectando pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="0473d-110">Connecting for the first time</span></span>

<span data-ttu-id="0473d-111">Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="0473d-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="0473d-112">Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo.</span><span class="sxs-lookup"><span data-stu-id="0473d-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="0473d-113">Certifique-se de que a rede não exija o uso de um certificado para que você se conecte.</span><span class="sxs-lookup"><span data-stu-id="0473d-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="0473d-114">Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="0473d-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="0473d-115">Em dispositivos do HoloLens 2, um usuário também pode [usar um adaptador USB-C para Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectar-se diretamente ao Wi-Fi e ajudar a configurar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0473d-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="0473d-116">Uma vez que o dispositivo foi configurado, um usuário pode continuar a usar o adaptador ou desconectá-lo do adaptador e [se conectar à uma rede Wi-Fi após a configuração](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="0473d-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="0473d-117">Conectando-se ao Wi-Fi após a configuração</span><span class="sxs-lookup"><span data-stu-id="0473d-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="0473d-118">Faça o **gesto de Iniciar** e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="0473d-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="0473d-119">O aplicativo Configurações será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="0473d-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0473d-120">Selecione **Rede e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="0473d-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="0473d-121">Verifique se o Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="0473d-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="0473d-122">Se você não vir sua rede, role a lista para baixo.</span><span class="sxs-lookup"><span data-stu-id="0473d-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="0473d-123">Selecione uma rede e, em seguida, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="0473d-124">Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="0473d-125">O HoloLens contém um rádio Wi-Fi 2x2, com capacitação 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="0473d-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="0473d-126">Conectar o HoloLens a uma rede Wi-Fi é semelhante a conectar um dispositivo móvel ou computador Windows 10 a uma rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="0473d-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configurações de Wi-Fi do HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="0473d-128">Você também pode confirmar se está conectado a uma rede Wi-Fi ao verificar o status do Wi-Fi no menu **Iniciar**:</span><span class="sxs-lookup"><span data-stu-id="0473d-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="0473d-129">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0473d-130">Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="0473d-131">O estado do Wi-Fi e do SSID da rede conectada serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="0473d-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="0473d-132">Solução de problemas de conexão com Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0473d-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="0473d-133">Se você tiver problemas para se conectar à rede Wi-Fi, confira [Não consigo me conectar ao Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="0473d-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="0473d-134">Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="0473d-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="0473d-135">Conectar o HoloLens à Rede Wi-Fi Empresarial</span><span class="sxs-lookup"><span data-stu-id="0473d-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="0473d-136">Os perfis de Wi-Fi Empresarial usam EAP (Protocolo de Autenticação Extensível) para autenticar conexões de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="0473d-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="0473d-137">O perfil de Wi-Fi Empresarial do HoloLens pode ser configurado por meio do pacote de provisionamento ou MDM criado pelo [Designer de Configuração do Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="0473d-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="0473d-138">Para o dispositivo gerenciado do Microsoft Intune, consulte o [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para obter instruções de configuração.</span><span class="sxs-lookup"><span data-stu-id="0473d-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="0473d-139">Para criar um pacote de provisionamento Wi-Fi em WCD, é necessário um arquivo .xml Wi-Fi pré-configurado.</span><span class="sxs-lookup"><span data-stu-id="0473d-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="0473d-140">Aqui está um exemplo de perfil Wi-Fi para WPA2-Enterprise com autenticação EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="0473d-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="0473d-141">O certificado de CA raiz do servidor e o certificado do cliente podem precisar ser provisionados no dispositivo, dependendo do tipo EAP.</span><span class="sxs-lookup"><span data-stu-id="0473d-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="0473d-142">Recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="0473d-142">Additional resources:</span></span>

- <span data-ttu-id="0473d-143">Esquema WLANv1Profile: [[MS-GPWL]: esquema do Perfil v1 da LAN Wireless | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="0473d-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="0473d-144">Esquema EAP-TLS: [[MS-GPWL]: esquema Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="0473d-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="0473d-145">Solução de problemas de EAP</span><span class="sxs-lookup"><span data-stu-id="0473d-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="0473d-146">Verifique se o perfil do Wi-Fi tem as configurações corretas:</span><span class="sxs-lookup"><span data-stu-id="0473d-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="0473d-147">O tipo EAP está configurado corretamente, tipos EAP comuns: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="0473d-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="0473d-148">O nome Wi-Fi SSID está correto e corresponde à cadeia de caracteres Hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="0473d-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="0473d-149">Para EAP-TLS, TrustedRootCA contém o hash SHA-1 do Certificado de Autoridade de Certificação raiz confiável do servidor&#39;s.</span><span class="sxs-lookup"><span data-stu-id="0473d-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="0473d-150">No comando do computador Windows &quot;certutil.exe-dump cert\_file\_name&quot; mostrará uma cadeia de caracteres hash de&#39;s SHA-1 de certificado.</span><span class="sxs-lookup"><span data-stu-id="0473d-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="0473d-151">Colete a captura de pacotes de rede no Ponto de Acesso ou nos logs do servidor AAA para descobrir onde a sessão EAP falha.</span><span class="sxs-lookup"><span data-stu-id="0473d-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="0473d-152">Se a identidade EAP fornecida pelo HoloLens não for esperada, verifique se a identidade foi provisionada corretamente por meio do perfil Wi-Fi ou do certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="0473d-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="0473d-153">Se o servidor rejeitar o certificado de cliente do HoloLens, verifique se o certificado de cliente necessário foi provisionado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0473d-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="0473d-154">Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de Autoridade de Certificação raiz do servidor foi provisionado no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0473d-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="0473d-155">Se o perfil da empresa for provisionado pelo pacote de provisionamento do Wi-Fi, considere a aplicação do pacote de provisionamento em um computador com o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0473d-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="0473d-156">Se ele também falhar no computador com o Windows 10, siga o [Guia de solução de problemas de autenticação do cliente do Windows 802.1X](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="0473d-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="0473d-157">Envie-nos comentários por meio do [Hub de feedback](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="0473d-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="0473d-158">Recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="0473d-158">Additional resources:</span></span>
- [<span data-ttu-id="0473d-159">Exportar configurações de Wi-Fi de um dispositivo Windows</span><span class="sxs-lookup"><span data-stu-id="0473d-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="0473d-160">VPN</span><span class="sxs-lookup"><span data-stu-id="0473d-160">VPN</span></span>
<span data-ttu-id="0473d-161">Uma VPN pode ajudar a estabelecer uma conexão mais segura além de acesso à rede da sua empresa e a Internet.</span><span class="sxs-lookup"><span data-stu-id="0473d-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="0473d-162">O HoloLens 2 oferece suporte para cliente VPN interno e plug-in VPN da Plataforma Universal do Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="0473d-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="0473d-163">Protocolos VPN Interno suportados:</span><span class="sxs-lookup"><span data-stu-id="0473d-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="0473d-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="0473d-164">IKEv2</span></span>
- <span data-ttu-id="0473d-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="0473d-165">L2TP</span></span>
- <span data-ttu-id="0473d-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="0473d-166">PPTP</span></span>

<span data-ttu-id="0473d-167">Ao usar o certificado para autenticação do cliente VPN interno, será necessário que o certificado do cliente seja adicionado ao armazenamento de certificados do usuário.</span><span class="sxs-lookup"><span data-stu-id="0473d-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="0473d-168">Para descobrir se um plug-in VPN de terceiros suporta o HoloLens 2, vá até à Loja e localize o aplicativo VPN, depois verifique se o HoloLens está listado como um dispositivo suportado e, na página Requisitos do Sistema, veja se o aplicativo suporta a arquitetura ARM ou ARM64.</span><span class="sxs-lookup"><span data-stu-id="0473d-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="0473d-169">O HoloLens dá suporte apenas a aplicativos VPN de terceiros que estão na Plataforma Universal do Windows.</span><span class="sxs-lookup"><span data-stu-id="0473d-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="0473d-170">A VPN pode ser gerenciada pelo MDM via[Configurações/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), e definida através da  [política Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="0473d-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="0473d-171">Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [esses guias](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="0473d-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="0473d-172">VPN via interface do usuário</span><span class="sxs-lookup"><span data-stu-id="0473d-172">VPN via UI</span></span>

<span data-ttu-id="0473d-173">A VPN não está ativada por padrão, mas pode ser ativada manualmente, abrindo **Configurações** do aplicativo e navegando para  **Rede & Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="0473d-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="0473d-174">Selecione um provedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="0473d-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="0473d-175">Crie um nome de conexão.</span><span class="sxs-lookup"><span data-stu-id="0473d-175">Create a connection name.</span></span> 
1. <span data-ttu-id="0473d-176">Digite o nome ou o endereço do servidor.</span><span class="sxs-lookup"><span data-stu-id="0473d-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="0473d-177">Selecione o tipo de VPN.</span><span class="sxs-lookup"><span data-stu-id="0473d-177">Select the VPN type.</span></span>
1. <span data-ttu-id="0473d-178">Selecione o tipo de informações de entrada.</span><span class="sxs-lookup"><span data-stu-id="0473d-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="0473d-179">Opcionalmente, adicione o nome de usuário e a senha.</span><span class="sxs-lookup"><span data-stu-id="0473d-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="0473d-180">Aplicar as configurações de VPN.</span><span class="sxs-lookup"><span data-stu-id="0473d-180">Apply the VPN settings.</span></span> 

![Configurações de VPN do HoloLens](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="0473d-182">Conjunto de VPN via Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="0473d-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="0473d-183">Em nosso Windows Holographic, versão 20H2 corrigimos um problema de configuração de proxy para conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="0473d-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="0473d-184">Considere a atualização de dispositivos para esta compilação se você pretende usar esse fluxo.</span><span class="sxs-lookup"><span data-stu-id="0473d-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="0473d-185">Inicie o Designer de Configuração do Windows.</span><span class="sxs-lookup"><span data-stu-id="0473d-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="0473d-186">Clique em **Provisionar dispositivos HoloLens**, em seguida, selecione dispositivo de destino e **próximo**.</span><span class="sxs-lookup"><span data-stu-id="0473d-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="0473d-187">Digite o nome e o caminho do pacote.</span><span class="sxs-lookup"><span data-stu-id="0473d-187">Enter package name and path.</span></span>
1. <span data-ttu-id="0473d-188">Clique em **Alternar para o editor avançado**.</span><span class="sxs-lookup"><span data-stu-id="0473d-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="0473d-189">Abrir **Configurações de tempo de execução** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="0473d-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="0473d-190">Configurar o VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="0473d-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="0473d-191">Selecione ProfileType: **Nativo** ou **Terceiros**.</span><span class="sxs-lookup"><span data-stu-id="0473d-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="0473d-192">Em perfil Nativo, selecione **NativeProtocolType**, em seguida, configurar servidor, política de roteamento, tipo de autenticação e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="0473d-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="0473d-193">Para o perfil de "Terceiros", configure a URL do servidor, o nome da família do pacote do aplicativo de plug-in de VPN (somente três predefinidos) e configurações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="0473d-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="0473d-194">Exporte seu pacote.</span><span class="sxs-lookup"><span data-stu-id="0473d-194">Export your package.</span></span>
1. <span data-ttu-id="0473d-195">Conecte seu HoloLens e copie o arquivo. ppkg no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0473d-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="0473d-196">No HoloLens, aplique a VPN .ppkg abrindo o menu Iniciar e selecionando **Configurações** -> **Conta** -> **Acessar trabalho ou escola** -> **Adicionar ou remover pacote de provisionamento** -> Selecionar pacote de VPN.</span><span class="sxs-lookup"><span data-stu-id="0473d-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="0473d-197">Configurando a VPN via Intune</span><span class="sxs-lookup"><span data-stu-id="0473d-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="0473d-198">Basta seguir as documentações do Intune para começar.</span><span class="sxs-lookup"><span data-stu-id="0473d-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="0473d-199">Ao seguir estas etapas, lembre-se dos protocolos VPN internos que os dispositivos do HoloLens dão suporte.</span><span class="sxs-lookup"><span data-stu-id="0473d-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="0473d-200">[Crie perfis VPN para se conectar a servidores VPN no Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="0473d-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="0473d-201">[Configurações do dispositivo Windows 10 e Windows Holographic para adicionar conexões VPN usando o Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="0473d-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="0473d-202">Quando terminar, lembre-se de [atribuir o perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="0473d-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="0473d-203">VPN por meio de soluções MDM de terceiros</span><span class="sxs-lookup"><span data-stu-id="0473d-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="0473d-204">Exemplo de conexão de VPN de terceiros:</span><span class="sxs-lookup"><span data-stu-id="0473d-204">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="0473d-205">Exemplo de VPN IKEv2 nativa:</span><span class="sxs-lookup"><span data-stu-id="0473d-205">Native IKEv2 VPN example:</span></span>
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
## <span data-ttu-id="0473d-206">Desabilitando o Wi-Fi no HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="0473d-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="0473d-207">Usando o aplicativo Configurações no HoloLens</span><span class="sxs-lookup"><span data-stu-id="0473d-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="0473d-208">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0473d-209">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0473d-210">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="0473d-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0473d-211">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="0473d-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0473d-212">Selecione o controle deslizante do Wi-Fi para movê-lo para a posição **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="0473d-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="0473d-213">Isso desativará os componentes de RF do rádio Wi-Fi e desabilitará toda a funcionalidade de Wi-Fi no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0473d-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="0473d-214">Quando o rádio Wi-Fi estiver desativado, o HoloLens não poderá carregar automaticamente seus [espaços](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="0473d-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="0473d-215">Mova o controle deslizante para a posição **Ativado** para ativar o rádio Wi-Fi e restaurar a funcionalidade de Wi-Fi no Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0473d-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="0473d-216">O estado do rádio Wi-Fi selecionado (**Ativado** ou **Desativado**) persistirá nas reinicializações.</span><span class="sxs-lookup"><span data-stu-id="0473d-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="0473d-217">Identificando o endereço IP do seu HoloLens na rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0473d-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="0473d-218">Ao usar o aplicativo Configurações</span><span class="sxs-lookup"><span data-stu-id="0473d-218">By using the Settings app</span></span>

1. <span data-ttu-id="0473d-219">Abra o menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0473d-220">Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="0473d-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0473d-221">O aplicativo **Configurações** será posicionado automaticamente à sua frente.</span><span class="sxs-lookup"><span data-stu-id="0473d-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0473d-222">Selecione **Rede e Internet**.</span><span class="sxs-lookup"><span data-stu-id="0473d-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0473d-223">Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="0473d-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propriedades de hardware nas configurações de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="0473d-225">O endereço IP é exibido ao lado do **Endereço IPv4**.</span><span class="sxs-lookup"><span data-stu-id="0473d-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="0473d-226">Usando comandos de voz</span><span class="sxs-lookup"><span data-stu-id="0473d-226">By using voice commands</span></span>

<span data-ttu-id="0473d-227">Dependendo da versão do seu dispositivo, você pode usar comandos de voz internos ou a Cortana para exibir seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="0473d-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="0473d-228">Em versões posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) fale "Qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="0473d-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="0473d-229">e será exibido.</span><span class="sxs-lookup"><span data-stu-id="0473d-229">and it will be displayed.</span></span> <span data-ttu-id="0473d-230">Para versões anteriores ou o HoloLens (1ª geração), diga: "Ei Cortana, qual é o meu endereço IP?"</span><span class="sxs-lookup"><span data-stu-id="0473d-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="0473d-231">e a Cortana exibirá e lerá seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="0473d-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="0473d-232">Ao usar o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="0473d-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="0473d-233">Em um navegador da Web em seu computador, abra o [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="0473d-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="0473d-234">Navegue até a seção **Rede**.</span><span class="sxs-lookup"><span data-stu-id="0473d-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="0473d-235">Essa seção exibe o endereço IP e outras informações de rede.</span><span class="sxs-lookup"><span data-stu-id="0473d-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="0473d-236">Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="0473d-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
