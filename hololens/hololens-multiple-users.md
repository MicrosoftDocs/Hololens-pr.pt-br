---
title: Compartilhar seu HoloLens com várias pessoas
description: Você pode configurar HoloLens para serem compartilhados por várias Azure Active Directory ou por vários usuários que usam uma única conta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032031"
---
# <a name="share-your-hololens-with-multiple-people"></a>Compartilhar seu HoloLens com várias pessoas

## <a name="overview"></a>Visão geral
As empresas geralmente invistam em muitos dispositivos HoloLens compartilhados. A maneira como você HoloLens é flexível em todo o painel, dependendo de seus requisitos individuais. Aqui está um exemplo de algumas experiências de vários usuários: 

- Dispositivos que são cobrados e têm Guias do Dynamics 365 e permitem que seus funcionários abram o aplicativo Configurações para fazer ajustes no Wi-Fi necessário, mas a política de Visibilidade de Página Configurações está habilitada para limitar a quantidade de páginas disponíveis no aplicativo Configurações.
- Dispositivos que são para a Assistência Remota e seu aplicativo de linha de negócios que são destinados a outras empresas. Esses dispositivos têm Quiosques que incluem apenas seu aplicativo e o Remote Assist. O WDAC é usado para impedir que o aplicativo Configurações e Microsoft Edge seja lançado. Incluído no aluguel está um pacote de bateria USB-C para manter os dispositivos com carga total em vários turnos.
- Todos os seus dispositivos estão definidos para o Autopilot e baixam todos os aplicativos da empresa. Você definiu alguns perfis de quiosque diferentes, direcionando diferentes grupos do Azure AD. Cada usuário faz login no HoloLens usando chaves FIDO2 e entrando em sua própria conta do Azure AD e é apresentado com uma experiência personalizada.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Compartilhar com várias pessoas, cada uma usando sua própria conta

**Pré-requisito:** o HoloLens deve estar executando Windows 10, versão 1803 ou posterior.  HoloLens (1ª geração) também precisa ser [atualizado para Windows Holographic for Business](hololens-upgrade-enterprise.md).

Quando eles usam suas próprias contas Azure Active Directory (Azure AD), vários usuários podem manter suas próprias configurações de usuário e dados de usuário no dispositivo.

Para garantir que várias pessoas possam usar suas próprias contas em seu HoloLens, siga estas etapas para configurá-la:

1. Certifique-se de que o dispositivo está Windows 10 versão 1803 ou posterior.
   > [!IMPORTANT]
   > Se você estiver usando um HoloLens (1ª geração), [atualize o dispositivo para Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Quando você configurar o dispositivo, selecione Minha empresa ou **escola** é proprietária dele e entre usando uma conta do Azure AD.
1. Depois de concluir a instalação, certifique-se de que as configurações da conta (**Configurações**  >  **Contas**) **incluam Outros usuários**.

Para usar HoloLens, cada usuário segue estas etapas:

1. Se outro usuário estiver usando o dispositivo, escolha uma das seguintes opções:
   - Pressione o botão de energia uma vez para ir para espera e, em seguida, pressione o botão de energia novamente para retornar à tela de bloqueio
   - HoloLens dois usuários podem selecionar o menu Iniciar para sair do usuário atual.

1. Use suas credenciais de conta do Azure AD para entrar no dispositivo.  
    Se for a primeira vez que você usou o [](hololens-calibration.md) dispositivo, será preciso calibrar HoloLens seus próprios olhos.

Para ver uma lista dos usuários do dispositivo ou para remover um usuário do dispositivo, vá para contas **Configurações**  >    >  **Outros usuários.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Compartilhar com várias pessoas, todas usando a mesma conta

Vários usuários também podem compartilhar um HoloLens ao usar uma única conta de usuário.

**No HoloLens 2,** quando um novo usuário coloca o dispositivo na cabeça pela primeira vez (mantendo a mesma conta conectado), o dispositivo solicita que o novo usuário calibrar e personalizar rapidamente a experiência de exibição. O dispositivo pode armazenar as informações de calibragem para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de exibição de cada usuário. Os usuários não precisam calibrar o dispositivo novamente.

**No HoloLens (1ª geração)** usuários que compartilham uma conta precisarão pedir para recalibrar no aplicativo Configurações aplicativo.  Leia mais sobre [calibragem](hololens-calibration.md).