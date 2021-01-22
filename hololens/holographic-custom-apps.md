---
title: Gerenciar aplicativos personalizados para HoloLens (1ª geração)
description: Saiba como instalar, desinstalar e carregar aplicativos holográficos personalizados em dispositivos HoloLens usando o Device Portal e o Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, sideload, store, uwp, app, install
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296984"
---
# Gerenciar aplicativos personalizados para HoloLens (1ª geração)

O HoloLens oferece suporte a vários aplicativos existentes na Microsoft Store, bem como novos aplicativos criados especificamente para o HoloLens. Este artigo se concentra em aplicativos holográficos personalizados.  

Para obter mais informações sobre aplicativos da loja, [consulte Gerenciar aplicativos com a loja.](holographic-store-apps.md)

> [!IMPORTANT]
> As informações a seguir foram criadas para o HoloLens (1ª geração), também chamada de HoloLens Developer Edition no momento. Assim, o sideload de aplicativos por meio do device portal e a instalação de aplicativos por meio do Visual Studio eram em comum. Para implantações corporativas, não recomendamos a habilitação do Modo de Desenvolvedor, que ambos os métodos usam. Se você estiver interessado em um método de implantação de aplicativo seguro, revise nosso Gerenciamento [de Aplicativos: Visão geral](app-deploy-overview.md).
>
> Se você estiver procurando um dos métodos de desenvolvedor de instalação de aplicativos para dispositivos HoloLens 2, confira:
> - [Device Portal: instalando um aplicativo](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Usando o Visual Studio para implantar e depurar aplicativos](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## Instalar aplicativos personalizados

Você pode instalar seus próprios aplicativos no HoloLens usando o Device Portal ou implantando os aplicativos do Visual Studio.

### Instalando um pacote de aplicativos com o Device Portal

1. Estabeleça uma conexão [do Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) com o HoloLens de destino.

1. Na navegação à esquerda, navegue até a **página Aplicativos.**

1. Em **Pacote de Aplicativos,** navegue até o arquivo .appx associado ao seu aplicativo.

   > [!IMPORTANT]
   > Certifique-se de fazer referência a qualquer dependência associada e arquivos de certificado.

1. Selecione **Ir.**

   > [!div class="mx-imgBorder"]
   > ![Instalar o formulário de aplicativo no Windows Device Portal no Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### Implantação do Microsoft Visual Studio 2015

1. Abra a solução do Visual Studio do seu aplicativo (arquivo .sln).

1. Abra as propriedades do **projeto.**

1. Selecione a seguinte configuração de com build: **Master/x86/Remote Machine**.

1. Ao selecionar **Máquina Remota:**
   - Certifique-se de que o endereço aponta para o Wi-Fi IP do seu HoloLens.
   - Definir autenticação **como Universal (Protocolo Não Criptografado).**
   
1. Crie sua solução.

1. Para implantar o aplicativo do seu computador de desenvolvimento em seu HoloLens, selecione **Máquina Remota.** Se você já tiver um build existente no HoloLens, selecione **Sim** para instalar essa versão mais recente.  

   ![Implantação de máquina remota para aplicativos no Microsoft HoloLens no Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. O aplicativo será instalado e iniciará automaticamente em seu HoloLens.

Depois de instalar um aplicativo, você o encontrará **** na lista Todos os aplicativos (**Iniciar**  >  **todos os aplicativos).**
