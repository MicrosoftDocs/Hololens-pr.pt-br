---
title: Usar o Visualizador 3D Beta no HoloLens (1ª geração)
description: Descreve os tipos de arquivos e recursos aos quais o Visualizador 3D Beta no HoloLens (1ª geração) oferece suporte e como usar e solucionar problemas do aplicativo.
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
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016282"
---
# <span data-ttu-id="5a985-103">Usar o Visualizador 3D Beta no HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="5a985-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="5a985-104">O Visualizador 3D Beta permite exibir os modelos 3D no HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="5a985-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="5a985-105">Você pode abrir e exibir arquivos .fbx *suportados* no Microsoft Edge, no OneDrive e em outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5a985-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="5a985-106">Este artigo se aplica ao aplicativo imersivo Unity **Visualizador 3D Beta**, que suporta arquivos .fbx e está disponível apenas no HoloLens (1ª geração).</span><span class="sxs-lookup"><span data-stu-id="5a985-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="5a985-107">O aplicativo **Visualizador 3D** pré-instalado no HoloLens 2 oferece suporte à abertura de modelos 3D .glb personalizados na casa mista, (consulte [Visão geral dos requisitos de ativo](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5a985-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="5a985-108">Embora a versão Beta do Visualizador 3D possa estar disponível na Microsoft Store para o HoloLens (1ª geração), ela não está mais no desenvolvimento ativo e não tem mais suporte.</span><span class="sxs-lookup"><span data-stu-id="5a985-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="5a985-109">Se você estiver tendo problemas para abrir um modelo 3D no Visualizador 3D Beta, ou se certos recursos do seu modelo 3D não tiverem suporte, consulte abaixo as[Especificações de conteúdo com suporte](#supported-content-specifications).</span><span class="sxs-lookup"><span data-stu-id="5a985-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="5a985-110">Para criar ou otimizar modelos 3D para usar no Visualizador 3D Beta, consulte abaixo [Otimizar modelos 3D para o Visualizador 3D](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="5a985-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="5a985-111">Há duas maneiras de abrir um modelo 3D no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="5a985-112">Consulte abaixo [Exibir arquivos FBX no HoloLens](#viewing-fbx-files-on-hololens) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5a985-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="5a985-113">Se você estiver tendo problemas após a leitura desses tópicos, consulte abaixo a[Solução de problemas](#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="5a985-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <span data-ttu-id="5a985-114">Especificações de conteúdo suportadas</span><span class="sxs-lookup"><span data-stu-id="5a985-114">Supported content specifications</span></span>

### <span data-ttu-id="5a985-115">Formato do arquivo</span><span class="sxs-lookup"><span data-stu-id="5a985-115">File format</span></span>

- <span data-ttu-id="5a985-116">Formato FBX</span><span class="sxs-lookup"><span data-stu-id="5a985-116">FBX format</span></span>
- <span data-ttu-id="5a985-117">Versão máxima do FBX 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="5a985-117">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="5a985-118">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="5a985-118">File size</span></span>

- <span data-ttu-id="5a985-119">Mínimo de 5 KB</span><span class="sxs-lookup"><span data-stu-id="5a985-119">Minimum 5 KB</span></span>
- <span data-ttu-id="5a985-120">Máximo de 500 MB</span><span class="sxs-lookup"><span data-stu-id="5a985-120">Maximum 500 MB</span></span>

### <span data-ttu-id="5a985-121">Geometria</span><span class="sxs-lookup"><span data-stu-id="5a985-121">Geometry</span></span>

- <span data-ttu-id="5a985-122">Apenas modelos poligonais.</span><span class="sxs-lookup"><span data-stu-id="5a985-122">Polygonal models only.</span></span> <span data-ttu-id="5a985-123">Nenhuma superfície de subdivisão ou de NURBs</span><span class="sxs-lookup"><span data-stu-id="5a985-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="5a985-124">Sistema de coordenadas para destros</span><span class="sxs-lookup"><span data-stu-id="5a985-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="5a985-125">O cisalhamento em matrizes de transformação não possui suporte</span><span class="sxs-lookup"><span data-stu-id="5a985-125">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="5a985-126">Texturas</span><span class="sxs-lookup"><span data-stu-id="5a985-126">Textures</span></span>

