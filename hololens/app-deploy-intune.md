---
title: Portal do Intune e da empresa
description: Intune, gerenciamento de aplicativos, aplicativo, portal da empresa, portal
keywords: Intune, gerenciamento de aplicativos, aplicativo, portal da empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: 5fc369caa2e5e26c91c07f9270c3984177507dbd
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009459"
---
# Portal do Intune e da empresa

Com o gerenciamento de dispositivos móveis (MDM), você pode usar seus próprios aplicativos personalizados por meio do [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implantá-lo diretamente em seus dispositivos HoloLens. O Microsoft Intune é um serviço baseado em nuvem que enfoca o gerenciamento de dispositivos móveis (MDM) e o gerenciamento de aplicativo móvel (MAM). O Intune está incluído no[pacote Microsoft Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)e permite que os usuários sejam produtivos enquanto mantêm seus dados de organização protegidos. Para saber mais sobre o Intune, consulte [o que é o Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Configuração

1. Carregue um aplicativo para uma linha de negócios ou carregue um aplicativo personalizado para o seu locatário do Intune. Consulte também: [Gerenciamento de aplicativos corporativos](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Atribua seu aplicativo a um grupo](https://docs.microsoft.com/mem/intune/apps/apps-deploy). Com base no tipo de atribuição escolhido, você pode fazer com que o aplicativo seja entregue automaticamente ou disponível para ser imediatamente retirado se você tiver uma seleção de aplicativos. 

> [!NOTE] 
> Ao criar seu pacote Appx, certifique-se de incluir a arquitetura para o (s) dispositivo (s) em que você está implantando. O HoloLens 2 é ARM64 e HoloLens (1ª gen) é x86. Você pode incluir ambos em um único pacote Appx se planejar ter um ambiente de dispositivos mistos.

## Tipos de atribuição

Se você preferir que o aplicativo seja instalado automaticamente no dispositivo após o registro, selecione **obrigatório** para esse (s) grupo (s).
Se você preferir disponibilizar o aplicativo para download para aqueles registrados pelo portal da empresa, selecione **disponível para dispositivos registrados**.


## Experiência do usuário final

Depois de configurar a configuração no Intune, você estará pronto para que os usuários finais recebam seus aplicativos selecionados.

Siga estas etapas para obter automaticamente seu (s) aplicativo (s):
1. Registre seu dispositivo com seu locatário. 
2. Depois que o dispositivo concluir o registro, você deverá receber o aplicativo em seu dispositivo. 
3. Se você não estiver vendo o aplicativo imediatamente, acesse **configurações**  >  **contas**  >  **corporativas ou de estudante**  >  **napágina** informações e role para baixo para ver as informações sobre o status do aplicativo instalado.

Como acessar os aplicativos por meio do portal da empresa:
1. Abra o **menu iniciar** e selecione **Microsoft Store**. 
2. Procure **portal da empresa** e baixe o aplicativo.
3. Conecte-se à sua conta.
4. Selecione o aplicativo que você deseja receber e baixe-o.

> [!Tip]
> Saiba mais sobre [a instalação automática do portal da empresa e a](https://docs.microsoft.com/mem/intune/apps/company-portal-app) [implantação e gerenciamento de aplicativos no Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
