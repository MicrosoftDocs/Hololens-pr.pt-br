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
# Conectar o HoloLens a uma rede

Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede. Este guia ajudará você a:

- Conectar-se a uma rede usando Wi-Fi ou (somente para HoloLens 2) USB-C por Ethernet
- Desabilitar e habilitar o Wi-Fi novamente

Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).

## Conectando pela primeira vez

Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi. Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo. Certifique-se de que a rede não exija o uso de um certificado para que você se conecte. Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.

Em dispositivos do HoloLens 2, um usuário também pode [usar um adaptador USB-C para Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectar-se diretamente ao Wi-Fi e ajudar a configurar o dispositivo. Uma vez que o dispositivo foi configurado, um usuário pode continuar a usar o adaptador ou desconectá-lo do adaptador e [se conectar à uma rede Wi-Fi após a configuração](hololens-network.md#connecting-to-wi-fi-after-setup). 

## Conectando-se ao Wi-Fi após a configuração

1. Faça o **gesto de Iniciar** e selecione **Configurações**. O aplicativo Configurações será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet** > **Wi-Fi**. Verifique se o Wi-Fi está ligado. Se você não vir sua rede, role a lista para baixo.
1. Selecione uma rede e, em seguida, **Conectar**.
1. Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.

O HoloLens contém um rádio Wi-Fi 2x2, com capacitação 802.11ac. Conectar o HoloLens a uma rede Wi-Fi é semelhante a conectar um dispositivo móvel ou computador Windows 10 a uma rede Wi-Fi.

![Configurações de Wi-Fi do HoloLens](./images/wifi-hololens-600px.jpg)

Você também pode confirmar se está conectado a uma rede Wi-Fi ao verificar o status do Wi-Fi no menu **Iniciar**:

1. Abra o menu **Iniciar**.
1. Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**. O estado do Wi-Fi e do SSID da rede conectada serão exibidos.

## Solução de problemas de conexão com Wi-Fi

Se você tiver problemas para se conectar à rede Wi-Fi, confira [Não consigo me conectar ao Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.

## Conectar o HoloLens à Rede Wi-Fi Empresarial

Os perfis de Wi-Fi Empresarial usam EAP (Protocolo de Autenticação Extensível) para autenticar conexões de Wi-Fi. O perfil de Wi-Fi Empresarial do HoloLens pode ser configurado por meio do pacote de provisionamento ou MDM criado pelo [Designer de Configuração do Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Para o dispositivo gerenciado do Microsoft Intune, consulte o [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para obter instruções de configuração.

Para criar um pacote de provisionamento Wi-Fi em WCD, é necessário um arquivo .xml Wi-Fi pré-configurado. Aqui está um exemplo de perfil Wi-Fi para WPA2-Enterprise com autenticação EAP-TLS:

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


O certificado de CA raiz do servidor e o certificado do cliente podem precisar ser provisionados no dispositivo, dependendo do tipo EAP.

Recursos adicionais:

- Esquema WLANv1Profile: [[MS-GPWL]: esquema do Perfil v1 da LAN Wireless | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Esquema EAP-TLS: [[MS-GPWL]: esquema Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### Solução de problemas de EAP

1. Verifique se o perfil do Wi-Fi tem as configurações corretas:
   1. O tipo EAP está configurado corretamente, tipos EAP comuns: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
   1. O nome Wi-Fi SSID está correto e corresponde à cadeia de caracteres Hexadecimal.
   1. Para EAP-TLS, TrustedRootCA contém o hash SHA-1 do Certificado de Autoridade de Certificação raiz confiável do servidor&#39;s. No comando do computador Windows &quot;certutil.exe-dump cert\_file\_name&quot; mostrará uma cadeia de caracteres hash de&#39;s SHA-1 de certificado.
1. Colete a captura de pacotes de rede no Ponto de Acesso ou nos logs do servidor AAA para descobrir onde a sessão EAP falha.
   1. Se a identidade EAP fornecida pelo HoloLens não for esperada, verifique se a identidade foi provisionada corretamente por meio do perfil Wi-Fi ou do certificado do cliente.
   1. Se o servidor rejeitar o certificado de cliente do HoloLens, verifique se o certificado de cliente necessário foi provisionado no dispositivo.
   1. Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de Autoridade de Certificação raiz do servidor foi provisionado no HoloLens.
1. Se o perfil da empresa for provisionado pelo pacote de provisionamento do Wi-Fi, considere a aplicação do pacote de provisionamento em um computador com o Windows 10. Se ele também falhar no computador com o Windows 10, siga o [Guia de solução de problemas de autenticação do cliente do Windows 802.1X](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).
1. Envie-nos comentários por meio do [Hub de feedback](https://docs.microsoft.com/hololens/hololens-feedback).

### Recursos adicionais:
- [Exportar configurações de Wi-Fi de um dispositivo Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## VPN
Uma VPN pode ajudar a estabelecer uma conexão mais segura além de acesso à rede da sua empresa e a Internet. O HoloLens 2 oferece suporte para cliente VPN interno e plug-in VPN da Plataforma Universal do Windows (UWP). 

Protocolos VPN Interno suportados:
- IKEv2
- L2TP
- PPTP

Ao usar o certificado para autenticação do cliente VPN interno, será necessário que o certificado do cliente seja adicionado ao armazenamento de certificados do usuário. Para descobrir se um plug-in VPN de terceiros suporta o HoloLens 2, vá até à Loja e localize o aplicativo VPN, depois verifique se o HoloLens está listado como um dispositivo suportado e, na página Requisitos do Sistema, veja se o aplicativo suporta a arquitetura ARM ou ARM64. O HoloLens dá suporte apenas a aplicativos VPN de terceiros que estão na Plataforma Universal do Windows.

 A VPN pode ser gerenciada pelo MDM via[Configurações/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), e definida através da  [política Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [esses guias](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

### VPN via interface do usuário

A VPN não está ativada por padrão, mas pode ser ativada manualmente, abrindo **Configurações** do aplicativo e navegando para  **Rede & Internet -> VPN**.
1. Selecione um provedor de VPN.
1. Crie um nome de conexão. 
1. Digite o nome ou o endereço do servidor.
1. Selecione o tipo de VPN.
1. Selecione o tipo de informações de entrada. 
1. Opcionalmente, adicione o nome de usuário e a senha.
1. Aplicar as configurações de VPN. 

![Configurações de VPN do HoloLens](./images/vpn-settings-ui.jpg)

### Conjunto de VPN via Pacote de Provisionamento

> [!TIP] 
> Em nosso Windows Holographic, versão 20H2 corrigimos um problema de configuração de proxy para conexão VPN. Considere a atualização de dispositivos para esta compilação se você pretende usar esse fluxo.

1. Inicie o Designer de Configuração do Windows.
1. Clique em **Provisionar dispositivos HoloLens**, em seguida, selecione dispositivo de destino e **próximo**.
1. Digite o nome e o caminho do pacote.
1. Clique em **Alternar para o editor avançado**.
1. Abrir **Configurações de tempo de execução** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.
1. Configurar o VPNProfileName
1. Selecione ProfileType: **Nativo** ou **Terceiros**.
    1. Em perfil Nativo, selecione **NativeProtocolType**, em seguida, configurar servidor, política de roteamento, tipo de autenticação e outras configurações.
    1. Para o perfil de "Terceiros", configure a URL do servidor, o nome da família do pacote do aplicativo de plug-in de VPN (somente três predefinidos) e configurações personalizadas.
1. Exporte seu pacote.
1. Conecte seu HoloLens e copie o arquivo. ppkg no dispositivo. 
1. No HoloLens, aplique a VPN .ppkg abrindo o menu Iniciar e selecionando **Configurações** -> **Conta** -> **Acessar trabalho ou escola** -> **Adicionar ou remover pacote de provisionamento** -> Selecionar pacote de VPN.


### Configurando a VPN via Intune
Basta seguir as documentações do Intune para começar. Ao seguir estas etapas, lembre-se dos protocolos VPN internos que os dispositivos do HoloLens dão suporte. 

[Crie perfis VPN para se conectar a servidores VPN no Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).

[Configurações do dispositivo Windows 10 e Windows Holographic para adicionar conexões VPN usando o Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).

Quando terminar, lembre-se de [atribuir o perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### VPN por meio de soluções MDM de terceiros
Exemplo de conexão de VPN de terceiros:
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

Exemplo de VPN IKEv2 nativa:
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
## Desabilitando o Wi-Fi no HoloLens (1ª geração)

### Usando o aplicativo Configurações no HoloLens

1. Abra o menu **Iniciar**.
1. Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**. O aplicativo **Configurações** será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet**.
1. Selecione o controle deslizante do Wi-Fi para movê-lo para a posição **Desativado**. Isso desativará os componentes de RF do rádio Wi-Fi e desabilitará toda a funcionalidade de Wi-Fi no HoloLens.

    > [!WARNING]
    > Quando o rádio Wi-Fi estiver desativado, o HoloLens não poderá carregar automaticamente seus [espaços](hololens-spaces.md).

1. Mova o controle deslizante para a posição **Ativado** para ativar o rádio Wi-Fi e restaurar a funcionalidade de Wi-Fi no Microsoft HoloLens. O estado do rádio Wi-Fi selecionado (**Ativado** ou **Desativado**) persistirá nas reinicializações.

## Identificando o endereço IP do seu HoloLens na rede Wi-Fi

### Ao usar o aplicativo Configurações

1. Abra o menu **Iniciar**.
1. Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**. O aplicativo **Configurações** será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet**.
1. Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.

    ![Propriedades de hardware nas configurações de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   O endereço IP é exibido ao lado do **Endereço IPv4**.

### Usando comandos de voz

Dependendo da versão do seu dispositivo, você pode usar comandos de voz internos ou a Cortana para exibir seu endereço IP. Em versões posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) fale "Qual é o meu endereço IP?" e será exibido. Para versões anteriores ou o HoloLens (1ª geração), diga: "Ei Cortana, qual é o meu endereço IP?" e a Cortana exibirá e lerá seu endereço IP.

### Ao usar o Portal de Dispositivos do Windows

1. Em um navegador da Web em seu computador, abra o [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navegue até a seção **Rede**.  
   Essa seção exibe o endereço IP e outras informações de rede. Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.
