---
title: Acesso Global Atribuído
description: Comece com nosso guia para usar OMA-URI para Quiosques de Acesso Atribuídos Globais com Intune e designer de configuração do Windows.
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
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283172"
---
# <span data-ttu-id="e9408-104">Acesso Global Atribuído – Quiosque</span><span class="sxs-lookup"><span data-stu-id="e9408-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="e9408-105">Este recurso configura o dispositivo HoloLens 2 para o modo quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todos que fazem login no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9408-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="e9408-106">Esse recurso só está disponível em compilações do Participante do Programa Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="e9408-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="e9408-107">Se você quiser experimentar esse recurso antes que ele esteja disponível em lançamentos do HoloLens, leia mais sobre as compilações do [Participante do Programa Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="e9408-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <span data-ttu-id="e9408-108">Como usar o Acesso Atribuído Global no Intune?</span><span class="sxs-lookup"><span data-stu-id="e9408-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="e9408-109">Lembre-se das áreas marcadas com "<!-".</span><span class="sxs-lookup"><span data-stu-id="e9408-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="e9408-110">Essas áreas exigem que você faça modificações baseadas nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="e9408-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="e9408-111">Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte maneira e aplique-o ao grupo de dispositivos do HoloLens:</span><span class="sxs-lookup"><span data-stu-id="e9408-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="e9408-112">Valor do URI:. Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="e9408-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > ![Acesso global atribuído a OMA-URI no Intune](images/global-assigned-access-omauri.png)

2. <span data-ttu-id="e9408-114">Para obter o valor, atualize e cole o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="e9408-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="e9408-115">Como usar o Acesso Atribuído Global no Designer de Configuração do Windows?</span><span class="sxs-lookup"><span data-stu-id="e9408-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="e9408-116">Atualize e salve o blob XML mencionado acima como arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="e9408-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="e9408-117">Siga as etapas em [Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou vários aplicativos](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a seção “pacote</span><span class="sxs-lookup"><span data-stu-id="e9408-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="e9408-118">de provisionamento, etapa 2 – Adicionar o arquivo XML de configuração do Kiosk a um pacote de provisionamento” e consultar o arquivo XML que foi salvo na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e9408-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <span data-ttu-id="e9408-119">Posso criar uma configuração na qual todas as pessoas e configurações separadas aplicam-se à 1 conta do Azure AD ou ao grupo do Microsoft Azure Active Directory?</span><span class="sxs-lookup"><span data-stu-id="e9408-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="e9408-120">Sim, consulte o exemplo de blob XML abaixo.</span><span class="sxs-lookup"><span data-stu-id="e9408-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="e9408-121">O perfil de Acesso Atribuído Global é aplicado no HoloLens quando um perfil específico para o usuário conectado não é encontrado, portanto, é a configuração do modo quiosque padrão para o usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="e9408-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="e9408-122">Aqui está um exemplo de blob XML a ser usado:</span><span class="sxs-lookup"><span data-stu-id="e9408-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="e9408-123">Lembre-se das áreas realçadas marcadas com `<!-`.</span><span class="sxs-lookup"><span data-stu-id="e9408-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="e9408-124">Essas áreas exigem que você faça modificações baseadas nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="e9408-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="e9408-125">Excluindo DeviceOwners do perfil de acesso global atribuído</span><span class="sxs-lookup"><span data-stu-id="e9408-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="e9408-126">Esse recurso permite que um usuário considerado "[Proprietário do dispositivo](security-adminless-os.md)" no HoloLens seja excluído do Acesso Atribuído Global.</span><span class="sxs-lookup"><span data-stu-id="e9408-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="e9408-127">Para aproveitar esse recurso, no blob XML para a configuração do Kiosk de vários aplicativos, certifique-se de que as linhas destacadas sejam adicionadas:</span><span class="sxs-lookup"><span data-stu-id="e9408-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <span data-ttu-id="e9408-128">Exemplos adicionais de Acesso Global Atribuído</span><span class="sxs-lookup"><span data-stu-id="e9408-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="e9408-129">Este é um exemplo de quiosque de Acesso Atribuído Global que, quando qualquer usuário entrar, terá um quiosque de vários aplicativos com o aplicativo Configurações, Hub de Comentários e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="e9408-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="e9408-130">Este exemplo é um quiosque de Acesso Atribuído Global que exclui o proprietário do dispositivo, quando qualquer outro usuário do Microsoft Azure Active Directory entrar, ele terá um quiosque de vários aplicativos com o aplicativo de Configurações, Hub de comentários e Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="e9408-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="e9408-131">Esse quiosque também inclui uma configuração de quiosque secundária para uma Conta de visitante, que pode ser conectada por qualquer pessoa na tela de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="e9408-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="e9408-132">Quando um usuário entra na conta de Visitante, ele terá um quiosque de vários aplicativos que tem apenas o aplicativo de Hub de Feedback.</span><span class="sxs-lookup"><span data-stu-id="e9408-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
