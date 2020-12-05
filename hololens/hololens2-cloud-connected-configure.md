---
title: Guia de implantação – implantação do HoloLens 2 conectado à nuvem em escala com assistência remota-configurar
description: Como configurar as configurações para registrar dispositivos do HoloLens em uma rede conectada na nuvem
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196253"
---
# <span data-ttu-id="47c68-104">Configurar-guia conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="47c68-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="47c68-105">Nesta seção do guia,&#39;remos como configurar o registro automático para o seu locatário e como aplicar licenças para o Intune e para a assistência remota.</span><span class="sxs-lookup"><span data-stu-id="47c68-105">In this section of the guide we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="47c68-106">Usuários e grupos do Azure</span><span class="sxs-lookup"><span data-stu-id="47c68-106">Azure Users and Groups</span></span>

<span data-ttu-id="47c68-107">O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças.</span><span class="sxs-lookup"><span data-stu-id="47c68-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="47c68-108">Para que você possa validar esse fluxo de implantação e fazer uma chamada de assistência remota de um usuário para outro, você precisará de duas contas de usuário do&#39;.</span><span class="sxs-lookup"><span data-stu-id="47c68-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need 2 user accounts.</span></span>

<span data-ttu-id="47c68-109">Podemos criar um único grupo de usuários com o objetivo de atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="47c68-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="47c68-110">Podemos associar os dois usuários ao mesmo grupo e aplicar uma licença do Intune e assistência remota a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="47c68-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="47c68-111">Se você não&#39;eu já tiver acesso a duas contas do AAD em um grupo de usuários, você poderá usar; Estes são os guias de início rápido para:</span><span class="sxs-lookup"><span data-stu-id="47c68-111">If you don&#39;t already have access to two AAD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="47c68-112">Como criar um usuário</span><span class="sxs-lookup"><span data-stu-id="47c68-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="47c68-113">Como criar um grupo</span><span class="sxs-lookup"><span data-stu-id="47c68-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="47c68-114">[Adicionar usuários a um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – adicionar usuários criados para criar grupo</span><span class="sxs-lookup"><span data-stu-id="47c68-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="47c68-115">[Configurar o AAD para permitir que um grupo de usuários ingresse em dispositivos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – garanta que o novo grupo de usuários tenha permissão para registrar dispositivos no AAD</span><span class="sxs-lookup"><span data-stu-id="47c68-115">[Configure AAD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to AAD</span></span>

## <span data-ttu-id="47c68-116">Registro automático no HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="47c68-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="47c68-117">Para ter uma experiência tranqüila e perfeita, configurar o Azure Active Directory Join (AADJ) e o registro automático para o Intune para dispositivos HoloLens 2 é como ir.</span><span class="sxs-lookup"><span data-stu-id="47c68-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="47c68-118">Isso permitirá que os usuários simplesmente insiram as credenciais de login da organização durante a OOBE e se registrem automaticamente no AAD e inscrevam o dispositivo no MDM.</span><span class="sxs-lookup"><span data-stu-id="47c68-118">This will allow users to simply input their organization log-in credentials during OOBE and automatically register with AAD and enroll the device into MDM.</span></span>

<span data-ttu-id="47c68-119">Ao usar [o Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) , podemos selecionar serviços e navegar em algumas páginas até que possamos selecionar obter uma avaliação Premium.</span><span class="sxs-lookup"><span data-stu-id="47c68-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="47c68-120">Você tem muitos avisos de que há o Azure Active Directory Premium 1 e 2, para o registro automático P1 é suficiente.</span><span class="sxs-lookup"><span data-stu-id="47c68-120">You many notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="47c68-121">Podemos selecionar o Intune e selecionar o escopo do usuário para registro automático e selecionar o grupo que foi criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="47c68-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="47c68-122">Para obter detalhes completos e etapas, leia o guia sobre [como habilitar o registro automático do Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span><span class="sxs-lookup"><span data-stu-id="47c68-122">For full details and steps please read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="47c68-123">Licenças de aplicativos</span><span class="sxs-lookup"><span data-stu-id="47c68-123">Application Licenses</span></span>

<span data-ttu-id="47c68-124">Uma licença de aplicativo permite que um usuário instale aplicativos comprados pela empresa ou atualize de uma avaliação gratuita para a versão completa de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="47c68-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="47c68-125">As licenças do aplicativo podem ser aplicadas a usuários, grupos de usuários ou grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="47c68-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="47c68-126">Você&#39;precisará de licenças de assistência remota para que os usuários da sua organização usem a assistência remota.</span><span class="sxs-lookup"><span data-stu-id="47c68-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="47c68-127">Para a finalidade deste guia, atribuiremos licenças de assistência remota ao grupo de usuários que criamos acima em [usuários e grupos do Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span><span class="sxs-lookup"><span data-stu-id="47c68-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="47c68-128">Os requisitos para licenças podem ser diferentes dependendo se o usuário estiver executando a chamada de assistência remota de um dispositivo ou será um colaborador remoto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="47c68-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="47c68-129">Por padrão, as caixas de seleção assistência remota e equipes estão marcadas.</span><span class="sxs-lookup"><span data-stu-id="47c68-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="47c68-130">Para os propósitos deste guia, sugerimos deixar as caixas padrão verificadas.</span><span class="sxs-lookup"><span data-stu-id="47c68-130">For the purposes of this guide, we suggest to leave the default boxes checked.</span></span>

1. <span data-ttu-id="47c68-131">Saiba mais sobre as diferentes [exigências de licenciamento e produtos por função](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span><span class="sxs-lookup"><span data-stu-id="47c68-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="47c68-132">Há alguns tipos diferentes de licenças de assistência remota, portanto, lembre-se de ter os corretos para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="47c68-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="47c68-133">Você&#39;precisa [adquirir a licença](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span><span class="sxs-lookup"><span data-stu-id="47c68-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="47c68-134">[Aplique suas licenças](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) ao grupo.</span><span class="sxs-lookup"><span data-stu-id="47c68-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="47c68-135">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="47c68-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="47c68-136">Implantação conectada na nuvem-implantação</span><span class="sxs-lookup"><span data-stu-id="47c68-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)