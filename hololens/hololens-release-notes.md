---
title: Notas sobre a versão do HoloLens 2
description: Mantenha-se atualizado com todas as atualizações em cada nova versão HoloLens 2.
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
ms.openlocfilehash: e0dd7d02ad923438134f2a45812db67f73fdcd8d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637176"
---
# <a name="hololens-2-release-notes"></a>Notas sobre a versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus HoloLens, continuamos a lançar atualizações de recursos, bugs e segurança. Nesta página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização HoloLens 2 mais recente, você pode verificar se há atualizações e [atualizar manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a FFU (Atualização Flash Completa) para piscar seu dispositivo por meio do [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). O [download](https://aka.ms/hololens2download) é mantido atualizado e fornece o build mais recente disponível.

> [!NOTE]
> O comunicado Windows 11 recente se concentrou na versão do computador Windows. Recentemente, lançamos [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) uma atualização principal do sistema operacional para o HoloLens 2 em maio de 2021 e estamos trabalhando em uma versão futura com base nos comentários dos clientes para essa queda.

> [!IMPORTANT]
> Devido a um problema conhecido agora resolvido em nosso [build 21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)que estava afetando os usuários do Remote Assist, pausamos temporalmente a oferta de atualizações do Windows Holographic, versão 21H1. Também mudamos o build padrão do ARC (Advanced Recovery Companion) para o Windows Holographic, versão 20H2 – Atualização de junho de [2021.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) O build arc agora retomará direcionando o build 21H1.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, versão 21H1 – Atualização de junho de 2021
- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive para trabalho ou escola upload de roll de câmera

Adicionamos um novo recurso ao aplicativo Configurações HoloLens 2, que permite que os clientes carreguem automaticamente fotos e vídeos de realidade misturada da pasta Imagens > Camera Roll do dispositivo para a pasta OneDrive correspondente para trabalho ou escola. Esse recurso aborda uma lacuna de recursos dentro do aplicativo [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) no HoloLens 2, que dá suporte apenas ao upload automático do Roll da Câmera para o cliente conta Microsoft pessoal (e não sua conta de trabalho ou de estudante).

**Como funciona**

- Visite **Configurações > sistema > Câmera de Realidade Misturada** para habilitar o "Upload da câmera".
- Ao definir esse  recurso para a posição Ativado, todas as fotos ou vídeos de realidade misturada capturados em seu dispositivo serão automaticamente na fila para upload na pasta Imagens > Do Roll da Câmera do seu OneDrive para a conta de trabalho ou de estudante.
    >[!NOTE]
    >Fotos e vídeos capturados antes  da habilitação desse recurso não serão na fila para upload e ainda precisarão ser carregados manualmente.
- Uma mensagem de status na página Configurações exibirá o número de arquivos pendentes de upload (ou lerá "OneDrive está atualizado" quando todos os arquivos pendentes foram carregados).
- Se você estiver preocupado com a largura de banda ou quiser "pausar" o upload por qualquer motivo, poderá alternar o recurso para a **posição** Desligado. Desabilitar temporariamente o recurso garante que a fila de upload continuará aumentando conforme você adicionar novos arquivos à pasta Roll da Câmera, mas os arquivos não serão carregados até que você reabilitar o recurso.
- Os arquivos mais novos serão carregados primeiro (último a entrar, primeiro a sair).
- Se sua OneDrive tiver problemas (por exemplo, depois que **sua** senha mudar), um botão Corrigir agora será exibido na página Configurações dados.
- Não há nenhum tamanho máximo de arquivo, mas observe que arquivos grandes levarão mais tempo para carregar (especialmente se a largura de banda de upload estiver restrita). Se você "pausar" ou desativar o upload enquanto um arquivo grande estiver sendo carregado, o upload parcial será preservado. Se o upload for reabilitar dentro de várias horas após ter sido "pausado" ou desligado, o upload continuará de onde parou. No entanto, se o upload for habilitado novamente após várias horas, o upload do arquivo grande será reiniciado desde o início.

**Problemas conhecidos e advertências**

- Essa configuração não tem limitação criada com base no uso de largura de banda atual. Se você precisar maximizar a largura de banda para outro cenário, desligue a configuração manualmente. Upload será pausado, mas o recurso continuará a monitorar arquivos recém-adicionados ao Camera Roll. Reabilitar o upload quando estiver pronto para continuar.
- Esse recurso deve ser habilitado para cada conta de usuário no dispositivo e só pode carregar ativamente arquivos para o usuário conectado no momento ao dispositivo.
- Se você estiver fazendo fotos ou vídeos enquanto observa a contagem de upload na página Configurações em tempo real, observe que a contagem de arquivos pendentes pode não mudar até que o arquivo atual tenha concluído o carregamento.
- Upload pausará se o dispositivo ficar inodor ou estiver desligado. Para garantir que os uploads pendentes são concluídos, use ativamente o dispositivo até que Configurações página do Configurações leia "OneDrive está atualizado" ou ajuste as configurações de sleep **do Power &.**
### <a name="added-support-for-some-telemetry-policies"></a>Adicionado suporte para algumas políticas de telemetria

As seguintes políticas de telemetria agora têm suporte no HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry e System\ConfigureTelemetryOptInSettingsUx devem ser usados juntos para ter controle total sobre a Telemetria e o comportamento no aplicativo Configurações.

Melhorias e correções na atualização:
- Corrige a corrupção de vídeo principal com calibragem de cores.
- Resolve um problema em que o texto pode ser truncado no menu Energia.
- Habilita o suporte para a política RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de junho de 2021
- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Adicionado suporte para algumas políticas de telemetria

As seguintes políticas de telemetria agora têm suporte no HoloLens 2:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry e System\ConfigureTelemetryOptInSettingsUx devem ser usados juntos para ter controle total sobre a Telemetria e o comportamento no aplicativo Configurações.

Incentivamos você a experimentar nosso build mais recente, Windows Holographic, versão 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, versão 1903 – Atualização de junho de 2021
- Build 18362.1116

Melhorias e correções na atualização:
- Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nosso build mais recente, Windows Holographic, versão 21H1.

>[!IMPORTANT]
> Esse build não será mais atendido.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, versão 21H1
- Build 20346.1002

