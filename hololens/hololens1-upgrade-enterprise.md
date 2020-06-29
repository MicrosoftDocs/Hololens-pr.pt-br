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
# Desbloquear os recursos do Windows Holographic for Business

> [!IMPORTANT]
> Esta página aplica-se apenas à 1ª Gen do HoloLens.

O Microsoft HoloLens está disponível na *edição de desenvolvimento*, que executa o Windows holográfico (uma edição do Windows 10 desenvolvida para o HoloLens) e no [pacote comercial](hololens-commercial-features.md), que fornece recursos adicionais projetados para negócios.

Ao comprar o Commercial Suite, você recebe uma licença que atualiza o Windows Holographic para o Windows Holographic for Business. Você pode aplicar essa licença ao dispositivo usando o [provedor de gerenciamento de dispositivos móveis (MDM)](#edition-upgrade-by-using-mdm) da organização ou um [pacote de provisionamento](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> No Windows 10, versão 1803, você pode verificar se o HoloLens foi atualizado para o Business Edition selecionando sistema de **configurações**  >  **System**.

## Atualização de edição usando o MDM

A licença corporativa pode ser aplicada por qualquer provedor MDM que dê suporte ao [CSP (provedor de serviços de configuração) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). A versão mais recente da API Microsoft MDM dará suporte ao CSP WindowsLicensing.

Para obter instruções passo a passo para atualizar o HoloLens usando o Microsoft Intune, consulte [Atualizar dispositivos que executam o Windows holográfico para o Windows holográfico for Business](https://docs.microsoft.com/intune/holographic-upgrade).

 Em outros provedores MDM, as etapas específicas para configurar e implantar a política podem variar.

## Atualização de edição usando um pacote de provisionamento

Pacotes de provisionamento são arquivos criados pela ferramenta Designer de Configuração do Windows que aplicam uma configuração especificada a um dispositivo.

### Criar um pacote de provisionamento que atualiza a edição do Windows Holographic

1. [Crie um pacote de provisionamento para o HoloLens.](hololens-provisioning.md)
1. Vá até **Configurações de tempo de execução** > **EditionUpgrade** e selecione **EditionUpgradeWithLicense**.

    ![Atualizar a edição usando a configuração de licença selecionada](images/icd1.png)

1. Localize o arquivo de licença XML fornecido ao comprar o pacote comercial.

    > [!NOTE]
    > É possível definir [configurações adicionais no pacote de provisionamento](hololens-provisioning.md).

1. No menu **arquivo** , selecione **salvar**. 

1. Leia o aviso de que os arquivos do Project podem conter informações confidenciais e clique em **OK**.

    > [!IMPORTANT]
    > Ao criar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (. ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluir os arquivos de projeto quando não forem mais necessários.

1. No menu **Exportar**, selecione **Pacote de provisionamento**.

1. Altere o **proprietário** para o **administrador de ti**, que define a precedência deste pacote de provisionamento para ser maior do que outras pessoas aplicadas a este dispositivo de fontes diferentes e, em seguida, selecione **Avançar**.

1. Defina um valor para **Versão do Pacote**.

    > [!TIP]
    > Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes previamente aplicados.

1. Em **selecionar detalhes de segurança para o pacote de provisionamento**, selecione **Avançar**.

1. Selecione **Avançar** para especificar o local de saída onde você deseja que o pacote de provisionamento se torne depois de criado. Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.

    Opcionalmente, você pode selecionar **procurar** para alterar o local de saída padrão.

1. Selecione **Avançar**.

1. Selecione **Compilar** para começar a criar o pacote. A página construir exibe as informações do projeto e a barra de progresso indica o status da compilação.

1. Quando a compilação for concluída, selecione **concluir**.

### Aplicar o pacote de provisionamento ao HoloLens

1. Usando o cabo USB, conecte o dispositivo a um computador. Inicie o dispositivo, mas não continue após a página **ajustar** da experiência de configuração inicial (a primeira página com a caixa azul). No computador, o HoloLens aparece como um dispositivo no explorador de arquivos.

    > [!NOTE]
    > Se o dispositivo HoloLens estiver executando o Windows 10, versão 1607 ou anterior, abra o explorador de arquivos e, em seguida, solte os botões de **volume baixo** e **energia** simultaneamente no dispositivo.

1. No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.

1. Embora o HoloLens ainda esteja na página **ajustar** , pressione brevemente e solte os botões de **volume baixo** e **energia** simultaneamente.

1. O HoloLens pergunta se você confia no pacote e gostaria de aplicá-lo. Confirme que você confia no pacote.

1. Você verá se o pacote foi aplicado com êxito ou não. Se a aplicação não foi bem-sucedida, você pode corrigir o pacote e tentar novamente. Se tiver êxito, prossiga com a instalação do dispositivo.
