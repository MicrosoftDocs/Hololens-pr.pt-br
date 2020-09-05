---
title: Considerações de ambiente HoloLens
description: Tenha a melhor experiência possível com o HoloLens ao otimizar o dispositivo para os seus olhos e o ambiente. Muitos fatores ambientais diferentes são mesclados para permitir o rastreamento, mas como um desenvolvedor de Realidade Misturada, há vários fatores que você pode ter em mente para ajustar um espaço para melhores hologramas.
keywords: quadro holográfico, campo de visão, fov, calibragem, espaços, ambiente, instruções
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
ms.openlocfilehash: dc8182d04a8cdc8a8ec3775a8e453a41d29486d3
ms.sourcegitcommit: 0abe53295191e22299d5be49f2cef4e85744d0fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993641"
---
# Considerações de ambiente HoloLens

O HoloLens combina o holográfico com o mundo "real", posicionando hologramas em seus arredores. Uma janela de aplicativo holográfica está "pendurada" na parede, uma bailarina holográfica gira sobre a mesa, orelhas de coelhinho repousam sobre a cabeça do seu amigo sem que ele perceba. Quando você estiver usando um jogo ou aplicativo imersivo, o mundo holográfico se espalhará para preencher seus arredores, mas você ainda conseguirá ver e se mover no espaço.

Os hologramas que você posicionar permanecerão no lugar, mesmo que o dispositivo seja desligado.

## Configurando um ambiente

Os dispositivos HoloLens sabem como posicionar hologramas estáveis e precisos *acompanhando* os usuários em um espaço. Sem o rastreamento adequado, o dispositivo não entende o ambiente nem o usuário dentro dele, portanto, os hologramas podem aparecer nos lugares errados, não aparecer sempre no mesmo lugar ou simplesmente não aparecer. Os dados usados para rastrear os usuários são representados no *mapa espacial*.  

O desempenho do rastreamento é muito influenciado pelo ambiente em que o usuário está, e o ajuste de um ambiente para induzir um rastreamento estável e consistente é uma arte em vez de uma ciência. Muitos fatores ambientais diferentes são mesclados para permitir o rastreamento, mas como um desenvolvedor de Realidade Misturada, há vários fatores que você pode ter em mente para ajustar um espaço para melhor rastreamento.

### Iluminação

O Windows Mixed Reality usa luz visual para rastrear a localização do usuário. Quando um ambiente é muito claro, as câmeras podem ficar saturadas e nada é visto. Se o ambiente for muito escuro, as câmeras não conseguirão obter informações suficientes e nada será visto. A iluminação deve ser regular e suficientemente clara para que uma pessoa possa ver sem esforço, mas não tão clara a ponto de ser desagradável à visão.  

Áreas com pontos de luz brilhante em uma área de penumbra geral também são problemáticas, pois a câmera precisa se ajustar ao entrar e sair de espaços claros. Isso pode fazer com que o dispositivo "se perca" e ache que a alteração na luz equivale a uma alteração de local. Níveis de luz estáveis em uma área resultarão em um melhor rastreamento.  

Qualquer iluminação externa também pode causar instabilidade no rastreador, pois o sol pode variar consideravelmente ao longo do tempo. Por exemplo, o rastreamento no mesmo espaço no verão versus no inverno pode produzir resultados drasticamente diferentes, pois a luz indireta externa pode ser maior em épocas diferentes do ano.  

Se você tiver um luxímetro, um lux estável de 500-1000 é um bom ponto de partida.  

#### Tipos de iluminação

Diferentes tipos de luz em um espaço também podem influenciar o rastreamento. Lâmpadas pulsam com a eletricidade em CA que passa por elas. Se a frequência da CA for de 50 Hz, a luz pulsará a 50 Hz. Para uma pessoa, essa pulsação não é perceptível. No entanto, a câmera de 30 fps do HoloLens vê essas alterações. Alguns quadros serão bem iluminados, alguns serão mal iluminados e alguns serão expostos em excesso à medida que a câmera tentar compensar os pulsos de luz.  

Nos EUA, a frequência elétrica padrão é de 60 Hz, então os pulsos das lâmpadas estão em harmonia com a taxa de quadros do HoloLens: pulsos de 60 Hz se alinham à taxa de quadros de 30 Fps do HoloLens. No entanto, muitos países têm um padrão de frequência de CA de 50 Hz, o que significa que alguns quadros do HoloLens serão realizados durante os pulsos e outros não. Em particular, a iluminação fluorescente na Europa é conhecida por causar problemas.  

