---
title: Acesso Global Atribuído
description: Guia de como usar o OMA-URI para quiosques de Acesso Global Atribuído
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c2be1123d0e8a09d6955fb6e5da782daebc96bcf
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052620"
---
# <span data-ttu-id="fa0fb-104">Acesso Global Atribuído – Quiosque</span><span class="sxs-lookup"><span data-stu-id="fa0fb-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="fa0fb-105">Esse recurso configura o dispositivo Hololens 2 para o modo de quiosque para vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todas as pessoas que se inscrevem no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa0fb-106">No momento, esse recurso só é disponível na compilação do Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="fa0fb-107">Se você deseja testar esse recurso antes que ele seja geralmente disponível nas versões do HoloLens, leia mais sobre compilações do[Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="fa0fb-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="fa0fb-108">Como usar isso no Intune?</span><span class="sxs-lookup"><span data-stu-id="fa0fb-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="fa0fb-109">Lembre-se das áreas marcadas com "<!-".</span><span class="sxs-lookup"><span data-stu-id="fa0fb-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="fa0fb-110">Essas áreas exigem que você faça modificações baseadas nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="fa0fb-111">Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte maneira e aplique-o ao grupo de dispositivos do HoloLens: ![Acesso Global Atribuído ao OMA-URI no Intune</span><span class="sxs-lookup"><span data-stu-id="fa0fb-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="fa0fb-112">Para obter o valor, atualize e cole o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-112">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="fa0fb-113">Como usar esse suplemento no Designer de Configuração do Windows?</span><span class="sxs-lookup"><span data-stu-id="fa0fb-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="fa0fb-114">Atualize e salve o blob XML mencionado acima como arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="fa0fb-115">Siga as etapas em [Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou vários aplicativos](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a seção “pacote</span><span class="sxs-lookup"><span data-stu-id="fa0fb-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="fa0fb-116">de provisionamento, etapa 2 – Adicionar o arquivo XML de configuração do Kiosk a um pacote de provisionamento” e consultar o arquivo XML que foi salvo na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="fa0fb-117">Posso criar uma configuração em que o acesso global se aplica a todos, e configurações separadas se apliquem a 1 conta AAD ou grupo AAD?</span><span class="sxs-lookup"><span data-stu-id="fa0fb-117">Can I create a configuration where global applies to everyone and separate configuration applies to 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="fa0fb-118">Sim, consulte o exemplo de blob XML abaixo.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="fa0fb-119">Os perfis de Acesso Global Atribuídos são aplicados no Hololens quando um perfil determinado para o usuário conectado não é encontrado, portanto, é a configuração padrão de modo de quiosque para o usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="fa0fb-120">Aqui está um exemplo de blob XML a ser usado:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="fa0fb-121">Lembre-se das áreas destacadas marcadas com <!- pois essas áreas exigem que você faça modificações com base nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-121">Please be aware of the highlighted areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="fa0fb-122">Excluindo DeviceOwners do perfil de acesso global atribuído</span><span class="sxs-lookup"><span data-stu-id="fa0fb-122">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="fa0fb-123">Esse recurso permite a um usuário que é considerado "[Proprietário do dispositivo](security-adminless-os.md)" no Hololens de ser excluído do acesso global atribuído.</span><span class="sxs-lookup"><span data-stu-id="fa0fb-123">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="fa0fb-124">Para aproveitar esse recurso, no blob XML para a configuração do Kiosk de vários aplicativos, certifique-se de que as linhas destacadas sejam adicionadas:</span><span class="sxs-lookup"><span data-stu-id="fa0fb-124">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
