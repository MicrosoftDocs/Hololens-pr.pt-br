---
title: Desbloquear os recursos do Windows Holographic for Business
description: Quando você atualiza para o Windows Holographic for Business, o HoloLens fornece recursos adicionais que são projetados para os negócios.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308131"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Desbloquear os recursos do Windows Holographic for Business

> [!IMPORTANT]
> Esta página se aplica somente à 1ª gen de HoloLens.

O Microsoft HoloLens está disponível na *edição de desenvolvimento*, que executa o Windows Holographic (uma edição do Windows 10 projetada para o HoloLens) e, no [pacote comercial](hololens-commercial-features.md), que fornece recursos adicionais projetados para os negócios.

Ao comprar o Commercial Suite, você recebe uma licença que atualiza o Windows Holographic para o Windows Holographic for Business. Você pode aplicar essa licença ao dispositivo usando o [provedor de MDM (gerenciamento de dispositivo móvel)](#edition-upgrade-by-using-mdm) da organização ou um [pacote de provisionamento](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> No Windows 10, versão 1803, você pode verificar se o HoloLens foi atualizado para a Business Edition selecionando **configurações**  >  **sistema**.

## <a name="edition-upgrade-by-using-mdm"></a>Atualização de edição usando o MDM

A licença corporativa pode ser aplicada por qualquer provedor MDM que dê suporte ao [CSP (provedor de serviços de configuração) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). A versão mais recente da API Microsoft MDM dará suporte ao CSP WindowsLicensing.

Para obter as instruções passo a passo para atualizar o HoloLens usando Microsoft Intune, consulte [Atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).

 Em outros provedores MDM, as etapas específicas para configurar e implantar a política podem variar.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Atualização de edição usando um pacote de provisionamento

Pacotes de provisionamento são arquivos criados pela ferramenta Designer de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Criar um pacote de provisionamento que atualiza a edição do Windows Holographic

1. [Crie um pacote de provisionamento para o HoloLens.](hololens-provisioning.md)
1. Vá para **configurações de tempo de execução**  >  **EditionUpgrade** e selecione **EditionUpgradeWithLicense**.

    ![Atualizar a edição usando a configuração de licença selecionada](images/icd1.png)

1. Localize o arquivo de licença XML que foi fornecido quando você comprou o pacote comercial.

    > [!NOTE]
    > É possível definir [configurações adicionais no pacote de provisionamento](hololens-provisioning.md).

1. No menu **Arquivo**, selecione **Salvar**. 

1. Leia o aviso de que os arquivos de projeto podem conter informações confidenciais e clique em **OK**.

    > [!IMPORTANT]
    > Ao criar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (. ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluir os arquivos de projeto quando não forem mais necessários.

1. No menu **Exportar**, selecione **Pacote de provisionamento**.

1. Altere **proprietário** para **administrador de ti**, que define a precedência desse pacote de provisionamento como maior que outros aplicados a esse dispositivo de fontes diferentes e, em seguida, selecione **Avançar**.

1. Defina um valor para **Versão do Pacote**.

    > [!TIP]
    > Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes já aplicados.

1. Em **selecionar detalhes de segurança para o pacote de provisionamento**, selecione **Avançar**.

1. Selecione **Avançar** para especificar o local de saída em que você deseja que o pacote de provisionamento vá depois de compilado. Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.

    Opcionalmente, você pode selecionar **procurar** para alterar o local de saída padrão.

1. Selecione **Avançar**.

1. Selecione **Compilar** para começar a criar o pacote. A página de compilação exibe as informações do projeto e a barra de progresso indica o status da compilação.

1. Quando a compilação for concluída, selecione **concluir**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Aplicar o pacote de provisionamento ao HoloLens

1. Usando o cabo USB, conecte o dispositivo a um PC. Inicie o dispositivo, mas não continue após a página **ajustar** da experiência inicial de instalação (a primeira página com a caixa azul). No PC, o HoloLens aparece como um dispositivo no explorador de arquivos.

    > [!NOTE]
    > Se o dispositivo HoloLens estiver executando o Windows 10, versão 1607 ou anterior, abra o explorador de arquivos pressionando e soltando brevemente o **volume** e os botões de **energia** simultaneamente no dispositivo.

1. No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.

1. Embora o HoloLens ainda esteja na página **ajustar** , pressione brevemente e solte os botões de **volume** e **energia** simultaneamente.

1. O HoloLens pergunta se você confia no pacote e deseja aplicá-lo. Confirme que você confia no pacote.

1. Você verá se o pacote foi aplicado com êxito ou não. Se ele não foi aplicado com êxito, você pode corrigir o pacote e tentar novamente. Se for bem-sucedido, prossiga com a configuração do dispositivo.
