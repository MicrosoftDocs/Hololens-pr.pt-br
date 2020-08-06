---
title: Reiniciar, redefinir ou recuperar o HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Como usar o Advanced Recovery Companion para instalar uma imagem para o HoloLens 2.
keywords: como fazer, reinicializar, redefinir, recuperar, reinicializar disco, redefinição rápida, ciclo de energia, HoloLens, desligar, arco, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915949"
---
# Reiniciar, redefinir ou recuperar o HoloLens 2

## Carregar o dispositivo

Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de 20 a 40% da capacidade da bateria, se possível. Verifique se você está usando o carregador e os cabos USB tipo C que vêm com o dispositivo HoloLens2. Se esses acessórios não estiverem disponíveis, certifique-se de que o carregador que está disponível suporte pelo menos 15W de potência.

> [!NOTE]
> Se possível, evite usar um computador para carregar o dispositivo por USB, pois é lento.

Se o dispositivo for reinicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria:

- No menu principal da interface de usuário do dispositivo do HoloLens.
- Exibir o LED próximo ao botão de energia (com 40% de carga, você deve ver pelo menos dois LEDS sólidos).
- No computador host, abra o Explorador de Arquivos e procure seu dispositivo do HoloLens 2 no lado esquerdo, em **Este Computador**. Clique com o botão direito do mouse no arquivo e selecione **Propriedades**. Uma caixa de diálogo mostrará o nível de carga da bateria.

   ![Uma tela de propriedades do HoloLens 2 mostra o nível de mudança da bateria](images/ResetRecovery2.png)

