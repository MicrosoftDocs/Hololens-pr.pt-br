---
title: Portal do Intune e da empresa
description: Intune, gerenciamento de aplicativos, aplicativo, portal da empresa, portal
keywords: Intune, gerenciamento de aplicativos, aplicativo, portal da empresa, portal, hololens
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
ms.openlocfilehash: 7871d5113b6803a3f702bf8d64f16fabc1c5a9bb
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252652"
---
# <span data-ttu-id="95e25-104">Portal do Intune e da empresa</span><span class="sxs-lookup"><span data-stu-id="95e25-104">Intune & Company Portal</span></span>

<span data-ttu-id="95e25-105">Com o gerenciamento de dispositivos móveis (MDM), você pode usar seus próprios aplicativos personalizados por meio do [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implantá-lo diretamente em seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="95e25-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="95e25-106">O Microsoft Intune é um serviço baseado em nuvem que enfoca o gerenciamento de dispositivos móveis (MDM) e o gerenciamento de aplicativo móvel (MAM).</span><span class="sxs-lookup"><span data-stu-id="95e25-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="95e25-107">O Intune está incluído no [pacote Microsoft Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)e permite que os usuários sejam produtivos enquanto mantêm seus dados de organização protegidos.</span><span class="sxs-lookup"><span data-stu-id="95e25-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="95e25-108">Para saber mais sobre o Intune, leia [o que é o Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="95e25-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="95e25-109">Configuração</span><span class="sxs-lookup"><span data-stu-id="95e25-109">Setup</span></span>

1. <span data-ttu-id="95e25-110">Carregue um aplicativo para uma linha de negócios ou carregue um aplicativo personalizado para o seu locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="95e25-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="95e25-111">Consulte também: [Gerenciamento de aplicativos corporativos](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="95e25-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="95e25-112">[Atribua seu aplicativo a um grupo](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="95e25-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="95e25-113">Com base no tipo de atribuição escolhido, o aplicativo pode ser entregue automaticamente ou disponível para ser imediatamente puxado se você tiver uma seleção de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="95e25-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="95e25-114">Ao criar seu pacote Appx, certifique-se de incluir a arquitetura para o (s) dispositivo (s) em que você está implantando.</span><span class="sxs-lookup"><span data-stu-id="95e25-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="95e25-115">O HoloLens 2 é ARM64 e HoloLens (1ª gen) é x86.</span><span class="sxs-lookup"><span data-stu-id="95e25-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="95e25-116">Você pode incluir ambos em um único pacote Appx se planejar ter um ambiente de dispositivos mistos.</span><span class="sxs-lookup"><span data-stu-id="95e25-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="95e25-117">Tipos de atribuição</span><span class="sxs-lookup"><span data-stu-id="95e25-117">Assignment types</span></span>

<span data-ttu-id="95e25-118">Para que seu aplicativo seja instalado automaticamente no dispositivo após o registro, você deve selecionar **obrigatório** para esse (s) grupo (s).</span><span class="sxs-lookup"><span data-stu-id="95e25-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="95e25-119">Para disponibilizar o aplicativo para download em dispositivos registrados no portal da empresa, selecione **disponível para dispositivos registrados**.</span><span class="sxs-lookup"><span data-stu-id="95e25-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="95e25-120">Experiência End-User</span><span class="sxs-lookup"><span data-stu-id="95e25-120">End-User Experience</span></span>

<span data-ttu-id="95e25-121">Depois de configurar a configuração no Intune, você estará pronto para que os usuários finais recebam seus aplicativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="95e25-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="95e25-122">Siga estas etapas para obter automaticamente seu (s) aplicativo (s):</span><span class="sxs-lookup"><span data-stu-id="95e25-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="95e25-123">Registre seu dispositivo com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="95e25-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="95e25-124">Depois que o dispositivo concluir o registro, você deverá receber o aplicativo em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95e25-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="95e25-125">Se você não estiver vendo o aplicativo imediatamente, vá para **configurações**  >  **contas**  >  **corporativas ou**  >  *de estudante da sua conta* e role para baixo para ver as informações sobre o status do aplicativo instalado.</span><span class="sxs-lookup"><span data-stu-id="95e25-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="95e25-126">Como acessar os aplicativos por meio do portal da empresa:</span><span class="sxs-lookup"><span data-stu-id="95e25-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="95e25-127">Abra o **menu iniciar** e selecione **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="95e25-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="95e25-128">Procure **portal da empresa** e baixe o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95e25-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="95e25-129">Conecte-se à sua conta.</span><span class="sxs-lookup"><span data-stu-id="95e25-129">Sign into your account.</span></span>
4. <span data-ttu-id="95e25-130">Selecione o aplicativo que você deseja receber e baixe-o.</span><span class="sxs-lookup"><span data-stu-id="95e25-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="95e25-131">Saiba mais sobre [a instalação automática do portal da empresa e a](https://docs.microsoft.com/mem/intune/apps/company-portal-app) [implantação e gerenciamento de aplicativos no Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="95e25-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
