---
title: Mapear espaços físicos com o HoloLens
description: O HoloLens aprende como um espaço é ao longo do tempo. Os usuários podem facilitar esse processo movimentando o HoloLens de algumas maneiras pelo espaço.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, design, spatial mapping, HoloLens, surface reconstruction, mesh, head tracking, mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640033"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapear espaços físicos com o HoloLens

O HoloLens combina os hologramas com o seu mundo físico. Para fazer isso, o HoloLens precisa saber mais sobre o mundo físico ao seu redor e se lembrar de onde você coloca os hologramas nesse espaço.

Com o tempo, o HoloLens cria um *mapa espacial* do ambiente que ele viu.  O HoloLens atualiza o mapa conforme o ambiente é alterado. Enquanto você está conectado e o dispositivo está ligado, o HoloLens cria e atualiza seus mapas espaciais. Se você mantiver ou usar o dispositivo com as câmeras apontadas para um espaço, o HoloLens tentará mapear a área. Apesar de o HoloLens aprender naturalmente sobre um espaço ao longo do tempo, existem formas de você ajudá-lo a mapear seu espaço de maneira mais rápida e eficiente.  

> [!NOTE]
> Se o HoloLens não puder mapear seu espaço ou estiver sem calibração, ele poderá entrar em Modo limitado. No Modo limitado, não será possível posicionar os hologramas nos arredores.

Este artigo explica como o HoloLens mapeia os espaços, como aprimorar o mapeamento espacial e como gerenciar os dados espaciais coletados pelo HoloLens.

## <a name="choosing-and-setting-up-and-your-space"></a>Como escolher e configurar seu espaço

Os recursos do ambiente podem dificultar a interpretação que o HoloLens faz de um espaço. Os níveis de luz, os materiais no espaço, a disposição dos objetos e outros aspectos podem afetar a forma como o HoloLens mapeia uma área.

O HoloLens funciona melhor em alguns tipos de ambientes. Para produzir o melhor mapa espacial, escolha um cômodo que tenha luz e espaço suficiente. Evite espaços escuros e cômodos com uma grande quantidade de superfícies escuras, brilhantes ou translúcidas (por exemplo, espelhos ou cortinas transparentes).

O HoloLens foi otimizado para uso interno. O mapeamento espacial também funciona melhor quando o Wi-Fi está ligado, embora ele não precise estar conectado a uma rede. O HoloLens pode obter os pontos de acesso Wi-Fi mesmo quando não está conectado ou autenticado. A funcionalidade do HoloLens não é alterada se os pontos de acesso estão conectados à Internet ou somente na intranet/no local.

