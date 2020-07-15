---
title: Segurança de rede
description: segurança de rede
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, rede, segurança de rede
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c88a9af7369a6a9d6fb115fb820c0a4da13eafdc
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865659"
---
# <span data-ttu-id="9cdb6-104">Segurança de rede</span><span class="sxs-lookup"><span data-stu-id="9cdb6-104">Network security</span></span>

## <span data-ttu-id="9cdb6-105">Protocolos de rede</span><span class="sxs-lookup"><span data-stu-id="9cdb6-105">Network protocols</span></span>

<span data-ttu-id="9cdb6-106">O NetBIOS (Network Basic Input/Output System) desatualizado era amplamente usado muitas vezes no passado em cenários de LAN – para fornecer resolução de nome para um computador e pastas compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="9cdb6-107">No entanto, com o tempo, o NetBIOS provou ser suscetível a vários ataques, e sua relevância diminuída em favor de outros protocolos mais seguros.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="9cdb6-108">Para remover esse problema de vulnerabilidade, o HoloLens 2 eliminou o código relacionado a NetBIOS do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="9cdb6-109">Os protocolos TLS (Transport Layer Security) estão sempre em constante evolução.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="9cdb6-110">Para manter-se atualizada com as várias explorações de segurança que foram descobertas nesta área, a indústria de computação se evoluiu em versões mais recentes e mais eficazes.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="9cdb6-111">Devido ao tempo necessário para que todas as implantações de servidor adotem as novas versões do protocolo TLS, é possível implementar um mecanismo de fallback que permite que clientes e servidores em diferentes versões padrão do protocolo ainda possam se comunicar durante o período de transição.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

<span data-ttu-id="9cdb6-112">No entanto, esses mecanismos de fallback aumentam os riscos à segurança.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-112">However, such fallback mechanisms increase security risks.</span></span> <span data-ttu-id="9cdb6-113">Entendendo esse problema, no HoloLens 2, o fallback do TLS 1.2 até TLS 1.1 ou 1.0 foi desabilitado e não há nenhuma interface de usuário para habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-113">Understanding this issue, in HoloLens 2 the fallback from TLS 1.2 to TLS 1.1 or 1.0 has been disabled, and there is no user interface to enable it.</span></span> <span data-ttu-id="9cdb6-114">Além disso, durante o método de handshake do TLS, o cliente solicitará o TLS 1.2 e não permitirá que o servidor faça o downgrade para uma versão mais baixa.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-114">Furthermore, during the TLS handshake, the client will ask for TLS 1.2, and does not allow the server to downgrade to a lower version.</span></span>

## <span data-ttu-id="9cdb6-115">Conectividade segura</span><span class="sxs-lookup"><span data-stu-id="9cdb6-115">Secure connectivity</span></span> 

<span data-ttu-id="9cdb6-116">O Windows Defender Firewall oferece funcionalidade fundamental para proteger a conectividade de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-116">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="9cdb6-117">Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo programaticamente ou por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-117">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="9cdb6-118">A privacidade de acesso remoto e conexão para clientes com dispositivo móvel pode ser garantida pela [plataforma de plug-in VPN UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="9cdb6-118">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="9cdb6-119">Provedores de VPN de terceiros podem criar seus próprios plug-ins usando APIs do WinRT que vão rodar dentro da área restrita do AppContainer, eliminando a complexidade e os problemas geralmente associados com a escrita de drivers a nível de sistema.</span><span class="sxs-lookup"><span data-stu-id="9cdb6-119">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
