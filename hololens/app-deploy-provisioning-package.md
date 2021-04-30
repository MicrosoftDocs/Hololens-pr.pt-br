---
title: Pacote de provisionamento
description: Saiba mais sobre empacotamento de aplicativos, provisionamento, implantação e implantação de aplicativos empresariais para dispositivos HoloLens.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308115"
---
# <a name="provisioning-package"></a>Pacote de provisionamento

Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade. Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status do registro, durante a OOBE (configuração inicial pelo usuário) ou pela [aplicação de um pacote de provisionamento durante a instalação](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Considerações sobre pacotes de provisionamento:

* Aplicativos não públicos
* Somente carregamento USB
* Nenhuma atualização automática (requer atualizações manuais via PPKGs)

Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no repositório do computador local. Os pacotes de provisionamento só podem instalar certificados no armazenamento do dispositivo (computador local), portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de provisionamento. Se você estiver implantando o certificado do MDM ou instalando por meio do [Gerenciador de certificados](certificate-manager.md), certifique-se de implantar o certificado no repositório do computador local para assinar aplicativos instalados dessa maneira.

Para saber os conceitos básicos da criação de um pacote de provisionamento para dispositivos HoloLens, visite [provisionamento do hololens](https://docs.microsoft.com/hololens/hololens-provisioning). Para implantar um aplicativo, você deve começar com o provisionamento avançado.

> [!NOTE]
> O HoloLens (1º gen) tem suporte limitado para a instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento. Os dispositivos HoloLens (1º gen) só dão suporte à instalação de um aplicativo por meio de PPKG somente durante o OOBE e somente com instalações de contexto de usuário.

## <a name="setup"></a>Instalação

No [Windows Configuration designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga as quatro etapas a seguir.

1. Defina ApplicationManagement/AllowAllTrustedApps como "Sim". Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navegue até **UniversalAppInstall**  >  **UserContextAppLicense** Insira o **PackageFamilyName**. Consulte [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Consulte também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Você pode usar o portal do dispositivo em um dispositivo no qual você já instalou o aplicativo. Visite a página de aplicativos e examine a linha PackageRelativeID, todas as informações antes de "!" É seu **PackageFamilyName**.

3. Em seguida, você verá que tem uma nova seção, **ApplicationFile**. Use esta área para carregar seu pacote Appx.

4. Dependendo de se você comprou seu aplicativo ou criou seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.

    - Para o arquivo de licença: Navegue até **UniversalAppInstall**  >  **UserContextAppLicence** e navegue até o local da sua licença e carregue-o.
    - Para o arquivo de segurança, navegue até **certificados** e selecione seu certificado para instalar junto com seu pacote. Appx.

Certifique-se de salvar seu projeto em um local seguro. Em seguida, **exporte** -o como um **pacote de provisionamento**.  

Consulte também: [aplicar seu pacote de provisionamento ao HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
