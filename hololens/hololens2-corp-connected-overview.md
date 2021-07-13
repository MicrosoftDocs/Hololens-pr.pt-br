---
title: Guia de implantação – Guia de implantação HoloLens 2 com Guias do Dynamics 365 – Visão geral
description: Saiba como registrar HoloLens 2 dispositivos com o Dynamics 365 Guides em uma rede conectada corporativa.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637006"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="32b18-104">Guia de implantação – Corporate Connected HoloLens 2 com Guias do Dynamics 365 – Visão geral</span><span class="sxs-lookup"><span data-stu-id="32b18-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="32b18-105">Este guia ajudará os profissionais de TI a planejar e implantar Microsoft HoloLens 2 dispositivos com Guias do Dynamics 365 (Guias) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="32b18-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="32b18-106">Este guia é ótimo para piloto, bem como implantações de produção e é semelhante ao Cenário [B: Implantar dentro](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) do guia de rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="32b18-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="32b18-107">Depois de testar sua prova de conceito, use este guia para avançar com a integração HoloLens em sua organização.</span><span class="sxs-lookup"><span data-stu-id="32b18-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="32b18-108">Neste guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos existente, aplicar licenças conforme necessário e validar se os usuários finais podem operar um Guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados após a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="32b18-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="32b18-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="32b18-109">Prerequisites</span></span>

<span data-ttu-id="32b18-110">A seguinte infraestrutura já deve estar em uso:</span><span class="sxs-lookup"><span data-stu-id="32b18-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="32b18-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="32b18-111">Wi-Fi</span></span>
    - <span data-ttu-id="32b18-112">Rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="32b18-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="32b18-113">Autenticação de certificado baseada em dispositivo.</span><span class="sxs-lookup"><span data-stu-id="32b18-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="32b18-114">Azure Active Directory (Azure AD) Ingressar com o Registro Automático do MDM[(assinatura do Azure AD P1](/azure/active-directory/fundamentals/active-directory-whatis) necessária)</span><span class="sxs-lookup"><span data-stu-id="32b18-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="32b18-115">MDM (Intune) Gerenciado</span><span class="sxs-lookup"><span data-stu-id="32b18-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="32b18-116">Um ou mais aplicativos são implantados por meio do MDM.</span><span class="sxs-lookup"><span data-stu-id="32b18-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="32b18-117">Rede</span><span class="sxs-lookup"><span data-stu-id="32b18-117">Network</span></span> 
    - <span data-ttu-id="32b18-118">Certificados (SCEP ou PKCS)</span><span class="sxs-lookup"><span data-stu-id="32b18-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="32b18-119">Configuração de Proxy</span><span class="sxs-lookup"><span data-stu-id="32b18-119">Proxy configuration</span></span>
- <span data-ttu-id="32b18-120">Os usuários entrarão com sua própria conta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="32b18-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="32b18-121">Há suporte para usuários individuais ou múltiplos por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="32b18-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="32b18-122">Níveis variados de configurações de bloqueio de dispositivo aplicadas com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.</span><span class="sxs-lookup"><span data-stu-id="32b18-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="32b18-123">Licenciamento e requisitos de guias</span><span class="sxs-lookup"><span data-stu-id="32b18-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="32b18-124">Conta do AD do Azure</span><span class="sxs-lookup"><span data-stu-id="32b18-124">Azure AD account</span></span>
- <span data-ttu-id="32b18-125">Aplicativos do Dynamics 365 Guides pc e HoloLens</span><span class="sxs-lookup"><span data-stu-id="32b18-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="32b18-126">Assinatura do Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="32b18-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="32b18-127">Microsoft Dataverse (incluído)</span><span class="sxs-lookup"><span data-stu-id="32b18-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="32b18-128">Power Apps (incluído)</span><span class="sxs-lookup"><span data-stu-id="32b18-128">Power Apps (included)</span></span>
- <span data-ttu-id="32b18-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="32b18-129">Power BI Desktop</span></span>
- <span data-ttu-id="32b18-130">Conectividade de rede</span><span class="sxs-lookup"><span data-stu-id="32b18-130">Network Connectivity</span></span>

