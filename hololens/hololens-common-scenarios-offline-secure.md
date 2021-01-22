---
title: Cenários comuns – HoloLens Seguro Offline 2
description: Saiba como configurar uma implantação segura offline e um cenário de implantação de aplicativo com provisionamento para dispositivos HoloLens.
keywords: HoloLens, gerenciamento, offline, seguro offline
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283411"
---
# <span data-ttu-id="f1533-104">Cenários comuns – HoloLens Seguro Offline 2</span><span class="sxs-lookup"><span data-stu-id="f1533-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="f1533-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f1533-105">Overview</span></span>

<span data-ttu-id="f1533-106">Este guia fornece orientações para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="f1533-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="f1533-107">Desabilitar WiFi.</span><span class="sxs-lookup"><span data-stu-id="f1533-107">Disable WiFi.</span></span>
-   <span data-ttu-id="f1533-108">Desabilitar BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="f1533-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="f1533-109">Desabilitar microfones.</span><span class="sxs-lookup"><span data-stu-id="f1533-109">Disable Microphones.</span></span>
-   <span data-ttu-id="f1533-110">Impede a adição ou remoção de pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="f1533-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="f1533-111">Nenhum usuário pode habilitar nenhum dos componentes restritos acima.</span><span class="sxs-lookup"><span data-stu-id="f1533-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="f1533-112">Preparar</span><span class="sxs-lookup"><span data-stu-id="f1533-112">Prepare</span></span>

