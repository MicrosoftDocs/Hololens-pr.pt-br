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
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="79cf3-103">Instalar versões localizadas do HoloLens (1ª gen)</span><span class="sxs-lookup"><span data-stu-id="79cf3-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="79cf3-104">Para alternar para a versão em chinês ou japonês do HoloLens, você precisará usar a ferramenta de recuperação de dispositivo do Windows (WDRT) para baixar a compilação para o idioma em um computador e, em seguida, instalá-lo em seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="79cf3-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79cf3-105">Usar o WDRT para instalar as compilações em chinês ou japonês do HoloLens exclui os dados existentes, como arquivos pessoais e configurações, do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="79cf3-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="79cf3-106">Em seu computador, baixe e instale [a ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="79cf3-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="79cf3-107">Baixe o pacote para o idioma que você deseja para seu PC:  [chinês simplificado](https://aka.ms/hololensdownload-ch) ou [japonês](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="79cf3-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="79cf3-108">Quando o download for concluído, selecione o **Explorador de arquivos**  >  **downloads**.</span><span class="sxs-lookup"><span data-stu-id="79cf3-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="79cf3-109">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.</span><span class="sxs-lookup"><span data-stu-id="79cf3-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="79cf3-110">Conecte seu HoloLens ao seu PC usando o cabo micro USB fornecido com o.</span><span class="sxs-lookup"><span data-stu-id="79cf3-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="79cf3-111">(Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)</span><span class="sxs-lookup"><span data-stu-id="79cf3-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="79cf3-112">Depois que a ferramenta detectar automaticamente seu HoloLens, selecione o bloco Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="79cf3-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="79cf3-113">Na próxima tela, selecione **seleção de pacote manual**   e selecione o arquivo de instalação que reside na pasta que você descompactou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="79cf3-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="79cf3-114">(Procure um arquivo que tenha a extensão ". FFU".)</span><span class="sxs-lookup"><span data-stu-id="79cf3-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="79cf3-115">Selecione **instalar software** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="79cf3-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="79cf3-116">Depois que o Build é instalado, a instalação do HoloLens é iniciada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="79cf3-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="79cf3-117">Coloque no dispositivo e siga as instruções de instalação.</span><span class="sxs-lookup"><span data-stu-id="79cf3-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="79cf3-118">Quando terminar de configurar, vá para **configurações**  >  **atualização &**  >  **programa Windows Insider** de segurança e verifique se você está configurado para receber as versões prévias mais recentes.</span><span class="sxs-lookup"><span data-stu-id="79cf3-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="79cf3-119">Como as compilações de visualização em inglês, o programa Windows Insider mantém as versões em chinês e japonês do HoloLens atualizadas com as mais recentes versões de visualização.</span><span class="sxs-lookup"><span data-stu-id="79cf3-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="79cf3-120">Você não pode usar o aplicativo configurações para alterar o idioma do sistema entre inglês, japonês e chinês.</span><span class="sxs-lookup"><span data-stu-id="79cf3-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="79cf3-121">A atualização de uma nova compilação é a única maneira com suporte de alterar o idioma do sistema do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="79cf3-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="79cf3-122">Embora você possa usar o teclado pinyin na tela para inserir texto em chinês simplificado ou japonês, não há suporte para o uso de um teclado de hardware Bluetooth para digitar texto em chinês simplificado ou japonês no momento.</span><span class="sxs-lookup"><span data-stu-id="79cf3-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="79cf3-123">No entanto, no HoloLens chinês ou japonês, você pode continuar a usar um teclado Bluetooth para digitar em inglês (para alternar um teclado de hardware para digitar em inglês, pressione a tecla ~).</span><span class="sxs-lookup"><span data-stu-id="79cf3-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
