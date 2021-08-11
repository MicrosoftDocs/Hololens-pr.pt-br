---
title: guia de implantação – corporativo conectado HoloLens 2 com guias do Dynamics 365 – manter
description: saiba como manter dispositivos HoloLens 2 em uma rede conectada corporativa com os guias do Dynamics 365.
keywords: HoloLens, gerenciamento, corporativo conectado, guias do Dynamics 365, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
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
ms.openlocfilehash: 2649e370e98747562591c031b8ae262674c831e071f4ef228557dda66d2dc768
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660275"
---
# <a name="maintain---corporate-connected-guide"></a>Manter-guia conectado corporativo

## <a name="update-hololens"></a>Atualizar o HoloLens

A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações.

Um método popular de gerenciamento de atualizações é fazer um adiamento de recursos de 30 dias. Isso permite que os administradores atualizem e visualizem novos recursos, ganhando conhecimento inicial e informando à sua mesa de suporte quaisquer novas alterações.

saiba como [gerenciar atualizações de HoloLens](/hololens/hololens-updates), incluindo os dias agendados, a hora agendada e a configuração de horas ativas no dispositivo, para que ele seja atualizado fora do horário de trabalho.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Como atualizar os guias do Dynamics 365 (e outros aplicativos da loja)

os guias do Dynamics 365 são um aplicativo In-Box e podem ser atualizados por meio do aplicativo Microsoft Store. para todos os aplicativos que são baixados por meio do Microsoft Store, eles podem ser [atualizados por meio do](/hololens/holographic-store-apps#update-apps) próprio aplicativo Microsoft Store manualmente.

## <a name="how-to-update-lob-apps"></a>Como atualizar aplicativos LOB

Os aplicativos LOB podem ser atualizados da mesma maneira que foram adicionados ao Intune. Os aplicativos podem ser atualizados no Intune carregando o novo aplicativo com um número de versão mais alto para a configuração de aplicativo existente. Quando o dispositivo for sincronizado com o Intune, ele observará que há uma versão mais recente do aplicativo, e o aplicativo mais recente será baixado e substituirá o aplicativo antigo.

1. Para carregar o aplicativo mais recente, navegue até os aplicativos do [portal do mem](https://endpoint.microsoft.com/#home)  ->   – > todas as propriedades de TheNameOfYourApp de todos os **aplicativos**  ->    ->  **.**
2. Ao lado de informações do aplicativo, selecione **Editar.**
3. Para o valor de &quot; Selecionar arquivo a ser atualizado &quot; , selecione o arquivo.
4. Aqui, use o menu de contexto para abrir o explorador de arquivos e carregar a versão mais recente do aplicativo LOB. Certifique-se de incluir dependências conforme necessário.

Veja mais: [implantação de aplicativo do Intune para HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plano de desenvolvimento

Com seu dispositivo registrado com êxito, agora você está preparado para implantar mais aplicativos LOB em seus dispositivos. Durante o período deste guia, estamos usando um aplicativo de exemplo, mas é mais provável que você queira usar aplicativos personalizados criados para as necessidades da sua organização.

Se você já tiver um aplicativo LOB, você estará pronto para [implantar seu aplicativo por meio do MDM](/hololens/app-deploy-intune). se você preferir um método diferente, examine a [visão geral da implantação do aplicativo para HoloLens 2](/hololens/app-deploy-overview) para saber mais métodos de implantação de seu aplicativo LOB em seus dispositivos.

Se você ainda tiver criado seu próprio aplicativo LOB ou ainda estiver no processo de criação, examine nossos documentos de desenvolvimento de realidade misturada para [começar a projetar e criar um protótipo](/windows/mixed-reality/design/design) ou aprender os conceitos básicos para começar a [usar o desenvolvimento de realidade misturada.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plano de suporte

Um plano de suporte é uma excelente coisa a ter em vigor. ter alguém, ou um grupo, treinado na solução de problemas do processo de registro em dispositivos HoloLens e também uso geral do dispositivo HoloLens em sua organização é útil. Para permitir que os usuários tenham a resolução mais rápida de seus problemas, sugerimos que o processo de escalonamento seja manipulado de maneira semelhante a esta ordem:

1. Seu suporte técnico.
2. sua equipe de especialistas HoloLens
3. [HoloLens Docs](/hololens/)  /  [HoloLens documentos de solução de problemas](/hololens/hololens-troubleshooting)
4. [Contatar o suporte](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Gerenciamento de Dispositivo

Este guia falou sobre como configurar o MDM (gerenciamento de dispositivo móvel) e usá-lo para definir algumas configurações de dispositivo e aplicar configurações para permitir o acesso em termos de Wi-Fi certificados e proxy. No entanto, o MDM também pode ser usado para aplicar restrições de dispositivo por meio de CSPs e políticas.

em muitos casos, os dispositivos podem ter restrições de conectividade, como Bluetooth, VPN, USB ou até mesmo desativar o acesso à câmera ou ao microfone. Se alguma delas lhe interessa, recomendamos que você leia nossa página de [restrições comuns de dispositivo](/hololens/hololens-common-device-restrictions).

Há outras restrições de dispositivo mais complexas que você pode usar. Como:

- limitar as páginas que podem ser exibidas no aplicativo Configurações usando o [SettingsPageVisibility](/hololens/settings-uri-list), permitindo que os usuários acessem apenas as configurações que precisam ajustar, como alterar a conexão Wi-Fi.
- Use o [modo de quiosque](/hololens/hololens-kiosk) para limitar a interface do usuário apresentada aos usuários em um dispositivo. Você pode definir quiosques para mostrar um único aplicativo ou vários aplicativos com uma página inicial personalizada. Os quiosques também podem apresentar experiências diferentes a usuários diferentes.
- o [controle de aplicativo Windows (WDAC)](/hololens/windows-defender-application-control-wdac) para impedir que aplicativos ou processos específicos sejam iniciados inteiramente.

Se você quiser saber mais sobre métodos adicionais de gerenciamento de dispositivos ou restrições de dispositivo, siga a próxima etapa e leia nossa [visão geral do gerenciamento de dispositivos](/hololens/hololens-csp-policy-overview).





