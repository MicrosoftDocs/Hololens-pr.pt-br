---
title: Pacote de provisionamento
description: Saiba mais sobre empacotamento de aplicativos, provisionamento, implantação e implantação de aplicativos corporativos para dispositivos HoloLens.
keywords: aplicativo, implantação de aplicativo, implantação de aplicativo empresarial, provisionamento
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283692"
---
# Pacote de provisionamento

Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de pontos de extremidade. Eles também podem ser implantados em um dispositivo independentemente da identidade do usuário, do status do registro, durante a configuração inicial pelo usuário (OOBE) ou pela aplicação de um pacote de [provisionamento](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)durante a instalação.

## Considerações sobre pacotes de provisionamento:

* Aplicativos não públicos
* Somente carregamento lateral USB
* Nenhuma atualização automática (requer atualizações manuais via PPKGs)

Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no armazenamento da máquina local. Os pacotes de provisionamento só podem instalar certificados no armazenamento do dispositivo (máquina local), portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de provisionamento. Se você estiver implantando seu certificado do MDM ou instalando por meio do Gerenciador de [Certificados,](certificate-manager.md)certifique-se de implantar o certificado no armazenamento da máquina local para assinar aplicativos instalados dessa maneira.

Para saber as noções básicas de criação de um pacote de provisionamento para dispositivos HoloLens, visite [o provisionamento do HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning) Para implantar um aplicativo, você deve começar com o provisionamento avançado.

> [!NOTE]
> O HoloLens (1ª geração) tem suporte limitado à instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento. Os dispositivos HoloLens (1ª geração) só suportam a instalação de um aplicativo via PPKG somente durante o OOBE e somente com as instalações de contexto do usuário.

## Configuração

No [Designer de Configuração do Windows,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) as quatro etapas são seguidas.

1. Definir ApplicationManagement/AllowAllTrustedApps como "Sim". Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navegue **até UniversalAppInstall**  >  **UserContextAppLicense** e insira **PackageFamilyName**. Consulte [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Consulte também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Você pode usar o Device Portal em um dispositivo em que já instalou seu aplicativo. Visite a página Aplicativos e veja a linha PackageRelativeID, todas as informações antes de "!" Seu **PackageFamilyName**.

3. Em seguida, você verá que tem uma nova seção, **ApplicationFile**. Use essa área para carregar seu pacote appx.

4. Dependendo se você tiver comprado seu aplicativo ou criado seu próprio aplicativo LOB, precisará carregar o arquivo de licença ou o certificado de segurança.

    - Para o arquivo de licença: navegue até **UniversalAppInstall**  >  **UserContextAppLicence,** navegue até o local da sua licença e carregue-o.
    - Para o arquivo de segurança, navegue até **Certificados** e selecione seu certificado a ser instalado junto com seu pacote .appx.

Certifique-se de salvar seu projeto em um local seguro. Em **seguida,** exporte-o **como um pacote de provisionamento.**  

Consulte também: [Aplicar seu pacote de provisionamento ao HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
