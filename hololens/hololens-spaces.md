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
# <span data-ttu-id="d05d9-105">Mapear espaços físicos com o HoloLens</span><span class="sxs-lookup"><span data-stu-id="d05d9-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="d05d9-106">O HoloLens mistura hologramas com o seu mundo físico.</span><span class="sxs-lookup"><span data-stu-id="d05d9-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="d05d9-107">Para fazer isso, o HoloLens precisa saber mais sobre o mundo físico ao seu redor e lembrar-se de onde você coloca os hologramas dentro desse espaço.</span><span class="sxs-lookup"><span data-stu-id="d05d9-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="d05d9-108">Com o tempo, o HoloLens cria um *mapa espacial* do ambiente que ele vê.</span><span class="sxs-lookup"><span data-stu-id="d05d9-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="d05d9-109">O HoloLens atualiza o mapa conforme o ambiente é alterado.</span><span class="sxs-lookup"><span data-stu-id="d05d9-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="d05d9-110">Enquanto você estiver conectado e o dispositivo estiver ativado, o HoloLens cria e atualiza seus mapas espaciais.</span><span class="sxs-lookup"><span data-stu-id="d05d9-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="d05d9-111">Se você mantiver ou usar o dispositivo com as câmeras apontadas para um espaço, o HoloLens tentará mapear a área.</span><span class="sxs-lookup"><span data-stu-id="d05d9-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="d05d9-112">Apesar do HoloLens aprender naturalmente sobre o espaço ao longo do tempo, existem formas de você ajudar o HoloLens a mapear seu espaço de maneira mais rápida e eficiente.</span><span class="sxs-lookup"><span data-stu-id="d05d9-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="d05d9-113">Se o seu HoloLens não puder mapear o seu espaço ou estiver sem calibração, o HoloLens poderá entrar em Modo limitado.</span><span class="sxs-lookup"><span data-stu-id="d05d9-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="d05d9-114">No Modo limitado, não será possível posicionar os hologramas nos arredores.</span><span class="sxs-lookup"><span data-stu-id="d05d9-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="d05d9-115">Este artigo explica como o HoloLens mapeia os espaços, como melhorar o mapeamento espacial e como gerenciar os dados espaciais que o HoloLens coleta.</span><span class="sxs-lookup"><span data-stu-id="d05d9-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <span data-ttu-id="d05d9-116">Escolha e configuração e seu espaço</span><span class="sxs-lookup"><span data-stu-id="d05d9-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="d05d9-117">Os recursos do seu ambiente podem dificultar a interpretação que o HoloLens faz de um espaço.</span><span class="sxs-lookup"><span data-stu-id="d05d9-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="d05d9-118">Os níveis de luz, os materiais no espaço, a disposição dos objetos e outros podem afetar como o HoloLens mapeia uma área.</span><span class="sxs-lookup"><span data-stu-id="d05d9-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="d05d9-119">O HoloLens funciona melhor em certos tipos de ambiente.</span><span class="sxs-lookup"><span data-stu-id="d05d9-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="d05d9-120">Para produzir o melhor mapa espacial, escolha um cômodo que tenha claridade e espaço suficiente.</span><span class="sxs-lookup"><span data-stu-id="d05d9-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="d05d9-121">Evite espaços escuros e cômodos com grande quantidade de superfícies escuras, brilhantes ou translúcidas (por exemplo, espelhos ou cortinas de gaze).</span><span class="sxs-lookup"><span data-stu-id="d05d9-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="d05d9-122">O HoloLens está otimizado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="d05d9-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="d05d9-123">O mapeamento espacial também funciona melhor quando o Wi-Fi está ativado, embora ele não precise estar conectado a uma rede.</span><span class="sxs-lookup"><span data-stu-id="d05d9-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="d05d9-124">O HoloLens pode obter pontos de acesso Wi-Fi mesmo se ele não estiver conectado ou autenticado.</span><span class="sxs-lookup"><span data-stu-id="d05d9-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="d05d9-125">A funcionalidade do HoloLens não altera se os pontos de acesso são conectados à Internet ou somente na intranet/local.</span><span class="sxs-lookup"><span data-stu-id="d05d9-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="d05d9-126">Use o HoloLens apenas em locais seguros sem riscos de acidentes.</span><span class="sxs-lookup"><span data-stu-id="d05d9-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="d05d9-127">[Mais sobre segurança](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="d05d9-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <span data-ttu-id="d05d9-128">Mapeando seu espaço</span><span class="sxs-lookup"><span data-stu-id="d05d9-128">Mapping your space</span></span>

<span data-ttu-id="d05d9-129">Agora você está pronto para começar a mapear o seu espaço.</span><span class="sxs-lookup"><span data-stu-id="d05d9-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="d05d9-130">Quando o HoloLens começar a mapear seus arredores, você verá um gráfico de malha se espalhando pelo espaço.</span><span class="sxs-lookup"><span data-stu-id="d05d9-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="d05d9-131">Na página inicial da realidade misturada, você pode acionar a exibição do mapa selecionando uma superfície mapeada.</span><span class="sxs-lookup"><span data-stu-id="d05d9-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="d05d9-132">Estas são as diretrizes para a criação de um ótimo mapa espacial.</span><span class="sxs-lookup"><span data-stu-id="d05d9-132">Here are guidelines for building a great spatial map.</span></span>

