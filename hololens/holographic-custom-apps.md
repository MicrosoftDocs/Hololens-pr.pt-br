---
title: gerenciar aplicativos personalizados para HoloLens (1ª gen)
description: saiba como instalar, desinstalar e carregar no lado os aplicativos holographic personalizados em dispositivos HoloLens usando o Portal do dispositivo e o Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, Sideload, carga lateral, carga lateral, armazenamento, UWP, aplicativo, instalação
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635901"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="ab9c5-104">gerenciar aplicativos personalizados para HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="ab9c5-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="ab9c5-105">o HoloLens dá suporte a muitos aplicativos existentes do Microsoft Store, bem como a novos aplicativos criados especificamente para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="ab9c5-106">Este artigo se concentra em aplicativos Holographic personalizados.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="ab9c5-107">Para obter mais informações sobre aplicativos da loja, consulte [gerenciar aplicativos com a loja](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ab9c5-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab9c5-108">as informações a seguir foram criadas para a HoloLens (1ª gen), também chamada de HoloLens developer Edition no momento.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="ab9c5-109">como esses aplicativos de sideload por meio do portal do dispositivo e a instalação de aplicativos via Visual Studio eram comuns.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="ab9c5-110">Para implantações corporativas, não recomendamos habilitar o modo de desenvolvedor, que ambos os métodos usam.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="ab9c5-111">Se você estiver interessado em um método de implantação de aplicativo seguro, examine nosso [Gerenciamento de aplicativo: visão geral](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ab9c5-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="ab9c5-112">se você estiver procurando um método de desenvolvedor de instalação de aplicativo para dispositivos HoloLens 2, consulte:</span><span class="sxs-lookup"><span data-stu-id="ab9c5-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="ab9c5-113">Portal do dispositivo: instalando um aplicativo</span><span class="sxs-lookup"><span data-stu-id="ab9c5-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="ab9c5-114">usando Visual Studio para implantar e depurar aplicativos</span><span class="sxs-lookup"><span data-stu-id="ab9c5-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="ab9c5-115">Instalar aplicativos personalizados</span><span class="sxs-lookup"><span data-stu-id="ab9c5-115">Install custom apps</span></span>

<span data-ttu-id="ab9c5-116">você pode instalar seus próprios aplicativos em HoloLens usando o Portal do dispositivo ou implantando os aplicativos do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="ab9c5-117">Instalando um pacote de aplicativos com o portal do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ab9c5-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="ab9c5-118">Estabeleça uma conexão do [portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal) com o HoloLens de destino.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="ab9c5-119">No painel de navegação esquerdo, navegue até a página **aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="ab9c5-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="ab9c5-120">Em **pacote do aplicativo** , navegue até o arquivo. Appx que está associado ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ab9c5-121">Certifique-se de fazer referência a qualquer dependência associada e arquivos de certificado.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="ab9c5-122">Selecione **Ir**.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab9c5-123">![instalar formulário de aplicativo no Portal do dispositivo Windows no Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="ab9c5-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="ab9c5-124">implantando do Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="ab9c5-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="ab9c5-125">abra a solução de Visual Studio do seu aplicativo (arquivo. sln).</span><span class="sxs-lookup"><span data-stu-id="ab9c5-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="ab9c5-126">Abra as **Propriedades** do projeto.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="ab9c5-127">Selecione a seguinte configuração de compilação: **mestre/x86/computador remoto**.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="ab9c5-128">Quando você seleciona **computador remoto**:</span><span class="sxs-lookup"><span data-stu-id="ab9c5-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="ab9c5-129">Verifique se o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="ab9c5-130">Defina a autenticação como **Universal (protocolo não criptografado)**.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="ab9c5-131">Compile sua solução.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-131">Build your solution.</span></span>

1. <span data-ttu-id="ab9c5-132">para implantar o aplicativo do seu PC de desenvolvimento em seu HoloLens, selecione **computador remoto**.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="ab9c5-133">se você já tiver uma compilação existente no HoloLens, selecione **sim** para instalar essa versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![implantação de máquina remota para aplicativos para Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="ab9c5-135">O aplicativo será instalado e iniciado automaticamente no seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ab9c5-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="ab9c5-136">Depois de instalar um aplicativo, você o encontrará na lista **todos os aplicativos** (**Iniciar**  >  **todos os aplicativos**).</span><span class="sxs-lookup"><span data-stu-id="ab9c5-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