<span data-ttu-id="32b18-131">[![Diagrama de rede conectada Corp, estágio 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="32b18-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="32b18-132">[![Diagrama de rede conectada Corp, estágio 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="32b18-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="32b18-133">Neste guia, você:</span><span class="sxs-lookup"><span data-stu-id="32b18-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="32b18-134">Preparar</span><span class="sxs-lookup"><span data-stu-id="32b18-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="32b18-135">Saiba mais sobre os fundamentos de infraestrutura para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="32b18-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="32b18-136">Saiba mais sobre o Azure AD e configurar um se você não o tiver.</span><span class="sxs-lookup"><span data-stu-id="32b18-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="32b18-137">Saiba mais sobre o Gerenciamento de identidades e como configurar melhor as contas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32b18-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="32b18-138">Saiba mais sobre o MDM e configurar com o Intune se você ainda não tiver um pronto.</span><span class="sxs-lookup"><span data-stu-id="32b18-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="32b18-139">Familiarize-se com o Wi-Fi baseado em certificado.</span><span class="sxs-lookup"><span data-stu-id="32b18-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="32b18-140">Familiarize-se com o Proxy.</span><span class="sxs-lookup"><span data-stu-id="32b18-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="32b18-141">Entenda como você pode usar aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="32b18-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="32b18-142">Saiba mais sobre como você pode usar Guias para sua organização.</span><span class="sxs-lookup"><span data-stu-id="32b18-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="32b18-143">Configurar</span><span class="sxs-lookup"><span data-stu-id="32b18-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="32b18-144">Como criar usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="32b18-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="32b18-145">Como configurar o Registro Automático.</span><span class="sxs-lookup"><span data-stu-id="32b18-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="32b18-146">Como configurar certificados Wi-Fi e perfis corporativos para conectividade Wi-Fi corporativa.</span><span class="sxs-lookup"><span data-stu-id="32b18-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="32b18-147">Upload e atribuir pacotes de aplicativos lob (linha de negócios).</span><span class="sxs-lookup"><span data-stu-id="32b18-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="32b18-148">Configurar guias do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32b18-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="32b18-149">Como configurar o Modo de Quiosque (opcional).</span><span class="sxs-lookup"><span data-stu-id="32b18-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="32b18-150">Como configurar o WDAC (opcional).</span><span class="sxs-lookup"><span data-stu-id="32b18-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="32b18-151">Implantar</span><span class="sxs-lookup"><span data-stu-id="32b18-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="32b18-152">Valide o registro por meio do dispositivo e do MDM.</span><span class="sxs-lookup"><span data-stu-id="32b18-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="32b18-153">Valide Wi-Fi certificados.</span><span class="sxs-lookup"><span data-stu-id="32b18-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="32b18-154">Valide a instalação do aplicativo LOB.</span><span class="sxs-lookup"><span data-stu-id="32b18-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="32b18-155">Valide guias por meio de autorização e operação.</span><span class="sxs-lookup"><span data-stu-id="32b18-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="32b18-156">Manter</span><span class="sxs-lookup"><span data-stu-id="32b18-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="32b18-157">Atualização HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="32b18-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="32b18-158">Como atualizar Guias (aplicativos da loja).</span><span class="sxs-lookup"><span data-stu-id="32b18-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="32b18-159">Como atualizar aplicativos LOB.</span><span class="sxs-lookup"><span data-stu-id="32b18-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="32b18-160">Plano de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="32b18-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="32b18-161">Como criar um plano de suporte.</span><span class="sxs-lookup"><span data-stu-id="32b18-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="32b18-162">Opções de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="32b18-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="32b18-163">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="32b18-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="32b18-164">Implantação conectada corporativa – Preparar</span><span class="sxs-lookup"><span data-stu-id="32b18-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
