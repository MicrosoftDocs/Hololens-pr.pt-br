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
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397777"
---
# <a name="known-issues-for-hololens"></a><span data-ttu-id="a1a28-104">Problemas conhecidos do HoloLens</span><span class="sxs-lookup"><span data-stu-id="a1a28-104">Known issues for HoloLens</span></span>

<span data-ttu-id="a1a28-105">Aqui está a lista atual de problemas conhecidos para dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="a1a28-106">Verifique primeiro se você está vendo um comportamento estranho.</span><span class="sxs-lookup"><span data-stu-id="a1a28-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="a1a28-107">Essa lista será mantida atualizada conforme novos problemas forem descobertos ou relatados, ou conforme os problemas forem resolvidos em futuras atualizações de software do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="a1a28-108">Se você descobrir um problema que não está bloqueando, informe-o em seu dispositivo de HoloLens por meio do [Hub de comentários](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="a1a28-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="a1a28-109">Se o problema que você está enfrentando está bloqueando você, além de fazer o arquivamento de comentários, registre [uma solicitação de suporte](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="a1a28-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="a1a28-110">Problemas conhecidos para todas as gerações de HoloLens</span><span class="sxs-lookup"><span data-stu-id="a1a28-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="a1a28-111">Problemas conhecidos para dispositivos do HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a1a28-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="a1a28-112">Problemas conhecidos do HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="a1a28-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="a1a28-113">Problemas conhecidos do emulador do HoloLens</span><span class="sxs-lookup"><span data-stu-id="a1a28-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="a1a28-114">Problemas conhecidos para todas as gerações de HoloLens</span><span class="sxs-lookup"><span data-stu-id="a1a28-114">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="a1a28-115">Unity</span><span class="sxs-lookup"><span data-stu-id="a1a28-115">Unity</span></span>

- <span data-ttu-id="a1a28-116">Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obter a versão mais atualizada do Unity recomendada para o desenvolvimento do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="a1a28-117">Problemas conhecidos com a visualização técnica do Unity HoloLens são documentados nos [fóruns do Hololens Unity](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="a1a28-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="a1a28-118">Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="a1a28-118">Windows Device Portal</span></span>

- <span data-ttu-id="a1a28-119">O recurso de visualização dinâmica na captura da realidade misturada pode exibir vários segundos de latência.</span><span class="sxs-lookup"><span data-stu-id="a1a28-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="a1a28-120">Na página entrada virtual, os controles de gesto e de rolagem na seção gestos virtuais não são funcionais.</span><span class="sxs-lookup"><span data-stu-id="a1a28-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="a1a28-121">Usá-los não terá nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="a1a28-121">Using them will have no effect.</span></span> <span data-ttu-id="a1a28-122">O teclado virtual na página de entrada virtual funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="a1a28-122">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="a1a28-123">Depois de habilitar o Modo de Desenvolvedor em Configurações, pode levar alguns segundos antes que a opção para ativar o Portal de Dispositivos está habilitada.</span><span class="sxs-lookup"><span data-stu-id="a1a28-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="a1a28-124">Upload da câmera do OneDrive</span><span class="sxs-lookup"><span data-stu-id="a1a28-124">OneDrive camera upload</span></span>

<span data-ttu-id="a1a28-125">O aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="a1a28-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="a1a28-126">Soluções alternativas:</span><span class="sxs-lookup"><span data-stu-id="a1a28-126">Workarounds:</span></span>

- <span data-ttu-id="a1a28-127">Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor.</span><span class="sxs-lookup"><span data-stu-id="a1a28-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="a1a28-128">Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte a dupla login).</span><span class="sxs-lookup"><span data-stu-id="a1a28-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="a1a28-129">No seu perfil conta Microsoft no OneDrive, você pode habilitar o upload automático de rolagem da câmera em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a1a28-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="a1a28-130">Se você não puder usar com segurança um conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do aplicativo OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a1a28-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="a1a28-131">Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no aplicativo OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a1a28-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="a1a28-132">Selecione o **+** botão e escolha **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="a1a28-133">Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="a1a28-134">Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.</span><span class="sxs-lookup"><span data-stu-id="a1a28-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-2-devices"></a><span data-ttu-id="a1a28-135">Problemas conhecidos para dispositivos HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a1a28-135">Known issues for HoloLens 2 devices</span></span>

### <a name="device-using-auto-login-asks-for-log-in"></a><span data-ttu-id="a1a28-136">O dispositivo que usa o logon automático solicita logon</span><span class="sxs-lookup"><span data-stu-id="a1a28-136">Device using Auto-login asks for log-in</span></span>

<span data-ttu-id="a1a28-137">Um dispositivo HoloLens 2 pode ser configurado para fazer logon automaticamente por meio de Opções de Entrada de Contas de Configurações -> e, em Obrigatório, definir o valor  ->    ->   como **Nunca**. </span><span class="sxs-lookup"><span data-stu-id="a1a28-137">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="a1a28-138">Alguns usuários podem precisar fazer logoff no dispositivo novamente ao atualizar um dispositivo com uma atualização substancialmente grande, como uma atualização de recurso.</span><span class="sxs-lookup"><span data-stu-id="a1a28-138">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span>

<span data-ttu-id="a1a28-139">Exemplo de quando isso pode ocorrer:</span><span class="sxs-lookup"><span data-stu-id="a1a28-139">Example of when this could occur:</span></span>

- <span data-ttu-id="a1a28-140">Atualizando um dispositivo do Windows Holographic, versão 2004 (Build 19041.xxxx) para o Windows Holographic, versão 21H1 (Build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="a1a28-140">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="a1a28-141">Atualizando um dispositivo para fazer uma grande atualização no mesmo build principal, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2</span><span class="sxs-lookup"><span data-stu-id="a1a28-141">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="a1a28-142">Atualizando um dispositivo de uma imagem de fábrica para a imagem mais recente</span><span class="sxs-lookup"><span data-stu-id="a1a28-142">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="a1a28-143">Isso não deve ocorrer durante:</span><span class="sxs-lookup"><span data-stu-id="a1a28-143">This should not occur during:</span></span>

- <span data-ttu-id="a1a28-144">Dispositivos que levam uma atualização mensal de manutenção</span><span class="sxs-lookup"><span data-stu-id="a1a28-144">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="a1a28-145">Contornar métodos:</span><span class="sxs-lookup"><span data-stu-id="a1a28-145">Work around methods:</span></span>

- <span data-ttu-id="a1a28-146">Métodos de entrada, como PIN, senha, íris, autenticação da Web ou chaves FIDO2.</span><span class="sxs-lookup"><span data-stu-id="a1a28-146">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="a1a28-147">Se o PIN do dispositivo não puder ser lembrado e outros métodos de autenticação não estiverem disponíveis, um usuário poderá usar o [modo de reflashing manual](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="a1a28-147">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

### <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="a1a28-148">Falha ao iniciar o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a1a28-148">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="a1a28-149">Esse problema foi criado originalmente com a versão de envio do Microsoft Edge em mente.</span><span class="sxs-lookup"><span data-stu-id="a1a28-149">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="a1a28-150">Esse problema pode ser resolvido no [novo Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="a1a28-150">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="a1a28-151">Se não estiver, envie comentários para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="a1a28-151">If it is not, please file feedback.</span></span>

<span data-ttu-id="a1a28-152">Alguns clientes relataram um problema em que o Microsoft Edge falha ao ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-152">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="a1a28-153">Para esses clientes, o problema persiste pela reinicialização e não é resolvido com atualizações do Windows ou do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a1a28-153">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="a1a28-154">Se você estiver enfrentando esse problema e tiver confirmado que o [Windows está atualizado](hololens-updates.md#manually-check-for-updates), registre um bug do [aplicativo de Hub de comentários](hololens-feedback.md) com a seguinte categoria e subcategoria: instalar e atualizar > baixar, instalar e configurar Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a1a28-154">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="a1a28-155">Não há soluções alternativas conhecidas, pois não conseguimos fazer a raiz causar o problema até o momento.</span><span class="sxs-lookup"><span data-stu-id="a1a28-155">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="a1a28-156">O arquivamento de um bug por meio do hub de comentários ajudará nossa investigação!</span><span class="sxs-lookup"><span data-stu-id="a1a28-156">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <a name="keyboard-does-not-switch-to-special-characters"></a><span data-ttu-id="a1a28-157">O teclado não muda para caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="a1a28-157">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="a1a28-158">Há um problema durante o OOBE, em que, depois que o usuário tiver escolhido uma conta corporativa ou de estudante e estiver inserindo sua senha, tentar alternar para os caracteres especiais no teclado tocando no botão &123 não mudará para caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="a1a28-158">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span>

<span data-ttu-id="a1a28-159">Solução alternativa:</span><span class="sxs-lookup"><span data-stu-id="a1a28-159">Work-arounds:</span></span>
-   <span data-ttu-id="a1a28-160">Feche o teclado e reabra-o tocando no campo de texto.</span><span class="sxs-lookup"><span data-stu-id="a1a28-160">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="a1a28-161">Insira incorretamente sua senha.</span><span class="sxs-lookup"><span data-stu-id="a1a28-161">Incorrectly enter your password.</span></span> <span data-ttu-id="a1a28-162">Quando o teclado for reiniciado da próxima vez, ele funcionará conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-162">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="a1a28-163">Autenticação na Web, feche o teclado e selecione **entrar em outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-163">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="a1a28-164">Se inserir apenas números, um usuário poderá pressionar e manter determinadas chaves para abrir um menu expandido.</span><span class="sxs-lookup"><span data-stu-id="a1a28-164">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="a1a28-165">Usando um teclado USB.</span><span class="sxs-lookup"><span data-stu-id="a1a28-165">Using a USB keyboard.</span></span>

<span data-ttu-id="a1a28-166">Isso não afeta:</span><span class="sxs-lookup"><span data-stu-id="a1a28-166">This does not affect:</span></span>
- <span data-ttu-id="a1a28-167">Usuários que optam por usar uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="a1a28-167">Users who choose to use a personal account.</span></span>

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a><span data-ttu-id="a1a28-168">A tela azul é mostrada após o desenrolamento de builds de visualização do Insider em um dispositivo com um build do Insider</span><span class="sxs-lookup"><span data-stu-id="a1a28-168">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with an Insider build</span></span>

<span data-ttu-id="a1a28-169">Esse é um problema que afeta os usuários que estavam em um build de visualização do Insider, reemerrou o HoloLens 2 com um novo build de visualização do insider e, em seguida, foi desaloculado do programa Insider.</span><span class="sxs-lookup"><span data-stu-id="a1a28-169">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span>

<span data-ttu-id="a1a28-170">Isso não afeta:</span><span class="sxs-lookup"><span data-stu-id="a1a28-170">This does not affect:</span></span>
- <span data-ttu-id="a1a28-171">Usuários que não estão inscritos no Participante do Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="a1a28-171">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="a1a28-172">Insiders:</span><span class="sxs-lookup"><span data-stu-id="a1a28-172">Insiders:</span></span>
    - <span data-ttu-id="a1a28-173">Se um dispositivo foi inscrito desde que os builds do Insider eram da versão 18362.x</span><span class="sxs-lookup"><span data-stu-id="a1a28-173">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="a1a28-174">Se eles piscaram um build 19041.x assinado pelo Insider e permanecem inscritos no programa Insider</span><span class="sxs-lookup"><span data-stu-id="a1a28-174">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="a1a28-175">Work-around:</span><span class="sxs-lookup"><span data-stu-id="a1a28-175">Work-around:</span></span> 
- <span data-ttu-id="a1a28-176">Evitar o problema</span><span class="sxs-lookup"><span data-stu-id="a1a28-176">Avoid the issue</span></span> 
    - <span data-ttu-id="a1a28-177">Flash de um build não interno.</span><span class="sxs-lookup"><span data-stu-id="a1a28-177">Flash a non-insider build.</span></span> <span data-ttu-id="a1a28-178">Uma das atualizações mensais regulares.</span><span class="sxs-lookup"><span data-stu-id="a1a28-178">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="a1a28-179">Mantenha-se no Insider Preview</span><span class="sxs-lookup"><span data-stu-id="a1a28-179">Stay on Insider Preview</span></span>
- <span data-ttu-id="a1a28-180">Reflash o dispositivo</span><span class="sxs-lookup"><span data-stu-id="a1a28-180">Reflash the device</span></span>

    1. <span data-ttu-id="a1a28-181">Coloque o [HoloLens 2 no modo de flash](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manualmente, completamente ligado e não se conectando.</span><span class="sxs-lookup"><span data-stu-id="a1a28-181">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="a1a28-182">Em seguida, enquanto Volume up, toque no botão Ligar.</span><span class="sxs-lookup"><span data-stu-id="a1a28-182">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="a1a28-183">Conecte-se ao computador e abra o Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="a1a28-183">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="a1a28-184">Atualize o HoloLens 2 para a compilação padrão.</span><span class="sxs-lookup"><span data-stu-id="a1a28-184">Flash the HoloLens 2 to the default build.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="a1a28-185">Problemas conhecidos do HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="a1a28-185">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="a1a28-186">Não é possível conectar e implantar no HoloLens por meio do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a1a28-186">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="a1a28-187">Última atualização: 8/8 @ 5:23h-o Visual Studio lançou o VS 2019 versão 16,2, que inclui uma correção para esse problema.</span><span class="sxs-lookup"><span data-stu-id="a1a28-187">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="a1a28-188">É recomendável atualizar para esta versão mais recente para evitar que esse erro seja apresentado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-188">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a1a28-189">O Visual Studio lançou o VS 2019 versão 16,2, que inclui uma correção para esse problema.</span><span class="sxs-lookup"><span data-stu-id="a1a28-189">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="a1a28-190">É recomendável atualizar para esta versão mais recente para evitar que esse erro seja apresentado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-190">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a1a28-191">Causa raiz do problema: os usuários que usaram o Visual Studio 2015 ou versões anteriores do Visual Studio 2017 para implantar e depurar aplicativos em seu HoloLens e, posteriormente, usaram as versões mais recentes do Visual Studio 2017 ou do Visual Studio 2019 com o mesmo HoloLens serão afetados.</span><span class="sxs-lookup"><span data-stu-id="a1a28-191">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="a1a28-192">As versões mais recentes do Visual Studio implantam uma nova versão de um componente, mas os arquivos da versão mais antiga são deixados no dispositivo, fazendo com que a versão mais recente falhe.</span><span class="sxs-lookup"><span data-stu-id="a1a28-192">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="a1a28-193">Isso causa a seguinte mensagem de erro: DEP0100: Verifique se o dispositivo de destino tem o modo de desenvolvedor habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-193">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="a1a28-194">Não foi possível obter uma licença de desenvolvedor em \<ip\> devido ao erro 80004005.</span><span class="sxs-lookup"><span data-stu-id="a1a28-194">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="a1a28-195">Solução alternativa</span><span class="sxs-lookup"><span data-stu-id="a1a28-195">Workaround</span></span>

<span data-ttu-id="a1a28-196">Nossa equipe está trabalhando em uma correção no momento.</span><span class="sxs-lookup"><span data-stu-id="a1a28-196">Our team is currently working on a fix.</span></span> <span data-ttu-id="a1a28-197">Enquanto isso, você pode usar as etapas a seguir para contornar o problema e ajudar a desbloquear a implantação e a depuração:</span><span class="sxs-lookup"><span data-stu-id="a1a28-197">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="a1a28-198">Abra o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a1a28-198">Open Visual Studio.</span></span>

1. <span data-ttu-id="a1a28-199">Selecione **Arquivo** > **Novo** > **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-199">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="a1a28-200">Selecione **Visual C#**  >  **Windows Desktop**  >  **console app (.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-200">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="a1a28-201">Dê um nome ao projeto (como "HoloLensDeploymentFix") e verifique se a estrutura está definida para pelo menos .NET Framework 4,5 e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-201">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="a1a28-202">Clique com o botão direito do mouse no nó **referências** em Gerenciador de soluções e adicione as seguintes referências (selecione para a seção **procurar** e selecione **procurar**):</span><span class="sxs-lookup"><span data-stu-id="a1a28-202">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="a1a28-203">Se você não tiver o 10.0.18362.0 instalado, use a versão mais recente que você tem.</span><span class="sxs-lookup"><span data-stu-id="a1a28-203">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="a1a28-204">Clique com o botão direito do mouse no projeto em Gerenciador de soluções e selecione **Adicionar**  >  **Item existente**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-204">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="a1a28-205">Navegue até C:\Arquivos de programas (x86) \Windows Kits\10\bin\10.0.18362.0\x86 e altere o filtro para **todos os arquivos ( \* . \* )**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-205">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="a1a28-206">Selecione SirepClient.dll e SshClient.dll e Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-206">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="a1a28-207">Localize e selecione os dois arquivos Gerenciador de Soluções (eles devem estar na parte inferior da lista  de arquivos) e **altere** Copiar para Diretório de Saída na janela Propriedades para Copiar **sempre**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-207">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="a1a28-208">Na parte superior do arquivo, adicione o seguinte à lista de instruções `using` existente:</span><span class="sxs-lookup"><span data-stu-id="a1a28-208">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="a1a28-209">Dentro de `static void Main(...)` , adicione o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="a1a28-209">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="a1a28-210">Selecione **Compilar** > **Compilar Solução**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-210">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="a1a28-211">Abra uma Janela do Prompt de Comando e o cd para a pasta que contém o arquivo .exe compilado (por exemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="a1a28-211">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="a1a28-212">Execute o executável e forneça o endereço IP do dispositivo como um argumento de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a1a28-212">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="a1a28-213">(Se conectado usando USB, você pode usar 127.0.0.1; caso contrário, use o endereço IP Wi-Fi do dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="a1a28-213">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="a1a28-214">Depois que a ferramenta sair sem nenhuma mensagem (isso deve levar apenas alguns segundos), agora você poderá implantar e depurar do Visual Studio 2017 ou mais novo.</span><span class="sxs-lookup"><span data-stu-id="a1a28-214">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="a1a28-215">O uso contínuo da ferramenta não é necessário.</span><span class="sxs-lookup"><span data-stu-id="a1a28-215">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="a1a28-216">Forneceremos mais atualizações à medida que elas se tornarem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a1a28-216">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="a1a28-217">Problemas ao iniciar o Microsoft Store e aplicativos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="a1a28-217">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="a1a28-218">Última Atualização: 02/04 às 10h – Problema resolvido.</span><span class="sxs-lookup"><span data-stu-id="a1a28-218">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="a1a28-219">Você pode ter problemas ao tentar iniciar o Microsoft Store e aplicativos no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-219">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="a1a28-220">Determinamos que o problema ocorre quando as atualizações do aplicativo em segundo plano implantam uma versão mais recente dos pacotes de estrutura em sequências específicas enquanto um ou mais aplicativos dependentes ainda estão em execução.</span><span class="sxs-lookup"><span data-stu-id="a1a28-220">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="a1a28-221">Nesse caso, uma atualização automática de aplicativos entregue uma nova versão do .NET Native Framework (versão 10.0.25531 a 10.0.27413) fez com que os aplicativos que estão em execução não sejam atualizados corretamente para todos os aplicativos em execução consumindo a versão anterior da estrutura.</span><span class="sxs-lookup"><span data-stu-id="a1a28-221">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="a1a28-222">O fluxo para a atualização da estrutura é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a1a28-222">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="a1a28-223">O novo pacote de estrutura é baixado da loja e instalado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-223">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="a1a28-224">Todos os apps usando a estrutura mais antiga são 'atualizados' para usar a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="a1a28-224">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="a1a28-225">Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais nova não foi registrada falharão ao iniciar no menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="a1a28-225">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="a1a28-226">Acreditamos que qualquer aplicativo no HoloLens poderia ser afetado por esse problema.</span><span class="sxs-lookup"><span data-stu-id="a1a28-226">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="a1a28-227">Alguns usuários relataram que o fechamento de aplicativos suspensos e a inicialização de outros aplicativos, como hub de comentários, visualizador 3D ou fotos, resolve o problema para eles-no entanto, isso não funciona 100% do tempo.</span><span class="sxs-lookup"><span data-stu-id="a1a28-227">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="a1a28-228">Temos a raiz causada que esse problema não foi causado pela atualização em si, mas um bug no sistema operacional que resultou na atualização do .NET Native Framework sendo tratada incorretamente.</span><span class="sxs-lookup"><span data-stu-id="a1a28-228">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="a1a28-229">Temos o prazer de anunciar que identificamos uma correção e lançamos uma atualização (versão do sistema operacional 17763,380) que contém a correção.</span><span class="sxs-lookup"><span data-stu-id="a1a28-229">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="a1a28-230">Para ver se o dispositivo pode executar a atualização:</span><span class="sxs-lookup"><span data-stu-id="a1a28-230">To see if your device can take the update:</span></span>

1. <span data-ttu-id="a1a28-231">Vá para o aplicativo Configurações e abra **atualizar & segurança**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-231">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="a1a28-232">Selecione **verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-232">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="a1a28-233">Se a atualização para 17763,380 estiver disponível, atualize para esse Build para receber a correção para o bug de parada do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a1a28-233">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="a1a28-234">Após a atualização para esta versão do sistema operacional, os aplicativos devem funcionar conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-234">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="a1a28-235">Além disso, como fazemos com cada versão do sistema operacional do HoloLens, publicamos a imagem FFU no [centro de download da Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).</span><span class="sxs-lookup"><span data-stu-id="a1a28-235">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="a1a28-236">Se você não quiser fazer a atualização, lançamos uma nova versão do aplicativo Microsoft Store UWP a partir de 3/29.</span><span class="sxs-lookup"><span data-stu-id="a1a28-236">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="a1a28-237">Depois de ter a versão atualizada do repositório:</span><span class="sxs-lookup"><span data-stu-id="a1a28-237">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="a1a28-238">Abra o repositório e confirme se ele é carregado.</span><span class="sxs-lookup"><span data-stu-id="a1a28-238">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="a1a28-239">Use o gesto de flor para abrir o menu.</span><span class="sxs-lookup"><span data-stu-id="a1a28-239">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="a1a28-240">Tentativa de abrir aplicativos interrompidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a1a28-240">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="a1a28-241">Se ainda não puder ser iniciado, toque e mantenha o ícone do aplicativo interrompido e selecione Desinstalar.</span><span class="sxs-lookup"><span data-stu-id="a1a28-241">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="a1a28-242">Reinstale esses aplicativos da loja.</span><span class="sxs-lookup"><span data-stu-id="a1a28-242">Reinstall these apps from the store.</span></span>

<span data-ttu-id="a1a28-243">Se o dispositivo ainda não puder carregar aplicativos, você poderá Sideload uma versão do .NET Native Framework e tempo de execução por meio do centro de download seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a1a28-243">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="a1a28-244">Baixe [este arquivo zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) do centro de download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1a28-244">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="a1a28-245">O descompactar produzirá dois arquivos.</span><span class="sxs-lookup"><span data-stu-id="a1a28-245">Unzipping will produce two files.</span></span>  <span data-ttu-id="a1a28-246">Microsoft .NET.Native.Runtime.1.7.appx e Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="a1a28-246">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="a1a28-247">Verifique se o dispositivo está desbloqueado em dev.</span><span class="sxs-lookup"><span data-stu-id="a1a28-247">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="a1a28-248">Se você ainda não fez isso antes, consulte [Usando o Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="a1a28-248">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="a1a28-249">Em seguida, você deseja entrar no Portal de Dispositivos do Windows.</span><span class="sxs-lookup"><span data-stu-id="a1a28-249">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="a1a28-250">Nossa recomendação é fazer isso por USB e você faria isso digitando http://127.0.0.1:10080 em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="a1a28-250">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="a1a28-251">Depois que você tiver a Portal de Dispositivos do Windows, será necessário "carregar lado a lado" os dois arquivos baixados.</span><span class="sxs-lookup"><span data-stu-id="a1a28-251">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="a1a28-252">Para fazer isso, você precisa ir para baixo na barra do lado esquerdo até chegar à seção **Aplicativos** e selecionar **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-252">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="a1a28-253">Em seguida, você verá uma tela semelhante à abaixo.</span><span class="sxs-lookup"><span data-stu-id="a1a28-253">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="a1a28-254">Você deseja ir para a  seção que diz Instalar Aplicativo e navegar até o local em que desemcortou esses dois arquivos APPX.</span><span class="sxs-lookup"><span data-stu-id="a1a28-254">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="a1a28-255">Você só pode fazer um de cada vez, portanto, depois de selecionar o primeiro, clique em "Ir" na seção Implantar.</span><span class="sxs-lookup"><span data-stu-id="a1a28-255">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="a1a28-256">Em seguida, faça isso para o segundo arquivo APPX.</span><span class="sxs-lookup"><span data-stu-id="a1a28-256">Then do this for the second APPX file.</span></span>

   ![Portal de Dispositivos do Windows instalar o Side-Loaded aplicativo](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="a1a28-258">Neste ponto, acreditamos que seus aplicativos devem começar a funcionar novamente e que você também pode chegar à Store.</span><span class="sxs-lookup"><span data-stu-id="a1a28-258">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="a1a28-259">Em alguns casos, é necessário executar a etapa adicional de iniciar o aplicativo Visualizador 3D antes que os aplicativos afetados sejam lançados.</span><span class="sxs-lookup"><span data-stu-id="a1a28-259">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="a1a28-260">Agradecemos sua saúde enquanto passamos pelo processo para resolver esse problema e estamos ansiosos para continuar trabalhando com nossa comunidade para criar experiências bem-sucedidas de Realidade Misturada.</span><span class="sxs-lookup"><span data-stu-id="a1a28-260">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="a1a28-261">Atualização do dispositivo</span><span class="sxs-lookup"><span data-stu-id="a1a28-261">Device Update</span></span>

- <span data-ttu-id="a1a28-262">30 segundos após uma nova atualização, o shell pode desaparecer uma vez.</span><span class="sxs-lookup"><span data-stu-id="a1a28-262">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="a1a28-263">Execute o gesto **de bloom** para retomar sua sessão.</span><span class="sxs-lookup"><span data-stu-id="a1a28-263">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="a1a28-264">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a1a28-264">Visual Studio</span></span>

- <span data-ttu-id="a1a28-265">Confira [Instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Visual Studio recomendada para o desenvolvimento do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-265">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="a1a28-266">Ao implantar um aplicativo do Visual Studio em seu HoloLens, você poderá ver o erro: A operação solicitada não pode ser executada em um arquivo com uma seção mapeada **pelo usuário aberta. (Exceção de HRESULT: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="a1a28-266">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="a1a28-267">Se isso acontecer, tente novamente e sua implantação geralmente terá êxito.</span><span class="sxs-lookup"><span data-stu-id="a1a28-267">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="a1a28-268">API</span><span class="sxs-lookup"><span data-stu-id="a1a28-268">API</span></span>

- <span data-ttu-id="a1a28-269">Se o aplicativo definir o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) por trás do usuário ou o normal para a câmera. encaminhar, os hologramas não aparecerão em fotos ou vídeos de captura de realidade misturada.</span><span class="sxs-lookup"><span data-stu-id="a1a28-269">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="a1a28-270">Até que esse bug seja corrigido no Windows, se os aplicativos definirem ativamente o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) , eles devem garantir que o plano normal esteja definido na frente da câmera oposta (por exemplo, normal =-Camera. Forward).</span><span class="sxs-lookup"><span data-stu-id="a1a28-270">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="a1a28-271">Controle sem Fio Xbox</span><span class="sxs-lookup"><span data-stu-id="a1a28-271">Xbox Wireless Controller</span></span>

- <span data-ttu-id="a1a28-272">Os S do controlador sem fio do Xbox devem ser atualizados para que possam ser usados com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-272">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="a1a28-273">Verifique se você está [atualizado](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) antes de tentar emparelhar seu controlador com um HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-273">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="a1a28-274">Se você reinicializar o HoloLens enquanto o controlador sem fio do Xbox estiver conectado, o controlador não será reconectado automaticamente ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-274">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="a1a28-275">A luz do botão de guia piscará lentamente até que o controlador seja desligado após 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="a1a28-275">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="a1a28-276">Para reconectar o controlador imediatamente, desligue o controlador mantendo o botão guia até que a luz se apague.</span><span class="sxs-lookup"><span data-stu-id="a1a28-276">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="a1a28-277">Quando você ligar o controlador novamente, ele se reconectará ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-277">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="a1a28-278">Se o seu HoloLens entrar em espera enquanto o controlador sem fio do Xbox estiver conectado, qualquer entrada no controlador ativará o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1a28-278">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="a1a28-279">Você pode evitar isso desligando o controlador quando terminar de usá-lo.</span><span class="sxs-lookup"><span data-stu-id="a1a28-279">You can prevent this by powering off your controller when you are done using it.</span></span>

## <a name="known-issues-for-hololens-emulator"></a><span data-ttu-id="a1a28-280">Problemas conhecidos do emulador do HoloLens</span><span class="sxs-lookup"><span data-stu-id="a1a28-280">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="a1a28-281">Nem todos os aplicativos na Microsoft Store são compatíveis com o emulador.</span><span class="sxs-lookup"><span data-stu-id="a1a28-281">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="a1a28-282">Por exemplo, jovens conkers e fragmentos não são reproduzidos no emulador.</span><span class="sxs-lookup"><span data-stu-id="a1a28-282">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="a1a28-283">Não é possível usar a webcam do PC no emulador.</span><span class="sxs-lookup"><span data-stu-id="a1a28-283">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="a1a28-284">O recurso de visualização dinâmica do portal do dispositivo Windows não funciona com o emulador.</span><span class="sxs-lookup"><span data-stu-id="a1a28-284">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="a1a28-285">Você ainda pode capturar vídeos e imagens de realidade misturada.</span><span class="sxs-lookup"><span data-stu-id="a1a28-285">You can still capture Mixed Reality videos and images.</span></span>
