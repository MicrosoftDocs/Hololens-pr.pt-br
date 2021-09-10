---
title: Hardware do HoloLens 2
description: Conheça os componentes que fazem parte do Microsoft HoloLens 2, a mais recente evolução de um computador holográfico da Microsoft sem fio com Windows 10.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: c1d83577400126903a80999c46ddaeabddaba029
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190371"
---
# <a name="about-hololens-2"></a>Sobre o HoloLens 2

![Vista lateral do HoloLens 2.](images/hololens2-breakdown.png)

O Microsoft HoloLens 2 é um computador holográfico sem fio.  Ele refina a jornada de computação holográfica iniciada pelo HoloLens (1ª geração) para fornecer uma experiência mais confortável e envolvente com mais opções para colaboração na realidade misturada. O HoloLens 2 é executado no [SO Windows Holographic](hololens-release-notes.md), que tem o Windows 10 como inspiração e oferece aos usuários, administradores e desenvolvedores uma plataforma robusta, de bom desempenho e segura. 

> [!NOTE]
> O comunicado recente do Windows 11 se concentrou na versão do Windows para computadores. Recentemente, lançamos uma [grande atualização do sistema operacional](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) para o HoloLens 2 em maio de 2021 e estamos trabalhando em uma próxima versão com base nos comentários dos clientes para o segundo semestre.

Uma conta de usuário é necessária para usar o HoloLens 2.

## <a name="hololens-components"></a>Componentes do HoloLens

- **Visor**. Contém os sensores e telas do HoloLens. Você pode girar o visor para cima enquanto estiver utilizando o HoloLens.
- **Faixa de cabeça**. Para colocar o HoloLens, use o roda de ajuste para expandir a headband. Com o HoloLens em uso, aperte a roda de ajuste girando-a para a direita, até que a headband esteja confortável.
- **Botões de brilho**. Ao usar o HoloLens, os botões de brilho ficam no lado esquerdo do visor perto da têmpora.
- **Botões de volume**. Ao usar o HoloLens, os botões de volume ficam do lado direito do visor perto da têmpora.
- **Botão Ligar/Desligar**. Ao usar o HoloLens, o botão liga/desliga está localizado no lado direito da tampa externa traseira.
- **Porta USB-C**. Ao usar o HoloLens, a porta USB-C está localizada no lado direito da tampa externa traseira abaixo do botão Liga/Desliga.

## <a name="in-the-box"></a>Na caixa

- **[Painel de navegação](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)** . Você pode remover e substituir o suporte da testa, conforme necessário.
- **[Faixa sobre a cabeça](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)** . Quando estiver utilizando o HoloLens ao se movimentar, use a faixa de sobrecarga para ajudar a manter o dispositivo no lugar. Ao usar o HoloLens por períodos prolongados, a faixa de sobrecarga pode tornar o uso do dispositivo mais confortável.
- **[Carregador e cabo USB-C](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)** . A fonte de alimentação conecta-se à tomada. Use o cabo USB-C para conectar o HoloLens à fonte de alimentação para carregamento ou para conectar o HoloLens ao seu computador.
- **Pano de microfibra**. Use para limpar o visor do HoloLens.

### <a name="power-supply-details"></a>Detalhes da Fonte de Alimentação

A fonte de alimentação e o cabo USB que acompanham o dispositivo são o melhor mecanismo com suporte para o carregamento. A fonte de alimentação é um carregador de 18W.  Ela fornece 9V a 2A.

A taxa e a velocidade da carga podem variar de acordo com o ambiente no qual o dispositivo está sendo executado.

Para manter/avançar o Percentual Interno de Carga da Bateria enquanto o dispositivo está ligado, ele deve ser conectado, no mínimo, a um carregador de 15 W.

## <a name="device-specifications"></a>Especificações do dispositivo

### <a name="display"></a>Exibir

|   | &nbsp; |
|---|---|
| **Óptica** | Lentes holográficas transparentes (guias de onda) |
| **Resolução holográfica** | 2 mil mecanismos de luz 3:2 |
| **Densidade holográfica** | > 2,5 mil radiantes (pontos de luz por radiano) |
| **Renderização baseada no olhar** | Otimização de tela para posição de olho 3D |

### <a name="sensors"></a>Sensores

