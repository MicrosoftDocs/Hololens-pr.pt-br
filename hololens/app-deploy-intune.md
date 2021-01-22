---
title: Intune e Portal da Empresa
description: Saiba como configurar, atribuir e criar uma experiência de usuário confortável com o Intune, o gerenciamento de dispositivos móveis e o portal da empresa.
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283712"
---
# Portal do Intune e da empresa

Com o Gerenciamento de Dispositivo Móvel (MDM), você pode usar seus próprios aplicativos personalizados por meio do [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implantá-lo diretamente em seus dispositivos HoloLens. O Microsoft Intune é um serviço baseado em nuvem que se concentra no gerenciamento de dispositivo móvel (MDM) e no gerenciamento de aplicativos móveis (MAM). O Intune está incluído no pacote [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)da Microsoft e permite que os usuários sejam produtivos enquanto mantêm os dados da sua organização protegidos. Para saber mais sobre o Intune, leia [o que é o Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## Configuração

1. Carregue um aplicativo para uma linha de negócios ou carregue um aplicativo personalizado em seu locatário do Intune. Consulte também: [Gerenciamento de aplicativos corporativos.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)

2. [Atribua seu aplicativo a um grupo.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) Com base no tipo de atribuição escolhido, o aplicativo pode ser entregue automaticamente ou disponível para ser prontamente retirado se você tiver uma seleção de aplicativos.

> [!NOTE]
> Ao criar seu pacote appx, certifique-se de levar em conta a inclusão da arquitetura para os dispositivos em que você está implantando. O HoloLens 2 é ARM64 e o HoloLens (1ª geração) é x86. Você pode incluir ambos em um único pacote appx se planeja ter um ambiente de dispositivos mistos.

## Tipos de atribuição

Para que seu aplicativo seja instalado automaticamente no dispositivo após o registro, você deve selecionar Obrigatório **para** esse(s) grupo(s).
Para disponibilizar seu aplicativo para download em dispositivos inscritos por meio do portal da empresa, selecione **Disponível para dispositivos inscritos.**

## End-User experiência

Depois de definir a configuração no Intune, você estará pronto para que os usuários finais recebam os aplicativos selecionados.

Siga estas etapas para obter automaticamente seu(s) aplicativo(s):

1. Registrar seu dispositivo com seu locatário.
2. Depois que seu dispositivo tiver concluído o registro, você deverá receber o aplicativo em seu dispositivo.
3. Se você não estiver vendo seu **** aplicativo imediatamente, vá para Configurações Contas Funcionam ou Escola suas informações de conta e role para baixo para ver informações sobre o  >  ****  >  ****  >  ** status do aplicativo instalado.

Como obter aplicativos por meio do Portal da Empresa:

1. Abra o **Menu Iniciar** e selecione **Microsoft Store.**
2. **Pesquise o Portal** da Empresa e baixe o aplicativo.
3. Entre em sua conta.
4. Selecione o aplicativo que você deseja receber e baixe-o.

> [!Tip]
> Saiba mais sobre [como instalar automaticamente o Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) da Empresa e implantar e gerenciar [aplicativos no Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
