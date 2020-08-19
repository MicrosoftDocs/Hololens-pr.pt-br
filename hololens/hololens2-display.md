---
title: Visores do HoloLens 2
description: Expectativas sobre os visores do HoloLens 2. Diretrizes para configurar os visores e obter uma melhor qualidade de imagem.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: visor, calibragem, conforto, elementos visuais, qualidade, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 80ac6348dd2cba932316b690cafc4c5dc0331353
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940201"
---
# Visor do HoloLens 2

O visor do HoloLens 2 é uma combinação de guias de ondas e de projetores de luz. Os usuários olham através do guia de ondas, as lentes dentro do visor, ao colocar o headset. Os projetores de luz estão dentro do gabinete acima das sobrancelhas. O HoloLens 2 usa luz de laser para iluminar o visor.

## Solução de problemas

Para o HoloLens 2, siga as etapas abaixo para garantir a melhor qualidade visual de hologramas apresentados em visores:

* **Aumente o brilho do visor.** Os hologramas têm melhor aparência quando o visor está em seu nível mais brilhante.
* **Traga o visor para mais perto de seus olhos.** Gire o visor para baixo até a posição mais próxima aos seus olhos.
* **Desloque o visor para baixo.** Tente mover o suporte da testa para baixo, o que fará com que o visor fique mais perto do seu nariz.
* **Execute a calibragem dos olhos.** O visor usa a sua IPD (distância interpupilar) e o olhar para otimizar as imagens no visor. Se você não executar a calibragem dos olhos, a qualidade da imagem poderá ficar pior. Para executar a calibragem dos olhos, vá para **Configurações** > **Sistema** > **Calibragem** > **Executar calibragem dos olhos**.

## Perguntas frequentes

### O que são os padrões que costumam piscar nos cantos inferiores do visor?

Às vezes, seu HoloLens 2 exibirá padrões diferentes nos cantos inferiores esquerdo e direito do visor. Os exemplos são mostrados abaixo (GIFs animados). Esse padrão faz parte da operação normal do dispositivo HoloLens 2 para calibrar o visor para uma experiência ideal.

![Padrão bifásico](./images/DAT-Biphase-Fiducial.gif) ![Padrão geográfico](./images/DAT-GEO-Fiducial.gif)

### Por que não consigo tirar uma fotografia precisa do meu visor do HoloLens 2?

O visor do HoloLens 2 foi projetado para ser visto pelo olho humano. O dispositivo tem um sistema de correção de cores ativo que se adapta aos olhos do usuário. Em comparação com o olho humano, as câmeras veem os ambientes de maneira diferente e, a seguir, estão alguns fatores que podem afetar qualquer inconsistência entre o que uma câmera captura e o que o usuário vê.

* **Posição dos olhos.** O visor do HoloLens 2 foi projetado especificamente para a posição dos olhos do usuário. O HoloLens 2 emprega uma tecnologia de rastreamento dos olhos para se adaptar à posição dos olhos do usuário. Uma câmera mal posicionada por alguns milímetros que seja, pode causar distorção da imagem. O posicionamento preciso com uma câmera é difícil e precisa corresponder ao local exato e ao relevo do olho para o qual o dispositivo está realizando a correção de cores.
* **Movimento dos olhos.** O visor se adapta ao movimento dos olhos do usuário para ajustar as cores. O que é mostrado no visor pode ser diferente, dependendo se o usuário está olhando para o centro, para a borda ou para o canto do visor. Uma única captura de imagem poderia, na melhor das hipóteses, mostrar a aparência do visor para o eixo que corresponde à direção do olhar.
* **Exibição binocular.** O visor do HoloLens 2 foi projetado para ser visto com ambos os olhos. O cérebro se adapta para ver duas imagens e as combina juntas. As imagens de apenas um visor ignoram as informações do outro visor.
* **Tempo de exposição da câmera.** O tempo de exposição da câmera deve ser um múltiplo exato de 1/120 de segundo. A taxa de quadros do visor do HoloLens é de 120 Hz. Devido à forma como o HoloLens 2 desenha imagens, capturar um quadro único também não será suficiente para corresponder à experiência visual de uma pessoa. Ao mesmo tempo, se o dispositivo se mover, até mesmo micromovimentos, o sistema reprojetará a imagem no visor para estabilizar os hologramas. Capturar vários quadros enquanto evita que o HoloLens se mova, geralmente requer uma configuração de laboratório.
* **Tamanho da abertura da câmera.** O tamanho da abertura da câmera deve ser pelo menos 3 mm para capturar uma imagem precisa. As câmeras de telefones celulares com pequenas aberturas integram a luz de uma área menor do que o olho humano. O dispositivo aplica a correção de cores para padrões observados por aberturas maiores. Com pequenas aberturas, os padrões de uniformidade ficam mais nítidos e permanecem visíveis, apesar das correções de cores aplicadas pelo sistema.
* **Pupila de entrada da câmera.** A pupila de entrada da câmera deve ter pelo menos 3 mm de diâmetro para capturar uma imagem precisa. Caso contrário, a câmera capturará alguns padrões de alta frequência não visíveis ao olho. A posição da pupila de entrada deve estar na frente da câmera e posicionada na distância do relevo do olho para evitar a introdução de anomalias e outras variações na imagem capturada.
* **Posição da câmera.** As câmeras que atendem aos requisitos para visualizar o visor do HoloLens 2 são maiores, e fica difícil posicionar a câmera perto o suficiente do visor do HoloLens 2 para observar a imagem com correção de cores. Se a câmera estiver no lugar errado, a correção de cores poderá afetar negativamente a captura do visor do HoloLens 2.
* **Correção de imagem.** As câmeras digitais comuns e as câmeras de smartphone aplicam uma TRC (curva de reprodução de tom) que aumenta o contraste e a cor para fornecer um resultado mais rápido. Quando aplicada a um visor do HoloLens 2, esta curva de tom amplifica as não uniformes.

