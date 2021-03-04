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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385487"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Conectar-se a dispositivos Bluetooth e USB-C

> [!NOTE]
> Microfones externos não podem ser usados. O HoloLens 2 usa a[Matriz do microfone](hololens2-hardware.md#audio-and-speech) interno.

## <a name="pair-bluetooth-devices"></a>Emparelhar dispositivos Bluetooth

O HoloLens 2 tem suporte para as seguintes classes de dispositivos Bluetooth:

- Mouse
- Teclado
- Dispositivos de saída de áudio Bluetooth (A2DP)

O HoloLens 2 (1° gen) tem suporte para as seguintes classes de dispositivos Bluetooth:

- Mouse
- Teclado
- [Usar o clicador do HoloLens (1ª gen)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Outros tipos de dispositivos Bluetooth, como alto-falantes, fones de ouvido, smartphones e game pads, podem estar listados como disponíveis nas configurações do HoloLens. No entanto, esses dispositivos não têm suporte no HoloLens (1ª gen). Para saber mais, confira [Configurações do HoloLens lista dispositivos como disponíveis, mas os dispositivos não funcionam](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Emparelhar um teclado ou mouse Bluetooth

1. Ligue o teclado ou o mouse e torne-o localizável. Para saber como tornar o dispositivo localizável, procure por informações sobre o dispositivo (ou sua documentação) ou visite o site do fabricante.

1. Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida, selecione **Configurações**.

1. Selecione **Dispositivos**, e verifique se o Bluetooth está ativado.  

1. Quando vir o nome do dispositivo, selecione **Emparelhar** e siga as instruções.

## <a name="disable-bluetooth"></a>Bluetooth desabilitado

Esse procedimento desativa os componentes RF do rádio Bluetooth e desabilita toda a funcionalidade Bluetooth no Microsoft HoloLens.

1. Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida slecione **Configurações** > **de dispositivos**.

1. Mova o controle deslizante para **Bluetooth** para a posição **Desativada**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: conectar dispositivos USB-C

O HoloLens 2 tem suporte para as seguintes classes de dispositivos USB-C:

- Dispositivos de armazenamento em massa (como unidades Thumb)
- Adaptadores de Ethernet (incluindo carregamento plus de Ethernet)
- Adaptadores de áudio digital USB-C a 3,5 mm
- Fones de ouvido digital USB-C (incluindo os adaptadores de carregamento plus do headset)
- Mouse com fio
- Teclado com fio
- Hubs PD combinados ( carregamento USB A + PD)

> [!NOTE]
> Em resposta aos comentários do cliente, habilitamos o suporte limitado para conectividade celular diretamente ao HoloLens via USB-C. Confira [Conectar-se ao Celular e 5G](hololens-cellular.md) para obter mais informações.

### <a name="usb-c-hubs"></a>Hubs USB-C

Alguns usuários podem precisar conectar vários dispositivos ao mesmo tempo. Para usuários que desejam uma prévia do recurso Insider e [usar um microfone USB-C](hololens-insider.md#usb-c-external-microphone-support) junto com outro dispositivo conectado, os hubs USB-C podem atender às necessidades do cliente. A Microsoft não testou esses dispositivos, nem podemos recomendar nenhuma marca específica.

**Requisitos para hub USB-C e dispositivos conectados:**

- Os dispositivos conectados não devem exigir a instalação de um driver.
- O consumo total de energia de todos os dispositivos conectados deve ser inferior a 4,5 Watts.

## <a name="connect-to-miracast"></a>Conectar a Miracast

Para usar o Miracast, siga estas etapas:

1. Siga um destes procedimentos:  

   - Abra o menu **Iniciar** e selecione o ícone exibição.
   - Diga "conectar" enquanto mira ao menu **Iniciar**.  

1. Na lista de dispositivos exibida, selecione um dispositivo disponível.

1. Concluir o emparelhamento para começar a projetar.
