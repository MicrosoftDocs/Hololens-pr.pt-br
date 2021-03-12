---
title: Capturar, gravar e compartilhar fotos e vídeos de realidade misturada
description: Saiba como capturar, gravar e exibir, além de fotos e vídeos de realidade misturada usando dispositivos de realidade misturada do HoloLens. Saiba como compartilhar por meio do Miracast ou arquivos coletados.
keywords: hololens, foto, vídeo, captura, mrc, captura de realidade misturada, fotos, câmera, miracast, stream, livestream, demo, record
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: 047738224840013bede45dbb642a0ad2115a9c84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406705"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Criar fotos e vídeos de realidade misturada

O HoloLens oferece aos usuários a experiência de misturar o mundo real com o mundo digital.  A captura de realidade mista (MRC) permite capturar essa experiência como uma foto ou vídeo ou compartilhar o que você vê com outras pessoas em tempo real.

A captura de realidade misturada usa um ponto de vista de primeira pessoa para que outras pessoas possam ver hologramas conforme você os vê. Para um ponto de vista de terceira pessoa, use o [modo de exibição de espectador.](https://docs.microsoft.com/windows/mixed-reality/spectator-view) O modo de exibição de espectador é especialmente útil para demonstrações.

Embora seja divertido compartilhar vídeos entre amigos e colegas, os vídeos também podem ajudar a ensinar outras pessoas a usar um aplicativo ou a comunicar problemas com aplicativos e experiências.

> [!NOTE]
> Se você não puder iniciar experiências de captura de realidade misturada e o HoloLens for um dispositivo de trabalho, verifique com o administrador do sistema. O acesso à câmera pode ser restrito por meio da política da empresa.

## <a name="capture-a-mixed-reality-photo"></a>Capturar uma foto de realidade misturada

Há várias maneiras de tirar uma foto da realidade misturada no HoloLens; você pode usar botões de hardware, voz ou o menu Iniciar.

### <a name="hardware-buttons-to-take-photos"></a>Botões de hardware para tirar fotos

Para tirar uma foto rápida do modo de exibição atual, pressione os botões de volume para cima e para baixo ao mesmo tempo.  Isso é um pouco parecido com a versão do HoloLens de uma captura de tela ou de uma tela de impressão.

- [Locais de botão no HoloLens 2](hololens2-hardware.md)
- [Locais de botão no HoloLens (1ª geração)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Manter os **botões de volume para cima** e **volume** para baixo por três segundos começará a gravar um vídeo em vez de tirar uma foto. Para interromper a gravação, toque nos botões **volume para cima** e volume **para** baixo simultaneamente.

### <a name="voice-commands-to-take-photos"></a>Comandos de voz para tirar fotos

No HoloLens 2, versão 2004 (e posterior), diga: "Tire uma foto".

No HoloLens (1ª geração) ou no HoloLens 2, versão 1903, diga: "Ei Cortana, tire uma foto".

### <a name="start-menu-to-take-photos"></a>Menu Iniciar para tirar fotos

Use o gesto Iniciar para ir para **Iniciar**e, em seguida, selecione o **ícone da** câmera.

Aponte a cabeça na direção do que você deseja capturar e toque [de ar](hololens2-basic-usage.md#touch-holograms-near-you) para tirar uma foto. Você pode continuar a tocar no ar e capturar fotos adicionais. Todas as fotos que você capturar serão salvas em seu dispositivo.

Use o gesto Iniciar novamente para encerrar a captura de fotos.  

## <a name="capture-a-mixed-reality-video"></a>Capturar um vídeo de realidade misturada

Há várias maneiras de gravar um vídeo de realidade misturada no HoloLens; você pode usar botões de hardware, voz ou o menu Iniciar.

### <a name="hardware-buttons-to-record-videos"></a>Botões de hardware para gravar vídeos

A maneira mais rápida de gravar um vídeo é pressionar e segurar os botões **de volume** para cima e **para** baixo simultaneamente até que uma contagem regressiva de três segundos comece. Para interromper a gravação, toque em ambos os botões simultaneamente.

> [!NOTE]
> Pressionar rapidamente os **botões de volume para** cima e para baixo de **volume** ao mesmo tempo tirará uma foto em vez de gravar um vídeo.

### <a name="voice-to-record-videos"></a>Voz para gravar vídeos

No HoloLens 2, versão 2004 (e posterior), diga: "Iniciar gravação". Para interromper a gravação, diga "Parar a gravação".

No HoloLens (1ª geração) ou no HoloLens 2, versão 1903, diga: "Ei Cortana, comece a gravar". Para interromper a gravação, diga "Ei Cortana, pare de gravar".

### <a name="start-menu-to-record-videos"></a>Menu Iniciar para gravar vídeos

Use o gesto Iniciar para ir para **Iniciar**e, em seguida, selecione o **ícone de** vídeo. Aponte a cabeça na direção do que você deseja capturar e toque [de ar](hololens2-basic-usage.md#touch-holograms-near-you) para iniciar a gravação. Haverá uma contagem regressiva de três segundos e sua gravação começará.

Para interromper a gravação, use o gesto Iniciar e selecione o ícone de **vídeo realçado.** O vídeo será salvo em seu dispositivo.

> [!NOTE]
> **Aplica-se apenas ao HoloLens (1ª geração)**  
> A [Atualização do Windows 10 de outubro de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) altera como o gesto Iniciar e o botão do Windows se comportam no HoloLens (1ª geração). Antes da atualização, o gesto Iniciar ou o botão Windows interromperia uma gravação de vídeo. No entanto, após a atualização, o **** botão Iniciar ou o botão Iniciar do Windows abre o menu Iniciar (ou **** o **menu** ações rápidas se você estiver em um aplicativo imersivo), do qual você pode selecionar o ícone de vídeo realçado para interromper a gravação.

## <a name="share-what-you-see-in-real-time"></a>Compartilhar o que você vê em tempo real

Você pode compartilhar o que vê no HoloLens com amigos e colegas em tempo real. Há alguns métodos disponíveis:

1. Conectar-se a um dispositivo ou adaptador habilitado para Miracast para assistir em uma TV.
1. Usando [o Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para assistir em um computador
1. Usando o [aplicativo parceiro do Microsoft HoloLens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) para assistir em um computador.
1. Implantando o aplicativo de Assistência Remota do [Microsoft Dynamics 365,](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) que permite que os funcionários de linha de frente transmitem o que veem para um especialista remoto. O especialista remoto pode, então, orientar o trabalhador de linha de frente verbalmente ou anotando em seu mundo.

> [!NOTE]
> Compartilhar o que você vê por meio do Windows Device Portal ou do microsoft holoLens app companion exige que o HoloLens seja no modo [desenvolvedor](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).

### <a name="stream-video-with-miracast"></a>Transmitir vídeo com Miracast

Use o gesto Iniciar para ir para **Iniciar**e, em seguida, selecione o **ícone de** conexão. No seletor exibido, selecione o dispositivo ou adaptador habilitado para Miracast ao qual você deseja se conectar.

Para interromper o compartilhamento, use o gesto Iniciar e selecione o ícone de **conexão realçada.** Como você estava transmitindo, nada será salvo em seu dispositivo.

> [!NOTE]
> O suporte ao Miracast foi habilitado no HoloLens (1ª geração) a partir da Atualização do Windows 10 de outubro de [2018.](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)

### <a name="real-time-video-with-windows-device-portal"></a>Vídeo em tempo real com o Windows Device Portal

Como o compartilhamento por meio do Windows Device Portal exige que o modo de desenvolvedor seja habilitado no HoloLens, siga as instruções em nossa documentação de desenvolvedor para configurar o modo desenvolvedor e navegar [pelo Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

### <a name="microsoft-hololens-companion-app"></a>Aplicativo parceiro do Microsoft HoloLens

Como o compartilhamento por meio do aplicativo parceiro do Microsoft HoloLens exige que o modo desenvolvedor seja habilitado no HoloLens, siga as instruções em nossa documentação de desenvolvedor para [configurar o](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)modo desenvolvedor . Em seguida, baixe o aplicativo de [acompanhamento do Microsoft HoloLens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) e siga as instruções dentro do aplicativo para se conectar ao holoLens.

Depois que o aplicativo for definido com o HoloLens, selecione a opção **Live stream** no menu principal do aplicativo.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Exibir suas fotos e vídeos de realidade misturada

Fotos e vídeos de realidade misturada são salvos no "Camera Roll" do dispositivo. Você pode procurar o conteúdo dessa pasta em seu HoloLens com o aplicativo Explorador de Arquivos (navegue até Imagens > Camera Roll).

Você também pode exibir suas fotos e vídeos de realidade misturada no aplicativo Fotos, que é pré-instalado no HoloLens. Para fixar uma foto em seu mundo, selecione-a no aplicativo Fotos e escolha **Lugar no mundo misto**. Você pode mover a foto ao redor do seu mundo depois que ela foi colocada.

Para exibir e/ou salvar suas fotos e vídeos de realidade misturada em um computador conectado ao HoloLens, você pode usar o [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) ou o Explorador de Arquivos do computador por meio de [MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Usar o Explorador de Arquivos para obter suas imagens, vídeos e arquivos

Semelhante a outros dispositivos móveis, conecte seu HoloLens ao computador para trazer o Explorador de Arquivos para acessar suas bibliotecas do HoloLens (fotos, vídeos, documentos) para facilitar a transferência. Esse método é fácil de usar e não exige o uso do portal do dispositivo ou do Wi-Fi.

1. Desbloqueie o dispositivo.
1. Conecte o dispositivo a um computador via USB.
1. O Explorador de Arquivos deve abrir no computador.
1. Navegue até: este computador\\*seu nomedohololensname*\Internal Storage\Pictures\Camera Roll
1. Copie todos os arquivos necessários para o computador.

Dicas:
- Se você não vir nenhum arquivo, certifique-se de entrar no HoloLens para habilitar o acesso aos seus dados.
- Você pode obter outros arquivos em outras pastas, como arquivos [de diagnóstico da](hololens-diagnostic-logs.md#offline-diagnostics) pasta Documentos.
- No Explorador de Arquivos no computador, você pode selecionar Propriedades do dispositivo para ver o número de versão do sistema operacional holográfico do Windows (versão de firmware), o número de série do dispositivo e a porcentagem de bateria.
- Se sua organização tiver usado o MDM para desabilitar [a Conectividade/AllowUSBConnection,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) você não poderá se conectar ao seu dispositivo.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Compartilhar suas fotos e vídeos de realidade misturada

Depois de capturar uma foto ou vídeo de realidade mista, uma visualização será exibida. Selecione o **ícone de compartilhamento** acima da visualização para trazer o assistente de compartilhamento. A partir daí, você pode selecionar o ponto final para o qual você gostaria de compartilhar essa foto ou vídeo.

Você também pode compartilhar fotos e vídeos de realidade mista do OneDrive carregando automaticamente suas fotos e vídeos de realidade misturada. Abra o aplicativo do OneDrive no HoloLens e entre com uma conta pessoal da [Microsoft,](https://account.microsoft.com) caso ainda não tenha feito isso. Selecione o **ícone de configurações** e escolha **Carregar câmera**. Ativar o carregamento da câmera. Suas fotos e vídeos de realidade misturada agora serão carregados no OneDrive sempre que você iniciar o aplicativo no HoloLens.

> [!NOTE]
> Você só poderá habilitar o carregamento da câmera no OneDrive se estiver entrando no OneDrive com uma conta pessoal da Microsoft. Se você configurar o HoloLens com uma conta de trabalho ou de estudante, poderá adicionar uma conta pessoal da Microsoft no aplicativo do OneDrive para habilitar esse recurso.

## <a name="limitations-of-mixed-reality-capture"></a>Limitações da captura de realidade misturada

- Ao usar captura de realidade misturada, a taxa de quadros do HoloLens será reduzida pela metade para 30 Hz.
- A resolução de fotos e vídeos pode ser reduzida se a câmera de foto/vídeo já estiver em uso por outro aplicativo, enquanto o streaming ao vivo ou quando os recursos do sistema estão baixos.

### <a name="maximum-recording-length"></a>Comprimento máximo de gravação

Em dispositivos HoloLens 2 antes do Windows Holographic, os vídeos da versão 20H2 gravados no dispositivo eram limitados ao comprimento máximo de cinco minutos.

Devido aos comentários dos clientes, aumentamos o comprimento de gravação de [capturas de realidade misturada.](holographic-photos-and-videos.md) As capturas de realidade misturada não serão mais limitadas a 5 minutos por padrão, mas, em vez disso, calcularão o comprimento máximo de gravação com base no espaço em disco disponível. O dispositivo estima a duração máxima da gravação de vídeo com base no espaço em disco disponível até 80% do espaço total em disco.

> [!NOTE]
> O HoloLens usará o comprimento padrão de gravação de vídeo (5 minutos) se ocorrer um dos seguintes:
> - A duração máxima de gravação máxima estimada é menor do que os 5 minutos padrão.
> - O espaço em disco disponível é inferior a 20% do espaço total em disco.

## <a name="default-file-format-and-resolution"></a>Formato e resolução de arquivo padrão

### <a name="default-photo-format-and-resolution"></a>Formato e resolução de fotos padrão

|  Dispositivo  |  Formato  |  Extensão  |  Resolução  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1ª geração) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Resolução e formato de vídeo gravados

| Dispositivo | Formato | Extensão | Resolução | Velocidade | Áudio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | Estéreo de 48kHz |
| HoloLens (1ª geração) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | Estéreo de 48kHz |
