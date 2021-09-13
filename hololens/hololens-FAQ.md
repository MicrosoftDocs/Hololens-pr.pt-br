---
title: Perguntas frequentes sobre HoloLens e hologramas
description: Você tem uma pergunta rápida sobre como HoloLens ou interagir com hologramas?  Este artigo fornece uma resposta rápida e mais recursos.
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
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031930"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramas solução de problemas e interações

Este artigo soluciona problemas com a colocação de hologramas, o trabalho com espaços e o relatório de problemas com hologramas.

Sempre que você tiver problemas, certifique-se de:
- Tente [reiniciá-lo](hololens-restart-recover.md) para ver se isso corrige as coisas.
- Antes de solucionar problemas, verifique se HoloLens é [cobrado](hololens2-charging.md) (cobrado por pelo menos uma hora). 


Use o aplicativo comentários para nos enviar informações sobre o problema. Você encontrará o aplicativo comentários no [  menu Iniciar](holographic-home.md). 

Para ver dicas sobre como usar seu HoloLens, consulte [Ajustar Ajuste.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [Não é possível criar novos espaços](#new-spaces-cant-be-created)
- [Os espaços não podem ser identificados ou carregados](#spaces-cant-be-identified-or-loaded)
- [Como fazer excluir todos os espaços?](#how-do-i-delete-all-spaces)
- [Hologramas não parecem corretos ou estão se movendo](#holograms-dont-look-right-or-are-moving-around)
- [Mensagem "Encontrando seu espaço"](#finding-your-space-message)
- [Hologramas esperados não estão sendo exibidos em meu espaço](#expected-holograms-arent-showing-in-my-space)
- [Não é possível colocar hologramas ou ver hologramas colocados anteriormente](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramas desaparecer ou são encapsulados em outros hologramas ou objetos](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramas estão aparecendo no outro lado de uma parede](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Depois de colocar um holograma em uma parede, parece que ela flutua](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Os aplicativos aparecem muito próximos depois de move-los](#apps-appear-too-close-after-moving-them)
- [Relatar problemas com hologramas instável ou inexatos](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Não é possível criar novos espaços

O problema mais provável é que você está ficando sem espaço de armazenamento. [Liberar espaço em disco e](hololens-troubleshooting.md#low-disk-space-error) tentar novamente.

[Voltar para a lista](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Os espaços não podem ser identificados ou carregados

Se o HoloLens não puder identificar e carregar o espaço em que você está automaticamente, verifique os seguintes fatores:

- Certifique-se de que você está conectado ao Wi-Fi
- Certifique-se de que haja muita luz na sala
- Certifique-se de que não houve nenhuma alteração importante no ambiente.

Você também pode carregar um espaço manualmente ou gerenciar seus espaços indo para **Configurações**  >  **System**  >  **Spaces**.

[Voltar para a lista](#list)

## <a name="how-do-i-delete-all-spaces"></a>Como fazer excluir todos os espaços?

*Em breve*

[Voltar para a lista](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramas não parecem corretos ou estão se movendo

Se os hologramas não parecer corretos (por exemplo, eles estão tremulando ou confusos ou você vê patches pretos sobre eles), tente uma destas correções:

- [Limpe o visor do dispositivo](hololens1-hardware.md#care-and-cleaning) e certifique-se de que nada está bloqueando os sensores.
- Certifique-se de que você esteja em uma sala bem luminada que não tenha muitos s meio diretos.
- Tente dar uma volta e olhar ao redor para que HoloLens possa digitalizar mais completamente.
- Se você tiver colocado muitos hologramas, tente remover alguns.

Se você ainda estiver tendo problemas, tentando executar o aplicativo De calibragem. Esse aplicativo calibra seu HoloLens apenas para ajudar a manter seus hologramas com melhor aparência. Para fazer isso, vá para **Configurações**  >    >  **Utilitários do Sistema**. Em **Calibragem,** selecione **Abrir Calibragem**.

[Voltar para a lista](#list)

## <a name="finding-your-space-message"></a>Mensagem "Encontrando seu espaço"

Quando HoloLens estiver aprendendo ou carregando um espaço, você poderá ver uma breve mensagem que diz "Encontrando seu espaço". Se essa mensagem for exibida por mais de alguns segundos, você verá outra mensagem no menu Iniciar que diz "Ainda procurando seu espaço".

Essas mensagens significam que HoloLens está tendo problemas para mapear seu espaço. Quando isso acontece, você pode abrir aplicativos, mas não pode colocar hologramas em seu ambiente.

Se você vir essas mensagens com frequência, tente uma ou mais das seguintes correções:

- Certifique-se de que você esteja em uma sala bem luminada que não tenha muitos s meio diretos.
- Certifique-se de que o visor do dispositivo está limpo. [Saiba como limpar o visor.](hololens1-hardware.md#care-and-cleaning)
- Certifique-se de que você tenha um sinal Wi-Fi forte. Se você inserir um novo ambiente que não tenha Wi-Fi ou um sinal Wi-Fi fraco, HoloLens poderá encontrar seu espaço. Verifique sua Wi-Fi de rede, indo **para Configurações** Rede  >  **&amp;**  >  **Wi-Fi da** Internet.
- Tente mover mais lentamente.

[Voltar para a lista](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Hologramas esperados não estão sendo exibidos em meu espaço

Se você não vir os hologramas que colocou ou se estiver vendo alguns que não espera, tente uma ou mais das seguintes correções:

- A ligar algumas luzes. HoloLens funciona melhor em um espaço bem-claro.
- Remova os hologramas que você não precisa indo para **Configurações**  >  **Sistema**  >  **Hologramas**  >  **Remover hologramas próximos.** Ou, se necessário, selecione **Remover todos os hologramas.**

  > [!NOTE]
  > Se o layout ou a iluminação em seu espaço mudar significativamente, seu dispositivo poderá ter problemas para identificar seu espaço e mostrar seus hologramas.

[Voltar para a lista](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Não é possível colocar hologramas ou ver hologramas colocados anteriormente

Se HoloLens não puder mapear ou carregar seu espaço, ele entrará no modo Limitado e você não poderá colocar hologramas ou ver hologramas que você colocou. Tente o seguinte:

- Certifique-se de que haja luz suficiente em seu ambiente para que HoloLens possa ver e mapear o espaço.
- Fique entre um e três metros de onde você está tentando colocar o holograma.
- Não coloque hologramas em superfícies pretas ou reflexivas.
- Certifique-se de que você está conectado a uma Wi-Fi rede. Se você não estiver conectado ao Wi-Fi, HoloLens poderá identificar e carregar um espaço conhecido.
- Ande pela sala para que HoloLens possa reexame seu ambiente. Para ver o que já foi verificado, toque no ar para revelar o gráfico de malha de mapeamento.
- Se você precisar criar um novo espaço, conecte-se ao Wi-Fi e reinicie o HoloLens.
- Para ver se o espaço correto está ativo ou para carregar manualmente um espaço, acesse Configurações  >  **System**  >  **Spaces.**
- Se o espaço correto for carregado e você ainda tiver problemas, o espaço poderá estar corrompido. Para corrigir esse problema, selecione o espaço e, em seguida, **selecione Remover**. Depois de remover o espaço, HoloLens começa a mapear seu ambiente e criar um novo espaço.

[Voltar para a lista](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramas desaparecer ou são encapsulados em outros hologramas ou objetos

Se você se aproximar muito de um holograma, ele desaparecerá temporariamente para restaurar o &mdash; holograma, apenas saia dele. Além disso, se você tiver colocado vários hologramas próximos, alguns poderão desaparecer. Tente remover alguns.

Hologramas também pode ser bloqueado ou encapsulado por outros hologramas ou por objetos como paredes. Se isso acontecer, tente uma das seguintes correções:

- Se o holograma estiver encapsulado em outro holograma, mova o holograma encassado para outro local. Para fazer isso, selecione **Ajustar** e, em seguida, toque e segure para posicioná-lo.
- Se o holograma estiver encassado em uma parede, selecione **Ajustar** e, em seguida, vá até a parede até que o holograma apareça. Toque e segure e, em seguida, espe o holograma para frente e para fora da parede.
- Se você não puder mover o holograma usando gestos, use sua voz para removê-lo. Olhar para o holograma e, em seguida, dizer "Remover". Em seguida, reabra o holograma e coloque-o em um novo local.

[Voltar para a lista](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramas estão aparecendo no outro lado de uma parede

Se você estiver muito próximo a uma parede ou se HoloLens ainda não examinou a parede, poderá ver hologramas que estão na próxima sala. Para examinar a parede, fique entre um e três metros da parede e a acar dele.

Um objeto preto ou reflexivo (por exemplo, um diviso preto ou um refrigerador de metal) próximo à parede pode causar problemas quando HoloLens tenta examinar a parede. Se houver esse objeto, digitalizar o outro lado da parede.

[Voltar para a lista](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Depois de colocar um holograma em uma parede, parece que ela flutua

Um holograma que você coloca em uma parede normalmente parece estar a uma polegada ou mais distante da parede. Se ele parecer estar mais distante, tente uma ou mais das seguintes correções:

- Quando você coloca um holograma em uma parede, fica entre um e três metros da parede e enfrenta a parede diretamente.
- Toque no ar na parede para revelar o gráfico de malha de mapeamento. Certifique-se de que a malha esteja alinhada com a parede. Se isso não acontecer, remova o holograma,scane novamente a parede e tente novamente.
- Se o problema persistir, execute o aplicativo Calibragem. Você o encontrará em utilitários **Configurações**  >    >  **sistema.**

[Voltar para a lista](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Os aplicativos aparecem muito próximos depois de move-los

Tente dar uma volta e olhar para a área em que você está colocando o aplicativo para que HoloLens a área de ângulos diferentes. [Limpar o visor do dispositivo](hololens1-hardware.md#care-and-cleaning) também pode ajudar.

[Voltar para a lista](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Relatar problemas com hologramas instável ou inexatos
 
1. Grave e um [Captura de Realidade Misturada vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) do problema. Este vídeo pode ser carregado posteriormente por meio do Hub de Comentários como um arquivo anexado.  
1. Habilita a telemetria completa por meio **do** aplicativo Configurações -> **de** diagnóstico de privacidade & comentários e, em Dados de diagnóstico  ->   **opcionais,** verifique se a alternância está definida como **Ativado**
1. Obter as correções mais recentes de escala e estabilidade do holograma atualizando para o sistema [operacional holográfico Windows mais recente, (20H2 ou superior).](hololens-release-notes.md#windows-holographic-version-20h2) Após a atualização, execute o seguinte:
    1. Remova todos os Hologramas via **Configurações** -> **System** Hologramas -> selecione Remover todos os hologramas e comece com  ->   um novo mapa. 
    1. Crie um novo mapa do seu espaço usando o HoloLens e passeando em sua sala e observando todas as áreas e superfícies no espaço. Faça isso por 2 a 3 minutos.
    1. Execute a calibragem de IPD. Vá para **Configurações**  >    >  **utilitários do sistema.** Em **Calibragem,** selecione **Abrir Calibragem**.
    1. Teste o cenário e veja se ele ainda persiste.
1. Se a atualização não corrigir o problema, arquiva um problema [do Hub de Comentários.](hololens-feedback.md) Depois de preencher os comentários,  você poderá usar o botão Compartilhar para criar um link fácil de compartilhar que pode ser enviado ao entrar em contato com o suporte.

[Voltar para a lista](#list)