---
title: guia de implantação – corporativo conectado HoloLens 2 com guias do Dynamics 365 – implantar
description: saiba como configurar implantações de dispositivos HoloLens 2 em uma rede conectada corporativa com os guias do Dynamics 365.
keywords: HoloLens, gerenciamento, corporativo conectado, guias do Dynamics 365, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637054"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="2b538-104">Implantar – guia conectado corporativo</span><span class="sxs-lookup"><span data-stu-id="2b538-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="2b538-105">Uma parte importante de cada implantação é garantir que sua implantação esteja configurada corretamente antes de testá-la para garantir uma experiência tranqüila para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="2b538-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="2b538-106">como estamos implantando o certificado de Wi-Fi por meio do MDM, precisaremos configurar inicialmente HoloLens e registrar dispositivos em uma rede Wi-Fi aberta ou uma rede que não exija o certificado.</span><span class="sxs-lookup"><span data-stu-id="2b538-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="2b538-107">depois que o HoloLens tiver concluído o OOBE e registrado, o dispositivo receberá o certificado de rede e o LOB configurados anteriormente e poderá validar ambos que foram recebidos pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b538-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="2b538-108">Posteriormente, você poderá confirmar que pode criar e operar um guia de teste.</span><span class="sxs-lookup"><span data-stu-id="2b538-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="2b538-109">Validação de registro</span><span class="sxs-lookup"><span data-stu-id="2b538-109">Enrollment Validation</span></span>

