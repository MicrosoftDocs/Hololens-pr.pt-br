---
title: Cenários comuns de implantação da infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em implantações de infraestrutura diferentes para realidade mista.
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448489"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="fb697-104">Visão geral dos cenários comuns de implantação de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="fb697-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="fb697-105">Essas informações a seguir fornece uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos do Microsoft HoloLens 2 dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="fb697-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="fb697-106">Geralmente, a maneira como você gerencia seus dispositivos e como acessar os recursos da sua organização é amplamente determinada por fatores já em uso.</span><span class="sxs-lookup"><span data-stu-id="fb697-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="fb697-107">Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivo comum nos cenários a seguir e experimentar nossos guias para implantar no cenário que corresponde às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="fb697-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="fb697-108">Cenários</span><span class="sxs-lookup"><span data-stu-id="fb697-108">Scenarios</span></span>

<span data-ttu-id="fb697-109">O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="fb697-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagrama de cenários](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="fb697-111">Cenário A: Implantar em dispositivos de conexão na nuvem</span><span class="sxs-lookup"><span data-stu-id="fb697-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="fb697-112">O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="fb697-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="fb697-113">Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN.</span><span class="sxs-lookup"><span data-stu-id="fb697-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="fb697-114">Essa implantação é semelhante a dispositivos móveis gerenciados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="fb697-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="fb697-115">Configurações Comuns Básicas</span><span class="sxs-lookup"><span data-stu-id="fb697-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="fb697-116">Wi-Fi redes normalmente estão totalmente abertas para os serviços de Internet e Nuvem.</span><span class="sxs-lookup"><span data-stu-id="fb697-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="fb697-117">Participação automática do Azure AD com o Registro Automático de Gerenciamento de Dispositivo Móvel (MDM), MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="fb697-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="fb697-118">Os usuários entrar com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="fb697-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="fb697-119">Usuários individuais ou múltiplos por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="fb697-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="fb697-120">Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto até Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="fb697-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="fb697-121">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="fb697-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="fb697-122">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="fb697-122">Common Challenges</span></span>
   * <span data-ttu-id="fb697-123">Determinando quais configurações de MDM serão aplicadas ao HoloLens 2 com base nos requisitos de cenário.</span><span class="sxs-lookup"><span data-stu-id="fb697-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="fb697-124">Para um guia de implantação semelhante ao cenário Uma revisão do nosso guia para [o HoloLens 2](hololens2-cloud-connected-overview.md)conectado à nuvem com Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="fb697-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fb697-125">Guia de Implantação – HoloLens 2 conectado à nuvem com Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="fb697-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="fb697-126">Cenário B: Implantar dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="fb697-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="fb697-127">O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="fb697-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="fb697-128">Os serviços de Internet e nuvem podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="fb697-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="fb697-129">Essa implantação é uma implantação típica para a maioria dos computadores windows 10.</span><span class="sxs-lookup"><span data-stu-id="fb697-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="fb697-130">Configurações Comuns Básicas</span><span class="sxs-lookup"><span data-stu-id="fb697-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="fb697-131">Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de Nuvem.</span><span class="sxs-lookup"><span data-stu-id="fb697-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="fb697-132">Azure AD Join with MDM Auto Enrollment</span><span class="sxs-lookup"><span data-stu-id="fb697-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="fb697-133">MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="fb697-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="fb697-134">Os usuários entrar com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="fb697-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="fb697-135">Usuários individuais ou múltiplos por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="fb697-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="fb697-136">Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto até Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="fb697-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="fb697-137">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="fb697-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="fb697-138">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="fb697-138">Common Challenges</span></span>
   * <span data-ttu-id="fb697-139">O HoloLens 2 não dá suporte ao AD join ou SCCM local.</span><span class="sxs-lookup"><span data-stu-id="fb697-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="fb697-140">Somente o Azure AD ingressará no MDM.</span><span class="sxs-lookup"><span data-stu-id="fb697-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="fb697-141">Muitas empresas ainda implantam computadores windows 10 neste cenário como dispositivos ingressados no AD local, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos internos do Windows 10 por meio de soluções MDM baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="fb697-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="fb697-142">Como o HoloLens 2 é um primeiro dispositivo de nuvem, ele depende muito dos serviços conectados à Internet e à nuvem para autenticação do usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="fb697-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="fb697-143">Ao se conectar a uma rede corporativa, as regras de Proxy/Firewall provavelmente precisarão ser ajustadas para habilitar o acesso para o HoloLens 2 e os aplicativos que são executados nele.</span><span class="sxs-lookup"><span data-stu-id="fb697-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="fb697-144">A Wi-Fi conectividade corporativa normalmente exige certificados para autenticar o dispositivo ou o usuário na rede.</span><span class="sxs-lookup"><span data-stu-id="fb697-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="fb697-145">A infraestrutura ou configurações necessárias para implantar certificados em dispositivos Windows 10 por meio do MDM pode ser um desafio para configurar.</span><span class="sxs-lookup"><span data-stu-id="fb697-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fb697-146">Guia de Implantação – HoloLens 2 conectado corporativo com Guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="fb697-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="fb697-147">Cenário C: Implantar em ambiente offline seguro</span><span class="sxs-lookup"><span data-stu-id="fb697-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="fb697-148">O HoloLens 2 é implantado para uso principalmente offline sem acesso à rede ou à Internet.</span><span class="sxs-lookup"><span data-stu-id="fb697-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="fb697-149">Essa é uma implantação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="fb697-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="fb697-150">Configurações Comuns Básicas</span><span class="sxs-lookup"><span data-stu-id="fb697-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="fb697-151">Wi-Fi conectividade está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="fb697-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="fb697-152">Ethernet via USB pode estar habilitada para conectividade lan, se necessário.</span><span class="sxs-lookup"><span data-stu-id="fb697-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="fb697-153">Não Gerenciado.</span><span class="sxs-lookup"><span data-stu-id="fb697-153">Not Managed.</span></span>
   * <span data-ttu-id="fb697-154">Conta de usuário local para entrada de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb697-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="fb697-155">O HoloLens 2 dá suporte a apenas uma conta local.</span><span class="sxs-lookup"><span data-stu-id="fb697-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="fb697-156">Níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de Pacotes de Provisionamento com base em casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="fb697-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="fb697-157">Essas configurações geralmente são restritas devido aos requisitos de ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="fb697-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="fb697-158">Um ou mais aplicativos são implantados por meio do Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="fb697-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="fb697-159">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="fb697-159">Common Challenges</span></span>
   * <span data-ttu-id="fb697-160">Há um conjunto limitado de configurações disponíveis por meio de Pacotes de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="fb697-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="fb697-161">Os serviços de nuvem não podem ser usados, portanto, limitando os recursos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="fb697-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="fb697-162">Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="fb697-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="fb697-163">Para obter um guia de implantação semelhante a esse cenário, revise nosso [Guia de Implantação Segura Offline.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="fb697-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fb697-164">Guia de Implantação – HoloLens Seguro Offline 2</span><span class="sxs-lookup"><span data-stu-id="fb697-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
