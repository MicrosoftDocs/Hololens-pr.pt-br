---
title: Como fazer side load e instalar aplicativos por meio do Instalador de Aplicativos do HoloLens 2
description: Saiba como instalar e solucionar problemas de aplicativos com o instalador do aplicativo e a carga lateral e instalar aplicativos por meio da interface do usuário.
keywords: gerenciamento de aplicativos, aplicativo, hololens, instalador de aplicativo
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
ms.openlocfilehash: 89f48fab236fdaf58fb0bf8b29e5a3aacb3bdee3
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283732"
---
# <span data-ttu-id="683a6-104">Instalar aplicativos no HoloLens 2 por meio do Instalador de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="683a6-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="683a6-105">Esse recurso foi disponibilizado no [Windows Holographic, versão 20H2 – atualização de dezembro de 2020.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="683a6-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="683a6-106">Certifique-se de que [seu dispositivo seja](hololens-update-hololens.md) atualizado para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="683a6-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="683a6-107">Adicionamos **um novo recurso (Instalador** de Aplicativo) para permitir que você instale aplicativos mais facilmente em seus dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="683a6-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="683a6-108">O recurso estará **conectado por padrão para dispositivos não-manageados.**</span><span class="sxs-lookup"><span data-stu-id="683a6-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="683a6-109">Para evitar a interrupção nas empresas, o instalador de aplicativo **não estará disponível para dispositivos gerenciados** no momento.</span><span class="sxs-lookup"><span data-stu-id="683a6-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="683a6-110">Um dispositivo é considerado "gerenciado" **se qualquer** um dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="683a6-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="683a6-111">MDM [inscrito](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="683a6-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="683a6-112">Configurado com o [pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="683a6-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="683a6-113">A [identidade do](hololens-identity.md) usuário é o Azure AD</span><span class="sxs-lookup"><span data-stu-id="683a6-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="683a6-114">Agora você pode instalar aplicativos sem precisar habilitar o Modo de Desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="683a6-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="683a6-115">Baixe (por USB ou por meio do Microsoft Edge) o Appx Bundle para seu dispositivo e navegue até o Pacote Appx no Explorador de Arquivos para ser solicitado a dar início à instalação.</span><span class="sxs-lookup"><span data-stu-id="683a6-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="683a6-116">Como alternativa, [inicie uma instalação a partir de uma página da Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="683a6-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="683a6-117">Assim como os aplicativos instalados da Microsoft Store ou sideload usando o recurso de implantação [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) do aplicativo [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) LOB do MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Assinatura e o certificado usado para assinar deve ser confiável para o dispositivo HoloLens antes que o aplicativo possa ser implantado.</span><span class="sxs-lookup"><span data-stu-id="683a6-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="683a6-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="683a6-118">Requirements</span></span>

