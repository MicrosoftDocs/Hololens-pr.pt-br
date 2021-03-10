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
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400671"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="0fb15-103">Registrar HoloLens em MDM</span><span class="sxs-lookup"><span data-stu-id="0fb15-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="0fb15-104">Você pode gerenciar vários dispositivos Do Microsoft HoloLens simultaneamente usando soluções como [o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="0fb15-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="0fb15-105">Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização.</span><span class="sxs-lookup"><span data-stu-id="0fb15-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="0fb15-106">Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="0fb15-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="0fb15-107">Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0fb15-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="0fb15-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fb15-108">Requirements</span></span>

 <span data-ttu-id="0fb15-109">Sua organização precisará ter o MDM (Gerenciamento de Dispositivo Móvel) definido para gerenciar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0fb15-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="0fb15-110">O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0fb15-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="0fb15-111">Maneiras diferentes de se inscrever</span><span class="sxs-lookup"><span data-stu-id="0fb15-111">Different ways to enroll</span></span>

<span data-ttu-id="0fb15-112">Dependendo do tipo de [identidade](hololens-identity.md) escolhida durante o OOBE ou pós-login, há diferentes métodos de registro.</span><span class="sxs-lookup"><span data-stu-id="0fb15-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="0fb15-113">Se Identity for o Azure AD, durante o OOBE ou **Configurações do App**  ->  **Access Work ou o botão Conexão**  ->  **de** Escola.</span><span class="sxs-lookup"><span data-stu-id="0fb15-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0fb15-114">Para o Azure AD, o registro [automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorrerá se o Azure AD tiver sido configurado com URLs de registro.</span><span class="sxs-lookup"><span data-stu-id="0fb15-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span> 
     
- <span data-ttu-id="0fb15-115">Se Identity for o Azure AD e o dispositivo tiver sido registrado anteriormente no servidor MDM do Intune com um perfil de configuração específico atribuído a ele, o Azure AD-Join e o registro [automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o OOBE.</span><span class="sxs-lookup"><span data-stu-id="0fb15-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="0fb15-116">Também chamado [de fluxo de piloto automático](hololens2-autopilot.md) Disponível em [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="0fb15-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="0fb15-117">Se Identity for MSA, em seguida, use **Configurações App**  ->  **Access Work ou Botão Conectar**  ->  **Escola.**</span><span class="sxs-lookup"><span data-stu-id="0fb15-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="0fb15-118">Também chamado de fluxo Adicionar Conta de Trabalho (AWA).</span><span class="sxs-lookup"><span data-stu-id="0fb15-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="0fb15-119">Se Identity for Usuário Local, use **Configurações Trabalho**do Acesso ao Aplicativo ou Registro escolar  ->  \*\*\*\*  ->  somente no link**de gerenciamento de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0fb15-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="0fb15-120">Também chamado de fluxo de registro MDM puro.</span><span class="sxs-lookup"><span data-stu-id="0fb15-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="0fb15-121">Depois que o dispositivo estiver inscrito no servidor MDM, o aplicativo Configurações agora refletirá que o dispositivo está inscrito no gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0fb15-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="0fb15-122">Registro automático no MDM</span><span class="sxs-lookup"><span data-stu-id="0fb15-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="0fb15-123">Se a sua organização tem uma assinatura do [Azure Premium](https://azure.microsoft.com/overview/), está usando o Azure Active Directory (Azure AD) e uma solução MDM que aceita um token do Azure AD para autenticação (atualmente, com suporte apenas no Microsoft Intune e no AirWatch), o administrador de IT pode configurar o Azure AD para permitir automaticamente o registro do MDM depois que o usuário entrar com sua conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0fb15-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="0fb15-124">Saiba como configurar o registro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0fb15-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="0fb15-125">Quando o registro automático está habilitado, nenhum registro manual adicional é necessário.</span><span class="sxs-lookup"><span data-stu-id="0fb15-125">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="0fb15-126">Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.</span><span class="sxs-lookup"><span data-stu-id="0fb15-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="0fb15-127">Quando um dispositivo é Azure AD Ingressado, ele pode afetar quem considera o proprietário [do dispositivo](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="0fb15-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="0fb15-128">Unenroll HoloLens from Intune</span><span class="sxs-lookup"><span data-stu-id="0fb15-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="0fb15-129">Embora o HoloLens 2 seja um dispositivo Windows 10, ele não pode ser simplesmente desemrollado do Intune.</span><span class="sxs-lookup"><span data-stu-id="0fb15-129">Although HoloLens 2 is Windows 10 device, it cannot be simply unenrolled from Intune.</span></span> <span data-ttu-id="0fb15-130">Se desejar desatar o HoloLens do Azure AD ou reapresentá-lo a um locatário diferente do Azure AD, você deve [redefinir/reajustar](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0fb15-130">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>