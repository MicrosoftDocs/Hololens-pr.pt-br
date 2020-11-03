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
ms.openlocfilehash: 415733bb2809b7ae2808edc097423f8928910c57
ms.sourcegitcommit: c4fd9a87bb7c728c73418f95a1b15dd93b0af7c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "11150912"
---
# <span data-ttu-id="35c94-104">Instalar aplicativos no HoloLens 2 via instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="35c94-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35c94-105">No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="35c94-105">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="35c94-106">[Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="35c94-106">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="35c94-107">No lançamento do Windows Insider, estamos **adicionando um novo recurso (instalador do aplicativo) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="35c94-107">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="35c94-108">O recurso estará **ativado por padrão para dispositivos não gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="35c94-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="35c94-109">Para evitar interrupções em empresas, o instalador do aplicativo **não estará disponível para dispositivos gerenciados** no momento.</span><span class="sxs-lookup"><span data-stu-id="35c94-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="35c94-110">Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="35c94-110">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="35c94-111">MDM [registrado](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="35c94-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="35c94-112">Configurado com o [pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="35c94-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="35c94-113">A [identidade](hololens-identity.md) do usuário é AAD</span><span class="sxs-lookup"><span data-stu-id="35c94-113">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="35c94-114">Agora você pode instalar aplicativos sem precisar habilitar o modo de desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="35c94-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="35c94-115">Basta baixar (via USB ou pelo Edge) o pacote Appx para o seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="35c94-115">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="35c94-116">Você também pode [iniciar uma instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="35c94-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="35c94-117">Assim como os aplicativos que você instala na Microsoft Store ou Sideload usando a funcionalidade de implantação do aplicativo LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiado](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de ser implantado.</span><span class="sxs-lookup"><span data-stu-id="35c94-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="35c94-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35c94-118">Requirements</span></span>