Essa atualização contém recursos para dois públicos-alvo; recursos que podem ser usados por qualquer pessoa em um dispositivo pelo Usuário Final e novas opções de gerenciamento de dispositivo que podem ser configuradas por administradores de IT. A tabela a seguir especifica os recursos relevantes para cada público-alvo. Se você for um administrador de TI, dê uma olhada em nosso Administrador [de TI – Atualizar Lista de Verificação.](#it-admin---update-checklist)
>[!IMPORTANT]
>Para atualizar para esse build, HoloLens 2 dispositivos devem estar executando a atualização de fevereiro de 2021 (build 19041.1136) ou mais recente. Se você não estiver vendo essa atualização de recurso disponível, atualize seu dispositivo primeiro e tente novamente.

>[!NOTE]
>Atualmente, Microsoft HoloLens 2 dá suporte a atualizações de manutenção mensais (correções de bugs e segurança) para as seguintes versões:
>- Windows Holographic, versão 20H2 (Build 19041.1128+)
>- Windows Holographic, versão 2004 (Build 19041.1103+)
>- Windows Holographic, versão 1903 (Build 18362+) 
>
> Com a introdução do Windows Holographic versão 21H1, estamos descontinuando as atualizações de manutenção mensal para o **Windows Holographic versão 1903.** Isso nos permite se concentrar em versões mais recentes e continuar a fornecer melhorias valiosas. 


| Nome do recurso                                              | Descrição breve                                                                      | Público-alvo | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Novos Microsoft Edge](#introducing-the-new-microsoft-edge)  | O novo Chromium baseado em Microsoft Edge está disponível para HoloLens 2. | Usuário Final | 
[WebXR e Visualizador 360](#webxr-and-360-viewer) | Experimente experiências imersivas na Web e reprodução de vídeo 360. | Usuário Final | 
[Novo Configurações aplicativo](#new-settings-app) | O aplicativo Configurações herdado está sendo substituído por uma versão atualizada por novos recursos e configurações. | Usuário Final |
[Exibir calibragem de cores](#display-color-calibration) | Selecione um perfil de cor alternativo para a exibição HoloLens 2. | Usuário Final |
[Selador de aplicativo padrão](#default-app-picker) | Escolha qual aplicativo deve ser lançado para cada arquivo ou tipo de link. | Usuário Final |
[Por controle de volume do aplicativo](#per-app-volume-control) | Controlar o volume no nível do aplicativo independentemente do volume do sistema. | Usuário Final |
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

- [visite o arquivo morto do HoloLens Emulator](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

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

- [definir configurações de política de Microsoft Edge com Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Versão Prévia do Microsoft Edge Microsoft Edge mapeamento de política](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [mapeamento de política do Google Chrome para Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- documentação completa de [Enterprise de Microsoft Edge](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> devido ao volume de políticas de navegador com suporte pelo novo Microsoft Edge, nossa equipe não consegue garantir que cada nova política funcione no HoloLens 2. no entanto, testamos e confirmamos o novo Microsoft Edge equivalente de cada política de Microsoft Edge herdada anteriormente com suporte no HoloLens 2 funciona conforme o esperado. consulte [Versão Prévia do Microsoft Edge para Microsoft Edge mapeamento de política](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) para encontrar o novo equivalente Microsoft Edge de cada política herdada de navegador Microsoft Edge que você estava usando com o HoloLens 2.
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

Há alguns métodos disponíveis para instalar os canais Microsoft Edge Insider para HoloLens 2:

**Instalação direta no dispositivo (atualmente disponível apenas para dispositivos não planejados)**
  1. No seu HoloLens 2, visite a página de [download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão Baixar HoloLens 2** para o canal do Edge Insider que você deseja instalar.
  1. Iniciar o arquivo .msix baixado da fila de download do Edge ou da pasta "Downloads" do dispositivo (usando Explorador de Arquivos).
  1. [O instalador de aplicativo](app-deploy-app-installer.md) será lançado.
  1. Selecione o botão **Instalar**.
  1. Após a instalação bem-sucedida, você encontrará Microsoft Edge Beta, Dev ou Canário como uma entrada separada na lista **Todos os apps** do menu Iniciar.

**Instalar por meio do pc com Windows Portal de Dispositivos [(requer](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) que o modo de desenvolvedor seja habilitado no HoloLens 2)**
  1. Em seu computador, visite a página [de download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão de seta para baixo** ao lado do botão "Baixar Windows 10" para o canal do Edge Insider que você deseja instalar.
  1. Selecione **HoloLens 2** no menu suspenso.
  1. Salve o arquivo .msix na pasta "Downloads" do computador (ou em outra pasta que você possa encontrar facilmente).
  1. Use [Windows Portal de Dispositivos](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) em seu computador para instalar o arquivo .msix baixado no HoloLens 2.
  1. Após a instalação bem-sucedida, você encontrará Microsoft Edge Beta, Dev ou Canário como uma entrada separada na lista **Todos os apps** do menu Iniciar.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Usando o WDAC para bloquear novos Microsoft Edge

Para administradores de TI que buscam atualizar a política [do WDAC](windows-defender-application-control-wdac.md) para bloquear o novo aplicativo Microsoft Edge, você precisará adicionar o seguinte à sua política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerenciando pontos de extremidade para a nova Microsoft Edge

Alguns ambientes podem ter restrições de rede a considerar como uma consideração. Para garantir uma experiência tranquila com o novo Edge, [habilita esses pontos de extremidade da Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os pontos de extremidade disponíveis no momento [para HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Instalar aplicativos Web
 > [!Note]
>A partir [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)o Office web não será mais pré-instalado.

Você pode usar o novo Edge para instalar aplicativos Web junto com Microsoft Store aplicativos. Por exemplo, você pode instalar o Microsoft Office Web para exibir e editar arquivos hospedados SharePoint ou OneDrive. Para instalar o Office Web, visite e selecione o botão Aplicativo Disponível ou Instalar Office na https://www.office.com barra de  endereços.  Selecione **Instalar** para confirmar.

> [!IMPORTANT]
> Office funcionalidade do aplicativo Web só estará disponível quando o HoloLens 2 tiver uma conexão de Internet ativa.

### <a name="webxr-and-360-viewer"></a>WebXR e Visualizador 360

O novo Microsoft Edge inclui suporte para WebXR, que é o novo padrão para criar experiências da Web imersivas (substituindo WebVR). Muitas experiências imersivas na Web foram projetadas com VR em mente (elas substituem seu campo de exibição por um ambiente virtual), mas essas experiências também têm suporte do HoloLens 2. O padrão WebXR também permite experiências da Web imersivas de realidade aumentada e misturada que usam seu ambiente físico. À medida que os desenvolvedores gastam mais tempo com o WebXR, prevemos que novas experiências imersivas de realidade aumentada e misturada chegarão para que HoloLens 2 clientes experimentem!

A extensão do Visualizador 360 é criada no WebXR e é instalada automaticamente junto com o novo Microsoft Edge no HoloLens 2. Essa extensão da Web oferece a capacidade de se aprofundar em vídeos de 360 graus. O YouTube oferece a maior seleção de 360 vídeos, portanto, incentivamos você a começar lá.

#### <a name="how-to-use-webxr"></a>Como usar o WebXR

1. Navegue até um site com suporte a WebXR.
1. Selecione o **botão Inserir VR** no site. O local e a representação visual desse botão podem variar por site, mas pode ser semelhante a:

    ![Exemplo de botão Inserir VR](images/75px-enter-vr.png)

1. Na primeira vez que você tentar iniciar uma experiência WebXR em um domínio específico, o navegador solicitará consentimento para inserir uma exibição imersiva, selecione **Permitir**.
1. Use [HoloLens dois gestos para](hololens2-basic-usage.md#the-hand-tracking-frame) manipular a experiência.
1. Se a experiência não tiver um botão **Sair,** use o gesto [Iniciar](hololens2-basic-usage.md#start-gesture) para retornar para casa.

**Exemplos de WebXR recomendados**
- Visualizador 360 (consulte a próxima seção)
- [XR Dinos](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Como usar o Visualizador do 360

1. Navegue até um vídeo de 360 graus no YouTube.
1. No quadro de vídeo, selecione o botão de headset de realidade misturada:

    ![Botão para ativar o Visualizador do 360](images/enter-360-viewer.jpg)

1. Na primeira vez que você tentar iniciar o Visualizador 360 em um domínio específico, o navegador solicitará consentimento para entrar em uma exibição imersiva. selecione **Permitir**.
1. [Toque de ar](hololens2-basic-usage.md#select-using-air-tap) para abrir os controles de reprodução. Use [raios de](hololens2-basic-usage.md#select-using-air-tap) mão e toque de ar para reproduzir/pausar, ignorar/voltar, ativar/desativar legendas ou parar a experiência (que sai da exibição imersiva). Os controles de reprodução desaparecerão após alguns segundos de inatividade.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principais problemas conhecidos do WebXR e do Visualizador 360
- Dependendo da complexidade da experiência WebXR, a taxa de quadros pode cair ou gaguejar.
- O suporte para junções de mão articuladas no WebXR não está habilitado por padrão. Os desenvolvedores podem `edge://flags` habilitar o suporte por meio da ative a "Entrada da Mão do WebXR".
- 360 vídeos de sites diferentes do YouTube podem não funcionar conforme o esperado.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo comentários sobre o WebXR e o Visualizador 360

Compartilhe comentários e bugs com nossa equipe por meio **do recurso** Enviar Comentários na nova Microsoft Edge.

### <a name="new-settings-app"></a>Novo Configurações aplicativo

Com esta versão, estamos introduzindo uma nova versão do Configurações aplicativo. O novo aplicativo Configurações inclui novos recursos e configurações expandidas para o HoloLens 2 nas seguintes áreas: Som, sleep do Power &, Internet do & de rede, Aplicativos, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Como o novo Configurações aplicativo é diferente do aplicativo Configurações herdado, todas as janelas Configurações que você colocou anteriormente em seu ambiente serão removidas após a atualização.

![Home page Configurações aplicativo novo](images/new-settings-app.png)

**Novos recursos e configurações**
- Configurações pesquisa: pesquise as configurações Configurações página inicial usando palavras-chave ou o nome da configuração.
- Som > sistema:
  - Dispositivos de áudio de entrada e saída: escolha independentemente seus dispositivos de áudio de entrada e saída (por exemplo, escutar áudio por meio de fones de ouvido Bluetooth ou usar um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Bluetooth microfones não são suportados pelo HoloLens 2.
  - Volume do aplicativo: ajuste independentemente o volume de cada aplicativo. Consulte [por controle de volume do aplicativo](#per-app-volume-control).
- Sistema > o & sleep: escolha quando o dispositivo deve ficar em atividade após um período de inatividade.
- Bateria > sistema: habilita manualmente o modo economia de bateria ou definir um limite de bateria no qual o modo economia de bateria ponto é ativado automaticamente.
- Dispositivos > USB: você pode desabilitar conexões USB por padrão.
- Rede & Internet:
  - Os adaptadores Ethernet USB-C agora aparecerão na Rede & Internet.
  - As configurações do adaptador Ethernet USB-C agora estão disponíveis, incluindo seu endereço IP.
  - Agora você pode habilitar o modo avião HoloLens 2.
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Para obter mais informações, [consulte Se picker de aplicativo padrão.](#default-app-picker)
- Contas > Outros usuários: os proprietários do dispositivo podem adicionar usuários, atualizar usuários padrão para proprietários de dispositivos, fazer downgrade de proprietários de dispositivos para usuários padrão e remover usuários.
- Facilidade de Acesso: alterar o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- As janelas Configurações anteriormente colocadas serão removidas (veja a observação acima).
- Você não pode mais renomear seu dispositivo com o Configurações aplicativo. Os administradores de IT podem renomear dispositivos usando o [Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) para o modelo de nome do dispositivo HoloLens 2 ou o nó [MDM DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- A página Ethernet mostra um dispositivo Ethernet virtual ("UsbNcm") em todos os momentos.
- O uso de bateria para o novo Microsoft Edge pode não ser preciso, devido à sua natureza como um aplicativo da área de trabalho Win32 com suporte por uma camada de adaptador UWP (nenhuma correção prevista em breve).

#### <a name="display-color-calibration"></a>Exibir calibragem de cores



Com essa nova configuração, você pode selecionar um perfil de cor alternativo para a exibição HoloLens 2. Isso pode ajudar as cores a aparecerem mais precisas, especialmente em níveis de brilho de exibição inferiores. A calibragem de cores de exibição pode ser encontrada no aplicativo Configurações, na página Calibragem > Sistema.

> [!NOTE]
> Como essa configuração salva um novo perfil de cor no firmware de exibição, é uma configuração por dispositivo (e não exclusiva para cada conta de usuário).

##### <a name="how-to-use-display-color-calibration"></a>Como usar a calibragem de cores de exibição

1. inicie o aplicativo **Configurações** e navegue até **System > calibration**.
1. Em **Exibir calibragem de cor**, selecione o botão **executar calibragem de cor de exibição** .
1. A experiência de calibragem de cor de exibição será iniciada e encorajada a garantir que o visor esteja na posição correta.
1. Depois de prosseguir com as caixas de diálogo de instrução, sua exibição será automaticamente esmaecida para um brilho de 30%.
    > [!TIP]
    > se você estiver tendo problemas para ver a cena esmaecida em seu ambiente, poderá ajustar manualmente o nível de brilho de HoloLens 2 usando os botões de brilho no lado esquerdo do dispositivo.
1. Selecione os botões 1-6 para testar instantaneamente cada perfil de cor e localize um que tenha a melhor aparência para os seus olhos (isso geralmente significa o perfil que ajuda a cena a parecer mais neutra, com o padrão de escala de cinza e tons de capas que parecem conforme o esperado).

    ![Exibir cena de calibragem de cor](images/color-cal-ui.png)
    
1. Quando estiver satisfeito com o perfil selecionado, selecione o botão **salvar & sair**
1. Se preferir não fazer alterações, selecione o botão **cancelar & sair** e suas alterações serão revertidas

> [!TIP]
> Aqui estão algumas dicas úteis para ter em mente ao usar a configuração de calibragem de cores de exibição:
> - você pode executar novamente a calibragem de cor de exibição de Configurações sempre que desejar
> - se qualquer pessoa no dispositivo tiver usado anteriormente a configuração para alterar os perfis de cor, a data/hora da alteração mais recente será refletida na página de Configurações
> - Quando você executa novamente a calibragem de cor de exibição, o perfil de cor que foi salvo anteriormente será realçado e o perfil 0 não será exibido (pois o perfil 0 representa o perfil de cor original da exibição)
> - se você quiser reverter para o perfil de cor original da exibição, poderá fazer isso na página Configurações (consulte [como redefinir o perfil de cor](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cor 

se você não estiver satisfeito com o perfil de cor personalizado salvo em seu HoloLens 2, poderá restaurar o perfil de cor original do dispositivo:
1. inicie o aplicativo **Configurações** e navegue até **System > calibration**.
1. Em **Exibir calibragem de cor**, selecione o botão **Redefinir para perfil de cor padrão** .
1. quando a caixa de diálogo for aberta, selecione **reiniciar** se você estiver pronto para reiniciar HoloLens 2 e aplicar suas alterações.

#### <a name="top-display-color-calibration-known-issues"></a>Problemas conhecidos de calibragem de cor de exibição superior

- na página Configurações, a cadeia de caracteres de status que informa quando o perfil de cor foi alterado pela última vez estará desatualizada até que você recarregue essa página de Configurações.
    - solução alternativa: selecione outra página de Configurações e, em seguida, selecione novamente a página calibragem.

#### <a name="default-app-picker"></a>Seletor de aplicativo padrão

Quando você ativa um hiperlink ou abre um tipo de arquivo com mais de um aplicativo instalado, que dá suporte a ele, você verá uma nova janela aberta solicitando que você selecione qual aplicativo instalado deve tratar do tipo de arquivo ou de link. Nessa janela, você também pode optar por fazer com que o aplicativo selecionado manipule o tipo de arquivo ou link "uma vez" ou "sempre".

se você escolher "sempre", mas posteriormente quiser alterar qual aplicativo trata um determinado arquivo ou tipo de link, poderá redefinir os padrões salvos em **aplicativos Configurações >**. Role até a parte inferior da página e selecione o botão **limpar** em "aplicativos padrão para tipos de arquivo" e/ou "aplicativos padrão para tipos de link". Diferentemente da configuração semelhante em computadores desktop, não é possível redefinir padrões de tipo de arquivo individuais.

#### <a name="per-app-volume-control"></a>Por controle de volume por aplicativo

agora, neste Windows build, os usuários podem ajustar manualmente o nível de volume de cada aplicativo. Isso permite que os usuários se concentrem melhor nos aplicativos que precisam ou ouvem-se melhor ao usar vários aplicativos. Como a necessidade de desativar o volume de um aplicativo ao chamar outra pessoa para assistência remota em outro.

para definir o volume de um aplicativo individual, navegue até **Configurações**  ->    ->  **som** do sistema e, em opções avançadas de som, selecione o **volume do aplicativo e as preferências do dispositivo**.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Passar o dedo para o tipo

Alguns clientes acham mais rápido para "digitar" em teclados virtuais, passando a forma da palavra que pretendem digitar e estamos visualizando esse recurso no teclado Holographic. Você pode passar uma palavra por vez passando a ponta do dedo por meio do plano do teclado do Holographic, passando a forma da palavra e, em seguida, retirando a ponta do dedo do plano do teclado. Você pode passar as palavras de acompanhamento sem precisar pressionar a barra de espaço removendo o dedo do teclado entre as palavras. Você saberá que o recurso está funcionando se vir uma trilha do dedo após o movimento do dedo no teclado.

Observe que esse recurso pode ser complicado para usar e dominar por causa da natureza de um teclado Holographic em que você não sente a resistência contra o dedo (ao contrário de uma exibição de telefone celular). 

### <a name="power-menu-from-start"></a>Menu de energia do início

Um novo menu que permite ao usuário sair, desligar e reiniciar o dispositivo. um indicador na tela iniciar HoloLens que mostra quando uma atualização do sistema está disponível.

#### <a name="how-to-use"></a>Como usar

1. abra a tela iniciar HoloLens usando o [gesto iniciar](hololens2-basic-usage.md#start-gesture) ou dizendo "ir para iniciar".

2. Observe o ícone de reticências (...) ao lado da imagem de perfil do usuário:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selecione a imagem de perfil do usuário usando suas mãos ou o comando de voz "Power".

4. Um menu é exibido com opções para sair, reiniciar ou desligar o dispositivo:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Selecione as opções de menu para sair, reiniciar ou desligar o HoloLens. A opção sair pode não estar disponível, se o dispositivo estiver configurado para uma [única conta da Microsoft (MSA) ou conta local](hololens-identity.md).

6. descartar o menu tocando em qualquer outro lugar ou fechando o menu Iniciar com o gesto de início.

#### <a name="update-indicator"></a>Indicador de atualização

Quando uma atualização está disponível, o ícone de reticências se acenderá para indicar que uma reinicialização instalará a atualização. as opções de menu também são alteradas para refletir a presença da atualização.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela de entrada

Anteriormente, a tela de entrada mostrou apenas o usuário conectado mais recentemente, bem como um ponto de entrada de "outro usuário". Recebemos comentários dos clientes de que isso não é suficiente se vários usuários tiverem entrado no dispositivo. Eles ainda eram solicitados a digitar novamente o nome de usuário, etc.

introduzidas neste Windows build, ao selecionar **outro usuário** que está localizado à direita do campo de entrada de PIN, a tela de entrada exibirá vários usuários com o conectado anteriormente ao dispositivo. isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entrem usando suas credenciais de Windows Hello. Um novo usuário também pode ser adicionado ao dispositivo por meio dessa página de outros usuários por meio do botão **adicionar conta** .

Quando estiver no menu outros usuários, o botão outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela de entrada deste usuário.

![Padrão da tela de entrada](./images/multiusers1.jpg)

<br>

![Tela de entrada de outros usuários](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Suporte ao microfone externo USB-C

> [!IMPORTANT]
> **A conexão a um mic USB não o definirá automaticamente como o dispositivo de entrada**. ao conectar um conjunto de fones USB-C, os usuários observarão que o áudio do headphone será redirecionado automaticamente para os fones de ouvido, mas o sistema operacional HoloLens prioriza a matriz de microfone interna acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

Os usuários podem selecionar microfones externos conectados a USB C usando o painel configurações de **som** . Microfones USB-C podem ser usados para chamada, gravação, etc.

abra o aplicativo **Configurações** e selecione   >  **som** do sistema.

![Configurações de som](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com o **auxílio remoto**, os usuários precisarão clicar no hiperlink "gerenciar dispositivos de som".
>
> Em seguida, use a lista suspensa para definir o microfone externo como **padrão** ou **padrão de comunicação.** Escolher **padrão** significa que o microfone externo será usado em todos os lugares.
>
> escolher **padrão de comunicação** significa que o microfone externo será usado no auxílio remoto e em outros aplicativos de comunicação, mas a matriz de HoloLens mic ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>e quanto Bluetooth suporte a microfone?

infelizmente, Bluetooth microfones ainda não têm suporte no momento no HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solução de problemas de microfones USB-C

Lembre-se de que alguns microfones USB-C se reportam incorretamente como um microlocutor *e* um palestrante. Esse é um problema com o microfone e não com HoloLens. ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

em **Configurações**  ->    ->  **som** do sistema, defina explicitamente os alto-falantes internos **(Driver de áudio de recurso analógico)** como o **dispositivo padrão**. HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado mais tarde.

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
| MixedReality/VisitorAutoLogon  | Permite que um visitante para logon automático em um quiosque   | 1 (Sim), 0 (Não, padrão.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usar os novos aplicativos Configurações e Edge nos modos de quiosque

Ao incluir aplicativos em [Quiosques,](hololens-kiosk.md)um administrador de IT geralmente adiciona o aplicativo ao Quiosque, mas usando sua AUMID (ID do Modelo de Usuário do Aplicativo). Como o aplicativo Configurações e o aplicativo Microsoft Edge são considerados novos aplicativos e diferentes dos aplicativos mais antigos, os quiosques que usam AUMIDs para esses aplicativos precisarão ser atualizados para usar o novo AUMID.

Ao modificar um Quiosque para incluir os novos aplicativos, recomendamos adicionar o novo AUMID, bem como deixar o antigo. Isso criará uma transição fácil quando os usuários atualizarem o sistema operacional e não precisarão receber novas políticas para continuar usando o Quiosque conforme o esperado.

| Aplicativo                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicativo Configurações antigo       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Novo Configurações Aplicativo       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Aplicativo Microsoft Edge antigo | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Novo Microsoft Edge aplicativo | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações no comportamento do modo de quiosque para tratamento de falhas

Em builds mais antigos, se um dispositivo tivesse uma configuração de quiosque, que é uma combinação de acesso atribuído global e acesso atribuído ao membro do grupo do AAD, se a determinação da associação ao grupo do AAD falhasse, o usuário verá[o](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)menu " nada mostrado no menu iniciar ".

A partir desta versão Windows, a experiência de quiosque fará fallback para a configuração de quiosque global (se presente) em caso de falhas durante o modo de quiosque do grupo do AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Novos URIs Configurações para visibilidade de Configurações página

No [Windows Holographic, versão 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) adicionamos a política [Configurações/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas dentro do Configurações aplicativo. PageVisibilityList é uma política que permite que os administradores de IT impeçam que páginas específicas no aplicativo system Configurações sejam visíveis ou acessíveis ou para fazer isso para todas as páginas, exceto aquelas especificadas.

Se você visitar [o Page Configurações Visibility](settings-uri-list.md), poderá encontrar instruções para usar esse CSP e a lista de URIs disponíveis nas versões anteriores.

Estamos expandindo a lista de URIs Configurações disponíveis, que os administradores de IT podem gerenciar. Alguns desses URIs são para áreas recém-disponíveis no novo Configurações aplicativo. Se você estiver usando Configurações/PageVisibilityList, revise a lista a seguir e ajuste suas páginas permitidas ou bloqueadas conforme necessário.

> [!NOTE]
> **Preterido: ms-settings:network-proxy**
>
> Uma página de configurações foi preterida nesses builds mais novos. A página **antiga Proxy & Internet** não está mais disponível como uma  >   configuração global. As novas configurações de proxy por conexão podem ser encontradas em Propriedades de Rede **&**  >  **Wi-Fi** da Internet ou Propriedades de Rede  >   & Ethernet   >  **da**  >  **Internet**.

<br>

| Página de configurações                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplicativos > aplicativos & recursos                               | `ms-settings:appsfeatures`                         |
| Aplicativos > aplicativos & recursos > opções avançadas          | `ms-settings:appsfeatures-app`                     |
| Aplicativos > mapas offline                                  | `ms-settings:maps`                                 |
| Aplicativos > mapas offline > Baixar mapas                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > Mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Rede & internet > modo avião                   | `ms-settings:network-airplanemode`                 |
| Privacidade > geral                                    | `ms-settings:privacy-general`                      |
| Privacidade > de & digitando a personalização             | `ms-settings:privacy-speechtyping`                 |
| Movimento de > privacidade                                     | `ms-settings:privacy-motion`                       |
| Privacidade > bordas de captura de tela                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Capturas de > privacidade e aplicativos                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Bateria > sistema                                     | `ms-settings:batterysaver`                         |
| Bateria > sistema                                     | `ms-settings:batterysaver-settings`                |
| Som > sistema                                       | `ms-settings:sound`                                |
| Sistema > som > preferências de dispositivo e volume do aplicativo | `ms-settings:apps-volume`                          |
| Sistema > som > gerenciar dispositivos de som              | `ms-settings:sound-devices`                        |
| Configuração > Armazenamento > sistema Armazenamento sense         | `ms-settings:storagepolicies`                      |
| Hora & de > de & hora                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Linguagem & de > tempo                           | `ms-settings:language`                             |
| Linguagem & de > tempo                           | `ms-settings:regionlanguage-languageoptions`       |
| Atualizar & segurança > redefinir & recuperação               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URIs atualizados

Anteriormente, os dois URIs a seguir não levariam um usuário diretamente para as páginas indicadas, mas apenas bloqueariam a página de atualizações principal. Os seguintes itens foram atualizados para direcionar para suas páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurando o Diagnóstico de Fallback por meio Configurações aplicativo

Agora, Configurações Aplicativo, um usuário pode configurar o comportamento do [Diagnóstico de Fallback.](hololens-diagnostic-logs.md) No aplicativo Configurações, navegue até **a página Solução** de problemas  ->  **de** privacidade para definir essa configuração.

> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.  

### <a name="share-things-with-nearby-devices"></a>Compartilhar coisas com dispositivos próximos

Compartilhe coisas com dispositivos quase Windows 10, incluindo PCs e outros HoloLens 2 dispositivos. Você pode experimentar em experiências compartilhadas **Configurações** sistema para compartilhar arquivos ou URLs de um HoloLens  ->    ->   para um PC. Para obter mais detalhes, leia mais sobre como compartilhar [coisas com dispositivos próximos no Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esse recurso pode ser gerenciado por [meio de Conectividade/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Novos rastreamentos de diagnóstico do sistema operacional

Além das soluções de problemas anteriores no aplicativo Configurações, uma nova solução de problemas foi adicionada com a adição do novo aplicativo Configurações para atualizações do sistema operacional. Navegue até **Configurações** atualizar a solução de Windows atualizar  ->  **&amp;**  >    >  **e** selecione **Iniciar**. Isso permite coletar rastreamentos ao reproduzir seu problema com atualizações do sistema operacional para ajudar melhor na solução de problemas com sua TI ou suporte.

### <a name="delivery-optimization-preview"></a>Otimização de Entrega versão prévia

Com essa atualização HoloLens, o Windows Holographic for Business permite que as configurações de otimização de entrega reduzam o consumo de largura de banda para downloads de vários HoloLens dispositivos. Uma descrição mais completa dessa funcionalidade junto com a configuração de rede recomendada está disponível aqui: Otimização de Entrega para Windows 10 [atualizações.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

As configurações a seguir são habilitadas como parte da superfície de gerenciamento e [podem ser configuradas no Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

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

Algumas advertências sobre essa oferta de versão prévia:

- HoloLens suporte é limitado nesta versão prévia apenas a atualizações do sistema operacional.
- Windows Holographic for Business dá suporte apenas a modos de download HTTP e downloads de um [ponto de extremidade do Microsoft Cache Conectado ;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Não há suporte para modos de download ponto a ponto e atribuições de grupo HoloLens dispositivos no momento.
- HoloLens dá suporte à implantação ou à otimização de entrega para Windows Server Update Services de extremidade.
- A solução de problemas exigirá o diagnóstico no servidor Cache Conectado ou a coleta de um rastreamento no HoloLens no HoloLens por meio do **Configurações** atualização & de solução de problemas de Windows  >    >     >   **atualização**.

### <a name="it-admin---update-checklist"></a>Administrador de IT – Lista de verificação de atualização

Essa lista de verificação ajudará você a conhecer os novos itens que estão sendo adicionados a essa atualização de recurso que podem afetar suas configurações atuais de gerenciamento de dispositivo ou novos recursos que talvez você queira começar a usar.

#### <a name="updates-to-kiosk-mode"></a>Atualizações no modo quiosque

✔️ novos [**AUMIDs para novos aplicativos no modo quiosque:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

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
- Adicionado suporte arm32 para o [Modo de Pesquisa.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

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

Agora você pode instalar aplicativos sem a necessidade de habilitar o Modo de Desenvolvedor ou usar Portal de Dispositivos.  Basta baixar (por USB ou por meio do Edge) o Pacote Appx para seu dispositivo e navegar até o Pacote Appx no Explorador de Arquivos ser solicitado a dar início à instalação.  Como alternativa, [inicie uma instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos instalados do Microsoft Store ou sideload usando a funcionalidade de implantação de Aplicativo [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB do [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Assinatura e o certificado usado para assinar deve ser confiável para o dispositivo HoloLens antes que o aplicativo possa ser implantado.

**Instruções de instalação do aplicativo.**

1.  Verifique se o dispositivo não é considerado gerenciado
1.  Verifique se o HoloLens 2 está ligado e conectado ao computador
1.  Verifique se você está conectado ao dispositivo HoloLens 2
1.  No computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para yourdevicename\Internal Armazenamento\Downloads.   Depois de terminar de copiar o arquivo, você poderá desconectar seu dispositivo
1.  Em seu HoloLens 2, abra o Menu Iniciar, selecione Todos os apps e inicie o Explorador de Arquivos aplicativo.
1.  Navegue até a pasta Downloads. Talvez seja necessário que, no painel esquerdo do aplicativo, selecione Este dispositivo primeiro e, em seguida, navegue até Downloads.
1.  Selecione o arquivo yourapp. appxbundle.
1.  O instalador do aplicativo será iniciado. Selecione o botão instalar para instalar o aplicativo.
O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.

você pode encontrar aplicativos de exemplo em [Windows exemplos universais GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar esse fluxo.

leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o instalador do aplicativo](app-deploy-app-installer.md).  

![Instalando exemplos do MRTK por meio do instalador do aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O rastreamento manual agora mantém o controle em vários novos casos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, apenas a posição Palm continua a ser atualizada com base na disponibilidade do usuário, enquanto as outras junções são inferidas com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência de rastreamento em movimentos como pregaria, lançando, scooping e Clapping.  Também ajuda nos casos em que a mão está perto de uma superfície ou segurando um objeto.  Quando as junções de mão estão sendo inferidas, o valor de [precisão por](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) conjunto será definido como "aproximado" em vez de "alto".
- Correção de um problema em que o PIN redefinido para contas do Azure AD mostraria um erro "algo deu errado.
- Os usuários devem ver muito menos falhas no OOBE após a inicialização de ET, íris no aplicativo de configurações, novo usuário ou notificação do sistema.
- Os usuários devem ter o fuso horário correto saindo do OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versão 1903 – atualização de dezembro de 2020
- Build 18362,1088

essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa última Windows Holographic, versão 20H2 – atualização de dezembro de 2020 e o novo recurso instalador de aplicativo adicionado na compilação.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versão 20H2
- Build 19041,1128

Windows Holographic, a versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para HoloLens 2 usuários e profissionais de ti. do posicionamento de olho automático, para o gerenciador de certificados no Configurações, para aprimorar a funcionalidade do modo de quiosque e para novos recursos de instalação do autopilot. essa nova atualização permite que as equipes de ti adotem um controle mais granular para configurar e gerenciar dispositivos HoloLens e oferece aos usuários experiências holographics ainda mais diretas. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. o número de build principal permanecerá o mesmo e Windows Update indicará uma versão mensal para a versão 2004 (build 19041). você pode examinar o número da sua versão no seu Configurações > tela sobre para confirmar se está no Build 19041.1128 + do mais recente disponível. para atualizar para a versão mais recente, abra o aplicativo Configurações, vá para atualização & segurança e toque em verificar se há atualizações. para obter mais informações sobre como gerenciar atualizações de HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>o que há de novo no Windows Holographic, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte de posição de olho automático](hololens-release-notes.md#auto-eye-position-support) | Computa ativamente posições de olho sem que os usuários passem pela calibragem de controle ocular.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | permite que novos métodos mais simples instalem e removam certificados do aplicativo Configurações.     |
| [Inicialização automática do provisionamento de USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | O provisionamento de pacotes em unidades USB solicita automaticamente a página de provisionamento no OOBE.                                                         |
| [Confirmar automaticamente os pacotes de provisionamento no OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante o OOBE da página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a inicialização automática de provisionamento e a confirmação automática em conjunto. |
| [Usando o piloto automático com conexão Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o AutoPilot do dispositivo Wi-Fi sem a necessidade do adaptador Ethernet. |
| [CSP Tenantlockdown e piloto automático](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após o registro do locatário e a política ser aplicada, o dispositivo só poderá ser registrado nesse locatário sempre que o dispositivo for redefinido ou atualizado novamente. |
| [Acesso global atribuído](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para vários modos de quiosque de aplicativo que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
| [Iniciar automaticamente um aplicativo no quiosque de vários aplicativos](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define um aplicativo para ser iniciado automaticamente ao entrar em um modo de quiosque de vários aplicativos.                                                        |
| [Alterações de comportamento do modo de quiosque para tratamento de falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Falha no modo de quiosque agora tem fallback restritivo.                                                                                                |
| [HoloLens Policie](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para HoloLens.     |
| [Armazenar em cache a associação de grupo do Azure AD para quiosque offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os usuários usem o cache de associação de grupo para usar o modo de quiosque offline por um número de dias definido.                                        |
| [novas políticas de restrição de dispositivo para o HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | políticas de gerenciamento de dispositivo habilitadas recentemente habilitadas para o HoloLens 2.                                                                                |
| [novas políticas de energia para o HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recentemente suportadas para configurações de tempo limite de energia.  |
| [Atualizar políticas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas habilitadas recentemente, permitindo o controle de atualizações.           |
| [Configurações visibilidade da página habilitada para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | política para escolher quais páginas são vistas no aplicativo Configurações.             |
| [Modo de pesquisa](hololens-release-notes.md#research-mode) | usando o modo de pesquisa no HoloLens 2. |
| [Tamanho de gravação aumentado](hololens-release-notes.md#recording-length-increased) | Gravações da MRC não são mais limitadas a 5 minutos. |
| [Melhorias e correções na atualização](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correções adicionais na atualização.   |

### <a name="auto-eye-position-support"></a>Suporte de posição de olho automático

no HoloLens 2, as posições de olho permitem o posicionamento preciso do holograma, a experiência de exibição confortável e a qualidade de exibição aprimorada. As posições de olho são calculadas internamente como parte da computação de controle de olho. No entanto, isso requer que cada usuário passe pela calibragem de controle ocular, mesmo quando a experiência pode não exigir a entrada de olhar de olho.

A **AEP (posição de olho automático)** habilita esses cenários com uma maneira sem interação de computar posições de olho para o usuário. A posição de olho automático começa a trabalhar em segundo plano automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de acompanhamento de olho anterior, a posição de olho automático começará a fornecer as posições de olho do usuário para o sistema de vídeo após um tempo de processamento de 20-30 segundos. Os dados do usuário não são persistidos no dispositivo e, portanto, esse processo é repetido quando o usuário retira o botão de volta e coloca o dispositivo novamente ou se o dispositivo é reinicializado ou sai do modo de suspensão.

Há algumas alterações de comportamento do sistema com o recurso de posição de olho automático quando um usuário não calibrado coloca no dispositivo. Nesse contexto, um usuário não calibrado refere-se a alguém que não passou pelo processo de calibragem de controle ocular no dispositivo anteriormente.

| Aplicativo ativo | Comportamento anterior | comportamento de Windows Holographic, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo não habilitado para olhar ou shell Holographic |A caixa de diálogo solicitação de calibragem de acompanhamento ocular é exibida. | Nenhum prompt é exibido. |
| Aplicativo habilitado para olhar | A caixa de diálogo solicitação de calibragem de acompanhamento ocular é exibida. | A solicitação de calibragem de controle de olho é exibida somente quando o aplicativo acessa o fluxo de olhar de olho. |

Se o usuário fizer a transição de um aplicativo não olhar habilitado para um que acesse os dados do olhar, o prompt de calibragem será exibido. 

Todo o outro comportamento do sistema será semelhante a quando o usuário atual não tiver uma calibragem de acompanhamento de olho ativo. Por exemplo, o gesto de início de uma mão não será habilitado. Não haverá nenhuma alteração na experiência de instalação inicial para a primeira.

Para experiências que exigem dados olhars de olho ou posicionamento muito preciso do holograma, recomendamos que usuários não calibrados executem a calibragem de controle ocular. ele pode ser acessado no prompt de calibragem de controle ocular ou ao iniciar o aplicativo Configurações no menu iniciar e, em seguida, selecionar **calibragem de > do sistema > calibragem de olho > executar a calibragem**

Essas informações podem ser encontradas posteriormente com [outras informações de calibragem](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança de dispositivo e conformidade por meio do novo Gerenciador de certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

no Windows Holographic versão 20H2, estamos adicionando um gerenciador de certificados no aplicativo HoloLens 2 Configurações. vá para **Configurações > atualizar & segurança > certificados**. Esse recurso fornece uma maneira simples e amigável de usuário para exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

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

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) o CSP permite que HoloLens 2 sejam vinculados ao registro do MDM usando somente o autopilot. depois que o nó RequireNetworkInOOBE do CSP do TenantLockdown for definido como true ou false (inicialmente definido) no HoloLens 2, esse valor permanecerá no dispositivo, independentemente da atualização, das atualizações do sistema operacional, etc. 

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
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Essas duas novas regras para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas [Restrições Comuns de Dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Em relação ao [RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens dará suporte apenas à configuração ./Vendor/MSFT/RemoteLock/Lock. Não há suporte para as configurações que lidam com o PIN, como redefinição e recuperação.

### <a name="new-power-policies-for-hololens-2"></a>Novas políticas de energia para HoloLens 2
- Mais opções para quando HoloLens ou bloqueios por meio de políticas de energia. 

Essas políticas recém-adicionadas permitem que os administradores controlem estados de energia, como tempo de ociosidade. Para ler mais sobre cada política individual, clique no link dessa política.

|     Link da documentação da política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado Windows Designer de Configuração, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado Windows Designer de Configuração, ou seja,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas regras para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas [Restrições Comuns de Dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Para uma experiência consistente HoloLens 2, verifique se os valores para DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery estão definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Consulte [Exibir, manter e hibernar temporizadores ociosos](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre a espera moderna.

### <a name="newly-enabled-update-policies-for-hololens"></a>Políticas de atualização recém-habilitadas para HoloLens
- Mais opções para quando as Atualizações são instaladas ou desabilitando o botão Pausar Atualizações para garantir atualizações.

Essas políticas de atualização agora estão habilitadas HoloLens 2 dispositivos:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Detalhes completos sobre essas políticas de atualização e como usá-las para HoloLens dispositivos podem ser lidos aqui em Gerenciar [HoloLens atualizações.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Habilitada Configurações de página para HoloLens 2
- Maior controle de interface do usuário no aplicativo Configurações, o que pode ser confundido para mostrar uma seleção limitada de páginas.

Agora habilitamos uma política que permite que os administradores de IT impeçam que páginas específicas no aplicativo system Configurações sejam visíveis ou acessíveis ou para fazer isso para todas as páginas, exceto aquelas especificadas. Para saber como personalizar totalmente esse recurso, clique no link abaixo.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais configurações de página você pode personalizar HoloLens 2, visite nossa [página Configurações URIs.](settings-uri-list.md) 
 
![Captura de tela das horas ativas que estão sendo modificadas no Configurações aplicativo](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de pesquisa
No Modo de Pesquisa, o HoloLens 2 se torna uma ferramenta de pesquisa visual computacional. Em comparação com as edições anteriores, o Modo de Pesquisa para HoloLens 2 tem as seguintes vantagens:
-   além dos sensores expostos no modo de pesquisa HoloLens (1ª gen), agora fornecemos acesso de sensor IMU, incluindo acelerômetro, giroscópio e magnetômetro.
-   o HoloLens 2 fornece novos recursos que podem ser usados juntamente com o modo de pesquisa. Especificamente, o acesso a APIs articuladas de acompanhamento de mão e acompanhamento de olho que podem oferecer um conjunto mais rico de experimentos.

os pesquisadores agora têm a opção de habilitar o modo de pesquisa em seus dispositivos HoloLens para acessar todos esses fluxos de sensores de imagem bruta externa voltados para o. o modo de pesquisa para HoloLens 2 também fornece acesso às leituras acelerômetro, giroscópio e magnetômetro. Para proteger a privacidade dos usuários, as imagens de câmera de controle de olho bruto não estão disponíveis por meio do modo de pesquisa, mas a direção olhar está disponível por meio de APIs existentes.

Confira a [documentação do modo de pesquisa](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

### <a name="recording-length-increased"></a>Tamanho de gravação aumentado
Devido aos comentários do cliente, aumentamos o tamanho da gravação de [capturas de realidade misturada](holographic-photos-and-videos.md). As capturas de realidade misturada não serão mais limitadas a 5 minutos por padrão, mas, em vez disso, calculará o tamanho máximo de gravação com base no espaço em disco disponível. O dispositivo irá estimar a duração máxima da gravação de vídeo com base no espaço em disco disponível até 80% do espaço total em disco.

> [!NOTE]
> o HoloLens usará o comprimento de gravação de vídeo padrão (5 minutos) se ocorrer uma das seguintes opções:
> - A duração de gravação máxima estimada é menor do que o padrão de 5 minutos.
> - O espaço em disco disponível é inferior a 20% do espaço total em disco.

Você pode encontrar os requisitos completos em nossa documentação de [fotos e vídeos do Holographic](holographic-photos-and-videos.md#maximum-recording-length) . 

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:
- Mais telas no OOBE agora estão no modo escuro.
- Saiba mais conteúdo deve apontar para a mais recente política de privacidade online.
- Foi resolvido um problema em que os usuários não podiam provisionar perfis VPN por meio de pacotes de provisionamento.
- Problema de configuração de proxy fixo para conexão VPN.
- Política atualizada para desabilitar a enumeração de funções USB por meio do MDM para NCM para AllowUsbConnection.
- foi resolvido um problema que impedia a exibição de um dispositivo HoloLens no explorador de arquivos sobre o MTP (protocolo de transferência de mídia) quando o dispositivo é configurado como um [quiosque de aplicativo único](hololens-kiosk.md). Observe que o MTP (e a conexão USB em geral) ainda podem ser desabilitados usando a política [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- corrigido um problema em que os ícones na menu Iniciar foram dimensionados corretamente no modo de quiosque.
- Corrigido um problema devido ao cache HTTP interferir no modo de quiosque direcionado aos grupos do Azure AD.
- Corrigido um problema em que os usuários não conseguiram usar o botão emparelhar depois de habilitar o modo de desenvolvedor com pacotes de provisionamento, a menos que eles tenham desabilitado e habilitado o modo de desenvolvedor novamente.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versão 1903 – atualização de novembro de 2020
- Build 18362,1085

essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa versão mais recente do build de lançamento Windows Holographic, version 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versão 2004 – atualização de outubro de 2020
- Build 19041,1124
 
Melhorias e correções na atualização:

- Foi removida uma verificação desnecessária que causou a falha do sistema em tempo de execução.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versão 1903 – atualização de outubro de 2020
- Build 18362,1081

essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas compilações mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versão 2004-atualização de setembro de 2020
- Build 19041,1117

Melhorias e correções na atualização:

- resolve um problema que impediu Visual Studio de depurar um aplicativo quando SupportsMultipleInstances = "true" estiver presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy do NCSI para tratar da detecção de Internet com falha no proxy de rede. O NCSI pode usar o proxy de computador e proxy por perfil para detecção de conectividade com a Internet. O proxy por usuário terá suporte do NCSI em versões futuras.
- na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao chão quando o cabeçalho do usuário está em uma posição neutra, olhando para o futuro. no entanto, as versões anteriores do HoloLens 2 alinharam o vetor para serem perpendiculares aos painéis de exibição, o que está inclinado para baixo em alguns graus em relação à orientação ideal. as versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores forma.
- Maior robustez de rastreamento de mão que resultará em menos perdas de controle em cenários específicos.
- Esta versão contém uma correção para melhorar a qualidade do carimbo de data/hora de áudio que pode ter contribuído para problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versão 1903-atualização de setembro de 2020
- Build 18362,1079

Melhorias e correções na atualização:

- na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao chão quando o cabeçalho do usuário está em uma posição neutra, olhando para o futuro. no entanto, as versões anteriores do HoloLens 2 alinharam o vetor para serem perpendiculares aos painéis de exibição, o que está inclinado para baixo em alguns graus em relação à orientação ideal. as versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores forma.
- Maior robustez de rastreamento de mão que resultará em menos perdas de controle em cenários específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versão 2004-atualização de agosto de 2020
- Build 19041,1113

Melhorias e correções na atualização:

- Configurações aplicativo não seguirá mais o usuário no registro de íris ou em experiências de calibragem de acompanhamento de olho.
- Corrigido um bug em que a aplicação de um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como a conexão a uma rede) falha ao executar as outras ações após a reinicialização do dispositivo devido à renomeação.
- Esquema de cores modificado de fluxos de configuração de dispositivo inicial para melhorar a qualidade visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versão 1903-atualização de agosto de 2020
- Build 18362,1074

essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas compilações mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versão 2004 – atualização de julho de 2020
- Build 19041,1109

Melhorias e correções na atualização:

- Os desenvolvedores agora podem escolher entre habilitar ou desabilitar o portal do dispositivo exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Alterado o brilho da caixa de entrada padrão para 100 por cento.
- foi resolvido um problema sobre o encaminhamento de HTTPS para o Portal do dispositivo Windows no HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versão 1903 – atualização de julho de 2020
- Build 18362,1071

Melhorias e correções na atualização:

- Correção de um problema que poderia fazer com que os hologramas desapareçam em aplicativos do Unity quando perderem ou reconhecerem o controle.
- correção de um problema que causou a falha de aplicativos HoloLens exclusivos no shell ao usar o HoloLens Emulator com aceleração de hardware em determinados dispositivos.
- foi resolvido um problema relacionado ao encaminhamento de HTTPS para o Portal do dispositivo Windows no HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versão 2004 – atualização de junho de 2020
- Build 19041,1106

Melhorias e correções na atualização:

- Os gravadores da MRC personalizados agora têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (headset de imersão))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "obter o áudio do aplicativo" na página de captura da realidade misturada no Portal do dispositivo Windows)
    - MicrophoneGain (o valor atual de "lucro de áudio do Mic" na página de captura da realidade misturada no Portal do dispositivo Windows)
- Correção de um bug para melhorar a qualidade de áudio em cenários de captura de realidade misturada. Especificamente, essa correção deve eliminar a falha de áudio na gravação quando o menu **Iniciar** é exibido.
- Melhoria da estabilidade do holograma nos vídeos gravados.
- Foi resolvido um problema em que a captura de realidade misturada não pôde gravar vídeo depois que o dispositivo foi deixado no estado de espera por vários dias.
- A API HolographicSpace. userpresence geralmente é desabilitada para aplicativos do Unity. Esse comportamento evita um problema que fez com que alguns aplicativos pausarem quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" estivesse habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity e do 2019.3.4 e posterior.
- Quando você acessa o portal do dispositivo em uma conexão Wi-Fi, um navegador da Web pode impedir o acesso devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo que o certificado do dispositivo tenha sido confiável anteriormente. Nesse caso, não é possível progredir para o portal do dispositivo, pois não há nenhuma opção para ignorar os avisos de segurança. Essa atualização resolveu o problema. Se o certificado do dispositivo tiver sido baixado anteriormente e for confiável em um computador para remover avisos de segurança do navegador e o erro SSL ocorrer, o novo certificado precisará ser baixado e confiável para resolver os avisos de segurança do navegador.
- Habilitada a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
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

Saiba mais no guia [de avaliação Windows Autopilot para HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Entre em contato com seu Gerente de Conta para ingressar na versão prévia do AutoPilot agora. Os dispositivos prontos para piloto automático começarão a ser entregados em breve.*

### <a name="fido2-security-key-support"></a>Suporte à chave de segurança FIDO2

Alguns usuários compartilham um HoloLens com outros em um ambiente corporativo ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. O Fast Identity Online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre perfeitamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação sem senha baseado em padrões "imfragável" que pode vir em qualquer fator de forma. FIDO é um padrão aberto para autenticação sem senha. Ele permite que usuários e organizações se inscrevam em seus recursos sem um nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma interna em um dispositivo.

Para começar, consulte [Habilitar a login](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)da chave de segurança sem senha.

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

Um [CSP (provedor de serviços de configuração)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou excluir definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores têm sobre dispositivos HoloLens implantados. Para ver a lista de CSPs com suporte pelo HoloLens, consulte [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novidades nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa configure políticas em Windows dispositivos. Nesta versão, adicionamos novas políticas para HoloLens, que são listadas aqui. Para saber mais, confira [CSPs de política com suporte HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

O provedor de serviços de configuração NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, confira [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Suporte expandido de Ethernet USB para dispositivos conectados a 5G/LTE

Foi adicionado suporte para habilitar determinados dispositivos de banda larga móvel, como telefones 5G/LTE e hotspots Wi-Fi, quando eles são conectados ao HoloLens 2 via USB. Esses dispositivos agora são exibidos nas **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos móveis de banda larga que exigem um driver externo.) Essa funcionalidade habilita conexões de alta largura de banda quando Wi-Fi não está disponível e Wi-Fi a conexões não tem desempenho suficiente. Para saber mais sobre dispositivos USB com suporte, [consulte Conexão para Bluetooth dispositivos USB-C e](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Melhorias no acompanhamento de mão

Esta versão inclui várias melhorias de acompanhamento de mão:

- **Apontando a estabilidade da pose:** O sistema agora resistem a inclinar o dedo indicador quando ele é ocluído pela mão. Essa alteração melhora a precisão quando você pressiona botões, digita, rola conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Melhoramos a detecção do gesto de toque de ar. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta as mãos para seus lados.
- **Confiabilidade da opção do usuário:** O sistema agora é mais rápido e confiável na atualização do tamanho da mão quando você compartilha um dispositivo.
- **Roubo de mão reduzido:** Melhoramos o tratamento de casos em que há mais de duas mãos à vista dos sensores. Se várias pessoas estão trabalhando juntas, agora há uma chance muito menor de que a mão rastreada "pule" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Corrigido um problema que fez com que o acompanhamento de mão parasse de funcionar quando o dispositivo está sob alta carga.

### <a name="dark-mode"></a>Modo escuro

Muitos Windows aplicativos agora são suportados nos modos escuro e claro. HoloLens dois usuários podem escolher o modo padrão para aplicativos que suportam ambos. Após a atualização, o modo de aplicativo padrão é "escuro", mas você pode alterar facilmente **essa** configuração: Navegue até Configurações Cores do Sistema Escolha o  >    >    >  **modo de aplicativo padrão**. 

Esses aplicativos "in-box" são suportados no modo escuro: 

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

![Janelas de modo escuro lado a lado](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, [consulte Usar sua voz para operar HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulte também [Idiomas com suporte para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Cortana atualizações

O aplicativo atualizado se integra ao Microsoft 365 para ajudá-lo a fazer mais em seus dispositivos (atualmente, US-English apenas). No HoloLens 2, Cortana dá mais suporte a determinados comandos específicos do dispositivo, como ajustar o volume ou reiniciar. Essas opções agora são suportadas pelos novos comandos de voz do sistema. Saiba mais sobre o novo Cortana em nosso [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibragem de exibição ativo. Esse recurso melhora a estabilidade e o alinhamento dos hologramas. Agora eles permanecem no local quando você move a cabeça de um lado para outro.
- Corrigido um bug em que Wi-Fi streaming para HoloLens interrompido periodicamente. Se um aplicativo indicar que ele precisa de streaming de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Corrigida uma trava de dispositivo que ocorreu durante o streaming no modo de pesquisa.
- Corrigido um bug em que, em alguns casos, o usuário correto não seria exibido na tela de logon ao retomar uma sessão.
- Corrigido um problema em que os usuários não podiam exportar logs de MDM por meio **Configurações**.
- Corrigido um problema em que a precisão do acompanhamento ocular imediatamente após a configuração pronta para uso poderia ser menor do que o esperado.
- Corrigido um problema em que o subsistema de acompanhamento ocular falhava ao inicializar ou executar a calibragem em determinadas condições.
- Corrigido um problema em que a calibragem ocular seria solicitado a um usuário já calibrado.
- Corrigido um problema em que um driver falhava durante a calibragem ocular.
- Corrigido um problema em que pressionamentos repetidos do botão de energia podiam causar um tempo de tempo de sistema de 60 segundos e uma falha no shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um **botão Compartilhar** no Hub de Comentários para que os usuários possam compartilhar comentários com mais facilidade.
- Corrigido um bug em que o RoboRaid wan não estava instalado corretamente.

### <a name="known-issues"></a>Problemas conhecidos

- Um problema com a linguagem do sistema zh-CN impede que os comandos de voz capturem uma realidade misturada ou exibem o endereço IP do dispositivo.
- Um problema exige que você iniciar o aplicativo Cortana depois de iniciar o dispositivo para usar a ativação de voz "Hey Cortana". Se você tiver atualizado de um build 18362, também poderá ver um segundo peças de aplicativo para a versão anterior do aplicativo Cortana que não funciona mais em **Iniciar**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versão 1903 – Atualização de maio de 2020 
- Build 18362.1061

Essa atualização de qualidade mensal não contém nenhuma alteração notável porque a equipe estava trabalhando no Windows Holographic versão 2004, conforme descrito anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versão 1903 – Atualização de abril de 2020
- Build 18362.1059

**Modo escuro para aplicativos com suporte** 

Muitos Windows aplicativos têm suporte para o modo escuro e claro. HoloLens 2 clientes agora podem escolher o modo padrão para aplicativos que suportam ambos os esquemas de cores. Com base nos comentários dos clientes, definimos o modo de aplicativo padrão como "escuro", mas você pode alterar facilmente essa configuração a qualquer momento: navegue até Configurações > Cores do **Sistema >** para encontrar "Escolher o modo de aplicativo **padrão".**

Esses aplicativos "in-box" são suportados no modo escuro:
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
- Garante que as sobreposições de shell sejam incluídas em capturas de realidade misturada.
- Os desenvolvedores do Unreal agora podem usar a página exibição 3D no Portal de Dispositivos testar e depurar seus aplicativos.
- Melhor estabilidade do holograma na captura de realidade misturada quando o *algoritmo HolographicDepthReprojectionMethod DepthReprojection* é usado.
- Correção do erro "Classe de API WinRT IStreamSocketListener não registrada" em aplicativos ARM de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versão 1903 – Atualização de março de 2020 
- Build 18362.1056

Melhorias e correções na atualização:

- Melhor estabilidade do holograma na captura de realidade misturada quando o *algoritmo HolographicDepthReprojectionMethod AutoPlanar* é usado.
- Garantiu que o sistema de coordenadas anexado a um exemplo de MF de profundidade é consistente com a documentação pública.
- Maior produtividade do desenvolvedor, permitindo que os clientes colem grandes quantidades de texto por meio do portal do dispositivo.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versão 1903-atualização de fevereiro de 2020 
- Build 18362,1053

Melhorias e correções na atualização:

- Desabilitada temporariamente a API HolographicSpace. userpresence para aplicativos Unity. Essa alteração evita um problema que fez com que alguns aplicativos pausarem quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" estivesse habilitada.
- Correção de uma falha aleatória do HUP causada pelo acompanhamento manual, em que o usuário observou uma interface do usuário e, em seguida, de volta para o Shell após vários segundos.
- Acompanhamento de mão aprimorado para que, quando você se refaça com o dedo do seu índice, a parte superior do dedo tenha menos probabilidade de ser enrolada inesperadamente.
- Maior confiabilidade de rastreamento de cabeçalho, mapeamento espacial e outros tempos de execução.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versão 1903 – atualização de janeiro de 2020 
- Build 18362,1043
 
Melhorias e correções na atualização:

- estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versão 1903-atualização de dezembro de 2019 
- Build 18362,1042

Melhorias e correções na atualização:

- Introduziu correções de LSR (última reprodução de estágio). Processamento visual aprimorado de hologramas para parecer mais estável e nítido por uma contabilidade mais precisa para sua profundidade. Esse sintoma será mais perceptível após essa atualização se os aplicativos não definirem a profundidade de holograma corretamente.
- Correção da estabilidade de aplicativos exclusivos e navegação entre aplicativos exclusivos.
- Foi resolvido um problema em que a captura de realidade misturada não pôde gravar vídeo depois que o dispositivo estava em estado de espera por vários dias.
- Melhoria da estabilidade do holograma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versão 1903 – atualização de novembro de 2019 
- Build 18362,1039

Melhorias e correções na atualização:

- Correção da funcionalidade de **selecionar** comandos de voz durante a configuração inicial para en-CA e en-au.
- a qualidade visual aprimorada de objetos foi colocada de longe nas versões mais recentes do Unity e da reality Toolkit (MRTK).
- correção de problemas de endereçamento com aplicativos holographic que ficam presos em um estado de pausa na inicialização até que o menu Iniciar foi aberto e, em seguida, fechado.
- correções de conformidade do OpenXR runtime e melhorias para o HoloLens 2 e o emulador.
