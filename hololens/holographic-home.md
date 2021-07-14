---
title: Usar o menu Iniciar e página inicial da realidade misturada
description: Aprenda a usar o menu iniciar, gerenciar e acessar aplicativos e navegar na página inicial de realidade mista em dispositivos HoloLens.
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
ms.openlocfilehash: 66271911a4692dea89b6338cc8c77a05dfcaae1d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397387"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Usar o menu Iniciar e página inicial da realidade misturada

Assim como a experiência do computador Windows começa com a área de trabalho, o Windows Holographic começa com a página inicial da realidade misturada.  Usando o menu Iniciar, você poderá abrir e posicionar janelas do aplicativo, iniciadores de aplicativos imersivos e conteúdo 3D na página inicial da realidade misturada e seu posicionamento no espaço físico será lembrado.

## <a name="use-the-start-menu"></a>Usar o menu Iniciar

No menu Iniciar do HoloLens, você abrirá aplicativos, verá informações de status importantes e acessará ferramentas como a câmera.

Onde quer que você esteja no HoloLens, sempre será possível abrir o menu Iniciar usando o **Gesto de Iniciar**.  No HoloLens (1ª geração), o gesto de Iniciar é [abrir a mão](https://support.microsoft.com/help/12644/hololens-use-gestures). Na HoloLens 2, o [gesto de Iniciar](hololens2-basic-usage.md#start-gesture) é tocar no ícone Iniciar que aparece em seu pulso.  Você também pode abrir o menu Iniciar usando sua voz dizendo "Go to Start" (Ir para Iniciar).

> [!TIP]
> Quando o menu Iniciar estiver aberto, use o gesto de Iniciar para fechá-lo ou olhe para o menu Iniciar e diga "Close" (Fechar).

Na parte superior do menu Iniciar, você verá indicadores de status para Wi-Fi, bateria, volume e um relógio. Na HoloLens 2, também há um indicador de escuta que mostra se o dispositivo está habilitado para fala e se está ouvindo comandos de voz. Na parte inferior, você encontrará os botões **Foto** e **Vídeo**, que permitem tirar fotos e gravar vídeos.  Também há um botão **Conectar**, que permite projetar o que você vê em outro dispositivo usando o Miracast.

### <a name="find-apps-on-start-menu"></a>Encontrar aplicativos no menu Iniciar

O menu Iniciar tem uma lista de **Aplicativos fixados** e uma lista de **Todos os apps**.

- A lista **Aplicativos fixados** mostra aplicativos que foram fixados. Você pode adicionar e remover aplicativos da lista **Aplicativos fixados** usando o menu de contexto que aparece quando você **escolhe e segura** um bloco de aplicativo.

- A lista **Todos os apps** mostra todos os aplicativos instalados no dispositivo.  Escolha o botão **Todos os apps** no lado direito do menu **Iniciar** para acessar a lista.

Em ambas as listas de aplicativos, use os botões **Page up** e **Page down** no lado direito do menu Iniciar para percorrer as páginas de todos os aplicativos da lista.  Ambas as listas de aplicativos são automaticamente abertas na página que foi usada pela última vez durante uma sessão de dispositivo.

> [!TIP]
> No HoloLens 2, você pode rolar pelas listas de aplicativos diretamente usando o dedo indicador. Basta tocar na lista com a ponta do dedo e arrastar para cima ou para baixo.

### <a name="open-apps-from-start-menu"></a>Abrir aplicativos no menu Iniciar

Para abrir um aplicativo da menu Iniciar, basta **escolher** um **bloco do aplicativo**. Você também pode dizer o nome de um aplicativo para abri-lo.

Quando você abre um aplicativo no menu Iniciar, ocorrerá uma das opções a seguir, dependendo de como o aplicativo foi projetado:

- Uma **janela de aplicativo** é posicionada. Em seguida, o aplicativo é carregado na janela e você poderá usá-lo como uma tela touch.
- Um **inicializador de aplicativo 3D** para um aplicativo de imersão é posicionado. Você precisa então **escolher** o inicializador para abrir o aplicativo imersivo.
- Uma janela do aplicativo é colocada e atua como um **inicializador** para um aplicativo imersivo. O aplicativo imersivo continuará a ser iniciado automaticamente.

Os inicializadores de aplicativos e as janelas do aplicativo colocados na página inicial da realidade misturada permanecerão até você decidir removê-los.  Eles oferecem um atalho conveniente no mundo para usar essas janelas do aplicativo ou para iniciar aplicativos imersivos sem precisar abri-los novamente no menu Iniciar. 

> [!NOTE]
>Assim como em um telefone, os recursos do sistema são gerenciados automaticamente no HoloLens.  Por exemplo, quando você abre um novo aplicativo imersivo, todos os outros aplicativos em execução se tornam inativos imediatamente. Não há necessidade de remover as janelas do aplicativo e os inicializadores da página inicial da realidade misturada para liberar recursos do sistema. 

## <a name="using-apps-on-hololens"></a>Uso de aplicativos no HoloLens

Os aplicativos no HoloLens podem usar o modo de exibição de janela do aplicativo ou o modo exibição imersiva. Com o modo de exibição janela do aplicativo, o aplicativo simplesmente mostra seu conteúdo em uma janela. Com o modo de exibição imersiva, um aplicativo retira você da página inicial da realidade misturada, onde poderá então exibir o conteúdo no ambiente físico à sua volta. Os aplicativos também podem optar por usar ambos os modos de exibição.

### <a name="use-app-windows"></a>Usar janelas do aplicativo

No HoloLens (1ª geração), as janelas do aplicativo são colocadas e usadas na página inicial da realidade misturada, onde você poderá [mover, redimensionar e girar](hololens1-basic-usage.md#move-resize-and-rotate-apps) como quiser. Além de usar janelas do aplicativo com foco e gesto, você também poderá usá-las com mouse e teclado conectados por Bluetooth.

No HoloLens 2, além de usar as janelas do aplicativo na página inicial da realidade misturada, você também poderá usar uma janela do aplicativo por vez em um aplicativo imersivo. Também é possível colocar uma janela do aplicativo no modo **Follow me**, onde ela permanecerá à sua frente à medida que você caminha. Quando você abrir uma janela do aplicativo enquanto estiver em um aplicativo imersivo, ela será aberta no modo **Follow me** automaticamente. Você pode [mover, redimensionar e girar](hololens2-basic-usage.md#move-resize-and-rotate-holograms) janelas do aplicativo diretamente usando suas mãos na página inicial da realidade misturada e em um aplicativo imersivo.

> [!NOTE]
>
> - Até três janelas do aplicativo podem ficar ativas em uma página inicial da realidade misturada ao mesmo tempo. Você pode abrir mais, mas apenas três permanecerão ativas.
> - Quando uma janela do aplicativo não estiver ativa, ela mostrará conteúdo que parecerá mais escuro em comparação a uma janela ativa.  Alguns simplesmente mostrarão o ícone do aplicativo em vez de qualquer conteúdo.  Para ativar uma janela inativa, bastará **escolhê-la**.
> - Cada aplicativo aberto pode ter uma janela ativa por vez, exceto o Microsoft Edge, que pode ter até três.

### <a name="close-apps"></a>Fechar aplicativos

Para fechar um aplicativo que usa uma janela do aplicativo, basta fechar a janela do aplicativo com o botão **Fechar** na barra de título.  Você também pode olhar para a janela e dizer "Close" (Fechar).

Para sair de um aplicativo que usa a exibição de imersão, use o gesto de Início para exibir o **menu Iniciar** e, em seguida, escolha o botão **Mixed reality home**.

Se um aplicativo imersivo estiver em um estado ignorado e for necessário reiniciá-lo, você poderá garantir que o aplicativo esteja completamente desligado fechando seu inicializador na página inicial da realidade misturada e então inicializando-o do menu Iniciar.

### <a name="default-app-picker"></a>Seletor de aplicativo padrão

Com o [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), ao ativar um hiperlink ou abrir um tipo de arquivo com mais de um aplicativo instalado, que seja compatível, você verá uma nova janela aberta solicitando que você escolha qual aplicativo instalado deve lidar com o arquivo ou tipo de link. Nessa janela, você também pode optar por fazer com que o aplicativo escolhido manipule o tipo de arquivo ou link "Uma vez" ou "Sempre".

![Janela do seletor de aplicativo](images/default-app-picker.png)

Se você escolher "Sempre", mas posteriormente quiser mudar qual aplicativo trata um determinado arquivo ou tipo de link, poderá redefinir os padrões salvos em **Configurações > Apps**. Role até a parte inferior da página e escolha o botão **Limpar** em "Aplicativos padrão para tipos de arquivo" e/ou "Aplicativos padrão para tipos de link". Ao contrário da configuração semelhante em computadores desktop, não é possível redefinir padrões de tipo de arquivo individuais.

### <a name="per-app-volume-control"></a>Controle de volume por aplicativo

Com o [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), os usuários podem ajustar manualmente o nível de volume de cada aplicativo. Isso permite que os usuários se concentrem melhor nos aplicativos que precisam ou se ouvir melhor ao usar vários aplicativos. Por exemplo, a necessidade de desativar o volume de um aplicativo ao chamar outra pessoa para assistência remota em outro.

Para definir o volume de um aplicativo individual, navegue até **Configurações**  -> **Sistema** -> **Som** e, em Opções avançadas de som, escolha **Volume do aplicativo e preferências do dispositivo**.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Informações relacionadas

[Encontrar, instalar e desinstalar aplicativos da Microsoft Store](holographic-store-apps.md)
