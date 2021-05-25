---
title: Visão geral do HoloLens 2 conectado à nuvem com Assistência Remota
description: Saiba como registrar dispositivos HoloLens 2 em uma rede conectada à nuvem usando o Dynamics 365 Remote Assist.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Dispositivos móveis Gerenciamento de Dispositivos
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397647"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guia de implantação – HoloLens 2 conectado à nuvem com Assistência Remota – Visão geral

Este guia ajuda os profissionais de TI a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com a meta geral de ter esses dispositivos conectados à nuvem à sua organização com o Dynamics 365 Remote Assist pronto para uso. Tenha em mente que isso servirá como um modelo para implantações de prova de conceito em sua organização em uma variedade de casos de uso do HoloLens 2.

Durante o guia, vamos abranger como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na configuração do dispositivo. Para fazer isso, vamos falar sobre as partes importantes da infraestrutura necessárias para se configurar e executar – alcançando a implantação em escala com o HoloLens 2.

[![Cenário conectado à nuvem ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>Neste guia

Este guia tem a meta específica de configurar o Remote Assist em sua organização em seus dispositivos HoloLens. Vamos abranger as necessidades necessárias para atingir essa meta. Para manter o foco nessa meta, determinadas configurações e preparação serão pré-selecionadas para otimizar essa implantação ou reduzir os itens necessários para configurar. Você será informado dessas opções e poderá personalizar sua implantação com base em suas necessidades de negócios.

Essa é uma configuração semelhante ao Cenário [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implantar em dispositivos de conexão de nuvem, que é uma boa opção para muitas implantações de Prova de Conceito, que incluirão:

- Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e nuvem
- Ingressar no Azure AD com Registro Automático do MDM – MDM (Intune) Gerenciado
- Os usuários entrarão com sua própria conta corporativa (Azure AD)
  - Usuários individuais ou múltiplos por dispositivo com suporte
- Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente aberto para quiosque de aplicativo único



Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, no entanto, recomendamos que você explore essas opções após a conclusão.

## <a name="learn-about-remote-assist"></a>Saiba mais sobre o auxílio remoto

A assistência remota permite a manutenção e o reparo colaborativos, a inspeção remota, bem como o compartilhamento e o treinamento de conhecimento. Ao conectar pessoas em diferentes funções e locais, um técnico usando a assistência remota pode se conectar com um colaborador remoto do Microsoft Teams. Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando estiverem des&#39;no mesmo local. Os colaboradores remotos podem inserir imagens de referência, esquemáticos e outras informações úteis que o técnico&#39;o espaço físico de forma que ele possa se referir ao esquema enquanto trabalha com as cabeças de trabalho e as mãos do HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Neste guia, você:

Preparar:

> [!div class="checklist"]
> - [Saiba mais sobre os conceitos básicos de infraestrutura para dispositivos do HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Saiba mais sobre o Azure AD e configure um se você não&#39;o tiver.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Saiba mais sobre o gerenciamento de identidade e como configurar melhor as contas do Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Saiba mais sobre o MDM e configure-o com o Intune se você não&#39;t já tiver um pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Saiba mais sobre os requisitos de rede do auxílio remoto.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para se conectar aos recursos organizacionais](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurar:

> [!div class="checklist"]
> - [Como criar usuários e grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Como configurar o registro automático no Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Como atribuir suas licenças de aplicativo.](hololens2-cloud-connected-configure.md#application-licenses)

Implantar:

> [!div class="checklist"]
> - [Configure seu HoloLens 2 e valide o registro.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Validar você pode fazer uma chamada de assistência remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Manter:

> [!div class="checklist"]
> - [Como atualizar a assistência remota usando o aplicativo Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Fazendo um plano de suporte.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plano de desenvolvimento.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem – Preparar](hololens2-cloud-connected-prepare.md)

