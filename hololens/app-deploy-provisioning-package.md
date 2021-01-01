---
title: Pacote de Provisionamento
description: aplicativo, implantação de aplicativo, implantação de aplicativo empresarial, provisionamento
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
ms.openlocfilehash: 11bc83be188e1b81959690efcb2bdf26d800aae3
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252672"
---
# <span data-ttu-id="2b00c-104">Pacote de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="2b00c-104">Provisioning Package</span></span>

<span data-ttu-id="2b00c-105">Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="2b00c-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="2b00c-106">Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status de inscrição, durante a experiência inicial (OOBE) ou pela [aplicação de um pacote de provisionamento durante a instalação](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="2b00c-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="2b00c-107">Considerações sobre pacotes de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="2b00c-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="2b00c-108">Aplicativos não públicos</span><span class="sxs-lookup"><span data-stu-id="2b00c-108">Non-Public apps</span></span>
* <span data-ttu-id="2b00c-109">Somente o carregamento do lado USB</span><span class="sxs-lookup"><span data-stu-id="2b00c-109">USB side-load only</span></span>
* <span data-ttu-id="2b00c-110">Sem atualização automática (exige atualizações manuais por meio do PPKGs)</span><span class="sxs-lookup"><span data-stu-id="2b00c-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="2b00c-111">Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no repositório do computador local.</span><span class="sxs-lookup"><span data-stu-id="2b00c-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="2b00c-112">Os pacotes de provisionamento só podem instalar certificados no repositório do dispositivo (computador local), portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de configuração.</span><span class="sxs-lookup"><span data-stu-id="2b00c-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="2b00c-113">Se você estiver implantando seu certificado do MDM ou instalando por meio do [Gerenciador de certificados](certificate-manager.md), certifique-se de implantar o certificado no repositório da máquina local para assinar aplicativos instalados dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="2b00c-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="2b00c-114">Para saber mais sobre como criar um pacote de provisionamento para dispositivos HoloLens, acesse o [provisionamento do hololens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="2b00c-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="2b00c-115">Para implantar um aplicativo, você deve começar com o provisionamento avançado.</span><span class="sxs-lookup"><span data-stu-id="2b00c-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="2b00c-116">O HoloLens (1ª gen) tem suporte limitado para a instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="2b00c-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="2b00c-117">Os dispositivos HoloLens (1ª gen) só dão suporte à instalação de um aplicativo via PPKG durante o OOBE e somente com instalações de contexto de usuário.</span><span class="sxs-lookup"><span data-stu-id="2b00c-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="2b00c-118">Configuração</span><span class="sxs-lookup"><span data-stu-id="2b00c-118">Setup</span></span>

<span data-ttu-id="2b00c-119">Dentro do [Designer de configuração do Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga quatro etapas.</span><span class="sxs-lookup"><span data-stu-id="2b00c-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="2b00c-120">Defina ApplicationManagement/AllowAllTrustedApps como "Sim".</span><span class="sxs-lookup"><span data-stu-id="2b00c-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="2b00c-121">Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="2b00c-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="2b00c-122">Navegue até **UniversalAppInstall**  >  **UserContextAppLicense** Insira o **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="2b00c-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="2b00c-123">Consulte [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="2b00c-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="2b00c-124">Consulte também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="2b00c-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="2b00c-125">Você pode usar o Device portal em um dispositivo em que você já instalou o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2b00c-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="2b00c-126">Acesse a página aplicativos e veja a linha PackageRelativeID, todas as informações antes do "!" É o seu **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="2b00c-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="2b00c-127">Em seguida, você verá que tem uma nova seção, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="2b00c-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="2b00c-128">Use esta área para carregar seu pacote Appx.</span><span class="sxs-lookup"><span data-stu-id="2b00c-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="2b00c-129">Dependendo se você comprou o aplicativo ou criou seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.</span><span class="sxs-lookup"><span data-stu-id="2b00c-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="2b00c-130">Para o arquivo de licença: Navegue até **UniversalAppInstall**  >  **UserContextAppLicence** e navegue até o local da sua licença e carregue-o.</span><span class="sxs-lookup"><span data-stu-id="2b00c-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="2b00c-131">Para o arquivo de segurança, navegue até **certificados** e selecione seu certificado para instalar juntamente com seu pacote. Appx.</span><span class="sxs-lookup"><span data-stu-id="2b00c-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="2b00c-132">Certifique-se de salvar seu projeto em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="2b00c-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="2b00c-133">Em seguida, **exporte** -o como um **pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="2b00c-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="2b00c-134">Consulte também: [aplicar seu pacote de provisionamento ao HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="2b00c-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
