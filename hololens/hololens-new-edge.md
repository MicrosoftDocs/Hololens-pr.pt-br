---
title: Apresentando o novo Microsoft Edge
description: Saiba mais sobre o novo aplicativo Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, Internet, navegador
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189691"
---
# <a name="introducing-the-new-microsoft-edge"></a>Apresentando o novo Microsoft Edge

![Animação do logotipo do Microsoft Edge herdado para o logotipo do novo Microsoft Edge.](images/new-edge.gif)

O novo Microsoft Edge [adota o projeto de software livre Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para que haja uma melhor compatibilidade para os clientes e menos fragmentação da Web para os desenvolvedores Web.

Com o [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), o novo Microsoft Edge está disponível para clientes do HoloLens 2 pela primeira vez! Compartilhe comentários e bugs com nossa equipe por meio do recurso **Enviar Comentários** no novo Microsoft Edge ou por meio do [Hub de Comentários](hololens-feedback.md).

> [!IMPORTANT]
> Esse novo Microsoft Edge substitui automaticamente o Microsoft Edge herdado, que [não tem mais suporte](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) em novas versões.

![Captura de tela do novo Microsoft Edge.](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Iniciando o novo Microsoft Edge

O novo Microsoft Edge ![O ícone do novo Microsoft Edge.](images/new_edge_logo.png) (representado por um ícone de espiral azul e verde) está fixado no menu Iniciar e será iniciado automaticamente quando você ativar um link da Web.

> [!NOTE]
> Quando você iniciar pela primeira vez o novo Microsoft Edge no HoloLens 2, suas configurações e dados serão importados do Microsoft Edge herdado.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Definindo as configurações de política para o novo Microsoft Edge

O novo Microsoft Edge oferece aos administradores de TI um conjunto muito mais amplo de políticas de navegador no HoloLens 2 em relação ao que estava disponível com o Microsoft Edge herdado.

Estes são alguns recursos úteis para saber mais sobre o gerenciamento de configurações de política para o novo Microsoft Edge:

- [Definir configurações de política do Microsoft Edge com o Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Mapeamento de políticas da Versão Prévia do Microsoft Edge para o Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapeamento de políticas do Google Chrome para o Microsoft Edge](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Documentação completa do Microsoft Edge Enterprise](/deployedge/)

> [!IMPORTANT]
> Devido ao volume de políticas de navegador com suporte do novo Microsoft Edge, nossa equipe não pode garantir que todas as novas políticas funcionam no HoloLens 2. No entanto, testamos e confirmamos que cada política do novo Microsoft Edge equivalente a uma política do Microsoft Edge herdado que tinha suporte no HoloLens 2 anteriormente funciona conforme o esperado. Confira o [Mapeamento de políticas da Versão Prévia do Microsoft Edge para o Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) para encontrar o equivalente no novo Microsoft Edge de cada política de navegador do Microsoft Edge herdado que você estava usando com o HoloLens 2.
>
> Há pelo menos duas novas políticas do Microsoft Edge que sabemos que *não* funcionam com o HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>O que esperar do novo Microsoft Edge no HoloLens 2

Como o novo Microsoft Edge é um aplicativo Win32 nativo com uma nova camada de adaptador da UWP que permite que ele seja executado em dispositivos somente UWP, como o HoloLens 2, alguns recursos podem não estar disponíveis imediatamente. Daremos suporte a novos cenários e recursos nos próximos meses, portanto, confira neste espaço as informações atualizadas.

**Cenários e recursos que devem funcionar:**
- Experiência de primeira execução, entrada no perfil e sincronização
- Os sites devem ser renderizados e devem se comportar conforme o esperado
- A maioria das funcionalidades do navegador (Favoritos, Histórico etc.) deve funcionar conforme o esperado
- Modo escuro
- Instalação de aplicativos Web no dispositivo
- Instalação de extensões (informe-nos se você usar alguma extensão que não funcionar corretamente no HoloLens 2)
- Exibição e marcação de PDF
- Som espacial de uma janela do navegador
- Atualização automática e manual do navegador
- Salvamento de PDF no menu Imprimir (usando a opção "Salvar em PDF")
- Extensão do WebXR e do Visualizador 360
- Restauração de conteúdo para a janela correta ao navegar entre várias janelas em seu ambiente

**Cenários e recursos que não devem funcionar:**
- Som espacial de várias janelas com fluxos de áudio simultâneos
- "Veja e diga"
- Imprimindo

**Principais problemas conhecidos do navegador:**
- A visualização com lupa no teclado holográfico foi desabilitada para o novo Microsoft Edge. Esperamos reabilitar esse recurso em uma atualização futura quando a ampliação estiver funcionando corretamente.
- O áudio poderá ser reproduzido na janela errada do navegador se você tiver outra janela do navegador aberta e ativa. Você pode contornar esse problema fechando a outra janela ativa que não deveria estar reproduzindo áudio.
- Ao reproduzir áudio de uma janela do navegador no modo "Follow me", o áudio continuará sendo reproduzido se você desabilitar o modo "Follow me". Você pode contornar esse problema interrompendo a reprodução de áudio antes de desabilitar o modo "Follow me" ou fechando a janela usando o botão X.
- A interação com janelas ativas do Microsoft Edge pode fazer com que outras janelas de aplicativo 2D fiquem inativas inesperadamente. Você pode reativar essas janelas interagindo com elas novamente.

## <a name="microsoft-edge-insider-channels"></a>Canais do Microsoft Edge Insider

A equipe do Microsoft Edge disponibiliza três canais de pré-visualização para a comunidade do Edge Insider: Beta, Dev e Canary. A instalação de um canal de pré-visualização não desinstala a versão de lançamento do Microsoft Edge no HoloLens 2 e você pode instalar mais de um ao mesmo tempo. 

Visite a [Home page do Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para saber mais sobre a comunidade do Edge Insider. Para saber mais sobre os diferentes canais do Edge Insider e começar, visite a [Página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).

Há alguns métodos disponíveis para instalar os canais do Microsoft Edge Insider no HoloLens 2:

**Instalação direta no dispositivo (disponível atualmente apenas para dispositivos não gerenciados)**
  1. Em seu HoloLens 2, visite a [Página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o botão **Baixar para o HoloLens 2** para o canal do Edge Insider que deseja instalar.
  1. Inicie o arquivo .msix baixado na fila de downloads do Edge ou na pasta "Downloads" do dispositivo (usando o Explorador de Arquivos).
  1. O [instalador do aplicativo](app-deploy-app-installer.md) será iniciado.
  1. Selecione o botão **Instalar**.
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge Beta, Dev ou Canary como uma entrada separada na lista **Todos os aplicativos** do menu Iniciar.

**Instalar via PC com o Portal de Dispositivos do Windows (requer que o [modo de desenvolvedor](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) esteja habilitado no HoloLens 2)**
  1. No PC, visite a [Página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão de seta suspensa** ao lado do botão "Baixar para o Windows 10" para o canal do Edge Insider que deseja instalar.
  1. Selecione **HoloLens 2** no menu suspenso.
  1. Salve o arquivo .msix na pasta "Downloads" do PC (ou em outra pasta que você possa encontrar facilmente).
  1. Use o [Portal de Dispositivos do Windows](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) no PC para instalar o arquivo .msix baixado no HoloLens 2.
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge Beta, Dev ou Canary como uma entrada separada na lista **Todos os aplicativos** do menu Iniciar.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Usando o WDAC para bloquear o novo Microsoft Edge

Para administradores de TI que desejam atualizar sua [política do WDAC](windows-defender-application-control-wdac.md) para bloquear o novo aplicativo Microsoft Edge, adicione o código a seguir à política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerenciando pontos de extremidade para o novo Microsoft Edge

Alguns ambientes podem ter restrições de rede a serem consideradas. Para garantir uma experiência tranquila com o novo Edge, [habilite esses pontos de extremidade da Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os [pontos de extremidade para o HoloLens](hololens-offline.md) no momento.

## <a name="install-web-apps"></a>Instalar aplicativos Web
 > [!Note]
> Começando na [versão 21H1 do Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h1), o aplicativo Web do Office não será mais pré-instalado. 

Você pode usar o novo Edge para instalar aplicativos Web com aplicativos da Microsoft Store. Por exemplo, você pode instalar o aplicativo Web do Microsoft Office para exibir e editar arquivos hospedados no SharePoint ou no OneDrive. Para instalar o aplicativo Web do Office, visite https://www.office.com e selecione o botão **Aplicativo Disponível** ou **Instalar o Office** na barra de endereços. Selecione **Instalar** para confirmar.
> [!IMPORTANT]
> A funcionalidade do aplicativo Web do Office fica disponível somente quando o HoloLens 2 tem uma conexão ativa com a Internet.

## <a name="webxr-and-360-viewer"></a>WebXR e Visualizador 360


O novo Microsoft Edge inclui suporte para o WebXR, que é o novo padrão para a criação de experiências imersivas na Web (substituindo o WebVR). Muitas experiências da Web imersivas foram projetadas com a VR em mente (elas substituem seu campo de visão por um ambiente virtual), mas também há suporte para essas experiências no HoloLens 2. O padrão WebXR também habilita experiências da Web imersivas aumentadas e de realidade misturada que usam seu ambiente físico. Esperamos que, conforme os desenvolvedores passarem mais tempo com o WebXR, novas experiências imersivas aumentadas e de realidade misturada cheguem para os clientes do HoloLens 2 experimentarem!

A extensão do Visualizador 360 é baseada no WebXR e é instalada automaticamente com o novo Microsoft Edge no HoloLens 2. Essa extensão da Web permite que você mergulhe em vídeos em 360 graus. O YouTube oferece a maior seleção de vídeos 360, portanto incentivamos você a começar por lá.

### <a name="how-to-use-webxr"></a>Como usar o WebXR

1. Navegue até um site com suporte para o WebXR.
1. Selecione o botão **Entrar na VR**. A localização e a representação visual do botão podem variar de acordo com o site, mas ele pode ser semelhante a:

    ![Exemplo de botão Entrar na VR.](images/75px-enter-vr.png)

1. Na primeira vez que você tentar iniciar uma experiência do WebXR em um domínio específico, o navegador solicitará consentimento para entrar em uma exibição imersiva; selecione **Permitir**.
1. Use [gestos do HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular a experiência.
1. Se a experiência não tiver um botão **Encerrar**, use o [Gesto de iniciar](hololens2-basic-usage.md#start-gesture) para voltar ao início.

**Exemplos de WebXR recomendados**
- Visualizador 360 (confira a próxima seção)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Como usar o Visualizador 360

1. Navegue até um vídeo com 360 graus no YouTube.
1. No quadro de vídeo, selecione o botão de headset de realidade misturada:

    ![Botão para ativar o Visualizador 360.](images/enter-360-viewer.jpg)

1. Na primeira vez que você tentar iniciar uma experiência do Visualizador 360 em um domínio específico, o navegador solicitará consentimento para entrar em uma exibição imersiva. selecione **Permitir**.
1. Com um gesto de [fechar e abrir dedos indicador e polegar](hololens2-basic-usage.md#select-using-air-tap), abra os controles de reprodução. Use gestos de [hand rays e fechar e abrir dedos indicador e polegar](hololens2-basic-usage.md#select-using-air-tap) para reproduzir/pausar, acelerar/voltar, ativar/desativar legendas ou parar a experiência (que sai da exibição imersiva). Os controles de reprodução desaparecem após alguns segundos de inatividade.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Principais problemas conhecidos do WebXR e do Visualizador 360
- Dependendo da complexidade da experiência no WebXR, a taxa de quadros poderá cair ou travar.
- O suporte para articulações de mão com movimento no WebXR não está habilitado por padrão. Os desenvolvedores podem habilitar o suporte em edge://flags ativando a "Entrada de Mão do WebXR".
- Vídeos em 360 de sites diferentes do YouTube podem não funcionar conforme o esperado.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo comentários sobre o WebXR e o Visualizador 360

Compartilhe comentários e bugs com nossa equipe por meio do recurso **Enviar Comentários** no novo Microsoft Edge.
