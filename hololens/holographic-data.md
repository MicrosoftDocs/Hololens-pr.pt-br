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
# <span data-ttu-id="aa705-104">Encontrar, abrir e salvar arquivos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="aa705-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="aa705-105">Os arquivos que você cria no HoloLens, incluindo fotos e vídeos, são salvos diretamente em seu dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa705-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="aa705-106">Exibir e gerenciá-los da mesma maneira que você gerenciaria arquivos no Windows 10:</span><span class="sxs-lookup"><span data-stu-id="aa705-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="aa705-107">Usar o aplicativo Explorador de Arquivos para acessar pastas locais.</span><span class="sxs-lookup"><span data-stu-id="aa705-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="aa705-108">Dentro do armazenamento de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aa705-108">Within an app's storage.</span></span>
- <span data-ttu-id="aa705-109">Em uma pasta especial (como o vídeo ou a biblioteca de músicas).</span><span class="sxs-lookup"><span data-stu-id="aa705-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="aa705-110">Usar um serviço de armazenamento que inclui um se picker de aplicativos e arquivos (como o OneDrive).</span><span class="sxs-lookup"><span data-stu-id="aa705-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="aa705-111">Usar um computador desktop conectado ao HoloLens usando um cabo USB, usando suporte para MTP (Protocolo de Transferência de Mídia).</span><span class="sxs-lookup"><span data-stu-id="aa705-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="aa705-112">Exibir arquivos no HoloLens usando o Explorador de Arquivos</span><span class="sxs-lookup"><span data-stu-id="aa705-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="aa705-113">Aplica-se a todos os dispositivos HoloLens 2 e HoloLens (1ª geração) a partir da Atualização de abril de [2018 (RS4) do Windows 10 para HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)</span><span class="sxs-lookup"><span data-stu-id="aa705-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="aa705-114">Use o Explorador de Arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo, incluindo objetos 3D, documentos e imagens.</span><span class="sxs-lookup"><span data-stu-id="aa705-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="aa705-115">Vá para **Iniciar Todos**   >  **os**   >  **aplicativos Explorador de** Arquivos para começar.</span><span class="sxs-lookup"><span data-stu-id="aa705-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="aa705-116">Se não houver arquivos listados no Explorador de Arquivos, selecione **Este** Dispositivo no painel superior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="aa705-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="aa705-117">Se você não vir nenhum arquivo no Explorador de Arquivos, o filtro "Recente" poderá estar ativo (o ícone de relógio está realçado no painel esquerdo).</span><span class="sxs-lookup"><span data-stu-id="aa705-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="aa705-118">Para corrigir isso, \*\*\*\* selecione o ícone de documento Este Dispositivo no painel esquerdo (abaixo do ícone de relógio) ou abra o menu e selecione **Este Dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="aa705-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="aa705-119">Encontre e veja suas fotos e vídeos</span><span class="sxs-lookup"><span data-stu-id="aa705-119">Find and view your photos and videos</span></span>

<span data-ttu-id="aa705-120">[A captura de realidade](holographic-photos-and-videos.md) misturada permite tirar fotos e vídeos de realidade misturada no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa705-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="aa705-121">Essas fotos e vídeos são salvos na pasta De rolagem da câmera do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa705-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="aa705-122">Você pode acessar fotos e vídeos feitos com o HoloLens:</span><span class="sxs-lookup"><span data-stu-id="aa705-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="aa705-123">acessar a rolagem da câmera diretamente por meio do [aplicativo Fotos.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="aa705-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="aa705-124">carregar fotos e vídeos no armazenamento na nuvem sincronizando suas fotos e vídeos com o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="aa705-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="aa705-125">usando a página Captura de Realidade Misturada do [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="aa705-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="aa705-126">Aplicativo Fotos</span><span class="sxs-lookup"><span data-stu-id="aa705-126">Photos app</span></span>

