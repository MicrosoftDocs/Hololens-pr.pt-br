---
title: Intune e Portal da Empresa
description: Saiba como configurar, atribuir e criar uma experiência de usuário confortável com o Intune, o gerenciamento de dispositivo móvel e o portal da empresa.
keywords: intune, gerenciamento de aplicativos, aplicativo, portal da empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635493"
---
# <a name="intune--company-portal"></a><span data-ttu-id="45897-104">Intune e Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="45897-104">Intune & Company Portal</span></span>

<span data-ttu-id="45897-105">Com o MDM (Mobile Gerenciamento de Dispositivos), você pode usar seus próprios aplicativos personalizados por meio [do Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) para implantá-lo diretamente em seus HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="45897-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="45897-106">O Microsoft Intune é um serviço baseado em nuvem que se concentra no MDM (gerenciamento de dispositivo móvel) e no MAM (gerenciamento de aplicativo móvel).</span><span class="sxs-lookup"><span data-stu-id="45897-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="45897-107">O Intune está incluído no [pacote de EMS (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) e permite que os usuários sejam produtivos, garantindo a proteção dos dados da organização.</span><span class="sxs-lookup"><span data-stu-id="45897-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="45897-108">Para saber mais sobre o Intune, leia [O que é o Intune.](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="45897-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="45897-109">Instalação</span><span class="sxs-lookup"><span data-stu-id="45897-109">Setup</span></span>

1. <span data-ttu-id="45897-110">Upload um aplicativo em uma Linha de Negócios ou carregar um aplicativo personalizado em seu locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="45897-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="45897-111">Confira também: gerenciamento [Enterprise aplicativo.](/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="45897-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="45897-112">[Atribua seu aplicativo a um grupo](/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="45897-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="45897-113">Com base no tipo de atribuição escolhido, o aplicativo poderá ser entregue automaticamente ou disponível para ser prontamente retirado se você tiver uma seleção de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="45897-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="45897-114">Ao criar seu pacote appx, certifique-se de incluir a arquitetura para os dispositivos nos quais você está implantando.</span><span class="sxs-lookup"><span data-stu-id="45897-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="45897-115">HoloLens 2 é ARM64 e HoloLens (1ª geração) é x86.</span><span class="sxs-lookup"><span data-stu-id="45897-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="45897-116">Você pode incluir ambos em um único pacote appx se planeja ter um ambiente de dispositivos mistos.</span><span class="sxs-lookup"><span data-stu-id="45897-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="45897-117">Tipos de Atribuição</span><span class="sxs-lookup"><span data-stu-id="45897-117">Assignment types</span></span>

<span data-ttu-id="45897-118">Para que seu aplicativo seja instalado automaticamente no dispositivo após o registro, você deve selecionar Obrigatório **para** esse(s) grupo(s).</span><span class="sxs-lookup"><span data-stu-id="45897-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="45897-119">Para disponibilizar seu aplicativo para download em dispositivos inscritos por meio do portal da empresa, selecione Disponível **para dispositivos inscritos.**</span><span class="sxs-lookup"><span data-stu-id="45897-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="45897-120">Experiência do usuário final</span><span class="sxs-lookup"><span data-stu-id="45897-120">End-User Experience</span></span>

<span data-ttu-id="45897-121">Depois de configurar a configuração no Intune, você estará pronto para que os usuários finais recebam seus aplicativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="45897-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="45897-122">Siga estas etapas para obter automaticamente seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="45897-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="45897-123">Registrar seu dispositivo com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="45897-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="45897-124">Depois que o dispositivo tiver concluído o registro, você deverá receber o aplicativo em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45897-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="45897-125">Se você não estiver vendo seu aplicativo imediatamente, vá para Contas do Configurações Trabalho ou Escola suas informações de conta e role para baixo para ver informações sobre o  >    >    >   status do aplicativo instalado.</span><span class="sxs-lookup"><span data-stu-id="45897-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="45897-126">Como chegar aos aplicativos por meio do Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="45897-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="45897-127">Abra o **Menu Iniciar** e selecione **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="45897-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="45897-128">**Pesquise Portal da Empresa** e baixe o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="45897-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="45897-129">Entre em sua conta.</span><span class="sxs-lookup"><span data-stu-id="45897-129">Sign into your account.</span></span>
4. <span data-ttu-id="45897-130">Selecione o aplicativo que você deseja receber e baixe-o.</span><span class="sxs-lookup"><span data-stu-id="45897-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="45897-131">Saiba mais sobre [como instalar automaticamente o Portal da Empresa](/mem/intune/apps/company-portal-app) e implantar e gerenciar [aplicativos no Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="45897-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
