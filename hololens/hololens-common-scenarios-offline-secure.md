---
title: Cenários comuns – HoloLens 2 seguro offline
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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397877"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="a7765-104">Cenários comuns – HoloLens 2 seguro offline</span><span class="sxs-lookup"><span data-stu-id="a7765-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="a7765-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="a7765-105">Overview</span></span>

<span data-ttu-id="a7765-106">Este guia fornece diretrizes para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="a7765-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="a7765-107">Desabilite o WiFi.</span><span class="sxs-lookup"><span data-stu-id="a7765-107">Disable WiFi.</span></span>
-   <span data-ttu-id="a7765-108">Desabilite BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="a7765-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="a7765-109">Desabilitar Microfones.</span><span class="sxs-lookup"><span data-stu-id="a7765-109">Disable Microphones.</span></span>
-   <span data-ttu-id="a7765-110">Impede a adição ou remoção de pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="a7765-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="a7765-111">Nenhum usuário pode habilitar nenhum dos componentes restritos acima.</span><span class="sxs-lookup"><span data-stu-id="a7765-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="a7765-112">[![Cenário de segurança offline ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a7765-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="a7765-113">Preparar</span><span class="sxs-lookup"><span data-stu-id="a7765-113">Prepare</span></span>

<span data-ttu-id="a7765-114">Windows 10 configuração do computador</span><span class="sxs-lookup"><span data-stu-id="a7765-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="a7765-115">Baixe o arquivo mais recente do sistema operacional [do HoloLens 2](https://aka.ms/hololens2download) diretamente em um computador.</span><span class="sxs-lookup"><span data-stu-id="a7765-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="a7765-116">O suporte para essa configuração está incluído no Build 19041.1117 e superior.</span><span class="sxs-lookup"><span data-stu-id="a7765-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="a7765-117">Baixe/instale a ferramenta ARC (Advanced Recovery Companion) [do Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) seu computador</span><span class="sxs-lookup"><span data-stu-id="a7765-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="a7765-118">Baixe/instale a ferramenta [WCD (Designer de Configuração do Windows)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) mais recente do Microsoft Store seu computador.</span><span class="sxs-lookup"><span data-stu-id="a7765-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="a7765-119">[Baixe a OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.</span><span class="sxs-lookup"><span data-stu-id="a7765-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="a7765-120">Prepare seu aplicativo [offline de Linha de Negócios para implantação do PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="a7765-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="a7765-121">Configurar</span><span class="sxs-lookup"><span data-stu-id="a7765-121">Configure</span></span>

<span data-ttu-id="a7765-122">Criar um pacote de provisionamento de configuração segura</span><span class="sxs-lookup"><span data-stu-id="a7765-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="a7765-123">Iniciar a ferramenta WCD em seu computador.</span><span class="sxs-lookup"><span data-stu-id="a7765-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="a7765-124">Selecione **Arquivo -> Abrir projeto**.</span><span class="sxs-lookup"><span data-stu-id="a7765-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="a7765-125">Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="a7765-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="a7765-126">O projeto deve ser aberto e agora você deve ter uma lista de Personalizações Disponíveis:</span><span class="sxs-lookup"><span data-stu-id="a7765-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7765-127">![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="a7765-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="a7765-128">Configurações definidas neste pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="a7765-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="a7765-129">Item</span><span class="sxs-lookup"><span data-stu-id="a7765-129">Item</span></span>                                                |     <span data-ttu-id="a7765-130">Setting</span><span class="sxs-lookup"><span data-stu-id="a7765-130">Setting</span></span>                       |     <span data-ttu-id="a7765-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="a7765-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="a7765-132">Contas/Usuários</span><span class="sxs-lookup"><span data-stu-id="a7765-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="a7765-133">Nome de usuário local & senha</span><span class="sxs-lookup"><span data-stu-id="a7765-133">Local User Name & Password</span></span>    |     <span data-ttu-id="a7765-134">Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a7765-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="a7765-135">Primeira experiência/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="a7765-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="a7765-136">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="a7765-136">True</span></span>                          |     <span data-ttu-id="a7765-137">Ignora a calibragem somente durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="a7765-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="a7765-138">Primeira experiência/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="a7765-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="a7765-139">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="a7765-139">True</span></span>                          |     <span data-ttu-id="a7765-140">Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="a7765-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="a7765-141">Primeira experiência/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="a7765-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="a7765-142">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="a7765-142">True</span></span>                          |     <span data-ttu-id="a7765-143">Ignora a configuração Wi-Fi durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="a7765-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="a7765-144">Políticas/Conectividade/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="a7765-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="a7765-145">No</span><span class="sxs-lookup"><span data-stu-id="a7765-145">No</span></span>                            |     <span data-ttu-id="a7765-146">Desabilita o Bluetooth</span><span class="sxs-lookup"><span data-stu-id="a7765-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="a7765-147">Políticas/Experiência/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="a7765-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="a7765-148">No</span><span class="sxs-lookup"><span data-stu-id="a7765-148">No</span></span>                            |     <span data-ttu-id="a7765-149">Desabilita a Cortana (para eliminar possíveis problemas, pois os microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="a7765-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="a7765-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="a7765-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="a7765-151">Yes</span><span class="sxs-lookup"><span data-stu-id="a7765-151">Yes</span></span>                           |     <span data-ttu-id="a7765-152">Desabilita o microfone</span><span class="sxs-lookup"><span data-stu-id="a7765-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="a7765-153">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="a7765-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="a7765-154">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="a7765-154">Force deny</span></span>                    |     <span data-ttu-id="a7765-155">Impede que os Aplicativos tentarem acessar dados de Localização (para eliminar possíveis problemas, pois o rastreamento de localização está desabilitado)</span><span class="sxs-lookup"><span data-stu-id="a7765-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="a7765-156">Policies/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="a7765-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="a7765-157">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="a7765-157">Force deny</span></span>                    |     <span data-ttu-id="a7765-158">Impede que os aplicativos tentarem acessar microfones (para eliminar possíveis problemas, pois os microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="a7765-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="a7765-159">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="a7765-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="a7765-160">No</span><span class="sxs-lookup"><span data-stu-id="a7765-160">No</span></span>                            |     <span data-ttu-id="a7765-161">Impede que qualquer pessoa adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="a7765-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="a7765-162">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="a7765-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="a7765-163">No</span><span class="sxs-lookup"><span data-stu-id="a7765-163">No</span></span>                            |     <span data-ttu-id="a7765-164">Impede que qualquer pessoa remova esse pacote de provisionamento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="a7765-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="a7765-165">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="a7765-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="a7765-166">No</span><span class="sxs-lookup"><span data-stu-id="a7765-166">No</span></span>                            |     <span data-ttu-id="a7765-167">Impede que o dispositivo tenta rastrear dados de localização.</span><span class="sxs-lookup"><span data-stu-id="a7765-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="a7765-168">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="a7765-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="a7765-169">No</span><span class="sxs-lookup"><span data-stu-id="a7765-169">No</span></span>                            |     <span data-ttu-id="a7765-170">Desabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a7765-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="a7765-171">Em Configurações de Runtime, selecione **Contas/Usuários/UserName: Holo /Password**.</span><span class="sxs-lookup"><span data-stu-id="a7765-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="a7765-172">Anote a senha e redefinir se desejar.</span><span class="sxs-lookup"><span data-stu-id="a7765-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="a7765-173">Navegue até UniversalAppInstall/UserContextApp e configure o [aplicativo LOB](app-deploy-provisioning-package.md) que você implantará nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a7765-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7765-174">![Captura de tela de onde adicionar seu aplicativo no WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="a7765-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="a7765-175">Depois de concluir, selecione o botão "Exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.</span><span class="sxs-lookup"><span data-stu-id="a7765-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7765-176">![Captura de tela do botão Exportar para este pacote no WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="a7765-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="a7765-177">Implantar</span><span class="sxs-lookup"><span data-stu-id="a7765-177">Deploy</span></span>

1. <span data-ttu-id="a7765-178">Conecte o HL2 ao seu PC com Windows 10 via cabo USB.</span><span class="sxs-lookup"><span data-stu-id="a7765-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="a7765-179">Inicie a ferramenta ARC e selecione **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="a7765-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Tela inicial do HoloLens 2 limpar reflash](images/ARC2.png)

1. <span data-ttu-id="a7765-181">Na próxima tela, selecione **seleção de pacote manual**.</span><span class="sxs-lookup"><span data-stu-id="a7765-181">On the next screen select **Manual package selection**.</span></span>

   ![Tela de informações sobre ARC 2 do HoloLens](images/arc_device_info.png)

1. <span data-ttu-id="a7765-183">Navegue até o arquivo. FFU baixado anteriormente e selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="a7765-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="a7765-184">Na página de aviso, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="a7765-184">At the Warning page select **Continue**.</span></span>

   ![Tela de aviso de arco 2 do HoloLens](images/arc_warning.png)

1. <span data-ttu-id="a7765-186">Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a7765-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="a7765-187">Depois que o dispositivo concluir a instalação e inicializar o backup, em seu PC, navegue até o explorador de arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a7765-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a7765-188">![Arquivo PPKG no PC na janela Explorador de arquivos.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="a7765-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="a7765-189">No HoloLens 2, pressione a combinação de botão a seguir para executar o pacote de provisionamento: toque em **volume baixo** e **botão de energia** ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a7765-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="a7765-190">Você será solicitado a aplicar o pacote de provisionamento, selecionar **confirmar**</span><span class="sxs-lookup"><span data-stu-id="a7765-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="a7765-191">Depois que o pacote de provisionamento for concluído, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7765-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="a7765-192">Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.</span><span class="sxs-lookup"><span data-stu-id="a7765-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="a7765-193">Manter</span><span class="sxs-lookup"><span data-stu-id="a7765-193">Maintain</span></span>

<span data-ttu-id="a7765-194">Com essa configuração, é recomendável reiniciar o processo acima e refazer o flash do dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer atualizações no sistema operacional e/ou aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a7765-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
