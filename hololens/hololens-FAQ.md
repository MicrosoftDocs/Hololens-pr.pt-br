---
title: perguntas frequentes sobre HoloLens dispositivos e hologramas
description: você tem uma pergunta rápida sobre HoloLens ou interagir com hologramas?  Este artigo fornece uma resposta rápida e mais recursos.
keywords: hololens, perguntas frequentes, problema conhecido, ajuda
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664614"
---
# <a name="holograms-and-interactions-troubleshooting"></a>solução de problemas de Hologramas e interações

Este artigo soluciona problemas com o posicionamento de hologramas, o trabalho com espaços e a emissão de relatórios de problemas com hologramas.

Sempre que tiver problemas, verifique se:
- Tente [reiniciá-lo](hololens-restart-recover.md) para ver se ele corrige coisas.
- antes de solucionar o problema, verifique se o HoloLens é [cobrado](hololens2-charging.md) (cobrado por pelo menos uma hora). 


Use o aplicativo de comentários para nos enviar informações sobre o problema. Você encontrará o aplicativo de comentários no [menu **Iniciar**](holographic-home.md). 

para obter dicas sobre como fazer o HoloLens, consulte [ajustar ajustar](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Não é possível criar novos espaços](#new-spaces-cant-be-created)
- [Os espaços não podem ser identificados ou carregados](#spaces-cant-be-identified-or-loaded)
- [Como fazer excluir todos os espaços?](#how-do-i-delete-all-spaces)
- [Hologramas não parecem corretos ou estão se movendo](#holograms-dont-look-right-or-are-moving-around)
- [Mensagem "localizando seu espaço"](#finding-your-space-message)
- [Os hologramas esperados não estão aparecendo no meu espaço](#expected-holograms-arent-showing-in-my-space)
- [Não é possível colocar os hologramas ou Ver os hologramas colocados anteriormente](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramas desaparecer ou são encaixados em outros hologramas ou objetos](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramas estão aparecendo no outro lado de uma parede](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Depois de colocar um holograma em uma parede, ele parece flutuar](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Os aplicativos aparecem muito próximos depois de serem movidos](#apps-appear-too-close-after-moving-them)
- [Relatando problemas com hologramas instáveis ou inexatos](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Não é possível criar novos espaços

O problema mais provável é que você está ficando com pouco espaço de armazenamento. [Libere espaço em disco](hololens-troubleshooting.md#low-disk-space-error) e tente novamente.

[Voltar para a lista](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Os espaços não podem ser identificados ou carregados

se o HoloLens não puder identificar e carregar o espaço que você está automaticamente, verifique os seguintes fatores:

- Verifique se você está conectado a Wi-Fi
- Certifique-se de que há muita luz na sala
- Certifique-se de que não houvesse nenhuma alteração importante no ambiente.

você também pode carregar um espaço manualmente ou gerenciar seus espaços acessando **Configurações**  >    >  **espaços** do sistema.

[Voltar para a lista](#list)

## <a name="how-do-i-delete-all-spaces"></a>Como fazer excluir todos os espaços?

*Em breve*

[Voltar para a lista](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramas não parecem corretos ou estão se movendo

Se os hologramas não parecerem corretos (por exemplo, eles estão tremidos ou tremidoss, ou se você vir patches pretos sobre eles), tente uma destas correções:

- [Limpe o visor do dispositivo](hololens1-hardware.md#care-and-cleaning) e certifique-se de que nada esteja bloqueando os sensores.
- Verifique se você está em uma sala bem iluminada que não tem muita luz de sol direta.
- tente percorrer e nuvens ao seu lugar para que HoloLens possa examiná-los mais completamente.
- Se você colocou muitos hologramas, tente remover alguns.

Se você ainda tiver problemas, tente executar o aplicativo de calibragem. esse aplicativo calibra sua HoloLens apenas para que você ajude a manter seus hologramas com a melhor aparência. para fazer isso, vá para **Configurações**  >    >  **utilitários** do sistema. Em **calibragem**, selecione **abrir calibragem**.

[Voltar para a lista](#list)

## <a name="finding-your-space-message"></a>Mensagem "localizando seu espaço"

quando HoloLens estiver aprendendo ou carregando um espaço, você poderá ver uma breve mensagem que diz "encontrando seu espaço". se essa mensagem for exibida por mais de alguns segundos, você verá outra mensagem na menu Iniciar que diz "ainda procurando seu espaço".

essas mensagens significam que HoloLens está tendo problemas para mapear seu espaço. Quando isso acontece, você pode abrir aplicativos, mas não pode posicionar os hologramas em seu ambiente.

Se você vir essas mensagens com frequência, tente uma ou mais das seguintes correções:

- Verifique se você está em uma sala bem iluminada que não tem muita luz de sol direta.
- Verifique se o visor do dispositivo está limpo. [Saiba como limpar o visor](hololens1-hardware.md#care-and-cleaning).
- Verifique se você tem um sinal de Wi-Fi forte. se você inserir um novo ambiente que não tenha Wi-Fi ou um sinal de Wi-Fi fraco, HoloLens não poderá encontrar seu espaço. verifique sua conexão de Wi-Fi acessando **Configurações**  >  **rede &amp; Internet**  >  **Wi-Fi**.
- Tente mover mais lentamente.

[Voltar para a lista](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Os hologramas esperados não estão aparecendo no meu espaço

Se você não vir os hologramas que colocou, ou se estiver vendo alguns que não espera, tente uma ou mais das seguintes correções:

- Ative algumas luzes. HoloLens funciona melhor em um espaço bem aceso.
- remova os hologramas que você não precisa acessando **Configurações**  >  **sistema**  >  **Hologramas**  >  **remover os hologramas próximos**. Ou, se necessário, selecione **remover todos os hologramas**.

  > [!NOTE]
  > Se o layout ou a iluminação em seu espaço mudar significativamente, seu dispositivo poderá ter problemas para identificar seu espaço e mostrar os hologramas.

[Voltar para a lista](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Não é possível colocar os hologramas ou Ver os hologramas colocados anteriormente

se HoloLens não puder mapear ou carregar seu espaço, ele entrará no modo limitado e você não poderá colocar os hologramas ou conferir os hologramas que você colocou. Tente o seguinte:

- verifique se há luz suficiente em seu ambiente para que HoloLens possa ver e mapear o espaço.
- Entre um e três medidores de onde você está tentando posicionar o holograma.
- Não coloque os hologramas em superfícies pretas ou reflexivas.
- Verifique se você está conectado a uma rede Wi-Fi. se você não estiver conectado ao Wi-Fi, HoloLens não poderá identificar e carregar um espaço conhecido.
- percorra as salas para que HoloLens possa examinar novamente o ambiente. Para ver o que já foi verificado, toque em ar para revelar o gráfico de malha de mapeamento.
- Se você precisar criar um novo espaço, conecte-se ao Wi-Fi e reinicie o HoloLens.
- para ver se o espaço correto está ativo ou para carregar manualmente um espaço, acesse **Configurações**  >    >  **espaços** do sistema.
- Se o espaço correto for carregado e você ainda tiver problemas, o espaço poderá estar corrompido. Para corrigir esse problema, selecione o espaço e, em seguida, selecione **remover**. depois de remover o espaço, HoloLens começará a mapear seus arredores e criar um novo espaço.

[Voltar para a lista](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramas desaparecer ou são encaixados em outros hologramas ou objetos

Se você ficar muito próximo de um holograma, ele desaparecerá temporariamente &mdash; para restaurar o holograma, apenas se afastar dele. Além disso, se você colocou vários hologramas próximos juntos, alguns podem desaparecer. Tente remover alguns.

Hologramas também pode ser bloqueado ou encaixado por outros hologramas ou por objetos como paredes. Se isso acontecer, tente uma das seguintes correções:

- Se o holograma for encaixado em outro holograma, mova o holograma encaixado para outro local. Para fazer isso, selecione **ajustar**, em seguida, toque e segure para posicioná-lo.
- Se o holograma for encaixado em uma parede, selecione **ajustar** e, em seguida, percorra a parede até que o holograma seja exibido. Toque e segure e, em seguida, puxe o holograma para frente e para fora da parede.
- Se você não conseguir mover o holograma usando gestos, use sua voz para removê-lo. Olhar no holograma e, em seguida, diga "remover". Em seguida, reabra o holograma e coloque-o em um novo local.

[Voltar para a lista](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramas estão aparecendo no outro lado de uma parede

se você estiver muito perto de uma parede ou se HoloLens ainda não tiver verificado a parede, você poderá ver os hologramas que estão na sala seguinte. Para digitalizar a parede, fique entre um e três medidores da parede e olhar-o.

um objeto preto ou reflexivo (por exemplo, um sofá negro ou um refrigerador de aço stainless) perto da parede pode causar problemas quando HoloLens tenta digitalizar a parede. Se houver um objeto desse tipo, digitalize o outro lado da parede.

[Voltar para a lista](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Depois de colocar um holograma em uma parede, ele parece flutuar

Um holograma que você coloca em uma parede normalmente parece ser uma polegada ou muito longe da parede. Se parecer mais distante, tente uma ou mais das seguintes correções:

- Quando você coloca um holograma em uma parede, ele se destaca entre um e três metros da parede e face a parede diretamente.
- O ar toca na parede para revelar o gráfico de malha de mapeamento. Certifique-se de que a malha se alinhe com a parede. Se não estiver, remova o holograma, examine novamente a parede e tente novamente.
- Se o problema persistir, execute o aplicativo de calibragem. você o encontrará em **Configurações**  >    >  **utilitários** do sistema.

[Voltar para a lista](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Os aplicativos aparecem muito próximos depois de serem movidos

tente percorrer a área em que você está colocando o aplicativo para que HoloLens examine a área de diferentes ângulos. [Limpar o visor do dispositivo](hololens1-hardware.md#care-and-cleaning) também pode ajudar.

[Voltar para a lista](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Relatando problemas com hologramas instáveis ou inexatos
 
1. Registre-se e um [vídeo de captura de realidade misturada](holographic-photos-and-videos.md#capture-a-mixed-reality-video) do problema. Este vídeo pode ser carregado posteriormente por meio do hub de comentários como um arquivo anexado.  
1. habilite a telemetria completa por meio do **Configurações** app-> diagnóstico de **privacidade**  ->  **& comentários** e, em **dados de diagnóstico opcionais** , verifique se a alternância está definida como **ativada**
1. obtenha a escala de holograma mais recente e as correções de estabilidade atualizando para o mais recente [Windows o sistema operacional Holographic, (20H2 ou superior)](hololens-release-notes.md#windows-holographic-version-20h2). Após a atualização, execute o seguinte:
    1. remova todos os Hologramas por meio do **Configurações** app-> **System**  ->  **Hologramas** -> em seguida, selecione **remover todos os hologramas** e comece com um mapa atualizado.
    1. crie um novo mapa do seu espaço aproveitando o HoloLens e percorrendo sua sala e observando todas as áreas e superfícies no espaço. Faça isso por 2-3 minutos.
    1. Executar calibração de IPD. vá para **Configurações**  >    >  **utilitários** do sistema. Em **calibragem**, selecione **abrir calibragem**.
    1. Teste novamente o cenário e veja se ele ainda persiste.
1. Se a atualização não corrigir o problema, registre um [problema de Hub de comentários](hololens-feedback.md). Depois de preencher os comentários, você pode usar o botão **compartilhar** para criar um link fácil de compartilhar que pode ser enviado ao contatar o suporte.

[Voltar para a lista](#list)