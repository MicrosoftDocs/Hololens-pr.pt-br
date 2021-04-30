---
title: Visão geral – gerenciamento de aplicativos
description: Comece com uma visão geral do gerenciamento de aplicativos de realidade misturada com gerenciamento de dispositivo móvel, Microsoft Store para empresas e pacotes de provisionamento.
keywords: HoloLens, usuário, conta, aplicativo, gerenciamento de aplicativos,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308083"
---
# <a name="app-management-overview"></a><span data-ttu-id="41448-104">Gerenciamento de aplicativos: visão geral</span><span class="sxs-lookup"><span data-stu-id="41448-104">App Management: Overview</span></span>

<span data-ttu-id="41448-105">Você pode implantar aplicativos em quatro caminhos diferentes: **MDM (gerenciamento de dispositivo móvel)**, **Microsoft Store para negócios**, **Microsoft Store** ou instalando-os por meio de **provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="41448-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="41448-106">Gerenciamento de Dispositivos Móveis (MDM)</span><span class="sxs-lookup"><span data-stu-id="41448-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="41448-107">Uma solução de MDM permite que os administradores e tomadores de decisões de ti instalem de forma privada (push) seus aplicativos internos de linha de negócios ou comprem aplicativos por meio da loja para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="41448-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="41448-108">Os dispositivos do HoloLens funcionam melhor com o Microsoft Endpoint Manager (Intune) para [Gerenciamento de aplicativos](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="41448-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="41448-109">O Intune também oferece aos usuários um controle mais refinado sobre aplicativos gerenciados por ti por meio da experiência Portal da Empresa baixável.</span><span class="sxs-lookup"><span data-stu-id="41448-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="41448-110">As instruções a seguir são para os usuários que desejam gerenciar seus aplicativos com o Intune.</span><span class="sxs-lookup"><span data-stu-id="41448-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="41448-111">A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="41448-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="41448-112">O MDM (gerenciamento de dispositivo móvel) é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="41448-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="41448-113">MDM implantado + Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="41448-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="41448-114">Aplicativos de linha de negócios (não públicos)</span><span class="sxs-lookup"><span data-stu-id="41448-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="41448-115">Instalação manual de aplicativos disponíveis por meio do Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="41448-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="41448-116">Push de administrador por meio da política de MDM</span><span class="sxs-lookup"><span data-stu-id="41448-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="41448-117">Atualizar automaticamente por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="41448-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="41448-118">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="41448-118">Microsoft Store for Business</span></span>

<span data-ttu-id="41448-119">O [Microsoft Store para negócios](app-deploy-store-business.md) fornece aos tomadores de decisão de ti e administradores em empresas para localizar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos.</span><span class="sxs-lookup"><span data-stu-id="41448-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="41448-120">Os administradores de ti podem gerenciar aplicativos Microsoft Store e aplicativos de linha de negócios privados em um único inventário, além de atribuir e reutilizar licenças conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="41448-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="41448-121">Para obter mais informações, visite [pré-requisitos para usar o Microsoft Store para negócios](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="41448-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="41448-122">O Microsoft Store para negócios é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="41448-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="41448-123">Aplicativos públicos ou de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="41448-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="41448-124">Instalação automática de aplicativos necessários por meio da Associação de MDM</span><span class="sxs-lookup"><span data-stu-id="41448-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="41448-125">O usuário baixa manualmente os aplicativos</span><span class="sxs-lookup"><span data-stu-id="41448-125">User manually downloads apps</span></span>
* <span data-ttu-id="41448-126">Atualização automática</span><span class="sxs-lookup"><span data-stu-id="41448-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="41448-127">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="41448-127">Microsoft Store apps</span></span>

<span data-ttu-id="41448-128">O Microsoft Store fornece aos tomadores de decisão de ti e administradores em empresas para localizar, adquirir, gerenciar e distribuir aplicativos públicos.</span><span class="sxs-lookup"><span data-stu-id="41448-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="41448-129">Esse Microsoft Store é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="41448-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="41448-130">Somente aplicativos públicos</span><span class="sxs-lookup"><span data-stu-id="41448-130">Public apps only</span></span>
* <span data-ttu-id="41448-131">O usuário baixa manualmente os aplicativos</span><span class="sxs-lookup"><span data-stu-id="41448-131">User manually downloads apps</span></span>
* <span data-ttu-id="41448-132">Atualização automática se estiver conectada à Internet</span><span class="sxs-lookup"><span data-stu-id="41448-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="41448-133">Para obter mais informações, visite [aplicativos da Holographic Store](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="41448-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="41448-134">Instalar por meio de pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="41448-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="41448-135">Os [pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de linha de negócios, permitindo que os profissionais de ti e os administradores instalem aplicativos rapidamente em um dispositivo local via USB.</span><span class="sxs-lookup"><span data-stu-id="41448-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="41448-136">Essa instalação pode ser feita sem uma conexão com a Internet e para qualquer tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="41448-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="41448-137">A instalação por meio de pacotes de provisionamento é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="41448-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="41448-138">Aplicativos de linha de negócios/desenvolvidos automaticamente (não públicos)</span><span class="sxs-lookup"><span data-stu-id="41448-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="41448-139">Aplicativos públicos (se o instalador offline estiver disponível)</span><span class="sxs-lookup"><span data-stu-id="41448-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="41448-140">Somente carregamento USB</span><span class="sxs-lookup"><span data-stu-id="41448-140">USB side-loading only</span></span>
* <span data-ttu-id="41448-141">Nenhuma atualização automática (requer atualizações manuais por meio do pacote de provisionamento)</span><span class="sxs-lookup"><span data-stu-id="41448-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="41448-142">Instalar aplicativos no HoloLens 2 por meio do instalador de aplicativo</span><span class="sxs-lookup"><span data-stu-id="41448-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="41448-143">Usar os usuários do [instalador do aplicativo](app-deploy-app-installer.md) pode ter uma experiência que seja simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não esteja familiarizado com outros métodos de instalação do aplicativo no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="41448-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="41448-144">Isso pode ser feito sem a necessidade de habilitar o modo de desenvolvedor nem usar o portal do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="41448-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="41448-145">Esse é um método simples de distribuir um aplicativo totalmente compilado.</span><span class="sxs-lookup"><span data-stu-id="41448-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="41448-146">Independentemente de se você simplesmente deseja demonstrar seu aplicativo para outro usuário com um HoloLens ou deseja implantar seu aplicativo, esse método funciona facilmente.</span><span class="sxs-lookup"><span data-stu-id="41448-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="41448-147">A instalação por meio do instalador do aplicativo é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="41448-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="41448-148">Aplicativos de linha de negócios/auto desenvolvidos (não públicos)</span><span class="sxs-lookup"><span data-stu-id="41448-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="41448-149">Somente carregamento lateral</span><span class="sxs-lookup"><span data-stu-id="41448-149">Side-load only</span></span>
* <span data-ttu-id="41448-150">Não requer o modo de desenvolvedor ou o portal do dispositivo</span><span class="sxs-lookup"><span data-stu-id="41448-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="41448-151">Fácil de instalar o usuário final</span><span class="sxs-lookup"><span data-stu-id="41448-151">Easy for end user to install</span></span>
