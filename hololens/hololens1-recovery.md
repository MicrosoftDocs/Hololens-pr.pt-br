---
title: Reiniciar, redefinir ou recuperar o HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Como usar a Windows Device Recovery Tool para mostrar uma imagem para o HoloLens de 1ª geração.
keywords: como fazer, reinicializar, redefinir, recuperar, reinicialização forçada, reinicialização flexível, ciclo de energia, HoloLens, desligar, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: de53f8f2cccfe3ece8900c88c5379adf2fb55a7b
ms.sourcegitcommit: 5d38af8d17dfcc028e7e0b2bb888c6c9d1e40524
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899174"
---
# <span data-ttu-id="4b228-104">Reiniciar, redefinir ou recuperar o HoloLens de 1ª geração</span><span class="sxs-lookup"><span data-stu-id="4b228-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="4b228-105">Se você estiver enfrentando problemas com o seu HoloLens, talvez seja necessário tentar uma reinicialização, redefinição ou, até mesmo, ire-instalar a partir de uma imagem do sistema utilizando a recuperação de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4b228-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="4b228-106">Aqui estão algumas coisas a serem feitas se o seu HoloLens não estiver funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="4b228-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="4b228-107">Este artigo o orientará pelas etapas de recuperação recomendadas.</span><span class="sxs-lookup"><span data-stu-id="4b228-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="4b228-108">Se você estiver tentando recuperar um HoloLens 2, confira a página para [Recuperar um HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), uma vez que há diferenças nos processos.</span><span class="sxs-lookup"><span data-stu-id="4b228-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="4b228-109">Esse artigo se concentra no software e dispositivo do HoloLens, se os hologramas não aparecerem corretamente, [este artigo](hololens-environment-considerations.md) fala sobre fatores ambientais que melhoram a qualidade do holograma.</span><span class="sxs-lookup"><span data-stu-id="4b228-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="4b228-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="4b228-110">Restart</span></span>

### <span data-ttu-id="4b228-111">Executar uma reinicialização segura usando a Cortana</span><span class="sxs-lookup"><span data-stu-id="4b228-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="4b228-112">A maneira mais segura de reiniciar o HoloLens é usar a Cortana.</span><span class="sxs-lookup"><span data-stu-id="4b228-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="4b228-113">Geralmente, essa é uma primeira etapa fácil de seguir quando ocorrer um problema com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4b228-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b228-114">A Cortana não está disponível em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4b228-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="4b228-115">A Cortana está disponível a todos os dispositivos do HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="4b228-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="4b228-116">A Cortana está disponível em dispositivos do HoloLens 2 em uma compilação anterior à atualização do Windows Holograpic, versão 2004.</span><span class="sxs-lookup"><span data-stu-id="4b228-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="4b228-117">Instale no seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="4b228-117">Put on your device</span></span>
1. <span data-ttu-id="4b228-118">Certifique-se de que ele está ligado, que um usuário está conectado e o dispositivo não está aguardando que uma senha seja desbloqueada.</span><span class="sxs-lookup"><span data-stu-id="4b228-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="4b228-119">Diga "Ei Cortana, reinicializar" ou "Ei Cortana, reiniciar".</span><span class="sxs-lookup"><span data-stu-id="4b228-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="4b228-120">Quando ela reconhecer, solicitará a confirmação.</span><span class="sxs-lookup"><span data-stu-id="4b228-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="4b228-121">Aguarde um pouco para que um som seja reproduzido após concluir a pergunta, indicando que ele está ouvindo você e, em seguida, diga "Sim".</span><span class="sxs-lookup"><span data-stu-id="4b228-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="4b228-122">O dispositivo será reiniciado agora.</span><span class="sxs-lookup"><span data-stu-id="4b228-122">The device will now restart.</span></span>

