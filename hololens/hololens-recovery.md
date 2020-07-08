---
title: Reiniciar, redefinir ou recuperar o HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857759"
---
# Reiniciar, redefinir ou recuperar o HoloLens

## Carregando o dispositivo

Antes de iniciar qualquer procedimento de solução de problemas, se possível, certifique-se de que seu dispositivo tenha sido cargado pelo menos entre 20% e 40%.

Verifique se você está usando o carregador e os cabos USB tipo C que vêm com o dispositivo HoloLens2. Caso não estejam disponíveis, certifique-se de que o carregador disponível possa oferecer suporte a pelo menos 15W de energia.

> [!NOTE]
> Se possível, não use um PC para carregar o dispositivo por USB, pois isso fornecerá uma carga muito lenta.

Se o dispositivo estiver inicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria.

1. No menu principal da interface de usuário do dispositivo do HoloLens.
2. Usando o LED próximo ao botão ligar (por 40%, você deve ver pelo menos dois LEDS sólidos).
3. No PC host, abra a janela do explorador de arquivos e procure seu dispositivo do HoloLens 2 no lado esquerdo, em "este computador".
    
      a. Clique com o botão direito do mouse no nome do dispositivo e selecione Propriedades. Aparecerá uma caixa de diálogo mostrando o nível da bateria para o seu dispositivo.

![ResetRecovery do HoloLens 2](images/ResetRecovery2.png)

