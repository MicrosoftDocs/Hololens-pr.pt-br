---
title: Reiniciar, redefinir ou recuperar o HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Como usar o Advanced Recovery Companion para instalar imagem no HoloLens 2.
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
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923628"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Reiniciar, redefinir ou recuperar o HoloLens 2

>[!IMPORTANT]
> Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de **20% a 40%** da capacidade da bateria, se possível. As [luzes indicadoras de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas sob o botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.

Use o [carregador e o cabo USB Tipo-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) que veio com o HoloLens 2, pois essa é a melhor maneira de carregar seu dispositivo. O carregador fornece 18 W de potência (9 V a 2 A). Usando o carregador de parede fornecido, os dispositivos HoloLens 2 podem carregar a bateria completamente em menos de 65 minutos quando o dispositivo está em espera. Se esses acessórios não estiverem disponíveis, verifique se o carregador que está disponível consegue suportar pelo menos 15 W de energia.

> [!NOTE]
> Se possível, evite usar um computador para carregar o dispositivo por USB, pois é lento.

Se o dispositivo for reinicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria:

- No menu principal da interface de usuário do dispositivo do HoloLens.
- Exibir o LED próximo ao botão de energia (com 40% de carga, você deve ver pelo menos dois LEDS sólidos).
    - Quando o dispositivo estiver sendo carregado, o indicador de bateria acenderá para indicar o nível de carga atual.  A última luz acenderá e apagará para indicar o carregamento ativo.
    - Quando o HoloLens estiver ligado, o indicador de bateria exibe o nível da bateria em cinco incrementos.
    - Quando somente uma das cinco luzes estiver acesa, o nível da bateria estará abaixo de 20%.
    - Se o nível da bateria estiver muito baixo e você tentar ligar o dispositivo, uma luz piscará rapidamente e apagará.
- No computador host, abra o **Explorador de Arquivos** e procure seu dispositivo HoloLens 2 no lado esquerdo em **Este Computador**. Clique com o botão direito do mouse no dispositivo e escolha **Propriedades**. Uma caixa de diálogo mostrará o nível de carga da bateria.

   ![Uma tela de propriedades do HoloLens 2 mostra o nível de mudança da bateria](images/ResetRecovery2.png)

Se o dispositivo não conseguir reiniciar pelo menu Iniciar, observe a aparência do LED e a enumeração do dispositivo no PC host. Em seguida, siga o [guia de solução de problemas](hololens-troubleshooting.md). Caso o estado do dispositivo não se enquadrar em nenhum dos estados listados no guia de solução de problemas, execute o [reinicialização forçada](hololens-recovery.md#hard-reset-procedure) com o dispositivo conectado à fonte de energia, não ao computador host. Aguarde pelo menos uma hora para o dispositivo ser carregado.

## <a name="reset-the-device"></a>Redefinir o dispositivo

Sob certas circunstâncias, você pode ter que reiniciar manualmente o dispositivo sem usar o software UI.

### <a name="standard-procedure"></a>Procedimento padrão

1. Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.

2. Pressione e mantenha pressionado o botão de **energia** por 15 segundos. Todos os LEDs devem estar desativados.

3. Aguarde 2-3 segundos e, em seguida, pressione rapidamente o botão de **energia**. Os LEDs próximos ao botão de energia terão uma iluminação e o dispositivo executará a inicialização.

4. Conecte o dispositivo ao computador host e, em seguida, abra o Gerenciador de Dispositivos. (Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e escolha **Gerenciador de Dispositivos**.) Verifique se o dispositivo é identificado corretamente como *Microsoft HoloLens* conforme mostrado na imagem a seguir:

   ![Gerenciador de dispositivos do HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedimento de redefinição de disco

Se o procedimento padrão de redefinição não funcionar, use o procedimento de redefinição forçada:

1. Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.

2. Mantenha os botões de **diminuir o volume** + **energia** pressionados por 15 segundos. O dispositivo será reinicializado automaticamente.

4. Conecte o dispositivo ao computador host.

5. Abra Gerenciador de Dispositivos (para Windows 10, pressione a tecla **Windows**, a tecla **X** e, em seguida, escolha **Gerenciador de Dispositivos**). Verifique se o dispositivo está identificado corretamente conforme *Microsoft HoloLens*, conforme mostrado na imagem a seguir:

   ![Gerenciador de dispositivos 2 MicrosoftHoloLensRecovery do HoloLens 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Limpeza da reflash do dispositivo

Em situações extraordinárias, talvez seja necessário "limpar a flash" no HoloLens 2. Observe que não se espera que a limpeza da reflash afete as seguintes questões:
- [Exibir a uniformidade de cor](hololens2-display.md)
- Inicialização com som, mas sem saída
- [Padrão de LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems)
- [Superaquecimento](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Ocorre um erro no SO (que é diferente do travamento do aplicativo)

Há duas maneiras de limpar a reflash do dispositivo. Para ambos, você deve primeiro [instalar o Advanced Recovery Companion pela Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Se você limpar a flash do seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição de TPM.

Por padrão, o Complemento Avançado de Recuperação está configurado para baixar a compilação do recurso mais recente, confira aqui para ler nossas [notas sobre a versão](hololens-release-notes.md#) para saber mais sobre a versão mais recente do recurso. Para obter o pacote HoloLens 2 FFU (Atualização Flash Completa) mais recente para fazer reflash do seu dispositivo por meio do Advanced Recovery Companion, [clique aqui para baixar a imagem HoloLens 2 mais recente](https://aka.ms/hololens2download). Esta versão é geralmente a versão mais recente disponível.

Antes de iniciar o procedimento de limpeza da flash, o aplicativo deve está instalado e em execução no PC com Windows 10 e pronto para detectar o dispositivo. O HoloLens também deve estar carregado em um mínimo de 40%.

![Captura de tela de reflash limpa do HoloLens 2](images/ARC1.png)

### <a name="normal-procedure"></a>Procedimento normal

1. Enquanto o dispositivo do HoloLens estiver em execução, conecte-o ao seu PC com Windows 10, em que você já havia aberto o aplicativo Advanced Recovery Companion.
 
   O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:

   ![Tela inicial da limpeza da flash do HoloLens 2](images/ARC2.png)

3. Escolha o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.

### <a name="manual-procedure"></a>Procedimento manual

Se o HoloLens 2 não iniciar corretamente ou se o Advanced Recovery Companion não conseguir detectar o dispositivo, talvez seja necessário colocar o dispositivo no modo de recuperação:

1. Desconecte o cabo tipo-C para desconectar o dispositivo da fonte de alimentação ou do computador host.

2. Pressione e mantenha pressionado o botão de **energia** por 15 segundos. Todos os LEDs devem se desligar.

3. Ao pressionar o botão **aumentar volume**, pressione e solte o botão de **energia** para iniciar o dispositivo. Aguarde 15 segundos e solte o botão **aumentar volume**. Apenas o LED central dos cinco LEDs se acenderá.

4. Conecte o dispositivo ao computador host e abra o Gerenciador de Dispositivos. (Para o Windows 10, pressione a tecla **Windows** e, em seguida, a tecla **X** e escolha **Gerenciador de Dispositivos**.) Verifique se o dispositivo é identificado corretamente como Microsoft HoloLens conforme mostrado na imagem a seguir:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   O dispositivo será detectado automaticamente, e a interface do usuário do Advanced Recovery Companion iniciará o processo de atualização:

   ![Tela de limpeza da reflash do HoloLens 2](images/ARC2.png)

6. Escolha o dispositivo do HoloLens 2 na interface do usuário do aplicativo Advanced Recovery Companion e siga as instruções para concluir a reflash.

## <a name="troubleshoot-advanced-recovery-companion"></a>Solucionar problemas do Advanced Recovery Companion

1. Verifique se o dispositivo é carregado em 40% ou mais antes de tentar instalar imagem.

2. Verifique se o dispositivo está desbloqueado.

3. Se o ARC não detectar seu dispositivo, verifique se você pode se conectar a ele por meio Explorador de Arquivos em seu computador. Se não for possível:

    1.  É possível que seu dispositivo tenha políticas de USB que desabilitam essa conexão. Em caso afirmativo, tente o [Modo de flash manual](hololens-recovery.md#manual-procedure).
    2.  Se não houver nenhuma política, tente um cabo USB diferente.

1. Verifique se o dispositivo não exibe um [padrão de LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).

## <a name="download-arc-without-using-the-app-store"></a>Baixar o ARC sem usar a app store

Se um ambiente de TI impede o uso do aplicativo da Windows Store ou limita o acesso à loja, os administradores de TI podem disponibilizá-lo por meio de outros caminhos de implantação "offline".

 >[!NOTE]
 > - O administrador de TI também pode distribuir esse aplicativo por meio do SCCM (System Center Configuration Manager) ou do Intune.
 > - Este guia se concentrará no Advanced Recovery Companion, mas ele será modificado para outros aplicativos offline.

Siga estas etapas para habilitar o caminho da implantação:

1. Acesse o [Microsoft Store para Empresas](https://businessstore.microsoft.com) e entre usando uma identidade do Azure Active Directory.

1. Vá para **Gerenciar – Configurações**. Ative **Mostrar aplicativos offline** em **Experiência de compra**.

1. Acesse **Comprar para meu grupo** e procure [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Mude o **Tipo de Licença** para **_offline_ *_ e escolha _* Gerenciar**.

1. Em **Fazer download do pacote para uso offline**, escolha o segundo botão de **Download** azul. Verifique se a extensão de arquivo é *.appxbundle*.

    - Nesse estágio, se o computador desktop tiver acesso à Internet, clique duas vezes no pacote para instalar o aplicativo.

    - Se o computador de destino não tiver conexão à Internet, siga estas etapas:
       1. Escolha a licença não codificada e, em seguida, escolha **Gerar licença**.
       2. Em **Estruturas necessárias**, escolha **Fazer download**.
       3. Use o DISM para aplicar o pacote com a dependência e a licença. Em um prompt de comando de administrador e execute o seguinte comando:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > O número de versão neste exemplo de código pode não corresponder à versão disponível no momento. Você também pode escolher um local de download diferente do especificado no exemplo. Faça todas as alterações no comando conforme necessário.

> [!TIP]
> Quando você planeja usar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil baixar a imagem flash. [**Fazer download da imagem atual para HoloLens 2**](https://aka.ms/hololens2download).


Outros recursos:
- [Distribuir aplicativos offline](/microsoft-store/distribute-offline-apps) 
- [Pacote de aplicativos DISM (.appx ou .appxbundle) servindo opções de linha de comando](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
