---
title: Solução de problemas
description: Mantenha-se atualizado sobre as soluções mais comuns para problemas de dispositivos HoloLens e técnicas de solução de problemas.
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
keywords: problemas, bug, solucionar problemas, corrigir, ajuda, suporte, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283042"
---
# Solução de problemas

Este artigo descreve como resolver vários problemas comuns do HoloLens.

## Meu HoloLens não responde ou não inicia

Se seu HoloLens não for iniciar:

- Se os LEDs ao lado do botão de energia não acendem ou apenas um LED pisca brevemente, talvez seja necessário carregar [o HoloLens.](hololens-recovery.md#charge-the-device)
- Se os LEDs acendem quando você pressiona o botão de energia, mas não consegue ver nada nas telas, [preforme](hololens-recovery.md#hard-reset-procedure)uma redefinição de disco rígido do dispositivo.

Se o HoloLens ficar congelado ou não responder:

- Desligue o HoloLens pressionando o botão de energia até que todos os cinco LEDs se desliguem ou por 15 segundos se os LEDs não responderem. Para iniciar o HoloLens, pressione o botão de energia novamente.

Se essas etapas não funcionarem, você pode tentar recuperar seu dispositivo [HoloLens 2](hololens-recovery.md) ou [dispositivo HoloLens (1ª geração).](hololens1-recovery.md)

## Os hologramas não são bons

Se os hologramas são instável, instável ou não parecem corretos, tente:

- Limpando o visor do dispositivo e a barra do sensor na frente do HoloLens.
- Aumentando a luz em sua sala.
- Passe o tempo e olhando para os arredores para que o HoloLens possa digitalizar mais completamente.
- Calibrar seu HoloLens para seus olhos. Vá para **Utilitários**  >  **do Sistema de**  >  **Configurações.** Em **Calibragem**, selecione **Abrir Calibragem**.
 
### Relatar problemas em que os hologramas são instável ou não parecem corretos
 
1. Grave e grave um [vídeo de Captura de Realidade](holographic-photos-and-videos.md#capture-a-mixed-reality-video) Misturada do problema. Este vídeo pode ser carregado posteriormente por meio do Hub de Feedback como um arquivo anexado.  
1. Habilitar a **** telemetria completa por meio do aplicativo Configurações -> **diagnóstico**de privacidade & comentários e em dados de diagnóstico opcionais garantem que a alternância está definida  ->  **** como **Ativado** ****
1. Obter as últimas correções de escala e estabilidade do holograma atualizando para o sistema operacional [Windows Holographic mais recente, (20H2 ou superior).](hololens-release-notes.md#windows-holographic-version-20h2) Após a atualização, execute o seguinte:
    1. Remova todos os hologramas **por** meio do aplicativo Configurações -> **hologramas**do sistema -> em seguida, selecione Remover todos os  ->  **** **hologramas** e comece com um mapa atualizado.
    1. Crie um novo mapa do seu espaço usando o HoloLens e passeando pela sala e observando todas as áreas e superfícies no espaço. Faça isso por 2 a 3 minutos.
    1. Execute a calibragem da IPD. Vá para **Utilitários**  >  **do Sistema de**  >  **Configurações.** Em **Calibragem**, selecione **Abrir Calibragem**.
    1. Teste o cenário de novo e veja se ele ainda persiste.
1. Se a atualização não corrigir o problema, arquivo um problema [do Hub de Feedback.](hololens-feedback.md) Depois de preencher os comentários, **** você pode usar o botão Compartilhar, para criar um link fácil de compartilhar que pode ser enviado ao entrar em contato com o suporte.

## O HoloLens não responde à entrada manual

Para garantir que o HoloLens possa ver suas mãos, você precisa mantê-las no quadro de gestos.  A Página Home da Realidade Misturada fornece comentários que permitem que você saiba quando suas mãos são controladas.  Os comentários são diferentes em diferentes versões do HoloLens:
- No HoloLens (1ª geração), o cursor de olhar muda de um ponto para um anel
- No HoloLens 2, um cursor da ponta do dedo aparece quando sua mão está perto de uma slate, e um raio manual aparece quando as marcas estão mais distantes

Muitos aplicativos imersivos seguem padrões de entrada semelhantes à Página Home da Realidade Misturada.  Saiba mais sobre como usar a entrada manual [no HoloLens (1ª geração)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [no HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Se você estiver usando esse tipo de coisa, observe que alguns tipos de pessoas não funcionam com o rastreamento de mãos.  Um exemplo comum é a tinta preta, que tendem a absorver a luz infravermelha e não são escolhidas pela câmera de profundidade.  Se o seu trabalho envolve um problema, recomendamos tentar uma cor mais clara, como azul ou cinza.  Outro exemplo é um grande problema, que tende a obscurecer a forma da sua mão. Recomendamos o uso de recomendáveis que sejam o mais apropriados possível para melhores resultados.

Se o visor tiver impressões digitais ou impressões digitais, use o pano de limpeza de microfibra que veio com o HoloLens para limpar seu visor com cuidado.

## O HoloLens não responde a meus comandos de voz

Se a Cortana não estiver respondendo aos seus comandos de voz, certifique-se de que a Cortana está 1. Na lista Todos os aplicativos, selecione **Configurações**do Bloco de Anotações de Menu da Cortana  >  ****  >  ****  >  **** para fazer alterações. Para saber mais sobre o que você pode dizer, confira [Usar sua voz com o HoloLens](hololens-cortana.md).

## Não consigo colocar hologramas ou ver hologramas que eu posiciono anteriormente

Se o HoloLens não puder mapear ou carregar seu espaço, ele entrará no modo Limitado e você não poderá colocar hologramas ou ver hologramas que você colocou. Algumas opções para tentar:

- Certifique-se de que haja luz suficiente em seu ambiente para que o HoloLens possa ver e mapear o espaço.
- Certifique-se de que você está conectado a uma Wi-Fi rede. Se você não estiver conectado ao Wi-Fi, o HoloLens não poderá identificar e carregar um espaço conhecido.
- Se você precisar criar um novo espaço, conecte-se ao Wi-Fi e reinicie o HoloLens.
- Para ver se o espaço correto está ativo ou para carregar manualmente um espaço, vá para **Configurações de**  >  **Espaços do**  >  **Sistema.**
- Se o espaço correto for carregado e você ainda estiver tendo problemas, o espaço poderá estar corrompido. Para corrigir esse problema, selecione o espaço e selecione **Remover.** Depois de remover o espaço, o HoloLens começa a mapear seus arredores e a criar um novo espaço.

## Meu HoloLens não consegue saber em qual espaço estou

Se seu HoloLens não puder identificar e carregar o espaço em que você está automaticamente, verifique os seguintes fatores:

- Certifique-se de que você está conectado ao Wi-Fi
- Certifique-se de que haja muita luz na sala
- Certifique-se de que não houve alterações importantes nos arredores.

Você também pode carregar um espaço manualmente ou gerenciar seus espaços indo para **Configurações de**  >  **Espaços do**  >  **Sistema.**

## Estou recebendo um erro de "pouco espaço em disco"

Você precisará liberar algum espaço de armazenamento fazendo um ou mais dos seguintes:

- Exclua alguns espaços nãoutilados. Vá para **Configurações**  >  **de Espaços do**  >  **Sistema,** selecione um espaço que você não precisa mais e selecione **Remover**.
- Remova alguns dos hologramas que você colocou.
- Exclua algumas fotos e vídeos do aplicativo Fotos.
- Desinstale alguns aplicativos de seu HoloLens. Na lista **Todos os aplicativos,** toque e segure o aplicativo que você deseja desinstalar e selecione **Desinstalar.**

## Meu HoloLens não pode criar um novo espaço

O problema mais provável é que você esteja com pouco espaço de armazenamento. Experimente uma das dicas [anteriores para](#im-getting-a-low-disk-space-error) liberar espaço em disco.

## O emulador do HoloLens não está funcionando

As informações sobre o emulador do HoloLens estão localizadas em nossa documentação de desenvolvedor.  Leia mais sobre [como solucionar problemas do emulador do HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
