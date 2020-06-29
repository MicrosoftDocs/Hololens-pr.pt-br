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
# Registrar HoloLens em MDM

Você pode gerenciar vários dispositivos Microsoft HoloLens simultaneamente usando soluções como [o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Você poderá gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da organização. Consulte [Gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), os [provedores de serviço de configuração (CSPs) que têm suporte no Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) e as [políticas compatíveis com o Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Gerenciamento de dispositivo móvel (MDM), incluindo a VPN, Bitlocker e recursos do modo de quiosque, só estão disponíveis quando você [faz upgrade para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisitos

 Sua organização precisará ter o gerenciamento de dispositivos móveis (MDM) configurado para gerenciar dispositivos HoloLens. O provedor MDM pode ser o Microsoft Intune ou um provedor de terceiros que use APIs MDM Microsoft.

## Registro automático no MDM

Se a organização usar o Azure AD (Azure Active Directory) e uma solução MDM que aceita um token AAD para autenticação (atualmente, compatível apenas no Microsoft Intune e no AirWatch), o administrador de TI poderá configurar o Azure AD para permitir automaticamente o registro no MDM depois que o usuário entrar usando a conta do Azure AD. [Saiba como configurar o registro do Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Quando o registro automático está habilitado, nenhum registro manual adicional é necessário. Quando o usuário entra usando uma conta do Azure AD, o dispositivo é registrado no MDM depois de concluir a experiência de primeira execução.

## Registrar-se por meio do aplicativo Configurações

 Quando o dispositivo não é registrado no MDM durante a experiência de primeira execução, o usuário pode registrar manualmente o dispositivo no servidor MDM da organização usando o aplicativo Configurações.

1. Vá até **Configurações** > **Contas** > **Acesso corporativo**.
1. Selecione **Registrar-se no gerenciamento de dispositivo (MDM)** e insira a conta organizacional. Você será redirecionado para a página de entrada da organização.
1. Após uma autenticação bem-sucedida no servidor MDM, uma mensagem de êxito será mostrada.

Agora o dispositivo está registrado no servidor MDM. O aplicativo Configurações agora refletirá que o dispositivo está registrado no gerenciamento de dispositivos.

## Cancelar inscrição do HoloLens do Intune

Você não pode [cancelar o registro](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) do HoloLens do Intune remotamente. Se o administrador cancelar o registro do dispositivo usando o MDM, o dispositivo será excluído do painel do Intune.