Dito isso, ainda é possível para câmeras industriais especializadas capturarem imagens representativas do visor do HoloLens 2. Infelizmente, as câmeras de smartphones, as comuns e as profissionais não capturam imagens que correspondam ao que o usuário vê no HoloLens 2.

### O que a calibragem dos olhos faz para exibir a qualidade da imagem?

O visor do HoloLens 2 corrige ativamente as cores das imagens com base na posição dos olhos do usuário. A [calibragem dos olhos](hololens-calibration.md) fornece duas entradas importantes: (1) a IPD (distância interpupilar) do usuário e (2) a direção que cada olho está olhando. Sem a calibração dos olhos, o sistema usa como padrão uma posição nominal dos olhos sem movimento ocular. A diferença entre correção de cor ativa e nenhuma correção, dependerá da própria fisiologia do usuário. Por exemplo, os usuários que têm a mesma IPD do padrão do sistema verão menos melhorias na correção de cores. Enquanto os usuários que têm uma IPD muito mais estreita ou mais ampla do que o padrão do sistema, verão mais alterações na imagem do visor.

Observação: um novo recurso em uma atualização futura do sistema operacional começará a [detectar automaticamente a posição dos olhos](hololens-insider.md#auto-eye-position-support). Os usuários podem se inscrever no [Insider Preview](hololens-insider.md) para experimentar esse recurso agora.

### Quais são as diferenças entre os visores do HoloLens (1ª geração) e do HoloLens 2?

Entre as principais solicitações que os clientes fizeram à Microsoft após experimentarem o HoloLens 1 foram (1) aumentar o campo de visão e (2) aumentar o brilho. Os desenvolvimentos tecnológicos permitiram que a Microsoft produzisse guias de ondas que dobrassem a área do campo de visão e produzisse projetores de luz com um visor até três vezes mais brilhante. O hardware define a linha de base para um trio de compensações para a qualidade da imagem do visor: (1) campo de visão, (2) brilho e (3) uniformidade das cores. O avanço contínuo da tecnologia permite aperfeiçoamentos em todas as áreas sem sacrificar outra área. Provisoriamente, a tecnologia existente define os limites disponíveis para essas compensações.

### Quais aperfeiçoamentos estão chegando para melhorar a qualidade de imagem do HoloLens 2?

Embora haja várias investigações em andamento para melhorar a qualidade de imagem, espera-se que as seguintes áreas cheguem nas próximas atualizações:

* **Posição dos olhos automática.** Esse recurso permitirá que os procedimentos de calibragem dos olhos ocorra em segundo plano. Os usuários não precisarão mais executar a calibragem dos olhos para que as correções ativas de cores funcionem. Em vez disso, ele só funcionará.
* **Aperfeiçoamentos na calibragem de Cores.** Esta atualização foca nos valores das cores mais escuras (por exemplo, cinza escuro). No momento, as cores mais escuras adquirem um tom avermelhado. Esse problema também acontece quando todo o vídeo fica esmaecido, o visor inteiro fica com cores avermelhadas. Esse problema é resultado de atividade excessiva no canal da cor vermelha para essas cores mais escuras. Caracterizamos as curvas de iluminação a laser nessas cores mais escuras e estamos trabalhando para oferecer um procedimento de calibragem ao usuário. O resultado será mais precisão das cores em todo o espectro de brilho. Isso não alterará a aparência dos fundos brancos com brilho total. Continuamos aconselhando o uso de padrões de design no modo escuro nos aplicativos.
* **Modo de Leitura.** É possível para os desenvolvedores de aplicativos trocar o campo de visão do visor para obter uma resolução angular maior. Os desenvolvedores de aplicativos podem substituir a matriz de projeção para que o conteúdo seja renderizado na resolução de desenho do visor. Esse recurso resulta em uma redução de 30% no campo de visão e em um aumento correspondente na resolução angular. O trabalho está em andamento para apresentar esse recurso ao Kit de Ferramentas de Realidade Misturada. Quando estiver disponível, o modo de leitura funcionará em qualquer sistema operacional do HoloLens 2; isso não dependerá de uma atualização do sistema operacional.

As atualizações do sistema operacional são entregues automaticamente. Você também pode testar versões anteriores de aperfeiçoamentos de software por meio do programa Insider Preview.

### Quais diretrizes estão disponíveis para os desenvolvedores aplicarem os princípios de design do modo escuro?

Os usuários terão uma melhor experiência se evitarem planos de fundo brancos. O modo escuro é um princípio de design usado por aplicativos para usar planos de fundo pretos ou de cores escuras. As configurações do sistema têm por padrão o modo escuro e podem ser ajustadas acessando **Configurações** > **Sistema** > **Cores**.

Os desenvolvedores são aconselhados a seguir as diretrizes de design do modo escuro:

* [Diretrizes de design do desenvolvedor para visores do HoloLens](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Tamanhos de fonte recomendados](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Quando um holograma exigir um plano de fundo branco, mantenha o tamanho do holograma menor do que o campo de visão total do visor. Esse tamanho permite aos usuários colocar o holograma no centro do visor.

### Como limpar o visor do HoloLens 2?

Use um tecido de microfibra para limpar suavemente o visor. Para higienizar o visor, umedeça levemente um pano com álcool isopropílico 70% e, em seguida, limpe o visor. Leia as diretrizes completas em [Perguntas frequentes sobre limpeza do HoloLens 2](hololens2-maintenance.md).
