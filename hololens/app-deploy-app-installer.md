---
title: Como carregar e instalar aplicativos por meio do HoloLens 2 Instalador de Aplicativo
description: Saiba como instalar e solucionar problemas de aplicativos com o instalador de aplicativo e o side load e instalar aplicativos por meio da interface do usuário.
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
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924121"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="b313a-104">Instalar aplicativos no HoloLens 2 por meio Instalador de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b313a-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="b313a-105">Esse recurso foi disponibilizado no [Windows Holographic, versão 20H2 – Atualização de dezembro de 2020.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="b313a-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="b313a-106">Verifique se o dispositivo [está atualizado](hololens-update-hololens.md) para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="b313a-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="b313a-107">Adicionamos **uma nova funcionalidade (Instalador de Aplicativo)** para permitir que você instale aplicativos de forma mais direta em seus dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b313a-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="b313a-108">O recurso estará em **por padrão para dispositivos não planejados.**</span><span class="sxs-lookup"><span data-stu-id="b313a-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="b313a-109">Para evitar interrupções nas empresas, o instalador de aplicativo não **estará disponível para dispositivos gerenciados** no momento.</span><span class="sxs-lookup"><span data-stu-id="b313a-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="b313a-110">Um dispositivo será considerado "gerenciado" **se qualquer** um dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="b313a-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="b313a-111">MDM [inscrito](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="b313a-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="b313a-112">Configurado com o [pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="b313a-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="b313a-113">A [Identidade do](hololens-identity.md) Usuário é o Azure AD</span><span class="sxs-lookup"><span data-stu-id="b313a-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="b313a-114">Agora você pode instalar aplicativos sem a necessidade de habilitar o Modo de Desenvolvedor ou usar Portal de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b313a-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="b313a-115">Baixe (por USB ou por Microsoft Edge) o Pacote Appx para seu dispositivo e navegue até o Pacote Appx no Explorador de Arquivos para ser solicitado a dar início à instalação.</span><span class="sxs-lookup"><span data-stu-id="b313a-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="b313a-116">Como alternativa, [inicie uma instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="b313a-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="b313a-117">Assim como os aplicativos instalados do Microsoft Store ou sideload usando a funcionalidade de implantação de Aplicativo [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) do MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Assinatura e o certificado usado para assinar deve ser confiável para o dispositivo HoloLens antes que o aplicativo possa ser implantado.</span><span class="sxs-lookup"><span data-stu-id="b313a-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="b313a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b313a-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="b313a-119">Para seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="b313a-119">For your devices:</span></span>

<span data-ttu-id="b313a-120">Esse recurso está disponível atualmente em builds do Windows Holographic 20H2 para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b313a-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="b313a-121">Certifique-se de que todos os dispositivos que usam esse método sejam [atualizados.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="b313a-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="b313a-122">Para seus aplicativos:</span><span class="sxs-lookup"><span data-stu-id="b313a-122">For your apps:</span></span>

<span data-ttu-id="b313a-123">A Configuração da Solução do  aplicativo deve ser **Mestre** ou Versão, pois o Instalador de Aplicativo usará dependências do armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b313a-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="b313a-124">Confira mais sobre como [criar pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="b313a-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="b313a-125">Os aplicativos instalados por meio desse método devem ser assinados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="b313a-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="b313a-126">Você precisará usar um certificado para assinar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b313a-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="b313a-127">Você pode obter um certificado da Lista de AC Confiáveis da [MS;](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)nesse caso, você não precisará tomar nenhuma ação extra.</span><span class="sxs-lookup"><span data-stu-id="b313a-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="b313a-128">Ou você pode assinar seu próprio certificado, no entanto, esse certificado precisará ser esvasado para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b313a-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="b313a-129">Como assinar aplicativos [usando a Ferramenta de Assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="b313a-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="b313a-130">**Opções de certificado:**</span><span class="sxs-lookup"><span data-stu-id="b313a-130">**Certificate options:**</span></span>

- [<span data-ttu-id="b313a-131">Lista de AC confiáveis do MS</span><span class="sxs-lookup"><span data-stu-id="b313a-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="b313a-132">**Escolha um método de implantação de certificado.**</span><span class="sxs-lookup"><span data-stu-id="b313a-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="b313a-133">[Os pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="b313a-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="b313a-134">O MDM pode ser usado para [aplicar certificados com configurações de dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="b313a-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="b313a-135">Use o no Gerenciador [de Certificados do dispositivo.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="b313a-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="b313a-136">Método de instalação</span><span class="sxs-lookup"><span data-stu-id="b313a-136">Installation method</span></span>

1. <span data-ttu-id="b313a-137">Verifique se o dispositivo não é considerado gerenciado.</span><span class="sxs-lookup"><span data-stu-id="b313a-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="b313a-138">Verifique se o dispositivo HoloLens 2 está ligado e se você está conectado.</span><span class="sxs-lookup"><span data-stu-id="b313a-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="b313a-139">No computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="b313a-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="b313a-140">Depois de concluir a cópia do arquivo, você poderá desconectar seu dispositivo e concluir a instalação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="b313a-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="b313a-141">Em seu dispositivo HoloLens 2, abra o **Menu** Iniciar, **selecione Todos os apps** e inicie o **Explorador de Arquivos** aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b313a-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="b313a-142">Navegue até a pasta Downloads.</span><span class="sxs-lookup"><span data-stu-id="b313a-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="b313a-143">Talvez seja necessário que, no painel esquerdo do aplicativo, selecione Este dispositivo **primeiro** e, em seguida, navegue até Downloads.</span><span class="sxs-lookup"><span data-stu-id="b313a-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="b313a-144">Selecione o arquivo yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="b313a-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="b313a-145">O Instalador de Aplicativo será lançado.</span><span class="sxs-lookup"><span data-stu-id="b313a-145">The App Installer will launch.</span></span> <span data-ttu-id="b313a-146">Selecione o **botão** Instalar para instalar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b313a-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="b313a-147">O aplicativo instalado será automaticamente lançado após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="b313a-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalando exemplos do MRTK por meio Instalador de Aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="b313a-149">Solução de problemas de instalação</span><span class="sxs-lookup"><span data-stu-id="b313a-149">Troubleshooting Installs</span></span>

<span data-ttu-id="b313a-150">Se o aplicativo não for instalado, verifique o seguinte para solucionar problemas:</span><span class="sxs-lookup"><span data-stu-id="b313a-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="b313a-151">Seu aplicativo é um build Mestre ou Versão.</span><span class="sxs-lookup"><span data-stu-id="b313a-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="b313a-152">Seu dispositivo é atualizado para um build no qual esse recurso está disponível.</span><span class="sxs-lookup"><span data-stu-id="b313a-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="b313a-153">Você está [conectado à Internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="b313a-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="b313a-154">Os [pontos de extremidade para o Microsoft Store](hololens-offline.md) estão configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="b313a-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="b313a-155">Instalador da Web</span><span class="sxs-lookup"><span data-stu-id="b313a-155">Web Installer</span></span>

<span data-ttu-id="b313a-156">Os usuários podem instalar um aplicativo diretamente de um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="b313a-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="b313a-157">Esse fluxo usa o Instalador de Aplicativo combinado com um método de distribuição fácil de baixar e instalar.</span><span class="sxs-lookup"><span data-stu-id="b313a-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="b313a-158">Como configurar a instalação da Web:</span><span class="sxs-lookup"><span data-stu-id="b313a-158">How to set up web install:</span></span>

1. <span data-ttu-id="b313a-159">Verifique se o aplicativo está configurado corretamente para instalação.</span><span class="sxs-lookup"><span data-stu-id="b313a-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="b313a-160">Siga estas [etapas para habilitar a instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="b313a-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="b313a-161">Experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="b313a-161">End user experience:</span></span>

1. <span data-ttu-id="b313a-162">O usuário recebe e instala o certificado no dispositivo usando um método escolhido anteriormente acima.</span><span class="sxs-lookup"><span data-stu-id="b313a-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="b313a-163">O usuário visita a URL criada na etapa acima.</span><span class="sxs-lookup"><span data-stu-id="b313a-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="b313a-164">O aplicativo agora será instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b313a-164">The app will now install to the device.</span></span> <span data-ttu-id="b313a-165">Para encontrar o aplicativo, abra o **menu Iniciar** e selecione o **botão Todos os apps** para encontrar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b313a-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="b313a-166">Para obter mais ajuda com a solução de problemas do método de instalação do instalador de aplicativo, visite [solucionar problemas do instalador de aplicativo.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="b313a-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="b313a-167">Não há suporte para a interface do usuário durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="b313a-167">UI during the update process is not supported.</span></span> <span data-ttu-id="b313a-168">Portanto, não há suporte para a opção ShowPrompt [nesta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e as opções relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b313a-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="b313a-169">Aplicativos de exemplo</span><span class="sxs-lookup"><span data-stu-id="b313a-169">Sample Apps</span></span>

<span data-ttu-id="b313a-170">Experimente o Instalador de Aplicativo com um de nossos aplicativos de exemplo disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b313a-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="b313a-171">Aplicativos de exemplo</span><span class="sxs-lookup"><span data-stu-id="b313a-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
