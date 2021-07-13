---
title: HoloLens Solução de problemas de dispositivo
description: mantenha-se atualizado sobre as soluções mais comuns para HoloLens problemas de dispositivo e técnicas de solução de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, bug, solução de problemas, correção, ajuda, suporte, HoloLens, emulador
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635442"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="3a3fe-104">Solução de problemas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="3a3fe-104">Device Troubleshooting</span></span>

<span data-ttu-id="3a3fe-105">este artigo descreve como resolver vários problemas comuns de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3a3fe-106">Antes de iniciar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo seja cobrado de **20 a 40%** da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="3a3fe-107">As [luzes do indicador de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas no botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="3a3fe-108">**Problemas conhecidos**</span><span class="sxs-lookup"><span data-stu-id="3a3fe-108">**Known Issues**</span></span>
- [<span data-ttu-id="3a3fe-109">O vídeo da assistência remota congela após 20 minutos</span><span class="sxs-lookup"><span data-stu-id="3a3fe-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="3a3fe-110">Logon automático solicita o logon</span><span class="sxs-lookup"><span data-stu-id="3a3fe-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="3a3fe-111">falha ao iniciar o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3a3fe-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="3a3fe-112">O teclado não muda para caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="3a3fe-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="3a3fe-113">O download de arquivos bloqueados não mostra erro</span><span class="sxs-lookup"><span data-stu-id="3a3fe-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="3a3fe-114">Tempo limite de carregamento/download do arquivo do portal do dispositivo</span><span class="sxs-lookup"><span data-stu-id="3a3fe-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="3a3fe-115">Tela azul após o cancelamento do registro do insider preview em um dispositivo atualizado com uma compilação Insider</span><span class="sxs-lookup"><span data-stu-id="3a3fe-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="3a3fe-116">OneDrive não carrega imagens automaticamente</span><span class="sxs-lookup"><span data-stu-id="3a3fe-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="3a3fe-117">**Geral**</span><span class="sxs-lookup"><span data-stu-id="3a3fe-117">**General**</span></span>
- [<span data-ttu-id="3a3fe-118">HoloLens não está respondendo ou não será iniciado</span><span class="sxs-lookup"><span data-stu-id="3a3fe-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="3a3fe-119">Erro de "pouco espaço em disco"</span><span class="sxs-lookup"><span data-stu-id="3a3fe-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="3a3fe-120">Falha na calibragem</span><span class="sxs-lookup"><span data-stu-id="3a3fe-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="3a3fe-121">não é possível entrar porque o meu HoloLens foi configurado anteriormente para outra pessoa</span><span class="sxs-lookup"><span data-stu-id="3a3fe-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="3a3fe-122">O Unity não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="3a3fe-123">Windows O portal do dispositivo não está funcionando corretamente</span><span class="sxs-lookup"><span data-stu-id="3a3fe-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="3a3fe-124">o Emulator de HoloLens não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="3a3fe-125">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="3a3fe-125">**Input**</span></span>
- [<span data-ttu-id="3a3fe-126">Os comandos de voz não estão funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="3a3fe-127">A entrada manual não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="3a3fe-128">**Conectividade**</span><span class="sxs-lookup"><span data-stu-id="3a3fe-128">**Connectivity**</span></span>
- [<span data-ttu-id="3a3fe-129">Não é possível conectar-se ao Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3a3fe-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="3a3fe-130">**Dispositivos externos**</span><span class="sxs-lookup"><span data-stu-id="3a3fe-130">**External Devices**</span></span> 
- [<span data-ttu-id="3a3fe-131">Bluetooth dispositivos não estão emparelhando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="3a3fe-132">O microfone USB-C não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="3a3fe-133">os dispositivos listados como disponíveis no Configurações não funcionam</span><span class="sxs-lookup"><span data-stu-id="3a3fe-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="3a3fe-134">O vídeo da assistência remota congela após 20 minutos</span><span class="sxs-lookup"><span data-stu-id="3a3fe-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="3a3fe-135">Há uma versão mais recente do auxílio remoto que tem uma correção para esse problema.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="3a3fe-136">[Atualize o auxílio remoto](holographic-store-apps.md#update-apps) para a versão mais recente para evitar esse problema.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="3a3fe-137">devido a essa gravidade do problema conhecido, fizemos temporariamente uma pausa na disponibilidade de Windows Holographic, versão 21H1.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="3a3fe-138">A compilação 21H1 agora está disponível novamente, portanto, os dispositivos podem ser novamente atualizados para a compilação de 21H1 mais recente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="3a3fe-139">na última versão do [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), alguns usuários da assistência remota experimentaram o congelamento do vídeo durante chamadas de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="3a3fe-140">Esse é um **problema conhecido**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="3a3fe-141">Soluções Alternativas</span><span class="sxs-lookup"><span data-stu-id="3a3fe-141">Workarounds</span></span>

<span data-ttu-id="3a3fe-142">Se não for possível atualizar o auxílio remoto para uma compilação mais nova, tente a seguinte solução alternativa.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="3a3fe-143">Reinicializar entre chamadas</span><span class="sxs-lookup"><span data-stu-id="3a3fe-143">Restart in between calls</span></span>

<span data-ttu-id="3a3fe-144">Se suas chamadas estiverem passando por um período de 20 minutos e você estiver enfrentando esse problema, tente reinicializar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="3a3fe-145">A reinicialização do dispositivo entre as chamadas de assistência remota atualizará o dispositivo e o colocará em um bom estado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="3a3fe-146">para reiniciar rapidamente um dispositivo no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) abra o menu iniciar e selecione o ícone usuário e, em seguida, selecione **reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="3a3fe-147">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="3a3fe-148">Logon automático solicita o logon</span><span class="sxs-lookup"><span data-stu-id="3a3fe-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="3a3fe-149">um dispositivo HoloLens 2 pode ser configurado para fazer logon automaticamente por meio de opções de entrada de contas de **Configurações**  ->    ->   -> e, em **requerido** , defina o valor como **nunca**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="3a3fe-150">Alguns usuários podem ser solicitados a fazer logon no dispositivo novamente ao atualizar um dispositivo com uma atualização substancialmente grande, como uma atualização de recurso.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="3a3fe-151">Esse é um **problema conhecido**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-151">This is a **known issue**.</span></span>

<span data-ttu-id="3a3fe-152">Exemplo de quando isso pode ocorrer:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-152">Example of when this could occur:</span></span>

- <span data-ttu-id="3a3fe-153">atualizando um dispositivo do Windows Holographic, versão 2004 (build 19041. xxxx) para Windows Holographic, versão 21H1 (build 20346. xxxx)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="3a3fe-154">atualização de um dispositivo para fazer uma atualização grande na mesma compilação principal, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2</span><span class="sxs-lookup"><span data-stu-id="3a3fe-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="3a3fe-155">Atualizando um dispositivo de uma imagem de fábrica para a imagem mais recente</span><span class="sxs-lookup"><span data-stu-id="3a3fe-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="3a3fe-156">Isso não deve ocorrer durante:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-156">This should not occur during:</span></span>

- <span data-ttu-id="3a3fe-157">Dispositivos que levam uma atualização mensal de manutenção</span><span class="sxs-lookup"><span data-stu-id="3a3fe-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="3a3fe-158">Contornar métodos:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-158">Work around methods:</span></span>

- <span data-ttu-id="3a3fe-159">Métodos de entrada, como PIN, senha, íris, autenticação da Web ou chaves FIDO2.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="3a3fe-160">Se o PIN do dispositivo não puder ser lembrado e outros métodos de autenticação não estiverem disponíveis, um usuário poderá usar o [modo de reflashing manual](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="3a3fe-161">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="3a3fe-162">falha ao iniciar o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3a3fe-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="3a3fe-163">esse problema foi criado originalmente com a versão de envio do Microsoft Edge em mente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="3a3fe-164">Esse problema pode ser resolvido no [novo Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="3a3fe-165">Se não estiver, envie comentários para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="3a3fe-166">alguns clientes relataram um problema em que Microsoft Edge falha ao iniciar.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="3a3fe-167">para esses clientes, o problema persiste pela reinicialização e não é resolvido com Windows ou atualizações de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="3a3fe-168">se você estiver enfrentando esse problema e tiver confirmado [Windows está atualizado](hololens-updates.md#manually-check-for-updates), registre um bug do [aplicativo de Hub de comentários](hololens-feedback.md) com a seguinte categoria e subcategoria: instalar e atualizar > baixar, instalar e configurar Windows Update.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="3a3fe-169">Não há soluções alternativas conhecidas, pois não conseguimos fazer a raiz causar o problema até o momento.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="3a3fe-170">O arquivamento de um bug por meio do hub de comentários ajudará nossa investigação!</span><span class="sxs-lookup"><span data-stu-id="3a3fe-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="3a3fe-171">Esse é um **problema conhecido**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-171">This is a **known issue**.</span></span>

[<span data-ttu-id="3a3fe-172">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="3a3fe-173">O teclado não muda para caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="3a3fe-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="3a3fe-174">Há um problema durante o OOBE, em que, depois que o usuário tiver escolhido uma conta corporativa ou de estudante e estiver inserindo sua senha, tentar alternar para os caracteres especiais no teclado tocando no botão &123 não mudará para caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="3a3fe-175">Esse é um **problema conhecido**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-175">This is a **known issue**.</span></span>

<span data-ttu-id="3a3fe-176">Solução alternativa:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-176">Work-arounds:</span></span>
-   <span data-ttu-id="3a3fe-177">Feche o teclado e reabra-o tocando no campo de texto.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="3a3fe-178">Insira incorretamente sua senha.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-178">Incorrectly enter your password.</span></span> <span data-ttu-id="3a3fe-179">Quando o teclado for reiniciado da próxima vez, ele funcionará conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="3a3fe-180">Autenticação na Web, feche o teclado e selecione **entrar em outro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="3a3fe-181">Se inserir apenas números, um usuário poderá pressionar e manter determinadas chaves para abrir um menu expandido.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="3a3fe-182">Usando um teclado USB.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-182">Using a USB keyboard.</span></span>

<span data-ttu-id="3a3fe-183">Isso não afeta:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-183">This does not affect:</span></span>
- <span data-ttu-id="3a3fe-184">Usuários que optam por usar uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="3a3fe-185">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="3a3fe-186">O download de arquivos bloqueados não é um erro</span><span class="sxs-lookup"><span data-stu-id="3a3fe-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="3a3fe-187">esse é um **problema conhecido** que é corrigido no Windows insider build, versão 20348,1403.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="3a3fe-188">em compilações anteriores do Windows Holographic, ao tentar baixar um arquivo bloqueado, o resultado seria uma página de erro HTTP.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="3a3fe-189">no Windows Holographic, versão 21H1 update, tentando baixar um arquivo bloqueado resulta em nada que está visível, o arquivo não é baixado e não há erro.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="3a3fe-190">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="3a3fe-191">Tempo limite de carregamento/download do arquivo do portal do dispositivo</span><span class="sxs-lookup"><span data-stu-id="3a3fe-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="3a3fe-192">esse é um **problema conhecido** que é corrigido no Windows insider build, versão 20348,1403.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="3a3fe-193">Se você tiver desabilitado anteriormente a conexão SSL como parte da solução alternativa, é altamente recomendável reabilitá-la.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="3a3fe-194">Alguns clientes encontraram, ao tentar carregar ou baixar arquivos, a operação pode parecer parar e expirar ou nunca concluir.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="3a3fe-195">isso é separado do[problema conhecido "arquivo bloqueado"](#downloading-locked-files-doesnt-error) – isso afeta Windows Holographic, versões 2004, 20H2 e 21H1 compilações no mercado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="3a3fe-196">O problema foi raiz causado por um bug no tratamento de determinadas solicitações do portal do dispositivo e é mais consistente quando se usa HTTPS, que é o padrão.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="3a3fe-197">Solução alternativa</span><span class="sxs-lookup"><span data-stu-id="3a3fe-197">Workaround</span></span>

<span data-ttu-id="3a3fe-198">Essa solução alternativa, que se aplica igualmente a Wi-Fi e UsbNcm, é desabilitar a opção "obrigatório" em "conexão SSL".</span><span class="sxs-lookup"><span data-stu-id="3a3fe-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="3a3fe-199">Para fazer isso, navegue até portal do dispositivo, **sistema** e selecione a página **preferências** .</span><span class="sxs-lookup"><span data-stu-id="3a3fe-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="3a3fe-200">Na seção **segurança do dispositivo** , localize **conexão SSL** e desmarque para desabilitar **necessário**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="3a3fe-201">Em seguida, o usuário deve ir para http://, não https:// (endereço IP) e recursos como upload e download de arquivo funcionarão.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="3a3fe-202">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="3a3fe-203">Tela azul após o unenrolling da versão prévia do Insider em um dispositivo com um build do Insider</span><span class="sxs-lookup"><span data-stu-id="3a3fe-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="3a3fe-204">Esse é um problema que afeta os usuários que estavam em um build de visualização do Insider, reemerrou o HoloLens 2 com um novo build de visualização do insider e, em seguida, foi desaloculado do programa Insider.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="3a3fe-205">Esse é um **problema conhecido.**</span><span class="sxs-lookup"><span data-stu-id="3a3fe-205">This is a **known issue**.</span></span>

<span data-ttu-id="3a3fe-206">Isso não afeta:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-206">This does not affect:</span></span>
- <span data-ttu-id="3a3fe-207">Usuários que não estão inscritos no Windows Insider</span><span class="sxs-lookup"><span data-stu-id="3a3fe-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="3a3fe-208">Insiders:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-208">Insiders:</span></span>
    - <span data-ttu-id="3a3fe-209">Se um dispositivo foi inscrito desde que os builds do Insider eram da versão 18362.x</span><span class="sxs-lookup"><span data-stu-id="3a3fe-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="3a3fe-210">Se eles piscaram um build 19041.x assinado pelo Insider e permanecem inscritos no programa Insider</span><span class="sxs-lookup"><span data-stu-id="3a3fe-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="3a3fe-211">Work-around:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-211">Work-around:</span></span> 
- <span data-ttu-id="3a3fe-212">Evitar o problema</span><span class="sxs-lookup"><span data-stu-id="3a3fe-212">Avoid the issue</span></span> 
    - <span data-ttu-id="3a3fe-213">Flash de um build não interno.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-213">Flash a non-insider build.</span></span> <span data-ttu-id="3a3fe-214">Uma das atualizações mensais regulares.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="3a3fe-215">Mantenha-se no Insider Preview</span><span class="sxs-lookup"><span data-stu-id="3a3fe-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="3a3fe-216">Reflash o dispositivo</span><span class="sxs-lookup"><span data-stu-id="3a3fe-216">Reflash the device</span></span>

    1. <span data-ttu-id="3a3fe-217">Coloque o [HoloLens 2 no modo de flash](hololens-recovery.md) manualmente, completamente ligado enquanto não se conecta.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="3a3fe-218">Em seguida, enquanto Volume up, toque no botão Ligar.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="3a3fe-219">Conexão no computador e abra o Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="3a3fe-220">Flash do HoloLens 2 para o build padrão.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="3a3fe-221">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="3a3fe-222">OneDrive não carrega imagens automaticamente</span><span class="sxs-lookup"><span data-stu-id="3a3fe-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="3a3fe-223">O OneDrive aplicativo para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="3a3fe-224">Esse é um **problema conhecido.**</span><span class="sxs-lookup"><span data-stu-id="3a3fe-224">This is a **known issue**.</span></span>

<span data-ttu-id="3a3fe-225">Soluções alternativas:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-225">Workarounds:</span></span>

- <span data-ttu-id="3a3fe-226">Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="3a3fe-227">Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte à dupla login).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="3a3fe-228">No seu perfil conta Microsoft no OneDrive você pode habilitar o upload automático de rolagem da câmera em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="3a3fe-229">Se você não puder usar com segurança uma conta de conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do OneDrive aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="3a3fe-230">Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no OneDrive aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="3a3fe-231">Selecione o **+** botão e escolha **Upload**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="3a3fe-232">Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="3a3fe-233">Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="3a3fe-234">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="3a3fe-235">HoloLens está sem resposta ou não iniciará</span><span class="sxs-lookup"><span data-stu-id="3a3fe-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="3a3fe-236">Se o HoloLens não for iniciar:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="3a3fe-237">Se os LEDs ao lado do botão de energia não piscarem ou apenas um LED piscar brevemente, talvez seja necessário cobrar o [HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="3a3fe-238">Se os LEDs se acenderem quando você pressionar o botão de energia, mas você não conseguir ver nada nas exibições, faça uma [redefinição de](hololens-recovery.md#hard-reset-procedure)disco rígido do dispositivo .</span><span class="sxs-lookup"><span data-stu-id="3a3fe-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="3a3fe-239">Se o HoloLens ficar congelado ou sem resposta:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="3a3fe-240">Desligue o HoloLens pressionando o botão de energia até que todos os cinco LEDs se desliguem ou por 15 segundos se os LEDs não responderem.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="3a3fe-241">Para iniciar o HoloLens, pressione o botão de energia novamente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="3a3fe-242">Se essas etapas não funcionarem, você poderá tentar recuperar seu dispositivo [HoloLens 2](hololens-recovery.md) ou HoloLens [(1ª geração).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="3a3fe-243">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="3a3fe-244">Erro "Espaço em Disco Baixo"</span><span class="sxs-lookup"><span data-stu-id="3a3fe-244">"Low Disk Space" error</span></span>

<span data-ttu-id="3a3fe-245">Você precisará liberar algum espaço de armazenamento fazendo um ou mais dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="3a3fe-246">Exclua alguns espaços nãoutilados.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-246">Delete some unused spaces.</span></span> <span data-ttu-id="3a3fe-247">Vá para **Configurações** System Spaces , selecione um espaço que você não precisa mais  >    >  e, em seguida, **selecione Remover**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="3a3fe-248">Remova alguns dos hologramas que você colocou.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="3a3fe-249">Exclua algumas imagens e vídeos do aplicativo Fotos.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="3a3fe-250">Desinstale alguns aplicativos do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="3a3fe-251">Na lista **Todos os apps,** toque e mantenha o aplicativo que você deseja desinstalar e, em seguida, selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="3a3fe-252">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="3a3fe-253">Falha na calibragem</span><span class="sxs-lookup"><span data-stu-id="3a3fe-253">Calibration fails</span></span>

<span data-ttu-id="3a3fe-254">A calibragem deve funcionar para a maioria das pessoas, mas há casos em que a calibragem falha.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="3a3fe-255">Alguns possíveis motivos para a falha de calibragem incluem:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="3a3fe-256">Ficando confuso e não seguindo os destinos de calibragem</span><span class="sxs-lookup"><span data-stu-id="3a3fe-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="3a3fe-257">Visor do dispositivo sujo ou com rascunho ou visor do dispositivo não posicionado corretamente</span><span class="sxs-lookup"><span data-stu-id="3a3fe-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="3a3fe-258">Óculos sujos ou com rascunho</span><span class="sxs-lookup"><span data-stu-id="3a3fe-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="3a3fe-259">Determinados tipos de lentes de contato e óculos (lentes de contato coloridas, algumas lentes de contato tóricas, óculos de bloqueio de IR, alguns óculos de óculos com alta receita, óculos de sol ou semelhantes)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="3a3fe-260">Mais pronunciada adeção e algumas extensões de cíoa</span><span class="sxs-lookup"><span data-stu-id="3a3fe-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="3a3fe-261">Quadros de óculos grandes ou de óculos se eles estão bloqueando o dispositivo de ver seus olhos</span><span class="sxs-lookup"><span data-stu-id="3a3fe-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="3a3fe-262">Determinadas coisas de olho, condições de olho ou olho, como olhos estreitos, malhas longas, amblyopia, nystagmus, alguns casos de LASIK ou outras óculos de olho</span><span class="sxs-lookup"><span data-stu-id="3a3fe-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="3a3fe-263">Se a calibragem não for bem-sucedida, tente:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="3a3fe-264">Limpando o visor do dispositivo</span><span class="sxs-lookup"><span data-stu-id="3a3fe-264">Cleaning your device visor</span></span>
- <span data-ttu-id="3a3fe-265">Limpando seus óculos</span><span class="sxs-lookup"><span data-stu-id="3a3fe-265">Cleaning your glasses</span></span>
- <span data-ttu-id="3a3fe-266">Esvasar o visor do dispositivo o mais próximo possível dos olhos</span><span class="sxs-lookup"><span data-stu-id="3a3fe-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="3a3fe-267">Mover objetos no visor para fora do caminho (como pelos)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="3a3fe-268">A ligar uma luz em seu quarto ou sair da área de trabalho direta</span><span class="sxs-lookup"><span data-stu-id="3a3fe-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="3a3fe-269">Se você seguiu todas as diretrizes e a calibragem ainda está falhando, desabilite o prompt de calibragem Configurações.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="3a3fe-270">Além disso, nos avise fazendo comentários no [Hub de Comentários.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="3a3fe-271">Confira também informações relacionadas para a solução de problemas de cor [ou brilho da imagem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="3a3fe-272">A configuração de IPD não é aplicável HoloLens 2, pois as posições dos olhos são computadas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="3a3fe-273">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="3a3fe-274">Não é possível entrar porque minha HoloLens foi configurada anteriormente para outra pessoa</span><span class="sxs-lookup"><span data-stu-id="3a3fe-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="3a3fe-275">Você pode [colocar o dispositivo no Modo de Flash **e** usar o Avançado Recovery Companion](hololens-recovery.md#clean-reflash-the-device) para recuperar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="3a3fe-276">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="3a3fe-277">O Unity não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-277">Unity isn't working</span></span>

- <span data-ttu-id="3a3fe-278">Confira [Instalar as ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Unity recomendada para HoloLens desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="3a3fe-279">Problemas conhecidos com o Unity HoloLens Technical Preview estão documentados [nos HoloLens fóruns do Unity.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="3a3fe-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="3a3fe-280">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="3a3fe-281">Windows Portal de Dispositivos não está funcionando corretamente</span><span class="sxs-lookup"><span data-stu-id="3a3fe-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="3a3fe-282">O recurso De visualização ao vivo na captura de Realidade Misturada pode exibir vários segundos de latência.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="3a3fe-283">Na página Entrada Virtual, os controles Gesto e Rolagem na seção Gestos Virtuais não são funcionais.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="3a3fe-284">Usá-los não terá nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-284">Using them will have no effect.</span></span> <span data-ttu-id="3a3fe-285">O teclado virtual na página de entrada virtual funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="3a3fe-286">Depois de habilitar o Modo de Desenvolvedor Configurações, pode levar alguns segundos antes que a opção para ativar o Portal de Dispositivos seja habilitada.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="3a3fe-287">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="3a3fe-288">O HoloLens Emulator não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="3a3fe-289">Informações sobre o HoloLens emulador estão localizadas em nossa documentação do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="3a3fe-290">Leia mais sobre [como solucionar problemas do HoloLens emulador](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="3a3fe-291">Nem todos os aplicativos no Microsoft Store são compatíveis com o emulador.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="3a3fe-292">Por exemplo, Conker e Fragmentos Não são reproduzíveis no emulador.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="3a3fe-293">Não é possível usar a webcam do computador no Emulator.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="3a3fe-294">O recurso Live Preview do Windows Portal de Dispositivos não funciona com o emulador.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="3a3fe-295">Você ainda pode capturar vídeos e imagens de Realidade Misturada.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="3a3fe-296">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="3a3fe-297">Os comandos de voz não estão funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-297">Voice commands aren't working</span></span>

<span data-ttu-id="3a3fe-298">Se Cortana estiver respondendo aos comandos de voz, certifique-se de Cortana está ligado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="3a3fe-299">Na lista Todos os apps, selecione **Cortana**  >    >  **Menu Notebook**  >  **Configurações** para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="3a3fe-300">Para saber mais sobre o que você pode dizer, [consulte Usar sua voz com HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="3a3fe-301">em HoloLens (1º gen), o reconhecimento de fala interno não é configurável.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="3a3fe-302">Ele está sempre ativado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-302">It is always turned on.</span></span> <span data-ttu-id="3a3fe-303">no HoloLens 2, você pode escolher se deseja ativar o reconhecimento de fala e Cortana durante a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="3a3fe-304">se o seu HoloLens 2 não estiver respondendo à sua voz, verifique se o reconhecimento de fala está ativado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="3a3fe-305">acesse **iniciar**  >  **Configurações** a fala de  >  **privacidade**  >   e ativar o **reconhecimento de fala**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="3a3fe-306">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="3a3fe-307">A entrada manual não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-307">Hand input isn't working</span></span>

<span data-ttu-id="3a3fe-308">para garantir que HoloLens possam ver suas mãos, você precisa mantê-las no quadro do gesto.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="3a3fe-309">A página inicial da realidade misturada fornece comentários que permitem que você saiba quando suas mãos são rastreadas.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="3a3fe-310">Os comentários são diferentes em versões diferentes do HoloLens:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="3a3fe-311">em HoloLens (1ª gen), o cursor olhar muda de um ponto para um anel</span><span class="sxs-lookup"><span data-stu-id="3a3fe-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="3a3fe-312">no HoloLens 2, um cursor de ponta aparece quando a sua mão está perto de um tablet e um raio de lado é exibido quando os slates estão mais distantes</span><span class="sxs-lookup"><span data-stu-id="3a3fe-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="3a3fe-313">Muitos aplicativos de imersão seguem os padrões de entrada que são semelhantes à realidade misturada em casa.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="3a3fe-314">saiba mais sobre como usar a entrada manual em [HoloLens (1ª gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="3a3fe-315">Se você estiver gastando luvas, observe que alguns tipos de luvas não funcionam com o rastreamento manual.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="3a3fe-316">Um exemplo comum é o luvas de borracha preta, que tende a absorver a luz infravermelha e não é captado pela câmera de profundidade.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="3a3fe-317">Se seu trabalho envolve um luvas de borracha, é recomendável tentar uma cor mais clara, como azul ou cinza.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="3a3fe-318">Outro exemplo é o luvas de Baggy grande, que tendem a obscurecer a forma de sua mão.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="3a3fe-319">É recomendável usar luvas que estejam como o ajuste de forma possível para obter melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="3a3fe-320">se o visor tiver impressões digitais ou manchas, use o pano de limpeza microfiber que acompanha o HoloLens para limpar o visor com cuidado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="3a3fe-321">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="3a3fe-322">Não é possível conectar ao Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3a3fe-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="3a3fe-323">aqui estão algumas coisas a serem experimentadas se você não puder conectar seu HoloLens a uma rede de Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="3a3fe-324">Verifique se Wi-Fi está ativado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="3a3fe-325">para verificar, use o gesto iniciar e, em seguida, selecione **Configurações**  >  **rede &amp; Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="3a3fe-326">Se Wi-Fi estiver ativado, tente desligá-lo e depois novamente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="3a3fe-327">Aproxime-se do roteador ou do ponto de acesso.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="3a3fe-328">Reinicie o Wi-Fi roteador e [reinicie o HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="3a3fe-329">Tente se conectar novamente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-329">Try connecting again.</span></span>
- <span data-ttu-id="3a3fe-330">Se nenhuma dessas coisas funcionar, verifique se o roteador está usando o firmware mais recente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="3a3fe-331">Você pode encontrar essas informações no site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="3a3fe-332">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="3a3fe-333">Bluetooth dispositivos não estão emparelhando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="3a3fe-334">se você estiver tendo problemas [para emparelhar um dispositivo Bluetooth](hololens-connect-devices.md), tente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="3a3fe-335">vá para **Configurações**  >  **dispositivos** e verifique se Bluetooth está ativado.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="3a3fe-336">Se estiver, desative-o e ative-o novamente.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="3a3fe-337">certifique-se de que seu dispositivo de Bluetooth seja totalmente cobrado ou tenha baterias novas.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="3a3fe-338">Se você ainda não conseguir se conectar, [reinicie o HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="3a3fe-339">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="3a3fe-340">O microfone USB-C não está funcionando</span><span class="sxs-lookup"><span data-stu-id="3a3fe-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="3a3fe-341">Lembre-se de que alguns microfones USB-C se reportam incorretamente como um microlocutor *e* um palestrante.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="3a3fe-342">Esse é um problema com o microfone e não com HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="3a3fe-343">ao conectar um desses microfones ao HoloLens, o som pode ser perdido.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="3a3fe-344">Felizmente, há uma correção simples.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="3a3fe-345">em **Configurações**  ->    ->  **som** do sistema, defina explicitamente os alto-falantes internos **(Driver de áudio de recurso analógico)** como o **dispositivo padrão**.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="3a3fe-346">HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado mais tarde.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="3a3fe-348">os dispositivos listados como disponíveis no Configurações não funcionam</span><span class="sxs-lookup"><span data-stu-id="3a3fe-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="3a3fe-349">HoloLens (1º gen) não oferece suporte a perfis de áudio Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="3a3fe-350">Bluetooth dispositivos de áudio, como alto-falantes e headsets, podem aparecer como disponíveis nas configurações de HoloLens, mas não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="3a3fe-351">o HoloLens 2 dá suporte ao perfil de áudio Bluetooth A2DP para reprodução de estéreo.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="3a3fe-352">o perfil Bluetooth hands Free que habilita a captura de microfone de um periférico de Bluetooth não tem suporte no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="3a3fe-353">se você tiver problemas ao usar um dispositivo Bluetooth, verifique se ele é um dispositivo com suporte.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="3a3fe-354">Os dispositivos com suporte incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3a3fe-354">Supported devices include the following:</span></span>

- <span data-ttu-id="3a3fe-355">os teclados de Bluetooth de QWERTY de idioma inglês (você pode usá-los em qualquer lugar que use o holographic keyboard).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="3a3fe-356">Bluetoothndo o mouse.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-356">Bluetooth mice.</span></span>
- <span data-ttu-id="3a3fe-357">o [HoloLens clicador](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="3a3fe-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="3a3fe-358">você pode emparelhar outros dispositivos Bluetooth HID e GATT junto com seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="3a3fe-359">no entanto, talvez seja necessário instalar os aplicativos complementares correspondentes de Microsoft Store para realmente usar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3a3fe-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="3a3fe-360">Voltar à lista</span><span class="sxs-lookup"><span data-stu-id="3a3fe-360">Back to list</span></span>](#list)
