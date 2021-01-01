---
title: Guia de implantação – HoloLens conectado à nuvem 2 com assistência remota-visão geral
description: Registrar dispositivos HoloLens em uma rede conectada na nuvem
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
ms.openlocfilehash: 7d954347c7c274b844d436c0d6fc96e8bbc59f10
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253178"
---
# <span data-ttu-id="145aa-104">Guia de implantação – HoloLens conectado à nuvem 2 com assistência remota – visão geral</span><span class="sxs-lookup"><span data-stu-id="145aa-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="145aa-105">Este guia ajudará os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com o objetivo geral de ter esses dispositivos em nuvem conectada à sua organização com a assistência remota do Dynamics 365 pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="145aa-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="145aa-106">Tenha em mente que isso servirá como um modelo para implantações de prova de conceito em sua organização em diversos casos de uso do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="145aa-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="145aa-107">Durante o guia, abordaremos como registrar seus dispositivos em seu gerenciamento de dispositivos, aplicar licenças conforme necessário e validar que os usuários finais podem usar imediatamente a assistência remota na instalação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="145aa-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="145aa-108">Para isso, veremos as importantes partes da infraestrutura necessárias para a configuração e a execução: obtendo implantação em escala com o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="145aa-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="145aa-109">Neste guia</span><span class="sxs-lookup"><span data-stu-id="145aa-109">In this Guide</span></span>

<span data-ttu-id="145aa-110">Este guia tem o objetivo específico de configurar o auxílio remoto dentro de sua organização em seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="145aa-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="145aa-111">Abordaremos a Necessities necessária para atingir essa meta.</span><span class="sxs-lookup"><span data-stu-id="145aa-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="145aa-112">Para manter o foco nessa meta, certas preparações e configurações serão previamente selecionadas para otimizar essa implantação ou para reduzir os itens necessários para a configuração.</span><span class="sxs-lookup"><span data-stu-id="145aa-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="145aa-113">Você será informado sobre essas opções e poderá personalizar a implantação com base nas necessidades da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="145aa-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="145aa-114">Isso é uma configuração semelhante ao [cenário a: implantar em dispositivos de conexão em nuvem](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que é uma boa opção para várias implantações de comprovação de conceito, que inclui:</span><span class="sxs-lookup"><span data-stu-id="145aa-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="145aa-115">As redes Wi-Fi geralmente são totalmente abertas para os serviços de nuvem e Internet</span><span class="sxs-lookup"><span data-stu-id="145aa-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="145aa-116">Ingressar no Azure AD com o registro automático do MDM--gerenciamento de MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="145aa-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="145aa-117">Os usuários entram com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="145aa-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="145aa-118">Suporte para um ou vários usuários por dispositivo</span><span class="sxs-lookup"><span data-stu-id="145aa-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="145aa-119">Os níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do quiosque totalmente aberto para um único aplicativo.</span><span class="sxs-lookup"><span data-stu-id="145aa-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Cenário conectado na nuvem](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="145aa-121">Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, mas incentivamos você a explorar essas opções após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="145aa-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="145aa-122">Saiba mais sobre a assistência remota</span><span class="sxs-lookup"><span data-stu-id="145aa-122">Learn about Remote Assist</span></span>

<span data-ttu-id="145aa-123">A assistência remota permite a manutenção e o reparo colaborativo, a inspeção remota, bem como o compartilhamento e o treinamento de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="145aa-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="145aa-124">Ao conectar pessoas em diferentes funções e locais, um técnico usando o recurso assistência remota pode se conectar com um colaborador remoto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="145aa-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="145aa-125">Elas podem combinar vídeos, capturas de tela e anotações para solucionar problemas em tempo real, mesmo quando não estiverem&#39;no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="145aa-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="145aa-126">Os colaboradores remotos podem inserir imagens de referência, esquemáticos e outras informações úteis que o técnico&#39;espaço físico para que ele possa se referir ao esquema enquanto estiver trabalhando e viva-se de mão livre no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="145aa-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="145aa-127">Neste guia, você vai:</span><span class="sxs-lookup"><span data-stu-id="145aa-127">In this guide you will:</span></span>

<span data-ttu-id="145aa-128">Pare</span><span class="sxs-lookup"><span data-stu-id="145aa-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="145aa-129">Saiba mais sobre os recursos básicos de infraestrutura para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="145aa-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="145aa-130">Saiba mais sobre o Azure AD e configure um se não&#39;o tiver.</span><span class="sxs-lookup"><span data-stu-id="145aa-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="145aa-131">Saiba mais sobre o gerenciamento de identidades e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="145aa-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="145aa-132">Saiba mais sobre o MDM e configure o Intune se você não&#39;já tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="145aa-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="145aa-133">Saiba mais sobre os requisitos de rede da assistência remota.</span><span class="sxs-lookup"><span data-stu-id="145aa-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="145aa-134">Opcionalmente: VPN para se conectar a recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="145aa-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="145aa-135">Configuração</span><span class="sxs-lookup"><span data-stu-id="145aa-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="145aa-136">Como criar usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="145aa-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="145aa-137">Como configurar o registro automático no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="145aa-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="145aa-138">Como atribuir suas licenças de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="145aa-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="145aa-139">Implementar</span><span class="sxs-lookup"><span data-stu-id="145aa-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="145aa-140">Configure seu HoloLens 2 e valide o registro.</span><span class="sxs-lookup"><span data-stu-id="145aa-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="145aa-141">Validar você pode fazer uma chamada de assistência remota.</span><span class="sxs-lookup"><span data-stu-id="145aa-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="145aa-142">Atualize</span><span class="sxs-lookup"><span data-stu-id="145aa-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="145aa-143">Como atualizar a assistência remota usando o aplicativo da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="145aa-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="145aa-144">Como criar um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="145aa-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="145aa-145">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="145aa-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="145aa-146">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="145aa-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="145aa-147">Implantação conectada na nuvem-preparação</span><span class="sxs-lookup"><span data-stu-id="145aa-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

