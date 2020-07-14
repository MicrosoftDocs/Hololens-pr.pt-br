---
title: Redes sem fio e Wi-Fi
description: Redes sem fio e Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, sem fio, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865641"
---
# <span data-ttu-id="ca728-104">Redes sem fio e Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ca728-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="ca728-105">A conectividade de LAN sem fio do HoloLens 2 oferece suporte a um grande número de padrões de segurança Wi-Fi mais recentes, como:</span><span class="sxs-lookup"><span data-stu-id="ca728-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="ca728-106">WPA2 (Wi-Fi Protected Access 2)</span><span class="sxs-lookup"><span data-stu-id="ca728-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="ca728-107">Protocolo TEAP (Tunnel Extensible Authentication Protocol)</span><span class="sxs-lookup"><span data-stu-id="ca728-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="ca728-108">OWE (Opportunistic Wireless Encryption)</span><span class="sxs-lookup"><span data-stu-id="ca728-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="ca728-109">TEAP, a próxima geração de autenticação de rede corporativa, proporciona a habilidade de encadear várias credenciais com segurança em uma única transação.</span><span class="sxs-lookup"><span data-stu-id="ca728-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="ca728-110">Isso permite aos administradores reforçarem uma melhor postura de segurança, que exige identidades válidas para o computador e o usuário durante a mesma transação de autenticação.</span><span class="sxs-lookup"><span data-stu-id="ca728-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="ca728-111">O HoloLens 2 tem protocolos modernos sem fio e Wi-Fi que permitem aos clientes o suporte máximo.</span><span class="sxs-lookup"><span data-stu-id="ca728-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="ca728-112">O rádio do HoloLens 2 é uma solução Qualcomm WCN3990 oferecendo uma experiência de rádio premium.</span><span class="sxs-lookup"><span data-stu-id="ca728-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="ca728-113">O Wi-Fi compatível é 802.11 ac/n.</span><span class="sxs-lookup"><span data-stu-id="ca728-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="ca728-114">A faixa de frequência não é configurável pelo usuário e depende do país de uso.</span><span class="sxs-lookup"><span data-stu-id="ca728-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="ca728-115">Nos Estados Unidos, o Wi-Fi usa canais de 2.4 GHz (1-11) e canais de 5 GHz (36-64, 100-165).</span><span class="sxs-lookup"><span data-stu-id="ca728-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="ca728-116">Nem os usuários nem os dispositivos podem fazer listas de permitir/negar para frequências específicas.</span><span class="sxs-lookup"><span data-stu-id="ca728-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="ca728-117">O Bluetooth SIC Core 5.0 tem uma antena dedicada de 2.4 GHz para Bluetooth que não é compartilhada com o Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="ca728-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="ca728-118">A pilha de software do HoloLens 2 aceita vários protocolos e perfis, como HID, HOGP, A2DP e GATT.</span><span class="sxs-lookup"><span data-stu-id="ca728-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="ca728-119">Os administradores de TI podem:</span><span class="sxs-lookup"><span data-stu-id="ca728-119">IT admins can:</span></span> 
  * <span data-ttu-id="ca728-120">Habilitar ou restringir o [acesso Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span><span class="sxs-lookup"><span data-stu-id="ca728-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="ca728-121">Definir [ Nomes de dispositivos Bluetooth locais](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span><span class="sxs-lookup"><span data-stu-id="ca728-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="ca728-122">Permitir que [dispositivos sejam detectáveis](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span><span class="sxs-lookup"><span data-stu-id="ca728-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="ca728-123">Permite/revogar permissão de [conexões Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span><span class="sxs-lookup"><span data-stu-id="ca728-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="ca728-124">Permite ou revogar permissão à [conexão Wi-Fi fora das redes instaladas pelo servidor MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span><span class="sxs-lookup"><span data-stu-id="ca728-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