### <span data-ttu-id="d05d9-133">Compreendendo os cenários da área</span><span class="sxs-lookup"><span data-stu-id="d05d9-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="d05d9-134">É importante gastar na maior parte do tempo onde você usará o HoloLens, para que o mapa seja relevante e completo.</span><span class="sxs-lookup"><span data-stu-id="d05d9-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="d05d9-135">Por exemplo, se um cenário de usuário do HoloLens envolve uma mudança do Ponto A para o Ponto B, faça esse trajeto três vezes, olhando para todas as direções à medida que você se movimenta.</span><span class="sxs-lookup"><span data-stu-id="d05d9-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <span data-ttu-id="d05d9-136">Percorra o espaço lentamente</span><span class="sxs-lookup"><span data-stu-id="d05d9-136">Walk slowly around the space</span></span>

<span data-ttu-id="d05d9-137">Se você andar rapidamente em torno da área, provavelmente o HoloLens perderá áreas de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="d05d9-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="d05d9-138">Percorra o espaço lentamente, parando a cada 1.73m para olhar para os arredores.</span><span class="sxs-lookup"><span data-stu-id="d05d9-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="d05d9-139">Os movimentos suaves também ajudam o HoloLens a mapear de maneira mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="d05d9-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <span data-ttu-id="d05d9-140">Olhe para todas as direções</span><span class="sxs-lookup"><span data-stu-id="d05d9-140">Look in all directions</span></span>

<span data-ttu-id="d05d9-141">Olhar ao redor enquanto você mapeia o espaço fornece ao HoloLens mais dado sobre onde os pontos são relativos entre si.</span><span class="sxs-lookup"><span data-stu-id="d05d9-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="d05d9-142">Se você não olha para cima, por exemplo, o HoloLens pode não saber onde está o teto de um cômodo.</span><span class="sxs-lookup"><span data-stu-id="d05d9-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="d05d9-143">Não se esqueça de olhar para o chão ao mapear o espaço.</span><span class="sxs-lookup"><span data-stu-id="d05d9-143">Don't forget to look down at the floor as you map the space.</span></span>

### <span data-ttu-id="d05d9-144">Aborde as principais áreas várias vezes</span><span class="sxs-lookup"><span data-stu-id="d05d9-144">Cover key areas multiple times</span></span>

<span data-ttu-id="d05d9-145">Percorrer uma área várias vezes ajudará a captar recursos que você pode ter perdido na primeira caminhada.</span><span class="sxs-lookup"><span data-stu-id="d05d9-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="d05d9-146">Para criar um mapa ideal, experimente percorrer uma área de duas a três vezes.</span><span class="sxs-lookup"><span data-stu-id="d05d9-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="d05d9-147">Se possível, durante a repetição desses movimentos, passe um tempo andando em uma área em uma direção e, em seguida, vire e volte pelo caminho que você fez.</span><span class="sxs-lookup"><span data-stu-id="d05d9-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <span data-ttu-id="d05d9-148">Faça o mapeamento da área no seu tempo</span><span class="sxs-lookup"><span data-stu-id="d05d9-148">Take your time mapping the area</span></span>

<span data-ttu-id="d05d9-149">Pode levar de 15 a 20 minutos para que o HoloLens mapeie totalmente e se ajuste aos seus arredores.</span><span class="sxs-lookup"><span data-stu-id="d05d9-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="d05d9-150">Se você tiver um espaço no qual planeja usar um HoloLens frequentemente, dedicar esse tempo para mapear o espaço poderá evitar problemas mais tarde.</span><span class="sxs-lookup"><span data-stu-id="d05d9-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <span data-ttu-id="d05d9-151">Possíveis erros no mapa espacial</span><span class="sxs-lookup"><span data-stu-id="d05d9-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="d05d9-152">Os erros nos dados de mapeamento espacial se enquadram em algumas categorias:</span><span class="sxs-lookup"><span data-stu-id="d05d9-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="d05d9-153">*Buracos*: superfícies reais estão ausentes nos dados de mapeamento espacial.</span><span class="sxs-lookup"><span data-stu-id="d05d9-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="d05d9-154">*Alucinações*: existem superfícies nos dados de mapeamento espacial que não existem no mundo real.</span><span class="sxs-lookup"><span data-stu-id="d05d9-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="d05d9-155">*Buraco de Minhoca*: o HoloLens 'perde' parte do mapa espacial, pensando que está em uma parte diferente do mapa do que realmente está.</span><span class="sxs-lookup"><span data-stu-id="d05d9-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="d05d9-156">*Viés*: as superfícies nos dados de mapeamento espacial estão alinhadas imperfeitamente com superfícies reais, empurradas ou retiradas.</span><span class="sxs-lookup"><span data-stu-id="d05d9-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="d05d9-157">Se você vir qualquer um desses erros, use o [FeedbackHub](hololens-feedback.md) para enviar comentários.</span><span class="sxs-lookup"><span data-stu-id="d05d9-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <span data-ttu-id="d05d9-158">Segurança e armazenamento para dados espaciais</span><span class="sxs-lookup"><span data-stu-id="d05d9-158">Security and storage for spatial data</span></span>