Há alguns procedimentos que você pode tentar para resolver problemas de cintilação. A temperatura, a idade das lâmpadas e os ciclos de aquecimento são causas comuns de cintilação fluorescente e a substituição das lâmpadas pode ajudar. Apertar as lâmpadas e garantir que os consumos de corrente sejam constantes também podem ajudar.  

### Itens em um espaço

O HoloLens usa pontos de referência ambientais exclusivos, também conhecidos como *recursos*, para se localizar em um espaço.  

Um dispositivo quase nunca consegue rastrear em uma área com poucos recursos, pois ele não tem como saber onde se encontra no espaço. A adição de recursos às paredes de um espaço costuma ser uma boa maneira de melhorar o rastreamento. Pôsteres, símbolos colados em uma parede, plantas, objetos exclusivos ou outros itens similares ajudam. Uma mesa bagunçada é um bom exemplo de ambiente que leva a um bom rastreamento. Há muitos recursos diferentes em uma única área.  

Além disso, use recursos exclusivos no mesmo espaço. O mesmo pôster repetido várias vezes em uma parede, por exemplo, causará confusão no dispositivo, pois o HoloLens não saberá para qual dos pôsteres repetitivos está olhando. Uma maneira comum de adicionar recursos exclusivos é usar linhas de fita crepe para criar padrões exclusivos e não repetitivos ao longo das paredes e do piso de um espaço.  

Uma boa pergunta para se fazer é: se você visse apenas uma pequena parte da cena, poderia localizar-se exclusivamente no espaço? Se a resposta for não, é provável que o dispositivo também tenha problemas de rastreamento.

#### Buracos de minhoca

Se você tem duas áreas ou regiões que parecem iguais, o rastreador pode achar que são iguais. Isso faz com que o dispositivo se engane, achando que está em outro lugar. Chamamos esses tipos de áreas repetitivas de *buracos de minhoca*.  

Para evitar buracos de minhoca, tente evitar áreas idênticas no mesmo espaço. As áreas idênticas às vezes podem incluir estações fabris, janelas em um edifício, racks de servidores ou estações de trabalho. Rotular áreas ou adicionar recursos exclusivos a cada área de aparência semelhante pode ajudar a reduzir os buracos de minhoca.

### Movimento em um espaço

Se o ambiente mudar constantemente, o dispositivo não terá recursos estáveis para a localização.  

Quanto mais objetos em movimento estiverem em um espaço, incluindo pessoas, mais fácil será perder o rastreamento. Esteiras rolantes em movimento, itens em diferentes estados de construção e muitas pessoas em um espaço são conhecidos por causar problemas de rastreamento.

O HoloLens pode adaptar-se rapidamente a essas alterações, mas somente quando essa área está claramente visível para o dispositivo. Áreas que não são vistas com tanta frequência podem ficar para trás da realidade, o que pode causar erros no mapa espacial. Por exemplo, um usuário digitaliza um amigo e, em seguida, se vira enquanto o amigo sai da sala. Uma representação 'fantasma' do amigo persistirá nos dados de mapeamento espacial até que o usuário digitalize novamente o espaço que agora está vazio.

### Proximidade do usuário aos itens no espaço

Assim como as pessoas não conseguem focar bem em objetos próximos aos olhos, o HoloLens tem dificuldade quando os objetos estão próximos a suas câmeras. Se um objeto estiver muito próximo para ser visto com ambas as câmeras ou se estiver bloqueando uma câmera, o dispositivo terá muito mais problemas com o rastreamento dele.  

As câmeras conseguem ver objetos com pelo menos 15 cm de distância.

### Superfícies em um espaço

Superfícies muito refletivas provavelmente terão uma aparência diferente, dependendo do ângulo, o que afeta o rastreamento. Pense em um carro totalmente novo. Conforme você se move em torno dele, a luz se reflete e você vê diferentes objetos na superfície. Para o rastreador, os diferentes objetos refletidos na superfície representam um ambiente dinâmico e o dispositivo perde o rastreamento.

É mais fácil rastrear objetos menos brilhantes.

### Considerações de impressão digital do Wi-Fi

