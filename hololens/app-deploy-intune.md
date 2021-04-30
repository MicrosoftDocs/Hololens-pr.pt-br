---
title: Intune e Portal da Empresa
description: Saiba como configurar, atribuir e criar uma experiência de usuário confortável com o Intune, o gerenciamento de dispositivos móveis e o portal da empresa.
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308216"
---
# <a name="intune--company-portal"></a><span data-ttu-id="a8798-104">& do Intune Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="a8798-104">Intune & Company Portal</span></span>

<span data-ttu-id="a8798-105">Com o MDM (gerenciamento de dispositivo móvel), você pode usar seus próprios aplicativos personalizados por meio do [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implantá-lo diretamente em seus dispositivos de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a8798-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="a8798-106">O Microsoft Intune é um serviço baseado em nuvem que se concentra no MDM (gerenciamento de dispositivo móvel) e no MAM (gerenciamento de aplicativo móvel).</span><span class="sxs-lookup"><span data-stu-id="a8798-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="a8798-107">O Intune está incluído no [pacote de EMS (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) e permite que os usuários sejam produtivos, garantindo a proteção dos dados da organização.</span><span class="sxs-lookup"><span data-stu-id="a8798-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="a8798-108">Para saber mais sobre o Intune, leia [o que é o Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="a8798-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="a8798-109">Instalação</span><span class="sxs-lookup"><span data-stu-id="a8798-109">Setup</span></span>

1. <span data-ttu-id="a8798-110">Carregar um aplicativo para uma linha de negócios ou carregar um aplicativo personalizado para seu locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="a8798-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="a8798-111">Consulte também: [Gerenciamento de aplicativos empresariais](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="a8798-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="a8798-112">[Atribua seu aplicativo a um grupo](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="a8798-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="a8798-113">Com base no tipo de atribuição escolhido, o aplicativo pode ser entregue automaticamente ou disponível para ser imediatamente retirado se você tiver uma seleção de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a8798-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="a8798-114">Ao criar seu pacote Appx, certifique-se de incluir a arquitetura para os dispositivos nos quais você está implantando.</span><span class="sxs-lookup"><span data-stu-id="a8798-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="a8798-115">O HoloLens 2 é ARM64 e o HoloLens (1º gen) é x86.</span><span class="sxs-lookup"><span data-stu-id="a8798-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="a8798-116">Você pode incluir ambos em um único pacote Appx se planejar ter um ambiente de dispositivos mistos.</span><span class="sxs-lookup"><span data-stu-id="a8798-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="a8798-117">Tipos de Atribuição</span><span class="sxs-lookup"><span data-stu-id="a8798-117">Assignment types</span></span>

<span data-ttu-id="a8798-118">Para que seu aplicativo seja instalado automaticamente no dispositivo após o registro, você deve selecionar **necessário** para esse grupo.</span><span class="sxs-lookup"><span data-stu-id="a8798-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="a8798-119">Para disponibilizar seu aplicativo para download em dispositivos registrados por meio do portal da empresa, selecione **disponível para dispositivos registrados**.</span><span class="sxs-lookup"><span data-stu-id="a8798-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="a8798-120">Experiência do usuário final</span><span class="sxs-lookup"><span data-stu-id="a8798-120">End-User Experience</span></span>

<span data-ttu-id="a8798-121">Depois de configurar a configuração no Intune, você estará pronto para que os usuários finais recebam seus aplicativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="a8798-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="a8798-122">Siga estas etapas para obter automaticamente seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="a8798-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="a8798-123">Registre seu dispositivo com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="a8798-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="a8798-124">Depois que o dispositivo tiver concluído o registro, você deverá receber o aplicativo em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a8798-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="a8798-125">Se você não estiver vendo seu aplicativo imediatamente, vá para **configurações**  >  **contas**  >  **trabalho ou escola**  >  *suas* informações de conta e role para baixo para ver informações sobre o status do aplicativo instalado.</span><span class="sxs-lookup"><span data-stu-id="a8798-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="a8798-126">Como obter aplicativos por meio do Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="a8798-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="a8798-127">Abra o **menu iniciar** e selecione **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="a8798-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="a8798-128">Pesquise **portal da empresa** e baixe o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a8798-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="a8798-129">Entre em sua conta.</span><span class="sxs-lookup"><span data-stu-id="a8798-129">Sign into your account.</span></span>
4. <span data-ttu-id="a8798-130">Selecione o aplicativo que você deseja receber e baixe-o.</span><span class="sxs-lookup"><span data-stu-id="a8798-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="a8798-131">Saiba mais sobre como [instalar automaticamente o portal da empresa](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e [implantar e gerenciar aplicativos no Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span><span class="sxs-lookup"><span data-stu-id="a8798-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
