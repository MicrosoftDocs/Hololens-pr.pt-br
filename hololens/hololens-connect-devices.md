---
title: Conectar-se a dispositivos Bluetooth e USB-C
description: Comece a conectar aos dispositivos e acessórios Bluetooth e USB C a partir de seus dispositivos de realidade mista HoloLens.
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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427729"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Conectar-se a dispositivos Bluetooth e USB-C

## <a name="pair-bluetooth-devices"></a>Emparelhar dispositivos Bluetooth

O HoloLens 2 é compatível com as seguintes classes de dispositivos Bluetooth:

- [HID](/windows-hardware/drivers/hid/):
    - Mouse
    - Keyboard
- Dispositivos de saída de áudio (A2DP)

O HoloLens 2 é compatível com as seguintes APIs de dispositivos Bluetooth:
- [Servidor](/windows/uwp/devices-sensors/gatt-server) e [Cliente](/windows/uwp/devices-sensors/gatt-client) GATT
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Talvez seja preciso instalar aplicativos complementares na Microsoft Store para realmente usar os dispositivos HID e GATT.

O HoloLens 2 (1ª geração) é compatível com as seguintes classes de dispositivos Bluetooth:

- Mouse
- Keyboard
- [Clicador do HoloLens (1ª geração)](hololens1-clicker.md)

> [!NOTE]
> Outros tipos de dispositivos Bluetooth, como alto-falantes, fones de ouvido, smartphones e game pads, podem estar listados como disponíveis nas configurações do HoloLens. No entanto, esses dispositivos não são compatíveis com o HoloLens (1ª geração). Para obter mais informações, confira [Configurações do HoloLens listam os dispositivos disponíveis, mas os dispositivos não funcionam](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Emparelhar um Bluetooth ou mouse

1. Ligue o teclado ou o mouse e torne-o localizável. Para saber como tornar o dispositivo localizável, procure por informações sobre o dispositivo (ou sua documentação) ou visite o site do fabricante.

1. Use o gesto de abrir a mão [HoloLens (1ª geração)] ou o gesto de início (HoloLens 2) para ir até **Iniciar** e, em seguida, escolha **Configurações**.

1. Escolha **Dispositivos** e verifique se o Bluetooth está ativado.  

1. Quando vir o nome do dispositivo, escolha **Emparelhar** e siga as instruções.

## <a name="disable-bluetooth"></a>Desativar Bluetooth

Esse procedimento desativa os componentes RF do rádio Bluetooth e desabilita toda a funcionalidade Bluetooth no Microsoft HoloLens.

1. Use o gesto de abrir a mão [HoloLens (1ª geração)] ou o gesto de início (HoloLens 2) para ir até **Iniciar** e, em seguida, escolha **Configurações** > **Dispositivos**.

1. Mova a opção do controle deslizante **Bluetooth** para a posição **Desligado**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: conectar dispositivos USB-C

O HoloLens 2 é compatível com as seguintes classes de dispositivos USB-C:

- Dispositivos de armazenamento em massa (como unidades Thumb)
- Adaptadores de Ethernet (incluindo carregamento Ethernet Plus)
- Adaptadores de áudio digital USB-C a 3,5 mm
- Fones de ouvido digital USB-C (incluindo os adaptadores de carregamento plus do headset)
- Microfones externos USB-C ([Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e versões superiores)
- Mouse com fio
- Teclado com fio
- Hubs PD combinados ( carregamento USB A + PD)


> [!NOTE]
> Em resposta aos comentários do cliente, habilitamos o suporte limitado para conectividade celular diretamente ao HoloLens via USB-C. Confira [Conexão para Celular e 5G](hololens-cellular.md) para obter mais informações.

### <a name="usb-c-external-microphone-support"></a>Suporte para microfone externo USB-C

> [!IMPORTANT]
> Conectar **um microfone USB não o definirá automaticamente como o dispositivo de entrada**. Ao conectar um conjunto de fones de ouvido USB-C, os usuários observarão que o áudio do fone de ouvido será redirecionado automaticamente para os fones de ouvido, mas o SO do HoloLens prioriza a matriz de microfone interno acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

> [!NOTE]
> Microfones externos não podem ser usados em builds anteriores ao [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e superiores. 

Os usuários podem escolher microfones externos conectados por USB-C usando o painel de configurações de **Som**. Os microfones USB-C podem ser usados para fazer chamadas, gravar etc.

Abra o aplicativo **Configurações** e escolha **Sistema** > **Som**.

![Configurações de Som.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com o **Remote Assist**, os usuários precisarão clicar no hiperlink "Gerenciar dispositivos de som".
>
> Em seguida, use o menu suspenso para definir o microfone externo como **Padrão** ou **Padrão de Comunicações**. Escolher **Padrão** significa que o microfone externo será usado em todos os lugares.
>
> Escolher **Padrão de Comunicações** significa que o microfone externo será usado no Remote Assist e em outros aplicativos de comunicação, mas a matriz de microfones do HoloLens ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som.](images/usbc-mic-2.png)

<br>

![Definir o padrão do microfone.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E quanto ao suporte para microfone Bluetooth?

Infelizmente, o Bluetooth ainda não oferece suporte para microfones no HoloLens 2.

### <a name="usb-c-hubs"></a>Hubs USB-C

Alguns usuários podem precisar conectar vários dispositivos ao mesmo tempo. Para usuários que desejam usar um [microfone USB-C](#usb-c-external-microphone-support) com outro dispositivo conectado, os hubs USB-C podem atender à necessidade do cliente. A Microsoft não testou esses dispositivos, nem podemos recomendar nenhuma marca específica.

**Requisitos para hub USB-C e dispositivos conectados:**

- Os dispositivos conectados não devem exigir a instalação de um driver.
- O consumo total de energia de todos os dispositivos conectados deve ser inferior a 4,5 Watts.

## <a name="connect-to-miracast"></a>Conectar a Miracast

Para usar o Miracast, siga estas etapas:

1. Realize um dos seguintes procedimentos:  

   - Abra o menu **Iniciar** e escolha o ícone **Exibir**.
   - Diga "Conectar" enquanto foca o menu **Iniciar**.  

1. Na lista de dispositivos exibida, escolha um dispositivo disponível.

1. Concluir o emparelhamento para começar a projetar.
