---
title: Configurar seu HoloLens 2
description: Saiba como configurar seu HoloLens 2 pela primeira vez em uma rede Wi-Fi com uma conta da Microsoft (MSA) ou do AAD (Azure Active Directory).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923662"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="5b546-104">Configurar seu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5b546-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="5b546-105">Na primeira vez que ligar o HoloLens, você será orientado para configurar o dispositivo, entrar usando uma conta de usuário e calibrar o HoloLens aos seus olhos.</span><span class="sxs-lookup"><span data-stu-id="5b546-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="5b546-106">Esta seção aborda a experiência de configuração inicial do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b546-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="5b546-107">Na próxima seção, você aprenderá a trabalhar com o HoloLens e a interagir com hologramas.</span><span class="sxs-lookup"><span data-stu-id="5b546-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="5b546-108">Para ir diretamente para esse artigo, confira [Noções básicas sobre o HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="5b546-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="5b546-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="5b546-109">Before you start</span></span>

<span data-ttu-id="5b546-110">Antes de começar, verifique se você tem:</span><span class="sxs-lookup"><span data-stu-id="5b546-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="5b546-111">**Uma conexão de rede**.</span><span class="sxs-lookup"><span data-stu-id="5b546-111">**A network connection**.</span></span> <span data-ttu-id="5b546-112">Você precisará conectar o HoloLens a uma rede para configurá-lo.</span><span class="sxs-lookup"><span data-stu-id="5b546-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="5b546-113">Com o HoloLens 2, você pode se conectar usando Wi-Fi ou a ethernet (você precisará de um adaptador USB-C para Ethernet).</span><span class="sxs-lookup"><span data-stu-id="5b546-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="5b546-114">Na primeira vez que se conectar, você precisará de uma rede aberta ou protegida por senha que não exija navegar até um site ou usar certificados para se conectar.</span><span class="sxs-lookup"><span data-stu-id="5b546-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="5b546-115">[Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="5b546-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="5b546-116">**Uma conta Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5b546-116">**A Microsoft account**.</span></span> <span data-ttu-id="5b546-117">Você também precisará entrar no HoloLens com uma conta Microsoft (ou com sua conta corporativa se a organização for proprietária do dispositivo).</span><span class="sxs-lookup"><span data-stu-id="5b546-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="5b546-118">Se não tiver uma conta Microsoft, acesse [account.microsoft.com](https://account.microsoft.com) e configure uma gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="5b546-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="5b546-119">**Um espaço seguro e bem iluminado em que não haja risco de tropeçar**.</span><span class="sxs-lookup"><span data-stu-id="5b546-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="5b546-120">[Informações sobre integridade e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="5b546-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="5b546-121">**Os acessórios opcionais para conforto** que acompanham seu HoloLens, para ajudar você a ajustá-lo da melhor maneira.</span><span class="sxs-lookup"><span data-stu-id="5b546-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="5b546-122">[Mais informações sobre ajuste e conforto](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="5b546-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="5b546-123">Configurar o Windows</span><span class="sxs-lookup"><span data-stu-id="5b546-123">Set up Windows</span></span>

<span data-ttu-id="5b546-124">Na primeira vez que você iniciar o HoloLens 2, a primeira tarefa será configurar o Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="5b546-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="5b546-125">Ao iniciar o HoloLens, você ouvirá uma música e verá um logotipo do Windows.</span><span class="sxs-lookup"><span data-stu-id="5b546-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Primeira tela durante a primeira inicialização](images/01-magic-moment.png)

<span data-ttu-id="5b546-127">O HoloLens 2 percorrerá as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5b546-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="5b546-128">Selecionar seu idioma.</span><span class="sxs-lookup"><span data-stu-id="5b546-128">Select your language.</span></span>

    ![Selecionar idioma](images/04-language.png)

1. <span data-ttu-id="5b546-130">Selecione sua região.</span><span class="sxs-lookup"><span data-stu-id="5b546-130">Select your region.</span></span>

    ![Selecionar região](images/05-region.png)

