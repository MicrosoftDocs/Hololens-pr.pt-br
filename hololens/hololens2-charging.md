---
title: Bateria e carregamento do HoloLens 2
description: Como carregar seu HoloLens e usar pacotes de bateria externos.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923577"
---
# <a name="hololens-2-battery-and-charging"></a>Bateria e carregamento do HoloLens 2

Esta página exibe informações sobre como carregar o HoloLens 2 e usar pacotes de bateria externos.

## <a name="charging-the-device"></a>Carregar o dispositivo

Use o [carregador e o cabo USB Tipo-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) que veio com o HoloLens 2, pois essa é a melhor maneira de carregar seu dispositivo. O carregador incluído com HoloLens 2 oferece até 9 V a 2 A (18 W). Com o carregador de parede fornecido, os dispositivos HoloLens 2 podem carregar a bateria completamente em menos de 65 minutos quando o dispositivo está em espera. Se esses acessórios não estiverem disponíveis, verifique se o carregador que está disponível consegue suportar pelo menos 15 W de energia.

> [!NOTE]
> Se possível, evite usar um computador para carregar o dispositivo por USB, pois é lento.

## <a name="checking-the-battery-charge-level"></a>Verificar o nível de carga da bateria
Se o dispositivo for reinicializado corretamente e em execução, há três maneiras diferentes de verificar a carga da bateria:

- No menu principal da interface de usuário do dispositivo do HoloLens.
- Exibir o LED próximo ao botão de energia (com 40% de carga, você deve ver pelo menos dois LEDS sólidos).
    - Quando o dispositivo estiver sendo carregado, o indicador de bateria acenderá para indicar o nível de carga atual.  A última luz acenderá e apagará para indicar o carregamento ativo.
    - Quando o HoloLens estiver ligado, o indicador de bateria exibe o nível da bateria em cinco incrementos.
    - Quando somente uma das cinco luzes estiver acesa, o nível da bateria estará abaixo de 20%.
    - Se o nível da bateria estiver muito baixo e você tentar ligar o dispositivo, uma luz piscará rapidamente e apagará.
- No computador host, abra o **Explorador de Arquivos** e procure seu dispositivo HoloLens 2 no lado esquerdo em **Este Computador**. Clique com o botão direito do mouse no dispositivo e escolha **Propriedades**. Uma caixa de diálogo mostrará o nível de carga da bateria.

   ![Uma tela de propriedades do HoloLens 2 mostra o nível de mudança da bateria](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Especificações de cobrança alternativas

O HoloLens 2 pode ser carregado por fontes [USB Power Delivery](https://www.usb.org/usb-charger-pd) de até 27 Watts. Se a fonte puder fornecer pelo menos 10 Watts, o tempo de operação do HoloLens poderá ser estendido (potencialmente de maneira indefinida para algumas cargas de trabalho). 

> [!NOTE]
> O uso de um cabo de carregamento USB-A para USB-C limitará a carga a 7,5 Watts. O tempo de operação ainda será estendido, mas não tanto quanto usar USB-C para C.

Quando o HoloLens está no modo de espera, 18 Watts são suficientes para alcançar a taxa máxima de carga para a bateria interna. Quando o HoloLens está em uso, a taxa de carregamento pode ser reduzida, pois o HoloLens prioriza o funcionamento ao carregamento.

> [!IMPORTANT]
> É recomendável que o HoloLens 2 seja carregado a, no mínimo, 5 V/1,5 A. Carregadores que não podem fornecer pelo menos 5 V/1,5 A não devem ser usados. 

### <a name="external-battery-packs"></a>Pacotes de bateria externa

Os pacotes de bateria que atendem às especificações acima podem ser usados com o HoloLens 2. No entanto, observe que algumas baterias USB-C recarregam e fornecem energia por meio da mesma porta USB-C. É importante que esses pacotes de bateria implementem [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) para garantir que eles carreguem o HoloLens em vez de obter carga dele. 

### <a name="managing-heat"></a>Gerenciando calor

Assim como em qualquer dispositivo, carregar o HoloLens gera calor. Quanto mais rápido for o carregamento, mais calor será gerado. Além disso, iniciar uma carga em um nível de bateria mais baixo gerará mais calor do que iniciar uma carga quando a bateria estiver mais cheia. Os clientes que precisam operar o HoloLens por longos períodos em ambientes quentes podem usar as seguintes técnicas:

- Não há problema em conectar o HoloLens 2 a uma fonte de alimentação externa, mesmo quando a bateria interna está totalmente carregada.
- Quando uma bateria externa for esgotada, o HoloLens continuará operando com sua bateria interna.    
- Se o calor ainda for um problema após as etapas acima, considere o uso de um carregador ou uma bateria que limite a carga a 1,5 A. Observe que essa opção não oferecerá tanto tempo de operação, pois a bateria interna ainda ficará lenta.

## <a name="troubleshooting"></a>Solução de problemas


### <a name="hololens-charges-external-battery"></a>HoloLens carrega bateria externa
Se o HoloLens 2 carregar uma bateria externa em vez de ser carregado por ela, isso indica que a bateria não implementa [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Mudar para uma bateria mais recente é a maneira recomendada de resolver esse problema, mas, como alternativa, você pode tentar mudar para um cabo USB-A para USB-C. Tenha em mente que isso limitará a taxa de carregamento a 7,5 watts.
