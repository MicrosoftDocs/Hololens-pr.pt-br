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
# Conectar o HoloLens a uma rede

Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede. Este guia ajudará você a:

- Conectar-se a uma rede usando Wi-Fi ou (somente para HoloLens 2) USB-C por Ethernet
- Desabilitar e habilitar o Wi-Fi novamente

Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).

## Conectando pela primeira vez

Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi. Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo. Certifique-se de que a rede não exija o uso de um certificado para que você se conecte. Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.

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

## VPN
Uma VPN pode ajudar a estabelecer uma conexão mais segura além de acesso à rede da sua empresa e a Internet. O HoloLens 2 oferece suporte para cliente VPN interno e plug-in VPN da Plataforma Universal do Windows (UWP). 

Protocolos VPN Interno suportados:
- IKEv2
- L2TP
- PPTP

Ao usar o certificado para autenticação do cliente VPN interno, será necessário que o certificado do cliente seja adicionado ao armazenamento de certificados do usuário. Para descobrir se um plug-in VPN de terceiros suporta o HoloLens 2, vá até à Loja e localize o aplicativo VPN, depois verifique se o HoloLens está listado como um dispositivo suportado e, na página Requisitos do Sistema, veja se o aplicativo suporta a arquitetura ARM ou ARM64. O HoloLens suporta apenas aplicativos VPN de terceiros que estão na Plataforma Universal do Windows.

A VPN não está ativada por padrão, mas pode ser ativada manualmente, abrindo **Configurações** do aplicativo e navegando para  **Rede & Internet -> VPN**. A VPN pode ser gerenciada pelo MDM via[Configurações/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), e definido através da  [política Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).
Saiba mais sobre [como configurar a VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) com [esses guias](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

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