### <span data-ttu-id="35c94-119">Para seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="35c94-119">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="35c94-120">No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +.</span><span class="sxs-lookup"><span data-stu-id="35c94-120">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="35c94-121">[Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="35c94-121">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="35c94-122">Para seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="35c94-122">For your apps:</span></span> 
<span data-ttu-id="35c94-123">A configuração da solução de seu aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja.</span><span class="sxs-lookup"><span data-stu-id="35c94-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="35c94-124">Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="35c94-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="35c94-125">Os aplicativos instalados por meio desse método devem ser assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="35c94-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="35c94-126">Você precisará usar um certificado para assinar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="35c94-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="35c94-127">Você pode obter um certificado da lista de [CAS confiáveis da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), caso em que você não precisará executar nenhuma ação adicional.</span><span class="sxs-lookup"><span data-stu-id="35c94-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="35c94-128">Ou você pode assinar seu próprio certificado, mas esse certificado precisará ser colocado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35c94-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="35c94-129">Como assinar aplicativos [usando a ferramenta de assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="35c94-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="35c94-130">Opções de certificado:</span><span class="sxs-lookup"><span data-stu-id="35c94-130">Certificate options:</span></span>** 
- [<span data-ttu-id="35c94-131">Lista de CAS confiáveis da MS</span><span class="sxs-lookup"><span data-stu-id="35c94-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="35c94-132">Escolha um método de implantação de certificado.</span><span class="sxs-lookup"><span data-stu-id="35c94-132">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="35c94-133">Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="35c94-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="35c94-134">O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="35c94-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="35c94-135">Use o Gerenciador de [certificados](hololens-insider.md#certificate-manager)no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35c94-135">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="35c94-136">Método de instalação</span><span class="sxs-lookup"><span data-stu-id="35c94-136">Installation method</span></span>

1.  <span data-ttu-id="35c94-137">Certifique-se de que seu dispositivo não seja considerado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="35c94-137">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="35c94-138">Verifique se o seu dispositivo do HoloLens 2 está ligado e se você está conectado.</span><span class="sxs-lookup"><span data-stu-id="35c94-138">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="35c94-139">No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="35c94-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="35c94-140">Depois de concluir a cópia do seu arquivo, você pode desconectar seu dispositivo e concluir a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="35c94-140">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="35c94-141">Em seu dispositivo do HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="35c94-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="35c94-142">Navegue até a pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="35c94-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="35c94-143">Talvez seja necessário no painel esquerdo do aplicativo selecione **este dispositivo** primeiro e, em seguida, navegue até downloads.</span><span class="sxs-lookup"><span data-stu-id="35c94-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="35c94-144">Selecione o arquivo yourapp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="35c94-144">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="35c94-145">O instalador do aplicativo será iniciado.</span><span class="sxs-lookup"><span data-stu-id="35c94-145">The App Installer will launch.</span></span> <span data-ttu-id="35c94-146">Selecione o botão **instalar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="35c94-146">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="35c94-147">O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="35c94-147">The installed app will automatically launch upon the completion of installing.</span></span> 

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="35c94-149">Solução de problemas de instalação</span><span class="sxs-lookup"><span data-stu-id="35c94-149">Troubleshooting Installs</span></span>
<span data-ttu-id="35c94-150">Se o aplicativo não tiver sido instalado, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="35c94-150">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="35c94-151">Seu aplicativo é uma compilação mestre ou de versão.</span><span class="sxs-lookup"><span data-stu-id="35c94-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="35c94-152">Seu dispositivo é atualizado para uma compilação em que esse recurso está disponível.</span><span class="sxs-lookup"><span data-stu-id="35c94-152">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="35c94-153">Você está [conectado à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="35c94-153">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="35c94-154">Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="35c94-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="35c94-155">Instalador da Web</span><span class="sxs-lookup"><span data-stu-id="35c94-155">Web Installer</span></span>

<span data-ttu-id="35c94-156">Os usuários podem instalar um aplicativo diretamente de um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="35c94-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="35c94-157">Isso usa o instalador do aplicativo combinado com um método fácil de distribuição de download e instalação.</span><span class="sxs-lookup"><span data-stu-id="35c94-157">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="35c94-158">Como configurar a instalação da Web:</span><span class="sxs-lookup"><span data-stu-id="35c94-158">How to set up web install:</span></span>
1.  <span data-ttu-id="35c94-159">Verifique se o aplicativo está configurado corretamente para a instalação.</span><span class="sxs-lookup"><span data-stu-id="35c94-159">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="35c94-160">Siga estas [etapas para habilitar isso em uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="35c94-160">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="35c94-161">Experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="35c94-161">End user experience:</span></span>
1. <span data-ttu-id="35c94-162">O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima.</span><span class="sxs-lookup"><span data-stu-id="35c94-162">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="35c94-163">O usuário visita a URL criada a partir da etapa acima.</span><span class="sxs-lookup"><span data-stu-id="35c94-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="35c94-164">O aplicativo agora será instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35c94-164">The app will now install to the device.</span></span> <span data-ttu-id="35c94-165">Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="35c94-165">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="35c94-166">Para ajudar a solucionar problemas com esse método de instalação, acesse [solucionar](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)problemas do instalador do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="35c94-166">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="35c94-167">Não há suporte para a interface do usuário durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="35c94-167">UI during the update process is not supported.</span></span> <span data-ttu-id="35c94-168">Portanto, não há suporte para a opção não receber [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e opções relacionadas.</span><span class="sxs-lookup"><span data-stu-id="35c94-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="35c94-169">Exemplos de aplicativos</span><span class="sxs-lookup"><span data-stu-id="35c94-169">Sample Apps</span></span>

<span data-ttu-id="35c94-170">Se quiser experimentar alguns exemplos de aplicativos, confira alguns dos exemplos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="35c94-170">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="35c94-171">Hub de exemplos MRTK</span><span class="sxs-lookup"><span data-stu-id="35c94-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="35c94-172">Produz</span><span class="sxs-lookup"><span data-stu-id="35c94-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="35c94-173">Exemplos de aplicativos UWP que podem ser usados para teste</span><span class="sxs-lookup"><span data-stu-id="35c94-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
