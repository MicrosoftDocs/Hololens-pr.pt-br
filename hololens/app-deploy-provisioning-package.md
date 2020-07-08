---
title: Pacote de provisionamento
description: aplicativo, implantação de aplicativo, Enterprise app demployment, provisionamento
keywords: aplicativo, implantação de aplicativo, Enterprise app demployment, provisionamento
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857869"
---
# <span data-ttu-id="698bc-104">Pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="698bc-104">Provisioning Package</span></span>

<span data-ttu-id="698bc-105">Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="698bc-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="698bc-106">Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status de inscrição, durante a experiência inicial (OOBE) ou pela [aplicação de um pacote de provisionamento durante a instalação](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="698bc-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="698bc-107">Considerações sobre pacotes de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="698bc-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="698bc-108">Aplicativos não públicos</span><span class="sxs-lookup"><span data-stu-id="698bc-108">Non-Public apps</span></span>
* <span data-ttu-id="698bc-109">Somente o carregamento do lado USB</span><span class="sxs-lookup"><span data-stu-id="698bc-109">USB side-load only</span></span>
* <span data-ttu-id="698bc-110">Sem atualização automática (exige atualizações manuais por meio do PPKGs)</span><span class="sxs-lookup"><span data-stu-id="698bc-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="698bc-111">Para saber mais sobre como criar um pacote de provisionamento para dispositivos HoloLens, acesse o [provisionamento do hololens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="698bc-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="698bc-112">Para implantar um aplicativo, você deve começar com o provisionamento avançado.</span><span class="sxs-lookup"><span data-stu-id="698bc-112">To deploy an app, you must start with advanced provisioning.</span></span> 

## <span data-ttu-id="698bc-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="698bc-113">Setup</span></span>

<span data-ttu-id="698bc-114">No [Designer de configuração do Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga as 4 etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="698bc-114">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="698bc-115">Defina ApplicationManagement/AllowAllTrustedApps como "Sim".</span><span class="sxs-lookup"><span data-stu-id="698bc-115">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="698bc-116">Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="698bc-116">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="698bc-117">Em **UniversalAppInstall**  >  **UserContextAppLicense** , digite o **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="698bc-117">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="698bc-118">Consulte [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="698bc-118">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="698bc-119">Consulte também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="698bc-119">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="698bc-120">Se não souber isso, você pode usar o Device portal em um dispositivo em que você já instalou o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="698bc-120">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="698bc-121">Acesse a página aplicativos e veja a linha PackageRelativeID, todas as informações antes do "!" É o seu **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="698bc-121">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="698bc-122">Em seguida, você verá que tem uma nova seção, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="698bc-122">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="698bc-123">Use esta área para carregar seu pacote Appx.</span><span class="sxs-lookup"><span data-stu-id="698bc-123">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="698bc-124">Dependendo se você comprou o aplicativo ou criou seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.</span><span class="sxs-lookup"><span data-stu-id="698bc-124">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="698bc-125">Para o arquivo de licença: em **UniversalAppInstall**  >  **UserContextAppLience** e navegue até o local da sua licença e carregue-o.</span><span class="sxs-lookup"><span data-stu-id="698bc-125">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="698bc-126">Para o arquivo de segurança, navegue até **certificados** e selecione seu certificado para instalar juntamente com seu pacote. Appx.</span><span class="sxs-lookup"><span data-stu-id="698bc-126">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="698bc-127">Certifique-se de salvar seu projeto em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="698bc-127">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="698bc-128">Em seguida, **exporte** -o como um **pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="698bc-128">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="698bc-129">Consulte também: [aplicar seu pacote provisiong ao HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="698bc-129">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
