---
title: Registrar o HoloLens no MDM
description: Saiba como registrar o HoloLens no MDM (gerenciamento de dispositivo móvel) para facilitar o gerenciamento de vários dispositivos.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308213"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="ae353-103">Registrar o HoloLens no MDM</span><span class="sxs-lookup"><span data-stu-id="ae353-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="ae353-104">Você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções como [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="ae353-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="ae353-105">Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização.</span><span class="sxs-lookup"><span data-stu-id="ae353-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="ae353-106">Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="ae353-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="ae353-107">Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ae353-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="ae353-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae353-108">Requirements</span></span>

 <span data-ttu-id="ae353-109">Sua organização precisará ter o MDM (gerenciamento de dispositivo móvel) configurado para gerenciar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ae353-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="ae353-110">O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae353-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="ae353-111">Diferentes maneiras de se registrar</span><span class="sxs-lookup"><span data-stu-id="ae353-111">Different ways to enroll</span></span>

<span data-ttu-id="ae353-112">Dependendo do tipo de [identidade](hololens-identity.md) escolhido durante o logon oobe ou post, há diferentes métodos de registro.</span><span class="sxs-lookup"><span data-stu-id="ae353-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="ae353-113">Se a identidade for o AD do Azure, então durante o OOBE ou **configurações**  ->  acesso ao aplicativo acessar o botão **de conexão corporativa ou de estudante**  ->   .</span><span class="sxs-lookup"><span data-stu-id="ae353-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ae353-114">Para o Azure AD, o [registro automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorrerá se o Azure ad tiver sido configurado com URLs de registro.</span><span class="sxs-lookup"><span data-stu-id="ae353-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="ae353-115">Se a identidade for o AD do Azure e o dispositivo tiver sido previamente registrado no servidor MDM do Intune com um perfil de configuração específico atribuído a ele, o Azure AD-Join e o [registro automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o Oobe.</span><span class="sxs-lookup"><span data-stu-id="ae353-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="ae353-116">Também chamado de [fluxo de piloto automático](hololens2-autopilot.md) disponível em [19041.1103 + Builds](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="ae353-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="ae353-117">Se a identidade for MSA, usando o botão Configurações acesso do **aplicativo**  ->  **acessar trabalho ou estudante**  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="ae353-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ae353-118">Também chamado de fluxo de adição de conta corporativa (AWA).</span><span class="sxs-lookup"><span data-stu-id="ae353-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="ae353-119">Se a identidade for usuário local, usar **configurações acesso do aplicativo**  ->  **acessar trabalho ou escola**  ->  **registrar somente no link de gerenciamento de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="ae353-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="ae353-120">Também chamado de fluxo de registro de MDM puro.</span><span class="sxs-lookup"><span data-stu-id="ae353-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="ae353-121">Depois que o dispositivo for registrado no servidor MDM, o aplicativo Configurações agora refletirá que o dispositivo está registrado no gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ae353-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="ae353-122">Registro automático no MDM</span><span class="sxs-lookup"><span data-stu-id="ae353-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="ae353-123">Se sua organização tiver uma [assinatura premium do Azure](https://azure.microsoft.com/overview/), estiver usando Azure Active Directory (AD do Azure) e uma solução de MDM que aceita um token do Azure ad para autenticação (atualmente, só tem suporte no Microsoft Intune e no relógio), o administrador de ti poderá configurar o Azure ad para permitir automaticamente o registro de MDM depois que o usuário entrar com sua conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ae353-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="ae353-124">Saiba como configurar o registro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ae353-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="ae353-125">Quando o registro automático está habilitado, nenhum registro manual adicional é necessário.</span><span class="sxs-lookup"><span data-stu-id="ae353-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="ae353-126">Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.</span><span class="sxs-lookup"><span data-stu-id="ae353-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="ae353-127">Quando um dispositivo é associado ao Azure AD, ele pode afetar quem considerou o [proprietário do dispositivo](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="ae353-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="ae353-128">Cancelar o registro do HoloLens do Intune</span><span class="sxs-lookup"><span data-stu-id="ae353-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="ae353-129">Dependendo do método de registro, o cancelamento do registro do dispositivo pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="ae353-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="ae353-130">Se o dispositivo tiver sido registrado com uma conta do Azure AD ou um piloto automático, não será possível cancelar o registro do Intune.</span><span class="sxs-lookup"><span data-stu-id="ae353-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="ae353-131">Se você deseja desassociar o HoloLens do Azure AD ou reassociá-lo a outro locatário do Azure AD, você deve [Redefinir/](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) refazer o flash do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ae353-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="ae353-132">Se o dispositivo tiver sido registrado a partir de uma conta MSA que adicionou uma conta de trabalho ou de uma conta local que foi registrada somente no gerenciamento de dispositivos, você poderá cancelar o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ae353-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="ae353-133">Abra o menu iniciar e selecione configurações acesso do **aplicativo**  ->  **acessar trabalho ou estudante**  ->  *suaconta*  ->  botão **Desconectar** .</span><span class="sxs-lookup"><span data-stu-id="ae353-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>