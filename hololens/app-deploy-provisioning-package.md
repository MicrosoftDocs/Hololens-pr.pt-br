---
title: Pacote de Provisionamento
description: aplicativo, implantação de aplicativo, implantação de aplicativo empresarial, provisionamento
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
ms.openlocfilehash: 11bc83be188e1b81959690efcb2bdf26d800aae3
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252672"
---
# Pacote de Provisionamento

Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade. Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status de inscrição, durante a experiência inicial (OOBE) ou pela [aplicação de um pacote de provisionamento durante a instalação](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## Considerações sobre pacotes de provisionamento:

* Aplicativos não públicos
* Somente o carregamento do lado USB
* Sem atualização automática (exige atualizações manuais por meio do PPKGs)

Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no repositório do computador local. Os pacotes de provisionamento só podem instalar certificados no repositório do dispositivo (computador local), portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de configuração. Se você estiver implantando seu certificado do MDM ou instalando por meio do [Gerenciador de certificados](certificate-manager.md), certifique-se de implantar o certificado no repositório da máquina local para assinar aplicativos instalados dessa maneira.

Para saber mais sobre como criar um pacote de provisionamento para dispositivos HoloLens, acesse o [provisionamento do hololens](https://docs.microsoft.com/hololens/hololens-provisioning). Para implantar um aplicativo, você deve começar com o provisionamento avançado.

> [!NOTE]
> O HoloLens (1ª gen) tem suporte limitado para a instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento. Os dispositivos HoloLens (1ª gen) só dão suporte à instalação de um aplicativo via PPKG durante o OOBE e somente com instalações de contexto de usuário.

## Configuração

Dentro do [Designer de configuração do Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga quatro etapas.

1. Defina ApplicationManagement/AllowAllTrustedApps como "Sim". Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navegue até **UniversalAppInstall**  >  **UserContextAppLicense** Insira o **PackageFamilyName**. Consulte [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Consulte também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Você pode usar o Device portal em um dispositivo em que você já instalou o aplicativo. Acesse a página aplicativos e veja a linha PackageRelativeID, todas as informações antes do "!" É o seu **PackageFamilyName**.

3. Em seguida, você verá que tem uma nova seção, **ApplicationFile**. Use esta área para carregar seu pacote Appx.

4. Dependendo se você comprou o aplicativo ou criou seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.

    - Para o arquivo de licença: Navegue até **UniversalAppInstall**  >  **UserContextAppLicence** e navegue até o local da sua licença e carregue-o.
    - Para o arquivo de segurança, navegue até **certificados** e selecione seu certificado para instalar juntamente com seu pacote. Appx.

Certifique-se de salvar seu projeto em um local seguro. Em seguida, **exporte** -o como um **pacote de provisionamento**.  

Consulte também: [aplicar seu pacote de provisionamento ao HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
