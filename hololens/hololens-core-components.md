---
title: Como planejar a implantação do HoloLens 2 em um ambiente comercial
description: saiba mais sobre as principais necessidades de implantação e gerenciamento de HoloLens em ambientes corporativos, incluindo infraestrutura, azure active directory e gerenciamento de dispositivo móvel.
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
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635782"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Como planejar a implantação do HoloLens 2 em um ambiente comercial

## <a name="overview"></a>Visão geral
> [!NOTE]
> esta visão geral destina-se a ajudar os profissionais de ti a entender as considerações de implantação e gerenciamento de Microsoft HoloLens 2 dispositivos em uma organização. para usuários finais do dispositivo, consulte [obter seu HoloLens 2 pronto para usar](hololens2-setup.md) para começar.

o HoloLens 2 é executado em Windows 10 Holographic que fornece às organizações tecnologias de gerenciamento de aplicativo e de dispositivo móvel robustas, flexíveis e integradas. o Windows 10 Holographic dá suporte ao gerenciamento de ciclo de vida de dispositivos de ponta a ponta para oferecer às empresas o controle sobre seus dispositivos, dados e aplicativos. o HoloLens 2 pode ser facilmente incorporado às práticas de ciclo de vida padrão, do registro de dispositivos, da configuração e do gerenciamento de aplicativos até manutenção e desativação usando uma solução abrangente de gerenciamento de dispositivos móveis.

as etapas e vídeos a seguir podem orientá-lo pelo processo de HoloLens 2 adoção em sua organização.

| | |
|--|--|
| ![Etapa 1](images/1green.png)| <br/> **[cenários comuns de implantação](hololens-requirements.md)**: compreenda os cenários de implantação e explore os componentes principais necessários para implantar HoloLens 2 dispositivos. |
| ![Etapa 2](images/2green.png)| <br/> **[Prepare](#prepare)**: familiarize-se com os princípios básicos de infra-estrutura necessários para o HoloLens 2. |
| ![Etapa 3](images/3green.png) | <br/> **[Configurar](#configure)**: saiba como configurar seus componentes essenciais para uma implantação baseada em nuvem. |
| ![Etapa 4](images/4green.png) | <br/> **[Implantar](#deploy)**: Descubra como implantar seus dispositivos e distribua seus aplicativos de forma segura e eficiente. |
| ![Etapa 5](images/5green.png) | <br/> **[manter](#maintain)**: descubra o que é necessário para manter corretamente o estado de seus HoloLens 2 dispositivos e garantir a conformidade com a política corporativa. |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Preparar

saiba mais sobre os serviços de infraestrutura essenciais necessários para dar suporte ao conjunto completo de recursos de HoloLens 2. 

| Componente | Descrição |
|-----------|------------|
| [Azure AD](hololens-identity.md) | fornece gerenciamento de identidade e acesso para o HoloLens 2  |
| [Gerenciamento de dispositivo móvel](hololens-mdm-configure.md)| gerencia HoloLens 2 dispositivos conectados ao seu locatário  |
| [Rede Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi está disponível e os dispositivos podem ser conectados à Internet  |

## <a name="configure"></a>Configurar

Use o Intune e o autopilot como soluções de baixo toque para registrar e configurar o HoloLens 2 para o locatário do Azure AD da sua organização e MDM.

| Componente | Descrição |
|-----------|------------|
| [Registro automático](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Após o logon inicial, os dispositivos são registrados automaticamente no Azure AD e são registrados no MDM  |
| [Licenças de aplicativos](hololens2-cloud-connected-configure.md#application-licenses)| Pode ser aplicado a usuários, grupos de usuários ou grupos de dispositivos  |
| [Usuários e grupos do Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | ajuda a atribuir configurações e licenças para o HoloLens 2  |

## <a name="deploy"></a>Implantar

distribua seus dispositivos HoloLens 2 e valide sua configuração. 

| Componente | Descrição |
|-----------|------------|
| [Validação de registro](hololens2-corp-connected-deploy.md#enrollment-validation) | validar se o dispositivo tem o Azure AD ingressado no Configurações ou no Portal do Azure |
| [Validação do certificado](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Verifique as configurações e valide se elas foram distribuídas corretamente |
| [Validar instalações de aplicativos](hololens2-corp-connected-deploy.md#validate-lob-app-install) | confirme se o aplicativo está presente e funcionando no seu HoloLens 2 |

## <a name="maintain"></a>Manter

Use Windows Update para negócios junto com seu sistema MDM ou o Microsoft Store para manter sua frota de HoloLens 2 e aplicativos atualizados.

| Componente | Descrição |
|-----------|------------|
| [atualizar HoloLens 2](hololens-updates.md) | configurar atualizações conforme necessário por meio do Windows updates for Business |
| [Atualizar aplicativos](app-deploy-overview.md) | Configurar por meio do seu sistema MDM ou do Microsoft Store
