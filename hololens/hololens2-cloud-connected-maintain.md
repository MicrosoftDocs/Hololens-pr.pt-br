---
title: Guia de Implantação – implantação do HoloLens 2 conectada à nuvem em escala com Assistência Remota - Manutenção
description: Mantenha-se atualizado com nossas dicas para manter e dar suporte a dispositivos HoloLens em uma rede conectada à nuvem.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283892"
---
# Manutenção - Guia conectado à nuvem

## Atualizações

A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.

Saiba como gerenciar as atualizações do [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) incluindo dias agendados, horário agendado e configuração do horário ativo no dispositivo para que ele seja atualizado fora do horário de trabalho.

A Assistência Remota é um In-Box e pode ser atualizada por meio do aplicativo da Microsoft Store. Para todos os aplicativos baixados por meio da Microsoft Store, eles podem ser atualizados manualmente por meio do [próprio aplicativo da Microsoft Store.](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps)

## Plano de Suporte

Um plano de suporte é uma excelente coisa a ser realizada. Ter alguém ou um grupo treinado para solucionar problemas do processo de inscrição em dispositivos HoloLens e também o uso geral do dispositivo HoloLens em sua organização é útil. Para permitir que os usuários tenham a resolução mais rápida dos problemas, sugerimos que o processo de escalonamento seja tratado de maneira semelhante a esta ordem:

1. Seu suporte técnico.
2. Sua equipe de especialistas do HoloLens
3. [Documentos do HoloLens](https://docs.microsoft.com/hololens/)  /  [Documentos de solução de problemas do HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contate o Suporte](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Plano de desenvolvimento

Com seu dispositivo registrado com êxito, agora você está preparado para implantar aplicativos de linha de negócios (aplicativos LOB) em seus dispositivos. Esses são aplicativos personalizados criado para a sua&#39;necessidades.

Se você já tiver um aplicativo de linha de negócios,&#39;está pronto para implantar seu [aplicativo por meio do MDM.](https://docs.microsoft.com/hololens/app-deploy-intune) Se você&#39;um método diferente, revise a visão geral da implantação do aplicativo para [o HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para saber mais métodos de implantação do aplicativo LOB em seus dispositivos.

Se você&#39;criou seu próprio aplicativo LOB ou ainda está em processo de criação, revise nossos documentos de desenvolvimento de realidade misturada para começar a [projetar](https://docs.microsoft.com/windows/mixed-reality/design/design) e criar protótipos ou aprender os principais conceitos para começar com o desenvolvimento de realidade [misturada.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## Gerenciamento de Dispositivo 

Embora este guia tenha falado sobre como configurar o Gerenciamento de Dispositivo Móvel (MDM), ele não foi empregado para aplicar restrições de dispositivo ou políticas foram aplicadas a dispositivos. O gerenciamento de dispositivos pode ser usado para permitir o acesso por meio de certificados por solicitação ou restringir o acesso com uma variedade de restrições de dispositivo. 

Em muitos casos, os dispositivos podem ter restrições de conectividade, como Bluetooth, VPN, USB ou até mesmo desligar o acesso à câmera ou microfone. Se qualquer um desses interesses, recomendamos que você leia nossa página [de restrições de dispositivos comuns.](hololens-common-device-restrictions.md)

Há outras restrições de dispositivo mais complexas que você pode usar. Como:

- Limitar as páginas que podem ser exibidas no aplicativo Configurações usando [SettingsPageVisibility](settings-uri-list.md), permitindo que os usuários acessem apenas as configurações que precisam ajustar, como alterar sua conexão Wi-Fi usuário.
- Use [o modo quiosque](hololens-kiosk.md) para limitar a interface do usuário apresentada aos usuários em um dispositivo. Você pode definir Quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada. Os quiosques também podem apresentar experiências diferentes para diferentes usuários.  
- [O Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) para impedir que aplicativos ou processos específicos seja totalmente lançados.

Se você quiser saber mais sobre métodos mais diferentes de gerenciamento de dispositivos ou restrições de dispositivos, então, dê a próxima etapa e leia nossa Visão Geral do Gerenciamento de Dispositivos.

## Próximas etapas

> [!div class="nextstepaction"]
> [Ler a visão geral de gerenciamento de dispositivos e CSPs](hololens-csp-policy-overview.md)