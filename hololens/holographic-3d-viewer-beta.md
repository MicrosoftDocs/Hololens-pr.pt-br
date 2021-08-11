---
title: Como usar o Visualizador 3D beta no HoloLens (1ª geração)
description: Descreve os tipos de arquivos e os recursos aos quais o Visualizador 3D beta no HoloLens (1ª geração) dá suporte, além de como usar o aplicativo e solucionar problemas dele.
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
ms.openlocfilehash: d25a87bd210535e36e18f165b5461141c40aa292a07c560018ba7c0cbf76f6ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664920"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Como usar o Visualizador 3D beta no HoloLens (1ª geração)

O Visualizador 3D beta permite que você veja os modelos 3D no HoloLens (1ª geração). Abra e veja os arquivos .fbx *compatíveis* no Microsoft Edge, no OneDrive e em outros aplicativos.

>[!NOTE]
>Este artigo se aplica ao aplicativo imersivo **Visualizador 3D beta** do Unity, que dá suporte a arquivos .fbx e só está disponível no HoloLens (1ª geração). O aplicativo pré-instalado do **Visualizador 3D** no HoloLens 2 dá suporte à abertura de modelos 3D .glb personalizados na Página Inicial da realidade misturada (confira [Visão geral dos requisitos do ativo](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para obter mais detalhes).

>[!IMPORTANT]
>Embora o Visualizador 3D beta possa estar disponível na Microsoft Store para o HoloLens (1ª geração), ele não está mais em desenvolvimento ativo e deixou de ter suporte.

Se você estiver tendo problemas para abrir um modelo 3D no Visualizador 3D beta ou se alguns recursos do seu modelo 3D não tiverem suporte, confira [Especificações de conteúdo compatíveis](#supported-content-specifications) abaixo.

Para criar ou otimizar os modelos 3D para uso com o Visualizador 3D beta, confira [Como otimizar modelos 3D para o Visualizador 3D beta](#optimizing-3d-models-for-3d-viewer-beta) abaixo.

Há duas maneiras de abrir um modelo 3D no HoloLens. Confira [Como exibir arquivos FBX no HoloLens](#viewing-fbx-files-on-hololens) abaixo para saber mais.

Se estiver tendo problemas depois de ler esses tópicos, confira [Solução de problemas](#troubleshooting) abaixo.

## <a name="supported-content-specifications"></a>Especificações de conteúdo compatíveis

### <a name="file-format"></a>Formato de arquivo

- Formato FBX
- Versão máxima do FBX 2015.1.0

### <a name="file-size"></a>Tamanho do arquivo

- Mínimo de 5 KB
- Máximo de 500 MB

### <a name="geometry"></a>Geometry

- Apenas modelos poligonais. Nenhuma superfície de subdivisão ou NURBs
- Sistema de coordenadas para destros
- A distorção em matrizes de transformação não é compatível

### <a name="textures"></a>Texturas

- Os mapas de textura precisam ser inseridos no arquivo FBX
- Formatos de imagem compatíveis
  - Imagens JPEG e PNG
  - Imagens BMP (RGB de 24 bits em true color)
  - Imagens TGA (RGB de 24 bits e RGBQ de 32 bits em true color)
- Resolução de textura máxima de 2.048 x 2.048
- Máximo de um mapa difuso, um mapa normal e um mapa do cubo de reflexão por malha
- O canal alfa em texturas difusas faz com que os pixels sejam descartados se ficam abaixo de 50%

### <a name="animation"></a>Animação

- Animação de escala/rotação/conversão em objetos individuais
- Animação esquelética (manipulada) com personalização
  - Máximo de quatro influências por vértice

### <a name="materials"></a>Materiais

- Há suporte para os materiais Lambert e Phong com parâmetros ajustáveis
- Propriedades de material compatíveis para Lambert
  - Textura principal (RGB + teste alfa)
  - Cor difusa (RGB)
  - Cor ambiente (RGB)
- Propriedades de material compatíveis para Phong
  - Textura principal (RGB + teste alfa)
  - Cor difusa (RGB)
  - Cor ambiente (RGB)
  - Cor especular (RGB)
  - Luminosidade
  - Refletividade
- Não há suporte para materiais personalizados
- Máximo de um material por malha
- Máximo de um material por camada
- Máximo de oito materiais por arquivo

### <a name="file-and-model-limitations"></a>Limitações de arquivo e de modelo

Há limites rígidos para o tamanho dos arquivos, bem como para o número de modelos, vértices e malhas que podem ser abertos simultaneamente no Visualizador 3D beta:

- Tamanho máximo de arquivo de 500 MB por modelo
- Vértices: 600 mil combinados em todos os modelos abertos
- Malhas: 1.600 combinadas em todos os modelos abertos
- Máximo de 40 modelos abertos ao mesmo tempo

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Otimização de modelos 3D para o Visualizador 3D beta

### <a name="special-considerations"></a>Considerações especiais

- Evite usar materiais pretos ou áreas pretas em mapas de textura. Os hologramas são feitos de luz. Portanto, o HoloLens renderiza o preto (a ausência de luz) como transparente.
- Antes da exportação para o FBX por meio da ferramenta de criação, verifique se a geometria está visível e desbloqueada e se nenhuma camada que contém a geometria está desativada ou em um modelo. A visibilidade não é respeitada.
- Evite deslocamentos de conversão muito grandes entre os nós (por exemplo, cem mil unidades). Isso pode causar tremulação no modelo enquanto ele é movido/escalado/girado.

### <a name="performance-optimization"></a>Otimização do desempenho

Lembre-se do desempenho ao criar o conteúdo e valide-o no aplicativo do Visualizador 3D beta no HoloLens durante o processo de criação para obter melhores resultados. O Visualizador 3D beta renderiza o conteúdo em tempo real e o desempenho está sujeito às funcionalidades de hardware do HoloLens.  

Há muitas variáveis em um modelo 3D que podem afetar o desempenho. O Visualizador 3D beta exibirá um aviso de carga se houver mais de 150 mil vértices ou mais de 400 malhas. As animações podem afetar o desempenho de outros modelos abertos. Também existem limites rígidos no número total de modelos, vértices e malhas que podem ser abertos simultaneamente no Visualizador 3D beta (confira [Limitações de arquivo e de modelo](#file-and-model-limitations)).  

Se o modelo 3D não estiver funcionando bem devido à complexidade do modelo, considere:

- Reduzir a contagem de polígonos
- Reduzir o número de ossos na animação manipulada
- Evitar a oclusão automática

Há suporte para a renderização frente e verso no Visualizador 3D beta, embora ela esteja desativada por padrão por motivos de desempenho. Isso pode ser ativado por meio do botão **Frente e Verso** na página **Detalhes**. Para obter um melhor desempenho, evite a necessidade de renderização frente e verso no conteúdo.

### <a name="validating-your-3d-model"></a>Como validar o modelo 3D

Valide o modelo abrindo-o no Visualizador 3D beta no HoloLens. Selecione o botão **Detalhes** para ver as características do modelo e os avisos de conteúdo sem suporte (se presente).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Renderização de modelos 3D com dimensões realistas

Por padrão, o Visualizador 3D beta exibe modelos 3D em um tamanho e uma posição confortáveis em relação ao usuário. No entanto, se a renderização de um modelo 3D com medidas realistas for importante (por exemplo, ao avaliar os modelos de móveis em uma sala), o criador do conteúdo poderá definir um sinalizador nos metadados do arquivo para impedir o redimensionamento desse modelo pelo aplicativo e pelo usuário.

Para impedir o dimensionamento do modelo, adicione um atributo personalizado booliano a qualquer objeto da cena chamado Microsoft_DisableScale e defina-o como verdadeiro. Em seguida, o Visualizador 3D beta respeitará as informações do FbxSystemUnit inseridas no arquivo FBX. A escala no Visualizador 3D beta é de 1 metro por unidade FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Como exibir arquivos FBX no HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Abrir um arquivo FBX no Microsoft Edge

Os arquivos FBX podem ser abertos diretamente de um site por meio do Microsoft Edge no HoloLens.

1. No Microsoft Edge, navegue até a página da Web que contém o arquivo FBX que deseja ver.
1. Selecione o arquivo para baixá-lo.
1. Quando o download estiver concluído, selecione o botão **Abrir** no Microsoft Edge para abrir o arquivo no Visualizador 3D beta.

O arquivo baixado poderá ser acessado e aberto novamente mais tarde por meio da opção Downloads no Microsoft Edge. Para salvar um modelo 3D e garantir o acesso contínuo, baixe o arquivo no computador e salve-o na sua conta do OneDrive. Em seguida, o arquivo poderá ser aberto no aplicativo OneDrive no HoloLens.

> [!NOTE]
> Alguns sites com modelos FBX para download os fornecem em formato ZIP compactado. O Visualizador 3D beta não pode abrir arquivos ZIP diretamente. Em vez disso, use o computador para extrair o arquivo FBX e salve-o na sua conta do OneDrive. Em seguida, o arquivo poderá ser aberto no aplicativo OneDrive no HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Abrir um arquivo FBX no OneDrive

Os arquivos FBX podem ser abertos no OneDrive por meio do aplicativo OneDrive no HoloLens. Verifique se você instalou o OneDrive usando o aplicativo Microsoft Store no HoloLens e se já carregou o arquivo FBX no OneDrive no computador.

Depois que estiverem no OneDrive, os arquivos FBX poderão ser abertos no HoloLens por meio do Visualizador 3D beta usando uma destas duas maneiras:

- Inicie o OneDrive no HoloLens e selecione o arquivo FBX para abri-lo no Visualizador 3D beta.
- Inicie o Visualizador 3D beta, feche e abra os dedos indicador e polegar para exibir a barra de ferramentas e selecione **Abrir Arquivo**. O OneDrive será iniciado, permitindo que você selecione um arquivo FBX.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Vejo um aviso quando abro um modelo 3D

Você verá um aviso se tentar abrir um modelo 3D que contiver recursos não compatíveis com o Visualizador 3D beta ou se o modelo for muito complexo e o desempenho poderá ser afetado. O Visualizador 3D beta ainda carregará o modelo 3D, mas o desempenho ou a fidelidade visual poderão ser comprometidos.

Para obter mais informações, confira [Especificações de conteúdo compatíveis](#supported-content-specifications) e [Como otimizar modelos 3D para o Visualizador 3D beta](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Vejo um aviso e o modelo 3D não é carregado

Você verá uma mensagem de erro quando o Visualizador 3D beta não puder carregar um modelo 3D devido à complexidade ou ao tamanho do arquivo ou se o arquivo FBX estiver corrompido ou for inválido. Você também verá uma mensagem de erro se tiver atingido o limite do número total de modelos, vértices ou malhas que podem ser abertos simultaneamente.  

Para obter mais informações, confira [Especificações de conteúdo compatíveis](#supported-content-specifications) e [Limitações de arquivo e de modelo](#file-and-model-limitations).

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Meu modelo 3D é carregado, mas não é exibido conforme o esperado

Se o seu modelo 3D não for exibido conforme o esperado no Visualizador 3D beta, feche e abra os dedos indicador e polegar para exibir a barra de ferramentas e selecione **Detalhes**. Os aspectos do arquivo que não são compatíveis com o Visualizador 3D beta serão realçados como avisos.

O problema mais comum que você poderá observar é a falta de texturas, provavelmente, porque elas não estão inseridas no arquivo FBX. Nesse caso, o modelo será exibido em branco. Esse problema pode ser solucionado no processo de criação pela exportação da ferramenta de criação para o FBX com a opção Inserir texturas selecionada.

Para obter mais informações, confira [Especificações de conteúdo compatíveis](#supported-content-specifications) e [Como otimizar modelos 3D para o Visualizador 3D beta](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Percebo quedas de desempenho ao ver meu modelo 3D

O desempenho ao carregar e exibir um modelo 3D pode ser afetado pela complexidade do modelo, pelo número de modelos abertos simultaneamente ou pelo número de modelos com animações ativas.

Para obter mais informações, confira [Como otimizar modelos 3D para o Visualizador 3D beta](#optimizing-3d-models-for-3d-viewer-beta) e [Limitações de arquivo e de modelo](#file-and-model-limitations).

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Quando abro um arquivo FBX no HoloLens, ele não é aberto no Visualizador 3D beta

O Visualizador 3D beta é associado automaticamente à extensão de arquivo .fbx quando ele é instalado.

Se você tentar abrir um arquivo FBX e uma caixa de diálogo que direciona você para a Microsoft Store for exibida, isso indica que, no momento, não há nenhum aplicativo associado à extensão de arquivo .fbx no HoloLens.

Verifique se o Visualizador 3D beta está instalado. Se ele não estiver instalado, baixe-o na Microsoft Store no HoloLens.

Se o Visualizador 3D beta já estiver instalado, inicie-o e tente abrir o arquivo novamente. Se o problema persistir, desinstale e reinstale o Visualizador 3D beta. Isso reassociará a extensão do arquivo .fbx ao Visualizador 3D beta.

Se a tentativa de abrir um arquivo FBX resultar na abertura de um aplicativo que não seja o Visualizador 3D beta, isso indicará que esse aplicativo provavelmente foi instalado depois do Visualizador 3D beta e assumiu a associação à extensão de arquivo .fbx. Se você preferir que o Visualizador 3D beta seja associado à extensão de arquivo .fbx, desinstale-o e reinstale-o.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>O botão Abrir Arquivo no Visualizador 3D beta não inicia um aplicativo

O botão **Abrir Arquivo** abrirá o aplicativo associado à função do seletor de arquivos no HoloLens. Se o OneDrive estiver instalado, o botão **Abrir Arquivo** iniciará o OneDrive. Entretanto, se atualmente não houver nenhum aplicativo associado à função do seletor de arquivos instalada no HoloLens, você será direcionado para a Microsoft Store.

Se o botão **Abrir Arquivo** iniciar um aplicativo que não seja o OneDrive, isso indicará que esse aplicativo provavelmente foi instalado depois do OneDrive e assumiu a associação à função do seletor de arquivos. Se você preferir que o OneDrive seja iniciado ao selecionar o botão **Abrir Arquivo** no Visualizador 3D beta, desinstale-o e reinstale-o.

Se o botão **Abrir Arquivo** não está ativo, é possível que você tenha atingido o limite de modelos que podem ser abertos no Visualizador 3D beta ao mesmo tempo. Se você tiver 40 modelos abertos no Visualizador 3D beta, precisará fechar alguns para abrir outros modelos.

## <a name="additional-resources"></a>Recursos adicionais

- [Fóruns de suporte](http://forums.hololens.com/categories/3d-viewer-beta) – somente para fins de arquivamento. Esse fórum não está mais ativo.
- [Avisos de terceiros](https://www.microsoft.com/{lang-locale}/legal/products)
