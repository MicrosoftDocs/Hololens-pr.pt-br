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
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903217"
---
# Registrar HoloLens em MDM

Você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções como [o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização. Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisitos

 Sua organização precisará ter o gerenciamento de dispositivos móveis (MDM) configurado para gerenciar dispositivos HoloLens. O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.
 
## Diferentes maneiras de se inscrever

Dependendo do tipo de identidade escolhido durante o OOBE ou o logon de postagem, há métodos diferentes de inscrição. Para saber mais sobre cada tipo de identidade no HoloLens, [acesse esta página](hololens-identity.md).

- Se identidade for AAD, em seguida, durante o controle de acesso do aplicativo oobe ou **Settings**,  ->  **acesse o trabalho ou o botão de**  ->  **conexão** escolar.
    - Para o AAD, o registro automático do MDM ocorre apenas se o AAD tiver sido configurado com URLs de registro.
- Se a identidade for AAD e o dispositivo tiver sido registrado previamente com o servidor de MDM do Intune com um perfil de configuração específico atribuído a ele, o AAD-Join e o registro ocorrerão automaticamente durante o OOBE.
    - Também chamado de [fluxo de piloto automático](hololens2-autopilot.md) disponível em [19041.1103 + Builds](hololens-release-notes.md#windows-holographic-version-2004).
- Se identidade for MSA, use o **Settings App**  ->  botão**de acesso do aplicativo de configurações trabalho ou escola**de  ->  **conexão** .
    - Também chamado de fluxo adicionar conta de trabalho (AWA).
- Se identidade for usuário local, usar o **aplicativo Configurações**  ->  **Access trabalho ou escola**  ->  **registrar somente no link gerenciamento de dispositivo** .
    - Também chamado de fluxo de registro MDM puro.

Depois que o dispositivo for registrado com seu servidor de MDM, o aplicativo Configurações refletirá que o dispositivo está registrado no gerenciamento de dispositivos.

## Registro automático no MDM

Se a organização usar o Azure AD (Azure Active Directory) e uma solução MDM que aceita um token AAD para autenticação (atualmente, compatível apenas no Microsoft Intune e no AirWatch), o administrador de TI poderá configurar o Azure AD para permitir automaticamente o registro no MDM depois que o usuário entrar usando a conta do Azure AD. [Saiba como configurar o registro do Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando o registro automático está habilitado, nenhum registro manual adicional é necessário. Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.

## Cancelar inscrição do HoloLens do Intune

Para saber mais sobre como cancelar o registro de um dispositivo, [acesse esta página](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