- <span data-ttu-id="5a985-127">Os mapas de textura devem ser incorporados no arquivo FBX</span><span class="sxs-lookup"><span data-stu-id="5a985-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="5a985-128">Formatos de imagem suportados</span><span class="sxs-lookup"><span data-stu-id="5a985-128">Supported image formats</span></span>
  - <span data-ttu-id="5a985-129">Imagens JPEG e PNG</span><span class="sxs-lookup"><span data-stu-id="5a985-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="5a985-130">Imagens BMP (RGB de 24 bit em cores verdadeiras)</span><span class="sxs-lookup"><span data-stu-id="5a985-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="5a985-131">Imagens TGA (RGB de 24 bits e RGBQ de 32 bits em cores verdadeiras)</span><span class="sxs-lookup"><span data-stu-id="5a985-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="5a985-132">Resolução de textura máxima de 2048x2048</span><span class="sxs-lookup"><span data-stu-id="5a985-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="5a985-133">Máximo de um mapa difuso, um mapa normal e um mapa do cubo de reflexão por malha</span><span class="sxs-lookup"><span data-stu-id="5a985-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="5a985-134">O canal alfa em texturas difusas faz com que os pixels sejam descartados se ficarem abaixo de 50%</span><span class="sxs-lookup"><span data-stu-id="5a985-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="5a985-135">Animação</span><span class="sxs-lookup"><span data-stu-id="5a985-135">Animation</span></span>

- <span data-ttu-id="5a985-136">Animação de escala/rotação/conversão em objetos individuais</span><span class="sxs-lookup"><span data-stu-id="5a985-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="5a985-137">Animação esquelética (manipulada) com esfolamento</span><span class="sxs-lookup"><span data-stu-id="5a985-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="5a985-138">Máximo de 4 influências por vértice</span><span class="sxs-lookup"><span data-stu-id="5a985-138">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="5a985-139">Materiais</span><span class="sxs-lookup"><span data-stu-id="5a985-139">Materials</span></span>

- <span data-ttu-id="5a985-140">Os materiais Lambert e Phong possuem suporte com parâmetros ajustáveis</span><span class="sxs-lookup"><span data-stu-id="5a985-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="5a985-141">Propriedades de material com suporte para Lambert</span><span class="sxs-lookup"><span data-stu-id="5a985-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="5a985-142">Textura principal (RGB + Teste Alfa)</span><span class="sxs-lookup"><span data-stu-id="5a985-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="5a985-143">Cor difusa (RGB)</span><span class="sxs-lookup"><span data-stu-id="5a985-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="5a985-144">Cor ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="5a985-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="5a985-145">Propriedades de material com suporte para Phong</span><span class="sxs-lookup"><span data-stu-id="5a985-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="5a985-146">Textura principal (RGB + Teste Alfa)</span><span class="sxs-lookup"><span data-stu-id="5a985-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="5a985-147">Cor difusa (RGB)</span><span class="sxs-lookup"><span data-stu-id="5a985-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="5a985-148">Cor ambiente (RGB)</span><span class="sxs-lookup"><span data-stu-id="5a985-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="5a985-149">Cor especular (RGB)</span><span class="sxs-lookup"><span data-stu-id="5a985-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="5a985-150">Claridade</span><span class="sxs-lookup"><span data-stu-id="5a985-150">Shininess</span></span>
  - <span data-ttu-id="5a985-151">Refletividade</span><span class="sxs-lookup"><span data-stu-id="5a985-151">Reflectivity</span></span>
- <span data-ttu-id="5a985-152">Os materiais personalizados não possuem suporte</span><span class="sxs-lookup"><span data-stu-id="5a985-152">Custom materials are not supported</span></span>
- <span data-ttu-id="5a985-153">Máximo de um material por malha</span><span class="sxs-lookup"><span data-stu-id="5a985-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="5a985-154">Máximo de um material por camada</span><span class="sxs-lookup"><span data-stu-id="5a985-154">Maximum of one material layer</span></span>
- <span data-ttu-id="5a985-155">Máximo de 8 materiais por arquivo</span><span class="sxs-lookup"><span data-stu-id="5a985-155">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="5a985-156">Limitações de arquivo e de modelo</span><span class="sxs-lookup"><span data-stu-id="5a985-156">File and model limitations</span></span>

