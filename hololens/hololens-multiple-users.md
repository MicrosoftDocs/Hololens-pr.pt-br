---
title: Compartilhar seu HoloLens com várias pessoas
description: Você pode configurar HoloLens para serem compartilhados por várias Azure Active Directory ou por vários usuários que usam uma única conta.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663079"
---
# <a name="share-your-hololens-with-multiple-people"></a>Compartilhar seu HoloLens com várias pessoas

É comum compartilhar um único HoloLens com muitas pessoas ou fazer com que muitas pessoas compartilhem um conjunto de HoloLens dispositivos.  Este artigo descreve as diferentes maneiras pelas quais você pode compartilhar um dispositivo.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Compartilhar com várias pessoas, cada uma usando sua própria conta

**Pré-requisito:** o HoloLens deve estar executando Windows 10, versão 1803 ou posterior.  HoloLens (1ª geração) também precisa ser [atualizado para Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando eles usam suas próprias contas Azure Active Directory (Azure AD), vários usuários podem manter suas próprias configurações de usuário e dados de usuário no dispositivo.

Para garantir que várias pessoas possam usar suas próprias contas em seu HoloLens, siga estas etapas para configurá-la:

1. Certifique-se de que o dispositivo está Windows 10 versão 1803 ou posterior.
   > [!IMPORTANT]
   > Se você estiver usando um HoloLens (1ª geração), [atualize o dispositivo para Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Ao configurar o dispositivo, selecione Minha empresa ou **escola** é proprietária dele e entre usando uma conta do Azure AD.
1. Depois de concluir a instalação, certifique-se de que as configurações da conta (**Configurações**  >  **Contas**) **incluam Outros usuários**.

Para usar HoloLens, cada usuário segue estas etapas:

1. Se outro usuário estiver usando o dispositivo, faça um dos seguintes:
   - Pressione o botão de energia uma vez para ir para espera e, em seguida, pressione o botão de energia novamente para retornar à tela de bloqueio
   - HoloLens dois usuários podem selecionar o menu Iniciar para sair do usuário atual.

1. Use suas credenciais de conta do Azure AD para entrar no dispositivo.  
    Se esta for a primeira vez que você [](hololens-calibration.md) usou o dispositivo, será preciso calibrar HoloLens seus próprios olhos.

Para ver uma lista dos usuários do dispositivo ou para remover um usuário do dispositivo, acesse Contas **Configurações**  >    >  **Outros usuários.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Compartilhar com várias pessoas, todas usando a mesma conta

Vários usuários também podem compartilhar um HoloLens ao usar uma única conta de usuário.

**No HoloLens 2,** quando um novo usuário coloca o dispositivo na cabeça pela primeira vez (mantendo a mesma conta conectado), o dispositivo solicita que o novo usuário calibrar e personalizar rapidamente a experiência de exibição. O dispositivo pode armazenar as informações de calibragem para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de exibição de cada usuário. Os usuários não precisam calibrar o dispositivo novamente.

**No HoloLens (1ª geração),** os usuários que compartilham uma conta precisarão solicitar a recalibrar no aplicativo Configurações aplicativo.  Leia mais sobre [calibragem](hololens-calibration.md).
