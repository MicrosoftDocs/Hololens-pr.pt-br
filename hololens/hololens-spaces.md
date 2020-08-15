---
title: Mapear espaços físicos com o HoloLens
description: O HoloLens aprende como um espaço é ao longo do tempo. Os usuários podem facilitar esse processo, movimentando o HoloLens de algumas maneiras pelo espaço.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, design, mapeamento espacial, HoloLens, reconstrução da superfície, malha, controle de cabeças, mapeamento
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: 6f2ec9ced776166f96eddcd601bef5de715703a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931833"
---
# Mapear espaços físicos com o HoloLens

O HoloLens mistura hologramas com o seu mundo físico. Para fazer isso, o HoloLens precisa saber mais sobre o mundo físico ao seu redor e lembrar-se de onde você coloca os hologramas dentro desse espaço.

Com o tempo, o HoloLens cria um *mapa espacial* do ambiente que ele vê.  O HoloLens atualiza o mapa conforme o ambiente é alterado. Enquanto você estiver conectado e o dispositivo estiver ativado, o HoloLens cria e atualiza seus mapas espaciais. Se você mantiver ou usar o dispositivo com as câmeras apontadas para um espaço, o HoloLens tentará mapear a área. Apesar do HoloLens aprender naturalmente sobre o espaço ao longo do tempo, existem formas de você ajudar o HoloLens a mapear seu espaço de maneira mais rápida e eficiente.  

> [!NOTE]
> Se o seu HoloLens não puder mapear o seu espaço ou estiver sem calibração, o HoloLens poderá entrar em Modo limitado. No Modo limitado, não será possível posicionar os hologramas nos arredores.

Este artigo explica como o HoloLens mapeia os espaços, como melhorar o mapeamento espacial e como gerenciar os dados espaciais que o HoloLens coleta.

## Escolha e configuração e seu espaço

Os recursos do seu ambiente podem dificultar a interpretação que o HoloLens faz de um espaço. Os níveis de luz, os materiais no espaço, a disposição dos objetos e outros podem afetar como o HoloLens mapeia uma área.

O HoloLens funciona melhor em certos tipos de ambiente. Para produzir o melhor mapa espacial, escolha um cômodo que tenha claridade e espaço suficiente. Evite espaços escuros e cômodos com grande quantidade de superfícies escuras, brilhantes ou translúcidas (por exemplo, espelhos ou cortinas de gaze).

O HoloLens está otimizado para uso interno. O mapeamento espacial também funciona melhor quando o Wi-Fi está ativado, embora ele não precise estar conectado a uma rede. O HoloLens pode obter pontos de acesso Wi-Fi mesmo se ele não estiver conectado ou autenticado. A funcionalidade do HoloLens não altera se os pontos de acesso são conectados à Internet ou somente na intranet/local.

