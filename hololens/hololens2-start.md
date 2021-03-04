---
title: Configurar seu HoloLens 2
description: Saiba como configurar seu HoloLens 2 pela primeira vez em uma rede Wi-Fi com uma conta da Microsoft (MSA) ou do Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 31c2c9ed7b2a35c759a0e1d86b89a2f0ab75d965
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385605"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="1dadc-104">Configurar seu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1dadc-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="1dadc-105">Na primeira vez que ligar o HoloLens, você será orientado para configurar seu dispositivo, entrar com uma conta de usuário e calibrar o HoloLens aos seus olhos.</span><span class="sxs-lookup"><span data-stu-id="1dadc-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="1dadc-106">Esta seção aborda a experiência de configuração inicial do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1dadc-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="1dadc-107">Na próxima seção, você aprenderá a trabalhar com o HoloLens e interagir com hologramas.</span><span class="sxs-lookup"><span data-stu-id="1dadc-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="1dadc-108">Para avançar para esse artigo, consulte [Introdução ao HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="1dadc-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="1dadc-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1dadc-109">Before you start</span></span>

<span data-ttu-id="1dadc-110">Antes de começar, verifique se você tem o seguinte disponível:</span><span class="sxs-lookup"><span data-stu-id="1dadc-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="1dadc-111">**Uma conexão de rede**.</span><span class="sxs-lookup"><span data-stu-id="1dadc-111">**A network connection**.</span></span> <span data-ttu-id="1dadc-112">Você precisará conectar o HoloLens a uma rede para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="1dadc-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="1dadc-113">Com o HoloLens 2, você pode se conectar ao Wi-Fi ou usando Ethernet (você precisará de um adaptador USB-C para Ethernet).</span><span class="sxs-lookup"><span data-stu-id="1dadc-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="1dadc-114">Na primeira vez que se conectar, você precisará de uma rede aberta ou protegida por senha que não exige a navegação até um site ou usar certificados para se conectar.</span><span class="sxs-lookup"><span data-stu-id="1dadc-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="1dadc-115">[Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="1dadc-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="1dadc-116">**Uma conta Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1dadc-116">**A Microsoft account**.</span></span> <span data-ttu-id="1dadc-117">Você também precisará entrar no HoloLens com uma conta Microsoft (ou com sua conta corporativa, se a organização possuir o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="1dadc-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="1dadc-118">Se você não tiver uma conta Microsoft, acesse [account.microsoft.com](https://account.microsoft.com) e configure uma gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="1dadc-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="1dadc-119">**Um espaço seguro e bem iluminado sem risco de tropeçar**.</span><span class="sxs-lookup"><span data-stu-id="1dadc-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="1dadc-120">[Informações de saúde e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="1dadc-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="1dadc-121">**Os acessórios de conforto opcionais** que vieram com o HoloLens, para ajudá-lo a obter o mais confortável.</span><span class="sxs-lookup"><span data-stu-id="1dadc-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="1dadc-122">[Mais sobre ajuste e conforto](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="1dadc-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="1dadc-123">Configurar o Windows</span><span class="sxs-lookup"><span data-stu-id="1dadc-123">Set up Windows</span></span>

<span data-ttu-id="1dadc-124">Na primeira vez que você iniciar o HoloLens 2, a primeira tarefa será configurar o Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="1dadc-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="1dadc-125">Ao iniciar o HoloLens, você ouvirá uma música e verá um logotipo do Windows.</span><span class="sxs-lookup"><span data-stu-id="1dadc-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Primeira tela durante a primeira inicialização](images/01-magic-moment.png)

<span data-ttu-id="1dadc-127">O HoloLens 2 abordará as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="1dadc-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="1dadc-128">Selecione seu idioma.</span><span class="sxs-lookup"><span data-stu-id="1dadc-128">Select your language.</span></span>
    ![Selecionar idioma](images/04-language.png)

1. <span data-ttu-id="1dadc-130">Selecione sua região.</span><span class="sxs-lookup"><span data-stu-id="1dadc-130">Select your region.</span></span>
    ![Selecionar região](images/05-region.png)

1. <span data-ttu-id="1dadc-132">Calibre o HoloLens aos seus olhos.</span><span class="sxs-lookup"><span data-stu-id="1dadc-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="1dadc-133">Se optar por ignorar a calibragem, você será avisado na próxima vez em que fizer logon.</span><span class="sxs-lookup"><span data-stu-id="1dadc-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="1dadc-134">Para calibrar, você verá um conjunto de alvos (chamados de gems).</span><span class="sxs-lookup"><span data-stu-id="1dadc-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="1dadc-135">Não há problema se você piscar ou fechar os olhos durante a calibragem, mas não olhe para outros objetos no cômodo ou no espaço físico.</span><span class="sxs-lookup"><span data-stu-id="1dadc-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="1dadc-136">O HoloLens usa esse processo para saber mais sobre a posição de seus olhos, para que você possa renderizar melhor o mundo holográfico.</span><span class="sxs-lookup"><span data-stu-id="1dadc-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="1dadc-137">Após a calibragem, os hologramas serão exibidos corretamente, mesmo que o visor mude de posição em sua cabeça.</span><span class="sxs-lookup"><span data-stu-id="1dadc-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="1dadc-138">As informações de calibragem são armazenadas localmente no dispositivo e não são associadas a informações de conta.</span><span class="sxs-lookup"><span data-stu-id="1dadc-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="1dadc-139">Para obter mais informações, consulte [Segurança e dados de calibragem](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="1dadc-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Tela de seleção da calibragem](images/06-et-corners.png)

