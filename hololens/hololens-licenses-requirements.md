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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427391"
---
# <a name="license-requirements"></a>Requisitos de licença

## <a name="overview"></a>Visão geral
Esta página contém uma visão geral de alto nível das licenças e contas necessárias para implantar dispositivos HoloLens 2 gerenciados e não gerenciados em sua organização. Ele também inclui informações para licenciamento do [Remote Assist](#dynamics-365-remote-assist) e dos [guias](#dynamics-365-guides) do Dynamics 365.

## <a name="hololens-2-license-and-account-requirements"></a>Requisitos de licença e conta do HoloLens 2

 
|       &nbsp;      | HoloLens gerenciado | HoloLens não gerenciado |
|-------------------|-----------------|---------------------|
| **Caso de uso empresarial** | | |
| [Implantar em dispositivos conectados à nuvem – prova de conceito/implantação piloto](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Implantar dentro da rede da sua organização – implantação em escala](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Implantar em um ambiente offline seguro](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licenças** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> ou <sup>2</sup>) | ✔️  | |
| **Contas** |  | |
| Conta do administrador do Azure AD | ✔️ |  |
| Conta de Usuário do Azure AD | ✔️ | |
| [MSA (conta Microsoft)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Conta local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> O [registro automático](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) durante a configuração inicial do dispositivo, que registra e ingressa no Azure Active Directory, permitindo que o dispositivo seja gerenciado com o Intune.
- <sup>2</sup> O [Windows Autopilot para HoloLens 2](hololens2-autopilot.md) simplifica a experiência de provisionamento para administradores de TI e usuários finais. Os administradores de TI podem pré-configurar políticas do HoloLens 2 e, na primeira inicialização, os dispositivos serão implantados no estado pronto para a empresa sem a interação do usuário final.
- <sup>3</sup> Essa conta precisa ser [provisionada](hololens-provisioning.md#provisioning-package-hololens-wizard) com antecedência por meio do WCD (Designer de Configuração do Windows).

> [!IMPORTANT]
> O AD (Active Directory) não pode ser usado para gerenciar dispositivos HoloLens.
 
> [!WARNING]
> Não há suporte para vários usuários em um dispositivo que usa MSA ou uma conta local.

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

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Conectividade de rede

Se você pretende implementar esse [cenário entre locatários](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), talvez precise ter uma licença de Barreiras de Informações. Confira [este artigo](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se uma licença de Barreiras de Informações é necessária.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Admin

1. Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)
2. [Assinatura ou avaliação gratuita](/dynamics365/mixed-reality/guides/setup-step-one) do Dynamics 365 Guides

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
