---
title: Usar o clicador de HoloLens
description: Este artigo descreve como usar o clicador de HoloLens, incluindo emparelhamento do cliquer, cobrança e recuperação.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308270"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>Usar o clicador do HoloLens (1ª gen)

O clicer foi projetado especificamente para o HoloLens (1º gen) e oferece a você outra maneira de interagir com os hologramas. Ele vem com o HoloLens (1º gen), em uma caixa separada.

Use-o em vez de gestos de mão para selecionar, rolar, mover e redimensionar aplicativos.

## <a name="clicker-hardware-and-pairing"></a>Hardware e emparelhamento do clique

O clicador de HoloLens (1ª gen) tem um loop de dedo para tornar mais fácil de manter e uma luz de indicador.

![O clicador de HoloLens](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Luzes do indicador do clique

Veja o que as luzes do clicador significam.

- **Branco piscando**. O clico está no modo de emparelhamento.
- **Branco piscando rapidamente**. O emparelhamento foi bem-sucedido.
- **Branco sólido**. O clicador está carregando.
- **Âmbar piscando**. A bateria está baixa.
- **Âmbar estável**. O clicador encontrou um erro e você precisará reiniciá-lo. Ao pressionar o botão de emparelhamento, clique e mantenha pressionado por 15 segundos.

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>Emparelhe o clico com seu HoloLens (1º gen)

1. Use o gesto de cair para ir até **Iniciar**, selecione **configurações**  >  **dispositivos** e verifique se o Bluetooth está ativado.
1. No clico, pressione e segure o botão de emparelhamento até que a luz de status pisque branca.
1. Na tela de emparelhamento, selecione par de **clico**  >  .

### <a name="charge-the-clicker"></a>Cobrar o cliquedor

Quando a bateria do clicer estiver baixa, o indicador de bateria piscará em âmbar. Conecte o cabo micro USB a uma fonte de alimentação USB para cobrar o dispositivo.

## <a name="use-the-clicker-with-hololens-1st-gen"></a>Usar o clico com o HoloLens (1º gen)

### <a name="hold-the-clicker"></a>Mantenha o botão do clique

Para colocar no clicador, deslize o loop sobre o anel ou o dedo médio para que a porta micro USB se Oriente para o pulso. Apóie seu polegar no recuo.

![Como manter o clicador](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Gestos de clique

Gestos de clique são pequenas rotações de pulsos, e não os movimentos maiores usados para gestos de mão do HoloLens. E o HoloLens reconhece seus gestos e cliques mesmo se o clicador estiver fora do [quadro de gesto](hololens1-basic-usage.md), para que você possa manter o clico na posição mais confortável para você.

- **Selecione**. Para selecionar um holograma, um botão ou outro elemento, olhar-o e clique em.

- **Clique e mantenha pressionado**. Clique e mantenha seu polegar sobre o botão para fazer algumas das mesmas coisas que você faria com tocar e segurar, como mover ou redimensionar um holograma.

- **Role**. Na barra de aplicativos, selecione **ferramenta de rolagem**. Clique e mantenha pressionado, em seguida, gire o clique do mouse para cima, para baixo, para a esquerda ou para a direita. Para rolar mais rapidamente, mova-o para longe do centro da ferramenta de rolagem.

- **Zoom**. Na barra de aplicativos, selecione **ferramenta de zoom**. Clique e mantenha pressionado, em seguida, gire o clique para cima para ampliar ou reduzir para reduzir.

> [!TIP]
> Para ampliar ou reduzir ao usar o Microsoft Edge, olhar em uma página e clique duas vezes.

## <a name="restart-or-recover-the-clicker"></a>Reiniciar ou recuperar o clicador

Aqui estão algumas coisas a serem experimentadas se o clicador de HoloLens não estiver respondendo ou não estiver funcionando bem.

### <a name="restart-the-clicker"></a>Reiniciar o clicador

Use a ponta de uma caneta para pressionar e manter o botão de emparelhamento. Ao mesmo tempo, clique e mantenha o botão do clique pressionado por 15 segundos. Se o clicador já tiver sido emparelhado com o seu HoloLens, ele permanecerá emparelhado após ser reiniciado.

Se o clico não ativar ou reiniciar, tente cobrar usando o carregador do HoloLens. Se a bateria for muito baixa, pode levar alguns minutos para que a luz do indicador branco seja ativada.

### <a name="re-pair-the-clicker"></a>Emparelhar novamente o clicador

Selecione **configurações**  >  **dispositivos** e selecione o cliquedor. Selecione **remover**, aguarde alguns segundos e, em seguida, emparelhe o clicador novamente.

### <a name="recover-the-clicker"></a>Recuperar o clicador

Se a reinicialização e o reemparelhamento do clicador não corrigirem o problema, a ferramenta de recuperação de dispositivo do Windows poderá ajudá-lo a recuperá-lo. O processo de recuperação pode levar algum tempo e instalará a versão mais recente do software do clique. Para usar a ferramenta, você precisará de um computador com Windows 10 ou posterior que tenha pelo menos 4 GB de espaço livre de armazenamento.

Para recuperar o clicador:

1. Baixe e instale a [ferramenta de recuperação de dispositivo do Windows](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) em seu computador.
1. Conecte o clico ao seu computador usando o cabo micro USB que acompanha o seu HoloLens.
1. Execute a ferramenta de recuperação de dispositivo do Windows e siga as instruções.

Se o clicador não for detectado automaticamente, selecione **meu dispositivo não foi detectado** e siga as instruções para colocar seu dispositivo no modo de recuperação.
