---
title: Visão geral do HoloLens 2 conectado à nuvem com Assistência Remota
description: Saiba como registrar dispositivos do HoloLens 2 em uma rede conectada à nuvem usando a Assistência Remota do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.openlocfilehash: 835b4be101b665d2b86c2170a65c04697686e403
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283072"
---
# <span data-ttu-id="21f50-104">Guia de Implantação – HoloLens 2 conectado à nuvem com Assistência Remota – Visão geral</span><span class="sxs-lookup"><span data-stu-id="21f50-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="21f50-105">Este guia ajuda os profissionais de TI a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com o objetivo geral de ter esses dispositivos conectados à nuvem em sua organização com a Assistência Remota do Dynamics 365 pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="21f50-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="21f50-106">Lembre-se de que isso servirá como modelo para implantações de prova de conceito em sua organização em uma variedade de casos de uso do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="21f50-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="21f50-107">Durante o guia, vamos falar sobre como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="21f50-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="21f50-108">Para fazer isso, vamos passar por cima das partes importantes da infraestrutura necessária para configurar e executar – alcançando a implantação em escala com o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="21f50-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="21f50-109">Neste guia</span><span class="sxs-lookup"><span data-stu-id="21f50-109">In this Guide</span></span>

<span data-ttu-id="21f50-110">Este guia tem o objetivo específico de configurar a Assistência Remota dentro de sua organização em seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21f50-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="21f50-111">Vamos abranger as necessidades necessárias para atingir essa meta.</span><span class="sxs-lookup"><span data-stu-id="21f50-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="21f50-112">Para manter o foco nesse objetivo, determinadas configurações e preparação serão pré-selecionadas para otimizar essa implantação ou reduzir os itens necessários à configuração.</span><span class="sxs-lookup"><span data-stu-id="21f50-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="21f50-113">Você será informado dessas opções e poderá personalizar sua implantação com base em suas necessidades de negócios.</span><span class="sxs-lookup"><span data-stu-id="21f50-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="21f50-114">Esta é uma configuração semelhante ao Cenário [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implantar em dispositivos conectados à nuvem, que é uma boa opção para muitas implantações de Prova de Conceito, que incluirão:</span><span class="sxs-lookup"><span data-stu-id="21f50-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="21f50-115">Wi-Fi redes são normalmente totalmente abertas para os serviços de Nuvem e Internet</span><span class="sxs-lookup"><span data-stu-id="21f50-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="21f50-116">Ingressar no Azure AD com o registro automático do MDM – MDM (Intune) gerenciado</span><span class="sxs-lookup"><span data-stu-id="21f50-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="21f50-117">Os usuários podem entrar com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="21f50-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="21f50-118">Um ou vários usuários por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="21f50-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="21f50-119">Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto a Quiosque de Aplicativo Único</span><span class="sxs-lookup"><span data-stu-id="21f50-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Cenário conectado à nuvem](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="21f50-121">Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, no entanto, recomendamos que você explore essas opções após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="21f50-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="21f50-122">Saiba mais sobre a Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="21f50-122">Learn about Remote Assist</span></span>

<span data-ttu-id="21f50-123">A Assistência Remota permite manutenção e reparo colaborativos, inspeção remota, bem como compartilhamento e treinamento de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="21f50-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="21f50-124">Conectando pessoas em diferentes funções e locais, um técnico que usa a Assistência Remota pode se conectar a um colaborador remoto no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="21f50-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="21f50-125">Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando&#39;estão no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="21f50-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="21f50-126">Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis que o técnico&#39;no espaço físico para que possam se referir ao esquema enquanto trabalham de cabeça para cima e sem mãos no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21f50-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="21f50-127">Neste guia, você irá:</span><span class="sxs-lookup"><span data-stu-id="21f50-127">In this guide you will:</span></span>

<span data-ttu-id="21f50-128">Prepare:</span><span class="sxs-lookup"><span data-stu-id="21f50-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21f50-129">Saiba mais sobre as noções básicas de infraestrutura para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="21f50-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="21f50-130">Saiba mais sobre o Azure AD e configurar um caso&#39;não o tenha.</span><span class="sxs-lookup"><span data-stu-id="21f50-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="21f50-131">Saiba mais sobre o gerenciamento de identidades e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="21f50-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="21f50-132">Saiba mais sobre o MDM e prepare-se com o Intune&#39;já tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="21f50-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="21f50-133">Saiba mais sobre os requisitos de rede da Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="21f50-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="21f50-134">Opcionalmente: VPN para se conectar a recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="21f50-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="21f50-135">Configure:</span><span class="sxs-lookup"><span data-stu-id="21f50-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21f50-136">Como criar Usuários e Grupos.</span><span class="sxs-lookup"><span data-stu-id="21f50-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="21f50-137">Como configurar o registro automático no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="21f50-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="21f50-138">Como atribuir suas licenças de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="21f50-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="21f50-139">Implantar:</span><span class="sxs-lookup"><span data-stu-id="21f50-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21f50-140">Configurar seu HoloLens 2 e validar o registro.</span><span class="sxs-lookup"><span data-stu-id="21f50-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="21f50-141">Valide se você pode fazer uma chamada de Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="21f50-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="21f50-142">Mantenha:</span><span class="sxs-lookup"><span data-stu-id="21f50-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="21f50-143">Como atualizar a Assistência Remota usando o aplicativo da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="21f50-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="21f50-144">Como criar um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="21f50-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="21f50-145">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="21f50-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="21f50-146">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="21f50-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="21f50-147">Implantação conectada à nuvem - Preparar</span><span class="sxs-lookup"><span data-stu-id="21f50-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

