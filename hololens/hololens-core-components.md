---
title: Como planejar a implantação do HoloLens 2 em um ambiente comercial
description: saiba mais sobre as principais necessidades de implantação e gerenciamento de HoloLens em ambientes corporativos, incluindo infraestrutura, azure active directory e gerenciamento de dispositivo móvel.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635782"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="9b323-103">Como planejar a implantação do HoloLens 2 em um ambiente comercial</span><span class="sxs-lookup"><span data-stu-id="9b323-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="9b323-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="9b323-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="9b323-105">esta visão geral destina-se a ajudar os profissionais de ti a entender as considerações de implantação e gerenciamento de Microsoft HoloLens 2 dispositivos em uma organização.</span><span class="sxs-lookup"><span data-stu-id="9b323-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="9b323-106">para usuários finais do dispositivo, consulte [obter seu HoloLens 2 pronto para usar](hololens2-setup.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="9b323-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="9b323-107">o HoloLens 2 é executado em Windows 10 Holographic que fornece às organizações tecnologias de gerenciamento de aplicativo e de dispositivo móvel robustas, flexíveis e integradas.</span><span class="sxs-lookup"><span data-stu-id="9b323-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="9b323-108">o Windows 10 Holographic dá suporte ao gerenciamento de ciclo de vida de dispositivos de ponta a ponta para oferecer às empresas o controle sobre seus dispositivos, dados e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9b323-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="9b323-109">o HoloLens 2 pode ser facilmente incorporado às práticas de ciclo de vida padrão, do registro de dispositivos, da configuração e do gerenciamento de aplicativos até manutenção e desativação usando uma solução abrangente de gerenciamento de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="9b323-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="9b323-110">as etapas e vídeos a seguir podem orientá-lo pelo processo de HoloLens 2 adoção em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9b323-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![Etapa 1](images/1green.png)| <br/> <span data-ttu-id="9b323-112">**[cenários comuns de implantação](hololens-requirements.md)**: compreenda os cenários de implantação e explore os componentes principais necessários para implantar HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9b323-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Etapa 2](images/2green.png)| <br/> <span data-ttu-id="9b323-114">**[Prepare](#prepare)**: familiarize-se com os princípios básicos de infra-estrutura necessários para o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9b323-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Etapa 3](images/3green.png) | <br/> <span data-ttu-id="9b323-116">**[Configurar](#configure)**: saiba como configurar seus componentes essenciais para uma implantação baseada em nuvem.</span><span class="sxs-lookup"><span data-stu-id="9b323-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Etapa 4](images/4green.png) | <br/> <span data-ttu-id="9b323-118">**[Implantar](#deploy)**: Descubra como implantar seus dispositivos e distribua seus aplicativos de forma segura e eficiente.</span><span class="sxs-lookup"><span data-stu-id="9b323-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Etapa 5](images/5green.png) | <br/> <span data-ttu-id="9b323-120">**[manter](#maintain)**: descubra o que é necessário para manter corretamente o estado de seus HoloLens 2 dispositivos e garantir a conformidade com a política corporativa.</span><span class="sxs-lookup"><span data-stu-id="9b323-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="9b323-121">Preparar</span><span class="sxs-lookup"><span data-stu-id="9b323-121">Prepare</span></span>

<span data-ttu-id="9b323-122">saiba mais sobre os serviços de infraestrutura essenciais necessários para dar suporte ao conjunto completo de recursos de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9b323-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="9b323-123">Componente</span><span class="sxs-lookup"><span data-stu-id="9b323-123">Component</span></span> | <span data-ttu-id="9b323-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b323-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="9b323-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="9b323-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="9b323-126">fornece gerenciamento de identidade e acesso para o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9b323-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="9b323-127">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="9b323-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="9b323-128">gerencia HoloLens 2 dispositivos conectados ao seu locatário</span><span class="sxs-lookup"><span data-stu-id="9b323-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="9b323-129">Rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="9b323-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="9b323-130">Wi-Fi está disponível e os dispositivos podem ser conectados à Internet</span><span class="sxs-lookup"><span data-stu-id="9b323-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="9b323-131">Configurar</span><span class="sxs-lookup"><span data-stu-id="9b323-131">Configure</span></span>

<span data-ttu-id="9b323-132">Use o Intune e o autopilot como soluções de baixo toque para registrar e configurar o HoloLens 2 para o locatário do Azure AD da sua organização e MDM.</span><span class="sxs-lookup"><span data-stu-id="9b323-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="9b323-133">Componente</span><span class="sxs-lookup"><span data-stu-id="9b323-133">Component</span></span> | <span data-ttu-id="9b323-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b323-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="9b323-135">Registro automático</span><span class="sxs-lookup"><span data-stu-id="9b323-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="9b323-136">Após o logon inicial, os dispositivos são registrados automaticamente no Azure AD e são registrados no MDM</span><span class="sxs-lookup"><span data-stu-id="9b323-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="9b323-137">Licenças de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9b323-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="9b323-138">Pode ser aplicado a usuários, grupos de usuários ou grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="9b323-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="9b323-139">Usuários e grupos do Azure</span><span class="sxs-lookup"><span data-stu-id="9b323-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="9b323-140">ajuda a atribuir configurações e licenças para o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9b323-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="9b323-141">Implantar</span><span class="sxs-lookup"><span data-stu-id="9b323-141">Deploy</span></span>

<span data-ttu-id="9b323-142">distribua seus dispositivos HoloLens 2 e valide sua configuração.</span><span class="sxs-lookup"><span data-stu-id="9b323-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="9b323-143">Componente</span><span class="sxs-lookup"><span data-stu-id="9b323-143">Component</span></span> | <span data-ttu-id="9b323-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b323-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="9b323-145">Validação de registro</span><span class="sxs-lookup"><span data-stu-id="9b323-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="9b323-146">validar se o dispositivo tem o Azure AD ingressado no Configurações ou no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="9b323-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="9b323-147">Validação do certificado</span><span class="sxs-lookup"><span data-stu-id="9b323-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="9b323-148">Verifique as configurações e valide se elas foram distribuídas corretamente</span><span class="sxs-lookup"><span data-stu-id="9b323-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="9b323-149">Validar instalações de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9b323-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="9b323-150">confirme se o aplicativo está presente e funcionando no seu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9b323-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="9b323-151">Manter</span><span class="sxs-lookup"><span data-stu-id="9b323-151">Maintain</span></span>

<span data-ttu-id="9b323-152">Use Windows Update para negócios junto com seu sistema MDM ou o Microsoft Store para manter sua frota de HoloLens 2 e aplicativos atualizados.</span><span class="sxs-lookup"><span data-stu-id="9b323-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="9b323-153">Componente</span><span class="sxs-lookup"><span data-stu-id="9b323-153">Component</span></span> | <span data-ttu-id="9b323-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b323-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="9b323-155">atualizar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9b323-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="9b323-156">configurar atualizações conforme necessário por meio do Windows updates for Business</span><span class="sxs-lookup"><span data-stu-id="9b323-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="9b323-157">Atualizar aplicativos</span><span class="sxs-lookup"><span data-stu-id="9b323-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="9b323-158">Configurar por meio do seu sistema MDM ou do Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9b323-158">Configure through your MDM system or the Microsoft Store</span></span>
