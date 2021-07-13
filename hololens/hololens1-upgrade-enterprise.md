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
# <a name="unlock-windows-holographic-for-business-features"></a>Desbloquear os recursos do Windows Holographic for Business

> [!IMPORTANT]
> Esta página se aplica somente HoloLens 1ª geração.

Microsoft HoloLens está disponível no *Development Edition,* que executa o Windows Holographic (uma edição do Windows 10 que foi projetada para HoloLens) e no [Commercial Suite](hololens-commercial-features.md), que fornece recursos extras projetados para negócios.

Ao comprar o Commercial Suite, você recebe uma licença que atualiza o Windows Holographic para o Windows Holographic for Business. Você pode aplicar essa licença ao dispositivo usando o provedor [de MDM (gerenciamento](#edition-upgrade-by-using-mdm) de dispositivo móvel) da organização ou um [pacote de provisionamento](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> No Windows 10, versão 1803, você pode verificar se o HoloLens foi atualizado para a edição de negócios selecionando **Configurações**  >  **Sistema**.

## <a name="edition-upgrade-by-using-mdm"></a>Atualização de edição usando o MDM

A licença corporativa pode ser aplicada por qualquer provedor MDM que dê suporte ao [CSP (provedor de serviços de configuração) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). A versão mais recente da API Microsoft MDM dará suporte ao CSP WindowsLicensing.

Para obter instruções passo a passo para atualizar HoloLens usando o Microsoft Intune, consulte Atualizar dispositivos que executam Windows [Holographic](/intune/holographic-upgrade)para Windows Holographic for Business .

 Em outros provedores MDM, as etapas específicas para configurar e implantar a política podem variar.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Atualização de edição usando um pacote de provisionamento

Pacotes de provisionamento são arquivos criados pela ferramenta Designer de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Criar um pacote de provisionamento que atualiza a edição do Windows Holographic

1. [Crie um pacote de provisionamento para HoloLens.](hololens-provisioning.md)
1. Vá para **Configurações de runtime**  >  **EditionGrade** e **selecione EditionUpgradeWithLicense**.

    ![Atualizar a edição usando a configuração de licença selecionada](images/icd1.png)

1. Encontre o arquivo de licença XML que foi fornecido quando você comprou o Commercial Suite.

    > [!NOTE]
    > É possível definir [configurações adicionais no pacote de provisionamento](hololens-provisioning.md).

1. No menu **Arquivo**, selecione **Salvar**. 

1. Leia o aviso de que os arquivos de projeto podem conter informações confidenciais e clique em **OK.**

    > [!IMPORTANT]
    > Ao criar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluir os arquivos de projeto quando não for mais necessário.

1. No menu **Exportar**, selecione **Pacote de provisionamento**.

1. Altere **Proprietário** para **Administrador** de IT, que define a precedência desse pacote de provisionamento para ser maior do que outras aplicadas a esse dispositivo de fontes diferentes e, em seguida, selecione **Próximo**.

1. Defina um valor para **Versão do Pacote**.

    > [!TIP]
    > Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes já aplicados.

1. Em **Selecionar detalhes de segurança para o pacote de provisionamento,** selecione **Próximo.**

1. Selecione **Próximo** para especificar o local de saída em que você deseja que o pacote de provisionamento vá quando ele for criado. Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.

    Opcionalmente, você pode selecionar **Procurar para** alterar o local de saída padrão.

1. Selecione **Avançar**.

1. Selecione **Build** para começar a criar o pacote. A página de build exibe as informações do projeto e a barra de progresso indica o status do build.

1. Quando o build for concluído, selecione **Concluir**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Aplicar o pacote de provisionamento ao HoloLens

1. Usando o cabo USB, conecte o dispositivo a um computador. Inicie o dispositivo, mas não continue após a página **de** ajuste da experiência de configuração inicial (a primeira página com a caixa azul). No computador, HoloLens aparece como um dispositivo no Explorador de Arquivos.

    > [!NOTE]
    > Se o dispositivo HoloLens estiver executando o Windows 10, versão 1607 ou anterior, abra o Explorador de Arquivos pressionando brevemente e liberando os botões **Volume Down** e **Power** simultaneamente no dispositivo.

1. No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.

1. Enquanto HoloLens ainda estiver na  página de ajuste, pressione e solte os botões **Volume Down** e **Power** simultaneamente novamente.

1. HoloLens pergunta se você confia no pacote e gostaria de aplicá-lo. Confirme que você confia no pacote.

1. Você verá se o pacote foi aplicado com êxito ou não. Se ele não tiver sido aplicado com êxito, você poderá corrigir o pacote e tentar novamente. Se for bem-sucedido, continue com a configuração do dispositivo.
