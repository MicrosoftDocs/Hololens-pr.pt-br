---
title: Instalar versões localizadas do HoloLens
description: saiba como instalar as versões localizadas do HoloLens (1ª gen), incluindo as versões em chinês e japonês.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661813"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>instalar versões localizadas do HoloLens (1ª gen)

para alternar para a versão em chinês ou japonês do HoloLens, você precisará usar a ferramenta de recuperação de dispositivo Windows (WDRT) para baixar a compilação do idioma em um computador e, em seguida, instalá-la em seu HoloLens.

> [!IMPORTANT]
> usando o WDRT para instalar as compilações em chinês ou japonês do HoloLens exclui os dados existentes, como arquivos pessoais e configurações, do seu HoloLens. 

1. no seu computador, baixe e instale [a WDRT (ferramenta de recuperação de dispositivo) do Windows](https://support.microsoft.com/help/12379).
1. Baixe o pacote para o idioma que você deseja para seu PC:  [chinês simplificado](https://aka.ms/hololensdownload-ch) ou [japonês](https://aka.ms/hololensdownload-jp).
1. Quando o download for concluído, selecione o **Explorador de arquivos**  >  **downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.
1. Conexão seu HoloLens ao seu PC usando o cabo micro USB fornecido com o. (mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)
1. depois que a ferramenta detectar automaticamente seu HoloLens, selecione o bloco Microsoft HoloLens.
1. Na próxima tela, selecione **seleção de pacote manual**   e selecione o arquivo de instalação que reside na pasta que você descompactou na etapa 4. (Procure um arquivo que tenha a extensão ". FFU".) 
1. Selecione **instalar software** e siga as instruções. 
1. depois que a compilação é instalada, HoloLens instalação é iniciada automaticamente. Coloque no dispositivo e siga as instruções de instalação. 

quando terminar a instalação, vá para **Configurações**  >  **atualização & Security**  >  **Windows programa insider** e verifique se você está configurado para receber as versões prévias mais recentes. assim como os builds de visualização em inglês, o programa insider Windows mantém as versões em chinês e japonês do HoloLens atualizadas com as compilações mais recentes da versão prévia.

> [!NOTE]
>  
> - você não pode usar o aplicativo Configurações para alterar o idioma do sistema entre inglês, japonês e chinês. A atualização de uma nova compilação é a única maneira com suporte de alterar o idioma do sistema do dispositivo.
> - embora você possa usar o teclado Pinyin na tela para inserir texto em chinês simplificado ou japonês, não há suporte para o uso de um teclado de hardware Bluetooth para digitar texto em chinês simplificado ou japonês no momento.  no entanto, no HoloLens de chinês ou japonês, você pode continuar a usar um teclado Bluetooth para digitar em inglês (para alternar um teclado de hardware para digitar em inglês, pressionar a tecla ~).
