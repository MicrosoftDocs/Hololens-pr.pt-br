---
title: Encontrar e salvar arquivos no HoloLens
description: Saiba como usar o Explorador de Arquivos no HoloLens para abrir, exibir e gerenciar arquivos em seu dispositivo de realidade misturada.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283522"
---
# Encontrar, abrir e salvar arquivos no HoloLens

Os arquivos que você cria no HoloLens, incluindo fotos e vídeos, são salvos diretamente em seu dispositivo HoloLens. Exibir e gerenciá-los da mesma maneira que você gerenciaria arquivos no Windows 10:

- Usar o aplicativo Explorador de Arquivos para acessar pastas locais.
- Dentro do armazenamento de um aplicativo.
- Em uma pasta especial (como o vídeo ou a biblioteca de músicas).
- Usar um serviço de armazenamento que inclui um se picker de aplicativos e arquivos (como o OneDrive).
- Usar um computador desktop conectado ao HoloLens usando um cabo USB, usando suporte para MTP (Protocolo de Transferência de Mídia).

## Exibir arquivos no HoloLens usando o Explorador de Arquivos

> Aplica-se a todos os dispositivos HoloLens 2 e HoloLens (1ª geração) a partir da Atualização de abril de [2018 (RS4) do Windows 10 para HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)

Use o Explorador de Arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo, incluindo objetos 3D, documentos e imagens. Vá para **Iniciar Todos**   >  **os**   >  **aplicativos Explorador de** Arquivos para começar.

> [!TIP]
> Se não houver arquivos listados no Explorador de Arquivos, selecione **Este** Dispositivo no painel superior esquerdo.

Se você não vir nenhum arquivo no Explorador de Arquivos, o filtro "Recente" poderá estar ativo (o ícone de relógio está realçado no painel esquerdo). Para corrigir isso, **** selecione o ícone de documento Este Dispositivo no painel esquerdo (abaixo do ícone de relógio) ou abra o menu e selecione **Este Dispositivo.**

## Encontre e veja suas fotos e vídeos

[A captura de realidade](holographic-photos-and-videos.md) misturada permite tirar fotos e vídeos de realidade misturada no HoloLens.  Essas fotos e vídeos são salvos na pasta De rolagem da câmera do dispositivo.

Você pode acessar fotos e vídeos feitos com o HoloLens:

- acessar a rolagem da câmera diretamente por meio do [aplicativo Fotos.](holographic-photos-and-videos.md)
- carregar fotos e vídeos no armazenamento na nuvem sincronizando suas fotos e vídeos com o OneDrive.
- usando a página Captura de Realidade Misturada do [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### Aplicativo Fotos

O aplicativo Fotos é um dos aplicativos padrão no **menu** Iniciar e vem integrado com o HoloLens. Saiba mais sobre [como usar o aplicativo Fotos para exibir conteúdo.](holographic-photos-and-videos.md)

Você também pode instalar o [aplicativo OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store para sincronizar fotos com outros dispositivos.

### Aplicativo do OneDrive

[O OneDrive](https://onedrive.live.com/) permite que você acesse, gerencie e compartilhe suas fotos e vídeos com qualquer dispositivo e com qualquer usuário. Para acessar as fotos e os vídeos capturados no HoloLens, baixe o aplicativo [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store em seu HoloLens. Depois de baixado, abra o aplicativo oneDrive, selecione **Configurações**de carregamento da câmera e  >  **** acione **o carregamento da câmera.**

### Conectar-se a um computador

Se o HoloLens estiver executando a atualização de abril de [2018 do Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou posterior, você poderá conectar seu HoloLens a um computador Windows 10 usando um cabo USB para procurar fotos e vídeos no dispositivo usando MTP (protocolo de transferência de mídia). Você precisará garantir que o dispositivo está desbloqueado para procurar arquivos se você tiver um PIN ou senha definido em seu dispositivo.  

Se você tiver habilitado o [Windows Device Portal,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)poderá usá-lo para procurar, recuperar e gerenciar as fotos e os vídeos armazenados em seu dispositivo.

## Acessar arquivos em um aplicativo

Se um aplicativo salvar arquivos no dispositivo, você poderá usá-lo para acessá-los.

### Solicitando arquivos de outro aplicativo

Um aplicativo pode solicitar para salvar um arquivo ou abrir um arquivo de outro aplicativo usando se [pickers de arquivos.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)

### Pastas conhecidas

O HoloLens oferece suporte a várias [pastas conhecidas que](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) os aplicativos podem solicitar permissão para acessar.

## Exibir arquivos do HoloLens em seu computador

Semelhante a outros dispositivos móveis, conecte o HoloLens ao computador desktop usando MTP (Protocolo de Transferência de Mídia) e abra o Explorador de Arquivos no computador para acessar suas bibliotecas do HoloLens para facilitar a transferência.

Para ver seus arquivos do HoloLens no Explorador de Arquivos em seu computador:

1. Entre no HoloLens e conecte-o ao computador usando o cabo USB que veio com o HoloLens.

1. Selecione **Abrir Dispositivo para exibir arquivos com o Explorador**de Arquivos ou abra o Explorador de Arquivos no computador e navegue até o dispositivo.

Para ver informações sobre o HoloLens, clique com o botão direito do mouse no nome do dispositivo no Explorador de Arquivos em seu computador e selecione **Propriedades.**

> [!NOTE]
> O HoloLens (1ª geração) não dá suporte à conexão a discos rígidos externos ou cartões SD.

## Sincronizar com a nuvem

Para sincronizar fotos e outros arquivos do HoloLens com a nuvem, instale e instale o OneDrive no HoloLens. Para obter o OneDrive, pesquise-o na Microsoft Store em seu HoloLens.

O HoloLens não faz o back up de arquivos e dados do aplicativo, portanto, é uma boa ideia salvar suas coisas importantes no OneDrive. Dessa forma, se você redefinir o dispositivo ou desinstalar um aplicativo, será feito backup das informações.
