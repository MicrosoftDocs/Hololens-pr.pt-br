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
# Registrar HoloLens em MDM

Você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções como [o Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business) Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização. Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisitos

 Sua organização precisará ter o Gerenciamento de Dispositivo Móvel (MDM) definido para gerenciar dispositivos HoloLens. O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.
 
## Diferentes maneiras de se inscrever

Dependendo do tipo de identidade escolhido durante a OOBE ou pós-login, há diferentes métodos de registro. Para saber mais sobre cada tipo de Identidade no HoloLens, visite [esta página.](hololens-identity.md)

- Se a Identidade for o Azure AD, durante OOBE ou **Configurações**do Aplicativo Acesso ao Trabalho  ->  **ou botão**  ->  **Conectar Escola.**
    - Para o Azure AD, o registro automático no MDM só ocorrerá se o Azure AD tiver sido configurado com URLs de registro.
- Se a Identidade for o Azure AD e o dispositivo tiver sido previamente registrado no servidor MDM do Intune com um perfil de configuração específico atribuído a ele, o Azure AD-Join e o registro ocorrerão automaticamente durante o OOBE.
    - Também chamado [de fluxo do Autopilot](hololens2-autopilot.md) Disponível [em builds 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)
- Se Identity for MSA, use **o botão Configurações do Acesso**ao Aplicativo trabalho ou ao  ->  **school**  ->  **connect.**
    - Também chamado de fluxo Adicionar Conta De Trabalho (AWA).
- Se Identity for Usuário **** Local, use Configurações de Acesso ao Aplicativo Trabalho ou  ->  **Registro**escolar somente no link de gerenciamento  ->  **de** dispositivo.
    - Também chamado de fluxo de registro puro do MDM.

Depois que o dispositivo for inscrito no servidor MDM, o aplicativo Configurações agora refletirá que o dispositivo está inscrito no gerenciamento de dispositivos.

## Registro automático no MDM

Se sua organização usa o Azure Active Directory (Azure AD) e uma solução MDM que aceita um token do Azure AD para autenticação (atualmente, com suporte apenas no Microsoft Intune e no AirWatch), o administrador de IT pode configurar o Azure AD para permitir automaticamente o registro no MDM depois que o usuário entrar com a conta do Azure AD. [Saiba como configurar o registro do Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando o registro automático está habilitado, nenhum registro manual adicional é necessário. Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.

Quando um dispositivo é ingressado no Azure AD, pode afetar quem considerou o [proprietário do dispositivo.](security-adminless-os.md#device-owner)

## Desemrollar o HoloLens do Intune

To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
