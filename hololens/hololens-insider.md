---
title: Versão prévia do Insider para Microsoft HoloLens
description: É fácil começar a usar as compilações do insider e fornecer comentários importantes para a nossa próxima atualização de sistema operacional para o HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162956"
---
# <span data-ttu-id="1d263-103">Versão prévia do Insider para Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="1d263-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="1d263-104">Bem-vindo às versões mais recentes do insider Preview para HoloLens!</span><span class="sxs-lookup"><span data-stu-id="1d263-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="1d263-105">É fácil [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários importantes para a nossa próxima atualização de sistema operacional para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d263-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="1d263-106">Notas da versão do Windows Insider</span><span class="sxs-lookup"><span data-stu-id="1d263-106">Windows Insider Release Notes</span></span>

### <span data-ttu-id="1d263-107">Instalar aplicativos no HoloLens 2 via instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1d263-107">Install Apps on HoloLens 2 via App Installer</span></span>
<span data-ttu-id="1d263-108">Enviaremos a funcionalidade do instalador do aplicativo logo após a atualização do Windows holográfico, versão 20H2.</span><span class="sxs-lookup"><span data-stu-id="1d263-108">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="1d263-109">Estamos **adicionando uma nova funcionalidade (instalador de aplicativos) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1d263-109">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="1d263-110">O recurso estará **ativado por padrão para dispositivos não gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="1d263-110">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="1d263-111">Para evitar interrupções em empresas, o instalador do aplicativo **não estará disponível para dispositivos gerenciados** no momento.</span><span class="sxs-lookup"><span data-stu-id="1d263-111">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="1d263-112">Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="1d263-112">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="1d263-113">MDM [registrado](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="1d263-113">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="1d263-114">Configurado com o [pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="1d263-114">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="1d263-115">A [identidade](hololens-identity.md) do usuário é AAD</span><span class="sxs-lookup"><span data-stu-id="1d263-115">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="1d263-116">Agora você pode instalar aplicativos sem precisar habilitar o modo de desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="1d263-116">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="1d263-117">Basta baixar (via USB ou pelo Edge) o pacote Appx para o seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="1d263-117">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="1d263-118">Você também pode [iniciar uma instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="1d263-118">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="1d263-119">Assim como os aplicativos que você instala na Microsoft Store ou Sideload usando a funcionalidade de implantação do aplicativo LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiado](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de ser implantado.</span><span class="sxs-lookup"><span data-stu-id="1d263-119">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

**<span data-ttu-id="1d263-120">Instruções de instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1d263-120">Application install instructions.</span></span>**

1.  <span data-ttu-id="1d263-121">Certifique-se de que seu dispositivo não seja considerado gerenciado</span><span class="sxs-lookup"><span data-stu-id="1d263-121">Ensure that your device is not considered managed</span></span>
1.  <span data-ttu-id="1d263-122">Verifique se o seu dispositivo do HoloLens 2 está ligado e conectado ao computador</span><span class="sxs-lookup"><span data-stu-id="1d263-122">Ensure that your HoloLens 2 device is powered on and connected to your PC</span></span>
1.  <span data-ttu-id="1d263-123">Certifique-se de estar conectado ao dispositivo HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1d263-123">Ensure that you are signed into the HoloLens 2 device</span></span>
1.  <span data-ttu-id="1d263-124">No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="1d263-124">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>   <span data-ttu-id="1d263-125">Depois de terminar de copiar seu arquivo, você pode desconectar seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="1d263-125">After you’ve finished copying your file you can disconnect your device</span></span>
1.  <span data-ttu-id="1d263-126">Em seu dispositivo do HoloLens 2, abra o menu Iniciar, selecione todos os aplicativos e inicie o aplicativo explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1d263-126">From your HoloLens 2 device Open the Start Menu, select All apps and launch the File Explorer app.</span></span>
1.  <span data-ttu-id="1d263-127">Navegue até a pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="1d263-127">Navigate to the Downloads folder.</span></span> <span data-ttu-id="1d263-128">Talvez seja necessário no painel esquerdo do aplicativo Selecione este dispositivo primeiro e, em seguida, navegue até downloads.</span><span class="sxs-lookup"><span data-stu-id="1d263-128">You may need to on the left panel of the app select This device first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="1d263-129">Selecione o arquivo yourapp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="1d263-129">Select the yourapp.appxbundle file.</span></span>
1.  <span data-ttu-id="1d263-130">O instalador do aplicativo será iniciado.</span><span class="sxs-lookup"><span data-stu-id="1d263-130">The App Installer will launch.</span></span> <span data-ttu-id="1d263-131">Selecione o botão instalar para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1d263-131">Select the Install button to install your app.</span></span>
<span data-ttu-id="1d263-132">O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="1d263-132">The installed app will automatically launch upon completion of installation.</span></span>

