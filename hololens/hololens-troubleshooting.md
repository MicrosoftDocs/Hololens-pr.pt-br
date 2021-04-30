---
title: Solução de problemas
description: Mantenha-se atualizado sobre as soluções mais comuns para problemas de dispositivos de HoloLens e técnicas de solução de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, Bug, solução de problemas, correção, ajuda, suporte, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308142"
---
# <a name="troubleshooting"></a>Solução de problemas

Este artigo descreve como resolver vários problemas comuns do HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>Meu HoloLens não está respondendo ou não será iniciado

Se o seu HoloLens não iniciar:

- Se os LEDs próximos ao botão de energia não acenderem ou apenas um LED piscar brevemente, talvez seja necessário [cobrar seu HoloLens.](hololens-recovery.md#charge-the-device)
- Se os LEDs acenderem quando você pressionar o botão de energia, mas não conseguir ver nada em exibições, [realizar uma redefinição de hardware do dispositivo](hololens-recovery.md#hard-reset-procedure).

Se seu HoloLens ficar congelado ou sem resposta:

- Desative seu HoloLens pressionando o botão de energia até que todos os cinco LEDs fiquem desligados ou por 15 segundos se os LEDs não responderem. Para iniciar o HoloLens, pressione o botão de energia novamente.

Se essas etapas não funcionarem, você poderá tentar [recuperar o dispositivo do hololens 2 ou o](hololens-recovery.md) [dispositivo hololens (1ª gen).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Os hologramas não parecem bons

Se os hologramas estiverem instáveis, com salto ou não estiverem corretos, tente:

- Limpando o visor do dispositivo e a barra de sensor na frente do seu HoloLens.
- Aumentando a luz em sua sala.
- Percorrendo e olhando seu ambiente para que o HoloLens possa examiná-los mais completamente.
- Calibrando seu HoloLens para seus olhos. Vá para **configurações**  >    >  **utilitários** do sistema. Em **calibragem**, selecione **abrir calibragem**.
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Problemas de relatório em que os hologramas estão instáveis ou não parecem corretos
 
1. Registre-se e um [vídeo de captura de realidade misturada](holographic-photos-and-videos.md#capture-a-mixed-reality-video) do problema. Este vídeo pode ser carregado posteriormente por meio do hub de comentários como um arquivo anexado.  
1. Habilite a telemetria completa por meio do aplicativo **configurações** -> diagnóstico de **privacidade**  ->  **& comentários** e, em **dados de diagnóstico opcionais** , verifique se a alternância está definida como **ativada**
1. Obtenha a escala de holograma mais recente e as correções de estabilidade Atualizando para o [sistema operacional Windows Holographic mais recente, (20H2 ou superior)](hololens-release-notes.md#windows-holographic-version-20h2). Após a atualização, execute o seguinte:
    1. Remova todos os hologramas por meio **das configurações** aplicativo->   ->  **hologramas** do sistema->, em seguida, selecione **remover todos os hologramas** e comece com um mapa atualizado.
    1. Crie um novo mapa do seu espaço aproveitando o HoloLens e percorrendo sua sala e observando todas as áreas e superfícies no espaço. Faça isso por 2-3 minutos.
    1. Executar calibração de IPD. Vá para **configurações**  >    >  **utilitários** do sistema. Em **calibragem**, selecione **abrir calibragem**.
    1. Teste novamente o cenário e veja se ele ainda persiste.
1. Se a atualização não corrigir o problema, registre um [problema de Hub de comentários](hololens-feedback.md). Depois de preencher os comentários, você pode usar o botão **compartilhar** para criar um link fácil de compartilhar que pode ser enviado ao contatar o suporte.

## <a name="hololens-doesnt-respond-to-hand-input"></a>O HoloLens não responde à entrada manual

Para garantir que o HoloLens possa ver suas mãos, você precisa mantê-las no quadro do gesto.  A página inicial da realidade misturada fornece comentários que permitem que você saiba quando suas mãos são rastreadas.  Os comentários são diferentes em versões diferentes do HoloLens:
- No HoloLens (1º gen), o cursor olhar muda de um ponto para um anel
- No HoloLens 2, um cursor de ponta aparece quando a sua mão está perto de um Tablet, e um raio de lado é exibido quando os slates estão mais distantes

Muitos aplicativos de imersão seguem os padrões de entrada que são semelhantes à realidade misturada em casa.  Saiba mais sobre como usar a entrada manual no [hololens (1ª gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) e o [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se você estiver gastando luvas, observe que alguns tipos de luvas não funcionam com o rastreamento manual.  Um exemplo comum é o luvas de borracha preta, que tende a absorver a luz infravermelha e não é captado pela câmera de profundidade.  Se seu trabalho envolve um luvas de borracha, é recomendável tentar uma cor mais clara, como azul ou cinza.  Outro exemplo é o luvas de Baggy grande, que tendem a obscurecer a forma de sua mão. É recomendável usar luvas que estejam como o ajuste de forma possível para obter melhores resultados.

Se o visor tiver impressões digitais ou manchas, use o pano de limpeza microfiber que veio com o HoloLens para limpar o visor com cuidado.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>O HoloLens não responde aos meus comandos de voz

Se a Cortana não estiver respondendo aos seus comandos de voz, verifique se a Cortana está ativada. Na lista todos os aplicativos, selecione o menu **Cortana**  >    >    >  **configurações** do bloco de anotações para fazer alterações. Para saber mais sobre o que você pode dizer, consulte [usar sua voz com o HoloLens](hololens-cortana.md).

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Não posso colocar hologramas ou Ver os hologramas que fiz anteriormente

Se o HoloLens não puder mapear ou carregar seu espaço, ele entrará no modo limitado e você não poderá colocar os hologramas ou Ver os hologramas que você colocou. Tente o seguinte:

- Verifique se há luz suficiente em seu ambiente para que o HoloLens possa ver e mapear o espaço.
- Verifique se você está conectado a uma rede Wi-Fi. Se você não estiver conectado ao Wi-Fi, o HoloLens não poderá identificar e carregar um espaço conhecido.
- Se você precisar criar um novo espaço, conecte-se ao Wi-Fi e reinicie o HoloLens.
- Para ver se o espaço correto está ativo ou para carregar manualmente um espaço, acesse **configurações**  >    >  **espaços** do sistema.
- Se o espaço correto for carregado e você ainda tiver problemas, o espaço poderá estar corrompido. Para corrigir esse problema, selecione o espaço e, em seguida, selecione **remover**. Depois de remover o espaço, o HoloLens começa a mapear seus arredores e criar um novo espaço.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Meu HoloLens não pode saber em que espaço estou

Se o seu HoloLens não conseguir identificar e carregar o espaço que você está automaticamente, verifique os seguintes fatores:

- Verifique se você está conectado a Wi-Fi
- Certifique-se de que há muita luz na sala
- Certifique-se de que não houvesse nenhuma alteração importante no ambiente.

Você também pode carregar um espaço manualmente ou gerenciar seus espaços acessando **configurações**  >    >  **espaços** do sistema.

## <a name="im-getting-a-low-disk-space-error"></a>Estou recebendo um erro de "pouco espaço em disco"

Você precisará liberar espaço de armazenamento seguindo um ou mais destes procedimentos:

- Exclua alguns espaços não utilizados. Acesse **configurações**  >    >  **espaços** do sistema, selecione um espaço que você não precisa mais e, em seguida, selecione **remover**.
- Remova alguns dos hologramas que você colocou.
- Exclua algumas imagens e vídeos do aplicativo fotos.
- Desinstale alguns aplicativos do seu HoloLens. Na lista **todos os aplicativos** , toque e mantenha o aplicativo que você deseja desinstalar e, em seguida, selecione **desinstalar**.

## <a name="my-hololens-cant-create-a-new-space"></a>Meu HoloLens não pode criar um novo espaço

O problema mais provável é que você está ficando com pouco espaço de armazenamento. Tente uma das [dicas anteriores](#im-getting-a-low-disk-space-error) para liberar espaço em disco.

## <a name="the-hololens-emulator-isnt-working"></a>O emulador do HoloLens não está funcionando

As informações sobre o emulador do HoloLens estão localizadas em nossa documentação do desenvolvedor.  Leia mais sobre como [solucionar problemas do emulador do HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
