---
title: Como instalar aplicativos via instalador da Web
description: Instalar aplicativos via instalador da Web para instalador de aplicativos
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos, instalação da Web
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027453"
---
# <span data-ttu-id="82f6a-104">Instalando aplicativos de uma página da Web</span><span class="sxs-lookup"><span data-stu-id="82f6a-104">Installing apps from a web page</span></span>

<span data-ttu-id="82f6a-105">Os usuários podem instalar um aplicativo diretamente de um servidor Web.</span><span class="sxs-lookup"><span data-stu-id="82f6a-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="82f6a-106">Isso usa o instalador do aplicativo combinado com um método fácil de distribuição de download e instalação.</span><span class="sxs-lookup"><span data-stu-id="82f6a-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="82f6a-107">No momento, esse recurso só avalible no Windows Insider compilações do 19041.1366 +.</span><span class="sxs-lookup"><span data-stu-id="82f6a-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="82f6a-108">[Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="82f6a-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="82f6a-109">Como configurar isso:</span><span class="sxs-lookup"><span data-stu-id="82f6a-109">How to set this up:</span></span>
1.  <span data-ttu-id="82f6a-110">Verifique se o aplicativo está configurado corretamente para a instalação.</span><span class="sxs-lookup"><span data-stu-id="82f6a-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="82f6a-111">Siga estas [etapas para habilitar isso em uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="82f6a-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="82f6a-112">Escolha um método de implantação de certificado.</span><span class="sxs-lookup"><span data-stu-id="82f6a-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="82f6a-113">Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="82f6a-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="82f6a-114">O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="82f6a-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="82f6a-115">Use o Gerenciador de [certificados](hololens-insider.md#certificate-manager)no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="82f6a-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="82f6a-116">Experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="82f6a-116">End User Experience:</span></span>
1.  <span data-ttu-id="82f6a-117">O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima.</span><span class="sxs-lookup"><span data-stu-id="82f6a-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="82f6a-118">O usuário visita a URL criada a partir da etapa acima.</span><span class="sxs-lookup"><span data-stu-id="82f6a-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="82f6a-119">O aplicativo agora será instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="82f6a-119">The app will now install to the device.</span></span> <span data-ttu-id="82f6a-120">Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82f6a-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="82f6a-121">Para ajudar a solucionar problemas com esse método de instalação, acesse [solucionar](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)problemas do instalador do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82f6a-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="82f6a-122">Não há suporte para a interface do usuário durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="82f6a-122">UI during the update process is not supported.</span></span> <span data-ttu-id="82f6a-123">Portanto, não há suporte para a opção não receber [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e opções relacionadas.</span><span class="sxs-lookup"><span data-stu-id="82f6a-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
