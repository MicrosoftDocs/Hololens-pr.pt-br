---
title: guia de implantação – corporativo conectado HoloLens 2 com guias do Dynamics 365-visão geral
description: saiba como registrar HoloLens 2 dispositivos com os guias do Dynamics 365 em uma rede conectada corporativa.
keywords: HoloLens, gerenciamento, corporativo conectado, guias do Dynamics 365, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
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
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031970"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>guia de implantação-corporativos conectados HoloLens 2 com guias do Dynamics 365-visão geral

este guia ajudará os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 com guias do Dynamics 365 (guias) para sua organização. Este guia é ótimo para pilotos, bem como para implantações de produção e é semelhante ao [cenário B: implantar dentro do guia de rede da sua organização](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) . depois de testar sua verificação de conceito, use este guia para continuar com a integração de HoloLens à sua organização.

Neste guia, abordaremos como registrar seus dispositivos em seu gerenciamento de dispositivo existente, aplicar licenças conforme necessário e validar que os usuários finais podem operar um guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados após a configuração do dispositivo. 

## <a name="prerequisites"></a>Pré-requisitos

A infraestrutura a seguir já deve estar em vigor:
- Wi-Fi
    - Rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem
    - Autenticação de certificado baseada em dispositivo.
- junção do Azure Active Directory (azure ad) com o registro automático[do MDM (assinatura do azure AD P1](/azure/active-directory/fundamentals/active-directory-whatis) necessária)
- MDM (Intune) gerenciado
    - Um ou mais aplicativos são implantados por meio do MDM.
- Rede 
    - Certificados (SCEP ou PKCS)
    - Configuração de proxy
- Os usuários entram com sua própria conta corporativa (Azure AD)
    - Há suporte para um ou vários usuários por dispositivo.
- Níveis variados de configurações de bloqueio de dispositivo aplicadas com base em casos de uso específicos, de totalmente aberto para quiosque de aplicativo único.

## <a name="guides-licensing-and-requirements"></a>[Guia de licenciamento e requisitos](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Conta do AD do Azure
- Dynamics 365 orienta os aplicativos PC e HoloLens
- Assinatura de guias do Dynamics 365
    - Microsoft dataverso (incluído)
    - Power Apps (incluído)
- Power BI Desktop
- Conectividade de rede

[![Diagrama de rede conectada Corp, estágio 1. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama de rede conectada Corp, estágio 2. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Neste guia, você:
### <a name="prepare"></a>Preparar
> [!div class="checklist"]
>- [saiba mais sobre as noções básicas de infraestrutura para dispositivos HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Saiba mais sobre o Azure AD e configure um se você não o tiver.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Saiba mais sobre o MDM e configure-o com o Intune se você ainda não tiver um pronto.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarize-se com Wi-Fi baseado em certificado.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarize-se com o proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Entenda como você pode usar aplicativos de linha de negócios.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Saiba mais sobre como você pode usar guias para sua organização.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurar
> [!div class="checklist"]
>- [Como criar usuários e grupos.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Como configurar o registro automático.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Como configurar Wi-Fi certificados e perfis para conectividade Wi-Fi corporativa.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload e atribuir pacotes de aplicativos de linha de negócios (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurar guias do Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Como configurar o modo de quiosque (opcional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Como configurar o WDAC (opcional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Implantar
> [!div class="checklist"]
>-  [Valide o registro por meio do dispositivo e do MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Validar Wi-Fi certificados.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Valide a instalação do aplicativo de LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Valide os guias por meio de criação e operação.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Manter
> [!div class="checklist"]
>- [atualização HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Como atualizar guias (aplicativos da loja).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Como atualizar aplicativos LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plano de desenvolvimento.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Fazendo um plano de suporte.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opções de gerenciamento de dispositivo.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa-preparar](hololens2-corp-connected-prepare.md)
