---
title: Cenários comuns de implantação de infraestrutura
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857859"
---
# <span data-ttu-id="2ad3a-103">Cenários comuns de implantação de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="2ad3a-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="2ad3a-104">Essas informações a seguir fornecem uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 na empresa.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="2ad3a-105">Cenários</span><span class="sxs-lookup"><span data-stu-id="2ad3a-105">Scenarios</span></span>

<span data-ttu-id="2ad3a-106">O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![possíveis](images/scenarios.jpg)

### <span data-ttu-id="2ad3a-108">Cenário A</span><span class="sxs-lookup"><span data-stu-id="2ad3a-108">Scenario A</span></span>

<span data-ttu-id="2ad3a-109">O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="2ad3a-110">Os recursos corporativos não são acessados ou podem ser limitados pela VPN.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="2ad3a-111">Isso é uma implantação muito semelhante a dispositivos móveis gerenciados dentro de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="2ad3a-112">Configurações básicas básicas</span><span class="sxs-lookup"><span data-stu-id="2ad3a-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="2ad3a-113">Geralmente, as redes Wi-Fi são totalmente abertas para a Internet e os serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="2ad3a-114">Ingressar no Azure AD com o registro automático do MDM--gerenciamento de MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="2ad3a-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="2ad3a-115">Os usuários entram com sua própria conta corporativa (AAD)</span><span class="sxs-lookup"><span data-stu-id="2ad3a-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="2ad3a-116">Suporte para um ou vários usuários por dispositivo</span><span class="sxs-lookup"><span data-stu-id="2ad3a-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="2ad3a-117">Os níveis variáveis das configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, de totalmente abertos para o quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="2ad3a-118">Um ou mais aplicativos são implantados via MDM</span><span class="sxs-lookup"><span data-stu-id="2ad3a-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="2ad3a-119">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="2ad3a-119">Common Challenges</span></span>
   * <span data-ttu-id="2ad3a-120">Determinar quais configurações do MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="2ad3a-121">Cenário B</span><span class="sxs-lookup"><span data-stu-id="2ad3a-121">Scenario B</span></span>

<span data-ttu-id="2ad3a-122">O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="2ad3a-123">Os serviços de nuvem e Internet podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="2ad3a-124">Esta é uma implantação típica para a maioria dos computadores com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="2ad3a-125">Configurações básicas básicas</span><span class="sxs-lookup"><span data-stu-id="2ad3a-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="2ad3a-126">A rede Wi-Fi é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="2ad3a-127">Ingressar no Azure AD com o registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="2ad3a-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="2ad3a-128">Gerenciamento de MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="2ad3a-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="2ad3a-129">Os usuários entram com sua própria conta corporativa (AAD)</span><span class="sxs-lookup"><span data-stu-id="2ad3a-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="2ad3a-130">Suporte para um ou vários usuários por dispositivo</span><span class="sxs-lookup"><span data-stu-id="2ad3a-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="2ad3a-131">Os níveis variáveis das configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, de totalmente abertos para o quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="2ad3a-132">Um ou mais aplicativos são implantados via MDM</span><span class="sxs-lookup"><span data-stu-id="2ad3a-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="2ad3a-133">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="2ad3a-133">Common Challenges</span></span>
   * <span data-ttu-id="2ad3a-134">O HoloLens 2 não é compatível com o ingresso no AD local ou SCCM.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="2ad3a-135">Somente ingresso do Azure AD com MDM.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="2ad3a-136">Hoje em dia, muitas empresas ainda implantam computadores Windows 10 nesse cenário, como os dispositivos ingressados no AD, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções MDM baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="2ad3a-137">Como o HoloLens 2 é um dispositivo de nuvem, ele depende muito de serviços conectados à Internet e na nuvem para autenticação de usuários, atualizações de so, gerenciamento de MDM, etc. Ao conectar-se a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para permitir o acesso para o HoloLens 2 e os aplicativos que são executados nele.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="2ad3a-138">Geralmente, a conectividade Wi-Fi corporativa requer certificados para autenticar o dispositivo ou o usuário na rede.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="2ad3a-139">A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio de MDM podem ser difíceis de configurar.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="2ad3a-140">Cenário C</span><span class="sxs-lookup"><span data-stu-id="2ad3a-140">Scenario C</span></span>

<span data-ttu-id="2ad3a-141">O HoloLens 2 é implantado para ser usado principalmente offline sem acesso à Internet ou à rede.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="2ad3a-142">Esta é uma implantação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="2ad3a-143">Configurações básicas básicas</span><span class="sxs-lookup"><span data-stu-id="2ad3a-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="2ad3a-144">A conectividade de Wi-Fi está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="2ad3a-145">A Ethernet via USB pode estar ativada para conectividade de LAN, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="2ad3a-146">Não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-146">Not Managed.</span></span>
   * <span data-ttu-id="2ad3a-147">Conta de usuário local para entrada de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="2ad3a-148">O HoloLens 2 oferece suporte a apenas 1 conta local.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="2ad3a-149">Os níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de pacotes de provisionamento com base em casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="2ad3a-150">Essas configurações geralmente são muito restritas devido a requisitos de ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="2ad3a-151">Um ou mais aplicativos são implantados por meio do pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="2ad3a-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="2ad3a-152">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="2ad3a-152">Common Challenges</span></span>
   * <span data-ttu-id="2ad3a-153">Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="2ad3a-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="2ad3a-154">Os serviços de nuvem não podem ser aproveitados, portanto limitando os recursos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="2ad3a-155">Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="2ad3a-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
