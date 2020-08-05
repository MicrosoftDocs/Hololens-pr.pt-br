---
title: Solução de problemas
description: Soluções para problemas comuns do HoloLens.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: problemas, erro, solução de problemas, correção, ajuda, suporte, HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 469848cf306675fcfb99247b5c91b159c204a5fe
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915935"
---
# Solução de problemas

Este artigo descreve como resolver vários problemas comuns do HoloLens.

## Meu HoloLens não responde ou não é iniciado

Se o seu HoloLens não iniciar:

- Se os LEDs ao lado do botão ligar não acenderem ou apenas um LED piscar, talvez seja necessário [cobrar o seu HoloLens.](hololens-recovery.md#charge-the-device)
- Se os LEDs acenderem quando você pressionar o botão de energia, mas não conseguir ver nada nos vídeos, [preform uma reinicialização forçada do dispositivo](hololens-recovery.md#hard-reset-procedure).

Se o seu HoloLens ficar congelado ou não responder:

- Para desativar o seu HoloLens, pressione o botão de energia até que todos os cinco LEDs se ativem ou por 15 segundos se os LEDs não responderem. Para iniciar seu HoloLens, pressione o botão de energia novamente.

Se essas etapas não funcionarem, você pode tentar [recuperar seu dispositivo do hololens 2](hololens-recovery.md) ou [dispositivo hololens (1ª gen).](hololens1-recovery.md)

## Os hologramas não têm uma boa aparência

Se seus hologramas estiverem instável, com salto ou não parecerem corretos, tente:

- Limpar o visor do dispositivo e a barra de sensor na frente do seu HoloLens.
- Aumentar a luz na sua sala.
- Percorrendo e examine seus arredores para que o HoloLens possa examiná-los de forma mais completa.
- Calibrando seu HoloLens para seus olhos. Vá para **configurações**  >  **System**  >  **utilitários**do sistema. Em **Calibragem**, selecione **Abrir Calibragem**.

## O HoloLens não responde à entrada à mão

Para garantir que o HoloLens possa ver suas mãos, você precisa mantê-las no quadro do gesto.  A página inicial da realidade misturada fornece comentários que permitem que você saiba quando suas mãos são rastreadas.  Os comentários são diferentes em diferentes versões do HoloLens:
- No HoloLens (1ª gen), o cursor olhar muda de um ponto para um anel
- No HoloLens 2, um cursor de ponta aparece quando a mão está perto de um Tablet, e um raio de mão é exibido quando os slates estão ainda ausentes

Muitos aplicativos imersivas seguem os padrões de entrada semelhantes à página inicial de realidade misturada.  Saiba mais sobre como usar a entrada hand no [HoloLens (1ª gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) e no [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se você estiver realçando luvas, observe que alguns tipos de luvas não funcionam com o rastreamento de mão.  Um exemplo comum é luvas de borracha pretos, que tendem a absorver luz infravermelha e não são captados pela câmera de profundidade.  Se o seu trabalho envolver luvas de borracha, recomendamos experimentar uma cor mais clara, como azul ou cinza.  Outro exemplo é grande Baggy luvas, que tendem a obscurecer a forma de sua mão. Recomendamos o uso de luvas que são mais adequados ao ajuste de forma possível para obter os melhores resultados.

Se o seu visor tiver impressões digitais ou manchas, use o pano de limpeza microfiber que veio com o HoloLens para limpar seu visor com cuidado.

## O HoloLens não responde aos meus comandos de voz

Se a Cortana não estiver respondendo aos comandos de voz, verifique se a Cortana está ativada. Na lista todos os aplicativos, selecione **Cortana**  >  as configurações do bloco de anotações do**menu**da Cortana  >  **Notebook**  >  **Settings** para fazer alterações. Para saber mais sobre o que você pode dizer, confira [Usar sua voz com o HoloLens](hololens-cortana.md).

## Não consigo colocar hologramas ou Ver os hologramas que fiz anteriormente

Se o HoloLens não conseguir mapear ou carregar seu espaço, ele entrará em modo limitado e você não poderá colocar hologramas ou Ver os hologramas que você colocou. Algumas opções para tentar:

- Certifique-se de que haja luz suficiente em seu ambiente para que o HoloLens possa ver e mapear o espaço.
- Verifique se você está conectado a uma rede Wi-Fi. Se você não estiver conectado ao Wi-Fi, o HoloLens não poderá identificar e carregar um espaço conhecido.
- Se você precisar criar um novo espaço, conecte-se a uma rede Wi-Fi e reinicie o HoloLens.
- Para ver se o espaço correto está ativo ou para carregar manualmente um espaço, vá para **configurações**espaço do  >  **sistema**  >  **Spaces**.
- Se o espaço correto estiver carregado e você ainda tiver problemas, o espaço pode estar corrompido. Para corrigir esse problema, selecione o espaço e, em seguida, selecione **remover**. Depois de remover o espaço, o HoloLens começa a mapear seus arredores e criar um novo espaço.

## Meu HoloLens não consegue saber o espaço que estou em

Se o seu HoloLens não conseguir identificar e carregar o espaço que você está fazendo automaticamente, verifique os seguintes fatores:

- Verifique se você está conectado à rede Wi-Fi
- Verifique se há muita luz na sala
- Certifique-se de que não houve nenhuma alteração importante nos arredores.

Você também pode carregar um espaço manualmente ou gerenciar seus espaços acessando **configurações**de espaços do  >  **sistema**  >  **Spaces**.

## Estou recebendo um erro de "pouco espaço em disco"

Você precisará liberar espaço de armazenamento seguindo um ou mais destes procedimentos:

- Exclua alguns espaços não utilizados. Vá para **configurações**  >  **System**  >  **espaço**do sistema, selecione um espaço que você não precisa mais e, em seguida, selecione **remover**.
- Remova alguns dos hologramas que você colocou.
- Exclua algumas imagens e vídeos do aplicativo fotos.
- Desinstale alguns aplicativos de seu HoloLens. Na lista **todos os aplicativos** , toque e segure o aplicativo que você deseja desinstalar e selecione **desinstalar**.

## Meu HoloLens não pode criar um novo espaço

O problema mais provável é que você está ficando sem espaço de armazenamento. Tente uma das [dicas anteriores](#im-getting-a-low-disk-space-error) para liberar espaço em disco.

## O emulador do HoloLens não está funcionando

Informações sobre o emulador do HoloLens estão localizadas na documentação do desenvolvedor.  Leia mais sobre como [solucionar problemas com o emulador do HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
