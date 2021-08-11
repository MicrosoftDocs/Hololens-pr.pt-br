---
title: reiniciar, redefinir ou recuperar HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: como usar Windows ferramenta de recuperação de dispositivo para atualizar uma imagem para HoloLens 1ª Gen.
keywords: instruções, reinicialização, redefinição, recuperação, redefinição de hardware, redefinição reversível, ciclo de energia, HoloLens, desligar, wdrt, ferramenta de recuperação de dispositivo do windows
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
ms.openlocfilehash: d6eb706c50e97a81910180c70be1d9dbc52bc6603cbc77ad130c1dd3b6a9010e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661816"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>reiniciar, redefinir ou recuperar HoloLens (1ª Gen)

se você estiver enfrentando problemas com seu HoloLens, convém tentar uma reinicialização ou redefinição, ou até mesmo refazer o reflash do dispositivo usando a recuperação do dispositivo. Este artigo orienta você pelas etapas de recuperação recomendadas na ordem.

se você pretende recuperar um HoloLens 2, consulte [recuperando um HoloLens 2](hololens-recovery.md), pois esse processo é diferente.

> [!NOTE]
> este artigo se concentra na HoloLens dispositivo e software. se os hologramas não parecem corretos, consulte **[HoloLens considerações](hololens-environment-considerations.md)** sobre o ambiente para obter informações sobre fatores que melhoram a qualidade do holograma.

## <a name="restart"></a>Reiniciar

### <a name="do-a-safe-restart-by-using-cortana"></a>Faça uma reinicialização segura usando Cortana

a maneira mais segura de reiniciar o HoloLens é usando Cortana, que é geralmente a primeira coisa a ser tentada quando você enfrenta um problema com HoloLens.

> [!NOTE] 
> Cortana não está disponível em todos os dispositivos.
> - Cortana está disponível em todos os dispositivos HoloLens (1ª Gen). 
> - Cortana está disponível em HoloLens 2 dispositivos em builds antes da atualização do Windows Holograpic, versão 2004.

1. Ative seu HoloLens.
1. Verifique se um usuário está conectado e se o dispositivo não está aguardando uma senha para desbloqueá-lo.
2. diga "ei Cortana, reinicializar" ou "ei Cortana, reiniciar."
3. Cortana responderá e solicitará que você confirme. Aguarde a reprodução de um som após a pergunta e, em seguida, diga "Sim". O dispositivo será reiniciado.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Usar o botão de energia para fazer uma reinicialização segura

Se você ainda não conseguir reiniciar o dispositivo, tente reiniciá-lo usando o botão de **energia** :

1. Pressione e segure o botão de **energia** por 5 segundos. Depois de 1 segundo, todos os cinco LEDs se acenderão e desligarão lentamente um por um da direita para a esquerda. Após 5 segundos, todos os LEDs estarão desativados, indicando o desligamento bem-sucedido.
      
   > [!IMPORTANT]
   > Pare de pressionar o botão imediatamente depois que todos os LEDs estiverem desligados.
1. Aguarde 1 minuto para a conclusão do desligamento. O desligamento ainda pode estar em andamento mesmo depois que as exibições estiverem desativadas.
2. Ligue o dispositivo novamente pressionando e segurando o botão de **energia** por 1 segundo.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>fazer uma reinicialização segura usando Windows Portal do dispositivo

> [!NOTE]
> para esse processo, HoloLens precisa ser configurado como um dispositivo de desenvolvedor. saiba mais em [Windows Portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal).

se o procedimento anterior não funcionou, tente reiniciar o dispositivo usando [Windows Portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal). No canto superior direito, localize a opção para reiniciar ou desligar o dispositivo.

### <a name="do-an-unsafe-forced-restart"></a>Fazer uma reinicialização forçada não segura

se os métodos anteriores não reiniciaram o HoloLens, force uma reinicialização. Esse método é equivalente a remover e reinstalar a bateria. É perigoso porque pode deixar seu dispositivo em um estado corrompido. Se isso acontecer, você precisará atualizar seu HoloLens.  

> [!WARNING]
> Esse é um método potencialmente prejudicial e só deve ser usado se os métodos citados anteriormente não funcionaram.

1. Pressione e mantenha pressionado o botão de **energia** por pelo menos 10 segundos.
   - Não há problema em manter o botão por mais de 10 segundos.
   - É seguro ignorar qualquer atividade de LED.
1. Solte o botão e aguarde 2-3 segundos.
1. Pressione e segure o botão de **energia** por 1 segundo.
1. Se você ainda tiver problemas, pressione o botão de **energia** por 4 segundos até que todos os indicadores de bateria apareçam e a tela pare de exibir os hologramas. Aguarde um minuto e pressione o botão de **energia** novamente para ligar o dispositivo.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>voltar para uma versão anterior-HoloLens (1ª Gen)