|   | &nbsp; |
|---|---|
| **Rastreamento da cabeça** | Quatro câmeras de luz visíveis |
| **Acompanhamento ocular** | Duas câmeras infravermelhas (IV) |
| **Profundidade** | Sensor de profundidade Time-of-Flight de 1 MP |
| **IMU (unidade de medida de inércia)** | Acelerômetro, giroscópio, magnetômetro |
| **Câmera** | Imagens estáticas de 8 MP, vídeo de 1080p30 |

![Sensores do HoloLens 2.](images/hololens2-front-view.png)

> [!NOTE]
> Não cubra nenhum dos sensores que aparecem na imagem. As câmeras de rastreamento de cabeça têm um FOV muito amplo, nada deve estar ao redor delas, além de não cobri-las.

### <a name="audio-and-speech"></a>Áudio e fala

|   | &nbsp; |
|---|---|
| **Matriz de microfones** | Cinco canais |
| **Speakers** | Som espacial interno |

### <a name="compute-and-connectivity"></a>Computação e conectividade

|   | &nbsp; |
|---|---|
| **Sistema no chip** | [Informações](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) do Qualcomm Snapdragon 850 Compute Platform |
| **Unidade de processamento holográfico** | Unidade de processamento holográfico personalizada de segunda geração |
| **Memória** | DRAM do sistema LPDDR4x de 4 GB |
| **Storage** | UFS 2.1 de 64 GB |
| **Wi-Fi** | 2x2 802.11ac |
| **Bluetooth** | 5.0 |
| **USB** | USB Tipo-C DRP |

### <a name="power"></a>Energia

