---
title: Guia de Implantação – implantação do HoloLens 2 conectada à nuvem em escala com Assistência Remota - Configurar
description: Saiba como configurar configurações para registrar dispositivos HoloLens em uma rede conectada à nuvem em escala com a Assistência Remota.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283882"
---
# <span data-ttu-id="21021-104">Configurar - Guia conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="21021-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="21021-105">Nesta seção do guia, vamos&#39;como configurar o Registro Automático para seu locatário e como aplicar licenças para o Intune e a Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="21021-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="21021-106">Usuários e grupos do Azure</span><span class="sxs-lookup"><span data-stu-id="21021-106">Azure Users and Groups</span></span>

<span data-ttu-id="21021-107">O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças.</span><span class="sxs-lookup"><span data-stu-id="21021-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="21021-108">Para validar esse fluxo de implantação e poder fazer uma chamada de Assistência Remota de um usuário para outro que você&#39;precisará de duas contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="21021-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="21021-109">Podemos fazer um único grupo de usuários para atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="21021-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="21021-110">Podemos unir os dois usuários ao mesmo grupo e aplicar uma licença para o Intune e a Assistência Remota a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="21021-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="21021-111">Se você não&#39;tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; Aqui estão os guias de início rápido para:</span><span class="sxs-lookup"><span data-stu-id="21021-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="21021-112">Como criar um usuário</span><span class="sxs-lookup"><span data-stu-id="21021-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="21021-113">Como criar um grupo</span><span class="sxs-lookup"><span data-stu-id="21021-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="21021-114">[Adicionar usuários a um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Adicionar usuários criados para criar um grupo</span><span class="sxs-lookup"><span data-stu-id="21021-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="21021-115">[Configurar o Azure AD para](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) permitir que um Grupo de Usuários inscreva dispositivos – Certifique-se de que o novo grupo de usuários tenha permissão para registrar dispositivos no Azure AD</span><span class="sxs-lookup"><span data-stu-id="21021-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <span data-ttu-id="21021-116">Registro automático no HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="21021-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="21021-117">Para ter uma experiência suave e perfeita, configurar o Azure Active Directory Join (AADJ) e o Registro Automático no Intune para dispositivos HoloLens 2 é a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="21021-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="21021-118">Isso permitirá que os usuários inscrevem suas credenciais de login da organização durante a OOBE e se registrem automaticamente no Azure AD e registrem o dispositivo no MDM.</span><span class="sxs-lookup"><span data-stu-id="21021-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="21021-119">Usando o [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos selecionar serviços e navegar em algumas páginas até podermos selecionar Obter uma avaliação Premium.</span><span class="sxs-lookup"><span data-stu-id="21021-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="21021-120">Você pode notar que há o Azure Active Directory Premium 1 e 2, para o registro automático P1 é suficiente.</span><span class="sxs-lookup"><span data-stu-id="21021-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="21021-121">Podemos selecionar o Intune, selecionar o escopo do usuário para o registro automático e selecionar o grupo que foi criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="21021-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="21021-122">Para obter detalhes completos e etapas, leia o guia [sobre como habilitar o registro automático para o Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)</span><span class="sxs-lookup"><span data-stu-id="21021-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="21021-123">Licenças de aplicativo</span><span class="sxs-lookup"><span data-stu-id="21021-123">Application Licenses</span></span>

<span data-ttu-id="21021-124">Uma licença de aplicativo permite que um usuário instale aplicativos comprados pela empresa ou atualize de uma avaliação gratuita para a versão completa de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="21021-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="21021-125">As licenças de aplicativo podem ser aplicadas a usuários, grupos de usuários ou grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="21021-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="21021-126">Você&#39;de licenças de Assistência Remota para que os usuários em sua organização usem a Assistência Remota.</span><span class="sxs-lookup"><span data-stu-id="21021-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="21021-127">Para os fins deste guia, atribuiremos licenças da Assistência Remota ao grupo de usuários que criamos acima em Usuários e Grupos do [Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="21021-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="21021-128">Os requisitos para licenças podem ser diferentes dependendo se o usuário fará a chamada de Assistência Remota de um dispositivo ou se será um colaborador remoto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="21021-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="21021-129">Por padrão, as caixas de seleção Assistência Remota e Teams estão marcadas.</span><span class="sxs-lookup"><span data-stu-id="21021-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="21021-130">Para os fins deste guia, sugerimos deixar as caixas padrão marcadas.</span><span class="sxs-lookup"><span data-stu-id="21021-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="21021-131">Saiba mais sobre os diferentes [requisitos de licenciamento e produto por função.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)</span><span class="sxs-lookup"><span data-stu-id="21021-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="21021-132">Existem alguns tipos diferentes de licenças da Assistência Remota, portanto, certifique-se de obter as corretas para suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="21021-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="21021-133">Você&#39;precisará adquirir [a licença.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="21021-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="21021-134">[Aplique suas licenças](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) ao grupo.</span><span class="sxs-lookup"><span data-stu-id="21021-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="21021-135">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="21021-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="21021-136">Implantação conectada à nuvem - Implantar</span><span class="sxs-lookup"><span data-stu-id="21021-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)