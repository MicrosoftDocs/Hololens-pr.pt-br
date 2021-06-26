---
title: Perguntas frequentes sobre os dispositivos e hologramas do HoloLens
description: Você tem uma pergunta rápida sobre o HoloLens ou a interação com os hologramas?  Este artigo fornece uma resposta rápida e mais recursos.
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
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924019"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Solução de problemas de hologramas e interações

Este artigo soluciona problemas com o posicionamento de hologramas, o trabalho com espaços e a emissão de relatórios de problemas com hologramas.

Sempre que tiver problemas, verifique se:
- Tente [reiniciá-lo](hololens-restart-recover.md) para ver se ele corrige coisas.
- Antes de solucionar o problema, verifique se o HoloLens é [cobrado](hololens2-charging.md) (cobrado por pelo menos uma hora). 


Use o aplicativo de comentários para nos enviar informações sobre o problema. Você encontrará o aplicativo de comentários no [menu **Iniciar**](holographic-home.md). 

Para obter dicas sobre como ter o HoloLens, consulte [ajustar ajustar](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Não é possível criar novos espaços](#new-spaces-cant-be-created)
- [Os espaços não podem ser identificados ou carregados](#spaces-cant-be-identified-or-loaded)
- [Como fazer excluir todos os espaços?](#how-do-i-delete-all-spaces)
- [Os hologramas não parecem corretos ou estão se movendo](#holograms-dont-look-right-or-are-moving-around)
- [Mensagem "localizando seu espaço"](#finding-your-space-message)
- [Os hologramas esperados não estão aparecendo no meu espaço](#expected-holograms-arent-showing-in-my-space)
- [Não é possível colocar os hologramas ou Ver os hologramas colocados anteriormente](#cant-place-holograms-or-see-previously-placed-holograms)
- [Os hologramas desaparecem ou são encaixados em outros hologramas ou objetos](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Os hologramas estão aparecendo no outro lado de uma parede](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Depois de colocar um holograma em uma parede, ele parece flutuar](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Os aplicativos aparecem muito próximos depois de serem movidos](#apps-appear-too-close-after-moving-them)
- [Relatando problemas com hologramas instáveis ou inexatos](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Não é possível criar novos espaços

O problema mais provável é que você está ficando com pouco espaço de armazenamento. [Libere espaço em disco](hololens-troubleshooting.md#low-disk-space-error) e tente novamente.

[Voltar à lista](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Os espaços não podem ser identificados ou carregados

Se o seu HoloLens não conseguir identificar e carregar o espaço que você está automaticamente, verifique os seguintes fatores:

- Verifique se você está conectado a Wi-Fi
- Certifique-se de que há muita luz na sala
- Certifique-se de que não houvesse nenhuma alteração importante no ambiente.

Você também pode carregar um espaço manualmente ou gerenciar seus espaços acessando **configurações**  >    >  **espaços** do sistema.

[Voltar à lista](#list)

## <a name="how-do-i-delete-all-spaces"></a>Como fazer excluir todos os espaços?

*Em breve*

[Voltar à lista](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Os hologramas não parecem corretos ou estão se movendo

Se os hologramas não parecerem corretos (por exemplo, eles estão tremidos ou tremidoss, ou se você vir patches pretos sobre eles), tente uma destas correções:

- [Limpe o visor do dispositivo](hololens1-hardware.md#care-and-cleaning) e certifique-se de que nada esteja bloqueando os sensores.
- Verifique se você está em uma sala bem iluminada que não tem muita luz de sol direta.
- Tente percorrer e nuvens ao seu lugar para que o HoloLens possa examiná-los mais completamente.
- Se você colocou muitos hologramas, tente remover alguns.

Se você ainda tiver problemas, tente executar o aplicativo de calibragem. Esse aplicativo Calibra o seu HoloLens apenas para que você ajude a manter seus hologramas mais adequados. Para fazer isso, vá para **configurações**  >    >  **utilitários** do sistema. Em **calibragem**, selecione **abrir calibragem**.

[Voltar à lista](#list)

## <a name="finding-your-space-message"></a>Mensagem "localizando seu espaço"

Quando o HoloLens está aprendendo ou carregando um espaço, você pode ver uma breve mensagem que diz "encontrando seu espaço". Se essa mensagem for exibida por mais de alguns segundos, você verá outra mensagem no menu iniciar que diz "ainda procurando seu espaço".

Essas mensagens significam que o HoloLens está tendo problemas para mapear seu espaço. Quando isso acontece, você pode abrir aplicativos, mas não pode posicionar os hologramas em seu ambiente.

Se você vir essas mensagens com frequência, tente uma ou mais das seguintes correções:

- Verifique se você está em uma sala bem iluminada que não tem muita luz de sol direta.
- Verifique se o visor do dispositivo está limpo. [Saiba como limpar o visor](hololens1-hardware.md#care-and-cleaning).
- Verifique se você tem um sinal de Wi-Fi forte. Se você inserir um novo ambiente que não tem nenhum Wi-Fi ou um sinal de Wi-Fi fraco, o HoloLens não poderá encontrar seu espaço. Verifique a conexão do Wi-Fi acessando **configurações**  >  **rede &amp; Internet**  >  **Wi-Fi**.
- Tente mover mais lentamente.

[Voltar à lista](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Os hologramas esperados não estão aparecendo no meu espaço

Se você não vir os hologramas que colocou, ou se estiver vendo alguns que não espera, tente uma ou mais das seguintes correções:

- Ative algumas luzes. O HoloLens funciona melhor em um espaço bem aceso.
- Remova os hologramas que você não precisa, acessando **configurações**  >    >  **hologramas** do sistema  >  **remover hologramas próximos**. Ou, se necessário, selecione **remover todos os hologramas**.

  > [!NOTE]
  > Se o layout ou a iluminação em seu espaço mudar significativamente, seu dispositivo poderá ter problemas para identificar seu espaço e mostrar os hologramas.

[Voltar à lista](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Não é possível colocar os hologramas ou Ver os hologramas colocados anteriormente

Se o HoloLens não puder mapear ou carregar seu espaço, ele entrará no modo limitado e você não poderá colocar os hologramas ou Ver os hologramas que você colocou. Tente o seguinte:

- Verifique se há luz suficiente em seu ambiente para que o HoloLens possa ver e mapear o espaço.
- Entre um e três medidores de onde você está tentando posicionar o holograma.
- Não coloque os hologramas em superfícies pretas ou reflexivas.
- Verifique se você está conectado a uma rede Wi-Fi. Se você não estiver conectado ao Wi-Fi, o HoloLens não poderá identificar e carregar um espaço conhecido.
- Percorra as salas para que o HoloLens possa examinar novamente seu ambiente. Para ver o que já foi verificado, toque em ar para revelar o gráfico de malha de mapeamento.
- Se você precisar criar um novo espaço, conecte-se ao Wi-Fi e reinicie o HoloLens.
- Para ver se o espaço correto está ativo ou para carregar manualmente um espaço, acesse **configurações**  >    >  **espaços** do sistema.
- Se o espaço correto for carregado e você ainda tiver problemas, o espaço poderá estar corrompido. Para corrigir esse problema, selecione o espaço e, em seguida, selecione **remover**. Depois de remover o espaço, o HoloLens começa a mapear seus arredores e criar um novo espaço.

[Voltar à lista](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Os hologramas desaparecem ou são encaixados em outros hologramas ou objetos

Se você ficar muito próximo de um holograma, ele desaparecerá temporariamente &mdash; para restaurar o holograma, apenas se afastar dele. Além disso, se você colocou vários hologramas próximos juntos, alguns podem desaparecer. Tente remover alguns.

Os hologramas também podem ser bloqueados ou encaixados por outros hologramas ou por objetos como paredes. Se isso acontecer, tente uma das seguintes correções:

- Se o holograma for encaixado em outro holograma, mova o holograma encaixado para outro local. Para fazer isso, selecione **ajustar**, em seguida, toque e segure para posicioná-lo.
- Se o holograma for encaixado em uma parede, selecione **ajustar** e, em seguida, percorra a parede até que o holograma seja exibido. Toque e segure e, em seguida, puxe o holograma para frente e para fora da parede.
- Se você não conseguir mover o holograma usando gestos, use sua voz para removê-lo. Olhar no holograma e, em seguida, diga "remover". Em seguida, reabra o holograma e coloque-o em um novo local.

[Voltar à lista](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramas estão aparecendo no outro lado de uma parede

Se você estiver muito próximo de uma parede ou se o HoloLens ainda não tiver verificado a parede, poderá ver hologramas que estão na próxima sala. Para examinar a parede, fique entre um e três metros da parede e a acar dele.

Um objeto preto ou reflexivo (por exemplo, um diviso preto ou um refrigerador de metal) próximo à parede pode causar problemas quando o HoloLens tenta examinar a parede. Se houver esse objeto, digitalizar o outro lado da parede.

[Voltar à lista](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Depois de colocar um holograma em uma parede, parece que ela flutua

Um holograma que você coloca em uma parede normalmente parece estar a uma polegada ou mais distante da parede. Se ele parecer estar mais distante, tente uma ou mais das seguintes correções:

- Quando você coloca um holograma em uma parede, fica entre um e três metros da parede e enfrenta a parede diretamente.
- Toque no ar na parede para revelar o gráfico de malha de mapeamento. Certifique-se de que a malha esteja alinhada com a parede. Se isso não acontecer, remova o holograma,scane novamente a parede e tente novamente.
- Se o problema persistir, execute o aplicativo Calibragem. Você o encontrará em **Configurações utilitários**  >    >  **do sistema.**

[Voltar à lista](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Os aplicativos aparecem muito próximos depois de move-los

Tente dar uma volta e olhar para a área em que você está colocando o aplicativo para que o HoloLens examina a área de ângulos diferentes. [Limpar o visor do dispositivo](hololens1-hardware.md#care-and-cleaning) também pode ajudar.

[Voltar à lista](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Relatar problemas com hologramas instável ou inexatos
 
1. Grave e um [Captura de Realidade Misturada vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) do problema. Este vídeo pode ser carregado posteriormente por meio do Hub de Comentários como um arquivo anexado.  
1. Habilita a  telemetria completa por meio do aplicativo Configurações -> **de** Diagnóstico de Privacidade & comentários e, em Dados de diagnóstico  ->   **opcionais,** verifique se a alternância está definida como **Ativado**
1. Obter as correções mais recentes de escala e estabilidade do holograma atualizando para o sistema operacional [Windows Holographic mais recente, (20H2 ou superior).](hololens-release-notes.md#windows-holographic-version-20h2) Após a atualização, execute o seguinte:
    1. Remova todos os hologramas por meio do aplicativo **Settings** ->  ->  **System Holograms** -> selecione Remover todos **os hologramas** e comece com um mapa novo.
    1. Crie um novo mapa do seu espaço usando o HoloLens e passeando em sua sala e observando todas as áreas e superfícies no espaço. Faça isso por 2 a 3 minutos.
    1. Execute a calibragem de IPD. Vá para **Configurações**  >  **Utilitários**  >  **do Sistema**. Em **Calibragem,** selecione **Abrir Calibragem**.
    1. Teste o cenário e veja se ele ainda persiste.
1. Se a atualização não corrigir o problema, arquiva um problema [do Hub de Comentários.](hololens-feedback.md) Depois de preencher os comentários,  você poderá usar o botão Compartilhar para criar um link fácil de compartilhar que pode ser enviado ao entrar em contato com o suporte.

[Voltar à lista](#list)