em alguns casos, talvez você queira voltar para uma versão anterior do software HoloLens. você pode fazer isso usando a ferramenta de recuperação de dispositivo Windows para redefinir o HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

para voltar para uma versão anterior do HoloLens 1, siga estas etapas:

1. certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.
1. no seu computador, baixe a [WDRT (ferramenta de recuperação de dispositivo) do Windows](https://support.microsoft.com/help/12379).
1. Faça download do [pacote de recuperação HoloLens Anniversary Update](https://aka.ms/hololensrecovery).
1. Quando o download for concluído, abra o **Explorador de arquivos**  >  **downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.
1. Conexão seu HoloLens ao seu PC usando o cabo micro USB com o qual ele veio. (mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)
1. O WDRT detectará automaticamente seu HoloLens. Escolha o bloco **Microsoft HoloLens**.
1. Na próxima tela, selecione **seleção de pacote manual** e escolha o arquivo de instalação contido na pasta descompactada na etapa 4. (Procure um arquivo com a extensão. FFU.)
1. Selecione **instalar software** e siga as instruções.

> [!NOTE]
> se o WDRT não detectar sua HoloLens, tente reiniciar o computador. Se isso não funcionar, escolha **Meu dispositivo não foi detectado**, **Microsoft HoloLens** e siga as instruções.

## <a name="reset-to-factory-settings"></a>Redefinir para as configurações de fábrica

> [!NOTE]
> A bateria precisa de pelo menos um encargo de 40% para ser redefinido.

se seu HoloLens ainda tiver um problema, tente redefini-lo para o estado de fábrica. esta etapa mantém a versão do Windows software Holographic que está instalado e retorna todas as outras configurações de fábrica.

>[!WARNING]
> Se você redefinir seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo informações de redefinição do TPM. a redefinição instalará apenas a versão mais recente instalada do Windows Holographic. Você precisará refazer todas as etapas de inicialização (calibrar, conectar-se ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).

1. abra o aplicativo Configurações e, em seguida, selecione **atualizar**  >  **recuperação**.
1. Selecione a opção **Redefinir dispositivo** e leia a mensagem de confirmação.
1. Confirme a redefinição. O dispositivo será reiniciado e exibirá um conjunto de engrenagens giratórias e uma barra de progresso.
1. Aguarde cerca de 30 minutos para que esse processo seja concluído. Quando terminar, o dispositivo será reiniciado na experiência "pronta para uso".

## <a name="reinstall-the-operating-system"></a>Reinstalar o sistema operacional

se o dispositivo ainda estiver tendo um problema após a reinicialização e a redefinição, você poderá usar uma ferramenta de recuperação no computador para reinstalar o sistema operacional HoloLens e o firmware.  

os dados que HoloLens necessidades da redefinição são empacotados em uma atualização completa do Flash (FFU), que é semelhante a um arquivo. iso,. wim ou. vhd. [Saiba mais sobre os formatos de arquivo de imagem FFU.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

você pode instalar um novo sistema operacional em seu HoloLens (1ª gen) usando a ferramenta de recuperação de dispositivo Windows. antes de usar essa ferramenta, confira se a reinicialização ou a redefinição de seu HoloLens corrige o problema.

O processo de recuperação pode demorar um pouco. quando terminar, a versão mais recente do Windows software Holographic será instalada.

para usar a ferramenta, você precisa de um computador executando o Windows 10 ou posterior com pelo menos 4 GB de espaço livre de armazenamento. Você não pode executar essa ferramenta em uma máquina virtual.

### <a name="recover-your-hololens"></a>Recuperar seu HoloLens

1. baixe e instale a [ferramenta de recuperação de dispositivo Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) em seu computador.
1. Conexão o HoloLens (1º gen) ao seu computador usando o cabo Micro USB que acompanha o HoloLens.
1. abra a ferramenta de recuperação de dispositivo Windows e siga as instruções.

se a HoloLens (1ª gen) não for detectada automaticamente, selecione **meu dispositivo não foi detectado**. Em seguida, siga as instruções para colocar o dispositivo no modo de recuperação.

### <a name="manual-flashing-mode"></a>Modo de intermitência manual

Se o dispositivo não for detectado, siga estas etapas para colocá-lo no modo flash:

1. Desconecte o dispositivo de qualquer fonte de energia.
1. Se o dispositivo estiver ligado, mantenha o botão de **energia** pressionado até que ele seja completamente desligado.
2. Mantenha o **botão de volume pressionado** e toque brevemente no botão **de** energia. O dispositivo deve iniciar e exibir apenas o LED do meio.
3. Conecte o dispositivo ao computador.
4. Abra a ferramenta Windows recuperação de dispositivo.
5. Selecione **Meu dispositivo não foi detectado e,** em **seguida, HoloLens**. 
6. Siga as instruções para recuperar seu dispositivo.
