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
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397257"
---
# <a name="troubleshoot-common-issues"></a>Solução de problemas comuns

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
 
1. Grave e um [Captura de Realidade Misturada vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) do problema. Este vídeo pode ser carregado posteriormente por meio do Hub de Comentários como um arquivo anexado.  
1. Habilita a  telemetria completa por meio do aplicativo Configurações -> **de** Diagnóstico de Privacidade & comentários e, em Dados de diagnóstico  ->   **opcionais,** verifique se a alternância está definida como **Ativado**
1. Obter as correções mais recentes de escala e estabilidade do holograma atualizando para o sistema operacional [Windows Holographic mais recente, (20H2 ou superior).](hololens-release-notes.md#windows-holographic-version-20h2) Após a atualização, execute o seguinte:
    1. Remova todos os hologramas por meio do aplicativo **Settings** ->  ->  **System Holograms** -> selecione Remover todos **os hologramas** e comece com um mapa novo.
    1. Crie um novo mapa do seu espaço usando o HoloLens e passeando em sua sala e observando todas as áreas e superfícies no espaço. Faça isso por 2 a 3 minutos.
    1. Execute a calibragem de IPD. Vá para **Configurações**  >  **Utilitários**  >  **do Sistema**. Em **Calibragem,** selecione **Abrir Calibragem**.
    1. Teste o cenário e veja se ele ainda persiste.
1. Se a atualização não corrigir o problema, arquiva um problema [do Hub de Comentários.](hololens-feedback.md) Depois de preencher os comentários,  você poderá usar o botão Compartilhar para criar um link fácil de compartilhar que pode ser enviado ao entrar em contato com o suporte.

## <a name="hololens-doesnt-respond-to-hand-input"></a>O HoloLens não responde à entrada manual

Para garantir que o HoloLens possa ver suas mãos, você precisa mantê-las no quadro de gestos.  A Página De Realidade Misturada fornece comentários que permitem saber quando suas mãos são rastreadas.  Os comentários são diferentes em diferentes versões do HoloLens:
- No HoloLens (1ª geração), o cursor de olhar muda de um ponto para um anel
- No HoloLens 2, um cursor de ponta do dedo aparece quando sua mão está perto de um slate e um raio de mão aparece quando os slates estão mais distantes

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
- Se o espaço correto for carregado e você ainda tiver problemas, o espaço poderá estar corrompido. Para corrigir esse problema, selecione o espaço e, em seguida, **selecione Remover**. Depois de remover o espaço, o HoloLens começa a mapear seu ambiente e criar um novo espaço.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Meu HoloLens não consegue saber em qual espaço estou

Se o HoloLens não puder identificar e carregar o espaço em que você está automaticamente, verifique os seguintes fatores:

- Certifique-se de que você está conectado ao Wi-Fi
- Certifique-se de que haja muita luz na sala
- Certifique-se de que não houve nenhuma alteração importante no ambiente.

Você também pode carregar um espaço manualmente ou gerenciar seus espaços indo para **Configurações**  >  **espaços do**  >  **sistema.**

## <a name="im-getting-a-low-disk-space-error"></a>Estou recebendo um erro de "espaço em disco baixo"

Você precisará liberar algum espaço de armazenamento fazendo um ou mais dos seguintes:

- Exclua alguns espaços nãoutilados. Vá para **Configurações Espaços** do Sistema , selecione um espaço que você não precisa mais  >    >  e, em seguida, **selecione Remover**.
- Remova alguns dos hologramas que você colocou.
- Exclua algumas imagens e vídeos do aplicativo Fotos.
- Desinstale alguns aplicativos do HoloLens. Na lista **Todos os apps,** toque e mantenha o aplicativo que você deseja desinstalar e, em seguida, selecione **Desinstalar**.

## <a name="my-hololens-cant-create-a-new-space"></a>Meu HoloLens não pode criar um novo espaço

O problema mais provável é que você está ficando sem espaço de armazenamento. Experimente uma das dicas [anteriores para](#im-getting-a-low-disk-space-error) liberar algum espaço em disco.

## <a name="the-hololens-emulator-isnt-working"></a>O emulador do HoloLens não está funcionando

As informações sobre o emulador do HoloLens estão localizadas em nossa documentação do desenvolvedor.  Leia mais sobre como [solucionar problemas do emulador do HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
