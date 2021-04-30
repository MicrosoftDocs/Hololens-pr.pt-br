---
title: Instalar versões localizadas do HoloLens
description: Saiba como instalar as versões localizadas do HoloLens (1ª gen), incluindo as versões em chinês e japonês.
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
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308282"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalar versões localizadas do HoloLens (1ª gen)

Para alternar para a versão em chinês ou japonês do HoloLens, você precisará usar a ferramenta de recuperação de dispositivo do Windows (WDRT) para baixar a compilação para o idioma em um computador e, em seguida, instalá-lo em seu HoloLens.

> [!IMPORTANT]
> Usar o WDRT para instalar as compilações em chinês ou japonês do HoloLens exclui os dados existentes, como arquivos pessoais e configurações, do seu HoloLens. 

1. Em seu computador, baixe e instale [a ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Baixe o pacote para o idioma que você deseja para seu PC:  [chinês simplificado](https://aka.ms/hololensdownload-ch) ou [japonês](https://aka.ms/hololensdownload-jp).
1. Quando o download for concluído, selecione o **Explorador de arquivos**  >  **downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.
1. Conecte seu HoloLens ao seu PC usando o cabo micro USB fornecido com o. (Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)
1. Depois que a ferramenta detectar automaticamente seu HoloLens, selecione o bloco Microsoft HoloLens.
1. Na próxima tela, selecione **seleção de pacote manual**   e selecione o arquivo de instalação que reside na pasta que você descompactou na etapa 4. (Procure um arquivo que tenha a extensão ". FFU".) 
1. Selecione **instalar software** e siga as instruções. 
1. Depois que o Build é instalado, a instalação do HoloLens é iniciada automaticamente. Coloque no dispositivo e siga as instruções de instalação. 

Quando terminar de configurar, vá para **configurações**  >  **atualização &**  >  **programa Windows Insider** de segurança e verifique se você está configurado para receber as versões prévias mais recentes. Como as compilações de visualização em inglês, o programa Windows Insider mantém as versões em chinês e japonês do HoloLens atualizadas com as mais recentes versões de visualização.

> [!NOTE]
>  
> - Você não pode usar o aplicativo configurações para alterar o idioma do sistema entre inglês, japonês e chinês. A atualização de uma nova compilação é a única maneira com suporte de alterar o idioma do sistema do dispositivo.
> - Embora você possa usar o teclado pinyin na tela para inserir texto em chinês simplificado ou japonês, não há suporte para o uso de um teclado de hardware Bluetooth para digitar texto em chinês simplificado ou japonês no momento.  No entanto, no HoloLens chinês ou japonês, você pode continuar a usar um teclado Bluetooth para digitar em inglês (para alternar um teclado de hardware para digitar em inglês, pressione a tecla ~).
