---
title: Gerenciar aplicativos personalizados para o HoloLens
description: Carregar aplicativos personalizados no HoloLens. Saiba mais sobre como instalar e desinstalar os aplicativos do holográfico.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827591"
---
# <span data-ttu-id="90d70-105">Gerenciar aplicativos personalizados para o HoloLens</span><span class="sxs-lookup"><span data-stu-id="90d70-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="90d70-106">O HoloLens dá suporte a muitos aplicativos existentes da Microsoft Store, bem como novos aplicativos criados especificamente para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="90d70-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="90d70-107">Este artigo se concentra em aplicativos de holográfico personalizados.</span><span class="sxs-lookup"><span data-stu-id="90d70-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="90d70-108">Para obter mais informações sobre aplicativos da loja, consulte [gerenciar aplicativos com a loja](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="90d70-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="90d70-109">Instalar aplicativos personalizados</span><span class="sxs-lookup"><span data-stu-id="90d70-109">Install custom apps</span></span>

<span data-ttu-id="90d70-110">Você pode instalar seus próprios aplicativos no HoloLens usando o Device portal ou implantando os aplicativos do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="90d70-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="90d70-111">Instalando um pacote de aplicativo com o Device Portal</span><span class="sxs-lookup"><span data-stu-id="90d70-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="90d70-112">Estabeleça uma conexão do [Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para o HoloLens do destino.</span><span class="sxs-lookup"><span data-stu-id="90d70-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="90d70-113">Na navegação à esquerda, navegue até a página **aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="90d70-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="90d70-114">Em **pacote do aplicativo** , navegue até o arquivo. Appx associado ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="90d70-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="90d70-115">Certifique-se de fazer referência a qualquer dependência e arquivo de certificado associados.</span><span class="sxs-lookup"><span data-stu-id="90d70-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="90d70-116">Selecione **ir**.</span><span class="sxs-lookup"><span data-stu-id="90d70-116">Select **Go**.</span></span>
   ![Instalar formulário de aplicativo no Windows Device portal no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="90d70-118">Implantando a partir do Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="90d70-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="90d70-119">Abra a solução do Visual Studio do seu aplicativo (arquivo. sln).</span><span class="sxs-lookup"><span data-stu-id="90d70-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="90d70-120">Abra as **Propriedades**do projeto.</span><span class="sxs-lookup"><span data-stu-id="90d70-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="90d70-121">Selecione a seguinte configuração de compilação: **Master/x86/máquina remota**.</span><span class="sxs-lookup"><span data-stu-id="90d70-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="90d70-122">Ao selecionar **computador remoto**:</span><span class="sxs-lookup"><span data-stu-id="90d70-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="90d70-123">Certifique-se de que o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="90d70-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="90d70-124">Defina a autenticação como **Universal (protocolo não criptografado)**.</span><span class="sxs-lookup"><span data-stu-id="90d70-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="90d70-125">Construa sua solução.</span><span class="sxs-lookup"><span data-stu-id="90d70-125">Build your solution.</span></span>
1. <span data-ttu-id="90d70-126">Para implantar o aplicativo do seu computador de desenvolvimento em seu HoloLens, selecione **computador remoto**.</span><span class="sxs-lookup"><span data-stu-id="90d70-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="90d70-127">Se você já tiver uma compilação existente no HoloLens, selecione **Sim** para instalar esta versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="90d70-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implantação de computador remoto para aplicativos para Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="90d70-129">O aplicativo será instalado e iniciado automaticamente no seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="90d70-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="90d70-130">Depois de instalar um aplicativo, você o encontrará na lista **todos os aplicativos** (**Iniciar**  >  **todos os aplicativos**).</span><span class="sxs-lookup"><span data-stu-id="90d70-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
