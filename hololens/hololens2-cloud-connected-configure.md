---
title: Guia de implantação – Implantação HoloLens 2 conectada à nuvem em escala com o Remote Assist – Configurar
description: Saiba como configurar configurações para registrar dispositivos HoloLens em uma rede conectada à nuvem em escala com o Remote Assist.
keywords: HoloLens, gerenciamento, nuvem conectada, Assistência Remota, AAD, Azure AD, MDM, Dispositivo móvel Gerenciamento de Dispositivos
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031990"
---
# <a name="configure---cloud-connected-guide"></a>Configurar – Guia conectado à nuvem

Nesta seção do guia, vamos&#39;sobre como configurar o Registro Automático para seu locatário e como aplicar licenças para o Intune e o Remote Assist.

## <a name="azure-users-and-groups"></a>Usuários e grupos do Azure

O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças. Para validar esse fluxo de implantação e poder fazer uma chamada de Assistência Remota de um usuário para outro,&#39;precisará de duas contas de usuário.

Podemos fazer um único grupo de usuários com a finalidade de atribuir licenças. Podemos unir os dois usuários ao mesmo grupo e aplicar uma licença para o Intune e o Remote Assist a esse grupo.

Se você ainda&#39;tem acesso a duas contas do Azure AD em um grupo de usuários que você pode usar; Aqui estão os guias de início rápido para:

- [Como criar um usuário](/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar usuários a um grupo](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Adicionar usuários criados para criar grupo
- [Configurar o Azure AD para](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) permitir que um Grupo de Usuários inscreva dispositivos – Verifique se o novo grupo de usuários tem permissão para registrar dispositivos no Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Registro automático no HoloLens 2

Para ter uma experiência suave e perfeita, configurar o AADJ (Azure Active Directory Join) e o Registro Automático para o Intune para dispositivos HoloLens 2 é a melhor opção. Isso permitirá que os usuários inscrevem suas credenciais de logoff da organização durante o OOBE e se registrem automaticamente no Azure AD e registrem o dispositivo no MDM.

Usando o [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos selecionar serviços e navegar por algumas páginas até que possamos selecionar Obter uma Premium avaliação. Você pode observar que há Azure Active Directory Premium 1 e 2, para o Registro Automático P1 é suficiente. Podemos selecionar o Intune, selecionar o escopo do usuário para registro automático e selecionar o grupo criado anteriormente.

Para obter detalhes completos e etapas, leia o guia [sobre como habilitar o registro automático para o Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Licenças de aplicativo

Uma licença de aplicativo permite que um usuário instale aplicativos comprados pela empresa ou atualize de uma avaliação gratuita para a versão completa de um aplicativo. As licenças de aplicativo podem ser aplicadas a usuários, grupos de usuários ou grupos de dispositivos. Você&#39;precisar de licenças de Assistência Remota para que os usuários em sua organização usem o Remote Assist. Para a finalidade deste guia, atribuiremos licenças de Assistência Remota ao grupo de usuários que criamos acima em Usuários e Grupos do [Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Os requisitos para licenças podem ser diferentes dependendo se o usuário fará a chamada de Assistência Remota de um dispositivo ou se será um colaborador remoto do Microsoft Teams. Por padrão, as caixas de seleção Assistência Remota e Teams são marcadas. Para os fins deste guia, sugerimos deixar as caixas padrão marcadas.

1. Saiba mais sobre os diferentes [requisitos de licenciamento e produto por função.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Há alguns tipos diferentes de licenças de Assistência Remota, portanto, certifique-se de obter as corretas para suas necessidades.
2. Você&#39;precisará adquirir [a licença](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Aplique suas licenças](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) ao grupo.

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem – Implantar](hololens2-cloud-connected-deploy.md)