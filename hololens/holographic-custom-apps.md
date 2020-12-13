---
title: Gerenciar aplicativos personalizados para o HoloLens
description: Carregar aplicativos personalizados no HoloLens. Saiba mais sobre como instalar e desinstalar os aplicativos do holográfico.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, Sideload, carregamento do lado, carregar lado a lado, loja, UWP, aplicativo, instalar
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218628"
---
# <span data-ttu-id="f0cec-105">Gerenciar aplicativos personalizados para o HoloLens</span><span class="sxs-lookup"><span data-stu-id="f0cec-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="f0cec-106">O HoloLens oferece suporte a vários aplicativos existentes na Microsoft Store, bem como novos aplicativos criados especificamente para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f0cec-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="f0cec-107">Este artigo se concentra em aplicativos de holográfico personalizados.</span><span class="sxs-lookup"><span data-stu-id="f0cec-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="f0cec-108">Para obter mais informações sobre aplicativos da loja, consulte [gerenciar aplicativos com a loja](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="f0cec-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0cec-109">As informações a seguir foram criadas para o HoloLens (1ª gen), também chamado de edição do desenvolvedor do HoloLens no momento.</span><span class="sxs-lookup"><span data-stu-id="f0cec-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="f0cec-110">Como esses aplicativos de Sideload por meio do Device portal e da instalação de aplicativos via Visual Studio foram comuns.</span><span class="sxs-lookup"><span data-stu-id="f0cec-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="f0cec-111">Para implantações corporativas, não recomendamos habilitar o modo de desenvolvedor, que ambos os métodos usam.</span><span class="sxs-lookup"><span data-stu-id="f0cec-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="f0cec-112">Se você estiver interessado em um método de implantação de aplicativo seguro, consulte a [visão geral sobre o gerenciamento de aplicativos:](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f0cec-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="f0cec-113">Se você estiver procurando por um método de desenvolvedor de instalação de aplicativo para dispositivos HoloLens 2, consulte:</span><span class="sxs-lookup"><span data-stu-id="f0cec-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="f0cec-114">Device Portal: instalando um aplicativo</span><span class="sxs-lookup"><span data-stu-id="f0cec-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="f0cec-115">Como usar o Visual Studio para implantar e depurar aplicativos</span><span class="sxs-lookup"><span data-stu-id="f0cec-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="f0cec-116">Instalar aplicativos personalizados</span><span class="sxs-lookup"><span data-stu-id="f0cec-116">Install custom apps</span></span>

<span data-ttu-id="f0cec-117">Você pode instalar seus próprios aplicativos no HoloLens usando o Device portal ou implantando os aplicativos do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0cec-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="f0cec-118">Instalando um pacote de aplicativo com o Device Portal</span><span class="sxs-lookup"><span data-stu-id="f0cec-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="f0cec-119">Estabeleça uma conexão do [Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para o HoloLens do destino.</span><span class="sxs-lookup"><span data-stu-id="f0cec-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="f0cec-120">Na navegação à esquerda, navegue até a página **aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="f0cec-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="f0cec-121">Em **pacote do aplicativo** , navegue até o arquivo. Appx associado ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f0cec-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="f0cec-122">Certifique-se de fazer referência a qualquer dependência e arquivo de certificado associados.</span><span class="sxs-lookup"><span data-stu-id="f0cec-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="f0cec-123">Selecione **ir**.</span><span class="sxs-lookup"><span data-stu-id="f0cec-123">Select **Go**.</span></span>
   ![Instalar formulário de aplicativo no Windows Device portal no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="f0cec-125">Implantando a partir do Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="f0cec-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="f0cec-126">Abra a solução do Visual Studio do seu aplicativo (arquivo. sln).</span><span class="sxs-lookup"><span data-stu-id="f0cec-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="f0cec-127">Abra as **Propriedades**do projeto.</span><span class="sxs-lookup"><span data-stu-id="f0cec-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="f0cec-128">Selecione a seguinte configuração de compilação: **Master/x86/máquina remota**.</span><span class="sxs-lookup"><span data-stu-id="f0cec-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="f0cec-129">Ao selecionar **computador remoto**:</span><span class="sxs-lookup"><span data-stu-id="f0cec-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="f0cec-130">Certifique-se de que o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f0cec-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="f0cec-131">Defina a autenticação como **Universal (protocolo não criptografado)**.</span><span class="sxs-lookup"><span data-stu-id="f0cec-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="f0cec-132">Construa sua solução.</span><span class="sxs-lookup"><span data-stu-id="f0cec-132">Build your solution.</span></span>
1. <span data-ttu-id="f0cec-133">Para implantar o aplicativo do seu computador de desenvolvimento em seu HoloLens, selecione **computador remoto**.</span><span class="sxs-lookup"><span data-stu-id="f0cec-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="f0cec-134">Se você já tiver uma compilação existente no HoloLens, selecione **Sim** para instalar esta versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="f0cec-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implantação de computador remoto para aplicativos para Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="f0cec-136">O aplicativo será instalado e iniciado automaticamente no seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f0cec-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="f0cec-137">Depois de instalar um aplicativo, você o encontrará na lista **todos os aplicativos** (**Iniciar**  >  **todos os aplicativos**).</span><span class="sxs-lookup"><span data-stu-id="f0cec-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
