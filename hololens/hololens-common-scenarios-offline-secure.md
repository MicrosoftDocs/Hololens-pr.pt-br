---
title: Cenários Comuns - Offline Secure HoloLens 2
description: Saiba como configurar um cenário de implantação de aplicativo e implantação de aplicativo seguro offline com provisionamento para dispositivos HoloLens.
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
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407566"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="f64a7-104">Cenários Comuns - Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f64a7-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="f64a7-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f64a7-105">Overview</span></span>

<span data-ttu-id="f64a7-106">Este guia fornece orientações para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="f64a7-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="f64a7-107">Desabilitar WiFi.</span><span class="sxs-lookup"><span data-stu-id="f64a7-107">Disable WiFi.</span></span>
-   <span data-ttu-id="f64a7-108">Desabilitar BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="f64a7-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="f64a7-109">Desabilitar microfones.</span><span class="sxs-lookup"><span data-stu-id="f64a7-109">Disable Microphones.</span></span>
-   <span data-ttu-id="f64a7-110">Impede a adição ou remoção de pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="f64a7-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="f64a7-111">Nenhum usuário pode habilitar nenhum dos componentes restritos acima.</span><span class="sxs-lookup"><span data-stu-id="f64a7-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="f64a7-112">Preparar</span><span class="sxs-lookup"><span data-stu-id="f64a7-112">Prepare</span></span>