1. <span data-ttu-id="1dadc-141">Conecte-se à Internet (selecione Wi-Fi ou sua conexão Ethernet).</span><span class="sxs-lookup"><span data-stu-id="1dadc-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="1dadc-142">O HoloLens define o fuso horário automaticamente com base nas informações obtidas da rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="1dadc-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="1dadc-143">Após a conclusão da configuração, você pode alterar o fuso horário usando o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="1dadc-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Conectar-se ao Wi-Fi](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="1dadc-145">Se você passar da etapa de Wi-Fi e posteriormente precisar alternar para uma rede diferente enquanto ainda estiver na configuração, pressione os botões **Diminuir o Volume** e **Ligar/Desligar** simultaneamente para retornar a esta etapa se estiver executando uma versão do SO de outubro de 2019 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="1dadc-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="1dadc-146">Para versões anteriores, talvez seja necessário [redefinir o dispositivo](hololens-recovery.md) ou reiniciá-lo em um local em que a rede Wi-Fi não esteja disponível para impedir a conexão automática.</span><span class="sxs-lookup"><span data-stu-id="1dadc-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="1dadc-147">Observe também que, durante a Instalação do HoloLens, há um tempo limite de credenciais de dois minutos.</span><span class="sxs-lookup"><span data-stu-id="1dadc-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="1dadc-148">O nome de usuário e a senha devem ser inseridos dentro de dois minutos, caso contrário, o campo do nome de usuário será automaticamente limpo.</span><span class="sxs-lookup"><span data-stu-id="1dadc-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="1dadc-149">Entre em sua conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1dadc-149">Sign in to your user account.</span></span> <span data-ttu-id="1dadc-150">Você escolherá entre **O proprietário é meu trabalho ou escola** e **Sou o proprietário**.</span><span class="sxs-lookup"><span data-stu-id="1dadc-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="1dadc-151">Ao escolher **O proprietário é meu trabalho ou escola**, você entra usando uma conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1dadc-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="1dadc-152">Se a organização usar o Azure AD Premium e tiver configurado o registro de MDM automático, o HoloLens será registrado automaticamente no MDM.</span><span class="sxs-lookup"><span data-stu-id="1dadc-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="1dadc-153">Se a organização não usar o Azure AD Premium, o registro de MDM automático não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="1dadc-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="1dadc-154">Nesse caso, você precisará [registrar o HoloLens no gerenciamento de dispositivo manualmente](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="1dadc-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="1dadc-155">Insira as informações de sua conta organizacional.</span><span class="sxs-lookup"><span data-stu-id="1dadc-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="1dadc-156">Aceite a política de privacidade e o contrato de licença do usuário final.</span><span class="sxs-lookup"><span data-stu-id="1dadc-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="1dadc-157">Entre usando as credenciais do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1dadc-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="1dadc-158">Isso pode redirecionar para a página de entrada da organização.</span><span class="sxs-lookup"><span data-stu-id="1dadc-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="1dadc-159">Continue a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1dadc-159">Continue setting up the device.</span></span>
    - <span data-ttu-id="1dadc-160">Ao escolher **É meu**, você entra usando uma conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dadc-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="1dadc-161">Depois que instalação for concluída, você poderá [registrar o HoloLens no gerenciamento de dispositivo manualmente](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="1dadc-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="1dadc-162">Insira as informações de sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1dadc-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="1dadc-163">Insira a senha.</span><span class="sxs-lookup"><span data-stu-id="1dadc-163">Enter your password.</span></span> <span data-ttu-id="1dadc-164">Se a conta Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.</span><span class="sxs-lookup"><span data-stu-id="1dadc-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Definir o usuário](images/13-device-owner.png)

1. <span data-ttu-id="1dadc-166">Escolha se deseja habilitar o controle por voz no HoloLens 2 e se deseja enviar telemetria de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="1dadc-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![Habilitar a Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="1dadc-168">Selecione o nível de telemetria.</span><span class="sxs-lookup"><span data-stu-id="1dadc-168">Select your telemetry level.</span></span> <span data-ttu-id="1dadc-169">Se possível, habilite a telemetria completa.</span><span class="sxs-lookup"><span data-stu-id="1dadc-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="1dadc-170">Essas informações ajudam muito a equipe de engenharia do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1dadc-170">This information really helps the HoloLens engineering team.</span></span>
     ![Nível de telemetria](images/24-telemetry.png)

1. <span data-ttu-id="1dadc-172">Saiba como usar o gesto de iniciar no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1dadc-172">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![Saiba como usar o gesto de iniciar, imagem 1](images/26-01-startmenu-learning.png) ![Saiba como usar o gesto de iniciar, imagem 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="1dadc-174">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="1dadc-174">Congratulations!</span></span>  <span data-ttu-id="1dadc-175">A configuração está completa, e você está pronto para usar o HoloLens!</span><span class="sxs-lookup"><span data-stu-id="1dadc-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="1dadc-176">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="1dadc-176">Next steps</span></span>

1. <span data-ttu-id="1dadc-177">Comece a interagir imediatamente com a realidade misturada e navegue no Windows 10 com seu HoloLens - confira o aplicativo **Dicas** para tutoriais práticos para interações manuais.</span><span class="sxs-lookup"><span data-stu-id="1dadc-177">Start interacting right away with with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="1dadc-178">Use o gesto de iniciar para voltar ao Início ou diga "Voltar ao início" e selecione Dicas.</span><span class="sxs-lookup"><span data-stu-id="1dadc-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span> 
1. <span data-ttu-id="1dadc-179">Clique abaixo para continuar lendo sobre como usar o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1dadc-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1dadc-180">Introdução ao HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1dadc-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
