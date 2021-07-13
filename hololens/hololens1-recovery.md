---
title: Reiniciar, redefinir ou recuperar HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como usar a Windows recuperação de dispositivo para piscar uma imagem para HoloLens 1ª geração.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635221"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Reiniciar, redefinir ou recuperar HoloLens (1ª geração)

Se você estiver tendo problemas com seu HoloLens, talvez você queira tentar reiniciar ou redefinir ou até mesmo reflashar o dispositivo usando a recuperação do dispositivo. Este artigo orienta você pelas etapas de recuperação recomendadas na ordem.

Se você estiver procurando recuperar um HoloLens 2, consulte Recuperando um HoloLens [2,](hololens-recovery.md)pois esse processo é diferente.

> [!NOTE]
> Este artigo se concentra no HoloLens software e dispositivo. Se os hologramas não parecem corretos, confira **[HoloLens de](hololens-environment-considerations.md)** ambiente para obter informações sobre fatores que melhoram a qualidade do holograma.

## <a name="restart"></a>Reiniciar

### <a name="do-a-safe-restart-by-using-cortana"></a>Faça uma reinicialização segura usando Cortana

A maneira mais segura de reiniciar o HoloLens é usando Cortana, que geralmente é a primeira coisa a tentar quando você tem um problema com HoloLens.

> [!NOTE] 
> Cortana está disponível em todos os dispositivos.
> - Cortana está disponível em todos os HoloLens (1ª geração). 
> - Cortana está disponível em HoloLens 2 dispositivos em builds anteriores à atualização Windows Holograpic, Versão 2004.

1. A turn on your HoloLens.
1. Certifique-se de que um usuário está conectado e se o dispositivo não está aguardando uma senha desbloqueá-la.
2. Diga "Hey Cortana, reboot" ou "Hey Cortana, restart".
3. Cortana responderá e solicitará que você confirme. Aguarde a reprodução de um som após a pergunta e, em seguida, diga "Sim". O dispositivo será reiniciado.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Usar o botão de energia para fazer uma reinicialização segura

Se você ainda não conseguir reiniciar o dispositivo, tente reiniciá-lo usando o **botão de** energia:

1. Pressione e mantenha o **botão de** energia pressionado por 5 segundos. Após 1 segundo, todos os cinco LEDs serão acesos e, em seguida, desligarão lentamente um por um da direita para a esquerda. Após 5 segundos, todos os LEDs estarão desligados, indicando desligamento bem-sucedido.
      
   > [!IMPORTANT]
   > Pare de pressionar o botão imediatamente depois que todos os LEDs foram desligados.
1. Aguarde 1 minuto para que o desligamento seja concluído. O desligamento ainda pode estar em andamento mesmo depois que as exibições são desligadas.
2. A ligar o dispositivo novamente pressionando e mantendo o **botão de** energia pressionado por 1 segundo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Faça uma reinicialização segura usando Windows Portal de Dispositivos

> [!NOTE]
> Para esse processo, HoloLens precisa ser configurado como um dispositivo de desenvolvedor. Saiba mais em [Windows Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal).

Se o procedimento anterior não funcionou, tente reiniciar o dispositivo [usando](/windows/mixed-reality/using-the-windows-device-portal)Windows Portal de Dispositivos . No canto superior direito, encontre a opção para reiniciar ou desligar o dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Fazer uma reinicialização forçada não segura

Se os métodos anteriores não reiniciarem o HoloLens, force uma reinicialização. Esse método é equivalente a remover e reinstalar a bateria. É perigoso porque pode deixar seu dispositivo em um estado corrompido. Se isso acontecer, você terá que piscar seu HoloLens.  

> [!WARNING]
> Esse é um método potencialmente prejudicial e só deverá ser usado se os métodos citados anteriormente não funcionarem.

1. Pressione e mantenha o **botão de** energia pressionado por pelo menos 10 segundos.
   - Não há problema em manter o botão por mais de 10 segundos.
   - É seguro ignorar qualquer atividade de LED.
1. Solte o botão e aguarde de 2 a 3 segundos.
1. Pressione e mantenha o **botão de** energia pressionado por 1 segundo.
1. Se você ainda tiver  problemas, pressione o botão de energia por 4 segundos, até que todos os indicadores de bateria esmaeçam e a tela pare de exibir hologramas. Aguarde 1 minuto e pressione o botão **de** energia novamente para ativar o dispositivo.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Go back para uma versão anterior – HoloLens (1ª geração)

Em alguns casos, talvez você queira voltar para uma versão anterior do HoloLens software. Você pode fazer isso usando a ferramenta Windows recuperação de dispositivo para redefinir seu HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar para uma versão anterior do HoloLens 1, siga estas etapas:

1. Certifique-se de que você não tenha telefones ou Windows conectados ao computador.
1. Em seu computador, baixe o [WDRT (Ferramenta Windows Recuperação](https://support.microsoft.com/help/12379)de Dispositivo) do .
1. Baixe o pacote [de recuperação HoloLens atualização de aniversário do .](https://aka.ms/hololensrecovery)
1. Quando os downloads terminarem, abra Explorador **de arquivos**  >  **Downloads**. Clique com o botão direito do mouse na pasta recortada que você acabou de baixar e selecione **Extrair tudo**  >  **extrair** para descomplicá-la.
1. Conexão seu HoloLens no computador usando o cabo micro USB que ele veio. (Mesmo que você tenha usado outros cabos para conectar seu HoloLens, esse funcionará melhor.)
1. O WDRT detectará automaticamente seu HoloLens. Selecione o **Microsoft HoloLens** de seleção.
1. Na próxima tela, selecione **Seleção manual de** pacotes e escolha o arquivo de instalação contido na pasta que você desempiou na etapa 4. (Procure um arquivo com a extensão .ffu.)
1. Selecione **Instalar software** e siga as instruções.

> [!NOTE]
> Se o WDRT não detectar seu HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **Meu dispositivo não** foi detectado, selecione Microsoft HoloLens e siga as instruções. 

## <a name="reset-to-factory-settings"></a>Redefinir para configurações de fábrica

> [!NOTE]
> A bateria precisa de pelo menos uma carga de 40% para redefinir.

Se o HoloLens ainda tiver um problema, tente redefini-lo para o estado de fábrica. Esta etapa mantém a versão do Windows software Holographic instalado nele e retorna todo o resto para as configurações de fábrica.

>[!WARNING]
> Se você redefinir seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição do TPM. A redefinição instalará apenas a versão mais recente instalada do Windows Holographic. Você terá que refazer todas as etapas de inicialização (calibrar, conectar-se ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).

1. Abra o Configurações aplicativo e, em seguida, selecione **Atualizar**  >  **Recuperação**.
1. Selecione a **opção Redefinir** dispositivo e leia a mensagem de confirmação.
1. Confirme a redefinição. O dispositivo reiniciará e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.
1. Aguarde cerca de 30 minutos para que esse processo seja concluído. Quando terminar, o dispositivo será reiniciado para a experiência "pronta para uso".

## <a name="reinstall-the-operating-system"></a>Reinstalar o sistema operacional

Se o dispositivo ainda estiver tendo um problema após a reinicialização e a redefinição, você poderá usar uma ferramenta de recuperação em seu computador para reinstalar o HoloLens operacional e firmware.  

Os dados HoloLens necessários para a redefinição são empacotados em uma FFU (Atualização Flash Completa), que é semelhante a um arquivo .iso, .wim ou .vhd. [Saiba mais sobre formatos de arquivo de imagem FFU.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Você pode instalar um novo sistema operacional em seu HoloLens (1ª geração) usando a ferramenta Windows recuperação de dispositivo. Antes de usar essa ferramenta, confira se reiniciar ou redefinir seu HoloLens corrige o problema.

O processo de recuperação pode levar algum tempo. Quando terminar, a versão mais recente do Windows holographic será instalada.

Para usar a ferramenta, você precisa de um computador executando Windows 10 ou posterior com pelo menos 4 GB de espaço de armazenamento livre. Você não pode executar essa ferramenta em uma máquina virtual.

### <a name="recover-your-hololens"></a>Recuperar sua HoloLens

1. Baixe e instale a ferramenta [Windows recuperação de dispositivo em](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) seu computador.
1. Conexão o HoloLens (1ª geração) para seu computador usando o cabo Micro USB que veio com seu HoloLens.
1. Abra a ferramenta Windows recuperação de dispositivo e siga as instruções.

Se a HoloLens (1ª geração) não for detectada automaticamente, selecione Meu dispositivo **não foi detectado.** Em seguida, siga as instruções para colocar o dispositivo no modo de recuperação.

### <a name="manual-flashing-mode"></a>Modo de flash manual

Se o dispositivo não for detectado, siga estas etapas para colocá-lo no modo de flash:

1. Desconectar o dispositivo de qualquer fonte de alimentação.
1. Se o dispositivo estiver conectado, mantenha pressionado o botão **de** energia até que ele seja completamente desligado.
2. Mantenha o botão do **volume** pressionado e toque brevemente no botão de **energia** . O dispositivo deve iniciar e exibir apenas o LED do meio.
3. Conecte o dispositivo ao seu PC.
4. abra a ferramenta de recuperação de dispositivo Windows.
5. Selecione **meu dispositivo não foi detectado** e, em seguida, **HoloLens**. 
6. Siga as instruções para recuperar o dispositivo.