<span data-ttu-id="aa705-127">O aplicativo Fotos é um dos aplicativos padrão no **menu** Iniciar e vem integrado com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa705-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="aa705-128">Saiba mais sobre [como usar o aplicativo Fotos para exibir conteúdo.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="aa705-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="aa705-129">Você também pode instalar o [aplicativo OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store para sincronizar fotos com outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aa705-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="aa705-130">Aplicativo do OneDrive</span><span class="sxs-lookup"><span data-stu-id="aa705-130">OneDrive app</span></span>

<span data-ttu-id="aa705-131">[O OneDrive](https://onedrive.live.com/) permite que você acesse, gerencie e compartilhe suas fotos e vídeos com qualquer dispositivo e com qualquer usuário.</span><span class="sxs-lookup"><span data-stu-id="aa705-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="aa705-132">Para acessar as fotos e os vídeos capturados no HoloLens, baixe o aplicativo [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store em seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa705-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="aa705-133">Depois de baixado, abra o aplicativo oneDrive, selecione **Configurações**de carregamento da câmera e  >  \*\*\*\* acione **o carregamento da câmera.**</span><span class="sxs-lookup"><span data-stu-id="aa705-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="aa705-134">Conectar-se a um computador</span><span class="sxs-lookup"><span data-stu-id="aa705-134">Connect to a PC</span></span>

<span data-ttu-id="aa705-135">Se o HoloLens estiver executando a atualização de abril de [2018 do Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou posterior, você poderá conectar seu HoloLens a um computador Windows 10 usando um cabo USB para procurar fotos e vídeos no dispositivo usando MTP (protocolo de transferência de mídia).</span><span class="sxs-lookup"><span data-stu-id="aa705-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="aa705-136">Você precisará garantir que o dispositivo está desbloqueado para procurar arquivos se você tiver um PIN ou senha definido em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa705-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="aa705-137">Se você tiver habilitado o [Windows Device Portal,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)poderá usá-lo para procurar, recuperar e gerenciar as fotos e os vídeos armazenados em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa705-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="aa705-138">Acessar arquivos em um aplicativo</span><span class="sxs-lookup"><span data-stu-id="aa705-138">Access files within an app</span></span>

<span data-ttu-id="aa705-139">Se um aplicativo salvar arquivos no dispositivo, você poderá usá-lo para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="aa705-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="aa705-140">Solicitando arquivos de outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="aa705-140">Requesting files from another app</span></span>

<span data-ttu-id="aa705-141">Um aplicativo pode solicitar para salvar um arquivo ou abrir um arquivo de outro aplicativo usando se [pickers de arquivos.](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="aa705-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="aa705-142">Pastas conhecidas</span><span class="sxs-lookup"><span data-stu-id="aa705-142">Known folders</span></span>

<span data-ttu-id="aa705-143">O HoloLens oferece suporte a várias [pastas conhecidas que](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) os aplicativos podem solicitar permissão para acessar.</span><span class="sxs-lookup"><span data-stu-id="aa705-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="aa705-144">Exibir arquivos do HoloLens em seu computador</span><span class="sxs-lookup"><span data-stu-id="aa705-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="aa705-145">Semelhante a outros dispositivos móveis, conecte o HoloLens ao computador desktop usando MTP (Protocolo de Transferência de Mídia) e abra o Explorador de Arquivos no computador para acessar suas bibliotecas do HoloLens para facilitar a transferência.</span><span class="sxs-lookup"><span data-stu-id="aa705-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="aa705-146">Para ver seus arquivos do HoloLens no Explorador de Arquivos em seu computador:</span><span class="sxs-lookup"><span data-stu-id="aa705-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="aa705-147">Entre no HoloLens e conecte-o ao computador usando o cabo USB que veio com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa705-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="aa705-148">Selecione **Abrir Dispositivo para exibir arquivos com o Explorador**de Arquivos ou abra o Explorador de Arquivos no computador e navegue até o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa705-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="aa705-149">Para ver informações sobre o HoloLens, clique com o botão direito do mouse no nome do dispositivo no Explorador de Arquivos em seu computador e selecione **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="aa705-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="aa705-150">O HoloLens (1ª geração) não dá suporte à conexão a discos rígidos externos ou cartões SD.</span><span class="sxs-lookup"><span data-stu-id="aa705-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="aa705-151">Sincronizar com a nuvem</span><span class="sxs-lookup"><span data-stu-id="aa705-151">Sync to the cloud</span></span>

<span data-ttu-id="aa705-152">Para sincronizar fotos e outros arquivos do HoloLens com a nuvem, instale e instale o OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa705-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="aa705-153">Para obter o OneDrive, pesquise-o na Microsoft Store em seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aa705-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="aa705-154">O HoloLens não faz o back up de arquivos e dados do aplicativo, portanto, é uma boa ideia salvar suas coisas importantes no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="aa705-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="aa705-155">Dessa forma, se você redefinir o dispositivo ou desinstalar um aplicativo, será feito backup das informações.</span><span class="sxs-lookup"><span data-stu-id="aa705-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
