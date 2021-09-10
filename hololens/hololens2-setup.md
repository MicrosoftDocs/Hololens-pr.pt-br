---
title: Preparar um novo HoloLens 2
description: Aprenda a configurar e ajustar seu dispositivo HoloLens 2 pela primeira vez, incluindo dicas de integridade e segurança e guias de hardware.
keywords: hololens, luzes, ajustar, conforto, partes
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 77c061c53806e7410d73ecf3aaa20d74c217ea33
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190405"
---
# <a name="get-your-hololens-2-ready-to-use"></a>Preparar seu HoloLens 2 para usar

Os procedimentos a seguir o ajudarão a configurar um HoloLens 2 pela primeira vez.

## <a name="charge-your-hololens"></a>Carregar seu HoloLens

Conecte a fonte de alimentação à porta de carregamento usando o cabo USB-C (incluído). Conecte a fonte de alimentação a uma tomada elétrica. A fonte de alimentação e o cabo USB-C-to-C que acompanham o dispositivo são a melhor maneira de carregar seu HoloLens 2. O carregador fornece 18 W de potência (9 V a 2 A). Usando o carregador de parede fornecido, os dispositivos HoloLens 2 podem carregar a bateria completamente em menos de 65 minutos quando o dispositivo está em espera.

A taxa e a velocidade da carga podem variar de acordo com o ambiente no qual o dispositivo está sendo executado.

- Quando o dispositivo estiver sendo carregado, o indicador de bateria acenderá para indicar o nível de carga atual.  A última luz acenderá e apagará para indicar o carregamento ativo.
- Quando seu HoloLens está ligado, o indicador de bateria exibe o nível da bateria em incrementos.
- Quando somente uma das cinco luzes estiver acesa, o nível da bateria estará abaixo de 20%.
- Se o nível da bateria estiver muito baixo e você tentar ligar o dispositivo, uma luz piscará rapidamente e apagará.

