---
title: Visão geral-gerenciamento de aplicativos
description: gerenciamento de aplicativos, gerenciamento e aplicativos
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
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252662"
---
# <span data-ttu-id="a7c25-104">Gerenciamento de aplicativos: Visão Geral</span><span class="sxs-lookup"><span data-stu-id="a7c25-104">App Management: Overview</span></span>

<span data-ttu-id="a7c25-105">Você pode implantar aplicativos em quatro caminhos diferentes: **Gerenciamento de dispositivos móveis (MDM)**, **Microsoft Store para empresas**, **Microsoft Store**ou instalando-os por meio do **provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="a7c25-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="a7c25-106">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="a7c25-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="a7c25-107">Uma solução MDM permite que os responsáveis por decisões e administradores de ti sejam instalados de forma privada (push) em seus aplicativos internos, de linha de negócios ou comprar aplicativos por meio da loja para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="a7c25-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="a7c25-108">Os dispositivos HoloLens funcionam melhor com o Microsoft Endpoint Manager (Intune) para [Gerenciamento de aplicativos](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="a7c25-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="a7c25-109">O Intune também oferece aos usuários um controle mais refinado sobre aplicativos gerenciados por ti por meio da experiência que pode ser baixada do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="a7c25-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="a7c25-110">As instruções a seguir são para os usuários que desejam gerenciar seus aplicativos com o Intune.</span><span class="sxs-lookup"><span data-stu-id="a7c25-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="a7c25-111">A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a7c25-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="a7c25-112">O MDM (gerenciamento de dispositivo móvel) é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="a7c25-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="a7c25-113">MDM implantado + portal da empresa</span><span class="sxs-lookup"><span data-stu-id="a7c25-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="a7c25-114">Aplicativos de linha de negócios (não públicos)</span><span class="sxs-lookup"><span data-stu-id="a7c25-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="a7c25-115">Instalação manual de aplicativos disponíveis por meio do portal da empresa</span><span class="sxs-lookup"><span data-stu-id="a7c25-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="a7c25-116">Push de administrador por meio de política MDM</span><span class="sxs-lookup"><span data-stu-id="a7c25-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="a7c25-117">Atualização automática por meio de MDM</span><span class="sxs-lookup"><span data-stu-id="a7c25-117">Auto update through MDM</span></span>

## <span data-ttu-id="a7c25-118">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="a7c25-118">Microsoft Store for Business</span></span>

<span data-ttu-id="a7c25-119">A [Microsoft Store para empresas](app-deploy-store-business.md) fornece aos responsáveis por decisões e administradores de ti nas empresas para localizar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos.</span><span class="sxs-lookup"><span data-stu-id="a7c25-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="a7c25-120">Os administradores de ti podem gerenciar aplicativos da Microsoft Store e aplicativos de linha de negócios particulares em um único inventário, além de atribuir licenças e reutilizar licenças conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="a7c25-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="a7c25-121">Para obter mais informações, acesse [pré-requisitos para usar a Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="a7c25-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="a7c25-122">A Microsoft Store para empresas se aplica a:</span><span class="sxs-lookup"><span data-stu-id="a7c25-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="a7c25-123">Aplicativos públicos ou de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="a7c25-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="a7c25-124">Instalação automática de aplicativos necessários por meio da Associação MDM</span><span class="sxs-lookup"><span data-stu-id="a7c25-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="a7c25-125">O usuário baixa os aplicativos manualmente</span><span class="sxs-lookup"><span data-stu-id="a7c25-125">User manually downloads apps</span></span>
* <span data-ttu-id="a7c25-126">Atualização automática</span><span class="sxs-lookup"><span data-stu-id="a7c25-126">Auto Update</span></span>

## <span data-ttu-id="a7c25-127">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a7c25-127">Microsoft Store apps</span></span>

<span data-ttu-id="a7c25-128">A Microsoft Store fornece aos responsáveis por decisões e administradores de ti nas empresas para localizar, adquirir, gerenciar e distribuir aplicativos públicos.</span><span class="sxs-lookup"><span data-stu-id="a7c25-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="a7c25-129">Esta Microsoft Store é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="a7c25-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="a7c25-130">Somente aplicativos públicos</span><span class="sxs-lookup"><span data-stu-id="a7c25-130">Public apps only</span></span>
* <span data-ttu-id="a7c25-131">O usuário baixa os aplicativos manualmente</span><span class="sxs-lookup"><span data-stu-id="a7c25-131">User manually downloads apps</span></span>
* <span data-ttu-id="a7c25-132">Atualização automática se estiver conectada à Internet</span><span class="sxs-lookup"><span data-stu-id="a7c25-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="a7c25-133">Para obter mais informações, visite [holográfico Store apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="a7c25-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="a7c25-134">Instalar via pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="a7c25-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="a7c25-135">Os [pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de linha de negócios, permitindo que os profissionais de ti e administradores instalem rapidamente aplicativos em um ou mais dispositivos (s) locais via USB.</span><span class="sxs-lookup"><span data-stu-id="a7c25-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="a7c25-136">Essa instalação pode ser feita sem conexão à Internet e para qualquer tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="a7c25-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="a7c25-137">A instalação por meio de pacotes de provisionamento é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="a7c25-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="a7c25-138">Aplicativos de linha de negócios/autodesenvolvidos (não públicos)</span><span class="sxs-lookup"><span data-stu-id="a7c25-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="a7c25-139">Aplicativos públicos (se o instalador offline estiver disponível)</span><span class="sxs-lookup"><span data-stu-id="a7c25-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="a7c25-140">Somente para USB no carregamento do lado USB</span><span class="sxs-lookup"><span data-stu-id="a7c25-140">USB side-loading only</span></span>
* <span data-ttu-id="a7c25-141">Sem atualização automática (exige atualizações manuais por meio do pacote de provisionamento)</span><span class="sxs-lookup"><span data-stu-id="a7c25-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="a7c25-142">Instalar aplicativos no HoloLens 2 via instalador de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a7c25-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="a7c25-143">Usar os usuários do [instalador de aplicativos](app-deploy-app-installer.md) pode ter uma experiência simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não esteja familiarizado com outros métodos de instalação do aplicativo no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7c25-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="a7c25-144">Isso pode ser feito sem a necessidade de habilitar o modo de desenvolvedor ou usar o Device Portal.</span><span class="sxs-lookup"><span data-stu-id="a7c25-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="a7c25-145">Trata-se de um método simples de distribuir um aplicativo completamente compilado.</span><span class="sxs-lookup"><span data-stu-id="a7c25-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="a7c25-146">Independentemente de se você simplesmente quer fazer uma demonstração do aplicativo para outro usuário com um HoloLens ou quiser implantar seu aplicativo, esse método funciona facilmente.</span><span class="sxs-lookup"><span data-stu-id="a7c25-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="a7c25-147">A instalação por meio do instalador do aplicativo é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="a7c25-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="a7c25-148">Aplicativos de linha de negócios/autônomos (não públicos)</span><span class="sxs-lookup"><span data-stu-id="a7c25-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="a7c25-149">Somente carregar lado a lado</span><span class="sxs-lookup"><span data-stu-id="a7c25-149">Side-load only</span></span>
* <span data-ttu-id="a7c25-150">Não requer modo de desenvolvedor ou Device Portal</span><span class="sxs-lookup"><span data-stu-id="a7c25-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="a7c25-151">É fácil instalar o usuário final</span><span class="sxs-lookup"><span data-stu-id="a7c25-151">Easy for end user to install</span></span>
