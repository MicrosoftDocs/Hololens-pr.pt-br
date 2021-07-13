---
title: visão geral da nuvem conectada HoloLens 2 com o auxílio remoto
description: saiba como registrar HoloLens 2 dispositivos em uma rede conectada na nuvem usando o assistente remoto do Dynamics 365.
keywords: HoloLens, gerenciamento, nuvem conectada, assistência remota, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 26fd2def8ce1fa8f960ab930e209c74fb37e2e0a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639753"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="2deff-104">guia de implantação – conectado à nuvem HoloLens 2 com assistência remota – visão geral</span><span class="sxs-lookup"><span data-stu-id="2deff-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="2deff-105">este guia ajudará os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 com o auxílio remoto para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2deff-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="2deff-106">isso servirá como um modelo para implantações de prova de conceito em sua organização em vários casos de uso HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2deff-106">This will serve as a model for proof-of-concept deployments to your organization across various HoloLens 2 use cases.</span></span> <span data-ttu-id="2deff-107">A configuração é semelhante ao [cenário a: implantar em dispositivos do Cloud Connect](common-scenarios.md#scenario-a).</span><span class="sxs-lookup"><span data-stu-id="2deff-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](common-scenarios.md#scenario-a).</span></span> 

<span data-ttu-id="2deff-108">Durante o guia, abordaremos como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar que os usuários finais podem usar imediatamente a assistência remota após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2deff-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="2deff-109">para fazer isso, veremos as importantes partes da infraestrutura necessária para a configuração e a execução – atingindo a implantação em escala com o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2deff-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="2deff-110">Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, no entanto, incentivamos você a explorar essas opções após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="2deff-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2deff-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2deff-111">Prerequisites</span></span>

<span data-ttu-id="2deff-112">a infraestrutura a seguir deve estar em vigor para implantar o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2deff-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="2deff-113">Caso contrário, a configuração do Azure e do Intune está incluída neste guia:</span><span class="sxs-lookup"><span data-stu-id="2deff-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="2deff-114">Essa é uma configuração semelhante ao [cenário a: implantar em dispositivos do Cloud Connect](/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implantações de prova de conceito, que incluirá:</span><span class="sxs-lookup"><span data-stu-id="2deff-114">This is a setup similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="2deff-115">As redes Wi-Fi normalmente são totalmente abertas na Internet e nos serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="2deff-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="2deff-116">Ingresso no Azure AD com o registro automático do MDM — gerenciado pelo MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="2deff-116">Azure AD Join with MDM Auto Enrollment—MDM-managed (Intune)</span></span>
- <span data-ttu-id="2deff-117">Os usuários entram com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="2deff-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="2deff-118">Há suporte para um ou vários usuários por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2deff-118">Single or multiple users per device are supported.</span></span>

:::image type="content" alt-text="Cenário conectado à nuvem" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="2deff-120">Saiba mais sobre o auxílio remoto</span><span class="sxs-lookup"><span data-stu-id="2deff-120">Learn about Remote Assist</span></span>

<span data-ttu-id="2deff-121">A assistência remota permite a manutenção e o reparo colaborativos, a inspeção remota, bem como o compartilhamento e o treinamento de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="2deff-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="2deff-122">Ao conectar pessoas em diferentes funções e locais, um técnico que usa a assistência remota pode se conectar com um colaborador remoto no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2deff-122">By connecting people in different roles and locations, a technician who uses Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="2deff-123">Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando não estiverem no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="2deff-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren't in the same location.</span></span> <span data-ttu-id="2deff-124">Os colaboradores remotos podem inserir imagens de referência, esquemáticos e outras informações úteis do espaço físico do técnico para que eles possam se referir ao esquema durante o trabalho e a mão livre em HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2deff-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician's physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="2deff-125">Requisitos e licenciamento da assistência remota</span><span class="sxs-lookup"><span data-stu-id="2deff-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="2deff-126">Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)</span><span class="sxs-lookup"><span data-stu-id="2deff-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="2deff-127">[Assinatura de assistência remota](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [avaliação de assistência remota](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="2deff-127">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="2deff-128">Usuário de assistência remota do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2deff-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="2deff-129">Licença de assistência remota</span><span class="sxs-lookup"><span data-stu-id="2deff-129">Remote Assist license</span></span>
- <span data-ttu-id="2deff-130">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="2deff-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="2deff-131">Microsoft Teams usuário</span><span class="sxs-lookup"><span data-stu-id="2deff-131">Microsoft Teams user</span></span>

- <span data-ttu-id="2deff-132">Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="2deff-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="2deff-133">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="2deff-133">Network connectivity</span></span>

<span data-ttu-id="2deff-134">Se você planeja implementar esse [cenário de locatário cruzado](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), talvez precise de uma licença de barreiras de informações.</span><span class="sxs-lookup"><span data-stu-id="2deff-134">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="2deff-135">Para determinar se uma licença de barreira de informações é necessária, consulte [fornecedores e clientes que usam recursos completos de assistência remota do Dynamics 365](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).</span><span class="sxs-lookup"><span data-stu-id="2deff-135">To determine if an Information Barrier License is required, see [Vendors and customers use full Dynamics 365 Remote Assist capabilities](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="2deff-136">Neste guia, você:</span><span class="sxs-lookup"><span data-stu-id="2deff-136">In this guide you will:</span></span>

<span data-ttu-id="2deff-137">Preparar:</span><span class="sxs-lookup"><span data-stu-id="2deff-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="2deff-138">saiba mais sobre as noções básicas de infraestrutura para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2deff-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="2deff-139">Saiba mais sobre o Azure AD e configure um se você não&#39;o tiver.</span><span class="sxs-lookup"><span data-stu-id="2deff-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="2deff-140">Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2deff-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="2deff-141">Saiba mais sobre o MDM e configure-o com o Intune se você não&#39;t já tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="2deff-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="2deff-142">Saiba mais sobre os requisitos de rede do auxílio remoto.</span><span class="sxs-lookup"><span data-stu-id="2deff-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="2deff-143">Opcionalmente: VPN para se conectar aos recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="2deff-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="2deff-144">Configurar:</span><span class="sxs-lookup"><span data-stu-id="2deff-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="2deff-145">Como criar usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="2deff-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="2deff-146">Como configurar o registro automático no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2deff-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="2deff-147">Como atribuir suas licenças de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2deff-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="2deff-148">Implantar:</span><span class="sxs-lookup"><span data-stu-id="2deff-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="2deff-149">configure seu HoloLens 2 e valide o registro.</span><span class="sxs-lookup"><span data-stu-id="2deff-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="2deff-150">Validar você pode fazer uma chamada de assistência remota.</span><span class="sxs-lookup"><span data-stu-id="2deff-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="2deff-151">Manter:</span><span class="sxs-lookup"><span data-stu-id="2deff-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="2deff-152">como atualizar a assistência remota usando o aplicativo Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="2deff-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="2deff-153">Fazendo um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="2deff-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="2deff-154">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="2deff-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="2deff-155">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2deff-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2deff-156">Implantação conectada na nuvem-preparar</span><span class="sxs-lookup"><span data-stu-id="2deff-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

