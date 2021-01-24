---
title: Usar o Menu Iniciar e página inicial da realidade misturada
description: Aprenda a usar o menu iniciar, gerenciar e acessar aplicativos e navegar na casa de realidade mista em dispositivos HoloLens.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 26dc73b59f569496d732bcde068b3647b3857c55
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283512"
---
# Usar o Menu Iniciar e página inicial da realidade misturada

Assim como a experiência do computador Windows começa com a área de trabalho, o Windows Holographic começa com a página inicial da realidade misturada.  Usando o menu Iniciar, você poderá abrir e posicionar janelas do aplicativo, iniciadores de aplicativos imersivos e conteúdo 3D na página inicial da realidade misturada e seu posicionamento no espaço físico será lembrado.

## Usar o menu Iniciar

O menu Iniciar no HoloLens é onde você abrirá aplicativos, verá informações de status importantes e acessará ferramentas como a câmera.

Onde quer que você esteja no HoloLens, sempre será possível abrir o menu Iniciar usando o **gesto de Iniciar**.  Na HoloLens (1ª geração), o gesto de Iniciar é [abrir a mão](https://support.microsoft.com/help/12644/hololens-use-gestures). Na HoloLens 2, o [gesto de Iniciar](hololens2-basic-usage.md#start-gesture) é tocar no ícone Iniciar que aparece em seu pulso.  Você também pode abrir o menu Iniciar usando sua voz dizendo "Go to Start" (Ir para Iniciar).

> [!TIP]
> Quando o menu Iniciar estiver aberto, use o gesto de Iniciar para fechá-lo ou olhe para o menu Iniciar e diga "Close" (Fechar).

Na parte superior do menu Iniciar, você verá indicadores de status para Wi-Fi, bateria, volume e um relógio. Na HoloLens 2, também há um indicador de escuta que mostra se o dispositivo está habilitado para fala e se está ouvindo comandos de voz. Na parte inferior, você encontrará os botões **Foto** e **Vídeo**, que permitem tirar fotos e gravar vídeos.  Também há um botão **Conectar**, que permite projetar o que você vê em outro dispositivo usando o Miracast.

### Localizar aplicativos no menu Iniciar

O menu Iniciar tem uma lista **Aplicativos fixados** e uma lista **Todos os apps**.

- A lista **Aplicativos fixados** mostra os aplicativos que foram fixados. Você pode adicionar e remover aplicativos da lista **Aplicativos fixados** usando o menu de contexto que aparece quando você **seleciona e segura** o bloco de um aplicativo.

- A lista **Todos os apps** mostra todos os aplicativos instalados no dispositivo.  Selecione o botão **Todos os apps** no lado direito do menu **Iniciar** para acessar a lista.

Nas duas listas de aplicativos, use os botões **Page up** e **Page down** no lado direito do menu Iniciar para consultar todos os aplicativos na lista.  Ambas as listas de aplicativos são automaticamente abertas na página que foi usada pela última vez durante uma sessão de dispositivo.

> [!TIP]
> No HoloLens 2, você pode rolar pelas listas de aplicativos diretamente usando o dedo indicador. Basta tocar na lista com a ponta do dedo e arrastar para cima ou para baixo.

### Abrir aplicativos no menu Iniciar

Para abrir um aplicativo no menu Iniciar, basta **selecionar** um **bloco de aplicativo**. Você também pode dizer o nome de um aplicativo para abri-lo.

Quando você abre um aplicativo no menu Iniciar, ocorrerá uma das opções a seguir, dependendo de como o aplicativo foi projetado:

- Uma **janela do aplicativo** é colocada. Em seguida, o aplicativo é carregado na janela e você poderá usá-lo como uma tela touch.
- Um **inicializador de aplicativos 3D** para um aplicativo imersivo é colocado. Você precisa então **selecionar** o inicializador para abrir o aplicativo imersivo.
- Uma janela do aplicativo é colocada e atua como um **inicializador** para um aplicativo imersivo. O aplicativo imersivo continuará a ser iniciado automaticamente.

Os inicializadores de aplicativos e as janelas do aplicativo colocados na página inicial da realidade misturada permanecerão até você decidir removê-los.  Eles oferecem um atalho conveniente no mundo para usar essas janelas do aplicativo ou para iniciar aplicativos imersivos sem precisar abri-los novamente no menu Iniciar. 

> [!NOTE]
>Assim como em um telefone, os recursos do sistema são gerenciados automaticamente no HoloLens.  Por exemplo, quando você abre um novo aplicativo imersivo, todos os outros aplicativos em execução se tornam inativos imediatamente. Não há necessidade de remover as janelas do aplicativo e os inicializadores da página inicial da realidade misturada para liberar recursos do sistema. 

## Uso de aplicativos no HoloLens

Os aplicativos no HoloLens podem usar o modo de exibição de janela do aplicativo ou o modo exibição imersiva. Com o modo de exibição janela do aplicativo, o aplicativo simplesmente mostra seu conteúdo em uma janela. Com o modo de exibição imersiva, um aplicativo retira você da página inicial da realidade misturada, onde poderá então exibir o conteúdo no ambiente físico à sua volta. Os aplicativos também podem optar por usar ambos os modos de exibição.

### Usar janelas do aplicativo

No HoloLens (1ª geração), as janelas do aplicativo são colocadas e usadas na página inicial da realidade misturada, onde poderá [movê-las, redimensioná-las e girá-las](hololens1-basic-usage.md#move-resize-and-rotate-apps) como quiser. Além de usar janelas do aplicativo com foco e gesto, você também poderá usá-las com mouse e teclado conectados por Bluetooth.

No HoloLens 2, além de usar as janelas do aplicativo na página inicial da realidade misturada, você também poderá usar uma janela do aplicativo por vez em um aplicativo imersivo. Também é possível colocar uma janela do aplicativo no modo **Siga-me**, onde ela permanecerá à sua frente à medida que você caminha. Quando você abrir uma janela do aplicativo enquanto estiver em um aplicativo imersivo, ela será aberta no modo **Siga-me** automaticamente. Você pode [mover, redimensionar e girar](hololens2-basic-usage.md#move-resize-and-rotate-holograms) janelas do aplicativo diretamente usando suas mãos na página inicial da realidade misturada e em um aplicativo imersivo.

> [!NOTE]
>
> - Até três janelas do aplicativo podem ficar ativas em uma página inicial da realidade misturada ao mesmo tempo. Você pode abrir mais, mas apenas três permanecerão ativas.
> - Quando uma janela do aplicativo não estiver ativa, ela mostrará conteúdo que parecerá mais escuro em comparação a uma janela ativa.  Alguns simplesmente mostrarão o ícone do aplicativo em vez de qualquer conteúdo.  Para ativar uma janela inativa, bastará **selecioná-la**.
> - Cada aplicativo aberto pode ter uma janela ativa por vez, exceto o Microsoft Edge, que pode ter até três.

### Fechar aplicativos

Para fechar um aplicativo que usa uma janela do aplicativo, basta fechar a janela do aplicativo com o botão **Fechar** na barra de título.  Você também pode olhar para a janela e dizer "Close" (Fechar).

Para sair de um aplicativo que usa o modo de exibição imersivo, use o gesto de Iniciar para abrir o **menu Iniciar** e, em seguida, selecione o botão **Página inicial da realidade misturada**.

Se um aplicativo imersivo estiver em um estado ignorado e for necessário reiniciá-lo, você poderá garantir que o aplicativo esteja completamente desligado fechando seu inicializador na página inicial da realidade misturada e então inicializando-o do menu Iniciar.

## Informações relacionadas

[Localizar, instalar e desinstalar aplicativos da Microsoft Store](holographic-store-apps.md)
