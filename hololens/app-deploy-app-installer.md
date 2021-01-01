---
title: Como carregar e instalar aplicativos pelo instalador do aplicativo HoloLens 2
description: Carregar e instalar aplicativos por meio da interface do usuário
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253088"
---
# <span data-ttu-id="0d510-104">Instalar aplicativos no HoloLens 2 via instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0d510-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="0d510-105">Estamos **adicionando uma nova funcionalidade (instalador de aplicativos) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0d510-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="0d510-106">O recurso estará **ativado por padrão para dispositivos não gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="0d510-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="0d510-107">Para evitar interrupções em empresas, o instalador **de aplicativos não estará disponível para dispositivos gerenciados** no momento.</span><span class="sxs-lookup"><span data-stu-id="0d510-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="0d510-108">Esse recurso foi disponibilizado no [Windows holográfico, versão 20H2 – atualização de dezembro de 2020](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="0d510-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="0d510-109">Verifique se o seu dispositivo está [atualizado](hololens-update-hololens.md) para usar este recurso.</span><span class="sxs-lookup"><span data-stu-id="0d510-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="0d510-110">**Adicionamos um novo recurso (instalador de aplicativos) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0d510-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="0d510-111">O recurso estará **ativado por padrão para dispositivos não gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="0d510-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="0d510-112">Para evitar interrupções em empresas, o instalador do aplicativo **não estará disponível para dispositivos gerenciados** no momento.</span><span class="sxs-lookup"><span data-stu-id="0d510-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="0d510-113">Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="0d510-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="0d510-114">MDM [registrado](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="0d510-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="0d510-115">Configurado com o [pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="0d510-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="0d510-116">A [identidade](hololens-identity.md) do usuário é o Azure AD</span><span class="sxs-lookup"><span data-stu-id="0d510-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="0d510-117">Agora você pode instalar aplicativos sem precisar habilitar o modo de desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="0d510-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="0d510-118">Baixe (em USB ou pelo Microsoft Edge) o pacote Appx para o seu dispositivo e navegue até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="0d510-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="0d510-119">Você também pode [iniciar uma instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="0d510-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="0d510-120">Assim como os aplicativos que você instala na Microsoft Store ou Sideload usando a funcionalidade de implantação do aplicativo LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiado](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de ser implantado.</span><span class="sxs-lookup"><span data-stu-id="0d510-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="0d510-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d510-121">Requirements</span></span>

