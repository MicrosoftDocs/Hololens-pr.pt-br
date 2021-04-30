---
title: Gerenciar aplicativos personalizados para o HoloLens (1ª gen)
description: Saiba como instalar, desinstalar e carregar os aplicativos Holographic personalizados em dispositivos do HoloLens usando o portal do dispositivo e o Visual Studio.
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308090"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="4f794-104">Gerenciar aplicativos personalizados para o HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="4f794-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="4f794-105">O HoloLens dá suporte a muitos aplicativos existentes do Microsoft Store, bem como a novos aplicativos criados especificamente para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f794-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="4f794-106">Este artigo se concentra em aplicativos Holographic personalizados.</span><span class="sxs-lookup"><span data-stu-id="4f794-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="4f794-107">Para obter mais informações sobre aplicativos da loja, consulte [gerenciar aplicativos com a loja](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="4f794-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f794-108">As informações a seguir foram criadas para o HoloLens (1ª gen), também chamado de edição de desenvolvedor do HoloLens no momento.</span><span class="sxs-lookup"><span data-stu-id="4f794-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="4f794-109">Assim, os aplicativos de Sideload por meio do portal do dispositivo e da instalação de aplicativos por meio do Visual Studio eram comuns.</span><span class="sxs-lookup"><span data-stu-id="4f794-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="4f794-110">Para implantações corporativas, não recomendamos habilitar o modo de desenvolvedor, que ambos os métodos usam.</span><span class="sxs-lookup"><span data-stu-id="4f794-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="4f794-111">Se você estiver interessado em um método de implantação de aplicativo seguro, examine nosso [Gerenciamento de aplicativo: visão geral](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4f794-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="4f794-112">Se você estiver procurando um método de desenvolvedor de instalação de aplicativo para dispositivos do HoloLens 2, consulte:</span><span class="sxs-lookup"><span data-stu-id="4f794-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="4f794-113">Portal do dispositivo: instalando um aplicativo</span><span class="sxs-lookup"><span data-stu-id="4f794-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="4f794-114">Usando o Visual Studio para implantar e depurar aplicativos</span><span class="sxs-lookup"><span data-stu-id="4f794-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="4f794-115">Instalar aplicativos personalizados</span><span class="sxs-lookup"><span data-stu-id="4f794-115">Install custom apps</span></span>

<span data-ttu-id="4f794-116">Você pode instalar seus próprios aplicativos no HoloLens usando o portal do dispositivo ou implantando os aplicativos do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4f794-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="4f794-117">Instalando um pacote de aplicativos com o portal do dispositivo</span><span class="sxs-lookup"><span data-stu-id="4f794-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="4f794-118">Estabeleça uma conexão do [portal do dispositivo](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) com o HoloLens de destino.</span><span class="sxs-lookup"><span data-stu-id="4f794-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="4f794-119">No painel de navegação esquerdo, navegue até a página **aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="4f794-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="4f794-120">Em **pacote do aplicativo** , navegue até o arquivo. Appx que está associado ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4f794-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4f794-121">Certifique-se de fazer referência a qualquer dependência associada e arquivos de certificado.</span><span class="sxs-lookup"><span data-stu-id="4f794-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="4f794-122">Selecione **Ir**.</span><span class="sxs-lookup"><span data-stu-id="4f794-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4f794-123">![Instalar formulário de aplicativo no portal de dispositivo do Windows no Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="4f794-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="4f794-124">Implantando do Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="4f794-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="4f794-125">Abra a solução do Visual Studio do seu aplicativo (arquivo. sln).</span><span class="sxs-lookup"><span data-stu-id="4f794-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="4f794-126">Abra as **Propriedades** do projeto.</span><span class="sxs-lookup"><span data-stu-id="4f794-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="4f794-127">Selecione a seguinte configuração de compilação: **mestre/x86/computador remoto**.</span><span class="sxs-lookup"><span data-stu-id="4f794-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="4f794-128">Quando você seleciona **computador remoto**:</span><span class="sxs-lookup"><span data-stu-id="4f794-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="4f794-129">Verifique se o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f794-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="4f794-130">Defina a autenticação como **Universal (protocolo não criptografado)**.</span><span class="sxs-lookup"><span data-stu-id="4f794-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="4f794-131">Compile sua solução.</span><span class="sxs-lookup"><span data-stu-id="4f794-131">Build your solution.</span></span>

1. <span data-ttu-id="4f794-132">Para implantar o aplicativo do seu PC de desenvolvimento em seu HoloLens, selecione **computador remoto**.</span><span class="sxs-lookup"><span data-stu-id="4f794-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="4f794-133">Se você já tiver uma compilação existente no HoloLens, selecione **Sim** para instalar essa versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="4f794-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implantação de máquina remota para aplicativos para o Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="4f794-135">O aplicativo será instalado e iniciado automaticamente no seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4f794-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="4f794-136">Depois de instalar um aplicativo, você o encontrará na lista **todos os aplicativos** (**Iniciar**  >  **todos os aplicativos**).</span><span class="sxs-lookup"><span data-stu-id="4f794-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
