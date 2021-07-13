---
title: guia de implantação – implantação em nuvem HoloLens 2 em escala com o auxílio remoto – configurar
description: saiba como configurar as configurações para registrar dispositivos HoloLens em uma rede conectada na nuvem em escala com o auxílio remoto.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635136"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="bfe1b-104">Configurar-guia conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="bfe1b-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="bfe1b-105">Nesta seção do guia,&#39;mos como configurar o registro automático para seu locatário e como aplicar licenças para o Intune e o auxiliar remoto.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="bfe1b-106">Usuários e grupos do Azure</span><span class="sxs-lookup"><span data-stu-id="bfe1b-106">Azure Users and Groups</span></span>

<span data-ttu-id="bfe1b-107">O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="bfe1b-108">Para validar esse fluxo de implantação e ser capaz de fazer uma chamada de assistência remota de um usuário para outro, você&#39;precisará de duas contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="bfe1b-109">Podemos criar um único grupo de usuários com a finalidade de atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="bfe1b-110">Podemos unir os dois usuários ao mesmo grupo e aplicar uma licença para o Intune e assistência remota a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="bfe1b-111">Se você Don&#39;t já tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; Aqui estão os guias de início rápido para:</span><span class="sxs-lookup"><span data-stu-id="bfe1b-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="bfe1b-112">Como criar um usuário</span><span class="sxs-lookup"><span data-stu-id="bfe1b-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="bfe1b-113">Como criar um grupo</span><span class="sxs-lookup"><span data-stu-id="bfe1b-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="bfe1b-114">[Adicionar usuários a um grupo](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – adicionar usuários criados para criar grupo</span><span class="sxs-lookup"><span data-stu-id="bfe1b-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="bfe1b-115">[Configurar o Azure ad para permitir que um grupo de usuários ingresse em dispositivos](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Verifique se o novo grupo de usuários tem permissão para registrar dispositivos no Azure AD</span><span class="sxs-lookup"><span data-stu-id="bfe1b-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="bfe1b-116">registro automático no HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bfe1b-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="bfe1b-117">para ter uma experiência tranqüila e perfeita, configurar Azure Active Directory Join (AADJ) e o registro automático para o Intune para dispositivos HoloLens 2 é a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="bfe1b-118">Isso permitirá que os usuários insiram suas credenciais de logon da organização durante o OOBE e se registrem automaticamente com o Azure AD e registrem o dispositivo no MDM.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="bfe1b-119">usando [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos selecionar serviços e navegar por algumas páginas até que possamos selecionar obter uma avaliação de Premium.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="bfe1b-120">você pode notar que há Azure Active Directory Premium 1 e 2, para o registro automático P1 é suficiente.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="bfe1b-121">Podemos selecionar o Intune e selecionar o escopo do usuário para registro automático e selecionar o grupo que foi criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="bfe1b-122">Para obter detalhes completos e etapas, leia o guia sobre [como habilitar o registro automático para o Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span><span class="sxs-lookup"><span data-stu-id="bfe1b-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="bfe1b-123">Licenças de aplicativos</span><span class="sxs-lookup"><span data-stu-id="bfe1b-123">Application Licenses</span></span>

<span data-ttu-id="bfe1b-124">Uma licença de aplicativo permite que um usuário instale aplicativos comprados pela empresa ou atualize de uma avaliação gratuita para a versão completa de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="bfe1b-125">As licenças de aplicativo podem ser aplicadas a usuários, grupos de usuários ou grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="bfe1b-126">Você&#39;que precisa de licenças de assistência remota para que os usuários em sua organização usem o auxílio remoto.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="bfe1b-127">Para o propósito deste guia, atribuíremos licenças de assistência remota ao grupo de usuários criado acima em [usuários e grupos do Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span><span class="sxs-lookup"><span data-stu-id="bfe1b-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="bfe1b-128">Os requisitos para licenças podem ser diferentes dependendo se o usuário estiver fazendo a chamada de assistência remota de um dispositivo ou for um colaborador remoto de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="bfe1b-129">por padrão, as caixas de seleção assistência remota e Teams são marcadas.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="bfe1b-130">Para os fins deste guia, sugerimos deixar as caixas padrão verificadas.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="bfe1b-131">Saiba mais sobre os diferentes [requisitos de licenciamento e produto por função](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span><span class="sxs-lookup"><span data-stu-id="bfe1b-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="bfe1b-132">Há alguns tipos diferentes de licenças de assistência remota, portanto, certifique-se de obter os corretos para suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="bfe1b-133">Você&#39;precisa [adquirir a licença](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span><span class="sxs-lookup"><span data-stu-id="bfe1b-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="bfe1b-134">[Aplique suas licenças](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) ao grupo.</span><span class="sxs-lookup"><span data-stu-id="bfe1b-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="bfe1b-135">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="bfe1b-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bfe1b-136">Implantação conectada na nuvem – implantar</span><span class="sxs-lookup"><span data-stu-id="bfe1b-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)