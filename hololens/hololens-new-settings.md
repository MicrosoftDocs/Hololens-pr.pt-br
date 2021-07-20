---
title: Apresentando o novo aplicativo Configurações
description: Saiba mais sobre o novo aplicativo Configurações
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, configurações, seletor de aplicativos, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640161"
---
# <a name="new-settings-app"></a>Novo aplicativo Configurações

Com a [versão 21H1 do Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h1), estamos introduzindo uma nova versão do aplicativo Configurações. O novo aplicativo Configurações inclui novos recursos e configurações expandidas para o HoloLens 2 nas seguintes áreas: Som, Energia e suspensão, Rede e Internet, Aplicativos, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Como o novo aplicativo Configurações é diferente do aplicativo Configurações herdado, as janelas de Configurações que você colocou em seu ambiente serão removidas após a atualização.

![Home page do novo aplicativo Configurações](images/new-settings-app.png)

**Novos recursos e configurações**
- Pesquisa de Configurações: pesquise por configurações na home page de Configurações usando palavras-chave ou o nome da configuração.
- Sistema > [Calibragem de cor](hololens2-display.md#how-to-use-display-color-calibration)
    - Selecione um perfil de cor alternativo para a exibição do HoloLens 2.
- Sistema > Som:
  - dispositivos de áudio de entrada e saída: escolha independentemente seus dispositivos de áudio de entrada e saída (por exemplo, ouça áudio com fones de ouvido Bluetooth ou use um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Microfones Bluetooth não têm suporte do HoloLens 2.
  - Volume do aplicativo: ajuste o volume de cada aplicativo de maneira independente. Confira [controle de volume por aplicativo](holographic-home.md#per-app-volume-control).
- Sistema > Energia e suspensão: escolha quando o dispositivo deve entrar em suspensão após um período de inatividade.
- Sistema > Bateria: habilite manualmente o modo de economia de bateria ou defina um limite de bateria no qual o modo de economia de bateria é ativado automaticamente.
- Dispositivos > USB: você pode desabilitar conexões USB por padrão.
- Rede e Internet:
  - agora, adaptadores USB-C para Ethernet aparecerão em Rede e Internet.
  - Configurações do adaptador USB-C para Ethernet estão disponíveis, incluindo o endereço IP dele.
  - Agora, você pode habilitar o modo avião no HoloLens 2.
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Para obter mais informações, confira [Seletor de aplicativos padrão](holographic-home.md#default-app-picker).
- Contas > Outros usuários: os proprietários dos dispositivos podem adicionar usuários, atualizar usuários padrão para proprietários do dispositivo, fazer downgrade de proprietários de dispositivo para usuários padrão e remover usuários.
- Facilidade de Acesso: altere o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- Janelas de Configurações fixadas anteriormente serão removidas (veja a observação acima).
- Você não pode mais renomear o dispositivo usando o aplicativo Configurações. Os administradores de TI podem renomear dispositivos usando o modelo de nome de dispositivo do [Windows Autopilot para HoloLens 2](hololens2-autopilot.md) ou o nó Ext/Microsoft/DNSComputerName do [CSP DevDetail](/windows/client-management/mdm/devdetail-csp) do MDM.
- A página Ethernet mostra um dispositivo de Ethernet virtual ("UsbNcm") o tempo todo.
- O uso da bateria no novo Microsoft Edge pode não estar preciso devido à sua natureza de aplicativo de área de trabalho Win32 com suporte de uma camada de adaptador da UWP (nenhuma correção prevista para o futuro próximo).

