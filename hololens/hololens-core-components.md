---
title: Como planejar a implantação do HoloLens 2 em um ambiente comercial
description: Saiba mais sobre as principais necessidades de implantação e gerenciamento de HoloLens em ambientes corporativos, incluindo infraestrutura, azure Active Directory e gerenciamento de dispositivo móvel.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 8273813d85c3b2df2c1a551fb0322a867a5a9c64fdd05e9a85a2097b1590fb62
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664371"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Como planejar a implantação do HoloLens 2 em um ambiente comercial

## <a name="overview"></a>Visão geral

> [!NOTE]
> Esta visão geral destina-se a ajudar os profissionais de TI a entender as considerações para implantar e gerenciar Microsoft HoloLens 2 dispositivos em uma organização. Para usuários finais do dispositivo, consulte [Preparar HoloLens 2 para uso](hololens2-setup.md) para começar.

HoloLens 2 é executado Windows 10 Holographic que fornece às organizações tecnologias robustas, flexíveis e de gerenciamento de aplicativos móveis. Windows 10 Holographic dá suporte ao gerenciamento de ciclo de vida do dispositivo de ponta a ponta para dar às empresas controle sobre seus dispositivos, dados e aplicativos. O HoloLens 2 pode ser facilmente incorporado às práticas de ciclo de vida padrão, desde o registro do dispositivo, a configuração e o gerenciamento de aplicativos até a manutenção e a replicação usando uma solução abrangente de gerenciamento de dispositivo móvel.

As etapas e o vídeo a seguir podem ajudar a orientá-lo pelo processo de HoloLens adoção 2 em sua organização.

| &nbsp; | &nbsp; |
|--|--|
| ![Etapa 1](images/1green.png)| <br/> **[Cenários comuns de implantação:](hololens-requirements.md)** entenda os cenários de implantação e explore os componentes principais necessários para implantar HoloLens 2 dispositivos. |
| ![Etapa 2](images/2green.png)| <br/> **[Preparar:](#prepare)** familiarizar-se com os fundamentos de infraestrutura necessários para HoloLens 2. |
| ![Etapa 3](images/3green.png) | <br/> **[Configurar](#configure)**: saiba como configurar seus componentes essenciais para uma implantação baseada em nuvem. |
| ![Etapa 4](images/4green.png) | <br/> **[Implantar:](#deploy)** descubra como implantar seus dispositivos e distribuir seus aplicativos com segurança e eficiência. |
| ![Etapa 5](images/5green.png) | <br/> **[Manter:](#maintain)** descubra o que é necessário para manter corretamente o estado de seus dispositivos HoloLens 2 e garantir a conformidade com a política corporativa. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Preparar

Saiba mais sobre os serviços de infraestrutura essenciais necessários para dar suporte ao conjunto completo de HoloLens 2.

| Componente | Descrição |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Fornece gerenciamento de identidade e acesso para o HoloLens 2  |
| [Gerenciamento de dispositivo móvel](hololens-mdm-configure.md)| Gerencia HoloLens dois dispositivos conectados ao seu locatário  |
| [Rede Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi está disponível e os dispositivos podem ser conectados à Internet  |

## <a name="configure"></a>Configurar

Use o Intune e o Autopilot como soluções de baixo toque para registrar e configurar o HoloLens 2 para o locatário e o MDM do Azure AD da sua organização.

| Componente | Descrição |
|-----------|------------|
| [Registro automático](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Após o logon inicial, os dispositivos se registram automaticamente no Azure AD e se registram no MDM  |
| [Licenças de aplicativo](hololens2-cloud-connected-configure.md#application-licenses)| Pode ser aplicado a usuários, grupos de usuários ou grupos de dispositivos  |
| [Usuários e grupos do Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Ajuda a atribuir configurações e licenças para o HoloLens 2  |

## <a name="deploy"></a>Implantar

Distribua seus HoloLens 2 dispositivos e valide sua configuração. 

| Componente | Descrição |
|-----------|------------|
| [Validação de registro](hololens2-corp-connected-deploy.md#enrollment-validation) | Validar se o dispositivo tem o Azure AD ingressado Configurações portal do Azure |
| [Validação do certificado](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Verifique as configurações e valide se elas foram distribuídas corretamente |
| [Validar as instalados do aplicativo](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Confirme se o aplicativo está presente e trabalhando em seu HoloLens 2 |

## <a name="maintain"></a>Manter

Use Windows Update for Business juntamente com seu sistema MDM ou o Microsoft Store para manter sua frota de HoloLens 2 e aplicativos atualizados.

| Componente | Descrição |
|-----------|------------|
| [Atualização HoloLens 2](hololens-updates.md) | Configurar atualizações conforme necessário por meio Windows Atualizações para Empresas |
| [Atualizar aplicativos](app-deploy-overview.md) | Configure por meio do sistema MDM ou do Microsoft Store
