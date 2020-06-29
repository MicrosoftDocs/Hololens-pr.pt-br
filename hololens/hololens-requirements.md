---
title: Configurar o HoloLens em um ambiente comercial
description: Saiba mais sobre a implantação e o gerenciamento do HoloLens em ambientes empresariais.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: 8aa8e0f679ad18a2e47f34c5f1233435a502dc0c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830125"
---
# <span data-ttu-id="5d67d-103">Implantar o HoloLens em um ambiente comercial</span><span class="sxs-lookup"><span data-stu-id="5d67d-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="5d67d-104">Você pode implantar e configurar o HoloLens em escala em uma configuração comercial.</span><span class="sxs-lookup"><span data-stu-id="5d67d-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="5d67d-105">Este artigo fornece instruções para a implantação de dispositivos HoloLens em um ambiente comercial.</span><span class="sxs-lookup"><span data-stu-id="5d67d-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="5d67d-106">Este guia pressupõe familiaridade básica com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5d67d-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="5d67d-107">Siga o [Guia de introdução](hololens1-setup.md) para configurar o HoloLens pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="5d67d-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="5d67d-108">Este documento também pressupõe que o HoloLens foi avaliado por equipes de segurança como seguras para uso na rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="5d67d-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span> <span data-ttu-id="5d67d-109">Perguntas frequentes de segurança podem ser encontradas [aqui](hololens-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="5d67d-109">Frequently asked security questions can be found [here](hololens-faq-security.md)</span></span>

## <span data-ttu-id="5d67d-110">Visão geral das etapas de implantação</span><span class="sxs-lookup"><span data-stu-id="5d67d-110">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="5d67d-111">Determinar quais recursos você precisa</span><span class="sxs-lookup"><span data-stu-id="5d67d-111">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="5d67d-112">Determinar quais são as licenças necessárias</span><span class="sxs-lookup"><span data-stu-id="5d67d-112">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="5d67d-113">[Configurar sua rede para o HoloLens](hololens-commercial-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="5d67d-113">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="5d67d-114">Esta seção inclui requisitos de largura de banda, URL e portas que precisam ser permitidos no seu firewall; Orientação do Azure AD; Orientação sobre o gerenciamento de dispositivos móveis (MDM); Diretrizes de implantação/gerenciamento de aplicativos; e a orientação do certificado.</span><span class="sxs-lookup"><span data-stu-id="5d67d-114">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="5d67d-115">Adicionais [Configurar o HoloLens usando um pacote de provisionamento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="5d67d-115">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="5d67d-116">Registrar dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d67d-116">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="5d67d-117">Configurar atualizações com base em anel para HoloLens</span><span class="sxs-lookup"><span data-stu-id="5d67d-117">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="5d67d-118">Habilitar criptografia de dispositivo do Bitlocker para HoloLens</span><span class="sxs-lookup"><span data-stu-id="5d67d-118">Enable Bitlocker device encryption for HoloLens</span></span>](hololens-encryption.md)

## <span data-ttu-id="5d67d-119">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="5d67d-119">Step 1.</span></span> <span data-ttu-id="5d67d-120">Determinar o que você precisa</span><span class="sxs-lookup"><span data-stu-id="5d67d-120">Determine what you need</span></span>

<span data-ttu-id="5d67d-121">Antes de implantar o HoloLens em seu ambiente, é importante determinar quais recursos, aplicativos e tipos de identidade são necessários primeiro.</span><span class="sxs-lookup"><span data-stu-id="5d67d-121">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="5d67d-122">Também é importante garantir que sua equipe de segurança tenha aprovado pelo uso do HoloLens na rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="5d67d-122">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="5d67d-123">Consulte perguntas [frequentes](hololens-faq-security.md) sobre segurança para obter informações adicionais sobre segurança.</span><span class="sxs-lookup"><span data-stu-id="5d67d-123">Please see [Frequently ask security questions](hololens-faq-security.md) for additional security information.</span></span>

### <span data-ttu-id="5d67d-124">Tipo de identidade</span><span class="sxs-lookup"><span data-stu-id="5d67d-124">Type of Identity</span></span>

<span data-ttu-id="5d67d-125">Determine o tipo de identidade que será usado para entrar no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d67d-125">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="5d67d-126">**Contas locais:** Essa conta é local para o dispositivo (como uma conta de administrador local em um computador Windows).</span><span class="sxs-lookup"><span data-stu-id="5d67d-126">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="5d67d-127">Isso permitirá que apenas 1 usuário conecte-se ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d67d-127">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="5d67d-128">**MSA:** Esta é uma conta pessoal (como o Outlook, o hotmail, o Gmail, o Yahoo, etc.) Isso permitirá que apenas 1 usuário conecte-se ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d67d-128">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="5d67d-129">**Contas do Azure Active Directory (Azure AD):** Esta é uma conta criada no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5d67d-129">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="5d67d-130">Isso concede à sua empresa a capacidade de gerenciar o dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5d67d-130">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="5d67d-131">Isso permitirá que vários usuários conectem-se ao pacote comercial do HoloLens da 1ª Gen/do dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5d67d-131">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="5d67d-132">Para obter informações mais detalhadas sobre os tipos de identidade, acesse nosso artigo de [identidade do HoloLens](hololens-identity.md) .</span><span class="sxs-lookup"><span data-stu-id="5d67d-132">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="5d67d-133">Tipo de recursos</span><span class="sxs-lookup"><span data-stu-id="5d67d-133">Type of Features</span></span>

