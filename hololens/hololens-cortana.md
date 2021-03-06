---
title: Usar sua voz para operar o HoloLens
description: Saiba como a Cortana pode ajudá-lo a fazer todos os tipos de coisas em seus dispositivos de realidade mista HoloLens, incluindo comandos de voz, ditado e interações de holograma.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393865"
---
# <a name="use-your-voice-to-operate-hololens"></a>Usar sua voz para operar o HoloLens

Você pode usar sua voz para fazer praticamente qualquer coisa no HoloLens, como tirar uma foto rápida ou abrir um aplicativo. Muitos comandos de voz são integrados no próprio HoloLens, enquanto outros estão disponíveis por meio da Cortana.

Este artigo ensina a controlar o HoloLens e seu mundo holográfico com sua voz e com a Cortana.

> [!NOTE]
> Só há suporte para a fala em [alguns idiomas](hololens2-language-support.md). O idioma de fala é baseado no idioma de exibição do Windows, não no idioma do teclado.  
>  
> Você pode verificar o idioma de exibição do Windows selecionando o **Configurações** > **Hora e Idioma** > **Idioma**.

## <a name="built-in-voice-commands"></a>Comandos de voz internos

Navegue pelo HoloLens mais rapidamente com estes comandos básicos. Para usá-los, habilite o Discurso durante a primeira execução do dispositivo ou em **Configurações** > **Privacidade** > **Discurso**. Você sempre pode verificar se o Discurso está habilitado examinando o status na parte superior do menu Iniciar. Para obter os melhores resultados de reconhecimento de fala, o HoloLens 2 usa os serviços baseados em nuvem da Microsoft. No entanto, você pode usar Configurações para desabilitar esse recurso. Para fazer isso, em Configurações, desative **Reconhecimento de fala online**. Depois de alterar essa configuração, o HoloLens 2 só processará os dados de voz localmente para reconhecer comandos e ditado, e a Cortana não estará disponível.

### <a name="general-speech-commands"></a>Comandos de fala gerais

Use esses comandos no Windows Mixed Reality para navegar mais rapidamente. Alguns comandos usam o cursor de foco, que você aciona dizendo "selecionar".

> [!NOTE]
> Raios manuais não são compatíveis com o HoloLens (1ª geração).

| Diga isto | Para fazer isto |
| - | - |
| "Select" | Diga "selecionar" para abrir o cursor de foco. Em seguida, vire sua cabeça para posicionar o cursor sobre o que deseja selecionar e diga "selecionar" novamente. |
| "Go to Start" |  Abrir o menu Iniciar |
| "Close"  | Fechar o menu Iniciar |
| Diga "Ir para o Início" para exibir o menu de ações rápidas e, em seguida, diga "Página inicial de realidade misturada".  | Deixe um aplicativo imersivo |
| "Hide hand ray" / "Show hand ray" | Ocultar e mostrar o raio manual |
| "What can I say?"  | Consulte comandos de fala disponíveis |

Iniciando com a versão 19041.x do HoloLens 2, você também pode usar estes comandos:

| Diga isto | Para fazer isto |
| - | - |
| "Restart device" | Exibição de uma caixa de diálogo para confirmar se você deseja reiniciar o dispositivo. Você pode dizer "Yes" para reiniciar. |
| "Shutdown device" | Exibição de uma caixa de diálogo para confirmar se você deseja desligar o dispositivo. Você pode dizer "Yes" para confirmar. |
| "Brightness up/down" | Aumente ou diminua o brilho da tela em 10%. |
| "Volume up/down" | Aumente ou diminua o volume em 10%. |
| "What's my IP address" | Exibição de uma caixa de diálogo mostrando o endereço IP atual do seu dispositivo na rede local. |
| "Take a picture" | Capture uma foto de realidade misturada do que você está vendo no momento. |
| "Take a video" | Comece a gravar um vídeo de realidade misturada. | 
| "Stop recording" | Interrompa a gravação de vídeo da realidade misturada atual se um estiver em andamento. |

### <a name="hologram-commands"></a>Comandos de holograma

Para usar estes comandos, olhe para um objeto 3D, um holograma ou uma janela de aplicativo.

