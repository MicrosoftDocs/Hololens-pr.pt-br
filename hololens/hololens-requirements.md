---
title: Cenários comuns de implantação
description: Saiba mais sobre como implantar e gerenciar HoloLens em ambientes corporativos, incluindo infraestrutura, Azure Active Directory e gerenciamento de dispositivo móvel.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639821"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="cbb93-103">Cenários comuns de implantação</span><span class="sxs-lookup"><span data-stu-id="cbb93-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="cbb93-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="cbb93-104">Overview</span></span>

<span data-ttu-id="cbb93-105">Esta página fornece uma visão geral da arquitetura de alto nível para três cenários comuns ao implantar e gerenciar Microsoft HoloLens 2 dispositivos dentro da empresa.</span><span class="sxs-lookup"><span data-stu-id="cbb93-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="cbb93-106">Geralmente, a maneira como você gerencia seus dispositivos e acessa os recursos da sua organização é determinada em grande parte pelos fatores já em uso.</span><span class="sxs-lookup"><span data-stu-id="cbb93-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="cbb93-107">Com base em sua infraestrutura existente, convidamos você a revisar o MDM (estilo de gerenciamento de dispositivo) comum nos cenários a seguir e, em seguida, ler Planejamento de implantações [do HoloLens 2](hololens-core-components.md) em um ambiente comercial para determinar qual cenário corresponde às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="cbb93-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="cbb93-108">Também há três guias correspondentes disponíveis para uso durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="cbb93-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="cbb93-109">Guia de implantação do ambiente conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="cbb93-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="cbb93-110">Guia de implantação do ambiente conectado à nuvem (clientes externos)</span><span class="sxs-lookup"><span data-stu-id="cbb93-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="cbb93-111">Guia de implantação de rede corporativa</span><span class="sxs-lookup"><span data-stu-id="cbb93-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="cbb93-112">Guia de implantação de ambiente seguro offline</span><span class="sxs-lookup"><span data-stu-id="cbb93-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="cbb93-113">Cenário A: Implantar em dispositivos conectados à nuvem</span><span class="sxs-lookup"><span data-stu-id="cbb93-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="cbb93-114">Esse cenário é comparável à implantação de dispositivos móveis gerenciados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="cbb93-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="cbb93-115">HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="cbb93-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="cbb93-116">Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN.</span><span class="sxs-lookup"><span data-stu-id="cbb93-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="cbb93-117">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="cbb93-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="cbb93-118">Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e Nuvem.</span><span class="sxs-lookup"><span data-stu-id="cbb93-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="cbb93-119">Ingressar no Azure AD com o registro automático do MDM (Mobile Gerenciamento de Dispositivos) – MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="cbb93-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="cbb93-120">Os usuários entrarão com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="cbb93-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="cbb93-121">Usuários individuais ou múltiplos por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="cbb93-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="cbb93-122">Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="cbb93-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="cbb93-123">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="cbb93-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="cbb93-124">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="cbb93-124">Common Challenges</span></span>
   * <span data-ttu-id="cbb93-125">Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.</span><span class="sxs-lookup"><span data-stu-id="cbb93-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="cbb93-126">[![Cenário Um diagrama ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cbb93-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="cbb93-127">O guia conectado à nuvem correspondente aborda como registrar o HoloLens 2 no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente o Remote Assist na instalação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cbb93-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="cbb93-128">Use o guia Clientes Externos para implantar dispositivos em um site remoto para uso externo de curto ou longo prazo.</span><span class="sxs-lookup"><span data-stu-id="cbb93-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cbb93-129">Guia de implantação do ambiente conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="cbb93-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="cbb93-130">Guia de implantação do ambiente conectado à nuvem (clientes externos)</span><span class="sxs-lookup"><span data-stu-id="cbb93-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="cbb93-131">Cenário B: Implantar dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="cbb93-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="cbb93-132">Esse cenário é idêntico a uma implantação clássica para a maioria Windows 10 PCs.</span><span class="sxs-lookup"><span data-stu-id="cbb93-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="cbb93-133">HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="cbb93-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="cbb93-134">Serviços de Internet e nuvem podem ser limitados.</span><span class="sxs-lookup"><span data-stu-id="cbb93-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="cbb93-135">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="cbb93-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="cbb93-136">Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="cbb93-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="cbb93-137">Ingressar no Azure AD com registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="cbb93-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="cbb93-138">MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="cbb93-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="cbb93-139">Os usuários entrarão com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="cbb93-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="cbb93-140">Usuários individuais ou múltiplos por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="cbb93-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="cbb93-141">Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="cbb93-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="cbb93-142">Um ou mais aplicativos são implantados por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="cbb93-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="cbb93-143">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="cbb93-143">Common Challenges</span></span>
   * <span data-ttu-id="cbb93-144">HoloLens 2 não dá suporte ao SCCM ou ao AD local.</span><span class="sxs-lookup"><span data-stu-id="cbb93-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="cbb93-145">Somente a junção do Azure AD ao MDM.</span><span class="sxs-lookup"><span data-stu-id="cbb93-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="cbb93-146">Muitas empresas hoje ainda implantam PCs Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo SCCM (System Center Configuration Manager) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos internos Windows 10 por meio de soluções de MDM baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="cbb93-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="cbb93-147">Como HoloLens 2 é um primeiro dispositivo de nuvem, ele depende muito dos serviços conectados à Internet e à nuvem para autenticação de usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="cbb93-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="cbb93-148">Ao se conectar a uma rede corporativa, as regras de Proxy/Firewall provavelmente precisarão ser ajustadas para habilitar o acesso para o HoloLens 2 e os aplicativos que são executados nele.</span><span class="sxs-lookup"><span data-stu-id="cbb93-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="cbb93-149">A Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o usuário na rede.</span><span class="sxs-lookup"><span data-stu-id="cbb93-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="cbb93-150">A infraestrutura ou as configurações necessárias para implantar certificados Windows 10 dispositivos por meio do MDM pode ser um desafio para configurar.</span><span class="sxs-lookup"><span data-stu-id="cbb93-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="cbb93-151">[![Diagrama do cenário B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cbb93-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="cbb93-152">[![Diagrama do cenário B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cbb93-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="cbb93-153">O guia de rede corporativa correspondente instrui sobre como registrar o HoloLens 2 em seu gerenciamento de dispositivo existente, aplicar licenças conforme necessário e validar se os usuários finais podem operar um Guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cbb93-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cbb93-154">Guia de implantação de rede corporativa</span><span class="sxs-lookup"><span data-stu-id="cbb93-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="cbb93-155">Cenário C: Implantar em um ambiente offline seguro</span><span class="sxs-lookup"><span data-stu-id="cbb93-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="cbb93-156">Essa é uma implantação típica para locais altamente seguros ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="cbb93-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="cbb93-157">HoloLens 2 é implantado para uso principalmente offline sem acesso à rede ou à Internet.</span><span class="sxs-lookup"><span data-stu-id="cbb93-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="cbb93-158">Configurações comuns básicas</span><span class="sxs-lookup"><span data-stu-id="cbb93-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="cbb93-159">Wi-Fi conectividade está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="cbb93-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="cbb93-160">Ethernet via USB pode ser habilitada para conectividade lan, se necessário.</span><span class="sxs-lookup"><span data-stu-id="cbb93-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="cbb93-161">Não Gerenciado.</span><span class="sxs-lookup"><span data-stu-id="cbb93-161">Not Managed.</span></span>
   * <span data-ttu-id="cbb93-162">Conta de usuário local para entrada do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cbb93-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="cbb93-163">HoloLens 2 dá suporte a apenas uma conta local.</span><span class="sxs-lookup"><span data-stu-id="cbb93-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="cbb93-164">Níveis variados de configurações de bloqueio de dispositivo são aplicados por meio de Pacotes de Provisionamento com base em casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="cbb93-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="cbb93-165">Essas configurações normalmente são restritas devido aos requisitos de ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="cbb93-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="cbb93-166">Um ou mais aplicativos são implantados por meio do Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="cbb93-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="cbb93-167">Desafios comuns</span><span class="sxs-lookup"><span data-stu-id="cbb93-167">Common Challenges</span></span>
   * <span data-ttu-id="cbb93-168">Há um conjunto limitado de configurações disponíveis por meio de Pacotes de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="cbb93-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="cbb93-169">Os serviços de nuvem não podem ser usados, portanto, limitando as HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cbb93-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="cbb93-170">Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.</span><span class="sxs-lookup"><span data-stu-id="cbb93-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="cbb93-171">[![Diagrama seguro offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cbb93-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="cbb93-172">O guia seguro offline correspondente fornece instruções para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros.</span><span class="sxs-lookup"><span data-stu-id="cbb93-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cbb93-173">Guia de implantação de ambiente seguro offline</span><span class="sxs-lookup"><span data-stu-id="cbb93-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


