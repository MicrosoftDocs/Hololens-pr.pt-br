---
title: Desbloquear os recursos do Windows Holographic for Business
description: Ao atualizar para o Windows holográfico for Business, o HoloLens fornece recursos extras projetados para empresas.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827735"
---
# <span data-ttu-id="0595a-103">Desbloquear os recursos do Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="0595a-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0595a-104">Esta página aplica-se apenas à 1ª Gen do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0595a-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="0595a-105">O Microsoft HoloLens está disponível na *edição de desenvolvimento*, que executa o Windows holográfico (uma edição do Windows 10 desenvolvida para o HoloLens) e no [pacote comercial](hololens-commercial-features.md), que fornece recursos adicionais projetados para negócios.</span><span class="sxs-lookup"><span data-stu-id="0595a-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="0595a-106">Ao comprar o Commercial Suite, você recebe uma licença que atualiza o Windows Holographic para o Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="0595a-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="0595a-107">Você pode aplicar essa licença ao dispositivo usando o [provedor de gerenciamento de dispositivos móveis (MDM)](#edition-upgrade-by-using-mdm) da organização ou um [pacote de provisionamento](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="0595a-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="0595a-108">No Windows 10, versão 1803, você pode verificar se o HoloLens foi atualizado para o Business Edition selecionando sistema de **configurações**  >  **System**.</span><span class="sxs-lookup"><span data-stu-id="0595a-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="0595a-109">Atualização de edição usando o MDM</span><span class="sxs-lookup"><span data-stu-id="0595a-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="0595a-110">A licença corporativa pode ser aplicada por qualquer provedor MDM que dê suporte ao [CSP (provedor de serviços de configuração) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="0595a-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="0595a-111">A versão mais recente da API Microsoft MDM dará suporte ao CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="0595a-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="0595a-112">Para obter instruções passo a passo para atualizar o HoloLens usando o Microsoft Intune, consulte [Atualizar dispositivos que executam o Windows holográfico para o Windows holográfico for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="0595a-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="0595a-113">Em outros provedores MDM, as etapas específicas para configurar e implantar a política podem variar.</span><span class="sxs-lookup"><span data-stu-id="0595a-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="0595a-114">Atualização de edição usando um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="0595a-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="0595a-115">Pacotes de provisionamento são arquivos criados pela ferramenta Designer de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0595a-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="0595a-116">Criar um pacote de provisionamento que atualiza a edição do Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="0595a-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="0595a-117">Crie um pacote de provisionamento para o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0595a-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="0595a-118">Vá até **Configurações de tempo de execução** > **EditionUpgrade** e selecione **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="0595a-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Atualizar a edição usando a configuração de licença selecionada](images/icd1.png)

1. <span data-ttu-id="0595a-120">Localize o arquivo de licença XML fornecido ao comprar o pacote comercial.</span><span class="sxs-lookup"><span data-stu-id="0595a-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0595a-121">É possível definir [configurações adicionais no pacote de provisionamento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="0595a-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="0595a-122">No menu **arquivo** , selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="0595a-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="0595a-123">Leia o aviso de que os arquivos do Project podem conter informações confidenciais e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0595a-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0595a-124">Ao criar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="0595a-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="0595a-125">Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados.</span><span class="sxs-lookup"><span data-stu-id="0595a-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="0595a-126">Você deve armazenar os arquivos de projeto em um local seguro e excluir os arquivos de projeto quando não forem mais necessários.</span><span class="sxs-lookup"><span data-stu-id="0595a-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="0595a-127">No menu **Exportar**, selecione **Pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="0595a-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="0595a-128">Altere o **proprietário** para o **administrador de ti**, que define a precedência deste pacote de provisionamento para ser maior do que outras pessoas aplicadas a este dispositivo de fontes diferentes e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0595a-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="0595a-129">Defina um valor para **Versão do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="0595a-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0595a-130">Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes previamente aplicados.</span><span class="sxs-lookup"><span data-stu-id="0595a-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="0595a-131">Em **selecionar detalhes de segurança para o pacote de provisionamento**, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0595a-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="0595a-132">Selecione **Avançar** para especificar o local de saída onde você deseja que o pacote de provisionamento se torne depois de criado.</span><span class="sxs-lookup"><span data-stu-id="0595a-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="0595a-133">Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.</span><span class="sxs-lookup"><span data-stu-id="0595a-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="0595a-134">Opcionalmente, você pode selecionar **procurar** para alterar o local de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="0595a-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="0595a-135">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0595a-135">Select **Next**.</span></span>

1. <span data-ttu-id="0595a-136">Selecione **Compilar** para começar a criar o pacote.</span><span class="sxs-lookup"><span data-stu-id="0595a-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="0595a-137">A página construir exibe as informações do projeto e a barra de progresso indica o status da compilação.</span><span class="sxs-lookup"><span data-stu-id="0595a-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="0595a-138">Quando a compilação for concluída, selecione **concluir**.</span><span class="sxs-lookup"><span data-stu-id="0595a-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="0595a-139">Aplicar o pacote de provisionamento ao HoloLens</span><span class="sxs-lookup"><span data-stu-id="0595a-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="0595a-140">Usando o cabo USB, conecte o dispositivo a um computador.</span><span class="sxs-lookup"><span data-stu-id="0595a-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="0595a-141">Inicie o dispositivo, mas não continue após a página **ajustar** da experiência de configuração inicial (a primeira página com a caixa azul).</span><span class="sxs-lookup"><span data-stu-id="0595a-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="0595a-142">No computador, o HoloLens aparece como um dispositivo no explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="0595a-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0595a-143">Se o dispositivo HoloLens estiver executando o Windows 10, versão 1607 ou anterior, abra o explorador de arquivos e, em seguida, solte os botões de **volume baixo** e **energia** simultaneamente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0595a-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="0595a-144">No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0595a-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="0595a-145">Embora o HoloLens ainda esteja na página **ajustar** , pressione brevemente e solte os botões de **volume baixo** e **energia** simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="0595a-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="0595a-146">O HoloLens pergunta se você confia no pacote e gostaria de aplicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0595a-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="0595a-147">Confirme que você confia no pacote.</span><span class="sxs-lookup"><span data-stu-id="0595a-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="0595a-148">Você verá se o pacote foi aplicado com êxito ou não.</span><span class="sxs-lookup"><span data-stu-id="0595a-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="0595a-149">Se a aplicação não foi bem-sucedida, você pode corrigir o pacote e tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="0595a-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="0595a-150">Se tiver êxito, prossiga com a instalação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0595a-150">If successful, proceed with device setup.</span></span>
