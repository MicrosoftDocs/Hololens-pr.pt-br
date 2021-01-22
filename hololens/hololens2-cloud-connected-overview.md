---
title: Visão geral do HoloLens 2 conectado à nuvem com Assistência Remota
description: Saiba como registrar dispositivos do HoloLens 2 em uma rede conectada à nuvem usando a Assistência Remota do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.openlocfilehash: 835b4be101b665d2b86c2170a65c04697686e403
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283072"
---
# Guia de Implantação – HoloLens 2 conectado à nuvem com Assistência Remota – Visão geral

Este guia ajuda os profissionais de TI a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com o objetivo geral de ter esses dispositivos conectados à nuvem em sua organização com a Assistência Remota do Dynamics 365 pronta para uso. Lembre-se de que isso servirá como modelo para implantações de prova de conceito em sua organização em uma variedade de casos de uso do HoloLens 2.

Durante o guia, vamos falar sobre como registrar seus dispositivos no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na configuração do dispositivo. Para fazer isso, vamos passar por cima das partes importantes da infraestrutura necessária para configurar e executar – alcançando a implantação em escala com o HoloLens 2.

## Neste guia

Este guia tem o objetivo específico de configurar a Assistência Remota dentro de sua organização em seus dispositivos HoloLens. Vamos abranger as necessidades necessárias para atingir essa meta. Para manter o foco nesse objetivo, determinadas configurações e preparação serão pré-selecionadas para otimizar essa implantação ou reduzir os itens necessários à configuração. Você será informado dessas opções e poderá personalizar sua implantação com base em suas necessidades de negócios.

Esta é uma configuração semelhante ao Cenário [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implantar em dispositivos conectados à nuvem, que é uma boa opção para muitas implantações de Prova de Conceito, que incluirão:

- Wi-Fi redes são normalmente totalmente abertas para os serviços de Nuvem e Internet
- Ingressar no Azure AD com o registro automático do MDM – MDM (Intune) gerenciado
- Os usuários podem entrar com sua própria conta corporativa (Azure AD)
  - Um ou vários usuários por dispositivo com suporte
- Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto a Quiosque de Aplicativo Único

![Cenário conectado à nuvem](./images/cloud-connected-guide-diagram.png)

Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, no entanto, recomendamos que você explore essas opções após a conclusão.

## Saiba mais sobre a Assistência Remota

A Assistência Remota permite manutenção e reparo colaborativos, inspeção remota, bem como compartilhamento e treinamento de conhecimento. Conectando pessoas em diferentes funções e locais, um técnico que usa a Assistência Remota pode se conectar a um colaborador remoto no Microsoft Teams. Eles podem combinar vídeos, capturas de tela e anotações para resolver problemas em tempo real, mesmo quando&#39;estão no mesmo local. Os colaboradores remotos podem inserir imagens de referência, esquemas e outras informações úteis que o técnico&#39;no espaço físico para que possam se referir ao esquema enquanto trabalham de cabeça para cima e sem mãos no HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Neste guia, você irá:

Prepare:

> [!div class="checklist"]
> - [Saiba mais sobre as noções básicas de infraestrutura para dispositivos HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Saiba mais sobre o Azure AD e configurar um caso&#39;não o tenha.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Saiba mais sobre o gerenciamento de identidades e como configurar melhor as contas do Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Saiba mais sobre o MDM e prepare-se com o Intune&#39;já tiver um pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Saiba mais sobre os requisitos de rede da Assistência Remota.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para se conectar a recursos organizacionais](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configure:

> [!div class="checklist"]
> - [Como criar Usuários e Grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Como configurar o registro automático no Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Como atribuir suas licenças de aplicativo.](hololens2-cloud-connected-configure.md#application-licenses)

Implantar:

> [!div class="checklist"]
> - [Configurar seu HoloLens 2 e validar o registro.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valide se você pode fazer uma chamada de Assistência Remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mantenha:

> [!div class="checklist"]
> - [Como atualizar a Assistência Remota usando o aplicativo da Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Como criar um plano de suporte.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plano de desenvolvimento.](hololens2-cloud-connected-maintain.md#development-plan)

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem - Preparar](hololens2-cloud-connected-prepare.md)

