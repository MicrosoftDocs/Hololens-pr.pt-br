---
title: Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs
description: Saiba como configurar CSPs, política e gerenciamento de dispositivos usando o Gerenciamento de Dispositivo Móvel e pacotes de provisionamento.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283242"
---
# <span data-ttu-id="99cb5-103">Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs</span><span class="sxs-lookup"><span data-stu-id="99cb5-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="99cb5-104">Os administradores de IT podem definir e implementar configurações de política no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="99cb5-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="99cb5-105">As configurações que você usa serão diferentes de acordo com o cenário de implantação, e os dispositivos corporativos oferecerão à TI um controle mais amplo.</span><span class="sxs-lookup"><span data-stu-id="99cb5-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="99cb5-106">No Windows 10, os Provedores de Serviços de Configuração (CSP) são uma interface para ler, definir, modificar ou excluir definições de configuração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99cb5-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="99cb5-107">Essas configurações mapeiam para arquivos ou chaves do Registro.</span><span class="sxs-lookup"><span data-stu-id="99cb5-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="99cb5-108">Alguns provedores de serviços de configuração suportam o formato WAP, alguns suportam SyncML e alguns suportam ambos.</span><span class="sxs-lookup"><span data-stu-id="99cb5-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="99cb5-109">Para obter mais informações sobre CSPs de gerenciamento de dispositivos holográficos do Windows 10, consulte a lista completa de CSPs com suporte em [dispositivos HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="99cb5-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="99cb5-110">Os administradores de IT também podem gerenciar csp de política em dispositivos, consulte a lista completa de CSPs de política com suporte [pelo HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span><span class="sxs-lookup"><span data-stu-id="99cb5-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="99cb5-111">Métodos de configuração</span><span class="sxs-lookup"><span data-stu-id="99cb5-111">Configuration methods</span></span>

### <span data-ttu-id="99cb5-112">Configurar com MDM</span><span class="sxs-lookup"><span data-stu-id="99cb5-112">Configure with MDM</span></span>

<span data-ttu-id="99cb5-113">CSPs e Políticas podem ser facilmente gerenciados em qualquer dispositivo pessoal ou corporativo inscrito em um sistema MDM.</span><span class="sxs-lookup"><span data-stu-id="99cb5-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="99cb5-114">Depois que um dispositivo for inscrito em sua solução MDM, você poderá gerenciar esse dispositivo ou um conjunto de dispositivos usando configurações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99cb5-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="99cb5-115">Saiba mais sobre como gerenciar [seus dispositivos HoloLens por meio do MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="99cb5-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="99cb5-116">Configurar com pacotes de provisionamento</span><span class="sxs-lookup"><span data-stu-id="99cb5-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="99cb5-117">O HoloLens 2 também dá suporte à definição de um conjunto limitado de configurações de CSP para dispositivos HoloLens 2 por meio de Pacotes de Provisionamento personalizados.</span><span class="sxs-lookup"><span data-stu-id="99cb5-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="99cb5-118">Os pacotes de provisionamento são geralmente aproveitados para dispositivos gerenciados não MDM e precisam ser aplicados manualmente a cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99cb5-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="99cb5-119">Leia as informações sobre como criar pacotes [de provisionamento personalizados para HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="99cb5-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="99cb5-120">Configurações</span><span class="sxs-lookup"><span data-stu-id="99cb5-120">Configurations</span></span>

### <span data-ttu-id="99cb5-121">Restrições comuns de dispositivos</span><span class="sxs-lookup"><span data-stu-id="99cb5-121">Common device restrictions</span></span>

<span data-ttu-id="99cb5-122">Algumas restrições de dispositivo são tão simples quanto desabilitar uma funcionalidade ou conexão com o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99cb5-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="99cb5-123">Para saber mais sobre eles, leia mais sobre [restrições comuns de dispositivos.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="99cb5-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="99cb5-124">Modos de quiosque</span><span class="sxs-lookup"><span data-stu-id="99cb5-124">Kiosk modes</span></span>

<span data-ttu-id="99cb5-125">Use o modo quiosque para controlar quais identidades têm acesso a quais aplicativos por padrão.</span><span class="sxs-lookup"><span data-stu-id="99cb5-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="99cb5-126">Os quiosques podem ser usados para um único aplicativo ou experiência de interface do usuário de vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="99cb5-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="99cb5-127">As configurações de quiosque variam de um único aplicativo para qualquer pessoa que usa o dispositivo até seleções diferentes de aplicativos para grupos diferentes.</span><span class="sxs-lookup"><span data-stu-id="99cb5-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="99cb5-128">O modo de quiosque não impede que "aplicativos permitidos" iniciam outros aplicativos e não foi planejado para nunca.</span><span class="sxs-lookup"><span data-stu-id="99cb5-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="99cb5-129">Saiba mais lendo [sobre modos de quiosque e como usá-los.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="99cb5-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="99cb5-130">Visibilidade da página de configurações</span><span class="sxs-lookup"><span data-stu-id="99cb5-130">Settings Page Visibility</span></span>

<span data-ttu-id="99cb5-131">Use a política de aplicativo Configurações para controlar quais identidades têm acesso às configurações por padrão.</span><span class="sxs-lookup"><span data-stu-id="99cb5-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="99cb5-132">Usando essa política, o aplicativo Configurações pode ser configurado para mostrar somente as páginas selecionadas ou ocultar todas as páginas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="99cb5-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="99cb5-133">[Leia sobre como configurar as páginas disponíveis.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="99cb5-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="99cb5-134">No momento, esse recurso só está disponível em [builds do Windows Insider.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="99cb5-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="99cb5-135">Certifique-se de que os dispositivos para os que você pretende usar esse recurso estão no build 19041.1349+.</span><span class="sxs-lookup"><span data-stu-id="99cb5-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="99cb5-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="99cb5-136">WDAC</span></span>

<span data-ttu-id="99cb5-137">Use a configuração do WDAC para controlar quais aplicativos/processos são permitidos/não podem ser lançados independentemente de o sistema estar ou não no modo de quiosque.</span><span class="sxs-lookup"><span data-stu-id="99cb5-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="99cb5-138">Consulte nossa visão geral do WDAC.</span><span class="sxs-lookup"><span data-stu-id="99cb5-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
