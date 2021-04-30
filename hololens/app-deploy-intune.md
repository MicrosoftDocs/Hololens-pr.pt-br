---
title: Intune e Portal da Empresa
description: Saiba como configurar, atribuir e criar uma experiência de usuário confortável com o Intune, o gerenciamento de dispositivos móveis e o portal da empresa.
keywords: Intune, gerenciamento de aplicativos, aplicativo, portal da empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308216"
---
# <a name="intune--company-portal"></a>& do Intune Portal da Empresa

Com o MDM (gerenciamento de dispositivo móvel), você pode usar seus próprios aplicativos personalizados por meio do [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implantá-lo diretamente em seus dispositivos de HoloLens. O Microsoft Intune é um serviço baseado em nuvem que se concentra no MDM (gerenciamento de dispositivo móvel) e no MAM (gerenciamento de aplicativo móvel). O Intune está incluído no [pacote de EMS (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) e permite que os usuários sejam produtivos, garantindo a proteção dos dados da organização. Para saber mais sobre o Intune, leia [o que é o Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## <a name="setup"></a>Instalação

1. Carregar um aplicativo para uma linha de negócios ou carregar um aplicativo personalizado para seu locatário do Intune. Consulte também: [Gerenciamento de aplicativos empresariais](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Atribua seu aplicativo a um grupo](https://docs.microsoft.com/mem/intune/apps/apps-deploy). Com base no tipo de atribuição escolhido, o aplicativo pode ser entregue automaticamente ou disponível para ser imediatamente retirado se você tiver uma seleção de aplicativos.

> [!NOTE]
> Ao criar seu pacote Appx, certifique-se de incluir a arquitetura para os dispositivos nos quais você está implantando. O HoloLens 2 é ARM64 e o HoloLens (1º gen) é x86. Você pode incluir ambos em um único pacote Appx se planejar ter um ambiente de dispositivos mistos.

## <a name="assignment-types"></a>Tipos de Atribuição

Para que seu aplicativo seja instalado automaticamente no dispositivo após o registro, você deve selecionar **necessário** para esse grupo.
Para disponibilizar seu aplicativo para download em dispositivos registrados por meio do portal da empresa, selecione **disponível para dispositivos registrados**.

## <a name="end-user-experience"></a>Experiência do usuário final

Depois de configurar a configuração no Intune, você estará pronto para que os usuários finais recebam seus aplicativos selecionados.

Siga estas etapas para obter automaticamente seus aplicativos:

1. Registre seu dispositivo com seu locatário.
2. Depois que o dispositivo tiver concluído o registro, você deverá receber o aplicativo em seu dispositivo.
3. Se você não estiver vendo seu aplicativo imediatamente, vá para **configurações**  >  **contas**  >  **trabalho ou escola**  >  *suas* informações de conta e role para baixo para ver informações sobre o status do aplicativo instalado.

Como obter aplicativos por meio do Portal da Empresa:

1. Abra o **menu iniciar** e selecione **Microsoft Store**.
2. Pesquise **portal da empresa** e baixe o aplicativo.
3. Entre em sua conta.
4. Selecione o aplicativo que você deseja receber e baixe-o.

> [!Tip]
> Saiba mais sobre como [instalar automaticamente o portal da empresa](https://docs.microsoft.com/mem/intune/apps/company-portal-app) e [implantar e gerenciar aplicativos no Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
