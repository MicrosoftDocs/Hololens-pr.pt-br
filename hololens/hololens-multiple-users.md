---
title: Compartilhe seu HoloLens com várias pessoas
description: Você pode configurar o HoloLens para ser compartilhado por várias contas de Azure Active Directory ou por vários usuários que usam uma única conta.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308150"
---
# <a name="share-your-hololens-with-multiple-people"></a>Compartilhe seu HoloLens com várias pessoas

É comum compartilhar um HoloLens com muitas pessoas ou fazer com que muitas pessoas compartilhem um conjunto de dispositivos HoloLens.  Este artigo descreve as diferentes maneiras em que você pode compartilhar um dispositivo.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Compartilhar com várias pessoas, cada uma usando sua própria conta

**Pré-requisito**: o dispositivo HoloLens deve estar executando o Windows 10, versão 1803 ou posterior.  O HoloLens (1º gen) também precisa ser [atualizado para o Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando eles usam suas próprias contas do Azure Active Directory (AD do Azure), vários usuários podem manter suas próprias configurações de usuário e dados de usuário no dispositivo.

Para garantir que várias pessoas possam usar suas próprias contas em seu HoloLens, siga estas etapas para configurá-lo:

1. Verifique se o dispositivo está executando o Windows 10, versão 1803 ou posterior.
   > [!IMPORTANT]
   > Se você estiver usando um dispositivo HoloLens (1º gen), [atualize o dispositivo para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quando você configurar o dispositivo, selecione **meu trabalho ou escola que o possui** e entre usando uma conta do Azure AD.
1. Depois de concluir a instalação, verifique se as configurações da conta (contas de **configurações**  >  ) incluem **outros usuários**.

Para usar o HoloLens, cada usuário segue estas etapas:

1. Se outro usuário estiver usando o dispositivo, siga um destes procedimentos:
   - Pressione o botão de energia uma vez para ir para o modo de espera e pressione o botão de energia novamente para retornar à tela de bloqueio
   - Os usuários do HoloLens 2 podem selecionar o bloco do usuário no menu Iniciar para sair do usuário atual.

1. Use suas credenciais de conta do Azure AD para entrar no dispositivo.  
    Se esta for a primeira vez que você usou o dispositivo, você precisará [calibrar](hololens-calibration.md) o HoloLens para seus próprios olhos.

Para ver uma lista dos usuários do dispositivo ou remover um usuário do dispositivo, vá para **configurações**  >  **contas**  >  **outros usuários**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Compartilhar com várias pessoas, tudo usando a mesma conta

Vários usuários também podem compartilhar um dispositivo HoloLens ao usar uma única conta de usuário.

**No HoloLens 2**, quando um novo usuário coloca o dispositivo na cabeça pela primeira vez (enquanto mantém a mesma conta conectada), o dispositivo solicita que o novo usuário calibre rapidamente e personalize a experiência de exibição. O dispositivo pode armazenar as informações de calibragem para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de exibição de cada usuário. Os usuários não precisam calibrar o dispositivo novamente.

**Em usuários do HoloLens (1ª gen)** , o compartilhamento de uma conta precisará solicitar a recalibração no aplicativo configurações.  Leia mais sobre [calibragem](hololens-calibration.md).
