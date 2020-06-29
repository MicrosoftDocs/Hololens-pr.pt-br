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
# <span data-ttu-id="4d07e-103">Instalar versões localizadas do HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="4d07e-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="4d07e-104">Para mudar para a versão em chinês ou em japonês do HoloLens, você precisará usar a Windows Device Recovery Tool (WDRT) para baixar o build para o idioma em um computador e depois instalá-lo em seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4d07e-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d07e-105">O uso da WDRT para instalar os builds em chinês ou japonês do HoloLens exclui os dados existentes, como arquivos pessoais e configurações, do seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4d07e-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="4d07e-106">No computador, baixe e instale [a Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="4d07e-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="4d07e-107">Baixe o pacote para o idioma que você deseja para seu computador: [chinês simplificado](https://aka.ms/hololensdownload-ch) ou [japonês](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="4d07e-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="4d07e-108">Quando o download for concluído, selecione **Explorador de Arquivos** > **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="4d07e-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="4d07e-109">Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **Extrair tudo** > **Extrair** para descompactar.</span><span class="sxs-lookup"><span data-stu-id="4d07e-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="4d07e-110">Conecte o HoloLens ao computador usando o cabo micro USB com o qual ele foi enviado.</span><span class="sxs-lookup"><span data-stu-id="4d07e-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="4d07e-111">(Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).</span><span class="sxs-lookup"><span data-stu-id="4d07e-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="4d07e-112">Depois que a ferramenta detectar automaticamente seu HoloLens, selecione o bloco Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4d07e-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="4d07e-113">Na tela seguinte, escolha **Seleção manual de pacote** e escolha o arquivo de instalação que reside na pasta descompactada na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="4d07e-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="4d07e-114">(Procure um arquivo com a extensão ".ffu").</span><span class="sxs-lookup"><span data-stu-id="4d07e-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="4d07e-115">Selecione **Instalar software** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="4d07e-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="4d07e-116">Após a instalação do build, a instalação do HoloLens será iniciada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4d07e-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="4d07e-117">Coloque o dispositivo e siga as instruções de instalação.</span><span class="sxs-lookup"><span data-stu-id="4d07e-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="4d07e-118">Ao concluir a instalação, acesse **Configurações** > **Atualização e Segurança** > **Programa Windows Insider** e verifique se você configurou para receber as versões prévias mais recentes do build.</span><span class="sxs-lookup"><span data-stu-id="4d07e-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="4d07e-119">Assim como nas versões prévias dos builds em inglês, o Programa Windows Insider mantém as versões em chinês e japonês do HoloLens atualizadas com as versões prévias mais recentes do build.</span><span class="sxs-lookup"><span data-stu-id="4d07e-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="4d07e-120">Você não pode usar o aplicativo Configurações para alterar o idioma do sistema entre inglês, japonês e chinês.</span><span class="sxs-lookup"><span data-stu-id="4d07e-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="4d07e-121">A atualização de um novo build é a única forma com suporte para a alteração do idioma do sistema do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4d07e-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="4d07e-122">Embora você possa usar o teclado virtual Pinyin para inserir texto em chinês simplificado ou japonês, o uso de um teclado de hardware Bluetooth para digitar texto em chinês simplificado ou em japonês não tem suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="4d07e-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="4d07e-123">No entanto, no HoloLens em chinês ou japonês, você pode continuar usando um teclado Bluetooth para digitar em inglês (para alternar um teclado de hardware para digitar em inglês, pressione a tecla ~).</span><span class="sxs-lookup"><span data-stu-id="4d07e-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
