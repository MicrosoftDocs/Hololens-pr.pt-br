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
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385633"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="7c3c1-103">Conectar-se ao Celular e 5G</span><span class="sxs-lookup"><span data-stu-id="7c3c1-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="7c3c1-104">O HoloLens 2 oferece suporte a dois métodos de conexão a redes celulares e 5G:</span><span class="sxs-lookup"><span data-stu-id="7c3c1-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="7c3c1-105">Uma rede WiFi ad hoc fornecida pelo dispositivo celular, comumente chamada de "Hotspot"</span><span class="sxs-lookup"><span data-stu-id="7c3c1-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="7c3c1-106">Suporte limitado para dispositivos conectados por USB-C</span><span class="sxs-lookup"><span data-stu-id="7c3c1-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="7c3c1-107">Hotspot (WiFi)</span><span class="sxs-lookup"><span data-stu-id="7c3c1-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="7c3c1-108">A maioria das necessidades de conectividade do celular pode ser atendida com um hotspot.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="7c3c1-109">O HoloLens 2 WiFi oferece suporte a 802.11ac, que pode fornecer os requisitos de largura de banda e latência necessários para a maioria dos casos de uso comuns.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="7c3c1-110">O WiFi é sem cabo e oferece compatibilidade com o maior número de dispositivos celulares.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="7c3c1-111">Conectando-se a um hotspot</span><span class="sxs-lookup"><span data-stu-id="7c3c1-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="7c3c1-112">Consulte o manual do seu dispositivo para saber como habilitar o modo hotspot.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="7c3c1-113">Habilite o modo hotspot, fornecendo um nome para a rede, bem como uma senha conhecida.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="7c3c1-114">Nas configurações de rede do HoloLens 2, localize a rede WiFi criada na etapa 2 e entre nela.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="7c3c1-115">USB-C tethering</span><span class="sxs-lookup"><span data-stu-id="7c3c1-115">USB-C Tethering</span></span>

<span data-ttu-id="7c3c1-116">O USB-C tethering pode fornecer latência mais baixa para cargas de trabalho avançadas que precisam dele.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="7c3c1-117">O [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), por exemplo, pode se beneficiar do tethering.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="7c3c1-118">Observe que o tethering requer um cabo entre o dispositivo celular e o HoloLens, e o tethering é compatível com um número limitado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="7c3c1-119">Compatibilidade USB-C</span><span class="sxs-lookup"><span data-stu-id="7c3c1-119">USB-C compatibility</span></span>

<span data-ttu-id="7c3c1-120">Os dispositivos que apresentam um adaptador ethernet podem ser usados com o Windows Holographic versão 2004 e posterior.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="7c3c1-121">Os dispositivos que não apresentam um adaptador ethernet devem ser compatíveis com o driver genérico [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="7c3c1-122">Consulte o fabricante do seu dispositivo para obter detalhes sobre se ele é compatível com o driver genérico RNDIS da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="7c3c1-123">Dispositivos que não são compatíveis com o RNDIS ou que exigem a instalação de um driver ou aplicativo não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="7c3c1-124">Embora a Microsoft não mantenha uma lista de dispositivos compatíveis, há uma discussão na comunidade sobre o assunto [aqui](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="7c3c1-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="7c3c1-125">Conectando-se a um dispositivo conectado por tethering</span><span class="sxs-lookup"><span data-stu-id="7c3c1-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="7c3c1-126">Consulte o manual do seu dispositivo sobre como habilitar o compartilhamento de dados por USB.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="7c3c1-127">Essa configuração é frequentemente referida como "USB tethering", "Compartilhamento de dados" ou "Modem USB".</span><span class="sxs-lookup"><span data-stu-id="7c3c1-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="7c3c1-128">Habilite o compartilhamento de dados por USB.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="7c3c1-129">Conecte seu dispositivo à porta USB-C do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="7c3c1-130">Nas configurações de rede do HoloLens 2, o dispositivo aparecerá automaticamente como uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="7c3c1-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
