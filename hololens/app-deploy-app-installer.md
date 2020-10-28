---
title: Como carregar e instalar aplicativos pelo instalador do aplicativo HoloLens 2
description: Carregar e instalar aplicativos por meio da interface do usuário
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135522"
---
# <span data-ttu-id="345e4-104">Instalar aplicativos no HoloLens 2 via instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="345e4-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="345e4-105">No lançamento do Windows Insider, estamos **adicionando um novo recurso (instalador do aplicativo) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="345e4-105">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span>  <span data-ttu-id="345e4-106">Agora você pode instalar aplicativos sem precisar habilitar o modo de desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="345e4-106">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="345e4-107">Basta baixar (via USB ou pelo Edge) o pacote Appx para o seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="345e4-107">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="345e4-108">Você também pode [iniciar uma instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="345e4-108">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="345e4-109">Assim como os aplicativos que você instala na Microsoft Store ou Sideload usando a funcionalidade de implantação do aplicativo LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiado](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de ser implantado.</span><span class="sxs-lookup"><span data-stu-id="345e4-109">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

<span data-ttu-id="345e4-110">Esta atualização se alinha à área de trabalho em que o [Sideload está habilitado por padrão](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)</span><span class="sxs-lookup"><span data-stu-id="345e4-110">This update aligns with desktop where [Sideloading is Enabled by Default](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="345e4-111">No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="345e4-111">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="345e4-112">[Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="345e4-112">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="345e4-113">Para administradores de ti que desejam desabilitar esse recurso, use o nome da família de pacotes a seguir como parte da [política WDAC](windows-defender-application-control-wdac.md).</span><span class="sxs-lookup"><span data-stu-id="345e4-113">For IT Admins who wish to disable this feature please use the following package family name as part of your [WDAC policy](windows-defender-application-control-wdac.md).</span></span> <span data-ttu-id="345e4-114">Isso só bloqueará o aplicativo instalador de aplicativos, e não os aplicativos instalados de outras fontes, como a Microsoft Store ou da solução MDM.</span><span class="sxs-lookup"><span data-stu-id="345e4-114">This will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> <span data-ttu-id="345e4-115">É recomendável usar a [política WDAC](windows-defender-application-control-wdac.md) para controlar aplicativos, no entanto, se você quiser apenas permitir aplicativos da Microsoft Store, os dispositivos configurados para definir a política [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) explicitamente para "não permitir" só permitirão que os aplicativos sejam instalados na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="345e4-115">It is recommended to use [WDAC policy](windows-defender-application-control-wdac.md) to control apps, however if you only want to allow Microsoft Store apps, devices configured to set the [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) policy explicitly to “not allow” will only allow apps to be installed from the Microsoft Store.</span></span> 

## <span data-ttu-id="345e4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="345e4-116">Requirements</span></span>

### <span data-ttu-id="345e4-117">Para seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="345e4-117">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="345e4-118">No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="345e4-118">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="345e4-119">[Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="345e4-119">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="345e4-120">Para seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="345e4-120">For your apps:</span></span> 
<span data-ttu-id="345e4-121">A configuração da solução de seu aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja.</span><span class="sxs-lookup"><span data-stu-id="345e4-121">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="345e4-122">Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="345e4-122">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="345e4-123">Os aplicativos instalados por meio desse método devem ser assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="345e4-123">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="345e4-124">Você precisará usar um certificado para assinar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="345e4-124">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="345e4-125">Você pode obter um certificado da lista de [CAS confiáveis da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), caso em que você não precisará executar nenhuma ação adicional.</span><span class="sxs-lookup"><span data-stu-id="345e4-125">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="345e4-126">Ou você pode assinar seu próprio certificado, mas esse certificado precisará ser colocado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="345e4-126">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="345e4-127">Como assinar aplicativos [usando a ferramenta de assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="345e4-127">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="345e4-128">Opções de certificado:</span><span class="sxs-lookup"><span data-stu-id="345e4-128">Certificate options:</span></span>** 
- [<span data-ttu-id="345e4-129">Lista de CAS confiáveis da MS</span><span class="sxs-lookup"><span data-stu-id="345e4-129">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="345e4-130">Escolha um método de implantação de certificado.</span><span class="sxs-lookup"><span data-stu-id="345e4-130">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="345e4-131">Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="345e4-131">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="345e4-132">O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="345e4-132">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="345e4-133">Use o Gerenciador de [certificados](hololens-insider.md#certificate-manager)no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="345e4-133">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="345e4-134">Método de instalação</span><span class="sxs-lookup"><span data-stu-id="345e4-134">Installation method</span></span>

1.  <span data-ttu-id="345e4-135">Verifique se o seu dispositivo do HoloLens 2 está ligado e se você está conectado.</span><span class="sxs-lookup"><span data-stu-id="345e4-135">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="345e4-136">No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="345e4-136">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="345e4-137">Depois de concluir a cópia do seu arquivo, você pode desconectar seu dispositivo e concluir a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="345e4-137">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="345e4-138">Em seu dispositivo do HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="345e4-138">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="345e4-139">Navegue até a pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="345e4-139">Navigate to the Downloads folder.</span></span> <span data-ttu-id="345e4-140">Talvez seja necessário no painel esquerdo do aplicativo selecione **este dispositivo** primeiro e, em seguida, navegue até downloads.</span><span class="sxs-lookup"><span data-stu-id="345e4-140">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="345e4-141">Selecione o arquivo yourapp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="345e4-141">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="345e4-142">O instalador do aplicativo será iniciado.</span><span class="sxs-lookup"><span data-stu-id="345e4-142">The App Installer will launch.</span></span> <span data-ttu-id="345e4-143">Selecione o botão **instalar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="345e4-143">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="345e4-144">O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="345e4-144">The installed app will automatically launch upon the completion of installing.</span></span> 

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="345e4-146">Solução de problemas de instalação</span><span class="sxs-lookup"><span data-stu-id="345e4-146">Troubleshooting Installs</span></span>
<span data-ttu-id="345e4-147">Se o aplicativo não tiver sido instalado, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="345e4-147">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="345e4-148">Seu aplicativo é uma compilação mestre ou de versão.</span><span class="sxs-lookup"><span data-stu-id="345e4-148">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="345e4-149">Seu dispositivo é atualizado para uma compilação em que esse recurso está disponível.</span><span class="sxs-lookup"><span data-stu-id="345e4-149">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="345e4-150">Você está [conectado à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="345e4-150">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="345e4-151">Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="345e4-151">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="345e4-152">Instalador da Web</span><span class="sxs-lookup"><span data-stu-id="345e4-152">Web Installer</span></span>

<span data-ttu-id="345e4-153">Os usuários podem instalar um aplicativo diretamente de um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="345e4-153">Users can install an app directly from a web server.</span></span> <span data-ttu-id="345e4-154">Isso usa o instalador do aplicativo combinado com um método fácil de distribuição de download e instalação.</span><span class="sxs-lookup"><span data-stu-id="345e4-154">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="345e4-155">Como configurar a instalação da Web:</span><span class="sxs-lookup"><span data-stu-id="345e4-155">How to set up web install:</span></span>
1.  <span data-ttu-id="345e4-156">Verifique se o aplicativo está configurado corretamente para a instalação.</span><span class="sxs-lookup"><span data-stu-id="345e4-156">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="345e4-157">Siga estas [etapas para habilitar isso em uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="345e4-157">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="345e4-158">Experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="345e4-158">End user experience:</span></span>
1. <span data-ttu-id="345e4-159">O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima.</span><span class="sxs-lookup"><span data-stu-id="345e4-159">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="345e4-160">O usuário visita a URL criada a partir da etapa acima.</span><span class="sxs-lookup"><span data-stu-id="345e4-160">User visits the URL created from the step above.</span></span>

<span data-ttu-id="345e4-161">O aplicativo agora será instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="345e4-161">The app will now install to the device.</span></span> <span data-ttu-id="345e4-162">Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="345e4-162">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="345e4-163">Para ajudar a solucionar problemas com esse método de instalação, acesse [solucionar](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)problemas do instalador do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="345e4-163">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="345e4-164">Não há suporte para a interface do usuário durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="345e4-164">UI during the update process is not supported.</span></span> <span data-ttu-id="345e4-165">Portanto, não há suporte para a opção não receber [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e opções relacionadas.</span><span class="sxs-lookup"><span data-stu-id="345e4-165">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="345e4-166">Exemplos de aplicativos</span><span class="sxs-lookup"><span data-stu-id="345e4-166">Sample Apps</span></span>

<span data-ttu-id="345e4-167">Se quiser experimentar alguns exemplos de aplicativos, confira alguns dos exemplos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="345e4-167">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="345e4-168">Hub de exemplos MRTK</span><span class="sxs-lookup"><span data-stu-id="345e4-168">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="345e4-169">Produz</span><span class="sxs-lookup"><span data-stu-id="345e4-169">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="345e4-170">Exemplos de aplicativos UWP que podem ser usados para teste</span><span class="sxs-lookup"><span data-stu-id="345e4-170">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
