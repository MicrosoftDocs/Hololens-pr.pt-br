---
title: HoloLens Criptografia do BitLocker
description: saiba como habilitar a criptografia de dispositivo BitLocker para proteger arquivos armazenados em seus HoloLens dispositivos de realidade misturada.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635238"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="cca98-103">Criptografia BitLocker do HoloLens (1ª geração)</span><span class="sxs-lookup"><span data-stu-id="cca98-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="cca98-104">HoloLens (1º gen) e HoloLens 2 dão suporte à criptografia de dispositivo usando o bitlocker, no entanto, o BitLocker sempre é habilitado no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cca98-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="cca98-105">este artigo o ajudará a habilitar e gerenciar o BitLocker em HoloLens (1ª gen).</span><span class="sxs-lookup"><span data-stu-id="cca98-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="cca98-106">em HoloLens (1ª gen), você pode habilitar a criptografia de dispositivo do BitLocker manualmente ou usando o MDM (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="cca98-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="cca98-107">Siga estas instruções para habilitar a [criptografia de dispositivo BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger arquivos e informações armazenadas no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cca98-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="cca98-108">A criptografia de dispositivo ajuda a proteger seus dados usando o método de criptografia AES-CBC 128, que é equivalente ao [método 3 do EncryptionMethodByDriveType](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) no provedor de serviços de configuração do BITLOCKER (CSP).</span><span class="sxs-lookup"><span data-stu-id="cca98-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="cca98-109">A equipe que tem a chave de criptografia correta (como uma senha) pode descriptografá-la ou executar uma recuperação de dados.</span><span class="sxs-lookup"><span data-stu-id="cca98-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="cca98-110">Habilitar a criptografia de dispositivo usando o MDM</span><span class="sxs-lookup"><span data-stu-id="cca98-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="cca98-111">Você pode usar seu provedor de MDM (gerenciamento de dispositivo móvel) para aplicar uma política que requer criptografia de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cca98-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="cca98-112">A política a ser usada é a [configuração de segurança/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) no CSP de política.</span><span class="sxs-lookup"><span data-stu-id="cca98-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="cca98-113">Consulte as instruções para habilitar a criptografia de dispositivo usando Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="cca98-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="cca98-114">Para outras ferramentas MDM, consulte a documentação do seu provedor MDM para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="cca98-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="cca98-115">Se o seu provedor de MDM exigir um URI personalizado para criptografia de dispositivo, use a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="cca98-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="cca98-116">**Nome**: um nome de sua escolha</span><span class="sxs-lookup"><span data-stu-id="cca98-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="cca98-117">**Descrição**: opcional</span><span class="sxs-lookup"><span data-stu-id="cca98-117">**Description**: optional</span></span>
- <span data-ttu-id="cca98-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="cca98-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="cca98-119">**Tipo de dados**: inteiro</span><span class="sxs-lookup"><span data-stu-id="cca98-119">**Data type**: integer</span></span>
- <span data-ttu-id="cca98-120">**Valor**: `1`</span><span class="sxs-lookup"><span data-stu-id="cca98-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="cca98-121">Habilitar a criptografia de dispositivo usando um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="cca98-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="cca98-122">Pacotes de provisionamento são arquivos criados pela ferramenta Designer de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cca98-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="cca98-123">criar um pacote de provisionamento que atualiza o Windows Holographic edition e habilita a criptografia</span><span class="sxs-lookup"><span data-stu-id="cca98-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="cca98-124">Crie um pacote de provisionamento para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cca98-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="cca98-125">Vá para **configurações de tempo de execução**  >  **políticas**  >  **segurança** e selecione **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="cca98-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![A configuração Exigir criptografia de dispositivo está definida como Sim](images/device-encryption.png)

1. <span data-ttu-id="cca98-127">Localize o arquivo de licença XML que foi fornecido quando você comprou o pacote comercial.</span><span class="sxs-lookup"><span data-stu-id="cca98-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="cca98-128">Procure e selecione o arquivo de licença XML que foi fornecido quando você comprou o Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="cca98-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cca98-129">É possível definir [configurações adicionais no pacote de provisionamento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="cca98-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="cca98-130">No menu **Arquivo**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cca98-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="cca98-131">Leia o aviso explicando que os arquivos de projeto podem conter informações confidenciais e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cca98-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cca98-132">Ao criar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="cca98-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="cca98-133">Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados.</span><span class="sxs-lookup"><span data-stu-id="cca98-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="cca98-134">Você deve armazenar os arquivos de projeto em um local seguro e excluir os arquivos de projeto quando não forem mais necessários.</span><span class="sxs-lookup"><span data-stu-id="cca98-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="cca98-135">No menu **Exportar**, clique em **Pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="cca98-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="cca98-136">Altere **proprietário** para **administrador de ti**, que definirá a precedência desse pacote de provisionamento superior ao provisionamento de pacotes aplicados a este dispositivo de outras fontes e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cca98-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="cca98-137">Defina um valor para **Versão do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="cca98-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="cca98-138">Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes já aplicados.</span><span class="sxs-lookup"><span data-stu-id="cca98-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="cca98-139">Em **Selecionar os detalhes de segurança do pacote de provisionamento**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cca98-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="cca98-140">Clique em **Avançar** para especificar o local de saída do pacote de provisionamento quando ele estiver compilado.</span><span class="sxs-lookup"><span data-stu-id="cca98-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="cca98-141">Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.</span><span class="sxs-lookup"><span data-stu-id="cca98-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="cca98-142">Como alternativa, clique em Procurar para alterar o local de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="cca98-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="cca98-143">Clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="cca98-143">Click **Next**.</span></span>
1. <span data-ttu-id="cca98-144">Clique em **Compilar** para começar a criar o pacote.</span><span class="sxs-lookup"><span data-stu-id="cca98-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="cca98-145">As informações do projeto são exibidas na página de compilação, e a barra de progresso indica o status da compilação.</span><span class="sxs-lookup"><span data-stu-id="cca98-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="cca98-146">Quando o processo for concluído, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="cca98-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="cca98-147">Aplicar o pacote de provisionamento ao HoloLens</span><span class="sxs-lookup"><span data-stu-id="cca98-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="cca98-148">Conecte o dispositivo via USB a um computador e inicie o dispositivo, mas não continue depois da página **fit** da experiência de configuração inicial (a primeira página com a caixa azul).</span><span class="sxs-lookup"><span data-stu-id="cca98-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="cca98-149">Pressione e solte rapidamente os botões de **Menos Volume** e **Ligar/Desligar** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="cca98-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="cca98-150">O HoloLens será mostrado como um dispositivo no Explorador de Arquivos no computador.</span><span class="sxs-lookup"><span data-stu-id="cca98-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="cca98-151">No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cca98-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="cca98-152">Pressione e solte rapidamente os botões **Menos Volume** e **Ligar/Desligar** simultaneamente mais uma vez enquanto estiver na página **fit**.</span><span class="sxs-lookup"><span data-stu-id="cca98-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="cca98-153">O dispositivo perguntará se você confia no pacote e se gostaria de aplicá-lo.</span><span class="sxs-lookup"><span data-stu-id="cca98-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="cca98-154">Confirme que você confia no pacote.</span><span class="sxs-lookup"><span data-stu-id="cca98-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="cca98-155">Você verá se o pacote foi aplicado com êxito ou não.</span><span class="sxs-lookup"><span data-stu-id="cca98-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="cca98-156">Se ele falhar, você poderá corrigir o pacote e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="cca98-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="cca98-157">Se ele for bem-sucedido, continue com a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cca98-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="cca98-158">Se o dispositivo tiver sido comprado antes de agosto de 2016, você precisará entrar no dispositivo usando uma conta da Microsoft, obter a atualização mais recente do sistema operacional e redefini-lo para aplicar o pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="cca98-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="cca98-159">Verificar a criptografia de dispositivo</span><span class="sxs-lookup"><span data-stu-id="cca98-159">Verify device encryption</span></span>

<span data-ttu-id="cca98-160">A criptografia é silenciosa no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cca98-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="cca98-161">Para verificar o status de criptografia do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="cca98-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="cca98-162">no HoloLens, vá para **Configurações**  >  **sistema**  >  **sobre**.</span><span class="sxs-lookup"><span data-stu-id="cca98-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="cca98-163">O **BitLocker** será **habilitado** se o dispositivo estiver criptografado.</span><span class="sxs-lookup"><span data-stu-id="cca98-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Tela sobre mostrando BitLocker habilitado](images/about-encryption.png)
