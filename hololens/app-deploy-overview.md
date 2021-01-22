---
title: Visão geral - Gerenciamento de Aplicativos
description: Começar com uma visão geral do gerenciamento de aplicativos de realidade misturada com gerenciamento de dispositivo móvel, Microsoft Store para Empresas e pacotes de provisionamento.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283702"
---
# <span data-ttu-id="94a36-104">Gerenciamento de aplicativos: Visão Geral</span><span class="sxs-lookup"><span data-stu-id="94a36-104">App Management: Overview</span></span>

<span data-ttu-id="94a36-105">Você pode implantar aplicativos em quatro caminhos diferentes: Gerenciamento de Dispositivo **Móvel (MDM),** **Microsoft Store**para Empresas , **Microsoft Store**ou instalando-os por meio de **provisionamento.**</span><span class="sxs-lookup"><span data-stu-id="94a36-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="94a36-106">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="94a36-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="94a36-107">Uma solução MDM permite que os tomadores de decisões de IT e os administradores instalem automaticamente (push) seus aplicativos de linha de negócios internamente ou comprem aplicativos por meio da loja para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="94a36-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="94a36-108">Os dispositivos HoloLens funcionam melhor com o Microsoft Endpoint Manager (Intune) para gerenciamento [de aplicativos.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="94a36-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="94a36-109">O Intune também oferece aos usuários um controle mais fino sobre aplicativos gerenciados por IT por meio da experiência baixável do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="94a36-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="94a36-110">As instruções a seguir são para usuários que querem gerenciar seus aplicativos com o Intune.</span><span class="sxs-lookup"><span data-stu-id="94a36-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="94a36-111">A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="94a36-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="94a36-112">O Gerenciamento de Dispositivo Móvel (MDM) é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="94a36-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="94a36-113">MDM implantado + Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="94a36-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="94a36-114">Aplicativos de linha de negócios (não públicos)</span><span class="sxs-lookup"><span data-stu-id="94a36-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="94a36-115">Instalação manual de aplicativos disponíveis por meio do Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="94a36-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="94a36-116">Admin push through MDM policy</span><span class="sxs-lookup"><span data-stu-id="94a36-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="94a36-117">Atualização automática por meio do MDM</span><span class="sxs-lookup"><span data-stu-id="94a36-117">Auto update through MDM</span></span>

## <span data-ttu-id="94a36-118">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="94a36-118">Microsoft Store for Business</span></span>

<span data-ttu-id="94a36-119">A [Microsoft Store para Empresas](app-deploy-store-business.md) fornece aos tomadores de decisões de IT e aos administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos.</span><span class="sxs-lookup"><span data-stu-id="94a36-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="94a36-120">Os administradores de IT podem gerenciar aplicativos da Microsoft Store e aplicativos privados de linha de negócios em um único inventário, além de atribuir e reutilizar licenças conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="94a36-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="94a36-121">Para obter mais informações, visite [Pré-requisitos para usar a Microsoft Store para Empresas.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="94a36-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="94a36-122">A Microsoft Store para Empresas se aplica a:</span><span class="sxs-lookup"><span data-stu-id="94a36-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="94a36-123">Aplicativos públicos ou de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="94a36-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="94a36-124">Instalação automática de aplicativos necessários por meio da associação MDM</span><span class="sxs-lookup"><span data-stu-id="94a36-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="94a36-125">O usuário baixa aplicativos manualmente</span><span class="sxs-lookup"><span data-stu-id="94a36-125">User manually downloads apps</span></span>
* <span data-ttu-id="94a36-126">Atualização Automática</span><span class="sxs-lookup"><span data-stu-id="94a36-126">Auto Update</span></span>

## <span data-ttu-id="94a36-127">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="94a36-127">Microsoft Store apps</span></span>

<span data-ttu-id="94a36-128">A Microsoft Store fornece aos tomadores de decisões de IT e aos administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos públicos.</span><span class="sxs-lookup"><span data-stu-id="94a36-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="94a36-129">Esta Microsoft Store é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="94a36-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="94a36-130">Somente aplicativos públicos</span><span class="sxs-lookup"><span data-stu-id="94a36-130">Public apps only</span></span>
* <span data-ttu-id="94a36-131">O usuário baixa aplicativos manualmente</span><span class="sxs-lookup"><span data-stu-id="94a36-131">User manually downloads apps</span></span>
* <span data-ttu-id="94a36-132">Atualização automática se conectado à Internet</span><span class="sxs-lookup"><span data-stu-id="94a36-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="94a36-133">Para obter mais informações, visite [Aplicativos da Loja Holográfica.](https://docs.microsoft.com/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="94a36-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="94a36-134">Instalar por meio de pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="94a36-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="94a36-135">[Os Pacotes de Provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de Linha de Negócios, permitindo que profissionais de TI e administradores instalem rapidamente aplicativos em dispositivos locais via USB.</span><span class="sxs-lookup"><span data-stu-id="94a36-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="94a36-136">Essa instalação pode ser feita sem uma conexão com a Internet e para qualquer tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="94a36-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="94a36-137">A instalação por meio de pacotes de provisionamento é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="94a36-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="94a36-138">Aplicativos de linha de negócios/auto-desenvolvidos (não públicos)</span><span class="sxs-lookup"><span data-stu-id="94a36-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="94a36-139">Aplicativos públicos (se o instalador offline estiver disponível)</span><span class="sxs-lookup"><span data-stu-id="94a36-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="94a36-140">Somente carregamento lateral USB</span><span class="sxs-lookup"><span data-stu-id="94a36-140">USB side-loading only</span></span>
* <span data-ttu-id="94a36-141">Nenhuma atualização automática (requer atualizações manuais por meio do Pacote de Provisionamento)</span><span class="sxs-lookup"><span data-stu-id="94a36-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="94a36-142">Instalar aplicativos no HoloLens 2 por meio do Instalador de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="94a36-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="94a36-143">Usar os usuários do [Instalador](app-deploy-app-installer.md) de Aplicativo pode ter uma experiência simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não seja familiar com outros métodos de instalação de aplicativos no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="94a36-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="94a36-144">Isso pode ser feito sem a necessidade de habilitar o Modo de Desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="94a36-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="94a36-145">Esse é um método simples de distribuir um aplicativo completamente criado.</span><span class="sxs-lookup"><span data-stu-id="94a36-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="94a36-146">Independentemente de você simplesmente desejar demonstra seu aplicativo para outro usuário com um HoloLens ou se deseja implantar seu aplicativo, esse método funciona facilmente.</span><span class="sxs-lookup"><span data-stu-id="94a36-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="94a36-147">A instalação por meio do Instalador de Aplicativo é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="94a36-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="94a36-148">Aplicativos de linha de negócios/auto-desenvolvidos (não públicos)</span><span class="sxs-lookup"><span data-stu-id="94a36-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="94a36-149">Somente side-load</span><span class="sxs-lookup"><span data-stu-id="94a36-149">Side-load only</span></span>
* <span data-ttu-id="94a36-150">Não exige o modo desenvolvedor ou o portal de dispositivos</span><span class="sxs-lookup"><span data-stu-id="94a36-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="94a36-151">Fácil para o usuário final instalar</span><span class="sxs-lookup"><span data-stu-id="94a36-151">Easy for end user to install</span></span>
