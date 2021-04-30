---
title: Guia de implantação – o HoloLens conectado corporativo 2 com guias do Dynamics 365-visão geral
description: Saiba como registrar dispositivos do HoloLens 2 com os guias do Dynamics 365 em uma rede corporativa conectada.
keywords: HoloLens, gerenciamento, corporativo conectado, guias do Dynamics 365, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308225"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="68449-104">Guia de implantação-instalação corporativa do HoloLens 2 com guias do Dynamics 365-visão geral</span><span class="sxs-lookup"><span data-stu-id="68449-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="68449-105">Este guia ajudará os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 com guias (guias) do Dynamics 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68449-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="68449-106">Este guia é ótimo para pilotos, bem como para implantações de produção e é semelhante ao [cenário B: implantar dentro do guia de rede da sua organização](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) .</span><span class="sxs-lookup"><span data-stu-id="68449-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="68449-107">Depois de testar sua prova de conceito, use este guia para avançar com a integração do HoloLens à sua organização.</span><span class="sxs-lookup"><span data-stu-id="68449-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="68449-108">Neste guia, abordaremos como registrar seus dispositivos em seu gerenciamento de dispositivo existente, aplicar licenças conforme necessário e validar que os usuários finais podem operar um guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68449-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="68449-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="68449-109">Prerequisites</span></span>

<span data-ttu-id="68449-110">A infraestrutura a seguir já deve estar em vigor:</span><span class="sxs-lookup"><span data-stu-id="68449-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="68449-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="68449-111">Wi-Fi</span></span>
    - <span data-ttu-id="68449-112">Rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="68449-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="68449-113">Autenticação de certificado baseada em dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68449-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="68449-114">Junção do Azure Active Directory (Azure AD) com o registro automático[do MDM (assinatura do Azure ad P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) necessária)</span><span class="sxs-lookup"><span data-stu-id="68449-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="68449-115">MDM (Intune) gerenciado</span><span class="sxs-lookup"><span data-stu-id="68449-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="68449-116">Um ou mais aplicativos são implantados por meio do MDM.</span><span class="sxs-lookup"><span data-stu-id="68449-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="68449-117">Rede</span><span class="sxs-lookup"><span data-stu-id="68449-117">Network</span></span> 
    - <span data-ttu-id="68449-118">Certificados (SCEP ou PKCS)</span><span class="sxs-lookup"><span data-stu-id="68449-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="68449-119">Configuração de proxy</span><span class="sxs-lookup"><span data-stu-id="68449-119">Proxy configuration</span></span>
- <span data-ttu-id="68449-120">Os usuários entram com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="68449-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="68449-121">Há suporte para um ou vários usuários por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68449-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="68449-122">Níveis variados de configurações de bloqueio de dispositivo aplicadas com base em casos de uso específicos, de totalmente aberto para quiosque de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="68449-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="68449-123">Guia de licenciamento e requisitos</span><span class="sxs-lookup"><span data-stu-id="68449-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="68449-124">Conta do AD do Azure</span><span class="sxs-lookup"><span data-stu-id="68449-124">Azure AD account</span></span>
- <span data-ttu-id="68449-125">Dynamics 365 orienta aplicativos PC e HoloLens</span><span class="sxs-lookup"><span data-stu-id="68449-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="68449-126">Assinatura de guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="68449-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="68449-127">Microsoft dataverso (incluído)</span><span class="sxs-lookup"><span data-stu-id="68449-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="68449-128">Power apps (incluído)</span><span class="sxs-lookup"><span data-stu-id="68449-128">Power Apps (included)</span></span>
- <span data-ttu-id="68449-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="68449-129">Power BI Desktop</span></span>
- <span data-ttu-id="68449-130">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="68449-130">Network Connectivity</span></span>

![Diagrama de rede conectada Corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="68449-132">Estágios da implantação</span><span class="sxs-lookup"><span data-stu-id="68449-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="68449-133">Preparar</span><span class="sxs-lookup"><span data-stu-id="68449-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="68449-134">Saiba mais sobre os conceitos básicos de infraestrutura para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="68449-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="68449-135">Saiba mais sobre o Azure AD e configure um se você não o tiver.</span><span class="sxs-lookup"><span data-stu-id="68449-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="68449-136">Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="68449-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="68449-137">Saiba mais sobre o MDM e configure-o com o Intune se você ainda não tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="68449-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="68449-138">Familiarize-se com Wi-Fi baseado em certificado.</span><span class="sxs-lookup"><span data-stu-id="68449-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="68449-139">Familiarize-se com o proxy.</span><span class="sxs-lookup"><span data-stu-id="68449-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="68449-140">Entenda como você pode usar aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="68449-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="68449-141">Saiba mais sobre como você pode usar guias para sua organização.</span><span class="sxs-lookup"><span data-stu-id="68449-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="68449-142">Configurar</span><span class="sxs-lookup"><span data-stu-id="68449-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="68449-143">Como criar usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="68449-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="68449-144">Como configurar o registro automático.</span><span class="sxs-lookup"><span data-stu-id="68449-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="68449-145">Como configurar Wi-Fi certificados e perfis para conectividade Wi-Fi corporativa.</span><span class="sxs-lookup"><span data-stu-id="68449-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="68449-146">Carregar e atribuir pacotes de aplicativos de linha de negócios (LOB).</span><span class="sxs-lookup"><span data-stu-id="68449-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="68449-147">Configurar guias do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="68449-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="68449-148">Como configurar o modo de quiosque (opcional).</span><span class="sxs-lookup"><span data-stu-id="68449-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="68449-149">Como configurar o WDAC (opcional).</span><span class="sxs-lookup"><span data-stu-id="68449-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="68449-150">Implantar</span><span class="sxs-lookup"><span data-stu-id="68449-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="68449-151">Valide o registro por meio do dispositivo e do MDM.</span><span class="sxs-lookup"><span data-stu-id="68449-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="68449-152">Validar Wi-Fi certificados.</span><span class="sxs-lookup"><span data-stu-id="68449-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="68449-153">Valide a instalação do aplicativo de LOB.</span><span class="sxs-lookup"><span data-stu-id="68449-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="68449-154">Valide os guias por meio de criação e operação.</span><span class="sxs-lookup"><span data-stu-id="68449-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="68449-155">Manter</span><span class="sxs-lookup"><span data-stu-id="68449-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="68449-156">Atualize o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="68449-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="68449-157">Como atualizar guias (aplicativos da loja).</span><span class="sxs-lookup"><span data-stu-id="68449-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="68449-158">Como atualizar aplicativos LOB.</span><span class="sxs-lookup"><span data-stu-id="68449-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="68449-159">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="68449-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="68449-160">Fazendo um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="68449-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="68449-161">Opções de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68449-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="68449-162">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="68449-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="68449-163">Implantação conectada corporativa-preparar</span><span class="sxs-lookup"><span data-stu-id="68449-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
