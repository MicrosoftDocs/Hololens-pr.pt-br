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
ms.openlocfilehash: afbcfd0762bea9e7a6bc217d5e4a2910eaab7359
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283342"
---
# Conectar-se a dispositivos Bluetooth e USB-C

> [!NOTE]
> Microfones externos não podem ser usados. O HoloLens 2 usa a[Matriz do microfone](hololens2-hardware.md#audio-and-speech) interno.

## Emparelhar dispositivos Bluetooth

O HoloLens 2 tem suporte para as seguintes classes de dispositivos Bluetooth:

- Mouse
- Teclado
- Dispositivos de saída de áudio Bluetooth (A2DP)

O HoloLens 2 (1° gen) tem suporte para as seguintes classes de dispositivos Bluetooth:

- Mouse
- Teclado
- Usar o clicador do HoloLens (1ª gen)

> [!NOTE]
> Outros tipos de dispositivos Bluetooth, como alto-falantes, fones de ouvido, smartphones e game pads, podem estar listados como disponíveis nas configurações do HoloLens. No entanto, esses dispositivos não têm suporte no HoloLens (1ª gen). Para saber mais, confira [Configurações do HoloLens lista dispositivos como disponíveis, mas os dispositivos não funcionam](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### Emparelhar um teclado ou mouse Bluetooth

1. Ligue o teclado ou o mouse e torne-o localizável. Para saber como tornar o dispositivo localizável, procure por informações sobre o dispositivo (ou sua documentação) ou visite o site do fabricante.

1. Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida, selecione **Configurações**.

1. Selecione **Dispositivos**, e verifique se o Bluetooth está ativado.  

1. Quando vir o nome do dispositivo, selecione **Emparelhar**e siga as instruções.

### HoloLens (1º gen): Emparelhe o clicador

1. Use o gesto de abrir a mão para ir para **Iniciar** e, em seguida, selecione **Configurações**.

1. Selecione **Dispositivos**, e verifique se o Bluetooth está ativado.

1. Use a ponta de uma caneta para pressionar e segurar o botão de emparelhamento do clicador até que o sinal luminoso de status do clicador piscar. Mantenha pressionado o botão até que a luz comece a piscar.  

   O botão de emparelhamento fica na parte inferior do clicador, ao lado do loop Finger.
   
   ![O botão de emparelhamento está ao lado do loop Finger](images/use-hololens-clicker-1.png)
   
1. Na tela emparelhamento, marque **Emparelhamento** > **do Clicador**.

## Bluetooth desabilitado

Esse procedimento desativa os componentes RF do rádio Bluetooth e desabilita toda a funcionalidade Bluetooth no Microsoft HoloLens.

1. Use o gesto de abrir a mão (HoloLens (1º gen)) ou o gesto de início (HoloLens 2) para ir até **Iniciar**e, em seguida slecione **Configurações** > **de dispositivos**.

1. Mova o controle deslizante para **Bluetooth** para a posição **Desativada**.

## HoloLens 2: conectar dispositivos USB-C

O HoloLens 2 tem suporte para as seguintes classes de dispositivos USB-C:

- Dispositivos de armazenamento em massa (como unidades Thumb)
- Adaptadores de Ethernet (incluindo carregamento plus de Ethernet)
- Adaptadores de áudio digital USB-C a 3,5 mm
- Fones de ouvido digital USB-C (incluindo os adaptadores de carregamento plus do headset)
- Mouse com fio
- Teclado com fio
- Hubs PD de combinação (USB A, carregamento plus de PD)

> [!NOTE]
> Alguns dispositivos móveis com conexões USB-C se apresentam ao HoloLens como adaptadores de Ethernet, portanto, podem ser usados em uma configuração de compartilhamento de Internet, começando com o Windows Holographic, versão 2004. Os modems USB LTE que exigem um driver separado e/ou aplicativo instalado para sua configuração não têm suporte.

Em resposta a comentários de clientes, habilitamos um suporte limitado para conectividade de rede celular, que pode ser acessado diretamente no HoloLens via USB-C.  A conectividade de compartilhamento só funciona para dispositivos que oferecem suporte à implementação genérica do driver [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) do Microsoft e que não exigem nenhum driver ou instalação do aplicativo.  Esse dispositivo, quando conectado, será exibido automaticamente como uma nova conexão Ethernet na interface de usuário das configurações de rede do HoloLens 2. Consulte o fabricante do seu dispositivo para obter mais detalhes sobre o suporte ao driver genérico RNDIS do Microsoft.

## Conectar a Miracast

Para usar o Miracast, siga estas etapas:

1. Siga um destes procedimentos:  

   - Abra o menu **Iniciar** e selecione o ícone exibição.
   - Diga "conectar" enquanto mira ao menu **Iniciar**.  

1. Na lista de dispositivos exibida, selecione um dispositivo disponível.

1. Concluir o emparelhamento para começar a projetar.
