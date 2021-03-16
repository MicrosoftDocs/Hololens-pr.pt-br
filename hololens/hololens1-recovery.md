---
title: Reiniciar, redefinir ou recuperar o HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como usar a Windows Device Recovery Tool para mostrar uma imagem para o HoloLens de 1ª geração.
keywords: como fazer, reinicializar, redefinir, recuperar, reinicialização forçada, reinicialização flexível, ciclo de energia, HoloLens, desligar, wdrt, windows device recovery tool
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
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439037"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Reiniciar, redefinir ou recuperar o HoloLens de 1ª geração

Se você estiver enfrentando problemas com o seu HoloLens, talvez queira tentar uma reinicialização ou redefinição, ou até mesmo refazer o flash do dispositivo usando a recuperação de dispositivos. Este artigo o orientará pelas etapas de recuperação recomendadas.

Se você estiver tentando recuperar um HoloLens 2, confira [Recuperar um HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), pois esse processo é diferente.

> [!NOTE]
> Esse artigo se concentra no dispositivo HoloLens e no seu software. Se o seu holograma não parecer correto, confira **[considerações sobre o ambiente do HoloLens](hololens-environment-considerations.md)** para saber mais sobre os fatores que melhoram a qualidade do holograma.

## <a name="restart"></a>Reiniciar

### <a name="do-a-safe-restart-by-using-cortana"></a>Executar uma reinicialização segura usando a Cortana

A maneira mais segura de reiniciar o HoloLens é usar a Cortana, que geralmente é a primeira coisa a fazer quando você se enfrenta um problema com o HoloLens.

> [!NOTE] 
> A Cortana não está disponível em todos os dispositivos.
> - A Cortana está disponível a todos os dispositivos do HoloLens (1ª geração). 
> - A Cortana está disponível em dispositivos do HoloLens 2 em uma compilação anterior à atualização do Windows Holograpic, versão 2004.

1. Ativar o seu HoloLens.
1. Certifique-se de que um usuário está conectado e o dispositivo não está aguardando que uma senha seja desbloqueada.
2. Diga "Ei Cortana, reinicializar" ou "Ei Cortana, reiniciar".
3. A Cortana responderá e solicitará que você confirme. Aguarde um som ser tocado após a pergunta e, em seguida, diga "Sim". O dispositivo será reiniciado agora.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Use o botão de energia para executar uma reinicialização segura

Se você ainda não conseguir reiniciar o dispositivo, experimente reiniciá-lo usando o botão de **energia**:

1. Pressione e mantenha pressionado o botão de **energia** por 5 segundos. Após 1 segundo, todos os cinco LEDs irão iluminar e, em seguida, desligar lentamente um por um da direita para a esquerda. Após 5 segundos, todos os LEDs estarão desligados, indicando um desligamento bem-sucedido.
      
   > [!IMPORTANT]
   > Pare de pressionar o botão imediatamente após todos os LEDs terem desligado.
1. Aguarde 1 minuto para concluir o desligamento. O desligamento ainda pode estar em andamento, mesmo depois que os monitores estiverem desligados.
2. Ligue o dispositivo novamente pressionando e mantendo pressionado o botão de **energia** por 1 segundo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Reiniciar com segurança usando o Portal de Dispositivos do Windows