### <span data-ttu-id="4b228-123">Execute uma reinicialização segura usando a Cortana</span><span class="sxs-lookup"><span data-stu-id="4b228-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="4b228-124">Se ainda não conseguir reiniciar o dispositivo, você pode tentar reiniciá-lo usando o botão de ligar:</span><span class="sxs-lookup"><span data-stu-id="4b228-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="4b228-125">Pressione e mantenha pressionado o botão de energia por cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="4b228-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="4b228-126">Após um segundo, você verá todos os cinco LEDs iluminando e, em seguida, desativando devagar da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="4b228-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="4b228-127">Após cinco segundos, todos os LEDs estarão inativos, indicando que o comando de desligamento foi emitido com sucesso.</span><span class="sxs-lookup"><span data-stu-id="4b228-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="4b228-128">Observe que é importante parar de pressionar o botão imediatamente após todos os LEDs terem desativado.</span><span class="sxs-lookup"><span data-stu-id="4b228-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="4b228-129">Aguarde um minuto para que o desligamento seja bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="4b228-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="4b228-130">Observe que o desligamento ainda pode estar em andamento, mesmo que os monitores estejam desativados.</span><span class="sxs-lookup"><span data-stu-id="4b228-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="4b228-131">Ligue o dispositivo novamente mantendo o botão de ligar por um segundo.</span><span class="sxs-lookup"><span data-stu-id="4b228-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="4b228-132">Executar uma reinicialização segura usando o Portal de Dispositivos do Windows</span><span class="sxs-lookup"><span data-stu-id="4b228-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="4b228-133">Para fazer isso, o HoloLens deve ser configurado como um dispositivo desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="4b228-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="4b228-134">Leia mais sobre [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="4b228-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="4b228-135">Se o procedimento anterior não funcionar, você pode tentar reiniciar o dispositivo usando [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="4b228-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="4b228-136">No canto superior direito, há uma opção para reiniciar ou desligar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b228-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="4b228-137">Executar uma reinicialização forçada sem segurança</span><span class="sxs-lookup"><span data-stu-id="4b228-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="4b228-138">Caso nenhum dos métodos anteriores conseguir reiniciar o dispositivo com êxito, você pode forçar uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="4b228-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="4b228-139">Esse método é equivalente a puxar a bateria do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4b228-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="4b228-140">É uma operação perigosa, o que pode deixar o seu dispositivo em um estado corrompido.</span><span class="sxs-lookup"><span data-stu-id="4b228-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="4b228-141">Se isso acontecer, você precisará ligar e desligar o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4b228-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="4b228-142">Esse é um método potencialmente nocivo e só deve ser usado no caso de nenhum dos métodos acima.</span><span class="sxs-lookup"><span data-stu-id="4b228-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="4b228-143">Pressione e mantenha pressionado o botão de energia por pelo menos dez segundos.</span><span class="sxs-lookup"><span data-stu-id="4b228-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="4b228-144">Não há problema em manter o botão por mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="4b228-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="4b228-145">É seguro ignorar qualquer atividade do LED.</span><span class="sxs-lookup"><span data-stu-id="4b228-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="4b228-146">Solte o botão e aguarde dois ou três segundos.</span><span class="sxs-lookup"><span data-stu-id="4b228-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="4b228-147">Ligue o dispositivo novamente mantendo o botão de ligar por um segundo.</span><span class="sxs-lookup"><span data-stu-id="4b228-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="4b228-148">Se você ainda estiver enfrentando problemas, pressione o botão de ligar por quatro segundos até que todos os indicadores de bateria apareçam gradualmente e a tela pare de exibir os hologramas.</span><span class="sxs-lookup"><span data-stu-id="4b228-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="4b228-149">Aguarde um minuto e, em seguida, pressione o botão de ligar novamente para ativar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b228-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="4b228-150">Redefinir para as configurações de fábrica</span><span class="sxs-lookup"><span data-stu-id="4b228-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="4b228-151">A bateria precisa de pelo menos 40% da carga para redefinir.</span><span class="sxs-lookup"><span data-stu-id="4b228-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="4b228-152">Se o seu HoloLens ainda estiver enfrentando problemas após reiniciar, tente redefini-lo para as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4b228-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="4b228-153">A redefinição do HoloLens mantém a versão do software do Windows Holographic que está instalada nele e retorna tudo para as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4b228-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="4b228-154">Se você reiniciar seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo a redefinição do TPM.</span><span class="sxs-lookup"><span data-stu-id="4b228-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="4b228-155">A redefinição instalará apenas a versão mais recente do Windows Holographic e será preciso refazer todas as etapas de inicialização (calibragem, conectar ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="4b228-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="4b228-156">Inicie o aplicativo de Configurações e selecione **Atualizar** > **Recuperação**.</span><span class="sxs-lookup"><span data-stu-id="4b228-156">Launch the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="4b228-157">Selecione a opção **Redefinir dispositivo** e leia a mensagem de confirmação.</span><span class="sxs-lookup"><span data-stu-id="4b228-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="4b228-158">Se você concordar em reiniciar seu dispositivo, ele será reiniciado e exibirá um conjunto de engrenagens giradas com uma barra de progresso.</span><span class="sxs-lookup"><span data-stu-id="4b228-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="4b228-159">Aguarde cerca de trinta minutos para a conclusão desse processo.</span><span class="sxs-lookup"><span data-stu-id="4b228-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="4b228-160">A redefinição será concluída, e o dispositivo será reiniciado para a configuração inicial.</span><span class="sxs-lookup"><span data-stu-id="4b228-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="4b228-161">Re-instalar o sistema operacional</span><span class="sxs-lookup"><span data-stu-id="4b228-161">Re-install the operating system</span></span>

