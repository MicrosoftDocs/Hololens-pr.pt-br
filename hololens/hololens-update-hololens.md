---
title: Atualizar HoloLens 2
description: Saiba como verificar seu número de Build do HoloLens, manter-se atualizado com as atualizações do dispositivo, ingressar no programa de pessoas e reverter atualizações.
keywords: como fazer, atualizar, reverter, HoloLens, verificar compilação, número de Build
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924104"
---
# <a name="update-hololens-2"></a>Atualizar HoloLens 2

O HoloLens usa Windows Update, assim como outros dispositivos Windows 10. Seu HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que ele estiver conectado à energia e conectado à Internet, mesmo quando ela estiver em espera.

Este artigo apresentará as ferramentas do HoloLens para:

- exibindo a versão atual do sistema operacional (número da versão)
- verificando se há atualizações
- atualizando manualmente o HoloLens
- reverter para uma atualização mais antiga

## <a name="check-your-operating-system-version-build-number"></a>Verificar a versão do sistema operacional (número da versão)

Você pode verificar o número de versão do sistema, (número da compilação) abrindo o aplicativo Configurações e selecionando **sistema**  >  **sobre**.

## <a name="check-for-updates-and-manually-update"></a>Verificar se há atualizações e atualizar manualmente

Você pode verificar se há atualizações a qualquer momento nas configurações.  Para ver as atualizações disponíveis e verificar se há novas atualizações:

1. Abra o aplicativo **Configurações**.
1. Navegue até **Atualizar & segurança**  >  **Windows Update**.
1. Selecione **Verificar se há atualizações**.

Se uma atualização estiver disponível, ela começará a baixar a nova versão. Após a conclusão do download, selecione o botão **reiniciar agora** para disparar a instalação. Se o dispositivo estiver abaixo de 40% e não conectado, a reinicialização não iniciará a instalação da atualização.

Enquanto o seu HoloLens está instalando a atualização, ele exibirá engrenagens giratórias e um indicador de progresso. Não desative seu HoloLens durante esse tempo. Ele será reiniciado automaticamente após a conclusão da instalação.

O HoloLens aplica uma atualização por vez.  Se o seu HoloLens for mais de uma versão por trás do mais recente, talvez seja necessário executar o processo de atualização várias vezes para atualizá-lo completamente.

## <a name="go-back-to-a-previous-version"></a>Voltar para uma versão anterior

Em alguns casos, talvez você queira voltar para uma versão anterior do software do HoloLens. As etapas recomendadas são:

1. Entre em contato com o suporte para ver se eles podem corrigir o problema.
    1. Verifique se a telemetria **opcional** ou **completa** está habilitada-isso torna seu bug mais acionável e mais fácil para os engenheiros diagnosticarem.
    1. Os [comentários de arquivo](hololens-feedback.md) são o mais descritivos possível. Anote o título ou use o recurso de compartilhamento para que você possa compartilhar seu bug com o suporte.
    1. Contate o [suporte](https://aka.ms/hlsupport). Se o problema for um que precisa ser resolvido retornando a uma versão anterior, eles podem fornecer a você o FFU para atualizar seu dispositivo.

1. Se isso não funcionar, [redefina ou repisque o seu HoloLens 2 com o complemento de recuperação avançada](hololens-recovery.md).
    1. No seu computador, baixe o [complemento de recuperação avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) do Microsoft Store.
    1. Certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.
    1. Escolha qual versão você deseja atualizar:
        1. Você pode baixar a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).
        1. Você pode usar a compilação padrão que os hosts ARC. (Se você escolher essa opção, ignore a próxima etapa.)
        1. Você pode usar um suporte de compilação fornecido com o.
    1. Depois de concluir esses downloads, abra o **Explorador de arquivos**  >  **downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.
    1. Conecte seu HoloLens ao seu PC usando um USB-a para um cabo USB-C. (Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)
    1. O complemento de recuperação avançada detecta automaticamente seu HoloLens. Selecione o bloco **Microsoft HoloLens** .
    1. Na próxima tela, selecione **seleção de pacote manual** e, em seguida, selecione o arquivo de instalação contido na pasta que você descompactou na etapa 4. (Procure um arquivo com a extensão. FFU.)
    1. Selecione **instalar software** e siga as instruções.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Além disso, se você quiser permanecer em sua versão atualmente instalada, também poderá [Pausar manualmente as atualizações](hololens-updates.md#pause-updates-via-device). Isso dará ao time da equipe de engenharia que o problema será corrigido.

## <a name="windows-insider-program-on-hololens"></a>Programa Windows Insider no HoloLens

Deseja ver os recursos mais recentes no HoloLens?  Nesse caso, junte-se ao programa Windows Insider; Você terá acesso a versões prévias de atualizações de software do HoloLens antes que elas estejam disponíveis para o público geral.

[Obtenha o Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).
