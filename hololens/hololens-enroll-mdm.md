---
title: Registrar HoloLens em MDM
description: Registre o HoloLens no MDM (gerenciamento de dispositivo móvel) para facilitar o gerenciamento de vários dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827557"
---
# <span data-ttu-id="2d86b-103">Registrar HoloLens em MDM</span><span class="sxs-lookup"><span data-stu-id="2d86b-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="2d86b-104">Você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções como [o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="2d86b-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="2d86b-105">Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização.</span><span class="sxs-lookup"><span data-stu-id="2d86b-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="2d86b-106">Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="2d86b-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="2d86b-107">Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="2d86b-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="2d86b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d86b-108">Requirements</span></span>

 <span data-ttu-id="2d86b-109">Sua organização precisará ter o gerenciamento de dispositivos móveis (MDM) configurado para gerenciar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2d86b-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="2d86b-110">O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d86b-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="2d86b-111">Registro automático no MDM</span><span class="sxs-lookup"><span data-stu-id="2d86b-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="2d86b-112">Se a organização usar o Azure AD (Azure Active Directory) e uma solução MDM que aceita um token AAD para autenticação (atualmente, compatível apenas no Microsoft Intune e no AirWatch), o administrador de TI poderá configurar o Azure AD para permitir automaticamente o registro no MDM depois que o usuário entrar usando a conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2d86b-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="2d86b-113">Saiba como configurar o registro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2d86b-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="2d86b-114">Quando o registro automático está habilitado, nenhum registro manual adicional é necessário.</span><span class="sxs-lookup"><span data-stu-id="2d86b-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="2d86b-115">Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.</span><span class="sxs-lookup"><span data-stu-id="2d86b-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="2d86b-116">Registrar-se por meio do aplicativo Configurações</span><span class="sxs-lookup"><span data-stu-id="2d86b-116">Enroll through Settings app</span></span>

 <span data-ttu-id="2d86b-117">Quando o dispositivo não é registrado no MDM durante a experiência de primeira execução, o usuário pode registrar manualmente o dispositivo no servidor MDM da organização usando o aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="2d86b-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="2d86b-118">Vá até **Configurações** > **Contas** > **Acesso corporativo**.</span><span class="sxs-lookup"><span data-stu-id="2d86b-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="2d86b-119">Selecione **Registrar-se no gerenciamento de dispositivo (MDM)** e insira a conta organizacional.</span><span class="sxs-lookup"><span data-stu-id="2d86b-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="2d86b-120">Você será redirecionado para a página de entrada da organização.</span><span class="sxs-lookup"><span data-stu-id="2d86b-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="2d86b-121">Após uma autenticação bem-sucedida no servidor MDM, uma mensagem de êxito será mostrada.</span><span class="sxs-lookup"><span data-stu-id="2d86b-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="2d86b-122">Agora o dispositivo está registrado no servidor MDM.</span><span class="sxs-lookup"><span data-stu-id="2d86b-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="2d86b-123">O aplicativo Configurações agora refletirá que o dispositivo está registrado no gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2d86b-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="2d86b-124">Cancelar inscrição do HoloLens do Intune</span><span class="sxs-lookup"><span data-stu-id="2d86b-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="2d86b-125">Você não pode [cancelar o registro](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) do HoloLens do Intune remotamente.</span><span class="sxs-lookup"><span data-stu-id="2d86b-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="2d86b-126">Se o administrador cancelar o registro do dispositivo usando o MDM, o dispositivo será excluído do painel do Intune.</span><span class="sxs-lookup"><span data-stu-id="2d86b-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
