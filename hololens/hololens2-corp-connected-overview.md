---
title: Guia de Implantação – HoloLens 2 conectado corporativo com guias do Dynamics 365 - Visão geral
description: Saiba como registrar dispositivos do HoloLens 2 com Guias do Dynamics 365 em uma rede conectada corporativa.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448501"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guia de Implantação - HoloLens 2 conectado corporativo com guias do Dynamics 365 - Visão geral

Este guia ajudará os profissionais de TI a planejar e implantar dispositivos do Microsoft HoloLens 2 com Guias do Dynamics 365 (Guias) em sua organização. Este guia é ótimo para pilotos, bem como implantações de produção e é semelhante ao [Cenário B: Implantar dentro](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) do guia de rede da sua organização. Depois de testar sua prova de conceito, use este guia para seguir em frente com a integração do HoloLens à sua organização.

Neste guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos existente, aplicar licenças conforme necessário e validar se os usuários finais podem operar um Guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados, após a configuração do dispositivo. 

## <a name="prerequisites"></a>Pré-requisitos

A seguinte infraestrutura já deve estar em uso:
- Wi-Fi
    - Rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou serviços de Nuvem
    - Autenticação de certificado baseada em dispositivo.
- Azure Active Directory (Azure AD) Ingressar no Registro Automático do MDM ( assinatura do[Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) necessária)
- MDM (Intune) Gerenciado
    - Um ou mais aplicativos são implantados por meio do MDM.
- Rede 
    - Certificados (SCEP ou PKCS)
    - Configuração proxy
- Os usuários entrar com sua própria conta corporativa (Azure AD)
    - Há suporte para usuários simples ou múltiplos por dispositivo.
- Níveis variáveis de configurações de bloqueio de dispositivo aplicadas com base em casos de uso específicos, de Totalmente Aberto a Quiosque de Aplicativo Único.

## [<a name="guides-licensing-and-requirements"></a>Guias de licenciamento e requisitos](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Conta do Azure AD
- Guias do Dynamics 365 aplicativos pc e HoloLens
- Assinatura de Guias do Dynamics 365
    - Microsoft Dataverse (incluído)
    - Power Apps (incluído)
- Área de trabalho do Power BI
- Conectividade de rede

![Diagrama de rede conectado Corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>Estágios de implantação
### <a name="prepare"></a>Preparar
> [!div class="checklist"]
>- [Saiba mais sobre os elementos essenciais de infraestrutura para dispositivos HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Saiba mais sobre o Azure AD e configurar um caso não o tenha.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Saiba mais sobre o MDM e configurar com o Intune se você ainda não tiver um pronto.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarize-se com o Wi-Fi baseado em certificado.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarize-se com Proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Entenda como você pode usar Aplicativos de Linha de Negócios.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Saiba mais sobre a maneira como você pode usar Guias para sua organização.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurar
> [!div class="checklist"]
>- [Como criar usuários e grupos.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Como configurar o Registro Automático.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Como configurar Wi-Fi certificados e perfis corporativos Wi-Fi Conectividade.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Carregar e atribuir pacotes de aplicativos de Linha de Negócios (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Setup Dynamics 365 Guides.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Como configurar o Modo de Quiosque (opcional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Como configurar o WDAC (opcional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Implantar
> [!div class="checklist"]
>-  [Validar o registro por meio de dispositivo e MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Validar Wi-Fi certificados.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Validar a instalação do aplicativo LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Valide guias por meio da autoria e da operação.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Manter
> [!div class="checklist"]
>- [Atualizar o HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Como atualizar Guias (aplicativos de armazenamento).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Como atualizar aplicativos LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plano de desenvolvimento.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Fazendo um plano de suporte.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opções de gerenciamento de dispositivos.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Próximas etapas 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa - Preparar](hololens2-corp-connected-prepare.md)
