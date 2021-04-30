---
title: Visão geral do HoloLens 2 conectado à nuvem com o auxílio remoto
description: Saiba como registrar dispositivos do HoloLens 2 em uma rede conectada na nuvem usando o assistente remoto do Dynamics 365.
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308043"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guia de implantação – nuvem conectada no Cloud 2 com assistência remota – visão geral

Este guia ajuda os profissionais de ti a planejar e implantar dispositivos Microsoft HoloLens 2 em sua organização com o objetivo geral de ter esses dispositivos na nuvem conectados à sua organização com o auxílio remoto do Dynamics 365 pronto para uso. Tenha em mente que isso servirá como um modelo para implantações de prova de conceito em sua organização em vários casos de uso de HoloLens 2.

Durante o guia, abordaremos como registrar seus dispositivos em seu gerenciamento de dispositivo, aplicar licenças conforme necessário e validar que os usuários finais podem usar o assistência remota imediatamente após a configuração do dispositivo. Para fazer isso, veremos as importantes partes da infraestrutura necessária para a configuração e a execução – alcançando a implantação em escala com o HoloLens 2.

![Faixa conectada na nuvem](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a>Neste guia

Este guia tem o objetivo específico de configurar o auxílio remoto em sua organização em seus dispositivos de HoloLens. Abordaremos o necessidades necessário para atingir essa meta. Para manter o foco nessa meta, certas preparações e configurações serão previamente selecionadas para otimizar essa implantação ou para reduzir os itens necessários para a configuração. Você será informado dessas opções e poderá personalizar sua implantação com base nas suas necessidades de negócios.

Essa é uma configuração semelhante ao [cenário a: implantar em dispositivos do Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que é uma boa opção para muitas implantações de prova de conceito, que incluirá:

- As redes Wi-Fi normalmente são totalmente abertas na Internet e nos serviços de nuvem
- Ingresso no Azure AD com o registro automático do MDM--MDM (Intune) gerenciado
- Os usuários entram com sua própria conta corporativa (Azure AD)
  - Um ou vários usuários por dispositivo com suporte
- Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente aberto para quiosque de aplicativo único

![Cenário conectado à nuvem](./images/cloud-connected-guide-diagram.png)

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
> [Implantação conectada na nuvem-preparar](hololens2-cloud-connected-prepare.md)