Desde que o Wi-Fi esteja habilitado, os dados do mapa serão correlacionados com uma impressão digital de Wi-Fi, mesmo quando não estiverem conectados a uma rede/roteador Wi-Fi real. Sem informações de Wi-Fi, o espaço e os hologramas podem ser reconhecidos com um pouco mais de lentidão. Se os sinais de Wi-Fi mudarem significativamente, o dispositivo pode achar que está em um espaço diferente.

A identificação da rede (como SSID ou endereço MAC) não é enviada à Microsoft e todas as referências de Wi-Fi são mantidas locais no HoloLens.

## Mapeando novos espaços

Ao inserir um novo espaço (ou carregar um existente), você verá um elemento gráfico de malha se espalhado pelo espaço. Isso significa que o dispositivo está mapeando seus arredores. Embora um HoloLens conheça um espaço ao longo do tempo, há dicas e truques para mapear espaços.

## Gerenciamento do ambiente

Há duas configurações que permitem aos usuários "limpar" os hologramas e fazer com que o HoloLens "esqueça" um espaço. Elas existem em **Hologramas e ambientes** no aplicativo de configurações, com a segunda configuração também sendo exibida em **Privacidade** nesse mesmo aplicativo.  

1. **Excluir hologramas próximos**. Quando você seleciona essa configuração, o HoloLens apaga todos os hologramas ancorados e todos os dados do mapa armazenados para o "espaço atual" onde o dispositivo está localizado. Uma nova seção do mapa seria criada e armazenada no banco de dados para esse local, depois que os hologramas fossem posicionados novamente nesse mesmo espaço.

1. **Excluir todos os hologramas**. Ao selecionar essa configuração, o HoloLens apagará TODOS os dados do mapa e os hologramas ancorados em todos os bancos de dados de espaços. Nenhum holograma será redescoberto e todos os hologramas precisarão receber novas posições para armazenar novamente seções do mapa no banco de dados.

## Qualidade do holograma

Os hologramas podem ser posicionados em todo o ambiente, locais altos, baixos e ao seu redor, mas você os verá por meio de um [quadro holográfico](https://docs.microsoft.com/windows/mixed-reality/holographic-frame) que fica diante dos seus olhos. Para obter a melhor visão, ajuste seu dispositivo para que você possa ver todo o quadro. E não hesite em andar pelo ambiente e explorar!

Para que os [hologramas](https://docs.microsoft.com/windows/mixed-reality/hologram) sejam nítidos, claros e estáveis, o HoloLens precisa ser calibrado apenas para você. Ao configurar o HoloLens pela primeira vez, você será orientado nesse processo. Mais tarde, se os hologramas não parecerem corretos ou se você estiver vendo muitos erros, poderá fazer ajustes.

Se você estiver com problemas para mapear espaços, tente excluir os hologramas próximos e mapear o espaço novamente.

### Calibragem

Se os hologramas parecerem irregulares ou tremidos, ou se você estiver com dificuldade para posicioná-los, a primeira coisa a tentar é o [aplicativo Calibragem](hololens-calibration.md). Esse aplicativo também pode ajudar se você estiver sentindo desconforto durante o uso do HoloLens.

Para acessar o aplicativo Calibragem, acesse **Configurações** > **Sistema** > **Utilitários**. Selecione **Abrir Calibragem** e siga as instruções.

Se outra pessoa for usar seu HoloLens, deverá executar o aplicativo Calibragem primeiro para que o dispositivo seja configurado corretamente para ela.

## Informações sobre temperatura e regulamentação

[Informações regulatórias do HoloLens](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): inclui informações sobre faixa de temperatura, alienação, interferência de rádio e TV, e muito mais.

Estas são algumas diretrizes a seguir ao usar o seu dispositivo:

1. Armazene o dispositivo em um ambiente dentro da faixa de temperatura (em Espera ou Desligado) por uma hora antes de usar o dispositivo.
1. Use o dispositivo em um ambiente dentro da faixa de temperatura.
1. Use o dispositivo internamente.
1. Use o dispositivo à sombra. mesmo quando em ambiente fechado, evite a luz solar direta pelas janelas ou claraboias.
1. Se você seguir as diretrizes acima, mas tiver problemas de superaquecimento inesperados, certifique-se de que a Telemetria total esteja habilitada antes de enviar [Comentários](hololens-feedback.md).

## Consulte também

- [Design de mapeamento espacial](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
- [Hologramas](https://docs.microsoft.com/windows/mixed-reality/hologram)