Os [detalhes completos sobre o carregamento do dispositivo podem ser vistos aqui](hololens2-charging.md#charging-the-device) se mais informações forem necessárias. 

## <a name="adjust-fit"></a>Ajustar

Coloque o HoloLens 2 em sua cabeça. Se você usa óculos, não é necessário tirá-los.  O suporte deve ajustar-se confortavelmente em sua testa, e a faixa traseira deve ficar na parte de trás da sua cabeça.

Se necessário, estenda a headband girando a roda de ajuste e então solte a faixa sobre a cabeça.

![Ajustes do HoloLens 2.](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Apertar e afrouxar a faixa sobre a cabeça

A faixa sobre a cabeça não é necessária, mas pode tornar o uso do HoloLens 2 mais confortável durante períodos longos de uso.

Para retirar a frente da faixa sobre a cabeça, afrouxe a faixa e deslize-a pelo arco retrátil do suporte da testa. Para colocá-la novamente, retire o arco e deslize a faixa de volta.

Para retirar a parte de trás da faixa sobre a cabeça, pressione o botão abaixo de cada guia de conexão e puxe-a com cuidado. Para colocá-la novamente, empurre as guias de conexão de volta aos slots até encaixá-las.

![anexar ou remover a faixa da cabeça do HoloLens 2.](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>Ligar o HoloLens 2

Para ligar o HoloLens 2, pressione o botão de energia.  Os LEDs abaixo do botão de energia exibem o nível da bateria.

> [!NOTE]
> Para ligar o HoloLens 2 pela primeira vez, depois de retirá-lo da caixa, pressione e segure o botão de energia por pelo menos 4 segundos para ligá-lo. Na próxima vez que você ligar HoloLens 2, ele será iniciado após um breve pressionamento do botão de energia.

### <a name="power-button-actions-for-different-power-transitions"></a>Ações do botão de energia para diferentes transições de energia

| Para fazer isso | Executar esta ação | O HoloLens 2 fará isto |
| - | - | - |
| Para ligar | Pressionamento simples do botão. | Todas as cinco luzes acendem e mudam para indicar o nível de bateria. Após quatro segundos, um som é reproduzido. |
| Para suspender | Pressionamento simples do botão. | Todas as cinco luzes acendem e esmaecem uma de cada vez. Depois que as luzes desligarem, um som será reproduzido, e a tela exibirá "Goodbye" (Até logo). |
| Para sair do modo de suspensão | Pressionamento simples do botão. | Todas as cinco luzes acendem e mudam para indicar o nível de bateria. Um som é reproduzido imediatamente. |
| Para desligar | Pressione e segure por 5 segundos. |  Todas as cinco luzes acendem e esmaecem uma de cada vez. Depois que as luzes desligarem, um som será reproduzido, e a tela exibirá "Goodbye" (Até logo). |
| Para forçar a reinicialização do HoloLens se não houver resposta | Pressione e segure por 10 segundos. | Todas as cinco luzes acendem e esmaecem uma de cada vez. Depois que as luzes apagarem. |

## <a name="hololens-behavior-reference"></a>Referência de comportamento do HoloLens

Não tem certeza sobre o significado das luzes indicadoras do HoloLens? Quer saber como o HoloLens deve se comportar durante o carregamento?  Vamos ajudá-lo.

### <a name="charging-behavior"></a>Comportamento de carregamento

| Estado do dispositivo | Ação | O HoloLens 2 fará isto |
| - | - | - |
| OFF | Conectar o cabo USB | O dispositivo faz a transição para ATIVADO com luzes indicadoras que mostram o nível de bateria, e o dispositivo começará o carregamento.
| ATIVADO | Remover cabo USB | O dispositivo interrompe o carregamento
| ATIVADO | Conectar o cabo USB | O dispositivo começa o carregamento
| SUSPENSÃO | Conectar o cabo USB | O dispositivo começa o carregamento
| SUSPENSÃO | Remover cabo USB | O dispositivo interrompe o carregamento
| ATIVADO com um cabo USB conectado | Desligar o dispositivo | O dispositivo faz a transição para ATIVADO com luzes indicadoras que mostram o nível de bateria, e o dispositivo começará o carregamento |

### <a name="lights-that-indicate-the-battery-level"></a>Luzes que indicam o nível da bateria

| Número de luzes | Nível da bateria |
| - | - |
| Quatro luzes sólidas, uma luz acendendo e apagando | Entre 100% e 81% (totalmente carregado) |
| Três luzes sólidas, uma luz acendendo e apagando | Entre 80% e 61% |
| Duas luzes sólidas, uma luz acendendo e apagando | Entre 60% e 41% |
| Uma luz sólida, uma luz acendendo e apagando | Entre 40% e 21% |
| Um luz acendendo e apagando | Entre 20% e 5% ou menos (bateria em nível crítico) |

### <a name="sleep-behavior"></a>Comportamento de suspensão

| Estado do dispositivo | Ação | O HoloLens 2 fará isto |
| - | - | - |
| ATIVADO | Pressionamento simples do botão Ligar/Desligar | O dispositivo faz a transição para o modo de SUSPENSÃO e desativa todas as luzes indicadoras |
| ATIVADO | Sem movimento por três minutos | O dispositivo faz a transição para o modo de SUSPENSÃO e desativa todas as luzes indicadoras |
| SUSPENSÃO | Pressionamento simples do botão Ligar/Desligar | O dispositivo faz a transição para ATIVADO e acende luzes indicadoras |

### <a name="lights-to-indicate-problems"></a>Luzes para indicar problemas

| Ao fazer isto | As luzes fazem isto | Isso significa |
| - | - | - |
| Você pressiona o botão Ligar/Desligar. | Uma luz pisca cinco vezes e depois apaga. | A bateria do HoloLens está criticamente baixa. Carregue seu HoloLens. |
| Você pressiona o botão Ligar/Desligar. | Todas as cinco luzes piscam cinco vezes e, em seguida, desligam. |  O HoloLens não consegue iniciar corretamente e está em estado de erro. [Reinstale o sistema operacional](hololens-recovery.md) para recuperar o dispositivo. |
| Você pressiona o botão Ligar/Desligar. | As luzes 1, 3 e 5 piscam juntas continuamente. |  O HoloLens pode ter uma falha de hardware. Entre em contato com o [suporte](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb). |

## <a name="safety-and-comfort"></a>Segurança e conforto

### <a name="use-hololens-in-safe-surroundings"></a>Usar o HoloLens em arredores seguros

Use seu HoloLens em um espaço seguro sem obstruções e riscos de tropeços. Não o utilize quando precisar de um campo de visão claro ou não puder prestar total atenção a ele, como quando estiver operando um veículo ou realizando qualquer outra atividade potencialmente perigosa.

### <a name="stay-comfortable"></a>Sinta-se confortável

Não utilize o HoloLens por muito tempo em suas primeiras sessões e faça pausas. Se você sentir algum desconforto, pare e descanse até se sentir melhor. Isso pode incluir sentimentos temporários de náusea, vertigem, tontura, desorientação, dores de cabeça, fadiga, pressão nos olhos ou olhos secos.

Confira os [avisos e instruções de segurança do produto](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions).

> [!div class="nextstepaction"]
> [Configurar seu HoloLens 2](hololens2-start.md)
