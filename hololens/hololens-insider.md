---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar builds do Insider e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924359"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="4c9cf-103">Versão prévia do Insider para Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c9cf-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="4c9cf-104">Bem-vindo aos builds mais recentes do Insider Preview para HoloLens!</span><span class="sxs-lookup"><span data-stu-id="4c9cf-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="4c9cf-105">É simples começar e [fornecer comentários](hololens-insider.md#start-receiving-insider-builds) valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="4c9cf-106">notas Participante do Programa Windows Insider versão do Participante do Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="4c9cf-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="4c9cf-107">Estamos empolgados em iniciar o voo de novos recursos para o Windows Insiders novamente.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="4c9cf-108">Novos builds serão disponibilizados para os Canais Dev e Beta para as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="4c9cf-109">Continuaremos a atualizar essa página à medida que adicionarmos mais recursos e atualizações às nossas Participante do Programa Windows Insider builds.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="4c9cf-110">Fique animado e pronto para misturar essas atualizações em sua realidade.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="4c9cf-111">Alterações do CSP no HoloLens</span><span class="sxs-lookup"><span data-stu-id="4c9cf-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="4c9cf-112">Introduzido no Participante do Programa Windows Insider build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="4c9cf-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="4c9cf-113">CSP DevDetail</span><span class="sxs-lookup"><span data-stu-id="4c9cf-113">DevDetail CSP</span></span>

<span data-ttu-id="4c9cf-114">O CSP de DevDetail agora também relata espaço de armazenamento livre no dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="4c9cf-115">Isso deve corresponder aproximadamente ao valor mostrado na página Armazenamento do Aplicativo de Configurações.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="4c9cf-116">A seguir está o nó específico que contém essas informações.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="4c9cf-117">./DevDetail/Ext/Microsoft/FreeStorage (somente operação GET)</span><span class="sxs-lookup"><span data-stu-id="4c9cf-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="4c9cf-118">CSP DeviceStatus</span><span class="sxs-lookup"><span data-stu-id="4c9cf-118">DeviceStatus CSP</span></span>

<span data-ttu-id="4c9cf-119">O CSP do DeviceStatus agora também relata SSID e BSSID da rede Wifi com a qual o HoloLens está conectado ativamente.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="4c9cf-120">A seguir estão os nós específicos que contêm essas informações.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="4c9cf-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ mac address *of Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="4c9cf-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="4c9cf-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ mac address *of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="4c9cf-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="4c9cf-123">Exemplo de blob syncml (para fornecedores de MDM) para consultar NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="4c9cf-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="4c9cf-124">Correções e melhorias:</span><span class="sxs-lookup"><span data-stu-id="4c9cf-124">Fixes and improvements:</span></span>

- <span data-ttu-id="4c9cf-125">Corrigido um [problema conhecido para Portal de Dispositivos em que não havia nenhum prompt baixando arquivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="4c9cf-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="4c9cf-126">Corrigido um problema conhecido para o Portal de Dispositivos com tempos de carregamento e [download de arquivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="4c9cf-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="4c9cf-127">Começar a receber builds do Insider</span><span class="sxs-lookup"><span data-stu-id="4c9cf-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="4c9cf-128">Se você não tiver atualizado recentemente, reinicialize seu dispositivo para atualizar o estado e obter o build mais recente.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="4c9cf-129">O comando de voz "Reinicializar dispositivo" funciona bem.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="4c9cf-130">Você também pode escolher o botão reiniciar em Configurações/Programa Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="4c9cf-131">Temos um bug no back-end que você pode ter encontrado e isso fará com que você volte ao caminho certo.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="4c9cf-132">Em um dispositivo HoloLens 2, vá para **Configurações** Atualizar  >  **& segurança**  >  **Programa Windows Insider** e **selecione Começar.**</span><span class="sxs-lookup"><span data-stu-id="4c9cf-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="4c9cf-133">Vincule a conta usada para se registrar como um Participante do Programa Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="4c9cf-134">O Windows Insider agora está mudando para Canais.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="4c9cf-135">O **anel Rápido** se tornará o  Canal **deV,** o anel Lento  se tornará o Canal beta **e** o anel versão prévia de versão se tornará **o** Canal de Versão Prévia.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="4c9cf-136">Veja a aparência desse mapeamento: explicação Participante do Programa Windows Insider Canais para obter mais informações, consulte ![ ](images/WindowsInsiderChannels.png) Introdução Participante do Programa Windows Insider [canais](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) em blogs do Windows.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="4c9cf-137">Em seguida, selecione Desenvolvimento ativo do **Windows,** escolha se você gostaria de receber o Canal **de** Desenvolvimento **ou** Canal beta builds e revise os termos do programa.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="4c9cf-138">Selecione **Confirmar > Reiniciar Agora** para concluir.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="4c9cf-139">Depois que o dispositivo for reinicializado, vá para Configurações > Atualizar & **Segurança > Verificar** se há atualizações para obter o build mais recente.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="4c9cf-140">Erro de 0x80070490 para resolver o erro</span><span class="sxs-lookup"><span data-stu-id="4c9cf-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="4c9cf-141">Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, tente a seguinte explicação de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="4c9cf-142">Isso envolve mover seu canal interno, pegar a atualização e, em seguida, mover seu canal insider de volta.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="4c9cf-143">Estágio um – Versão Prévia</span><span class="sxs-lookup"><span data-stu-id="4c9cf-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="4c9cf-144">Configurações, Atualizar & Segurança, Programa Windows Insider, selecione **Versão** Prévia do Canal .</span><span class="sxs-lookup"><span data-stu-id="4c9cf-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="4c9cf-145">Configurações, Atualizar & Segurança, Windows Update, **Verificar se há atualizações.**</span><span class="sxs-lookup"><span data-stu-id="4c9cf-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="4c9cf-146">Após a atualização, continue no Estágio dois.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="4c9cf-147">Estágio dois – Canal dev</span><span class="sxs-lookup"><span data-stu-id="4c9cf-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="4c9cf-148">Configurações, Atualizar & Segurança, Programa Windows Insider, selecione **Canal deV**.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="4c9cf-149">Configurações, Atualizar & Segurança, Windows Update, **Verificar se há atualizações.**</span><span class="sxs-lookup"><span data-stu-id="4c9cf-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="4c9cf-150">Instruções de download e flash do FFU</span><span class="sxs-lookup"><span data-stu-id="4c9cf-150">FFU download and flash directions</span></span>
<span data-ttu-id="4c9cf-151">Para testar com um voo assinado ffu, primeiro você precisa desbloquear seu dispositivo antes de piscar o voo com sinal ffu.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="4c9cf-152">No PC:</span><span class="sxs-lookup"><span data-stu-id="4c9cf-152">On PC:</span></span>
    1. <span data-ttu-id="4c9cf-153">Baixe o ffu no seu computador do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="4c9cf-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="4c9cf-154">Instale o ARC (Advanced Recovery Companion) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="4c9cf-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="4c9cf-155">No HoloLens – Desbloqueio de Voo: Abrir Configurações Atualize &   >  **Segurança**  >  **Programa Windows Insider,** em seguida, inscreva-se e reinicialize o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="4c9cf-156">Flash FFU – agora você pode piscar o FFU com assinatura de voo usando ARC.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="4c9cf-157">Fornecer comentários e relatar problemas</span><span class="sxs-lookup"><span data-stu-id="4c9cf-157">Provide feedback and report issues</span></span>
<span data-ttu-id="4c9cf-158">Use o [aplicativo Hub de Comentários](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="4c9cf-159">Usar o Hub de Comentários garante que todas as informações de diagnóstico necessárias sejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="4c9cf-160">Problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="4c9cf-161">Certifique-se de aceitar o prompt que pergunta se você gostaria que o Hub de Comentários acessasse sua pasta Documentos (selecione **Sim** quando solicitado).</span><span class="sxs-lookup"><span data-stu-id="4c9cf-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="4c9cf-162">Observação para desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="4c9cf-162">Note for developers</span></span>
<span data-ttu-id="4c9cf-163">Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando builds insider do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="4c9cf-164">Confira a [Documentação do Desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="4c9cf-165">Essas mesmas instruções funcionam com builds insider do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="4c9cf-166">Você pode usar os mesmos builds do Unity e Visual Studio que já está usando para o desenvolvimento do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="4c9cf-167">Parar de receber builds do Insider</span><span class="sxs-lookup"><span data-stu-id="4c9cf-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="4c9cf-168">Se você não quiser mais receber builds insider do Windows Holographic, poderá optar quando o [](hololens-recovery.md) HoloLens estiver executando um build de produção ou recuperar seu dispositivo usando o Advanced Recovery Companion para recuperar seu dispositivo para uma versão não insider do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="4c9cf-169">Há um problema conhecido em que os usuários que não se registram no Insider Preview são builds depois de reinstalar manualmente um novo build de visualização experimentariam uma tela azul.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="4c9cf-170">Posteriormente, eles devem recuperar manualmente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="4c9cf-171">Para obter detalhes completos sobre se você seria afetado ou não, veja mais sobre esse [problema conhecido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="4c9cf-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="4c9cf-172">Para verificar se o HoloLens está executando um build de produção:</span><span class="sxs-lookup"><span data-stu-id="4c9cf-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="4c9cf-173">Vá para **Configurações > Sistema > Sobre** e encontre o número de build.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="4c9cf-174">[Consulte as notas de versão para números de build de produção](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="4c9cf-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="4c9cf-175">Para não fazer builds do Insider:</span><span class="sxs-lookup"><span data-stu-id="4c9cf-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="4c9cf-176">Em um HoloLens executando um build de produção, acesse Configurações > Atualizar & **Segurança > Programa Windows Insider** e selecione **Parar Builds do Insider**.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="4c9cf-177">Siga as instruções para ressutar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c9cf-177">Follow the instructions to opt out your device.</span></span>
