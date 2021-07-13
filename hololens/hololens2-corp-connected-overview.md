---
title: Guia de implantação – Guia de implantação HoloLens 2 com Guias do Dynamics 365 – Visão geral
description: Saiba como registrar HoloLens 2 dispositivos com o Dynamics 365 Guides em uma rede conectada corporativa.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637006"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guia de implantação – Corporate Connected HoloLens 2 com Guias do Dynamics 365 – Visão geral

Este guia ajudará os profissionais de TI a planejar e implantar Microsoft HoloLens 2 dispositivos com Guias do Dynamics 365 (Guias) em sua organização. Este guia é ótimo para piloto, bem como implantações de produção e é semelhante ao Cenário [B: Implantar dentro](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) do guia de rede da sua organização. Depois de testar sua prova de conceito, use este guia para avançar com a integração HoloLens em sua organização.

Neste guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos existente, aplicar licenças conforme necessário e validar se os usuários finais podem operar um Guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados após a configuração do dispositivo. 

## <a name="prerequisites"></a>Pré-requisitos

A seguinte infraestrutura já deve estar em uso:
- Wi-Fi
    - Rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem
    - Autenticação de certificado baseada em dispositivo.
- Azure Active Directory (Azure AD) Ingressar com o Registro Automático do MDM[(assinatura do Azure AD P1](/azure/active-directory/fundamentals/active-directory-whatis) necessária)
- MDM (Intune) Gerenciado
    - Um ou mais aplicativos são implantados por meio do MDM.
- Rede 
    - Certificados (SCEP ou PKCS)
    - Configuração de Proxy
- Os usuários entrarão com sua própria conta corporativa (Azure AD)
    - Há suporte para usuários individuais ou múltiplos por dispositivo.
- Níveis variados de configurações de bloqueio de dispositivo aplicadas com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.

## <a name="guides-licensing-and-requirements"></a>[Licenciamento e requisitos de guias](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Conta do AD do Azure
- Aplicativos do Dynamics 365 Guides pc e HoloLens
- Assinatura do Dynamics 365 Guides
    - Microsoft Dataverse (incluído)
    - Power Apps (incluído)
- Power BI Desktop
- Conectividade de rede

[![Diagrama de rede conectada Corp, estágio 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama de rede conectada Corp, estágio 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Neste guia, você:
### <a name="prepare"></a>Preparar
> [!div class="checklist"]
>- [Saiba mais sobre os fundamentos de infraestrutura para HoloLens 2 dispositivos.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Saiba mais sobre o Azure AD e configurar um se você não o tiver.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Saiba mais sobre o Gerenciamento de identidades e como configurar melhor as contas do Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Saiba mais sobre o MDM e configurar com o Intune se você ainda não tiver um pronto.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarize-se com o Wi-Fi baseado em certificado.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarize-se com o Proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Entenda como você pode usar aplicativos de linha de negócios.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Saiba mais sobre como você pode usar Guias para sua organização.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurar
> [!div class="checklist"]
>- [Como criar usuários e grupos.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Como configurar o Registro Automático.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Como configurar certificados Wi-Fi e perfis corporativos para conectividade Wi-Fi corporativa.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload e atribuir pacotes de aplicativos lob (linha de negócios).](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurar guias do Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Como configurar o Modo de Quiosque (opcional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Como configurar o WDAC (opcional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Implantar
> [!div class="checklist"]
>-  [Valide o registro por meio do dispositivo e do MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Valide Wi-Fi certificados.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Valide a instalação do aplicativo LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Valide guias por meio de autorização e operação.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Manter
> [!div class="checklist"]
>- [Atualização HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Como atualizar Guias (aplicativos da loja).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Como atualizar aplicativos LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plano de desenvolvimento.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Como criar um plano de suporte.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opções de gerenciamento de dispositivo.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa – Preparar](hololens2-corp-connected-prepare.md)
