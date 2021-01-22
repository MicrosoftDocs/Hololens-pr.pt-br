---
title: Guia de Implantação – implantação do HoloLens 2 conectada à nuvem em escala com Assistência Remota - Manutenção
description: Mantenha-se atualizado com nossas dicas para manter e dar suporte a dispositivos HoloLens em uma rede conectada à nuvem.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283892"
---
# <span data-ttu-id="e8250-104">Manutenção - Guia conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="e8250-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="e8250-105">Atualizações</span><span class="sxs-lookup"><span data-stu-id="e8250-105">Updates</span></span>

<span data-ttu-id="e8250-106">A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.</span><span class="sxs-lookup"><span data-stu-id="e8250-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="e8250-107">Saiba como gerenciar as atualizações do [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) incluindo dias agendados, horário agendado e configuração do horário ativo no dispositivo para que ele seja atualizado fora do horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e8250-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="e8250-108">A Assistência Remota é um In-Box e pode ser atualizada por meio do aplicativo da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e8250-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="e8250-109">Para todos os aplicativos baixados por meio da Microsoft Store, eles podem ser atualizados manualmente por meio do [próprio aplicativo da Microsoft Store.](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps)</span><span class="sxs-lookup"><span data-stu-id="e8250-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="e8250-110">Plano de Suporte</span><span class="sxs-lookup"><span data-stu-id="e8250-110">Support Plan</span></span>

<span data-ttu-id="e8250-111">Um plano de suporte é uma excelente coisa a ser realizada.</span><span class="sxs-lookup"><span data-stu-id="e8250-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="e8250-112">Ter alguém ou um grupo treinado para solucionar problemas do processo de inscrição em dispositivos HoloLens e também o uso geral do dispositivo HoloLens em sua organização é útil.</span><span class="sxs-lookup"><span data-stu-id="e8250-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="e8250-113">Para permitir que os usuários tenham a resolução mais rápida dos problemas, sugerimos que o processo de escalonamento seja tratado de maneira semelhante a esta ordem:</span><span class="sxs-lookup"><span data-stu-id="e8250-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="e8250-114">Seu suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e8250-114">Your Support desk.</span></span>
2. <span data-ttu-id="e8250-115">Sua equipe de especialistas do HoloLens</span><span class="sxs-lookup"><span data-stu-id="e8250-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="e8250-116">[Documentos do HoloLens](https://docs.microsoft.com/hololens/)  /  [Documentos de solução de problemas do HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="e8250-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="e8250-117">Contate o Suporte</span><span class="sxs-lookup"><span data-stu-id="e8250-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="e8250-118">Plano de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="e8250-118">Development Plan</span></span>

<span data-ttu-id="e8250-119">Com seu dispositivo registrado com êxito, agora você está preparado para implantar aplicativos de linha de negócios (aplicativos LOB) em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8250-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="e8250-120">Esses são aplicativos personalizados criado para a sua&#39;necessidades.</span><span class="sxs-lookup"><span data-stu-id="e8250-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="e8250-121">Se você já tiver um aplicativo de linha de negócios,&#39;está pronto para implantar seu [aplicativo por meio do MDM.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="e8250-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="e8250-122">Se você&#39;um método diferente, revise a visão geral da implantação do aplicativo para [o HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para saber mais métodos de implantação do aplicativo LOB em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8250-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="e8250-123">Se você&#39;criou seu próprio aplicativo LOB ou ainda está em processo de criação, revise nossos documentos de desenvolvimento de realidade misturada para começar a [projetar](https://docs.microsoft.com/windows/mixed-reality/design/design) e criar protótipos ou aprender os principais conceitos para começar com o desenvolvimento de realidade [misturada.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="e8250-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="e8250-124">Gerenciamento de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="e8250-124">Device Management</span></span> 

<span data-ttu-id="e8250-125">Embora este guia tenha falado sobre como configurar o Gerenciamento de Dispositivo Móvel (MDM), ele não foi empregado para aplicar restrições de dispositivo ou políticas foram aplicadas a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8250-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="e8250-126">O gerenciamento de dispositivos pode ser usado para permitir o acesso por meio de certificados por solicitação ou restringir o acesso com uma variedade de restrições de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8250-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="e8250-127">Em muitos casos, os dispositivos podem ter restrições de conectividade, como Bluetooth, VPN, USB ou até mesmo desligar o acesso à câmera ou microfone.</span><span class="sxs-lookup"><span data-stu-id="e8250-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="e8250-128">Se qualquer um desses interesses, recomendamos que você leia nossa página [de restrições de dispositivos comuns.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="e8250-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="e8250-129">Há outras restrições de dispositivo mais complexas que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="e8250-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="e8250-130">Como:</span><span class="sxs-lookup"><span data-stu-id="e8250-130">Such as:</span></span>

- <span data-ttu-id="e8250-131">Limitar as páginas que podem ser exibidas no aplicativo Configurações usando [SettingsPageVisibility](settings-uri-list.md), permitindo que os usuários acessem apenas as configurações que precisam ajustar, como alterar sua conexão Wi-Fi usuário.</span><span class="sxs-lookup"><span data-stu-id="e8250-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="e8250-132">Use [o modo quiosque](hololens-kiosk.md) para limitar a interface do usuário apresentada aos usuários em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8250-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="e8250-133">Você pode definir Quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada.</span><span class="sxs-lookup"><span data-stu-id="e8250-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="e8250-134">Os quiosques também podem apresentar experiências diferentes para diferentes usuários.</span><span class="sxs-lookup"><span data-stu-id="e8250-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="e8250-135">[O Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) para impedir que aplicativos ou processos específicos seja totalmente lançados.</span><span class="sxs-lookup"><span data-stu-id="e8250-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="e8250-136">Se você quiser saber mais sobre métodos mais diferentes de gerenciamento de dispositivos ou restrições de dispositivos, então, dê a próxima etapa e leia nossa Visão Geral do Gerenciamento de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e8250-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="e8250-137">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e8250-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e8250-138">Ler a visão geral de gerenciamento de dispositivos e CSPs</span><span class="sxs-lookup"><span data-stu-id="e8250-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)