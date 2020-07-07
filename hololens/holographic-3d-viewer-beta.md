---
title: Usar o Visualizador 3D no HoloLens (1ª geração)
description: Descreve os tipos de arquivos e recursos que o Visualizador 3D no HoloLens (1ª ger.) oferece suporte e como usar e solucionar problemas do aplicativo.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 47fe1fd5dc164c56ce22a09d7edf5bffdb60ea14
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827596"
---
# Usar o Visualizador 3D no HoloLens (1ª geração)

O Visualizador 3D permite exibir os modelos 3D no HoloLens (1ª ger.). Você pode abrir e exibir arquivos .fbx *suportados* no Microsoft Edge, no OneDrive e em outros aplicativos.

>[!NOTE]
>Este artigo se aplica ao aplicativo imersivo Unity **3D Viewer**, que suporta arquivos .fbx e está disponível apenas no HoloLens (1ª ger.). O aplicativo **Visualizador 3D** pré-instalado no HoloLens 2 oferece suporte à abertura de modelos 3D .glb personalizados na casa mista, (consulte [Visão geral dos requisitos de ativo](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para obter mais detalhes.

Se você estiver tendo problemas para abrir um modelo 3D no Visualizador 3D, ou se certos recursos do seu modelo 3D não tiverem suporte, consulte [Especificações de conteúdo com suporte](#supported-content-specifications).

Para criar ou otimizar modelos 3D para usar no Visualizador 3D, consulte [Otimizando modelos 3D para o Visualizador 3D](#optimizing-3d-models-for-3d-viewer).

Há duas maneiras de abrir um modelo 3D no HoloLens. Consulte [Exibir arquivos FBX no HoloLens](#viewing-fbx-files-on-hololens) para obter mais detalhes.

Se você estiver tendo problemas após a leitura desses tópicos, consulte [Solução de problemas](#troubleshooting).

## Especificações de conteúdo suportadas

### Formato do arquivo

- Formato FBX
- Versão máxima do FBX 2015.1.0

### Tamanho do arquivo

- Mínimo de 5 KB
- Máximo de 500 MB

### Geometria

- Apenas modelos poligonais. Nenhuma superfície de subdivisão ou de NURBs
- Sistema de coordenadas para destros
- O cisalhamento em matrizes de transformação não possui suporte

### Texturas

- Os mapas de textura devem ser incorporados no arquivo FBX
- Formatos de imagem suportados
  - Imagens JPEG e PNG
  - Imagens BMP (RGB de 24 bit em cores verdadeiras)
  - Imagens TGA (RGB de 24 bits e RGBQ de 32 bits em cores verdadeiras)
- Resolução de textura máxima de 2048x2048
- Máximo de um mapa difuso, um mapa normal e um mapa do cubo de reflexão por malha
- O canal alfa em texturas difusas faz com que os pixels sejam descartados se ficarem abaixo de 50%

### Animação

- Animação de escala/rotação/conversão em objetos individuais
- Animação esquelética (manipulada) com esfolamento
  - Máximo de 4 influências por vértice

### Materiais

- Os materiais Lambert e Phong possuem suporte com parâmetros ajustáveis
- Propriedades de material com suporte para Lambert
  - Textura principal (RGB + Teste Alfa)
  - Cor difusa (RGB)
  - Cor ambiente (RGB)
- Propriedades de material com suporte para Phong
  - Textura principal (RGB + Teste Alfa)
  - Cor difusa (RGB)
  - Cor ambiente (RGB)
  - Cor especular (RGB)
  - Claridade
  - Refletividade
- Os materiais personalizados não possuem suporte
- Máximo de um material por malha
- Máximo de um material por camada
- Máximo de 8 materiais por arquivo

### Limitações de arquivo e de modelo

Há limites rígidos para o tamanho dos arquivos, bem como o número de modelos, vértices e malhas que podem ser abertos simultaneamente no Visualizador 3D:

- Tamanho máximo de arquivo de 500 MB por modelo
- Vértices: 600.000 combinados em todos os modelos abertos
- Malhas: 1.600 combinadas em todos os modelos abertos
- Máximo de 40 modelos abertos ao mesmo tempo

## Otimização de modelos 3D para o Visualizador 3D

### Considerações especiais

- Evite materiais pretos ou áreas pretas em mapas de textura. Os hologramas são feitos de luz, portanto, o HoloLens faz o preto ficar (a ausência de luz) transparente.
- Antes de exportar para o FBX da sua ferramenta de criação, verifique se a geometria está visível e desbloqueada e se nenhuma camada que contiver geometria está desativada ou modelada. A visibilidade não é respeitada.
- Evite desvios de conversão muito grandes entre os nós (por exemplo, 100.000 unidades). Isso pode causar tremulação no modelo enquanto é movido/redimensionado/girado.

### Otimização de desempenho

Lembre-se do desempenho ao criar conteúdo e valide no aplicativo Visualizador 3D no HoloLens durante o processo de criação para obter melhores resultados. O Visualizador 3D processa o conteúdo em tempo real e o desempenho está sujeito aos recursos de hardware do HoloLens.  

Há muitas variáveis em um modelo 3D que podem afetar o desempenho. O Visualizador 3D exibirá um aviso de carga se houver mais de 150.000 vértices ou mais de 400 malhas. As animações podem afetar o desempenho de outros modelos abertos. Também existem limites rígidos no número total de modelos, vértices e malhas que podem ser abertos simultaneamente no Visualizador 3D (consulte [Limitações de arquivo e de modelo](#file-and-model-limitations)).  

Se o modelo 3D não estiver funcionando bem devido à complexidade do modelo, considere:

- Reduzir a contagem de polígonos
- Reduzir o número de ossos na animação manipulada
- Evitar a oclusão automática

O processamento em frente e verso possui suporte do Visualizador 3D, embora esteja desativado por padrão por motivos de desempenho. Isso pode ser ativado pelo botão **Frente e verso** na página **Detalhes**. Para obter um melhor desempenho, evite a necessidade de processamento frente e verso no seu conteúdo.

### Validar seu modelo 3D

Valide seu modelo abrindo-o no Visualizador 3D no HoloLens. Selecione o botão **Detalhes** para visualizar as características do seu modelo e os avisos de conteúdo que não possuem suporte (se presentes).

### Processamento de modelos 3D com dimensões reais

Por padrão, o Visualizador 3D exibe modelos 3D em um tamanho e posição confortáveis em relação ao usuário. No entanto, se o processamento de um modelo 3D com medidas reais for importante (por exemplo, ao avaliar modelos de móveis em uma sala), o criador do conteúdo pode definir um sinalizador nos metadados do arquivo para evitar o redimensionamento desse modelo pelo aplicativo e pelo usuário.

Para impedir o dimensionamento do modelo, adicione um atributo personalizado booleano a qualquer objeto na cena chamado Microsoft_DisableScale e defina-o como verdadeiro. O Visualizador 3D respeitará as informações do FbxSystemUnit inseridas no arquivo FBX. A escala no Visualizador 3D é de 1 metro por unidade FBX.

## Visualizar arquivos FBX no HoloLens

### Abra um arquivo FBX no Microsoft Edge

Os arquivos FBX podem ser abertos diretamente de um site usando o Microsoft Edge no HoloLens.

1. No Microsoft Edge, navegue até a página da Web que contiver o arquivo FBX que você quer visualizar.
1. Selecione o arquivo para fazer o download.
1. Quando o download estiver concluído, selecione o botão **Abrir** no Microsoft Edge para abrir o arquivo no Visualizador 3D.

O arquivo baixado pode ser acessado e aberto novamente mais tarde usando Downloads no Microsoft Edge. Para salvar um modelo 3D e garantir acesso contínuo, baixe o arquivo no seu computador e salve-o na sua conta do OneDrive. O arquivo pode ser aberto no aplicativo OneDrive no HoloLens.

> [!NOTE]
> Alguns sites com modelos FBX para download os fornecem em formato ZIP compactado. O Visualizador 3D não pode abrir arquivos ZIP diretamente. Em vez disso, use seu computador para extrair o arquivo FBX e salve-o na sua conta do OneDrive. O arquivo pode ser aberto no aplicativo OneDrive no HoloLens.

### Abra um arquivo FBX no OneDrive

Os arquivos FBX podem ser abertos no OneDrive usando o aplicativo OneDrive no HoloLens. Verifique se você instalou o OneDrive usando o aplicativo Microsoft Store no HoloLens e se já carregou o arquivo FBX no OneDrive no seu computador.

Uma vez no OneDrive, os arquivos FBX podem ser abertos no HoloLens usando o Visualizador 3D de uma de duas maneiras:

- Inicie o OneDrive no HoloLens e selecione o arquivo FBX para abri-lo no Visualizador 3D.
- Inicie o Visualizador 3D, toque para exibir a barra de ferramentas e selecione **Abrir arquivo**. O OneDrive será iniciado, permitindo que você selecione um arquivo FBX.

## Solução de problemas

### Vejo um aviso quando abro um modelo 3D

Você verá um aviso se tentar abrir um modelo 3D que contiver recursos que não possuem suporte do Visualizador 3D ou se o modelo for muito complexo e o desempenho puder ser afetado. O Visualizador 3D ainda carregará o modelo 3D, mas o desempenho ou a fidelidade visual poderão ser comprometidos.

Para obter mais informações, consulte [Especificações de conteúdo suportadas](#supported-content-specifications) e [Otimizar modelos 3D ao Visualizador 3D](#optimizing-3d-models-for-3d-viewer).

### Vejo um aviso e o modelo 3D não carrega

Você verá uma mensagem de erro quando o Visualizador 3D não puder carregar um modelo 3D devido à complexidade ou tamanho do arquivo ou se o arquivo FBX estiver corrompido ou for inválido. Você também verá uma mensagem de erro se tiver atingido o limite do número total de modelos, vértices ou malhas que podem ser abertos simultaneamente.  

Para obter mais informações, consulte [Especificações de conteúdo suportadas](#supported-content-specifications) e [Limitações de arquivo e de modelo](#file-and-model-limitations).

Se você acha que seu modelo atende às especificações de conteúdo suportadas e não excedeu as limitações de arquivo ou modelo, envie o arquivo FBX para a equipe do Visualizador 3D em holoapps@microsoft.com. Não podemos responder pessoalmente, mas ter exemplos de arquivos que não são carregados corretamente ajudará nossa equipe a melhorar as futuras versões do aplicativo.

### Meu modelo 3D é carregado, mas não é exibido conforme o esperado

Se o seu modelo 3D não for exibido como o esperada no Visualizador 3D, clique levemente para exibir a barra de ferramentas e selecione **Detalhes**. Aspectos do arquivo que não possuem suporte do Visualizador 3D serão destacados como avisos.

O problema mais comum que você vê é a falta de texturas, provavelmente porque elas não estão incorporadas no arquivo FBX. Nesse caso, o modelo será exibido em branco. Esse problema pode ser solucionado no processo de criação, exportando da sua ferramenta de criação para o FBX com a opção incorporar texturas selecionada.

Para obter mais informações, consulte [Especificações de conteúdo suportadas](#supported-content-specifications) e [Otimizar modelos 3D ao Visualizador 3D](#optimizing-3d-models-for-3d-viewer).

### Percebo quedas de desempenho ao visualizar meu modelo 3D

O desempenho ao carregar e visualizar um modelo 3D pode ser afetado pela complexidade do modelo, número de modelos abertos simultaneamente ou número de modelos com animações ativas.

Para obter mais informações, consulte [Otimizar modelos 3D para o Visualizador 3D](#optimizing-3d-models-for-3d-viewer) e [Limitações de arquivo e modelo](#file-and-model-limitations).

### Quando abro um arquivo FBX no HoloLens, ele não é aberto no Visualizador 3D

O Visualizador 3D é associado automaticamente à extensão de arquivo .fbx quando ele é instalado.

Se você tentar abrir um arquivo FBX e vir uma caixa de diálogo que o direciona para a Microsoft Store, no momento não há um aplicativo associado à extensão de arquivo .fbx no HoloLens.

Verifique se o Visualizador 3D está instalado. Se ele não estiver instalado, baixe-o na Microsoft Store no HoloLens.

Se o Visualizador 3D já estiver instalado, inicie-o e tente abrir o arquivo novamente. Se o problema persistir, desinstale e reinstale o Visualizador 3D. Isso reassociará a extensão do arquivo .fbx com o Visualizador 3D.

Se a tentativa de abrir um arquivo FBX abrir um aplicativo que não seja o Visualizador 3D, esse aplicativo provavelmente foi instalado depois do Visualizador 3D e assumiu a associação com a extensão de arquivo .fbx. Se você preferir que o Visualizador 3D esteja associado com a extensão de arquivo .fbx, desinstale e reinstale o Visualizador 3D.

### O botão Abrir arquivo no Visualizador 3D não inicia um aplicativo

O botão **Abrir arquivo** abrirá o aplicativo associado à função de seleção de arquivos no HoloLens. Se o OneDrive estiver instalado, o botão **Abrir arquivo** deve iniciar o OneDrive. Entretanto, se atualmente não houver nenhum aplicativo associado à função seletora de arquivos instalada no HoloLens, você será direcionado para a Microsoft Store.

Se o botão **Abrir arquivo** iniciar um aplicativo que não seja o OneDrive, esse aplicativo provavelmente foi instalado depois do OneDrive e assumiu a associação com a função do seletor de arquivos. Se você preferir que o OneDrive seja iniciado ao selecionar o botão **Abrir arquivo** no Visualizador 3D, desinstale e reinstale o OneDrive.

Se o botão **Abrir arquivo** não estiver ativo, é possível que você tenha atingido o limite de modelos que podem ser abertos no Visualizador 3D ao mesmo tempo. Se você tiver 40 modelos abertos no Visualizador 3D, será preciso fechar alguns antes de poder abrir outros modelos.

## Recursos adicionais

- [Fóruns de suporte](http://forums.hololens.com/categories/3d-viewer-beta)
- [Notificações de terceiros](https://www.microsoft.com/{lang-locale}/legal/products)
