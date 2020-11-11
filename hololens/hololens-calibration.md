---
title: Melhorar o conforto e a qualidade visual
description: A calibragem da DIP (distância interpupilar) pode melhorar a qualidade de seus elementos visuais. Os headsets imersivos do HoloLens e do Windows Mixed Reality oferecem formas de personalizar a DIP.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: calibragem, conforto, elementos visuais, qualidade, DIP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f466d64da8ef122ce2917117a74ab904a573b4e3
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163054"
---
# Melhorar o conforto e a qualidade visual

O HoloLens 2 e o HoloLens (1ª geração) funcionam melhor quando são calibrados para seus olhos exclusivamente.

Embora os dois dispositivos precisem ser calibrados para a melhor experiência de visualização de hologramas, eles usam técnicas e tecnologias de calibragem diferentes.  Vá para [Calibragem do HoloLens 2](#calibrating-your-hololens-2) ou [Calibragem do HoloLens (1ª geração)](#calibrating-your-hololens-1st-gen).

## Calibrando seu HoloLens 2

O HoloLens 2 usa a tecnologia de rastreamento ocular para melhorar a experiência de visualização e interação com o ambiente virtual. A calibragem do HoloLens 2 garante que ele possa rastrear seus olhos com precisão (e os olhos de qualquer outra pessoa que use o dispositivo). Ele também ajuda no conforto do usuário, no alinhamento do holograma e no acompanhamento da mão. Após a calibragem, os hologramas serão exibidos corretamente, mesmo que o visor mude de posição em sua cabeça.

O HoloLens 2 solicita que o usuário calibre o dispositivo nas seguintes circunstâncias:

- O usuário está usando o dispositivo pela primeira vez
- O usuário rejeitou o processo de calibragem anteriormente
- O processo de calibragem não obteve êxito na última vez em que o usuário usou o dispositivo
- O usuário excluiu os perfis de calibragem
- O dispositivo foi retirado e recolocado e qualquer uma das circunstâncias acima se aplica 


![Sistema de gerenciamento de calibragem para ajustar ocular.](./images/07-et-adjust-for-your-eyes.png)

Durante esse processo, você verá um conjunto de alvos (gems). Tudo bem se você piscar durante a calibragem, mas tente se concentrar nas joias, ao invés de outros objetos da sala.  Isso permite que o HoloLens saiba mais sobre a posição de seus olhos para renderizar o mundo holográfico.

![Sistema de gerenciamento de calibragem informa ao usuário para manter a cabeça imóvel e seguir os pontos com os olhos.](./images/07-et-hold-head-still.png)

![Sistema de gerenciamento de calibragem com exemplo de joia.](./images/08-et-gems.png)

![Ajuste do sistema de gerenciamento de calibragem.](./images/09-et-adjusting.png)

Se a calibragem for bem-sucedida, você verá uma tela de êxito.  Caso contrário, leia mais sobre como diagnosticar falhas de calibragem [aqui](#troubleshooting-hololens-2-calibration).

![Sucesso do sistema de gerenciamento de calibragem.](./images/10-et-success.png)

### Calibragem ao compartilhar um dispositivo ou uma sessão

Vários usuários podem compartilhar um dispositivo HoloLens 2, sem a necessidade de que cada pessoa passe pela configuração do dispositivo. Quando um novo usuário coloca o dispositivo em sua própria cabeça pela primeira vez, o HoloLens 2 solicita automaticamente que o usuário calibre os elementos visuais. Quando um usuário que calibrou os elementos visuais anteriormente coloca o dispositivo em sua cabeça, a exibição se ajusta perfeitamente para a qualidade e a uma experiência de visualização confortável.  

### Iniciando o processo de calibragem manual

1. Use o gesto de iniciar para abrir o [menu **Iniciar**](hololens2-basic-usage.md#start-gesture).
1. Se o aplicativo Configurações não estiver fixado em **Iniciar**, selecione **Todos os apps**.
1. Selecione **Configurações** e **Sistema** > **Calibragem** > **Calibragem dos olhos** > **Executar calibragem dos olhos**.

   ![O aplicativo Configurações, mostrando a opção Executar calibragem dos olhos](./images/C-Settings.Calibration.png)

### Suporte Automático de Posição Ocular
- Agora oferecemos maior precisão para o posicionamento do holograma por meio do Suporte Automático de Posição do Ocular para maior conforto de visualização e melhor qualidade de exibição. 

No HoloLens 2, as posições dos olhos habilitam o posicionamento preciso do holograma, experiência de visualização confortável e qualidade de exibição aprimorada. As posições dos olhos são calculadas como parte do resultado do rastreamento ocular. No entanto, isso requer que cada usuário passe pela calibragem do rastreamento ocular, mesmo quando a experiência não exigir a entrada do olhar fixo.

A ** Posição Automática Ocular (AEP)** habilita esses cenários com uma forma livre de interação de calcular as posições dos olhos para o usuário.  A Posição Automática Ocular começa a funcionar em tela de fundo automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de rastreamento ocular anterior, a posição Auto Ocular começará a fornecer as posições oculares do usuário ao sistema de exibição após um pequeno tempo de processamento. Esse tempo de processamento normalmente é de 20 a 60 segundos. Os dados do usuário não são persistentes no dispositivo e consequentemente esse processo é repetido se o usuário tirar e colocar o dispositivo novamente ou se o dispositivo for reinicializado ou acordar da suspensão.  

Existem algumas alterações de comportamento do sistema com o recurso Posição Automática Ocular quando um usuário não calibrado coloca o dispositivo. Um usuário não calibrado refere-se a alguém que não passou pelo processo de calibragem de rastreamento ocular no dispositivo anteriormente.

|     Aplicativo Ativo                           |     Comportamento Antigo                                   |     Comportamento para Windows HWindows Holographic, versão 20H2 em diante                                                     |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     Aplicativo não habilitado para o olhar ou o Shell Holográfico    |     O sistema de gerenciamento de calibragem do rastreamento ocular é exibido.    |     Nenhum sistema de gerenciamento é exibido.                                                                                |
|     Aplicativo habilitado para olhar                             |     O sistema de gerenciamento de calibragem do rastreamento ocular é exibido.    |     O sistema de gerenciamento de calibragem do rastreamento ocular é exibido apenas quando o aplicativo acessa o fluxo do olhar fixo.     |

 Se o usuário fizer a transição de um aplicativo não habilitado para olhar para um que acesse os dados do olhar, o sistema de gerenciamento de calibragem será exibido. Não haverá alterações no fluxo Experiência Imediata. 
 
Para experiências que exigem dados do olhar fixo ou posicionamento de holograma muito preciso, recomendamos que os usuários não calibrados executem a calibragem de rastreamento ocular a partir do sistema de gerenciamento de calibragem de rastreamento ocular ou abrindo as Configurações do aplicativo no menu iniciar e, em seguida, selecionando ** Sistema> Calibragem> Calibragem Ocular> Execute a calibragem ocular**.

**Problemas conhecidos**
 - Estamos investigando um problema em que o processo de host do driver do rastreador ocular pode travar ao ser executado sob carga de memória pesada. O processo de host do driver de rastreamento ocular deve se recuperar automaticamente.


### Solução de problemas de calibragem do HoloLens 2

A calibragem deve funcionar para a maioria das pessoas, mas há casos em que há falha na calibragem.
  
Alguns possíveis motivos para a falha de calibragem incluem:

- Distrair-se e não seguir os alvos de calibragem
- Visor do dispositivo sujo ou riscado ou visor do dispositivo posicionado incorretamente
- Óculos riscados ou sujos
- Certos tipos de lentes e óculos de contato (lentes de contato coloridas, algumas lentes de contato tóricas, óculos de bloqueio de IR, alguns óculos de lentes grossas, óculos de sol ou similares)
- Maquiagem forte e extensões de cílios
- Cabelos ou armações de óculos grossas que estão impedindo que o dispositivo veja seus olhos
- Certas fisiologias, quadros médicos ou cirurgias dos olhos, como olhos estreitos, cílios longos, olhos preguiçosos, nistagmo, alguns casos de LASIK ou outras cirurgias dos olhos

Se a calibragem não for bem-sucedida, tente:

- Limpar o visor do dispositivo
- Limpar seus óculos
- Colocar o visor do dispositivo o mais próximo possível de seus olhos
- Tirar do caminho os objetos em seu visor (como cabelo)
- Acender uma luz no cômodo ou sair da luz do sol direta

Se você seguiu todas as diretrizes e a calibração ainda assim falhar, você pode desabilitar a solicitação de calibragem em Configurações. Informe-nos enviando um comentário no [Hub de Feedback](hololens-feedback.md).

Consulte também as informações relacionadas para [solução de cor ou brilho da imagem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Observe que a configuração de IPD não é aplicável para o Hololens 2, uma vez que as posições de olho são computadas pelo sistema. 

### Segurança e dados de calibragem

As informações de calibragem são armazenadas localmente no dispositivo e não são associadas a informações de conta. Não há registro de quem usou o dispositivo sem a calibragem. Isso significa que os novos usuários receberão avisos para calibrar os elementos visuais quando usarem o dispositivo pela primeira vez, bem como os usuários que rejeitaram a calibragem anteriormente ou se a calibragem não foi bem-sucedida.

O dispositivo pode armazenar localmente até 50 perfis de calibragem. Quando este número for alcançado, o dispositivo exclui automaticamente o perfil não utilizado mais antigo.

As informações de calibragem sempre podem ser excluídas do dispositivo em **Configurações** > **Privacidade** > **Rastreador ocular**.  

### Desabilitar a calibragem

Você também pode desabilitar a solicitação de calibragem seguindo estas etapas:

1. Selecione **Configurações** > **Sistema** > **Calibragem**.
1. Desative **Quando uma nova pessoa usar este HoloLens, solicitar automaticamente a execução da calibragem dos olhos**.

> [!IMPORTANT]
> Essa configuração pode afetar de forma adversa a qualidade e o conforto da renderização de hologramas.  Quando você desativar essa configuração, os recursos que dependem do acompanhamento com os olhos (como a rolagem de texto) não funcionarão mais em aplicativos imersivos.

### Tecnologia de acompanhamento com os olhos do HoloLens 2

O dispositivo usa a tecnologia de rastreamento ocular para melhorar a qualidade da tela e garantir que todos os hologramas sejam posicionados com precisão e confortáveis para exibição em 3D. Como usa os olhos como pontos de referência, o dispositivo pode se ajustar para cada usuário e ajustar seus elementos visuais à medida que o headset muda de posição ao longo do uso.  Todos os ajustes acontecem instantaneamente, sem necessidade de ajuste manual.
> [!NOTE]
> Definir o IPD não é aplicável para o Hololens 2, uma vez que as posições de olho são computadas pelo sistema.

Os aplicativos do HoloLens usam o rastreamento ocular para rastrear para onde você está olhando em tempo real. Esse é o principal recurso que os desenvolvedores podem aproveitar para proporcionar um nível totalmente novo de contexto, compreensão humana e interações na experiência holográfica. Os desenvolvedores não precisam fazer nada para aproveitar esse recurso.

## Calibrando seu HoloLens (1ª geração)

O HoloLens (1ª geração) ajusta a exibição de hologramas de acordo com sua [distância interpupilar](https://en.wikipedia.org/wiki/Interpupillary_distance) (DIP). Se a DIP não for precisa, os hologramas poderão parecer instáveis ou a uma distância incorreta. Você pode melhorar a qualidade dos elementos visuais ao calibrar o dispositivo para sua distância interpupilar (DIP).

Ao configurar seu dispositivo Hololens (1ª geração), a calibragem dos elementos visuais é solicitada depois que Cortana se apresenta. É recomendável que você conclua a etapa de calibragem durante esta fase de configuração. No entanto, você pode ignorá-la ao aguardar até que a Cortana a solicite e dizer "Skip" (Ignorar).

Durante o processo de calibragem, o HoloLens solicita que você alinhe o dedo com uma série de seis alvos por olho. O HoloLens usa esse processo para definir a DIP corretamente para seus olhos.

![Tela de alinhamento do dedo da DIP na segunda etapa](./images/ipd-finger-alignment-300px.jpg)

### Iniciar o processo de calibragem manual

Se você precisar atualizar a calibragem, ou se um novo usuário precisar ajustá-la, poderá executar o aplicativo Calibragem manualmente a qualquer momento. O aplicativo Calibragem é instalado por padrão. Você pode acessá-lo usando o menu **Iniciar** ou o aplicativo Configurações.

Para usar o menu **Iniciar** para executar o aplicativo Calibragem, siga estas etapas:

1. Use o gesto de [abrir a mão](hololens1-basic-usage.md) para abrir o menu **Iniciar**.
1. Para exibir todos os aplicativos, selecione **+**.
1. Selecione **Calibragem**.

![Acessando o aplicativo de calibragem no shell](./images/calibration-shell.png)

![O aplicativo de calibragem exibido como um cubo mágico depois de ser iniciado](./images/calibration-livecube-200px.png)

Para usar aplicativo Configurações para executar o aplicativo Calibragem, siga estas etapas:

1. Use o gesto de [abrir a mão](hololens1-basic-usage.md) para abrir o menu **Iniciar**.
1. Se **Configurações** não estiver fixado em **Iniciar**, selecione **+** para exibir todos os aplicativos.
1. Selecione **Configurações**.
1. Selecione **Sistema** > **Utilitários** > **Abrir Calibragem**.

![Iniciando o aplicativo de calibragem no aplicativo de configurações](./images/calibration-settings-500px.jpg)

## Headsets imersivos

Alguns headsets imersivos permitem personalizar a configuração de DIP. Para alterar a DIP para seu headset, abra o aplicativo Configurações e selecione **Realidade misturada** > **Exibição do headset** e mova o controle deslizante. Você verá as alterações em tempo real no seu headset. Se você sabe sua DIP, talvez por conta de uma visita ao oftalmologista, também pode digitá-la diretamente.

Você também pode ajustar essa configuração no computador selecionando **Configurações** > **Realidade misturada** > **Exibição do headset**.

Se o headset não oferecer suporte à personalização de DIP, essa configuração será desabilitada.
