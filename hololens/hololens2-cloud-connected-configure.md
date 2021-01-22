---
title: Guia de Implantação – implantação do HoloLens 2 conectada à nuvem em escala com Assistência Remota - Configurar
description: Saiba como configurar configurações para registrar dispositivos HoloLens em uma rede conectada à nuvem em escala com a Assistência Remota.
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283882"
---
# Configurar - Guia conectado à nuvem

Nesta seção do guia, vamos&#39;como configurar o Registro Automático para seu locatário e como aplicar licenças para o Intune e a Assistência Remota.

## Usuários e grupos do Azure

O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças. Para validar esse fluxo de implantação e poder fazer uma chamada de Assistência Remota de um usuário para outro que você&#39;precisará de duas contas de usuário.

Podemos fazer um único grupo de usuários para atribuir licenças. Podemos unir os dois usuários ao mesmo grupo e aplicar uma licença para o Intune e a Assistência Remota a esse grupo.

Se você não&#39;tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; Aqui estão os guias de início rápido para:

- [Como criar um usuário](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar usuários a um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Adicionar usuários criados para criar um grupo
- [Configurar o Azure AD para](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) permitir que um Grupo de Usuários inscreva dispositivos – Certifique-se de que o novo grupo de usuários tenha permissão para registrar dispositivos no Azure AD

## Registro automático no HoloLens 2

Para ter uma experiência suave e perfeita, configurar o Azure Active Directory Join (AADJ) e o Registro Automático no Intune para dispositivos HoloLens 2 é a melhor opção. Isso permitirá que os usuários inscrevem suas credenciais de login da organização durante a OOBE e se registrem automaticamente no Azure AD e registrem o dispositivo no MDM.

Usando o [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos selecionar serviços e navegar em algumas páginas até podermos selecionar Obter uma avaliação Premium. Você pode notar que há o Azure Active Directory Premium 1 e 2, para o registro automático P1 é suficiente. Podemos selecionar o Intune, selecionar o escopo do usuário para o registro automático e selecionar o grupo que foi criado anteriormente.

Para obter detalhes completos e etapas, leia o guia [sobre como habilitar o registro automático para o Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## Licenças de aplicativo

Uma licença de aplicativo permite que um usuário instale aplicativos comprados pela empresa ou atualize de uma avaliação gratuita para a versão completa de um aplicativo. As licenças de aplicativo podem ser aplicadas a usuários, grupos de usuários ou grupos de dispositivos. Você&#39;de licenças de Assistência Remota para que os usuários em sua organização usem a Assistência Remota. Para os fins deste guia, atribuiremos licenças da Assistência Remota ao grupo de usuários que criamos acima em Usuários e Grupos do [Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Os requisitos para licenças podem ser diferentes dependendo se o usuário fará a chamada de Assistência Remota de um dispositivo ou se será um colaborador remoto do Microsoft Teams. Por padrão, as caixas de seleção Assistência Remota e Teams estão marcadas. Para os fins deste guia, sugerimos deixar as caixas padrão marcadas.

1. Saiba mais sobre os diferentes [requisitos de licenciamento e produto por função.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Existem alguns tipos diferentes de licenças da Assistência Remota, portanto, certifique-se de obter as corretas para suas necessidades.
2. Você&#39;precisará adquirir [a licença.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Aplique suas licenças](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) ao grupo.

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem - Implantar](hololens2-cloud-connected-deploy.md)