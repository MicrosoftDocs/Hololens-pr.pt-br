---
title: Registrar HoloLens em MDM
description: Saiba como registrar o HoloLens no gerenciamento de dispositivo móvel (MDM) para facilitar o gerenciamento de vários dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b9473f4e80f6438ef4c438711ac0de342c5327e1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283182"
---
# <span data-ttu-id="c0faa-103">Registrar HoloLens em MDM</span><span class="sxs-lookup"><span data-stu-id="c0faa-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="c0faa-104">Você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções como [o Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="c0faa-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="c0faa-105">Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização.</span><span class="sxs-lookup"><span data-stu-id="c0faa-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="c0faa-106">Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="c0faa-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="c0faa-107">Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c0faa-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="c0faa-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0faa-108">Requirements</span></span>

 <span data-ttu-id="c0faa-109">Sua organização precisará ter o Gerenciamento de Dispositivo Móvel (MDM) definido para gerenciar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c0faa-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="c0faa-110">O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c0faa-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="c0faa-111">Diferentes maneiras de se inscrever</span><span class="sxs-lookup"><span data-stu-id="c0faa-111">Different ways to enroll</span></span>

<span data-ttu-id="c0faa-112">Dependendo do tipo de identidade escolhido durante a OOBE ou pós-login, há diferentes métodos de registro.</span><span class="sxs-lookup"><span data-stu-id="c0faa-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="c0faa-113">Para saber mais sobre cada tipo de Identidade no HoloLens, visite [esta página.](hololens-identity.md)</span><span class="sxs-lookup"><span data-stu-id="c0faa-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="c0faa-114">Se a Identidade for o Azure AD, durante OOBE ou **Configurações**do Aplicativo Acesso ao Trabalho  ->  **ou botão**  ->  **Conectar Escola.**</span><span class="sxs-lookup"><span data-stu-id="c0faa-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="c0faa-115">Para o Azure AD, o registro automático no MDM só ocorrerá se o Azure AD tiver sido configurado com URLs de registro.</span><span class="sxs-lookup"><span data-stu-id="c0faa-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="c0faa-116">Se a Identidade for o Azure AD e o dispositivo tiver sido previamente registrado no servidor MDM do Intune com um perfil de configuração específico atribuído a ele, o Azure AD-Join e o registro ocorrerão automaticamente durante o OOBE.</span><span class="sxs-lookup"><span data-stu-id="c0faa-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="c0faa-117">Também chamado [de fluxo do Autopilot](hololens2-autopilot.md) Disponível [em builds 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="c0faa-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="c0faa-118">Se Identity for MSA, use **o botão Configurações do Acesso**ao Aplicativo trabalho ou ao  ->  **school**  ->  **connect.**</span><span class="sxs-lookup"><span data-stu-id="c0faa-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="c0faa-119">Também chamado de fluxo Adicionar Conta De Trabalho (AWA).</span><span class="sxs-lookup"><span data-stu-id="c0faa-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="c0faa-120">Se Identity for Usuário \*\*\*\* Local, use Configurações de Acesso ao Aplicativo Trabalho ou  ->  **Registro**escolar somente no link de gerenciamento  ->  **de** dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0faa-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="c0faa-121">Também chamado de fluxo de registro puro do MDM.</span><span class="sxs-lookup"><span data-stu-id="c0faa-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="c0faa-122">Depois que o dispositivo for inscrito no servidor MDM, o aplicativo Configurações agora refletirá que o dispositivo está inscrito no gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c0faa-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="c0faa-123">Registro automático no MDM</span><span class="sxs-lookup"><span data-stu-id="c0faa-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="c0faa-124">Se sua organização usa o Azure Active Directory (Azure AD) e uma solução MDM que aceita um token do Azure AD para autenticação (atualmente, com suporte apenas no Microsoft Intune e no AirWatch), o administrador de IT pode configurar o Azure AD para permitir automaticamente o registro no MDM depois que o usuário entrar com a conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0faa-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="c0faa-125">Saiba como configurar o registro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c0faa-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="c0faa-126">Quando o registro automático está habilitado, nenhum registro manual adicional é necessário.</span><span class="sxs-lookup"><span data-stu-id="c0faa-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="c0faa-127">Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.</span><span class="sxs-lookup"><span data-stu-id="c0faa-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="c0faa-128">Quando um dispositivo é ingressado no Azure AD, pode afetar quem considerou o [proprietário do dispositivo.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="c0faa-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="c0faa-129">Desemrollar o HoloLens do Intune</span><span class="sxs-lookup"><span data-stu-id="c0faa-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="c0faa-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="c0faa-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