|   | &nbsp; |
|---|---|
| **Duração da bateria** | De 2 a 3 horas de uso ativo. Até duas semanas de tempo de espera. |
| **Tecnologia da bateria** | [Baterias de lítio](https://www.microsoft.com/download/details.aspx?id=43388) |
| **Comportamento de carregamento** | Totalmente funcional durante o carregamento |
| **Tipo de resfriamento** | Resfriado de forma passiva (sem ventiladores) |
| **Consumo de energia** | Para manter/avançar o Percentual Interno de Carga da Bateria enquanto o dispositivo está ligado, ele deve ser conectado, no mínimo, a um carregador de 15 W. |

### <a name="fit"></a>Adequação

|   | &nbsp; |
|---|---|
| **Dimensionamento** | Tamanho único com faixa ajustável.  Ajusta-se sobre os óculos |
| **Weight** | 566 gramas |

## <a name="device-capabilities"></a>Funcionalidades de dispositivo

### <a name="human-understanding"></a>Entendimento humano

|   | &nbsp; |
|---|---|
| **Acompanhamento da mão** | Modelo totalmente articulado de duas mãos, manipulação direta |
| **Acompanhamento ocular** | Rastreamento em tempo real |
| **Voz** | Comando e controle no dispositivo; idioma natural da Cortana com conectividade com a internet |

### <a name="environment-understanding"></a>Compreensão do ambiente

|   | &nbsp; |
|---|---|
| **Rastreamento Six Degrees of Freedom (6DoF)** | Rastreamento de posição de escala mundial |
| **Mapeamento espacial** | Malha de ambiente em tempo real |
| **Captura de realidade mista** | Fotos e vídeos sobre hologramas e ambientes físicos misturados |

## <a name="pre-installed-software"></a>Software pré-instalado

| &nbsp; | &nbsp; |
|---|---|
| **Sistema operacional Windows Holographic** | Com o [SO Windows Holographic](hololens-release-notes.md), os usuários do Windows 10 poderão usar alguns de seus aplicativos e jogos em um ambiente de realidade misturada pelo HoloLens 2.
| **Visualizador 3D** | O [Visualizador 3D](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) permite que você veja facilmente modelos e animações 3D em tempo real.|
| **Cortana** | A [Cortana](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab), seu assistente de produtividade pessoal, ajuda você a ficar por dentro do que é importante e economizar tempo encontrando o que precisa.  |
| **Dynamics 365 Guides** |  Os [guias do Dynamics 365](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) ajudarão os funcionários a aprender novas habilidades com mais rapidez com os dispositivos HoloLens. |
| **Dynamics 365 Remote Assist** | A [Assistência Remota do Microsoft Dynamics 365](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) permite que os técnicos colaborem e resolvam problemas com colaboradores remotos usando o Microsoft Teams ou a Assistência Remota do Dynamics 365.  |
| **Hub de Feedback** | O [Hub de Comentários](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) permite que você forneça comentários sobre o Windows e aplicativos ao compartilhar suas sugestões ou problemas.  |
| **Explorador de Arquivos** | O Explorador de Arquivos fornece uma interface gráfica do usuário para acessar os sistemas de arquivos. |
| **Email e Calendário.** | Os aplicativos [Email e Calendário](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) ajudam você a se manter atualizado com seu email, gerenciar sua agenda e conversar com seus contatos. |
| **Microsoft Edge** | O Microsoft Edge oferece desempenho de alta qualidade com mais privacidade, mais produtividade e mais valor enquanto você navega. |
| **Microsoft Store** | A [Microsoft Store](https://www.microsoft.com) é a sua primeira opção para aplicativos e jogos que funcionam com o HoloLens.|
| **Filmes e TV** | O [Filmes e TV](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) traz a você o entretenimento mais recente em um aplicativo simples, rápido e elegante. |
| **OneDrive** | O [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) permite acessar e editar seus arquivos de todos os seus dispositivos e de qualquer lugar.  |
| **Fotos** | O [Fotos](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) permite visualizar e editar suas fotos e vídeos, fazer filmes e criar álbuns.  |
| **Configurações** | O aplicativo Configurações é o local em que você personaliza detalhadamente como o Windows Holographic funcionará.  |
| **Dicas** | O [Dicas](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab) deixa que você faça coisas surpreendentes e menos conhecidas com o Windows Holographic. |

## <a name="device-certifications"></a>Certificações do dispositivo

### <a name="safety"></a>Segurança

* [Segurança do produto](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [Avisos e instruções de segurança do produto](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* Segurança ocular: HoloLens 2 foi testado e está em conformidade com os requisitos básicos de proteção de impacto da ANSI Z87.1, CSA Z94.3 e EN 166.
* [Informações SAR](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>Informações normativas
[Regulamentação HoloLens](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): inclui informações sobre temperatura, alienação, interferência de rádio e TV, e muito mais.

## <a name="warranty-information"></a>Informações da Garantia

O Microsoft HoloLens 2 vem com uma [garantia](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5) limitada padrão. 


A compra está sujeita aos [Termos de Uso e Venda da Microsoft Store](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1). Todas as vendas são finais. Não há reembolso.

Ao comprar o HoloLens 2, você concorda com o [contrato de licença de software](https://www.microsoft.com/Useterms/).

Não destinado para uso por crianças menores de 13 anos.

## <a name="package-dimensions"></a>Dimensões do Pacote

|      Medida               |      Medidas das unidades     |      Unidades imperiais     |
|--------------------------------|-----------------------|-------------------------|
|     Comprimento da Unidade                |     378,97 mm          |     14,920 polegadas       |
|     Largura da Unidade                 |     247,90 mm          |     9,760 polegadas        |
|     Profundidade da Unidade                 |     163,07 mm          |     6,420 polegadas        |
|     Peso da Unidade                |     2,878 kg           |     6,344 lb           |
|     Comprimento do Transportador Externo    |     446,00 mm          |     17,559 polegadas       |
|     Largura do Transportador Externo     |     257,99 mm          |     10,157 polegadas       |
|     Profundidade do Transportador Externo     |     172,01 mm          |     6,772 polegadas        |
|     Peso do Transportador Externo    |     3,284 kg           |     7,240 lb           |

> [!NOTE]
> - Unidade: a caixa preta, no estilo de varejo, do HoloLens 2 é vendida.
> - Transportador Externo: a embalagem protetora de envio da Unidade.

## <a name="finding-the-serial-number"></a>Encontre o número de série

O número de série para dispositivos do HoloLens 2 é impresso embaixo do visor.

1. Levante o visor do dispositivo.
1. Olhe perto da almofada para a testa.
1. Você pode encontrar o número de série próximo à dobradiça.

   <img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

O número de série também pode ser localizado por um computador conectado:

1. Conectar o dispositivo
1. Navegue até **Este computador** no explorador de arquivos
1. Clique com o botão direito do mouse e escolha as **Propriedades** do dispositivo HoloLens
1. Isso exibirá o número da série do dispositivo, conforme mostrado na captura de tela abaixo.

   <br/><img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Comparar as edições do HoloLens 2](hololens2-options.md)

> [!div class="nextstepaction"]
> [Configurar e iniciar o HoloLens 2](hololens2-setup.md)
