---
title: Como instalar aplicativos via instalador da Web
description: Instalar aplicativos via instalador da Web para instalador de aplicativos
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos, instalação da Web
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
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135435"
---
# Instalando aplicativos de uma página da Web

Os usuários podem instalar um aplicativo diretamente de um servidor Web. Isso usa o instalador do aplicativo combinado com um método fácil de distribuição de download e instalação. 

> [!IMPORTANT]
> No momento, esse recurso só avalible no Windows Insider compilações do 19041.1366 +. [Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).

## Como configurar isso:
1.  Verifique se o aplicativo está configurado corretamente para a instalação.
1.  Siga estas [etapas para habilitar isso em uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 
1.  Escolha um método de implantação de certificado. 
    1.  Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.
    1.  O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
    1.  Use o Gerenciador de [certificados](hololens-insider.md#certificate-manager)no dispositivo. 

## Experiência do usuário final:
1.  O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima. 
1.  O usuário visita a URL criada a partir da etapa acima.

O aplicativo agora será instalado no dispositivo. Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar seu aplicativo. 

-   Para ajudar a solucionar problemas com esse método de instalação, acesse [solucionar](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)problemas do instalador do aplicativo. 

> [!NOTE]
> Não há suporte para a interface do usuário durante o processo de atualização. Portanto, não há suporte para a opção não receber [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e opções relacionadas.
