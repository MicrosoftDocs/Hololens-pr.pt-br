---
title: Atualização HoloLens 2
description: Saiba como verificar seu número HoloLens build, manter-se atualizado com as atualizações do dispositivo, ingressar no Programa Insiders e reverter atualizações.
keywords: how-to, update, roll back, HoloLens, check build, build number
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
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662843"
---
# <a name="update-hololens-2"></a>Atualização HoloLens 2

HoloLens usa Windows Update, assim como outros Windows 10 dispositivos. O HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que ele estiver conectado à energia e conectado à Internet, mesmo quando estiver em espera.

Este artigo explica as HoloLens ferramentas para:

- exibindo a versão atual do sistema operacional (número de build)
- verificando se há atualizações
- atualizando manualmente HoloLens
- reverter para uma atualização mais antiga

## <a name="check-your-operating-system-version-build-number"></a>Verificar a versão do sistema operacional (número de build)

Você pode verificar o número de versão do sistema (número de build) abrindo o aplicativo Configurações e selecionando **Sistema**  >  **Sobre**.

## <a name="check-for-updates-and-manually-update"></a>Verificar se há atualizações e atualizar manualmente

Você pode verificar se há atualizações a qualquer momento nas configurações.  Para ver as atualizações disponíveis e verificar se há novas atualizações:

1. Abra o aplicativo **Configurações**.
1. Navegue até **Atualizar & Segurança Windows**  >  **Atualizar**.
1. Selecione **Verificar atualizações**.

Se uma atualização estiver disponível, ela começará a baixar a nova versão. Depois que o download for concluído, selecione o **botão Reiniciar Agora** para disparar a instalação. Se o dispositivo estiver abaixo de 40% e não estiver conectado, a reinicialização não iniciará a instalação da atualização.

Enquanto o HoloLens estiver instalando a atualização, ele exibirá engrenagens giratórias e um indicador de progresso. Não desligue seu HoloLens durante esse tempo. Ele será reiniciado automaticamente depois de concluir a instalação.

HoloLens aplica uma atualização por vez.  Se o HoloLens estiver mais de uma versão atrás da versão mais recente, talvez seja necessário executar o processo de atualização várias vezes para que ele fique totalmente atualizado.

## <a name="go-back-to-a-previous-version"></a>Go back para uma versão anterior

Em alguns casos, talvez você queira voltar para uma versão anterior do HoloLens software. As etapas recomendadas são:

1. Entre em contato com o Suporte para ver se eles podem corrigir o problema.
    1. Verifique se **a** **telemetria** opcional ou completa está habilitada– isso torna o bug mais a actionable e mais fácil para os engenheiros diagnosticarem.
    1. [Comentários de arquivo](hololens-feedback.md) sendo o mais descritivo possível. Anote o título ou use o recurso de compartilhamento para que você possa compartilhar o bug com o Suporte.
    1. Entre em [contato com o Suporte](https://aka.ms/hlsupport)do . Se o problema for aquele que precisa ser resolvido retornando para uma versão anterior, ele poderá fornecer o FFU para piscar seu dispositivo.

1. Se isso não funcionar, redefinir ou [reflash seu HoloLens 2 com o Advanced Recovery Companion](hololens-recovery.md).
    1. No computador, baixe o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) no Microsoft Store.
    1. Certifique-se de que você não tenha telefones ou Windows conectados ao computador.
    1. Escolha para qual versão você deseja piscar:
        1. Você pode baixar a [versão mais recente HoloLens 2.](https://aka.ms/hololens2download)
        1. Você pode usar o build padrão que o ARC hospeda. (Se você escolher essa opção, ignore a próxima etapa.)
        1. Você pode usar um suporte de build fornecido com você.
    1. Quando você terminar esses downloads, abra **Explorador de Arquivos**  >  **Downloads**. Clique com o botão direito do mouse na pasta recortada que você acabou de baixar e selecione **Extrair tudo**  >  **extrair** para descomplicá-la.
    1. Conexão seu HoloLens no computador usando um cabo USB-A para USB-C. (Mesmo que você tenha usado outros cabos para conectar seu HoloLens, esse funcionará melhor.)
    1. O Advanced Recovery Companion detecta automaticamente seu HoloLens. Escolha o bloco **Microsoft HoloLens**.
    1. Na próxima tela, selecione **Seleção manual** de pacotes e, em seguida, selecione o arquivo de instalação contido na pasta que você desemcortou na etapa 4. (Procure um arquivo com a extensão .ffu.)
    1. Selecione **Instalar software** e siga as instruções.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Além disso, se você quiser permanecer em sua versão instalada no momento, também poderá pausar manualmente [as atualizações](hololens-updates.md#pause-updates-via-device). Isso dará tempo à equipe de engenharia para corrigir o problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programa Insider em HoloLens

Deseja ver os recursos mais recentes no HoloLens?  Em caso disso, insinte o Windows Programa Insider; Você obterá acesso a builds de visualização HoloLens atualizações de software antes que elas estão disponíveis para o público em geral.

[Obter Windows versão prévia do Insider para Microsoft HoloLens](hololens-insider.md).
