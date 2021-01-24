---
title: Requisitos de Licença
description: Mantenha-se atualizado com todos os requisitos de licenciamento e diretrizes de que você precisa para gerenciamento de dispositivos móveis, HoloLens e Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283962"
---
# <span data-ttu-id="b9b1b-103">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="b9b1b-103">License requirements</span></span>

## <span data-ttu-id="b9b1b-104">Diretrizes de Licença do MDM (Sistema de Gerenciamento de Dispositivo Móvel)</span><span class="sxs-lookup"><span data-stu-id="b9b1b-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="b9b1b-105">Se planeja gerenciar dispositivos HoloLens, será necessário ter o Azure AD e um MDM.</span><span class="sxs-lookup"><span data-stu-id="b9b1b-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="b9b1b-106">O Active Directory (AD) não pode ser usado para gerenciar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9b1b-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="b9b1b-107">Se você planeja usar um MDM diferente do Intune, será necessário ter uma [Licença do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="b9b1b-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="b9b1b-108">Se você planeja usar o Intune como o seu MDM, leia a [lista de pacotes que incluem licenças do Intune](https://docs.microsoft.com/intune/fundamentals/licenses).</span><span class="sxs-lookup"><span data-stu-id="b9b1b-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> **<span data-ttu-id="b9b1b-109">Observe que o Microsoft Azure Active Directory está incluído na maioria desses pacotes.</span><span class="sxs-lookup"><span data-stu-id="b9b1b-109">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="b9b1b-110">Identifique as licenças necessárias para seu cenário e produtos</span><span class="sxs-lookup"><span data-stu-id="b9b1b-110">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="b9b1b-111">Requisitos de Licenças do HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="b9b1b-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="b9b1b-112">Talvez seja necessário atualizar o dispositivo HoloLens 1ª geração para o Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="b9b1b-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="b9b1b-113">(Confira os [recursos comerciais do HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para determinar se você precisa fazer atualizações).</span><span class="sxs-lookup"><span data-stu-id="b9b1b-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="b9b1b-114">Em caso afirmativo, você precisará fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b9b1b-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="b9b1b-115">Adquirir um arquivo XML de licença do HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9b1b-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="b9b1b-116">Aplicar o arquivo XML ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9b1b-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="b9b1b-117">É possível fazer isso através de um [Pacote de provisionamento](hololens-provisioning.md) ou através do [Gerenciador de Dispositivo Móvel](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="b9b1b-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="b9b1b-118">Requisitos da Licença da Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="b9b1b-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="b9b1b-119">Certifique-se de ter o licenciamento e o dispositivo necessários, que podem ser verificados na documentação de [requisitos](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="b9b1b-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="b9b1b-120">Licença de Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="b9b1b-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="b9b1b-121">Ou experimente a [avaliação do Assistente Remoto](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="b9b1b-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="b9b1b-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="b9b1b-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="b9b1b-123">Licença do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b9b1b-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="b9b1b-124">Se você planeja implementar **[esse cenário entre locatários](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, pode precisar de uma licença de Barreiras de Informações.</span><span class="sxs-lookup"><span data-stu-id="b9b1b-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="b9b1b-125">Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma licença de Barreira de Informações.</span><span class="sxs-lookup"><span data-stu-id="b9b1b-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="b9b1b-126">Requisitos de Licença de Guias</span><span class="sxs-lookup"><span data-stu-id="b9b1b-126">Guides License Requirements</span></span>

<span data-ttu-id="b9b1b-127">Confira os [requisitos de licenciamento e dispositivo atualizados.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)</span><span class="sxs-lookup"><span data-stu-id="b9b1b-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="b9b1b-128">Licença do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b9b1b-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="b9b1b-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="b9b1b-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="b9b1b-130">Guias</span><span class="sxs-lookup"><span data-stu-id="b9b1b-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
