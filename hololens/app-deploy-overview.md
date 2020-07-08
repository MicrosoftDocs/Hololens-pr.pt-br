---
title: Visão geral-gerenciamento de aplicativos
description: gerenciamento de aplicativos, gerenciamento e aplicativos
keywords: HoloLens, usuário, conta, aplicativo, gerenciamento de aplicativos,
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857870"
---
# <span data-ttu-id="5dae2-104">Gerenciamento de aplicativos: visão geral</span><span class="sxs-lookup"><span data-stu-id="5dae2-104">App Management: Overview</span></span>

<span data-ttu-id="5dae2-105">Você pode implantar aplicativos em quatro caminhos diferentes: **Gerenciamento de dispositivos móveis (MDM)**, **Microsoft Store para empresas**, **Microsoft Store**ou instalando-os por meio do **provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="5dae2-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="5dae2-106">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="5dae2-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="5dae2-107">Uma solução MDM permite que os responsáveis por decisões e administradores de ti sejam instalados de forma privada (push) em seus aplicativos internos, de linha de negócios ou comprar aplicativos por meio da loja para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="5dae2-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="5dae2-108">Os dispositivos HoloLens funcionam melhor com o Microsoft Endpoint Manager (Intune) para [Gerenciamento de aplicativos](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="5dae2-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="5dae2-109">O Intune também oferece aos usuários um controle mais refinado sobre aplicativos gerenciados por ti por meio da experiência que pode ser baixada do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="5dae2-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="5dae2-110">As instruções a seguir são para os usuários que desejam gerenciar seus aplicativos com o Intune.</span><span class="sxs-lookup"><span data-stu-id="5dae2-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="5dae2-111">A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5dae2-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="5dae2-112">O MDM (gerenciamento de dispositivo móvel) é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="5dae2-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="5dae2-113">MDM implantado + portal da empresa</span><span class="sxs-lookup"><span data-stu-id="5dae2-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="5dae2-114">Linha de aplicativos Business (não públicos)</span><span class="sxs-lookup"><span data-stu-id="5dae2-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="5dae2-115">Instalação manual de aplicativos disponíveis por meio do portal da empresa</span><span class="sxs-lookup"><span data-stu-id="5dae2-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="5dae2-116">Push de administrador por meio de política MDM</span><span class="sxs-lookup"><span data-stu-id="5dae2-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="5dae2-117">Atualização automática por meio de MDM</span><span class="sxs-lookup"><span data-stu-id="5dae2-117">Auto update through MDM</span></span>

## <span data-ttu-id="5dae2-118">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="5dae2-118">Microsoft Store for Business</span></span>

<span data-ttu-id="5dae2-119">A [Microsoft Store para empresas](app-deploy-store-business.md) fornece aos responsáveis por decisões e administradores de ti nas empresas para localizar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos.</span><span class="sxs-lookup"><span data-stu-id="5dae2-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="5dae2-120">Os administradores de TI podem gerenciar os aplicativos da Microsoft Store e os aplicativos privados de linha de negócios em um único inventário, além de atribuir e reutilizar licenças conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5dae2-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="5dae2-121">Para obter mais informações, acesse [pré-requisitos para usar a Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="5dae2-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="5dae2-122">A Microsoft Store para empresas se aplica a:</span><span class="sxs-lookup"><span data-stu-id="5dae2-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="5dae2-123">Aplicativos públicos ou de linha de negócios</span><span class="sxs-lookup"><span data-stu-id="5dae2-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="5dae2-124">Instalação automática de aplicativos necessários por meio da Associação MDM</span><span class="sxs-lookup"><span data-stu-id="5dae2-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="5dae2-125">O usuário baixa os aplicativos manualmente</span><span class="sxs-lookup"><span data-stu-id="5dae2-125">User manually downloads apps</span></span>
* <span data-ttu-id="5dae2-126">Atualização automática</span><span class="sxs-lookup"><span data-stu-id="5dae2-126">Auto Update</span></span>

## <span data-ttu-id="5dae2-127">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="5dae2-127">Microsoft Store apps</span></span>

<span data-ttu-id="5dae2-128">A Microsoft Store fornece aos responsáveis por decisões e administradores de ti nas empresas para localizar, adquirir, gerenciar e distribuir aplicativos públicos.</span><span class="sxs-lookup"><span data-stu-id="5dae2-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="5dae2-129">Esta Microsoft Store é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="5dae2-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="5dae2-130">Somente aplicativos públicos</span><span class="sxs-lookup"><span data-stu-id="5dae2-130">Public apps only</span></span>
* <span data-ttu-id="5dae2-131">O usuário baixa os aplicativos manualmente</span><span class="sxs-lookup"><span data-stu-id="5dae2-131">User manually downloads apps</span></span>
* <span data-ttu-id="5dae2-132">Atualização automática se estiver conectada à Internet</span><span class="sxs-lookup"><span data-stu-id="5dae2-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="5dae2-133">Para obter mais informações, visite [holográfico Store apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="5dae2-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="5dae2-134">Instalar via pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="5dae2-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="5dae2-135">Os [pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de linha de negócios, permitindo que os profissionais de ti e administradores instalem rapidamente aplicativos em um ou mais dispositivos (s) locais via USB.</span><span class="sxs-lookup"><span data-stu-id="5dae2-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="5dae2-136">Isso pode ser feito sem uma conexão à Internet e para qualquer tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="5dae2-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="5dae2-137">A instalação por meio de pacotes de provisionamento é aplicável para:</span><span class="sxs-lookup"><span data-stu-id="5dae2-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="5dae2-138">Linha de aplicativos Business (não públicos)</span><span class="sxs-lookup"><span data-stu-id="5dae2-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="5dae2-139">Aplicativos públicos (se o instalador offline estiver disponível)</span><span class="sxs-lookup"><span data-stu-id="5dae2-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="5dae2-140">Somente o carregamento do lado USB</span><span class="sxs-lookup"><span data-stu-id="5dae2-140">USB side-load only</span></span>
* <span data-ttu-id="5dae2-141">Sem atualização automática (exige atualizações manuais por meio do pacote de provisionamento)</span><span class="sxs-lookup"><span data-stu-id="5dae2-141">No auto update (requires manual updates via Provisioning Package)</span></span>
