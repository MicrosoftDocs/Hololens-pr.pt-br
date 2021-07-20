---
title: Conectar-se ao Celular e 5G
description: Conectando-se a redes celulares de seus dispositivos de realidade misturada do HoloLens.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635833"
---
# <a name="connect-to-cellular-and-5g"></a>Conectar-se ao Celular e 5G

O HoloLens 2 oferece suporte a dois métodos de conexão a redes celulares e 5G:

- Uma rede Wi-Fi ad hoc fornecida pelo dispositivo celular, comumente chamada de "Hotspot"
- Suporte limitado para dispositivos conectados por USB-C

## <a name="hotspot-wifi"></a>Hotspot (Wi-Fi)

A maioria das necessidades de conectividade do celular pode ser atendida com um hotspot. O HoloLens 2 WiFi oferece suporte a 802.11ac, que pode fornecer os requisitos de largura de banda e latência necessários para a maioria dos casos de uso comuns. O Wi-Fi é sem cabo e oferece compatibilidade com o maior número de dispositivos celulares.

### <a name="connecting-to-a-hotspot"></a>Conectar-se a um hotspot

1. Consulte o manual do seu dispositivo para saber como habilitar o modo hotspot.
1. Habilite o modo hotspot, fornecendo um nome para a rede, bem como uma senha conhecida.
1. Nas configurações de rede do HoloLens 2, localize a rede Wi-Fi criada na etapa 2 e entre nela.

## <a name="usb-c-tethering"></a>USB-C Tethering

O USB-C tethering pode fornecer latência mais baixa para cargas de trabalho avançadas que precisam dele. O [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), por exemplo, pode se beneficiar do tethering. Observe que o tethering requer um cabo entre o dispositivo celular e o HoloLens, e o tethering é compatível com um número limitado de dispositivos.

### <a name="usb-c-compatibility"></a>Compatibilidade USB-C

Um número limitado de dispositivos que apresentam um adaptador ethernet podem ser usados com o Windows Holographic versão 2004 e posterior.

Os dispositivos que não apresentam um adaptador ethernet devem ser compatíveis com o driver genérico [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) da Microsoft. No entanto, apenas um número limitado desses dispositivos é compatível com o HoloLens 2. Consulte o fabricante do seu dispositivo para obter detalhes sobre se ele é compatível com o driver genérico RNDIS da Microsoft.

Dispositivos que não são compatíveis com o RNDIS ou que exigem a instalação de um driver ou aplicativo não são compatíveis.

Embora a Microsoft não mantenha uma lista de dispositivos compatíveis, há uma discussão na comunidade sobre o assunto [aqui](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Conectar-se a um dispositivo conectado por tethering

1. Consulte o manual do seu dispositivo sobre como habilitar o compartilhamento de dados por USB. Essa configuração é frequentemente referida como "USB tethering", "Compartilhamento de dados" ou "Modem USB".
1. Habilite o compartilhamento de dados por USB.
1. Conecte seu dispositivo à porta USB-C do HoloLens.
1. Nas configurações de rede do HoloLens 2, o dispositivo aparecerá automaticamente como uma conexão Ethernet.
