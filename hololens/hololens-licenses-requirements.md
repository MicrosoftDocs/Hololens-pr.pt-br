---
title: Requisitos de Licença
description: ''
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
ms.openlocfilehash: 3ac86512755620ebb6159dd4d845b488e203dbad
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956757"
---
# <span data-ttu-id="c917b-102">Requisitos de Licença</span><span class="sxs-lookup"><span data-stu-id="c917b-102">License requirements</span></span>

## <span data-ttu-id="c917b-103">Diretrizes de Licença do MDM (Sistema de Gerenciamento de Dispositivo Móvel)</span><span class="sxs-lookup"><span data-stu-id="c917b-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="c917b-104">Se planeja gerenciar dispositivos HoloLens, será necessário ter o Azure AD e um MDM.</span><span class="sxs-lookup"><span data-stu-id="c917b-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="c917b-105">O Active Directory (AD) não pode ser usado para gerenciar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c917b-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="c917b-106">Se você planeja usar um MDM diferente do Intune, será necessário ter uma [Licença do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="c917b-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="c917b-107">Se você planeja usar o Intune como o seu MDM, veja [aqui](https://docs.microsoft.com/intune/fundamentals/licenses) uma lista de pacotes que incluem licenças do Intune.</span><span class="sxs-lookup"><span data-stu-id="c917b-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="c917b-108">Observe que o Azure AD está incluído na maioria desses pacotes.</span><span class="sxs-lookup"><span data-stu-id="c917b-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="c917b-109">Identifique as licenças necessárias para seu cenário e produtos</span><span class="sxs-lookup"><span data-stu-id="c917b-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="c917b-110">Requisitos de Licenças do HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="c917b-110">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="c917b-111">Talvez seja necessário atualizar o dispositivo HoloLens 1ª geração para o Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="c917b-111">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="c917b-112">(Confira os [recursos comerciais do HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para determinar se você precisa fazer atualizações).</span><span class="sxs-lookup"><span data-stu-id="c917b-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="c917b-113">Em caso afirmativo, você precisará fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c917b-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="c917b-114">Adquirir um arquivo XML de licença do HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="c917b-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="c917b-115">Aplicar o arquivo XML ao HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c917b-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="c917b-116">É possível fazer isso através de um [Pacote de provisionamento](hololens-provisioning.md) ou através do [Gerenciador de Dispositivo Móvel](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="c917b-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="c917b-117">Requisitos da Licença da Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="c917b-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="c917b-118">Verifique se você tem o licenciamento e o dispositivo necessários.</span><span class="sxs-lookup"><span data-stu-id="c917b-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="c917b-119">O licenciamento atualizado e os requisitos do produto podem ser encontrados [aqui](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span><span class="sxs-lookup"><span data-stu-id="c917b-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="c917b-120">Licença de Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="c917b-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="c917b-121">Ou experimente a [avaliação do Assistente Remoto](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="c917b-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="c917b-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="c917b-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="c917b-123">Licença do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c917b-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="c917b-124">Se você planeja implementar **[esse cenário entre locatários](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, pode precisar de uma licença de Barreiras de Informações.</span><span class="sxs-lookup"><span data-stu-id="c917b-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="c917b-125">Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma licença de Barreira de Informações.</span><span class="sxs-lookup"><span data-stu-id="c917b-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="c917b-126">Requisitos de Licença de Guias</span><span class="sxs-lookup"><span data-stu-id="c917b-126">Guides License Requirements</span></span>

<span data-ttu-id="c917b-127">O licenciamento atualizado e os requisitos do dispositivo podem ser encontrados [aqui](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span><span class="sxs-lookup"><span data-stu-id="c917b-127">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="c917b-128">Licença do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c917b-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="c917b-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="c917b-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="c917b-130">Guias</span><span class="sxs-lookup"><span data-stu-id="c917b-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
