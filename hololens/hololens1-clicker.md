---
title: Usar o clicker do HoloLens
description: Este artigo descreve como usar o clicker do HoloLens, incluindo o emparelhamento, carregamento e recuperação com o clicker.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439047"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>Usar o clicker do HoloLens (1ª gen)

O clicker foi projetado especificamente para o HoloLens (1ª geração) e oferece outra maneira de interagir com o holograma. Ele vem com o HoloLens (1ª geração) em uma caixa separada.

Use-o ao invés de gestos de mão para selecionar, rolar, mover e redimensionar aplicativos.

## <a name="clicker-hardware-and-pairing"></a>Hardware e emparelhamento do clicker

O clicker do HoloLens (1ª geração) tem uma alça de dedo para facilitar a empunhadura e uma luz indicadora.

![O HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Luzes indicadoras do clicker

Veja o que as luzes no clicker significam.

- **Branco piscando**. O clicker está em modo de emparelhamento.
- **Branco piscando rapidamente**. O emparelhamento foi bem-sucedido.
- **Branco contínuo**. O clicker está carregando.
- **Âmbar piscando**. A bateria está baixa.
- **Âmbar contínuo**. O clicker teve um problema e você precisará reiniciá-lo. Enquanto pressiona o botão de emparelhamento, clique e segure por 15 segundos.

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>Emparelhar o clicker com seu HoloLens (1ª geração)

1. Use o gesto de abrir a mão para ir até **Iniciar**, em seguida, selecione **Configurações** > **Dispositivos** e verifique se o Bluetooth está ativado.
1. No clicker, pressione e mantenha pressionado o botão de emparelhamento até que a luz de status pisque na cor branca.
1. Na tela emparelhamento, selecione **Clicker** > **Emparelhar**.

### <a name="charge-the-clicker"></a>Carregar o clicker

Quando a bateria do clicker estiver baixa, o indicador da bateria piscará na cor âmbar. Conecte o cabo Micro USB a uma fonte de alimentação USB para carregar o dispositivo.

## <a name="use-the-clicker-with-hololens-1st-gen"></a>Utilize o clicker com seu HoloLens (1ª geração)

### <a name="hold-the-clicker"></a>Segure o clicker

Para manusear o clicker, deslize a alça em seus dedos anelar ou médio de forma que a porta Micro USB esteja virada em direção ao seu pulso. Coloque o polegar no recuo.

![Como segurar o clicker](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Gestos do clicker

Os gestos de clicker são pequenas rotações de punho, não os movimentos maiores usados para gestos de mão do HoloLens. E o HoloLens reconhece seus gestos e cliques, mesmo que o clicker esteja fora do [quadro de gesto](hololens1-basic-usage.md), para que você possa segurar o clicker na posição mais confortável para você.

- **Select**. Para selecionar um holograma, botão ou outro elemento, fixe o olhar nele e, em seguida, clique.

- **Clique e mantenha pressionado**. Clique e mantenha o dedo pressionado sobre o botão para executar algumas das mesmas coisas que você faria com toque e segure, como mover ou redimensionar um holograma.

- **Rolar**. Na barra do aplicativo, selecione a **Ferramenta de Rolagem**. Clique e mantenha pressionado, em seguida, gire o clicker para cima, para baixo, para a esquerda ou para a direita. Para rolar mais rapidamente, afaste a sua mão do centro da ferramenta de rolagem.

- **Zoom**. Na barra do aplicativo, selecione a **Ferramenta de Zoom**. Clique e mantenha pressionado, em seguida, gire o clicker para cima para aumentar ou diminuir o zoom.

> [!TIP]
> Para ampliar ou reduzir ao usar o Microsoft Edge, fixe o olhar em uma página e clique duas vezes.

## <a name="restart-or-recover-the-clicker"></a>Reiniciar ou recuperar o clicker

Aqui estão algumas coisas a serem feitas se o clicker do HoloLens não for responsivo ou não estiver funcionando corretamente.

### <a name="restart-the-clicker"></a>Reiniciar o clicker

Use a ponta de uma caneta para pressionar e segurar o botão de emparelhamento. Ao mesmo tempo, clique e mantenha pressionado o clicker por 15 segundos. Se o clicker já tiver sido emparelhado com o seu HoloLens, ele permanecerá emparelhado após ser reiniciado.

Se o clicker não ativar ou reiniciar, experimente carregá-lo o usando o carregador do HoloLens. Se a bateria estiver muito baixa, pode levar alguns minutos para que a luz branca do indicador seja ativada.

### <a name="re-pair-the-clicker"></a>Reemparelhar o clicker

Selecione **Configurações** > **Dispositivos** e selecione o clicker. Selecione **Remover**, aguarde alguns segundos e, em seguida, emparelhe o clicker novamente.

### <a name="recover-the-clicker"></a>Recuperar o clicker

Se reiniciar e reemparelhar o clicker não corrigir o problema, a Windows Device Recovery Tool poderá ajudá-lo a resolver. O processo de recuperação pode demorar um pouco e instalará a versão mais recente do software do programa. Para usar a ferramenta, você precisará de um computador que esteja executando o Windows 10 ou posterior, com pelo menos 4 GB de espaço de armazenamento disponível.

Para recuperar o clicker:

1. No computador, baixe e instale a [Windows Device Recovery Tool (WDRT).](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/)
1. Conecte o clicker ao seu computador usando o cabo micro USB que veio com o seu HoloLens.
1. Execute a Windows Device Recovery Tool e siga as instruções.

Se o clicker não for detectado automaticamente, selecione **Meu dispositivo não foi detectado** e siga as instruções para colocar o dispositivo no modo de recuperação.
