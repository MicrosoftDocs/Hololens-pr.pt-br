---
title: Requisitos de licença
description: Mantenha-se atualizado com todos os requisitos de licenciamento e as diretrizes de que você precisa para o gerenciamento de dispositivo móvel, o HoloLens e o Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640264"
---
# <a name="license-requirements"></a>Requisitos de licença

## <a name="hololens-2-device-managed"></a>Dispositivo HoloLens 2 (gerenciado)

[Conta do Azure AD](/azure/active-directory/)

> [!IMPORTANT]
> O AD (Active Directory) não pode ser usado para gerenciar dispositivos HoloLens.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) ou outro MDM.
- [Windows Autopilot para HoloLens 2](hololens2-autopilot.md): simplifica a experiência de provisionamento para administradores de TI e usuários finais. Os administradores de TI podem pré-configurar políticas do HoloLens 2 e, na primeira inicialização, os dispositivos serão implantados no estado pronto para a empresa sem a interação do usuário final. 

  > [!NOTE]
  > O Windows Autopilot exige a que o [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) e o [registro automático](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) sejam configurados primeiro para o fluxo de poucos toques do Autopilot e a implantação do dispositivo. 

### <a name="business-use-case"></a>Caso de uso empresarial: 

- [Cenário de implantação A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices): prova de conceito ou implantação piloto.

- [Cenário de implantação B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network): implantação em escala.

## <a name="hololens-2-device-only-non-managed"></a>Somente dispositivo HoloLens 2 (não gerenciado)

Quando uma MSA (conta Microsoft) ou uma conta local é usada, nenhuma licença adicional é necessária para essas contas.

[Conta local](/windows/security/identity-protection/access-control/local-accounts)

- Essa conta precisa ser [provisionada](hololens-provisioning.md#provisioning-package-hololens-wizard) com antecedência por meio do WCD (Designer de Configuração do Windows).

[MSA (conta Microsoft)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Não há suporte para o uso de vários usuários em um dispositivo com uma dessas contas.

### <a name="business-use-case"></a>Caso de uso empresarial: 

- [Cenário de implantação C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment): implantação offline ou segura.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Requisitos e licenciamento do Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Admin

- Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)
- [Assinatura do Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [avaliação do Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Usuário do Dynamics 365 Remote Assist

- Conta do AD do Azure

- Licença do Remote Assist 

  > [!NOTE]
  > O Microsoft Teams está incluído no pacote com o Remote Assist

- Conectividade de rede

#### <a name="microsoft-teams-user"></a>Usuário do Microsoft Teams

- Conta do AD do Azure

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free).

- Conectividade de rede

Se você pretende implementar esse [cenário entre locatários](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), talvez precise ter uma licença de Barreiras de Informações. Confira [este artigo](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se uma licença de Barreiras de Informações é necessária.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Admin

- Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)
- [Assinatura ou avaliação gratuita](/dynamics365/mixed-reality/guides/setup-step-one) do Dynamics 365 Guides

#### <a name="guides-author"></a>Autor de guias

1. Conta do AD do Azure
1. [Licença do Dynamics 365 Guides](/dynamics365/mixed-reality/guides/requirements)
1. Aplicativo Dynamics 365 Guides instalado em um computador ou em um HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (usado para exibir o dashboard do Analytics)
1. Função de autor (para criar guias)
1. Conectividade de rede

#### <a name="guides-user"></a>Usuário de guias

1. Conta do AD do Azure
1. [Licença do Dynamics 365 Guides](/dynamics365/mixed-reality/guides/requirements)
1. Aplicativo Dynamics 365 Guides instalado em um HoloLens
1. Função de operador (para testar ou usar guias)
1. Conectividade de rede