<span data-ttu-id="5a985-157">Há limites rígidos para o tamanho dos arquivos, bem como para o número de modelos, vértices e malhas que podem ser abertos simultaneamente no Visualizador 3D Beta:</span><span class="sxs-lookup"><span data-stu-id="5a985-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="5a985-158">Tamanho máximo de arquivo de 500 MB por modelo</span><span class="sxs-lookup"><span data-stu-id="5a985-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="5a985-159">Vértices: 600.000 combinados em todos os modelos abertos</span><span class="sxs-lookup"><span data-stu-id="5a985-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="5a985-160">Malhas: 1.600 combinadas em todos os modelos abertos</span><span class="sxs-lookup"><span data-stu-id="5a985-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="5a985-161">Máximo de 40 modelos abertos ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="5a985-161">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="5a985-162">Otimização de modelos 3D para o Visualizador 3D Beta</span><span class="sxs-lookup"><span data-stu-id="5a985-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <span data-ttu-id="5a985-163">Considerações especiais</span><span class="sxs-lookup"><span data-stu-id="5a985-163">Special considerations</span></span>

- <span data-ttu-id="5a985-164">Evite materiais pretos ou áreas pretas em mapas de textura.</span><span class="sxs-lookup"><span data-stu-id="5a985-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="5a985-165">Os hologramas são feitos de luz, portanto, o HoloLens faz o preto ficar (a ausência de luz) transparente.</span><span class="sxs-lookup"><span data-stu-id="5a985-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="5a985-166">Antes de exportar para o FBX da sua ferramenta de criação, verifique se a geometria está visível e desbloqueada e se nenhuma camada que contiver geometria está desativada ou modelada.</span><span class="sxs-lookup"><span data-stu-id="5a985-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="5a985-167">A visibilidade não é respeitada.</span><span class="sxs-lookup"><span data-stu-id="5a985-167">Visibility is not respected.</span></span>
- <span data-ttu-id="5a985-168">Evite desvios de conversão muito grandes entre os nós (por exemplo, 100.000 unidades).</span><span class="sxs-lookup"><span data-stu-id="5a985-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="5a985-169">Isso pode causar tremulação no modelo enquanto é movido/redimensionado/girado.</span><span class="sxs-lookup"><span data-stu-id="5a985-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="5a985-170">Otimização de desempenho</span><span class="sxs-lookup"><span data-stu-id="5a985-170">Performance optimization</span></span>