<span data-ttu-id="f64a7-113">Instalação do computador windows 10</span><span class="sxs-lookup"><span data-stu-id="f64a7-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="f64a7-114">Baixe o arquivo operacional mais recente do [HoloLens 2](https://aka.ms/hololens2download) diretamente para um computador.</span><span class="sxs-lookup"><span data-stu-id="f64a7-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="f64a7-115">O suporte para essa configuração está incluído no Build 19041.1117 e acima.</span><span class="sxs-lookup"><span data-stu-id="f64a7-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="f64a7-116">Baixar/instalar a ferramenta Arc (Advanced Recovery Companion) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para o computador</span><span class="sxs-lookup"><span data-stu-id="f64a7-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="f64a7-117">Baixe/instale a ferramenta mais recente do Designer de Configuração do [Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store para seu computador.</span><span class="sxs-lookup"><span data-stu-id="f64a7-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="f64a7-118">[Baixe a OfflineSecureHL2_Sample com os arquivos do projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.</span><span class="sxs-lookup"><span data-stu-id="f64a7-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="f64a7-119">Prepare seu aplicativo [de Linha de Negócios offline para implantação do PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="f64a7-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="f64a7-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="f64a7-120">Configure</span></span>

<span data-ttu-id="f64a7-121">Criar um pacote de provisionamento de configuração segura</span><span class="sxs-lookup"><span data-stu-id="f64a7-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="f64a7-122">Iniciar a ferramenta WCD em seu computador.</span><span class="sxs-lookup"><span data-stu-id="f64a7-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="f64a7-123">Selecione **Arquivo -> Abrir projeto**.</span><span class="sxs-lookup"><span data-stu-id="f64a7-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="f64a7-124">Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="f64a7-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="f64a7-125">O projeto deve ser aberto e agora você deve ter uma lista de Personalizações Disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f64a7-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="f64a7-127">Configurações definidas neste pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="f64a7-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="f64a7-128">Item</span><span class="sxs-lookup"><span data-stu-id="f64a7-128">Item</span></span>                                                |     <span data-ttu-id="f64a7-129">Configuração</span><span class="sxs-lookup"><span data-stu-id="f64a7-129">Setting</span></span>                       |     <span data-ttu-id="f64a7-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="f64a7-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="f64a7-131">Contas/Usuários</span><span class="sxs-lookup"><span data-stu-id="f64a7-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="f64a7-132">Nome de usuário local & Senha</span><span class="sxs-lookup"><span data-stu-id="f64a7-132">Local User Name & Password</span></span>    |     <span data-ttu-id="f64a7-133">Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f64a7-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="f64a7-134">Primeira Experiência / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="f64a7-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="f64a7-135">True</span><span class="sxs-lookup"><span data-stu-id="f64a7-135">True</span></span>                          |     <span data-ttu-id="f64a7-136">Ignora a calibragem somente durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f64a7-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="f64a7-137">Primeira Experiência / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="f64a7-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="f64a7-138">True</span><span class="sxs-lookup"><span data-stu-id="f64a7-138">True</span></span>                          |     <span data-ttu-id="f64a7-139">Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f64a7-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="f64a7-140">Primeira Experiência / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="f64a7-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="f64a7-141">True</span><span class="sxs-lookup"><span data-stu-id="f64a7-141">True</span></span>                          |     <span data-ttu-id="f64a7-142">Ignora Wi-Fi configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f64a7-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="f64a7-143">Políticas/Conectividade/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="f64a7-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="f64a7-144">Não</span><span class="sxs-lookup"><span data-stu-id="f64a7-144">No</span></span>                            |     <span data-ttu-id="f64a7-145">Desabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f64a7-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="f64a7-146">Políticas/Experiência/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="f64a7-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="f64a7-147">Não</span><span class="sxs-lookup"><span data-stu-id="f64a7-147">No</span></span>                            |     <span data-ttu-id="f64a7-148">Desabilita a Cortana (para eliminar possíveis problemas, já que os microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="f64a7-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="f64a7-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="f64a7-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="f64a7-150">Sim</span><span class="sxs-lookup"><span data-stu-id="f64a7-150">Yes</span></span>                           |     <span data-ttu-id="f64a7-151">Desabilita o microfone</span><span class="sxs-lookup"><span data-stu-id="f64a7-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="f64a7-152">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="f64a7-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="f64a7-153">Negar força</span><span class="sxs-lookup"><span data-stu-id="f64a7-153">Force deny</span></span>                    |     <span data-ttu-id="f64a7-154">Impede que os aplicativos acessem dados de localização (para eliminar possíveis problemas, já que o rastreamento de local está desabilitado)</span><span class="sxs-lookup"><span data-stu-id="f64a7-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="f64a7-155">Policies/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="f64a7-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="f64a7-156">Negar força</span><span class="sxs-lookup"><span data-stu-id="f64a7-156">Force deny</span></span>                    |     <span data-ttu-id="f64a7-157">Impede que os aplicativos acessem microfones (para eliminar possíveis problemas, já que os Microfones estão desabilitados)</span><span class="sxs-lookup"><span data-stu-id="f64a7-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="f64a7-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="f64a7-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="f64a7-159">Não</span><span class="sxs-lookup"><span data-stu-id="f64a7-159">No</span></span>                            |     <span data-ttu-id="f64a7-160">Impede que qualquer pessoa adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="f64a7-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="f64a7-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="f64a7-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="f64a7-162">Não</span><span class="sxs-lookup"><span data-stu-id="f64a7-162">No</span></span>                            |     <span data-ttu-id="f64a7-163">Impede que qualquer pessoa remova esse pacote de provisionamento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="f64a7-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="f64a7-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="f64a7-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="f64a7-165">Não</span><span class="sxs-lookup"><span data-stu-id="f64a7-165">No</span></span>                            |     <span data-ttu-id="f64a7-166">Impede que o dispositivo tenta rastrear dados de localização.</span><span class="sxs-lookup"><span data-stu-id="f64a7-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="f64a7-167">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="f64a7-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="f64a7-168">Não</span><span class="sxs-lookup"><span data-stu-id="f64a7-168">No</span></span>                            |     <span data-ttu-id="f64a7-169">Desabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f64a7-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="f64a7-170">Em Configurações de Tempo de Execução, Selecione **Contas / Usuários / UserName: Holo / Password**.</span><span class="sxs-lookup"><span data-stu-id="f64a7-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="f64a7-171">Observe a senha e redefinir se desejado.</span><span class="sxs-lookup"><span data-stu-id="f64a7-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="f64a7-172">Navegue até UniversalAppInstall /UserContextApp e configure o [aplicativo LOB](app-deploy-provisioning-package.md) que você implantará nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f64a7-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo no WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="f64a7-174">Depois de concluir, selecione o botão "Exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.</span><span class="sxs-lookup"><span data-stu-id="f64a7-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote no WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="f64a7-176">Implantar</span><span class="sxs-lookup"><span data-stu-id="f64a7-176">Deploy</span></span>

1. <span data-ttu-id="f64a7-177">Conecte o HL2 ao computador windows 10 por meio de cabo USB.</span><span class="sxs-lookup"><span data-stu-id="f64a7-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="f64a7-178">Iniciar a ferramenta ARC e selecionar **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="f64a7-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Tela inicial da limpeza da flash do HoloLens 2](images/ARC2.png)

1. <span data-ttu-id="f64a7-180">Na próxima tela, selecione **Seleção manual de pacote**.</span><span class="sxs-lookup"><span data-stu-id="f64a7-180">On the next screen select **Manual package selection**.</span></span>

   ![Tela de informações do HoloLens 2 ARC](images/arc_device_info.png)

1. <span data-ttu-id="f64a7-182">Navegue até o arquivo .ffu baixado anteriormente e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f64a7-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="f64a7-183">Na página Aviso, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="f64a7-183">At the Warning page select **Continue**.</span></span>

   ![Tela de aviso do HoloLens 2 ARC](images/arc_warning.png)

1. <span data-ttu-id="f64a7-185">Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f64a7-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="f64a7-186">Depois que o dispositivo concluir a instalação e inicializar o back-up, do computador navegue até o Explorador de Arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f64a7-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Arquivo PPKG no computador na janela Explorador de Arquivos.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="f64a7-188">No HoloLens 2, pressione a combinação de botão a seguir para executar o Pacote de Provisionamento: Toque em **Volume** Para Baixo e **Botão** Desligar ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f64a7-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="f64a7-189">Você será solicitado a aplicar o Pacote de Provisionamento, selecione **Confirmar**</span><span class="sxs-lookup"><span data-stu-id="f64a7-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="f64a7-190">Depois que o pacote de provisionamento é concluído, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f64a7-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="f64a7-191">Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.</span><span class="sxs-lookup"><span data-stu-id="f64a7-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="f64a7-192">Manter</span><span class="sxs-lookup"><span data-stu-id="f64a7-192">Maintain</span></span>

<span data-ttu-id="f64a7-193">Com essa configuração, é recomendável reiniciar o processo acima e reaflar o dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer qualquer atualização no sistema operacional e/ou aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f64a7-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
