---
title: Localizar e salvar arquivos no HoloLens
description: Usar o explorador de arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo
keywords: instruções, seletor de arquivos, arquivos, fotos, vídeos, imagens, OneDrive, armazenamento, explorador de arquivos, hololens
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
ms.openlocfilehash: fb3287f0a074eddeac0c7ee2871e289b93eafcac
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919114"
---
# Encontrar, abrir e salvar arquivos no HoloLens

Os arquivos criados no HoloLens, incluindo fotos e vídeos, são salvos diretamente no seu dispositivo HoloLens. Exiba e gerencie-os da mesma maneira que você gerencia arquivos no Windows 10:

- Usar o aplicativo explorador de arquivos para acessar pastas locais.
- No armazenamento de um aplicativo.
- Em uma pasta especial (como a biblioteca de vídeo ou de música).
- Usar um serviço de armazenamento que inclui um aplicativo e um seletor de arquivos (como o OneDrive).
- Usando um computador desktop conectado ao seu HoloLens usando um cabo USB, o uso do suporte a MTP (Media Transfer Protocol).

## Exibir arquivos no HoloLens usando o explorador de arquivos

> Aplica-se a todos os dispositivos HoloLens 2 e HoloLens (1ª gen) a partir da [atualização do Windows 10 de abril de 2018 (RS4) para o HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).

Use o explorador de arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo, incluindo objetos 3D, documentos e imagens. Vá para **Iniciar**   >  **todos os aplicativos**do   >  **Explorador de arquivos** para começar.

> [!TIP]
> Se não houver arquivos listados no explorador de arquivos, selecione **este dispositivo** no painel superior esquerdo.

Se você não vir nenhum arquivo no explorador de arquivos, o filtro "recentes" pode estar ativo (o ícone de relógio é realçado no painel esquerdo). Para corrigir o problema, selecione o ícone do documento do **dispositivo** no painel esquerdo (abaixo do ícone do relógio) ou abra o menu e selecione **este dispositivo**.

## Localizar e exibir suas fotos e vídeos

A [captura de realidade mista](holographic-photos-and-videos.md) permite que você faça fotos e vídeos de realidade misturados no HoloLens.  Essas fotos e vídeos são salvos na pasta de rolagem da câmera do dispositivo.

Você pode acessar fotos e vídeos tirados com o HoloLens por:

- Acessando a rolagem da câmera diretamente por meio do [aplicativo fotos](holographic-photos-and-videos.md).
- carregar fotos e vídeos para armazenamento na nuvem ao sincronizar suas fotos e vídeos com o OneDrive.
- usando a página de captura da realidade misturada do [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### Aplicativo Fotos

O aplicativo fotos é um dos aplicativos padrão no menu **Iniciar** e vem embutido com o HoloLens. Saiba mais sobre como [usar o aplicativo fotos para exibir o conteúdo](holographic-photos-and-videos.md).

Você também pode instalar o [aplicativo onedrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) na Microsoft Store para sincronizar fotos com outros dispositivos.

### Aplicativo do OneDrive

O [onedrive](https://onedrive.live.com/) permite que você acesse, gerencie e compartilhe suas fotos e vídeos com qualquer dispositivo e com qualquer usuário. Para acessar as fotos e os vídeos capturados no HoloLens, baixe o [aplicativo onedrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store no seu HoloLens. Depois de baixar, abra o aplicativo onedrive e selecione **configurações**  >  **carregamento de câmera**e ative o **carregamento da câmera**.

### Conectar-se a um PC

Se o seu HoloLens estiver executando a [atualização do Windows 10 abril de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou posterior, você poderá conectar seu HoloLens a um computador com o Windows 10 usando um cabo USB para procurar fotos e vídeos no dispositivo usando MTP (Media Transfer Protocol). Você precisará verificar se o dispositivo está desbloqueado para procurar arquivos se tiver um PIN ou senha configurados em seu dispositivo.  

Se você tiver habilitado o [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), poderá usá-lo para procurar, recuperar e gerenciar as fotos e os vídeos armazenados no seu dispositivo.

## Acessar arquivos em um aplicativo

Se um aplicativo salva arquivos em seu dispositivo, você pode usar esse aplicativo para acessá-los.

### Solicitando arquivos de outro aplicativo

Um aplicativo pode solicitar o salvamento de um arquivo ou abrir um arquivo de outro aplicativo usando [seletores de arquivos](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### Pastas conhecidas

O HoloLens oferece suporte a várias [pastas conhecidas](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) que os aplicativos podem solicitar permissão para acessar.

## Exibir arquivos HoloLens em seu PC

Semelhante a outros dispositivos móveis, conecte o HoloLens ao seu computador desktop usando o MTP (protocolo de transferência de mídia) e abra o explorador de arquivos no computador para acessar suas bibliotecas do HoloLens e facilitar a transferência.

Para ver seus arquivos do HoloLens no explorador de arquivos em seu PC:

1. Entre no HoloLens e conecte-o ao PC usando o cabo USB que veio com o HoloLens.

1. Selecione **abrir dispositivo para exibir arquivos com o explorador de arquivos**ou abra o explorador de arquivos no computador e navegue até o dispositivo.

Para ver informações sobre seu HoloLens, clique com o botão direito do mouse no nome do dispositivo no explorador de arquivos em seu computador e selecione **Propriedades**.

> [!NOTE]
> HoloLens (1ª gen) não suporta conexão a discos rígidos externos ou cartões SD.

## Sincronizar com a nuvem

Para sincronizar fotos e outros arquivos de seu HoloLens para a nuvem, instale e configure o OneDrive no HoloLens. Para obter o OneDrive, procure-o na Microsoft Store em seu HoloLens.

O HoloLens não faz backup dos arquivos e dos dados do aplicativo, portanto, é uma boa ideia salvar seu conteúdo importante no OneDrive. Dessa forma, se você reinicializar o dispositivo ou desinstalar um aplicativo, será feito o backup das suas informações.
