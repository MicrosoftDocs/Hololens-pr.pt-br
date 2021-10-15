---
title: atualizar HoloLens 2
description: saiba como verificar seu número de build de HoloLens, manter-se atualizado com as atualizações de dispositivo, ingressar no programa de pessoas e reverter atualizações.
keywords: como fazer, atualizar, reverter, HoloLens, verificar compilação, número de build
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034256"
---
# <a name="update-hololens-2"></a>atualizar HoloLens 2

## <a name="overview"></a>Visão geral

Estamos sempre trabalhando em novos recursos, correções de bugs e atualizações de segurança. Você será notificado quando essas atualizações estiverem prontas.

com base em sua preferência, seu HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que ele estiver conectado à energia, conectado à Internet e até mesmo em espera.

para garantir que o HoloLens seja sempre atualizado, deixe-o conectado com o carregador que o acompanha. você também deseja que seu HoloLens conectado à internet. Dessa forma, ele baixará e instalará automaticamente as atualizações do sistema. 

com o serviço Windows Update, você controlará vários aspectos do processo de atualização, como quais dispositivos obtêm as atualizações em que momento. esse controle é útil porque você pode distribuir atualizações para um subconjunto de dispositivos HoloLens para teste. Em seguida, distribua as atualizações para as restantes. Ou você pode definir diferentes agendamentos de atualização para diferentes tipos de atualizações.

## <a name="types-of-updates"></a>Tipos de atualizações

por HoloLens, você pode gerenciar automaticamente dois tipos de atualizações.

- Atualizações de recursos: lançadas duas vezes por ano.
- Atualizações de qualidade: incluem atualizações de segurança críticas. Eles são liberados mensalmente ou conforme necessário.

Use o **Update** / **AllowAutoUpdate** para gerenciar a verificação, o download e a instalação de atualizações. 

## <a name="scheduling-updates"></a>Agendando atualizações

Você também pode definir um agendamento de atualização. Ele pode estar em um dia específico ou todos os dias, em um determinado momento. Por exemplo, às 17:00 ou fora do horário ativo.

Por fim, algumas palavras sobre como planejar sua estratégia de atualização. Damos suporte a adiamentos de atualização, para que você possa decidir por quanto tempo esperar depois que a Microsoft lançar uma atualização para instalar essa atualização nos dispositivos.

Às vezes, uma empresa gosta de experimentar todos os novos recursos para ter certeza de que tudo funciona e está familiarizado com as novas atualizações para que sua equipe de suporte seja preparada. Depois de confirmar que tudo está certo, eles distribuem as atualizações para toda a empresa. Ao associar subconjuntos de seus dispositivos a diferentes políticas de adiamento, conhecidas como anéis de atualização, você pode coordenar uma estratégia de distribuição de atualização para sua organização.

## <a name="hololens-update-tools"></a>ferramentas de atualização do HoloLens

esta seção o guiará pelas ferramentas de HoloLens para:

- verificando se há atualizações
- atualizando manualmente HoloLens
- exibindo a versão atual do sistema operacional (número da versão)
- reverter para uma atualização mais antiga

### <a name="check-for-updates-and-manually-update"></a>Verificar se há atualizações e atualizar manualmente

Você pode verificar se há atualizações a qualquer momento nas configurações.  Para ver as atualizações disponíveis e verificar se há novas atualizações:

1. Abra o aplicativo **Configurações**.
1. navegue até **atualizar & segurança**  >  **Windows Update**.
1. Selecione **Verificar se há atualizações**.

Se uma atualização estiver disponível, ela começará a baixar a nova versão. Após a conclusão do download, selecione o botão **reiniciar agora** para disparar a instalação. Se o dispositivo estiver abaixo de 40% e não conectado, a reinicialização não iniciará a instalação da atualização.

enquanto o HoloLens estiver instalando a atualização, ele exibirá engrenagens giratórias e um indicador de progresso. não desative seu HoloLens durante esse tempo. Ele será reiniciado automaticamente após a conclusão da instalação.

HoloLens aplica uma atualização por vez.  se sua HoloLens for mais de uma versão por trás da mais recente, talvez seja necessário executar o processo de atualização várias vezes para atualizá-la completamente.

### <a name="check-your-operating-system-version-build-number"></a>Verificar a versão do sistema operacional (número da versão)

você pode verificar o número de versão do sistema (número da compilação) abrindo **Configurações** e selecionar **sistema**  >  **sobre**.

### <a name="go-back-to-a-previous-version"></a>Voltar para uma versão anterior

em alguns casos, talvez você queira voltar para uma versão anterior do software HoloLens. As etapas recomendadas são:

1. Entre em contato com o suporte para ver se eles podem corrigir o problema.
    1. Verifique se a telemetria **opcional** ou **completa** está habilitada-isso torna seu bug mais acionável e mais fácil para os engenheiros diagnosticarem.
    1. Nos [comentários do arquivo](hololens-feedback.md) , seja o mais descritivo possível. Anote o título ou use o recurso de compartilhamento para que você possa compartilhar seu bug com o suporte.
    1. Contate o [suporte](https://aka.ms/hlsupport). Se o problema for um que precisa ser resolvido retornando a uma versão anterior, eles podem fornecer a você o FFU para atualizar seu dispositivo.

1. se isso não funcionar, atualize novamente [o HoloLens 2 com o complemento de recuperação avançada](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Além disso, se você quiser permanecer em sua versão atualmente instalada, também poderá [Pausar manualmente as atualizações](hololens-updates.md#pause-updates-via-device). Isso dará ao time da equipe de engenharia que o problema será corrigido.

## <a name="windows-insider-program-on-hololens"></a>Windows Programa do insider no HoloLens

Deseja ver os recursos mais recentes no HoloLens?  nesse caso, junte-se ao programa insider Windows; você terá acesso a versões prévias de HoloLens atualizações de software antes que elas estejam disponíveis para o público geral.

[obtenha Windows insider preview para Microsoft HoloLens](hololens-insider.md).