| Diga isto | Para fazer isto |
| - | - |
| "Bigger" | Aumentar o item |
| "Smaller" | Torná-lo menor |
| "Face me" | Fazer com que o item vire para você |
| "Move this" | Mover o item (segue o seu olhar) |
| "Close" | Fechar o item |
| "Follow me" / "Stop following" | Fazer com que o item acompanhe você |

### <a name="see-it-say-it"></a>Veja, diga

Muitos botões e outros elementos no HoloLens também respondem à sua voz, por exemplo, **Siga-me** e **Fechar** na barra de aplicativos ou o botão **Voltar** no Edge. Para descobrir se um botão está habilitado para voz, descanse seu **cursor de foco**, **cursor de toque** ou um **raio de mão** nele por um momento. Se o botão estiver habilitado para voz, uma dica de voz será exibida.

### <a name="dictation-mode"></a>Modo de ditado

Está cansado de digitar? Alterne para o modo de ditado sempre que o teclado holográfico estiver ativo. Para começar, selecione o botão do microfone ou diga "Iniciar ditado". Para parar de ditar, selecione o botão novamente ou diga "Parar ditado". Para excluir o que você acabou de ditar, diga "Excluir isso". 

> [!NOTE]
> Para usar o modo de ditado, você precisa ter uma conexão com a Internet.

O ditado do HoloLens usa pontuação explícita, o que significa que você precisa dizer o nome da pontuação que deseja usar. Por exemplo, você pode dizer "Oi **vírgula** o que você está fazendo **ponto de interrogação**".

Aqui estão as palavras-chave de pontuação que você pode usar:

- Ponto, vírgula, ponto de interrogação, ponto de exclamação
- Nova linha/novo parágrafo
- Ponto e vírgula, dois pontos
- Abrir aspas(s), fechar aspas(s)
- Hashtag, smiley/carinha feliz, carinha triste, piscada
- Dólar, porcentagem

Às vezes pode ser útil soletrar itens como endereços de email. Por exemplo, para ditar exemplo@outlook.com, você diria "E X E M P L O arroba Outlook ponto com".

## <a name="do-more-with-cortana"></a>Faça mais com a Cortana

A Cortana pode ajudá-lo a fazer uma infinidade de coisas em seu HoloLens, mas dependendo de qual versão do Windows Holographic você está usando, os recursos podem ser diferentes. Você pode saber mais sobre os recursos atualizados da versão mais recente da Cortana aqui: [Cortana na próxima versão do Windows 10: focada em sua produtividade com segurança e privacidade aprimoradas](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

![Ei Cortana!](images/cortana-on-hololens.png)

Aqui estão alguns exemplos que você pode tentar dizer (lembre-se de dizer "Ei Cortana" primeiro).

**Hey, Cortana**...

- What can I say?
- Launch <*nome do aplicativo*>.
- What time is it?
- Show me the latest NBA scores.
- Tell me a joke.

Se estiver usando a *versão 18362.x ou anterior*, também poderá usar estes comandos:

**Hey, Cortana**...

- Increase the volume.
- Decrease the brightness.
- Shut down.
- Restart.
- Go to sleep.
- Mute.
- Move <*nome do aplicativo*> here (olhe para o local aonde deseja que o aplicativo se mova).
- Go to Start.
- Take a picture.
- Start recording. (Começa a gravar um vídeo.)
- Stop recording. (Para de gravar um vídeo.)
- How much battery do I have left?

Alguns recursos da Cortana aos quais você está acostumado do Windows no seu PC ou telefone (por exemplo, lembretes e notificações) não são compatíveis com o Microsoft HoloLens e a experiência da Cortana pode variar de uma região para outra.

### <a name="turn-cortana-off"></a>Desativar a Cortana

A Cortana estará ativada na primeira vez que você usar o HoloLens ao ativar a fala. Você pode desativá-la nas configurações da Cortana. Na lista **Todos os apps**, selecione **Cortana** > **Configurações**. Em seguida, desative a opção A Cortana pode oferecer sugestões, ideias, lembretes, alertas e muito mais.

Se a Cortana não responder ao comando "Ei Cortana," verifique se a opção fala está habilitada no menu Iniciar e vá para as configurações da Cortana e verifique se ela está ativada.
