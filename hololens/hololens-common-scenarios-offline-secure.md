---
title: Cenários comuns – HoloLens offline seguro 2
description: Uma implantação segura offline e implantação de aplicativo por meio do provisionamento.
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080457"
---
# <span data-ttu-id="3c8b0-104">Cenários comuns – HoloLens offline seguro 2</span><span class="sxs-lookup"><span data-stu-id="3c8b0-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="3c8b0-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="3c8b0-105">Overview</span></span>
<span data-ttu-id="3c8b0-106">Este guia fornece orientação para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para ser usado em ambientes seguros com as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="3c8b0-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="3c8b0-107">Desative o WiFi.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-107">Disable WiFi.</span></span>
-   <span data-ttu-id="3c8b0-108">Desative o BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="3c8b0-109">Desative os microfones.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-109">Disable Microphones.</span></span>
-   <span data-ttu-id="3c8b0-110">Impede a adição ou a remoção de pacotes de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="3c8b0-111">Nenhum usuário pode habilitar qualquer um dos componentes restritos acima.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="3c8b0-112">Preparar</span><span class="sxs-lookup"><span data-stu-id="3c8b0-112">Prepare</span></span> 
<span data-ttu-id="3c8b0-113">Configuração do Windows 10 para PC</span><span class="sxs-lookup"><span data-stu-id="3c8b0-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="3c8b0-114">[Baixe o arquivo mais recente do sistema operacional do HoloLens 2](https://aka.ms/hololens2download) diretamente em um PC.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="3c8b0-115">O suporte para essa configuração está incluído no Build 19041,1117 e versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="3c8b0-116">Baixar/instalar a ferramenta avançado de recuperação (ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para seu PC</span><span class="sxs-lookup"><span data-stu-id="3c8b0-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="3c8b0-117">Baixe/instale a ferramenta de configuração mais recente do [Windows Configuration designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store para seu PC.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="3c8b0-118">[Baixe a pasta OfflineSecureHL2_Sample com os arquivos do projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="3c8b0-119">Prepare seu [aplicativo de linha de negócios offline para a implantação do PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="3c8b0-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="3c8b0-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="3c8b0-120">Configure</span></span>
<span data-ttu-id="3c8b0-121">Criar um pacote de provisionamento de configuração segura</span><span class="sxs-lookup"><span data-stu-id="3c8b0-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="3c8b0-122">Inicie a ferramenta WCD em seu computador.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="3c8b0-123">Selecione **arquivo – > Abrir projeto**.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="3c8b0-124">Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="3c8b0-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="3c8b0-125">O projeto deve abrir e agora você deve ter uma lista de personalizações disponíveis:</span><span class="sxs-lookup"><span data-stu-id="3c8b0-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto em WCD](images/offline-secure-sample-wcd.png)

<span data-ttu-id="3c8b0-127">Configurações definidas neste pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="3c8b0-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="3c8b0-128">Item</span><span class="sxs-lookup"><span data-stu-id="3c8b0-128">Item</span></span>                                                |     <span data-ttu-id="3c8b0-129">Configuração</span><span class="sxs-lookup"><span data-stu-id="3c8b0-129">Setting</span></span>                       |     <span data-ttu-id="3c8b0-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c8b0-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="3c8b0-131">Contas/usuários</span><span class="sxs-lookup"><span data-stu-id="3c8b0-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="3c8b0-132">Nome de usuário local & senha</span><span class="sxs-lookup"><span data-stu-id="3c8b0-132">Local User Name & Password</span></span>    |     <span data-ttu-id="3c8b0-133">Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="3c8b0-134">Primeira experiência/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="3c8b0-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="3c8b0-135">True</span><span class="sxs-lookup"><span data-stu-id="3c8b0-135">True</span></span>                          |     <span data-ttu-id="3c8b0-136">Ignora a calibragem durante a configuração inicial do dispositivo apenas</span><span class="sxs-lookup"><span data-stu-id="3c8b0-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="3c8b0-137">Primeira experiência/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="3c8b0-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="3c8b0-138">True</span><span class="sxs-lookup"><span data-stu-id="3c8b0-138">True</span></span>                          |     <span data-ttu-id="3c8b0-139">Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="3c8b0-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="3c8b0-140">Primeira experiência/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="3c8b0-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="3c8b0-141">True</span><span class="sxs-lookup"><span data-stu-id="3c8b0-141">True</span></span>                          |     <span data-ttu-id="3c8b0-142">Ignora a configuração de Wi-Fi durante a configuração inicial do dispositivo</span><span class="sxs-lookup"><span data-stu-id="3c8b0-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="3c8b0-143">Políticas/conectividade/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="3c8b0-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="3c8b0-144">Não</span><span class="sxs-lookup"><span data-stu-id="3c8b0-144">No</span></span>                            |     <span data-ttu-id="3c8b0-145">Desabilita o Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3c8b0-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="3c8b0-146">Políticas/experiência/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="3c8b0-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="3c8b0-147">Não</span><span class="sxs-lookup"><span data-stu-id="3c8b0-147">No</span></span>                            |     <span data-ttu-id="3c8b0-148">Desabilita a Cortana (para eliminar problemas em potencial, pois os microfones estão desativados)</span><span class="sxs-lookup"><span data-stu-id="3c8b0-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="3c8b0-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="3c8b0-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="3c8b0-150">Sim</span><span class="sxs-lookup"><span data-stu-id="3c8b0-150">Yes</span></span>                           |     <span data-ttu-id="3c8b0-151">Desabilita o microfone</span><span class="sxs-lookup"><span data-stu-id="3c8b0-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="3c8b0-152">Políticas/privacidade/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="3c8b0-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="3c8b0-153">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="3c8b0-153">Force deny</span></span>                    |     <span data-ttu-id="3c8b0-154">Impede que os aplicativos tentem acessar dados de localização (para eliminar problemas em potencial porque o rastreamento de localização está desabilitado)</span><span class="sxs-lookup"><span data-stu-id="3c8b0-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="3c8b0-155">Políticas/privacidade/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="3c8b0-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="3c8b0-156">Forçar negação</span><span class="sxs-lookup"><span data-stu-id="3c8b0-156">Force deny</span></span>                    |     <span data-ttu-id="3c8b0-157">Impede que os aplicativos tentem acessar microfones (para eliminar problemas potenciais, já que os microfones estão desativados)</span><span class="sxs-lookup"><span data-stu-id="3c8b0-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="3c8b0-158">Políticas/segurança/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="3c8b0-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="3c8b0-159">Não</span><span class="sxs-lookup"><span data-stu-id="3c8b0-159">No</span></span>                            |     <span data-ttu-id="3c8b0-160">Impede que qualquer pessoa Adicione pacotes de provisionamento que podem tentar substituir políticas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="3c8b0-161">Políticas/segurança/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="3c8b0-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="3c8b0-162">Não</span><span class="sxs-lookup"><span data-stu-id="3c8b0-162">No</span></span>                            |     <span data-ttu-id="3c8b0-163">Impede que qualquer pessoa Remova esse pacote de provisionamento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="3c8b0-164">Políticas/sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="3c8b0-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="3c8b0-165">Não</span><span class="sxs-lookup"><span data-stu-id="3c8b0-165">No</span></span>                            |     <span data-ttu-id="3c8b0-166">Impede que o dispositivo tente acompanhar os dados de localização.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="3c8b0-167">Políticas/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="3c8b0-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="3c8b0-168">Não</span><span class="sxs-lookup"><span data-stu-id="3c8b0-168">No</span></span>                            |     <span data-ttu-id="3c8b0-169">Desabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3c8b0-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="3c8b0-170">Em configurações de tempo de execução, selecione **contas/usuários/nome de usuário: holo/senha**</span><span class="sxs-lookup"><span data-stu-id="3c8b0-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="3c8b0-171">Anote a senha e redefina se desejado.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="3c8b0-172">Navegue até UniversalAppInstall/UserContextApp e [Configure o aplicativo LOB](app-deploy-provisioning-package.md) que você vai implantar nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo em WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="3c8b0-174">Depois de concluir, selecione o botão "exportar" e siga todos os avisos até que o pacote de provisionamento seja criado.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar deste pacote em WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="3c8b0-176">Implantar</span><span class="sxs-lookup"><span data-stu-id="3c8b0-176">Deploy</span></span>
1. <span data-ttu-id="3c8b0-177">Conecte o HL2 ao seu PC Windows 10 via cabo USB.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="3c8b0-178">Iniciar a ferramenta ARC e selecionar **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="3c8b0-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="3c8b0-179">Na tela seguinte, selecione **seleção manual do pacote**.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="3c8b0-180">Navegue até o arquivo. FFU baixado anteriormente e selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="3c8b0-181">Na página de aviso, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="3c8b0-182">Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="3c8b0-183">Depois que o dispositivo concluir o backup da instalação e inicialização, no seu computador, navegue até explorador de arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![PPKG arquivo no PC na janela do explorador de arquivos.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="3c8b0-185">No HoloLens 2, pressione a combinação de botões a seguir para executar o pacote de provisionamento: toque em **volume para baixo** e **botão de energia** ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="3c8b0-186">Você será solicitado a aplicar o pacote de provisionamento, selecionar **confirmar**</span><span class="sxs-lookup"><span data-stu-id="3c8b0-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="3c8b0-187">Depois que o pacote de provisionamento terminar, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="3c8b0-188">Em seguida, você deve ser solicitado a conectar-se ao dispositivo com a conta local e a senha compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="3c8b0-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="3c8b0-189">Manter</span><span class="sxs-lookup"><span data-stu-id="3c8b0-189">Maintain</span></span>
<span data-ttu-id="3c8b0-190">Com essa configuração, é recomendável reiniciar o processo acima e reativar o dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer atualizações para o sistema operacional e/ou aplicativo (s).</span><span class="sxs-lookup"><span data-stu-id="3c8b0-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

