---
title: Como planejar a implantação do HoloLens 2 em um ambiente comercial
description: Saiba mais sobre as principais necessidades de implantação e gerenciamento de HoloLens em ambientes corporativos, incluindo infraestrutura, azure Active Directory e gerenciamento de dispositivo móvel.
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
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639073"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="f0f2c-103">Como planejar a implantação do HoloLens 2 em um ambiente comercial</span><span class="sxs-lookup"><span data-stu-id="f0f2c-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="f0f2c-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f0f2c-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="f0f2c-105">Esta visão geral destina-se a ajudar os profissionais de TI a entender as considerações para implantar e gerenciar Microsoft HoloLens 2 dispositivos em uma organização.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="f0f2c-106">Para usuários finais do dispositivo, consulte [Preparar HoloLens 2 para uso](hololens2-setup.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="f0f2c-107">HoloLens 2 é executado Windows 10 Holographic que fornece às organizações tecnologias robustas, flexíveis e de gerenciamento de aplicativos móveis.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="f0f2c-108">Windows 10 Holographic dá suporte ao gerenciamento de ciclo de vida do dispositivo de ponta a ponta para dar às empresas controle sobre seus dispositivos, dados e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="f0f2c-109">O HoloLens 2 pode ser facilmente incorporado às práticas de ciclo de vida padrão, desde o registro do dispositivo, a configuração e o gerenciamento de aplicativos até a manutenção e a replicação usando uma solução abrangente de gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="f0f2c-110">As etapas e o vídeo a seguir podem ajudar a orientá-lo pelo processo de HoloLens adoção 2 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![Etapa 1](images/1green.png)| <br/> <span data-ttu-id="f0f2c-112">**[Cenários comuns de implantação:](hololens-requirements.md)** entenda os cenários de implantação e explore os componentes principais necessários para implantar HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Etapa 2](images/2green.png)| <br/> <span data-ttu-id="f0f2c-114">**[Preparar:](#prepare)** familiarizar-se com os fundamentos de infraestrutura necessários para HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Etapa 3](images/3green.png) | <br/> <span data-ttu-id="f0f2c-116">**[Configurar](#configure)**: saiba como configurar seus componentes essenciais para uma implantação baseada em nuvem.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Etapa 4](images/4green.png) | <br/> <span data-ttu-id="f0f2c-118">**[Implantar:](#deploy)** descubra como implantar seus dispositivos e distribuir seus aplicativos com segurança e eficiência.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Etapa 5](images/5green.png) | <br/> <span data-ttu-id="f0f2c-120">**[Manter:](#maintain)** descubra o que é necessário para manter corretamente o estado de seus dispositivos HoloLens 2 e garantir a conformidade com a política corporativa.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="f0f2c-121">Preparar</span><span class="sxs-lookup"><span data-stu-id="f0f2c-121">Prepare</span></span>

<span data-ttu-id="f0f2c-122">Saiba mais sobre os serviços de infraestrutura essenciais necessários para dar suporte ao conjunto completo de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="f0f2c-123">Componente</span><span class="sxs-lookup"><span data-stu-id="f0f2c-123">Component</span></span> | <span data-ttu-id="f0f2c-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0f2c-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="f0f2c-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="f0f2c-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="f0f2c-126">Fornece gerenciamento de identidade e acesso para o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f0f2c-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="f0f2c-127">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="f0f2c-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="f0f2c-128">Gerencia HoloLens dois dispositivos conectados ao seu locatário</span><span class="sxs-lookup"><span data-stu-id="f0f2c-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="f0f2c-129">Rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f0f2c-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="f0f2c-130">Wi-Fi está disponível e os dispositivos podem ser conectados à Internet</span><span class="sxs-lookup"><span data-stu-id="f0f2c-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="f0f2c-131">Configurar</span><span class="sxs-lookup"><span data-stu-id="f0f2c-131">Configure</span></span>

<span data-ttu-id="f0f2c-132">Use o Intune e o Autopilot como soluções de baixo toque para registrar e configurar o HoloLens 2 para o locatário e o MDM do Azure AD da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="f0f2c-133">Componente</span><span class="sxs-lookup"><span data-stu-id="f0f2c-133">Component</span></span> | <span data-ttu-id="f0f2c-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0f2c-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="f0f2c-135">Registro automático</span><span class="sxs-lookup"><span data-stu-id="f0f2c-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="f0f2c-136">Após o logon inicial, os dispositivos se registram automaticamente no Azure AD e se registram no MDM</span><span class="sxs-lookup"><span data-stu-id="f0f2c-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="f0f2c-137">Licenças de aplicativo</span><span class="sxs-lookup"><span data-stu-id="f0f2c-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="f0f2c-138">Pode ser aplicado a usuários, grupos de usuários ou grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f0f2c-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="f0f2c-139">Usuários e grupos do Azure</span><span class="sxs-lookup"><span data-stu-id="f0f2c-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="f0f2c-140">Ajuda a atribuir configurações e licenças para o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f0f2c-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="f0f2c-141">Implantar</span><span class="sxs-lookup"><span data-stu-id="f0f2c-141">Deploy</span></span>

<span data-ttu-id="f0f2c-142">Distribua seus HoloLens 2 dispositivos e valide sua configuração.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="f0f2c-143">Componente</span><span class="sxs-lookup"><span data-stu-id="f0f2c-143">Component</span></span> | <span data-ttu-id="f0f2c-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0f2c-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="f0f2c-145">Validação de registro</span><span class="sxs-lookup"><span data-stu-id="f0f2c-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="f0f2c-146">Validar se o dispositivo tem o Azure AD ingressado Configurações portal do Azure</span><span class="sxs-lookup"><span data-stu-id="f0f2c-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="f0f2c-147">Validação do certificado</span><span class="sxs-lookup"><span data-stu-id="f0f2c-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="f0f2c-148">Verifique as configurações e valide se elas foram distribuídas corretamente</span><span class="sxs-lookup"><span data-stu-id="f0f2c-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="f0f2c-149">Validar as instalados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="f0f2c-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="f0f2c-150">Confirme se o aplicativo está presente e trabalhando em seu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f0f2c-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="f0f2c-151">Manter</span><span class="sxs-lookup"><span data-stu-id="f0f2c-151">Maintain</span></span>

<span data-ttu-id="f0f2c-152">Use Windows Update for Business juntamente com seu sistema MDM ou o Microsoft Store para manter sua frota de HoloLens 2 e aplicativos atualizados.</span><span class="sxs-lookup"><span data-stu-id="f0f2c-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="f0f2c-153">Componente</span><span class="sxs-lookup"><span data-stu-id="f0f2c-153">Component</span></span> | <span data-ttu-id="f0f2c-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0f2c-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="f0f2c-155">Atualização HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f0f2c-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="f0f2c-156">Configurar atualizações conforme necessário por meio Windows Atualizações para Empresas</span><span class="sxs-lookup"><span data-stu-id="f0f2c-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="f0f2c-157">Atualizar aplicativos</span><span class="sxs-lookup"><span data-stu-id="f0f2c-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="f0f2c-158">Configure por meio do sistema MDM ou do Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f0f2c-158">Configure through your MDM system or the Microsoft Store</span></span>
