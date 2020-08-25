---
title: Requisitos de Licença
description: ''
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3ac86512755620ebb6159dd4d845b488e203dbad
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956757"
---
# Requisitos de Licença

## Diretrizes de Licença do MDM (Sistema de Gerenciamento de Dispositivo Móvel)

Se planeja gerenciar dispositivos HoloLens, será necessário ter o Azure AD e um MDM. O Active Directory (AD) não pode ser usado para gerenciar dispositivos HoloLens.
Se você planeja usar um MDM diferente do Intune, será necessário ter uma [Licença do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).
Se você planeja usar o Intune como o seu MDM, veja [aqui](https://docs.microsoft.com/intune/fundamentals/licenses) uma lista de pacotes que incluem licenças do Intune. **Observe que o Azure AD está incluído na maioria desses pacotes.**

## Identifique as licenças necessárias para seu cenário e produtos

### Requisitos de Licenças do HoloLens (1ª geração)

Talvez seja necessário atualizar o dispositivo HoloLens 1ª geração para o Windows Holographic for Business. (Confira os [recursos comerciais do HoloLens](holoLens-commercial-features.md#feature-comparison-between-editions) para determinar se você precisa fazer atualizações).

 Em caso afirmativo, você precisará fazer o seguinte:

- Adquirir um arquivo XML de licença do HoloLens Enterprise
- Aplicar o arquivo XML ao HoloLens. É possível fazer isso através de um [Pacote de provisionamento](hololens-provisioning.md) ou através do [Gerenciador de Dispositivo Móvel](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### Requisitos da Licença da Assistência Remota

Verifique se você tem o licenciamento e o dispositivo necessários. O licenciamento atualizado e os requisitos do produto podem ser encontrados [aqui](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).

1. [Licença de Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Ou experimente a [avaliação do Assistente Remoto](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Licença do Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Se você planeja implementar **[esse cenário entre locatários](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, pode precisar de uma licença de Barreiras de Informações. Consulte [este artigo](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) para determinar se é necessária uma licença de Barreira de Informações.

### Requisitos de Licença de Guias

O licenciamento atualizado e os requisitos do dispositivo podem ser encontrados [aqui](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).

1. [Licença do Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Guias](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