Se o dispositivo não puder ser inicializado no menu Iniciar, anote os LEDs e a enumeração no PC host e siga o guia de solução de problemas (https://docs.microsoft.com/hololens/hololens-troubleshooting). Caso o estado do dispositivo não se enquadrar em nenhum dos estados listados no guia de solução de problemas, execute o **procedimento de reinicialização forçada** sem reconectar o dispositivo ao PC host, mas conectá-lo à fonte de alimentação. Aguarde pelo menos uma hora para o dispositivo ser carregado.

## Redefina o dispositivo

Em determinadas circunstâncias, o cliente pode ser solicitado a redefinir manualmente o dispositivo sem usar a IU do SW. 

### Procedimento padrão
1. Desconecte o dispositivo da fonte de alimentação ou PC host desconectando o cabo tipo-C.

2. Pressione e mantenha pressionado o **botão de energia** por 15 segundos. Todos os LEDs devem estar desativados.

3. Aguarde 2-3 segundos e pressione o **botão de energia**, os LEDs próximos ao botão de energia terão iluminação e o dispositivo começará a ser inicializado. 

4. Conecte o dispositivo ao PC host, abra o Gerenciador de dispositivos (para Windows 10 pressione a **tecla "Windows"** e, em seguida, a **tecla “x”** e clique em "Gerenciador de dispositivos") e verifique se o dispositivo enumera corretamente como Microsoft HoloLens, conforme mostrado nas imagens a seguir:

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### Procedimento de redefinição de disco

Se o procedimento de redefinição padrão não funcionar, você pode usar o procedimento de redefinição de disco.

1. Desconecte o dispositivo da fonte de alimentação ou PC host desconectando o cabo tipo-C.

2. Mantenha o **diminuir o volume + botão de energia** por 15 segundos.

3. O dispositivo será reinicializado automaticamente. 

4. Conecte o dispositivo ao PC host, abra o Gerenciador de dispositivos (para Windows 10 pressione a **tecla "Windows"** e, em seguida, a **tecla “x”** e clique em "Gerenciador de dispositivos") e verifique se o dispositivo enumera corretamente como Microsoft HoloLens, conforme mostrado nas imagens a seguir.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Reflash limpo do dispositivo

Em situações extraordinárias, talvez seja necessário limpar o flash no dispositivo. Há duas maneiras de refazer a pisca de um dispositivo HoloLens2. Para todos os procedimentos de intermitência, você será solicitado a [instalar o aplicativo Advanced Recovery Companion do Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8). Se você reiniciar seu dispositivo, todos os seus dados, aplicativos e configurações pessoais serão apagados, incluindo a redefinição do TPM.

O complemento avançado de recuperação está configurado para descarregar a versão de lançamento do recurso para [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), se você quiser baixar a versão mais recente do HoloLens 2 para piscar seu dispositivo por meio do Advanced Recovery Companion, poderá baixá-lo da [aqui](https://aka.ms/hololens2download). Esse recurso é mantido atualizado e será redirecionado para o Build mais recente disponível. 

Antes de iniciar o procedimento de flashação, certifique-se de que o aplicativo está instalado e em execução no PC com Windows 10 e está pronto para detectar o dispositivo.

![Reflash limpo 2 do HoloLens](images/ARC1.png)

### Procedimento normal

1. Enquanto o dispositivo do HoloLens estiver em execução, conecte-o ao seu PC com Windows 10, em que você já havia lançado o aplicativo Advanced Recovery Companion.

2. O dispositivo será detectado automaticamente e a IU do aplicativo Advanced Recovery Companion será atualizada da seguinte maneira:

![Reflash limpo 2 do HoloLens](images/ARC2.png)

3. Selecione o dispositivo HoloLens2 na IU do aplicativo Advanced Recovery Companion e siga as instruções para concluir a intermitência.

### Procedimento manual

Se o dispositivo não inicializar corretamente, talvez seja necessário colocar o dispositivo do HoloLens 2 no modo de recuperação.

1. Desconecte o dispositivo da fonte de alimentação ou PC host desconectando o cabo tipo-C. 

2. Pressione e mantenha pressionado o **botão de energia** por 15 segundos. Todos os LEDs devem se desligar. 

3. Enquanto pressiona o botão **aumentar volume**, pressione e solte o **botão de energia** para iniciar o dispositivo. Aguarde 15 segundos antes de liberar o botão aumentar volume. De 5 LEDs no dispositivo, apenas o LED intermediário iluminará.

4. Conecte o dispositivo ao PC host, abra o Gerenciador de dispositivos (para Windows 10 pressione a **tecla "Windows"** e, em seguida, a **tecla “x”** e clique em "Gerenciador de dispositivos") e verifique se o dispositivo enumera corretamente como Microsoft HoloLens, conforme mostrado na imagem a seguir.

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. O dispositivo será detectado automaticamente, e a IU do aplicativo Advanced Recovery Companion será atualizada da seguinte maneira:

![Reflash limpo 2 do HoloLens](images/ARC2.png)

6. Selecione o dispositivo Microsoft HoloLens 2 na IU do aplicativo Advanced Recovery Companion e siga as instruções para concluir a intermitência.

## Baixando o ARC sem usar a Loja de aplicativos

Se um ambiente de TI impede o uso do aplicativo da Windows Store ou limita o acesso à loja de varejo, os administradores de TI podem disponibilizá-lo por meio de outros caminhos de implantação "offline". 

- Esse processo também pode ser usado para outros aplicativos, como visto na etapa 2. Este guia se concentrará no Advanced Recovery Companion, mas ele será modificado para outros aplicativos offline.  

Esse caminho de implantação pode ser habilitado com as seguintes etapas:
1.  Vá para o site do [Microsoft Store para Empresas](https://businessstore.microsoft.com) e entre com uma identidade do Azure Active Directory.
1.  Vá para **Gerenciar – Configurações**e ative **Mostrar aplicativos offline** em **Experiência de compra** conforme descrito em https://businessstore.microsoft.com/manage/settings/shop 
1.  Vá para **Comprar para o meu grupo** e pesquise o aplicativo [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1.  Altere a caixa de **Tipo de licença** para offline e clique em **Gerenciar**.
1.  Em Baixar o pacote para uso offline, clique no segundo botão azul **"Baixar"**. Verifique se a extensão de arquivo é. appxbundle.
1.  Nessa etapa, se o PC tiver acesso à Internet, basta clicar duas vezes e instalar. 
1.  O administrador de TI também pode distribuir esse aplicativo por meio do SCCM (System Center Configuration Manager) ou do Intune.
1.  Se o PC de destino não tiver conectividade com a Internet, serão necessárias algumas etapas adicionais: 
    1.  Selecione a licença não codificada e clique em **"Gerar licença"** e em **"Estruturas necessárias"** clique em **"Baixar".** 
    1.  Os PCs sem acesso à Internet precisarão usar o DISM para aplicar o pacote à dependência e à licença. Em um aviso de comando do administrador, digite:

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> O número de versão neste exemplo de código pode não corresponder à versão disponível no momento. Você também pode escolher um local de download diferente do especificado no exemplo. Certifique-se de fazer as alterações necessárias.

> [!TIP]
> Ao planejar usar o Advanced Recovery Companion para instalar um FFU offline, pode ser útil baixar a imagem instalada para ser disponível, aqui está a [imagem atual para o Microsoft HoloLens 2](https://aka.ms/hololens2download). 

Outros recursos:
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


