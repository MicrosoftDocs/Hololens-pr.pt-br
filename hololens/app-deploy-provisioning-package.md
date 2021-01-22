---
title: Pacote de provisionamento
description: Saiba mais sobre empacotamento de aplicativos, provisionamento, implantação e implantação de aplicativos corporativos para dispositivos HoloLens.
keywords: aplicativo, implantação de aplicativo, implantação de aplicativo empresarial, provisionamento
author: evmill
ms.author: v-evmill
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283692"
---
# <span data-ttu-id="295dc-104">Pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="295dc-104">Provisioning Package</span></span>

<span data-ttu-id="295dc-105">Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="295dc-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="295dc-106">Eles também podem ser implantados em um dispositivo independentemente da identidade do usuário, do status do registro, durante a configuração inicial pelo usuário (OOBE) ou pela aplicação de um pacote de [provisionamento](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="295dc-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="295dc-107">Considerações sobre pacotes de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="295dc-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="295dc-108">Aplicativos não públicos</span><span class="sxs-lookup"><span data-stu-id="295dc-108">Non-Public apps</span></span>
* <span data-ttu-id="295dc-109">Somente carregamento lateral USB</span><span class="sxs-lookup"><span data-stu-id="295dc-109">USB side-load only</span></span>
* <span data-ttu-id="295dc-110">Nenhuma atualização automática (requer atualizações manuais via PPKGs)</span><span class="sxs-lookup"><span data-stu-id="295dc-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="295dc-111">Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no armazenamento da máquina local.</span><span class="sxs-lookup"><span data-stu-id="295dc-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="295dc-112">Os pacotes de provisionamento só podem instalar certificados no armazenamento do dispositivo (máquina local), portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="295dc-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="295dc-113">Se você estiver implantando seu certificado do MDM ou instalando por meio do Gerenciador de [Certificados,](certificate-manager.md)certifique-se de implantar o certificado no armazenamento da máquina local para assinar aplicativos instalados dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="295dc-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="295dc-114">Para saber as noções básicas de criação de um pacote de provisionamento para dispositivos HoloLens, visite [o provisionamento do HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="295dc-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="295dc-115">Para implantar um aplicativo, você deve começar com o provisionamento avançado.</span><span class="sxs-lookup"><span data-stu-id="295dc-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="295dc-116">O HoloLens (1ª geração) tem suporte limitado à instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="295dc-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="295dc-117">Os dispositivos HoloLens (1ª geração) só suportam a instalação de um aplicativo via PPKG somente durante o OOBE e somente com as instalações de contexto do usuário.</span><span class="sxs-lookup"><span data-stu-id="295dc-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="295dc-118">Configuração</span><span class="sxs-lookup"><span data-stu-id="295dc-118">Setup</span></span>

<span data-ttu-id="295dc-119">No [Designer de Configuração do Windows,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) as quatro etapas são seguidas.</span><span class="sxs-lookup"><span data-stu-id="295dc-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="295dc-120">Definir ApplicationManagement/AllowAllTrustedApps como "Sim".</span><span class="sxs-lookup"><span data-stu-id="295dc-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="295dc-121">Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="295dc-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="295dc-122">Navegue **até UniversalAppInstall**  >  **UserContextAppLicense** e insira **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="295dc-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="295dc-123">Consulte [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="295dc-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="295dc-124">Consulte também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="295dc-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="295dc-125">Você pode usar o Device Portal em um dispositivo em que já instalou seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="295dc-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="295dc-126">Visite a página Aplicativos e veja a linha PackageRelativeID, todas as informações antes de "!" Seu **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="295dc-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="295dc-127">Em seguida, você verá que tem uma nova seção, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="295dc-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="295dc-128">Use essa área para carregar seu pacote appx.</span><span class="sxs-lookup"><span data-stu-id="295dc-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="295dc-129">Dependendo se você tiver comprado seu aplicativo ou criado seu próprio aplicativo LOB, precisará carregar o arquivo de licença ou o certificado de segurança.</span><span class="sxs-lookup"><span data-stu-id="295dc-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="295dc-130">Para o arquivo de licença: navegue até **UniversalAppInstall**  >  **UserContextAppLicence,** navegue até o local da sua licença e carregue-o.</span><span class="sxs-lookup"><span data-stu-id="295dc-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="295dc-131">Para o arquivo de segurança, navegue até **Certificados** e selecione seu certificado a ser instalado junto com seu pacote .appx.</span><span class="sxs-lookup"><span data-stu-id="295dc-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="295dc-132">Certifique-se de salvar seu projeto em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="295dc-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="295dc-133">Em **seguida,** exporte-o **como um pacote de provisionamento.**</span><span class="sxs-lookup"><span data-stu-id="295dc-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="295dc-134">Consulte também: [Aplicar seu pacote de provisionamento ao HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="295dc-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