<span data-ttu-id="5d67d-134">Seus requisitos de recursos determinarão o HoloLens que você precisa.</span><span class="sxs-lookup"><span data-stu-id="5d67d-134">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="5d67d-135">Um recurso conhecido que vemos implantar em ambientes de cliente com frequência é o modo de quiosque.</span><span class="sxs-lookup"><span data-stu-id="5d67d-135">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="5d67d-136">Uma lista de recursos chave do HoloLens e as edições do HoloLens que dão suporte a eles podem ser encontradas [aqui](hololens-commercial-features.md).</span><span class="sxs-lookup"><span data-stu-id="5d67d-136">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="5d67d-137">O que é o modo de quiosque?</span><span class="sxs-lookup"><span data-stu-id="5d67d-137">What is Kiosk Mode?</span></span>**

<span data-ttu-id="5d67d-138">O modo de quiosque é uma maneira de restringir os aplicativos aos quais um usuário tem acesso.</span><span class="sxs-lookup"><span data-stu-id="5d67d-138">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="5d67d-139">Isso significa que os usuários só poderão acessar determinados aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5d67d-139">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="5d67d-140">Qual é o modo de quiosque necessário?</span><span class="sxs-lookup"><span data-stu-id="5d67d-140">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="5d67d-141">Há dois tipos de modos de quiosque: aplicativo único e vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5d67d-141">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="5d67d-142">O modo de quiosque de aplicativo único permite que o usuário acesse apenas um aplicativo enquanto o modo de quiosque de vários aplicativos permite que os usuários acessem vários aplicativos especificados.</span><span class="sxs-lookup"><span data-stu-id="5d67d-142">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="5d67d-143">Para determinar qual é o modo de quiosque correto para sua empresa, as duas perguntas a seguir precisam ser respondidas:</span><span class="sxs-lookup"><span data-stu-id="5d67d-143">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="5d67d-144">Os diferentes usuários exigem experiências/restrições diferentes?</span><span class="sxs-lookup"><span data-stu-id="5d67d-144">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="5d67d-145">Considere o exemplo a seguir: o usuário A é um engenheiro de serviços de campo que só precisa de acesso à assistência remota.</span><span class="sxs-lookup"><span data-stu-id="5d67d-145">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="5d67d-146">O usuário B é um estagiário que só precisa de acesso a guias.</span><span class="sxs-lookup"><span data-stu-id="5d67d-146">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="5d67d-147">Em caso afirmativo, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d67d-147">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="5d67d-148">Contas do Azure AD como o método de inscrição no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d67d-148">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="5d67d-149">Modo **de quiosque de vários aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="5d67d-149">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="5d67d-150">Se não, continue com a pergunta dois</span><span class="sxs-lookup"><span data-stu-id="5d67d-150">If no, continue to question two</span></span>
1. **<span data-ttu-id="5d67d-151">Você precisa de experiência com vários aplicativos?</span><span class="sxs-lookup"><span data-stu-id="5d67d-151">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="5d67d-152">Se sim, o quiosque **de vários aplicativos** é o modo necessário</span><span class="sxs-lookup"><span data-stu-id="5d67d-152">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="5d67d-153">Se a sua resposta para as perguntas 1 e 2 não for o modo de quiosque de **aplicativo único** pode ser usado</span><span class="sxs-lookup"><span data-stu-id="5d67d-153">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="5d67d-154">Como configurar o modo de quiosque:</span><span class="sxs-lookup"><span data-stu-id="5d67d-154">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="5d67d-155">Há duas maneiras principais ([pacotes de provisionamento](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) para implantar o modo de quiosque para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5d67d-155">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="5d67d-156">Essas opções serão discutidas mais tarde no documento; no entanto, você pode usar os links acima para saltar para as respectivas seções neste documento.</span><span class="sxs-lookup"><span data-stu-id="5d67d-156">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="5d67d-157">Aplicativos e cenários específicos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="5d67d-157">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="5d67d-158">A maioria das etapas encontradas neste documento também será aplicada aos seguintes aplicativos:</span><span class="sxs-lookup"><span data-stu-id="5d67d-158">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="5d67d-159">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5d67d-159">App</span></span> | <span data-ttu-id="5d67d-160">Cenários específicos do aplicativo</span><span class="sxs-lookup"><span data-stu-id="5d67d-160">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="5d67d-161">Assistência remota</span><span class="sxs-lookup"><span data-stu-id="5d67d-161">Remote Assist</span></span> | [<span data-ttu-id="5d67d-162">Comunicação entre os locatários</span><span class="sxs-lookup"><span data-stu-id="5d67d-162">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="5d67d-163">Guias</span><span class="sxs-lookup"><span data-stu-id="5d67d-163">Guides</span></span>  | *<span data-ttu-id="5d67d-164">Em breve</span><span class="sxs-lookup"><span data-stu-id="5d67d-164">Coming Soon</span></span>* |
|<span data-ttu-id="5d67d-165">Aplicativos personalizados</span><span class="sxs-lookup"><span data-stu-id="5d67d-165">Custom Apps</span></span> | *<span data-ttu-id="5d67d-166">Em breve</span><span class="sxs-lookup"><span data-stu-id="5d67d-166">Coming Soon</span></span>* |

### <span data-ttu-id="5d67d-167">Determinar o método de registro</span><span class="sxs-lookup"><span data-stu-id="5d67d-167">Determine your enrollment method</span></span>

1. <span data-ttu-id="5d67d-168">Registro em massa com um token de segurança em um pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="5d67d-168">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="5d67d-169">Prós: esta é a abordagem mais automatizada </span><span class="sxs-lookup"><span data-stu-id="5d67d-169">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="5d67d-170">Desvantagens: retira a configuração inicial do lado do servidor</span><span class="sxs-lookup"><span data-stu-id="5d67d-170">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="5d67d-171">Inscrição automática na entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="5d67d-171">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="5d67d-172">Prós: abordagem mais fácil</span><span class="sxs-lookup"><span data-stu-id="5d67d-172">Pros: easiest approach</span></span>  
  <span data-ttu-id="5d67d-173">Contras: os usuários precisarão concluir a configuração após a aplicação do pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="5d67d-173">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="5d67d-174">_não recomendado_ -Registre a pós-instalação manualmente.</span><span class="sxs-lookup"><span data-stu-id="5d67d-174">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="5d67d-175">Prós: possível se inscrever após a configuração</span><span class="sxs-lookup"><span data-stu-id="5d67d-175">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="5d67d-176">Desvantagens: a maioria dos dispositivos e a abordagem manual não são gerenciáveis de maneira centralizada até que sejam manualmente registrados.</span><span class="sxs-lookup"><span data-stu-id="5d67d-176">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="5d67d-177">Mais informações podem ser encontradas [aqui](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="5d67d-177">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="5d67d-178">Determinar se você precisa criar um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="5d67d-178">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="5d67d-179">Há dois métodos para configurar um dispositivo HoloLens (pacotes de provisionamento e MDMs).</span><span class="sxs-lookup"><span data-stu-id="5d67d-179">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="5d67d-180">Sugerimos usar o MDM para configurar seu dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5d67d-180">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="5d67d-181">No entanto, há alguns cenários em que usar um pacote de provisionamento é a melhor opção:</span><span class="sxs-lookup"><span data-stu-id="5d67d-181">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="5d67d-182">Você deseja configurar o HoloLens para ignorar a experiência inicial (OOBE)</span><span class="sxs-lookup"><span data-stu-id="5d67d-182">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="5d67d-183">Você está tendo problemas para implantar o certificado em uma rede complexa.</span><span class="sxs-lookup"><span data-stu-id="5d67d-183">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="5d67d-184">Na maioria das vezes, você pode implantar certificados usando o MDM (mesmo em ambientes complexos).</span><span class="sxs-lookup"><span data-stu-id="5d67d-184">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="5d67d-185">No entanto, alguns cenários exigem que os certificados sejam implantados por meio do pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="5d67d-185">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="5d67d-186">Algumas das configurações do HoloLens que é possível aplicar em um pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="5d67d-186">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="5d67d-187">Aplicar certificados ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d67d-187">Apply certificates to the device</span></span>
- <span data-ttu-id="5d67d-188">Configurar uma conexão Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="5d67d-188">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="5d67d-189">Pré-configurar as caixas de perguntas, como idioma e localidade</span><span class="sxs-lookup"><span data-stu-id="5d67d-189">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="5d67d-190">(HoloLens 2) Registrar-se em massa no gerenciamento de dispositivo móvel </span><span class="sxs-lookup"><span data-stu-id="5d67d-190">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="5d67d-191">(HoloLens v1) Aplicar chave para habilitar o Holographic for Business do Windows</span><span class="sxs-lookup"><span data-stu-id="5d67d-191">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="5d67d-192">Se você decidir usar pacotes de provisionamento, siga [este guia](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="5d67d-192">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="5d67d-193">Obter suporte</span><span class="sxs-lookup"><span data-stu-id="5d67d-193">Get support</span></span>

<span data-ttu-id="5d67d-194">Obtenha suporte por meio do site de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d67d-194">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="5d67d-195">Arquivar uma solicitação de suporte</span><span class="sxs-lookup"><span data-stu-id="5d67d-195">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
