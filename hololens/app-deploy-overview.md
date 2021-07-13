---
title: Visão geral – Gerenciamento de Aplicativos
description: Começar com uma visão geral do gerenciamento de aplicativos de realidade misturada com gerenciamento de dispositivo móvel, Microsoft Store para empresas e pacotes de provisionamento.
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635544"
---
# <a name="app-management-overview"></a><span data-ttu-id="aa611-104">Gerenciamento de Aplicativos: Visão geral</span><span class="sxs-lookup"><span data-stu-id="aa611-104">App Management: Overview</span></span>

<span data-ttu-id="aa611-105">Você pode implantar aplicativos em quatro caminhos diferentes: **MDM (Mobile Gerenciamento de Dispositivos),** **Microsoft Store para Empresas**, **Microsoft Store** ou instalando-os por meio **do Provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="aa611-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="aa611-106">Gerenciamento de Dispositivos Móveis (MDM)</span><span class="sxs-lookup"><span data-stu-id="aa611-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="aa611-107">Uma solução de MDM permite que os tomadores de decisões e administradores de IT instalem (push) seus aplicativos de linha de negócios internamente ou comprem aplicativos por meio da loja para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="aa611-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="aa611-108">HoloLens dispositivos funcionam melhor com o Microsoft Endpoint Manager (Intune) para gerenciamento [de aplicativos.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="aa611-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="aa611-109">O Intune também oferece aos usuários um controle mais fino sobre aplicativos gerenciados por IT por meio da Portal da Empresa baixável.</span><span class="sxs-lookup"><span data-stu-id="aa611-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="aa611-110">As instruções a seguir são para usuários que querem gerenciar seus aplicativos com o Intune.</span><span class="sxs-lookup"><span data-stu-id="aa611-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="aa611-111">A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa611-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="aa611-112">O MDM (mobile Gerenciamento de Dispositivos) é aplicável a:</span><span class="sxs-lookup"><span data-stu-id="aa611-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="aa611-113">MDM implantado + Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="aa611-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="aa611-114">Aplicativos de linha de negócios (não públicos)</span><span class="sxs-lookup"><span data-stu-id="aa611-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="aa611-115">Instalação manual de aplicativos disponíveis por meio Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="aa611-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="aa611-116">Push do administrador por meio da política de MDM</span><span class="sxs-lookup"><span data-stu-id="aa611-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="aa611-117">Atualização automática por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="aa611-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="aa611-118">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="aa611-118">Microsoft Store for Business</span></span>

<span data-ttu-id="aa611-119">A [Microsoft Store para Empresas](app-deploy-store-business.md) fornece tomadores de decisões de IT e administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos.</span><span class="sxs-lookup"><span data-stu-id="aa611-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="aa611-120">Os administradores de gerenciar Microsoft Store aplicativos de linha de negócios privados em um inventário, além de atribuir e reutilizar licenças conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="aa611-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="aa611-121">Para obter mais informações, [visite Pré-requisitos para usar o Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="aa611-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="aa611-122">O Microsoft Store para Empresas é aplicável a:</span><span class="sxs-lookup"><span data-stu-id="aa611-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="aa611-123">Aplicativos públicos ou de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="aa611-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="aa611-124">Instalação automática de aplicativos necessários por meio da associação de MDM</span><span class="sxs-lookup"><span data-stu-id="aa611-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="aa611-125">O usuário baixa manualmente aplicativos</span><span class="sxs-lookup"><span data-stu-id="aa611-125">User manually downloads apps</span></span>
* <span data-ttu-id="aa611-126">Atualização automática</span><span class="sxs-lookup"><span data-stu-id="aa611-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="aa611-127">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="aa611-127">Microsoft Store apps</span></span>

<span data-ttu-id="aa611-128">O Microsoft Store fornece tomadores de decisões de IT e administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos públicos.</span><span class="sxs-lookup"><span data-stu-id="aa611-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="aa611-129">Este Microsoft Store é aplicável a:</span><span class="sxs-lookup"><span data-stu-id="aa611-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="aa611-130">Somente aplicativos públicos</span><span class="sxs-lookup"><span data-stu-id="aa611-130">Public apps only</span></span>
* <span data-ttu-id="aa611-131">O usuário baixa manualmente aplicativos</span><span class="sxs-lookup"><span data-stu-id="aa611-131">User manually downloads apps</span></span>
* <span data-ttu-id="aa611-132">Atualização automática se conectado à Internet</span><span class="sxs-lookup"><span data-stu-id="aa611-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="aa611-133">Para obter mais informações, visite [Aplicativos da Holographic Store.](/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="aa611-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="aa611-134">Instalar por meio de pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="aa611-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="aa611-135">[Os pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de Linha de Negócios, permitindo que profissionais de TI e administradores instalem rapidamente aplicativos em um(s) dispositivo(s) local via USB.</span><span class="sxs-lookup"><span data-stu-id="aa611-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="aa611-136">Essa instalação pode ser feita sem uma conexão com a Internet e com qualquer tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="aa611-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="aa611-137">A instalação por meio de pacotes de provisionamento é aplicável a:</span><span class="sxs-lookup"><span data-stu-id="aa611-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="aa611-138">Aplicativos de linha de negócios/autodepro desenvolvidos (não públicos)</span><span class="sxs-lookup"><span data-stu-id="aa611-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="aa611-139">Aplicativos públicos (se o instalador offline estiver disponível)</span><span class="sxs-lookup"><span data-stu-id="aa611-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="aa611-140">Somente carregamento lateral USB</span><span class="sxs-lookup"><span data-stu-id="aa611-140">USB side-loading only</span></span>
* <span data-ttu-id="aa611-141">Nenhuma atualização automática (requer atualizações manuais por meio do Pacote de Provisionamento)</span><span class="sxs-lookup"><span data-stu-id="aa611-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="aa611-142">Instalar aplicativos no HoloLens 2 por meio Instalador de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="aa611-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="aa611-143">Usar o [Instalador de Aplicativo](app-deploy-app-installer.md) usuários pode ter uma experiência simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não está familiarizado com outros métodos de instalação de aplicativo no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa611-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="aa611-144">Isso pode ser feito sem a necessidade de habilitar o Modo de Desenvolvedor ou usar Portal de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa611-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="aa611-145">Esse é um método simples de distribuir um aplicativo completamente criado.</span><span class="sxs-lookup"><span data-stu-id="aa611-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="aa611-146">Independentemente de se você simplesmente deseja demonstração de seu aplicativo para outro usuário com um HoloLens ou se deseja implantar seu aplicativo, esse método funciona facilmente.</span><span class="sxs-lookup"><span data-stu-id="aa611-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="aa611-147">A instalação por Instalador de Aplicativo é aplicável a:</span><span class="sxs-lookup"><span data-stu-id="aa611-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="aa611-148">Aplicativos de linha de negócios/autodepro desenvolvidos (não públicos)</span><span class="sxs-lookup"><span data-stu-id="aa611-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="aa611-149">Somente side-load</span><span class="sxs-lookup"><span data-stu-id="aa611-149">Side-load only</span></span>
* <span data-ttu-id="aa611-150">Não requer o modo de desenvolvedor ou o portal de dispositivos</span><span class="sxs-lookup"><span data-stu-id="aa611-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="aa611-151">Fácil para o usuário final instalar</span><span class="sxs-lookup"><span data-stu-id="aa611-151">Easy for end user to install</span></span>