### <span data-ttu-id="683a6-119">Para seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="683a6-119">For your devices:</span></span>

 <span data-ttu-id="683a6-120">está atualmente disponível em builds do Windows Holographic 20H2 para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="683a6-120">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="683a6-121">Certifique-se de que todos os dispositivos que usam esse método sejam [atualizados.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="683a6-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="683a6-122">Para seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="683a6-122">For your apps:</span></span> 
<span data-ttu-id="683a6-123">A Configuração da Solução do \*\*\*\* aplicativo deve ser **Mestre** ou Versão, pois o Instalador de Aplicativo usará dependências da loja.</span><span class="sxs-lookup"><span data-stu-id="683a6-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="683a6-124">Veja mais sobre [como criar pacotes de aplicativos.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="683a6-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="683a6-125">Os aplicativos instalados por meio desse método devem ser assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="683a6-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="683a6-126">Você precisará usar um certificado para assinar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="683a6-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="683a6-127">Você pode obter um certificado da lista de CA confiáveis do [MS.](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)Nesse caso, não será necessário tomar nenhuma ação extra.</span><span class="sxs-lookup"><span data-stu-id="683a6-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="683a6-128">Ou você pode assinar seu próprio certificado, no entanto, esse certificado precisará ser emitido para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="683a6-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="683a6-129">Como assinar [aplicativos usando a Ferramenta de Assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="683a6-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="683a6-130">Opções de certificado:</span><span class="sxs-lookup"><span data-stu-id="683a6-130">Certificate options:</span></span>**

- [<span data-ttu-id="683a6-131">Lista de CA confiáveis do MS</span><span class="sxs-lookup"><span data-stu-id="683a6-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="683a6-132">Escolha um método de implantação de certificado.</span><span class="sxs-lookup"><span data-stu-id="683a6-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="683a6-133">[Os Pacotes de Provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="683a6-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="683a6-134">O MDM pode ser usado para [aplicar certificados com configurações de dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="683a6-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="683a6-135">Use o Gerenciador de [Certificados no dispositivo.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="683a6-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="683a6-136">Método de instalação</span><span class="sxs-lookup"><span data-stu-id="683a6-136">Installation method</span></span>

1. <span data-ttu-id="683a6-137">Verifique se o dispositivo não é considerado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="683a6-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="683a6-138">Verifique se o dispositivo HoloLens 2 está ligado e se você está conectado.</span><span class="sxs-lookup"><span data-stu-id="683a6-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="683a6-139">Em seu computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="683a6-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="683a6-140">Depois de terminar de copiar o arquivo, você poderá desconectar o dispositivo e concluir a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="683a6-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="683a6-141">No dispositivo HoloLens 2, abra o **Menu Iniciar,** selecione **Todos os** aplicativos e inicie o aplicativo **Explorador de** Arquivos.</span><span class="sxs-lookup"><span data-stu-id="683a6-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="683a6-142">Navegue até a pasta Downloads.</span><span class="sxs-lookup"><span data-stu-id="683a6-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="683a6-143">Talvez seja necessário que, no painel esquerdo do aplicativo, selecione **Este** dispositivo primeiro e, em seguida, navegue até Downloads.</span><span class="sxs-lookup"><span data-stu-id="683a6-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="683a6-144">Selecione o arquivo yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="683a6-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="683a6-145">O Instalador de Aplicativo será lançado.</span><span class="sxs-lookup"><span data-stu-id="683a6-145">The App Installer will launch.</span></span> <span data-ttu-id="683a6-146">Selecione o **botão Instalar** para instalar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="683a6-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="683a6-147">O aplicativo instalado será automaticamente lançado após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="683a6-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalando exemplos de MRTK por meio do Instalador de Aplicativo](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="683a6-149">Solução de problemas de instalação</span><span class="sxs-lookup"><span data-stu-id="683a6-149">Troubleshooting Installs</span></span>

<span data-ttu-id="683a6-150">Se o aplicativo não tiver êxito na instalação, verifique o seguinte para solucionar problemas:</span><span class="sxs-lookup"><span data-stu-id="683a6-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="683a6-151">Seu aplicativo é uma complicação Master ou Release.</span><span class="sxs-lookup"><span data-stu-id="683a6-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="683a6-152">Seu dispositivo é atualizado para um build no qual esse recurso está disponível.</span><span class="sxs-lookup"><span data-stu-id="683a6-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="683a6-153">Você está [conectado à Internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="683a6-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="683a6-154">Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="683a6-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="683a6-155">Instalador da Web</span><span class="sxs-lookup"><span data-stu-id="683a6-155">Web Installer</span></span>

<span data-ttu-id="683a6-156">Os usuários podem instalar um aplicativo diretamente de um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="683a6-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="683a6-157">Esse fluxo usa o Instalador de Aplicativo combinado com um método de distribuição fácil de baixar e instalar.</span><span class="sxs-lookup"><span data-stu-id="683a6-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="683a6-158">Como configurar a instalação da Web:</span><span class="sxs-lookup"><span data-stu-id="683a6-158">How to set up web install:</span></span>

1. <span data-ttu-id="683a6-159">Certifique-se de que seu aplicativo está configurado corretamente para instalação.</span><span class="sxs-lookup"><span data-stu-id="683a6-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="683a6-160">Siga estas [etapas para habilitar a instalação a partir de uma página da Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="683a6-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="683a6-161">Experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="683a6-161">End user experience:</span></span>

1. <span data-ttu-id="683a6-162">O usuário recebe e instala o certificado no dispositivo usando um método escolhido anteriormente acima.</span><span class="sxs-lookup"><span data-stu-id="683a6-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="683a6-163">O usuário visita a URL criada na etapa acima.</span><span class="sxs-lookup"><span data-stu-id="683a6-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="683a6-164">O aplicativo agora será instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="683a6-164">The app will now install to the device.</span></span> <span data-ttu-id="683a6-165">Para encontrar o aplicativo, abra o **menu Iniciar** e selecione o botão Todos os **aplicativos** para encontrar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="683a6-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="683a6-166">Para obter mais ajuda com a solução de problemas do método de instalação do instalador de aplicativo, visite [solucionar problemas do instalador de aplicativo.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="683a6-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="683a6-167">A interface do usuário durante o processo de atualização não é suportada.</span><span class="sxs-lookup"><span data-stu-id="683a6-167">UI during the update process is not supported.</span></span> <span data-ttu-id="683a6-168">Portanto, a opção ShowPrompt [nesta página e](https://docs.microsoft.com/windows/msix/app-installer/update-settings) as opções relacionadas não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="683a6-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="683a6-169">Aplicativos de exemplo</span><span class="sxs-lookup"><span data-stu-id="683a6-169">Sample Apps</span></span>

<span data-ttu-id="683a6-170">Para testar o Instalador de Aplicativo com alguns aplicativos de exemplo, confira alguns dos nossos exemplos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="683a6-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="683a6-171">Hub de Exemplos de MRTK</span><span class="sxs-lookup"><span data-stu-id="683a6-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="683a6-172">Superfícies</span><span class="sxs-lookup"><span data-stu-id="683a6-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="683a6-173">Aplicativos de exemplo UWP que podem ser usados para teste</span><span class="sxs-lookup"><span data-stu-id="683a6-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
