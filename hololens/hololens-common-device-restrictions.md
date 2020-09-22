---
title: Restrições comuns de dispositivo
description: O dispositivo restrctions comumente definido no HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016755"
---
# <span data-ttu-id="78809-103">Restrições comuns de dispositivo</span><span class="sxs-lookup"><span data-stu-id="78809-103">Common Device Restrictions</span></span> 

<span data-ttu-id="78809-104">Este guia ajuda os profissionais de ti a entenderem as opções de gerenciamento mais comuns disponíveis para o Windows 10 holográfico o sistema operacional da empresa.</span><span class="sxs-lookup"><span data-stu-id="78809-104">This guide helps IT professionals understand the more commonly used management options available for the Windows 10 Holographic OS in the enterprise.</span></span> <span data-ttu-id="78809-105">Consulte a documentação de seu sistema MDM para entender como essas políticas são habilitadas por seu fornecedor de MDM.</span><span class="sxs-lookup"><span data-stu-id="78809-105">Please consult your MDM system documentation to understand how these policies are enabled by your MDM vendor.</span></span> <span data-ttu-id="78809-106">Nem todos os sistemas MDM dão suporte a todas as configurações descritas neste guia.</span><span class="sxs-lookup"><span data-stu-id="78809-106">Not all MDM systems support every setting described in this guide.</span></span> <span data-ttu-id="78809-107">Alguns dão suporte a políticas personalizadas por meio de arquivos XML OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="78809-107">Some support custom policies through OMA-URI XML files.</span></span> <span data-ttu-id="78809-108">Consulte [Suporte do Microsoft Intune para políticas personalizadas](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="78809-108">See [Microsoft Intune support for Custom Policies](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span> <span data-ttu-id="78809-109">As convenções de nomenclatura também podem variar entre os fornecedores de MDM.</span><span class="sxs-lookup"><span data-stu-id="78809-109">Naming conventions may also vary among MDM vendors.</span></span>

## <span data-ttu-id="78809-110">Impedir alteração das configurações</span><span class="sxs-lookup"><span data-stu-id="78809-110">Prevent changing of settings</span></span>
<span data-ttu-id="78809-111">Geralmente, os funcionários têm permissão para alterar determinadas configurações do dispositivo pessoal que você pode bloquear em dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="78809-111">Employees are usually allowed to change certain personal device settings that you may want to lock down on corporate devices.</span></span> <span data-ttu-id="78809-112">Os funcionários podem ajustar interativamente determinadas configurações do HoloLens por meio da interface do usuário de configurações.</span><span class="sxs-lookup"><span data-stu-id="78809-112">Employees can interactively adjust certain settings of the HoloLens through the settings UI.</span></span> <span data-ttu-id="78809-113">Usando o MDM, você pode limitar quais usuários têm permissão para alterar.</span><span class="sxs-lookup"><span data-stu-id="78809-113">Using MDM, you can limit what users are allowed to change.</span></span> <span data-ttu-id="78809-114">A seguir lista as configurações de MDM comumente usadas que o Windows 10 holográfico suporta para configurar restrições de configurações:</span><span class="sxs-lookup"><span data-stu-id="78809-114">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure settings restrictions:</span></span>
-   <span data-ttu-id="78809-115">[Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite que o usuário altere as configurações de VPN</span><span class="sxs-lookup"><span data-stu-id="78809-115">[Allow VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Allows the user to change VPN settings</span></span>
-   <span data-ttu-id="78809-116">[Permitir configuração manual WiFi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os usuários façam conexões Wi-Fi fora das redes provisionadas pelo MDM</span><span class="sxs-lookup"><span data-stu-id="78809-116">[Allow Manual WiFi Configuration:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Allows users to make Wi-Fi connections outside of MDM provisioned networks</span></span>
-   <span data-ttu-id="78809-117">[Permitir cancelamento de registro do MDM manual](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se os usuários podem excluir a conta do local de trabalho (ou seja, cancelar o registro do dispositivo do sistema MDM)</span><span class="sxs-lookup"><span data-stu-id="78809-117">[Allow Manual MDM Unenrollment](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Whether users are allowed to delete the workplace account (i.e., unenroll the device from the MDM system)</span></span>

<span data-ttu-id="78809-118">Encontre mais detalhes sobre as opções de política nos [CSPs de política](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) com suporte do HoloLens</span><span class="sxs-lookup"><span data-stu-id="78809-118">Find more details on policy options in the HoloLens supported [Policy CSPs](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span></span>

## <span data-ttu-id="78809-119">Restrições de hardware</span><span class="sxs-lookup"><span data-stu-id="78809-119">Hardware restrictions</span></span>
<span data-ttu-id="78809-120">Os dispositivos Windows 10 holográfico usam a tecnologia de ponta que inclui recursos de hardware populares, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="78809-120">Windows 10 Holographic devices use state-of-the-art technology that includes popular hardware features such as cameras, microphones, speakers, USB interfaces, Bluetooth interfaces, and Wi-Fi.</span></span> <span data-ttu-id="78809-121">Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.</span><span class="sxs-lookup"><span data-stu-id="78809-121">You can use hardware restrictions to control the availability of these features.</span></span>
<span data-ttu-id="78809-122">A seguir lista as configurações de MDM comumente usadas que o Windows 10 holográfico suporta para configurar restrições de hardware:</span><span class="sxs-lookup"><span data-stu-id="78809-122">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure hardware restrictions:</span></span>

> [!NOTE]
> <span data-ttu-id="78809-123">Algumas dessas restrições de hardware afetam a conectividade e ajudam na proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="78809-123">Some of these hardware restrictions affect connectivity and assist in data protection.</span></span>

-   <span data-ttu-id="78809-124">[Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar o rádio WiFi em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="78809-124">[Allow Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Whether users can enable and use the WiFi radio on their devices.</span></span>
-   <span data-ttu-id="78809-125">[Permitir conexão USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não afeta o carregamento USB.)</span><span class="sxs-lookup"><span data-stu-id="78809-125">[Allow USB Connection:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Whether the USB connection is enabled (doesn’t affect USB charging.)</span></span>
-   <span data-ttu-id="78809-126">[Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o rádio Bluetooth em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="78809-126">[Allow Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Whether users can enable and use the Bluetooth radio on their devices.</span></span>
-   <span data-ttu-id="78809-127">[Restringe câmera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica se os aplicativos do Windows podem acessar a câmera.</span><span class="sxs-lookup"><span data-stu-id="78809-127">[Restrict Camera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifies whether Windows apps can access the camera.</span></span>
-   <span data-ttu-id="78809-128">[Restringir microfones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica se os aplicativos do Windows podem acessar o microfone.</span><span class="sxs-lookup"><span data-stu-id="78809-128">[Restrict Microphones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifies whether Windows apps can access the microphone.</span></span>