<span data-ttu-id="5a985-171">Lembre-se do desempenho ao criar conteúdo e valide no aplicativo Visualizador 3D Beta no HoloLens durante o processo de criação para obter melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="5a985-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="5a985-172">O Visualizador 3D Beta processa o conteúdo em tempo real e o desempenho está sujeito aos recursos de hardware do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="5a985-173">Há muitas variáveis em um modelo 3D que podem afetar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="5a985-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="5a985-174">O Visualizador 3D Beta exibirá um aviso de carga se houver mais de 150.000 vértices ou mais de 400 malhas.</span><span class="sxs-lookup"><span data-stu-id="5a985-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="5a985-175">As animações podem afetar o desempenho de outros modelos abertos.</span><span class="sxs-lookup"><span data-stu-id="5a985-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="5a985-176">Também existem limites rígidos no número total de modelos, vértices e malhas que podem ser abertos simultaneamente no Visualizador 3D Beta (consulte [Limitações de arquivo e de modelo](#file-and-model-limitations)).</span><span class="sxs-lookup"><span data-stu-id="5a985-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="5a985-177">Se o modelo 3D não estiver funcionando bem devido à complexidade do modelo, considere:</span><span class="sxs-lookup"><span data-stu-id="5a985-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="5a985-178">Reduzir a contagem de polígonos</span><span class="sxs-lookup"><span data-stu-id="5a985-178">Reducing polygon count</span></span>
- <span data-ttu-id="5a985-179">Reduzir o número de ossos na animação manipulada</span><span class="sxs-lookup"><span data-stu-id="5a985-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="5a985-180">Evitar a oclusão automática</span><span class="sxs-lookup"><span data-stu-id="5a985-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="5a985-181">O processamento em frente e verso possui suporte do Visualizador 3D Beta, embora esteja desativado por padrão por motivos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="5a985-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="5a985-182">Isso pode ser ativado pelo botão **Frente e verso** na página **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5a985-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="5a985-183">Para obter um melhor desempenho, evite a necessidade de processamento frente e verso no seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5a985-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="5a985-184">Validar seu modelo 3D</span><span class="sxs-lookup"><span data-stu-id="5a985-184">Validating your 3D model</span></span>

<span data-ttu-id="5a985-185">Validar seu modelo abrindo-o no Visualizador 3D Beta no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="5a985-186">Selecione o botão **Detalhes** para visualizar as características do seu modelo e os avisos de conteúdo que não possuem suporte (se presentes).</span><span class="sxs-lookup"><span data-stu-id="5a985-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="5a985-187">Processamento de modelos 3D com dimensões reais</span><span class="sxs-lookup"><span data-stu-id="5a985-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="5a985-188">Por padrão, o Visualizador 3D Beta exibe modelos 3D em um tamanho e posição confortáveis em relação ao usuário.</span><span class="sxs-lookup"><span data-stu-id="5a985-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="5a985-189">No entanto, se o processamento de um modelo 3D com medidas reais for importante (por exemplo, ao avaliar modelos de móveis em uma sala), o criador do conteúdo pode definir um sinalizador nos metadados do arquivo para evitar o redimensionamento desse modelo pelo aplicativo e pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="5a985-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="5a985-190">Para impedir o dimensionamento do modelo, adicione um atributo personalizado booleano a qualquer objeto na cena chamado Microsoft_DisableScale e defina-o como verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5a985-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="5a985-191">O Visualizador 3D Beta respeitará as informações do FbxSystemUnit inseridas no arquivo FBX.</span><span class="sxs-lookup"><span data-stu-id="5a985-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="5a985-192">A escala no Visualizador 3D Beta é de 1 metro por unidade FBX.</span><span class="sxs-lookup"><span data-stu-id="5a985-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="5a985-193">Visualizar arquivos FBX no HoloLens</span><span class="sxs-lookup"><span data-stu-id="5a985-193">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="5a985-194">Abra um arquivo FBX no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5a985-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="5a985-195">Os arquivos FBX podem ser abertos diretamente de um site usando o Microsoft Edge no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="5a985-196">No Microsoft Edge, navegue até a página da Web que contiver o arquivo FBX que você quer visualizar.</span><span class="sxs-lookup"><span data-stu-id="5a985-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="5a985-197">Selecione o arquivo para fazer o download.</span><span class="sxs-lookup"><span data-stu-id="5a985-197">Select the file to download it.</span></span>
1. <span data-ttu-id="5a985-198">Quando o download estiver concluído, selecione o botão **Abrir** no Microsoft Edge para abrir o arquivo no Visualizador 3D Beta.</span><span class="sxs-lookup"><span data-stu-id="5a985-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="5a985-199">O arquivo baixado pode ser acessado e aberto novamente mais tarde usando Downloads no Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="5a985-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="5a985-200">Para salvar um modelo 3D e garantir acesso contínuo, baixe o arquivo no seu computador e salve-o na sua conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5a985-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="5a985-201">O arquivo pode ser aberto no aplicativo OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="5a985-202">Alguns sites com modelos FBX para download os fornecem em formato ZIP compactado.</span><span class="sxs-lookup"><span data-stu-id="5a985-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="5a985-203">O Visualizador 3D Beta não pode abrir arquivos ZIP diretamente.</span><span class="sxs-lookup"><span data-stu-id="5a985-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="5a985-204">Em vez disso, use seu computador para extrair o arquivo FBX e salve-o na sua conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5a985-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="5a985-205">O arquivo pode ser aberto no aplicativo OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="5a985-206">Abra um arquivo FBX no OneDrive</span><span class="sxs-lookup"><span data-stu-id="5a985-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="5a985-207">Os arquivos FBX podem ser abertos no OneDrive usando o aplicativo OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="5a985-208">Verifique se você instalou o OneDrive usando o aplicativo Microsoft Store no HoloLens e se já carregou o arquivo FBX no OneDrive no seu computador.</span><span class="sxs-lookup"><span data-stu-id="5a985-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="5a985-209">Uma vez no OneDrive, os arquivos FBX podem ser abertos no HoloLens usando o Visualizador 3D Beta de uma de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="5a985-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="5a985-210">Inicie o OneDrive no HoloLens e selecione o arquivo FBX para abri-lo no Visualizador 3D Beta.</span><span class="sxs-lookup"><span data-stu-id="5a985-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="5a985-211">Inicie o Visualizador 3D Beta, toque para exibir a barra de ferramentas e selecione **Abrir arquivo**.</span><span class="sxs-lookup"><span data-stu-id="5a985-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="5a985-212">O OneDrive será iniciado, permitindo que você selecione um arquivo FBX.</span><span class="sxs-lookup"><span data-stu-id="5a985-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="5a985-213">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="5a985-213">Troubleshooting</span></span>

### <span data-ttu-id="5a985-214">Vejo um aviso quando abro um modelo 3D</span><span class="sxs-lookup"><span data-stu-id="5a985-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="5a985-215">Você verá um aviso se tentar abrir um modelo 3D que contiver recursos que não possuem suporte do Visualizador 3D Beta ou se o modelo for muito complexo e o desempenho puder ser afetado.</span><span class="sxs-lookup"><span data-stu-id="5a985-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="5a985-216">O Visualizador 3D Beta ainda carregará o modelo 3D, mas o desempenho ou a fidelidade visual poderão ser comprometidos.</span><span class="sxs-lookup"><span data-stu-id="5a985-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="5a985-217">Para obter mais informações, consulte [Especificações de conteúdo suportadas](#supported-content-specifications) e [Otimizar modelos 3D no Visualizador 3D Beta](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="5a985-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="5a985-218">Vejo um aviso e o modelo 3D não carrega</span><span class="sxs-lookup"><span data-stu-id="5a985-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="5a985-219">Você verá uma mensagem de erro quando o Visualizador 3D Beta não puder carregar um modelo 3D devido à complexidade ou tamanho do arquivo ou se o arquivo FBX estiver corrompido ou for inválido.</span><span class="sxs-lookup"><span data-stu-id="5a985-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="5a985-220">Você também verá uma mensagem de erro se tiver atingido o limite do número total de modelos, vértices ou malhas que podem ser abertos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="5a985-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="5a985-221">Para obter mais informações, consulte [Especificações de conteúdo suportadas](#supported-content-specifications) e [Limitações de arquivo e de modelo](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="5a985-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="5a985-222">Meu modelo 3D é carregado, mas não é exibido conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="5a985-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="5a985-223">Se o seu modelo 3D não for exibido como o esperado no Visualizador 3D Beta, clique levemente para exibir a barra de ferramentas e selecione **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="5a985-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="5a985-224">Aspectos do arquivo que não possuem suporte do Visualizador 3D Beta serão destacados como avisos.</span><span class="sxs-lookup"><span data-stu-id="5a985-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="5a985-225">O problema mais comum que você vê é a falta de texturas, provavelmente porque elas não estão incorporadas no arquivo FBX.</span><span class="sxs-lookup"><span data-stu-id="5a985-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="5a985-226">Nesse caso, o modelo será exibido em branco.</span><span class="sxs-lookup"><span data-stu-id="5a985-226">In this case, the model will appear white.</span></span> <span data-ttu-id="5a985-227">Esse problema pode ser solucionado no processo de criação, exportando da sua ferramenta de criação para o FBX com a opção incorporar texturas selecionada.</span><span class="sxs-lookup"><span data-stu-id="5a985-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="5a985-228">Para obter mais informações, consulte [Especificações de conteúdo suportadas](#supported-content-specifications) e [Otimizar modelos 3D no Visualizador 3D Beta](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="5a985-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="5a985-229">Percebo quedas de desempenho ao visualizar meu modelo 3D</span><span class="sxs-lookup"><span data-stu-id="5a985-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="5a985-230">O desempenho ao carregar e visualizar um modelo 3D pode ser afetado pela complexidade do modelo, número de modelos abertos simultaneamente ou número de modelos com animações ativas.</span><span class="sxs-lookup"><span data-stu-id="5a985-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="5a985-231">Para obter mais informações, consulte [Otimizar modelos 3D para o Visualizador 3D Beta](#optimizing-3d-models-for-3d-viewer-beta) e [Limitações de arquivo e modelo](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="5a985-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="5a985-232">Quando abro um arquivo FBX no HoloLens, ele não é aberto no Visualizador 3D Beta</span><span class="sxs-lookup"><span data-stu-id="5a985-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="5a985-233">O Visualizador 3D Beta é associado automaticamente à extensão de arquivo .fbx quando ele é instalado.</span><span class="sxs-lookup"><span data-stu-id="5a985-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="5a985-234">Se você tentar abrir um arquivo FBX e vir uma caixa de diálogo que o direciona para a Microsoft Store, no momento não há um aplicativo associado à extensão de arquivo .fbx no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="5a985-235">Verifique se o Visualizador 3D Beta está instalado.</span><span class="sxs-lookup"><span data-stu-id="5a985-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="5a985-236">Se ele não estiver instalado, baixe-o na Microsoft Store no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="5a985-237">Se o Visualizador 3D Beta já estiver instalado, inicie-o e tente abrir o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="5a985-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="5a985-238">Se o problema persistir, desinstale e reinstale o Visualizador 3D Beta.</span><span class="sxs-lookup"><span data-stu-id="5a985-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="5a985-239">Isso reassociará a extensão do arquivo .fbx com o Visualizador 3D Beta.</span><span class="sxs-lookup"><span data-stu-id="5a985-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="5a985-240">Se a tentativa de abrir um arquivo FBX abrir um aplicativo que não seja o Visualizador 3D Beta, esse aplicativo provavelmente foi instalado depois do Visualizador 3D Beta e assumiu a associação com a extensão de arquivo .fbx.</span><span class="sxs-lookup"><span data-stu-id="5a985-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="5a985-241">Se você preferir que o Visualizador 3D Beta esteja associado com a extensão de arquivo .fbx, desinstale e reinstale o Visualizador 3D Beta.</span><span class="sxs-lookup"><span data-stu-id="5a985-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <span data-ttu-id="5a985-242">O botão Abrir arquivo no Visualizador 3D Beta não inicia um aplicativo</span><span class="sxs-lookup"><span data-stu-id="5a985-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="5a985-243">O botão **Abrir arquivo** abrirá o aplicativo associado à função de seleção de arquivos no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5a985-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="5a985-244">Se o OneDrive estiver instalado, o botão **Abrir arquivo** deve iniciar o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5a985-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="5a985-245">Entretanto, se atualmente não houver nenhum aplicativo associado à função seletora de arquivos instalada no HoloLens, você será direcionado para a Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="5a985-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="5a985-246">Se o botão **Abrir arquivo** iniciar um aplicativo que não seja o OneDrive, esse aplicativo provavelmente foi instalado depois do OneDrive e assumiu a associação com a função do seletor de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5a985-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="5a985-247">Se você preferir que o OneDrive seja iniciado ao selecionar o botão **Abrir arquivo** no Visualizador 3D Beta, desinstale e reinstale o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="5a985-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="5a985-248">Se o botão **Abrir arquivo** não estiver ativo, é possível que você tenha atingido o limite de modelos que podem ser abertos no Visualizador 3D Beta ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5a985-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="5a985-249">Se você tiver 40 modelos abertos no Visualizador 3D Beta, será preciso fechar alguns antes de poder abrir outros modelos.</span><span class="sxs-lookup"><span data-stu-id="5a985-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="5a985-250">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5a985-250">Additional resources</span></span>

- <span data-ttu-id="5a985-251">[Fóruns de suporte](http://forums.hololens.com/categories/3d-viewer-beta) - somente para fins de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="5a985-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="5a985-252">Este fórum não está mais ativo.</span><span class="sxs-lookup"><span data-stu-id="5a985-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="5a985-253">Notificações de terceiros</span><span class="sxs-lookup"><span data-stu-id="5a985-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
