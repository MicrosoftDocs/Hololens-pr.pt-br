---
title: Guia de implantação – implantação do HoloLens 2 em nuvem conectada em escala com o auxílio remoto – configurar
description: Saiba como configurar as configurações para registrar dispositivos HoloLens em uma rede conectada na nuvem em escala com o auxílio remoto.
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308103"
---
# <a name="configure---cloud-connected-guide"></a>Configurar-guia conectado à nuvem

Nesta seção do guia,&#39;mos como configurar o registro automático para seu locatário e como aplicar licenças para o Intune e o auxiliar remoto.

## <a name="azure-users-and-groups"></a>Usuários e grupos do Azure

O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças. Para validar esse fluxo de implantação e ser capaz de fazer uma chamada de assistência remota de um usuário para outro, você&#39;precisará de duas contas de usuário.

Podemos criar um único grupo de usuários com a finalidade de atribuir licenças. Podemos unir os dois usuários ao mesmo grupo e aplicar uma licença para o Intune e assistência remota a esse grupo.

Se você Don&#39;t já tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; Aqui estão os guias de início rápido para:

- [Como criar um usuário](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar usuários a um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – adicionar usuários criados para criar grupo
- [Configurar o Azure ad para permitir que um grupo de usuários ingresse em dispositivos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Verifique se o novo grupo de usuários tem permissão para registrar dispositivos no Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Registro automático no HoloLens 2

Para ter uma experiência tranqüila e perfeita, configurar Azure Active Directory Join (AADJ) e o registro automático para o Intune para dispositivos do HoloLens 2 é a melhor opção. Isso permitirá que os usuários insiram suas credenciais de logon da organização durante o OOBE e se registrem automaticamente com o Azure AD e registrem o dispositivo no MDM.

Usando [o Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos selecionar serviços e navegar por algumas páginas até que possamos selecionar obter uma avaliação Premium. Você pode notar que há Azure Active Directory Premium 1 e 2, para o registro automático P1 é suficiente. Podemos selecionar o Intune e selecionar o escopo do usuário para registro automático e selecionar o grupo que foi criado anteriormente.

Para obter detalhes completos e etapas, leia o guia sobre [como habilitar o registro automático para o Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="application-licenses"></a>Licenças de aplicativos

Uma licença de aplicativo permite que um usuário instale aplicativos comprados pela empresa ou atualize de uma avaliação gratuita para a versão completa de um aplicativo. As licenças de aplicativo podem ser aplicadas a usuários, grupos de usuários ou grupos de dispositivos. Você&#39;que precisa de licenças de assistência remota para que os usuários em sua organização usem o auxílio remoto. Para o propósito deste guia, atribuíremos licenças de assistência remota ao grupo de usuários criado acima em [usuários e grupos do Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).

Os requisitos para licenças podem ser diferentes dependendo se o usuário estiver fazendo a chamada de assistência remota de um dispositivo ou for um colaborador remoto do Microsoft Teams. Por padrão, as caixas de seleção assistência remota e equipes são marcadas. Para os fins deste guia, sugerimos deixar as caixas padrão verificadas.

1. Saiba mais sobre os diferentes [requisitos de licenciamento e produto por função](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Há alguns tipos diferentes de licenças de assistência remota, portanto, certifique-se de obter os corretos para suas necessidades.
2. Você&#39;precisa [adquirir a licença](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Aplique suas licenças](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) ao grupo.

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem – implantar](hololens2-cloud-connected-deploy.md)