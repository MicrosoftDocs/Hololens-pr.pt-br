---
title: Guia de Implantação – HoloLens 2 conectado corporativo com guias do Dynamics 365 - Visão geral
description: Saiba como registrar dispositivos do HoloLens 2 com Guias do Dynamics 365 em uma rede conectada corporativa.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448501"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="7c299-104">Guia de Implantação - HoloLens 2 conectado corporativo com guias do Dynamics 365 - Visão geral</span><span class="sxs-lookup"><span data-stu-id="7c299-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="7c299-105">Este guia ajudará os profissionais de TI a planejar e implantar dispositivos do Microsoft HoloLens 2 com Guias do Dynamics 365 (Guias) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7c299-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="7c299-106">Este guia é ótimo para pilotos, bem como implantações de produção e é semelhante ao [Cenário B: Implantar dentro](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) do guia de rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7c299-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="7c299-107">Depois de testar sua prova de conceito, use este guia para seguir em frente com a integração do HoloLens à sua organização.</span><span class="sxs-lookup"><span data-stu-id="7c299-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="7c299-108">Neste guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos existente, aplicar licenças conforme necessário e validar se os usuários finais podem operar um Guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados, após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7c299-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="7c299-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7c299-109">Prerequisites</span></span>

<span data-ttu-id="7c299-110">A seguinte infraestrutura já deve estar em uso:</span><span class="sxs-lookup"><span data-stu-id="7c299-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="7c299-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7c299-111">Wi-Fi</span></span>
    - <span data-ttu-id="7c299-112">Rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou serviços de Nuvem</span><span class="sxs-lookup"><span data-stu-id="7c299-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="7c299-113">Autenticação de certificado baseada em dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7c299-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="7c299-114">Azure Active Directory (Azure AD) Ingressar no Registro Automático do MDM ( assinatura do[Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) necessária)</span><span class="sxs-lookup"><span data-stu-id="7c299-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="7c299-115">MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="7c299-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="7c299-116">Um ou mais aplicativos são implantados por meio do MDM.</span><span class="sxs-lookup"><span data-stu-id="7c299-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="7c299-117">Rede</span><span class="sxs-lookup"><span data-stu-id="7c299-117">Network</span></span> 
    - <span data-ttu-id="7c299-118">Certificados (SCEP ou PKCS)</span><span class="sxs-lookup"><span data-stu-id="7c299-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="7c299-119">Configuração proxy</span><span class="sxs-lookup"><span data-stu-id="7c299-119">Proxy configuration</span></span>
- <span data-ttu-id="7c299-120">Os usuários entrar com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7c299-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="7c299-121">Há suporte para usuários simples ou múltiplos por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7c299-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="7c299-122">Níveis variáveis de configurações de bloqueio de dispositivo aplicadas com base em casos de uso específicos, de Totalmente Aberto a Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="7c299-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="7c299-123">Guias de licenciamento e requisitos</span><span class="sxs-lookup"><span data-stu-id="7c299-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="7c299-124">Conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c299-124">Azure AD account</span></span>
- <span data-ttu-id="7c299-125">Guias do Dynamics 365 aplicativos pc e HoloLens</span><span class="sxs-lookup"><span data-stu-id="7c299-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="7c299-126">Assinatura de Guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="7c299-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="7c299-127">Microsoft Dataverse (incluído)</span><span class="sxs-lookup"><span data-stu-id="7c299-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="7c299-128">Power Apps (incluído)</span><span class="sxs-lookup"><span data-stu-id="7c299-128">Power Apps (included)</span></span>
- <span data-ttu-id="7c299-129">Área de trabalho do Power BI</span><span class="sxs-lookup"><span data-stu-id="7c299-129">Power BI Desktop</span></span>
- <span data-ttu-id="7c299-130">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="7c299-130">Network Connectivity</span></span>

![Diagrama de rede conectado Corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="7c299-132">Estágios de implantação</span><span class="sxs-lookup"><span data-stu-id="7c299-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="7c299-133">Preparar</span><span class="sxs-lookup"><span data-stu-id="7c299-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="7c299-134">Saiba mais sobre os elementos essenciais de infraestrutura para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7c299-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="7c299-135">Saiba mais sobre o Azure AD e configurar um caso não o tenha.</span><span class="sxs-lookup"><span data-stu-id="7c299-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="7c299-136">Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7c299-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="7c299-137">Saiba mais sobre o MDM e configurar com o Intune se você ainda não tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="7c299-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="7c299-138">Familiarize-se com o Wi-Fi baseado em certificado.</span><span class="sxs-lookup"><span data-stu-id="7c299-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="7c299-139">Familiarize-se com Proxy.</span><span class="sxs-lookup"><span data-stu-id="7c299-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="7c299-140">Entenda como você pode usar Aplicativos de Linha de Negócios.</span><span class="sxs-lookup"><span data-stu-id="7c299-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="7c299-141">Saiba mais sobre a maneira como você pode usar Guias para sua organização.</span><span class="sxs-lookup"><span data-stu-id="7c299-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="7c299-142">Configurar</span><span class="sxs-lookup"><span data-stu-id="7c299-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="7c299-143">Como criar usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="7c299-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="7c299-144">Como configurar o Registro Automático.</span><span class="sxs-lookup"><span data-stu-id="7c299-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="7c299-145">Como configurar Wi-Fi certificados e perfis corporativos Wi-Fi Conectividade.</span><span class="sxs-lookup"><span data-stu-id="7c299-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="7c299-146">Carregar e atribuir pacotes de aplicativos de Linha de Negócios (LOB).</span><span class="sxs-lookup"><span data-stu-id="7c299-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="7c299-147">Setup Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="7c299-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="7c299-148">Como configurar o Modo de Quiosque (opcional).</span><span class="sxs-lookup"><span data-stu-id="7c299-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="7c299-149">Como configurar o WDAC (opcional).</span><span class="sxs-lookup"><span data-stu-id="7c299-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="7c299-150">Implantar</span><span class="sxs-lookup"><span data-stu-id="7c299-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="7c299-151">Validar o registro por meio de dispositivo e MDM.</span><span class="sxs-lookup"><span data-stu-id="7c299-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="7c299-152">Validar Wi-Fi certificados.</span><span class="sxs-lookup"><span data-stu-id="7c299-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="7c299-153">Validar a instalação do aplicativo LOB.</span><span class="sxs-lookup"><span data-stu-id="7c299-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="7c299-154">Valide guias por meio da autoria e da operação.</span><span class="sxs-lookup"><span data-stu-id="7c299-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="7c299-155">Manter</span><span class="sxs-lookup"><span data-stu-id="7c299-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="7c299-156">Atualizar o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7c299-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="7c299-157">Como atualizar Guias (aplicativos de armazenamento).</span><span class="sxs-lookup"><span data-stu-id="7c299-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="7c299-158">Como atualizar aplicativos LOB.</span><span class="sxs-lookup"><span data-stu-id="7c299-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="7c299-159">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="7c299-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="7c299-160">Fazendo um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="7c299-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="7c299-161">Opções de gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7c299-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="7c299-162">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7c299-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="7c299-163">Implantação conectada corporativa - Preparar</span><span class="sxs-lookup"><span data-stu-id="7c299-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
