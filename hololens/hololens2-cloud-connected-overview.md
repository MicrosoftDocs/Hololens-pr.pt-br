---
title: Visão geral do Cloud Connected HoloLens 2 com o Remote Assist
description: Saiba como registrar HoloLens 2 dispositivos em uma rede conectada à nuvem usando o Dynamics 365 Remote Assist.
keywords: HoloLens, gerenciamento, nuvem conectada, Assistência Remota, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031987"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guia de implantação – Nuvem conectada HoloLens 2 com Assistência Remota – Visão geral

Este guia ajudará os profissionais de TI a planejar e implantar Microsoft HoloLens 2 dispositivos com o Remote Assist em sua organização. Isso servirá como um modelo para implantações de prova de conceito em sua organização em vários HoloLens dois casos de uso. A configuração é semelhante ao [Cenário A: Implantar em dispositivos de conexão de nuvem.](common-scenarios.md#scenario-a) 

Durante o guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na instalação do dispositivo. Para fazer isso, vamos falar sobre as partes importantes da infraestrutura necessárias para ser configurada e em execução , alcançando a implantação em escala com HoloLens 2. Nenhuma outra restrição de dispositivo ou configurações será aplicada neste guia, no entanto, incentivamos você a explorar essas opções após a conclusão.

## <a name="prerequisites"></a>Pré-requisitos

A infraestrutura a seguir deve estar em uso para implantar o HoloLens 2. Caso não, a configuração do Azure e do Intune está incluída neste guia:

Essa é uma configuração semelhante ao Cenário [A:](/hololens/common-scenarios#scenario-a)Implantar em dispositivos de conexão de nuvem, que é uma boa opção para muitas implantações de Prova de Conceito, o que incluirá:

- Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e nuvem
- Ingressar no Azure AD com o registro automático do MDM — gerenciado por MDM (Intune)
- Os usuários entrarão com sua própria conta corporativa (Azure AD)
    - Há suporte para usuários individuais ou múltiplos por dispositivo.

:::image type="content" alt-text="Cenário conectado à nuvem." source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Saiba mais sobre o Remote Assist

O Remote Assist permite manutenção e reparo colaborativos, inspeção remota, bem como treinamento e compartilhamento de conhecimento. Conectando pessoas em diferentes funções e locais, um técnico que usa a Assistência Remota pode se conectar com um colaborador remoto Microsoft Teams. Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando não estão no mesmo local. Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis do espaço físico do técnico para que possam se referir ao esquema enquanto trabalham de cabeça para cima e sem mãos HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licenciamento e requisitos do Remote Assist

- Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)
- [Assinatura do Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [avaliação do Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Usuário do Dynamics 365 Remote Assist

- Licença do Remote Assist
- Conectividade de rede

#### <a name="microsoft-teams-user"></a>Usuário do Microsoft Teams

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Conectividade de rede

Se você pretende implementar esse [cenário entre locatários](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), talvez precise ter uma licença de Barreiras de Informações. Para determinar se uma Licença de Barreira de Informações é necessária, consulte Fornecedores e clientes [usam funcionalidades completas do Dynamics 365 Remote Assist.](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)

## <a name="in-this-guide-you-will"></a>Neste guia, você:

Preparar:

> [!div class="checklist"]
> - [Saiba mais sobre os fundamentos de infraestrutura para HoloLens 2 dispositivos.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Saiba mais sobre o Azure AD e configurar um se você&#39;o tiver.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Saiba mais sobre o Gerenciamento de identidades e como configurar melhor as contas do Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Saiba mais sobre o MDM e configurar com o Intune se&#39;ainda não tiver um pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Saiba mais sobre os requisitos de rede do Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para se conectar a recursos organizacionais](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurar:

> [!div class="checklist"]
> - [Como criar Usuários e Grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Como configurar o registro automático no Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Como atribuir suas licenças de aplicativo.](hololens2-cloud-connected-configure.md#application-licenses)

Implantar:

> [!div class="checklist"]
> - [Configurar seu HoloLens 2 e validar o registro.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valide se você pode fazer uma chamada de Assistência Remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Manter:

> [!div class="checklist"]
> - [Como atualizar o Remote Assist usando o Microsoft Store aplicativo.](hololens2-cloud-connected-maintain.md#updates)
> - [Como criar um plano de suporte.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plano de desenvolvimento.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem – Preparar](hololens2-cloud-connected-prepare.md)

