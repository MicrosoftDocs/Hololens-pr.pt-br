---
title: Guia de implantação – implantação do HoloLens 2 em nuvem conectada em escala com o auxílio remoto-manter
description: Mantenha-se atualizado com nossas dicas para manter e dar suporte a dispositivos de HoloLens em uma rede conectada em nuvem.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308227"
---
# <a name="maintain---cloud-connected-guide"></a>Maintain-guia conectado à nuvem

## <a name="updates"></a>Atualizações

A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.

Saiba como [gerenciar atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , incluindo dias agendados, hora agendada e definindo horas ativas no dispositivo para que ele seja atualizado fora do horário de trabalho.

O auxílio remoto é um aplicativo In-Box e pode ser atualizado por meio do aplicativo Microsoft Store. Para todos os aplicativos que são baixados por meio do Microsoft Store eles podem ser [atualizados por meio do](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) próprio aplicativo Microsoft Store manualmente.

## <a name="support-plan"></a>Plano de suporte

Um plano de suporte é uma excelente coisa a ter em vigor. Ter alguém ou um grupo treinado na solução de problemas do processo de registro em dispositivos HoloLens e também o uso geral do dispositivo HoloLens em sua organização é útil. Para permitir que os usuários tenham a resolução mais rápida de seus problemas, sugerimos que o processo de escalonamento seja manipulado de maneira semelhante a esta ordem:

1. Seu suporte técnico.
2. Sua equipe de especialistas em HoloLens
3. [Documentos](https://docs.microsoft.com/hololens/)  /  do HoloLens [Documentos de solução de problemas do HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contatar o suporte](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plano de desenvolvimento

Com seu dispositivo registrado com êxito, você agora está preparado para implantar aplicativos de linha de negócios (aplicativos LOB) em seus dispositivos. Esses são aplicativos personalizados criados para a sua organização&#39;s necessidades.

Se você já tiver um aplicativo de linha de negócios, você&#39;pronto para [implantar seu aplicativo por meio do MDM](https://docs.microsoft.com/hololens/app-deploy-intune). Se você&#39;d preferir um método diferente, examine a [visão geral da implantação do aplicativo para o HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para saber mais métodos de implantação de seu aplicativo LOB em seus dispositivos.

Se você&#39;ainda criar seu próprio aplicativo LOB ou ainda estiver no processo de criação, examine nossos documentos de desenvolvimento de realidade misturada para [começar a projetar e criar um protótipo](https://docs.microsoft.com/windows/mixed-reality/design/design) ou aprender os conceitos básicos para começar a [usar o desenvolvimento de realidade misturada.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Gerenciamento de Dispositivo 

Embora este guia tenha falado sobre a configuração do MDM (gerenciamento de dispositivo móvel), ele não foi empregado para aplicar restrições de dispositivo ou as políticas foram aplicadas a dispositivos. O gerenciamento de dispositivos pode ser usado para permitir o acesso enviando certificados por Push ou restringir o acesso com uma variedade de restrições de dispositivo. 

Em muitos casos, os dispositivos podem ter restrições de conectividade, como Bluetooth, VPN, USB ou até mesmo desativar o acesso à câmera ou ao microfone. Se qualquer um desses interesses, incentivamos você a ler nossa [página de restrições de dispositivo comum](hololens-common-device-restrictions.md).

Há outras restrições de dispositivo mais complexas que você pode usar. Como:

- Limitar as páginas que podem ser exibidas no aplicativo de configurações usando o [SettingsPageVisibility](settings-uri-list.md), permitindo que os usuários acessem apenas as configurações que precisam para se ajustar, como alterar sua conexão de Wi-Fi.
- Use o [modo de quiosque](hololens-kiosk.md) para limitar a interface do usuário apresentada aos usuários em um dispositivo. Você pode definir quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada. Os quiosques também podem apresentar experiências diferentes a usuários diferentes.  
- [Controle de aplicativo do Windows (WDAC)](windows-defender-application-control-wdac.md) para impedir que aplicativos ou processos específicos sejam iniciados inteiramente.

Se você quiser saber mais sobre métodos mais diferentes de gerenciamento de dispositivos ou restrições de dispositivos, siga a próxima etapa e leia nossa visão geral do gerenciamento de dispositivos.

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Leia a visão geral de gerenciamento de CSPs e de dispositivos](hololens-csp-policy-overview.md)