<span data-ttu-id="2b538-110">Agora que tudo está configurado corretamente para o Azure AD e o registro de MDM, o restante agora deve ser um snap.</span><span class="sxs-lookup"><span data-stu-id="2b538-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="2b538-111">você precisará de uma conexão Wi-Fi e do dispositivo HoloLens e uma das contas de usuário do Azure AD configuradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2b538-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="2b538-112">Se seu dispositivo não estiver atualmente em um estado de configurações de fábrica, agora seria um bom momento para refazer [o flash do dispositivo](/hololens/hololens-recovery#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="2b538-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="2b538-113">Depois que o dispositivo estiver em OOBE, você precisará começar a interagir e seguir os prompts.</span><span class="sxs-lookup"><span data-stu-id="2b538-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="2b538-114">Conexão a uma rede aberta Wi-Fi que não requer certificados para ingressar no Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="2b538-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="2b538-115">Isso permitirá que o dispositivo Baixe o certificado a ser usado no Wi-Fi da organização após a configuração inicial.</span><span class="sxs-lookup"><span data-stu-id="2b538-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="2b538-116">o aviso crítico será quando você for solicitado **Who a possuir este HoloLens?**</span><span class="sxs-lookup"><span data-stu-id="2b538-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="2b538-117">Selecione **meu trabalho ou escola possui** e insira suas credenciais de conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2b538-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="2b538-118">Quando o registro for bem-sucedido, você será solicitado a configurar um PIN.</span><span class="sxs-lookup"><span data-stu-id="2b538-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="2b538-119">Este PIN é exclusivo para este dispositivo para este usuário.</span><span class="sxs-lookup"><span data-stu-id="2b538-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="2b538-120">Você também será solicitado a fornecer verificações de íris, dados de voz e configurações de telemetria e, por fim, poderá aprender a abrir o menu iniciar e concluir o OOBE.</span><span class="sxs-lookup"><span data-stu-id="2b538-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="2b538-121">depois de chegar à casa misturada na realidade, abra o menu Iniciar usando o **gesto de início** que você acabou de aprender.</span><span class="sxs-lookup"><span data-stu-id="2b538-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="2b538-122">selecione o aplicativo **Configurações** e selecione **sistema**.</span><span class="sxs-lookup"><span data-stu-id="2b538-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="2b538-123">a primeira informação que você verá é o nome do dispositivo, que para o dispositivo HoloLens 2 será o &quot; HoloLens- &quot; seguido por uma cadeia de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="2b538-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="2b538-124">Anote esse nome.</span><span class="sxs-lookup"><span data-stu-id="2b538-124">Take note of this name.</span></span>

    ![tela do HoloLens 2 Configurações](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="2b538-126">Verifique se o dispositivo ingressou no Azure AD com êxito.</span><span class="sxs-lookup"><span data-stu-id="2b538-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="2b538-127">Há duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="2b538-127">There are two ways;</span></span>

    1.  <span data-ttu-id="2b538-128">o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="2b538-128">The Settings app.</span></span> <span data-ttu-id="2b538-129">em **Configurações** selecione **contas**  ->  **acesso corporativo ou de estudante**.</span><span class="sxs-lookup"><span data-stu-id="2b538-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="2b538-130">Nessa tela, você pode verificar se está registrado com êxito ao ver &quot; conectado ao nameofAAD&#39;s do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2b538-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="2b538-131">Conectado por *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="2b538-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="2b538-132">Isso verificará se o dispositivo está associado à sua organização&#39;s do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2b538-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="2b538-133">O [Portal do Azure](https://portal.azure.com/#home).</span><span class="sxs-lookup"><span data-stu-id="2b538-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="2b538-134">vá para **Azure Active Directory**  ->  **dispositivos**  ->  **todos os dispositivos** e pesquise o nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b538-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="2b538-135">Em tipo de junção, ele aparecerá como "ingressado no Azure AD".</span><span class="sxs-lookup"><span data-stu-id="2b538-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="2b538-136">![Verificar tipo de junção no Azure AD](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="2b538-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="2b538-137">Verifique se o dispositivo está registrado no MDM.</span><span class="sxs-lookup"><span data-stu-id="2b538-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="2b538-138">Há duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="2b538-138">There are two ways;</span></span>

    1. <span data-ttu-id="2b538-139">em **Configurações**, selecione **contas**  ->  **acesso corporativo ou de estudante**.</span><span class="sxs-lookup"><span data-stu-id="2b538-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="2b538-140">Nessa tela, você pode verificar se está registrado com êxito ao ver &quot; conectado ao nameofAAD&#39;s do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2b538-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="2b538-141">Conectado por *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="2b538-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="2b538-142">Nessa conta corporativa ou de estudante do Access, selecionando &quot; conectado ao nameofAAD&#39;s AD do Azure.</span><span class="sxs-lookup"><span data-stu-id="2b538-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="2b538-143">Conectado por yourusername@nameofAAD.onmicrosoft.com &quot; e selecione o botão **informações** .</span><span class="sxs-lookup"><span data-stu-id="2b538-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="2b538-144">[centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home).</span><span class="sxs-lookup"><span data-stu-id="2b538-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="2b538-145">Faça logon e selecione  **dispositivos**  e, em seguida,  **todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2b538-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="2b538-146">a partir daqui, você pode pesquisar seu HoloLens dispositivo&#39;nome.</span><span class="sxs-lookup"><span data-stu-id="2b538-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="2b538-147">você deve ser capaz de ver suas HoloLens listadas no Intune.</span><span class="sxs-lookup"><span data-stu-id="2b538-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Verificar gerenciado pelo Intune no Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="2b538-149">Wi-Fi validação de certificado</span><span class="sxs-lookup"><span data-stu-id="2b538-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="2b538-150">Agora, o dispositivo deve ter recebido o certificado de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="2b538-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="2b538-151">A validação mais simples que você pode fazer é tentar se conectar à conexão de Wi-Fi para a qual você&#39;recebido o certificado.</span><span class="sxs-lookup"><span data-stu-id="2b538-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="2b538-152">abra o aplicativo **Configurações** e navegue até **rede &amp; Internet**  ->  **wi-fi** e selecione a conexão wi-fi.</span><span class="sxs-lookup"><span data-stu-id="2b538-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="2b538-153">uma vez conectado, abra o aplicativo Microsoft Edge e confirme que você pode navegar para um site.</span><span class="sxs-lookup"><span data-stu-id="2b538-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="2b538-154">Para confirmar que você recebeu o certificado no dispositivo, você pode usar o Gerenciador de [certificados](/hololens/certificate-manager).</span><span class="sxs-lookup"><span data-stu-id="2b538-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="2b538-155">Validar a instalação do aplicativo de LOB</span><span class="sxs-lookup"><span data-stu-id="2b538-155">Validate LOB app install</span></span>

<span data-ttu-id="2b538-156">para ver o progresso da instalação de um aplicativo gerenciado, você verá se o aplicativo está instalado ou verifica Configurações.</span><span class="sxs-lookup"><span data-stu-id="2b538-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="2b538-157">ao configurar um aplicativo LOB como uma instalação necessária para nosso grupo, depois de registrar o HoloLens com um usuário no grupo atribuído, o aplicativo será baixado automaticamente para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b538-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="2b538-158">abra o menu Iniciar e selecione **todos os aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2b538-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="2b538-159">Dependendo do número de aplicativos que você tem, talvez seja necessário usar os botões **Page Up** ou **Page Down** .</span><span class="sxs-lookup"><span data-stu-id="2b538-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="2b538-160">para validar a instalação do aplicativo no dispositivo, você pode fazer isso por meio de **Configurações**  ->  **contas**  ->  **acessar o trabalho ou a escola**; selecione a conta, em seguida, o botão **informações** e role para baixo para ver diferentes configurações e aplicativos aplicados ao dispositivo do MDM.</span><span class="sxs-lookup"><span data-stu-id="2b538-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="2b538-161">Para validar a instalação do Intune, navegue até a página aplicativos do [portal do mem](https://endpoint.microsoft.com/#home)  ->   – > todos os **aplicativos**  -> *TheNameOfYourApp* de  ->  **status de instalação do dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="2b538-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="2b538-162">Veja mais: [implantação de aplicativo do Intune para HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="2b538-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="2b538-163">Validar guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2b538-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="2b538-164">há modos para o aplicativo de guias em HoloLens, criação e operação.</span><span class="sxs-lookup"><span data-stu-id="2b538-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="2b538-165">Você precisará concluir a criação de um guia antes de operar.</span><span class="sxs-lookup"><span data-stu-id="2b538-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="2b538-166">Criando o guia</span><span class="sxs-lookup"><span data-stu-id="2b538-166">Authoring the Guide</span></span>

<span data-ttu-id="2b538-167">Não precisamos fazer muito para essa validação rápida.</span><span class="sxs-lookup"><span data-stu-id="2b538-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="2b538-168">Basta selecionar o guia que você preparou em seu computador.</span><span class="sxs-lookup"><span data-stu-id="2b538-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="2b538-169">Você precisará [ancorar o guia](/dynamics365/mixed-reality/guides/hololens-app-anchor)para uma validação rápida, você pode usar uma âncora Holographic.</span><span class="sxs-lookup"><span data-stu-id="2b538-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="2b538-170">Depois disso, você deve [posicionar suas etapas e modelos](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span><span class="sxs-lookup"><span data-stu-id="2b538-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="2b538-171">Você precisará da função de **criação** para fazer logon no PC e criar no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b538-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="2b538-172">A função operador é somente leitura e não tem acesso ao aplicativo de PC.</span><span class="sxs-lookup"><span data-stu-id="2b538-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="2b538-173">Operando o guia</span><span class="sxs-lookup"><span data-stu-id="2b538-173">Operating the Guide</span></span>

<span data-ttu-id="2b538-174">Depois que os hologramas estiverem em vigor, você poderá testar a operação de seu guia.</span><span class="sxs-lookup"><span data-stu-id="2b538-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="2b538-175">Selecionar **modo de operador**</span><span class="sxs-lookup"><span data-stu-id="2b538-175">Select **Operator mode**</span></span>
- <span data-ttu-id="2b538-176">Clique nas etapas do seu guia.</span><span class="sxs-lookup"><span data-stu-id="2b538-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="2b538-177">Para obter diretrizes mais detalhadas sobre como operar um guia, confira estes recursos:</span><span class="sxs-lookup"><span data-stu-id="2b538-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="2b538-178">Visão geral da operação de um guia em guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2b538-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="2b538-179">Seja orientado com o cartão Step como um operador nos guias do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2b538-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="2b538-180">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2b538-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="2b538-181">Implantação conectada corporativa-manter</span><span class="sxs-lookup"><span data-stu-id="2b538-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
