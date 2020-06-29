---
title: Compartilhar seu HoloLens com várias pessoas
description: Você pode configurar o HoloLens para ser compartilhado por várias contas do Azure Active Directory ou por vários usuários que usam uma única conta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827723"
---
# Compartilhar seu HoloLens com várias pessoas

É comum compartilhar um HoloLens com muitas pessoas ou fazer com que muitas pessoas compartilhem um conjunto de dispositivos HoloLens.  Este artigo descreve as diferentes maneiras nas quais você pode compartilhar um dispositivo.

## Compartilhe com várias pessoas, cada uma usando sua própria conta

**Pré-requisito**: o dispositivo HoloLens deve estar executando o Windows 10, versão 1803 ou posterior.  O HoloLens (1ª gen) também precisa ser [atualizado para o Windows holográfico for Business](hololens-upgrade-enterprise.md).

Quando eles usam suas próprias contas do Azure Active Directory (Azure AD), vários usuários podem manter suas próprias configurações de usuário e dados de usuário no dispositivo.

Para garantir que várias pessoas possam usar suas próprias contas em seu HoloLens, siga estas etapas para configurá-lo:

1. Verifique se o dispositivo está executando o Windows 10, versão 1803 ou posterior.
   > [!IMPORTANT]
   > Se você estiver usando um dispositivo HoloLens (1ª gen), [atualize o dispositivo para o Windows holográfico for Business](hololens1-upgrade-enterprise.md).
1. Ao configurar o dispositivo, selecione **minha empresa ou escola** e entre usando uma conta do Azure AD.
1. Depois de concluir a instalação, verifique se as configurações da conta (contas de**configurações**  >  **Accounts**) incluem **outros usuários**.

Para usar o HoloLens, cada usuário segue estas etapas:

1. Se outro usuário estiver usando o dispositivo, siga um destes procedimentos:
   - Pressione o botão liga/desliga uma vez para ir para o modo de espera e, em seguida, pressione o botão de energia novamente para retornar à tela de bloqueio
   - Os usuários do HoloLens 2 podem selecionar o bloco do usuário no menu Iniciar para desconectar o usuário atual.

1. Use as credenciais da sua conta do Azure AD para entrar no dispositivo.  
    Se esta for a primeira vez que você usou o dispositivo, você precisará [calibrar](hololens-calibration.md) o HoloLens para seus próprios olhos.

Para ver uma lista dos usuários do dispositivo ou remover um usuário do dispositivo, acesse **configurações**  >  **contas**  >  **outros usuários**.

## Compartilhar com várias pessoas, todas usando a mesma conta

Vários usuários também podem compartilhar um dispositivo HoloLens usando uma única conta de usuário.

**No HoloLens 2**, quando um novo usuário coloca o dispositivo na cabeça pela primeira vez (enquanto mantém a mesma conta conectada), o dispositivo solicita que o novo usuário calibre rapidamente e personalize a experiência de visualização. O dispositivo pode armazenar as informações de calibragem para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de exibição de cada usuário. Os usuários não precisam calibrar o dispositivo novamente.

**Em usuários do HoloLens (1ª gen)** , é preciso solicitar a recalibração no aplicativo configurações.  Leia mais sobre [calibragem](hololens-calibration.md).
