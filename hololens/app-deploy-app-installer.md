---
title: Como carregar e instalar aplicativos pelo instalador do aplicativo HoloLens 2
description: Carregar e instalar aplicativos por meio da interface do usuário
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027454"
---
# Instalar aplicativos no HoloLens 2 via instalador de aplicativos

Agora os usuários podem instalar aplicativos por meio de pacotes Appx sem a necessidade de habilitar o modo de desenvolvedor ou usar o Device Portal. Essa experiência é simples para a instalação de aplicativos em dispositivos locais ou o compartilhamento de um aplicativo com outra pessoa que não esteja familiarizado com outros métodos de instalação de aplicativo no HoloLens. 

> [!IMPORTANT]
> No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +. [Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).

> [!NOTE]
> A configuração da solução de seu aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja. Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

1.  Verifique se o seu dispositivo do HoloLens 2 está ligado e se você está conectado.
1.  No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads. 
    Depois de concluir a cópia do seu arquivo, você pode desconectar seu dispositivo e concluir a instalação mais tarde.
1.  Em seu dispositivo do HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .
1.  Navegue até a pasta downloads. Talvez seja necessário no painel esquerdo do aplicativo selecione **este dispositivo** primeiro e, em seguida, navegue até downloads.
1.  Selecione o arquivo yourapp. appxbundle. 
1.  O instalador do aplicativo será iniciado. Selecione o botão **instalar** para instalar o aplicativo. 

O aplicativo instalado será iniciado automaticamente após a conclusão da instalação. 

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

Se o aplicativo não tiver sido instalado, verifique o seguinte:
-   Seu aplicativo é uma compilação mestre ou de versão.
-   Você está [conectado à Internet](hololens-network.md).
-   Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.  
