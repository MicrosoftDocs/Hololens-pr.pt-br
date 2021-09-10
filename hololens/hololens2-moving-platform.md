---
title: Modo de plataforma móvel do HoloLens 2
description: Como usar o HoloLens em plataformas móveis
keywords: plataformas móveis, movimento dinâmico, hololens, modo de plataforma móvel
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 81b3231827fce9a2ae2d5e3105800685fedb917b
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428691"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Modo de plataforma móvel em plataformas móveis de movimento dinâmico baixo

No **Insider build 20348.1411** adicionamos suporte beta para acompanhamento em plataformas móveis de movimento dinâmico baixo no HoloLens 2. Depois de instalar o build e habilitar o Modo de Plataforma Móvel, você poderá usar o HoloLens 2 em ambientes anteriormente inacessíveis, como grandes navios e embarcações marinhas. Atualmente, o recurso tem como alvo habilitar apenas essas plataformas móveis específicas. Embora nada impeça você de tentar usar o recurso em outros ambientes, ele se concentra em adicionar suporte a esses ambientes primeiro.

> [!NOTE]
> Atualmente, esse recurso só está disponível por meio do Programa [Windows Insider](hololens-insider.md).

![Exemplo de plataforma móvel.](./images/mpm-compare.gif)

Este artigo cobre:

1. [Por que a Plataforma Móvel é necessária](#why-moving-platform-mode-is-necessary)
1. [Habilitando o Modo de Plataforma Móvel](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Por que o Modo de Plataforma Móvel é necessário

O HoloLens precisa acompanhar a posição da sua cabeça com [6 graus de liberdade](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (translação X, Y, Z e rotação de rolagem, arfagem e guinada) para mostrar hologramas estáveis. Para fazer isso, o HoloLens rastreia duas informações semelhantes de duas fontes separadas:

1. Câmeras de luz visíveis – que acompanham o ambiente, por exemplo, a local físico em que você está usando o HoloLens
1. IMU (Unidade de Medida Inercial) – que consiste em um acelerômetro, um giroscópio e um magnetômetro que acompanha o movimento e a orientação da cabeça em relação à Terra

As informações dessas duas fontes são compostas para acompanhar a posição sua da cabeça em uma baixa latência e alta frequência suficiente para renderizar hologramas suaves.

No entanto, essa abordagem se baseia em uma suposição crítica: o ambiente (controlado pelas câmeras) permanece estacionário em relação à Terra (que é a referência par as medidas da IMU). Quando esse não é o caso, como em um barco na água, as informações de ambas as fontes podem entrar em conflito entre si e fazer com que o rastreador fique perdido. Esse conflito produz informações de posição incorretas e resulta em hologramas instáveis ou até mesmo na perda de acompanhamento.

O Modo de Plataforma Móvel soluciona esse problema. Quando você habilita o Modo de Plataforma Móvel, isso gera uma dica para nosso rastreador de que não podemos confiar que as entradas dos nossos sensores são completamente confiáveis entre si o tempo todo. Em vez disso, precisamos depender mais do acompanhamento visual e identificar rapidamente dados de movimento inerciais incongruentes e filtrá-los adequadamente para podermos usar a entrada da IMU.

## <a name="supported-environments-and-known-limitations"></a>Ambientes com suporte e limitações conhecidas

Embora o Modo de Plataforma Móvel seja desenvolvido para lidar com casos de conflito de dados visuais e inerciais de maneira inteligente, ele está atualmente voltado para grandes embarcações marítimas com baixo movimento dinâmico. Isso significa que certamente há limitações e cenários sem suporte.

### <a name="known-limitations"></a>Limitações conhecidas

- Os únicos ambientes com suporte para o MPM (Modo de Plataforma Móvel) são grandes navios com movimento de baixa dinâmica. Em outras palavras, muitos ambientes/situações comuns ainda **não** têm suporte devido ao movimento de alta frequência e altos níveis de aceleração e [sacudidas](https://en.wikipedia.org/wiki/Jerk_(physics)). Por exemplo: aviões, trens, carros, bicicletas, ônibus, pequenos barcos, elevadores etc.
- Os hologramas podem oscilar um pouco quando o MPM está habilitado, especialmente quando estiver em água agitada.
- Nada impede que os usuários tentem usar o MPM em ambientes sem suporte. No entanto, os usuários poderão experimentar efeitos colaterais indesejáveis se o dispositivo for capaz de manter o acompanhamento no espaço sem suporte. Por exemplo, com o MPM, os usuários podem achar que é possível usar em um elevador ao mudar de andar, sendo que isso era impossível anteriormente. Infelizmente, embora o MPM permita que o dispositivo mantenha o controle, ele não lida com o gerenciamento de mapa no momento. Os usuários descobrirão que a mudança de andares em um elevador fará com que o dispositivo confunda os andares superiores e inferiores afetando negativamente a qualidade do mapa.

## <a name="prerequisites"></a>Pré-requisitos

O suporte beta para o Modo de Plataforma Móvel tem apenas alguns pré-requisitos:

1. Instale o build 20348.1411 ou mais recente [instalando a imagem do build mais recente do Insiders via ARC](hololens-insider.md#ffu-download-and-flash-directions) ou [registrando e atualizando seu dispositivo](hololens-insider.md#start-receiving-insider-builds).

   > [!NOTE]
   > Atualmente, esse build só está disponível no [Canal do Desenvolvedor do Insider](hololens-insider.md#start-receiving-insider-builds).

2. Habilite o [Modo de Desenvolvedor e o Portal de Dispositivos](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Habilitando o Modo de Plataforma Móvel

Para habilitar o modo de Plataforma Móvel, primeiro [habilite o Portal de Dispositivos](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Selecione a sanfona do **Sistema** no menu à esquerda

   ![Primeira imagem.](.\images\mpm-01.png)

2. Selecione a página **Modo de Plataforma Móvel** e marque a caixa de seleção **Modo de Plataforma Móvel**

    ![Segunda imagem.](.\images\mpm-02.png)

3. Quando se deparar com um aviso, selecione **OK**

   ![Terceira imagem.](.\images\mpm-03.png)

4. Reinicialize o dispositivo, o que pode ser feito por meio do menu **Power** do Portal de Dispositivos no canto superior direito ou emitindo o comando de voz &quot;Reinicializar o dispositivo&quot; e selecionando &quot;Sim&quot;.

   ![Quarta imagem.](.\images\mpm-04.png)

Se você não conseguir ver a opção para aceitar o Modo de Plataforma Móvel no Portal de Dispositivos, isso provavelmente significa que você ainda não está no build adequado. Confira a seção [Pré-requisitos](#prerequisites).

## <a name="reporting-issues"></a>Problemas de relatórios

Conforme mencionado acima, esse é um recurso beta disponível somente no Modo de Desenvolvedor, o que significa que você pode ter problemas. Se isso acontecer, podemos investigar e aprimorar o produto.

1. Relate o problema por meio do [Hub de Comentários](hololens-feedback.md) na categoria **Precisão, estabilidade e confiabilidade do holograma** e inclua:
    1. Uma descrição do problema, inclusive o comportamento esperado e o comportamento vivenciado
    1. Uma [captura de vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) da Realidade Misturada do problema
2.  Abra um caso de suporte em [https://aka.ms/hlsupport](https://aka.ms/hlsupport) e compartilhe a URL do Hub de Comentários, para que possamos entrar em contato caso tenhamos perguntas de acompanhamento