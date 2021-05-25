---
title: Visão geral do HoloLens 2 conectado à nuvem com Assistência Remota
description: Saiba como registrar dispositivos HoloLens 2 em uma rede conectada à nuvem usando o Dynamics 365 Remote Assist.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Dispositivos móveis Gerenciamento de Dispositivos
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397647"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="ef85b-104">Guia de implantação – HoloLens 2 conectado à nuvem com Assistência Remota – Visão geral</span><span class="sxs-lookup"><span data-stu-id="ef85b-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="ef85b-105">Este guia ajuda os profissionais de TI a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com a meta geral de ter esses dispositivos conectados à nuvem à sua organização com o Dynamics 365 Remote Assist pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="ef85b-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="ef85b-106">Tenha em mente que isso servirá como um modelo para implantações de prova de conceito em sua organização em uma variedade de casos de uso do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ef85b-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="ef85b-107">Durante o guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ef85b-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="ef85b-108">Para fazer isso, vamos falar sobre as partes importantes da infraestrutura necessárias para se configurar e executar – alcançando a implantação em escala com o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ef85b-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="ef85b-109">[![Cenário conectado à nuvem ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ef85b-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="ef85b-110">Neste guia</span><span class="sxs-lookup"><span data-stu-id="ef85b-110">In this Guide</span></span>

<span data-ttu-id="ef85b-111">Este guia tem a meta específica de configurar o Remote Assist em sua organização em seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ef85b-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="ef85b-112">Vamos abranger as necessidades necessárias para atingir essa meta.</span><span class="sxs-lookup"><span data-stu-id="ef85b-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="ef85b-113">Para manter o foco nessa meta, determinadas configurações e preparação serão pré-selecionadas para otimizar essa implantação ou reduzir os itens necessários para configurar.</span><span class="sxs-lookup"><span data-stu-id="ef85b-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="ef85b-114">Você será informado dessas opções e poderá personalizar sua implantação com base em suas necessidades de negócios.</span><span class="sxs-lookup"><span data-stu-id="ef85b-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="ef85b-115">Essa é uma configuração semelhante ao Cenário [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implantar em dispositivos de conexão de nuvem, que é uma boa opção para muitas implantações de Prova de Conceito, que incluirão:</span><span class="sxs-lookup"><span data-stu-id="ef85b-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="ef85b-116">Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e nuvem</span><span class="sxs-lookup"><span data-stu-id="ef85b-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="ef85b-117">Ingressar no Azure AD com Registro Automático do MDM – MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="ef85b-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="ef85b-118">Os usuários entrarão com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ef85b-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="ef85b-119">Usuários individuais ou múltiplos por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="ef85b-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="ef85b-120">Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente aberto para quiosque de aplicativo único</span><span class="sxs-lookup"><span data-stu-id="ef85b-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="ef85b-121">Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, no entanto, recomendamos que você explore essas opções após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="ef85b-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="ef85b-122">Saiba mais sobre o auxílio remoto</span><span class="sxs-lookup"><span data-stu-id="ef85b-122">Learn about Remote Assist</span></span>

<span data-ttu-id="ef85b-123">A assistência remota permite a manutenção e o reparo colaborativos, a inspeção remota, bem como o compartilhamento e o treinamento de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="ef85b-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="ef85b-124">Ao conectar pessoas em diferentes funções e locais, um técnico usando a assistência remota pode se conectar com um colaborador remoto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ef85b-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="ef85b-125">Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando estiverem des&#39;no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="ef85b-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="ef85b-126">Os colaboradores remotos podem inserir imagens de referência, esquemáticos e outras informações úteis que o técnico&#39;o espaço físico de forma que ele possa se referir ao esquema enquanto trabalha com as cabeças de trabalho e as mãos do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ef85b-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="ef85b-127">Neste guia, você:</span><span class="sxs-lookup"><span data-stu-id="ef85b-127">In this guide you will:</span></span>

<span data-ttu-id="ef85b-128">Preparar:</span><span class="sxs-lookup"><span data-stu-id="ef85b-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ef85b-129">Saiba mais sobre os conceitos básicos de infraestrutura para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ef85b-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="ef85b-130">Saiba mais sobre o Azure AD e configure um se você não&#39;o tiver.</span><span class="sxs-lookup"><span data-stu-id="ef85b-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="ef85b-131">Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ef85b-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="ef85b-132">Saiba mais sobre o MDM e configure-o com o Intune se você não&#39;t já tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="ef85b-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="ef85b-133">Saiba mais sobre os requisitos de rede do auxílio remoto.</span><span class="sxs-lookup"><span data-stu-id="ef85b-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="ef85b-134">Opcionalmente: VPN para se conectar aos recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="ef85b-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="ef85b-135">Configurar:</span><span class="sxs-lookup"><span data-stu-id="ef85b-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ef85b-136">Como criar usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="ef85b-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="ef85b-137">Como configurar o registro automático no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ef85b-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="ef85b-138">Como atribuir suas licenças de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ef85b-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="ef85b-139">Implantar:</span><span class="sxs-lookup"><span data-stu-id="ef85b-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ef85b-140">Configure seu HoloLens 2 e valide o registro.</span><span class="sxs-lookup"><span data-stu-id="ef85b-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="ef85b-141">Validar você pode fazer uma chamada de assistência remota.</span><span class="sxs-lookup"><span data-stu-id="ef85b-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="ef85b-142">Manter:</span><span class="sxs-lookup"><span data-stu-id="ef85b-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ef85b-143">Como atualizar a assistência remota usando o aplicativo Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ef85b-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="ef85b-144">Fazendo um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="ef85b-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="ef85b-145">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="ef85b-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="ef85b-146">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ef85b-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ef85b-147">Implantação conectada à nuvem – Preparar</span><span class="sxs-lookup"><span data-stu-id="ef85b-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

