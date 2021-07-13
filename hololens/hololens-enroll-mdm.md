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
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640399"
---
# <a name="enroll-hololens-in-mdm"></a>Registrar o HoloLens no MDM

Você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções [como Microsoft Intune](/intune/windows-holographic-for-business). Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização. Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 Sua organização precisará ter o MDM (mobile Gerenciamento de Dispositivos) configurada para gerenciar HoloLens dispositivos. O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.
 
## <a name="different-ways-to-enroll"></a>Diferentes maneiras de se registrar

Dependendo do tipo de [identidade](hololens-identity.md) escolhido durante o OOBE ou após a inscrição, há diferentes métodos de registro.

- Se Identity for o Azure AD, durante o OOBE ou Configurações App Access Work ou  ->  **o botão Conexão**  ->   School.
    - Para o Azure AD, o registro automático de [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorrerá se o Azure AD tiver sido configurado com URLs de registro.
     
- Se o Identity for o Azure AD e o dispositivo tiver sido previamente registrado no servidor MDM do Intune com um perfil de configuração específico atribuído a ele, o Azure AD-Join e o registro automático de [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o OOBE.
    - Também chamado [de fluxo do Autopilot](hololens2-autopilot.md) Disponível [em builds 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Se Identity for MSA, use o Configurações **De** Acesso ao Aplicativo  ->  **ou o Conexão** De  ->   estudante.
    - Também chamado de fluxo adicionar conta de trabalho (AWA).
- Se a Identidade for Usuário Local, use o **Configurações De** Acesso ao Aplicativo ou o Registro de Estudante  ->    ->  somente no link **de gerenciamento de** dispositivos.
    - Também chamado de fluxo de registro de MDM puro.

Depois que o dispositivo for inscrito no servidor MDM, o Configurações aplicativo agora refletirá que o dispositivo está inscrito no gerenciamento de dispositivos.

## <a name="auto-enrollment-in-mdm"></a>Registro automático no MDM

Se sua organização tiver uma assinatura do [Azure Premium](https://azure.microsoft.com/overview/), estiver usando o Azure Active Directory (Azure AD) e uma solução de MDM que aceite um token do Azure AD para autenticação (atualmente, com suporte apenas no Microsoft Intune e no AirWatch), o administrador de IT poderá configurar o Azure AD para permitir automaticamente o registro de MDM depois que o usuário entrar com sua conta do Azure AD. [Saiba como configurar o registro do Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando o registro automático está habilitado, nenhum registro manual extra é necessário. Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.

Quando um dispositivo é ingressado no Azure AD, ele pode afetar quem considerou o [proprietário do dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Unenroll HoloLens do Intune

Dependendo do método de registro, o registro do dispositivo pode não estar disponível.

Se o dispositivo tiver sido inscrito com uma conta do Azure AD ou o Autopilot, ele não poderá ser anuado do Intune. Se você quiser desajosar o HoloLens do Azure AD ou reapresentá-lo a um locatário diferente do Azure AD, você deverá [redefinir/reajustar](hololens-recovery.md#reset-the-device) o dispositivo.

Se o dispositivo tiver sido inscrito de uma conta MSA que adicionou uma conta de trabalho ou de uma conta Local que se registrou somente no gerenciamento de dispositivos, você poderá desinscritar o dispositivo. Abra o menu Iniciar e, em **seguida, selecione Configurações** Trabalho do Acesso ao Aplicativo  ->  **ou o botão**  ->  *Desconectar Sua Conta*  ->  **da** Conta.