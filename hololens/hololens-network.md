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
# Conectar a uma rede

Para fazer a maioria das coisas no HoloLens, você precisa estar conectado a uma rede. Este guia ajudará você a:

- Conectar-se a uma rede usando Wi-Fi ou (somente para HoloLens 2) USB-C por Ethernet
- Desabilitar e habilitar o Wi-Fi novamente

Leia mais sobre [como usar o HoloLens offline](hololens-offline.md).

## Conectando pela primeira vez

Na primeira vez em usar o HoloLens, você será orientado em meio à conexão a uma rede Wi-Fi. Se você tiver problemas para se conectar ao Wi-Fi durante a configuração, verifique se sua rede é uma rede aberta, protegida por senha ou de portal cativo. Certifique-se de que a rede não exija o uso de um certificado para que você se conecte. Após a configuração, você pode se conectar a outros tipos de redes Wi-Fi.

## Conectando-se ao Wi-Fi após a configuração

1. Selecione **Iniciar** > **Configurações**.
   - *Somente para HoloLens (1ª geração)*: use seu foco para mover o aplicativo Configurações, depois feche e abra os dedos indicador e polegar para posicioná-lo ou diga "Place" (Posicionar).
1. Selecione **Rede e Internet** > **Wi-Fi**. Se você não vir sua rede, role a lista para baixo.
1. Selecione uma rede e, em seguida, **Conectar**.
1. Se for solicitada uma senha de rede, digite-a e selecione **Avançar**.

## Conectando-se ao Wi-Fi no HoloLens (1ª geração)

O HoloLens contém um rádio Wi-Fi 2x2, com capacitação 802.11ac. Conectar o HoloLens a uma rede Wi-Fi é semelhante a conectar um dispositivo móvel ou computador Windows 10 a uma rede Wi-Fi.

![Configurações de Wi-Fi do HoloLens](./images/wifi-hololens-600px.jpg)

1. Abra o menu **Iniciar**.
1. Selecione o aplicativo Configurações em **Iniciar** ou na lista **Todos os apps** à direita do menu **Iniciar**. O aplicativo Configurações será posicionado automaticamente à sua frente.
1. Selecione **Rede e Internet**.
1. Verifique se o Wi-Fi está ligado.
1. Selecione uma rede Wi-Fi na lista.
1. Se necessário, digite a senha da rede Wi-Fi.

Você também pode confirmar se está conectado a uma rede Wi-Fi ao verificar o status do Wi-Fi no menu **Iniciar**:

1. Abra o menu **Iniciar**.
1. Veja o status do Wi-Fi no canto superior esquerdo do menu **Iniciar**. O estado do Wi-Fi e do SSID da rede conectada serão exibidos.

## Solução de problemas de conexão com Wi-Fi

Se você tiver problemas para se conectar à rede Wi-Fi, confira [Não consigo me conectar ao Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.

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

### Ao usar a Cortana

Diga "Hey Cortana, What's my IP address?" (Ei, Cortana, qual é o meu endereço IP?) e a Cortana exibirá e lerá seu endereço IP.

### Ao usar o Portal de Dispositivos do Windows

1. Em um navegador da Web em seu computador, abra o [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Navegue até a seção **Rede**.  
   Essa seção exibe o endereço IP e outras informações de rede. Usando esse método, você pode copiar e colar o endereço IP em seu computador de desenvolvimento.
