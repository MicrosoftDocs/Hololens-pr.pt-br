---
title: Diretrizes de Infraestrutura para o HoloLens
description: Diretrizes de Infraestrutura para dispositivos HoloLens
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a67aaa5df4c74531b5bed88abaa266b00de5c406
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253158"
---
# <span data-ttu-id="4c1ed-103">Configurar Sua Rede para o HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c1ed-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="4c1ed-104">Essa parte do documento exigirá as seguintes pessoas:</span><span class="sxs-lookup"><span data-stu-id="4c1ed-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="4c1ed-105">Administrador de Rede com permissões para fazer alterações no proxy/firewall</span><span class="sxs-lookup"><span data-stu-id="4c1ed-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="4c1ed-106">Administrador do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c1ed-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="4c1ed-107">Administrador de Gerenciador de Dispositivos Móveis</span><span class="sxs-lookup"><span data-stu-id="4c1ed-107">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="4c1ed-108">Requisitos de Infraestrutura</span><span class="sxs-lookup"><span data-stu-id="4c1ed-108">Infrastructure Requirements</span></span>

<span data-ttu-id="4c1ed-109">Em essência, o HoloLens é um dispositivo móvel do Windows integrado ao Azure.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="4c1ed-110">Funciona melhor em ambientes comerciais com disponibilidade de rede sem fio (Wi-Fi) e acesso aos serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="4c1ed-111">Os serviços de nuvem essenciais incluem:</span><span class="sxs-lookup"><span data-stu-id="4c1ed-111">Critical cloud services include:</span></span>

