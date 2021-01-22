---
title: Melhorar o conforto e a qualidade visual
description: Aprenda a calibrar sua distância interpupilar (IPD) para melhorar a qualidade de seus visuais em dispositivos HoloLens.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: calibração, conforto, visuais, qualidade, ipd, HoloLens, Windows Mixed Reality, headset VR
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283542"
---
# Melhorar o conforto e a qualidade visual

O HoloLens 2 e o HoloLens (1ª geração) funcionam melhor quando são calibrados para seus olhos exclusivamente.

Embora os dois dispositivos precisem ser calibrados para a melhor experiência de visualização de hologramas, eles usam técnicas e tecnologias de calibragem diferentes.  Vá para [Calibragem do HoloLens 2](#calibrating-your-hololens-2) ou [Calibragem do HoloLens (1ª geração)](#calibrating-your-hololens-1st-gen).

## Calibrando seu HoloLens 2

O HoloLens 2 usa a tecnologia de rastreamento ocular para melhorar a experiência de visualização e interação com o ambiente virtual. A calibragem do HoloLens 2 garante que ele possa rastrear seus olhos com precisão (e os olhos de qualquer outra pessoa que use o dispositivo). Ele também ajuda no conforto do usuário, no alinhamento do holograma e no acompanhamento da mão. Após a calibragem, os hologramas serão exibidos corretamente, mesmo que o visor mude de posição em sua cabeça.

O HoloLens 2 solicita que o usuário calibre o dispositivo nas seguintes circunstâncias:

- O usuário está usando o dispositivo pela primeira vez
- O usuário rejeitou o processo de calibragem anteriormente
- O processo de calibração não teve sucesso na última vez que o usuário usou o dispositivo
- O usuário excluiu os perfis de calibragem
- O dispositivo é retirado e colocado de volta e qualquer uma das circunstâncias acima se aplica 


![Sistema de gerenciamento de calibragem para ajustar ocular.](./images/07-et-adjust-for-your-eyes.png)

Durante esse processo, você verá um conjunto de alvos (gems). Tudo bem se você piscar durante a calibragem, mas tente se concentrar nas joias, ao invés de outros objetos da sala.  Focar nas joias permite que o HoloLens aprenda sobre a posição de seus olhos para renderizar seu mundo holográfico.

![Sistema de gerenciamento de calibragem informa ao usuário para manter a cabeça imóvel e seguir os pontos com os olhos.](./images/07-et-hold-head-still.png)

![Sistema de gerenciamento de calibragem com exemplo de joia.](./images/08-et-gems.png)

![Ajuste do sistema de gerenciamento de calibragem.](./images/09-et-adjusting.png)

Se a calibragem for bem-sucedida, você verá uma tela de êxito.  Caso não seja, leia mais sobre [como diagnosticar falhas de calibragem.](#troubleshooting-hololens-2-calibration)

![Sucesso do sistema de gerenciamento de calibragem.](./images/10-et-success.png)

### Calibragem ao compartilhar um dispositivo ou uma sessão

Vários usuários podem compartilhar um dispositivo HoloLens 2, sem a necessidade de que cada pessoa passe pela configuração do dispositivo. Quando um novo usuário coloca o dispositivo em sua própria cabeça pela primeira vez, o HoloLens 2 solicita automaticamente que o usuário calibre os elementos visuais. Quando um usuário que calibrou os elementos visuais anteriormente coloca o dispositivo em sua cabeça, a exibição se ajusta perfeitamente para a qualidade e a uma experiência de visualização confortável.  

### Iniciando o processo de calibragem manual

1. Use o gesto de iniciar para abrir o [menu **Iniciar**](hololens2-basic-usage.md#start-gesture).
1. Se o aplicativo Configurações não estiver fixado em **Iniciar**, selecione **Todos os apps**.
1. Selecione **Configurações** e **Sistema** > **Calibragem** > **Calibragem dos olhos** > **Executar calibragem dos olhos**.

   ![O aplicativo Configurações, mostrando a opção Executar calibragem dos olhos](./images/C-Settings.Calibration.png)

### Suporte Automático de Posição Ocular

No HoloLens 2, as posições dos olhos permitem um posicionamento preciso do holograma, uma experiência de visualização confortável e uma qualidade de exibição aprimorada. As posições do olho são calculadas internamente como parte da computação de rastreamento ocular. Entretanto, isso requer que cada usuário passe pela calibragem de rastreamento ocular, mesmo quando a experiência possa não requerer a entrada do olhar fixo.

A ** Posição Automática Ocular (AEP)** habilita esses cenários com uma forma livre de interação de calcular as posições dos olhos para o usuário. A posição automática dos olhos começa a funcionar em tela de fundo automaticamente a partir do momento em que o usuário coloca no dispositivo. Se o usuário não tiver uma calibração de rastreamento ocular anterior, a posição automática dos olhos começará a fornecer as posições dos olhos do usuário para o sistema de exibição após um tempo de processamento de 20 a 30 segundos. Os dados do usuário não são persistentes no dispositivo e este processo é repetido se o usuário decolar e colocar o dispositivo novamente ou se o dispositivo for reinicializado ou acordar do repouso.

Há algumas alterações de comportamento do sistema com o recurso Posição Automática Ocular quando um usuário não calibrado coloca o dispositivo. Nesse contexto, um usuário não calibrado se refere a alguém que não passou pelo processo de calibração do rastreamento ocular no dispositivo anteriormente.

| Aplicativo Ativo | Comportamento Anterior | Comportamento do Windows Holográfico, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo não habilitado para olhar ou o Shell Holográfico |A caixa de diálogo do sistema de gerenciamento de calibragem do rastreamento ocular é exibida. | Nenhum sistema de gerenciamento é exibido. |
| Aplicativo habilitado para olhar | A caixa de diálogo do sistema de gerenciamento de calibragem do rastreamento ocular é exibida. | O aviso de calibragem de rastreamento ocular é exibido apenas quando o aplicativo acessa o fluxo do olhar fixo. |

Se o usuário fizer a transição de um aplicativo não habilitado para olhar para um que acesse os dados do olhar, o sistema de gerenciamento de calibragem será exibido. 

Todos os outros comportamentos do sistema serão semelhantes a quando o usuário atual não tem uma calibração de rastreamento ocular ativa. Por exemplo, o gesto de início com uma mão não será ativado. Não haverá nenhuma alteração na Experiência Inicial do programa de instalação inicial.

Para experiências que requerem dados do olhar fixo ou posicionamento preciso do holograma, recomendamos que os usuários não calibrados executem a calibração do rastreamento ocular. É acessível a partir do prompt de calibração de rastreamento ocular ou iniciando o aplicativo Configurações no menu inicial e, em seguida, selecionando **Sistema> Calibração > Calibração ocular> Executar calibração ocular**.

#### Aviso de Calibragem Adiado

Com a Posição Ocular Automática, a caixa de diálogo de aviso de Calibragem de Rastreamento Ocular é adiada até que um aplicativo solicite dados Olhar. Isso garante que não haja nenhum prompt para o usuário quando o aplicativo ativo não requerer olhar. Se o aplicativo exigir dados fixos e o usuário atual não estiver calibrado, será apresentado ao usuário um prompt de calibração. Esse comportamento pode ser usado para exibir o aviso de calibragem de rastreamento ocular em um momento adequado para a experiência. Esse método é recomendado pelos seguintes motivos

1.  A caixa de diálogo de Aviso de Calibragem de Rastreamento Ocular fornece ao usuário detalhes sobre por que o rastreamento de olho é necessário.
2.  Apresenta ao usuário uma maneira de recusar que seus olhos sejam calibrados.

Se o usuário escolher iniciar a Calibragem de Rastreamento Ocular, o foco deve retornar ao aplicativo original após a calibragem ser concluída. 

### Solução de problemas de calibragem do HoloLens 2

A calibragem deve funcionar para a maioria das pessoas, mas há casos em que há falha na calibragem.
  
Alguns possíveis motivos para a falha de calibragem incluem:

- Distrair-se e não seguir os alvos de calibragem
- Visor do dispositivo sujo ou riscado ou visor do dispositivo posicionado incorretamente
- Óculos riscados ou sujos
- Certos tipos de lentes e óculos de contato (lentes de contato coloridas, algumas lentes de contato tóricas, óculos de bloqueio de IR, alguns óculos de lentes grossas, óculos de sol ou similares)
- Maquiagem forte e extensões de cílios
- Cabelo ou armações de óculos grossas, se estiverem bloqueando o dispositivo de ver seus olhos
- Certas fisiologia ocular, condições oculares ou cirurgia ocular, como olhos estreitos, cílios longos, ambliopia, nistagmo, alguns casos de LASIK ou outras cirurgias oculares

Se a calibragem não for bem-sucedida, tente:

- Limpar o visor do dispositivo
- Limpar seus óculos
- Colocar o visor do dispositivo o mais próximo possível de seus olhos
- Tirar do caminho os objetos em seu visor (como cabelo)
- Acender uma luz no cômodo ou sair da luz do sol direta

Se você seguiu todas as diretrizes e a calibração ainda assim falhar, você pode desabilitar a solicitação de calibragem em Configurações. Também nos avise arquivando comentários no [Hub de Comentários](hololens-feedback.md).

Confira também as informações relacionadas para [solução de problemas de cor ou brilho da imagem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

A configuração de IPD não é aplicável ao HoloLens 2, uma vez que as posições dos olhos são calculadas pelo sistema. 

### Segurança e dados de calibragem

As informações de calibração são armazenadas localmente no dispositivo e não estão associadas a nenhuma informação da conta. Não há registro de quem usou o dispositivo sem calibração. Isso significa que os novos usuários serão solicitados a calibrar os visuais quando usarem o dispositivo pela primeira vez, e os usuários que optaram por sair da calibração anteriormente ou se a calibração não foi bem-sucedida.

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

Os aplicativos HoloLens usam rastreamento ocular para rastrear para onde você está olhando em tempo real. Este é o principal recurso que os desenvolvedores podem usar para permitir um nível totalmente novo de contexto, compreensão humana e interações dentro da experiência holográfica. Os desenvolvedores não precisam fazer nada para usar esse recurso.

## Calibrando seu HoloLens (1ª geração)

HoloLens (1ª geração) ajusta a exibição do holograma de acordo com sua [distância interpupilar](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Se o IPD não for preciso, os hologramas poderão parecer instável ou a uma distância incorreta. Você pode melhorar a qualidade dos elementos visuais ao calibrar o dispositivo para sua distância interpupilar (DIP).

Quando você configura o seu dispositivo HoloLens (1ª geração), ele solicita calibrar os seus elementos visuais depois que a Cortana se apresenta. É recomendável que você conclua a etapa de calibragem durante esta fase de configuração. No entanto, você pode ignorá-la ao aguardar até que a Cortana a solicite e dizer "Skip" (Ignorar).

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

Se o seu headset não for compatível com a personalização de IPD, esta configuração será desabilitada.
