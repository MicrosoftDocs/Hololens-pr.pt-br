---
title: Reiniciar, redefinir ou recuperar o HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Como usar a ferramenta de recuperação de dispositivo do Windows para atualizar uma imagem para 1ª gen de HoloLens.
keywords: instruções, reinicialização, redefinição, recuperação, redefinição de hardware, redefinição reversível, ciclo de energia, HoloLens, desligamento, wdrt, ferramenta de recuperação de dispositivo do Windows
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308111"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Reiniciar, redefinir ou recuperar o HoloLens (1ª gen)

Se você estiver enfrentando problemas com o seu HoloLens, convém tentar uma reinicialização ou redefinição, ou até mesmo refazer o reflash do dispositivo usando a recuperação do dispositivo. Este artigo orienta você pelas etapas de recuperação recomendadas na ordem.

Se você pretende recuperar um HoloLens 2, consulte [recuperando um hololens 2](https://docs.microsoft.com/hololens/hololens-recovery), pois esse processo é diferente.

> [!NOTE]
> Este artigo se concentra no dispositivo e software do HoloLens. Se os hologramas não parecem corretos, consulte Considerações sobre o **[ambiente do HoloLens](hololens-environment-considerations.md)** para obter informações sobre fatores que melhoram a qualidade do holograma.

## <a name="restart"></a>Reiniciar

### <a name="do-a-safe-restart-by-using-cortana"></a>Fazer uma reinicialização segura usando a Cortana

A maneira mais segura de reiniciar o HoloLens é usando a Cortana, que geralmente é a primeira coisa a ser tentada quando você enfrenta um problema com o HoloLens.

> [!NOTE] 
> A Cortana não está disponível em todos os dispositivos.
> - A Cortana está disponível em todos os dispositivos de HoloLens (1º gen). 
> - A Cortana está disponível em dispositivos de HoloLens 2 em builds anteriores ao holograpic do Windows, versão 2004 atualização.

1. Ative seu HoloLens.
1. Verifique se um usuário está conectado e se o dispositivo não está aguardando uma senha para desbloqueá-lo.
2. Diga "Ei Cortana, reboot" ou "Ei Cortana, reiniciar".
3. O Cortana responderá e solicitará que você confirme. Aguarde a reprodução de um som após a pergunta e, em seguida, diga "Sim". O dispositivo será reiniciado.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Usar o botão de energia para fazer uma reinicialização segura

Se você ainda não conseguir reiniciar o dispositivo, tente reiniciá-lo usando o botão de **energia** :

1. Pressione e segure o botão de **energia** por 5 segundos. Depois de 1 segundo, todos os cinco LEDs se acenderão e desligarão lentamente um por um da direita para a esquerda. Após 5 segundos, todos os LEDs estarão desativados, indicando o desligamento bem-sucedido.
      
   > [!IMPORTANT]
   > Pare de pressionar o botão imediatamente depois que todos os LEDs estiverem desligados.
1. Aguarde 1 minuto para a conclusão do desligamento. O desligamento ainda pode estar em andamento mesmo depois que as exibições estiverem desativadas.
2. Ligue o dispositivo novamente pressionando e segurando o botão de **energia** por 1 segundo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Fazer uma reinicialização segura usando o portal de dispositivos do Windows

> [!NOTE]
> Para esse processo, o HoloLens deve ser configurado como um dispositivo de desenvolvedor. Saiba mais no [portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Se o procedimento anterior não funcionou, tente reiniciar o dispositivo usando o [portal de dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). No canto superior direito, localize a opção para reiniciar ou desligar o dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Fazer uma reinicialização forçada não segura

Se os métodos anteriores não reiniciaram o HoloLens, Force uma reinicialização. Esse método é equivalente a remover e reinstalar a bateria. É perigoso porque pode deixar seu dispositivo em um estado corrompido. Se isso acontecer, você precisará atualizar seu HoloLens.  

> [!WARNING]
> Esse é um método potencialmente prejudicial e só deve ser usado se os métodos citados anteriormente não funcionaram.

1. Pressione e mantenha pressionado o botão de **energia** por pelo menos 10 segundos.
   - Não há problema em manter o botão por mais de 10 segundos.
   - É seguro ignorar qualquer atividade de LED.
1. Solte o botão e aguarde 2-3 segundos.
1. Pressione e segure o botão de **energia** por 1 segundo.
1. Se você ainda tiver problemas, pressione o botão de **energia** por 4 segundos até que todos os indicadores de bateria apareçam e a tela pare de exibir os hologramas. Aguarde um minuto e pressione o botão de **energia** novamente para ligar o dispositivo.

## <a name="reset-to-factory-settings"></a>Redefinir para as configurações de fábrica

> [!NOTE]
> A bateria precisa de pelo menos um encargo de 40% para ser redefinido.

Se o seu HoloLens ainda tiver um problema, tente redefini-lo para o estado de fábrica. Esta etapa mantém a versão do software Holographic do Windows que está instalada e retorna todo o resto às configurações de fábrica.

>[!WARNING]
> Se você redefinir seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição do TPM. A redefinição instalará apenas a versão mais recente instalada do Windows Holographic. Você precisará refazer todas as etapas de inicialização (calibrar, conectar-se ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).

1. Abra o aplicativo Configurações e, em seguida, selecione **Atualizar**  >  **recuperação**.
1. Selecione a opção **Redefinir dispositivo** e leia a mensagem de confirmação.
1. Confirme a redefinição. O dispositivo será reiniciado e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.
1. Aguarde cerca de 30 minutos para que esse processo seja concluído. Quando terminar, o dispositivo será reiniciado na experiência "pronta para uso".

## <a name="reinstall-the-operating-system"></a>Reinstalar o sistema operacional

Se o dispositivo ainda estiver tendo um problema após a reinicialização e a redefinição, você poderá usar uma ferramenta de recuperação no computador para reinstalar o sistema operacional e o firmware do HoloLens.  

Os dados que o HoloLens precisa para a redefinição são empacotados em uma atualização completa do flash (FFU), que é semelhante a um arquivo. ISO,. wim ou. vhd. [Saiba mais sobre os formatos de arquivo de imagem FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Você pode instalar um novo sistema operacional em seu HoloLens (1ª gen) usando a ferramenta de recuperação de dispositivo do Windows. Antes de usar essa ferramenta, confira se a reinicialização ou a redefinição de seu HoloLens corrige o problema.

O processo de recuperação pode demorar um pouco. Quando terminar, a versão mais recente do software Holographic do Windows será instalada.

Para usar a ferramenta, você precisa de um computador com Windows 10 ou posterior com pelo menos 4 GB de espaço livre de armazenamento. Você não pode executar essa ferramenta em uma máquina virtual.

### <a name="recover-your-hololens"></a>Recuperar seu HoloLens

1. Baixe e instale a [ferramenta de recuperação de dispositivo do Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) em seu computador.
1. Conecte o HoloLens (1º gen) ao seu computador usando o cabo micro USB que acompanha o seu HoloLens.
1. Abra a ferramenta de recuperação de dispositivo do Windows e siga as instruções.

Se o HoloLens (1º gen) não for detectado automaticamente, selecione **meu dispositivo não foi detectado**. Em seguida, siga as instruções para colocar o dispositivo no modo de recuperação.

### <a name="manual-flashing-mode"></a>Modo de intermitência manual

Se o dispositivo não for detectado, siga estas etapas para colocá-lo no modo flash:

1. Desconecte o dispositivo de qualquer fonte de energia.
1. Se o dispositivo estiver ligado, mantenha o botão de **energia** pressionado até que ele seja completamente desligado.
2. Mantenha o botão do **volume** pressionado e toque brevemente no botão de **energia** . O dispositivo deve iniciar e exibir apenas a luz do LED do meio.
3. Conecte o dispositivo ao seu PC.
4. Abra a ferramenta de recuperação de dispositivo do Windows.
5. Selecione **meu dispositivo não foi detectado** e, em seguida, **HoloLens**. 
6. Siga as instruções para recuperar o dispositivo.
