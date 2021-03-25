---
title: Guia de Implantação – HoloLens 2 conectado corporativo com Guias do Dynamics 365 - Manter
description: Saiba como manter os dispositivos do HoloLens 2 em uma rede conectada corporativa com guias do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448500"
---
# <a name="maintain---corporate-connected-guide"></a>Maintain - Guia conectado corporativo

## <a name="update-hololens"></a>Atualizar o HoloLens

A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.

Um método popular de gerenciamento de atualizações é fazer um adiamento de recursos de 30 dias. Isso permite que os administradores atualizem e visualizem novos recursos, ganhando conhecimento em primeira mão e informando seu suporte sobre quaisquer novas alterações.

Saiba como gerenciar atualizações do [HoloLens](https://docs.microsoft.com/hololens/hololens-updates), incluindo dias agendados, horário agendado e definição de horários ativos no dispositivo, para que ele seja atualizado fora do horário comercial.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Como atualizar guias do Dynamics 365 (e outros aplicativos da loja)

Os Guias do Dynamics 365 são um In-Box e podem ser atualizados por meio do aplicativo da Microsoft Store. Para todos os aplicativos baixados por meio da Microsoft Store, eles podem ser atualizados manualmente por meio do próprio aplicativo [da Microsoft Store.](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps)

## <a name="how-to-update-lob-apps"></a>Como atualizar aplicativos LOB

Os aplicativos LOB podem ser atualizados da mesma forma que foram adicionados ao Intune. Os aplicativos podem ser atualizados no Intune carregando o novo aplicativo com um número de versão mais alto para a configuração do aplicativo existente. Quando o dispositivo é sincronizado com o Intune, ele observará que há uma versão mais recente do aplicativo e o aplicativo mais recente será baixado e substituirá o aplicativo antigo.

1. Para carregar o aplicativo mais novo, navegue até o [portal MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Todos os **aplicativos**  ->  *As PropriedadesNameOfYourApp.*  ->  ****
2. Ao lado das informações do aplicativo, selecione **Editar.**
3. Para que o valor do &quot; arquivo Select seja &quot; atualizado, selecione seu arquivo.
4. A partir daqui, use o menu de contexto para abrir o explorador de arquivos e carregar a versão mais recente do aplicativo LOB. Certifique-se de incluir dependências conforme necessário.

Confira mais: [Implantação de aplicativo do Intune para HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plano de Desenvolvimento

Com seu dispositivo registrado com êxito, agora você está preparado para implantar mais aplicativos LOB em seus dispositivos. Durante a duração deste Guia, estamos usando um aplicativo de exemplo, mas é mais provável que você queira usar aplicativos personalizados construídos para as necessidades da sua organização.

Se você já tiver um aplicativo LOB, estará pronto para [implantar seu aplicativo por meio do MDM](https://docs.microsoft.com/hololens/app-deploy-intune). Se você preferir um método diferente, revise a visão geral de implantação do aplicativo para [o HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para saber mais métodos de implantação do aplicativo LOB em seus dispositivos.

Se você ainda tiver que criar seu próprio aplicativo LOB ou ainda estiver no processo de criação, revise nossos documentos de desenvolvimento de realidade misturada para começar a projetar e [prototipar](https://docs.microsoft.com/windows/mixed-reality/design/design) ou aprender os principais conceitos para começar com o desenvolvimento de realidade [misturada.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plano de Suporte

Um plano de suporte é uma excelente opção. Ter alguém, ou um grupo, treinado para solucionar problemas do processo de registro em dispositivos HoloLens e também o uso geral do dispositivo HoloLens em sua organização é útil. Para permitir que seus usuários tenham a resolução mais rápida de seus problemas, sugerimos que seu processo de escalonamento seja tratado de maneira semelhante a esta ordem:

1. Sua mesa de Suporte.
2. Sua equipe de Especialistas do HoloLens
3. [Documentos do HoloLens](https://docs.microsoft.com/hololens/)  /  [Documentos de solução de problemas do HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contate o Suporte](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gerenciamento de Dispositivo

Este guia fala sobre como configurar o Gerenciamento de Dispositivo Móvel (MDM) e o usou para configurar algumas configurações de dispositivo e aplicar configurações para permitir o acesso em termos de certificados Wi-Fi e proxy. No entanto, o MDM também pode ser usado para aplicar restrições de dispositivo por meio de CSPs e Políticas.

Em muitos casos, os dispositivos podem ter restrições de conectividade, como Bluetooth, VPN, USB ou até mesmo desligar o acesso à câmera ou microfone. Se algum desses interesses você quiser, recomendamos que você leia nossa página de [restrições de dispositivo comum.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

Há outras restrições de dispositivo mais complexas que você pode usar. Como:

- Limitar as páginas que podem ser exibidas no aplicativo Configurações usando [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), permitindo que os usuários acessem apenas as configurações que precisam ajustar, como alterar sua conexão Wi-Fi.
- Use [o modo Quiosque](https://docs.microsoft.com/hololens/hololens-kiosk) para limitar a interface do usuário apresentada aos usuários em um dispositivo. Você pode definir Quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada. Os quiosques também podem apresentar experiências diferentes para usuários diferentes.
- [Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) para impedir que aplicativos ou processos específicos seja lançado inteiramente.

Se você quiser saber mais sobre métodos adicionais de gerenciamento de dispositivos ou restrições de dispositivos, dê a próxima etapa e leia nossa Visão Geral de Gerenciamento [de Dispositivos.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





