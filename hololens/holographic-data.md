---
title: Localizar e salvar arquivos no HoloLens
description: saiba como usar o explorador de arquivos no HoloLens para abrir, exibir e gerenciar arquivos em seu dispositivo de realidade misturada.
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
ms.openlocfilehash: ad210c9d31d8d7c226345618b6dfabf8457ee2398882935920d7b3217259a644
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664869"
---
# <a name="find-open-and-save-files-on-hololens"></a>Encontrar, abrir e salvar arquivos no HoloLens

os arquivos criados em HoloLens, incluindo fotos e vídeos, são salvos diretamente em seu dispositivo HoloLens. Exiba e gerencie-os da mesma maneira que você gerenciaria arquivos no Windows 10:

- Usando o aplicativo explorador de arquivos para acessar pastas locais.
- No armazenamento de um aplicativo.
- Em uma pasta especial (como a biblioteca de vídeo ou música).
- Usando um serviço de armazenamento que inclui um seletor de aplicativo e de arquivo (como OneDrive).
- usando um computador desktop conectado ao seu HoloLens usando um cabo USB, usando o suporte MTP (protocolo de transferência de mídia).

## <a name="view-files-on-hololens-using-file-explorer"></a>exibir arquivos no HoloLens usando o explorador de arquivos

> aplica-se a todos os dispositivos HoloLens 2 e HoloLens (1ª gen) a partir do [Windows 10 atualização de abril de 2018 (RS4) para HoloLens](/windows/mixed-reality/release-notes-april-2018).

Use o explorador de arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo, incluindo objetos 3d, documentos e imagens. Vá para **Iniciar**   >  **todos os aplicativos**   >  **Explorador de arquivos** para começar.

> [!TIP]
> Se não houver arquivos listados no explorador de arquivos, selecione **este dispositivo** no painel superior esquerdo.

Se você não vir nenhum arquivo no explorador de arquivos, o filtro "recente" pode estar ativo (o ícone de relógio é realçado no painel esquerdo). Para corrigir isso, selecione o ícone este documento de **dispositivo** no painel esquerdo (abaixo do ícone de relógio) ou abra o menu e selecione **este dispositivo**.

## <a name="find-and-view-your-photos-and-videos"></a>Encontre e exiba suas fotos e vídeos

A [captura de realidade misturada](holographic-photos-and-videos.md) permite que você faça fotos e vídeos de realidade misturados em HoloLens.  Essas fotos e vídeos são salvos na pasta de rolagem da câmera do dispositivo.

você pode acessar fotos e vídeos feitos com o HoloLens pelo:

- acessar o rolo da câmera diretamente por meio do [aplicativo photos](holographic-photos-and-videos.md).
- carregando fotos e vídeos no armazenamento em nuvem sincronizando suas fotos e vídeos para OneDrive.
- usando a página de captura da realidade misturada do [Portal do dispositivo Windows](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplicativo Fotos

O aplicativo de fotos é um dos aplicativos padrão no menu **Iniciar** e vem interno com HoloLens. Saiba mais sobre como [usar o aplicativo de fotos para exibir o conteúdo](holographic-photos-and-videos.md).

você também pode instalar o [aplicativo OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store para sincronizar fotos com outros dispositivos.

### <a name="onedrive-app"></a>Aplicativo do OneDrive

[OneDrive](https://onedrive.live.com/) permite que você acesse, gerencie e compartilhe suas fotos e vídeos com qualquer dispositivo e com qualquer usuário. para acessar as fotos e os vídeos capturados no HoloLens, baixe o [aplicativo OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) do Microsoft Store em seu HoloLens. depois de baixado, abra o aplicativo OneDrive e selecione **Configurações**  >  **carregar a câmera** e ative o **carregamento da câmera**.

### <a name="connect-to-a-pc"></a>Conexão a um PC

se sua HoloLens estiver executando a [atualização Windows 10 abril de 2018](/windows/mixed-reality/release-notes-april-2018) ou posterior, você poderá conectar seu HoloLens a um computador Windows 10 usando um cabo USB para procurar fotos e vídeos no dispositivo usando o MTP (protocolo de transferência de mídia). Você precisará certificar-se de que o dispositivo está desbloqueado para procurar arquivos se você tiver um PIN ou senha configurada em seu dispositivo.  

se você habilitou o [Windows Portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal), poderá usá-lo para procurar, recuperar e gerenciar as fotos e os vídeos armazenados em seu dispositivo.

## <a name="access-files-within-an-app"></a>Acessar arquivos em um aplicativo

Se um aplicativo salvar arquivos em seu dispositivo, você poderá usar esse aplicativo para acessá-los.

### <a name="requesting-files-from-another-app"></a>Solicitando arquivos de outro aplicativo

Um aplicativo pode solicitar para salvar um arquivo ou abrir um arquivo de outro aplicativo usando os [seletores de arquivos](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Pastas conhecidas

HoloLens dá suporte a várias [pastas conhecidas](/windows/mixed-reality/app-model#known-folders) que os aplicativos podem solicitar permissão para acessar.

## <a name="view-hololens-files-on-your-pc"></a>exibir HoloLens arquivos em seu PC

semelhante a outros dispositivos móveis, conecte HoloLens ao seu pc desktop usando o MTP (protocolo de transferência de mídia) e abra o explorador de arquivos no pc para acessar suas bibliotecas de HoloLens para facilitar a transferência.

para ver seus arquivos de HoloLens no explorador de arquivos no seu computador:

1. entre no HoloLens, em seguida, conecte-o ao PC usando o cabo USB que acompanha o HoloLens.

1. Selecione **abrir dispositivo para exibir arquivos com o explorador de arquivos** ou abra o explorador de arquivos no computador e navegue até o dispositivo.

para ver informações sobre sua HoloLens, clique com o botão direito do mouse no nome do dispositivo no explorador de arquivos em seu computador e selecione **propriedades**.

> [!NOTE]
> HoloLens (1º gen) não oferece suporte à conexão com discos rígidos externos ou cartões SD.

## <a name="sync-to-the-cloud"></a>Sincronizar com a nuvem

para sincronizar fotos e outros arquivos de seu HoloLens para a nuvem, instale e configure o OneDrive no HoloLens. para obter OneDrive, pesquise-o no Microsoft Store em seu HoloLens.

HoloLens não faz backup de arquivos e dados do aplicativo, portanto, é uma boa ideia salvar suas coisas importantes em OneDrive. Dessa forma, se você redefinir o dispositivo ou desinstalar um aplicativo, suas informações serão submetidas a backup.
