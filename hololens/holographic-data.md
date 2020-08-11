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
# <span data-ttu-id="1d772-104">Encontrar, abrir e salvar arquivos no HoloLens</span><span class="sxs-lookup"><span data-stu-id="1d772-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="1d772-105">Os arquivos criados no HoloLens, incluindo fotos e vídeos, são salvos diretamente no seu dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d772-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="1d772-106">Exiba e gerencie-os da mesma maneira que você gerencia arquivos no Windows 10:</span><span class="sxs-lookup"><span data-stu-id="1d772-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="1d772-107">Usar o aplicativo explorador de arquivos para acessar pastas locais.</span><span class="sxs-lookup"><span data-stu-id="1d772-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="1d772-108">No armazenamento de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1d772-108">Within an app's storage.</span></span>
- <span data-ttu-id="1d772-109">Em uma pasta especial (como a biblioteca de vídeo ou de música).</span><span class="sxs-lookup"><span data-stu-id="1d772-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="1d772-110">Usar um serviço de armazenamento que inclui um aplicativo e um seletor de arquivos (como o OneDrive).</span><span class="sxs-lookup"><span data-stu-id="1d772-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="1d772-111">Usando um computador desktop conectado ao seu HoloLens usando um cabo USB, o uso do suporte a MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="1d772-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="1d772-112">Exibir arquivos no HoloLens usando o explorador de arquivos</span><span class="sxs-lookup"><span data-stu-id="1d772-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="1d772-113">Aplica-se a todos os dispositivos HoloLens 2 e HoloLens (1ª gen) a partir da [atualização do Windows 10 de abril de 2018 (RS4) para o HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="1d772-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="1d772-114">Use o explorador de arquivos no HoloLens para exibir e gerenciar arquivos em seu dispositivo, incluindo objetos 3D, documentos e imagens.</span><span class="sxs-lookup"><span data-stu-id="1d772-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="1d772-115">Vá para **Iniciar**   >  **todos os aplicativos**do   >  **Explorador de arquivos** para começar.</span><span class="sxs-lookup"><span data-stu-id="1d772-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="1d772-116">Se não houver arquivos listados no explorador de arquivos, selecione **este dispositivo** no painel superior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="1d772-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="1d772-117">Se você não vir nenhum arquivo no explorador de arquivos, o filtro "recentes" pode estar ativo (o ícone de relógio é realçado no painel esquerdo).</span><span class="sxs-lookup"><span data-stu-id="1d772-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="1d772-118">Para corrigir o problema, selecione o ícone do documento do **dispositivo** no painel esquerdo (abaixo do ícone do relógio) ou abra o menu e selecione **este dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1d772-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="1d772-119">Localizar e exibir suas fotos e vídeos</span><span class="sxs-lookup"><span data-stu-id="1d772-119">Find and view your photos and videos</span></span>

<span data-ttu-id="1d772-120">A [captura de realidade mista](holographic-photos-and-videos.md) permite que você faça fotos e vídeos de realidade misturados no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d772-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="1d772-121">Essas fotos e vídeos são salvos na pasta de rolagem da câmera do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d772-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="1d772-122">Você pode acessar fotos e vídeos tirados com o HoloLens por:</span><span class="sxs-lookup"><span data-stu-id="1d772-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="1d772-123">Acessando a rolagem da câmera diretamente por meio do [aplicativo fotos](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="1d772-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="1d772-124">carregar fotos e vídeos para armazenamento na nuvem ao sincronizar suas fotos e vídeos com o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1d772-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="1d772-125">usando a página de captura da realidade misturada do [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="1d772-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="1d772-126">Aplicativo Fotos</span><span class="sxs-lookup"><span data-stu-id="1d772-126">Photos app</span></span>

<span data-ttu-id="1d772-127">O aplicativo fotos é um dos aplicativos padrão no menu **Iniciar** e vem embutido com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d772-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="1d772-128">Saiba mais sobre como [usar o aplicativo fotos para exibir o conteúdo](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="1d772-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="1d772-129">Você também pode instalar o [aplicativo onedrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) na Microsoft Store para sincronizar fotos com outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1d772-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="1d772-130">Aplicativo do OneDrive</span><span class="sxs-lookup"><span data-stu-id="1d772-130">OneDrive app</span></span>

<span data-ttu-id="1d772-131">O [onedrive](https://onedrive.live.com/) permite que você acesse, gerencie e compartilhe suas fotos e vídeos com qualquer dispositivo e com qualquer usuário.</span><span class="sxs-lookup"><span data-stu-id="1d772-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="1d772-132">Para acessar as fotos e os vídeos capturados no HoloLens, baixe o [aplicativo onedrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da Microsoft Store no seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d772-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="1d772-133">Depois de baixar, abra o aplicativo onedrive e selecione **configurações**  >  **carregamento de câmera**e ative o **carregamento da câmera**.</span><span class="sxs-lookup"><span data-stu-id="1d772-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="1d772-134">Conectar-se a um PC</span><span class="sxs-lookup"><span data-stu-id="1d772-134">Connect to a PC</span></span>

<span data-ttu-id="1d772-135">Se o seu HoloLens estiver executando a [atualização do Windows 10 abril de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ou posterior, você poderá conectar seu HoloLens a um computador com o Windows 10 usando um cabo USB para procurar fotos e vídeos no dispositivo usando MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="1d772-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="1d772-136">Você precisará verificar se o dispositivo está desbloqueado para procurar arquivos se tiver um PIN ou senha configurados em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d772-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="1d772-137">Se você tiver habilitado o [Windows Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), poderá usá-lo para procurar, recuperar e gerenciar as fotos e os vídeos armazenados no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d772-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="1d772-138">Acessar arquivos em um aplicativo</span><span class="sxs-lookup"><span data-stu-id="1d772-138">Access files within an app</span></span>

<span data-ttu-id="1d772-139">Se um aplicativo salva arquivos em seu dispositivo, você pode usar esse aplicativo para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="1d772-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="1d772-140">Solicitando arquivos de outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="1d772-140">Requesting files from another app</span></span>

<span data-ttu-id="1d772-141">Um aplicativo pode solicitar o salvamento de um arquivo ou abrir um arquivo de outro aplicativo usando [seletores de arquivos](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="1d772-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="1d772-142">Pastas conhecidas</span><span class="sxs-lookup"><span data-stu-id="1d772-142">Known folders</span></span>

<span data-ttu-id="1d772-143">O HoloLens oferece suporte a várias [pastas conhecidas](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) que os aplicativos podem solicitar permissão para acessar.</span><span class="sxs-lookup"><span data-stu-id="1d772-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="1d772-144">Exibir arquivos HoloLens em seu PC</span><span class="sxs-lookup"><span data-stu-id="1d772-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="1d772-145">Semelhante a outros dispositivos móveis, conecte o HoloLens ao seu computador desktop usando o MTP (protocolo de transferência de mídia) e abra o explorador de arquivos no computador para acessar suas bibliotecas do HoloLens e facilitar a transferência.</span><span class="sxs-lookup"><span data-stu-id="1d772-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="1d772-146">Para ver seus arquivos do HoloLens no explorador de arquivos em seu PC:</span><span class="sxs-lookup"><span data-stu-id="1d772-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="1d772-147">Entre no HoloLens e conecte-o ao PC usando o cabo USB que veio com o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d772-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="1d772-148">Selecione **abrir dispositivo para exibir arquivos com o explorador de arquivos**ou abra o explorador de arquivos no computador e navegue até o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d772-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="1d772-149">Para ver informações sobre seu HoloLens, clique com o botão direito do mouse no nome do dispositivo no explorador de arquivos em seu computador e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1d772-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d772-150">HoloLens (1ª gen) não suporta conexão a discos rígidos externos ou cartões SD.</span><span class="sxs-lookup"><span data-stu-id="1d772-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="1d772-151">Sincronizar com a nuvem</span><span class="sxs-lookup"><span data-stu-id="1d772-151">Sync to the cloud</span></span>

<span data-ttu-id="1d772-152">Para sincronizar fotos e outros arquivos de seu HoloLens para a nuvem, instale e configure o OneDrive no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d772-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="1d772-153">Para obter o OneDrive, procure-o na Microsoft Store em seu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1d772-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="1d772-154">O HoloLens não faz backup dos arquivos e dos dados do aplicativo, portanto, é uma boa ideia salvar seu conteúdo importante no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1d772-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="1d772-155">Dessa forma, se você reinicializar o dispositivo ou desinstalar um aplicativo, será feito o backup das suas informações.</span><span class="sxs-lookup"><span data-stu-id="1d772-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
