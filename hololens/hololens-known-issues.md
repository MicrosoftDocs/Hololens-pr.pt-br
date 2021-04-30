---
title: Problemas conhecidos do HoloLens
description: Mantenha-se atualizado com nossa lista de problemas conhecidos e soluções alternativas que podem afetar clientes e desenvolvedores do HoloLens usando o Unity e o portal do dispositivo Windows.
keywords: solução de problemas, problema conhecido, ajuda
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308153"
---
# <a name="known-issues-for-hololens"></a><span data-ttu-id="04c59-104">Problemas conhecidos do HoloLens</span><span class="sxs-lookup"><span data-stu-id="04c59-104">Known issues for HoloLens</span></span>

<span data-ttu-id="04c59-105">Esta é a lista atual de problemas conhecidos para dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="04c59-106">Verifique primeiro se você está vendo um comportamento estranho.</span><span class="sxs-lookup"><span data-stu-id="04c59-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="04c59-107">Essa lista será mantida atualizada conforme novos problemas forem descobertos ou relatados, ou conforme os problemas forem resolvidos em futuras atualizações de software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="04c59-108">Se você descobrir um problema que não está bloqueando, informe-o em seu dispositivo de HoloLens por meio do [Hub de comentários](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="04c59-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="04c59-109">Se o problema que você está enfrentando está bloqueando você, além de fazer o arquivamento de comentários, registre [uma solicitação de suporte](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="04c59-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="04c59-110">Problemas conhecidos para todas as gerações de HoloLens</span><span class="sxs-lookup"><span data-stu-id="04c59-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="04c59-111">Problemas conhecidos para dispositivos do HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="04c59-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="04c59-112">Problemas conhecidos do HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="04c59-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="04c59-113">Problemas conhecidos do emulador do HoloLens</span><span class="sxs-lookup"><span data-stu-id="04c59-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="04c59-114">Problemas conhecidos para todas as gerações de HoloLens</span><span class="sxs-lookup"><span data-stu-id="04c59-114">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="04c59-115">Unity</span><span class="sxs-lookup"><span data-stu-id="04c59-115">Unity</span></span>

- <span data-ttu-id="04c59-116">Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obter a versão mais atualizada do Unity recomendada para o desenvolvimento do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="04c59-117">Problemas conhecidos com a visualização técnica do Unity HoloLens são documentados nos [fóruns do Hololens Unity](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="04c59-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="04c59-118">Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="04c59-118">Windows Device Portal</span></span>

- <span data-ttu-id="04c59-119">O recurso de visualização dinâmica na captura da realidade misturada pode exibir vários segundos de latência.</span><span class="sxs-lookup"><span data-stu-id="04c59-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="04c59-120">Na página entrada virtual, os controles de gesto e de rolagem na seção gestos virtuais não são funcionais.</span><span class="sxs-lookup"><span data-stu-id="04c59-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="04c59-121">Usá-los não terá nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="04c59-121">Using them will have no effect.</span></span> <span data-ttu-id="04c59-122">O teclado virtual na mesma página funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="04c59-122">The virtual keyboard on the same page works correctly.</span></span>

- <span data-ttu-id="04c59-123">Depois de habilitar o modo de desenvolvedor em configurações, pode levar alguns segundos antes que a opção para ativar o portal do dispositivo esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="04c59-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="04c59-124">Carregamento da câmera do OneDrive</span><span class="sxs-lookup"><span data-stu-id="04c59-124">OneDrive camera upload</span></span>

<span data-ttu-id="04c59-125">O aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas corporativas ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="04c59-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="04c59-126">Soluções alternativas:</span><span class="sxs-lookup"><span data-stu-id="04c59-126">Workarounds:</span></span>

- <span data-ttu-id="04c59-127">Se for viável para sua empresa, o carregamento automático de câmera terá suporte nas contas de consumidor da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04c59-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="04c59-128">Você pode entrar em seu conta Microsoft além de sua conta corporativa ou de estudante (o aplicativo OneDrive dá suporte a logon duplo).</span><span class="sxs-lookup"><span data-stu-id="04c59-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="04c59-129">Em seu perfil de conta Microsoft no OneDrive, você pode habilitar o carregamento automático de câmera em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="04c59-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="04c59-130">Se você não pode usar com segurança um conta Microsoft de consumidor para carregar suas fotos automaticamente, você pode carregar manualmente as fotos para sua conta corporativa ou de estudante do aplicativo OneDrive.</span><span class="sxs-lookup"><span data-stu-id="04c59-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="04c59-131">Para fazer isso, verifique se você está conectado à sua conta corporativa ou de estudante no aplicativo OneDrive.</span><span class="sxs-lookup"><span data-stu-id="04c59-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="04c59-132">Selecione o **+** botão e escolha **carregar**.</span><span class="sxs-lookup"><span data-stu-id="04c59-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="04c59-133">Encontre as fotos ou vídeos que você deseja carregar navegando até **imagens > a câmera**.</span><span class="sxs-lookup"><span data-stu-id="04c59-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="04c59-134">Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o botão **abrir** .</span><span class="sxs-lookup"><span data-stu-id="04c59-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-2-devices"></a><span data-ttu-id="04c59-135">Problemas conhecidos para dispositivos do HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="04c59-135">Known issues for HoloLens 2 devices</span></span>

### <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="04c59-136">Falha ao iniciar o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="04c59-136">Microsoft Edge fails to launch</span></span>

<span data-ttu-id="04c59-137">Alguns clientes relataram um problema em que o Microsoft Edge falha ao ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="04c59-137">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="04c59-138">Para esses clientes, o problema persiste pela reinicialização e não é resolvido com atualizações do Windows ou do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="04c59-138">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="04c59-139">Se você estiver enfrentando esse problema e tiver confirmado que o [Windows está atualizado](hololens-updates.md#manually-check-for-updates), registre um bug do [aplicativo de Hub de comentários](hololens-feedback.md) com a seguinte categoria e subcategoria: instalar e atualizar > baixar, instalar e configurar Windows Update.</span><span class="sxs-lookup"><span data-stu-id="04c59-139">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="04c59-140">Não há soluções alternativas conhecidas, pois não conseguimos fazer a raiz causar o problema até o momento.</span><span class="sxs-lookup"><span data-stu-id="04c59-140">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="04c59-141">O arquivamento de um bug por meio do hub de comentários ajudará nossa investigação!</span><span class="sxs-lookup"><span data-stu-id="04c59-141">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <a name="keyboard-does-not-switch-to-special-characters"></a><span data-ttu-id="04c59-142">O teclado não muda para caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="04c59-142">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="04c59-143">Há um problema durante o OOBE, em que, depois que o usuário tiver escolhido uma conta corporativa ou de estudante e estiver inserindo sua senha, tentar alternar para os caracteres especiais no teclado tocando no botão &123 não mudará para caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="04c59-143">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="04c59-144">Solução alternativa:</span><span class="sxs-lookup"><span data-stu-id="04c59-144">Work-arounds:</span></span>
-   <span data-ttu-id="04c59-145">Feche o teclado e reabra-o tocando no campo de texto.</span><span class="sxs-lookup"><span data-stu-id="04c59-145">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="04c59-146">Insira incorretamente sua senha.</span><span class="sxs-lookup"><span data-stu-id="04c59-146">Incorrectly enter your password.</span></span> <span data-ttu-id="04c59-147">Quando o teclado for reiniciado da próxima vez, ele funcionará conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="04c59-147">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="04c59-148">Autenticação na Web, feche o teclado e selecione **entrar em outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="04c59-148">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="04c59-149">Se inserir apenas números, um usuário poderá pressionar e manter determinadas chaves para abrir um menu expandido.</span><span class="sxs-lookup"><span data-stu-id="04c59-149">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="04c59-150">Usando um teclado USB.</span><span class="sxs-lookup"><span data-stu-id="04c59-150">Using a USB keyboard.</span></span>

<span data-ttu-id="04c59-151">Isso não afeta:</span><span class="sxs-lookup"><span data-stu-id="04c59-151">This does not affect:</span></span>
- <span data-ttu-id="04c59-152">Usuários que optam por usar uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="04c59-152">Users who choose to use a personal account.</span></span>

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build"></a><span data-ttu-id="04c59-153">A tela azul é mostrada após o cancelamento do registro de builds do insider preview em um dispositivo atualizado com uma compilação Insider</span><span class="sxs-lookup"><span data-stu-id="04c59-153">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="04c59-154">Esse é um problema que afeta que os usuários que estão em uma versão de visualização Insider, reativaram seu HoloLens 2 com uma nova compilação do insider Preview e, depois, cancelaram o registro do programa Insider.</span><span class="sxs-lookup"><span data-stu-id="04c59-154">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="04c59-155">Isso não afeta:</span><span class="sxs-lookup"><span data-stu-id="04c59-155">This does not affect:</span></span>
- <span data-ttu-id="04c59-156">Usuários que não estão registrados no Windows Insider</span><span class="sxs-lookup"><span data-stu-id="04c59-156">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="04c59-157">Insiders</span><span class="sxs-lookup"><span data-stu-id="04c59-157">Insiders:</span></span>
    - <span data-ttu-id="04c59-158">Se um dispositivo tiver sido registrado desde que as compilações do insider fossem a versão 18362. x</span><span class="sxs-lookup"><span data-stu-id="04c59-158">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="04c59-159">Se eles piscaram uma compilação 19041. x assinada Insider e permanecer inscrito no programa Insider</span><span class="sxs-lookup"><span data-stu-id="04c59-159">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="04c59-160">Solução alternativa:</span><span class="sxs-lookup"><span data-stu-id="04c59-160">Work-around:</span></span> 
- <span data-ttu-id="04c59-161">Evitar o problema</span><span class="sxs-lookup"><span data-stu-id="04c59-161">Avoid the issue</span></span> 
    - <span data-ttu-id="04c59-162">Pisque um Build não Insider.</span><span class="sxs-lookup"><span data-stu-id="04c59-162">Flash a non-insider build.</span></span> <span data-ttu-id="04c59-163">Uma das atualizações regulares mensais.</span><span class="sxs-lookup"><span data-stu-id="04c59-163">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="04c59-164">Mantenha-se no Insider Preview</span><span class="sxs-lookup"><span data-stu-id="04c59-164">Stay on Insider Preview</span></span>
- <span data-ttu-id="04c59-165">Repiscar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="04c59-165">Reflash the device</span></span>

    1. <span data-ttu-id="04c59-166">Coloque o [HoloLens 2 no modo flash](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manualmente, desligando completamente enquanto não se conecta.</span><span class="sxs-lookup"><span data-stu-id="04c59-166">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="04c59-167">Em seguida, ao manter o volume ativo, toque no botão de energia.</span><span class="sxs-lookup"><span data-stu-id="04c59-167">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="04c59-168">Conecte-se ao PC e abra o complemento de recuperação avançada.</span><span class="sxs-lookup"><span data-stu-id="04c59-168">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    
    1. <span data-ttu-id="04c59-169">Atualize o HoloLens 2 para a compilação padrão.</span><span class="sxs-lookup"><span data-stu-id="04c59-169">Flash the HoloLens 2 to the default build.</span></span>   

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="04c59-170">Problemas conhecidos do HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="04c59-170">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="04c59-171">Não é possível conectar e implantar no HoloLens por meio do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04c59-171">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="04c59-172">Última atualização: 8/8 @ 5:23h-o Visual Studio lançou o VS 2019 versão 16,2, que inclui uma correção para esse problema.</span><span class="sxs-lookup"><span data-stu-id="04c59-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="04c59-173">É recomendável atualizar para esta versão mais recente para evitar que esse erro seja apresentado.</span><span class="sxs-lookup"><span data-stu-id="04c59-173">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="04c59-174">O Visual Studio lançou o VS 2019 versão 16,2, que inclui uma correção para esse problema.</span><span class="sxs-lookup"><span data-stu-id="04c59-174">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="04c59-175">É recomendável atualizar para esta versão mais recente para evitar que esse erro seja apresentado.</span><span class="sxs-lookup"><span data-stu-id="04c59-175">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="04c59-176">Causa raiz do problema: os usuários que usaram o Visual Studio 2015 ou versões anteriores do Visual Studio 2017 para implantar e depurar aplicativos em seu HoloLens e, posteriormente, usaram as versões mais recentes do Visual Studio 2017 ou do Visual Studio 2019 com o mesmo HoloLens serão afetados.</span><span class="sxs-lookup"><span data-stu-id="04c59-176">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="04c59-177">As versões mais recentes do Visual Studio implantam uma nova versão de um componente, mas os arquivos da versão mais antiga são deixados no dispositivo, fazendo com que a versão mais recente falhe.</span><span class="sxs-lookup"><span data-stu-id="04c59-177">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="04c59-178">Isso causa a seguinte mensagem de erro: DEP0100: Verifique se o dispositivo de destino tem o modo de desenvolvedor habilitado.</span><span class="sxs-lookup"><span data-stu-id="04c59-178">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="04c59-179">Não foi possível obter uma licença de desenvolvedor em \<ip\> devido ao erro 80004005.</span><span class="sxs-lookup"><span data-stu-id="04c59-179">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="04c59-180">Solução alternativa</span><span class="sxs-lookup"><span data-stu-id="04c59-180">Workaround</span></span>

<span data-ttu-id="04c59-181">Nossa equipe está trabalhando em uma correção no momento.</span><span class="sxs-lookup"><span data-stu-id="04c59-181">Our team is currently working on a fix.</span></span> <span data-ttu-id="04c59-182">Enquanto isso, você pode usar as etapas a seguir para contornar o problema e ajudar a desbloquear a implantação e a depuração:</span><span class="sxs-lookup"><span data-stu-id="04c59-182">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="04c59-183">Abra o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04c59-183">Open Visual Studio.</span></span>

1. <span data-ttu-id="04c59-184">Selecione **Arquivo** > **Novo** > **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="04c59-184">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="04c59-185">Selecione **Visual C#**  >  **Windows Desktop**  >  **console app (.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="04c59-185">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="04c59-186">Dê um nome ao projeto (como "HoloLensDeploymentFix") e verifique se a estrutura está definida para pelo menos .NET Framework 4,5 e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04c59-186">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="04c59-187">Clique com o botão direito do mouse no nó **referências** em Gerenciador de soluções e adicione as seguintes referências (selecione para a seção **procurar** e selecione **procurar**):</span><span class="sxs-lookup"><span data-stu-id="04c59-187">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="04c59-188">Se você não tiver o 10.0.18362.0 instalado, use a versão mais recente que você tem.</span><span class="sxs-lookup"><span data-stu-id="04c59-188">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="04c59-189">Clique com o botão direito do mouse no projeto em Gerenciador de soluções e selecione **Adicionar**  >  **Item existente**.</span><span class="sxs-lookup"><span data-stu-id="04c59-189">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="04c59-190">Navegue até C:\Arquivos de programas (x86) \Windows Kits\10\bin\10.0.18362.0\x86 e altere o filtro para **todos os arquivos ( \* . \* )**.</span><span class="sxs-lookup"><span data-stu-id="04c59-190">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="04c59-191">Selecione SirepClient.dll e SshClient.dll e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="04c59-191">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="04c59-192">Localize e selecione ambos os arquivos em Gerenciador de Soluções (eles devem estar na parte inferior da lista de arquivos) e altere **copiar para diretório de saída** na janela **Propriedades** para **copiar sempre**.</span><span class="sxs-lookup"><span data-stu-id="04c59-192">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="04c59-193">Na parte superior do arquivo, adicione o seguinte à lista de `using` instruções existente:</span><span class="sxs-lookup"><span data-stu-id="04c59-193">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="04c59-194">Dentro do `static void Main(...)` , adicione o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="04c59-194">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="04c59-195">Selecione **Compilar** > **Compilar Solução**.</span><span class="sxs-lookup"><span data-stu-id="04c59-195">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="04c59-196">Abra uma janela de prompt de comando e CD para a pasta que contém o arquivo. exe compilado (por exemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="04c59-196">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="04c59-197">Execute o executável e forneça o endereço IP do dispositivo como um argumento de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="04c59-197">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="04c59-198">(Se conectado usando USB, você pode usar 127.0.0.1, caso contrário, use o endereço IP Wi-Fi do dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="04c59-198">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="04c59-199">Depois que a ferramenta for encerrada sem nenhuma mensagem (isso deve levar apenas alguns segundos), agora você poderá implantar e depurar do Visual Studio 2017 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="04c59-199">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="04c59-200">O uso contínuo da ferramenta não é necessário.</span><span class="sxs-lookup"><span data-stu-id="04c59-200">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="04c59-201">Forneceremos mais atualizações à medida que forem disponibilizadas.</span><span class="sxs-lookup"><span data-stu-id="04c59-201">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="04c59-202">Problemas ao iniciar o Microsoft Store e os aplicativos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="04c59-202">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="04c59-203">Última atualização: 4/2 @ 10-problema resolvido.</span><span class="sxs-lookup"><span data-stu-id="04c59-203">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="04c59-204">Você pode enfrentar problemas ao tentar iniciar o Microsoft Store e os aplicativos no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-204">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="04c59-205">Determinamos que o problema ocorre quando as atualizações do aplicativo em segundo plano implantam uma versão mais recente dos pacotes do Framework em sequências específicas, enquanto um ou mais de seus aplicativos dependentes ainda estão em execução.</span><span class="sxs-lookup"><span data-stu-id="04c59-205">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="04c59-206">Nesse caso, uma atualização automática de aplicativo forneceu uma nova versão do .NET Native Framework (versão 10.0.25531 para 10.0.27413) fez com que os aplicativos que estão sendo executados não sejam atualizados corretamente para todos os aplicativos em execução que consomem a versão anterior do Framework.</span><span class="sxs-lookup"><span data-stu-id="04c59-206">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="04c59-207">A atualização do Flow for Framework é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="04c59-207">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="04c59-208">O novo pacote de estrutura é baixado da loja e instalado.</span><span class="sxs-lookup"><span data-stu-id="04c59-208">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="04c59-209">Todos os aplicativos que usam a estrutura mais antiga são "atualizados" para usar a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="04c59-209">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="04c59-210">Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais recente não foi registrada falharão ao iniciar no menu iniciar.</span><span class="sxs-lookup"><span data-stu-id="04c59-210">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="04c59-211">Acreditamos que qualquer aplicativo no HoloLens poderia ser afetado por esse problema.</span><span class="sxs-lookup"><span data-stu-id="04c59-211">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="04c59-212">Alguns usuários relataram que o fechamento de aplicativos suspensos e a inicialização de outros aplicativos, como hub de comentários, visualizador 3D ou fotos, resolve o problema para eles &mdash; no entanto, isso não funciona 100% do tempo.</span><span class="sxs-lookup"><span data-stu-id="04c59-212">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="04c59-213">Temos a raiz causada que esse problema não foi causado pela atualização em si, mas um bug no sistema operacional que resultou na atualização do .NET Native Framework sendo tratada incorretamente.</span><span class="sxs-lookup"><span data-stu-id="04c59-213">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="04c59-214">Temos o prazer de anunciar que identificamos uma correção e lançamos uma atualização (versão do sistema operacional 17763,380) que contém a correção.</span><span class="sxs-lookup"><span data-stu-id="04c59-214">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="04c59-215">Para ver se o dispositivo pode executar a atualização, por favor:</span><span class="sxs-lookup"><span data-stu-id="04c59-215">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="04c59-216">Vá para o aplicativo Configurações e abra **atualizar & segurança**.</span><span class="sxs-lookup"><span data-stu-id="04c59-216">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="04c59-217">Selecione **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="04c59-217">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="04c59-218">Se a atualização para 17763,380 estiver disponível, atualize para esse Build para receber a correção para o bug de parada do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="04c59-218">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="04c59-219">Após a atualização para esta versão do sistema operacional, os aplicativos devem funcionar conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="04c59-219">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="04c59-220">Além disso, como fazemos com cada versão do sistema operacional do HoloLens, publicamos a imagem FFU no [centro de download da Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).</span><span class="sxs-lookup"><span data-stu-id="04c59-220">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="04c59-221">Se você não quiser fazer a atualização, lançamos uma nova versão do aplicativo Microsoft Store UWP a partir de 3/29.</span><span class="sxs-lookup"><span data-stu-id="04c59-221">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="04c59-222">Depois de ter a versão atualizada do repositório:</span><span class="sxs-lookup"><span data-stu-id="04c59-222">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="04c59-223">Abra o repositório e confirme se ele é carregado.</span><span class="sxs-lookup"><span data-stu-id="04c59-223">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="04c59-224">Use o gesto de flor para abrir o menu.</span><span class="sxs-lookup"><span data-stu-id="04c59-224">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="04c59-225">Tentativa de abrir aplicativos interrompidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="04c59-225">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="04c59-226">Se ainda não puder ser iniciado, toque e mantenha o ícone do aplicativo interrompido e selecione Desinstalar.</span><span class="sxs-lookup"><span data-stu-id="04c59-226">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="04c59-227">Reinstale esses aplicativos da loja.</span><span class="sxs-lookup"><span data-stu-id="04c59-227">Re-install these apps from the store.</span></span>

<span data-ttu-id="04c59-228">Se o dispositivo ainda não puder carregar aplicativos, você poderá Sideload uma versão do .NET Native Framework e tempo de execução por meio do centro de download seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04c59-228">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="04c59-229">Baixe [este arquivo zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) do centro de download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04c59-229">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="04c59-230">O descompactar produzirá dois arquivos.</span><span class="sxs-lookup"><span data-stu-id="04c59-230">Unzipping will produce two files.</span></span>  <span data-ttu-id="04c59-231">Microsoft. NET. Native. Runtime. 1.7. Appx e Microsoft. NET. Native. Framework. 1.7. Appx.</span><span class="sxs-lookup"><span data-stu-id="04c59-231">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="04c59-232">Verifique se o dispositivo está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="04c59-232">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="04c59-233">Se você ainda não fez isso, consulte [usando o portal de dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="04c59-233">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="04c59-234">Em seguida, você deseja entrar no portal do dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="04c59-234">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="04c59-235">Nossa recomendação é fazer isso por USB e fazer isso digitando http://127.0.0.1:10080 em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="04c59-235">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="04c59-236">Depois de ter o portal do dispositivo Windows, precisamos que você "carregue" os dois arquivos que você baixou.</span><span class="sxs-lookup"><span data-stu-id="04c59-236">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="04c59-237">Para fazer isso, você precisa descer a barra do lado esquerdo até chegar à seção de **aplicativos** e selecionar **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="04c59-237">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="04c59-238">Em seguida, você verá uma tela semelhante à mostrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="04c59-238">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="04c59-239">Você deseja ir para a seção que diz **instalar aplicativo** e procurar onde você descompactou esses dois arquivos Appx.</span><span class="sxs-lookup"><span data-stu-id="04c59-239">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="04c59-240">Você só pode fazer uma por vez, portanto, depois de selecionar a primeira, clique em "ir" na seção implantar.</span><span class="sxs-lookup"><span data-stu-id="04c59-240">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="04c59-241">Em seguida, faça isso para o segundo arquivo APPX.</span><span class="sxs-lookup"><span data-stu-id="04c59-241">Then do this for the second APPX file.</span></span>

   ![Portal de dispositivos Windows para instalar Side-Loaded aplicativo](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="04c59-243">Neste ponto, acreditamos que seus aplicativos devem começar a funcionar novamente e que você também pode chegar à loja.</span><span class="sxs-lookup"><span data-stu-id="04c59-243">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="04c59-244">Em alguns casos, é necessário executar a etapa adicional de iniciar o aplicativo do visualizador 3D antes que os aplicativos afetados sejam iniciados.</span><span class="sxs-lookup"><span data-stu-id="04c59-244">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="04c59-245">Agradecemos sua paciência, já que passamos pelo processo para resolver esse problema, e esperamos continuar trabalhando com nossa comunidade para criar experiências de realidade misturadas bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="04c59-245">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="04c59-246">Atualização do dispositivo</span><span class="sxs-lookup"><span data-stu-id="04c59-246">Device Update</span></span>

- <span data-ttu-id="04c59-247">30 segundos após uma nova atualização, o Shell pode desaparecer uma vez.</span><span class="sxs-lookup"><span data-stu-id="04c59-247">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="04c59-248">Execute o gesto de **cair** para continuar a sessão.</span><span class="sxs-lookup"><span data-stu-id="04c59-248">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="04c59-249">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04c59-249">Visual Studio</span></span>

- <span data-ttu-id="04c59-250">Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obter a versão mais atualizada do Visual Studio que é recomendada para o desenvolvimento do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-250">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="04c59-251">Ao implantar um aplicativo do Visual Studio em seu HoloLens, você poderá ver o erro: **a operação solicitada não pode ser executada em um arquivo com uma seção mapeada pelo usuário aberta. (Exceção de HRESULT: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="04c59-251">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="04c59-252">Se isso acontecer, tente novamente e sua implantação geralmente terá sucesso.</span><span class="sxs-lookup"><span data-stu-id="04c59-252">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="04c59-253">API</span><span class="sxs-lookup"><span data-stu-id="04c59-253">API</span></span>

- <span data-ttu-id="04c59-254">Se o aplicativo definir o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) por trás do usuário ou o normal para a câmera. encaminhar, os hologramas não aparecerão em fotos ou vídeos de captura de realidade misturada.</span><span class="sxs-lookup"><span data-stu-id="04c59-254">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="04c59-255">Até que esse bug seja corrigido no Windows, se os aplicativos definirem ativamente o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) , eles devem garantir que o plano normal esteja definido na frente da câmera oposta (por exemplo, normal =-Camera. Forward).</span><span class="sxs-lookup"><span data-stu-id="04c59-255">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="04c59-256">Controle sem Fio Xbox</span><span class="sxs-lookup"><span data-stu-id="04c59-256">Xbox Wireless Controller</span></span>

- <span data-ttu-id="04c59-257">Os S do controlador sem fio do Xbox devem ser atualizados para que possam ser usados com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-257">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="04c59-258">Verifique se você está [atualizado](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) antes de tentar emparelhar seu controlador com um HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-258">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="04c59-259">Se você reinicializar o HoloLens enquanto o controlador sem fio do Xbox estiver conectado, o controlador não será reconectado automaticamente ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-259">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="04c59-260">A luz do botão de guia piscará lentamente até que o controlador seja desligado após 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="04c59-260">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="04c59-261">Para reconectar o controlador imediatamente, desligue o controlador mantendo o botão guia até que a luz se apague.</span><span class="sxs-lookup"><span data-stu-id="04c59-261">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="04c59-262">Quando você ligar o controlador novamente, ele se reconectará ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-262">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="04c59-263">Se o seu HoloLens entrar em espera enquanto o controlador sem fio do Xbox estiver conectado, qualquer entrada no controlador ativará o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="04c59-263">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="04c59-264">Você pode evitar isso desligando o controlador quando terminar de usá-lo.</span><span class="sxs-lookup"><span data-stu-id="04c59-264">You can prevent this by powering off your controller when you are done using it.</span></span>

## <a name="known-issues-for-hololens-emulator"></a><span data-ttu-id="04c59-265">Problemas conhecidos do emulador do HoloLens</span><span class="sxs-lookup"><span data-stu-id="04c59-265">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="04c59-266">Nem todos os aplicativos na Microsoft Store são compatíveis com o emulador.</span><span class="sxs-lookup"><span data-stu-id="04c59-266">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="04c59-267">Por exemplo, jovens conkers e fragmentos não são reproduzidos no emulador.</span><span class="sxs-lookup"><span data-stu-id="04c59-267">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="04c59-268">Não é possível usar a webcam do PC no emulador.</span><span class="sxs-lookup"><span data-stu-id="04c59-268">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="04c59-269">O recurso de visualização dinâmica do portal do dispositivo Windows não funciona com o emulador.</span><span class="sxs-lookup"><span data-stu-id="04c59-269">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="04c59-270">Você ainda pode capturar vídeos e imagens de realidade misturada.</span><span class="sxs-lookup"><span data-stu-id="04c59-270">You can still capture Mixed Reality videos and images.</span></span>
