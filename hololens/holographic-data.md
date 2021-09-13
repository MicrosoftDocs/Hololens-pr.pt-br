---
title: Encontrar e salvar arquivos no HoloLens
description: Saiba como usar o Explorador de Arquivos no HoloLens para abrir, exibir e gerenciar arquivos em seu dispositivo de realidade misturada.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031941"
---
# <a name="find-open-and-save-files-on-hololens"></a>Encontrar, abrir e salvar arquivos no HoloLens

Os arquivos que você cria HoloLens, incluindo fotos e vídeos, são salvos diretamente em seu HoloLens dispositivo. Veja e gerencie-os da mesma maneira que você gerenciaria arquivos Windows 10:

- Usando o Explorador de Arquivos para acessar pastas locais.
- No armazenamento de um aplicativo.
- Em uma pasta especial (como o vídeo ou a biblioteca de música).
- Usando um serviço de armazenamento que inclui um aplicativo e um selador de arquivos (como OneDrive).
- Usando um computador desktop conectado à sua HoloLens usando um cabo USB, usando o suporte a MTP (Protocolo de Transferência de Mídia).

## <a name="view-files-on-hololens-using-file-explorer"></a>Exibir arquivos em HoloLens usando Explorador de Arquivos

> Aplica-se a todos os HoloLens 2 dispositivos e HoloLens (1ª geração) Windows 10 atualização de abril de [2018 (RS4)](/windows/mixed-reality/release-notes-april-2018)para HoloLens .

Use Explorador de Arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo, incluindo objetos 3D, documentos e imagens. Acesse **Iniciar Todos os apps**   >     >  **Explorador de Arquivos** para começar.

> [!TIP]
> Se não houver arquivos listados Explorador de Arquivos, selecione **Este** Dispositivo no painel superior esquerdo.

Se você não vir nenhum arquivo no Explorador de Arquivos, o filtro "Recente" poderá estar ativo (o ícone do relógio está realçada no painel esquerdo). Para corrigir isso, selecione **o** ícone de documento Este Dispositivo no painel esquerdo (abaixo do ícone do relógio) ou abra o menu e selecione **Este Dispositivo**.

## <a name="find-and-view-your-photos-and-videos"></a>Encontrar e exibir suas fotos e vídeos

[A captura de realidade](holographic-photos-and-videos.md) misturada permite que você tire fotos e vídeos de realidade misturada HoloLens.  Essas fotos e vídeos são salvos na pasta Camera Roll do dispositivo.

Você pode acessar fotos e vídeos feitos com HoloLens:

- acessando o Roll da Câmera diretamente por meio do [aplicativo Fotos](holographic-photos-and-videos.md).
- carregando fotos e vídeos no armazenamento em nuvem sincronizando suas fotos e vídeos para OneDrive.
- usando a Captura de Realidade Misturada do [Windows Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplicativo Fotos

O aplicativo Fotos é um dos aplicativos padrão no **menu** Iniciar e vem integrado com HoloLens. Saiba mais sobre como [usar o aplicativo Fotos para exibir o conteúdo](holographic-photos-and-videos.md).

Você também pode instalar o [aplicativo OneDrive do Microsoft Store](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) para sincronizar fotos com outros dispositivos.

### <a name="onedrive-app"></a>Aplicativo do OneDrive

[OneDrive](https://onedrive.live.com/) permite que você acesse, gerencie e compartilhe suas fotos e vídeos com qualquer dispositivo e com qualquer usuário. Para acessar as fotos e vídeos capturados HoloLens, baixe o aplicativo [OneDrive do](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) Microsoft Store em seu HoloLens. Depois de baixado, abra o aplicativo OneDrive, selecione carregar **Configurações**  >  **câmera e** ativar o upload da **câmera.**

### <a name="connect-to-a-pc"></a>Conexão em um COMPUTADOR

Se o HoloLens estiver executando a atualização de abril de [2018](/windows/mixed-reality/release-notes-april-2018) do Windows 10 ou posterior, você poderá conectar o HoloLens a um computador Windows 10 usando um cabo USB para procurar fotos e vídeos no dispositivo usando MTP (protocolo de transferência de mídia). Você precisará garantir que o dispositivo seja desbloqueado para procurar arquivos se você tiver um PIN ou senha configurada em seu dispositivo.  

Se você habilitar o [Windows Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal), poderá usá-lo para procurar, recuperar e gerenciar as fotos e vídeos armazenados em seu dispositivo.

## <a name="access-files-within-an-app"></a>Acessar arquivos em um aplicativo

Se um aplicativo salvar arquivos em seu dispositivo, você poderá usar esse aplicativo para acessá-los.

### <a name="requesting-files-from-another-app"></a>Solicitando arquivos de outro aplicativo

Um aplicativo pode solicitar para salvar um arquivo ou abrir um arquivo de outro aplicativo usando [seladores de arquivo](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Pastas conhecidas

HoloLens dá suporte a várias pastas [conhecidas que](/windows/mixed-reality/app-model#known-folders) os aplicativos podem solicitar permissão para acessar.

## <a name="view-hololens-files-on-your-pc"></a>Exibir HoloLens arquivos no computador

Semelhante a outros dispositivos móveis, conecte o HoloLens ao computador desktop usando MTP (Protocolo de Transferência de Mídia) e abra o Explorador de Arquivos no computador para acessar suas bibliotecas HoloLens para facilitar a transferência.

Para ver os arquivos HoloLens em Explorador de Arquivos no computador:

1. Entre no HoloLens, conecte-o ao computador usando o cabo USB que veio com o HoloLens.

1. Selecione **Abrir Dispositivo para exibir arquivos com Explorador de Arquivos** ou abra Explorador de Arquivos no computador e navegue até o dispositivo.

Para ver informações sobre seu HoloLens, clique com o botão direito do mouse no nome do dispositivo Explorador de Arquivos no computador e selecione **Propriedades**.

> [!NOTE]
> HoloLens (1ª geração) não dá suporte à conexão a discos rígidos externos ou cartões SD.

## <a name="sync-to-the-cloud"></a>Sincronizar com a nuvem

Para sincronizar fotos e outros arquivos do seu HoloLens para a nuvem, instale e OneDrive no HoloLens. Para obter OneDrive, pesquise-o no Microsoft Store em seu HoloLens.

HoloLens faz o back-up de arquivos e dados do aplicativo, portanto, é uma boa ideia salvar suas coisas importantes para OneDrive. Dessa forma, se você redefinir seu dispositivo ou desinstalar um aplicativo, suas informações terão o backup feito.
