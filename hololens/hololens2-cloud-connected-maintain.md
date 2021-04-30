---
title: Guia de implantação – implantação do HoloLens 2 em nuvem conectada em escala com o auxílio remoto-manter
description: Mantenha-se atualizado com nossas dicas para manter e dar suporte a dispositivos de HoloLens em uma rede conectada em nuvem.
keywords: HoloLens, gerenciamento, nuvem conectada, assistência remota, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308227"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="fb985-104">Maintain-guia conectado à nuvem</span><span class="sxs-lookup"><span data-stu-id="fb985-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="fb985-105">Atualizações</span><span class="sxs-lookup"><span data-stu-id="fb985-105">Updates</span></span>

<span data-ttu-id="fb985-106">A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.</span><span class="sxs-lookup"><span data-stu-id="fb985-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="fb985-107">Saiba como [gerenciar atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , incluindo dias agendados, hora agendada e definindo horas ativas no dispositivo para que ele seja atualizado fora do horário de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb985-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="fb985-108">O auxílio remoto é um aplicativo In-Box e pode ser atualizado por meio do aplicativo Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="fb985-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="fb985-109">Para todos os aplicativos que são baixados por meio do Microsoft Store eles podem ser [atualizados por meio do](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) próprio aplicativo Microsoft Store manualmente.</span><span class="sxs-lookup"><span data-stu-id="fb985-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="fb985-110">Plano de suporte</span><span class="sxs-lookup"><span data-stu-id="fb985-110">Support Plan</span></span>

<span data-ttu-id="fb985-111">Um plano de suporte é uma excelente coisa a ter em vigor.</span><span class="sxs-lookup"><span data-stu-id="fb985-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="fb985-112">Ter alguém ou um grupo treinado na solução de problemas do processo de registro em dispositivos HoloLens e também o uso geral do dispositivo HoloLens em sua organização é útil.</span><span class="sxs-lookup"><span data-stu-id="fb985-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="fb985-113">Para permitir que os usuários tenham a resolução mais rápida de seus problemas, sugerimos que o processo de escalonamento seja manipulado de maneira semelhante a esta ordem:</span><span class="sxs-lookup"><span data-stu-id="fb985-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="fb985-114">Seu suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fb985-114">Your Support desk.</span></span>
2. <span data-ttu-id="fb985-115">Sua equipe de especialistas em HoloLens</span><span class="sxs-lookup"><span data-stu-id="fb985-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="fb985-116">[Documentos](https://docs.microsoft.com/hololens/)  /  do HoloLens [Documentos de solução de problemas do HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="fb985-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="fb985-117">Contatar o suporte</span><span class="sxs-lookup"><span data-stu-id="fb985-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="fb985-118">Plano de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="fb985-118">Development Plan</span></span>

<span data-ttu-id="fb985-119">Com seu dispositivo registrado com êxito, você agora está preparado para implantar aplicativos de linha de negócios (aplicativos LOB) em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb985-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="fb985-120">Esses são aplicativos personalizados criados para a sua organização&#39;s necessidades.</span><span class="sxs-lookup"><span data-stu-id="fb985-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="fb985-121">Se você já tiver um aplicativo de linha de negócios, você&#39;pronto para [implantar seu aplicativo por meio do MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span><span class="sxs-lookup"><span data-stu-id="fb985-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="fb985-122">Se você&#39;d preferir um método diferente, examine a [visão geral da implantação do aplicativo para o HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para saber mais métodos de implantação de seu aplicativo LOB em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb985-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="fb985-123">Se você&#39;ainda criar seu próprio aplicativo LOB ou ainda estiver no processo de criação, examine nossos documentos de desenvolvimento de realidade misturada para [começar a projetar e criar um protótipo](https://docs.microsoft.com/windows/mixed-reality/design/design) ou aprender os conceitos básicos para começar a [usar o desenvolvimento de realidade misturada.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="fb985-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="fb985-124">Gerenciamento de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="fb985-124">Device Management</span></span> 

<span data-ttu-id="fb985-125">Embora este guia tenha falado sobre a configuração do MDM (gerenciamento de dispositivo móvel), ele não foi empregado para aplicar restrições de dispositivo ou as políticas foram aplicadas a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb985-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="fb985-126">O gerenciamento de dispositivos pode ser usado para permitir o acesso enviando certificados por Push ou restringir o acesso com uma variedade de restrições de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb985-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="fb985-127">Em muitos casos, os dispositivos podem ter restrições de conectividade, como Bluetooth, VPN, USB ou até mesmo desativar o acesso à câmera ou ao microfone.</span><span class="sxs-lookup"><span data-stu-id="fb985-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="fb985-128">Se qualquer um desses interesses, incentivamos você a ler nossa [página de restrições de dispositivo comum](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="fb985-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="fb985-129">Há outras restrições de dispositivo mais complexas que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="fb985-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="fb985-130">Como:</span><span class="sxs-lookup"><span data-stu-id="fb985-130">Such as:</span></span>

- <span data-ttu-id="fb985-131">Limitar as páginas que podem ser exibidas no aplicativo de configurações usando o [SettingsPageVisibility](settings-uri-list.md), permitindo que os usuários acessem apenas as configurações que precisam para se ajustar, como alterar sua conexão de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="fb985-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="fb985-132">Use o [modo de quiosque](hololens-kiosk.md) para limitar a interface do usuário apresentada aos usuários em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb985-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="fb985-133">Você pode definir quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada.</span><span class="sxs-lookup"><span data-stu-id="fb985-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="fb985-134">Os quiosques também podem apresentar experiências diferentes a usuários diferentes.</span><span class="sxs-lookup"><span data-stu-id="fb985-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="fb985-135">[Controle de aplicativo do Windows (WDAC)](windows-defender-application-control-wdac.md) para impedir que aplicativos ou processos específicos sejam iniciados inteiramente.</span><span class="sxs-lookup"><span data-stu-id="fb985-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="fb985-136">Se você quiser saber mais sobre métodos mais diferentes de gerenciamento de dispositivos ou restrições de dispositivos, siga a próxima etapa e leia nossa visão geral do gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fb985-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="fb985-137">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="fb985-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fb985-138">Leia a visão geral de gerenciamento de CSPs e de dispositivos</span><span class="sxs-lookup"><span data-stu-id="fb985-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)