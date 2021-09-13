---
title: Guia de implantação – Implantação HoloLens 2 conectada à nuvem em escala com o Remote Assist – Maintain
description: Mantenha-se atualizado com nossas dicas para manter e dar suporte HoloLens dispositivos em uma rede conectada à nuvem.
keywords: HoloLens, gerenciamento, nuvem conectada, Assistência Remota, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031988"
---
# <a name="maintain---cloud-connected-guide"></a>Manter – Guia conectado à nuvem

## <a name="updates"></a>Atualizações

A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.

Saiba como gerenciar [atualizações HoloLens,](/hololens/hololens-updates) incluindo dias agendados, hora agendada e configuração de horas ativas no dispositivo para que ele seja atualizado fora do horário comercial.

O Remote Assist é um In-Box e pode ser atualizado por meio do Microsoft Store aplicativo. Para todos os aplicativos baixados por meio do Microsoft Store eles podem ser atualizados por meio [do](/hololens/holographic-store-apps#update-apps) Microsoft Store aplicativo em si manualmente.

## <a name="support-plan"></a>Plano de suporte

Um plano de suporte é uma coisa excelente para ter em ação. Ter alguém ou um grupo treinado para solucionar problemas do processo de registro em dispositivos HoloLens e também o uso geral do dispositivo HoloLens em sua organização é útil. Para permitir que os usuários tenham a resolução mais rápida dos problemas, sugerimos que o processo de escalonamento seja tratado de maneira semelhante a esta ordem:

1. Seu suporte técnico.
2. Sua equipe HoloLens Especialista em HoloLens
3. [HoloLens Docs](/hololens/)  /  [HoloLens documentação de solução de problemas](/hololens/hololens-troubleshooting)
4. [Entrar em contato com o suporte](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plano de desenvolvimento

Com o dispositivo registrado com êxito, agora você está preparado para implantar aplicativos de Linha de Negócios (aplicativos LOB) em seus dispositivos. Esses são aplicativos personalizados criado para suas necessidades&#39;organização.

Se você já tiver um aplicativo de linha de negócios,&#39;estará pronto para implantar seu [aplicativo por meio do MDM](/hololens/app-deploy-intune). Se você&#39;preferir um método diferente, revise a visão geral da implantação do aplicativo para [HoloLens 2](/hololens/app-deploy-overview) para saber mais sobre os métodos de implantação do aplicativo LOB em seus dispositivos.

Se você ainda&#39;criar seu próprio aplicativo LOB ou ainda estiver no processo de criação, revise nossos documentos de desenvolvimento de realidade misturada para começar a [projetar](/windows/mixed-reality/design/design) e criar protótipos ou aprender os principais conceitos para começar a desenvolver realidade [misturada.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Gerenciamento de Dispositivo 

Embora este guia tenha falado sobre como configurar o MDM (Mobile Gerenciamento de Dispositivos), ele não foi empregado para aplicar restrições de dispositivo ou políticas foram aplicadas aos dispositivos. O gerenciamento de dispositivos pode ser usado para permitir o acesso por meio do endossar certificados ou restringir o acesso com uma variedade de restrições de dispositivo. 

Em muitos casos, os dispositivos podem ter restrições de conectividade, como Bluetooth, VPN, USB ou até mesmo desligar o acesso à câmera ou ao microfone. Se qualquer um desses interesses você então incentivamos você a ler nossa [página de restrições de dispositivo comuns](hololens-common-device-restrictions.md).

Há outras restrições de dispositivo mais complexas que você pode usar. Como:

- Limitando as páginas que podem ser exibidas no aplicativo Configurações usando [SettingsPageVisibility](settings-uri-list.md), permitindo que os usuários acessem apenas as configurações de que precisam ajustar, como alterar a conexão Wi-Fi configuração.
- Use [o modo quiosque](hololens-kiosk.md) para limitar a interface do usuário apresentada aos usuários em um dispositivo. Você pode definir Quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada. Os quiosques também podem apresentar experiências diferentes para usuários diferentes.  
- [Windows WDAC (Controle de Aplicativos)](windows-defender-application-control-wdac.md) para impedir que aplicativos ou processos específicos seja totalmente lançados.

Se você quiser saber mais sobre métodos mais diferentes de gerenciamento de dispositivos ou restrições de dispositivo, dê a próxima etapa e leia nossa visão geral Gerenciamento de Dispositivos segurança.

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Leia os CSPs e Gerenciamento de Dispositivos Visão geral](hololens-csp-policy-overview.md)