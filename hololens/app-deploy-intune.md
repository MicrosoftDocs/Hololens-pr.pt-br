---
title: Intune e Portal da Empresa
description: Saiba como configurar, atribuir e criar uma experiência de usuário confortável com o Intune, o gerenciamento de dispositivo móvel e o portal da empresa.
keywords: intune, gerenciamento de aplicativos, aplicativo, portal da empresa, portal, hololens
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635493"
---
# <a name="intune--company-portal"></a>Intune e Portal da Empresa

Com o MDM (Mobile Gerenciamento de Dispositivos), você pode usar seus próprios aplicativos personalizados por meio [do Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) para implantá-lo diretamente em seus HoloLens dispositivos. O Microsoft Intune é um serviço baseado em nuvem que se concentra no MDM (gerenciamento de dispositivo móvel) e no MAM (gerenciamento de aplicativo móvel). O Intune está incluído no [pacote de EMS (Enterprise Mobility + Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) e permite que os usuários sejam produtivos, garantindo a proteção dos dados da organização. Para saber mais sobre o Intune, leia [O que é o Intune.](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Instalação

1. Upload um aplicativo em uma Linha de Negócios ou carregar um aplicativo personalizado em seu locatário do Intune. Confira também: gerenciamento [Enterprise aplicativo.](/windows/client-management/mdm/enterprise-app-management)

2. [Atribua seu aplicativo a um grupo](/mem/intune/apps/apps-deploy). Com base no tipo de atribuição escolhido, o aplicativo poderá ser entregue automaticamente ou disponível para ser prontamente retirado se você tiver uma seleção de aplicativos.

> [!NOTE]
> Ao criar seu pacote appx, certifique-se de incluir a arquitetura para os dispositivos nos quais você está implantando. HoloLens 2 é ARM64 e HoloLens (1ª geração) é x86. Você pode incluir ambos em um único pacote appx se planeja ter um ambiente de dispositivos mistos.

## <a name="assignment-types"></a>Tipos de Atribuição

Para que seu aplicativo seja instalado automaticamente no dispositivo após o registro, você deve selecionar Obrigatório **para** esse(s) grupo(s).
Para disponibilizar seu aplicativo para download em dispositivos inscritos por meio do portal da empresa, selecione Disponível **para dispositivos inscritos.**

## <a name="end-user-experience"></a>Experiência do usuário final

Depois de configurar a configuração no Intune, você estará pronto para que os usuários finais recebam seus aplicativos selecionados.

Siga estas etapas para obter automaticamente seus aplicativos:

1. Registrar seu dispositivo com seu locatário.
2. Depois que o dispositivo tiver concluído o registro, você deverá receber o aplicativo em seu dispositivo.
3. Se você não estiver vendo seu aplicativo imediatamente, vá para Contas do Configurações Trabalho ou Escola suas informações de conta e role para baixo para ver informações sobre o  >    >    >   status do aplicativo instalado.

Como chegar aos aplicativos por meio do Portal da Empresa:

1. Abra o **Menu Iniciar** e selecione **Microsoft Store**.
2. **Pesquise Portal da Empresa** e baixe o aplicativo.
3. Entre em sua conta.
4. Selecione o aplicativo que você deseja receber e baixe-o.

> [!Tip]
> Saiba mais sobre [como instalar automaticamente o Portal da Empresa](/mem/intune/apps/company-portal-app) e implantar e gerenciar [aplicativos no Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
