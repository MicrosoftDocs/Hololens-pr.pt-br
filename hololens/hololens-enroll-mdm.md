---
title: Registrar o HoloLens no MDM
description: saiba como registrar HoloLens no MDM (gerenciamento de dispositivo móvel) para facilitar o gerenciamento de vários dispositivos.
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
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979348"
---
# <a name="enroll-hololens-in-mdm"></a>Registrar o HoloLens no MDM

você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções como [Microsoft Intune](/intune/windows-holographic-for-business). Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização. Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 sua organização precisará ter o MDM (gerenciamento de dispositivo móvel) configurado para gerenciar dispositivos HoloLens. O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.

## <a name="different-ways-to-enroll"></a>Diferentes maneiras de se registrar

Dependendo do tipo de [identidade](hololens-identity.md) escolhido durante o logon oobe ou post, há diferentes métodos de registro.

- se a identidade for Azure AD, então durante o acesso do aplicativo OOBE ou **Configurações**  ->  Conexão botão **de trabalho ou escola**  ->   .
    - Para o Azure AD, o [registro automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) só ocorrerá se o Azure ad tiver sido configurado com URLs de registro.

- Se a identidade for o AD do Azure e o dispositivo tiver sido previamente registrado no servidor MDM do Intune com um perfil de configuração específico atribuído a ele, o Azure AD-Join e o [registro automático do MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) ocorrerão durante o Oobe.
    - Também chamado de [fluxo de piloto automático](hololens2-autopilot.md) disponível em [19041.1103 + Builds](hololens-release-notes.md#windows-holographic-version-2004).


- se a identidade for a MSA, use **Configurações**  ->  botão **acesso de aplicativo ou Conexão de estudante**  ->   .
    - Também chamado de fluxo de adição de conta corporativa (AWA).
- se a identidade for usuário Local, usar **Configurações acesso ao aplicativo**  ->  **acesse o trabalho ou a escola** registrar-se  ->  **somente no link de gerenciamento de dispositivo** .
    - Também chamado de fluxo de registro de MDM puro.

depois que o dispositivo for registrado no servidor MDM, o aplicativo Configurações agora refletirá que o dispositivo está registrado no gerenciamento de dispositivos.

## <a name="auto-enrollment-in-mdm"></a>Registro automático no MDM

se sua organização tiver uma [assinatura de Premium do azure](https://azure.microsoft.com/overview/), estiver usando Azure Active Directory (AD do azure) e uma solução de MDM que aceita um token do azure ad para autenticação (atualmente, só tem suporte no Microsoft Intune e no relógio), o administrador de ti poderá configurar o Azure ad para permitir automaticamente o registro de MDM depois que o usuário entrar com sua conta do Azure AD. [Saiba como configurar o registro do Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando o registro automático está habilitado, nenhum registro manual adicional é necessário. Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.

Quando um dispositivo é associado ao Azure AD, ele pode afetar quem considerou o [proprietário do dispositivo](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>cancelar o registro de HoloLens do Intune

Dependendo do método de registro, o cancelamento do registro do dispositivo pode não estar disponível.

Se o dispositivo tiver sido registrado com uma conta do Azure AD ou um piloto automático, não será possível cancelar o registro do Intune. se você quiser desassociar HoloLens do Azure ad ou reassociá-lo a outro locatário do azure ad, será necessário [redefinir/](hololens-recovery.md#reset-the-device) refazer o flash do dispositivo.

Se o dispositivo tiver sido registrado a partir de uma conta MSA que adicionou uma conta de trabalho ou de uma conta local que foi registrada somente no gerenciamento de dispositivos, você poderá cancelar o registro do dispositivo. abra o menu Iniciar e, em seguida, selecione Configurações acesso ao **aplicativo**  ->  acessar o botão de desconexão **de trabalho ou escola**  ->  *suaconta*  ->   .

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>verifique se o registro de MDM não está bloqueado para dispositivos Windows

para que o registro tenha sucesso, você precisará garantir que seus HoloLens dispositivos possam ser registrados. como HoloLens é considerado um dispositivo de Windows, não será necessário nenhuma restrição de registro que possa bloquear sua implantação. [Examine esta lista de restrições](/mem/intune/enrollment/enrollment-restrictions-set) e verifique se você poderá registrar seus dispositivos.