> [!NOTE]
> Para fazer isso, o HoloLens deve ser configurado como um dispositivo desenvolvedor. Saiba mais em [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Se o procedimento anterior não funcionar, você pode tentar reiniciar o dispositivo usando [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). No canto superior direito, há uma opção para reiniciar ou desligar o dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Reinicialização forçada sem segurança

Se os métodos anteriores não reiniciarem o seu HoloLens, force uma reinicialização. Esse método é equivalente a remover e reinstalar a bateria. É perigoso porque pode deixar o seu dispositivo em um estado corrompido. Se isso acontecer, você precisará ligar e desligar o seu HoloLens.  

> [!WARNING]
> Esse é um método potencialmente nocivo e só deve ser usado se os métodos mencionados anteriormente não funcionarem.

1. Pressione e mantenha pressionado o botão de **energia** por pelo menos dez segundos.
   - Não há problema em manter o botão por mais de 10 segundos.
   - É seguro ignorar qualquer atividade do LED.
1. Solte o botão e aguarde dois ou três segundos.
1. Pressione e mantenha pressionado o botão de **energia** por 1 segundo.
1. Se você ainda estiver enfrentando problemas, pressione o botão de **energia** por quatro segundos até que todos os indicadores de bateria apareçam gradualmente e a tela pare de exibir os hologramas. Aguarde um minuto e, em seguida, pressione o botão de **energia** novamente para ativar o dispositivo.

## <a name="reset-to-factory-settings"></a>Redefinir para as configurações de fábrica

> [!NOTE]
> A bateria precisa de pelo menos 40% da carga para reiniciar.

Se o seu HoloLens ainda tiver um problema, tente redefini-lo para o estado de fábrica. Esta etapa mantém a versão do software do Windows Holographic que está instalada nela e retorna tudo para as configurações de fábrica.

>[!WARNING]
> Se você reiniciar seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo a redefinição do TPM. A redefinição instalará apenas a versão mais recente do Windows Holographic. Será necessário refazer todas as etapas de inicialização (calibragem, conectar ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).

1. Abra o aplicativo Configurações e, em seguida, selecione **Atualizar** > **Recuperação**.
1. Selecione a opção **Redefinir dispositivo** e leia a mensagem de confirmação.
1. Confirme a redefinição. O dispositivo será reiniciado e exibirá um conjunto de engrenagens giradas e uma barra de progresso.
1. Aguarde cerca de trinta minutos para a conclusão desse processo. Quando for concluído, o dispositivo será reiniciado para a experiência "inicial".

## <a name="reinstall-the-operating-system"></a>Re-instalar o sistema operacional

Se o dispositivo ainda estiver com problemas após a reinicialização e redefinição, você pode usar uma ferramenta de recuperação no computador para reinstalar o firmware e o sistema operacional do HoloLens.  

Os dados necessários para a redefinição do HoloLens são fornecidos no formato UFF (Full Flash Update), que é semelhante a um arquivo .iso, .wim ou .vhd. [Saiba mais sobre os formatos de arquivo de imagem do FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Você pode instalar um novo sistema operacional no seu HoloLens (1ª geração) usando a Windows Device Recovery Tool. Antes de usar essa ferramenta, confira se reiniciar ou redefinir o seu HoloLens corrige o problema.

O processo de recuperação pode demorar um pouco. Quando terminar, a versão mais recente do software Windows Holographic será instalada.

Para usar a ferramenta, você precisará de um computador que esteja executando o Windows 10 ou posterior, com pelo menos 4 GB de espaço de armazenamento disponível. Não é possível executar essa ferramenta em uma máquina virtual.

### <a name="recover-your-hololens"></a>Recuperar seu HoloLens

1. No computador, baixe e instale a [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
1. Conecte o HoloLens (1ª geração) ao seu computador usando o cabo micro USB que veio com o seu HoloLens.
1. Execute a Windows Device Recovery Tool e siga as instruções.

Se o HoloLens (1ª geração) não for detectado automaticamente, selecione **Meu dispositivo não foi detectado**. Em seguida, siga as instruções para colocar o dispositivo no modo de recuperação.

### <a name="manual-flashing-mode"></a>Modo de flash manual

Se o seu dispositivo não for detectado, siga estas etapas para inseri-lo no modo flash:

1. Desconecte o dispositivo de qualquer fonte de alimentação.
1. Se o dispositivo estiver ativado, mantenha pressionado botão de **energia** até que ele seja completamente desligado.
2. Segure o botão **aumentar o volume** e toque brevemente no botão de **energia**. O dispositivo deve ser iniciado e exibir apenas a luz LED central.
3. Conecte o dispositivo em seu PC.
4. Abra a ferramenta Windows Device Recovery Tool.
5. Selecione **Meu dispositivo não foi detectado** e, então, **HoloLens**. 
6. Siga as instruções para recuperar seu dispositivo.
