---
title: gerenciar aplicativos personalizados para HoloLens (1ª gen)
description: saiba como instalar, desinstalar e carregar no lado os aplicativos holographic personalizados em dispositivos HoloLens usando o Portal do dispositivo e o Visual Studio.
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031931"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>gerenciar aplicativos personalizados para HoloLens (1ª gen)

o HoloLens dá suporte a muitos aplicativos existentes do Microsoft Store, bem como a novos aplicativos criados especificamente para HoloLens. Este artigo se concentra em aplicativos Holographic personalizados.  

Para obter mais informações sobre aplicativos da loja, consulte [gerenciar aplicativos com a loja](holographic-store-apps.md).

> [!IMPORTANT]
> as informações a seguir foram criadas para a HoloLens (1ª gen), também chamada de HoloLens developer Edition no momento. como esses aplicativos de sideload por meio do portal do dispositivo e a instalação de aplicativos via Visual Studio eram comuns. Para implantações corporativas, não recomendamos habilitar o modo de desenvolvedor, que ambos os métodos usam. Se você estiver interessado em um método de implantação de aplicativo seguro, examine nosso [Gerenciamento de aplicativo: visão geral](app-deploy-overview.md).
>
> se você estiver procurando um método de desenvolvedor de instalação de aplicativo para dispositivos HoloLens 2, consulte:
>
> - [Portal do dispositivo: instalando um aplicativo](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [usando Visual Studio para implantar e depurar aplicativos](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalar aplicativos personalizados

você pode instalar seus próprios aplicativos em HoloLens usando o Portal do dispositivo ou implantando os aplicativos do Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalando um pacote de aplicativos com o portal do dispositivo

1. Estabeleça uma conexão do [portal do dispositivo](/windows/mixed-reality/using-the-windows-device-portal) com o HoloLens de destino.

1. No painel de navegação esquerdo, navegue até a página **aplicativos** .

1. Em **pacote do aplicativo** , navegue até o arquivo. Appx que está associado ao seu aplicativo.

   > [!IMPORTANT]
   > Certifique-se de fazer referência a qualquer dependência associada e arquivos de certificado.

1. Selecione **Ir**.

   > [!div class="mx-imgBorder"]
   > ![instale o formulário de aplicativo no Portal do dispositivo Windows no Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>implantando do Microsoft Visual Studio 2015

1. abra a solução de Visual Studio do seu aplicativo (arquivo. sln).

1. Abra as **Propriedades** do projeto.

1. Selecione a seguinte configuração de compilação: **mestre/x86/computador remoto**.

1. Quando você seleciona **computador remoto**:
   - Verifique se o endereço aponta para o endereço IP Wi-Fi do seu HoloLens.
   - Defina a autenticação como **Universal (protocolo não criptografado)**.
   
1. Compile sua solução.

1. para implantar o aplicativo do seu PC de desenvolvimento em seu HoloLens, selecione **computador remoto**. se você já tiver uma compilação existente no HoloLens, selecione **sim** para instalar essa versão mais recente.  

   ![implantação de máquina remota para aplicativos para Microsoft HoloLens no Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. O aplicativo será instalado e iniciado automaticamente no seu HoloLens.

Depois de instalar um aplicativo, você o encontrará na lista **todos os aplicativos** (**Iniciar**  >  **todos os aplicativos**).
