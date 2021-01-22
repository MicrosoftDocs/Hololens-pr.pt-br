---
title: Cenários comuns de implantação da infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em diferentes implantações de infraestrutura para realidade misturada.
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283622"
---
# <span data-ttu-id="7a7e0-104">Visão geral de cenários comuns de implantação de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="7a7e0-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="7a7e0-105">Essas informações a seguir proporcionam uma visão geral da arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="7a7e0-106">Muitas vezes, a maneira como você gerencia seus dispositivos e como acessar os recursos da sua organização é amplamente determinada por fatores já em uso.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="7a7e0-107">Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivo comum nos cenários a seguir e testar nossos guias para implantação no cenário que corresponde às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="7a7e0-108">Cenários</span><span class="sxs-lookup"><span data-stu-id="7a7e0-108">Scenarios</span></span>

<span data-ttu-id="7a7e0-109">O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagrama de cenários](images/scenarios.jpg)

### <span data-ttu-id="7a7e0-111">Cenário A: Implantar em dispositivos conectados à nuvem</span><span class="sxs-lookup"><span data-stu-id="7a7e0-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="7a7e0-112">O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="7a7e0-113">Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="7a7e0-114">Essa implantação é semelhante aos dispositivos móveis gerenciados dentro de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="7a7e0-115">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="7a7e0-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="7a7e0-116">Wi-Fi redes são normalmente totalmente abertas para os serviços de Nuvem e Internet.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="7a7e0-117">Ingressar no Azure AD com o registro automático de gerenciamento de dispositivo móvel (MDM) – MDM (Intune) gerenciado</span><span class="sxs-lookup"><span data-stu-id="7a7e0-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="7a7e0-118">Os usuários podem entrar com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7a7e0-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="7a7e0-119">Um ou vários usuários por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="7a7e0-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="7a7e0-120">Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto a Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="7a7e0-121">Um ou mais aplicativos são implantados via MDM</span><span class="sxs-lookup"><span data-stu-id="7a7e0-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="7a7e0-122">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="7a7e0-122">Common Challenges</span></span>
   * <span data-ttu-id="7a7e0-123">Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos de cenário.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="7a7e0-124">Para ver um guia de implantação semelhante ao cenário, confira nosso guia para [o HoloLens 2](hololens2-cloud-connected-overview.md)conectado à nuvem com Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7a7e0-125">Guia de Implantação – HoloLens 2 conectado à nuvem com Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="7a7e0-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="7a7e0-126">Cenário B: Implantar dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="7a7e0-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="7a7e0-127">O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="7a7e0-128">Serviços de nuvem e Internet podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="7a7e0-129">Essa implantação é típica para a maioria dos computadores com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="7a7e0-130">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="7a7e0-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="7a7e0-131">Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="7a7e0-132">Ingressar no Azure AD com o registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="7a7e0-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="7a7e0-133">MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="7a7e0-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="7a7e0-134">Os usuários podem entrar com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7a7e0-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="7a7e0-135">Um ou vários usuários por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="7a7e0-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="7a7e0-136">Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto a Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="7a7e0-137">Um ou mais aplicativos são implantados via MDM</span><span class="sxs-lookup"><span data-stu-id="7a7e0-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="7a7e0-138">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="7a7e0-138">Common Challenges</span></span>
   * <span data-ttu-id="7a7e0-139">O HoloLens 2 não dá suporte ao AD ou SCCM local.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="7a7e0-140">Somente o Azure AD entra no MDM.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="7a7e0-141">Muitas empresas hoje ainda implantam computadores Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Internos do Windows 10 por meio de soluções MDM baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="7a7e0-142">Como o HoloLens 2 é um primeiro dispositivo de nuvem, ele depende muito dos serviços conectados à Internet e à nuvem para autenticação do usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="7a7e0-143">Ao se conectar a uma rede corporativa, as regras de Proxy/Firewall provavelmente precisarão ser ajustadas para habilitar o acesso ao HoloLens 2 e aos aplicativos que são executados nele.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="7a7e0-144">A Wi-Fi corporativa geralmente requer certificados para autenticar o dispositivo ou o usuário na rede.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="7a7e0-145">A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio do MDM pode ser desafiadora de configurar.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="7a7e0-146">Cenário C: Implantar em um ambiente offline seguro</span><span class="sxs-lookup"><span data-stu-id="7a7e0-146">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="7a7e0-147">O HoloLens 2 é implantado para uso principalmente offline sem acesso à rede ou à Internet.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-147">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="7a7e0-148">Essa é uma implantação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-148">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="7a7e0-149">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="7a7e0-149">Basic Common Configurations</span></span>
   * <span data-ttu-id="7a7e0-150">Wi-Fi conectividade está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-150">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="7a7e0-151">Ethernet via USB pode estar habilitada para conectividade lan, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-151">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="7a7e0-152">Não Gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-152">Not Managed.</span></span>
   * <span data-ttu-id="7a7e0-153">Conta de usuário local para entrada do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-153">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="7a7e0-154">O HoloLens 2 dá suporte a apenas uma conta local.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-154">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="7a7e0-155">Níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de Pacotes de Provisionamento com base em casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-155">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="7a7e0-156">Essas configurações são normalmente restritas devido a requisitos de ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-156">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="7a7e0-157">Um ou mais aplicativos são implantados por meio do Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="7a7e0-157">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="7a7e0-158">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="7a7e0-158">Common Challenges</span></span>
   * <span data-ttu-id="7a7e0-159">Há um conjunto limitado de configurações disponíveis por meio de Pacotes de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="7a7e0-159">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="7a7e0-160">Os serviços de nuvem não podem ser usados, portanto, limitando os recursos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-160">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="7a7e0-161">Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="7a7e0-161">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="7a7e0-162">Para obter um guia de implantação semelhante a este cenário, revise nosso Guia [de Implantação Segura Offline.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="7a7e0-162">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7a7e0-163">Guia de Implantação – HoloLens Seguro Offline 2</span><span class="sxs-lookup"><span data-stu-id="7a7e0-163">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
