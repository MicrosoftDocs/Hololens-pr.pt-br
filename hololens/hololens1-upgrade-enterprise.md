---
title: Desbloquear os recursos do Windows Holographic for Business
description: Quando você atualiza para Windows Holographic for Business, o HoloLens fornece recursos adicionais projetados para empresas.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635187"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="e3c13-103">Desbloquear os recursos do Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="e3c13-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3c13-104">Esta página se aplica somente HoloLens 1ª geração.</span><span class="sxs-lookup"><span data-stu-id="e3c13-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="e3c13-105">Microsoft HoloLens está disponível no *Development Edition,* que executa o Windows Holographic (uma edição do Windows 10 que foi projetada para HoloLens) e no [Commercial Suite](hololens-commercial-features.md), que fornece recursos extras projetados para negócios.</span><span class="sxs-lookup"><span data-stu-id="e3c13-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="e3c13-106">Ao comprar o Commercial Suite, você recebe uma licença que atualiza o Windows Holographic para o Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="e3c13-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="e3c13-107">Você pode aplicar essa licença ao dispositivo usando o provedor [de MDM (gerenciamento](#edition-upgrade-by-using-mdm) de dispositivo móvel) da organização ou um [pacote de provisionamento](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="e3c13-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="e3c13-108">No Windows 10, versão 1803, você pode verificar se o HoloLens foi atualizado para a edição de negócios selecionando **Configurações**  >  **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="e3c13-109">Atualização de edição usando o MDM</span><span class="sxs-lookup"><span data-stu-id="e3c13-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="e3c13-110">A licença corporativa pode ser aplicada por qualquer provedor MDM que dê suporte ao [CSP (provedor de serviços de configuração) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="e3c13-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="e3c13-111">A versão mais recente da API Microsoft MDM dará suporte ao CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="e3c13-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="e3c13-112">Para obter instruções passo a passo para atualizar HoloLens usando o Microsoft Intune, consulte Atualizar dispositivos que executam Windows [Holographic](/intune/holographic-upgrade)para Windows Holographic for Business .</span><span class="sxs-lookup"><span data-stu-id="e3c13-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="e3c13-113">Em outros provedores MDM, as etapas específicas para configurar e implantar a política podem variar.</span><span class="sxs-lookup"><span data-stu-id="e3c13-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="e3c13-114">Atualização de edição usando um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="e3c13-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="e3c13-115">Pacotes de provisionamento são arquivos criados pela ferramenta Designer de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3c13-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="e3c13-116">Criar um pacote de provisionamento que atualiza a edição do Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="e3c13-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="e3c13-117">Crie um pacote de provisionamento para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e3c13-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="e3c13-118">Vá para **Configurações de runtime**  >  **EditionGrade** e **selecione EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Atualizar a edição usando a configuração de licença selecionada](images/icd1.png)

1. <span data-ttu-id="e3c13-120">Encontre o arquivo de licença XML que foi fornecido quando você comprou o Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="e3c13-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3c13-121">É possível definir [configurações adicionais no pacote de provisionamento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="e3c13-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="e3c13-122">No menu **Arquivo**, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="e3c13-123">Leia o aviso de que os arquivos de projeto podem conter informações confidenciais e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="e3c13-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e3c13-124">Ao criar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="e3c13-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="e3c13-125">Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados.</span><span class="sxs-lookup"><span data-stu-id="e3c13-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="e3c13-126">Você deve armazenar os arquivos de projeto em um local seguro e excluir os arquivos de projeto quando não for mais necessário.</span><span class="sxs-lookup"><span data-stu-id="e3c13-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="e3c13-127">No menu **Exportar**, selecione **Pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="e3c13-128">Altere **Proprietário** para **Administrador** de IT, que define a precedência desse pacote de provisionamento para ser maior do que outras aplicadas a esse dispositivo de fontes diferentes e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="e3c13-129">Defina um valor para **Versão do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="e3c13-130">Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes já aplicados.</span><span class="sxs-lookup"><span data-stu-id="e3c13-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="e3c13-131">Em **Selecionar detalhes de segurança para o pacote de provisionamento,** selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="e3c13-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="e3c13-132">Selecione **Próximo** para especificar o local de saída em que você deseja que o pacote de provisionamento vá quando ele for criado.</span><span class="sxs-lookup"><span data-stu-id="e3c13-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="e3c13-133">Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.</span><span class="sxs-lookup"><span data-stu-id="e3c13-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="e3c13-134">Opcionalmente, você pode selecionar **Procurar para** alterar o local de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="e3c13-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="e3c13-135">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-135">Select **Next**.</span></span>

1. <span data-ttu-id="e3c13-136">Selecione **Build** para começar a criar o pacote.</span><span class="sxs-lookup"><span data-stu-id="e3c13-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="e3c13-137">A página de build exibe as informações do projeto e a barra de progresso indica o status do build.</span><span class="sxs-lookup"><span data-stu-id="e3c13-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="e3c13-138">Quando o build for concluído, selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="e3c13-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="e3c13-139">Aplicar o pacote de provisionamento ao HoloLens</span><span class="sxs-lookup"><span data-stu-id="e3c13-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="e3c13-140">Usando o cabo USB, conecte o dispositivo a um computador.</span><span class="sxs-lookup"><span data-stu-id="e3c13-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="e3c13-141">Inicie o dispositivo, mas não continue após a página **de** ajuste da experiência de configuração inicial (a primeira página com a caixa azul).</span><span class="sxs-lookup"><span data-stu-id="e3c13-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="e3c13-142">No computador, HoloLens aparece como um dispositivo no Explorador de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="e3c13-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3c13-143">Se o dispositivo HoloLens estiver executando o Windows 10, versão 1607 ou anterior, abra o Explorador de Arquivos pressionando brevemente e liberando os botões **Volume Down** e **Power** simultaneamente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3c13-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="e3c13-144">No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3c13-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="e3c13-145">Enquanto HoloLens ainda estiver na  página de ajuste, pressione e solte os botões **Volume Down** e **Power** simultaneamente novamente.</span><span class="sxs-lookup"><span data-stu-id="e3c13-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="e3c13-146">HoloLens pergunta se você confia no pacote e gostaria de aplicá-lo.</span><span class="sxs-lookup"><span data-stu-id="e3c13-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="e3c13-147">Confirme que você confia no pacote.</span><span class="sxs-lookup"><span data-stu-id="e3c13-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="e3c13-148">Você verá se o pacote foi aplicado com êxito ou não.</span><span class="sxs-lookup"><span data-stu-id="e3c13-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="e3c13-149">Se ele não tiver sido aplicado com êxito, você poderá corrigir o pacote e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="e3c13-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="e3c13-150">Se for bem-sucedido, continue com a configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3c13-150">If successful, proceed with device setup.</span></span>
