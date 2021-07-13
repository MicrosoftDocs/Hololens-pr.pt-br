---
title: Capturar, registrar e compartilhar fotos e vídeos de realidade misturada
description: Saiba como capturar, registrar e exibir fotos e vídeos de realidade misturada usando HoloLens de realidade misturada. Saiba como compartilhar por meio de arquivos Miracast ou coletados.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
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
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635952"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Criar fotos e vídeos de realidade misturada

HoloLens oferece aos usuários a experiência de misturar o mundo real com o mundo digital.  A MRC (Captura de Realidade Misturada) permite capturar essa experiência como uma foto ou vídeo ou compartilhar o que você vê com outras pessoas em tempo real.

A captura de realidade misturada usa um ponto de vista de primeira pessoa para que outras pessoas possam ver hologramas conforme você os vê. Para um ponto de vista de terceira pessoa, use a [exibição espectadora](/windows/mixed-reality/spectator-view). A exibição de espectador é especialmente útil para demonstrações.

Embora seja divertido compartilhar vídeos entre amigos e colegas, os vídeos também podem ajudar a ensinar outras pessoas a usar um aplicativo ou a comunicar problemas com aplicativos e experiências.

> [!NOTE]
> Se você não puder iniciar experiências de captura de realidade misturada e seu HoloLens for um dispositivo de trabalho, verifique com o administrador do sistema. O acesso à câmera pode ser restrito por meio da política da empresa.

## <a name="capture-a-mixed-reality-photo"></a>Capturar uma foto de realidade misturada

Há várias maneiras de tirar uma foto da realidade misturada no HoloLens; você pode usar botões de hardware, voz ou o menu Iniciar.

### <a name="hardware-buttons-to-take-photos"></a>Botões de hardware para tirar fotos

Para tirar uma foto rápida do modo de exibição atual, pressione os botões volume para cima e volume para baixo ao mesmo tempo.  Isso é um pouco parecido com a HoloLens de uma captura de tela ou tela de impressão.

