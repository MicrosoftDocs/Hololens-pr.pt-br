---
title: Instalar versões localizadas do HoloLens
description: Saiba como instalar as versões em chinês ou japonês do HoloLens
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9ccee2e11650926a5570967f1de5f6b341a17ae6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827779"
---
# Instalar versões localizadas do HoloLens (1ª geração)

Para mudar para a versão em chinês ou em japonês do HoloLens, você precisará usar a Windows Device Recovery Tool (WDRT) para baixar o build para o idioma em um computador e depois instalá-lo em seu HoloLens.

> [!IMPORTANT]
> O uso da WDRT para instalar os builds em chinês ou japonês do HoloLens exclui os dados existentes, como arquivos pessoais e configurações, do seu HoloLens. 

1. No computador, baixe e instale [a Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Baixe o pacote para o idioma que você deseja para seu computador: [chinês simplificado](https://aka.ms/hololensdownload-ch) ou [japonês](https://aka.ms/hololensdownload-jp).
1. Quando o download for concluído, selecione **Explorador de Arquivos** > **Downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **Extrair tudo** > **Extrair** para descompactar.
1. Conecte o HoloLens ao computador usando o cabo micro USB com o qual ele foi enviado. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).
1. Depois que a ferramenta detectar automaticamente seu HoloLens, selecione o bloco Microsoft HoloLens.
1. Na tela seguinte, escolha **Seleção manual de pacote** e escolha o arquivo de instalação que reside na pasta descompactada na etapa 4. (Procure um arquivo com a extensão ".ffu"). 
1. Selecione **Instalar software** e siga as instruções. 
1. Após a instalação do build, a instalação do HoloLens será iniciada automaticamente. Coloque o dispositivo e siga as instruções de instalação. 

Ao concluir a instalação, acesse **Configurações** > **Atualização e Segurança** > **Programa Windows Insider** e verifique se você configurou para receber as versões prévias mais recentes do build. Assim como nas versões prévias dos builds em inglês, o Programa Windows Insider mantém as versões em chinês e japonês do HoloLens atualizadas com as versões prévias mais recentes do build.

> [!NOTE]
>  
> - Você não pode usar o aplicativo Configurações para alterar o idioma do sistema entre inglês, japonês e chinês. A atualização de um novo build é a única forma com suporte para a alteração do idioma do sistema do dispositivo.
> - Embora você possa usar o teclado virtual Pinyin para inserir texto em chinês simplificado ou japonês, o uso de um teclado de hardware Bluetooth para digitar texto em chinês simplificado ou em japonês não tem suporte no momento.  No entanto, no HoloLens em chinês ou japonês, você pode continuar usando um teclado Bluetooth para digitar em inglês (para alternar um teclado de hardware para digitar em inglês, pressione a tecla ~).
