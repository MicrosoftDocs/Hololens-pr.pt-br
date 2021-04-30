---
title: Como carregar e instalar aplicativos por meio do instalador de aplicativo do HoloLens 2
description: Saiba como instalar e solucionar problemas de aplicativos com o instalador do aplicativo e a carga do lado e instalar aplicativos por meio da interface do usuário.
keywords: gerenciamento de aplicativo, aplicativo, hololens, instalador de aplicativo
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308081"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="881e1-104">Instalar aplicativos no HoloLens 2 por meio do instalador de aplicativo</span><span class="sxs-lookup"><span data-stu-id="881e1-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="881e1-105">Esse recurso foi disponibilizado no [Windows Holographic, versão 20H2 – atualização de dezembro de 2020](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="881e1-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="881e1-106">Verifique se o dispositivo está [atualizado](hololens-update-hololens.md) para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="881e1-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="881e1-107">**Adicionamos um novo recurso (instalador de aplicativo) para permitir que você instale aplicativos com mais perfeição** em seus dispositivos de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="881e1-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="881e1-108">O recurso estará **ativado por padrão para dispositivos não gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="881e1-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="881e1-109">Para evitar a interrupção para as empresas, o instalador **de aplicativos não estará disponível para dispositivos gerenciados** no momento.</span><span class="sxs-lookup"><span data-stu-id="881e1-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="881e1-110">Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="881e1-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="881e1-111">MDM [registrado](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="881e1-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="881e1-112">Configurado com [pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="881e1-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="881e1-113">A [identidade](hololens-identity.md) do usuário é Azure AD</span><span class="sxs-lookup"><span data-stu-id="881e1-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="881e1-114">Agora você pode instalar aplicativos sem a necessidade de habilitar o modo de desenvolvedor ou usar o portal do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="881e1-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="881e1-115">Baixe (via USB ou por meio do Microsoft Edge) o pacote Appx em seu dispositivo e navegue até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="881e1-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="881e1-116">Como alternativa, [inicie uma instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="881e1-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="881e1-117">Assim como os aplicativos que você instala do Microsoft Store ou Sideload usando o recurso de implantação de aplicativo de LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiável](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo de HoloLens antes que o aplicativo possa ser implantado.</span><span class="sxs-lookup"><span data-stu-id="881e1-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="881e1-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="881e1-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="881e1-119">Para seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="881e1-119">For your devices:</span></span>

<span data-ttu-id="881e1-120">Esse recurso está disponível no momento no Windows Holographic 20H2 Builds para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="881e1-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="881e1-121">Certifique-se de que todos os dispositivos que usam esse método sejam [atualizados](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="881e1-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="881e1-122">Para seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="881e1-122">For your apps:</span></span>

<span data-ttu-id="881e1-123">A configuração da solução do aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja.</span><span class="sxs-lookup"><span data-stu-id="881e1-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="881e1-124">Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="881e1-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="881e1-125">Os aplicativos instalados por meio desse método devem ser assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="881e1-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="881e1-126">Você precisará usar um certificado para assinar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="881e1-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="881e1-127">Você pode obter um certificado da lista de [AC confiável da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), caso em que você não precisará realizar nenhuma ação extra.</span><span class="sxs-lookup"><span data-stu-id="881e1-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="881e1-128">Ou você pode assinar seu próprio certificado, no entanto, o certificado precisará ser enviado por push para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="881e1-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="881e1-129">Como assinar aplicativos [usando a ferramenta de assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="881e1-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="881e1-130">**Opções de certificado:**</span><span class="sxs-lookup"><span data-stu-id="881e1-130">**Certificate options:**</span></span>

- [<span data-ttu-id="881e1-131">Lista de AC confiável da MS</span><span class="sxs-lookup"><span data-stu-id="881e1-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="881e1-132">**Escolha um método de implantação de certificado.**</span><span class="sxs-lookup"><span data-stu-id="881e1-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="881e1-133">Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="881e1-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="881e1-134">O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="881e1-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="881e1-135">Use o no [Gerenciador de certificados](certificate-manager.md)do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="881e1-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="881e1-136">Método de instalação</span><span class="sxs-lookup"><span data-stu-id="881e1-136">Installation method</span></span>

1. <span data-ttu-id="881e1-137">Verifique se o dispositivo não é considerado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="881e1-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="881e1-138">Verifique se o dispositivo do HoloLens 2 está ligado e se você está conectado.</span><span class="sxs-lookup"><span data-stu-id="881e1-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="881e1-139">Em seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="881e1-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="881e1-140">Depois de terminar de copiar o arquivo, você pode desconectar o dispositivo e concluir a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="881e1-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="881e1-141">Em seu dispositivo de HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="881e1-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="881e1-142">Navegue até a pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="881e1-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="881e1-143">Talvez seja necessário no painel esquerdo do aplicativo selecione primeiro **este dispositivo** e, em seguida, navegue até downloads.</span><span class="sxs-lookup"><span data-stu-id="881e1-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="881e1-144">Selecione o arquivo yourapp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="881e1-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="881e1-145">O instalador do aplicativo será iniciado.</span><span class="sxs-lookup"><span data-stu-id="881e1-145">The App Installer will launch.</span></span> <span data-ttu-id="881e1-146">Selecione o botão **instalar** para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="881e1-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="881e1-147">O aplicativo instalado será iniciado automaticamente após a conclusão da instalação do.</span><span class="sxs-lookup"><span data-stu-id="881e1-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalando exemplos do MRTK por meio do instalador do aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="881e1-149">Solução de problemas de instalações</span><span class="sxs-lookup"><span data-stu-id="881e1-149">Troubleshooting Installs</span></span>

<span data-ttu-id="881e1-150">Se o aplicativo não for instalado, verifique o seguinte para solucionar o problema:</span><span class="sxs-lookup"><span data-stu-id="881e1-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="881e1-151">Seu aplicativo é um Build mestre ou de versão.</span><span class="sxs-lookup"><span data-stu-id="881e1-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="881e1-152">Seu dispositivo é atualizado para uma compilação em que esse recurso está disponível.</span><span class="sxs-lookup"><span data-stu-id="881e1-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="881e1-153">Você está [conectado à Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="881e1-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="881e1-154">Seus [pontos de extremidade para o Microsoft Store](hololens-offline.md) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="881e1-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="881e1-155">Instalador da Web</span><span class="sxs-lookup"><span data-stu-id="881e1-155">Web Installer</span></span>

<span data-ttu-id="881e1-156">Os usuários podem instalar um aplicativo diretamente de um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="881e1-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="881e1-157">Esse fluxo usa o instalador do aplicativo combinado com um método de distribuição fácil de baixar e instalar.</span><span class="sxs-lookup"><span data-stu-id="881e1-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="881e1-158">Como configurar a instalação da Web:</span><span class="sxs-lookup"><span data-stu-id="881e1-158">How to set up web install:</span></span>

1. <span data-ttu-id="881e1-159">Verifique se seu aplicativo está configurado corretamente para instalação.</span><span class="sxs-lookup"><span data-stu-id="881e1-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="881e1-160">Siga estas [etapas para habilitar a instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="881e1-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="881e1-161">Experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="881e1-161">End user experience:</span></span>

1. <span data-ttu-id="881e1-162">O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima.</span><span class="sxs-lookup"><span data-stu-id="881e1-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="881e1-163">O usuário visita a URL criada na etapa acima.</span><span class="sxs-lookup"><span data-stu-id="881e1-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="881e1-164">O aplicativo agora será instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="881e1-164">The app will now install to the device.</span></span> <span data-ttu-id="881e1-165">Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="881e1-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="881e1-166">Para obter mais ajuda com a solução de problemas do método de instalação do instalador de aplicativos, visite [solucionar problemas do instalador de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="881e1-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="881e1-167">Não há suporte para a interface do usuário durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="881e1-167">UI during the update process is not supported.</span></span> <span data-ttu-id="881e1-168">Portanto, não há suporte para a opção de não-prompt nessa [página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e nas opções relacionadas.</span><span class="sxs-lookup"><span data-stu-id="881e1-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="881e1-169">Aplicativos de exemplo</span><span class="sxs-lookup"><span data-stu-id="881e1-169">Sample Apps</span></span>

<span data-ttu-id="881e1-170">Para experimentar o instalador do aplicativo com alguns aplicativos de exemplo, confira alguns dos nossos exemplos disponíveis:</span><span class="sxs-lookup"><span data-stu-id="881e1-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="881e1-171">Hub de exemplos do MRTK</span><span class="sxs-lookup"><span data-stu-id="881e1-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="881e1-172">Surfaces</span><span class="sxs-lookup"><span data-stu-id="881e1-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="881e1-173">Aplicativos de exemplo UWP que podem ser usados para teste</span><span class="sxs-lookup"><span data-stu-id="881e1-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