Use o HoloLens apenas em locais seguros sem riscos de acidentes. [Mais informações sobre segurança](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Como mapear seu espaço

Agora você está pronto para começar a mapear seu espaço.  Quando o HoloLens começar a mapear seus arredores, você verá um gráfico de malha sendo distribuído pelo espaço.  Na Página Inicial da realidade misturada, dispare a exibição do mapa selecionando uma superfície mapeada.

Estas são as diretrizes para a criação de um ótimo mapa espacial.

### <a name="understand-the-scenarios-for-the-area"></a>Noções básicas dos cenários da área

É importante gastar a maior parte do tempo nos cenários em que você usará o HoloLens, para que o mapa seja relevante e completo. Por exemplo, se um cenário de usuário do HoloLens envolve uma movimentação do Ponto A para o Ponto B, faça esse trajeto de duas a três vezes olhando para todas as direções à medida que você se movimenta.  

### <a name="walk-slowly-around-the-space"></a>Percorra o espaço lentamente

Se você andar rapidamente em torno da área, provavelmente, o HoloLens perderá áreas de mapeamento. Percorra o espaço lentamente, parando a cada 1,73 m para olhar para os arredores.  

Os movimentos suaves também ajudam o HoloLens a mapear o espaço de maneira mais eficiente.

### <a name="look-in-all-directions"></a>Olhe para todas as direções

Se você olha ao redor enquanto mapeia o espaço, isso fornece ao HoloLens mais dados sobre onde os pontos são relativos entre si.  

Se você não olha para cima, por exemplo, o HoloLens pode não saber onde está o teto de um cômodo.  

Não se esqueça de olhar para o chão ao mapear o espaço.

### <a name="cover-key-areas-multiple-times"></a>Percorra as principais áreas várias vezes

Percorrer uma área várias vezes ajudará a capturar recursos que você pode ter perdido na primeira caminhada. Para criar um mapa ideal, experimente percorrer uma área de duas a três vezes.

Se possível, durante a repetição desses movimentos, passe um tempo andando em uma área em uma direção e, depois, vire e volte pelo caminho que você fez.

### <a name="take-your-time-mapping-the-area"></a>Faça o mapeamento da área no seu tempo

Pode levar de 15 a 20 minutos para que o HoloLens mapeie totalmente e se ajuste aos seus arredores. Se você tiver um espaço no qual pretende usar um HoloLens frequentemente, dedicar esse tempo para mapear o espaço poderá evitar problemas mais tarde.  

## <a name="possible-errors-in-the-spatial-map"></a>Possíveis erros no mapa espacial

Os erros nos dados de mapeamento espacial se enquadram em algumas categorias:

- *Buracos*: as superfícies reais estão ausentes dos dados de mapeamento espacial.
- *Alucinações*: existem superfícies nos dados de mapeamento espacial que não existem no mundo real.
- *Buracos de minhoca*: o HoloLens 'perde' uma parte do mapa espacial, pensando que está em uma parte diferente do mapa do que realmente está.
- *Desvios*: as superfícies nos dados de mapeamento espacial estão alinhadas imperfeitamente com as superfícies reais, encurtadas ou esticadas.

Se você observar um desses erros, use o [Hub de Comentários](hololens-feedback.md) para enviar comentários.

## <a name="security-and-storage-for-spatial-data"></a>Segurança e armazenamento de dados espaciais

A atualização do Windows 10 versão 1803 para o Microsoft HoloLens e versões posteriores armazena o mapeamento de dados em um banco de dados local (no dispositivo).

Os usuários do HoloLens não podem acessar diretamente o banco de dados do mapa, mesmo quando o dispositivo está conectado a um computador ou enquanto eles usam o aplicativo Explorador de Arquivos. Quando o BitLocker está habilitado no HoloLens, os dados armazenados do mapa também são criptografados com o volume inteiro.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Remover dados do mapa e espaços conhecidos do HoloLens

Há duas opções para excluir dados do mapa em **Configurações > Sistema > Hologramas**:

- Para excluir os hologramas próximos, selecione **Remover hologramas próximos**. Esse comando limpa os dados do mapa e os hologramas ancorados do espaço atual. Se você continuar usando o dispositivo no mesmo espaço, o programa criará e armazenará uma seção do mapa para substituir as informações excluídas.

   > [!NOTE]
   > Os hologramas "próximos" são hologramas ancorados na mesma seção do mapa no espaço atual.

   Por exemplo, você pode usar essa opção para limpar os dados do mapa relacionados ao trabalho, sem afetar os dados do mapa relacionados à residência.

- Para excluir todos os hologramas, selecione **Remover todos os hologramas**. Esse comando limpa todos os dados do mapa armazenados no dispositivo, bem como todos os hologramas ancorados. Será necessário posicionar os hologramas explicitamente. Você não poderá redescobrir os hologramas inseridos anteriormente.

> [!NOTE]
> Depois que você remove os hologramas próximos ou todos os hologramas, o HoloLens começa a verificar e mapear o espaço atual imediatamente.

### <a name="wi-fi-data-in-spatial-maps"></a>Dados do Wi-Fi em mapas espaciais

O HoloLens armazena as características do Wi-Fi para ajudar a correlacionar as localizações dos hologramas e a mapear as seções armazenadas no banco de dados do HoloLens de espaços conhecidos. As informações sobre as características do Wi-Fi não são acessíveis aos usuários e não são enviadas à Microsoft usando a nuvem nem a telemetria.

Enquanto o Wi-Fi está habilitado, o HoloLens correlaciona os dados do mapa com os pontos de acesso Wi-Fi próximos. Não há diferença no comportamento se uma rede está conectada ou se ela foi apenas detectada nas proximidades. Se o Wi-Fi estiver desabilitado, o HoloLens ainda pesquisará o espaço. No entanto, o HoloLens deve pesquisar mais dados do mapa dentro do banco de dados dos espaços e talvez precise de mais tempo para encontrar hologramas. Sem as informações do Wi-Fi, o HoloLens precisa comparar as verificações ativas com todas as âncoras de hologramas e as seções do mapa armazenadas no dispositivo para localizar a parte correta do mapa.

## <a name="related-topics"></a>Tópicos relacionados

- [Projeto de mapeamento espacial](/windows/mixed-reality/spatial-mapping)
