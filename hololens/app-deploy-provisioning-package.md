---
title: Pacote de provisionamento
description: saiba mais sobre empacotamento de aplicativos, provisionamento, implantação e implantação de aplicativos empresariais para dispositivos HoloLens.
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635510"
---
# <a name="provisioning-package"></a>Pacote de provisionamento

Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade. Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status do registro, durante a OOBE (configuração inicial pelo usuário) ou pela [aplicação de um pacote de provisionamento durante a instalação](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Considerações sobre pacotes de provisionamento:

* Aplicativos não públicos
* Somente carregamento USB
* Nenhuma atualização automática (requer atualizações manuais via PPKGs)

Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no repositório do computador local. Os pacotes de provisionamento só podem instalar certificados no armazenamento do dispositivo (computador local), portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de provisionamento. Se você estiver implantando o certificado do MDM ou instalando por meio do [Gerenciador de certificados](certificate-manager.md), certifique-se de implantar o certificado no repositório do computador local para assinar aplicativos instalados dessa maneira.

para saber os conceitos básicos da criação de um pacote de provisionamento para dispositivos HoloLens, visite [HoloLens provisionando](/hololens/hololens-provisioning). Para implantar um aplicativo, você deve começar com o provisionamento avançado.

> [!NOTE]
> HoloLens (1º gen) tem suporte limitado para a instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento. os dispositivos HoloLens (1ª gen) só dão suporte à instalação de um aplicativo por meio de PPKG somente durante o OOBE e somente com instalações de contexto de usuário.

## <a name="setup"></a>Instalação

no [Windows Designer de configuração](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga quatro etapas.

1. Defina ApplicationManagement/AllowAllTrustedApps como "Sim". Consulte: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navegue até **UniversalAppInstall**  >  **UserContextAppLicense** Insira o **PackageFamilyName**. Consulte [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall). Consulte também: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Você pode usar o portal do dispositivo em um dispositivo no qual você já instalou o aplicativo. Visite a página de aplicativos e examine a linha PackageRelativeID, todas as informações antes de "!" É seu **PackageFamilyName**.

3. Em seguida, você verá que tem uma nova seção, **ApplicationFile**. Use esta área para carregar seu pacote Appx.

4. Dependendo de se você comprou seu aplicativo ou criou seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.

    - Para o arquivo de licença: Navegue até **UniversalAppInstall**  >  **UserContextAppLicence** e navegue até o local da sua licença e carregue-o.
    - Para o arquivo de segurança, navegue até **certificados** e selecione seu certificado para instalar junto com seu pacote. Appx.

Certifique-se de salvar seu projeto em um local seguro. Em seguida, **exporte** -o como um **pacote de provisionamento**.  

Consulte também: [aplicar seu pacote de provisionamento ao HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