<span data-ttu-id="1d263-133">Você pode encontrar aplicativos de exemplo no [GitHub de exemplos universais do Windows](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar esse fluxo.</span><span class="sxs-lookup"><span data-stu-id="1d263-133">You can find sample apps on [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) to test this flow.</span></span>

<span data-ttu-id="1d263-134">Leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o instalador do aplicativo](app-deploy-app-installer.md).</span><span class="sxs-lookup"><span data-stu-id="1d263-134">Read about the full process of [installing apps on HoloLens 2 with the App Installer](app-deploy-app-installer.md).</span></span>  

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

## <span data-ttu-id="1d263-136">Comece a receber Builds do insider</span><span class="sxs-lookup"><span data-stu-id="1d263-136">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="1d263-137">Se você não atualizou recentemente, reinicialize o seu dispositivo para atualizar o estado e obtenha a compilação mais recente.</span><span class="sxs-lookup"><span data-stu-id="1d263-137">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="1d263-138">O comando de voz "reinicializar dispositivo" funciona bem.</span><span class="sxs-lookup"><span data-stu-id="1d263-138">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="1d263-139">Você também pode escolher o botão de reinicialização no programa configurações/Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="1d263-139">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="1d263-140">Tivemos um bug no back-end que você pode ter encontrado e isso permitirá que você se retorne ao caminho.</span><span class="sxs-lookup"><span data-stu-id="1d263-140">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="1d263-141">Em um dispositivo HoloLens 2, vá para **configurações**  >  **Update &**  >  programa de segurança do**Windows Insider** e selecione **introdução**.</span><span class="sxs-lookup"><span data-stu-id="1d263-141">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="1d263-142">Vincule a conta que você usou para se registrar como um Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="1d263-142">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="1d263-143">O Windows Insider agora está migrando para canais.</span><span class="sxs-lookup"><span data-stu-id="1d263-143">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="1d263-144">O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta**, e o anel de **versão de pré-lançamento** se tornará o canal de visualização de **lançamento**.</span><span class="sxs-lookup"><span data-stu-id="1d263-144">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="1d263-145">Veja como é a aparência do mapeamento:</span><span class="sxs-lookup"><span data-stu-id="1d263-145">Here is what that mapping looks like:</span></span>

![Explicação de canais do Windows Insider](images/WindowsInsiderChannels.png)

