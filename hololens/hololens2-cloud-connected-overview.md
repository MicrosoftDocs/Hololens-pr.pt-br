---
title: visão geral da nuvem conectada HoloLens 2 com o auxílio remoto
description: saiba como registrar HoloLens 2 dispositivos em uma rede conectada na nuvem usando o assistente remoto do Dynamics 365.
keywords: HoloLens, gerenciamento, nuvem conectada, assistência remota, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
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
ms.openlocfilehash: 8bba313e7b5ee3d055c2b6ff2c60810baf428ecfa7d5554a1efb4e0aa9e1e98b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660326"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>guia de implantação – conectado à nuvem HoloLens 2 com assistência remota – visão geral

este guia ajudará os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 com o auxílio remoto para sua organização. isso servirá como um modelo para implantações de prova de conceito em sua organização em vários casos de uso HoloLens 2. A configuração é semelhante ao [cenário a: implantar em dispositivos do Cloud Connect](common-scenarios.md#scenario-a). 

Durante o guia, abordaremos como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar que os usuários finais podem usar imediatamente a assistência remota após a configuração do dispositivo. para fazer isso, veremos as importantes partes da infraestrutura necessária para a configuração e a execução – atingindo a implantação em escala com o HoloLens 2. Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, no entanto, incentivamos você a explorar essas opções após a conclusão.

## <a name="prerequisites"></a>Pré-requisitos

a infraestrutura a seguir deve estar em vigor para implantar o HoloLens 2. Caso contrário, a configuração do Azure e do Intune está incluída neste guia:

Essa é uma configuração semelhante ao [cenário a: implantar em dispositivos do Cloud Connect](/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implantações de prova de conceito, que incluirá:

- As redes Wi-Fi normalmente são totalmente abertas na Internet e nos serviços de nuvem
- Ingresso no Azure AD com o registro automático do MDM — gerenciado pelo MDM (Intune)
- Os usuários entram com sua própria conta corporativa (Azure AD)
    - Há suporte para um ou vários usuários por dispositivo.

:::image type="content" alt-text="Cenário conectado à nuvem" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Saiba mais sobre o auxílio remoto

A assistência remota permite a manutenção e o reparo colaborativos, a inspeção remota, bem como o compartilhamento e o treinamento de conhecimento. Ao conectar pessoas em diferentes funções e locais, um técnico que usa a assistência remota pode se conectar com um colaborador remoto no Microsoft Teams. Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando não estiverem no mesmo local. Os colaboradores remotos podem inserir imagens de referência, esquemáticos e outras informações úteis do espaço físico do técnico para que eles possam se referir ao esquema durante o trabalho e a mão livre em HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Requisitos e licenciamento da assistência remota

- Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)
- [Assinatura de assistência remota](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [avaliação de assistência remota](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Usuário de assistência remota do Dynamics 365

- Licença de assistência remota
- Conectividade de rede

#### <a name="microsoft-teams-user"></a>Microsoft Teams usuário

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Conectividade de rede

Se você planeja implementar esse [cenário de locatário cruzado](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), talvez precise de uma licença de barreiras de informações. Para determinar se uma licença de barreira de informações é necessária, consulte [fornecedores e clientes que usam recursos completos de assistência remota do Dynamics 365](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).

## <a name="in-this-guide-you-will"></a>Neste guia, você:

Preparar:

> [!div class="checklist"]
> - [saiba mais sobre as noções básicas de infraestrutura para dispositivos HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Saiba mais sobre o Azure AD e configure um se você não&#39;o tiver.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Saiba mais sobre o MDM e configure-o com o Intune se você não&#39;t já tiver um pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Saiba mais sobre os requisitos de rede do auxílio remoto.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para se conectar aos recursos organizacionais](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurar:

> [!div class="checklist"]
> - [Como criar usuários e grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Como configurar o registro automático no Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Como atribuir suas licenças de aplicativo.](hololens2-cloud-connected-configure.md#application-licenses)

Implantar:

> [!div class="checklist"]
> - [configure seu HoloLens 2 e valide o registro.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Validar você pode fazer uma chamada de assistência remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Manter:

> [!div class="checklist"]
> - [como atualizar a assistência remota usando o aplicativo Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Fazendo um plano de suporte.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plano de desenvolvimento.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem-preparar](hololens2-cloud-connected-prepare.md)