Use o HoloLens apenas em locais seguros sem riscos de acidentes. [Mais sobre segurança](https://support.microsoft.com/help/4023454/safety-information).

## Mapeando seu espaço

Agora você está pronto para começar a mapear o seu espaço.  Quando o HoloLens começar a mapear seus arredores, você verá um gráfico de malha se espalhando pelo espaço.  Na página inicial da realidade misturada, você pode acionar a exibição do mapa selecionando uma superfície mapeada.

Estas são as diretrizes para a criação de um ótimo mapa espacial.

### Compreendendo os cenários da área

É importante gastar na maior parte do tempo onde você usará o HoloLens, para que o mapa seja relevante e completo. Por exemplo, se um cenário de usuário do HoloLens envolve uma mudança do Ponto A para o Ponto B, faça esse trajeto três vezes, olhando para todas as direções à medida que você se movimenta.  

### Percorra o espaço lentamente

Se você andar rapidamente em torno da área, provavelmente o HoloLens perderá áreas de mapeamento. Percorra o espaço lentamente, parando a cada 1.73m para olhar para os arredores.  

Os movimentos suaves também ajudam o HoloLens a mapear de maneira mais eficiente.

### Olhe para todas as direções

Olhar ao redor enquanto você mapeia o espaço fornece ao HoloLens mais dado sobre onde os pontos são relativos entre si.  

Se você não olha para cima, por exemplo, o HoloLens pode não saber onde está o teto de um cômodo.  

Não se esqueça de olhar para o chão ao mapear o espaço.

### Aborde as principais áreas várias vezes

Percorrer uma área várias vezes ajudará a captar recursos que você pode ter perdido na primeira caminhada. Para criar um mapa ideal, experimente percorrer uma área de duas a três vezes.

Se possível, durante a repetição desses movimentos, passe um tempo andando em uma área em uma direção e, em seguida, vire e volte pelo caminho que você fez.

### Faça o mapeamento da área no seu tempo

Pode levar de 15 a 20 minutos para que o HoloLens mapeie totalmente e se ajuste aos seus arredores. Se você tiver um espaço no qual planeja usar um HoloLens frequentemente, dedicar esse tempo para mapear o espaço poderá evitar problemas mais tarde.  

## Possíveis erros no mapa espacial

Os erros nos dados de mapeamento espacial se enquadram em algumas categorias:

- *Buracos*: superfícies reais estão ausentes nos dados de mapeamento espacial.
- *Alucinações*: existem superfícies nos dados de mapeamento espacial que não existem no mundo real.
- *Buraco de Minhoca*: o HoloLens 'perde' parte do mapa espacial, pensando que está em uma parte diferente do mapa do que realmente está.
- *Viés*: as superfícies nos dados de mapeamento espacial estão alinhadas imperfeitamente com superfícies reais, empurradas ou retiradas.

Se você vir qualquer um desses erros, use o [FeedbackHub](hololens-feedback.md) para enviar comentários.

## Segurança e armazenamento para dados espaciais

A atualização da versão 1803 do Windows 10 para o Microsoft HoloLens e versões posteriores armazenam o  mapeamento de dados em um banco de dados local (no dispositivo).

Os usuários do HoloLens não podem acessar diretamente o banco de dados do mapa, mesmo quando o dispositivo estiver conectado a um computador ou usando o aplicativo do Explorador de Arquivos. Quando o BitLocker está habilitado no HoloLens, os dados armazenados do mapa também são criptografados juntamente com o volume inteiro.

### Remover dados de mapa e espaços conhecidos do HoloLens

Há duas opções para excluir dados de mapa em **Configurações > Sistema > Hologramas**:

- Para excluir hologramas próximos, marque **Remover hologramas próximos**. Esse comando limpa os dados do mapa e os hologramas ancorados do espaço atual. Se você continuar usando o dispositivo no mesmo espaço, o programa cria e armazena uma nova seção de mapa para substituir as informações excluídas.

   > [!NOTE]
   > Os hologramas "próximos" são hologramas ancorados na mesma seção do mapa no espaço atual.

   Por exemplo, você pode usar essa opção para limpar os dados do mapa relacionados ao trabalho, sem afetar os dados do mapa relacionados à página inicial.

- Para excluir todos os hologramas, marque **Remover todos os hologramas**. Esse comando limpa todos os dados do mapa armazenados no dispositivo, bem como todos os hologramas ancorados. Será necessário posicionar os hologramas explicitamente. Você não poderá redescobrir os hologramas inseridos anteriormente.

> [!NOTE]
> Depois de remover o holograma ou todos os hologramas, o HoloLens começa a verificar e mapear o espaço atual imediatamente.

### Dados Wi-Fi em mapas espaciais

O HoloLens armazena características de Wi-Fi para ajudar a correlacionar os locais de holograma e a mapear seções armazenadas no banco de dados do HoloLens de espaços conhecidos. As informações sobre características de Wi-Fi não são acessíveis aos usuários e não são enviadas para a Microsoft usando nuvem ou telemetria.

Enquanto o Wi-Fi estiver habilitado, o HoloLens correlaciona os dados do mapa com pontos de acesso de rede Wi-Fi próximos. Não há diferença no comportamento, esteja uma rede está conectada ou apenas detectada nas proximidades. Se o Wi-Fi estiver desabilitado, o HoloLens ainda pesquisará o espaço. No entanto, o HoloLens deve pesquisar mais dados de mapa dentro do banco de dados dos espaços e talvez precise de mais tempo para encontrar hologramas. Sem as informações de Wi-Fi, o HoloLens tem que comparar as verificações ativas a todas as âncoras de holograma e as seções de mapa armazenadas no dispositivo para localizar a parte correta do mapa.

## Tópicos relacionados

- [Design de mapeamento espacial](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
