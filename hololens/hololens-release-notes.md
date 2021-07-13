---
title: Notas sobre a versão do HoloLens 2
description: mantenha-se atualizado com todas as atualizações em cada nova versão do HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 73d89619498c61f2809702d788ffafc532afa67e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640025"
---
# <a name="hololens-2-release-notes"></a>Notas sobre a versão do HoloLens 2

para garantir que você tenha uma experiência produtiva com seus dispositivos HoloLens, continuamos lançando recursos, bugs e atualizações de segurança. nessa página, você pode ver as novidades de HoloLens a cada mês. para obter a atualização mais recente do HoloLens 2, você pode [verificar se há atualizações e atualizar manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a atualização completa do Flash (FFU) para atualizar [seu dispositivo usando o complemento de recuperação avançada](hololens-recovery.md#clean-reflash-the-device). O [Download](https://aka.ms/hololens2download) é mantido atualizado e fornece a compilação mais recente disponível ao público em geral.

> [!NOTE]
> o anúncio recente do Windows 11 foi focado na versão do Windows do PC. recentemente, lançamos uma [atualização principal do sistema operacional](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) para HoloLens 2 em maio de 2021, e estamos trabalhando em uma versão futura com base nos comentários dos clientes para esse outono.

> [!IMPORTANT]
> devido a um [problema conhecido agora resolvido em nossa compilação 21H1 que estava afetando os usuários de assistência remota](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes), na última pausa a oferta de Windows Holographic, a versão 21H1 atualiza. também alteramos a compilação padrão do ARC (Advanced Recovery Companion) para o [Windows Holographic, versão 20H2 – atualização de junho de 2021](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). A compilação ARC agora retomará o destino da compilação 21H1.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, versão 21H1-atualização de junho de 2021
- Build 20348,1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive para carregamento de rolo de câmera corporativa ou de estudante

adicionamos um novo recurso ao aplicativo HoloLens 2 Configurações, que permite aos clientes carregar automaticamente fotos e vídeos de realidade misturada das imagens do dispositivo > pasta de rolagem da câmera para a OneDrive correspondente para a pasta trabalho ou escolar. esse recurso aborda uma [lacuna de recursos no aplicativo OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) no HoloLens 2, que dá suporte apenas ao carregamento automático da câmera para o conta Microsoft pessoal do cliente (e não a sua conta corporativa ou de estudante).

**Como funciona**

- visite a **câmera Configurações > sistema > realidade mista** para habilitar o "carregamento da câmera".
- ao definir esse recurso como a posição **On** , qualquer foto ou vídeo da realidade misturada capturada em seu dispositivo será automaticamente enfileirado para carregamento nas imagens > pasta de distribuição da câmera de sua OneDrive para conta corporativa ou de estudante.
    >[!NOTE]
    >Fotos e vídeos capturados antes de habilitar esse recurso *não serão* enfileirados para carregamento e ainda precisarão ser carregados manualmente.
- uma mensagem de status na página Configurações exibirá o número de arquivos com carregamento pendente (ou leitura "OneDrive está atualizado" quando todos os arquivos pendentes tiverem sido carregados).
- Se estiver preocupado com a largura de banda ou se quiser fazer o upload de "pausa" por qualquer motivo, você poderá alternar o recurso para a posição **desativado** . Desabilitar temporariamente o recurso garante que a fila de carregamento continuará aumentando à medida que você adicionar novos arquivos à pasta de rolagem da câmera, mas os arquivos não serão carregados até que você habilite novamente o recurso.
- Os arquivos mais recentes serão carregados primeiro (último a entrar, primeiro a sair).
- se sua conta de OneDrive tiver problemas (por exemplo, após a alteração da senha), um botão **corrigir agora** será exibido na página Configurações.
- Não há tamanho máximo de arquivo, mas observe que os arquivos grandes levarão mais tempo para carregar (especialmente se a largura de banda de upload for restrita). Se você "Pausar" ou desativar o carregamento enquanto um arquivo grande estiver sendo carregado, o carregamento parcial será preservado. Se o carregamento for habilitado novamente dentro de várias horas após ser "pausado" ou desativado, o carregamento continuará de onde parou. No entanto, se o upload for reabilitado após várias horas, o carregamento do arquivo grande será reiniciado desde o início.

**Problemas conhecidos e advertências**

- Essa configuração não tem limitação interna baseada no uso de largura de banda atual. Se você precisar maximizar a largura de banda para outro cenário, desative a configuração manualmente. Upload será pausado, mas o recurso continuará a monitorar arquivos recém-adicionados no rolo da câmera. Habilite o carregamento novamente quando estiver pronto para continuar.
- Esse recurso deve ser habilitado para cada conta de usuário no dispositivo e só pode carregar ativamente arquivos para o usuário que está conectado no momento ao dispositivo.
- se você estiver tirando fotos ou vídeos enquanto assiste a contagem de carregamento na página de Configurações em tempo real, observe que a contagem de arquivos pendentes pode não ser alterada até que o arquivo atual tenha concluído o carregamento.
- Upload será pausado se o dispositivo estiver suspenso ou desligado. para garantir que os carregamentos pendentes sejam concluídos, use ativamente o dispositivo até que a página de Configurações leia "OneDrive esteja atualizado" ou ajuste as configurações de **energia & suspensão** .
### <a name="added-support-for-some-telemetry-policies"></a>Suporte adicionado para algumas políticas de telemetria

agora há suporte para as seguintes políticas de telemetria no HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry e System\ConfigureTelemetryOptInSettingsUx devem ser usados juntos para ter controle total sobre a telemetria e o comportamento no aplicativo Configurações.

Melhorias e correções na atualização:
- Corrige a grande corrupção de vídeo com a calibragem de cores.
- Aborda um problema em que o texto pode ser truncado no menu de energia.
- Habilita o suporte para a política RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, versão 20H2 – atualização de junho de 2021
- Build 19041,1154

### <a name="added-support-for-some-telemetry-policies"></a>Suporte adicionado para algumas políticas de telemetria

agora há suporte para as seguintes políticas de telemetria no HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry e System\ConfigureTelemetryOptInSettingsUx devem ser usados juntos para ter controle total sobre a telemetria e o comportamento no aplicativo Configurações.

incentivamos você a experimentar nossa compilação mais recente, Windows Holographic, versão 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, versão 1903 – atualização de junho de 2021
- Build 18362,1116

Melhorias e correções na atualização:
- essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa compilação mais recente, Windows Holographic, versão 21H1.

>[!IMPORTANT]
> Esta compilação não será mais atendida.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, versão 21H1
- Build 20346,1002

Esta atualização contém recursos para dois públicos-alvo; recursos que podem ser usados por qualquer pessoa em um dispositivo pelo usuário final e novas opções de gerenciamento de dispositivo que podem ser configuradas por administradores de ti. A tabela a seguir especifica os recursos que são relevantes para cada público. Se você for um administrador de ti, Confira nossa [lista de verificação de administrador de ti – atualização](#it-admin---update-checklist).
>[!IMPORTANT]
>para atualizar para essa compilação, HoloLens 2 dispositivos devem estar atualmente em execução na atualização de fevereiro de 2021 (build 19041,1136) ou mais recente. Se você não estiver vendo essa atualização de recurso disponível, atualize o dispositivo primeiro e tente novamente.

>[!NOTE]
>hoje, Microsoft HoloLens 2 dá suporte a atualizações de serviços mensais (correções de bugs e de segurança) para as seguintes versões:
>- Windows Holographic, versão 20H2 (Build 19041.1128 +)
>- Windows Holographic, versão 2004 (Build 19041.1103 +)
>- Windows Holographic, versão 1903 (Build 18362 +) 
>
> com a introdução do Windows Holographic versão 21H1, **estamos descontinuando as atualizações de manutenção mensal para Windows Holographic versão 1903**. Isso nos permite focar em versões mais recentes e continuar a fornecer melhorias valiosas. 


| Nome do recurso                                              | Descrição breve                                                                      | Público-alvo | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Novo Microsoft Edge](#introducing-the-new-microsoft-edge)  | o novo Microsoft Edge baseado em Chromium agora está disponível para o HoloLens 2. | Usuário Final | 
[Visualizador de WebXR e 360](#webxr-and-360-viewer) | Experimente experiências de imersão da Web e reprodução de vídeo 360. | Usuário Final | 
[novo aplicativo Configurações](#new-settings-app) | o aplicativo Configurações herdado está sendo substituído por uma versão atualizada com novos recursos e configurações. | Usuário Final |
[Exibir calibragem de cor](#display-color-calibration) | selecione um perfil de cor alternativo para a exibição do HoloLens 2. | Usuário Final |
[Seletor de aplicativo padrão](#default-app-picker) | Escolha qual aplicativo deve ser iniciado para cada arquivo ou tipo de link. | Usuário Final |
[Por controle de volume por aplicativo](#per-app-volume-control) | Controlar o volume de nível do aplicativo independentemente do volume do sistema. | Usuário Final |
[Instalar aplicativos Web](#install-web-apps) | instale os aplicativos web no HoloLens 2, como Microsoft Office, com o novo navegador Microsoft Edge. | Usuário Final |
[Passar o dedo para o tipo](#swipe-to-type) | Use a ponta do dedo para "deslizar" palavras no teclado Holographic. | Usuário Final |
[Menu de energia do início](#power-menu-from-start) | no Menu iniciar, reinicie e desligue HoloLens dispositivo. | Usuário Final |
[Vários usuários listados na tela de entrada](#multiple-users-listed-on-sign-in-screen) | Exibe várias contas de usuário na tela de entrada. | Usuário Final |
[Suporte ao microfone externo USB-C](#usb-c-external-microphone-support) | Use microfones USB-C para aplicativos e/ou assistência remota. | Usuário Final |
[Logon automático do visitante para quiosques](#visitor-auto-logon-for-kiosks) | Permite que o logon automático em contas de visitante seja usado para modos de quiosque. | Administrador de TI |
[Novo AUMIDs para novos aplicativos no modo de quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs para novos aplicativos de Configurações e borda. | Administrador de TI |
[Falha na entrega do modo de quiosque aprimorado](#kiosk-mode-behavior-changes-for-handling-of-failures) | O modo de quiosque procura acesso global atribuído antes do menu iniciar vazio. | Administrador de TI |
[novo SettingsURIs para a visibilidade da Configurações de página](#new-settings-uris-for-page-settings-visibility) | 20 + novo SettingsURIs para a política de/PageVisibilityList de Configurações. | Administrador de TI |
[Configurar o diagnóstico de fallback](#configuring-fallback-diagnostics-via-settings-app) | definindo o comportamento de diagnóstico de Fallback no aplicativo Configurações. | Administrador de TI |
[Compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices) | compartilhar arquivos ou URLs de um HoloLens para um PC. | Tudo |
[Novos rastreamentos de diagnóstico do sistema operacional](#new-os-diagnostic-traces) | nova solução de problemas no Configurações para atualizações do sistema operacional. | Administrador de TI |
[Visualização da otimização de entrega](#delivery-optimization-preview) | reduza o consumo de largura de banda para downloads de vários dispositivos HoloLens. | Administrador de TI |

Confira as notas de versão relacionadas:

- [visite o arquivo morto do HoloLens Emulator](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Apresentando o novo Microsoft Edge

![animação do logotipo de Microsoft Edge herdado para o novo logotipo de Microsoft Edge](images/new-edge.gif)

o novo Microsoft Edge [adota o Chromium projeto](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) de software livre para criar uma melhor compatibilidade para os clientes e menos fragmentação da web para desenvolvedores da web.

> [!IMPORTANT]
> esse novo Microsoft Edge substitui automaticamente Microsoft Edge herdados, que [não tem mais suporte](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) em novas versões.

![nova captura de tela de Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Iniciando o novo Microsoft Edge

O novo Microsoft Edge ![novo ícone de Microsoft Edge](images/new_edge_logo.png) (representado por um ícone de espiral azul e verde) é fixado na menu Iniciar e será iniciado automaticamente quando você ativar um link da web.

> [!NOTE]
> ao iniciar pela primeira vez o novo Microsoft Edge no HoloLens 2, suas configurações e dados serão importados do Microsoft Edge herdado. se você continuar a usar o Microsoft Edge herdado depois de iniciar o novo Microsoft Edge, esses novos dados não serão sincronizados do Microsoft Edge herdado para o novo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Definindo as configurações de política para o novo Microsoft Edge

a nova Microsoft Edge oferece aos administradores de ti um conjunto muito mais amplo de políticas de navegador no HoloLens 2 do que estavam disponíveis anteriormente com o Microsoft Edge herdado.

Aqui estão alguns recursos úteis para aprender mais sobre o gerenciamento de configurações de política para o novo Microsoft Edge:

- [definir configurações de política de Microsoft Edge com Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Versão Prévia do Microsoft Edge Microsoft Edge mapeamento de política](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [mapeamento de política do Google Chrome para Microsoft Edge](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- documentação completa de [Enterprise de Microsoft Edge](/deployedge/)

> [!IMPORTANT]
> devido ao volume de políticas de navegador com suporte pelo novo Microsoft Edge, nossa equipe não consegue garantir que cada nova política funcione no HoloLens 2. no entanto, testamos e confirmamos o novo Microsoft Edge equivalente de cada política de Microsoft Edge herdada anteriormente com suporte no HoloLens 2 funciona conforme o esperado. consulte [Versão Prévia do Microsoft Edge para Microsoft Edge mapeamento de política](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) para encontrar o novo equivalente Microsoft Edge de cada política herdada de navegador Microsoft Edge que você estava usando com o HoloLens 2.
>
> há pelo menos duas novas políticas de Microsoft Edge que sabemos que *não* funcionarão com HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>o que esperar da nova Microsoft Edge no HoloLens 2

como o novo Microsoft Edge é um aplicativo Win32 nativo com uma nova camada de adaptador UWP, permitindo que ele seja executado em dispositivos somente UWP como o HoloLens 2, alguns recursos podem não estar imediatamente disponíveis. Daremos suporte a novos cenários e recursos nos próximos meses, portanto, verifique este espaço para obter informações atualizadas.

**Cenários e recursos que se espera que funcionem:**
- Experiência de primeira execução, entrar no perfil e sincronizar
- Os sites devem renderizar e se comportar conforme o esperado
- A maioria das funcionalidades do navegador (favoritos, histórico, etc.) deve funcionar conforme o esperado
- Modo escuro
- Instalando aplicativos Web no dispositivo
- instalando extensões (informe-nos se você usar qualquer extensão que não funcione corretamente no HoloLens 2)
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

- A visualização da lupa no teclado Holographic foi desabilitada para o novo Microsoft Edge. Esperamos reabilitar esse recurso em uma atualização futura, uma vez que a ampliação esteja funcionando corretamente.
- O áudio pode ser reproduzido na janela do navegador incorreta se você tiver outra janela do navegador aberta e ativa. Você pode contornar esse problema fechando a outra janela ativa que não deveria estar reproduzindo áudio.
- Ao reproduzir áudio de uma janela do navegador no [modo "Follow-me"](hololens2-basic-usage.md#follow-me-stop-following), o áudio continuará a ser reproduzido se você desabilitar o modo "Siga eu". Você pode contornar esse problema interrompendo a reprodução de áudio antes de desabilitar o modo "Follow-me" ou fechando a janela com o botão **X** .
- interagir com o active Microsoft Edge windows pode fazer com que outras janelas de aplicativo 2d fiquem inativas inesperadamente. Você pode reativar essas janelas interagindo com elas novamente.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Canais Insider

a equipe de Microsoft Edge disponibiliza três canais de visualização para o Edge insider community: Beta, Dev e canário. a instalação de um canal de visualização não desinstala a versão de lançamento do Microsoft Edge no HoloLens 2, e você pode instalar mais de um ao mesmo tempo. 

visite a [home page do Microsoft Edge insider](https://www.microsoftedgeinsider.com) para saber mais sobre a comunidade do Edge insider. Para saber mais sobre os diferentes canais do Edge Insider e comece, visite a [página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).

há alguns métodos disponíveis para instalar Microsoft Edge os canais do insider para HoloLens 2:

**Instalação direta no dispositivo (atualmente disponível apenas para dispositivos não gerenciados)**
  1. no seu HoloLens 2, visite a [página de download do Edge insider](https://www.microsoftedgeinsider.com/download).
  1. selecione o botão **baixar para HoloLens 2** para o canal do Edge insider que você deseja instalar.
  1. Inicie o arquivo. msix baixado na fila de download do Edge ou na pasta "downloads" do seu dispositivo (usando o explorador de arquivos).
  1. O [instalador do aplicativo](app-deploy-app-installer.md) será iniciado.
  1. Selecione o botão **Instalar**.
  1. após a instalação bem-sucedida, você encontrará Microsoft Edge Beta, Dev ou canário como uma entrada separada na lista **todos os aplicativos** do menu Iniciar.

**instalar via PC com Windows Portal de dispositivo (requer que o [modo de desenvolvedor](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) esteja habilitado no HoloLens 2)**
  1. Em seu computador, visite a [página de download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. selecione o **botão de seta suspensa** ao lado do botão "baixar para Windows 10" para o canal do Edge insider que você deseja instalar.
  1. selecione **HoloLens 2** no menu suspenso.
  1. Salve o arquivo. msix na pasta "downloads" do seu PC (ou outra pasta que você possa encontrar facilmente).
  1. Use [Windows Portal do dispositivo](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) em seu PC para instalar o arquivo. msix baixado no HoloLens 2.
  1. após a instalação bem-sucedida, você encontrará Microsoft Edge Beta, Dev ou canário como uma entrada separada na lista **todos os aplicativos** do menu Iniciar.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Usando o WDAC para bloquear novos Microsoft Edge

para os administradores de ti que procuram atualizar sua [política WDAC](windows-defender-application-control-wdac.md) para bloquear o novo aplicativo Microsoft Edge, você precisará adicionar o seguinte à sua política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerenciando pontos de extremidade para o novo Microsoft Edge

Alguns ambientes podem ter restrições de rede para considerar como uma consideração. Para garantir uma experiência tranqüila com a nova borda, [habilite esses pontos de extremidade da Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os pontos de extremidade disponíveis no momento [para HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Instalar aplicativos Web
 > [!Note]
>a partir de [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), o aplicativo web do Office não será mais pré-instalado.

você pode usar a nova borda para instalar aplicativos web junto com Microsoft Store aplicativos. por exemplo, você pode instalar o aplicativo web Microsoft Office para exibir e editar arquivos hospedados em SharePoint ou OneDrive. para instalar o aplicativo web Office, visite https://www.office.com e selecione o botão **aplicativo disponível** ou **instalar Office** na barra de endereços. Selecione **instalar** para confirmar.

> [!IMPORTANT]
> Office funcionalidade de aplicativo web só está disponível quando o HoloLens 2 tem uma conexão ativa com a internet.

### <a name="webxr-and-360-viewer"></a>Visualizador de WebXR e 360

o novo Microsoft Edge inclui suporte para WebXR, que é o novo padrão para a criação de experiências de imersão na web (substituindo WebVR). muitas experiências da web de imersão foram projetadas com o VR em mente (elas substituem o campo de exibição por um ambiente virtual), mas também há suporte para essas experiências no HoloLens 2. O padrão WebXR também permite experiências ampliadas e mistas de imersão da Web que usam seu ambiente físico. à medida que os desenvolvedores passam mais tempo com o WebXR, esperamos que novas experiências de imersão aumentadas e mistas cheguem para que HoloLens 2 clientes tentem!

a extensão do visualizador 360 é criada em WebXR e instalada automaticamente junto com o novo Microsoft Edge no HoloLens 2. Essa extensão da Web oferece a capacidade de aprofundar-lo em vídeos de 360 graus. O YouTube oferece a maior seleção de 360 vídeos, portanto, incentivamos você a começar lá.

#### <a name="how-to-use-webxr"></a>Como usar o WebXR

1. Navegue até um site com suporte a WebXR.
1. Selecione o botão **Inserir VR** no site. O local e a representação visual desse botão podem variar por site, mas pode ser semelhante a:

    ![Inserir exemplo de botão VR](images/75px-enter-vr.png)

1. Na primeira vez que você tentar iniciar uma experiência de WebXR em um domínio específico, o navegador pedirá autorização para inserir uma exibição de imersão, selecione **permitir**.
1. Use [gestos de HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular a experiência.
1. Se a experiência não tiver um botão **sair** , use o [gesto iniciar](hololens2-basic-usage.md#start-gesture) para retornar à página inicial.

**Exemplos de WebXR recomendados**
- 360 Viewer (consulte a próxima seção)
- [Dinossauro do XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [Paint WebXR](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Como usar o Visualizador de 360

1. Navegue até um vídeo de 360 graus no YouTube.
1. No quadro de vídeo, selecione o botão de headset de realidade misturada:

    ![Botão para ativar o Visualizador de 360](images/enter-360-viewer.jpg)

1. Na primeira vez que você tentar iniciar o Visualizador de 360 em um domínio específico, o navegador solicitará o consentimento para inserir uma exibição de imersão. selecione **Permitir**.
1. [Toque de ar](hololens2-basic-usage.md#select-using-air-tap) para abrir os controles de reprodução. Use [raios de mão e toque de ar](hololens2-basic-usage.md#select-using-air-tap) para reproduzir/pausar, pular para frente/para trás, ativar/desativar legendas ou interromper a experiência (que sai da exibição imersiva). Os controles de reprodução desaparecerão após alguns segundos de inatividade.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Problemas conhecidos do Visualizador de WebXR e 360 principais
- Dependendo da complexidade da experiência do WebXR, a taxa de quadros pode cair ou stutter.
- O suporte para junções de mão articuladas em WebXR não está habilitado por padrão. Os desenvolvedores podem habilitar o suporte via `edge://flags` ativando a "entrada do WebXR Hand".
- 360 vídeos de sites diferentes do YouTube podem não funcionar conforme o esperado.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo comentários sobre o Visualizador de WebXR e 360

Compartilhe comentários e bugs com nossa equipe por meio do recurso **enviar comentários** no novo Microsoft Edge.

### <a name="new-settings-app"></a>novo aplicativo Configurações

com esta versão, estamos introduzindo uma nova versão do aplicativo Configurações. o novo aplicativo Configurações inclui novos recursos e configurações expandidas para HoloLens 2 nas seguintes áreas: som, energia & suspensão, rede & Internet, aplicativos, contas, facilidade de acesso e muito mais.

> [!NOTE]
> como o novo aplicativo Configurações é diferente do aplicativo herdado Configurações, qualquer Configurações do windows que você colocou anteriormente em seu ambiente será removida após a atualização.

![home page do novo aplicativo Configurações](images/new-settings-app.png)

**Novos recursos e configurações**
- pesquisa de Configurações: procure configurações na home page do Configurações usando palavras-chave ou o nome da configuração.
- Som de > do sistema:
  - dispositivos de áudio de entrada e saída: escolha independentemente seus dispositivos de áudio de entrada e saída (por exemplo, ouça o áudio via fone de ouvido Bluetooth ou use um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > os microfones Bluetooth não têm suporte do HoloLens 2.
  - Volume do aplicativo: ajuste o volume de cada aplicativo de forma independente. Consulte [controle de volume por aplicativo](#per-app-volume-control).
- Suspensão de & de energia do sistema >: escolha quando o dispositivo deve ir para o estado de suspensão após um período de inatividade.
- Bateria de > do sistema: habilite manualmente o modo de economia de bateria ou defina um limite de bateria no qual o modo de economia de bateria é ativado automaticamente.
- Dispositivos > USB: você pode desabilitar conexões USB por padrão.
- Rede & Internet:
  - Adaptadores Ethernet USB-C agora aparecerão na rede & Internet.
  - As configurações do adaptador Ethernet USB-C agora estão disponíveis, incluindo seu endereço IP.
  - agora você pode habilitar o modo avião no HoloLens 2.
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Para obter mais informações, consulte [seletor de aplicativo padrão](#default-app-picker).
- Contas > outros usuários: os proprietários de dispositivo podem adicionar usuários, atualizar usuários padrão para proprietários de dispositivo, fazer downgrade de proprietários de dispositivo para usuários padrão e remover usuários.
- Facilidade de acesso: alterar o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- Configurações previamente posicionadas, as janelas serão removidas (veja a observação acima).
- você não pode mais renomear seu dispositivo com o aplicativo Configurações. os administradores de ti podem renomear dispositivos usando o modelo de nome de dispositivo [Windows autopilot para HoloLens 2](hololens2-autopilot.md) ou o nó MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- A página Ethernet mostra um dispositivo Ethernet virtual ("UsbNcm") em todos os momentos.
- o uso da bateria para o novo Microsoft Edge pode não ser preciso, devido à sua natureza como um aplicativo de área de trabalho Win32 com suporte de uma camada de adaptador UWP (sem correção antecipada em breve).

#### <a name="display-color-calibration"></a>Exibir calibragem de cor



com essa nova configuração, você pode selecionar um perfil de cor alternativo para a exibição do HoloLens 2. Isso pode ajudar as cores a parecerem mais precisas, especialmente em níveis de brilho de exibição mais baixos. a calibragem de cores de exibição pode ser encontrada no aplicativo Configurações, na página calibragem de > do sistema.

> [!NOTE]
> Como essa configuração salva um novo perfil de cor em seu firmware de vídeo, ela é uma configuração por dispositivo (e não exclusiva para cada conta de usuário).

##### <a name="how-to-use-display-color-calibration"></a>Como usar a calibragem de cor de exibição

1. Iniciar o **aplicativo Configurações** e navegue até **Calibragem > Sistema.**
1. Em **Exibir calibragem de cores,** selecione o **botão Executar calibragem de cor de** exibição.
1. A experiência de calibragem de cores de exibição será lançada e o incentivará a garantir que o visor está na posição correta.
1. Depois de prosseguir com as caixas de diálogo de instrução, a exibição será esmaecida automaticamente para 30% de brilho.
    > [!TIP]
    > Se você estiver tendo problemas para ver a cena esmaecida em seu ambiente, poderá ajustar manualmente o nível de brilho do HoloLens 2 usando os botões de brilho no lado esquerdo do dispositivo.
1. Selecione os botões de 1 a 6 para experimentar instantaneamente cada perfil de cor e encontre um que tem a melhor aparência para seus olhos (isso geralmente significa que o perfil que ajuda a cena a parecer mais neutro, com o padrão de escala de cinza e os tons de capa com a aparência esperada.)

    ![Exibir cena de calibragem de cores](images/color-cal-ui.png)
    
1. Quando estiver satisfeito com o perfil selecionado, selecione o **botão Salvar &** Sair
1. Se você preferir não fazer alterações, selecione o **botão Cancelar & Sair** e as alterações serão revertidas

> [!TIP]
> Aqui estão algumas dicas úteis para ter em mente ao usar a configuração de calibragem de cores de exibição:
> - Você pode executar a calibragem de cores de exibição Configurações sempre que quiser
> - Se alguém no dispositivo tiver usado anteriormente a configuração para alterar perfis de cor, a data/hora da alteração mais recente será refletida na página Configurações dados
> - Quando você executar a calibragem de cores de exibição, o perfil de cor salvo anteriormente será realçado e o Perfil 0 não será exibido (como o Perfil 0 representa o perfil de cor original da exibição)
> - Se você quiser reverter para o perfil de cor original da exibição, poderá fazer isso na página Configurações (consulte como redefinir o perfil [de cor](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cor 

Se você não estiver satisfeito com o perfil de cor personalizado salvo no HoloLens 2, poderá restaurar o perfil de cor original do dispositivo:
1. Iniciar o **aplicativo Configurações** e navegue até **Calibragem > Sistema.**
1. Em **Exibir calibragem de cores,** selecione o **botão Redefinir para o perfil de cor** padrão.
1. Quando a caixa de diálogo for aberta, **selecione** Reiniciar se você estiver pronto para reiniciar HoloLens 2 e aplicar as alterações.

#### <a name="top-display-color-calibration-known-issues"></a>Principais problemas conhecidos de calibragem de cores de exibição

- Na página Configurações, a cadeia de caracteres de status que informa quando o perfil de cor foi alterado pela última vez ficará des date até que você recarregue essa página Configurações.
    - Solução alternativa: selecione outra Configurações e, em seguida, selecione a página Calibragem.

#### <a name="default-app-picker"></a>Selador de aplicativo padrão

Ao ativar um hiperlink ou abrir um tipo de arquivo com mais de um aplicativo instalado, que dá suporte a ele, você verá uma nova janela aberta solicitando que você selecione qual aplicativo instalado deve lidar com o tipo de arquivo ou link. Nessa janela, você também pode optar por fazer com que o aplicativo selecionado manipular o arquivo ou o tipo de link "Uma vez" ou "Sempre".

Se você escolher "Sempre", mas posteriormente quiser alterar qual aplicativo lida com um arquivo ou tipo de link específico, poderá redefinir os padrões salvos no **Configurações > Apps**. Role até a parte inferior  da página e selecione o botão Limpar em "Aplicativos padrão para tipos de arquivo" e/ou "Aplicativos padrão para tipos de link". Ao contrário da configuração semelhante em computadores desktop, você não pode redefinir padrões de tipo de arquivo individuais.

#### <a name="per-app-volume-control"></a>Por controle de volume do aplicativo

Agora, neste Windows build, os usuários podem ajustar manualmente o nível de volume de cada aplicativo. Isso permite que os usuários se concentrem melhor nos aplicativos que precisam ou ouvir melhor ao usar vários aplicativos. Como a necessidade de desativar o volume de um aplicativo ao chamar outra pessoa para assistência remota em outro.

Para definir o volume de um aplicativo individual, navegue **até Configurações** Som do Sistema e, em Opções de som  ->    ->   **avançadas,** selecione Volume do aplicativo e preferências do dispositivo .<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Passar o dedo para o tipo

Alguns clientes acham mais rápido "digitar" em teclados virtuais ao deslizar a forma da palavra que pretendem digitar e estamos visualizando esse recurso para o teclado holográfico. Você pode passar o dedo uma palavra por vez passando a ponta do dedo pelo plano do teclado holográfico, passando a forma da palavra e, em seguida, retirando a ponta do dedo do plano do teclado. Você pode passar o dedo nas palavras de acompanhamento sem precisar pressionar a barra de espaço removendo o dedo do teclado entre palavras. Você saberá que o recurso está funcionando se vir uma trilha de deslizar o dedo após o movimento do dedo no teclado.

Observe que esse recurso pode ser complicado de usar e ser mestre devido à natureza de um teclado holográfico em que você não sinta resistência ao dedo (ao contrário de uma exibição de telefone celular). 

### <a name="power-menu-from-start"></a>Menu de energia de Iniciar

Um novo menu que permite que o usuário saia, desligue e reinicie o dispositivo. Um indicador no HoloLens tela inicial que mostra quando uma atualização do sistema está disponível.

#### <a name="how-to-use"></a>Como usar

1. Abra o HoloLens tela inicial usando o [gesto Iniciar ou](hololens2-basic-usage.md#start-gesture) dizendo "Go to Start".

2. Observe o ícone de re elipse (...) ao lado da imagem do perfil do usuário:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selecione a imagem do perfil do usuário usando as mãos ou o comando de voz "Power".

4. Um menu é exibido com opções para Sair, Reiniciar ou Desligar o dispositivo:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Selecione as opções de menu para sair, reiniciar ou desligar o HoloLens. A opção Sair pode não estar disponível, se o dispositivo estiver definido para uma única [MSA (Conta Microsoft) ou conta local](hololens-identity.md).

6. Descarte o menu tocando em qualquer outro lugar ou fechando o menu Iniciar com o gesto Iniciar.

#### <a name="update-indicator"></a>Indicador de atualização

Quando uma atualização estiver disponível, o ícone de reellipse será aluminado para indicar que uma reinicialização instalará a atualização As opções de menu também mudam para refletir a presença da atualização.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela Entrar

Anteriormente, a tela Entrar mostrava apenas o usuário que entrou mais recentemente, bem como um ponto de entrada "Outro usuário". Recebemos comentários dos clientes de que isso não é suficiente se vários usuários entraram no dispositivo. Eles ainda eram necessários para novo tipo de nome de usuário etc.

Introduzido neste build Windows, ao  selecionar Outro usuário localizado à direita do campo de entrada pin, a tela Entrar exibirá vários usuários com já conectados ao dispositivo. Isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entre usando suas Windows Hello credenciais. Um novo usuário também pode ser adicionado ao dispositivo desta página Outros usuários por meio do **botão Adicionar conta.**

Quando estiver no menu Outros usuários, o botão Outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela Entrar para esse usuário.

![Padrão da tela de login](./images/multiusers1.jpg)

<br>

![Tela de login de outros usuários](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Suporte a microfone externo USB-C

> [!IMPORTANT]
> Conectar-se **a um microfone USB não o definirá automaticamente como o dispositivo de entrada**. Ao conectar um conjunto de fones de ouvido USB-C, os usuários observarão que o áudio do fone de ouvido será redirecionado automaticamente para os fones de ouvido, mas o so HoloLens prioriza a matriz de microfone interno acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

Os usuários podem selecionar microfones externos conectados por USB-C usando o **painel Configurações** de som. Os microfones USB-C podem ser usados para chamar, gravar etc.

Abra o **Configurações** aplicativo e selecione **Som do**  >  **Sistema**.

![Som Configurações](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com **o Remote Assist,** os usuários precisarão clicar no hiperlink "Gerenciar dispositivos de som".
>
> Em seguida, use a lista para definir o microfone externo como **Padrão ou** Padrão **de Comunicações.** Escolher **Padrão** significa que o microfone externo será usado em todos os lugares.
>
> Escolher **Padrão de** Comunicações significa que o microfone externo será usado no Remote Assist e em outros aplicativos de comunicação, mas HoloLens matriz de microfones ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir o padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E quanto ao Bluetooth microfone?

Infelizmente, Bluetooth ainda não há suporte para microfones no HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solução de problemas de microfones USB-C

Esteja ciente de que alguns microfones USB-C relatam-se incorretamente como um microfone *e um* alto-falante. Esse é um problema com o microfone e não com HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

No **Configurações** system sound , de definir explicitamente os  ->    ->  alto-falantes integrados **(Driver de** Áudio de Recurso Análogo) como **o dispositivo padrão**. HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado posteriormente.

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Logon automático do Visitante para Quiosques

Esse novo recurso permite que o logon automático em contas de Visitante seja usado para modos de quiosque.

Para uma configuração não AAD, para configurar um dispositivo para logon automático de visitante:

1. Crie um pacote de provisionamento que:
    1. Define as **configurações de Runtime/AssignedAccess** para permitir contas de Visitante.
    1. Opcionalmente, registra o dispositivo no MDM **(configurações de runtime/Workplace/Enrollments)** para que ele possa ser gerenciado posteriormente.
    1. Não crie uma conta local
1. [Aplique o pacote de provisionamento](hololens-provisioning.md).

Para uma configuração do AAD, os usuários podem obter algo semelhante a isso hoje sem essa alteração. Os dispositivos ingressados no AAD configurados para o modo de quiosque podem entrar em uma conta de Visitante com um único toque de botão na tela de entrada. Depois de conectado à conta de visitante, o dispositivo não solicitará a entrada novamente até que o Visitante seja explicitamente conectado no menu iniciar ou o dispositivo seja reiniciado.

O logon automático do Visitante pode ser gerenciado por meio da [política personalizada de OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Valor do URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Política  | Descrição   | Configurações  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Permite que um visitante faça logon automaticamente em um quiosque   | 1 (Sim), 0 (não, padrão.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>usar os novos aplicativos de Configurações e borda em modos de quiosque

Ao incluir aplicativos em [quiosques](hololens-kiosk.md), um administrador de ti geralmente adiciona o aplicativo ao quiosque, mas usando seu AUMID (ID do modelo de usuário de aplicativo). como o aplicativo Configurações e o aplicativo Microsoft Edge são considerados novos aplicativos e diferentes dos quiosques de aplicativos mais antigos que usam o AUMIDs para esses aplicativos precisarão ser atualizados para usar o novo AUMID.

Ao modificar um quiosque para incluir os novos aplicativos, recomendamos adicionar o novo AUMID, bem como deixar o antigo. Isso criará uma transição fácil quando os usuários atualizarem o sistema operacional e não precisarão receber novas políticas para continuar usando o quiosque como pretendido.

| Aplicativo                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| antigo aplicativo de Configurações       | HolographicSystemSettings_cw5n1h2txyewy! Aplicação            |
| novo aplicativo Configurações       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicação |
| antigo aplicativo de Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| novo aplicativo Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações de comportamento do modo de quiosque para tratamento de falhas

Em compilações mais antigas, se um dispositivo tivesse uma configuração de quiosque, que é uma combinação de acesso global atribuído e acesso atribuído ao membro do grupo do AAD, se determinar a associação do grupo do AAD falhar, o usuário verá o menu "[nada mostrado no início](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)".

a partir desta Windows versão, a experiência de quiosque fará fallback para a configuração de quiosque global (se houver) em caso de falhas durante o modo de quiosque do grupo do AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>novos URIs de Configurações para visibilidade de Configurações de página

no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) adicionamos a [política de/PageVisibilityList de Configurações](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas no aplicativo Configurações. o PageVisibilityList é uma política que permite que os administradores de ti impeçam que páginas específicas no sistema Configurações aplicativo sejam visíveis ou acessíveis, ou para fazer isso para todas as páginas, exceto aquelas especificadas.

se você visitar a [página Configurações visibilidade](settings-uri-list.md), poderá encontrar instruções para usar esse CSP e a lista de URIs disponíveis em versões anteriores.

estamos expandindo a lista de URIs de Configurações disponíveis, que os administradores de ti podem gerenciar. alguns desses URIs são para áreas disponíveis recentemente dentro do novo aplicativo Configurações. se você estiver usando Configurações política/PageVisibilityList, examine a lista a seguir e ajuste as páginas permitidas ou bloqueadas, conforme necessário.

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
| > do sistema Armazenamento > configurar Armazenamento Sense         | `ms-settings:storagepolicies`                      |
| Hora & idioma > data & hora                        | `ms-settings:dateandtime`                          |
| Hora & idioma > teclado                           | `ms-settings:keyboard`                             |
| Idioma de > do idioma da & de tempo                           | `ms-settings:language`                             |
| Idioma de > do idioma da & de tempo                           | `ms-settings:regionlanguage-languageoptions`       |
| Atualizar & segurança > redefinir & recuperação               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URIs atualizados

Anteriormente, os dois URIs a seguir não levam um usuário diretamente às páginas indicadas, mas só bloqueamos a página atualizações principais. Os seguintes itens foram atualizados para direcionar suas páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>configurando o diagnóstico de Fallback por meio do aplicativo Configurações

agora, no aplicativo Configurações, um usuário pode configurar o comportamento do [diagnóstico de Fallback](hololens-diagnostic-logs.md). na página Configurações aplicativo, navegue até a  ->  **solução de problemas** de privacidade para definir essa configuração.

> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.  

### <a name="share-things-with-nearby-devices"></a>Compartilhar coisas com dispositivos próximos

compartilhe coisas com quase Windows 10 dispositivos, incluindo computadores e outros dispositivos HoloLens 2. você pode experimentá-lo em **Configurações**  ->    ->  **experiências compartilhadas** do sistema para compartilhar arquivos ou URLs de um HoloLens para um PC. Para obter mais detalhes, leia mais sobre como [compartilhar coisas com dispositivos próximos no Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esse recurso pode ser gerenciado por meio de [conectividade/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Novos rastreamentos de diagnóstico do sistema operacional

além das soluções de problemas anteriores no aplicativo Configurações, uma nova solução de problemas foi adicionada com a adição do novo aplicativo Configurações para atualizações do sistema operacional. navegue até **Configurações**  ->  **atualização &amp;** de solução de problemas de segurança  >    >  **Windows Update** e selecione **iniciar**. Isso permite que você colete rastreamentos ao reproduzir seu problema com as atualizações do sistema operacional para auxiliar na solução de problemas com sua ti ou suporte.

### <a name="delivery-optimization-preview"></a>Visualização da otimização de entrega

com essa atualização de HoloLens, Windows Holographic for Business permite que as configurações de otimização de entrega reduzam o consumo de largura de banda para downloads de vários dispositivos HoloLens. uma descrição mais completa dessa funcionalidade junto com a configuração de rede recomendada está disponível aqui: [otimização de entrega para atualizações de Windows 10](/windows/deployment/update/waas-delivery-optimization).

As configurações a seguir são habilitadas como parte da superfície de gerenciamento e [podem ser configuradas no Intune](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algumas limitações sobre esta oferta de visualização:

- HoloLens suporte é limitado nesta visualização somente para atualizações do sistema operacional.
- Windows Holographic for Business dá suporte apenas a modos de download de HTTP e downloads de um [ponto de extremidade de Cache conectado da Microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); não há suporte para modos de download ponto a ponto e atribuições de grupo para dispositivos HoloLens no momento.
- HoloLens não oferece suporte à otimização de implantação ou de distribuição para pontos de extremidade de Windows Server Update Services.
- a solução de problemas exigirá diagnósticos no servidor de Cache conectado ou coletando um rastreamento em HoloLens em HoloLens por meio de **Configurações**  >  Windows Update de solução de problemas de segurança de & de **atualização**  >     >   .

### <a name="it-admin---update-checklist"></a>Administrador de ti – lista de verificação de atualização

Esta lista de verificação ajudará você a saber os novos itens que os recursos que estão sendo adicionados nesta atualização de recurso podem afetar suas configurações atuais de gerenciamento de dispositivo ou os novos recursos que você pode querer começar a usar.

#### <a name="updates-to-kiosk-mode"></a>Atualizações para o modo de quiosque

✔️ [**novo AUMIDs para novos aplicativos no modo de quiosque**](#use-the-new-settings-and-edge-apps-in-kiosk-modes):

Se você estava usando anteriormente o aplicativo Configurações ou Microsoft Edge em um Quiosque, substituímos esses aplicativos por novos aplicativos que usam uma ID de aplicativo diferente. Recomendamos que você leia [Novos AUMIDs para novos aplicativos no modo quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) abaixo. Isso garantirá que você continue a ter o aplicativo Configurações em seu Quiosque ou inclua o novo Microsoft Edge aplicativo. Essas alterações podem ser feitas agora e implantadas em todos os dispositivos e permitem uma transição mais suave na atualização.

✔️ [**logon automático do Visitante para Quiosques:**](#visitor-auto-logon-for-kiosks) 

Os visitantes agora podem ser conectados automaticamente a um Quiosque. Esse comportamento está em por padrão, mas pode ser gerenciado e desabilitado.

✔️ [**entrega de falha do modo de quiosque aprimorado:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Se a associação ao grupo do AAD do usuário do AAD não for determinada com êxito, a configuração de quiosque global será usada para o menu Iniciar (se presente), caso contrário, o usuário será apresentado com o menu iniciar vazio. Embora o menu inicial vazio não seja uma configuração que você possa definir diretamente, essa nova manipulação pode ser algo para informar ao departamento de suporte se você estiver usando Quiosques, pois isso pode se aplicar às suas configurações ou talvez você queira fazer novos ajustes nas configurações de acesso atribuídas.

#### <a name="updates-to-page-settings-visibility"></a>Atualizações na visibilidade Configurações página

✔️ [**URIs de Configurações para visibilidade de Configurações página**](#new-settings-uris-for-page-settings-visibility)

Se você estiver usando o [Page Configurações Visibility,](settings-uri-list.md) talvez você queira fazer ajustes em seus URIs existentes permitidos ou bloqueados.

#### <a name="updates-for-your-wdac-policy"></a>Atualizações para sua política do WDAC
✔️ se você estava bloqueando o Microsoft Edge via WDAC, será melhor atualizar sua política do WDAC. Revise o seguinte e use o código de exemplo fornecido.
#### <a name="enable-new-endpoints-for-edge"></a>Habilitar novos pontos de extremidade para o Edge
✔️ se você tiver uma infraestrutura que envolva a configuração de pontos de extremidade de rede, como proxy ou firewall, habilita esses novos pontos de extremidade para o novo Microsoft Edge aplicativo.

#### <a name="newly-configurable-items"></a>Itens configuráveis recentemente

✔️ Configurar [o Diagnóstico de Fallback:](#configuring-fallback-diagnostics-via-settings-app)você pode configurar se e quem pode coletar o Diagnóstico de Fallback.

✔️ compartilhar[coisas com dispositivos próximos:](#share-things-with-nearby-devices)você pode desabilitar o novo recurso de compartilhamento próximo.

✔️ [definindo configurações](#configuring-policy-settings-for-the-new-microsoft-edge)de política para o novo Microsoft Edge: revise as configurações recém-disponíveis para Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nova ferramenta de diagnóstico

✔️[novos rastreamentos de diagnóstico do sistema operacional:](#new-os-diagnostic-traces)colete logs relacionados às atualizações do sistema operacional.

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- [O diagnóstico offline também](hololens-diagnostic-logs.md#offline-diagnostics) incluirá informações adicionais do dispositivo para o número de série e a versão do sistema operacional.
- Corrige um problema em torno da implantação de aplicativos de linha de negócios por meio de pacotes de provisionamento de runtime.
- Corrige um problema em torno do relatório de status de instalação do aplicativo de linha de negócios.
- Corrige um problema em torno da persistência de novos pacotes de aplicativos em redefinições de dispositivo.
- Corrige um problema que pode levar a símbolos incorretos que estão sendo digitados no Edge para clientes japonês.
- Melhora a resiliência das atualizações do sistema operacional em torno de aplicativos pré-instalados, como o Edge. 
- Aborda uma confiabilidade de atualização que afeta a instalação do Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de maio de 2021
- Build 19041.1146

Melhorias e correções na atualização:
- Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nosso build mais recente, Windows Holographic, versão 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, versão 1903 – Atualização de maio de 2021
- Build 18362.1110

Melhorias e correções na atualização:
- Essa atualização de qualidade mensal não contém nenhuma alteração notável. **Esse build não receberá mais atualizações de serviço mensais.** Incentivamos você a experimentar nosso build mais recente, Windows Holographic, versão 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de abril de 2021
- Build 19041.1144

Melhorias e correções na atualização:

- Corrige um problema em torno do relatório de status de instalação do aplicativo de linha de negócios.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versão 1903 – Atualização de abril de 2021
- Build 18362.1108

Melhorias e correções na atualização:

- Resolve um problema em que o Configurações falha ao tentar alterar uma senha para uma conta local.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de março de 2021
- Build 19041.1140

Melhorias e correções na atualização:

- Os clientes que usam AdvancedPhotoCapture ou LowLagPhotoCapture para capturar fotos com o HoloLens 2 agora podem recuperar a pose da câmera até 3 segundos após a captura da foto.
- Correção de uma perda de memória no serviço Portal de Dispositivos, o problema causou o aumento do uso de memória pelo serviço que fez com que outros aplicativos falhassem ao alocar memória.
- Corrigido um problema em que os usuários inscritos no Staged Rollout não conseguem entrar no dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versão 1903 – Atualização de março de 2021
- Build 18362.1102

Melhorias e correções na atualização:

- Correção de uma perda de memória no serviço Portal de Dispositivos, o problema causou o aumento do uso de memória pelo serviço que fez com que outros aplicativos falhassem ao alocar memória.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de fevereiro de 2021
- Build 19041.1136

Melhorias e correções na atualização:

- Corrige um problema em torno da configuração inicial do dispositivo e das atualizações de aplicativo da loja.
- Aborda um problema em torno de atualizações e voos para versões HoloLens versões posteriores.
- Remoção de certificados pré-instalados não HoloLens eSIM do armazenamento raiz do eSIM.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versão 1903 – Atualização de fevereiro de 2021
- Build 18362.1098

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossos builds mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de janeiro de 2021
- Build 19041.1134

Melhorias e correções na atualização:

- Desempenho aprimorado durante a inicialização, retomada e troca de usuário quando há muitos usuários no dispositivo.
- Adicionado suporte arm32 para o [Modo de Pesquisa.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versão 1903 – Atualização de janeiro de 2021
- Build 18362.1091

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossos builds mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versão 20H2 – Atualização de dezembro de 2020
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicativos no HoloLens 2 por meio Instalador de Aplicativo

Estamos **adicionando uma nova funcionalidade (Instalador de Aplicativo)** para permitir que você instale aplicativos de forma mais direta em seus dispositivos HoloLens 2. O recurso estará em **por padrão para dispositivos não planejados.** Para evitar interrupções nas empresas, o instalador de aplicativo não **estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" **se qualquer** um dos seguintes for verdadeiro:
- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado com o [pacote de provisionamento](hololens-provisioning.md)
- A [Identidade do](hololens-identity.md) Usuário é o Azure AD

Agora você pode instalar aplicativos sem a necessidade de habilitar o Modo de Desenvolvedor ou usar Portal de Dispositivos.  Basta baixar (por USB ou por meio do Edge) o Pacote Appx para seu dispositivo e navegar até o Pacote Appx no Explorador de Arquivos ser solicitado a dar início à instalação.  Como alternativa, [inicie uma instalação de uma página da Web](/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos instalados do Microsoft Store ou sideload usando a funcionalidade de implantação de Aplicativo [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB do [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Assinatura e o certificado usado para assinar deve ser confiável para o dispositivo HoloLens antes que o aplicativo possa ser implantado.

**Instruções de instalação do aplicativo.**

1.  Verifique se o dispositivo não é considerado gerenciado
1.  Verifique se o HoloLens 2 está ligado e conectado ao computador
1.  Verifique se você está conectado ao dispositivo HoloLens 2
1.  No computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para yourdevicename\Internal Armazenamento\Downloads.   Depois de terminar de copiar o arquivo, você poderá desconectar seu dispositivo
1.  Em seu HoloLens 2, abra o Menu Iniciar, selecione Todos os apps e inicie o Explorador de Arquivos aplicativo.
1.  Navegue até a pasta Downloads. Talvez seja necessário que, no painel esquerdo do aplicativo, selecione Este dispositivo primeiro e, em seguida, navegue até Downloads.
1.  Selecione o arquivo yourapp.appxbundle.
1.  O Instalador de Aplicativo será lançado. Selecione o botão Instalar para instalar seu aplicativo.
O aplicativo instalado será automaticamente lançado após a conclusão da instalação.

Você pode encontrar aplicativos de exemplo [Windows Exemplos Universais GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) testar esse fluxo.

Leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o Instalador de Aplicativo](app-deploy-app-installer.md).  

![Instalando exemplos do MRTK por meio Instalador de Aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O acompanhamento de mão agora mantém o acompanhamento em muitos casos novos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, somente a posição de mão de mão continua a ser atualizada com base na mão real do usuário, enquanto as outras junções são inferidos com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência de acompanhamento em movimentos como desacodagem, lançamento, desalocar e deboche.  Ele também ajuda em casos em que a mão está perto de uma superfície ou mantendo um objeto .  Quando as junções de mão estão sendo inferidos, [o](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) valor de precisão por junção será definido como "Aproximado" em vez de "Alto".
- Corrigido um problema em que a redefinição de PIN para contas do Azure AD mostrava um erro "Algo deu errado.
- Os usuários devem ver muito menos falhas de OOBE pós-inicialização ao iniciar ET, Iris do aplicativo de configurações, novo usuário ou sistema de notificação.
- Os usuários devem ter um fuso horário correto saindo do OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versão 1903 – Atualização de dezembro de 2020
- Build 18362.1088

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nosso recurso mais recente do Windows Holographic, versão 20H2 – Atualização de dezembro de 2020 e o novo recurso Instalador de Aplicativo adicionado ao build.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versão 20H2
- Build 19041.1128

Windows Holographic, versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para HoloLens usuários e profissionais de TI. Do Posicionamento Ocular Automático ao Gerenciador de Certificados no Configurações, à funcionalidade aprimorada do Modo de Quiosque e aos novos recursos de instalação do Autopilot. Essa nova atualização permite que as equipes de IT tomem um controle mais granular para configurar e gerenciar HoloLens dispositivos e oferecem aos usuários experiências holográficas ainda mais perfeitas. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. O número de build principal permanecerá o mesmo e a atualização Windows indicará uma versão mensal para a versão 2004 (build 19041). Você pode ver o número de build na tela Configurações > sobre para confirmar que está no build 19041.1128+, mais recente disponível. Para atualizar para a versão mais recente, abra o aplicativo Configurações, acesse Atualizar & Segurança e toque em Verificar se há Atualizações. Para obter mais informações sobre como gerenciar HoloLens atualizações, visite [Gerenciar HoloLens atualizações.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novidades no Windows Holographic, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte à posição do olho automático](hololens-release-notes.md#auto-eye-position-support) | Calcula ativamente as posições dos olhos sem que os usuários passam pela calibragem do Acompanhamento Ocular.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que novos métodos mais simples instalem e removam certificados do Configurações aplicativo.     |
| [Provisionamento de início automático de USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | O provisionamento de pacotes em unidades USB solicita automaticamente a página de provisionamento em OOBE.                                                         |
| [Confirmar automaticamente os pacotes de provisionamento no OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante o OOBE na página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a iniciação automática de provisionamento e a confirmação automática. |
| [Usando o Autopilot com Wi-Fi conexão](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o autopilot do dispositivo Wi-Fi sem a necessidade de adaptador ethernet. |
| [Tenantlockdown CSP e Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após o registro de locatário e a política ser aplicada, o dispositivo só poderá ser inscrito nesse locatário sempre que o dispositivo for redefinido ou flash novamente. |
| [Acesso Atribuído Global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para o modo de quiosque de vários aplicativos que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
| [Iniciar automaticamente um aplicativo no quiosque de vários aplicativos](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define um aplicativo a ser lançado automaticamente ao entrar em um modo de quiosque de vários aplicativos.                                                        |
| [Alterações no comportamento do modo de quiosque para tratamento de falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | A falha no modo de quiosque agora tem fallback restritivo.                                                                                                |
| [HoloLens Políticas](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para HoloLens.     |
| [Armazenar em cache a associação do Grupo do Azure AD para quiosque offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os usuários usem o cache de associação de grupo para usar o modo de quiosque offline para o número definido de dias.                                        |
| [Novas políticas de restrição de dispositivo HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Políticas de gerenciamento de dispositivos habilitadas recentemente para HoloLens 2.                                                                                |
| [Novas políticas de energia para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recém-suportadas para configurações de tempo de vida de energia.  |
| [Atualizar políticas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas habilitadas recentemente, permitindo o controle de atualizações.           |
| [Habilitada Configurações de página para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Política para escolher quais páginas são vistas Configurações aplicativo.             |
| [Modo de pesquisa](hololens-release-notes.md#research-mode) | Usando o modo de pesquisa HoloLens 2. |
| [Comprimento da gravação aumentado](hololens-release-notes.md#recording-length-increased) | As gravações do MRC não são mais limitados a 5 minutos. |
| [Melhorias e correções na atualização](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correções adicionais na atualização.   |

### <a name="auto-eye-position-support"></a>Suporte à posição do olho automático

No HoloLens 2, as posições de olho permitem posicionamento preciso do holograma, experiência de exibição confortável e qualidade de exibição aprimorada. As posições de olho são computadas internamente como parte da computação de acompanhamento ocular. No entanto, isso exige que cada usuário passa pela calibragem de acompanhamento ocular, mesmo quando a experiência pode não exigir entrada de olhar.

**A AEP (Posição Ocular Automática)** permite esses cenários com uma maneira sem interação de computar posições de olho para o usuário. A Posição Ocular Automática começa a funcionar em segundo plano automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de acompanhamento ocular anterior, a Posição Ocular Automática começará a fornecer as posições de olho do usuário para o sistema de exibição após um tempo de processamento de 20 a 30 segundos. Os dados do usuário não são persistentes no dispositivo e, portanto, esse processo será repetido se o usuário sair e colocar o dispositivo novamente ou se o dispositivo reiniciar ou sair do modo de sleep.

Há algumas alterações de comportamento do sistema com o recurso Posição Ocular Automática quando um usuário nãocalibizado coloca o dispositivo. Nesse contexto, um usuário nãocalibizado refere-se a alguém que não passou pelo processo de calibragem de acompanhamento ocular no dispositivo anteriormente.

| Aplicativo ativo | Comportamento anterior | Comportamento da Windows Holographic, versão 20H2 Atualização |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo habilitado para não olhar ou Shell Holographic |A caixa de diálogo de prompt de calibragem de acompanhamento ocular é exibida. | Nenhum prompt é exibido. |
| Aplicativo habilitado para o gaze | A caixa de diálogo de prompt de calibragem de acompanhamento ocular é exibida. | O prompt de calibragem de acompanhamento ocular é exibido somente quando o aplicativo acessa o fluxo de olhar. |

Se o usuário faz a transição de um aplicativo sem olhar habilitado para um que acessa os dados de olhar, o prompt de calibragem será exibido. 

Todos os outros comportamentos do sistema serão semelhantes a quando o usuário atual não tiver uma calibragem ativa de acompanhamento ocular. Por exemplo, o gesto De início com uma mão não será habilitado. Não haverá nenhuma alteração na experiência inicial para configuração inicial.

Para experiências que exigem dados de olhar com o olhar ou posicionamento de holograma muito preciso, recomendamos que usuários nãocalibados executem a calibragem de acompanhamento ocular. Ele pode ser acessado no prompt de calibragem de acompanhamento ocular ou iniciando o aplicativo Configurações no menu iniciar e, em seguida, selecionando Calibragem do > > Calibragem ocular **> Calibragem** de olho.

Essas informações podem ser encontradas posteriormente com [outras informações de calibragem](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança e conformidade do dispositivo por meio do novo Gerenciador de Certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

Na Windows Holographic versão 20H2, estamos adicionando um Gerenciador de Certificados no HoloLens 2 Configurações aplicativo. vá para **Configurações > atualizar & segurança > certificados**. Esse recurso fornece uma maneira simples e amigável de usuário para exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar que um certificado foi implantado corretamente ou de confirmar que foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade desejada e está funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para localizar um certificado específico na lista rapidamente, há opções para classificar por nome, loja ou data de validade. Os usuários também podem procurar um certificado diretamente. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **informações**. 

A instalação do certificado atualmente dá suporte a arquivos. cer e. CRT. Os proprietários de dispositivo podem instalar certificados no computador local e no usuário atual;  todos os outros usuários só podem instalar no usuário atual. os usuários só podem remover certificados instalados diretamente da interface do usuário do Configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Conexão seu HoloLens 2 a um PC.
1.  coloque o arquivo de certificado que você deseja instalar em um local no seu HoloLens 2.
1.  navegue até **Configurações aplicativo > atualizar & segurança > certificados** e selecione instalar um certificado.
1.  Clique em **Importar arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione o **local do repositório**.
1.  Selecione **repositório de certificados**.
1.  Clique em **Instalar**.

O certificado agora deve estar instalado no dispositivo.

#### <a name="to-remove-a-certificate"></a>Para remover um certificado: 
1. navegue até **Configurações aplicativo > atualização e segurança > certificados**.
1. Procure o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **remover**
1. Selecione **Sim** quando solicitada a confirmação.

![visualizador de certificados no aplicativo Configurações](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado](images/certificate-device-install.jpg)

Essas informações podem ser encontradas posteriormente [em uma nova página do Gerenciador de certificados](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Inicialização automática do provisionamento de USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante o OOBE.

Antes desta versão, os usuários precisavam iniciar a tela de provisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora, os usuários podem ignorar a combinação de botões, usando um pacote de provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagindo do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB for deixada conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como observará que outros que estão sendo conectados.

para obter mais informações sobre como aplicar pacotes de provisionamento durante o OOBE, visite a documentação de [provisionamento do HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) .

informações adicionais sobre o [provisionamento automático de um USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) podem ser encontradas na documentação de provisionamento do HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmar automaticamente os pacotes de provisionamento no OOBE
- Processo automatizado permitindo menos interação do usuário, quando a página pacote de provisionamento for exibida, ele aplicará automaticamente todos os pacotes listados.

Quando a tela principal de provisionamento aparecer, o OOBE será reduzido 10 segundos antes de iniciar a aplicação de todos os pacotes de provisionamento automaticamente. Os usuários ainda podem [confirmar ou cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dentro desse 10 segundos depois de verificar os pacotes esperados.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para interações de dispositivo reduzidas para provisionamento. 

ao combinar o lançamento automático do provisionamento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um usuário pode provisionar HoloLens 2 dispositivos automaticamente sem usar a interface do usuário do dispositivo ou até mesmo utilizar o dispositivo. Você pode continuar a usar a mesma unidade USB e pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos de uma só vez na mesma área. 

1. [crie um pacote de provisionamento](hololens-provisioning.md) usando [Windows Designer de configuração](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie o pacote em uma unidade de armazenamento USB.
1. [atualize seu HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) para [19041,1361 ou build mais recente](https://aka.ms/hololens2previewdownload). 
1. Quando o [complemento de recuperação avançada](https://www.microsoft.com/store/productId/9P74Z35SFRS8) concluiu o seu dispositivo, desconecte seu cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. quando o dispositivo HoloLens 2 for inicializado no OOBE, ele detectará automaticamente o pacote de provisionamento na unidade USB e iniciará a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Agora, seu dispositivo está configurado e [exibirá a tela de provisionamento bem-sucedido](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Usando o piloto automático com conexão Wi-Fi
- Necessidade de adaptadores USB-C para redução de Ethernet para reduzir as necessidades de hardware, permitindo que o AutoPilot funcione em dispositivos Wi-Fi conectados.

agora, durante o oobe, quando você se conectar HoloLens 2 com Wi-Fi, o OOBE verificará se há um perfil do autopilot para o dispositivo. Se um for encontrado, ele será usado para concluir o restante da União do AAD e do fluxo de registro. Em outras palavras, usar Ethernet para USB-C ou Wi-Fi para o adaptador USB-C não é mais um requisito, no entanto, ele continuará a funcionar se fornecido no início do OOBE. saiba mais sobre o [piloto automático para dispositivos HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP Tenantlockdown e piloto automático
- Mantém os dispositivos no locatário da organização bloqueando-os para o locatário mesmo por meio da redefinição do dispositivo ou do reflash. Com segurança adicional, desautorizando a criação de conta no por meio do provisionamento. 

os dispositivos HoloLens 2 agora dão suporte ao CSP TenantLockdown a partir do [Windows versão 20H2 do Holographic](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) o CSP permite que HoloLens 2 sejam vinculados ao registro do MDM usando somente o autopilot. depois que o nó RequireNetworkInOOBE do CSP do TenantLockdown for definido como true ou false (inicialmente definido) no HoloLens 2, esse valor permanecerá no dispositivo, independentemente da atualização, das atualizações do sistema operacional, etc. 

depois que o nó RequireNetworkInOOBE de CSPs do TenantLockdown for definido como true no HoloLens 2, o OOBE aguardará indefinidamente que o perfil do autopilot seja baixado e aplicado com êxito, após a conectividade de rede. 

depois que o nó RequireNetworkInOOBE de CSPs do TenantLockdown for definido como true no HoloLens 2, as operações a seguir não serão permitidas no OOBE: 
- Criando usuário local usando provisionamento de tempo de execução 
- Executando a operação de ingresso do Azure AD por meio do provisionamento de tempo de execução 
- Selecionando quem possui o dispositivo na experiência do OOBE 

#### <a name="how-to-set-this-using-intune"></a>Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique true para o nó RequireNetworkInOOBE, conforme mostrado abaixo.
O valor de OMA-URI deve ser./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configurando o bloqueio locatário via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. torne o membro do dispositivo HoloLens 2 do grupo criado na etapa anterior e acione a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com êxito. depois que essa configuração de dispositivo se aplicar com êxito no dispositivo HoloLens 2, os efeitos de TenantLockdown estarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>como remover a definição de RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune? 
1. remova o HoloLens 2 do grupo de dispositivos ao qual a configuração de dispositivo criada acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em OMA URI personalizado e especifique false para RequireNetworkInOOBE, conforme mostrado abaixo. O valor de OMA-URI deve ser./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE como false por meio do URI OMA no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. torne o membro do dispositivo HoloLens 2 do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com êxito. depois que essa configuração de dispositivo se aplicar com êxito no dispositivo HoloLens 2, os efeitos de TenantLockdown ficarão inativos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>o que aconteceria durante o OOBE, se o perfil do autopilot não for atribuído em um HoloLens depois que TenantLockdown for definido como true? 
O OOBE aguardará indefinidamente o perfil do AutoPilot para baixar e a caixa de diálogo a seguir será apresentada. Para remover efeitos de TenantLockdown, o dispositivo deve ser registrado primeiro com seu locatário original usando somente o AutoPilot e RequireNetworkInOOBE deve ser desmarcado, conforme descrito na etapa anterior, antes que as restrições apresentadas pelo CSP do TenantLockdown sejam removidas. 

![Exibição no dispositivo para quando a política é imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

Essas informações agora podem ser encontradas junto com o restante do piloto automático em [TENANTLOCKDOWN CSP e AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Acesso atribuído global – modo de quiosque
- Gerenciamento de identidades reduzido para quiosque, habilitando o novo método de quiosque que aplica o modo de quiosque no nível do sistema.

esse novo recurso permite que um administrador de ti configure um dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos que é aplicável no nível do sistema, não tem nenhuma afinidade com nenhuma identidade no sistema e se aplica a todos que se conectam ao dispositivo. leia sobre esse novo recurso em detalhes na [HoloLens quiosque de acesso global atribuído](hololens-global-assigned-access-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Lançamento automático de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada com a abertura automática do aplicativo, aumentando ainda mais as seleções de interface do usuário e aplicativo escolhidas para experiências de modo de quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e apenas um aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração acesso atribuído. 

O aplicativo é automaticamente lançado quando o usuário se insiciona. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações no comportamento do modo de quiosque para tratamento de falhas
- Modo de quiosque mais seguro eliminando os aplicativos disponíveis em falhas no modo de quiosque. 

Anteriormente, ao encontrar falhas na aplicação do modo de quiosque, HoloLens usado para mostrar todos os aplicativos no menu Iniciar. Agora, Windows versão holográfica 20H2 no caso de falhas, nenhum aplicativo será mostrado no menu iniciar, como abaixo: 

![Imagem da aparência do modo de quiosque agora quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Políticas
- Opções de gerenciamento de dispositivo especificamente para HoloLens criadas para gerenciar o dispositivo. 

Novas políticas de realidade misturada foram criadas para HoloLens 2 dispositivos Windows Holographic versão 20H2. As novas configurações controláveis incluem: definir brilho, definir volume, desabilitar a gravação de áudio em capturas de realidade misturada, definir quando o diagnóstico pode ser coletado e cache de associação de grupo do AAD.  

| Nova HoloLens política                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados para que pressionar ele não altere o brilho.       | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que os botões de volume sejam desabilitados para que pressionar ele não altere o volume.               | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | Desabilita o microfone para que nenhuma gravação de áudio seja possível HoloLens 2.                      | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os logs de diagnóstico podem ser coletados.                               | 0 Desabilitado, 1 Habilitado para Proprietários de Dispositivos, 2 Habilitado para todos (Padrão) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla por quantos dias o cache de associação de grupo do Azure AD é usado para o quiosque destinado a grupos do Azure AD. | Veja abaixo.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Armazenar em cache a associação do Grupo do Azure AD para quiosque offline
- Quiosques Offline habilitados para serem usados com grupos do AAD por até 60 dias.

Essa política controla por quantos dias o cache de associação de grupo do Azure AD tem permissão para ser usado para configurações de Acesso Atribuído destinados a grupos do Azure AD para usuários com entrada. Depois que esse valor de política for definido como valor maior que 0, o cache será usado caso contrário, não.  

Nome: AADGroupMembershipCacheValidityInDays Valor de URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín. – 0 dias  
Máximo – 60 dias 

Etapas para usar essa política corretamente: 
1. Crie um perfil de configuração de dispositivo para quiosque destinado a grupos do Azure AD e atribua-o HoloLens dispositivos. 
1. Crie uma configuração de dispositivo baseada em URI de OMA personalizada que define esse valor de política para o número desejado de dias (> 0) e atribua-o HoloLens dispositivos. 
    1. O valor de URI deve ser inserido na caixa de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre mín/máx. permitido.
1. Registrar HoloLens dispositivos e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário do Azure AD entre 1 quando a Internet estiver disponível, depois que o usuário entrar e a associação ao grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário do Azure AD 1 pode HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita x número de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD N. O ponto principal aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet para que, pelo menos, uma vez possamos determinar que ele é membro do grupo do Azure AD ao qual a configuração de Quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para um usuário do Azure AD, o comportamento de falha será mencionado em ambientes "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Novas políticas de restrição de dispositivo HoloLens 2
- Permite que os usuários gerenciem políticas específicas de gerenciamento de dispositivo, como bloquear a adição ou remoção de pacotes de provisionamento.

Políticas habilitadas recentemente que permitem mais opções de gerenciamento HoloLens 2 dispositivos. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Essas duas novas regras para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas [Restrições Comuns de Dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Em relação ao [RemoteLock,](/windows/client-management/mdm/remotelock-csp)HoloLens dará suporte apenas à configuração ./Vendor/MSFT/RemoteLock/Lock. Não há suporte para as configurações que lidam com o PIN, como redefinição e recuperação.

### <a name="new-power-policies-for-hololens-2"></a>Novas políticas de energia para HoloLens 2
- Mais opções para quando HoloLens ou bloqueios por meio de políticas de energia. 

Essas políticas recém-adicionadas permitem que os administradores controlem estados de energia, como tempo de ociosidade. Para ler mais sobre cada política individual, clique no link dessa política.

|     Link da documentação da política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado Windows Designer de Configuração, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas regras para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas [Restrições Comuns de Dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Para uma experiência consistente HoloLens 2, verifique se os valores para DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery estão definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Consulte [Exibir, manter e hibernar temporizadores ociosos](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre a espera moderna.

### <a name="newly-enabled-update-policies-for-hololens"></a>Políticas de atualização recém-habilitadas para HoloLens
- Mais opções para quando as Atualizações são instaladas ou desabilitando o botão Pausar Atualizações para garantir atualizações.

Essas políticas de atualização agora estão habilitadas HoloLens 2 dispositivos:
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Detalhes completos sobre essas políticas de atualização e como usá-las para HoloLens dispositivos podem ser lidos aqui em Gerenciar [HoloLens atualizações.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Habilitada Configurações de página para HoloLens 2
- Maior controle de interface do usuário no aplicativo Configurações, o que pode ser confundido para mostrar uma seleção limitada de páginas.

Agora habilitamos uma política que permite que os administradores de IT impeçam que páginas específicas no aplicativo system Configurações sejam visíveis ou acessíveis ou para fazer isso para todas as páginas, exceto aquelas especificadas. Para saber como personalizar totalmente esse recurso, clique no link abaixo.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais configurações de página você pode personalizar HoloLens 2, visite nossa [página Configurações URIs.](settings-uri-list.md) 
 
![Captura de tela das horas ativas que estão sendo modificadas no Configurações aplicativo](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de pesquisa
No Modo de Pesquisa, o HoloLens 2 se torna uma ferramenta de pesquisa visual computacional. Em comparação com as edições anteriores, o Modo de Pesquisa para HoloLens 2 tem as seguintes vantagens:
-   Além dos sensores expostos no modo de pesquisa HoloLens (1ª geração), agora fornecemos acesso ao sensor de IMU, incluindo um acelerômetro, um giroscope e um magnetômetro.
-   HoloLens 2 fornece novos recursos que podem ser usados junto com o Modo de Pesquisa. Especificamente, acesso a APIs articuladas de acompanhamento e acompanhamento ocular que podem fornecer um conjunto mais rico de experimentos.

Os pesquisadores agora têm a opção de habilenciar o Modo de Pesquisa em seus HoloLens para acessar todos esses fluxos de sensores de imagem bruta voltados para o exterior. O Modo de Pesquisa HoloLens 2 também fornece acesso ao acelerômetro, ao giroscope e às leituras de magnetômetro. Para proteger a privacidade dos usuários, as imagens brutas da câmera de acompanhamento ocular não estão disponíveis por meio do Modo de Pesquisa, mas a direção do olhar está disponível por meio de APIs existentes.

Confira a [documentação do Modo de Pesquisa](/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

### <a name="recording-length-increased"></a>Comprimento da gravação aumentado
Devido aos comentários dos clientes, aumentamos o tamanho da gravação das [capturas de realidade misturada.](holographic-photos-and-videos.md) As capturas de realidade misturada não serão mais limitadas a 5 minutos por padrão, mas, em vez disso, calcularão o comprimento máximo da gravação com base no espaço em disco disponível. O dispositivo estima a duração máxima da gravação de vídeo com base no espaço em disco disponível até 80% do espaço total em disco.

> [!NOTE]
> O HoloLens usará o comprimento de gravação de vídeo padrão (5 minutos) se ocorrer um dos seguintes:
> - A duração máxima estimada da gravação é menor do que o padrão de 5 minutos.
> - O espaço em disco disponível é menor que 20% do espaço total em disco.

Você pode encontrar os requisitos completos em nossa [documentação de fotos e vídeos](holographic-photos-and-videos.md#maximum-recording-length) holográficos. 

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:
- Mais telas no OOBE agora estão no modo escuro.
- Saiba mais sobre o conteúdo que deve apontar para a Política de Privacidade mais recente online.
- Foi resolvido um problema em que os usuários não podiam provisionar perfis VPN por meio de pacotes de provisionamento.
- Correção do problema de configuração de proxy para conexão VPN.
- Política atualizada para desabilitar a enumeração de funções USB por meio do MDM para NCM para AllowUsbConnection.
- Foi resolvido um problema que impedia que um dispositivo HoloLens aparecendo no Explorador de Arquivos por MTP (Protocolo de Transferência de Mídia) quando o dispositivo é configurada como um [quiosque](hololens-kiosk.md)de aplicativo único. Observe que o MTP (e a conexão USB em geral) ainda podem ser desabilitados usando a [política AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Corrigido um problema em que os ícones no menu Iniciar eram dimensionados corretamente no modo quiosque.
- Corrigido um problema devido ao cache HTTP interferir no modo de quiosque direcionado para grupos do Azure AD.
- Corrigido um problema em que os usuários não conseguiram usar o botão Emparelhar depois de habilitar o modo desenvolvedor com pacotes de provisionamento, a menos que eles desabilita e reabilitar o modo de Desenvolvedor.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versão 1903 – Atualização de novembro de 2020
- Build 18362.1085

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nosso build de versão de recurso mais recente Windows Holographic, versão 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versão 2004 – Atualização de outubro de 2020
- Build 19041.1124
 
Melhorias e correções na atualização:

- Remoção de uma verificação desnecessária que causou a falha do sistema de runtime.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versão 1903 – Atualização de outubro de 2020
- Build 18362.1081

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossos builds mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versão 2004 – Atualização de setembro de 2020
- Build 19041.1117

Melhorias e correções na atualização:

- Resolve um problema que impedia Visual Studio depurar um aplicativo quando SupportsMultipleInstances="true" está presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy NCSI para resolver a falha na detecção da Internet por proxy de rede. O NCSI pode usar proxy de computador e proxy por perfil para detecção de conectividade com a Internet. O proxy por usuário terá suporte do NCSI na versão futura.
- Na maioria Windows Mixed Reality dispositivos, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor a ser alinhado aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores forma.
- Maior robustez de acompanhamento de mão que resultará em menos perdas de acompanhamento em cenários específicos.
- Esta versão contém uma correção para melhorar a qualidade do timestamp de áudio que pode ter contribuído para problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versão 1903 – Atualização de setembro de 2020
- Build 18362.1079

Melhorias e correções na atualização:

- Na maioria Windows Mixed Reality dispositivos, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor a ser alinhado aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores forma.
- Maior robustez de acompanhamento de mão que resultará em menos perdas de acompanhamento em cenários específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versão 2004 – Atualização de agosto de 2020
- Build 19041.1113

Melhorias e correções na atualização:

- Configurações aplicativo não seguirá mais o usuário em Experiências de Registro de Íris ou Calibragem de Acompanhamento Ocular.
- Corrigido um bug em que a aplicação de um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como conectar-se a uma rede) não executaria as outras ações após a reinicialização do dispositivo devido à renomeação.
- Esquema de cores modificado dos fluxos iniciais de instalação do dispositivo para melhorar a qualidade visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versão 1903 – Atualização de agosto de 2020
- Build 18362.1074

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossos builds mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versão 2004 – Atualização de julho de 2020
- Build 19041.1109

Melhorias e correções na atualização:

- Os desenvolvedores agora podem escolher entre habilenciar ou desabilitar a Portal de Dispositivos exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Alteração do brilho da caixa de entrada padrão para 100%.
- Foi resolvido um problema sobre o encaminhamento HTTPS para o Windows Portal de Dispositivos no HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versão 1903 – Atualização de julho de 2020
- Build 18362.1071

Melhorias e correções na atualização:

- Corrigido um problema que poderia fazer com que os hologramas desaparecessem em aplicativos unity ao perder ou recuperar o controle.
- Corrigido um problema que fez com que aplicativos HoloLens exclusivos falham no shell ao usar o HoloLens Emulator com aceleração de hardware em determinados dispositivos.
- Foi resolvido um problema referente ao encaminhamento HTTPS para o Windows Portal de Dispositivos no HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versão 2004 – Atualização de junho de 2020
- Build 19041.1106

Melhorias e correções na atualização:

- Os gravadores personalizados do MRC agora terão novos valores padrão para determinadas propriedades, caso não sejam especificados.
  - No efeito *de vídeo do MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (headset imersivo))
  - No efeito *de áudio mrc*:
    - LoopbackGain (o valor atual de "Ganho de Áudio do Aplicativo" na página Captura de Realidade Misturada no Windows Portal de Dispositivos)
    - MicrophoneGain (o valor atual de "Ganho de Áudio de Microfone" na página Captura de Realidade Misturada no Windows Portal de Dispositivos)
- Correção de um bug para melhorar a qualidade do áudio em cenários de captura de realidade misturada. Especificamente, essa correção deve eliminar falhas de áudio na gravação quando **o** menu Iniciar for exibido.
- Melhor estabilidade do holograma em vídeos gravados.
- Resolvido um problema em que a captura de realidade misturada não podia gravar vídeo depois que o dispositivo era deixado em estado de espera por vários dias.
- A API HolographicSpace.UserPresence geralmente está desabilitada para aplicativos unity. Esse comportamento evita um problema que fez alguns aplicativos pausarem quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" tenha sido habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity e 2019.3.4 e posteriores.
- Quando você acessa Portal de Dispositivos uma conexão Wi-Fi, um navegador da Web pode impedir o acesso a devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo se o certificado do dispositivo fosse confiável anteriormente. Nesse caso, você não pode avançar para Portal de Dispositivos, pois não há nenhuma opção para ignorar avisos de segurança. Essa atualização resolveu o problema. Se o certificado do dispositivo tiver sido baixado anteriormente e for confiável em um computador para remover avisos de segurança do navegador e o erro SSL ocorrer, o novo certificado terá que ser baixado e confiável para resolver os avisos de segurança do navegador.
- Habilitada a capacidade de criar um pacote de provisionamento de runtime que pode instalar um aplicativo usando pacotes MSIX.
- Adicionada uma configuração **no Configurações** System Hologramas que permite aos usuários remover automaticamente todos os hologramas da casa da Realidade Misturada quando o dispositivo  >    >   for desligado.
- Corrigido um problema que HoloLens aplicativos que alteram o formato de pixel para renderizar preto no HoloLens emulador.
- Corrigido um bug que causava uma falha durante o logon do Iris.
- Corrigido um problema sobre downloads de lojas repetidas para aplicativos já atuais.
- Corrigido um bug para impedir que aplicativos imersivos abriam Microsoft Edge repetidamente.
- Corrigido um problema com lançamentos do aplicativo Photos na inicialização inicial após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versão 1903 – Atualização de junho de 2020
- Build 18362.1064

Melhorias e correções na atualização:

- Os gravadores personalizados do MRC terão novos valores padrão para determinadas propriedades, caso não sejam especificados.
  - No efeito *de vídeo do MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (headset imersivo))
  - No efeito *de áudio mrc*:
    - LoopbackGain (o valor atual de "Ganho de Áudio do Aplicativo" na página Captura de Realidade Misturada no Windows Portal de Dispositivos)
    - MicrophoneGain (o valor atual de "Ganho de Áudio de Microfone" na página Captura de Realidade Misturada no Windows Portal de Dispositivos)
- A API HolographicSpace.UserPresence geralmente está desabilitada para aplicativos unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração a ser executado em segundo plano estiver habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity e 2019.3.4 e posteriores.
- Corrigido um problema que HoloLens aplicativos que alteram o formato de pixel para renderizar preto no HoloLens Emulator.
- Corrigido um problema sobre lançamentos do aplicativo Photos na inicialização inicial após a atualização da versão 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versão 2004  
- Build – 19041.1103

A atualização de software principal de maio de 2020 para o HoloLens 2, *Windows Holographic, versão 2004* inclui uma série de novos recursos interessantes, como suporte para o Windows Autopilot, modo escuro do aplicativo, suporte a Ethernet USB para hotspots 5G/LTE e muito mais. Para atualizar para a versão mais recente, abra **o aplicativo Configurações,** acesse Atualizar & Segurança e selecione o botão   Verificar  **** **atualizações.**   

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurar e configurar perfeitamente novos dispositivos para produção usando Windows AutoPilot                 |
|       Suporte a FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar perfeitamente um pacote de provisionamento de uma unidade USB à sua HoloLens                              |
|       Status de instalação do aplicativo                 |          Verifique o status da instalação no Configurações aplicativo para aplicativos que foram HoloLens 2 por meio do MDM               |
|       CSPs (provedores de serviços de configuração)   |          Novos provedores de serviços de configuração adicionados para aprimorar os recursos de controle de administrador                 |
|       Suporte a USB 5G/LTE                       |          A funcionalidade de Ethernet USB expandida habilita o suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que suportam os modos escuro e claro, melhorando a experiência de exibição        |
|       Comandos de voz                             |          Suporte para comandos de voz do sistema adicionais para HoloLens de mãos livres                           |
|       Melhorias no acompanhamento de mão                 |          As melhorias de acompanhamento de mão torna os botões e as interações de slate 2D mais precisas                        |
|       Melhorias e correções de qualidade                 |          Vários aprimoramentos de desempenho e confiabilidade do sistema em toda a plataforma                            |

### <a name="support-for-windows-autopilot"></a>Suporte para Windows Autopilot

Windows O Autopilot para HoloLens 2 permite que o canal de vendas do dispositivo se inscreva previamente HoloLens seu locatário do Intune. Quando os dispositivos chegam, eles estão prontos para auto-implantar como dispositivos compartilhados em seu locatário. Para aproveitar a auto-implantação, o dispositivo deve se conectar a uma rede durante a primeira tela na instalação usando um USB-C-to-Ethernet.

Depois que um usuário inicia o processo de auto-implantação do Autopilot, o processo conclui as seguintes etapas:

1. Ingressar o dispositivo no Azure Active Directory (Azure AD).
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou em outro serviço MDM).
1. Baixe as políticas, os certificados e os perfis de rede direcionados ao dispositivo.
1. Provisione o dispositivo.
1. Apresente a tela de login ao usuário.

Saiba mais no guia [de avaliação Windows Autopilot para HoloLens 2.](hololens2-autopilot.md)

*Entre em contato com seu Gerente de Conta para ingressar na versão prévia do AutoPilot agora. Os dispositivos prontos para piloto automático começarão a ser entregados em breve.*

### <a name="fido2-security-key-support"></a>Suporte à chave de segurança FIDO2

Alguns usuários compartilham um HoloLens com outros em um ambiente corporativo ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. O Fast Identity Online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre perfeitamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação sem senha baseado em padrões "imfragável" que pode vir em qualquer fator de forma. FIDO é um padrão aberto para autenticação sem senha. Ele permite que usuários e organizações se inscrevam em seus recursos sem um nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma interna em um dispositivo.

Para começar, consulte [Habilitar a login](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)da chave de segurança sem senha.

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Registro de MDM aprimorado por meio do pacote de provisionamento

Os pacotes de provisionamento permitem HoloLens configuração por meio de um arquivo de configuração, em vez de HoloLens uma experiência inicial. Anteriormente, os pacotes de provisionamento tinham que ser copiados para o HoloLens memória interna. Agora eles podem estar em uma unidade USB, portanto, é mais fácil reutilizar em vários HoloLens e você pode provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também suportam um campo para se registrar no gerenciamento de dispositivos, portanto, não há nenhuma configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do Windows Designer de Configuração do Windows em seu computador.
1. Selecione **Provisionamento HoloLens Dispositivos**  >  **Provisionamento HoloLens 2 dispositivos**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C em qualquer dispositivo com flash HoloLens. Em seguida, pressione **os botões de** energia para baixo do volume para aplicar o pacote de  +   provisionamento.

### <a name="line-of-business-application-install-status"></a>Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento de aplicativos MDM para aplicativos de linha de negócios são essenciais para HoloLens. Administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **Contas** de Configurações Acesso ao trabalho ou à escola  >    >    >  **Clique em suas Informações da**  >  **conta.**

### <a name="additional-csps-and-policies"></a>CSPs e políticas adicionais

Um [CSP (provedor de serviços de configuração)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou excluir definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores têm sobre dispositivos HoloLens implantados. Para ver a lista de CSPs com suporte pelo HoloLens, consulte [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

Novidades nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa configure políticas em Windows dispositivos. Nesta versão, adicionamos novas políticas para HoloLens, que são listadas aqui. Para saber mais, confira [CSPs de política com suporte HoloLens 2](/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

O provedor de serviços de configuração do NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, confira [NETWORKQOSPOLICY CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Suporte de Ethernet USB expandido para dispositivos 5G/LTE de compartilhamento de Internet

foi adicionado suporte para habilitar determinados dispositivos de banda larga móvel, como telefones 5G/LTE e hotspots Wi-Fi, quando eles estão vinculados ao HoloLens 2 via USB. Esses dispositivos agora são exibidos nas **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos de banda larga móvel que exigem um driver externo.) Essa funcionalidade permite conexões de alta largura de banda quando Wi-Fi não está disponível e Wi-Fi compartilhamento de Internet não é um desempenho suficiente. para saber mais sobre os dispositivos usb com suporte, consulte [Conexão a Bluetooth e dispositivos usb-C](hololens-connect-devices.md).  

### <a name="hand-tracking-improvements"></a>Aprimoramentos de acompanhamento de mão

Esta versão inclui vários aprimoramentos de acompanhamento:

- **Apontando para a estabilidade:** O sistema agora se resiste à curva do dedo do índice quando ele fica obstruído pelo Palm. Essa alteração melhora a exatidão ao enviar botões, digitar, rolar conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Melhoramos a detecção do gesto de toque do ar. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta suas mãos em seus lados.
- **Confiabilidade do comutador do usuário:** O sistema agora é mais rápido e mais confiável na atualização do tamanho da mão quando você compartilha um dispositivo.
- **Roubo reduzido:** Melhoramos o manuseio de casos em que há mais de duas mãos na exibição dos sensores. Se várias pessoas estiverem trabalhando juntas, agora há uma chance muito menor de que a mão controlada vai "saltar" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Corrigido um problema que fazia com que o rastreamento à mão deixasse de funcionar quando o dispositivo está sob carga alta.

### <a name="dark-mode"></a>Modo escuro

muitos aplicativos Windows agora dão suporte aos modos escuro e claro. HoloLens 2 os usuários podem escolher o modo padrão para aplicativos que dão suporte a ambos. após a atualização, o modo de aplicativo padrão é "escuro", mas você pode alterar facilmente essa configuração: navegue até **Configurações**  >  cores do **sistema**  >    >  **escolha o modo de aplicativo padrão**. 

Esses aplicativos "integrados" suportam o modo escuro: 

- Configurações 
- Microsoft Store 
- Email 
- Calendário 
- Explorador de Arquivos 
- Hub de Feedback 
- OneDrive 
- Fotos 
- Visualizador 3D 
- Filmes e TV 

![Xadrez do modo escuro do Windows](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, consulte [usar sua voz para operar HoloLens](hololens-cortana.md). consulte também [idiomas com suporte para o HoloLens 2](hololens2-language-support.md).  

### <a name="cortana-updates"></a>atualizações de Cortana

o aplicativo atualizado integra-se com o Microsoft 365 para ajudá-lo a fazer mais em seus dispositivos (atualmente em US-English apenas). no HoloLens 2, Cortana não dá mais suporte a determinados comandos específicos do dispositivo, como ajustar o volume ou reiniciar. Agora, há suporte para essas opções nos novos comandos de voz do sistema. saiba mais sobre o novo aplicativo Cortana em nosso [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibragem de vídeo ativo. Esse recurso melhora a estabilidade e o alinhamento de hologramas. Agora, eles permanecem em vigor quando você move sua cabeça do lado para o outro.
- corrigido um bug em que Wi-Fi streaming para HoloLens foi interrompido periodicamente. Se um aplicativo indicar que ele precisa de streaming de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correção de um dispositivo suspenso que ocorreu durante o streaming no modo de pesquisa.
- Corrigido um bug em que, em alguns casos, o usuário certo não seria exibido na tela de entrada ao retomar uma sessão.
- corrigido um problema em que os usuários não podiam exportar logs do MDM por meio de **Configurações**.
- Correção de um problema em que a precisão do acompanhamento de olho imediatamente após a configuração pronta para uso pode ser menor do que o esperado.
- Corrigido um problema em que o subsistema de acompanhamento de olho falhou ao inicializar ou executar a calibragem sob determinadas condições.
- Corrigido um problema em que a calibragem de olhos seria solicitada por um usuário já calibrado.
- Corrigido um problema em que um driver falhava durante a calibragem de olho.
- Corrigido um problema em que os pressionamentos de botão de energia repetidos poderiam causar um tempo limite do sistema de 60 segundos e uma falha de Shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um botão de **compartilhamento** no Hub de comentários para que os usuários possam compartilhar com mais facilidade os comentários.
- Corrigido um bug em que RoboRaid wan't foi instalado corretamente.

### <a name="known-issues"></a>Problemas conhecidos

- Um problema com o idioma do sistema zh-CN impede que os comandos de voz executem uma captura de realidade misturada ou exiba o endereço IP do dispositivo.
- um problema requer que você inicie o aplicativo Cortana depois de iniciar o dispositivo para usar a ativação de voz "ei Cortana". se você atualizou a partir de uma compilação 18362, também poderá ver um bloco de segundo aplicativo para a versão anterior do Cortana aplicativo que não funciona mais em **iniciar**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versão 1903 – maio de 2020 atualização 
- Build 18362,1061

essa atualização de qualidade mensal não contém nenhuma alteração notável porque a equipe estava trabalhando no Windows Holographic versão 2004 pode ser atualizada, conforme descrito anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versão 1903 – atualização de abril de 2020
- Build 18362,1059

**Modo escuro para aplicativos com suporte** 

muitos aplicativos Windows dão suporte ao modo escuro e leve. os clientes do HoloLens 2 agora podem escolher o modo padrão para aplicativos que dão suporte a esquemas de cores. com base nos comentários do cliente, definimos o modo de aplicativo padrão como "escuro", mas você pode alterar facilmente essa configuração a qualquer momento: navegue até **Configurações > sistema > cores** para localizar **"escolher o modo de aplicativo padrão".**

Esses aplicativos "integrados" suportam o modo escuro:
- Configurações
- Microsoft Store
- Email
- Calendário
- Explorador de Arquivos
- Hub de Feedback
- OneDrive
- Fotos
- Visualizador 3D
- Filmes e TV

**Melhorias e correções também na atualização:** 
- Garantiu que as sobreposições de shell estão incluídas em capturas de realidade misturadas.
- Os desenvolvedores inreais agora podem usar a página exibição 3D no portal do dispositivo para testar e depurar seus aplicativos.
- Melhoria da estabilidade do holograma na captura de realidade misturada quando o algoritmo *HolographicDepthReprojectionMethod DepthReprojection* é usado.
- Corrigido o erro "classe de API IStreamSocketListener do WinRT não registrada" em aplicativos ARM de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versão 1903-atualização de março de 2020 
- Build 18362,1056

Melhorias e correções na atualização:

- Melhoria da estabilidade do holograma na captura de realidade misturada quando o algoritmo do *Autoplanar HolographicDepthReprojectionMethod* é usado.
- Verifique se o sistema de coordenadas anexado a um exemplo de MF de profundidade é consistente com a documentação pública.
- Melhor produtividade do desenvolvedor, permitindo que os clientes colem grandes quantidades de texto por meio do portal do dispositivo.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versão 1903 – Atualização de fevereiro de 2020 
- Build 18362.1053

Melhorias e correções na atualização:

- Desabilitada temporariamente a API HolographicSpace.UserPresence para aplicativos unity. Essa alteração evita um problema que causou a pausa de alguns aplicativos quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" tenha sido habilitada.
- Corrigida uma falha de HUP aleatória causada pelo acompanhamento de mão, na qual o usuário observou um congelamento de interface do usuário e, em seguida, de volta ao shell após vários segundos.
- Acompanhamento de mão aprimorado para que, quando você se desdoque com o dedo indicador, a parte superior desse dedo tenha menos probabilidade de ondular inesperadamente.
- Confiabilidade aprimorada do acompanhamento de cabeça, mapeamento espacial e outros runtimes.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versão 1903 – Atualização de janeiro de 2020 
- Build 18362.1043
 
Melhorias e correções na atualização:

- Estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versão 1903 – Atualização de dezembro de 2019 
- Build 18362.1042

Melhorias e correções na atualização:

- Introduziu correções de reprodução de última fase (LSR). Renderização visual aprimorada de hologramas para parecer mais estável e mais nítido, contabilizar com mais precisão sua profundidade. Esse sintoma será mais perceptível após essa atualização se os aplicativos não definirem a profundidade dos hologramas corretamente.
- Corrigida a estabilidade de aplicativos exclusivos e a navegação entre aplicativos exclusivos.
- Resolvido um problema em que a captura de realidade misturada não podia gravar vídeo depois que o dispositivo estava em estado de espera por vários dias.
- Estabilidade aprimorada do holograma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versão 1903 – Atualização de novembro de 2019 
- Build 18362.1039

Melhorias e correções na atualização:

- Corrigida a funcionalidade de **Selecionar comandos** de voz durante a configuração inicial para en-CA e en-AU.
- Qualidade visual aprimorada de objetos colocados longe nas versões mais recentes do Unity e do MRTK (Mixed Reality Toolkit).
- Corrigidos problemas com aplicativos holográficos travando em um estado de pausa na inicialização até que o menu Iniciar fosse aberto e fechado.
- Correções e melhorias de conformidade do runtime do OpenXR para HoloLens 2 e o emulador.
