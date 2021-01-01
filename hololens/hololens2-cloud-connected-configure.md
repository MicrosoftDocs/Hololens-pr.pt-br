---
title: Guia de implantação – implantação do HoloLens 2 conectado à nuvem em escala com assistência remota-configurar
description: Como configurar as configurações para registrar dispositivos do HoloLens em uma rede conectada na nuvem
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
ms.openlocfilehash: 042a29fe436b21ca37a2fcd7921fc53d6a9686d5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253038"
---
# Configurar-guia conectado à nuvem

Nesta seção do guia,&#39;remos como configurar o registro automático para o seu locatário e como aplicar licenças para o Intune e para a assistência remota.

## Usuários e grupos do Azure

O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças. Para que você possa validar esse fluxo de implantação e fazer uma chamada de assistência remota de um usuário para outro, você precisará de duas contas de usuário do&#39;.

Podemos criar um único grupo de usuários com o objetivo de atribuir licenças. Podemos associar os dois usuários ao mesmo grupo e aplicar uma licença do Intune e assistência remota a esse grupo.

Se você não&#39;já tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; Estes são os guias de início rápido para:

- [Como criar um usuário](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar usuários a um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – adicionar usuários criados para criar grupo
- [Configurar o Azure ad para permitir que um grupo de usuários ingresse em dispositivos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – garanta que o novo grupo de usuários tenha permissão para registrar dispositivos no Azure AD

## Registro automático no HoloLens 2

Para ter uma experiência tranqüila e perfeita, configurar o Azure Active Directory Join (AADJ) e o registro automático para o Intune para dispositivos HoloLens 2 é como ir. Isso permitirá que os usuários insiram as credenciais de login da organização durante a OOBE e se registrem automaticamente com o Azure AD e registrem o dispositivo no MDM.

Usando [o Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos selecionar os serviços e navegar em algumas páginas até que possamos selecionar obter uma avaliação Premium. Você pode observar que há o Azure Active Directory Premium 1 e 2, para o registro automático P1 é suficiente. Podemos selecionar o Intune e selecionar o escopo do usuário para registro automático e selecionar o grupo que foi criado anteriormente.

Para obter detalhes completos e etapas, leia o guia sobre [como habilitar o registro automático do Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## Licenças de aplicativos

Uma licença de aplicativo permite que um usuário instale aplicativos comprados pela empresa ou atualize de uma avaliação gratuita para a versão completa de um aplicativo. As licenças do aplicativo podem ser aplicadas a usuários, grupos de usuários ou grupos de dispositivos. Você&#39;precisará de licenças de assistência remota para que os usuários da sua organização usem a assistência remota. Para a finalidade deste guia, atribuiremos licenças de assistência remota ao grupo de usuários que criamos acima em [usuários e grupos do Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).

Os requisitos para licenças podem ser diferentes dependendo se o usuário estiver executando a chamada de assistência remota de um dispositivo ou será um colaborador remoto do Microsoft Teams. Por padrão, as caixas de seleção assistência remota e equipes estão marcadas. Para os fins deste guia, sugerimos deixar as caixas padrão verificadas.

1. Saiba mais sobre as diferentes [exigências de licenciamento e produtos por função](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Há alguns tipos diferentes de licenças de assistência remota, portanto, lembre-se de ter os corretos para atender às suas necessidades.
2. Você&#39;precisa [adquirir a licença](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Aplique suas licenças](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) ao grupo.

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem-implantação](hololens2-cloud-connected-deploy.md)