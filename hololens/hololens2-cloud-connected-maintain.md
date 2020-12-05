---
title: Guia de implantação – implantação do HoloLens 2 conectado à nuvem em escala com assistência remota-manter
description: Dicas para manter dispositivos HoloLens em uma rede conectada na nuvem
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
ms.openlocfilehash: beee64159415c0635812463f81c0b5565e44e4a8
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196252"
---
# Maintain-guia conectado à nuvem

## Atualizações

A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.

Saiba como [gerenciar as atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , incluindo os dias agendados, o horário programado e a configuração de horas ativas no dispositivo para que ele seja atualizado fora do horário de trabalho.

O auxílio remoto é um aplicativo In-Box e pode ser atualizado por meio do aplicativo da Microsoft Store. Para todos os aplicativos que são baixados por meio da Microsoft Store, eles podem ser [atualizados manualmente por meio do aplicativo da Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) .

## Plano de Suporte

Um plano de suporte é uma coisa excelente para se ter em vigor. Ter alguém ou um grupo treinado para solucionar o problema do processo de inscrição em dispositivos HoloLens e também o uso geral do dispositivo HoloLens em sua organização é útil. Para permitir que os usuários tenham a solução mais rápida de seus problemas, sugerimos que o processo de escalonamento seja manipulado de maneira semelhante a isto:

1. O suporte técnico.
2. Sua equipe de especialistas do HoloLens
3. [Documentos](https://docs.microsoft.com/hololens/)  /  do HoloLens [Documentos de solução de problemas do HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contate o Suporte](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Plano de desenvolvimento

Com o seu dispositivo registrado com êxito, você agora está preparado para implantar aplicativos de linha de negócios (aplicativos LOB) em seus dispositivos. Estes são aplicativos personalizados criados para sua organização&#39;s necessidades.

Se você já tiver um aplicativo de linha de negócios,&#39;pronto para [implantar o aplicativo por meio do MDM](https://docs.microsoft.com/hololens/app-deploy-intune). Se você&#39;d prefere um método diferente, examine a [visão geral de implantação do aplicativo para o HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para saber mais métodos de implantação do seu aplicativo LOB em seus dispositivos.

Se você&#39;ainda criar seu próprio aplicativo LOB ou ainda estiver em processo de criação, analise nossos documentos de desenvolvimento de realidade misturados para [começar a projetar e criar protótipos](https://docs.microsoft.com/windows/mixed-reality/design/design) ou aprender os conceitos básicos para começar a criar um [desenvolvimento de realidade misturada.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## Gerenciamento de Dispositivo 

Neste guia, falamos sobre a configuração do MDM (gerenciamento de dispositivo móvel) que não foi empregado para aplicar restrições de dispositivo ou políticas foram aplicadas a dispositivos. O gerenciamento de dispositivos pode ser usado para permitir o acesso por push de certificados ou restringir o acesso a várias restrições de dispositivo. 

Em muitos casos, os dispositivos podem ter restrições de conectividade como Bluetooth, VPN, USB ou até mesmo desativar o acesso à câmera ou ao microfone. Se qualquer um desses juros, recomendamos que você leia nossa [página de restrições de dispositivo comum](hololens-common-device-restrictions.md).

Há outras restrições de dispositivo mais complexas que você pode usar. Como:

- Limitar as páginas que podem ser visualizadas no aplicativo configurações usando o [SettingsPageVisibility](settings-uri-list.md), permitindo que os usuários acessem somente as configurações necessárias para ajustar tais como alterar a conexão do Wi-Fi.
- Use o [modo de quiosque](hololens-kiosk.md) para limitar a interface do usuário apresentada aos usuários em um dispositivo. Você pode definir quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada. Os quiosques também podem apresentar experiências diferentes para usuários diferentes.  
- [Controle de aplicativos do Windows (WDAC)](windows-defender-application-control-wdac.md) para impedir que aplicativos ou processos específicos sejam iniciados completamente.

Se quiser saber mais sobre os métodos mais diferentes de gerenciamento de dispositivos ou restrições de dispositivo, siga a próxima etapa e leia a visão geral do gerenciamento de dispositivos.

## Próximas etapas

> [!div class="nextstepaction"]
> [Leia a visão geral de gerenciamento de dispositivos e CSPs](hololens-csp-policy-overview.md)