---
title: atualizar HoloLens 2
description: saiba como verificar seu número de build de HoloLens, manter-se atualizado com as atualizações de dispositivo, ingressar no programa de pessoas e reverter atualizações.
keywords: como fazer, atualizar, reverter, HoloLens, verificar compilação, número de build
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032020"
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

Por fim, algumas palavras sobre como planejar sua estratégia de atualização. Damos suporte a adiamentos de atualização. Portanto, você pode decidir por quanto tempo esperar depois que a Microsoft lançar uma atualização para instalar essa atualização nos dispositivos.

Às vezes, uma empresa gosta de experimentar todos os novos recursos para garantir que tudo funcione e esteja familiarizado com as novas atualizações para que sua equipe de suporte esteja preparada. Depois de confirmar que tudo está certo, eles distribuem as atualizações para toda a empresa. Ao associar subconjuntos de seus dispositivos a diferentes políticas de adiamento, conhecidas como anéis de atualização, você pode coordenar uma estratégia de distribuição de atualização para sua organização.

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
    1. Os [comentários de arquivo](hololens-feedback.md) são o mais descritivos possível. Anote o título ou use o recurso de compartilhamento para que você possa compartilhar seu bug com o suporte.
    1. Contate o [suporte](https://aka.ms/hlsupport). Se o problema for um que precisa ser resolvido retornando a uma versão anterior, eles podem fornecer a você o FFU para atualizar seu dispositivo.

1. se isso não funcionar, [redefina ou refaça o reflash do HoloLens 2 com o complemento de recuperação avançada](hololens-recovery.md).
    1. No seu computador, baixe o [complemento de recuperação avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) do Microsoft Store.
    1. certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.
    1. Escolha qual versão você deseja atualizar:
        1. você pode baixar a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).
        1. Você pode usar a compilação padrão que os hosts ARC. (Se você escolher essa opção, ignore a próxima etapa.)
        1. Você pode usar um suporte de compilação fornecido com o.
    1. Depois de concluir esses downloads, abra o **Explorador de arquivos**  >  **downloads**. Clique com o botão direito do mouse na pasta compactada que você baixou e selecione **extrair tudo**  >  **extrair** para descompactá-la.
    1. Conexão seu HoloLens ao seu PC usando um usb-a para cabo usb-C. (mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)
    1. O complemento de recuperação avançada detecta automaticamente seu HoloLens. Escolha o bloco **Microsoft HoloLens**.
    1. Na próxima tela, selecione **seleção de pacote manual** e, em seguida, selecione o arquivo de instalação contido na pasta que você descompactou na etapa 4. (Procure um arquivo com a `.ffu` extensão.)
    1. Selecione **instalar software** e siga as instruções.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Além disso, se você quiser permanecer em sua versão atualmente instalada, também poderá [Pausar manualmente as atualizações](hololens-updates.md#pause-updates-via-device). Isso dará ao time da equipe de engenharia que o problema será corrigido.

## <a name="windows-insider-program-on-hololens"></a>Windows Programa do insider no HoloLens

Deseja ver os recursos mais recentes no HoloLens?  nesse caso, junte-se ao programa insider Windows; você terá acesso a versões prévias de HoloLens atualizações de software antes que elas estejam disponíveis para o público geral.

[obtenha Windows insider preview para Microsoft HoloLens](hololens-insider.md).