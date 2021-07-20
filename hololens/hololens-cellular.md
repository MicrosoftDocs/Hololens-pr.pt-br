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
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="43fce-103">Conectar-se ao Celular e 5G</span><span class="sxs-lookup"><span data-stu-id="43fce-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="43fce-104">O HoloLens 2 oferece suporte a dois métodos de conexão a redes celulares e 5G:</span><span class="sxs-lookup"><span data-stu-id="43fce-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="43fce-105">Uma rede Wi-Fi ad hoc fornecida pelo dispositivo celular, comumente chamada de "Hotspot"</span><span class="sxs-lookup"><span data-stu-id="43fce-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="43fce-106">Suporte limitado para dispositivos conectados por USB-C</span><span class="sxs-lookup"><span data-stu-id="43fce-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="43fce-107">Hotspot (Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="43fce-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="43fce-108">A maioria das necessidades de conectividade do celular pode ser atendida com um hotspot.</span><span class="sxs-lookup"><span data-stu-id="43fce-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="43fce-109">O HoloLens 2 WiFi oferece suporte a 802.11ac, que pode fornecer os requisitos de largura de banda e latência necessários para a maioria dos casos de uso comuns.</span><span class="sxs-lookup"><span data-stu-id="43fce-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="43fce-110">O Wi-Fi é sem cabo e oferece compatibilidade com o maior número de dispositivos celulares.</span><span class="sxs-lookup"><span data-stu-id="43fce-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="43fce-111">Conectar-se a um hotspot</span><span class="sxs-lookup"><span data-stu-id="43fce-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="43fce-112">Consulte o manual do seu dispositivo para saber como habilitar o modo hotspot.</span><span class="sxs-lookup"><span data-stu-id="43fce-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="43fce-113">Habilite o modo hotspot, fornecendo um nome para a rede, bem como uma senha conhecida.</span><span class="sxs-lookup"><span data-stu-id="43fce-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="43fce-114">Nas configurações de rede do HoloLens 2, localize a rede Wi-Fi criada na etapa 2 e entre nela.</span><span class="sxs-lookup"><span data-stu-id="43fce-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="43fce-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="43fce-115">USB-C Tethering</span></span>

<span data-ttu-id="43fce-116">O USB-C tethering pode fornecer latência mais baixa para cargas de trabalho avançadas que precisam dele.</span><span class="sxs-lookup"><span data-stu-id="43fce-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="43fce-117">O [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), por exemplo, pode se beneficiar do tethering.</span><span class="sxs-lookup"><span data-stu-id="43fce-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="43fce-118">Observe que o tethering requer um cabo entre o dispositivo celular e o HoloLens, e o tethering é compatível com um número limitado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="43fce-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="43fce-119">Compatibilidade USB-C</span><span class="sxs-lookup"><span data-stu-id="43fce-119">USB-C compatibility</span></span>

<span data-ttu-id="43fce-120">Um número limitado de dispositivos que apresentam um adaptador ethernet podem ser usados com o Windows Holographic versão 2004 e posterior.</span><span class="sxs-lookup"><span data-stu-id="43fce-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="43fce-121">Os dispositivos que não apresentam um adaptador ethernet devem ser compatíveis com o driver genérico [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43fce-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="43fce-122">No entanto, apenas um número limitado desses dispositivos é compatível com o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="43fce-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="43fce-123">Consulte o fabricante do seu dispositivo para obter detalhes sobre se ele é compatível com o driver genérico RNDIS da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43fce-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="43fce-124">Dispositivos que não são compatíveis com o RNDIS ou que exigem a instalação de um driver ou aplicativo não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="43fce-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="43fce-125">Embora a Microsoft não mantenha uma lista de dispositivos compatíveis, há uma discussão na comunidade sobre o assunto [aqui](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="43fce-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="43fce-126">Conectar-se a um dispositivo conectado por tethering</span><span class="sxs-lookup"><span data-stu-id="43fce-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="43fce-127">Consulte o manual do seu dispositivo sobre como habilitar o compartilhamento de dados por USB.</span><span class="sxs-lookup"><span data-stu-id="43fce-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="43fce-128">Essa configuração é frequentemente referida como "USB tethering", "Compartilhamento de dados" ou "Modem USB".</span><span class="sxs-lookup"><span data-stu-id="43fce-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="43fce-129">Habilite o compartilhamento de dados por USB.</span><span class="sxs-lookup"><span data-stu-id="43fce-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="43fce-130">Conecte seu dispositivo à porta USB-C do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="43fce-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="43fce-131">Nas configurações de rede do HoloLens 2, o dispositivo aparecerá automaticamente como uma conexão Ethernet.</span><span class="sxs-lookup"><span data-stu-id="43fce-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
