---
title: Cenários comuns de implantação de infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em implantações de infraestrutura diferentes para realidade misturada.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308133"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="ff036-104">Visão geral dos cenários comuns de implantação de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="ff036-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="ff036-105">Essas informações a seguir fornecem uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="ff036-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="ff036-106">Geralmente, a maneira como você gerencia seus dispositivos e como acessar os recursos de sua organização é basicamente determinado por fatores já estabelecidos.</span><span class="sxs-lookup"><span data-stu-id="ff036-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="ff036-107">Com base na infraestrutura existente, convidamos você a examinar o estilo comum de gerenciamento de dispositivos nos cenários a seguir e experimentar nossos guias para a implantação no cenário que atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="ff036-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="ff036-108">Cenários</span><span class="sxs-lookup"><span data-stu-id="ff036-108">Scenarios</span></span>

<span data-ttu-id="ff036-109">O diagrama a seguir representa três cenários típicos para implantações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ff036-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
<span data-ttu-id="ff036-110">![Diagrama de cenários](images/scenarios.jpg)</span><span class="sxs-lookup"><span data-stu-id="ff036-110">![Scenarios diagram](images/scenarios.jpg)</span></span>

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="ff036-111">Cenário A: implantar em dispositivos do Cloud Connect</span><span class="sxs-lookup"><span data-stu-id="ff036-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="ff036-112">O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="ff036-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="ff036-113">Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN.</span><span class="sxs-lookup"><span data-stu-id="ff036-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="ff036-114">Essa implantação é semelhante a dispositivos móveis gerenciados dentro de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="ff036-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="ff036-115">Configurações básicas comuns</span><span class="sxs-lookup"><span data-stu-id="ff036-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="ff036-116">As redes Wi-Fi normalmente são totalmente abertas na Internet e nos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="ff036-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="ff036-117">Ingresso no Azure AD com o registro automático de MDM (gerenciamento de dispositivo móvel)--MDM (Intune) gerenciado</span><span class="sxs-lookup"><span data-stu-id="ff036-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="ff036-118">Os usuários entram com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ff036-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="ff036-119">Um ou vários usuários por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="ff036-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="ff036-120">Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente abertas para quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="ff036-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="ff036-121">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="ff036-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="ff036-122">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="ff036-122">Common Challenges</span></span>
   * <span data-ttu-id="ff036-123">Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.</span><span class="sxs-lookup"><span data-stu-id="ff036-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="ff036-124">Para obter um guia de implantação semelhante ao cenário A, examine nosso guia para a [nuvem conectada no HoloLens 2 com o auxílio remoto](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ff036-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ff036-125">Guia de implantação – nuvem conectada no Cloud 2 com assistência remota</span><span class="sxs-lookup"><span data-stu-id="ff036-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="ff036-126">Cenário B: implantar dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="ff036-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="ff036-127">O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="ff036-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="ff036-128">Serviços de nuvem e Internet podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="ff036-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="ff036-129">Essa implantação é uma implantação típica para a maioria dos PCs com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ff036-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="ff036-130">Configurações básicas comuns</span><span class="sxs-lookup"><span data-stu-id="ff036-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="ff036-131">Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="ff036-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="ff036-132">Ingresso no Azure AD com o registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="ff036-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="ff036-133">MDM (Intune) gerenciado</span><span class="sxs-lookup"><span data-stu-id="ff036-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="ff036-134">Os usuários entram com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ff036-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="ff036-135">Um ou vários usuários por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="ff036-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="ff036-136">Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente abertas para quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="ff036-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="ff036-137">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="ff036-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="ff036-138">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="ff036-138">Common Challenges</span></span>
   * <span data-ttu-id="ff036-139">O HoloLens 2 não dá suporte ao ingresso no AD local ou ao SCCM.</span><span class="sxs-lookup"><span data-stu-id="ff036-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="ff036-140">Somente ingresso no Azure AD com o MDM.</span><span class="sxs-lookup"><span data-stu-id="ff036-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="ff036-141">Hoje em dia, muitas empresas ainda implantam PCs com Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções de MDM baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="ff036-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="ff036-142">Como o HoloLens 2 é um dispositivo de nuvem primeiro, ele depende muito da Internet e dos serviços conectados na nuvem para autenticação do usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="ff036-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="ff036-143">Ao se conectar a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para habilitar o acesso para o HoloLens 2 e os aplicativos executados nele.</span><span class="sxs-lookup"><span data-stu-id="ff036-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="ff036-144">A conectividade de Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o usuário na rede.</span><span class="sxs-lookup"><span data-stu-id="ff036-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="ff036-145">A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio do MDM podem ser difíceis de configurar.</span><span class="sxs-lookup"><span data-stu-id="ff036-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ff036-146">Guia de implantação – o HoloLens 2 conectado à empresa com guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ff036-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="ff036-147">Cenário C: implantar em ambiente offline seguro</span><span class="sxs-lookup"><span data-stu-id="ff036-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="ff036-148">O HoloLens 2 é implantado para uso principalmente offline, sem acesso à rede ou à Internet.</span><span class="sxs-lookup"><span data-stu-id="ff036-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="ff036-149">Essa é uma implantação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="ff036-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="ff036-150">Configurações básicas comuns</span><span class="sxs-lookup"><span data-stu-id="ff036-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="ff036-151">A conectividade do Wi-Fi está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="ff036-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="ff036-152">A Ethernet via USB pode estar habilitada para conectividade de LAN, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ff036-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="ff036-153">Não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ff036-153">Not Managed.</span></span>
   * <span data-ttu-id="ff036-154">Conta de usuário local para entrada do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff036-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="ff036-155">O HoloLens 2 dá suporte a apenas uma conta local.</span><span class="sxs-lookup"><span data-stu-id="ff036-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="ff036-156">Níveis variados de configurações de bloqueio de dispositivo são aplicadas por meio de pacotes de provisionamento com base em casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="ff036-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="ff036-157">Essas configurações normalmente são restritas devido a requisitos de ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="ff036-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="ff036-158">Um ou mais aplicativos são implantados por meio do pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="ff036-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="ff036-159">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="ff036-159">Common Challenges</span></span>
   * <span data-ttu-id="ff036-160">Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="ff036-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="ff036-161">Os serviços de nuvem não podem ser usados, portanto limitando os recursos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ff036-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="ff036-162">Maior sobrecarga administrativa, uma vez que esses dispositivos precisam ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="ff036-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="ff036-163">Para obter um guia de implantação semelhante a este cenário, examine nosso [Guia de implantação seguro offline](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="ff036-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ff036-164">Guia de implantação – HoloLens seguro offline 2</span><span class="sxs-lookup"><span data-stu-id="ff036-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
