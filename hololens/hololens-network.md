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
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034065"
---
# <a name="connect-hololens-to-a-network"></a>Conectar o HoloLens a uma rede

Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede. O HoloLens contém uma rádio Wi-Fi 2x2 compatível com 802.11ac. Conectá-lo a uma rede é semelhante a conectar um dispositivo Windows 10 Desktop ou Mobile a uma rede Wi-Fi. Este guia ajudará você a:

- Conectar-se a uma rede usando Wi-Fi ou, somente para o HoloLens 2, Wi-Fi Direct ou Ethernet por USB-C
- Desabilitar e habilitar o Wi-Fi novamente

Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Conectando pela primeira vez

Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi. Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo. Além disso, verifique se a rede não exige o uso de um certificado para se conectar. Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.

Em dispositivos HoloLens 2, um usuário também pode [usar um adaptador USB-C para Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para se conectar diretamente à Wi-Fi para ajudar a configurar o dispositivo. Uma vez que o dispositivo foi configurado, o usuário pode continuar usando o adaptador ou desconectá-lo do adaptador e [conectar-se à Wi-Fi após a configuração](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Conectar-se ao Wi-Fi após a configuração

1. Faça o **Gesto de iniciar** e selecione **Configurações**. O aplicativo Configurações será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet** > **Wi-Fi**. Verifique se o Wi-Fi está ativado. Se você não vir sua rede, role a lista para baixo.
1. Selecione uma rede e escolha **Conectar**.
1. Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.

![Configurações de Wi-Fi do HoloLens.](./images/hololens-2-wifi-settings.jpg)

Para confirmar que você está conectado a uma rede Wi-Fi, verifique o status Wi-Fi no menu **Iniciar**:

1. Abra o menu **Iniciar**.
1. Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**. O estado do Wi-Fi e do SSID da rede conectada serão exibidos.

> [!TIP]
> Se o Wi-Fi não estiver disponível, você poderá [conectar-se a redes celular e 5G](hololens-cellular.md).

> [!IMPORTANT]
> Por design, os usuários não podem ajustar o comportamento de roaming de Wi-Fi do HoloLens 2. **A única maneira de atualizar a lista de redes Wi-Fi é ligar e desligar a Wi-Fi**. Isso evita vários problemas, como quando um dispositivo pode ficar "preso" a um PA ao estar fora de alcance.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Conectar o HoloLens à Rede Wi-Fi Corporativa

Os perfis de Wi-Fi Corporativo usam EAP (Protocolo de Autenticação Extensível) para autenticar conexões de Wi-Fi. O perfil de Wi-Fi Corporativo do HoloLens pode ser configurado por meio do pacote de provisionamento ou MDM criado pelo [Designer de Configuração do Windows](/windows/configuration/provisioning-packages/provisioning-packages).

Para o dispositivo gerenciado do Microsoft Intune, consulte o [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para obter instruções de configuração.

Para criar um pacote de provisionamento Wi-Fi em WCD, é necessário um arquivo .xml de perfil de Wi-Fi pré-configurado. Aqui está um exemplo de perfil Wi-Fi para WPA2-Enterprise com autenticação EAP-TLS:

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


O AC raiz do servidor e o certificado do cliente podem precisar ser provisionados no dispositivo, dependendo do tipo EAP.

Recursos adicionais:

- Esquema WLANv1Profile: [[MS-GPWL]: Esquema de Perfil de LAN Sem Fio v1 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Esquema EAP-TLS: [[MS-GPWL]: Esquema Microsoft EAP TLS | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Verifique nossa página de [Solução de problemas](hololens2-enterprise-troubleshooting.md#) se você tiver problemas para se conectar ao seu Wi-Fi.

## <a name="configure-network-proxy"></a>Configurar o proxy de rede

Esta seção aborda o proxy de rede para aplicativos do sistema operacional HoloLens e da UWP (Plataforma Universal do Windows) que usam a pilha HTTP do Windows. Aplicativos que usam uma pilha HTTP que não é do Windows podem ter a própria configuração e manipulação de proxy. 

### <a name="proxy-configurations"></a>Configurações de proxy 

- Script de PAC (configuração automática de proxy): um [arquivo PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (abre um site que não é da Microsoft) contém uma função JavaScript FindProxyForURL(url, host). 
- Proxy estático: na forma de Servidor:Porta.  
- Protocolo WPAD (protocolo de descoberta automática de proxy da Web): forneça a URL do arquivo de configuração de proxy por DHCP ou DNS. 

### <a name="proxy-provisioning-methods"></a>Métodos de provisionamento de proxy 
Existem três maneiras de provisionar proxies:

 

1.  **Interface do usuário de Configurações:** 
    1. Proxy por usuário (20H2 ou anterior):
        1. Abra o menu Iniciar e selecione Configurações.
        2. Selecione Rede e Internet e, depois, Proxy no menu à esquerda.
        3. Role para baixo até Configuração de proxy manual e alterne Usar um servidor proxy para Ativado.
        4. Digite o endereço IP do servidor proxy.
        5. Digite o número da porta.
        6. Clique em Salvar.
      1. Proxy de Wi-Fi (21H1 ou superior):
          1. Abra o menu Iniciar e vá para a página de Propriedades da rede Wi-Fi.
          1. Role até Proxy
          1. Altere para Configuração manual
          1. Digite o endereço IP do servidor proxy.
          1. Digite o número da porta.
          1. Clique em Aplicar.
        
 2. **MDM** 
     1. Intune: use estas [etapas](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para configurar o proxy no Intune. Você precisará rolar até a parte inferior da seção.
     1. Outras soluções de MDM de terceiros: use um [CSP de WiFi](/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. Abra o Designer de Configuração do Windows
    1. Clique em Provisionamento avançado, insira o nome do novo Projeto e clique em Avançar.
    1. Selecione Windows Holographic (HoloLens 2) e clique em Avançar.
    1. Importe seu PPKG (opcional) e clique em Concluir.
    1. Expanda Configurações de Runtime -> Perfis de Conectividade -> WLAN -> Proxy de WLAN.
    1. Insira o SSID de sua rede Wi-Fi e clique em Adicionar.
    1. Selecione a rede Wi-Fi na janela esquerda e insira as personalizações desejadas. As personalizações habilitadas serão exibidas em negrito no menu à esquerda.
    1. Clique em Salvar e Encerrar.
    1. [Aplique](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) o pacote de provisionamento ao HoloLens.

Os [CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) estão por trás de muitas das tarefas de gerenciamento e das políticas do Windows 10, no Microsoft Intune e nos provedores de serviço MDM que não são da Microsoft. Você também pode usar o [Designer de Configuração do Windows](/windows/configuration/provisioning-packages/provisioning-install-icd) para criar um [pacote de provisionamento](/windows/configuration/provisioning-packages/provisioning-packages) e aplicá-lo ao HoloLens 2.
Os CSPs com maior probabilidade de serem aplicados ao seu HoloLens 2 são:

- [CSP de Wi-Fi](/windows/client-management/mdm/wifi-csp): proxy de Wi-Fi por perfil 

[Outros CSPs com suporte de dispositivos HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Uma conexão VPN pode ajudar a estabelecer uma conexão mais segura além de acesso à rede da sua empresa e a Internet. O HoloLens 2 dá suporte para cliente VPN interno e plug-in VPN da UWP (Plataforma Universal do Windows). 

Protocolos de VPN Interno compatíveis:
- IKEv2
- L2TP
- PPTP

Ao usar o certificado para autenticação do cliente de VPN interno, será necessário que o certificado do cliente seja adicionado ao repositório de certificados do usuário. Para descobrir se um plug-in de VPN de terceiros dá suporte ao HoloLens 2, acesse a Store e localize o aplicativo VPN, depois verifique se o HoloLens está listado como um dispositivo compatível e, na página Requisitos do Sistema, veja se o aplicativo dá suporte à arquitetura ARM ou ARM64. O HoloLens dá suporte apenas a aplicativos VPN de terceiros que estão na Plataforma Universal do Windows.

 A VPN pode ser gerenciada pelo MDM via [Configurações/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) e definida por meio da [política Vpnv2-csp](/windows/client-management/mdm/vpnv2-csp).

Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [estes guias](/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN via interface do usuário

A VPN não está habilitada por padrão, mas pode ser habilitada manualmente abrindo o aplicativo **Configurações** e navegando para **Rede e Internet -> VPN**.
1. Selecione um provedor de VPN.
1. Crie um nome de conexão. 
1. Digite o nome ou o endereço do servidor.
1. Selecione o tipo de VPN.
1. Selecione o tipo de informações de conexão. 
1. Opcionalmente, adicione o nome de usuário e a senha.
1. Aplicar as configurações de VPN. 

![Configurações de VPN do HoloLens.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Conjunto de VPN via Pacote de Provisionamento

> [!TIP] 
> Em nosso Windows Holographic versão 20H2, corrigimos um problema de configuração de proxy para conexão VPN. Considere a atualização de dispositivos para esse build se você pretende usar esse fluxo.

1. Inicie o Designer de Configuração do Windows.
1. Clique em **Provisionar dispositivos HoloLens**, selecione o dispositivo de destino e escolha **Avançar**.
1. Digite o nome e o caminho do pacote.
1. Clique em **Alternar para o editor avançado**.
1. Abra **Configurações de runtime** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.
1. Configurar o VPNProfileName
1. Selecione o ProfileType: **Nativo** ou **Terceiros**.
    1. Para o perfil Nativo, selecione **NativeProtocolType**, em seguida, configurar servidor, política de roteamento, tipo de autenticação e outras configurações.
    1. Para o perfil de "Terceiros", configure a URL do servidor, o nome da família do pacote do aplicativo de plug-in de VPN (somente três predefinidos) e configurações personalizadas.
1. Exporte seu pacote.
1. Conecte seu HoloLens e copie o arquivo .ppkg no dispositivo. 
1. No HoloLens, aplique o .ppkg da VPN abrindo o menu Iniciar e selecionando **Configurações** -> **Conta** -> **Acessar conta corporativa ou de estudante** -> **Adicionar ou remover pacote de provisionamento** -> Selecione seu pacote de VPN.


### <a name="setting-up-vpn-via-intune"></a>Configuração de VPN via Intune
Basta seguir as documentações do Intune para começar. Ao seguir estas etapas, lembre-se dos protocolos de VPN internos a que os dispositivos do HoloLens dão suporte. 

[Criar perfis de VPN para se conectar a servidores VPN no Microsoft Intune](/mem/intune/configuration/vpn-settings-configure).

[Configurações de dispositivos Windows 10 e Windows Holographic para adicionar conexões VPN usando o Intune](/mem/intune/configuration/vpn-settings-windows-10).

Quando terminar, lembre-se de [atribuir o perfil](/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN por meio de soluções MDM de terceiros
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Desabilitando o Wi-Fi no HoloLens (1ª geração)

### <a name="using-the-settings-app-on-hololens"></a>Usando o aplicativo Configurações no HoloLens

1. Abra o menu **Iniciar**.
1. Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os Aplicativos** à direita do menu **Iniciar**. O aplicativo **Configurações** será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet**.
1. Selecione o controle deslizante do Wi-Fi para movê-lo para a posição **Desativado**. Isso desligará os componentes de RF do rádio Wi-Fi e desabilitará toda a funcionalidade de Wi-Fi no HoloLens.

    > [!WARNING]
    > Quando o rádio Wi-Fi estiver desabilitado, o HoloLens não poderá carregar automaticamente seus [espaços](hololens-spaces.md).

1. Mova o controle deslizante para a posição **Ativado** para ativar o rádio Wi-Fi e restaurar a funcionalidade de Wi-Fi no Microsoft HoloLens. O estado do rádio Wi-Fi selecionado (**Ativado** ou **Desativado**) persistirá nas reinicializações.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identificando o endereço IP do seu HoloLens na rede Wi-Fi

### <a name="by-using-the-settings-app"></a>Usando o aplicativo Configurações

1. Abra o menu **Iniciar**.
1. Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os Aplicativos** à direita do menu **Iniciar**. O aplicativo **Configurações** será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet**.
1. Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.

    ![Propriedades de hardware nas configurações de Wi-Fi.](./images/wifi-hololens-hwdetails.jpg)

   O endereço IP aparece ao lado do **endereço IPv4**.

### <a name="by-using-voice-commands"></a>Usando comandos de voz

Dependendo do build dos seus dispositivos, você pode usar comandos de voz internos ou a Cortana para exibir seu endereço IP. Em builds posteriores ao [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), fale "Qual é o meu endereço IP?" e ele será exibido. Para builds anteriores ou o HoloLens (1ª geração), diga: "Ei Cortana, qual é o meu endereço IP?" e a Cortana exibirá e lerá seu endereço IP.

### <a name="by-using-windows-device-portal"></a>Usando o Portal de Dispositivos do Windows

1. Em um navegador da Web no PC, abra o [portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navegue até a seção **Rede**.  
   Essa seção exibe o endereço IP e outras informações de rede. Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.

## <a name="change-ip-address-to-static-address"></a>Alterar o endereço IP para um endereço estático
### <a name="by-using-settings"></a>Usando Configurações
 
1. Abra o menu **Iniciar**.
1. Selecione o aplicativo **Configurações** em **Iniciar** ou na lista **Todos os Aplicativos** à direita do menu **Iniciar**. O aplicativo **Configurações** será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet**.
1. Role para baixo até a lista de redes Wi-Fi disponíveis e selecione **Propriedades de hardware**.
1. Na janela **Editar configurações de IP**, altere o primeiro campo para **Manual**.
1. Insira a configuração de IP desejada nos campos restantes e clique em **Salvar**.

### <a name="by-using-windows-device-portal"></a>Usando o Portal de Dispositivos do Windows

1. Em um navegador da Web no PC, abra o [portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navegue até a seção **Rede**.
1. Selecione o botão **Configuração do IPv4**.
1. Selecione **Usar o endereço IP a seguir** e insira a configuração TCP/IP desejada.
1. Selecione **Usar os endereços de servidor DNS a seguir** e insira os endereços de servidor DNS Preferencial e Alternativo, se necessário.
1. Clique em **Save** (Salvar). 
