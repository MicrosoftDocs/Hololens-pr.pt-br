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
# <a name="enroll-hololens-in-mdm"></a>Registrar HoloLens em MDM

Você pode gerenciar vários dispositivos Do Microsoft HoloLens simultaneamente usando soluções como [o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização. Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 Sua organização precisará ter o MDM (Gerenciamento de Dispositivo Móvel) definido para gerenciar dispositivos HoloLens. O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.
 
## <a name="different-ways-to-enroll"></a>Maneiras diferentes de se inscrever

Dependendo do tipo de [identidade](hololens-identity.md) escolhida durante o OOBE ou pós-login, há diferentes métodos de registro.

- Se Identity for o Azure AD, durante o OOBE ou **Configurações do App**  ->  **Access Work ou o botão Conexão**  ->  **de** Escola.
    - Para o Azure AD, o registro [automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorrerá se o Azure AD tiver sido configurado com URLs de registro. 
     
- Se Identity for o Azure AD e o dispositivo tiver sido registrado anteriormente no servidor MDM do Intune com um perfil de configuração específico atribuído a ele, o Azure AD-Join e o registro [automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o OOBE.
    - Também chamado [de fluxo de piloto automático](hololens2-autopilot.md) Disponível em [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).
    

- Se Identity for MSA, em seguida, use **Configurações App**  ->  **Access Work ou Botão Conectar**  ->  **Escola.**
    - Também chamado de fluxo Adicionar Conta de Trabalho (AWA).
- Se Identity for Usuário Local, use **Configurações Trabalho**do Acesso ao Aplicativo ou Registro escolar  ->  ****  ->  somente no link**de gerenciamento de** dispositivos.
    - Também chamado de fluxo de registro MDM puro.

Depois que o dispositivo estiver inscrito no servidor MDM, o aplicativo Configurações agora refletirá que o dispositivo está inscrito no gerenciamento de dispositivos.

## <a name="auto-enrollment-in-mdm"></a>Registro automático no MDM

Se a sua organização tem uma assinatura do [Azure Premium](https://azure.microsoft.com/overview/), está usando o Azure Active Directory (Azure AD) e uma solução MDM que aceita um token do Azure AD para autenticação (atualmente, com suporte apenas no Microsoft Intune e no AirWatch), o administrador de IT pode configurar o Azure AD para permitir automaticamente o registro do MDM depois que o usuário entrar com sua conta do Azure AD. [Saiba como configurar o registro do Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando o registro automático está habilitado, nenhum registro manual adicional é necessário. Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.

Quando um dispositivo é Azure AD Ingressado, ele pode afetar quem considera o proprietário [do dispositivo](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Unenroll HoloLens from Intune

Embora o HoloLens 2 seja um dispositivo Windows 10, ele não pode ser simplesmente desemrollado do Intune. Se desejar desatar o HoloLens do Azure AD ou reapresentá-lo a um locatário diferente do Azure AD, você deve [redefinir/reajustar](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) o dispositivo.