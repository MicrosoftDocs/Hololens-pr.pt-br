---
title: Localizar, instalar e desinstalar aplicativos
description: A Microsoft Store é a sua fonte de aplicativos e jogos que funcionam com o HoloLens.  Saiba mais sobre como encontrar, instalar e desinstalar aplicativos holográficos.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4705112ee41ce6de0598358b9c81775f261bb2fa
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800548"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Encontrar, instalar e desinstalar aplicativos da Microsoft Store

A Microsoft Store é a sua primeira opção para aplicativos e jogos que funcionam com o HoloLens. Quando você acessa a Store no HoloLens, todos os aplicativos exibidos nela são executados nele.

Os aplicativos do HoloLens usam a exibição 2D ou holográfica. Os aplicativos que usam a exibição 2D têm aparência semelhante a janelas e podem ser colocados em qualquer posição à sua volta. Os aplicativos que usam a exibição holográfica ficam ao seu redor e se tornam o único aplicativo que você vê.

O HoloLens dá suporte a muitos aplicativos existentes da Microsoft Store e a novos aplicativos criados especificamente para o HoloLens.  Esse artigo tem como foco os aplicativos holográficos da Microsoft Store.

Para saber mais sobre como instalar e executar aplicativos personalizados, leia [Aplicativos holográficos personalizados](holographic-custom-apps.md).

## <a name="find-apps"></a>Encontrar aplicativos

Abra a Microsoft Store no menu **Iniciar**. Em seguida, procure aplicativos e jogos. Use os [comandos de voz](hololens-cortana.md) para a pesquisa dizendo "Search". Depois que a janela de pesquisa for aberta, diga "Start dictating" e, quando solicitado, comece a dizer os termos da pesquisa.

> [!NOTE]
> Os requisitos do sistema para dispositivos HoloLens são baseados na arquitetura do build do aplicativo. Se um build do aplicativo para o HoloLens (1ª geração) não tiver sido atualizado com uma nova UWP na loja para incluir o pacote de arquitetura ARM, ele não estará disponível para os dispositivos HoloLens 2. Da mesma forma, se um aplicativo HoloLens 2 não incluir o pacote de arquitetura x86, ele não estará disponível para os dispositivos HoloLens (1ª geração). Arquiteturas de dispositivos HoloLens:
>
> - x86 = HoloLens (1ª geração)
> - ARM = HoloLens 2

> [!NOTE]
> Em 12 de janeiro de 2021, os aplicativos a seguir chegaram ao fim do suporte em dispositivos HoloLens. Incentivamos você a usar o link a seguir no seu dispositivo para usar a versão Web do aplicativo.

| Aplicativo        | Link                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> O aplicativo OneDrive atualmente não é compatível com as contas do Azure Active Directory no HoloLens. Recomendamos que você baixe o aplicativo PWA do Microsoft OneDrive. [Siga estas etapas para baixar o aplicativo.]

## <a name="install-apps"></a>Instalar aplicativos

Para baixar aplicativos, você precisará estar conectado com uma conta Microsoft. Alguns aplicativos são gratuitos e podem ser baixados imediatamente. Para os aplicativos que exigem uma compra, você precisará entrar na Store com a sua conta Microsoft e ter uma forma de pagamento válida.

> [!NOTE]
> A conta usada na Microsoft Store não precisa ser igual à conta com a qual você está conectado. Se você estiver usando uma conta corporativa ou de estudante no HoloLens, talvez precise entrar com a sua conta pessoal no aplicativo Store para fazer uma compra.

