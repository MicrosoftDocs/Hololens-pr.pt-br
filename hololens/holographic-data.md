---
title: Localizar e salvar arquivos no HoloLens
description: Saiba como usar o explorador de arquivos no HoloLens para abrir, exibir e gerenciar arquivos em seu dispositivo de realidade misturada.
keywords: como fazer, seletor de arquivos, arquivos, fotos, vídeos, imagens, OneDrive, armazenamento, explorador de arquivos, hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308059"
---
# <a name="find-open-and-save-files-on-hololens"></a>Localizar, abrir e salvar arquivos no HoloLens

Os arquivos criados no HoloLens, incluindo fotos e vídeos, são salvos diretamente no seu dispositivo de HoloLens. Exiba e gerencie-os da mesma maneira que você gerenciaria arquivos no Windows 10:

- Usando o aplicativo explorador de arquivos para acessar pastas locais.
- No armazenamento de um aplicativo.
- Em uma pasta especial (como a biblioteca de vídeo ou música).
- Usando um serviço de armazenamento que inclui um seletor de aplicativo e de arquivo (como o OneDrive).
- Usando um computador desktop conectado ao seu HoloLens usando um cabo USB, usando o suporte MTP (protocolo de transferência de mídia).

## <a name="view-files-on-hololens-using-file-explorer"></a>Exibir arquivos no HoloLens usando o explorador de arquivos

> Aplica-se a todos os dispositivos de HoloLens 2 e HoloLens (1ª gen) a partir da [atualização de abril de 2018 do Windows (RS4) para o HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Use o explorador de arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo, incluindo objetos 3D, documentos e imagens. Vá para **Iniciar**   >  **todos os aplicativos**   >  **Explorador de arquivos** para começar.

> [!TIP]
> Se não houver arquivos listados no explorador de arquivos, selecione **este dispositivo** no painel superior esquerdo.

Se você não vir nenhum arquivo no explorador de arquivos, o filtro "recente" pode estar ativo (o ícone de relógio é realçado no painel esquerdo). Para corrigir isso, selecione o ícone este documento de **dispositivo** no painel esquerdo (abaixo do ícone de relógio) ou abra o menu e selecione **este dispositivo**.

## <a name="find-and-view-your-photos-and-videos"></a>Encontre e exiba suas fotos e vídeos

A [captura de realidade misturada](holographic-photos-and-videos.md) permite que você faça fotos e vídeos de realidade misturados no HoloLens.  Essas fotos e vídeos são salvos na pasta de rolagem da câmera do dispositivo.

Você pode acessar fotos e vídeos obtidos com o HoloLens por:

- acessar o rolo da câmera diretamente por meio do [aplicativo photos](holographic-photos-and-videos.md).
- carregando fotos e vídeos no armazenamento em nuvem sincronizando suas fotos e vídeos no OneDrive.
- usando a página de captura da realidade misturada do [portal de dispositivo do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplicativo Fotos

O aplicativo de fotos é um dos aplicativos padrão no menu **Iniciar** e vem interno com o HoloLens. Saiba mais sobre como [usar o aplicativo de fotos para exibir o conteúdo](holographic-photos-and-videos.md).

Você também pode instalar o [aplicativo onedrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) do Microsoft Store para sincronizar fotos com outros dispositivos.

### <a name="onedrive-app"></a>Aplicativo do OneDrive

O [onedrive](https://onedrive.live.com/) permite que você acesse, gerencie e compartilhe suas fotos e vídeos com qualquer dispositivo e com qualquer usuário. Para acessar as fotos e os vídeos capturados no HoloLens, baixe o [aplicativo onedrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) do Microsoft Store no seu HoloLens. Depois de baixado, abra o aplicativo do onedrive e selecione **configurações**  >  **carregamento da câmera** e ative o **carregamento da câmera**.

### <a name="connect-to-a-pc"></a>Conectar-se a um PC

Se o seu HoloLens estiver executando a [atualização do Windows 10 de abril de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou posterior, você poderá conectar seu hololens a um computador com Windows 10 usando um cabo USB para procurar fotos e vídeos no dispositivo usando MTP (protocolo de transferência de mídia). Você precisará certificar-se de que o dispositivo está desbloqueado para procurar arquivos se você tiver um PIN ou senha configurada em seu dispositivo.  

Se você tiver habilitado o [portal do dispositivo Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), poderá usá-lo para procurar, recuperar e gerenciar fotos e vídeos armazenados em seu dispositivo.

## <a name="access-files-within-an-app"></a>Acessar arquivos em um aplicativo

Se um aplicativo salvar arquivos em seu dispositivo, você poderá usar esse aplicativo para acessá-los.

### <a name="requesting-files-from-another-app"></a>Solicitando arquivos de outro aplicativo

Um aplicativo pode solicitar para salvar um arquivo ou abrir um arquivo de outro aplicativo usando os [seletores de arquivos](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Pastas conhecidas

O HoloLens dá suporte a várias [pastas conhecidas](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) que os aplicativos podem solicitar permissão para acessar.

## <a name="view-hololens-files-on-your-pc"></a>Exibir arquivos do HoloLens em seu PC

Semelhante a outros dispositivos móveis, conecte o HoloLens ao seu PC desktop usando o MTP (protocolo de transferência de mídia) e abra o explorador de arquivos no PC para acessar suas bibliotecas de HoloLens para facilitar a transferência.

Para ver seus arquivos do HoloLens no explorador de arquivos em seu computador:

1. Entre no HoloLens e, em seguida, conecte-o ao computador usando o cabo USB que veio com o HoloLens.

1. Selecione **abrir dispositivo para exibir arquivos com o explorador de arquivos** ou abra o explorador de arquivos no computador e navegue até o dispositivo.

Para ver informações sobre seu HoloLens, clique com o botão direito do mouse no nome do dispositivo no explorador de arquivos em seu computador e selecione **Propriedades**.

> [!NOTE]
> O HoloLens (1º gen) não oferece suporte à conexão com discos rígidos externos ou cartões SD.

## <a name="sync-to-the-cloud"></a>Sincronizar com a nuvem

Para sincronizar fotos e outros arquivos de seu HoloLens para a nuvem, instale e configure o OneDrive no HoloLens. Para obter o OneDrive, pesquise por ele no Microsoft Store em seu HoloLens.

O HoloLens não faz backup de arquivos e dados do aplicativo, portanto, é uma boa ideia salvar suas coisas importantes no OneDrive. Dessa forma, se você redefinir o dispositivo ou desinstalar um aplicativo, suas informações serão submetidas a backup.
