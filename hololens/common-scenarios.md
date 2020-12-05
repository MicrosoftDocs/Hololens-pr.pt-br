---
title: Cenários comuns de implantação da infraestrutura
description: Alguns cenários comuns de implantação baseados em infra-estruturas comuns diferentes
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195564"
---
# <span data-ttu-id="cc994-104">Visão geral dos cenários comuns de implantação de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="cc994-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="cc994-105">Essas informações a seguir fornecem uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 na empresa.</span><span class="sxs-lookup"><span data-stu-id="cc994-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="cc994-106">Muitas vezes, como você gerencia seus dispositivos e como o acesso aos recursos da sua organização é determinado por fatores que já estão em vigor.</span><span class="sxs-lookup"><span data-stu-id="cc994-106">Often how you manage your devices and how access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="cc994-107">Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivos comuns nos seguintes cenários e experimentar nossos guias para a implantação no cenário que atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="cc994-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="cc994-108">Cenários</span><span class="sxs-lookup"><span data-stu-id="cc994-108">Scenarios</span></span>

<span data-ttu-id="cc994-109">O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cc994-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagrama de cenários](images/scenarios.jpg)

### <span data-ttu-id="cc994-111">Cenário A: implantar em dispositivos de conexão em nuvem</span><span class="sxs-lookup"><span data-stu-id="cc994-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="cc994-112">O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="cc994-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="cc994-113">Os recursos corporativos não são acessados ou podem ser limitados pela VPN.</span><span class="sxs-lookup"><span data-stu-id="cc994-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="cc994-114">Isso é uma implantação muito semelhante a dispositivos móveis gerenciados dentro de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="cc994-114">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="cc994-115">Configurações básicas básicas</span><span class="sxs-lookup"><span data-stu-id="cc994-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="cc994-116">Geralmente, as redes Wi-Fi são totalmente abertas para a Internet e os serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="cc994-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="cc994-117">Ingressar no Azure AD com o registro automático do MDM--gerenciamento de MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="cc994-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="cc994-118">Os usuários entram com sua própria conta corporativa (AAD)</span><span class="sxs-lookup"><span data-stu-id="cc994-118">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="cc994-119">Suporte para um ou vários usuários por dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc994-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="cc994-120">Os níveis variáveis das configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, de totalmente abertos para o quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="cc994-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="cc994-121">Um ou mais aplicativos são implantados via MDM</span><span class="sxs-lookup"><span data-stu-id="cc994-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="cc994-122">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="cc994-122">Common Challenges</span></span>
   * <span data-ttu-id="cc994-123">Determinar quais configurações do MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.</span><span class="sxs-lookup"><span data-stu-id="cc994-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="cc994-124">Para um guia de implantação semelhante a este cenário, consulte o nosso guia para o [HoloLens conectado à nuvem 2 com assistência remota](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc994-124">For a deployment guide that is similar to this scenario please review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cc994-125">Guia de implantação – HoloLens conectado à nuvem 2 com assistência remota</span><span class="sxs-lookup"><span data-stu-id="cc994-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="cc994-126">Cenário B: implantar dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="cc994-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="cc994-127">O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="cc994-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="cc994-128">Os serviços de nuvem e Internet podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="cc994-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="cc994-129">Esta é uma implantação típica para a maioria dos computadores com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cc994-129">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="cc994-130">Configurações básicas básicas</span><span class="sxs-lookup"><span data-stu-id="cc994-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="cc994-131">Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="cc994-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="cc994-132">Ingressar no Azure AD com o registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="cc994-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="cc994-133">Gerenciamento de MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="cc994-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="cc994-134">Os usuários entram com sua própria conta corporativa (AAD)</span><span class="sxs-lookup"><span data-stu-id="cc994-134">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="cc994-135">Suporte para um ou vários usuários por dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc994-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="cc994-136">Os níveis variáveis das configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, de totalmente abertos para o quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="cc994-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="cc994-137">Um ou mais aplicativos são implantados via MDM</span><span class="sxs-lookup"><span data-stu-id="cc994-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="cc994-138">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="cc994-138">Common Challenges</span></span>
   * <span data-ttu-id="cc994-139">O HoloLens 2 não é compatível com o ingresso no AD local ou SCCM.</span><span class="sxs-lookup"><span data-stu-id="cc994-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="cc994-140">Somente ingresso do Azure AD com MDM.</span><span class="sxs-lookup"><span data-stu-id="cc994-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="cc994-141">Hoje em dia, muitas empresas ainda implantam computadores Windows 10 nesse cenário, como os dispositivos ingressados no AD, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções MDM baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="cc994-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="cc994-142">Como o HoloLens 2 é um dispositivo de nuvem, ele depende muito de serviços conectados à Internet e na nuvem para autenticação de usuários, atualizações de so, gerenciamento de MDM, etc. Ao conectar-se a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para permitir o acesso para o HoloLens 2 e os aplicativos que são executados nele.</span><span class="sxs-lookup"><span data-stu-id="cc994-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="cc994-143">Geralmente, a conectividade com Wi-Fi corporativos requer certificados para autenticar o dispositivo ou o usuário na rede.</span><span class="sxs-lookup"><span data-stu-id="cc994-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="cc994-144">A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio de MDM podem ser difíceis de configurar.</span><span class="sxs-lookup"><span data-stu-id="cc994-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="cc994-145">Cenário C: implantar no ambiente offline seguro</span><span class="sxs-lookup"><span data-stu-id="cc994-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="cc994-146">O HoloLens 2 é implantado para ser usado principalmente offline sem acesso à Internet ou à rede.</span><span class="sxs-lookup"><span data-stu-id="cc994-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="cc994-147">Esta é uma implantação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="cc994-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="cc994-148">Configurações básicas básicas</span><span class="sxs-lookup"><span data-stu-id="cc994-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="cc994-149">Wi-Fi conectividade está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="cc994-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="cc994-150">A Ethernet via USB pode estar ativada para conectividade de LAN, se necessário.</span><span class="sxs-lookup"><span data-stu-id="cc994-150">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="cc994-151">Não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="cc994-151">Not Managed.</span></span>
   * <span data-ttu-id="cc994-152">Conta de usuário local para entrada de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc994-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="cc994-153">O HoloLens 2 oferece suporte a apenas 1 conta local.</span><span class="sxs-lookup"><span data-stu-id="cc994-153">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="cc994-154">Os níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de pacotes de provisionamento com base em casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="cc994-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="cc994-155">Essas configurações geralmente são muito restritas devido a requisitos de ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="cc994-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="cc994-156">Um ou mais aplicativos são implantados por meio do pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="cc994-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="cc994-157">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="cc994-157">Common Challenges</span></span>
   * <span data-ttu-id="cc994-158">Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="cc994-158">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="cc994-159">Os serviços de nuvem não podem ser aproveitados, portanto limitando os recursos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cc994-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="cc994-160">Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="cc994-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="cc994-161">Para obter um guia de implantação semelhante a este cenário, consulte o nosso [Guia de implantação seguro offline](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="cc994-161">For a deployment guide that is similar to this scenario please review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cc994-162">Guia de implantação – HoloLens offline seguro 2</span><span class="sxs-lookup"><span data-stu-id="cc994-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
