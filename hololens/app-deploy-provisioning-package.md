---
title: Pacote de provisionamento
description: saiba mais sobre empacotamento de aplicativos, provisionamento, implantação e implantação de aplicativos empresariais para dispositivos HoloLens.
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635510"
---
# <a name="provisioning-package"></a><span data-ttu-id="66102-104">Pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="66102-104">Provisioning Package</span></span>

<span data-ttu-id="66102-105">Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="66102-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="66102-106">Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status do registro, durante a OOBE (configuração inicial pelo usuário) ou pela [aplicação de um pacote de provisionamento durante a instalação](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="66102-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="66102-107">Considerações sobre pacotes de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="66102-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="66102-108">Aplicativos não públicos</span><span class="sxs-lookup"><span data-stu-id="66102-108">Non-Public apps</span></span>
* <span data-ttu-id="66102-109">Somente carregamento USB</span><span class="sxs-lookup"><span data-stu-id="66102-109">USB side-load only</span></span>
* <span data-ttu-id="66102-110">Nenhuma atualização automática (requer atualizações manuais via PPKGs)</span><span class="sxs-lookup"><span data-stu-id="66102-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="66102-111">Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no repositório do computador local.</span><span class="sxs-lookup"><span data-stu-id="66102-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="66102-112">Os pacotes de provisionamento só podem instalar certificados no armazenamento do dispositivo (computador local), portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="66102-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="66102-113">Se você estiver implantando o certificado do MDM ou instalando por meio do [Gerenciador de certificados](certificate-manager.md), certifique-se de implantar o certificado no repositório do computador local para assinar aplicativos instalados dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="66102-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="66102-114">para saber os conceitos básicos da criação de um pacote de provisionamento para dispositivos HoloLens, visite [HoloLens provisionando](/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="66102-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="66102-115">Para implantar um aplicativo, você deve começar com o provisionamento avançado.</span><span class="sxs-lookup"><span data-stu-id="66102-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="66102-116">HoloLens (1º gen) tem suporte limitado para a instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="66102-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="66102-117">os dispositivos HoloLens (1ª gen) só dão suporte à instalação de um aplicativo por meio de PPKG somente durante o OOBE e somente com instalações de contexto de usuário.</span><span class="sxs-lookup"><span data-stu-id="66102-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="66102-118">Instalação</span><span class="sxs-lookup"><span data-stu-id="66102-118">Setup</span></span>

<span data-ttu-id="66102-119">no [Windows Designer de configuração](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga quatro etapas.</span><span class="sxs-lookup"><span data-stu-id="66102-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="66102-120">Defina ApplicationManagement/AllowAllTrustedApps como "Sim".</span><span class="sxs-lookup"><span data-stu-id="66102-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="66102-121">Consulte: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="66102-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="66102-122">Navegue até **UniversalAppInstall**  >  **UserContextAppLicense** Insira o **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="66102-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="66102-123">Consulte [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="66102-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="66102-124">Consulte também: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="66102-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="66102-125">Você pode usar o portal do dispositivo em um dispositivo no qual você já instalou o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="66102-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="66102-126">Visite a página de aplicativos e examine a linha PackageRelativeID, todas as informações antes de "!" É seu **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="66102-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="66102-127">Em seguida, você verá que tem uma nova seção, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="66102-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="66102-128">Use esta área para carregar seu pacote Appx.</span><span class="sxs-lookup"><span data-stu-id="66102-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="66102-129">Dependendo de se você comprou seu aplicativo ou criou seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.</span><span class="sxs-lookup"><span data-stu-id="66102-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="66102-130">Para o arquivo de licença: Navegue até **UniversalAppInstall**  >  **UserContextAppLicence** e navegue até o local da sua licença e carregue-o.</span><span class="sxs-lookup"><span data-stu-id="66102-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="66102-131">Para o arquivo de segurança, navegue até **certificados** e selecione seu certificado para instalar junto com seu pacote. Appx.</span><span class="sxs-lookup"><span data-stu-id="66102-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="66102-132">Certifique-se de salvar seu projeto em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="66102-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="66102-133">Em seguida, **exporte** -o como um **pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="66102-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="66102-134">Consulte também: [aplicar seu pacote de provisionamento ao HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="66102-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