1. <span data-ttu-id="5b546-132">Calibrar o HoloLens aos seus olhos.</span><span class="sxs-lookup"><span data-stu-id="5b546-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="5b546-133">Se optar por ignorar a calibragem, você será avisado na próxima vez em que fizer logon.</span><span class="sxs-lookup"><span data-stu-id="5b546-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="5b546-134">Primeiro, você ajustará o visor.</span><span class="sxs-lookup"><span data-stu-id="5b546-134">First, you'll adjust your visor.</span></span>
    
        ![Tela de seleção de calibragem](images/06-et-corners.png)

    2. <span data-ttu-id="5b546-136">Para calibrar, você olhará para um conjunto de alvos (chamados de joias).</span><span class="sxs-lookup"><span data-stu-id="5b546-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="5b546-137">Não há problema se você piscar ou fechar os olhos durante a calibragem, mas tente não olhar fixamente para outros objetos no cômodo ou no espaço físico.</span><span class="sxs-lookup"><span data-stu-id="5b546-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="5b546-138">O HoloLens usa esse processo para saber mais sobre a posição de seus olhos para que ele possa renderizar melhor seu mundo holográfico.</span><span class="sxs-lookup"><span data-stu-id="5b546-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Ajustar para seus olhos](images/07-adjust-eyes.png)

        <span data-ttu-id="5b546-140">Após a calibragem, os hologramas serão exibidos corretamente mesmo que o visor mude de posição em sua cabeça.</span><span class="sxs-lookup"><span data-stu-id="5b546-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="5b546-141">As informações de calibragem são armazenadas localmente no dispositivo e não são associadas a informações de conta.</span><span class="sxs-lookup"><span data-stu-id="5b546-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="5b546-142">Para saber mais, confira [Dados de calibragem e segurança](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="5b546-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![A calibragem foi concluída](images/calibration-complete.png)

1. <span data-ttu-id="5b546-144">Conecte-se à Internet (selecione Wi-Fi ou sua conexão Ethernet).</span><span class="sxs-lookup"><span data-stu-id="5b546-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="5b546-145">O HoloLens define o fuso horário automaticamente com base nas informações obtidas da rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="5b546-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="5b546-146">Após a conclusão da configuração, você pode alterar o fuso horário usando o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="5b546-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Conectar ao Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="5b546-148">Se você passar da etapa de Wi-Fi e posteriormente precisar alternar para uma rede diferente enquanto ainda estiver na configuração, pressione os botões **Diminuir volume** e **Ligar/Desligar** simultaneamente para retornar a esta etapa se estiver executando uma versão do SO de outubro de 2019 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="5b546-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="5b546-149">Para versões anteriores, talvez seja necessário [redefinir o dispositivo](hololens-recovery.md) ou reiniciá-lo em uma localização em que a rede Wi-Fi não esteja disponível para impedir a conexão automática.</span><span class="sxs-lookup"><span data-stu-id="5b546-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="5b546-150">Observe também que, durante a Instalação do HoloLens, há um tempo limite de credenciais de dois minutos.</span><span class="sxs-lookup"><span data-stu-id="5b546-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="5b546-151">O nome de usuário e a senha devem ser inseridos dentro de dois minutos, caso contrário, o campo do nome de usuário será limpo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5b546-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="5b546-152">O HoloLens 2 pesquisará e aplicará um perfil do Autopilot, se houver.</span><span class="sxs-lookup"><span data-stu-id="5b546-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="5b546-153">Nenhuma ação é necessária nesta tela.</span><span class="sxs-lookup"><span data-stu-id="5b546-153">No action is needed on this screen.</span></span>
 
    ![Pesquisa de perfil do Autopilot](images/autopilot-profile-search.png) 

1. <span data-ttu-id="5b546-155">Clique em **Aceitar** na tela de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="5b546-155">Click **Accept** on the licensing screen.</span></span>

    ![Contrato de licença do Windows](images/windows-license-agreement.png)

1. <span data-ttu-id="5b546-157">Entre em sua conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5b546-157">Sign in to your user account.</span></span> <span data-ttu-id="5b546-158">Você escolherá entre **O proprietário é meu trabalho ou escola** ou **É meu**.</span><span class="sxs-lookup"><span data-stu-id="5b546-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="5b546-159">Ao escolher **O proprietário é meu trabalho ou escola**, você entra usando uma conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5b546-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="5b546-160">Se a organização usar o Azure AD Premium e tiver configurado o registro de MDM automático, o HoloLens será registrado automaticamente no MDM.</span><span class="sxs-lookup"><span data-stu-id="5b546-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="5b546-161">Se a organização não usar o Azure AD Premium, o registro de MDM automático não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="5b546-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="5b546-162">Nesse caso, você precisará [registrar manualmente o HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="5b546-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="5b546-163">Insira as informações de conta de sua organização.</span><span class="sxs-lookup"><span data-stu-id="5b546-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="5b546-164">Aceite a política de privacidade e o contrato de licença do usuário final.</span><span class="sxs-lookup"><span data-stu-id="5b546-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="5b546-165">Entre usando as credenciais do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5b546-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="5b546-166">Isso pode redirecionar para a página de entrada da organização.</span><span class="sxs-lookup"><span data-stu-id="5b546-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="5b546-167">Continue a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b546-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="5b546-168">Ao escolher **É meu**, você entra usando uma conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b546-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="5b546-169">Depois que instalação for concluída, você poderá [registrar manualmente o HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="5b546-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="5b546-170">Insira as informações de sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b546-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="5b546-171">Digite sua senha.</span><span class="sxs-lookup"><span data-stu-id="5b546-171">Enter your password.</span></span> <span data-ttu-id="5b546-172">Se a conta da Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.</span><span class="sxs-lookup"><span data-stu-id="5b546-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Definir usuário](images/13-device-owner.png)

1. <span data-ttu-id="5b546-174">Configure a conexão com a Íris selecionando **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5b546-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="5b546-175">Você passará por uma experiência semelhante à de calibragem dos olhos.</span><span class="sxs-lookup"><span data-stu-id="5b546-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="5b546-176">Selecione **Concluído** quando a varredura for concluída.</span><span class="sxs-lookup"><span data-stu-id="5b546-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="5b546-177">Você também pode selecionar **Ignorar** para ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="5b546-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="5b546-178">![Configuração da íris](images/setup-iris.png) ![Conclusão da configuração da íris](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="5b546-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="5b546-179">Você vai configurar um PIN para fazer logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b546-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="5b546-180">Este PIN é específico do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b546-180">This PIN is device specific.</span></span> 

    ![Configurar o Windows Hello](images/setup-windows-hello.png)

    ![Configurar o PIN do Windows Hello](images/windows-hello-pin.png)

    ![Configuração do Windows Hello bem-sucedida](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="5b546-184">Selecione se deseja habilitar a fala no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b546-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Habilitar a Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="5b546-186">Selecione se deseja habilitar a localização no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b546-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Habilitar serviços de localização](images/setup-location-services.png)

1. <span data-ttu-id="5b546-188">Selecione o nível de telemetria.</span><span class="sxs-lookup"><span data-stu-id="5b546-188">Select your telemetry level.</span></span> <span data-ttu-id="5b546-189">Se possível, habilite a telemetria opcional.</span><span class="sxs-lookup"><span data-stu-id="5b546-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="5b546-190">Essas informações ajudam muito a equipe de engenharia do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b546-190">This information really helps the HoloLens engineering team.</span></span>

     ![Nível de telemetria](images/24-telemetry.png)

1. <span data-ttu-id="5b546-192">Saiba como usar o gesto de iniciar no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b546-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Saiba como usar o gesto de iniciar, imagem 1](images/26-01-startmenu-learning.png)

     ![Saiba como usar o gesto de iniciar, imagem 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="5b546-195">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="5b546-195">Congratulations!</span></span>  <span data-ttu-id="5b546-196">A configuração está completa e você está pronto para usar o HoloLens!</span><span class="sxs-lookup"><span data-stu-id="5b546-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b546-197">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5b546-197">Next steps</span></span>

1. <span data-ttu-id="5b546-198">Comece a interagir imediatamente com a realidade misturada e navegue no Windows 10 com seu HoloLens. Confira o aplicativo **Dicas** para ver tutoriais práticos para interações manuais.</span><span class="sxs-lookup"><span data-stu-id="5b546-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="5b546-199">Use o gesto de iniciar para voltar ao Início ou diga "Voltar ao início" e selecione Dicas.</span><span class="sxs-lookup"><span data-stu-id="5b546-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="5b546-200">Clique abaixo para continuar lendo sobre como utilizar o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b546-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b546-201">Conheça o HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5b546-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