- [Localizações de botão HoloLens 2](hololens2-hardware.md)
- [Locais de botão HoloLens (1ª geração)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Manter o **volume para cima** e os botões de **volume** para baixo por três segundos iniciarão a gravação de um vídeo em vez de tirar uma foto. Para interromper a gravação, toque nos **botões volume para cima** e volume **para** baixo simultaneamente.

### <a name="voice-commands-to-take-photos"></a>Comandos de voz para tirar fotos

Na HoloLens 2, versão 2004 (e posterior), digamos: "Take a picture".

Na HoloLens (1ª geração) ou HoloLens 2, versão 1903, diga: "Olá, Cortana, tirar uma foto".

### <a name="start-menu-to-take-photos"></a>menu Iniciar tirar fotos

Use o gesto Iniciar para ir para **Iniciar** e, em seguida, selecione o **ícone Câmera.**

Aponte a cabeça na direção do que você deseja capturar e, em seguida, [toque no ar](hololens2-basic-usage.md#touch-holograms-near-you) para tirar uma foto. Você pode continuar a tocar no ar e capturar fotos adicionais. Todas as fotos que você capturar serão salvas em seu dispositivo.

Use o gesto Iniciar novamente para encerrar a captura de fotos.  

## <a name="capture-a-mixed-reality-video"></a>Capturar um vídeo de realidade misturada

Há várias maneiras de gravar um vídeo de realidade misturada no HoloLens; você pode usar botões de hardware, voz ou o menu Iniciar.

### <a name="hardware-buttons-to-record-videos"></a>Botões de hardware para gravar vídeos

A maneira mais rápida de gravar um vídeo é pressionar e manter o **volume** para cima e os botões de **volume** para baixo simultaneamente até que uma contagem regressiva de três segundos seja iniciada. Para interromper a gravação, toque em ambos os botões simultaneamente.

> [!NOTE]
> Pressionar rapidamente os **botões para cima** e para baixo do **volume** ao mesmo tempo tirará uma foto em vez de gravar um vídeo.

### <a name="voice-to-record-videos"></a>Voz para gravar vídeos

No HoloLens 2, versão 2004 (e posterior), diga: "Iniciar gravação". Para interromper a gravação, diga "Stop recording".

No HoloLens (1ª geração) ou HoloLens 2, versão 1903, diga: "Olá, Cortana, inicie a gravação". Para interromper a gravação, diga "Olá, Cortana, pare a gravação".

### <a name="start-menu-to-record-videos"></a>menu Iniciar gravar vídeos

Use o gesto Iniciar para ir para **Iniciar** e, em seguida, selecione o **ícone Vídeo.** Aponte a cabeça na direção do que você deseja capturar e, em seguida, toque [no ar](hololens2-basic-usage.md#touch-holograms-near-you) para iniciar a gravação. Haverá uma contagem regressiva de três segundos e a gravação será iniciada.

Para interromper a gravação, use o gesto Iniciar e selecione o ícone **Vídeo realçado.** O vídeo será salvo em seu dispositivo.

> [!NOTE]
> **Aplica-se somente HoloLens (1ª geração)**  
> O [Atualização de outubro de 2018 para o Windows 10](/windows/mixed-reality/release-notes-october-2018) altera como o gesto Iniciar e o botão Windows se comportam HoloLens (1ª geração). Antes da atualização, o gesto Iniciar ou Windows pararia uma gravação de vídeo. No entanto, após a atualização, o botão  Iniciar gesto ou Windows abre o menu Iniciar (ou o **menu** ações rápidas  se você estiver em um aplicativo imersivo), do qual você pode selecionar o ícone de vídeo realçado para interromper a gravação.

## <a name="share-what-you-see-in-real-time"></a>Compartilhar o que você vê em tempo real

Você pode compartilhar o que vê no HoloLens com amigos e colegas em tempo real. Há alguns métodos disponíveis:

1. Conectar-se a um Miracast ou adaptador habilitado para uso para assistir em uma TV.
1. Usando [Windows Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal) para assistir em um COMPUTADOR
1. Usando o [Microsoft HoloLens para](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) assistir em um computador.
1. Implantar o aplicativo Assistência Remota do [Microsoft Dynamics 365,](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) que permite que os trabalhadores de linha de frente transmitem o que veem para um especialista remoto. Em seguida, o especialista remoto pode orientar o trabalho de linha de frente de forma verbal ou anotando em seu mundo.

> [!NOTE]
> Compartilhar o que você vê por meio Windows Portal de Dispositivos ou Microsoft HoloLens aplicativos de adoção de aplicativos que HoloLens estar no modo [de Desenvolvedor.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Transmitir vídeo com Miracast

Use o gesto Iniciar para ir para **Iniciar** e, em seguida, selecione o **Conexão** ícone. No seletor exibido, selecione o Miracast ou adaptador habilitado para Miracast ao qual você deseja se conectar.

Para interromper o compartilhamento, use o gesto Iniciar e selecione o ícone **Conexão** realçada. Como você estava transmitindo, nada será salvo em seu dispositivo.

> [!NOTE]
> Miracast suporte foi habilitado no HoloLens (1ª geração) começando com o [Atualização de outubro de 2018 para o Windows 10](/windows/mixed-reality/release-notes-october-2018).

### <a name="real-time-video-with-windows-device-portal"></a>Vídeo em tempo real com Windows Portal de Dispositivos

Como o compartilhamento via Windows Portal de Dispositivos requer que o modo de desenvolvedor seja habilitado no HoloLens, siga as instruções em nossa documentação do desenvolvedor para configurar o modo desenvolvedor e navegar Windows Portal de Dispositivos [.](/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens aplicativo de adoção

Como o compartilhamento por meio Microsoft HoloLens aplicativo de acompanhamento exige que o modo de desenvolvedor seja habilitado no HoloLens, siga as instruções em nossa documentação do desenvolvedor para [configurar o Modo de desenvolvedor.](/windows/mixed-reality/using-the-windows-device-portal) Em seguida, baixe [o Microsoft HoloLens de aplicativos e](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) siga as instruções dentro do aplicativo para se conectar ao seu HoloLens.

Depois que o aplicativo for definido com seu  HoloLens, selecione a opção Transmissão ao vivo no menu principal do aplicativo.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Exibir suas fotos e vídeos de realidade misturada

Fotos e vídeos de realidade misturada são salvos no "Camera Roll" do dispositivo. Você pode procurar o conteúdo dessa pasta em seu HoloLens com o aplicativo Explorador de Arquivos (navegue até **Imagens > De rolagem da Câmera**).

Você também pode exibir suas fotos e vídeos de realidade misturada no aplicativo Fotos, que é pré-instalado no HoloLens. Para fixar uma foto em seu mundo, selecione-a no aplicativo Fotos e **escolha Colocar no mundo misto.** Você pode mover a foto ao redor do mundo depois que ela foi colocada.

Para exibir e/ou salvar suas fotos e vídeos de realidade misturada [](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) em um computador conectado ao HoloLens, você pode usar o Windows Portal de Dispositivos ou o Explorador de Arquivos do [computador via MTP](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Use Explorador de Arquivos para obter suas imagens, vídeos e arquivos

Semelhante a outros dispositivos móveis, conecte seu HoloLens ao computador para abrir o Explorador de Arquivos para acessar suas bibliotecas HoloLens (fotos, vídeos, documentos) para facilitar a transferência. Esse método é fácil de usar e não requer o uso do portal do dispositivo ou do Wi-Fi.

1. Desbloqueie o dispositivo.
1. Conexão o dispositivo em um computador via USB.
1. Explorador de Arquivos deve abrir em seu computador.
1. Navegue até: este computador \\ *yourhololensname*\Internal Armazenamento\Pictures\Camera Roll
1. Copie os arquivos necessários para o computador.

Dicas:
- Se você não vir nenhum arquivo, entre em seu HoloLens para habilitar o acesso aos seus dados.
- Você pode obter outros arquivos em outras pastas, como arquivos [de diagnóstico](hololens-diagnostic-logs.md#offline-diagnostics) da pasta Documentos.
- No Explorador de Arquivos no computador, você pode selecionar Propriedades do dispositivo para ver Windows número de versão do sistema operacional holográfico (versão do firmware), número de série do dispositivo e percentual da bateria.
- Se sua organização tiver usado o MDM para desabilitar [Conectividade/AllowUSBConnection,](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) você não poderá se conectar ao seu dispositivo.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Compartilhar fotos e vídeos de realidade misturada

Antes de [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)depois de capturar uma foto ou vídeo de realidade misturada, uma versão prévia será exibida. Selecione o **ícone Compartilhar** acima da visualização para abrir o assistente de compartilhamento. A partir daí, você pode selecionar o ponto de extremidade ao qual você gostaria de compartilhar essa foto ou vídeo.

Com Windows Holographic, versão 21H1, depois de capturar uma foto ou vídeo de realidade misturada, uma versão prévia será exibida. Selecione o **ícone Compartilhar** acima da visualização para abrir o assistente de compartilhamento. A partir daí, você pode selecionar o ponto de extremidade (Email, OneDrive etc.) ao qual você gostaria de compartilhar essa foto ou vídeo. Você também pode habilitar seu HoloLens compartilhar com dispositivos próximos indo para Configurações **-> System -> Shared Experiences**. Para obter mais detalhes, leia [Compartilhar coisas com dispositivos próximos no Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

> [!TIP] 
> Você também pode compartilhar fotos e vídeos de realidade misturada OneDrive carregando automaticamente suas fotos e vídeos de realidade misturada. Abra o OneDrive no HoloLens e entre com uma conta **[conta Microsoft](https://account.microsoft.com)** pessoal , caso ainda não tenha feito isso. Selecione o ícone **Configurações** e escolha **Carregar câmera**. Ativar o upload da câmera. Suas fotos e vídeos de realidade misturada agora serão carregados OneDrive sempre que você iniciar o aplicativo HoloLens.

> [!NOTE]
> Você só poderá habilitar o upload da câmera OneDrive se estiver OneDrive com uma conta conta Microsoft. Se você configurar o HoloLens com uma conta de trabalho ou de estudante, poderá adicionar um conta Microsoft pessoal no aplicativo OneDrive para habilitar esse recurso.

## <a name="limitations-of-mixed-reality-capture"></a>Limitações da captura de realidade misturada

- Ao usar a captura de realidade misturada, a taxa de quadros HoloLens será reduzida pela metade para 30 Hz.
- A resolução de fotos e vídeos poderá ser reduzida se a câmera de foto/vídeo já estiver em uso por outro aplicativo, durante a transmissão ao vivo ou quando os recursos do sistema estão baixos.

### <a name="maximum-recording-length"></a>Comprimento máximo de gravação

Em HoloLens dois dispositivos antes do Windows Holographic, versão 20H2, os vídeos gravados no dispositivo eram limitados ao comprimento máximo de cinco minutos.

Devido aos comentários dos clientes, aumentamos o tamanho da gravação das [capturas de realidade misturada.](holographic-photos-and-videos.md) As capturas de realidade misturada não serão mais limitadas a 5 minutos por padrão, mas, em vez disso, calcularão o comprimento máximo da gravação com base no espaço em disco disponível. O dispositivo estima a duração máxima da gravação de vídeo com base no espaço em disco disponível até 80% do espaço total em disco.

> [!NOTE]
> O HoloLens usará o comprimento de gravação de vídeo padrão (5 minutos) se ocorrer um dos seguintes:
> - A duração máxima estimada da gravação é menor do que o padrão de 5 minutos.
> - O espaço em disco disponível é menor que 20% do espaço total em disco.

## <a name="default-file-format-and-resolution"></a>Resolução e formato de arquivo padrão

### <a name="default-photo-format-and-resolution"></a>Resolução e formato de foto padrão

|  Dispositivo  |  Formatar  |  Extensão  |  Resolução  |
|----------|----------|----------|----------|
| HoloLens 2 | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1ª geração) | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Resolução e formato de vídeo gravados

| Dispositivo | Formatar | Extensão | Resolução | Velocidade | Áudio |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | Estéreo de 48kHz |
| HoloLens (1ª geração) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | Estéreo de 48kHz |
