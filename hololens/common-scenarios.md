---
title: Cenários comuns de implantação de infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em diferentes implantações de infraestrutura para realidade misturada.
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397407"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="d4f6c-104">Visão geral de cenários comuns de implantação de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="d4f6c-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="d4f6c-105">Essas informações a seguir fornece uma visão geral da arquitetura de alto nível para três cenários comuns ao implantar e gerenciar Microsoft HoloLens 2 dispositivos dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="d4f6c-106">Geralmente, a maneira como você gerencia seus dispositivos e como acessar os recursos da sua organização é determinada em grande parte pelos fatores já em uso.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="d4f6c-107">Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivo comum nos cenários a seguir e experimentar nossos guias para implantação no cenário que corresponde às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d4f6c-108">Cenários</span><span class="sxs-lookup"><span data-stu-id="d4f6c-108">Scenarios</span></span>

<span data-ttu-id="d4f6c-109">O diagrama a seguir representa dois cenários gerenciados típicos para implantações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="d4f6c-110">Também há um terceiro cenário que permite implantações seguras offline.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="d4f6c-111">Cenário A: Implantar em dispositivos conectados à nuvem</span><span class="sxs-lookup"><span data-stu-id="d4f6c-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="d4f6c-112">O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="d4f6c-113">Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="d4f6c-114">Essa implantação é semelhante a dispositivos móveis gerenciados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="d4f6c-115">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="d4f6c-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="d4f6c-116">Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e Nuvem.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="d4f6c-117">Ingressar no Azure AD com o registro automático do MDM (Mobile Gerenciamento de Dispositivos) – MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="d4f6c-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d4f6c-118">Os usuários entrarão com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d4f6c-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d4f6c-119">Usuários individuais ou múltiplos por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="d4f6c-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d4f6c-120">Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d4f6c-121">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="d4f6c-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="d4f6c-122">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="d4f6c-122">Common Challenges</span></span>
   * <span data-ttu-id="d4f6c-123">Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="d4f6c-124">[![Cenário de um diagrama ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d4f6c-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="d4f6c-125">Para obter um guia de implantação semelhante a este cenário, consulte o [Guia de implantação do ambiente conectado à nuvem](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d4f6c-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d4f6c-126">Guia de implantação do ambiente conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="d4f6c-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="d4f6c-127">Guia de implantação do ambiente conectado à nuvem (clientes externos)</span><span class="sxs-lookup"><span data-stu-id="d4f6c-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="d4f6c-128">Cenário B: implantar dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="d4f6c-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="d4f6c-129">O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="d4f6c-130">Serviços de nuvem e Internet podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="d4f6c-131">Essa implantação é uma implantação típica para a maioria dos PCs com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="d4f6c-132">Configurações básicas comuns</span><span class="sxs-lookup"><span data-stu-id="d4f6c-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="d4f6c-133">Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="d4f6c-134">Ingresso no Azure AD com o registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="d4f6c-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="d4f6c-135">MDM (Intune) gerenciado</span><span class="sxs-lookup"><span data-stu-id="d4f6c-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d4f6c-136">Os usuários entram com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d4f6c-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d4f6c-137">Um ou vários usuários por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="d4f6c-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d4f6c-138">Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente abertas para quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d4f6c-139">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="d4f6c-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="d4f6c-140">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="d4f6c-140">Common Challenges</span></span>
   * <span data-ttu-id="d4f6c-141">O HoloLens 2 não dá suporte ao ingresso no AD local ou ao SCCM.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="d4f6c-142">Somente ingresso no Azure AD com o MDM.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="d4f6c-143">Hoje em dia, muitas empresas ainda implantam PCs com Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções de MDM baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="d4f6c-144">Como o HoloLens 2 é um dispositivo de nuvem primeiro, ele depende muito da Internet e dos serviços conectados na nuvem para autenticação do usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="d4f6c-145">Ao se conectar a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para habilitar o acesso para o HoloLens 2 e os aplicativos executados nele.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="d4f6c-146">A conectividade de Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o usuário na rede.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="d4f6c-147">A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio do MDM podem ser difíceis de configurar.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="d4f6c-148">[![Diagrama ](images/deployment-guides-revised-scenario-b-01-1.png) do cenário B1](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d4f6c-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="d4f6c-149">[![Diagrama ](images/deployment-guides-revised-scenario-b-02-1.png) de cenário B2](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d4f6c-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="d4f6c-150">Para obter um guia de implantação semelhante a este cenário, consulte nosso guia para o [Guia de implantação de rede corporativa](hololens2-corp-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d4f6c-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d4f6c-151">Guia de implantação de rede corporativa</span><span class="sxs-lookup"><span data-stu-id="d4f6c-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="d4f6c-152">Cenário C: implantar em ambiente offline seguro</span><span class="sxs-lookup"><span data-stu-id="d4f6c-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="d4f6c-153">O HoloLens 2 é implantado para uso principalmente offline, sem acesso à rede ou à Internet.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="d4f6c-154">Essa é uma implantação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="d4f6c-155">Configurações básicas comuns</span><span class="sxs-lookup"><span data-stu-id="d4f6c-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="d4f6c-156">A conectividade do Wi-Fi está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="d4f6c-157">A Ethernet via USB pode estar habilitada para conectividade de LAN, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="d4f6c-158">Não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-158">Not Managed.</span></span>
   * <span data-ttu-id="d4f6c-159">Conta de usuário local para entrada do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="d4f6c-160">O HoloLens 2 dá suporte a apenas uma conta local.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="d4f6c-161">Níveis variados de configurações de bloqueio de dispositivo são aplicadas por meio de pacotes de provisionamento com base em casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="d4f6c-162">Essas configurações normalmente são restritas devido a requisitos de ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="d4f6c-163">Um ou mais aplicativos são implantados por meio do pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="d4f6c-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="d4f6c-164">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="d4f6c-164">Common Challenges</span></span>
   * <span data-ttu-id="d4f6c-165">Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="d4f6c-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="d4f6c-166">Os serviços de nuvem não podem ser usados, portanto limitando os recursos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="d4f6c-167">Maior sobrecarga administrativa, uma vez que esses dispositivos precisam ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="d4f6c-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="d4f6c-168">[![Diagrama seguro offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d4f6c-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="d4f6c-169">Para obter um guia de implantação semelhante a este cenário, examine nosso [Guia de implantação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="d4f6c-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d4f6c-170">Guia de implantação de ambiente seguro offline</span><span class="sxs-lookup"><span data-stu-id="d4f6c-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
