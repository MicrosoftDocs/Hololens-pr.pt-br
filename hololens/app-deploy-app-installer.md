---
title: Como carregar e instalar aplicativos pelo instalador do aplicativo HoloLens 2
description: Carregar e instalar aplicativos por meio da interface do usuário
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027454"
---
# <span data-ttu-id="979d4-104">Instalar aplicativos no HoloLens 2 via instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="979d4-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="979d4-105">Agora os usuários podem instalar aplicativos por meio de pacotes Appx sem a necessidade de habilitar o modo de desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="979d4-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="979d4-106">Essa experiência é simples para a instalação de aplicativos em dispositivos locais ou o compartilhamento de um aplicativo com outra pessoa que não esteja familiarizado com outros métodos de instalação de aplicativo no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="979d4-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="979d4-107">No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="979d4-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="979d4-108">[Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="979d4-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="979d4-109">A configuração da solução de seu aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja.</span><span class="sxs-lookup"><span data-stu-id="979d4-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="979d4-110">Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="979d4-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="979d4-111">Verifique se o seu dispositivo do HoloLens 2 está ligado e se você está conectado.</span><span class="sxs-lookup"><span data-stu-id="979d4-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="979d4-112">No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="979d4-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="979d4-113">Depois de concluir a cópia do seu arquivo, você pode desconectar seu dispositivo e concluir a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="979d4-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="979d4-114">Em seu dispositivo do HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="979d4-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="979d4-115">Navegue até a pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="979d4-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="979d4-116">Talvez seja necessário no painel esquerdo do aplicativo selecione **este dispositivo** primeiro e, em seguida, navegue até downloads.</span><span class="sxs-lookup"><span data-stu-id="979d4-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="979d4-117">Selecione o arquivo yourapp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="979d4-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="979d4-118">O instalador do aplicativo será iniciado.</span><span class="sxs-lookup"><span data-stu-id="979d4-118">The App Installer will launch.</span></span> <span data-ttu-id="979d4-119">Selecione o botão **instalar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="979d4-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="979d4-120">O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="979d4-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="979d4-122">Se o aplicativo não tiver sido instalado, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="979d4-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="979d4-123">Seu aplicativo é uma compilação mestre ou de versão.</span><span class="sxs-lookup"><span data-stu-id="979d4-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="979d4-124">Você está [conectado à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="979d4-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="979d4-125">Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="979d4-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
