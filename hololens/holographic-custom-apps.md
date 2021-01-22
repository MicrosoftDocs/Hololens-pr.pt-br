---
title: Gerenciar aplicativos personalizados para HoloLens (1ª geração)
description: Saiba como instalar, desinstalar e carregar aplicativos holográficos personalizados em dispositivos HoloLens usando o Device Portal e o Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, sideload, store, uwp, app, install
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296984"
---
# <span data-ttu-id="37521-104">Gerenciar aplicativos personalizados para HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="37521-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="37521-105">O HoloLens oferece suporte a vários aplicativos existentes na Microsoft Store, bem como novos aplicativos criados especificamente para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="37521-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="37521-106">Este artigo se concentra em aplicativos holográficos personalizados.</span><span class="sxs-lookup"><span data-stu-id="37521-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="37521-107">Para obter mais informações sobre aplicativos da loja, [consulte Gerenciar aplicativos com a loja.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="37521-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37521-108">As informações a seguir foram criadas para o HoloLens (1ª geração), também chamada de HoloLens Developer Edition no momento.</span><span class="sxs-lookup"><span data-stu-id="37521-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="37521-109">Assim, o sideload de aplicativos por meio do device portal e a instalação de aplicativos por meio do Visual Studio eram em comum.</span><span class="sxs-lookup"><span data-stu-id="37521-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="37521-110">Para implantações corporativas, não recomendamos a habilitação do Modo de Desenvolvedor, que ambos os métodos usam.</span><span class="sxs-lookup"><span data-stu-id="37521-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="37521-111">Se você estiver interessado em um método de implantação de aplicativo seguro, revise nosso Gerenciamento [de Aplicativos: Visão geral](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="37521-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="37521-112">Se você estiver procurando um dos métodos de desenvolvedor de instalação de aplicativos para dispositivos HoloLens 2, confira:</span><span class="sxs-lookup"><span data-stu-id="37521-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="37521-113">Device Portal: instalando um aplicativo</span><span class="sxs-lookup"><span data-stu-id="37521-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="37521-114">Usando o Visual Studio para implantar e depurar aplicativos</span><span class="sxs-lookup"><span data-stu-id="37521-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="37521-115">Instalar aplicativos personalizados</span><span class="sxs-lookup"><span data-stu-id="37521-115">Install custom apps</span></span>

<span data-ttu-id="37521-116">Você pode instalar seus próprios aplicativos no HoloLens usando o Device Portal ou implantando os aplicativos do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="37521-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="37521-117">Instalando um pacote de aplicativos com o Device Portal</span><span class="sxs-lookup"><span data-stu-id="37521-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="37521-118">Estabeleça uma conexão [do Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) com o HoloLens de destino.</span><span class="sxs-lookup"><span data-stu-id="37521-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="37521-119">Na navegação à esquerda, navegue até a **página Aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="37521-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="37521-120">Em **Pacote de Aplicativos,** navegue até o arquivo .appx associado ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="37521-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="37521-121">Certifique-se de fazer referência a qualquer dependência associada e arquivos de certificado.</span><span class="sxs-lookup"><span data-stu-id="37521-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="37521-122">Selecione **Ir.**</span><span class="sxs-lookup"><span data-stu-id="37521-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Instalar o formulário de aplicativo no Windows Device Portal no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="37521-124">Implantação do Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="37521-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="37521-125">Abra a solução do Visual Studio do seu aplicativo (arquivo .sln).</span><span class="sxs-lookup"><span data-stu-id="37521-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="37521-126">Abra as propriedades do **projeto.**</span><span class="sxs-lookup"><span data-stu-id="37521-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="37521-127">Selecione a seguinte configuração de com build: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="37521-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="37521-128">Ao selecionar **Máquina Remota:**</span><span class="sxs-lookup"><span data-stu-id="37521-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="37521-129">Certifique-se de que o endereço aponta para o Wi-Fi IP do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="37521-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="37521-130">Definir autenticação **como Universal (Protocolo Não Criptografado).**</span><span class="sxs-lookup"><span data-stu-id="37521-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="37521-131">Crie sua solução.</span><span class="sxs-lookup"><span data-stu-id="37521-131">Build your solution.</span></span>

1. <span data-ttu-id="37521-132">Para implantar o aplicativo do seu computador de desenvolvimento em seu HoloLens, selecione **Máquina Remota.**</span><span class="sxs-lookup"><span data-stu-id="37521-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="37521-133">Se você já tiver um build existente no HoloLens, selecione **Sim** para instalar essa versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="37521-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implantação de máquina remota para aplicativos no Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="37521-135">O aplicativo será instalado e iniciará automaticamente em seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="37521-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="37521-136">Depois de instalar um aplicativo, você o encontrará \*\*\*\* na lista Todos os aplicativos (**Iniciar**  >  **todos os aplicativos).**</span><span class="sxs-lookup"><span data-stu-id="37521-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