- <span data-ttu-id="4c1ed-112">Active Directory do Azure (Microsoft Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="4c1ed-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="4c1ed-113">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="4c1ed-113">Windows Update (WU)</span></span>

<span data-ttu-id="4c1ed-114">Os clientes comerciais precisarão da infraestrutura de EMM (gerenciamento de mobilidade corporativa) ou de MDM (gerenciamento de dispositivo móvel) para gerenciar os dispositivos HoloLens em escala.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="4c1ed-115">Este guia usa o [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como exemplo, embora qualquer provedor com suporte completo à Política da Microsoft dão suporte ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="4c1ed-116">Pergunte ao seu provedor de gerenciamento de dispositivo móvel se eles dão suporte ao HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="4c1ed-117">O HoloLens é compatível com um conjunto limitado de experiências desconectadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="4c1ed-118">Suporte a redes sem fio EAP</span><span class="sxs-lookup"><span data-stu-id="4c1ed-118">Wireless network EAP support</span></span>

- <span data-ttu-id="4c1ed-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="4c1ed-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="4c1ed-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="4c1ed-120">PEAP-TLS</span></span>
- <span data-ttu-id="4c1ed-121">TLS</span><span class="sxs-lookup"><span data-stu-id="4c1ed-121">TLS</span></span>
- <span data-ttu-id="4c1ed-122">CHAP TTLS</span><span class="sxs-lookup"><span data-stu-id="4c1ed-122">TTLS-CHAP</span></span>
- <span data-ttu-id="4c1ed-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="4c1ed-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="4c1ed-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="4c1ed-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="4c1ed-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="4c1ed-125">TTLS-PAP</span></span>
- <span data-ttu-id="4c1ed-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="4c1ed-126">TTLS-TLS</span></span>

### <span data-ttu-id="4c1ed-127">Requisitos de Rede Específicos do HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c1ed-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="4c1ed-128">Certifique-se de que [essa lista](hololens-offline.md)de pontos de extremidade são permitidas no firewall da sua rede.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="4c1ed-129">Isso permitirá que o HoloLens funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-129">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="4c1ed-130">Requisitos de Rede Específicos da Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="4c1ed-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="4c1ed-131">A largura de banda recomendada para o desempenho ideal da Assistência Remota é de 1.5 Mbps.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="4c1ed-132">Os requisitos de rede detalhados e informações adicionais podem ser encontrados [aqui](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-132">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="4c1ed-133">(Observe que, caso não haja velocidades de rede de pelo menos 1.5 Mbps, a Assistência Remota continuará funcionando.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-133">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="4c1ed-134">No entanto, a qualidade pode ser afetada).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-134">However, quality may suffer).</span></span>**
1. <span data-ttu-id="4c1ed-135">Verifique se essas portas e URLs são permitidas no firewall da sua rede.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-135">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="4c1ed-136">Isso permitirá que o Microsoft Teams funcione.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-136">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="4c1ed-137">A lista mais recente pode ser encontrada [aqui](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-137">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="4c1ed-138">Saiba mais, especificamente, sobre os [Requisitos de Rede para Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-138">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="4c1ed-139">Saiba mais sobre como [preparar a rede da sua organização para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="4c1ed-139">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="4c1ed-140">Guias dos Requisitos de Rede Específicos</span><span class="sxs-lookup"><span data-stu-id="4c1ed-140">Guides Specific Network Requirements</span></span>

<span data-ttu-id="4c1ed-141">As guias só exigem o acesso à rede para baixar e usar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-141">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="4c1ed-142">Diretrizes do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c1ed-142">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="4c1ed-143">Essa etapa só será necessária se a sua empresa planeja gerenciar os aplicativos do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-143">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="4c1ed-144">Verifique se você tem uma licença do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-144">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="4c1ed-145">Confira [Requisitos de Licenças do HoloLens](hololens-licenses-requirements.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-145">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="4c1ed-146">Se planeja usar o Registro Automático, será necessário [Configurar o registro do Azure AD](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-146">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="4c1ed-147">Verifique se os usuários da sua empresa estão no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-147">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="4c1ed-148">Instruções para adicionar usuários podem ser encontradas [aqui](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-148">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="4c1ed-149">Sugerimos que os usuários que precisarem de licenças similares sejam adicionados a um mesmo grupo.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-149">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="4c1ed-150">Criar um grupo</span><span class="sxs-lookup"><span data-stu-id="4c1ed-150">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="4c1ed-151">Adicionar usuários a grupos</span><span class="sxs-lookup"><span data-stu-id="4c1ed-151">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="4c1ed-152">Verifique se os usuários da sua empresa (ou grupo de usuários) têm as licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-152">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="4c1ed-153">As instruções para atribuir licenças podem ser encontradas [aqui](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-153">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="4c1ed-154">Execute esta etapa apenas se espera que os usuários registrem seus dispositivos HoloLens/Dispositivo móvel (existem três opções). Estas etapas garantem que os usuários da empresa (ou um grupo de usuários) possam adicionar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-154">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="4c1ed-155">**Opção 1:** Conceda a todos os usuários permissão para adicionar dispositivos ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-155">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="4c1ed-156">Entrar no portal do Azure como um administradorAzure Active DirectoryDispositivosConfigurações de Dispositivo\*\*Configurar Usuários para adicionar dispositivos ao Azure AD em Todos\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4c1ed-156">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="4c1ed-157">**Opção 2:** Conceder permissão aos usuários/grupos selecionados para adicionar dispositivos ao Azure AD **Entrar no portal do Azure como administrador** > **Azure Active Directory** > **Dispositivos** > \*\* Configurações de Dispositivos\*\* >
\*\*Configurar usuários para adicionar dispositivos ao Azure AD para \*Selecionar\*\*\*
![ Imagem que mostra a Configuração dos Dispositivos Adicionados ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="4c1ed-157">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="4c1ed-158">**Opção 3:** Você pode impedir que todos os usuários ingressem em seus dispositivos no domínio.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-158">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="4c1ed-159">Isso significa que todos os dispositivos precisarão ser registrados manualmente.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-159">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="4c1ed-160">Diretrizes do Administrador de Gerenciador de Dispositivos Móveis</span><span class="sxs-lookup"><span data-stu-id="4c1ed-160">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="4c1ed-161">Gerenciamento contínuo de dispositivos </span><span class="sxs-lookup"><span data-stu-id="4c1ed-161">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="4c1ed-162">Essa etapa só será necessária se a sua empresa planeja gerenciar o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-162">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="4c1ed-163">O gerenciamento contínuo de dispositivos dependerá da infraestrutura de gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-163">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="4c1ed-164">A maioria tem a mesma funcionalidade geral, mas a interface do usuário pode variar muito.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-164">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="4c1ed-165">Os [CSPs (Provedores de Serviços de Configuração)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) permitem criar e implantar as configurações de gerenciamento para os dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-165">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="4c1ed-166">É possível encontrar uma lista de CSPs para o HoloLens [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-166">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="4c1ed-167">[Políticas de conformidade](https://docs.microsoft.com/intune/device-compliance-get-started) são regras e configurações que os dispositivos devem atender para serem compatíveis com a sua infraestrutura corporativa.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-167">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="4c1ed-168">Use essas políticas com Acesso Condicional para bloquear o acesso a recursos da empresa por dispositivos que não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-168">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="4c1ed-169">Por exemplo, você pode criar uma política que requer que o Bitlocker esteja ativado.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-169">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="4c1ed-170">[Criar Política de Conformidade](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-170">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="4c1ed-171">O Acesso Condicional permite/nega que aplicativos e dispositivos móveis acessem recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-171">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="4c1ed-172">Os dois documentos que você pode achar úteis são [Planejar a Implantação da AC](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) e [Práticas Recomendadas](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-172">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="4c1ed-173">[Este artigo](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) explicar sobre as ferramentas de gerenciamento do Intune para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-173">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="4c1ed-174">Criar um perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="4c1ed-174">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="4c1ed-175">Gerenciar atualizações</span><span class="sxs-lookup"><span data-stu-id="4c1ed-175">Manage updates</span></span>

<span data-ttu-id="4c1ed-176">O Intune inclui um recurso chamado Anéis de atualização para dispositivos Windows 10, incluindo o HoloLens 2 e o HoloLens v1 (com o Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-176">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="4c1ed-177">Os Anéis de atualização incluem um grupo de configurações que determinam como e quando as atualizações serão instaladas.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-177">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="4c1ed-178">Por exemplo, você pode criar uma janela de manutenção para instalar atualizações ou optar por reiniciar após atualizar.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-178">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="4c1ed-179">Também é possível optar por pausar atualizações indefinidamente até estar pronto para atualizar.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-179">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="4c1ed-180">Leia mais sobre [configurar anéis de atualização com o Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-180">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="4c1ed-181">Gerenciamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="4c1ed-181">Application management</span></span>

<span data-ttu-id="4c1ed-182">Gerenciar aplicativos do HoloLens através de:</span><span class="sxs-lookup"><span data-stu-id="4c1ed-182">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="4c1ed-183">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4c1ed-183">Microsoft Store</span></span>  
  <span data-ttu-id="4c1ed-184">A Microsoft Store é a melhor maneira de distribuir e usar aplicativos no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-184">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="4c1ed-185">Já existe um ótimo conjunto de aplicativos principais do HoloLens disponíveis na loja ou você pode [publicar seus próprios](https://docs.microsoft.com/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-185">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="4c1ed-186">Todos os aplicativos na loja estão disponíveis publicamente, mas se não for aceitável, finalize a compra na Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-186">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="4c1ed-187">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="4c1ed-187">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="4c1ed-188">A Microsoft Store para Empresas e Educação é um armazenamento personalizado para ambiente corporativo.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-188">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="4c1ed-189">Permite o uso da Microsoft Store no Windows 10 e no HoloLens para encontrar, adquirir, distribuir e gerenciar aplicativos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-189">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="4c1ed-190">Também permite implantar aplicativos específicos para ambiente comercial, mas não global.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-190">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="4c1ed-191">Implantação e gerenciamento de aplicativos via Intune ou outra solução de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="4c1ed-191">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="4c1ed-192">A maioria das soluções de gerenciamento de dispositivo móvel, incluindo o Intune, oferece uma maneira de implantar aplicativos de linha de negócios diretamente em um conjunto de dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-192">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="4c1ed-193">Confira este artigo sobre [instalação de aplicativos do Intune](https://docs.microsoft.com/intune/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-193">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="4c1ed-194">Portal de Dispositivos _não recomendado_</span><span class="sxs-lookup"><span data-stu-id="4c1ed-194">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="4c1ed-195">Os aplicativos também podem ser instalados no HoloLens diretamente usando o Portal de Dispositivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-195">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="4c1ed-196">Isso não é recomendado, pois o Modo de Desenvolvedor deve estar ativado para usar o portal do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-196">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="4c1ed-197">Leia mais sobre [instalação de aplicativos no HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-197">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="4c1ed-198">Certificados</span><span class="sxs-lookup"><span data-stu-id="4c1ed-198">Certificates</span></span>

<span data-ttu-id="4c1ed-199">Você pode distribuir certificados através do provedor de MDM.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-199">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="4c1ed-200">O Intune dá suporte a PKCS, PFX e SCEP, caso sua empresa exija certificados.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-200">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="4c1ed-201">É importante entender qual certificado é adequado para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-201">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="4c1ed-202">Visite [aqui](https://docs.microsoft.com/intune/protect/certificates-configure) para determinar o certificado ideal para você.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-202">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="4c1ed-203">Se você planeja usar certificados para Autenticação do HoloLens, o PFX ou SCEP talvez sejam adequados para você.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-203">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="4c1ed-204">As etapas para o SCEP podem ser encontradas [aqui](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-204">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="4c1ed-205">Como Atualizar para o Pacote Comercial do Holographics for Business</span><span class="sxs-lookup"><span data-stu-id="4c1ed-205">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="4c1ed-206">O Holographics for Business (pacote comercial) do Windows destina-se apenas a dispositivos da 1ª geração do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-206">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="4c1ed-207">O perfil não será aplicado a dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-207">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="4c1ed-208">As instruções de como atualizar para o pacote comercial podem ser encontradas [aqui](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-208">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="4c1ed-209">Como Configurar o Modo de Quiosque usando o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-209">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="4c1ed-210">Sincronizar a Microsoft Store com o Intune ([Aqui](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-210">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="4c1ed-211">Verificar as configurações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="4c1ed-211">Check your app settings</span></span>
    1. <span data-ttu-id="4c1ed-212">Entrar na sua conta da Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="4c1ed-212">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="4c1ed-213">Gerenciar > Produtos e Serviços> Aplicativos e Software > Select o aplicativo que você deseja sincronizar > Disponibilidade de Repositório Particular > Selecionar “Todos” ou “Grupos Específicos”</span><span class="sxs-lookup"><span data-stu-id="4c1ed-213">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="4c1ed-214">Se você não vir o aplicativo desejado, será necessário "obter" o aplicativo pesquisando a loja do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-214">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="4c1ed-215">**clique na barra "Pesquisar" no canto superior direito > digite o nome do aplicativo > clique no aplicativo > selecione "Obter"**.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-215">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="4c1ed-216">Caso não veja seus aplicativos no **Intune > Aplicativos cliente > Aplicativos** , talvez seja preciso [sincronizar seus aplicativos](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) novamente.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-216">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="4c1ed-217">Criar um perfil de dispositivo para o Modo de quiosque</span><span class="sxs-lookup"><span data-stu-id="4c1ed-217">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="4c1ed-218">Você pode configurar diferentes usuários para ter diferentes experiências de Modo de Quiosque usando o "Azure AD" como "Tipo de logon do usuário".</span><span class="sxs-lookup"><span data-stu-id="4c1ed-218">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="4c1ed-219">No entanto, esta opção está disponível apenas no modo de quiosque para Vários Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-219">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="4c1ed-220">O modo de quiosque para vários aplicativos funcionará com apenas um aplicativo, bem como com vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-220">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Imagem que mostra a Configuração do Modo de Quiosque no Intune](images/aad-kioskmode.png)

<span data-ttu-id="4c1ed-222">Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-222">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="4c1ed-223">Caso precise usar uma configuração personalizada e uma configuração XML completa para instalar um quiosque no seu serviço MDM, instruções adicionais podem ser encontradas [aqui](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="4c1ed-223">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="4c1ed-224">Certificados e Autenticação</span><span class="sxs-lookup"><span data-stu-id="4c1ed-224">Certificates and Authentication</span></span>

<span data-ttu-id="4c1ed-225">Os certificados podem ser implantados via MDM (confira "certificados" na [Seção MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span><span class="sxs-lookup"><span data-stu-id="4c1ed-225">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="4c1ed-226">Os certificados também podem ser implantados no HoloLens por meio do provisionamento de pacotes.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-226">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="4c1ed-227">Confira [Provisionamento do HoloLens](hololens-provisioning.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-227">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="4c1ed-228">Links Rápidos Adicionais do Intune</span><span class="sxs-lookup"><span data-stu-id="4c1ed-228">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="4c1ed-229">[Criar perfis:](https://docs.microsoft.com/intune/configuration/device-profile-create) os perfis permitem que você adicione e defina as configurações que serão transferidas para os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4c1ed-229">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