<span data-ttu-id="f1533-113">Configuração do computador Windows 10</span><span class="sxs-lookup"><span data-stu-id="f1533-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="f1533-114">Baixe o arquivo do sistema operacional mais recente do [HoloLens 2](https://aka.ms/hololens2download) diretamente para um computador.</span><span class="sxs-lookup"><span data-stu-id="f1533-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="f1533-115">O suporte para essa configuração está incluído no Build 19041.1117 e superior.</span><span class="sxs-lookup"><span data-stu-id="f1533-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="f1533-116">Baixar/instalar a ferramenta Advanced Recovery Companion (ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) em seu computador</span><span class="sxs-lookup"><span data-stu-id="f1533-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="f1533-117">Baixe/instale a ferramenta mais recente do Designer de Configuração [do Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store para seu computador.</span><span class="sxs-lookup"><span data-stu-id="f1533-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="f1533-118">[Baixe a OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.</span><span class="sxs-lookup"><span data-stu-id="f1533-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="f1533-119">Prepare seu aplicativo [offline de linha de negócios para implantação ppkg](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="f1533-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="f1533-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="f1533-120">Configure</span></span>

<span data-ttu-id="f1533-121">Criar um pacote de provisionamento de configuração segura</span><span class="sxs-lookup"><span data-stu-id="f1533-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="f1533-122">Iniciar a ferramenta WCD em seu computador.</span><span class="sxs-lookup"><span data-stu-id="f1533-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="f1533-123">Select **File -> Open project**.</span><span class="sxs-lookup"><span data-stu-id="f1533-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="f1533-124">Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="f1533-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="f1533-125">O projeto deve ser aberto e agora você deve ter uma lista de Personalizações Disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f1533-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)

<span data-ttu-id="f1533-127">Configurações definidas neste pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="f1533-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="f1533-128">Item</span><span class="sxs-lookup"><span data-stu-id="f1533-128">Item</span></span>                                                |     <span data-ttu-id="f1533-129">Configuração</span><span class="sxs-lookup"><span data-stu-id="f1533-129">Setting</span></span>                       |     <span data-ttu-id="f1533-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="f1533-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="f1533-131">Contas/usuários</span><span class="sxs-lookup"><span data-stu-id="f1533-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="f1533-132">Local User Name & Password</span><span class="sxs-lookup"><span data-stu-id="f1533-132">Local User Name & Password</span></span>    |     <span data-ttu-id="f1533-133">Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1533-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="f1533-134">Primeira Experiência/ HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="f1533-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="f1533-135">True</span><span class="sxs-lookup"><span data-stu-id="f1533-135">True</span></span>                          |     <span data-ttu-id="f1533-136">Ignora a calibragem somente durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f1533-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="f1533-137">Primeira Experiência/ HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="f1533-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="f1533-138">True</span><span class="sxs-lookup"><span data-stu-id="f1533-138">True</span></span>                          |     <span data-ttu-id="f1533-139">Ignora o treinamento de dispositivos durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f1533-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="f1533-140">Primeira Experiência/ HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="f1533-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="f1533-141">True</span><span class="sxs-lookup"><span data-stu-id="f1533-141">True</span></span>                          |     <span data-ttu-id="f1533-142">Ignora Wi-Fi configuração durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f1533-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="f1533-143">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="f1533-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="f1533-144">Não</span><span class="sxs-lookup"><span data-stu-id="f1533-144">No</span></span>                            |     <span data-ttu-id="f1533-145">Desabilita o Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f1533-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="f1533-146">Policies/Experience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="f1533-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="f1533-147">Não</span><span class="sxs-lookup"><span data-stu-id="f1533-147">No</span></span>                            |     <span data-ttu-id="f1533-148">Desabilita a Cortana (para eliminar possíveis problemas, pois os microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="f1533-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="f1533-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="f1533-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="f1533-150">Sim</span><span class="sxs-lookup"><span data-stu-id="f1533-150">Yes</span></span>                           |     <span data-ttu-id="f1533-151">Desabilita o microfone</span><span class="sxs-lookup"><span data-stu-id="f1533-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="f1533-152">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="f1533-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="f1533-153">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="f1533-153">Force deny</span></span>                    |     <span data-ttu-id="f1533-154">Impede que os aplicativos tentam acessar dados de localização (para eliminar possíveis problemas, pois o rastreamento de localização está desabilitado)</span><span class="sxs-lookup"><span data-stu-id="f1533-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="f1533-155">Policies/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="f1533-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="f1533-156">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="f1533-156">Force deny</span></span>                    |     <span data-ttu-id="f1533-157">Impede que os aplicativos tentam acessar microfones (para eliminar possíveis problemas, pois os microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="f1533-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="f1533-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="f1533-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="f1533-159">Não</span><span class="sxs-lookup"><span data-stu-id="f1533-159">No</span></span>                            |     <span data-ttu-id="f1533-160">Impede que qualquer pessoa adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="f1533-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="f1533-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="f1533-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="f1533-162">Não</span><span class="sxs-lookup"><span data-stu-id="f1533-162">No</span></span>                            |     <span data-ttu-id="f1533-163">Impede que qualquer pessoa remova esse pacote de provisionamento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="f1533-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="f1533-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="f1533-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="f1533-165">Não</span><span class="sxs-lookup"><span data-stu-id="f1533-165">No</span></span>                            |     <span data-ttu-id="f1533-166">Impede que o dispositivo tentar rastrear dados de localização.</span><span class="sxs-lookup"><span data-stu-id="f1533-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="f1533-167">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="f1533-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="f1533-168">Não</span><span class="sxs-lookup"><span data-stu-id="f1533-168">No</span></span>                            |     <span data-ttu-id="f1533-169">Desabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f1533-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="f1533-170">Em Configurações de Tempo de Execução, Selecione **Contas/Usuários / Nome de Usuário: Holo / Senha**</span><span class="sxs-lookup"><span data-stu-id="f1533-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="f1533-171">Anote a senha e redefinir, se desejado.</span><span class="sxs-lookup"><span data-stu-id="f1533-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="f1533-172">Navegue até UniversalAppInstall / UserContextApp e configure o aplicativo [LOB](app-deploy-provisioning-package.md) que você implantará nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f1533-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo no WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="f1533-174">Depois de concluir, selecione o botão "Exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.</span><span class="sxs-lookup"><span data-stu-id="f1533-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote no WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="f1533-176">Implantar</span><span class="sxs-lookup"><span data-stu-id="f1533-176">Deploy</span></span>

1. <span data-ttu-id="f1533-177">Conecte o HL2 ao seu computador Windows 10 por meio de cabo USB.</span><span class="sxs-lookup"><span data-stu-id="f1533-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="f1533-178">Iniciar a ferramenta ARC e selecionar **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="f1533-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="f1533-179">Na próxima tela, selecione **Seleção manual de pacote.**</span><span class="sxs-lookup"><span data-stu-id="f1533-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="f1533-180">Navegue até o arquivo .ffu baixado anteriormente e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f1533-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="f1533-181">Na página Aviso, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="f1533-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="f1533-182">Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f1533-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="f1533-183">Depois que o dispositivo concluir a instalação e inicializar o back-up, no computador, navegue até o Explorador de Arquivos e copie o arquivo PPKG salvo anteriormente na pasta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f1533-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Arquivo PPKG no computador na janela do Explorador de Arquivos.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="f1533-185">No HoloLens 2, pressione a combinação do botão a seguir para \*\*\*\* executar o Pacote de Provisionamento: toque em **Aumentar o Volume** e no Botão Ligar/Desligar ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f1533-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="f1533-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span><span class="sxs-lookup"><span data-stu-id="f1533-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="f1533-187">Depois que o pacote de provisionamento é concluído, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1533-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="f1533-188">Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.</span><span class="sxs-lookup"><span data-stu-id="f1533-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="f1533-189">Manter</span><span class="sxs-lookup"><span data-stu-id="f1533-189">Maintain</span></span>

<span data-ttu-id="f1533-190">Com essa configuração, é recomendável reiniciar o processo acima e reflash o dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer quaisquer atualizações para o sistema operacional e/ou aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f1533-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

