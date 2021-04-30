---
title: Visão geral do HoloLens 2 conectado à nuvem com o auxílio remoto
description: Saiba como registrar dispositivos do HoloLens 2 em uma rede conectada na nuvem usando o assistente remoto do Dynamics 365.
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308043"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="ee4b5-104">Guia de implantação – nuvem conectada no Cloud 2 com assistência remota – visão geral</span><span class="sxs-lookup"><span data-stu-id="ee4b5-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="ee4b5-105">Este guia ajuda os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com o objetivo geral de ter esses dispositivos na nuvem conectados à sua organização com o auxílio remoto do Dynamics 365 pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="ee4b5-106">Tenha em mente que isso servirá como um modelo para implantações de prova de conceito em sua organização em vários casos de uso de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="ee4b5-107">Durante o guia, abordaremos como registrar seus dispositivos em seu gerenciamento de dispositivo, aplicar licenças conforme necessário e validar que os usuários finais podem usar o assistência remota imediatamente após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="ee4b5-108">Para fazer isso, veremos as importantes partes da infraestrutura necessária para a configuração e a execução – alcançando a implantação em escala com o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![Faixa conectada na nuvem](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a><span data-ttu-id="ee4b5-110">Neste guia</span><span class="sxs-lookup"><span data-stu-id="ee4b5-110">In this Guide</span></span>

<span data-ttu-id="ee4b5-111">Este guia tem o objetivo específico de configurar o auxílio remoto em sua organização em seus dispositivos de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="ee4b5-112">Abordaremos o necessidades necessário para atingir essa meta.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="ee4b5-113">Para manter o foco nessa meta, certas preparações e configurações serão previamente selecionadas para otimizar essa implantação ou para reduzir os itens necessários para a configuração.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="ee4b5-114">Você será informado dessas opções e poderá personalizar sua implantação com base nas suas necessidades de negócios.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="ee4b5-115">Essa é uma configuração semelhante ao [cenário a: implantar em dispositivos do Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implantações de prova de conceito, que incluirá:</span><span class="sxs-lookup"><span data-stu-id="ee4b5-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="ee4b5-116">As redes Wi-Fi normalmente são totalmente abertas na Internet e nos serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="ee4b5-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="ee4b5-117">Ingresso no Azure AD com o registro automático do MDM--MDM (Intune) gerenciado</span><span class="sxs-lookup"><span data-stu-id="ee4b5-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="ee4b5-118">Os usuários entram com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ee4b5-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="ee4b5-119">Um ou vários usuários por dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="ee4b5-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="ee4b5-120">Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente aberto para quiosque de aplicativo único</span><span class="sxs-lookup"><span data-stu-id="ee4b5-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Cenário conectado à nuvem](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="ee4b5-122">Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, no entanto, recomendamos que você explore essas opções após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="ee4b5-123">Saiba mais sobre o auxílio remoto</span><span class="sxs-lookup"><span data-stu-id="ee4b5-123">Learn about Remote Assist</span></span>

<span data-ttu-id="ee4b5-124">A assistência remota permite a manutenção e o reparo colaborativos, a inspeção remota, bem como o compartilhamento e o treinamento de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="ee4b5-125">Ao conectar pessoas em diferentes funções e locais, um técnico usando a assistência remota pode se conectar com um colaborador remoto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="ee4b5-126">Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando estiverem des&#39;no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="ee4b5-127">Os colaboradores remotos podem inserir imagens de referência, esquemáticos e outras informações úteis que o técnico&#39;o espaço físico de forma que ele possa se referir ao esquema enquanto trabalha com as cabeças de trabalho e as mãos do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="ee4b5-128">Neste guia, você:</span><span class="sxs-lookup"><span data-stu-id="ee4b5-128">In this guide you will:</span></span>

<span data-ttu-id="ee4b5-129">Preparar:</span><span class="sxs-lookup"><span data-stu-id="ee4b5-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ee4b5-130">Saiba mais sobre os conceitos básicos de infraestrutura para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="ee4b5-131">Saiba mais sobre o Azure AD e configure um se você não&#39;o tiver.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="ee4b5-132">Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="ee4b5-133">Saiba mais sobre o MDM e configure-o com o Intune se você não&#39;t já tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="ee4b5-134">Saiba mais sobre os requisitos de rede do auxílio remoto.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="ee4b5-135">Opcionalmente: VPN para se conectar aos recursos organizacionais</span><span class="sxs-lookup"><span data-stu-id="ee4b5-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="ee4b5-136">Configurar:</span><span class="sxs-lookup"><span data-stu-id="ee4b5-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ee4b5-137">Como criar usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="ee4b5-138">Como configurar o registro automático no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="ee4b5-139">Como atribuir suas licenças de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="ee4b5-140">Implantar:</span><span class="sxs-lookup"><span data-stu-id="ee4b5-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ee4b5-141">Configure seu HoloLens 2 e valide o registro.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="ee4b5-142">Validar você pode fazer uma chamada de assistência remota.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="ee4b5-143">Manter:</span><span class="sxs-lookup"><span data-stu-id="ee4b5-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ee4b5-144">Como atualizar a assistência remota usando o aplicativo Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="ee4b5-145">Fazendo um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="ee4b5-146">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="ee4b5-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="ee4b5-147">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ee4b5-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ee4b5-148">Implantação conectada na nuvem-preparar</span><span class="sxs-lookup"><span data-stu-id="ee4b5-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

