---
title: Cenários comuns – HoloLens seguro offline 2
description: Saiba como configurar uma implantação segura offline e um cenário de implantação de aplicativo com o provisionamento para dispositivos HoloLens.
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308046"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="8a718-104">Cenários comuns – HoloLens seguro offline 2</span><span class="sxs-lookup"><span data-stu-id="8a718-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="8a718-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="8a718-105">Overview</span></span>

<span data-ttu-id="8a718-106">Este guia fornece diretrizes para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="8a718-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="8a718-107">Desabilite o WiFi.</span><span class="sxs-lookup"><span data-stu-id="8a718-107">Disable WiFi.</span></span>
-   <span data-ttu-id="8a718-108">Desabilite o BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="8a718-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="8a718-109">Desabilite os microfones.</span><span class="sxs-lookup"><span data-stu-id="8a718-109">Disable Microphones.</span></span>
-   <span data-ttu-id="8a718-110">Impede a adição ou remoção de pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="8a718-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="8a718-111">Nenhum usuário pode habilitar qualquer um dos componentes restritos acima.</span><span class="sxs-lookup"><span data-stu-id="8a718-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="8a718-112">Preparar</span><span class="sxs-lookup"><span data-stu-id="8a718-112">Prepare</span></span>

<span data-ttu-id="8a718-113">Instalação do PC com Windows 10</span><span class="sxs-lookup"><span data-stu-id="8a718-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="8a718-114">[Baixe o mais recente arquivo do sistema operacional do HoloLens 2](https://aka.ms/hololens2download) diretamente em um PC.</span><span class="sxs-lookup"><span data-stu-id="8a718-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="8a718-115">O suporte para essa configuração está incluído no Build 19041,1117 e superior.</span><span class="sxs-lookup"><span data-stu-id="8a718-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="8a718-116">Baixe/instale a ferramenta complementar de recuperação avançada (ARC) [do Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para seu PC</span><span class="sxs-lookup"><span data-stu-id="8a718-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="8a718-117">Baixe/instale a mais recente ferramenta do [Windows Configuration designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) do Microsoft Store para seu PC.</span><span class="sxs-lookup"><span data-stu-id="8a718-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="8a718-118">[Baixe a pasta OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.</span><span class="sxs-lookup"><span data-stu-id="8a718-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="8a718-119">Prepare seu [aplicativo de linha de negócios offline para a implantação do PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="8a718-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="8a718-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="8a718-120">Configure</span></span>

<span data-ttu-id="8a718-121">Criar um pacote de provisionamento de configuração segura</span><span class="sxs-lookup"><span data-stu-id="8a718-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="8a718-122">Inicie a ferramenta WCD em seu computador.</span><span class="sxs-lookup"><span data-stu-id="8a718-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="8a718-123">Selecione **arquivo-> projeto aberto**.</span><span class="sxs-lookup"><span data-stu-id="8a718-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="8a718-124">Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="8a718-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="8a718-125">O projeto deve ser aberto e agora você deve ter uma lista de personalizações disponíveis:</span><span class="sxs-lookup"><span data-stu-id="8a718-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8a718-126">![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="8a718-126">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="8a718-127">Configurações definidas neste pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="8a718-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="8a718-128">Item</span><span class="sxs-lookup"><span data-stu-id="8a718-128">Item</span></span>                                                |     <span data-ttu-id="8a718-129">Configuração</span><span class="sxs-lookup"><span data-stu-id="8a718-129">Setting</span></span>                       |     <span data-ttu-id="8a718-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="8a718-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="8a718-131">Contas/usuários</span><span class="sxs-lookup"><span data-stu-id="8a718-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="8a718-132">Nome de usuário local & senha</span><span class="sxs-lookup"><span data-stu-id="8a718-132">Local User Name & Password</span></span>    |     <span data-ttu-id="8a718-133">Para esses dispositivos offline, um único nome de usuário e uma senha deverão ser definidos e compartilhados por todos os usuários do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8a718-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="8a718-134">Primeira experiência/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="8a718-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="8a718-135">True</span><span class="sxs-lookup"><span data-stu-id="8a718-135">True</span></span>                          |     <span data-ttu-id="8a718-136">Ignora a calibragem durante somente a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8a718-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="8a718-137">Primeira experiência/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="8a718-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="8a718-138">True</span><span class="sxs-lookup"><span data-stu-id="8a718-138">True</span></span>                          |     <span data-ttu-id="8a718-139">Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8a718-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="8a718-140">Primeira experiência/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="8a718-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="8a718-141">True</span><span class="sxs-lookup"><span data-stu-id="8a718-141">True</span></span>                          |     <span data-ttu-id="8a718-142">Ignora Wi-Fi config durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8a718-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="8a718-143">Políticas/conectividade/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="8a718-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="8a718-144">No</span><span class="sxs-lookup"><span data-stu-id="8a718-144">No</span></span>                            |     <span data-ttu-id="8a718-145">Desabilita o Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8a718-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="8a718-146">Políticas/experiência/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="8a718-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="8a718-147">No</span><span class="sxs-lookup"><span data-stu-id="8a718-147">No</span></span>                            |     <span data-ttu-id="8a718-148">Desabilita a Cortana (para eliminar problemas potenciais, pois os microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="8a718-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="8a718-149">Políticas/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="8a718-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="8a718-150">Yes</span><span class="sxs-lookup"><span data-stu-id="8a718-150">Yes</span></span>                           |     <span data-ttu-id="8a718-151">Desabilita o microfone</span><span class="sxs-lookup"><span data-stu-id="8a718-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="8a718-152">Políticas/privacidade/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="8a718-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="8a718-153">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="8a718-153">Force deny</span></span>                    |     <span data-ttu-id="8a718-154">Impede que os aplicativos tentem acessar os dados do local (para eliminar problemas potenciais, já que o rastreamento de local está desabilitado)</span><span class="sxs-lookup"><span data-stu-id="8a718-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="8a718-155">Políticas/privacidade/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="8a718-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="8a718-156">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="8a718-156">Force deny</span></span>                    |     <span data-ttu-id="8a718-157">Impede que os aplicativos tentem acessar microfones (para eliminar problemas potenciais, pois os microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="8a718-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="8a718-158">Políticas/segurança/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="8a718-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="8a718-159">No</span><span class="sxs-lookup"><span data-stu-id="8a718-159">No</span></span>                            |     <span data-ttu-id="8a718-160">Impede que qualquer pessoa Adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="8a718-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="8a718-161">Políticas/segurança/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="8a718-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="8a718-162">No</span><span class="sxs-lookup"><span data-stu-id="8a718-162">No</span></span>                            |     <span data-ttu-id="8a718-163">Impede que qualquer pessoa Remova esse pacote de provisionamento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="8a718-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="8a718-164">Políticas/sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="8a718-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="8a718-165">No</span><span class="sxs-lookup"><span data-stu-id="8a718-165">No</span></span>                            |     <span data-ttu-id="8a718-166">Impede que o dispositivo tente controlar os dados de localização.</span><span class="sxs-lookup"><span data-stu-id="8a718-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="8a718-167">Políticas/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="8a718-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="8a718-168">No</span><span class="sxs-lookup"><span data-stu-id="8a718-168">No</span></span>                            |     <span data-ttu-id="8a718-169">Desabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8a718-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="8a718-170">Em configurações de tempo de execução, selecione **contas/usuários/nome de usuário: holo/senha**.</span><span class="sxs-lookup"><span data-stu-id="8a718-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="8a718-171">Anote a senha e redefina, se desejado.</span><span class="sxs-lookup"><span data-stu-id="8a718-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="8a718-172">Navegue até UniversalAppInstall/UserContextApp e [Configure o aplicativo LOB](app-deploy-provisioning-package.md) que você estará implantando nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8a718-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8a718-173">![Captura de tela de onde adicionar seu aplicativo em WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="8a718-173">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="8a718-174">Depois de concluído, selecione o botão "exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.</span><span class="sxs-lookup"><span data-stu-id="8a718-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8a718-175">![Captura de tela do botão Exportar para este pacote em WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="8a718-175">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="8a718-176">Implantar</span><span class="sxs-lookup"><span data-stu-id="8a718-176">Deploy</span></span>

1. <span data-ttu-id="8a718-177">Conecte o HL2 ao seu PC com Windows 10 via cabo USB.</span><span class="sxs-lookup"><span data-stu-id="8a718-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="8a718-178">Inicie a ferramenta ARC e selecione **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="8a718-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Tela inicial do HoloLens 2 limpar reflash](images/ARC2.png)

1. <span data-ttu-id="8a718-180">Na próxima tela, selecione **seleção de pacote manual**.</span><span class="sxs-lookup"><span data-stu-id="8a718-180">On the next screen select **Manual package selection**.</span></span>

   ![Tela de informações sobre ARC 2 do HoloLens](images/arc_device_info.png)

1. <span data-ttu-id="8a718-182">Navegue até o arquivo. FFU baixado anteriormente e selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="8a718-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="8a718-183">Na página de aviso, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="8a718-183">At the Warning page select **Continue**.</span></span>

   ![Tela de aviso de arco 2 do HoloLens](images/arc_warning.png)

1. <span data-ttu-id="8a718-185">Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8a718-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="8a718-186">Depois que o dispositivo concluir a instalação e inicializar o backup, em seu PC, navegue até o explorador de arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8a718-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8a718-187">![Arquivo PPKG no PC na janela Explorador de arquivos.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="8a718-187">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="8a718-188">No HoloLens 2, pressione a combinação de botão a seguir para executar o pacote de provisionamento: toque em **volume baixo** e **botão de energia** ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8a718-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="8a718-189">Você será solicitado a aplicar o pacote de provisionamento, selecionar **confirmar**</span><span class="sxs-lookup"><span data-stu-id="8a718-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="8a718-190">Depois que o pacote de provisionamento for concluído, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a718-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="8a718-191">Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.</span><span class="sxs-lookup"><span data-stu-id="8a718-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="8a718-192">Manter</span><span class="sxs-lookup"><span data-stu-id="8a718-192">Maintain</span></span>

<span data-ttu-id="8a718-193">Com essa configuração, é recomendável reiniciar o processo acima e refazer o flash do dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer atualizações no sistema operacional e/ou aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8a718-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