> [!TIP]
> Para configurar uma forma de pagamento, acesse [account.microsoft.com](https://account.microsoft.com/) e selecione **Pagamento e cobrança** > **Opções de pagamento** > **Adicionar uma opção de pagamento**.

1. Para abrir o [menu **Iniciar**](holographic-home.md), execute um [gesto de Iniciar](/hololens/hololens2-basic-usage#start-gesture) ou um gesto de [abrir a mão](hololens1-basic-usage.md) no HoloLens (1ª geração).

1. Selecione o aplicativo Microsoft Store. Depois que o aplicativo Store for aberto:
   1. Use a barra de pesquisa para procurar aplicativos.
   1. Selecione aplicativos essenciais ou aplicativos feitos especificamente para o HoloLens de uma das categorias coletadas.
   1. No canto superior direito do aplicativo Store, selecione o botão **"…"** e escolha **Minha Biblioteca** para ver os aplicativos comprados anteriormente.

1. Selecione **Obter** ou **Instalar** na página do aplicativo (uma compra pode ser necessária).

### <a name="install-microsoft-onedrive-pwa-app"></a>Instale o aplicativo PWA do Microsoft OneDrive

> [!NOTE]
> O PWA não pode ser gerenciado nem implantado por meio do Microsoft Intune/MDM.

Pré-requisitos: o usuário precisa ter adicionado o dispositivo do HoloLens 2 ao seu locatário de trabalho.

1. Abra o menu Iniciar e inicie o navegador Edge.

    ![Menu Iniciar](images/office-pwa-1.jpg)

1. Em seu HoloLens, vá para [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) e insira as credenciais da sua conta corporativa

    ![Entrar no trabalho](images/office-pwa-2.jpg)

1. Depois de ter entrado com êxito no portal Web do OneDrive, aguarde de 30 a 60 segundos para o botão de download do PWA aparecer

    ![Botão de instalação do PWA](images/office-pwa-3.jpg)

1. Selecione o botão de download do PWA e instale o aplicativo

    ![Prompt de instalação](images/office-pwa-4.jpg)

1. Feche o navegador Edge e, no menu Iniciar, selecione o botão **Todos os Aplicativos** e inicie o aplicativo PWA do OneDrive **rotulado Microsoft OneDrive**

    ![Todos os apps mostram os dois aplicativos.](images/office-pwa-5.jpg)

    > [!NOTE]
    > O "Microsoft OneDrive" é o aplicativo PWA no qual o "OneDrive" é a UWP mais antiga.

1. Após isso, você poderá ver seus arquivos do OneDrive.

    ![PWA do OneDrive](images/office-pwa-6.jpg)

Confira também: [Habilitando uploads automáticos para o OneDrive for Business](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Atualizar aplicativos

### <a name="manual-updates"></a>Atualizações manuais

Para atualizar um aplicativo que você instalou da Microsoft Store, atualize-o por meio do aplicativo Microsoft Store. Para os aplicativos instalados para a Microsoft Store para Empresas, atualize também esses aplicativos na Microsoft Store para Empresas.

1. Para abrir o [menu **Iniciar**](holographic-home.md), execute um [gesto de Iniciar](/hololens/hololens2-basic-usage#start-gesture) ou um gesto de [abrir a mão](hololens1-basic-usage.md) no HoloLens (1ª geração).

1. Escolha o aplicativo Store.

1. Olhe para o canto superior direito do aplicativo Store.

1. Selecione o botão **"…"** ou “Ver mais”.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do aplicativo Microsoft Store.](images/store-update-1.png)

1. Escolha **Downloads e atualizações**.
    1. Se o seu dispositivo identificou atualizações anteriormente, pode haver uma seta para baixo e um número que representa as atualizações pendentes.

1. Selecione **Obter atualizações**. Agora, seu dispositivo pesquisará se há atualizações e as definirá para download e instalação.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do aplicativo Microsoft Store obtendo atualizações.](images/store-update-2.png.jpg)

> [!NOTE]
> Se os aplicativos do seu dispositivo foram distribuídos pela sua organização, eles podem ser atualizados por meio dos mesmos métodos de gerenciamento de aplicativos comerciais. Se isso se aplicar à sua situação, leia mais por meio de nossa [visão geral da implantação de aplicativos comerciais.](app-deploy-overview.md)
>
> Se você deseja atualizar um aplicativo personalizado de sideload ou implantado, use o mesmo método com a versão atualizada do aplicativo. Para saber mais sobre como instalar e executar aplicativos personalizados, leia [Aplicativos holográficos personalizados](holographic-custom-apps.md).

### <a name="automatic-app-updates"></a>Atualizações automáticas do aplicativo

As atualizações automáticas ocorrem em aplicativos da Microsoft Store ou Microsoft Store para Empresas e somente se os aplicativos tiverem sido instalados diretamente da Store. Quando instalados do Intune, o TI pode forçar atualizações pelo MDM, sincronizando com a Microsoft Store para Empresas, para obter a versão mais recente disponível para o aplicativo.

> [!NOTE]
> No caso de aplicativos originados na Microsoft Store para Empresas, você precisa estar conectado à Store e autenticado com o mesmo locatário associado ao catálogo da Microsoft Store para Empresas usado no dispositivo.

#### <a name="how-automatic-updates-work"></a>Como as atualizações automáticas funcionam

As atualizações automáticas de aplicativo estão programadas para ocorrer diariamente (aproximadamente a cada 24 horas), sujeitos à disponibilidade da rede. Mantenha seu dispositivo ativo ou conectado à alimentação para receber as atualizações. Mesmo se as atualizações do aplicativo forem baixadas durante o uso diário ativo, elas só serão instaladas quando o aplicativo em questão não estiver mais em uso.

> [!TIP]
> Se possível, carregue seu dispositivo durante a noite enquanto está conectado à rede corporativa. Se as atualizações puderem ser baixadas e instaladas durante a noite, será menos provável que elas interrompam o uso ativo do dispositivo.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>Como os administradores de TI podem controlar as atualizações automáticas

Os administradores de TI podem controlar as atualizações automáticas dos aplicativos por meio da [política ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate). Essa política permite que eles habilitem ou desabilitem completamente as atualizações automáticas dos aplicativos, mas não controla quando ocorrerão as atualizações.

A partir da versão [21H2](hololens-release-notes.md#windows-holographic-version-21h1), os administradores de TI também podem usar a política [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) para controlar quando os aplicativos que estavam em uso, mas não puderam ser atualizados nas tentativas anteriores, devem ser reiniciados à força.

## <a name="uninstall-apps"></a>Desinstalar aplicativos

Há três maneiras de desinstalar aplicativos. Você pode desinstalar aplicativos por meio da Microsoft Store, do menu Iniciar ou em Configurações.

> [!WARNING]
> Não é possível desinstalar um aplicativo do sistema ou da própria Microsoft Store.

> [!IMPORTANT]
> Se o HoloLens 2 tiver vários usuários, você precisará estar conectado como o usuário que instalou o aplicativo para desinstalá-lo.

### <a name="uninstall-from-the-microsoft-store"></a>Desinstalação por meio da Microsoft Store

Abra a Microsoft Store no menu **Iniciar** e procure o aplicativo que deseja desinstalar.  Na página da Store, cada aplicativo instalado tem um botão **Desinstalar**.

### <a name="uninstall-from-the-start-menu"></a>Desinstalação no menu Iniciar

No menu **Iniciar** ou na lista **Todos os aplicativos**, navegue até o aplicativo. Pressione e segure até que o menu seja exibido e selecione **Desinstalar**.

### <a name="uninstall-from-settings"></a>Desinstalação em Configurações

No menu **Iniciar**, selecione **Configurações > Aplicativos.** Localize o aplicativo na lista, selecione-o e clique em **Desinstalar**.

Se você não conseguir desinstalar um aplicativo, envie [comentários](/hololens/hololens-feedback) usando o Hub de Comentários.
