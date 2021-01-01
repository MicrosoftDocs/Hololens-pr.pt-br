---
title: Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs
description: Como configurar CSPs, políticas e gerenciamento de dispositivos.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252772"
---
# <span data-ttu-id="24191-103">Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs</span><span class="sxs-lookup"><span data-stu-id="24191-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="24191-104">Os administradores de ti podem definir e implementar configurações de política no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="24191-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="24191-105">As configurações que você usa serão diferentes de acordo com o cenário de implantação, e os dispositivos corporativos oferecerão à TI um controle mais amplo.</span><span class="sxs-lookup"><span data-stu-id="24191-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="24191-106">No Windows 10, os provedores de serviços de configuração (CSP) são uma interface para ler, definir, modificar ou excluir definições de configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="24191-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="24191-107">Essas configurações mapeiam para arquivos ou chaves do Registro.</span><span class="sxs-lookup"><span data-stu-id="24191-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="24191-108">Alguns provedores de serviços de configuração dão suporte ao formato WAP, alguns dão suporte ao SyncML e alguns dão suporte a ambos.</span><span class="sxs-lookup"><span data-stu-id="24191-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="24191-109">Para obter mais informações sobre os CSPs de gerenciamento de dispositivos do Windows 10 holográfico, consulte a lista completa de [CSPs com suporte em dispositivos do HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span><span class="sxs-lookup"><span data-stu-id="24191-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="24191-110">Os administradores de ti também podem gerenciar o CSP de políticas em dispositivos, ver a lista completa de [CSPs de política compatíveis com o HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span><span class="sxs-lookup"><span data-stu-id="24191-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="24191-111">Métodos de configuração</span><span class="sxs-lookup"><span data-stu-id="24191-111">Configuration methods</span></span>

### <span data-ttu-id="24191-112">Configurar com o MDM</span><span class="sxs-lookup"><span data-stu-id="24191-112">Configure with MDM</span></span>

<span data-ttu-id="24191-113">Provedores e diretivas podem ser facilmente gerenciados em qualquer dispositivo pessoal ou corporativo registrado em um sistema MDM.</span><span class="sxs-lookup"><span data-stu-id="24191-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="24191-114">Depois que um dispositivo estiver registrado na sua solução MDM, você poderá gerenciá-lo ou definir dispositivos usando configurações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="24191-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="24191-115">Saiba mais sobre como [gerenciar seus dispositivos do HoloLens por meio do MDM](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="24191-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="24191-116">Configurar com pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="24191-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="24191-117">O HoloLens 2 também oferece suporte à configuração de um conjunto limitado de configurações de CSP para dispositivos do HoloLens 2 por meio de pacotes de provisionamento personalizados.</span><span class="sxs-lookup"><span data-stu-id="24191-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="24191-118">Os pacotes de provisionamento geralmente são aproveitados para dispositivos gerenciados não MDM e exigem que sejam aplicados manualmente a cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="24191-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="24191-119">Leia informações sobre a criação [de pacotes de aprovisionamento personalizados para o HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="24191-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="24191-120">Configurações</span><span class="sxs-lookup"><span data-stu-id="24191-120">Configurations</span></span>

### <span data-ttu-id="24191-121">Restrições comuns de dispositivo</span><span class="sxs-lookup"><span data-stu-id="24191-121">Common device restrictions</span></span>

<span data-ttu-id="24191-122">Algumas restrições de dispositivo são simples e desabilitam uma funcionalidade ou conexão com o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="24191-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="24191-123">Para saber mais sobre essas informações, leia mais sobre as [restrições comuns do dispositivo.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="24191-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="24191-124">Modos de quiosque</span><span class="sxs-lookup"><span data-stu-id="24191-124">Kiosk modes</span></span>

<span data-ttu-id="24191-125">Use o modo de quiosque para controlar quais identidades têm acesso a quais aplicativos por padrão.</span><span class="sxs-lookup"><span data-stu-id="24191-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="24191-126">Os quiosques podem ser usados para um único aplicativo ou uma experiência de interface do usuário de vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="24191-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="24191-127">Configurações do quiosque variam de um único aplicativo para qualquer pessoa que esteja usando o dispositivo, a seleções diferentes de aplicativos para grupos diferentes.</span><span class="sxs-lookup"><span data-stu-id="24191-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="24191-128">O modo de quiosque não interrompe "aplicativos permitidos" de iniciar outros aplicativos e não foi projetado para nunca.</span><span class="sxs-lookup"><span data-stu-id="24191-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="24191-129">Saiba mais em como [ler sobre modos de quiosque e como usá-los](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="24191-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="24191-130">Visibilidade da página Configurações</span><span class="sxs-lookup"><span data-stu-id="24191-130">Settings Page Visibility</span></span>

<span data-ttu-id="24191-131">Use a política de aplicativos de configurações para controlar quais identidades têm acesso às configurações por padrão.</span><span class="sxs-lookup"><span data-stu-id="24191-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="24191-132">Usando esta política, o aplicativo configurações pode ser configurado para mostrar apenas as páginas selecionadas ou ocultar todas as páginas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="24191-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="24191-133">[Leia sobre como configurar as páginas disponíveis](settings-uri-list.md).</span><span class="sxs-lookup"><span data-stu-id="24191-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="24191-134">No momento, esse recurso só está disponível em [compilações do Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="24191-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="24191-135">Certifique-se de que os dispositivos que você pretende usar nesse recurso estejam no Build 19041.1349 +.</span><span class="sxs-lookup"><span data-stu-id="24191-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="24191-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="24191-136">WDAC</span></span>

<span data-ttu-id="24191-137">Use a configuração WDAC para controlar quais aplicativos/processos são permitidos/despermitidos para serem iniciados independentemente de o sistema estar ou não no modo quiosque.</span><span class="sxs-lookup"><span data-stu-id="24191-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="24191-138">Veja nossa visão geral para WDAC.</span><span class="sxs-lookup"><span data-stu-id="24191-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
