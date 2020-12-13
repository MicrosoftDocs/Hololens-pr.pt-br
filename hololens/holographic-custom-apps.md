---
title: Gerenciar aplicativos personalizados para o HoloLens
description: Carregar aplicativos personalizados no HoloLens. Saiba mais sobre como instalar e desinstalar os aplicativos do holográfico.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, Sideload, carregamento do lado, carregar lado a lado, loja, UWP, aplicativo, instalar
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218628"
---
# Gerenciar aplicativos personalizados para o HoloLens

O HoloLens oferece suporte a vários aplicativos existentes na Microsoft Store, bem como novos aplicativos criados especificamente para o HoloLens. Este artigo se concentra em aplicativos de holográfico personalizados.  

Para obter mais informações sobre aplicativos da loja, consulte [gerenciar aplicativos com a loja](holographic-store-apps.md).

> [!IMPORTANT]
> As informações a seguir foram criadas para o HoloLens (1ª gen), também chamado de edição do desenvolvedor do HoloLens no momento. Como esses aplicativos de Sideload por meio do Device portal e da instalação de aplicativos via Visual Studio foram comuns. Para implantações corporativas, não recomendamos habilitar o modo de desenvolvedor, que ambos os métodos usam. Se você estiver interessado em um método de implantação de aplicativo seguro, consulte a [visão geral sobre o gerenciamento de aplicativos:](app-deploy-overview.md).
>
> Se você estiver procurando por um método de desenvolvedor de instalação de aplicativo para dispositivos HoloLens 2, consulte:
> - [Device Portal: instalando um aplicativo](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Como usar o Visual Studio para implantar e depurar aplicativos](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Instalar aplicativos personalizados

Você pode instalar seus próprios aplicativos no HoloLens usando o Device portal ou implantando os aplicativos do Visual Studio.

### Instalando um pacote de aplicativo com o Device Portal

1. Estabeleça uma conexão do [Device portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para o HoloLens do destino.
1. Na navegação à esquerda, navegue até a página **aplicativos** .
1. Em **pacote do aplicativo** , navegue até o arquivo. Appx associado ao seu aplicativo.
   > [!IMPORTANT]
   > Certifique-se de fazer referência a qualquer dependência e arquivo de certificado associados.

1. Selecione **ir**.
   ![Instalar formulário de aplicativo no Windows Device portal no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Implantando a partir do Microsoft Visual Studio 2015

1. Abra a solução do Visual Studio do seu aplicativo (arquivo. sln).
1. Abra as **Propriedades**do projeto.
1. Selecione a seguinte configuração de compilação: **Master/x86/máquina remota**.
1. Ao selecionar **computador remoto**:
   - Certifique-se de que o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.
   - Defina a autenticação como **Universal (protocolo não criptografado)**.
1. Construa sua solução.
1. Para implantar o aplicativo do seu computador de desenvolvimento em seu HoloLens, selecione **computador remoto**. Se você já tiver uma compilação existente no HoloLens, selecione **Sim** para instalar esta versão mais recente.  

   ![Implantação de computador remoto para aplicativos para Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
1. O aplicativo será instalado e iniciado automaticamente no seu HoloLens.

Depois de instalar um aplicativo, você o encontrará na lista **todos os aplicativos** (**Iniciar**  >  **todos os aplicativos**).
