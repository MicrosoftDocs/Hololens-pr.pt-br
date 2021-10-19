---
title: Atualização HoloLens 2
description: Saiba como verificar seu número HoloLens build, manter-se atualizado com as atualizações do dispositivo, ingressar no Programa Insiders e reverter as atualizações.
keywords: how-to, update, roll back, HoloLens, check build, build number
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
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151690"
---
# <a name="update-hololens-2"></a>Atualização HoloLens 2

## <a name="overview"></a>Visão geral

Estamos sempre trabalhando em novos recursos, correções de bugs e atualizações de segurança. Você será notificado quando essas atualizações estão prontas.

Com base em sua preferência, o HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que estiver conectado à energia, conectado à Internet e até mesmo em espera.

Para garantir que o HoloLens esteja sempre atualizado, deixe-o conectado com o carregador que veio com ele. Você também deseja que seu HoloLens conectado à Internet. Dessa forma, ele baixará e instalará automaticamente as atualizações do sistema. 

Com Windows atualizar serviço, você controlará vários aspectos do processo de atualização, como quais dispositivos receberão quais atualizações no momento. Esse controle é útil porque você pode lançar atualizações em um subconjunto de HoloLens para teste. Em seguida, roll out updates to the remaining. Ou você pode definir diferentes agendamentos de atualização para diferentes tipos de atualizações.

## <a name="types-of-updates"></a>Tipos de atualizações

Por HoloLens, você pode gerenciar automaticamente dois tipos de atualizações.

- Atualizações de recursos: lançadas duas vezes por ano.
- Atualizações de qualidade: incluem atualizações de segurança críticas. Eles são liberados mensalmente ou conforme necessário.

Use **Atualizar** / **AllowAutoUpdate** para gerenciar a verificação, o download e a instalação de atualizações. 

## <a name="scheduling-updates"></a>Agendando atualizações

Você também pode definir um agendamento de atualização. Ele pode ser em um dia específico ou todos os dias, em um momento específico. Por exemplo, às 17h ou fora do horário ativo.

Por fim, algumas palavras sobre como planejar sua estratégia de atualização. Damos suporte a adiamentos de atualização, para que você possa decidir quanto tempo esperar depois que a Microsoft lançar uma atualização para instalar essa atualização nos dispositivos.

Às vezes, uma empresa gosta de experimentar todos os novos recursos primeiro para garantir que tudo funcione e esteja familiarizado com as novas atualizações para que sua equipe de suporte esteja preparada. Depois de confirmar que tudo é bom, eles lançarão as atualizações para toda a empresa. Ao associar subconjunto de seus dispositivos a diferentes políticas de adiamento, conhecidas como anéis de atualização, você pode coordenar uma estratégia de distribuição de atualizações para sua organização.

## <a name="hololens-update-tools"></a>HoloLens ferramentas de atualização

Esta seção o seguirá por meio HoloLens ferramentas para:

- verificando se há atualizações
- atualizando manualmente HoloLens
- exibindo a versão atual do sistema operacional (número de build)
- reverter para uma atualização mais antiga

### <a name="check-for-updates-and-manually-update"></a>Verificar se há atualizações e atualizar manualmente

Você pode verificar se há atualizações a qualquer momento nas configurações.  Para ver as atualizações disponíveis e verificar se há novas atualizações:

1. Abra o aplicativo **Configurações**.
1. Navegue até **Atualizar & Segurança Windows**  >  **Atualizar**.
1. Selecione **Verificar se há atualizações**.

Se uma atualização estiver disponível, ela começará a baixar a nova versão. Depois que o download for concluído, selecione o **botão Reiniciar Agora** para disparar a instalação. Se o dispositivo estiver abaixo de 40% e não estiver conectado, a reinicialização não iniciará a instalação da atualização.

Enquanto o HoloLens estiver instalando a atualização, ele exibirá engrenagens giratórias e um indicador de progresso. Não desligue seu HoloLens durante esse tempo. Ele será reiniciado automaticamente depois de concluir a instalação.

HoloLens aplica uma atualização por vez.  Se o HoloLens estiver mais de uma versão atrás da versão mais recente, talvez seja necessário executar o processo de atualização várias vezes para que ele fique totalmente atualizado.

### <a name="check-your-operating-system-version-build-number"></a>Verificar a versão do sistema operacional (número de build)

Você pode verificar o número de versão do sistema (número de build) **abrindo Configurações** e selecione **Sistema**  >  **Sobre**.

### <a name="go-back-to-a-previous-version"></a>Go back para uma versão anterior

Em alguns casos, talvez você queira voltar para uma versão anterior do HoloLens software. As etapas recomendadas são:

1. Entre em contato com o Suporte para ver se eles podem corrigir o problema.
    1. Verifique se **a** **telemetria** opcional ou completa está habilitada – isso torna o bug mais a actionable e mais fácil para os engenheiros diagnosticarem.
    1. Em [Comentários de Arquivo,](hololens-feedback.md) seja o mais descritivo possível. Anote o título ou use o recurso de compartilhamento para que você possa compartilhar seu bug com o Suporte.
    1. Entre em [contato com o Suporte](https://aka.ms/hlsupport)do . Se o problema for aquele que precisa ser resolvido retornando para uma versão anterior, ele poderá fornecer o FFU para piscar seu dispositivo.

1. Como alternativa, você pode [reflash seu HoloLens 2 com o Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device).
    1.  Escolha para qual versão você deseja piscar: 
        1.  Você pode baixar a [versão mais recente HoloLens 2.](https://aka.ms/hololens2download)
        1.  Você pode usar o build padrão que o ARC hospeda.
        1.  Você pode usar um suporte de build fornecido com você.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Além disso, se você quiser permanecer em sua versão instalada no momento, também poderá pausar manualmente [as atualizações](hololens-updates.md#pause-updates-via-device). Isso dará tempo à equipe de engenharia para corrigir o problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programa Insider no HoloLens

Deseja ver os recursos mais recentes no HoloLens?  Em caso disso, insinte o Windows Programa Insider; Você obterá acesso a builds de visualização de HoloLens de software antes que elas estão disponíveis para o público em geral.

[Obter Windows versão prévia do Insider para Microsoft HoloLens](hololens-insider.md).