Se o dispositivo não conseguir reiniciar até o menu Iniciar, observe a aparência do LED e a enumeração do dispositivo no PC host. Em seguida, siga o [guia de solução de problemas](https://docs.microsoft.com/hololens/hololens-troubleshooting). Caso o estado do dispositivo não se enquadrar em nenhum dos estados listados no guia de solução de problemas, execute o *procedimento de reinicialização forçada* com o dispositivo conectado à fonte de energia, não ao computador host. Aguarde pelo menos uma hora para o dispositivo ser carregado.

## Redefina o dispositivo

Em determinadas circunstâncias, o cliente pode ser solicitado a redefinir manualmente o dispositivo sem usar a IU do SW.

### Procedimento padrão
1. Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.

2. Pressione e mantenha pressionado o botão de **energia** por 15 segundos. Todos os LEDs devem estar desativados.

3. Aguarde 2-3 segundos e, em seguida, pressione rapidamente o botão de **energia**. Os LEDs próximos ao botão de energia terão uma iluminação e o dispositivo executará a inicialização.

4. Conecte o dispositivo ao computador host e, em seguida, abra o Gerenciador de Dispositivos. (Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Device Manager**.) Verifique se o dispositivo é identificado corretamente como  *Microsoft HoloLens* conforme mostrado na imagem a seguir:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### Procedimento de redefinição de disco

Se o procedimento padrão de redefinição não funcionar, use o procedimento de redefinição forçada:

1. Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.

2. Mantenha pressionada os botões **baixar volume** + **energia** por 15 segundos. O dispositivo será reinicializado automaticamente.

4. Conecte o dispositivo ao computador host.
5. Abra o Gerenciador de Dispositivos (para Windows 10 pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Gerenciador de Dispositivos**). Verifique se o dispositivo está identificado corretamente conforme *Microsoft HoloLens* conforme mostrado na imagem a seguir:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Limpar a flash do dispositivo

Em situações extraordinárias, talvez seja necessário "limpar a flash" no HoloLens 2. Há duas maneiras de limpar a flash do dispositivo. Para ambos, você deve primeiro instalar o [Advanced Recovery Companion na Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Se você limpar a flash do seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição de TPM.

Por padrão, o Advanced Recovery Companion está definido atualmente para baixar a versão de lançamento do recurso para [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004). Para obter o pacote mais recente da imagem no formato UFF (Full Flash Update) do HoloLens 2 para limpar a flash do seu dispositivo por meio da Advanced Recovery Companion, [baixe aqui](https://aka.ms/hololens2download). Esta versão é geralmente a versão mais recente disponível.

Antes de iniciar o procedimento de limpeza da flash, certifique-se de que o aplicativo está instalado e em execução no PC com Windows 10 e está pronto para detectar o dispositivo.

![Captura de tela de reflash limpa do HoloLens 2](images/ARC1.png)

### Procedimento normal

1. Enquanto o dispositivo do HoloLens estiver em execução, conecte-o ao seu PC com Windows 10, em que você já havia aberto o aplicativo Advanced Recovery Companion.
 
   O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:

   ![Tela inicial da limpeza da flash do HoloLens 2](images/ARC2.png)

3. Selecione o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.

### Procedimento manual

Se o HoloLens 2 não iniciar corretamente, talvez seja necessário colocar o dispositivo no Modo de recuperação:

1. Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.

2. Pressione e mantenha pressionado o botão de **energia** por 15 segundos. Todos os LEDs devem se desligar.

3. Enquanto pressiona o botão **aumentar o volume**, pressione e solte o botão **energia** para iniciar o dispositivo. Aguarde 15 segundos e, em seguida, solte o botão **aumentar o volume**. Apenas o LED central dos cinco LEDs se acenderá.

4. Conecte o dispositivo ao computador host e abra o Gerenciador de Dispositivos. (Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e selecione **Gerenciador de Dispositivos**.) Verifique se o dispositivo é identificado corretamente como Microsoft HoloLens conforme mostrado na imagem a seguir:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:

   ![Tela de limpeza do reflash do HoloLens 2](images/ARC2.png)

6. Selecione o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.

## Baixando o ARC sem usar a app store

Se um ambiente de TI impede o uso do aplicativo da Windows Store ou limita o acesso à loja, os administradores de TI podem disponibilizá-lo por meio de outros caminhos de implantação "offline".

 >[!NOTE] 
 > - O administrador de TI também pode distribuir esse aplicativo por meio do SCCM (System Center Configuration Manager) ou do Intune.
 > - Este guia se concentrará no Advanced Recovery Companion, mas ele será modificado para outros aplicativos offline.

Siga estas etapas para habilitar o caminho da implantação:
1. Acesse a [Microsoft Store para Empresas](https://businessstore.microsoft.com) e entre usando uma identidade do Azure Active Directory.

1. Vá para **Gerenciar – Configurações**. Ative **Mostrar aplicativos offline** em **Experiência de compra**. 
1. Vá para **comprar para o meu grupo** e procure por [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1. Altere o **Tipo de Licença** para ***offline*** e clique em **Gerenciar**.
1. Em **Baixe o pacote para uso offline**, selecione o segundo botão azul **Baixar**. Verifique se a extensão de arquivo é *.appxbundle*.

    - Nessa etapa, se o PC tiver acesso à Internet, basta clicar duas vezes para instalar o aplicativo.


    - Se o computador de destino não tiver conexão à Internet, siga estas etapas: 
       1. Selecione a licença não codificada e, em seguida, selecione **Gerar licença**.
       2. Em **Estruturas Necessárias**, marque **Baixar**.
       3. Use o DISM para aplicar o pacote com a dependência e a licença. Em um prompt de comando de administrador e execute o seguinte comando:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > O número de versão neste exemplo de código pode não corresponder à versão disponível no momento. Você também pode escolher um local de download diferente do especificado no exemplo. Faça todas as alterações no comando conforme necessário.

> [!TIP]
> Quando você planeja usar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil baixar a imagem flash. [**Baixar a imagem atual para o HoloLens 2**](https://aka.ms/hololens2download). 

Outros recursos:
- [Distribuir aplicativos offline](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [Pacote de aplicativos DISM (.appx ou .appxbundle) servindo opções de linha de comando.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
