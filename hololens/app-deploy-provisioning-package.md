---
title: Pacote de provisionamento
description: Saiba mais sobre empacotamento de aplicativos, provisionamento, implantação e implantação de aplicativos empresariais para HoloLens dispositivos.
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
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: f480d3cc8d549fa356e05df6ce15e9517f5b978a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2021
ms.locfileid: "123610982"
---
# <a name="provisioning-package"></a>Pacote de provisionamento

Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade. Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status do registro, durante a OOBE (Experiência Inicial) ou aplicando um pacote de [provisionamento](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)durante a instalação do .

## <a name="provisioning-packages-considerations"></a>Considerações sobre pacotes de provisionamento

* Aplicativos não públicos
* Somente carregamento lateral USB
* Nenhuma atualização automática (requer atualizações manuais por meio de PPKGs)

Os aplicativos instalados por meio de um pacote de provisionamento devem ser assinados por um certificado no armazenamento do computador local. Os pacotes de provisionamento só podem instalar certificados no armazenamento do dispositivo (computador local). Portanto, um aplicativo e um certificado podem ser instalados por meio do mesmo pacote de provisionamento. Se você estiver implantando seu certificado do MDM ou instalando por meio do [Gerenciador](certificate-manager.md)de Certificados, implante o certificado no armazenamento do computador local para assinar aplicativos instalados dessa maneira.

Para saber as noções básicas da criação de um pacote de provisionamento para dispositivos HoloLens, visite [HoloLens Provisionamento.](/hololens/hololens-provisioning) Para implantar um aplicativo, você deve começar com o provisionamento avançado.

> [!NOTE]
> HoloLens (1ª geração) tem suporte limitado para instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento. HoloLens (1ª geração) só são compatíveis com a instalação de um aplicativo via PPKG somente durante o OOBE e somente com as instalações de contexto do usuário.

## <a name="setup"></a>Instalação

Dentro [Windows Designer de Configuração,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) tome as quatro etapas a seguir.

1. De acordo com ApplicationManagement/AllowAllTrustedApps como "Sim". Consulte: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Navegue **até UniversalAppInstall**  >  **UserContextApp** insira **PackageFamilyName.** Consulte [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   Você pode usar Portal de Dispositivos em um dispositivo em que você já instalou seu aplicativo. Visite a página Aplicativos e veja a linha PackageRelativeID, todas as informações antes de "!" É **o PackageFamilyName.**

3. Em seguida, você verá que tem uma nova seção, **ApplicationFile.** Use essa área para carregar seu pacote appx.

4. Dependendo se você tiver comprado seu aplicativo ou criado seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.

    - Para o arquivo de licença: navegue até **UniversalAppInstall**  >  **UserContextAppLicence** e insira sua ID do produto de licença. Uma nova seção <b>LicenseProductID:</b><i>yourlicenseproductid</i> será criada, selecione esta nova seção e navegue até o local da sua licença e carregue-a.
        - Consulte [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Para o arquivo de segurança, navegue até **Certificados** e selecione seu certificado para instalar junto com o pacote .appx.

Salve seu projeto em um local seguro. Em **seguida,** exporte-o **como um pacote de provisionamento.**  

Confira também: [Aplicar seu pacote de provisionamento ao HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