<span data-ttu-id="4b228-162">Se o dispositivo ainda estiver com problemas após a reinicialização e a redefinição, você pode usar uma ferramenta de recuperação no computador para reinstalar o firmware e o sistema operacional do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4b228-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="4b228-163">Todos os dados do HoloLens devem ser redefinidos em uma Atualização Completa do Flash (FFU).</span><span class="sxs-lookup"><span data-stu-id="4b228-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="4b228-164">Isso é semelhante a um ISO, WIM ou VHD.</span><span class="sxs-lookup"><span data-stu-id="4b228-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="4b228-165">Saiba mais sobre os formatos de arquivo de imagem do FFU.</span><span class="sxs-lookup"><span data-stu-id="4b228-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="4b228-166">Se necessário, você pode instalar um sistema operacional completamente novo em seu HoloLens (1ª geração) com a Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="4b228-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="4b228-167">Antes de usar essa ferramenta, determine se reiniciar ou redefinir seu HoloLens corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="4b228-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="4b228-168">O processo de recuperação pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="4b228-168">The recovery process may take some time.</span></span>  <span data-ttu-id="4b228-169">Quando terminar, a versão mais recente do software Windows Holographic aprovado para o seu HoloLens será instalada.</span><span class="sxs-lookup"><span data-stu-id="4b228-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="4b228-170">Para usar a ferramenta, você precisará de um computador que esteja executando o Windows 10 ou posterior, com pelo menos 4 GB de espaço de armazenamento disponível.</span><span class="sxs-lookup"><span data-stu-id="4b228-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="4b228-171">Observe que você não pode executar essa ferramenta em uma máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="4b228-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="4b228-172">Recuperar seu HoloLens 2:</span><span class="sxs-lookup"><span data-stu-id="4b228-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="4b228-173">No computador, baixe e instale a [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)</span><span class="sxs-lookup"><span data-stu-id="4b228-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="4b228-174">Conecte o HoloLens (1ª geração) ao seu computador usando o cabo micro USB que veio com o seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4b228-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="4b228-175">Execute a Windows Device Recovery Tool e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="4b228-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="4b228-176">Se o HoloLens (1ª geração) não for detectado automaticamente, selecione **Meu dispositivo não foi detectado** e siga as instruções para colocar o dispositivo no modo de recuperação.</span><span class="sxs-lookup"><span data-stu-id="4b228-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="4b228-177">Modo de Piscar Manualmente:</span><span class="sxs-lookup"><span data-stu-id="4b228-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="4b228-178">No caso de o seu dispositivo não estar sendo detectado, use o seguinte método para inseri-lo manualmente no modo de piscar.</span><span class="sxs-lookup"><span data-stu-id="4b228-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="4b228-179">Desconecte o dispositivo de todas as fontes de alimentação.</span><span class="sxs-lookup"><span data-stu-id="4b228-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="4b228-180">Se o dispositivo estiver ligado, mantenha pressionado o botão de ligar até que ele desligue completamente.</span><span class="sxs-lookup"><span data-stu-id="4b228-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="4b228-181">Segure o botão **Aumentar o volume** e toque brevemente no botão **Ligar**.</span><span class="sxs-lookup"><span data-stu-id="4b228-181">Hold the **Volume Up** button, and briefly tap the **Power button**.</span></span> 
1. <span data-ttu-id="4b228-182">O dispositivo deve ser inicializado e, em seguida, exibir apenas a luz LED central.</span><span class="sxs-lookup"><span data-stu-id="4b228-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="4b228-183">Conecte o dispositivo em seu PC.</span><span class="sxs-lookup"><span data-stu-id="4b228-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="4b228-184">Iniciar a Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="4b228-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="4b228-185">Será necessário selecionar *Meu dispositivo não foi detectado*\* e, em seguida, selecionar **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="4b228-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="4b228-186">Siga as instruções para recuperar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b228-186">Follow the instructions to recover your device.</span></span>
