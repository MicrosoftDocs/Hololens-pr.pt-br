---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar as builds do Insider e fornecer comentários valiosos para a próxima grande atualização do sistema operacional para o HoloLens.
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
ms.sourcegitcommit: ad725427c2c88e73df2e5753001a26502b2327de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474836"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às versões mais recentes do Insider Preview para o HoloLens! É simples começar e [fornecer](hololens-insider.md#start-receiving-insider-builds) comentários valiosos para a próxima grande atualização do sistema operacional para o HoloLens.

## <a name="windows-insider-release-notes"></a>Notas de versão do Windows Insider

Estamos animados para começar a iniciar a versão de novos recursos para o Windows Insiders novamente. As novas versões serão usadas no Canal de Dev para as atualizações mais recentes. Continuaremos a atualizar essa página à medida que adicionarmos mais recursos e atualizações às nossas builds do Windows Insider.  Fique animado e pronto para misturar essas atualizações em sua realidade.

Essa atualização de recursos contém recursos para dois públicos-alvo. Recursos que podem ser usados por qualquer pessoa em um dispositivo pelo usuário final e novas opções de gerenciamento de dispositivos que podem ser configuradas por administradores de IT. A tabela de recursos abaixo especifica as audiências com quem poderá usar cada novo recurso. Se você for um administrador de TI, confira nosso Administrador de [TI - Lista de](#it-admin---update-checklist) verificação de atualização

> [!IMPORTANT]
> Se você estava usando anteriormente o aplicativo Configurações ou o aplicativo Microsoft Edge em um Quiosque, substituímos esses aplicativos por novos aplicativos que usam uma ID de aplicativo diferente. Recomendamos que você leia [Novos AUMIDs para novos aplicativos no modo Quiosque abaixo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Isso garantirá que você continue a ter o aplicativo Configurações em seu Quiosque ou incluirá o novo aplicativo do Microsoft Edge.

<br>

| Nome do Recurso                                              | Descrição breve                                                                      | Público-alvo | Disponível na com build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Novo Microsoft Edge](#introducing-the-new-microsoft-edge) | O novo Microsoft Edge baseado em Chromium agora está disponível para o HoloLens 2                         | Usuário Final | 20279.1006 |
| [WebXR e Visualizador 360](#webxr-and-360-viewer)             | Experimente experiências imersivas da Web e reprodução de vídeo 360                                           | Usuário Final | 20289.1000 |
| [Novo aplicativo configurações](#new-settings-app)                     | O aplicativo de Configurações herdado está sendo substituído por uma versão atualizada por novos recursos e configurações | Usuário Final | 20279.1006 |
| [Exibir calibragem de cores](#display-color-calibration)   | Selecione um perfil de cor alternativo para a exibição do HoloLens 2                                | Usuário Final | 20293.1000 |
| [Se picker de aplicativo padrão](#default-app-picker)                 | Escolha qual aplicativo deve ser lançado para cada arquivo ou tipo de link                                      | Usuário Final | 20279.1006 |
| [Por controle de volume de aplicativo](#per-app-volume-control) |  Controlar o volume do nível do aplicativo independentemente do volume do sistema | Usuário Final | 20293.1000 |
| [Aplicativo Web do Office](#office-web-app)                         | Um atalho para o aplicativo Web do Office agora está listado em "Todos os aplicativos"                                   | Usuário Final | 20279.1006 |
| [Passar o dedo para digitar](#swipe-to-type)                           | Use a ponta do dedo para "passar o dedo" palavras no teclado holográfico                        | Usuário Final | 20279.1006 |
| [Menu De energia a partir de Iniciar](#power-menu-from-start) | No Menu Iniciar, reinicie e desligue o dispositivo HoloLens | Usuário Final | 20293.1000 |
| [Vários usuários listados na tela Entrar](#multiple-users-listed-on-sign-in-screen) | Exibir várias contas de usuário na tela Entrar | Usuário Final | 20293.1000 |
| [Suporte a microfone externo USB-C](#usb-c-external-microphone-support) | Use microfones USB-C para aplicativos e/ou Assistência Remota.| Usuário Final | 20279.1006 |
| [Logon automático do visitante para quiosques](#visitor-auto-logon-for-kiosks)                          | Habilita o logon automático em contas de visitante a serem usadas para modos de Quiosque.                         | Administrador de TI | 20279.1006                 |
| [Novos AUMIDs para novos aplicativos no modo Quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs para novos aplicativos de Configurações e Borda | Administrador de TI | 20279.1006 |
| [Entrega de falha do modo Quiosque aprimorado](#kiosk-mode-behavior-changes-for-handling-of-failures) | O modo de quiosque procura o Acesso Atribuído Global antes do menu iniciar vazio. | Administrador de TI | 20279.1006 |
| [New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20+ novas ConfiguraçõesURIs para configurações/política PageVisibilityList | Administrador de TI | 20289.1000 |
| [Configurar Diagnóstico de Fallback](#configuring-fallback-diagnostics-via-settings-app) | Definindo o comportamento de diagnóstico de fallback no aplicativo de configurações | Administrador de TI | 20279.1006 |
| [Compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices) | Compartilhar arquivos ou URLs de um HoloLens para um computador | Todas | 20279.1006 |
| [Novo solução de problemas de atualização do sistema operacional](#new-os-update-troubleshooter) | Novo solução de problemas em Configurações para atualizações do sistema operacional | Administrador de TI | 20279.1006 |
| [Visualização de Otimização de Entrega](#delivery-optimization-preview) | Reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens | Administrador de TI | 20301.1000 |
| [Melhorias e correções na atualização](#improvements-and-fixes-in-the-update) | Correções adicionais na atualização. | Todas | 20279.1006 |

### <a name="it-admin---update-checklist"></a>Administrador de IT - Lista de verificação de atualizações

Essa lista de verificação ajudará você a conhecer os novos itens que os recursos que estão sendo adicionados nesta atualização de recursos que podem afetar suas configurações atuais de gerenciamento de dispositivos ou novos recursos que você pode querer começar a usar.

#### <a name="updates-to-kiosk-mode"></a>Atualizações no modo Quiosque

[**Novos AUMIDs para novos aplicativos no modo Quiosque**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Se você estava usando anteriormente o aplicativo Configurações ou o aplicativo Microsoft Edge em um Quiosque, substituímos esses aplicativos por novos aplicativos que usam uma ID de aplicativo diferente. Recomendamos que você leia [Novos AUMIDs para novos aplicativos no modo Quiosque abaixo.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Isso garantirá que você continue a ter o aplicativo Configurações em seu Quiosque ou incluirá o novo aplicativo do Microsoft Edge.

Essas alterações podem ser feitas agora e implantadas em todos os dispositivos e permitem uma transição mais suave na atualização.

[**Logon automático do visitante para quiosques**](#visitor-auto-logon-for-kiosks)

Os visitantes agora podem ser conectados automaticamente em um Quiosque. Esse comportamento está on por padrão, mas pode ser gerenciado e desabilitado.

[**Entrega de falha do modo Quiosque aprimorado**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Se a associação de grupo do AAD do usuário AAD não for determinada com êxito, a configuração de quiosque global será usada para o menu iniciar (se presente) caso contrário, o usuário será apresentado com o menu inicial vazio. Embora o menu inicial vazio não seja uma configuração que você possa definir diretamente, essa nova manipulação pode ser algo para informar ao seu departamento de suporte se você está usando Quiosques, pois isso pode se aplicar às suas configurações ou talvez você queira fazer novos ajustes nas configurações de acesso atribuídas.

#### <a name="updates-to-page-settings-visibility"></a>Atualizações para Visibilidade das Configurações da Página

[**New SettingsURIs for Page Settings Visibility**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

SE você estiver usando a [Visibilidade](settings-uri-list.md) de Configurações de Página no momento, talvez você queira fazer ajustes nas URIs existentes que você permitiu ou bloqueou.

#### <a name="updates-for-your-wdac-policy"></a>Atualizações para sua política do WDAC

Se você estava bloqueando anteriormente o Microsoft Edge via WDAC, você vai querer atualizar sua política do WDAC. Revise [o seguinte e](#using-wdac-to-block-new-microsoft-edge) use o código de exemplo fornecido.

#### <a name="enable-new-endpoints-for-edge"></a>Habilitar novos pontos de extremidade para Borda

Se você tiver uma infraestrutura que envolva a configuração de pontos de extremidade de rede, como proxy ou firewall, [habilita](#managing-endpoints-for-the-new-microsoft-edge) esses novos pontos de extremidade para o novo aplicativo do Microsoft Edge.

#### <a name="newly-configurable-items"></a>Itens configuráveis recentemente

- [Configurar Diagnóstico de Fallback](#configuring-fallback-diagnostics-via-settings-app)
  - Você pode configurar se e quem pode coletar Diagnóstico de Fallback.
- [Compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices)
  - Você pode desabilitar o novo recurso de compartilhamento próximo.
- [Configurando configurações de política para o novo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Revise as novas configurações disponíveis para o Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nova ferramenta de diagnóstico

- [Novo solução de problemas de atualização do sistema operacional](#new-os-update-troubleshooter)
  - Coletar logs relacionados a atualizações do sistema operacional

### <a name="introducing-the-new-microsoft-edge"></a>Apresentando o novo Microsoft Edge

![Animação do logotipo herddo do Microsoft Edge para o novo logotipo do Microsoft Edge](images/new-edge.gif)

O novo Microsoft Edge adota o projeto de código aberto [do Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para criar melhor compatibilidade para clientes e menos fragmentação da Web para desenvolvedores web.

Com essa visualização do Insider, o novo Microsoft Edge está disponível para clientes do HoloLens 2 pela primeira vez! Embora o novo Microsoft Edge eventualmente substitua o Microsoft Edge herdada no HoloLens 2, ambos os navegadores estão disponíveis no momento para Insiders. Compartilhe comentários e bugs com nossa equipe por meio do recurso **Enviar Comentários** no novo Microsoft Edge ou por meio do Hub [de Feedback.](hololens-feedback.md)

![Nova captura de tela do Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Iniciando o novo Microsoft Edge

Há duas versões do Microsoft Edge disponíveis para Insiders: o novo ícone do Microsoft Edge novo Microsoft Edge (representado por um ícone de redemoinho azul e verde) e o Microsoft Edge herdado (representado pelo ícone ![ ](images/new_edge_logo.png) "e" branco). O novo Microsoft Edge é fixado no menu Iniciar e será aberto automaticamente quando você ativar um link da Web. Se você quiser reverter o uso do Microsoft Edge herdado como navegador da Web padrão, consulte as instruções abaixo para [redefinir](#default-app-picker)aplicativos padrão .

> [!NOTE]
> Quando você iniciar pela primeira vez o novo Microsoft Edge no HoloLens 2, suas configurações e dados serão importados do Microsoft Edge herdada. Se você continuar a usar o Microsoft Edge herdado depois de iniciar o novo Microsoft Edge, esses novos dados não serão sincronizados do Microsoft Edge herdado para o novo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configurando configurações de política para o novo Microsoft Edge

O novo Microsoft Edge oferece aos administradores de IT um conjunto muito mais amplo de políticas de navegador no HoloLens 2 do que estavam disponíveis anteriormente com o Microsoft Edge herdado.

Aqui estão alguns recursos úteis para saber mais sobre como gerenciar configurações de política para o novo Microsoft Edge:

- [Definir as configurações de política do Microsoft Edge com o Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mapeamento de políticas do Microsoft Edge Legacy para o Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapeamento de políticas do Google Chrome para o Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentação [completa do Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Devido ao volume de políticas de navegador suportadas pelo novo Microsoft Edge, nossa equipe não consegue garantir que cada nova política funcione no HoloLens 2. No entanto, testamos e confirmamos que o novo equivalente do Microsoft Edge de cada política herdada do Microsoft Edge anteriormente suportada no HoloLens 2 funciona como esperado. Consulte o mapeamento de política do [Microsoft Edge Legacy to Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) para encontrar o novo equivalente do Microsoft Edge de cada política de navegador herdada do Microsoft Edge que você estava usando com o HoloLens 2.
>
> Há pelo menos duas novas políticas do Microsoft Edge que sabemos que *não funcionarão* com o HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>O que esperar do novo Microsoft Edge no HoloLens 2

Como o novo Microsoft Edge é um aplicativo Win32 nativo com uma nova camada de adaptador UWP permitindo que ele seja executado em dispositivos somente UWP como o HoloLens 2, alguns recursos podem não estar disponíveis imediatamente. Ofereceremos suporte a novos cenários e recursos nos próximos meses, portanto, verifique esse espaço para obter informações atualizadas.

**Cenários e recursos esperados para funcionar:**
- Experiência de primeira, entrar no perfil e sincronizar
- Sites devem renderizar e se comportar conforme esperado
- A maioria das funcionalidades do navegador (Favoritos, Histórico etc.) deve funcionar conforme o esperado
- Modo escuro
- Instalar aplicativos Web no dispositivo
- Instalando extensões (saiba se você usa extensões que não funcionam corretamente no HoloLens 2)
- Exibindo e marcando um PDF
- Som espacial de uma única janela do navegador
- Atualização automática e manual do navegador
- Salvar um PDF do menu Imprimir (usando a opção "Salvar em PDF" )
- Extensão do Visualizador WebXR e 360
- Restauração de conteúdo para a janela correta, ao navegar por várias janelas colocadas em seu ambiente

**Cenários e recursos não esperados para funcionar:**
- Som espacial de várias janelas com fluxos de áudio simultâneos
- "Veja, diga".
- Impressão

**Principais problemas conhecidos do navegador:**
- Wi-Fi configurações de proxy, que são políticas de proxy que visam conexões Wi-Fi individuais, atualmente não funcionam com o novo Microsoft Edge. Estamos trabalhando ativamente para desbloquear esse problema antes do lançamento público da atualização do sistema operacional.
- A visualização da lupa no teclado holográfico foi desabilitada para o novo Microsoft Edge. Esperamos reenvelar esse recurso em uma atualização futura, uma vez que a ampliação está funcionando corretamente.
- Dois caracteres no teclado japonês não funcionam conforme o esperado no novo Microsoft Edge. Esse problema foi causado por raiz e deve ser corrigido em breve.
- Os links da Web no aplicativo da Microsoft Store podem não iniciar o navegador
- O áudio pode ser reproduzir da janela do navegador errada se você tiver outra janela do navegador aberta e ativa. Você pode resolver esse problema fechando a outra janela ativa que não deveria estar tocando áudio.
- Ao tocar áudio de uma janela do navegador no modo ["Siga-me",](hololens2-basic-usage.md#follow-me-stop-following)o áudio continuará a ser gravado se você desabilitar o modo "Siga-me". Você pode resolver esse problema interrompendo a reprodução de áudio antes de desabilitar o modo "Siga-me" ou fechando a janela com o **botão X.**
- Interagir com janelas ativas do Microsoft Edge pode fazer com que outras janelas de aplicativo 2D inativam inesperadamente. Você pode reativar essas janelas interagindo com elas novamente.
- Abrir um link da Web de outro aplicativo ou determinados tipos de documentos, como PDFs, pode fazer com que uma segunda guia em branco seja aberta no navegador (além da nova guia criada com o conteúdo do link da Web ou do link de arquivo). Você pode resolver esse problema fechando a guia em branco adicional.

#### <a name="microsoft-edge-insider-channels"></a>Canais do Microsoft Edge Insider

A equipe do Microsoft Edge disponibiliza três canais de visualização para a comunidade do Edge Insider: Beta, Dev e Canary. Instalar um canal de visualização não desinstala a versão lançada do Microsoft Edge no HoloLens 2 e você pode instalar mais de um ao mesmo tempo. 

Visite a [homepage do Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para saber mais sobre a comunidade do Edge Insider. Para saber mais sobre os diferentes canais do Edge Insider e começar, visite a página de [download do Edge Insider](https://www.microsoftedgeinsider.com/download).

Há alguns métodos disponíveis para instalar canais do Microsoft Edge Insider no HoloLens 2:

**Instalação direta no dispositivo (atualmente disponível apenas para dispositivos nãomanageados)**
  1. Em seu HoloLens 2, visite a página de [download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão Baixar para HoloLens 2** para o canal Edge Insider que você deseja instalar.
  1. Iniciar o arquivo .msix baixado da fila de download de Borda ou da pasta "Downloads" do dispositivo (usando o Explorador de Arquivos).
  1. [O instalador de aplicativos](app-deploy-app-installer.md) será acionada.
  1. Selecione o **botão Instalar.**
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge Beta, **** Dev ou Canary como uma entrada separada na lista Todos os aplicativos do menu Iniciar.

**Instalar por computador com o Windows Device Portal (exige que o modo de [desenvolvedor](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) seja habilitado no HoloLens 2)**
  1. Em seu computador, visite a página de [download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão de seta** para baixo ao lado do botão "Baixar para Windows 10" para o canal Edge Insider que você deseja instalar.
  1. Selecione **HoloLens 2** no menu suspenso.
  1. Salve o arquivo .msix na pasta "Downloads" do computador (ou outra pasta que você pode encontrar facilmente).
  1. Use [o Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) em seu computador para instalar o arquivo .msix baixado no HoloLens 2.
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge Beta, **** Dev ou Canary como uma entrada separada na lista Todos os aplicativos do menu Iniciar.

> [!NOTE]
> Durante essa visualização do Windows Insider para o HoloLens 2, a versão do Microsoft Edge em seu dispositivo pode ser maior do que as disponíveis em alguns (ou todos) dos canais do Microsoft Edge Insider. Isso é para garantir que novos recursos e correções voltadas especificamente para o navegador da Web no HoloLens 2 estão chegando aos nossos Windows Insiders o mais rápido possível. Logo após o lançamento público da próxima atualização do Windows, os builds do canal Do Microsoft Edge Insider superarão e permanecerão à frente da versão do Microsoft Edge em seu HoloLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Usando o WDAC para bloquear o novo Microsoft Edge

Para os administradores de TI que procuram atualizar a política [do WDAC](windows-defender-application-control-wdac.md) para bloquear o novo aplicativo do Microsoft Edge, você precisará adicionar o seguinte à sua política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerenciando pontos de extremidade para o novo Microsoft Edge

Alguns ambientes podem ter restrições de rede para considerar. Para garantir uma experiência suave com o novo Edge, [habilita esses pontos de extremidade da Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os pontos de extremidade disponíveis no momento [para o HoloLens](hololens-offline.md).

### <a name="webxr-and-360-viewer"></a>WebXR e Visualizador 360

*Adicionado à com build 20289.1000 do Windows Insider*

O novo Microsoft Edge inclui suporte para WebXR, que é o novo padrão para criar experiências da Web imersivas (substituindo WebVR). Muitas experiências imersivas da Web foram projetadas com o VR em mente (eles substituem seu campo de exibição por um ambiente virtual), mas essas experiências também são suportadas pelo HoloLens 2. O padrão WebXR também permite experiências da Web imersivas de realidade aumentada e misturada que usam seu ambiente físico. À medida que os desenvolvedores passam mais tempo com o WebXR, antecipamos que novas experiências imersivas de realidade aumentada e misturada chegarão para os clientes do HoloLens 2 tentarem!

A extensão do Visualizador 360 é criada no WebXR e é instalada automaticamente junto com o novo Microsoft Edge no HoloLens 2. Essa extensão da Web oferece a capacidade de imersão em vídeos de 360 graus. O YouTube oferece a maior seleção de 360 vídeos, portanto, incentivamos você a começar por lá.

#### <a name="how-to-use-webxr"></a>Como usar o WebXR

1. Navegue até um site com suporte a WebXR.
1. Selecione o **botão Inserir VR** no site. O local e a representação visual deste botão podem variar por site, mas pode ser semelhante a:

    ![Exemplo do botão Enter VR](images/75px-enter-vr.png)

1. Na primeira vez que você tentar iniciar uma experiência WebXR em um domínio específico, o navegador solicitará consentimento para inserir uma exibição imersiva, selecione **Permitir**.
1. Use [os gestos do HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular a experiência.
1. Se a experiência não tiver um **botão Sair,** use o gesto [Iniciar](hololens2-basic-usage.md#start-gesture) para retornar para casa.

**Exemplos WebXR recomendados**
- Visualizador 360 (consulte a próxima seção)
- [Dinossauro XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [Tinta WebXR](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Como usar o Visualizador 360

1. Navegue até um vídeo de 360 graus no YouTube.
1. No quadro de vídeo, selecione o botão de fone de ouvido de realidade misturada:

    ![Botão para ativar o Visualizador 360](images/enter-360-viewer.jpg)

1. Na primeira vez que você tentar iniciar o Visualizador 360 em um domínio específico, o navegador solicitará consentimento para inserir um exibição imersivo. Selecione **Permitir**.
1. [Toque de ar](hololens2-basic-usage.md#select-using-air-tap) para trazer os controles de reprodução. Use [raios de mão](hololens2-basic-usage.md#select-using-air-tap) e toque de ar para reproduzir/pausar, pular para frente/para trás, ativar/desativar legendas ou interromper a experiência (que sai do exibição imersivo). Os controles de reprodução desaparecerão após alguns segundos de inatividade.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principais problemas conhecidos do WebXR e do Visualizador 360
- Dependendo da complexidade da experiência WebXR, a taxa de quadros pode soltar ou gaguejar.
- O suporte para juntas de mão articuladas no WebXR não está habilitado por padrão. Os desenvolvedores podem habilitar o suporte por meio `edge://flags` da aplicação de "WebXR Hand Input".
- Ao sair de uma experiência do Visualizador WebXR ou 360, pode levar 30 segundos ou mais para os hologramas na casa da realidade misturada reaparecerem.
- 360 vídeos de sites diferentes do YouTube podem não funcionar conforme o esperado.
- As legendas estão desabilitadas no Visualizador 360 no HoloLens 2. Planejamos habilitar esse recurso em uma atualização futura.
- Pausar um vídeo no Visualizador 360 interrompe a renderização do vídeo (mas selecionar o botão reproduzir corretamente retoma a reprodução).
- O botão "próximo vídeo" no Visualizador 360 não funciona no momento.
- Você pode reproduzir vídeos 2D em um modo imersivo de "teatro", mas a taxa de quadros pode ser inferior a 30 fps.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo comentários sobre WebXR e Visualizador 360

Compartilhe comentários e bugs com nossa equipe por meio do **recurso Enviar Comentários** no novo Microsoft Edge.

### <a name="new-settings-app"></a>Novo aplicativo configurações

Com essa versão, apresentamos uma nova versão do aplicativo Configurações. O novo aplicativo Configurações inclui novos recursos e configurações expandidas para o HoloLens 2 nas seguintes áreas: Som, Power & sleep, Rede & Internet, Aplicativos, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Como o novo aplicativo Configurações é diferente do aplicativo de Configurações herdado, todas as janelas de Configurações que você colocou anteriormente ao redor do seu ambiente serão removidas após a atualização.

![Página inicial do aplicativo Novas Configurações](images/new-settings-app.png)

**Novos recursos e configurações**
- Pesquisa de configurações: pesquise as configurações da página inicial Configurações usando palavras-chave ou o nome da configuração.
- Som > sistema:
  - Dispositivos de áudio de entrada e saída: escolha independentemente seus dispositivos de áudio de entrada e saída (por exemplo, ouvir áudio por meio de Bluetooth fones de ouvido ou usar um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Bluetooth microfones não são suportados pelo HoloLens 2.
  - Volume do aplicativo: ajuste independentemente o volume de cada aplicativo. Consulte [por controle de volume do aplicativo](#per-app-volume-control).
- Sistema > Power &: escolha quando o dispositivo deve dormir após um período de inatividade.
- System > Battery: habilitar manualmente o modo de economia de bateria ou definir um limite de bateria no qual o modo de economia de bateria de ponto é ativado automaticamente.
- Dispositivos > USB: você pode desabilitar conexões USB por padrão.
- Rede & Internet:
  - Os adaptadores Ethernet USB-C agora aparecerão em Rede & Internet.
  - As configurações do adaptador Ethernet USB-C agora estão disponíveis, incluindo seu endereço IP.
  - Agora você pode habilitar o modo de avião no HoloLens 2.
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Para obter mais informações, [consulte Se picker de aplicativo padrão](#default-app-picker).
- Contas > Outros usuários: os proprietários de dispositivos podem adicionar usuários, atualizar usuários padrão para proprietários de dispositivos, fazer downgrade de proprietários de dispositivos para usuários padrão e remover usuários.
- Facilidade de Acesso: alterar o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- Janelas de configurações colocadas anteriormente serão removidas (consulte a observação acima).
- Você não pode mais renomear seu dispositivo com o aplicativo Configurações. Os administradores de IT podem renomear dispositivos usando o modelo de nome do dispositivo [Windows Autopilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) ou o nó [MDM DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- A página Ethernet mostra sempre um dispositivo Ethernet virtual ("UsbNcm").
- O uso da bateria para o novo Microsoft Edge pode não ser preciso, devido à sua natureza como um aplicativo de área de trabalho Win32 suportado por uma camada de adaptador UWP (nenhuma correção prevista em breve).

### <a name="display-color-calibration"></a>Exibir calibragem de cores

*Adicionado à com build 20293.1000 do Windows Insider*

Com essa nova configuração, você pode selecionar um perfil de cor alternativo para a exibição do HoloLens 2. Isso pode ajudar as cores a aparecerem mais precisas, especialmente em níveis de brilho de exibição mais baixos. A calibragem de cores de exibição pode ser encontrada no aplicativo Configurações, na página Calibragem > Sistema.

> [!NOTE]
> Como essa configuração salva um novo perfil de cor no firmware de exibição, é uma configuração por dispositivo (e não exclusiva para cada conta de usuário).

#### <a name="how-to-use-display-color-calibration"></a>Como usar a calibragem de cores de exibição

1. Iniciar o **aplicativo Configurações** e navegue até **System > Calibragem**.
1. Em **Calibragem de cores de**exibição, selecione o botão Executar **calibragem de cores de** exibição.
1. A experiência de calibragem de cores de exibição será lançada e o incentivará a garantir que o visor está na posição correta.
1. Depois de prosseguir pelas caixas de diálogo de instrução, sua exibição será automaticamente esmaecida para 30% de brilho.
    > [!TIP]
    > Se você estiver com problemas para ver a cena esmaecida em seu ambiente, poderá ajustar manualmente o nível de brilho do HoloLens 2 usando os botões de brilho no lado esquerdo do dispositivo.
1. Selecione os botões 1 a 6 para testar instantaneamente cada perfil de cores e encontre um que pareça melhor para seus olhos (isso geralmente significa que o perfil que ajuda a cena a aparecer mais neutra, com o padrão de escala de cinza e os tons de pele olhando conforme o esperado.)

    ![Exibir cena de calibragem de cores](images/color-cal-ui.png)
    
1. Quando você estiver satisfeito com o perfil selecionado, selecione o **botão Salvar** & Sair
1. Se você preferir não fazer alterações, selecione o botão Cancelar & **Sair** e suas alterações serão revertidas

> [!TIP]
> Aqui estão algumas dicas úteis para ter em mente ao usar a configuração de calibragem de cores de exibição:
> - Você pode executar a calibragem de cores de exibição a partir de Configurações sempre que quiser
> - Se alguém no dispositivo tiver usado anteriormente a configuração para alterar perfis de cor, a data/hora da alteração mais recente será refletida na página Configurações
> - Quando você executar a calibragem de cores de exibição, o perfil de cores que foi salvo anteriormente será realçado e o Perfil 0 não aparecerá (como o Perfil 0 representa o perfil de cores original da exibição)
> - Se você quiser reverter para o perfil de cores original da exibição, você pode fazê-lo na página Configurações (consulte como redefinir o perfil [de cor](#how-to-reset-color-profile))

#### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cores

Se você não estiver satisfeito com o perfil de cor personalizado salvo no HoloLens 2, poderá restaurar o perfil de cores original do dispositivo:
1. Iniciar o **aplicativo Configurações** e navegue até **System > Calibragem**.
1. Em **Calibragem de cores de**exibição, selecione o botão **Redefinir para perfil de cor** padrão.
1. Quando a caixa de diálogo for aberta, selecione **Reiniciar** se você estiver pronto para reiniciar o HoloLens 2 e aplicar suas alterações.

#### <a name="top-display-color-calibration-known-issues"></a>Principais problemas conhecidos de calibragem de cores de exibição

- Na página Configurações, a cadeia de caracteres de status que informa quando o perfil de cor foi alterado pela última vez estará desregregada até que você recarregue essa página de Configurações.
    - Solução alternativa: selecione outra página Configurações e selecione a página Calibragem.

### <a name="default-app-picker"></a>Se picker de aplicativo padrão

Quando você ativa um hiperlink ou abre um tipo de arquivo com mais de um aplicativo instalado, que oferece suporte a ele, você verá uma nova janela aberta solicitando que você selecione qual aplicativo instalado deve manipular o arquivo ou o tipo de link. Nesta janela, você também pode optar por fazer com que o aplicativo selecionado manipular o arquivo ou o tipo de link "Uma vez" ou "Sempre".

![Janela do se picker de aplicativos](images/default-app-picker.png)

Se você escolher "Sempre" mas depois quiser alterar qual aplicativo lida com um determinado arquivo ou tipo de link, você pode redefinir seus padrões salvos em **Configurações > Aplicativos**. Role até a parte inferior **** da página e selecione o botão Limpar em "Aplicativos padrão para tipos de arquivo" e/ou "Aplicativos padrão para tipos de link". Ao contrário da configuração semelhante em computadores desktop, você não pode redefinir padrões de tipo de arquivo individual.

### <a name="per-app-volume-control"></a>Por controle de volume de aplicativo

Agora, nesta com build do Windows Insider, os usuários podem ajustar manualmente o nível de volume de cada aplicativo. Isso permite que os usuários se concentrem melhor nos aplicativos necessários ou ouçam melhor ao usar vários aplicativos. Como a necessidade de desativar o volume de um aplicativo enquanto chama outra pessoa para assistência remota em outro.

Para definir o volume de um aplicativo individual, navegue até Configurações som do sistema e, em Opções de som **avançadas,** selecione Volume do aplicativo e  ->  ****  ->  **** **preferências de dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Aplicativo Web do Office

>[!NOTE]
>A partir da com build 20325.1000 do Windows Insider, o aplicativo Web do Office não será mais pré-instalado (e não será pré-instalado para a próxima versão pública da atualização do sistema operacional. Para instalar o aplicativo Web do Office, visite e selecione o botão https://www.office.com **App Available** ou **Install Office** na barra de endereços. Selecione **Instalar** para confirmar.

O aplicativo Web do Office foi adicionado à lista "Todos os aplicativos" no menu Iniciar. Esse aplicativo Web também pode ser fixado em Iniciar ou desinstalado. Como esse é um aplicativo Web, sua funcionalidade corresponde exatamente ao que você experimentaria visitando https://www.office.com . A funcionalidade do aplicativo Web do Office só estará disponível quando o HoloLens 2 tiver uma conexão de Internet ativa.

**Problema conhecido**
- Redefinir seu dispositivo removerá o aplicativo Web do Office

### <a name="swipe-to-type"></a>Passar o dedo para digitar

Alguns clientes acham mais rápido "digitar" em teclados virtuais, girando a forma da palavra que pretendem digitar e estamos visualizando esse recurso para o teclado holográfico. Você pode passar uma palavra por vez passando a ponta do dedo pelo plano do teclado holográfico, girando a forma da palavra e, em seguida, retirando a ponta do dedo do plano do teclado. Você pode passar o dedo as palavras de acompanhamento sem precisar pressionar a barra de espaço removendo o dedo do teclado entre palavras. Você vai saber que o recurso está funcionando se vir uma trilha de passar o dedo seguindo o movimento do dedo no teclado.

Observe que esse recurso pode ser complicado de usar e ser mestre devido à natureza de um teclado holográfico em que você não sente resistência ao dedo (ao contrário de uma exibição de telefone celular). Estamos avaliando esse recurso para lançamento público, portanto, seus comentários são importantes; se você achar o recurso útil ou se tiver comentários construtivos, nos avise por meio do [Hub de Feedback.](hololens-feedback.md)

### <a name="power-menu-from-start"></a>Menu De energia a partir de Iniciar

Um novo menu que permite que o usuário saia, desligue e reinicie o dispositivo. Um indicador na tela Inicial do HoloLens que mostra quando uma atualização do sistema está disponível.

#### <a name="how-to-use"></a>Como usar

1. Abra a tela Inicial do HoloLens usando o gesto [Iniciar](hololens2-basic-usage.md#start-gesture) ou dizendo "Vá para Iniciar".

2. Observe o ícone de reellipse (...) ao lado da imagem de perfil do usuário:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selecione a imagem de perfil de usuário usando suas mãos ou o comando de voz "Power".

4. Um menu aparece com opções para Sair, Reiniciar ou Desligar o dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Selecione as opções de menu para sair, reiniciar ou desligar o HoloLens. A opção Sair pode não estar disponível, se o dispositivo estiver definido para uma única conta [da Microsoft (MSA) ou conta local](hololens-identity.md).

6. Descarte o menu tocando em qualquer outro lugar ou fechando o menu Iniciar com o gesto Iniciar.

#### <a name="update-indicator"></a>Indicador de atualização

Quando uma atualização estiver disponível, o ícone de reellipse será iluminado para indicar que uma reinicialização instalará a atualização As opções de menu também mudam para refletir a presença da atualização.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela Entrar

Anteriormente, a tela Entrar mostrava apenas o usuário mais recentemente assinado, bem como um ponto de entrada "Outro usuário". Recebemos comentários do cliente de que isso não é suficiente se vários usuários entraram no dispositivo. Eles ainda eram necessários para retipo seu nome de usuário etc.

Introduzido nesta com build do Windows Insider, ao selecionar **Outro** usuário localizado à direita do campo de entrada pin, a tela Entrar exibirá vários usuários com já conectados ao dispositivo. Isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entre usando suas credenciais do Windows Hello. Um novo usuário também pode ser adicionado ao dispositivo a partir desta página Outros usuários por meio do **botão Adicionar conta.**

Quando estiver no menu Outros usuários, o botão Outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela Entrar para este usuário.

![Padrão da tela de login](./images/multiusers1.jpg)

<br>

![Tela de login de outros usuários](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Suporte a microfone externo USB-C

> [!IMPORTANT]
> Conectar um microfone USB não o **definirá automaticamente como o dispositivo de entrada**. Ao conectar um conjunto de fones de ouvido USB-C, os usuários observarão que o áudio do fone de ouvido será redirecionado automaticamente para os fones de ouvido, mas o sistema operacional do HoloLens prioriza a matriz de microfone interna acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

Os usuários podem selecionar microfones externos conectados USB-C usando o **painel Configurações** de som. Microfones USB-C podem ser usados para chamar, gravar etc.

Abra o **aplicativo Configurações** e selecione **Som do**  >  **Sistema**.

![Definições de Som](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com **Assistência Remota,** os usuários precisarão clicar no hiperlink "Gerenciar dispositivos de som".
>
> Em seguida, use o drop-down para definir o microfone externo como **Padrão** ou **Padrão de Comunicações.** Escolher **Padrão** significa que o microfone externo será usado em todos os lugares.
>
> Escolher **o Padrão** de Comunicações significa que o microfone externo será usado no Remote Assist e em outros aplicativos de comunicação, mas a matriz de microfone do HoloLens ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir o padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E o Bluetooth microfone?

Infelizmente, Bluetooth microfones ainda não são suportados no HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solução de problemas de microfones USB-C

Saiba que alguns microfones USB-C relatam-se incorretamente como microfone *e* alto-falante. Isso é um problema com o microfone e não com o HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

Em **Configurações**som do sistema , de definir explicitamente os  ->  ****  ->  **** alto-falantes **integrados (Driver de** Áudio de Recurso Analógico) como **o dispositivo padrão**. O HoloLens deve lembrar-se dessa configuração mesmo que o microfone seja removido e reconectado posteriormente.

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Logon automático do visitante para quiosques

Esse novo recurso permite que o logon automático em contas de visitante seja usado para modos de Quiosque.

Para uma configuração não AAD, para configurar um dispositivo para o logon automático do visitante:

1. Crie um pacote de provisionamento que:
    1. Configura as **configurações do Tempo de Execução/AssignedAccess** para permitir contas do Visitante.
    1. Opcionalmente, registra o dispositivo no MDM (configurações do tempo de **execução/Workplace/Enrollments)** para que ele possa ser gerenciado posteriormente.
    1. Não crie uma conta local
1. [Aplicar o pacote de provisionamento](hololens-provisioning.md).

Para uma configuração do AAD, os usuários podem alcançar algo semelhante a isso hoje sem essa alteração. Os dispositivos ingressados no AAD configurados para o modo quiosque podem entrar em uma conta de Visitante com um único toque de botão na tela de entrada. Depois de entrar na conta de visitante, o dispositivo não solicitará entrar novamente até que o Visitante seja explicitamente conectado no menu iniciar ou o dispositivo seja reiniciado.

O logon automático do visitante pode ser gerenciado por meio da [política OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizada:

- Valor de URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Política  | Descrição   | Configurações  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Permite que um visitante fazer logon automático em um Quiosque   | 1 (Sim), 0 (Não, padrão.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usar os novos aplicativos de Configurações e Borda nos modos de quiosque

Ao incluir aplicativos em [Quiosques,](hololens-kiosk.md)um administrador de IT geralmente adiciona o aplicativo ao Quiosque, mas usando a ID do Modelo de Usuário do Aplicativo (AUMID). Como o aplicativo Configurações e o aplicativo Microsoft Edge são considerados novos aplicativos e diferentes dos aplicativos mais antigos, os Quiosques que usam AUMIDs para esses aplicativos precisarão ser atualizados para usar o novo AUMID.

Ao modificar um Quiosque para incluir os novos aplicativos, recomendamos adicionar o novo AUMID, bem como deixar o antigo. Isso criará uma transição fácil quando os usuários atualizarem o sistema operacional e não precisarão receber novas políticas para continuar usando o Quiosque conforme o pretendido.

| Aplicativo                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicativo configurações antigas       | HolographicSystemSettings_cw5n1h2txyewy! Aplicativo            |
| Novo Aplicativo de Configurações       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicativo |
| Aplicativo antigo do Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Novo aplicativo do Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações no comportamento do modo quiosque para tratamento de falhas

Em versões mais antigas, se um dispositivo tivesse uma configuração de quiosque, que é uma combinação de acesso atribuído global e acesso atribuído ao membro do grupo AAD, se a determinação da associação ao grupo do AAD falhasse, o usuário verá o menu "[nada](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)mostrado no início ".

A partir do lançamento do Windows Insider, a experiência de quiosque fará fallback para a configuração de quiosque global (se presente) em caso de falhas durante o modo de quiosque de grupo do AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>New SettingsURIs for Page Settings Visibility

No [Windows Holographic, versão 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) adicionamos a política [Configurações/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas no aplicativo Configurações. PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema, ou para isso, para todas as páginas, exceto aquelas especificadas.

Se você visitar [a Visibilidade de](settings-uri-list.md)Configurações de Página, poderá encontrar instruções para usar esse CSP e a lista de URIs disponíveis em versões anteriores.

Em builds do Windows Insider, estamos expandindo na lista de URIs de configurações disponíveis, que os administradores de IT podem gerenciar. Algumas dessas URIs são para áreas recém-disponíveis no novo aplicativo Configurações. Se você estiver usando a política Configurações/PageVisibilityList, revise a lista a seguir e ajuste suas páginas permitidas ou bloqueadas conforme necessário.

> [!NOTE]
> **Preterido: ms-settings:network-proxy**
>
> Uma página de configurações é preterida nessas builds mais novas. A página & Proxy da **Internet**antiga não está mais disponível como uma  >  **** configuração global. As novas configurações de proxy por conexão podem ser encontradas em **Network & Internet**  >  **Wi-Fi**  >  **Properties** ou Network **& Internet**  >  **Ethernet**  >  **Properties**.

<br>

| Página de configurações                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplicativos > aplicativos & recursos                               | `ms-settings:appsfeatures`                         |
| Aplicativos > aplicativos & recursos > opções avançadas          | `ms-settings:appsfeatures-app`                     |
| Aplicativos > mapas offline                                  | `ms-settings:maps`                                 |
| Aplicativos > mapas offline > Baixar mapas                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > Mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Modo & internet > de avião                   | `ms-settings:network-airplanemode`                 |
| Privacidade > Geral                                    | `ms-settings:privacy-general`                      |
| Privacidade > tinta & personalização de digitação             | `ms-settings:privacy-speechtyping`                 |
| Movimento > privacidade                                     | `ms-settings:privacy-motion`                       |
| Privacidade > de captura de tela                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Privacidade > Capturas de tela e aplicativos                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Bateria > sistema                                     | `ms-settings:batterysaver`                         |
| Bateria > sistema                                     | `ms-settings:batterysaver-settings`                |
| Som > sistema                                       | `ms-settings:sound`                                |
| Sistema > som > de aplicativo e preferências de dispositivo | `ms-settings:apps-volume`                          |
| Sistema > som > Gerenciar dispositivos de som              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Hora & Idioma > Data & hora                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Idioma & tempo > idioma                           | `ms-settings:language`                             |
| Idioma & tempo > idioma                           | `ms-settings:regionlanguage-languageoptions`       |
| Atualizar & segurança > redefinir & recuperação               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URIs atualizados

Anteriormente, as duas URIs a seguir não levariam um usuário diretamente para as páginas indicadas, mas apenas bloqueariam a página de atualizações principais. Os itens a seguir foram atualizados para direcionar para suas páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurando o Diagnóstico de Fallback por meio do aplicativo Configurações

Agora, no Aplicativo de Configurações, um usuário pode configurar o comportamento do [Diagnóstico de Fallback.](hololens-diagnostic-logs.md) Na página Configurações do aplicativo navegue até **Solução**de Problemas  ->  **de** Privacidade para configurar essa configuração.

> [!NOTE]
> Se houver política MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.  

### <a name="share-things-with-nearby-devices"></a>Compartilhar coisas com dispositivos próximos

Compartilhar coisas próximas por dispositivos Windows 10, incluindo computadores e outros dispositivos HoloLens 2 que executam o HoloLens Insider cria 20279.1006+. Você pode experimentar em **Configurações**Experiências Compartilhadas do Sistema para compartilhar arquivos ou URLs de um  ->  ****  ->  **** HoloLens para um computador. Para obter mais detalhes, leia mais sobre como [compartilhar coisas com dispositivos próximos no Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esse recurso pode ser gerenciado por [meio de Conectividade/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-update-troubleshooter"></a>Novo solução de problemas de atualização do sistema operacional

Além dos solução de problemas anteriores no aplicativo Configurações, um novo solucionador de problemas foi adicionado com a adição do novo aplicativo configurações para atualizações do sistema operacional. Navegue até **Configurações Atualizar**Segurança  ->  ** &amp; Solução**de Problemas  >  ****  >  **do Windows Update** e selecione **Iniciar**. Isso permite coletar rastreamentos ao reproduzir seu problema com atualizações do sistema operacional para ajudar melhor na solução de problemas com sua TI ou suporte.

### <a name="delivery-optimization-preview"></a>Visualização de Otimização de Entrega

Com essa atualização do HoloLens Insider, o Windows Holographic for Business permite uma visualização antecipada para configurações de otimização de entrega para reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa dessa funcionalidade juntamente com a configuração de rede recomendada está disponível aqui: Otimização de Entrega para atualizações do [Windows 10.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

As configurações a seguir são habilitadas como parte da superfície de gerenciamento e podem ser [configuradas a partir do Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

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

Algumas advertências sobre essa oferta de visualização:

- O suporte ao HoloLens é limitado nessa visualização apenas para atualizações do sistema operacional.
- O Windows Holographic for Business só dá suporte a modos de download HTTP e downloads de um ponto de extremidade [do Cache Conectado da Microsoft;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Os modos de download ponto a ponto e as atribuições de grupo não são suportados para dispositivos HoloLens no momento.
- O HoloLens não dá suporte à otimização de implantação ou entrega para pontos de extremidade do Windows Server Update Services.
- A solução de problemas exigirá diagnósticos no servidor de Cache Conectado ou **** coletará um rastreamento no HoloLens no HoloLens por meio da Atualização de Configurações & Solução de Problemas de Segurança do  >  ****  >   ****  >   **Windows Update.**

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- [O diagnóstico offline também](hololens-diagnostic-logs.md#offline-diagnostics) incluirá informações adicionais do dispositivo para o número de série e a versão do sistema operacional.

### <a name="known-issues-and-work-around"></a>Problemas conhecidos e trabalhar ao redor

#### <a name="pairing-hololens-to-pc"></a>Emparelhamento do HoloLens com o computador

Antes da com build do Windows Insider 20325.1000, quando um usuário tinha definido credenciais de emparelhamento no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) e atualizado para as builds do Windows Insider, suas credenciais de conjunto anterior para emparelhar o HoloLens com o computador para fins de implantação e depuração de aplicativos, como por meio do Visual Studio, não funciona mais. A com build 20325.1000 do Windows Insider corrige esse problema e não exige ações adicionais para continuar usando o portal do dispositivo.

Os usuários que piscaram seus dispositivos com uma com build [do Insider](#ffu-download-and-flash-directions) agora precisarão reaflar seus dispositivos (para 20325.1000+ ou uma com build ga) para emparelhar seus dispositivos com seu computador.

Os usuários que não se registraram no Windows Insiders e que receberão a atualização de recursos quando ela estiver geralmente disponível não serão afetados.


## <a name="start-receiving-insider-builds"></a>Começar a receber builds do Insider

> [!NOTE]
> Se você não tiver atualizado recentemente, reinicie seu dispositivo para atualizar o estado e obter a com build mais recente.
> - O comando de voz "Reiniciar dispositivo" funciona bem. 
> - Você também pode escolher o botão reiniciar em Configurações/Programa Windows Insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso o fará voltar aos trilhos.

Em um dispositivo do HoloLens 2, acesse **Configurações**Atualização & Programa Windows  >  ****  >  **Insider** de Segurança e selecione **Iniciar**. Vincule a conta usada para se registrar como windows insider.

O Windows insider agora está mudando para Canais. O **anel Fast** se tornará o **** Canal **de Desenvolvedor,** o **** anel Lento se tornará o **Canal Beta**e o anel de Visualização de Versão se tornará o Canal de Visualização de **Versão**. Veja a aparência desse mapeamento:

![Explicação dos Canais do Windows Insider](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [Apresentando canais do Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos Blogs do Windows.

Em seguida, selecione **Desenvolvimento ativo**do Windows , escolha se você gostaria de receber builds do Canal **de Desenvolvimento** ou Canal **Beta** e revise os termos do programa.

Selecione **Confirmar > Reiniciar Agora** para concluir. Depois que o dispositivo for reiniciado, vá para Configurações > Atualização & **Segurança > Verificar** se há atualizações para obter a com build mais recente.

### <a name="update-error-0x80070490-work-around"></a>Atualizar erros 0x80070490 de trabalho
Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, experimente o seguinte trabalho de curto prazo. Envolve mover seu canal interno, pegar a atualização e, em seguida, mover seu canal Insider de volta.

#### <a name="stage-one---release-preview"></a>Estágio um - Versão Prévia
1.  Configurações, Atualização & Segurança, Programa Windows Insider, selecione **Canal de Visualização de Versão**.
2.  Configurações, Atualizar & Segurança, Windows Update, **Verificar se há atualizações**. Após a atualização, continue no Estágio dois.

#### <a name="stage-two---dev-channel"></a>Estágio dois - Canal de Dev
1. Configurações, Atualização & Segurança, Programa Windows Insider, selecione **Canal de Dev**.
2. Configurações, Atualizar & Segurança, Windows Update, **Verificar se há atualizações**.

## <a name="ffu-download-and-flash-directions"></a>Instruções de download e flash FFU
Para testar com um ffu de voo assinado, primeiro você precisa desbloquear o dispositivo antes de piscar o ffu assinado para o voo.
1. No computador:

    1. Baixe ffu para seu computador de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. No HoloLens - Desbloqueio de Pré-&: Abra Configurações Atualizar & Programa Windows **** Insider de Segurança e, em seguida, inscreva-se,  >  ****  >  **** reinicie o dispositivo.

1. Flash FFU - Agora você pode piscar o FFU assinado de pré-voo usando ARC.

## <a name="provide-feedback-and-report-issues"></a>Fornecer comentários e problemas de relatório

Use o [aplicativo Hub de Feedback](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas. O uso do Hub de Feedback garante que todas as informações de diagnóstico necessárias sejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.  Os problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.

> [!NOTE]
> Certifique-se de aceitar o prompt que pergunta se você gostaria que o Hub de Comentários acessasse sua pasta Documentos (selecione **Sim** quando solicitado).

## <a name="note-for-developers"></a>Observação para desenvolvedores

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando builds do Insider do HoloLens.  Confira a [Documentação do Desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com builds insider do HoloLens.  Você pode usar as mesmas builds do Unity e Visual Studio que já está usando para o desenvolvimento do HoloLens.

## <a name="stop-receiving-insider-builds"></a>Parar de receber builds do Insider

Se você não quiser mais receber builds do Insider do Windows Holographic, poderá optar quando [](hololens-recovery.md) o HoloLens estiver executando uma com build de produção ou pode recuperar seu dispositivo usando o Advanced Recovery Companion para recuperar seu dispositivo em uma versão não Insider do Windows Holographic.

> [!CAUTION]
> Há um problema conhecido em que os usuários que não se inscreverem no Insider Preview são builds após a reinstalação manual de uma nova versão de visualização experimentariam uma tela azul. Posteriormente, eles devem recuperar manualmente o dispositivo. Para obter detalhes completos sobre se você seria afetado ou não, confira mais sobre este [Problema Conhecido.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Para verificar se o HoloLens está executando uma com build de produção:

1. Vá para **Configurações > Sistema > Sobre**e encontre o número de com build.

1. [Consulte as notas de versão para números de com build de produção](hololens-release-notes.md).

Para optar por não fazer com builds do Insider:

1. Em um HoloLens executando uma com build de produção, acesse **Configurações > Atualização**& Segurança > Programa Windows Insider e selecione Parar **builds do Insider**.

1. Siga as instruções para excluir o dispositivo.
