---
title: Gerenciar aplicativos personalizados para HoloLens (1ª geração)
description: Saiba como instalar, desinstalar e carregar aplicativos holográficos personalizados em dispositivos HoloLens usando o Portal de Dispositivos e Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 7d564fd00567033060428d5b47b34ddf827dea2fdeeb8955c73bc22e4ba87164
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664937"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Gerenciar aplicativos personalizados para HoloLens (1ª geração)

HoloLens dá suporte a muitos aplicativos existentes do Microsoft Store, bem como novos aplicativos criados especificamente para HoloLens. Este artigo se concentra em aplicativos holográficos personalizados.  

Para obter mais informações sobre aplicativos da loja, [consulte Gerenciar aplicativos com a loja](holographic-store-apps.md).

> [!IMPORTANT]
> As informações a seguir foram criadas para o HoloLens (1ª geração), também chamada de HoloLens Developer Edition no momento. Assim, o sideload de aplicativos por meio do portal do dispositivo e a instalação de aplicativos por meio Visual Studio eram comuns. Para implantações corporativas, não recomendamos habilenciar o Modo de Desenvolvedor, que ambos os métodos usam. Se você estiver interessado em um método de implantação de aplicativo seguro, revise nosso Gerenciamento [de Aplicativos: Visão geral.](app-deploy-overview.md)
>
> Se você estiver procurando qualquer método de desenvolvedor de instalação de aplicativo para HoloLens 2 dispositivos, consulte:
>
> - [Portal de Dispositivos: instalando um aplicativo](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Usando Visual Studio para implantar e depurar aplicativos](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalar aplicativos personalizados

Você pode instalar seus próprios aplicativos HoloLens usando o Portal de Dispositivos ou implantando os aplicativos do Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalando um pacote de aplicativos com o Portal de Dispositivos

1. Estabeleça uma [conexão Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal) para o destino HoloLens.

1. No painel de navegação esquerdo, navegue até a **página Aplicativos.**

1. Em **Pacote do Aplicativo,** navegue até o arquivo .appx associado ao seu aplicativo.

   > [!IMPORTANT]
   > Certifique-se de fazer referência a qualquer dependência associada e arquivos de certificado.

1. Selecione **Ir**.

   > [!div class="mx-imgBorder"]
   > ![Instalar o formulário de aplicativo Windows Portal de Dispositivos no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Implantação do Microsoft Visual Studio 2015

1. Abra a solução de Visual Studio aplicativo (arquivo .sln).

1. Abra as Propriedades do **projeto.**

1. Selecione a seguinte configuração de build: **Mestre/x86/Computador Remoto.**

1. Ao selecionar Computador **Remoto:**
   - Certifique-se de que o endereço aponta para o Wi-Fi IP da sua HoloLens.
   - Descriptografe **a autenticação como Universal (Protocolo Não Criptografado).**
   
1. Compile sua solução.

1. Para implantar o aplicativo do computador de desenvolvimento em seu HoloLens, selecione **Computador Remoto**. Se você já tiver um build existente no HoloLens, selecione **Sim** para instalar essa versão mais recente.  

   ![Implantação de computador remoto para aplicativos Microsoft HoloLens em Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. O aplicativo será instalado e iniciará automaticamente em seu HoloLens.

Depois de instalar um aplicativo, você o encontrará na lista **de** Todos os apps (**Iniciar**  >  **Todos os apps**).
