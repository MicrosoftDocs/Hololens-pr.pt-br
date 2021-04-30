---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar o Insider compilações e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308191"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às compilações mais recentes do insider Preview para o HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.

## <a name="windows-insider-release-notes"></a>Notas de versão do Windows Insider

Estamos empolgados para começar a comprovar novos recursos para os insideres do Windows novamente. Novas compilações serão comprovadas no canal de desenvolvimento para as atualizações mais recentes. Continuaremos a atualizar esta página à medida que adicionamos mais recursos e atualizações para nossas compilações do Windows Insider.  Fique empolgado e pronto para misturar essas atualizações em sua realidade.

Esta atualização de recurso contém recursos para dois públicos-alvo. Recursos que podem ser usados por qualquer pessoa em um dispositivo pelo usuário final e novas opções de gerenciamento de dispositivo que podem ser configuradas por administradores de ti. A tabela de recursos abaixo especifica as audiências com quem pode usar cada novo recurso. Se você for um administrador de ti, dê uma olhada no nosso [administrador de ti – lista de verificação de atualização](#it-admin---update-checklist)

> [!IMPORTANT]
> Se você estava usando anteriormente o aplicativo de configurações ou o aplicativo Microsoft Edge em um quiosque, substituímos esses aplicativos por novos aplicativos que usam uma ID de aplicativo diferente. É altamente recomendável que você leia [novos AUMIDs para novos aplicativos no modo de quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) abaixo. Isso garantirá que você continue a ter o aplicativo configurações em seu quiosque ou inclua o novo aplicativo Microsoft Edge.

<br>

| Nome do recurso                                              | Descrição breve                                                                      | Público-alvo | Disponível no Build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Novo Microsoft Edge](#introducing-the-new-microsoft-edge) | O novo Microsoft Edge baseado em Chromium agora está disponível para o HoloLens 2                         | Usuário Final | 20279,1006 |
| [Visualizador de WebXR e 360](#webxr-and-360-viewer)             | Experimente experiências da Web de imersão e reprodução de vídeo 360                                           | Usuário Final | 20289,1000 |
| [Novo aplicativo de configurações](#new-settings-app)                     | O aplicativo configurações herdadas está sendo substituído por uma versão atualizada com novos recursos e configurações | Usuário Final | 20279,1006 |
| [Exibir calibragem de cor](#display-color-calibration)   | Selecione um perfil de cor alternativo para a tela do HoloLens 2                                | Usuário Final | 20293,1000 |
| [Seletor de aplicativo padrão](#default-app-picker)                 | Escolha qual aplicativo deve ser iniciado para cada arquivo ou tipo de link                                      | Usuário Final | 20279,1006 |
| [Por controle de volume por aplicativo](#per-app-volume-control) |  Controlar o volume de nível do aplicativo independentemente do volume do sistema | Usuário Final | 20293,1000 |
| [Aplicativo Web do Office](#office-web-app)                         | Um atalho para o Office Web App agora está listado em "todos os aplicativos"                                   | Usuário Final | 20279,1006 |
| [Passar o dedo para o tipo](#swipe-to-type)                           | Use a ponta do dedo para "deslizar" palavras no teclado Holographic                        | Usuário Final | 20279,1006 |
| [Menu de energia do início](#power-menu-from-start) | No menu Iniciar, reinicie e desligue o dispositivo HoloLens | Usuário Final | 20293,1000 |
| [Vários usuários listados na tela de entrada](#multiple-users-listed-on-sign-in-screen) | Exibir várias contas de usuário na tela de entrada | Usuário Final | 20293,1000 |
| [Suporte ao microfone externo USB-C](#usb-c-external-microphone-support) | Use microfones USB-C para aplicativos e/ou assistência remota.| Usuário Final | 20279,1006 |
| [Logon automático do visitante para quiosques](#visitor-auto-logon-for-kiosks)                          | Permite que o logon automático em contas de visitante seja usado para modos de quiosque.                         | Administrador de TI | 20279,1006                 |
| [Novo AUMIDs para novos aplicativos no modo de quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs para novas configurações e aplicativos de borda | Administrador de TI | 20279,1006 |
| [Falha na entrega do modo de quiosque aprimorado](#kiosk-mode-behavior-changes-for-handling-of-failures) | O modo de quiosque procura acesso global atribuído antes do menu iniciar vazio. | Administrador de TI | 20279,1006 |
| [Novo SettingsURIs para visibilidade de configurações de página](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20 + novo SettingsURIs para configurações/política de PageVisibilityList | Administrador de TI | 20289,1000 |
| [Configurar o diagnóstico de fallback](#configuring-fallback-diagnostics-via-settings-app) | Definindo o comportamento de diagnóstico de fallback no aplicativo de configurações | Administrador de TI | 20279,1006 |
| [Compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices) | Compartilhar arquivos ou URLs de um HoloLens para um PC | Tudo | 20279,1006 |
| [Novo solucionador de problemas de atualização do sistema operacional](#new-os-update-troubleshooter) | Novo solucionador de problemas em configurações para atualizações do sistema operacional | Administrador de TI | 20279,1006 |
| [Visualização da otimização de entrega](#delivery-optimization-preview) | Reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens | Administrador de TI | 20301,1000 |
| [Melhorias e correções na atualização](#improvements-and-fixes-in-the-update) | Correções adicionais na atualização. | Tudo | 20279,1006 |

### <a name="it-admin---update-checklist"></a>Administrador de ti – lista de verificação de atualização

Esta lista de verificação ajudará você a saber os novos itens que os recursos que estão sendo adicionados nesta atualização de recurso podem afetar suas configurações atuais de gerenciamento de dispositivo ou os novos recursos que você pode querer começar a usar.

#### <a name="updates-to-kiosk-mode"></a>Atualizações para o modo de quiosque

[**Novo AUMIDs para novos aplicativos no modo de quiosque**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Se você estava usando anteriormente o aplicativo de configurações ou o aplicativo Microsoft Edge em um quiosque, substituímos esses aplicativos por novos aplicativos que usam uma ID de aplicativo diferente. É altamente recomendável que você leia [novos AUMIDs para novos aplicativos no modo de quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) abaixo. Isso garantirá que você continue a ter o aplicativo configurações em seu quiosque ou inclua o novo aplicativo Microsoft Edge.

Essas alterações podem ser feitas agora e implantadas em todos os dispositivos e permitem uma transição mais suave na atualização.

[**Logon automático do visitante para quiosques**](#visitor-auto-logon-for-kiosks)

Os visitantes agora podem ser conectados automaticamente a um quiosque. Esse comportamento é ativado por padrão, mas pode ser gerenciado e desabilitado.

[**Falha na entrega do modo de quiosque aprimorado**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Se a associação de grupo do AAD do usuário conectado do AAD não for determinada com êxito, a configuração de quiosque global será usada para o menu iniciar (se houver) caso contrário, o usuário será apresentado com o menu iniciar vazio. Embora o menu iniciar vazio não seja uma configuração que você possa definir diretamente, essa nova manipulação pode ser algo para informar o departamento de suporte de se você estiver usando quiosques, pois isso pode se aplicar às suas configurações ou você talvez queira fazer novos ajustes nas suas configurações de acesso atribuídas.

#### <a name="updates-to-page-settings-visibility"></a>A visibilidade das configurações da página é atualizada

[**Novo SettingsURIs para visibilidade de configurações de página**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Se você estiver usando a [visibilidade de configurações de página](settings-uri-list.md) no momento, talvez queira fazer ajustes em seus URIs existentes que você tenha permitido ou bloqueado.

#### <a name="updates-for-your-wdac-policy"></a>Atualizações para sua política WDAC

Se você estava bloqueando o Microsoft Edge anteriormente por meio de WDAC, convém atualizar sua política WDAC. [Examine o seguinte](#using-wdac-to-block-new-microsoft-edge) e use o código de exemplo fornecido.

#### <a name="enable-new-endpoints-for-edge"></a>Habilitar novos pontos de extremidade para o Edge

Se você tiver uma infraestrutura que envolve a configuração de pontos de extremidade de rede, como proxy ou firewall, [habilite esses novos pontos de extremidade para o novo aplicativo Microsoft Edge.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>Itens configuráveis recentemente

- [Configurar o diagnóstico de fallback](#configuring-fallback-diagnostics-via-settings-app)
  - Você pode configurar se e quem pode coletar diagnósticos de fallback.
- [Compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices)
  - Você pode desabilitar o novo recurso de compartilhamento próximo.
- [Definindo as configurações de política para o novo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Examine as configurações recentes disponíveis para o Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nova ferramenta de diagnóstico

- [Novo solucionador de problemas de atualização do sistema operacional](#new-os-update-troubleshooter)
  - Coletar logs relacionados às atualizações do sistema operacional

### <a name="introducing-the-new-microsoft-edge"></a>Apresentando o novo Microsoft Edge

![Animação do logotipo herdado do Microsoft Edge para o novo logotipo do Microsoft Edge](images/new-edge.gif)

O novo Microsoft Edge [adota o projeto de](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) software livre Chromium para criar uma melhor compatibilidade para clientes e menos fragmentação da Web para desenvolvedores da Web.

Com essa visualização do Insider, o novo Microsoft Edge está disponível para clientes do HoloLens 2 pela primeira vez! Embora o novo Microsoft Edge eventualmente substitua o Microsoft Edge herdado no HoloLens 2, ambos os navegadores estão atualmente disponíveis para pessoas. Compartilhe comentários e bugs com nossa equipe por meio do recurso **enviar comentários** no novo Microsoft Edge ou por meio do [Hub de comentários](hololens-feedback.md).

![Nova captura de tela do Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Iniciando o novo Microsoft Edge

Há duas versões do Microsoft Edge disponíveis para pessoas: o novo ![ novo ícone do Microsoft Edge ](images/new_edge_logo.png) (representado por um ícone de espiral azul e verde) e o Microsoft Edge herdado (representado pelo ícone "e" branco). O novo Microsoft Edge é fixado no menu iniciar e será iniciado automaticamente quando você ativar um link da Web. Se você quiser reverter o uso do Microsoft Edge herdado como seu navegador da Web padrão, consulte as instruções abaixo para [redefinir os aplicativos padrão](#default-app-picker).

> [!NOTE]
> Quando você inicia o novo Microsoft Edge no HoloLens 2 pela primeira vez, suas configurações e dados serão importados do Microsoft Edge herdado. Se você continuar usando o Microsoft Edge herdado depois de iniciar o novo Microsoft Edge, esses novos dados não serão sincronizados do Microsoft Edge herdado para o novo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Definindo as configurações de política para o novo Microsoft Edge

O novo Microsoft Edge oferece aos administradores de ti um conjunto muito mais amplo de políticas de navegador no HoloLens 2 do que estavam disponíveis anteriormente com o Microsoft Edge herdado.

Aqui estão alguns recursos úteis para aprender mais sobre o gerenciamento de configurações de política para o novo Microsoft Edge:

- [Definir configurações de política do Microsoft Edge com Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge herdado para o mapeamento de política do Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapeamento de política do Google Chrome para o Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Documentação completa do Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Devido ao volume de políticas de navegador com suporte no novo Microsoft Edge, nossa equipe não consegue garantir que cada nova política funcione no HoloLens 2. No entanto, testamos e confirmamos o novo equivalente do Microsoft Edge de cada política herdada do Microsoft Edge com suporte anteriormente no HoloLens 2 funciona conforme o esperado. Consulte o [Microsoft Edge herdado para o mapeamento de política do Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) para encontrar o novo equivalente do Microsoft Edge de cada política de navegador do Microsoft Edge herdada que você estava usando com o HoloLens 2.
>
> Há pelo menos duas novas políticas do Microsoft Edge que sabemos que *não* funcionarão com o HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>O que esperar do novo Microsoft Edge no HoloLens 2

Como o novo Microsoft Edge é um aplicativo Win32 nativo com uma nova camada de adaptador UWP, permitindo que ele seja executado em dispositivos somente UWP, como o HoloLens 2, alguns recursos podem não estar imediatamente disponíveis. Daremos suporte a novos cenários e recursos nos próximos meses, portanto, verifique este espaço para obter informações atualizadas.

**Cenários e recursos que se espera que funcionem:**
- Experiência de primeira execução, entrar no perfil e sincronizar
- Os sites devem renderizar e se comportar conforme o esperado
- A maioria das funcionalidades do navegador (favoritos, histórico, etc.) deve funcionar conforme o esperado
- Modo escuro
- Instalando aplicativos Web no dispositivo
- Instalando extensões (informe-nos se você usar qualquer extensão que não funcione corretamente no HoloLens 2)
- Exibindo e marcando um PDF
- Som espacial de uma única janela do navegador
- Atualização automática e manual do navegador
- Salvando um PDF no menu Imprimir (usando a opção "salvar em PDF")
- Extensão do Visualizador de WebXR e 360
- Restauração de conteúdo para a janela correta, ao navegar por várias janelas colocadas em seu ambiente

**Cenários e recursos que não devem funcionar:**
- Som espacial de várias janelas com fluxos de áudio simultâneos
- "Vê-lo, digamos"
- Imprimindo

**Principais problemas conhecidos do navegador:**
- Wi-Fi configurações de proxy, que são políticas de proxy que têm como destino conexões de Wi-Fi individuais, não funcionam atualmente com o novo Microsoft Edge. Estamos trabalhando ativamente para desbloquear esse problema antes da liberação pública da atualização do sistema operacional.
- A visualização da lupa no teclado Holographic foi desabilitada para o novo Microsoft Edge. Esperamos reabilitar esse recurso em uma atualização futura, uma vez que a ampliação esteja funcionando corretamente.
- Dois caracteres no teclado japonês não funcionam conforme o esperado no novo Microsoft Edge. Esse problema foi causado pela raiz e deve ser corrigido em breve.
- Os links da Web no aplicativo Microsoft Store podem não iniciar o navegador
- O áudio pode ser reproduzido na janela do navegador incorreta se você tiver outra janela do navegador aberta e ativa. Você pode contornar esse problema fechando a outra janela ativa que não deveria estar reproduzindo áudio.
- Ao reproduzir áudio de uma janela do navegador no [modo "Follow-me"](hololens2-basic-usage.md#follow-me-stop-following), o áudio continuará a ser reproduzido se você desabilitar o modo "Siga eu". Você pode contornar esse problema interrompendo a reprodução de áudio antes de desabilitar o modo "Follow-me" ou fechando a janela com o botão **X** .
- Interagir com janelas ativas do Microsoft Edge pode fazer com que outras janelas de aplicativo 2D fiquem inativas inesperadamente. Você pode reativar essas janelas interagindo com elas novamente.
- Abrir um link da Web de outro aplicativo, ou determinados tipos de documentos, como PDFs, pode fazer com que uma segunda guia em branco seja aberta no navegador (além da nova guia criada com o conteúdo do link da Web ou do link do arquivo). Você pode contornar esse problema fechando a guia em branco adicional.

#### <a name="microsoft-edge-insider-channels"></a>Canais do Microsoft Edge Insider

A equipe do Microsoft Edge disponibiliza três canais de visualização para a Comunidade do Edge Insider: beta, dev e canário. A instalação de um canal de visualização não desinstala a versão de lançamento do Microsoft Edge no seu HoloLens 2, e você pode instalar mais de uma ao mesmo tempo. 

Visite a [Home Page do Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para saber mais sobre a Comunidade do Edge Insider. Para saber mais sobre os diferentes canais do Edge Insider e comece, visite a [página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).

Há alguns métodos disponíveis para a instalação de canais do Microsoft Edge Insider no HoloLens 2:

**Instalação direta no dispositivo (atualmente disponível apenas para dispositivos não gerenciados)**
  1. No seu HoloLens 2, visite a [página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o botão **baixar para o HoloLens 2** para o canal do Edge Insider que você deseja instalar.
  1. Inicie o arquivo. msix baixado na fila de download do Edge ou na pasta "downloads" do seu dispositivo (usando o explorador de arquivos).
  1. O [instalador do aplicativo](app-deploy-app-installer.md) será iniciado.
  1. Selecione o botão **Instalar**.
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge beta, dev ou canário como uma entrada separada na lista **todos os aplicativos** do menu iniciar.

**Instalar via PC com o Windows Device Portal (requer que o [modo de desenvolvedor](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) esteja habilitado no HoloLens 2)**
  1. Em seu computador, visite a [página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão de seta suspensa** ao lado do botão "download para Windows 10" para o canal do Edge Insider que você deseja instalar.
  1. Selecione **HoloLens 2** no menu suspenso.
  1. Salve o arquivo. msix na pasta "downloads" do seu PC (ou outra pasta que você possa encontrar facilmente).
  1. Use o [portal de dispositivo do Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) em seu computador para instalar o arquivo. msix baixado no HoloLens 2.
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge beta, dev ou canário como uma entrada separada na lista **todos os aplicativos** do menu iniciar.

> [!NOTE]
> Durante esta visualização do Windows Insider para o HoloLens 2, a versão do Microsoft Edge no seu dispositivo pode ser maior do que aquelas disponíveis em alguns (ou todos) dos canais do Microsoft Edge Insider. Isso é para garantir que os novos recursos e correções especificamente direcionados ao navegador da Web no HoloLens 2 estejam chegando aos nossos insideres do Windows o mais rápido possível. Logo após o lançamento público do próximo Windows Update, as compilações de canal do Microsoft Edge Insider ultrapassarão e ficarão à frente da versão do Microsoft Edge no seu HoloLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Usando o WDAC para bloquear o novo Microsoft Edge

Para os administradores de ti que procuram atualizar sua [política WDAC](windows-defender-application-control-wdac.md) para bloquear o novo aplicativo Microsoft Edge, você precisará adicionar o seguinte à sua política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerenciando pontos de extremidade para o novo Microsoft Edge

Alguns ambientes podem ter restrições de rede para considerar como uma consideração. Para garantir uma experiência tranqüila com a nova borda, [habilite esses pontos de extremidade da Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os pontos de [extremidade](hololens-offline.md)disponíveis no momento para o HoloLens.

### <a name="webxr-and-360-viewer"></a>Visualizador de WebXR e 360

*Adicionado no Windows Insider Build 20289,1000*

O novo Microsoft Edge inclui suporte para WebXR, que é o novo padrão para a criação de experiências de imersão na Web (substituindo WebVR). Muitas experiências da Web de imersão foram projetadas com o VR em mente (elas substituem o campo de exibição por um ambiente virtual), mas também há suporte para essas experiências no HoloLens 2. O padrão WebXR também permite experiências ampliadas e mistas de imersão da Web que usam seu ambiente físico. À medida que os desenvolvedores gastam mais tempo com o WebXR, antecipamos novas experiências de imersão aumentadas e mistas de realidade para que os clientes do HoloLens 2 tentem!

A extensão do visualizador 360 é criada no WebXR e é instalada automaticamente junto com o novo Microsoft Edge no HoloLens 2. Essa extensão da Web oferece a capacidade de aprofundar-lo em vídeos de 360 graus. O YouTube oferece a maior seleção de 360 vídeos, portanto, incentivamos você a começar lá.

#### <a name="how-to-use-webxr"></a>Como usar o WebXR

1. Navegue até um site com suporte a WebXR.
1. Selecione o botão **Inserir VR** no site. O local e a representação visual desse botão podem variar por site, mas pode ser semelhante a:

    ![Inserir exemplo de botão VR](images/75px-enter-vr.png)

1. Na primeira vez que você tentar iniciar uma experiência de WebXR em um domínio específico, o navegador pedirá autorização para inserir uma exibição de imersão, selecione **permitir**.
1. Use [gestos do HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular a experiência.
1. Se a experiência não tiver um botão **sair** , use o [gesto iniciar](hololens2-basic-usage.md#start-gesture) para retornar à página inicial.

**Exemplos de WebXR recomendados**
- 360 Viewer (consulte a próxima seção)
- [Dinossauro do XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Como usar o Visualizador de 360

1. Navegue até um vídeo de 360 graus no YouTube.
1. No quadro de vídeo, selecione o botão de headset de realidade misturada:

    ![Botão para ativar o Visualizador de 360](images/enter-360-viewer.jpg)

1. Na primeira vez que você tentar iniciar o Visualizador de 360 em um domínio específico, o navegador solicitará o consentimento para inserir uma exibição de imersão. selecione **Permitir**.
1. [Toque de ar](hololens2-basic-usage.md#select-using-air-tap) para abrir os controles de reprodução. Use [raios de mão e toque de ar](hololens2-basic-usage.md#select-using-air-tap) para reproduzir/pausar, pular para frente/para trás, ativar/desativar legendas ou interromper a experiência (que sai da exibição imersiva). Os controles de reprodução desaparecerão após alguns segundos de inatividade.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Problemas conhecidos do Visualizador de WebXR e 360 principais
- Dependendo da complexidade da experiência do WebXR, a taxa de quadros pode cair ou stutter.
- O suporte para junções de mão articuladas em WebXR não está habilitado por padrão. Os desenvolvedores podem habilitar o suporte via `edge://flags` ativando a "entrada do WebXR Hand".
- Ao sair de uma experiência do visualizador WebXR ou 360, pode levar 30 segundos ou mais para que os hologramas da realidade misturada reapareçam.
- 360 vídeos de sites diferentes do YouTube podem não funcionar conforme o esperado.
- As legendas estão atualmente desabilitadas no visualizador 360 no HoloLens 2. Planejamos habilitar esse recurso em uma atualização futura.
- Pausar um vídeo no visualizador 360 interrompe o vídeo do processamento (mas a seleção do botão reproduzir reinicia corretamente a reprodução).
- O botão "próximo vídeo" no visualizador 360 não funciona atualmente.
- Você pode reproduzir vídeos 2D em um modo "teatro" de imersão, mas a taxa de quadros pode ser inferior a 30 fps.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo comentários sobre o Visualizador de WebXR e 360

Compartilhe comentários e bugs com nossa equipe por meio do recurso **enviar comentários** no novo Microsoft Edge.

### <a name="new-settings-app"></a>Novo aplicativo de configurações

Com esta versão, estamos introduzindo uma nova versão do aplicativo de configurações. O novo aplicativo de configurações inclui novos recursos e configurações expandidas para o HoloLens 2 nas seguintes áreas: som, energia & suspensão, rede & Internet, aplicativos, contas, facilidade de acesso e muito mais.

> [!NOTE]
> Como o novo aplicativo de configurações é diferente do aplicativo de configurações herdadas, todas as janelas de configurações que você colocou anteriormente em seu ambiente serão removidas após a atualização.

![Home Page de novo aplicativo de configurações](images/new-settings-app.png)

**Novos recursos e configurações**
- Pesquisa de configurações: Procure configurações na página inicial configurações usando palavras-chave ou o nome da configuração.
- Som de > do sistema:
  - Dispositivos de áudio de entrada e saída: escolha de forma independente os dispositivos de áudio de entrada e saída (por exemplo, ouça o áudio por meio de fones de ouvido Bluetooth ou use um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Os microfones Bluetooth não têm suporte do HoloLens 2.
  - Volume do aplicativo: ajuste o volume de cada aplicativo de forma independente. Consulte [controle de volume por aplicativo](#per-app-volume-control).
- Suspensão de & de energia do sistema >: escolha quando o dispositivo deve ir para o estado de suspensão após um período de inatividade.
- Bateria de > do sistema: habilite manualmente o modo de economia de bateria ou defina um limite de bateria no qual o modo de economia de bateria é ativado automaticamente.
- Dispositivos > USB: você pode desabilitar conexões USB por padrão.
- Rede & Internet:
  - Adaptadores Ethernet USB-C agora aparecerão na rede & Internet.
  - As configurações do adaptador Ethernet USB-C agora estão disponíveis, incluindo seu endereço IP.
  - Agora você pode habilitar o modo avião no HoloLens 2.
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Para obter mais informações, consulte [seletor de aplicativo padrão](#default-app-picker).
- Contas > outros usuários: os proprietários de dispositivo podem adicionar usuários, atualizar usuários padrão para proprietários de dispositivo, fazer downgrade de proprietários de dispositivo para usuários padrão e remover usuários.
- Facilidade de acesso: alterar o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- Configurações colocadas anteriormente as janelas serão removidas (consulte a observação acima).
- Você não pode mais renomear seu dispositivo com o aplicativo configurações. Os administradores de ti podem renomear dispositivos usando o modelo de nome de dispositivo do [Windows AutoPilot para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) ou o nó MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- A página Ethernet mostra um dispositivo Ethernet virtual ("UsbNcm") em todos os momentos.
- O uso da bateria para o novo Microsoft Edge pode não ser preciso, devido à sua natureza como um aplicativo de área de trabalho Win32 com suporte de uma camada de adaptador UWP (sem correção prevista em breve).

### <a name="display-color-calibration"></a>Exibir calibragem de cor

*Adicionado no Windows Insider Build 20293,1000*

Com essa nova configuração, você pode selecionar um perfil de cor alternativo para sua exibição do HoloLens 2. Isso pode ajudar as cores a parecerem mais precisas, especialmente em níveis de brilho de exibição mais baixos. A calibragem de cores de exibição pode ser encontrada no aplicativo configurações, na página calibragem de > do sistema.

> [!NOTE]
> Como essa configuração salva um novo perfil de cor em seu firmware de vídeo, ela é uma configuração por dispositivo (e não exclusiva para cada conta de usuário).

#### <a name="how-to-use-display-color-calibration"></a>Como usar a calibragem de cor de exibição

1. Inicie o aplicativo **configurações** e navegue até **System > Calibration**.
1. Em **Exibir calibragem de cor**, selecione o botão **executar calibragem de cor de exibição** .
1. A experiência de calibragem de cor de exibição será iniciada e encorajada a garantir que o visor esteja na posição correta.
1. Depois de prosseguir com as caixas de diálogo de instrução, sua exibição será automaticamente esmaecida para um brilho de 30%.
    > [!TIP]
    > Se você estiver tendo problemas para ver a cena esmaecida em seu ambiente, poderá ajustar manualmente o nível de brilho do HoloLens 2 usando os botões de brilho no lado esquerdo do dispositivo.
1. Selecione os botões 1-6 para testar instantaneamente cada perfil de cor e localize um que tenha a melhor aparência para os seus olhos (isso geralmente significa o perfil que ajuda a cena a parecer mais neutra, com o padrão de escala de cinza e tons de capas que parecem conforme o esperado).

    ![Exibir cena de calibragem de cor](images/color-cal-ui.png)
    
1. Quando estiver satisfeito com o perfil selecionado, selecione o botão **salvar & sair**
1. Se preferir não fazer alterações, selecione o botão **cancelar & sair** e suas alterações serão revertidas

> [!TIP]
> Aqui estão algumas dicas úteis para ter em mente ao usar a configuração de calibragem de cores de exibição:
> - Você pode executar novamente a calibragem de cor de exibição de configurações sempre que desejar
> - Se qualquer pessoa no dispositivo tiver usado anteriormente a configuração para alterar os perfis de cor, a data/hora da alteração mais recente será refletida na página de configurações
> - Quando você executa novamente a calibragem de cor de exibição, o perfil de cor que foi salvo anteriormente será realçado e o perfil 0 não será exibido (pois o perfil 0 representa o perfil de cor original da exibição)
> - Se você quiser reverter para o perfil de cor original da exibição, poderá fazer isso na página Configurações (consulte [como redefinir o perfil de cor](#how-to-reset-color-profile))

#### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cor

Se você não estiver satisfeito com o perfil de cor personalizado salvo no seu HoloLens 2, poderá restaurar o perfil de cor original do dispositivo:
1. Inicie o aplicativo **configurações** e navegue até **System > Calibration**.
1. Em **Exibir calibragem de cor**, selecione o botão **Redefinir para perfil de cor padrão** .
1. Quando a caixa de diálogo for aberta, selecione **reiniciar** se você estiver pronto para reiniciar o HoloLens 2 e aplicar suas alterações.

#### <a name="top-display-color-calibration-known-issues"></a>Problemas conhecidos de calibragem de cor de exibição superior

- Na página configurações, a cadeia de caracteres de status que informa quando o perfil de cores foi alterado pela última vez estará desatualizada até que você recarregue essa página de configurações.
    - Solução alternativa: selecione outra página de configurações e, em seguida, selecione novamente a página calibragem.

### <a name="default-app-picker"></a>Seletor de aplicativo padrão

Quando você ativa um hiperlink ou abre um tipo de arquivo com mais de um aplicativo instalado, que dá suporte a ele, você verá uma nova janela aberta solicitando que você selecione qual aplicativo instalado deve tratar do tipo de arquivo ou de link. Nessa janela, você também pode optar por fazer com que o aplicativo selecionado manipule o tipo de arquivo ou link "uma vez" ou "sempre".

![Janela do seletor de aplicativo](images/default-app-picker.png)

Se você escolher "sempre", mas posteriormente quiser alterar qual aplicativo trata um determinado arquivo ou tipo de link, poderá redefinir os padrões salvos em **configurações > aplicativos**. Role até a parte inferior da página e selecione o botão **limpar** em "aplicativos padrão para tipos de arquivo" e/ou "aplicativos padrão para tipos de link". Diferentemente da configuração semelhante em computadores desktop, não é possível redefinir padrões de tipo de arquivo individuais.

### <a name="per-app-volume-control"></a>Por controle de volume por aplicativo

Agora, neste Windows Insider Build, os usuários podem ajustar manualmente o nível de volume de cada aplicativo. Isso permite que os usuários se concentrem melhor nos aplicativos que precisam ou ouvem-se melhor ao usar vários aplicativos. Como a necessidade de desativar o volume de um aplicativo ao chamar outra pessoa para assistência remota em outro.

Para definir o volume de um aplicativo individual, navegue até **configurações**  ->  som do **sistema** e  ->  , em opções avançadas de som, selecione o **volume do aplicativo e as preferências do dispositivo**.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Aplicativo Web do Office

>[!NOTE]
>A partir do Build 20325,1000 do Windows Insider, o Office Web App não será mais pré-instalado (e não será pré-instalado para a próxima versão pública da atualização do sistema operacional. Para instalar o Office Web App, visite https://www.office.com e selecione o botão **aplicativo disponível** ou **instalar o Office** na barra de endereços. Selecione **instalar** para confirmar.

O Office Web App foi adicionado à lista "todos os aplicativos" no menu iniciar. Esse aplicativo Web também pode ser fixado para iniciar ou desinstalar. Como esse é um aplicativo Web, sua funcionalidade corresponde exatamente ao que você teria ao visitar https://www.office.com . A funcionalidade do Office Web App está disponível somente quando o seu HoloLens 2 tem uma conexão ativa com a Internet.

**Problema conhecido**
- A redefinição do dispositivo removerá o Office Web App

### <a name="swipe-to-type"></a>Passar o dedo para o tipo

Alguns clientes acham mais rápido para "digitar" em teclados virtuais, passando a forma da palavra que pretendem digitar e estamos visualizando esse recurso no teclado Holographic. Você pode passar uma palavra por vez passando a ponta do dedo por meio do plano do teclado do Holographic, passando a forma da palavra e, em seguida, retirando a ponta do dedo do plano do teclado. Você pode passar as palavras de acompanhamento sem precisar pressionar a barra de espaço removendo o dedo do teclado entre as palavras. Você saberá que o recurso está funcionando se vir uma trilha do dedo após o movimento do dedo no teclado.

Observe que esse recurso pode ser complicado para usar e dominar por causa da natureza de um teclado Holographic em que você não sente a resistência contra o dedo (ao contrário de uma exibição de telefone celular). Estamos avaliando esse recurso para liberação pública, para que seus comentários sejam importantes; Se você achar o recurso útil ou se tiver comentários construtivas, informe-nos por meio do [Hub de comentários](hololens-feedback.md).

### <a name="power-menu-from-start"></a>Menu de energia do início

Um novo menu que permite ao usuário sair, desligar e reiniciar o dispositivo. Um indicador na tela inicial do HoloLens que mostra quando uma atualização do sistema está disponível.

#### <a name="how-to-use"></a>Como usar

1. Abra a tela inicial do HoloLens usando o [gesto de início](hololens2-basic-usage.md#start-gesture) ou dizendo "ir para iniciar".

2. Observe o ícone de reticências (...) ao lado da imagem de perfil do usuário:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selecione a imagem de perfil do usuário usando suas mãos ou o comando de voz "Power".

4. Um menu é exibido com opções para sair, reiniciar ou desligar o dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Selecione as opções de menu para sair, reiniciar ou desligar seu HoloLens. A opção sair pode não estar disponível, se o dispositivo estiver configurado para uma [única conta da Microsoft (MSA) ou conta local](hololens-identity.md).

6. Descartar o menu tocando em qualquer outro lugar ou fechando o menu iniciar com o gesto de início.

#### <a name="update-indicator"></a>Indicador de atualização

Quando uma atualização está disponível, o ícone de reticências se acenderá para indicar que uma reinicialização instalará a atualização. as opções de menu também são alteradas para refletir a presença da atualização.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela de entrada

Anteriormente, a tela de entrada mostrou apenas o usuário conectado mais recentemente, bem como um ponto de entrada de "outro usuário". Recebemos comentários dos clientes de que isso não é suficiente se vários usuários tiverem entrado no dispositivo. Eles ainda eram solicitados a digitar novamente o nome de usuário, etc.

Introduzida nesta compilação do Windows Insider, ao selecionar **outro usuário** que está localizado à direita do campo de entrada de PIN, a tela de entrada exibirá vários usuários com o conectado anteriormente ao dispositivo. Isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entrem usando suas credenciais do Windows Hello. Um novo usuário também pode ser adicionado ao dispositivo por meio dessa página de outros usuários por meio do botão **adicionar conta** .

Quando estiver no menu outros usuários, o botão outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela de entrada deste usuário.

![Padrão da tela de entrada](./images/multiusers1.jpg)

<br>

![Tela de entrada de outros usuários](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Suporte ao microfone externo USB-C

> [!IMPORTANT]
> **A conexão a um mic USB não o definirá automaticamente como o dispositivo de entrada**. Ao conectar um conjunto de fones USB-C, os usuários observarão que o áudio do Headphone será redirecionado automaticamente para os fones de ouvido, mas o sistema operacional do HoloLens prioriza a matriz de microfone interna acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

Os usuários podem selecionar microfones externos conectados a USB C usando o painel configurações de **som** . Microfones USB-C podem ser usados para chamada, gravação, etc.

Abra o aplicativo **configurações** e selecione   >  **som** do sistema.

![Configurações de som](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com o **auxílio remoto**, os usuários precisarão clicar no hiperlink "gerenciar dispositivos de som".
>
> Em seguida, use a lista suspensa para definir o microfone externo como **padrão** ou **padrão de comunicação.** Escolher **padrão** significa que o microfone externo será usado em todos os lugares.
>
> Escolher **padrão de comunicação** significa que o microfone externo será usado no auxílio remoto e em outros aplicativos de comunicação, mas a matriz de Mic do HoloLens ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E quanto ao suporte a microfone Bluetooth?

Infelizmente, os microfones Bluetooth ainda não têm suporte no HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solução de problemas de microfones USB-C

Lembre-se de que alguns microfones USB-C se reportam incorretamente como um microlocutor *e* um palestrante. Isso é um problema com o microfone e não com o HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

Em **configurações**  ->    ->  **som** do sistema, defina explicitamente os alto-falantes internos **(driver de áudio de recurso analógico)** como o **dispositivo padrão**. O HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado posteriormente.

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Logon automático do visitante para quiosques

Esse novo recurso permite que o logon automático em contas de visitante seja usado para modos de quiosque.

Para uma configuração não AAD, para configurar um dispositivo para logon automático do visitante:

1. Crie um pacote de provisionamento que:
    1. Define **as configurações de tempo de execução/AssignedAccess** para permitir contas de visitante.
    1. Opcionalmente, registra o dispositivo no MDM **(configurações de tempo de execução/local de trabalho/registros)** para que possa ser gerenciado posteriormente.
    1. Não criar uma conta local
1. [Aplique o pacote de provisionamento](hololens-provisioning.md).

Para uma configuração do AAD, os usuários podem obter algo semelhante a isso hoje sem essa alteração. Os dispositivos ingressados no AAD configurados para o modo de quiosque podem entrar em uma conta de visitante com um único toque de botão na tela de entrada. Depois de entrar na conta do visitante, o dispositivo não solicitará a entrada novamente até que o visitante seja explicitamente desconectado do menu iniciar ou o dispositivo seja reiniciado.

O logon automático do visitante pode ser gerenciado por meio de uma política [de OMA-URI personalizada](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) :

- Valor do URI:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Política  | Descrição   | Configurações  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Permite que um visitante faça logon automaticamente em um quiosque   | 1 (Sim), 0 (não, padrão.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usar as novas configurações e os aplicativos de borda nos modos de quiosque

Ao incluir aplicativos em [quiosques](hololens-kiosk.md), um administrador de ti geralmente adiciona o aplicativo ao quiosque, mas usando seu AUMID (ID do modelo de usuário de aplicativo). Como o aplicativo Configurações e o aplicativo Microsoft Edge são considerados novos aplicativos e diferentes dos quiosques de aplicativos mais antigos que usam o AUMIDs para esses aplicativos precisarão ser atualizados para usar o novo AUMID.

Ao modificar um quiosque para incluir os novos aplicativos, recomendamos adicionar o novo AUMID, bem como deixar o antigo. Isso criará uma transição fácil quando os usuários atualizarem o sistema operacional e não precisarão receber novas políticas para continuar usando o quiosque como pretendido.

| Aplicativo                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicativo de configurações antigo       | HolographicSystemSettings_cw5n1h2txyewy! Aplicação            |
| Novo aplicativo de configurações       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicação |
| Aplicativo antigo do Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Novo aplicativo Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações de comportamento do modo de quiosque para tratamento de falhas

Em compilações mais antigas, se um dispositivo tivesse uma configuração de quiosque, que é uma combinação de acesso global atribuído e acesso atribuído ao membro do grupo do AAD, se determinar a associação do grupo do AAD falhar, o usuário verá o menu "[nada mostrado no início](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)".

A partir do lançamento do Windows Insider, a experiência de quiosque fará fallback para a configuração global do quiosque (se presente) em caso de falhas durante o modo de quiosque do grupo do AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>Novo SettingsURIs para visibilidade de configurações de página

No [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) adicionamos a [política Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas no aplicativo de configurações. PageVisibilityList é uma política que permite aos administradores de ti impedir que páginas específicas no aplicativo de configurações do sistema sejam visíveis ou acessíveis, ou para fazer isso para todas as páginas, exceto aquelas especificadas.

Se você visitar [visibilidade de configurações de página](settings-uri-list.md), poderá encontrar instruções para usar esse CSP e a lista de URIs disponíveis em versões anteriores.

Em compilações do Windows Insider, estamos expandindo a lista de URIs de configurações disponíveis, que os administradores de ti podem gerenciar. Alguns desses URIs são para áreas disponíveis recentemente dentro do novo aplicativo de configurações. Se você estiver usando a política configurações/PageVisibilityList, examine a lista a seguir e ajuste as páginas permitidas ou bloqueadas, conforme necessário.

> [!NOTE]
> **Preterido: MS-Settings: Network-proxy**
>
> Uma página de configurações é preterida nessas compilações mais recentes. A página de proxy da **Internet & rede** antiga  >   não está mais disponível como uma configuração global. As novas configurações de proxy por conexão podem ser encontradas em Propriedades da **rede & Internet**  >  **Wi-Fi**  >   ou na **rede &**  >  Propriedades de **Ethernet** da Internet  >  .

<br>

| Página de configurações                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplicativos > aplicativos & recursos                               | `ms-settings:appsfeatures`                         |
| Aplicativos > aplicativos & recursos > opções avançadas          | `ms-settings:appsfeatures-app`                     |
| Aplicativos > mapas offline                                  | `ms-settings:maps`                                 |
| Aplicativos > mapas offline > mapas de download                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Modo avião de > de rede & Internet                   | `ms-settings:network-airplanemode`                 |
| Privacidade > geral                                    | `ms-settings:privacy-general`                      |
| Privacidade > a personalização de digitação de & tinta             | `ms-settings:privacy-speechtyping`                 |
| Privacidade > Motion                                     | `ms-settings:privacy-motion`                       |
| Privacidade > bordas de captura de tela                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Privacidade > capturas de tela e aplicativos                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Bateria de > do sistema                                     | `ms-settings:batterysaver`                         |
| Bateria de > do sistema                                     | `ms-settings:batterysaver-settings`                |
| Som de > do sistema                                       | `ms-settings:sound`                                |
| > de som do sistema > o volume do aplicativo e as preferências do dispositivo | `ms-settings:apps-volume`                          |
| > de som do sistema > gerenciar dispositivos de som              | `ms-settings:sound-devices`                        |
| > de armazenamento do sistema > configurar o sensor de armazenamento         | `ms-settings:storagepolicies`                      |
| Hora & idioma > data & hora                        | `ms-settings:dateandtime`                          |
| Hora & idioma > teclado                           | `ms-settings:keyboard`                             |
| Idioma de > do idioma da & de tempo                           | `ms-settings:language`                             |
| Idioma de > do idioma da & de tempo                           | `ms-settings:regionlanguage-languageoptions`       |
| Atualizar & segurança > redefinir & recuperação               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URIs atualizados

Anteriormente, os dois URIs a seguir não levam um usuário diretamente às páginas indicadas, mas só bloqueamos a página atualizações principais. Os seguintes itens foram atualizados para direcionar suas páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurando o diagnóstico de fallback via aplicativo de configurações

Agora no aplicativo configurações, um usuário pode configurar o comportamento do [diagnóstico de fallback](hololens-diagnostic-logs.md). No aplicativo configurações, navegue até a página de  ->  **solução de problemas** de privacidade para definir essa configuração.

> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.  

### <a name="share-things-with-nearby-devices"></a>Compartilhar coisas com dispositivos próximos

Compartilhe coisas com perto de dispositivos Windows 10, incluindo PCs e outros dispositivos de HoloLens 2 que executam o HoloLens Insider Builds 20279.1006 +. Você pode experimentá-lo em **configurações**  ->    ->  **experiências compartilhadas** do sistema para compartilhar arquivos ou URLs de um HoloLens para um PC. Para obter mais detalhes, leia mais sobre como [compartilhar coisas com dispositivos próximos no Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esse recurso pode ser gerenciado por meio de [conectividade/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-update-troubleshooter"></a>Novo solucionador de problemas de atualização do sistema operacional

Além das soluções de problemas anteriores no aplicativo de configurações, uma nova solução de problemas foi adicionada com a adição do novo aplicativo configurações para atualizações do sistema operacional. Navegue até **configurações**  ->  **Atualizar &amp; segurança**  >  **solucionar problemas**  >  **Windows Update** e selecione **Iniciar**. Isso permite que você colete rastreamentos ao reproduzir seu problema com as atualizações do sistema operacional para auxiliar na solução de problemas com sua ti ou suporte.

### <a name="delivery-optimization-preview"></a>Visualização da otimização de entrega

Com essa atualização interna do HoloLens, o Windows Holographic for Business permite uma visualização antecipada das configurações de otimização de entrega para reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa dessa funcionalidade junto com a configuração de rede recomendada está disponível aqui: [otimização de entrega para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

As configurações a seguir são habilitadas como parte da superfície de gerenciamento e [podem ser configuradas no Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algumas limitações sobre esta oferta de visualização:

- O suporte ao HoloLens é limitado nesta visualização somente para atualizações do sistema operacional.
- O Windows Holographic for Business só dá suporte a modos de download de HTTP e downloads de um [ponto de extremidade de cache conectado da Microsoft](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Não há suporte para modos de download ponto a ponto e atribuições de grupo para dispositivos HoloLens no momento.
- O HoloLens não oferece suporte à otimização de implantação ou de distribuição para pontos de extremidade de Windows Server Update Services.
- A solução de problemas exigirá diagnóstico no servidor de cache conectado ou coletando um rastreamento no hololens no hololens por meio **das configurações**  >  **atualização & segurança**  >   **Windows Update solução de problemas**  >   .

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O [diagnóstico offline](hololens-diagnostic-logs.md#offline-diagnostics) também incluirá informações adicionais do dispositivo para o número de série e a versão do sistema operacional.

### <a name="known-issues-and-work-around"></a>Problemas conhecidos e contornar

#### <a name="pairing-hololens-to-pc"></a>Emparelhamento do HoloLens para o PC

Antes do Build 20325,1000 do Windows Insider, quando um usuário tinha definido credenciais de emparelhamento no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) e atualizado para o Windows Insider compilações, suas credenciais de conjunto anteriores para emparelhar o HoloLens com o PC para fins de implantação e depuração de aplicativos, como por meio do Visual Studio, não funcionaram mais. O Windows Insider Build 20325,1000 corrige esse problema e não requer ações adicionais para continuar usando o portal do dispositivo.

Os usuários que [piscaram seus dispositivos com uma compilação Insider](#ffu-download-and-flash-directions) agora precisarão refazer a reversão de seu dispositivo (para 20325.1000 + ou uma compilação GA) para emparelhar seus dispositivos com seus PCs.

Os usuários que não se registraram no Windows Insider e realizarão a atualização do recurso quando ele estiver geralmente disponível não serão afetados.


## <a name="start-receiving-insider-builds"></a>Comece a receber compilações do insider

> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize o dispositivo para atualizar o estado e obtenha a compilação mais recente.
> - O comando de voz "reinicializar dispositivo" funciona bem. 
> - Você também pode escolher o botão reiniciar em configurações/programa do Windows Insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso o levará de volta ao controle.

Em um dispositivo de HoloLens 2, vá para **configurações**  >  **atualização &**  >  **programa Windows Insider** de segurança e selecione **introdução**. Vincule a conta que você usou para se registrar como um Windows Insider.

O Windows Insider agora está migrando para os canais. O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta** e o anel de **versão prévia** se tornará o **canal versão prévia**. Aqui está o que esse mapeamento é semelhante a:

![Explicação dos canais do Windows Insider](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [introdução de canais do Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) em Blogs do Windows.

Em seguida, selecione **desenvolvimento ativo do Windows**, escolha se deseja receber as compilações do canal de **desenvolvimento** ou **beta** e examine os termos do programa.

Selecione **confirmar > reiniciar agora** para concluir. Depois que o dispositivo for reinicializado, vá para **configurações > atualização & segurança > verificar se há atualizações** para obter a compilação mais recente.

### <a name="update-error-0x80070490-work-around"></a>Erro de atualização 0x80070490 solução alternativa
Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal de desenvolvimento ou beta, tente a seguinte solução alternativa de curto prazo. Ele envolve mover seu canal Insider, selecionando a atualização e, em seguida, movendo o canal Insider de volta.

#### <a name="stage-one---release-preview"></a>Estágio One-Release versão prévia
1.  Configurações, atualização & segurança, programa Windows Insider, selecione **liberar canal de versão prévia**.
2.  Configurações, atualização & segurança, Windows Update, **verificar se há atualizações**. Após a atualização, continue no estágio dois.

#### <a name="stage-two---dev-channel"></a>Preparar canal de dois desenvolvedores
1. Configurações, atualização & segurança, programa Windows Insider, selecionar **canal de desenvolvimento**.
2. Configurações, atualização & segurança, Windows Update, **verificar se há atualizações**.

## <a name="ffu-download-and-flash-directions"></a>Download do FFU e direções do flash
Para testar com um FFU assinado por voo, primeiro você precisará desbloquear o dispositivo antes de atualizar o FFU assinado por voo.
1. No PC:

    1. Baixe o FFU para o seu PC do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (complemento de recuperação avançada) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Em HoloLens-Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Insider Program** , Inscreva-se, reinicie o dispositivo.

1. Flash FFU – agora você pode piscar o FFU assinado por voo usando o ARC.

## <a name="provide-feedback-and-report-issues"></a>Fornecer comentários e relatar problemas

Use [o aplicativo de Hub de comentários](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas. O uso do hub de comentários garante que todas as informações de diagnóstico necessárias estejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.  Problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.

> [!NOTE]
> Lembre-se de aceitar o prompt que pergunta se você deseja que o Hub de comentários acesse sua pasta documentos (selecione **Sim** quando solicitado).

## <a name="note-for-developers"></a>Observação para desenvolvedores

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando compilações internas do HoloLens.  Confira a [documentação do desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com compilações internas do HoloLens.  Você pode usar as mesmas compilações do Unity e do Visual Studio que já está usando para o desenvolvimento do HoloLens.

## <a name="stop-receiving-insider-builds"></a>Parar de receber compilações do insider

Se você não deseja mais receber compilações internas do Windows Holographic, pode recusar quando o seu HoloLens está executando uma compilação de produção ou pode [recuperar seu dispositivo](hololens-recovery.md) usando o complemento de recuperação avançada para recuperar seu dispositivo para uma versão não Insider do Windows Holographic.

> [!CAUTION]
> Há um problema conhecido em que os usuários que cancelam o registro do insider Preview são criados após a reinstalação manual de uma nova versão de visualização que teria uma tela azul. Depois, eles devem recuperar manualmente seu dispositivo. Para obter detalhes completos sobre se você for afetado ou não, veja mais sobre esse [problema conhecido](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Para verificar se o seu HoloLens está executando uma compilação de produção:

1. Vá para **configurações > > do sistema** e localize o número da versão.

1. [Consulte as notas de versão para obter os números de Build de produção](hololens-release-notes.md).

Para recusar compilações internas:

1. Em um HoloLens executando uma compilação de produção, vá para **configurações > atualização & segurança > programa Windows Insider** e selecione **parar compilações do insider**.

1. Siga as instruções para recusar seu dispositivo.
