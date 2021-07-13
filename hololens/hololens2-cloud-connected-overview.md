---
title: Visão geral do Cloud Connected HoloLens 2 com Assistência Remota
description: Saiba como registrar HoloLens 2 dispositivos em uma rede conectada à nuvem usando o Dynamics 365 Remote Assist.
keywords: HoloLens, gerenciamento, nuvem conectada, Assistência Remota, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635119"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="e8c85-104">Guia de implantação – Nuvem conectada HoloLens 2 com Assistência Remota – Visão geral</span><span class="sxs-lookup"><span data-stu-id="e8c85-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="e8c85-105">Este guia ajudará os profissionais de TI a planejar e implantar Microsoft HoloLens 2 dispositivos com Assistência Remota em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8c85-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="e8c85-106">Isso servirá como um modelo para implantações de prova de conceito em sua organização em uma variedade de HoloLens dois casos de uso.</span><span class="sxs-lookup"><span data-stu-id="e8c85-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="e8c85-107">A configuração é semelhante ao [Cenário A: Implantar em dispositivos de conexão de nuvem.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="e8c85-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="e8c85-108">Durante o guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na instalação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8c85-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="e8c85-109">Para fazer isso, vamos falar sobre as partes importantes da infraestrutura necessárias para ser configurada e em execução – alcançando a implantação em escala com HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e8c85-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="e8c85-110">Nenhuma outra restrição de dispositivo ou configurações será aplicada neste guia, no entanto, incentivamos você a explorar essas opções após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="e8c85-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8c85-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e8c85-111">Prerequisites</span></span>

<span data-ttu-id="e8c85-112">A infraestrutura a seguir deve estar em uso para implantar o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e8c85-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="e8c85-113">Caso não, a configuração do Azure e do Intune está incluída neste guia:</span><span class="sxs-lookup"><span data-stu-id="e8c85-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="e8c85-114">Essa é uma configuração semelhante ao Cenário [A:](/hololens/common-scenarios#scenario-a)Implantar em dispositivos de conexão de nuvem, que é uma boa opção para muitas implantações de Prova de Conceito, que incluirão:</span><span class="sxs-lookup"><span data-stu-id="e8c85-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="e8c85-115">Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e nuvem</span><span class="sxs-lookup"><span data-stu-id="e8c85-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="e8c85-116">Ingressar no Azure AD com Registro Automático do MDM – MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="e8c85-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="e8c85-117">Os usuários entrarão com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e8c85-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="e8c85-118">Há suporte para usuários individuais ou múltiplos por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8c85-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Cenário conectado à nuvem" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="e8c85-120">Saiba mais sobre o Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e8c85-120">Learn about Remote Assist</span></span>

<span data-ttu-id="e8c85-121">O Remote Assist permite manutenção e reparo colaborativos, inspeção remota, bem como treinamento e compartilhamento de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="e8c85-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="e8c85-122">Conectando pessoas em diferentes funções e locais, um técnico que usa o Remote Assist pode se conectar com um colaborador remoto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e8c85-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="e8c85-123">Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando&#39;estão no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="e8c85-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="e8c85-124">Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis que o técnico&#39;tem no espaço físico para que possam se referir ao esquema enquanto trabalham de cabeça para cima e mãos livres em HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e8c85-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="e8c85-125">Licenciamento e requisitos do Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e8c85-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="e8c85-126">Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)</span><span class="sxs-lookup"><span data-stu-id="e8c85-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="e8c85-127">[Assinatura do Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [Avaliação do Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="e8c85-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="e8c85-128">Usuário do Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e8c85-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="e8c85-129">Licença do Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e8c85-129">Remote Assist license</span></span>
- <span data-ttu-id="e8c85-130">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="e8c85-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="e8c85-131">Microsoft Teams usuário</span><span class="sxs-lookup"><span data-stu-id="e8c85-131">Microsoft Teams user</span></span>

- <span data-ttu-id="e8c85-132">Microsoft Teams ou [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="e8c85-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="e8c85-133">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="e8c85-133">Network connectivity</span></span>

<span data-ttu-id="e8c85-134">Se você planeja implementar esse cenário [entre locatários,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)talvez precise de uma licença de Barreiras de Informações.</span><span class="sxs-lookup"><span data-stu-id="e8c85-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="e8c85-135">Consulte [este artigo para](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) determinar se uma Licença de Barreira de Informações é necessária.</span><span class="sxs-lookup"><span data-stu-id="e8c85-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="e8c85-136">Neste guia, você:</span><span class="sxs-lookup"><span data-stu-id="e8c85-136">In this guide you will:</span></span>

<span data-ttu-id="e8c85-137">Preparar:</span><span class="sxs-lookup"><span data-stu-id="e8c85-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8c85-138">Saiba mais sobre os fundamentos de infraestrutura para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8c85-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="e8c85-139">Saiba mais sobre o Azure AD e configurar um se você&#39;o tiver.</span><span class="sxs-lookup"><span data-stu-id="e8c85-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="e8c85-140">Saiba mais sobre o Gerenciamento de identidades e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e8c85-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="e8c85-141">Saiba mais sobre o MDM e configurar com o Intune se&#39;ainda não tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="e8c85-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="e8c85-142">Saiba mais sobre os requisitos de rede do Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="e8c85-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="e8c85-143">Opcionalmente: VPN para se conectar a recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="e8c85-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="e8c85-144">Configurar:</span><span class="sxs-lookup"><span data-stu-id="e8c85-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8c85-145">Como criar Usuários e Grupos.</span><span class="sxs-lookup"><span data-stu-id="e8c85-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="e8c85-146">Como configurar o registro automático no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e8c85-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="e8c85-147">Como atribuir suas licenças de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8c85-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="e8c85-148">Implantar:</span><span class="sxs-lookup"><span data-stu-id="e8c85-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8c85-149">Configurar seu HoloLens 2 e validar o registro.</span><span class="sxs-lookup"><span data-stu-id="e8c85-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="e8c85-150">Valide se você pode fazer uma chamada de Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="e8c85-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="e8c85-151">Manter:</span><span class="sxs-lookup"><span data-stu-id="e8c85-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8c85-152">Como atualizar o Remote Assist usando o Microsoft Store aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8c85-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="e8c85-153">Como criar um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="e8c85-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="e8c85-154">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="e8c85-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="e8c85-155">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e8c85-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e8c85-156">Implantação conectada à nuvem – Preparar</span><span class="sxs-lookup"><span data-stu-id="e8c85-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

