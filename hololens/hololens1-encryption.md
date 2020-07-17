---
title: Criptografia BitLocker HoloLens
description: Habilitar criptografia de dispositivo do Bitlocker para proteger arquivos armazenados no HoloLens
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
ms.openlocfilehash: 5ab35f0804c6a906cb0bb262211e8ae5ab017459
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865642"
---
# Criptografia de BitLocker do HoloLens (1ª gen)

O HoloLens (1ª gen) e o HoloLens 2 dão suporte à criptografia de dispositivo usando o BitLocker, no entanto, o BitLocker sempre é habilitado no HoloLens 2.

Este artigo ajudará você a habilitar e gerenciar o BitLocker no HoloLens (1ª gen).

No HoloLens (1ª gen), você pode habilitar a criptografia de dispositivo BitLocker manualmente ou usar o gerenciamento de dispositivos móveis (MDM). Siga estas instruções para habilitar a [criptografia de dispositivo BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger arquivos e informações armazenados no HoloLens. A criptografia de dispositivo ajuda a proteger seus dados usando o método de criptografia AES-CBC 128, que equivale ao [método 3 do EncryptionMethodByDriveType](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) no provedor de serviços de configuração do BITLOCKER (CSP). O pessoal que tem a chave de criptografia correta (como uma senha) pode descriptografá-la ou executar uma recuperação de dados.

## Habilitar a criptografia de dispositivo usando o MDM

Você pode usar seu provedor de gerenciamento de dispositivo móvel (MDM) para aplicar uma política que exija criptografia de dispositivo. A política a ser usada é a [configuração segurança/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) no CSP da política.

[Confira instruções para habilitar a criptografia de dispositivo usando o Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Para outras ferramentas MDM, consulte a documentação do seu provedor MDM para obter instruções. Se o seu provedor de MDM exigir um URI personalizado para a criptografia do dispositivo, use a seguinte configuração:

- **Nome**: um nome de sua escolha
- **Descrição**: opcional
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Tipo de dados**: inteiro
- **Valor**: `1`

## Habilitar a criptografia de dispositivo usando um pacote de provisionamento

Pacotes de provisionamento são arquivos criados pela ferramenta Designer de Configuração do Windows que aplicam uma configuração especificada a um dispositivo. 

### Criar um pacote de provisionamento que atualize a edição do Windows holográfico e habilita a criptografia

1. [Crie um pacote de provisionamento para o HoloLens.](hololens-provisioning.md)
1. Acesse **Configurações de tempo de execução** > **Políticas** > **Segurança** e selecione **RequireDeviceEncryption**.

    ![A configuração Exigir criptografia de dispositivo está definida como Sim](images/device-encryption.png)

1. Localize o arquivo de licença XML fornecido ao comprar o pacote comercial.

1. Procure e selecione o arquivo de licença XML que foi fornecido quando você comprou o Commercial Suite.
    > [!NOTE]
    > É possível definir [configurações adicionais no pacote de provisionamento](hololens-provisioning.md).

1. No menu **Arquivo**, clique em **Salvar**. 

1. Leia o aviso explicando que os arquivos do projeto podem conter informações confidenciais e clique em **OK**.

    > [!IMPORTANT]
    > Ao criar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (. ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluir os arquivos de projeto quando não forem mais necessários.

1. No menu **Exportar**, clique em **Pacote de provisionamento**.
1. Altere **Proprietário** para **Administrador de TI**, que definirá a precedência desse pacote de provisionamento como mais alta do que os pacotes de provisionamento aplicados a este dispositivo de outras origens, e selecione **Avançar**.
1. Defina um valor para **Versão do Pacote**.

    > [!TIP]
    > Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes previamente aplicados.

1. Em **Selecionar os detalhes de segurança do pacote de provisionamento**, clique em **Avançar**.
1. Clique em **Avançar** para especificar o local de saída do pacote de provisionamento quando ele estiver compilado. Por padrão, o Windows ICD usa a pasta do projeto como o local de saída.

    Como alternativa, clique em Procurar para alterar o local de saída padrão.

1. Clique em **Avançar**.
1. Clique em **Compilar** para começar a criar o pacote. As informações do projeto são exibidas na página de compilação, e a barra de progresso indica o status da compilação.
1. Quando o processo for concluído, clique em **Concluir**.

### Aplicar o pacote de provisionamento ao HoloLens

1. Conecte o dispositivo via USB a um computador e inicie o dispositivo, mas não continue depois da página **fit** da experiência de configuração inicial (a primeira página com a caixa azul).
1. Pressione e solte rapidamente os botões de **Menos Volume** e **Ligar/Desligar** simultaneamente.
1. O HoloLens será mostrado como um dispositivo no Explorador de Arquivos no computador.
1. No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.
1. Pressione e solte rapidamente os botões **Menos Volume** e **Ligar/Desligar** simultaneamente mais uma vez enquanto estiver na página **fit**.
1. O dispositivo perguntará se você confia no pacote e se gostaria de aplicá-lo. Confirme que você confia no pacote.
1. Você verá se o pacote foi aplicado com êxito ou não. Se ele falhar, você poderá corrigir o pacote e tentar novamente. Se ele for bem-sucedido, continue com a configuração do dispositivo.

> [!NOTE]
> Se o dispositivo tiver sido comprado antes de agosto de 2016, você precisará entrar no dispositivo usando uma conta da Microsoft, obter a atualização mais recente do sistema operacional e redefini-lo para aplicar o pacote de provisionamento.

## Verificar a criptografia de dispositivo

A criptografia é silenciosa no HoloLens. Para verificar o status de criptografia do dispositivo:

- No HoloLens, acesse **Configurações** > **Sistema** > **Sobre**. O **BitLocker** estará **habilitado** se o dispositivo estiver criptografado. 

    ![A tela sobre como mostrar o BitLocker está habilitada](images/about-encryption.png)