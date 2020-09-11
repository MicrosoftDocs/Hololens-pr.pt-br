---
title: Pacote de provisionamento
description: aplicativo, implantação de aplicativo, Enterprise app demployment, provisionamento
keywords: aplicativo, implantação de aplicativo, Enterprise app demployment, provisionamento
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
ms.openlocfilehash: 6daf99fbb60e0daf892d5d02e86492061a665070
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009499"
---
# Pacote de provisionamento

Os pacotes de provisionamento podem ser usados para preparar e configurar dispositivos em um ambiente sem acesso ao gerenciamento de ponto de extremidade. Eles também podem ser implantados em um dispositivo, independentemente da identidade do usuário, do status de inscrição, durante a experiência inicial (OOBE) ou pela [aplicação de um pacote de provisionamento durante a instalação](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## Considerações sobre pacotes de provisionamento:
* Aplicativos não públicos
* Somente o carregamento do lado USB
* Sem atualização automática (exige atualizações manuais por meio do PPKGs)

> [!NOTE] 
> Para saber mais sobre como criar um pacote de provisionamento para dispositivos HoloLens, acesse o [provisionamento do hololens](https://docs.microsoft.com/hololens/hololens-provisioning). Para implantar um aplicativo, você deve começar com o provisionamento avançado. 

## Configuração

No [Designer de configuração do Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga as 4 etapas a seguir.

1. Defina ApplicationManagement/AllowAllTrustedApps como "Sim". Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).
2. Em **UniversalAppInstall**  >  **UserContextAppLicense** , digite o **PackageFamilyName**. Consulte [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Consulte também: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Se não souber isso, você pode usar o Device portal em um dispositivo em que você já instalou o aplicativo. Acesse a página aplicativos e veja a linha PackageRelativeID, todas as informações antes do "!" É o seu **PackageFamilyName**.
3. Em seguida, você verá que tem uma nova seção, **ApplicationFile**. Use esta área para carregar seu pacote Appx. 
4. Dependendo se você comprou o aplicativo ou criou seu próprio aplicativo LOB, será necessário carregar o arquivo de licença ou o certificado de segurança.
    - Para o arquivo de licença: em **UniversalAppInstall**  >  **UserContextAppLience** e navegue até o local da sua licença e carregue-o. 
    - Para o arquivo de segurança, navegue até **certificados** e selecione seu certificado para instalar juntamente com seu pacote. Appx. 

Certifique-se de salvar seu projeto em um local seguro. Em seguida, **exporte** -o como um **pacote de provisionamento**.  
    
Consulte também: [aplicar seu pacote provisiong ao HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