<span data-ttu-id="d05d9-159">A atualização da versão 1803 do Windows 10 para o Microsoft HoloLens e versões posteriores armazenam o  mapeamento de dados em um banco de dados local (no dispositivo).</span><span class="sxs-lookup"><span data-stu-id="d05d9-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="d05d9-160">Os usuários do HoloLens não podem acessar diretamente o banco de dados do mapa, mesmo quando o dispositivo estiver conectado a um computador ou usando o aplicativo do Explorador de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="d05d9-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="d05d9-161">Quando o BitLocker está habilitado no HoloLens, os dados armazenados do mapa também são criptografados juntamente com o volume inteiro.</span><span class="sxs-lookup"><span data-stu-id="d05d9-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <span data-ttu-id="d05d9-162">Remover dados de mapa e espaços conhecidos do HoloLens</span><span class="sxs-lookup"><span data-stu-id="d05d9-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="d05d9-163">Há duas opções para excluir dados de mapa em **Configurações > Sistema > Hologramas**:</span><span class="sxs-lookup"><span data-stu-id="d05d9-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="d05d9-164">Para excluir hologramas próximos, marque **Remover hologramas próximos**.</span><span class="sxs-lookup"><span data-stu-id="d05d9-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="d05d9-165">Esse comando limpa os dados do mapa e os hologramas ancorados do espaço atual.</span><span class="sxs-lookup"><span data-stu-id="d05d9-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="d05d9-166">Se você continuar usando o dispositivo no mesmo espaço, o programa cria e armazena uma nova seção de mapa para substituir as informações excluídas.</span><span class="sxs-lookup"><span data-stu-id="d05d9-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d05d9-167">Os hologramas "próximos" são hologramas ancorados na mesma seção do mapa no espaço atual.</span><span class="sxs-lookup"><span data-stu-id="d05d9-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="d05d9-168">Por exemplo, você pode usar essa opção para limpar os dados do mapa relacionados ao trabalho, sem afetar os dados do mapa relacionados à página inicial.</span><span class="sxs-lookup"><span data-stu-id="d05d9-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="d05d9-169">Para excluir todos os hologramas, marque **Remover todos os hologramas**.</span><span class="sxs-lookup"><span data-stu-id="d05d9-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="d05d9-170">Esse comando limpa todos os dados do mapa armazenados no dispositivo, bem como todos os hologramas ancorados.</span><span class="sxs-lookup"><span data-stu-id="d05d9-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="d05d9-171">Será necessário posicionar os hologramas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="d05d9-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="d05d9-172">Você não poderá redescobrir os hologramas inseridos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d05d9-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="d05d9-173">Depois de remover o holograma ou todos os hologramas, o HoloLens começa a verificar e mapear o espaço atual imediatamente.</span><span class="sxs-lookup"><span data-stu-id="d05d9-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <span data-ttu-id="d05d9-174">Dados Wi-Fi em mapas espaciais</span><span class="sxs-lookup"><span data-stu-id="d05d9-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="d05d9-175">O HoloLens armazena características de Wi-Fi para ajudar a correlacionar os locais de holograma e a mapear seções armazenadas no banco de dados do HoloLens de espaços conhecidos.</span><span class="sxs-lookup"><span data-stu-id="d05d9-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="d05d9-176">As informações sobre características de Wi-Fi não são acessíveis aos usuários e não são enviadas para a Microsoft usando nuvem ou telemetria.</span><span class="sxs-lookup"><span data-stu-id="d05d9-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="d05d9-177">Enquanto o Wi-Fi estiver habilitado, o HoloLens correlaciona os dados do mapa com pontos de acesso de rede Wi-Fi próximos.</span><span class="sxs-lookup"><span data-stu-id="d05d9-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="d05d9-178">Não há diferença no comportamento, esteja uma rede está conectada ou apenas detectada nas proximidades.</span><span class="sxs-lookup"><span data-stu-id="d05d9-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="d05d9-179">Se o Wi-Fi estiver desabilitado, o HoloLens ainda pesquisará o espaço.</span><span class="sxs-lookup"><span data-stu-id="d05d9-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="d05d9-180">No entanto, o HoloLens deve pesquisar mais dados de mapa dentro do banco de dados dos espaços e talvez precise de mais tempo para encontrar hologramas.</span><span class="sxs-lookup"><span data-stu-id="d05d9-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="d05d9-181">Sem as informações de Wi-Fi, o HoloLens tem que comparar as verificações ativas a todas as âncoras de holograma e as seções de mapa armazenadas no dispositivo para localizar a parte correta do mapa.</span><span class="sxs-lookup"><span data-stu-id="d05d9-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <span data-ttu-id="d05d9-182">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d05d9-182">Related topics</span></span>

- [<span data-ttu-id="d05d9-183">Design de mapeamento espacial</span><span class="sxs-lookup"><span data-stu-id="d05d9-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