### <span data-ttu-id="0d510-122">Para seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="0d510-122">For your devices:</span></span>

 <span data-ttu-id="0d510-123">no momento, o recurso está disponível no Windows holográfico 20H2 compila para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0d510-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="0d510-124">Verifique se todos os dispositivos que usam esse método são [atualizados](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="0d510-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="0d510-125">Para seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="0d510-125">For your apps:</span></span> 
<span data-ttu-id="0d510-126">A configuração da solução de seu aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja.</span><span class="sxs-lookup"><span data-stu-id="0d510-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="0d510-127">Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="0d510-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="0d510-128">Os aplicativos instalados por meio desse método devem ser assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="0d510-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="0d510-129">Você precisará usar um certificado para assinar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d510-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="0d510-130">Você pode obter um certificado da lista de [CAS confiáveis da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), caso em que você não precisará executar nenhuma ação adicional.</span><span class="sxs-lookup"><span data-stu-id="0d510-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="0d510-131">Ou você pode assinar seu próprio certificado, mas esse certificado precisará ser colocado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d510-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="0d510-132">Como assinar aplicativos [usando a ferramenta de assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="0d510-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="0d510-133">Opções de certificado:</span><span class="sxs-lookup"><span data-stu-id="0d510-133">Certificate options:</span></span>**

- [<span data-ttu-id="0d510-134">Lista de CAS confiáveis da MS</span><span class="sxs-lookup"><span data-stu-id="0d510-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="0d510-135">Escolha um método de implantação de certificado.</span><span class="sxs-lookup"><span data-stu-id="0d510-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="0d510-136">Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="0d510-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="0d510-137">O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="0d510-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="0d510-138">Use o Gerenciador de [certificados](certificate-manager.md)no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d510-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="0d510-139">Método de instalação</span><span class="sxs-lookup"><span data-stu-id="0d510-139">Installation method</span></span>

1. <span data-ttu-id="0d510-140">Verifique se o seu dispositivo não é considerado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="0d510-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="0d510-141">Verifique se o seu dispositivo do HoloLens 2 está ligado e se você está conectado.</span><span class="sxs-lookup"><span data-stu-id="0d510-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="0d510-142">No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="0d510-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="0d510-143">Depois de terminar de copiar o arquivo, você pode desconectar o dispositivo e concluir a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="0d510-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="0d510-144">Em seu dispositivo do HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="0d510-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="0d510-145">Navegue até a pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="0d510-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="0d510-146">Talvez seja necessário no painel esquerdo do aplicativo selecione **este dispositivo** primeiro e, em seguida, navegue até downloads.</span><span class="sxs-lookup"><span data-stu-id="0d510-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="0d510-147">Selecione o arquivo yourapp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="0d510-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="0d510-148">O instalador do aplicativo será iniciado.</span><span class="sxs-lookup"><span data-stu-id="0d510-148">The App Installer will launch.</span></span> <span data-ttu-id="0d510-149">Selecione o botão **instalar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d510-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="0d510-150">O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="0d510-150">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="0d510-152">Solução de problemas de instalação</span><span class="sxs-lookup"><span data-stu-id="0d510-152">Troubleshooting Installs</span></span>

<span data-ttu-id="0d510-153">Se o aplicativo não tiver sido instalado, verifique o seguinte para solucionar o problema:</span><span class="sxs-lookup"><span data-stu-id="0d510-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="0d510-154">Seu aplicativo é uma compilação mestre ou de versão.</span><span class="sxs-lookup"><span data-stu-id="0d510-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="0d510-155">Seu dispositivo é atualizado para uma compilação em que esse recurso está disponível.</span><span class="sxs-lookup"><span data-stu-id="0d510-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="0d510-156">Você está [conectado à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="0d510-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="0d510-157">Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="0d510-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="0d510-158">Instalador da Web</span><span class="sxs-lookup"><span data-stu-id="0d510-158">Web Installer</span></span>

<span data-ttu-id="0d510-159">Os usuários podem instalar um aplicativo diretamente de um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="0d510-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="0d510-160">Esse fluxo usa o instalador do aplicativo combinado com um método fácil de distribuição de download e instalação.</span><span class="sxs-lookup"><span data-stu-id="0d510-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="0d510-161">Como configurar a instalação da Web:</span><span class="sxs-lookup"><span data-stu-id="0d510-161">How to set up web install:</span></span>

1. <span data-ttu-id="0d510-162">Verifique se o aplicativo está configurado corretamente para a instalação.</span><span class="sxs-lookup"><span data-stu-id="0d510-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="0d510-163">Siga estas [etapas para habilitar a instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="0d510-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="0d510-164">Experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="0d510-164">End user experience:</span></span>

1. <span data-ttu-id="0d510-165">O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima.</span><span class="sxs-lookup"><span data-stu-id="0d510-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="0d510-166">O usuário visita a URL criada a partir da etapa acima.</span><span class="sxs-lookup"><span data-stu-id="0d510-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="0d510-167">O aplicativo agora será instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d510-167">The app will now install to the device.</span></span> <span data-ttu-id="0d510-168">Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d510-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="0d510-169">Para obter mais ajuda com a solução de problemas com o método de instalação do instalador de aplicativos, acesse problemas do [instalador do aplicativo](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="0d510-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="0d510-170">Não há suporte para a interface do usuário durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="0d510-170">UI during the update process is not supported.</span></span> <span data-ttu-id="0d510-171">Portanto, não há suporte para a opção não receber [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e opções relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0d510-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="0d510-172">Exemplos de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0d510-172">Sample Apps</span></span>

<span data-ttu-id="0d510-173">Para experimentar o instalador do aplicativo com alguns exemplos de aplicativos, confira alguns dos exemplos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0d510-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="0d510-174">Hub de exemplos MRTK</span><span class="sxs-lookup"><span data-stu-id="0d510-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="0d510-175">Produz</span><span class="sxs-lookup"><span data-stu-id="0d510-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="0d510-176">Exemplos de aplicativos UWP que podem ser usados para teste</span><span class="sxs-lookup"><span data-stu-id="0d510-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
