---
title: Segurança de rede
description: segurança de rede
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, rede, segurança de rede
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009419"
---
# <span data-ttu-id="1c416-104">Segurança de rede</span><span class="sxs-lookup"><span data-stu-id="1c416-104">Network security</span></span>

## <span data-ttu-id="1c416-105">Protocolos de rede</span><span class="sxs-lookup"><span data-stu-id="1c416-105">Network protocols</span></span>

<span data-ttu-id="1c416-106">O NetBIOS (Network Basic Input/Output System) desatualizado era amplamente usado muitas vezes no passado em cenários de LAN – para fornecer resolução de nome para um computador e pastas compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="1c416-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="1c416-107">No entanto, com o tempo, o NetBIOS provou ser suscetível a vários ataques, e sua relevância diminuída em favor de outros protocolos mais seguros.</span><span class="sxs-lookup"><span data-stu-id="1c416-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="1c416-108">Para remover esse problema de vulnerabilidade, o HoloLens 2 eliminou o código relacionado a NetBIOS do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1c416-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="1c416-109">Os protocolos TLS (Transport Layer Security) estão sempre em constante evolução.</span><span class="sxs-lookup"><span data-stu-id="1c416-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="1c416-110">Para manter-se atualizada com as várias explorações de segurança que foram descobertas nesta área, a indústria de computação se evoluiu em versões mais recentes e mais eficazes.</span><span class="sxs-lookup"><span data-stu-id="1c416-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="1c416-111">Devido ao tempo necessário para que todas as implantações de servidor adotem as novas versões do protocolo TLS, é possível implementar um mecanismo de fallback que permite que clientes e servidores em diferentes versões padrão do protocolo ainda possam se comunicar durante o período de transição.</span><span class="sxs-lookup"><span data-stu-id="1c416-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <span data-ttu-id="1c416-112">Conectividade segura</span><span class="sxs-lookup"><span data-stu-id="1c416-112">Secure connectivity</span></span> 

<span data-ttu-id="1c416-113">O Windows Defender Firewall oferece funcionalidade fundamental para proteger a conectividade de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1c416-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="1c416-114">Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo programaticamente ou por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="1c416-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="1c416-115">A privacidade de acesso remoto e conexão para clientes com dispositivo móvel pode ser garantida pela [plataforma de plug-in VPN UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="1c416-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="1c416-116">Provedores de VPN de terceiros podem criar seus próprios plug-ins usando APIs do WinRT que vão rodar dentro da área restrita do AppContainer, eliminando a complexidade e os problemas geralmente associados com a escrita de drivers a nível de sistema.</span><span class="sxs-lookup"><span data-stu-id="1c416-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
