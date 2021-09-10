---
title: Aprimorar o conforto e a qualidade visual
description: Saiba calibrar sua IPD (distância interpupilar) para aprimorar a qualidade de seus visuais em dispositivos HoloLens.
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
keywords: calibragem, conforto, visuais, qualidade, ipd, HoloLens, Windows Mixed Reality, headsets VR
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427853"
---
# <a name="improve-visual-quality-and-comfort"></a>Aprimorar o conforto e a qualidade visual

O HoloLens 2 e o HoloLens (1ª geração) funcionam melhor quando são calibrados para seus olhos exclusivamente.

Embora os dois dispositivos precisem ser calibrados para a melhor experiência de visualização de hologramas, eles usam técnicas e tecnologias de calibragem diferentes.  Vá diretamente para [Calibragem do HoloLens 2](#calibrating-your-hololens-2) ou [Calibragem do HoloLens (1ª geração)](#calibrating-your-hololens-1st-gen).

## <a name="calibrating-your-hololens-2"></a>Calibrando seu HoloLens 2

O HoloLens 2 usa a tecnologia de rastreamento ocular para melhorar a experiência de visualização e interação com o ambiente virtual. A calibragem do HoloLens 2 garante que ele possa rastrear seus olhos com precisão (e os olhos de qualquer outra pessoa que use o dispositivo). Ele também ajuda no conforto do usuário, no alinhamento do holograma e no acompanhamento da mão. Após a calibragem, os hologramas serão exibidos corretamente mesmo que o visor mude de posição em sua cabeça.

O HoloLens 2 solicita que o usuário calibre o dispositivo nas seguintes circunstâncias:

- O usuário está usando o dispositivo pela primeira vez
- O usuário rejeitou o processo de calibragem anteriormente
- O processo de calibragem não teve sucesso na última vez que o usuário usou o dispositivo
- O usuário excluiu os perfis de calibragem
- O dispositivo é retirado e colocado de volta e qualquer uma das circunstâncias acima se aplica 


![Prompt de calibragem para ajuste ocular.](./images/07-et-adjust-for-your-eyes.png)

Durante esse processo, você verá um conjunto de alvos (joias). Tudo bem se você piscar durante a calibragem, mas tente se concentrar nas joias, e não em outros objetos da sala.  Focar nas joias permite que o HoloLens aprenda sobre a posição de seus olhos para renderizar seu mundo holográfico.

![O prompt de calibragem informa ao usuário para manter a cabeça imóvel e seguir os pontos com os olhos.](./images/07-et-hold-head-still.png)

![Prompt de calibragem com exemplo de joia.](./images/08-et-gems.png)

![Ajuste do prompt de calibragem.](./images/09-et-adjusting.png)

Se a calibragem for bem-sucedida, você verá uma tela de êxito.  Caso contrário, leia mais sobre como [diagnosticar falhas de calibragem](hololens2-display.md#troubleshooting).

![Êxito do prompt de calibragem.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Calibragem ao compartilhar um dispositivo ou uma sessão

Vários usuários podem compartilhar um dispositivo HoloLens 2, sem a necessidade de que cada pessoa passe pela configuração do dispositivo. Quando um novo usuário coloca o dispositivo em sua própria cabeça pela primeira vez, o HoloLens 2 solicita automaticamente que o usuário calibre os elementos visuais. Quando um usuário que calibrou os elementos visuais anteriormente coloca o dispositivo em sua cabeça, a exibição se ajusta perfeitamente para a qualidade e a uma experiência de visualização confortável.  

### <a name="manually-starting-the-calibration-process"></a>Iniciando o processo de calibragem manualmente

1. Use o gesto de iniciar para abrir o [**menu Iniciar**](hololens2-basic-usage.md#start-gesture).
1. Se o aplicativo Configurações não estiver fixado em a **Iniciar**, selecione **Todos os Aplicativos**.
1. Selecione **Configurações** e escolha **Sistema** > **Calibragem** > **Calibragem Ocular** > **Executar calibragem ocular**.

   ![O aplicativo Configurações, mostrando a opção Executar calibragem ocular.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Suporte Automático de Posição Ocular

No HoloLens 2, as posições dos olhos permitem um posicionamento preciso do holograma, uma experiência de visualização confortável e uma qualidade de exibição aprimorada. As posições do olho são calculadas internamente como parte da computação de rastreamento ocular. Entretanto, isso requer que cada usuário passe pela calibragem de rastreamento ocular, mesmo quando a experiência possa não requerer a entrada do olhar fixo.

A **AEP (Posição Automática dos Olhos)** habilita esses cenários com uma forma livre de interação para calcular as posições dos olhos para o usuário. A posição automática dos olhos começa a funcionar em tela de fundo automaticamente quando o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de rastreamento ocular anterior, a posição automática dos olhos começará a fornecer as posições dos olhos do usuário para o sistema de exibição após um tempo de processamento de 20 a 30 segundos. Os dados do usuário não são persistentes no dispositivo. Esse processo será repetido se o usuário retirar e colocar o dispositivo de volta ou se o dispositivo for reinicializado ou acordar do repouso.

Há algumas alterações de comportamento do sistema com o recurso Posição Automática Ocular quando um usuário não calibrado coloca o dispositivo. Nesse contexto, um usuário não calibrado se refere a alguém que não passou pelo processo de calibragem do rastreamento ocular no dispositivo anteriormente.

| Aplicativo Ativo | Comportamento Anterior | Comportamento do Windows Holográfico, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo não habilitado para olhar ou o Shell Holográfico |A caixa de diálogo do prompt de calibragem do rastreamento ocular é exibida. | Nenhum prompt é exibido. |
| Aplicativo habilitado para olhar | A caixa de diálogo do prompt de calibragem do rastreamento ocular é exibida. | O prompt de calibragem de rastreamento ocular é exibido apenas quando o aplicativo acessa o fluxo do olhar fixo. |

Se o usuário fizer a transição de um aplicativo não habilitado para olhar para um que acesse os dados do olhar, o prompt de calibragem será exibido. 

Todos os outros comportamentos do sistema serão semelhantes a quando o usuário atual não tem uma calibragem de rastreamento ocular ativa. Por exemplo, o gesto de iniciar com uma mão não será habilitado. Não haverá nenhuma alteração na Experiência Inicial do programa de instalação inicial.

Para experiências que requerem dados do olhar fixo ou posicionamento preciso do holograma, recomendamos que os usuários não calibrados executem a calibragem do rastreamento ocular. É acessível pelo prompt de calibragem de rastreamento ocular ou iniciando o aplicativo Configurações no menu inicial e, em seguida, selecionando **Sistema > Calibragem > Calibragem Ocular > Executar calibragem ocular**.

#### <a name="deferred-calibration-prompt"></a>Prompt de Calibragem Adiado

Com a Posição Ocular Automática, a caixa de diálogo de prompt de Calibragem de Rastreamento Ocular é adiada até que um aplicativo solicite dados Olhar. Isso garante que não haja nenhum prompt para o usuário quando o aplicativo ativo não requerer olhar. Se o aplicativo exigir dados fixos e o usuário atual não estiver calibrado, será apresentado ao usuário um prompt de calibragem. Esse comportamento pode ser usado para exibir o prompt de calibragem de rastreamento ocular em um momento adequado para a experiência. Esse método é recomendado pelos seguintes motivos

1.  A caixa de diálogo de Prompt de Calibragem de Rastreamento Ocular fornece ao usuário detalhes sobre por que o rastreamento de olho é necessário.
2.  Apresenta ao usuário um modo de recusar que seus olhos sejam calibrados.

Se o usuário escolher iniciar a Calibragem de Acompanhamento Ocular, o foco deverá retornar ao aplicativo original após a calibragem ser concluída. 

### <a name="calibration-data-and-security"></a>Segurança e dados de calibragem

As informações de calibragem são armazenadas localmente no dispositivo e não estão associadas a nenhuma informação da conta. Não há registro de quem usou o dispositivo sem calibragem. Isso significa que os novos usuários serão solicitados a calibrar os visuais quando usarem o dispositivo pela primeira vez, bem como os usuários que optaram por sair da calibragem anteriormente ou se a calibragem não tiver sido bem-sucedida.

O dispositivo pode armazenar localmente até 50 perfis de calibragem. Quando esse número for alcançado, o dispositivo excluirá automaticamente o perfil não usado mais antigo.

As informações de calibragem sempre podem ser excluídas do dispositivo em **Configurações** > **Privacidade** > **Rastreador ocular**.  

### <a name="disable-calibration"></a>Desabilitar a calibragem

Você também pode desabilitar o prompt de calibragem seguindo estas etapas:

1. Selecione **Configurações** > **Sistema** > **Calibragem**.
1. Desligue **Quando uma nova pessoa usar este HoloLens, pedir automaticamente para executar a calibragem ocular**.

   > [!IMPORTANT]
   > Essa configuração pode afetar de modo adverso a qualidade e o conforto da renderização de hologramas.  Quando você desligar essa configuração, os recursos que dependem do acompanhamento com os olhos (como a rolagem de texto) não funcionarão mais em aplicativos imersivos.

> [!NOTE]
> A opção Configurações foi removida da versão 20H2 em diante do Windows Holographic, com o início do [suporte à Posição Automática dos Olhos](hololens-release-notes.md#auto-eye-position-support). O aviso de calibragem será exibido automaticamente somente se um usuário não calibrado estiver usando um aplicativo habilitado para acompanhamento de olho.

### <a name="hololens-2-eye-tracking-technology"></a>Tecnologia de acompanhamento ocular do HoloLens 2

O dispositivo usa a tecnologia de rastreamento ocular para melhorar a qualidade da tela e garantir que todos os hologramas sejam posicionados com precisão e confortáveis para exibição em 3D. Como usa os olhos como pontos de referência, o dispositivo pode se ajustar para cada usuário e ajustar seus elementos visuais à medida que o headset muda de posição ao longo do uso.  Todos os ajustes acontecem instantaneamente, sem necessidade de ajuste manual.
> [!NOTE]
> Definir o IPD não é aplicável para o Hololens 2, uma vez que as posições de olho são computadas pelo sistema.

Os aplicativos HoloLens usam rastreamento ocular para rastrear para onde você está olhando em tempo real. Esta é a principal funcionalidade que os desenvolvedores podem usar para permitir um nível totalmente novo de contexto, compreensão humana e interações dentro da experiência holográfica. Os desenvolvedores não precisam fazer nada para usar essa funcionalidade.

## <a name="calibrating-your-hololens-1st-gen"></a>Calibrando seu HoloLens (1ª geração)

O HoloLens (1ª geração) ajusta a exibição do holograma de acordo com sua [IPD (distância interpupilar)](https://en.wikipedia.org/wiki/Interpupillary_distance). Se a IPD não for precisa, os hologramas poderão parecer instável ou a uma distância incorreta. Você pode melhorar a qualidade dos elementos visuais ao calibrar o dispositivo para sua IPD (distância interpupilar).

Quando você configura o seu dispositivo HoloLens (1ª geração), ele solicita calibrar os seus elementos visuais depois que a Cortana se apresenta. É recomendável que você conclua a etapa de calibragem durante esta fase de configuração. No entanto, você pode ignorá-la ao aguardar até que a Cortana solicite e dizer "Ignorar".

Durante o processo de calibragem, o HoloLens solicita que você alinhe o dedo com uma série de seis alvos por olho. O HoloLens usa esse processo para definir a IPD corretamente para seus olhos.

![Tela de alinhamento de IPD com o dedo na segunda etapa.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Iniciar o processo de calibragem manual

Se você precisar atualizar a calibragem, ou se um novo usuário precisar ajustá-la, você poderá executar o aplicativo Calibragem manualmente a qualquer momento. O aplicativo Calibragem é instalado por padrão. Você pode acessá-lo usando o menu **Iniciar** ou o aplicativo Configurações.

Para usar o menu **Iniciar** para executar o aplicativo Calibragem, siga estas etapas:

1. Use o gesto de [abrir a mão](hololens1-basic-usage.md) para abrir o menu **Iniciar**.
1. Para exibir todos os aplicativos, selecione **+** .
1. Selecione **Calibragem**.

   ![Acessando o aplicativo de calibragem no shell.](./images/calibration-shell.png)

   ![O aplicativo de calibragem exibido como um cubo mágico depois de ser iniciado.](./images/calibration-livecube-200px.png)

Para usar aplicativo Configurações para executar o aplicativo Calibragem, siga estas etapas:

1. Use o gesto de [abrir a mão](hololens1-basic-usage.md) para abrir o menu **Iniciar**.
1. Se **Configurações** não estiver fixado em **Iniciar**, selecione **+** para exibir todos os aplicativos.
1. Selecione **Configurações**.
1. Selecione **Sistema** > **Utilitários** > **Abrir Calibragem**.

   ![Iniciando o aplicativo de calibragem no aplicativo de configurações.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Headsets imersivos

Alguns headsets imersivos permitem personalizar a configuração de IPD. Para alterar a IPD do headset, abra o aplicativo Configurações e selecione **Realidade misturada** > **Exibição do headset** e mova o controle deslizante. Você verá as alterações em tempo real no seu headset. Se você sabe sua IPD, talvez por conta de uma visita ao oftalmologista, também pode digitá-la diretamente.

Você também pode ajustar essa configuração no PC selecionando **Configurações** > **Realidade misturada** > **Exibição do headset**.

Se o seu headset não for compatível com a personalização de IPD, esta configuração será desabilitada.
