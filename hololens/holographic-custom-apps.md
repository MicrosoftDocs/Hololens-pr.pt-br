---
title: Gerenciar aplicativos personalizados para o HoloLens (1ª gen)
description: Saiba como instalar, desinstalar e carregar os aplicativos Holographic personalizados em dispositivos do HoloLens usando o portal do dispositivo e o Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, Sideload, carga lateral, carga lateral, armazenamento, UWP, aplicativo, instalação
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308090"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Gerenciar aplicativos personalizados para o HoloLens (1ª gen)

O HoloLens dá suporte a muitos aplicativos existentes do Microsoft Store, bem como a novos aplicativos criados especificamente para o HoloLens. Este artigo se concentra em aplicativos Holographic personalizados.  

Para obter mais informações sobre aplicativos da loja, consulte [gerenciar aplicativos com a loja](holographic-store-apps.md).

> [!IMPORTANT]
> As informações a seguir foram criadas para o HoloLens (1ª gen), também chamado de edição de desenvolvedor do HoloLens no momento. Assim, os aplicativos de Sideload por meio do portal do dispositivo e da instalação de aplicativos por meio do Visual Studio eram comuns. Para implantações corporativas, não recomendamos habilitar o modo de desenvolvedor, que ambos os métodos usam. Se você estiver interessado em um método de implantação de aplicativo seguro, examine nosso [Gerenciamento de aplicativo: visão geral](app-deploy-overview.md).
>
> Se você estiver procurando um método de desenvolvedor de instalação de aplicativo para dispositivos do HoloLens 2, consulte:
> - [Portal do dispositivo: instalando um aplicativo](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Usando o Visual Studio para implantar e depurar aplicativos](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalar aplicativos personalizados

Você pode instalar seus próprios aplicativos no HoloLens usando o portal do dispositivo ou implantando os aplicativos do Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalando um pacote de aplicativos com o portal do dispositivo

1. Estabeleça uma conexão do [portal do dispositivo](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) com o HoloLens de destino.

1. No painel de navegação esquerdo, navegue até a página **aplicativos** .

1. Em **pacote do aplicativo** , navegue até o arquivo. Appx que está associado ao seu aplicativo.

   > [!IMPORTANT]
   > Certifique-se de fazer referência a qualquer dependência associada e arquivos de certificado.

1. Selecione **Ir**.

   > [!div class="mx-imgBorder"]
   > ![Instalar formulário de aplicativo no portal de dispositivo do Windows no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Implantando do Microsoft Visual Studio 2015

1. Abra a solução do Visual Studio do seu aplicativo (arquivo. sln).

1. Abra as **Propriedades** do projeto.

1. Selecione a seguinte configuração de compilação: **mestre/x86/computador remoto**.

1. Quando você seleciona **computador remoto**:
   - Verifique se o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.
   - Defina a autenticação como **Universal (protocolo não criptografado)**.
   
1. Compile sua solução.

1. Para implantar o aplicativo do seu PC de desenvolvimento em seu HoloLens, selecione **computador remoto**. Se você já tiver uma compilação existente no HoloLens, selecione **Sim** para instalar essa versão mais recente.  

   ![Implantação de máquina remota para aplicativos para o Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. O aplicativo será instalado e iniciado automaticamente no seu HoloLens.

Depois de instalar um aplicativo, você o encontrará na lista **todos os aplicativos** (**Iniciar**  >  **todos os aplicativos**).