<span data-ttu-id="1d263-147">Para obter mais informações, consulte [apresentando os canais do Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos Blogs do Windows.</span><span class="sxs-lookup"><span data-stu-id="1d263-147">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="1d263-148">Em seguida, selecione **desenvolvimento ativo do Windows**, escolha se deseja receber o **canal de dev** ou versões de **canal beta** e examine os termos do programa.</span><span class="sxs-lookup"><span data-stu-id="1d263-148">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="1d263-149">Selecione **confirmar > reiniciar agora** para concluir.</span><span class="sxs-lookup"><span data-stu-id="1d263-149">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="1d263-150">Após a reinicialização do seu dispositivo, vá para **configurações > atualização & segurança > verificar se há atualizações** para obter a compilação mais recente.</span><span class="sxs-lookup"><span data-stu-id="1d263-150">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="1d263-151">FFU de download e trajetos do flash</span><span class="sxs-lookup"><span data-stu-id="1d263-151">FFU download and flash directions</span></span>
<span data-ttu-id="1d263-152">Para testar com um FFU assinado no Flight, primeiro é preciso desbloquear o dispositivo antes de atualizar o FFU assinado no.</span><span class="sxs-lookup"><span data-stu-id="1d263-152">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="1d263-153">No PC:</span><span class="sxs-lookup"><span data-stu-id="1d263-153">On PC:</span></span>

    1. <span data-ttu-id="1d263-154">Faça o download do FFU para o seu PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="1d263-154">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="1d263-155">Instale o ARC (Advanced Recovery Companion) na Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="1d263-155">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="1d263-156">No HoloLens-bloqueio de voo: abrir **configurações**  >  **Atualizar & segurança**  >  **programa do Windows Insider** , em seguida, Inscreva-se, reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d263-156">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="1d263-157">Flash FFU-agora você pode fazer o flash do FFU assinado por meio do ARC.</span><span class="sxs-lookup"><span data-stu-id="1d263-157">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="1d263-158">Fornecer comentários e relatar problemas</span><span class="sxs-lookup"><span data-stu-id="1d263-158">Provide feedback and report issues</span></span>

<span data-ttu-id="1d263-159">Use [o aplicativo Hub de feedback](hololens-feedback.md) no seu HoloLens para fornecer comentários e relatar problemas.</span><span class="sxs-lookup"><span data-stu-id="1d263-159">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="1d263-160">Usar o Hub de feedback garante que todas as informações de diagnóstico necessárias estejam incluídas para ajudar nossos engenheiros a depurar e solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="1d263-160">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="1d263-161">Problemas com a versão em chinês e japonês do HoloLens devem ser reportados da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="1d263-161">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="1d263-162">Lembre-se de aceitar o prompt que pergunta se você deseja que o Hub de feedback acesse a pasta documentos (selecione **Sim** quando solicitado).</span><span class="sxs-lookup"><span data-stu-id="1d263-162">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="1d263-163">Observação para desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="1d263-163">Note for developers</span></span>

<span data-ttu-id="1d263-164">Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando as compilações do Insider do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d263-164">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="1d263-165">Confira a [documentação do desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar.</span><span class="sxs-lookup"><span data-stu-id="1d263-165">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="1d263-166">Essas mesmas instruções funcionam com compilações do Insider do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d263-166">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="1d263-167">Você pode usar as mesmas versões do Unity e do Visual Studio que já está usando para o desenvolvimento do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d263-167">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="1d263-168">Parar de receber compilações do insider</span><span class="sxs-lookup"><span data-stu-id="1d263-168">Stop receiving Insider builds</span></span>

<span data-ttu-id="1d263-169">Se você não quiser mais receber compilações do Insider do Windows holográfico, poderá cancelar quando o seu HoloLens está executando uma compilação de produção ou pode [recuperar seu dispositivo](hololens-recovery.md) usando o complemento avançado de recuperação para recuperar seu dispositivo para uma versão não Insider do Windows holográfico.</span><span class="sxs-lookup"><span data-stu-id="1d263-169">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="1d263-170">Há um problema conhecido em que os usuários que não se inscrevem em compilações do insider Preview após a reinstalação manual de uma nova versão prévia teria uma tela azul.</span><span class="sxs-lookup"><span data-stu-id="1d263-170">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="1d263-171">Depois disso, eles devem recuperar manualmente seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1d263-171">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="1d263-172">Para obter detalhes completos sobre se você for afetado ou não, veja mais sobre esse [problema conhecido](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span><span class="sxs-lookup"><span data-stu-id="1d263-172">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="1d263-173">Para verificar se o seu HoloLens está executando uma compilação de produção:</span><span class="sxs-lookup"><span data-stu-id="1d263-173">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="1d263-174">Vá para **configurações > > do sistema**e localize o número do Build.</span><span class="sxs-lookup"><span data-stu-id="1d263-174">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="1d263-175">[Consulte as notas de versão para números de Build de produção](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="1d263-175">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="1d263-176">Para recusar as compilações do insider:</span><span class="sxs-lookup"><span data-stu-id="1d263-176">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="1d263-177">Em um HoloLens executando uma compilação de produção, acesse **configurações > atualização & segurança > programa Windows Insider**e selecione **parar compilações**do Office Insider.</span><span class="sxs-lookup"><span data-stu-id="1d263-177">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="1d263-178">Siga as instruções para recusar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d263-178">Follow the instructions to opt out your device.</span></span>
