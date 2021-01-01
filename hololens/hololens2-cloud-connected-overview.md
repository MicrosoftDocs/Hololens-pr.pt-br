---
title: Guia de implantação – HoloLens conectado à nuvem 2 com assistência remota-visão geral
description: Registrar dispositivos HoloLens em uma rede conectada na nuvem
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
ms.openlocfilehash: 7d954347c7c274b844d436c0d6fc96e8bbc59f10
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253178"
---
# Guia de implantação – HoloLens conectado à nuvem 2 com assistência remota – visão geral

Este guia ajudará os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com o objetivo geral de ter esses dispositivos em nuvem conectada à sua organização com a assistência remota do Dynamics 365 pronta para uso. Tenha em mente que isso servirá como um modelo para implantações de prova de conceito em sua organização em diversos casos de uso do HoloLens 2.

Durante o guia, abordaremos como registrar seus dispositivos em seu gerenciamento de dispositivos, aplicar licenças conforme necessário e validar que os usuários finais podem usar imediatamente a assistência remota na instalação do dispositivo. Para isso, veremos as importantes partes da infraestrutura necessárias para a configuração e a execução: obtendo implantação em escala com o HoloLens 2.

## Neste guia

Este guia tem o objetivo específico de configurar o auxílio remoto dentro de sua organização em seus dispositivos HoloLens. Abordaremos a Necessities necessária para atingir essa meta. Para manter o foco nessa meta, certas preparações e configurações serão previamente selecionadas para otimizar essa implantação ou para reduzir os itens necessários para a configuração. Você será informado sobre essas opções e poderá personalizar a implantação com base nas necessidades da sua empresa.

Isso é uma configuração semelhante ao [cenário a: implantar em dispositivos de conexão em nuvem](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que é uma boa opção para várias implantações de comprovação de conceito, que inclui:

- As redes Wi-Fi geralmente são totalmente abertas para os serviços de nuvem e Internet
- Ingressar no Azure AD com o registro automático do MDM--gerenciamento de MDM (Intune)
- Os usuários entram com sua própria conta corporativa (Azure AD)
  - Suporte para um ou vários usuários por dispositivo
- Os níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do quiosque totalmente aberto para um único aplicativo.

![Cenário conectado na nuvem](./images/cloud-connected-deployment-chart.png)

Nenhuma outra restrição ou configuração de dispositivo será aplicada neste guia, mas incentivamos você a explorar essas opções após a conclusão.

## Saiba mais sobre a assistência remota

A assistência remota permite a manutenção e o reparo colaborativo, a inspeção remota, bem como o compartilhamento e o treinamento de conhecimento. Ao conectar pessoas em diferentes funções e locais, um técnico usando o recurso assistência remota pode se conectar com um colaborador remoto do Microsoft Teams. Elas podem combinar vídeos, capturas de tela e anotações para solucionar problemas em tempo real, mesmo quando não estiverem&#39;no mesmo local. Os colaboradores remotos podem inserir imagens de referência, esquemáticos e outras informações úteis que o técnico&#39;espaço físico para que ele possa se referir ao esquema enquanto estiver trabalhando e viva-se de mão livre no HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Neste guia, você vai:

Pare

> [!div class="checklist"]
> - [Saiba mais sobre os recursos básicos de infraestrutura para dispositivos HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Saiba mais sobre o Azure AD e configure um se não&#39;o tiver.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Saiba mais sobre o gerenciamento de identidades e como configurar melhor as contas do Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Saiba mais sobre o MDM e configure o Intune se você não&#39;já tiver um pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Saiba mais sobre os requisitos de rede da assistência remota.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para se conectar a recursos organizacionais](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configuração

> [!div class="checklist"]
> - [Como criar usuários e grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Como configurar o registro automático no Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Como atribuir suas licenças de aplicativo.](hololens2-cloud-connected-configure.md#application-licenses)

Implementar

> [!div class="checklist"]
> - [Configure seu HoloLens 2 e valide o registro.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Validar você pode fazer uma chamada de assistência remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Atualize

> [!div class="checklist"]
> - [Como atualizar a assistência remota usando o aplicativo da Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Como criar um plano de suporte.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plano de desenvolvimento.](hololens2-cloud-connected-maintain.md#development-plan)

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem-preparação](hololens2-cloud-connected-prepare.md)

