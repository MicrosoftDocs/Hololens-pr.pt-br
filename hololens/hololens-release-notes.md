---
title: Notas sobre a versão do HoloLens 2
description: Mantenha-se atualizado com todas as atualizações em cada nova versão do HoloLens 2.
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
ms.openlocfilehash: 16aec0e60fde40f0a2bffefa871a7a3774b1eb2e
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924529"
---
# <a name="hololens-2-release-notes"></a>Notas sobre a versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus dispositivos HoloLens, continuamos a lançar atualizações de recursos, bugs e segurança. Nesta página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização mais recente do HoloLens 2, você pode verificar se há atualizações e atualizar [manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a FFU (Atualização flash completa) para piscar seu dispositivo por meio do [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). O [download](https://aka.ms/hololens2download) é mantido atualizado e fornece o build mais recente disponível.

> [!NOTE]
> O comunicado recente do Windows 11 se concentrou na versão do pc do Windows. Recentemente, lançamos uma atualização [principal](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) do sistema operacional para o HoloLens 2 em maio de 2021 e estamos trabalhando em uma versão futura com base nos comentários dos clientes para essa queda.

> [!IMPORTANT]
> Devido a um problema conhecido em nosso [build do 21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)que está afetando os usuários do Remote Assist, estamos pausando a oferta de atualizações do Windows Holographic, versão 21H1. Também mudamos o build do Advanced Recovery Companion padrão para ser o Windows Holographic, versão 20H2 – Atualização de junho de [2021,](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)que é a versão mais recente do 20H2.
>
> Embora reduzimos a disponibilidade de 21H1 para reduzir o impacto desse problema, entendemos que alguns clientes ainda podem querer atualizar para 21H1. Para clientes que desejam atualizar para o 21H1, há dois caminhos diferentes disponíveis:
>
> - [Registrar seus dispositivos](hololens-insider.md#start-receiving-insider-builds) como Windows Insiders e selecionar o Canal beta **,** isso permitirá que esses dispositivos atualizem para 21H1 e tenham builds confiáveis.
> - [Baixe o FFU mais recente em seu computador e,](https://aka.ms/hololens2download) em seguida, [flash do dispositivo por meio do Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device).

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, versão 21H1 – Atualização de junho de 2021
- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>Upload do OneDrive for Work ou School Camera Roll

Adicionamos um novo recurso ao aplicativo configurações do HoloLens 2, que permite que os clientes carreguem automaticamente fotos e vídeos de realidade misturada da pasta Imagens > Camera Roll do dispositivo para a pasta correspondente do OneDrive para trabalho ou escola. Esse recurso aborda uma lacuna de recursos dentro do aplicativo [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) no HoloLens 2, que dá suporte apenas ao upload automático do Roll da Câmera para o sistema conta Microsoft pessoal do cliente (e não sua conta de trabalho ou de estudante).

**Como funciona**

- Visite **Configurações > sistema > Câmera de Realidade Misturada** para habilitar o "Upload da câmera".
- Ao definir esse  recurso para a posição Ativado, todas as fotos ou vídeos de realidade misturada capturados em seu dispositivo serão automaticamente en enxuados para upload na pasta Imagens > do Roll da Câmera do OneDrive para a conta de trabalho ou de estudante.
    >[!NOTE]
    >Fotos e vídeos capturados antes  da habilitação desse recurso não serão na fila para upload e ainda precisarão ser carregados manualmente.
- Uma mensagem de status na página Configurações exibirá o número de arquivos pendentes de upload (ou leia "O OneDrive está atualizado" quando todos os arquivos pendentes foram carregados).
- Se você estiver preocupado com a largura de banda ou quiser "pausar" o upload por qualquer motivo, poderá alternar o recurso para a **posição** Desligado. Desabilitar temporariamente o recurso garante que a fila de upload continuará aumentando conforme você adicionar novos arquivos à pasta Roll da Câmera, mas os arquivos não serão carregados até que você reabilitar o recurso.
- Os arquivos mais novos serão carregados primeiro (último a entrar, primeiro a sair).
- Se sua conta do OneDrive tiver problemas (por exemplo, após **a** alteração da senha), um botão Corrigir agora será exibido na página Configurações.
- Não há nenhum tamanho máximo de arquivo, mas observe que arquivos grandes levarão mais tempo para carregar (especialmente se a largura de banda de upload estiver restrita). Se você "pausar" ou desativar o upload enquanto um arquivo grande estiver sendo carregado, o upload parcial será preservado. Se o upload for reabilitar dentro de várias horas após ter sido "pausado" ou desligado, o upload continuará de onde parou. No entanto, se o upload for habilitado novamente após várias horas, o upload do arquivo grande será reiniciado desde o início.

**Problemas conhecidos e advertências**

- Essa configuração não tem limitação criada com base no uso de largura de banda atual. Se você precisar maximizar a largura de banda para outro cenário, desligue a configuração manualmente. O upload será pausado, mas o recurso continuará a monitorar os arquivos recém-adicionados ao Roll da Câmera. Reabilitar o upload quando estiver pronto para continuar.
- Esse recurso deve ser habilitado para cada conta de usuário no dispositivo e só pode carregar ativamente arquivos para o usuário conectado no momento ao dispositivo.
- Se você estiver fazendo fotos ou vídeos enquanto observa a contagem de upload na página Configurações em tempo real, observe que a contagem de arquivos pendentes pode não mudar até que o arquivo atual tenha concluído o carregamento.
- O upload será pausado se o dispositivo ficar inodor ou estiver desligado. Para garantir que os uploads pendentes são concluídos, use ativamente o dispositivo até que a página Configurações leia "O OneDrive está atualizado" ou ajuste as configurações de sleep **do Power &.**
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
>Para atualizar para esse build, os dispositivos holoLens 2 devem estar executando a atualização de fevereiro de 2021 (build 19041.1136) ou mais recente. Se você não estiver vendo essa atualização de recurso disponível, atualize seu dispositivo primeiro e tente novamente.

>[!NOTE]
>Atualmente, Microsoft HoloLens 2 dá suporte a atualizações mensais de manutenção (correções de bugs e segurança) para as seguintes versões:
>- Windows Holographic, versão 20H2 (Build 19041.1128+)
>- Windows Holographic, versão 2004 (Build 19041.1103+)
>- Windows Holographic, versão 1903 (Build 18362+) 
>
> Com a introdução do Windows Holographic versão 21H1, estamos descontinuando as atualizações mensais de manutenção para **o Windows Holographic versão 1903.** Isso nos permite se concentrar em versões mais recentes e continuar a fornecer melhorias valiosas. 


| Nome do recurso                                              | Descrição breve                                                                      | Público-alvo | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Novos Microsoft Edge](#introducing-the-new-microsoft-edge)  | O novo modelo baseado em Chromium Microsoft Edge está disponível para o HoloLens 2. | Usuário Final | 
[WebXR e Visualizador 360](#webxr-and-360-viewer) | Experimente experiências imersivas na Web e reprodução de vídeo 360. | Usuário Final | 
[Novo aplicativo configurações](#new-settings-app) | O aplicativo de Configurações herdado está sendo substituído por uma versão atualizada por novos recursos e configurações. | Usuário Final |
[Exibir calibragem de cores](#display-color-calibration) | Selecione um perfil de cor alternativo para a exibição do HoloLens 2. | Usuário Final |
[Selador de aplicativo padrão](#default-app-picker) | Escolha qual aplicativo deve ser lançado para cada arquivo ou tipo de link. | Usuário Final |
[Por controle de volume do aplicativo](#per-app-volume-control) | Controlar o volume no nível do aplicativo independentemente do volume do sistema. | Usuário Final |
[Instalar aplicativos Web](#install-web-apps) | Instale aplicativos Web no HoloLens 2, como Microsoft Office, com o novo Microsoft Edge navegador. | Usuário Final |
[Passar o dedo para o tipo](#swipe-to-type) | Use a dica do dedo para "passar o dedo" nas palavras no teclado holográfico. | Usuário Final |
[Menu de energia de Iniciar](#power-menu-from-start) | No Menu Iniciar, reinicie e desligue o dispositivo HoloLens. | Usuário Final |
[Vários usuários listados na tela Entrar](#multiple-users-listed-on-sign-in-screen) | Exibir várias contas de usuário na tela Entrar. | Usuário Final |
[Suporte a microfone externo USB-C](#usb-c-external-microphone-support) | Use microfones USB-C para aplicativos e/ou Assistência Remota. | Usuário Final |
[Logon automático do Visitante para Quiosques](#visitor-auto-logon-for-kiosks) | Permite que o logon automático em contas de Visitante seja usado para modos de quiosque. | Administrador de TI |
[Novos AUMIDs para novos aplicativos no modo quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs para novos aplicativos configurações e borda. | Administrador de TI |
[Melhoria na entrega de falha do modo de quiosque](#kiosk-mode-behavior-changes-for-handling-of-failures) | O modo de quiosque procura Acesso Atribuído Global antes do menu iniciar vazio. | Administrador de TI |
[Novas configuraçõesURIs para visibilidade de configurações de página](#new-settings-uris-for-page-settings-visibility) | 20+ novas ConfiguraçõesURIs para configurações/política PageVisibilityList. | Administrador de TI |
[Configurar o diagnóstico de fallback](#configuring-fallback-diagnostics-via-settings-app) | Definindo o comportamento de diagnóstico de fallback no aplicativo de configurações. | Administrador de TI |
[Compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices) | Compartilhar arquivos ou URLs de um HoloLens para um PC. | Tudo |
[Novos rastreamentos de diagnóstico do sistema operacional](#new-os-diagnostic-traces) | Nova solução de problemas em Configurações para atualizações do sistema operacional. | Administrador de TI |
[Otimização de Entrega versão prévia](#delivery-optimization-preview) | Reduza o consumo de largura de banda para downloads de vários dispositivos HoloLens. | Administrador de TI |

Confira as notas de versão relacionadas:

- [Visite o arquivo do Emulador do HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Introdução à nova Microsoft Edge

![Animação do logotipo Microsoft Edge herdado para o novo Microsoft Edge logotipo](images/new-edge.gif)

A nova Microsoft Edge o projeto de software livre [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para criar melhor compatibilidade para clientes e menos fragmentação da Web para desenvolvedores da Web.

> [!IMPORTANT]
> Esse novo Microsoft Edge substitui automaticamente os Microsoft Edge herdados, que não [têm mais suporte](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) em novas versões.

![Nova Microsoft Edge de tela](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Iniciando a nova Microsoft Edge

O novo Microsoft Edge ![novo Microsoft Edge ícone](images/new_edge_logo.png) (representado por um ícone azul e verde) é fixado no menu Iniciar e será automaticamente lançado quando você ativar um link da Web.

> [!NOTE]
> Quando você iniciar o novo Microsoft Edge no HoloLens 2, suas configurações e dados serão importados do Microsoft Edge. Se você continuar a usar o Microsoft Edge herdado depois de iniciar o novo Microsoft Edge, esses novos dados não serão sincronizados do Microsoft Edge herdado para o novo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Definindo configurações de política para o novo Microsoft Edge

O novo Microsoft Edge oferece aos administradores de IT um conjunto muito mais amplo de políticas de navegador no HoloLens 2 do que estavam disponíveis anteriormente com recursos Microsoft Edge.

Aqui estão alguns recursos úteis para saber mais sobre como gerenciar configurações de política para o novo Microsoft Edge:

- [Definir Microsoft Edge de política com Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Versão Prévia do Microsoft Edge para Microsoft Edge de política](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome para Microsoft Edge de política](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentação [Microsoft Edge Enterprise completa](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Devido ao volume de políticas de navegador com suporte pelo novo Microsoft Edge, nossa equipe não pode garantir que cada nova política funcione no HoloLens 2. No entanto, testamos e confirmamos que o novo Microsoft Edge equivalente de cada política de Microsoft Edge herdada com suporte anteriormente no HoloLens 2 funciona conforme o esperado. Consulte [Versão Prévia do Microsoft Edge para Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) de política para encontrar o novo Microsoft Edge equivalente de cada política de navegador Microsoft Edge herdada que você estava usando com o HoloLens 2.
>
> Há pelo menos duas novas políticas Microsoft Edge que sabemos que *não funcionarão* com o HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>O que esperar da nova Microsoft Edge no HoloLens 2

Como o novo Microsoft Edge é um aplicativo Win32 nativo com uma nova camada de adaptador UWP que permite que ele seja executado em dispositivos somente UWP como o HoloLens 2, alguns recursos podem não estar disponíveis imediatamente. Vamos dar suporte a novos cenários e recursos nos próximos meses, portanto, verifique esse espaço para obter informações atualizadas.

**Cenários e recursos esperados para funcionar:**
- Experiência de primeira vez, entrar no perfil e sincronizar
- Os sites devem renderizar e se comportar conforme o esperado
- A maioria das funcionalidades do navegador (Favoritos, Histórico etc.) deve funcionar conforme o esperado
- Modo escuro
- Instalando aplicativos Web no dispositivo
- Instalando extensões (conte-nos se você usar extensões que não funcionam corretamente no HoloLens 2)
- Exibindo e marcando um PDF
- Som espacial de uma única janela do navegador
- Atualização automática e manual do navegador
- Salvando um PDF no menu Imprimir (usando a opção "Salvar em PDF")
- Extensão webXR e visualizador 360
- Restauração de conteúdo para a janela correta ao navegar entre várias janelas colocadas em seu ambiente

**Cenários e recursos que não devem funcionar:**
- Som espacial de várias janelas com fluxos de áudio simultâneos
- "Veja isso, diga".
- Imprimindo

**Principais problemas conhecidos do navegador:**

- A visualização da lupa no teclado holográfico foi desabilitada para o novo Microsoft Edge. Esperamos reativar esse recurso em uma atualização futura, quando a ampliação estiver funcionando corretamente.
- O áudio poderá ser reproduzir na janela do navegador errada se você tiver outra janela do navegador aberta e ativa. Você pode resolver esse problema fechando a outra janela ativa que não deveria estar tocando áudio.
- Ao tocar áudio de uma janela do navegador [no modo "Follow me",](hololens2-basic-usage.md#follow-me-stop-following)o áudio continuará sendo gravado se você desabilitar o modo "Follow me". Você pode resolver esse problema interrompendo a reprodução de áudio antes de desabilitar o modo "Follow me" ou fechando a janela com o **botão X.**
- Interagir com janelas Microsoft Edge ativa pode fazer com que outras janelas de aplicativo 2D inativam inesperadamente. Você pode reativar essas janelas interagindo com elas novamente.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge insider

A Microsoft Edge disponibiliza três canais de visualização para a comunidade do Edge Insider: Beta, Dev e Canary. A instalação de um canal de visualização não desinstala a versão lançada do Microsoft Edge em seu HoloLens 2 e você pode instalar mais de um ao mesmo tempo. 

Visite a [home page do Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para saber mais sobre a comunidade do Edge Insider. Para saber mais sobre os diferentes canais do Edge Insider e começar, visite a página de [download do Edge Insider](https://www.microsoftedgeinsider.com/download).

Há alguns métodos disponíveis para instalar os canais Microsoft Edge Insider no HoloLens 2:

**Instalação direta no dispositivo (atualmente disponível apenas para dispositivos não planejados)**
  1. No HoloLens 2, visite a página de [download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão Baixar para HoloLens 2** para o canal do Edge Insider que você deseja instalar.
  1. Iniciar o arquivo .msix baixado da fila de download do Edge ou da pasta "Downloads" do dispositivo (usando Explorador de Arquivos).
  1. [O instalador de aplicativo](app-deploy-app-installer.md) será lançado.
  1. Selecione o botão **Instalar**.
  1. Após a instalação bem-sucedida, você encontrará Microsoft Edge Beta, Dev ou Canário como uma entrada separada na lista **Todos os apps** do menu Iniciar.

**Instalar por meio de computador com Portal de Dispositivos do Windows (requer que [o](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) modo de desenvolvedor seja habilitado no HoloLens 2)**
  1. Em seu computador, visite a página [de download do Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecione o **botão de seta para baixo** ao lado do botão "Baixar Windows 10" para o canal do Edge Insider que você deseja instalar.
  1. Selecione **HoloLens 2** no menu suspenso.
  1. Salve o arquivo .msix na pasta "Downloads" do computador (ou em outra pasta que você possa encontrar facilmente).
  1. Use [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) em seu computador para instalar o arquivo .msix baixado no HoloLens 2.
  1. Após a instalação bem-sucedida, você encontrará Microsoft Edge Beta, Dev ou Canário como uma entrada separada na lista **Todos os apps** do menu Iniciar.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Usando o WDAC para bloquear novos Microsoft Edge

Para administradores de TI que buscam atualizar a política [do WDAC](windows-defender-application-control-wdac.md) para bloquear o novo aplicativo Microsoft Edge, você precisará adicionar o seguinte à sua política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerenciando pontos de extremidade para a nova Microsoft Edge

Alguns ambientes podem ter restrições de rede a considerar como uma consideração. Para garantir uma experiência tranquila com o novo Edge, [habilita esses pontos de extremidade da Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os pontos de extremidade disponíveis no momento [para o HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Instalar aplicativos Web
 > [!Note]
>A partir [do Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)o aplicativo Web do Office não será mais pré-instalado.

Você pode usar o novo Edge para instalar aplicativos Web junto com Microsoft Store aplicativos. Por exemplo, você pode instalar o Microsoft Office Web para exibir e editar arquivos hospedados no SharePoint ou no OneDrive. Para instalar o aplicativo Web do Office, visite e selecione o botão Aplicativo https://www.office.com **Disponível** ou Instalar **o Office** na barra de endereços. Selecione **Instalar** para confirmar.

> [!IMPORTANT]
> A funcionalidade do aplicativo Web do Office só estará disponível quando o HoloLens 2 tiver uma conexão de Internet ativa.

### <a name="webxr-and-360-viewer"></a>WebXR e Visualizador 360

O novo Microsoft Edge inclui suporte para WebXR, que é o novo padrão para criar experiências da Web imersivas (substituindo WebVR). Muitas experiências imersivas da Web foram projetadas com VR em mente (elas substituem seu campo de exibição por um ambiente virtual), mas essas experiências também têm suporte do HoloLens 2. O padrão WebXR também permite experiências da Web imersivas de realidade aumentada e misturada que usam seu ambiente físico. À medida que os desenvolvedores gastam mais tempo com o WebXR, prevemos que novas experiências imersivas de realidade aumentada e misturada chegarão para os clientes do HoloLens 2 experimentarem!

A extensão do Visualizador 360 é criada no WebXR e é instalada automaticamente junto com o novo Microsoft Edge no HoloLens 2. Essa extensão da Web oferece a capacidade de se aprofundar em vídeos de 360 graus. O YouTube oferece a maior seleção de 360 vídeos, portanto, incentivamos você a começar lá.

#### <a name="how-to-use-webxr"></a>Como usar o WebXR

1. Navegue até um site com suporte a WebXR.
1. Selecione o **botão Inserir VR** no site. O local e a representação visual desse botão podem variar por site, mas pode ser semelhante a:

    ![Exemplo de botão Inserir VR](images/75px-enter-vr.png)

1. Na primeira vez que você tentar iniciar uma experiência WebXR em um domínio específico, o navegador solicitará consentimento para inserir uma exibição imersiva, selecione **Permitir**.
1. Use [gestos do HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular a experiência.
1. Se a experiência não tiver um botão **Sair,** use o gesto [Iniciar](hololens2-basic-usage.md#start-gesture) para retornar para casa.

**Exemplos de WebXR recomendados**
- Visualizador 360 (consulte a próxima seção)
- [XR Dinos](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [Pintura do WebXR](https://threejs.org/examples/webxr_vr_paint.html)

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

### <a name="new-settings-app"></a>Novo aplicativo configurações

Com esta versão, estamos introduzindo uma nova versão do aplicativo Configurações. O novo aplicativo Configurações inclui novos recursos e configurações expandidas para o HoloLens 2 nas seguintes áreas: Som, avaliação do Power &, Internet do & de rede, Aplicativos, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Como o novo aplicativo Configurações é diferente do aplicativo de Configurações herdado, todas as janelas configurações colocadas anteriormente em seu ambiente serão removidas após a atualização.

![Home page do aplicativo Novas Configurações](images/new-settings-app.png)

**Novos recursos e configurações**
- Pesquisa de configurações: pesquise as configurações na home page Configurações usando palavras-chave ou o nome da configuração.
- Som > sistema:
  - Dispositivos de áudio de entrada e saída: escolha independentemente seus dispositivos de áudio de entrada e saída (por exemplo, escutar áudio por meio de fones de ouvido Bluetooth ou usar um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Não há suporte para microfones Bluetooth no HoloLens 2.
  - Volume do aplicativo: ajuste independentemente o volume de cada aplicativo. Consulte [por controle de volume do aplicativo](#per-app-volume-control).
- Sistema > o & sleep: escolha quando o dispositivo deve ficar em atividade após um período de inatividade.
- Bateria > sistema: habilita manualmente o modo economia de bateria ou definir um limite de bateria no qual o modo economia de bateria ponto é ativado automaticamente.
- Dispositivos > USB: você pode desabilitar conexões USB por padrão.
- Rede & Internet:
  - Os adaptadores Ethernet USB-C agora aparecerão na Rede & Internet.
  - As configurações do adaptador Ethernet USB-C agora estão disponíveis, incluindo seu endereço IP.
  - Agora você pode habilitar o modo avião no HoloLens 2.
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Para obter mais informações, [consulte Se picker de aplicativo padrão.](#default-app-picker)
- Contas > Outros usuários: os proprietários do dispositivo podem adicionar usuários, atualizar usuários padrão para proprietários de dispositivos, fazer downgrade de proprietários de dispositivos para usuários padrão e remover usuários.
- Facilidade de Acesso: alterar o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- Janelas de configurações colocadas anteriormente serão removidas (veja a observação acima).
- Você não pode mais renomear seu dispositivo com o aplicativo Configurações. Os administradores de IT podem renomear dispositivos usando o modelo de nome de dispositivo [Windows Autopilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) ou o nó [MDM DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- A página Ethernet mostra um dispositivo Ethernet virtual ("UsbNcm") em todos os momentos.
- O uso de bateria para o novo Microsoft Edge pode não ser preciso, devido à sua natureza como um aplicativo da área de trabalho Win32 com suporte por uma camada de adaptador UWP (nenhuma correção prevista em breve).

#### <a name="display-color-calibration"></a>Exibir calibragem de cores



Com essa nova configuração, você pode selecionar um perfil de cor alternativo para a exibição do HoloLens 2. Isso pode ajudar as cores a aparecerem mais precisas, especialmente em níveis de brilho de exibição inferiores. A calibragem de cores de exibição pode ser encontrada no aplicativo Configurações, na página Calibragem > Sistema.

> [!NOTE]
> Como essa configuração salva um novo perfil de cor no firmware de exibição, é uma configuração por dispositivo (e não exclusiva para cada conta de usuário).

##### <a name="how-to-use-display-color-calibration"></a>Como usar a calibragem de cores de exibição

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
> - Você pode executar a calibragem de cores de exibição de configurações sempre que quiser
> - Se alguém no dispositivo tiver usado anteriormente a configuração para alterar perfis de cor, a data/hora da alteração mais recente será refletida na página Configurações
> - Quando você executar a calibragem de cores de exibição, o perfil de cor salvo anteriormente será realçado e o Perfil 0 não será exibido (como o Perfil 0 representa o perfil de cor original da exibição)
> - Se você quiser reverter para o perfil de cor original da exibição, poderá fazer isso na página Configurações (consulte como redefinir o perfil [de cor](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cor 

Se você não estiver satisfeito com o perfil de cor personalizado salvo no HoloLens 2, poderá restaurar o perfil de cor original do dispositivo:
1. Iniciar o **aplicativo Configurações** e navegue até **Calibragem > Sistema.**
1. Em **Exibir calibragem de cores,** selecione o **botão Redefinir para o perfil de cor** padrão.
1. Quando a caixa de diálogo for aberta, **selecione** Reiniciar se você estiver pronto para reiniciar o HoloLens 2 e aplicar as alterações.

#### <a name="top-display-color-calibration-known-issues"></a>Principais problemas conhecidos de calibragem de cores de exibição

- Na página Configurações, a cadeia de caracteres de status que informa quando o perfil de cor foi alterado pela última vez ficará des date até que você recarregue essa página de Configurações.
    - Solução alternativa: selecione outra página Configurações e, em seguida, selecione a página Calibragem.

#### <a name="default-app-picker"></a>Selador de aplicativo padrão

Ao ativar um hiperlink ou abrir um tipo de arquivo com mais de um aplicativo instalado, que dá suporte a ele, você verá uma nova janela aberta solicitando que você selecione qual aplicativo instalado deve lidar com o tipo de arquivo ou link. Nessa janela, você também pode optar por fazer com que o aplicativo selecionado manipular o arquivo ou o tipo de link "Uma vez" ou "Sempre".

Se você escolher "Sempre", mas posteriormente quiser alterar qual aplicativo lida com um arquivo ou tipo de link específico, poderá redefinir os padrões salvos em Configurações **> Aplicativos**. Role até a parte inferior  da página e selecione o botão Limpar em "Aplicativos padrão para tipos de arquivo" e/ou "Aplicativos padrão para tipos de link". Ao contrário da configuração semelhante em computadores desktop, você não pode redefinir padrões de tipo de arquivo individuais.

#### <a name="per-app-volume-control"></a>Por controle de volume do aplicativo

Agora, neste build do Windows, os usuários podem ajustar manualmente o nível de volume de cada aplicativo. Isso permite que os usuários se concentrem melhor nos aplicativos que precisam ou ouvir melhor ao usar vários aplicativos. Como a necessidade de desativar o volume de um aplicativo ao chamar outra pessoa para assistência remota em outro.

Para definir o volume de um aplicativo individual, navegue até Configurações Som do Sistema e, em Opções de som **avançadas,** selecione Volume do aplicativo e  ->    ->   **preferências do dispositivo.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Passar o dedo para o tipo

Alguns clientes acham mais rápido "digitar" em teclados virtuais ao deslizar a forma da palavra que pretendem digitar e estamos visualizando esse recurso para o teclado holográfico. Você pode passar o dedo uma palavra por vez passando a ponta do dedo pelo plano do teclado holográfico, passando a forma da palavra e, em seguida, retirando a ponta do dedo do plano do teclado. Você pode passar o dedo nas palavras de acompanhamento sem precisar pressionar a barra de espaço removendo o dedo do teclado entre palavras. Você saberá que o recurso está funcionando se vir uma trilha de deslizar o dedo após o movimento do dedo no teclado.

Observe que esse recurso pode ser complicado de usar e ser mestre devido à natureza de um teclado holográfico em que você não sinta resistência ao dedo (ao contrário de uma exibição de telefone celular). 

### <a name="power-menu-from-start"></a>Menu de energia de Iniciar

Um novo menu que permite que o usuário saia, desligue e reinicie o dispositivo. Um indicador no holoLens tela inicial que mostra quando uma atualização do sistema está disponível.

#### <a name="how-to-use"></a>Como usar

1. Abra o tela inicial HoloLens usando o [gesto Iniciar](hololens2-basic-usage.md#start-gesture) ou dizendo "Go to Start".

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

Introduzido neste build do  Windows, ao selecionar Outro usuário localizado à direita do campo de entrada pin, a tela Entrar exibirá vários usuários com já conectados ao dispositivo. Isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entre usando suas Windows Hello credenciais. Um novo usuário também pode ser adicionado ao dispositivo desta página Outros usuários por meio do **botão Adicionar conta.**

Quando estiver no menu Outros usuários, o botão Outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela Entrar para esse usuário.

![Padrão da tela de login](./images/multiusers1.jpg)

<br>

![Tela de login de outros usuários](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Suporte a microfone externo USB-C

> [!IMPORTANT]
> Conectar-se **a um microfone USB não o definirá automaticamente como o dispositivo de entrada**. Ao conectar um conjunto de fones de ouvido USB-C, os usuários observarão que o áudio do fone de ouvido será redirecionado automaticamente para os fones de ouvido, mas o sistema operacional holoLens prioriza a matriz de microfone interno acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

Os usuários podem selecionar microfones externos conectados por USB-C usando o **painel Configurações** de som. Os microfones USB-C podem ser usados para chamar, gravar etc.

Abra o **aplicativo Configurações** e selecione **Som do**  >  **Sistema**.

![Configurações de som](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com **o Remote Assist,** os usuários precisarão clicar no hiperlink "Gerenciar dispositivos de som".
>
> Em seguida, use a lista para definir o microfone externo como **Padrão ou** Padrão **de Comunicações.** Escolher **Padrão** significa que o microfone externo será usado em todos os lugares.
>
> Escolher **Padrão de** Comunicações significa que o microfone externo será usado no Remote Assist e em outros aplicativos de comunicação, mas a matriz de microfones do HoloLens ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir o padrão do microfone](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E quanto ao suporte ao microfone Bluetooth?

Infelizmente, os microfones Bluetooth ainda não têm suporte no HoloLens 2 no momento.

#### <a name="troubleshooting-usb-c-microphones"></a>Solução de problemas de microfones USB-C

Esteja ciente de que alguns microfones USB-C relatam-se incorretamente como um microfone *e um* alto-falante. Esse é um problema com o microfone e não com o HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

Em **Configurações** do Som do Sistema , de definir explicitamente os alto-falantes integrados (Driver de Áudio de Recurso Análogo) como o dispositivo  ->    ->   **Padrão.**  O HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado posteriormente.

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Logon automático do Visitante para Quiosques

Esse novo recurso permite que o logon automático em contas de Visitante seja usado para modos de quiosque.

Para uma configuração não AAD, para configurar um dispositivo para logon automático de visitante:

1. Crie um pacote de provisionamento que:
    1. Define as **configurações de Runtime/AssignedAccess** para permitir contas de Visitante.
    1. Opcionalmente, registra o dispositivo no MDM **(configurações de runtime/Workplace/Enrollments)** para que ele possa ser gerenciado posteriormente.
    1. Não crie uma conta local
1. [Aplique o pacote de provisionamento](hololens-provisioning.md).

Para uma configuração do AAD, os usuários podem obter algo semelhante a isso hoje sem essa alteração. Os dispositivos ingressados no AAD configurados para o modo de quiosque podem entrar em uma conta de Visitante com um único toque de botão na tela de entrada. Depois de entrar na conta do visitante, o dispositivo não solicitará a entrada novamente até que o visitante seja explicitamente desconectado do menu iniciar ou o dispositivo seja reiniciado.

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

A partir desta versão do Windows, a experiência de quiosque fará fallback para a configuração global do quiosque (se presente) em caso de falhas durante o modo de quiosque do grupo do AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Novos URIs de configurações para visibilidade de configurações de página

No [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) adicionamos a [política Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas no aplicativo de configurações. PageVisibilityList é uma política que permite aos administradores de ti impedir que páginas específicas no aplicativo de configurações do sistema sejam visíveis ou acessíveis, ou para fazer isso para todas as páginas, exceto aquelas especificadas.

Se você visitar [visibilidade de configurações de página](settings-uri-list.md), poderá encontrar instruções para usar esse CSP e a lista de URIs disponíveis em versões anteriores.

Estamos expandindo a lista de URIs de configurações disponíveis que os administradores de ti podem gerenciar. Alguns desses URIs são para áreas disponíveis recentemente dentro do novo aplicativo de configurações. Se você estiver usando a política configurações/PageVisibilityList, examine a lista a seguir e ajuste as páginas permitidas ou bloqueadas, conforme necessário.

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

Compartilhe coisas com perto de dispositivos Windows 10, incluindo PCs e outros dispositivos de HoloLens 2. Você pode experimentá-lo em **configurações**  ->    ->  **experiências compartilhadas** do sistema para compartilhar arquivos ou URLs de um HoloLens para um PC. Para obter mais detalhes, leia mais sobre como [compartilhar coisas com dispositivos próximos no Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esse recurso pode ser gerenciado por meio de [conectividade/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Novos rastreamentos de diagnóstico do sistema operacional

Além das soluções de problemas anteriores no aplicativo de configurações, uma nova solução de problemas foi adicionada com a adição do novo aplicativo configurações para atualizações do sistema operacional. Navegue até **configurações**  ->  **Atualizar &amp; segurança**  >  **solucionar problemas**  >  **Windows Update** e selecione **Iniciar**. Isso permite que você colete rastreamentos ao reproduzir seu problema com as atualizações do sistema operacional para auxiliar na solução de problemas com sua ti ou suporte.

### <a name="delivery-optimization-preview"></a>Visualização da otimização de entrega

Com essa atualização do HoloLens, o Windows Holographic for Business permite que as configurações de otimização de entrega reduzam o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa dessa funcionalidade junto com a configuração de rede recomendada está disponível aqui: [otimização de entrega para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

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

### <a name="it-admin---update-checklist"></a>Administrador de ti – lista de verificação de atualização

Esta lista de verificação ajudará você a saber os novos itens que os recursos que estão sendo adicionados nesta atualização de recurso podem afetar suas configurações atuais de gerenciamento de dispositivo ou os novos recursos que você pode querer começar a usar.

#### <a name="updates-to-kiosk-mode"></a>Atualizações para o modo de quiosque

✔️ [**novo AUMIDs para novos aplicativos no modo de quiosque**](#use-the-new-settings-and-edge-apps-in-kiosk-modes):

Se você estava usando anteriormente o aplicativo de configurações ou o aplicativo Microsoft Edge em um quiosque, substituímos esses aplicativos por novos aplicativos que usam uma ID de aplicativo diferente. É altamente recomendável que você leia [novos AUMIDs para novos aplicativos no modo de quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) abaixo. Isso garantirá que você continue a ter o aplicativo configurações em seu quiosque ou inclua o novo aplicativo Microsoft Edge. Essas alterações podem ser feitas agora e implantadas em todos os dispositivos e permitem uma transição mais suave na atualização.

[**logon automático do visitante do ✔️ para quiosques**](#visitor-auto-logon-for-kiosks): 

Os visitantes agora podem ser conectados automaticamente a um quiosque. Esse comportamento é ativado por padrão, mas pode ser gerenciado e desabilitado.

✔️ [**envio de falha do modo de quiosque aprimorado**](#kiosk-mode-behavior-changes-for-handling-of-failures):

Se a associação de grupo do AAD do usuário conectado do AAD não for determinada com êxito, a configuração de quiosque global será usada para o menu iniciar (se houver) caso contrário, o usuário será apresentado com o menu iniciar vazio. Embora o menu iniciar vazio não seja uma configuração que você possa definir diretamente, essa nova manipulação pode ser algo para informar o departamento de suporte de se você estiver usando quiosques, pois isso pode se aplicar às suas configurações ou você talvez queira fazer novos ajustes nas suas configurações de acesso atribuídas.

#### <a name="updates-to-page-settings-visibility"></a>A visibilidade das configurações da página é atualizada

✔️ [**novos URIs de configurações para visibilidade de configurações de página**](#new-settings-uris-for-page-settings-visibility)

Se você estiver usando a [visibilidade de configurações de página](settings-uri-list.md) no momento, talvez queira fazer ajustes em seus URIs existentes que você tenha permitido ou bloqueado.

#### <a name="updates-for-your-wdac-policy"></a>Atualizações para sua política WDAC
✔️ Se você estava bloqueando o Microsoft Edge anteriormente por meio de WDAC, convém atualizar sua política WDAC. Examine o seguinte e use o código de exemplo fornecido.
#### <a name="enable-new-endpoints-for-edge"></a>Habilitar novos pontos de extremidade para o Edge
✔️ Se você tiver uma infraestrutura que envolve a configuração de pontos de extremidade de rede, como proxy ou firewall, habilite esses novos pontos de extremidade para o novo aplicativo Microsoft Edge.

#### <a name="newly-configurable-items"></a>Itens configuráveis recentemente

✔️ [Configurar o diagnóstico de fallback](#configuring-fallback-diagnostics-via-settings-app): você pode configurar se e quem pode coletar diagnósticos de fallback.

✔️[compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices): você pode desabilitar o novo recurso de compartilhamento próximo.

✔️ [definir as configurações de política para o novo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge): examine as configurações recentes disponíveis para o Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nova ferramenta de diagnóstico

✔️[novos rastreamentos de diagnóstico do sistema operacional](#new-os-diagnostic-traces): coletar logs relacionados às atualizações do sistema operacional.

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O [diagnóstico offline](hololens-diagnostic-logs.md#offline-diagnostics) também incluirá informações adicionais do dispositivo para o número de série e a versão do sistema operacional.
- Corrige um problema em relação à implantação de aplicativos de linha de negócios por meio de pacotes de provisionamento de tempo de execução.
- Corrige um problema em torno da linha de relatórios de status de instalação do aplicativo de negócios.
- Corrige um problema em relação à persistência de novos pacotes de aplicativos entre redefinições de dispositivo.
- Corrige um problema que pode levar à digitação de símbolos incorretos no Edge para clientes japoneses.
- Melhora a resiliência das atualizações do sistema operacional em relação a aplicativos pré-instalados, como o Edge. 
- Aborda uma confiabilidade de atualização que afeta a instalação do Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, versão 20H2 – atualização 2021 de maio
- Build 19041,1146

Melhorias e correções na atualização:
- Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa compilação mais recente, o Windows Holographic, a versão 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, versão 1903-maio 2021 atualização
- Build 18362,1110

Melhorias e correções na atualização:
- Essa atualização de qualidade mensal não contém nenhuma alteração notável. **Essa compilação não receberá mais atualizações de serviço mensais**. Incentivamos você a experimentar nosso Build mais recente, o Windows Holographic, a versão 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versão 20H2 – atualização de abril de 2021
- Build 19041,1144

Melhorias e correções na atualização:

- Corrige um problema em torno da linha de relatórios de status de instalação do aplicativo de negócios.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versão 1903 – atualização de abril de 2021
- Build 18362,1108

Melhorias e correções na atualização:

- Resolve um problema em que o aplicativo de configurações falha ao tentar alterar uma senha para uma conta local.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versão 20H2-atualização de março de 2021
- Build 19041,1140

Melhorias e correções na atualização:

- Os clientes que usam AdvancedPhotoCapture ou LowLagPhotoCapture para capturar fotos com o HoloLens 2 agora podem recuperar a câmera até 3 segundos após a captura da foto.
- Correção para um vazamento de memória no serviço do portal do dispositivo, o problema causou um aumento no uso da memória pelo serviço que fazia com que outros aplicativos falhassem Alocando memória.
- Corrigido um problema em que os usuários registrados na distribuição em etapas não conseguem entrar no dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versão 1903-atualização de março de 2021
- Build 18362,1102

Melhorias e correções na atualização:

- Correção para um vazamento de memória no serviço do portal do dispositivo, o problema causou um aumento no uso da memória pelo serviço que fazia com que outros aplicativos falhassem Alocando memória.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versão 20H2-atualização de fevereiro de 2021
- Build 19041,1136

Melhorias e correções na atualização:

- Corrige um problema em relação à configuração inicial do dispositivo e à loja de atualizações do aplicativo.
- Resolve um problema em relação a atualizações e voos para versões posteriores do HoloLens.
- Removeu certificados pré-instalados não utilizados do armazenamento raiz do eSIM de dispositivos do HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versão 1903 – atualização de fevereiro de 2021
- Build 18362,1098

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas versões mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versão 20H2-atualização de janeiro de 2021
- Build 19041,1134

Melhorias e correções na atualização:

- Desempenho aprimorado durante a inicialização, retomada e troca de usuário quando há muitos usuários no dispositivo.
- Adicionado suporte arm32 para o [modo de pesquisa](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versão 1903 – atualização de janeiro de 2021
- Build 18362,1091

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas versões mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versão 20H2 – atualização de dezembro de 2020
- Build 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicativos no HoloLens 2 por meio do instalador de aplicativo

Estamos **adicionando um novo recurso (instalador do aplicativo) para permitir que você instale aplicativos com mais perfeição** em seus dispositivos de HoloLens 2. O recurso estará **ativado por padrão para dispositivos não gerenciados**. Para evitar a interrupção para as empresas, o instalador **de aplicativos não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:
- MDM [registrado](hololens-enroll-mdm.md)
- Configurado com [pacote de provisionamento](hololens-provisioning.md)
- A [identidade](hololens-identity.md) do usuário é Azure AD

Agora você pode instalar aplicativos sem a necessidade de habilitar o modo de desenvolvedor ou usar o portal do dispositivo.  Basta baixar (por USB ou por borda) o pacote Appx para seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.  Como alternativa, [inicie uma instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos que você instala do Microsoft Store ou Sideload usando o recurso de implantação de aplicativo de LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiável](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo de HoloLens antes que o aplicativo possa ser implantado.

**Instruções de instalação do aplicativo.**

1.  Certifique-se de que seu dispositivo não seja considerado gerenciado
1.  Verifique se o dispositivo do seu HoloLens 2 está ligado e conectado ao seu PC
1.  Verifique se você está conectado ao dispositivo do HoloLens 2
1.  Em seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.   Depois de terminar de copiar o arquivo, você pode desconectar seu dispositivo
1.  Em seu dispositivo de HoloLens 2, abra o menu Iniciar, selecione todos os aplicativos e inicie o aplicativo explorador de arquivos.
1.  Navegue até a pasta downloads. Talvez seja necessário no painel esquerdo do aplicativo selecione primeiro este dispositivo e, em seguida, navegue até downloads.
1.  Selecione o arquivo yourapp. appxbundle.
1.  O instalador do aplicativo será iniciado. Selecione o botão instalar para instalar o aplicativo.
O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.

Você pode encontrar aplicativos de exemplo no [GitHub de exemplos do Windows universal](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar esse fluxo.

Leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o instalador do aplicativo](app-deploy-app-installer.md).  

![Instalando exemplos do MRTK por meio do instalador do aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O rastreamento manual agora mantém o controle em vários novos casos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, apenas a posição Palm continua a ser atualizada com base na disponibilidade do usuário, enquanto as outras junções são inferidas com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência de rastreamento em movimentos como pregaria, lançando, scooping e Clapping.  Também ajuda nos casos em que a mão está perto de uma superfície ou segurando um objeto.  Quando as junções de mão estão sendo inferidas, o valor de [precisão por](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) conjunto será definido como "aproximado" em vez de "alto".
- Correção de um problema em que o PIN redefinido para contas do Azure AD mostraria um erro "algo deu errado.
- Os usuários devem ver muito menos falhas no OOBE após a inicialização de ET, íris no aplicativo de configurações, novo usuário ou notificação do sistema.
- Os usuários devem ter o fuso horário correto saindo do OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versão 1903 – atualização de dezembro de 2020
- Build 18362,1088

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa mais recente Holographic do Windows, versão 20H2 – atualização de dezembro de 2020 e o novo recurso instalador do aplicativo adicionado na compilação.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versão 20H2
- Build 19041,1128

O Windows Holographic, versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para usuários do HoloLens 2 e profissionais de ti. Do posicionamento de olho automático, para o Gerenciador de certificados em configurações, para aprimorar a funcionalidade do modo de quiosque e para novos recursos de instalação do AutoPilot. Essa nova atualização permite que as equipes de ti adotem um controle mais granular para configurar e gerenciar dispositivos HoloLens e oferece aos usuários experiências holographics ainda mais diretas. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. O número de Build principal permanecerá o mesmo e Windows Update indicará uma versão mensal para a versão 2004 (Build 19041). Você pode examinar o número da sua versão em suas configurações > tela para confirmar que está no Build mais recente disponível 19041.1128 +. Para atualizar para a versão mais recente, abra o aplicativo configurações, vá para atualizar & segurança e toque em verificar se há atualizações. Para obter mais informações sobre como gerenciar atualizações do HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>O que há de novo no Windows Holographic, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte de posição de olho automático](hololens-release-notes.md#auto-eye-position-support) | Computa ativamente posições de olho sem que os usuários passem pela calibragem de controle ocular.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que novos métodos mais simples instalem e removam certificados do aplicativo configurações.     |
| [Inicialização automática do provisionamento de USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | O provisionamento de pacotes em unidades USB solicita automaticamente a página de provisionamento no OOBE.                                                         |
| [Confirmar automaticamente os pacotes de provisionamento no OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante o OOBE da página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a inicialização automática de provisionamento e a confirmação automática em conjunto. |
| [Usando o piloto automático com conexão Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o AutoPilot do dispositivo Wi-Fi sem a necessidade do adaptador Ethernet. |
| [CSP Tenantlockdown e piloto automático](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após o registro do locatário e a política ser aplicada, o dispositivo só poderá ser registrado nesse locatário sempre que o dispositivo for redefinido ou atualizado novamente. |
| [Acesso global atribuído](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para vários modos de quiosque de aplicativo que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
| [Iniciar automaticamente um aplicativo no quiosque de vários aplicativos](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define um aplicativo para ser iniciado automaticamente ao entrar em um modo de quiosque de vários aplicativos.                                                        |
| [Alterações de comportamento do modo de quiosque para tratamento de falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Falha no modo de quiosque agora tem fallback restritivo.                                                                                                |
| [Políticas de HoloLens](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para o HoloLens.     |
| [Armazenar em cache a associação de grupo do Azure AD para quiosque offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os usuários usem o cache de associação de grupo para usar o modo de quiosque offline por um número de dias definido.                                        |
| [Novas políticas de restrição de dispositivo para o HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Políticas de gerenciamento de dispositivo habilitadas recentemente habilitadas para o HoloLens 2.                                                                                |
| [Novas políticas de energia para o HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recentemente suportadas para configurações de tempo limite de energia.  |
| [Atualizar políticas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas habilitadas recentemente, permitindo o controle de atualizações.           |
| [Visibilidade da página Configurações habilitadas para o HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Política para escolher quais páginas são vistas no aplicativo configurações.             |
| [Modo de pesquisa](hololens-release-notes.md#research-mode) | Usando o modo de pesquisa no HoloLens 2. |
| [Tamanho de gravação aumentado](hololens-release-notes.md#recording-length-increased) | Gravações da MRC não são mais limitadas a 5 minutos. |
| [Melhorias e correções na atualização](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correções adicionais na atualização.   |

### <a name="auto-eye-position-support"></a>Suporte de posição de olho automático

No HoloLens 2, as posições de olho permitem o posicionamento preciso do holograma, a experiência de exibição confortável e a qualidade de exibição aprimorada. As posições de olho são calculadas internamente como parte da computação de controle de olho. No entanto, isso requer que cada usuário passe pela calibragem de controle ocular, mesmo quando a experiência pode não exigir a entrada de olhar de olho.

A **AEP (posição de olho automático)** habilita esses cenários com uma maneira sem interação de computar posições de olho para o usuário. A posição de olho automático começa a trabalhar em segundo plano automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de acompanhamento de olho anterior, a posição de olho automático começará a fornecer as posições de olho do usuário para o sistema de vídeo após um tempo de processamento de 20-30 segundos. Os dados do usuário não são persistidos no dispositivo e, portanto, esse processo é repetido quando o usuário retira o botão de volta e coloca o dispositivo novamente ou se o dispositivo é reinicializado ou sai do modo de suspensão.

Há algumas alterações de comportamento do sistema com o recurso de posição de olho automático quando um usuário não calibrado coloca no dispositivo. Nesse contexto, um usuário não calibrado refere-se a alguém que não passou pelo processo de calibragem de controle ocular no dispositivo anteriormente.

| Aplicativo ativo | Comportamento anterior | Comportamento do Windows Holographic, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo não habilitado para olhar ou shell Holographic |A caixa de diálogo solicitação de calibragem de acompanhamento ocular é exibida. | Nenhum prompt é exibido. |
| Aplicativo habilitado para olhar | A caixa de diálogo solicitação de calibragem de acompanhamento ocular é exibida. | A solicitação de calibragem de controle de olho é exibida somente quando o aplicativo acessa o fluxo de olhar de olho. |

Se o usuário fizer a transição de um aplicativo não olhar habilitado para um que acesse os dados do olhar, o prompt de calibragem será exibido. 

Todo o outro comportamento do sistema será semelhante a quando o usuário atual não tiver uma calibragem de acompanhamento de olho ativo. Por exemplo, o gesto de início de uma mão não será habilitado. Não haverá nenhuma alteração na experiência de instalação inicial para a primeira.

Para experiências que exigem dados olhars de olho ou posicionamento muito preciso do holograma, recomendamos que usuários não calibrados executem a calibragem de controle ocular. Ele pode ser acessado no prompt de calibragem de controle ocular ou ao iniciar o aplicativo de configurações no menu iniciar e selecionar a calibragem de **> do sistema > calibragem de olho > executar a calibragem**

Essas informações podem ser encontradas posteriormente com [outras informações de calibragem](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança e conformidade do dispositivo por meio do novo Gerenciador de Certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows Holographic versão 20H2, estamos adicionando um Gerenciador de Certificados no aplicativo configurações do HoloLens 2. Vá para **Configurações > Atualizar & Certificados > Segurança**. Esse recurso fornece uma maneira simples e amigável de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de Certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar se um certificado foi implantado corretamente ou para confirmar que ele foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, validar que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade pretendido e é funcional pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar um certificado específico na lista rapidamente, há opções para classificar por nome, armazenamento ou data de validade. Os usuários também podem pesquisar diretamente um certificado. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **Informações.** 

Atualmente, a instalação do certificado dá suporte a arquivos .cer e .crt. Os proprietários do dispositivo podem instalar certificados no Computador Local e no Usuário Atual;  todos os outros usuários só podem instalar no Usuário Atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário de Configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um computador.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.
1.  Navegue **até Configurações Aplicativo > Atualizar & Certificados**> Segurança e selecione Instalar um certificado.
1.  Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione **Local do Armazenamento**.
1.  Selecione **Armazenamento de Certificados**.
1.  Clique em **Instalar**.

O certificado agora deve ser instalado no dispositivo.

#### <a name="to-remove-a-certificate"></a>Para remover um certificado: 
1. Navegue **até Configurações Aplicativo > Atualização e Segurança > Certificados**.
1. Pesquise o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **Remover**
1. Selecione **Sim** quando solicitada a confirmação.

![Visualizador de certificados no aplicativo Configurações](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado](images/certificate-device-install.jpg)

Essas informações podem ser encontradas [posteriormente em uma nova página do Gerenciador de Certificados](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Provisionamento de início automático de USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante o OOBE.

Antes desta versão, os usuários tinham que iniciar a tela de provisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora os usuários podem ignorar a combinação de botões usando um Pacote de Provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagido do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB for deixada conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como observará se há outros que estão conectados.

Para obter mais informações sobre como aplicar pacotes de provisionamento durante o OOBE, visite a [documentação de provisionamento do HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Informações adicionais [sobre o provisionamento de início automático de um USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) podem ser encontradas na documentação de provisionamento do HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmar automaticamente os pacotes de provisionamento no OOBE
- Processo automatizado permitindo menos interação do usuário, quando a página Pacote de Provisionamento for exibida, ele aplicará automaticamente todos os pacotes listados.

Quando a tela principal de provisionamento aparecer, o OOBE contará 10 segundos antes de iniciar automaticamente a aplicação de todos os pacotes de provisionamento. Os usuários ainda [podem confirmar ou cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dentro de 10 segundos depois de verificar os pacotes esperados.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para interações de dispositivo reduzidas para provisionamento. 

Combinando o início automático do provisionamento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um usuário pode provisionar dispositivos HoloLens 2 automaticamente sem usar a interface do usuário do dispositivo ou até mesmo usar o dispositivo. Você pode continuar a usar a mesma unidade USB e o mesmo pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos ao mesmo tempo na mesma área. 

1. [Crie um pacote de provisionamento usando](hololens-provisioning.md) o [Designer de Configuração do Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copie o pacote para uma unidade de armazenamento USB.
1. [Flash do HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) para [19041.1361 ou build mais novo.](https://aka.ms/hololens2previewdownload) 
1. Quando [o Avançado Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) tiver concluído a exibição do dispositivo, desconectar o cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. Quando o dispositivo HoloLens 2 for inicializado no OOBE, ele detectará automaticamente o pacote de provisionamento na unidade USB e iniciará a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Seu dispositivo agora está configurado e [exibirá a tela Provisionamento bem-sucedido](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Usando o Autopilot com Wi-Fi conexão
- Remoção da necessidade de adaptadores USB-C para ethernet reduzindo as necessidades de hardware, permitindo que o Autopilot funcione em Wi-Fi dispositivos conectados.

Agora, durante o OOBE, depois de conectar o HoloLens 2 ao Wi-Fi, o OOBE verificará se há um perfil do Autopilot para o dispositivo. Se for encontrado, ele será usado para concluir o restante do fluxo de registro e junção do AAD. Em outras palavras, o uso de ethernet para USB-C ou Wi-Fi adaptador usb-C não é mais um requisito, no entanto, eles continuam a funcionar se fornecidos no início do OOBE. Saiba mais sobre [o Autopilot para dispositivos HoloLens 2.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP e Autopilot
- Mantém os dispositivos no locatário da organização ao bloqueá-los para o locatário, mesmo por meio da redefinição ou reflash do dispositivo. Com mais segurança, não permitir a criação de conta no por meio do provisionamento. 

Os dispositivos HoloLens 2 agora são compatíveis com o CSP TenantLockdown a partir [do Windows Holographic versão 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) O CSP permite que o HoloLens 2 seja vinculado ao registro de MDM usando apenas o Autopilot. Depois que o nó RequireNetworkInOOBE do TenantLockdown do CSP for definido como o valor true ou false (inicialmente definido) no HoloLens 2, esse valor permanecerá no dispositivo, apesar da nova piscação, das atualizações do sistema operacional etc. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como true no HoloLens 2, o OOBE aguardará indefinidamente que o perfil do Autopilot seja baixado e aplicado com êxito, após a conectividade de rede. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como true no HoloLens 2, as seguintes operações não serão permitidos no OOBE: 
- Criando um usuário local usando o provisionamento de runtime 
- Executando a operação de junção do Azure AD por meio do provisionamento de runtime 
- Selecionando quem possui o dispositivo na experiência OOBE 

#### <a name="how-to-set-this-using-intune"></a>Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique true para o nó RequireNetworkInOOBE, conforme mostrado abaixo.
O valor de OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Definindo bloqueio de tennant via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. Tornar o membro do dispositivo HoloLens 2 do grupo criado na etapa anterior e disparar a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com êxito. Depois que essa configuração de dispositivo for aplicada com êxito no dispositivo HoloLens 2, os efeitos de TenantLockdown estarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Como desajustar RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune? 
1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração do dispositivo criada acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em URI de OMA personalizado e especifique false para RequireNetworkInOOBE, conforme mostrado abaixo. O valor de OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração RequireNetworkInOOBE como false por meio do URI do OMA no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. Tornar o membro do dispositivo HoloLens 2 do grupo criado na etapa anterior e disparar a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com êxito. Depois que essa configuração de dispositivo for aplicada com êxito no dispositivo HoloLens 2, os efeitos de TenantLockdown estarão inativos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>O que acontecerá durante o OOBE, se o perfil do Autopilot não for atribuído em um HoloLens depois que TenantLockdown for definido como true? 
O OOBE aguardará indefinidamente o download do perfil do Autopilot e a caixa de diálogo a seguir será apresentada. Para remover os efeitos de TenantLockdown, o dispositivo deve ser inscrito com seu locatário original primeiro usando apenas o Autopilot e RequireNetworkInOOBE deve ser desaixado conforme descrito na etapa anterior antes que as restrições introduzidas pelo TenantLockdown CSP sejam removidas. 

![Exibição no dispositivo para quando a política é imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

Essas informações agora podem ser encontradas junto com o restante do Autopilot em [Tenantlockdown CSP e Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Acesso Atribuído Global – Modo de Quiosque
- Gerenciamento de identidades reduzido para quiosque, habilitando o novo método de quiosque que aplica o modo de quiosque no nível do sistema.

Esse novo recurso permite que um administrador de ti configure um dispositivo do HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem nenhuma afinidade com nenhuma identidade no sistema e se aplica a todos que se conectam ao dispositivo. Leia sobre esse novo recurso em detalhes no [quiosque de acesso global atribuído do HoloLens](hololens-global-assigned-access-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicialização automática de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada com a inicialização automática do aplicativo, aumentando ainda mais a interface do usuário e as seleções de aplicativo escolhidas para experiências de modo de quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e somente um aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração de acesso atribuída. 

O aplicativo é iniciado automaticamente quando o usuário entra. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações de comportamento do modo de quiosque para tratamento de falhas
- Modo de quiosque mais seguro ao eliminar aplicativos disponíveis em falhas do modo de quiosque. 

Antes de encontrar falhas na aplicação do modo de quiosque, o HoloLens costumava mostrar todos os aplicativos no menu iniciar. Agora no Windows Holographic versão 20H2 no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, como abaixo: 

![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Políticas de HoloLens
- Opções de gerenciamento de dispositivo especificamente para o HoloLens criado para gerenciar o dispositivo. 

Novas políticas de realidade misturada foram criadas para dispositivos do HoloLens 2 no Windows Holographic versão 20H2. As novas configurações controláveis incluem: definir o brilho, definir o volume, desabilitar a gravação de áudio em capturas de realidade misturada, definir quando o diagnóstico pode ser coletado e o cache de associação do grupo do AAD.  

| Nova política de HoloLens                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados e, portanto, pressioná-lo não altera o brilho.       | 1 Sim, 0 não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que os botões de volume sejam desabilitados e, portanto, pressionados não altera o volume.               | 1 Sim, 0 não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | Desabilita o microfone, portanto, não é possível gravar áudio no HoloLens 2.                      | 1 Sim, 0 não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os logs de diagnóstico podem ser coletados.                               | 0 desabilitado, 1 habilitado para proprietários de dispositivo, 2 habilitados para todos (padrão) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla quantos dias o cache de associação de grupo do Azure AD é usado para o quiosque de destino de grupos do Azure AD. | Veja abaixo.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Armazenar em cache a associação de grupo do Azure AD para quiosque offline
- Os quiosques offline habilitados serão usados com grupos do AAD por até 60 dias.

Essa política controla por quantos dias o cache de associação de grupo do Azure AD pode ser usado para configurações de acesso atribuídas direcionando grupos do Azure AD para o usuário conectado. Quando esse valor de política for definido como valor maior que 0 somente, o cache será usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays URI value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 dias  
Máx.-60 dias 

Etapas para usar esta política corretamente: 
1. Crie um perfil de configuração de dispositivo para o quiosque de destino de grupos do Azure AD e atribua-o a dispositivos do HoloLens. 
1. Crie uma configuração de dispositivo personalizada de OMA URI que defina esse valor de política para o número de dias desejado (> 0) e atribua-o aos dispositivos do HoloLens. 
    1. O valor do URI deve ser inserido na caixa de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre min/max permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário 1 do Azure AD entre quando a Internet estiver disponível, quando o usuário entrar e a associação de grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário 1 do Azure AD pode colocar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD. o ponto-chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que eles são membros do grupo do Azure AD ao qual a configuração de quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para um usuário do Azure AD passará por um comportamento de falha mencionado em ambientes "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Novas políticas de restrição de dispositivo para o HoloLens 2
- Permite que os usuários gerenciem políticas específicas de gerenciamento de dispositivos, como bloquear a adição ou remoção de pacotes de provisionamento.

Políticas habilitadas recentemente que permitem mais opções de gerenciamento de dispositivos do HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Essas duas novas políticas para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Em relação ao [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp), o HoloLens dará suporte apenas à configuração./Vendor/MSFT/RemoteLock/Lock. Não há suporte para as configurações que lidam com PIN como redefinição e recuperação.

### <a name="new-power-policies-for-hololens-2"></a>Novas políticas de energia para o HoloLens 2
- Mais opções para quando o HoloLens é suspenso ou trava por meio de políticas de energia. 

Essas políticas adicionadas recentemente permitem que os administradores controlem os Estados de energia, como tempo limite de ociosidade. Para ler mais sobre cada política individual, clique no link para essa política.

|     Link de documentação da política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas políticas para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Para uma experiência consistente no HoloLens 2, certifique-se de que os valores para DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery sejam definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Consulte os [temporizadores ociosos de exibição, suspensão e hibernação](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre o modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Políticas de atualização habilitadas recentemente para o HoloLens
- Mais opções para quando as atualizações são instaladas ou a desabilitação do botão Pausar atualizações para garantir as atualizações.

Essas políticas de atualização agora estão habilitadas em dispositivos do HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Atualizar/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Os detalhes completos sobre essas políticas de atualização e como usá-las para dispositivos do HoloLens podem ser lidos aqui em [gerenciar atualizações do hololens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilidade da página Configurações habilitadas para o HoloLens 2
- Controle de interface do usuário aumentado no aplicativo de configurações, que pode ser confundido para mostrar uma seleção limitada de páginas.

Agora habilitamos uma política que permite que os administradores de ti impeçam que páginas específicas no aplicativo Configurações do sistema sejam visíveis ou acessíveis, ou que façam isso para todas as páginas, exceto aquelas especificadas. Para saber como personalizar totalmente esse recurso, clique no link abaixo.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais configurações de página você pode personalizar no HoloLens 2, visite nossa [página URIs de configurações](settings-uri-list.md). 
 
![Captura de tela de horas ativas sendo modificadas no aplicativo de configurações](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de pesquisa
No Modo de Pesquisa, o HoloLens 2 se torna uma ferramenta de pesquisa visual computacional. Em comparação com as edições anteriores, o Modo de Pesquisa para HoloLens 2 tem as seguintes vantagens:
-   Além dos sensores expostos no Modo de Pesquisa do HoloLens (1ª geração), agora fornecemos acesso ao sensor de IMU, incluindo um acelerômetro, um giroscope e um hologramômetro.
-   O HoloLens 2 fornece novos recursos que podem ser usados junto com o Modo de Pesquisa. Especificamente, acesso a APIs articuladas de acompanhamento e acompanhamento ocular que podem fornecer um conjunto mais rico de experimentos.

Os pesquisadores agora têm a opção de habilenciar o Modo de Pesquisa em seus dispositivos HoloLens para acessar todos esses fluxos de sensores de imagem bruta voltados para o externo. O Modo de Pesquisa para HoloLens 2 também fornece acesso ao acelerômetro, ao giroscope e às leituras de holograma. Para proteger a privacidade dos usuários, as imagens brutas da câmera de acompanhamento ocular não estão disponíveis por meio do Modo de Pesquisa, mas a direção do olhar está disponível por meio de APIs existentes.

Confira a [documentação do Modo de Pesquisa](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

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
- Foi resolvido um problema que impedia que um dispositivo HoloLens aparece no Explorador de Arquivos por MTP (Protocolo de Transferência de Mídia) quando o dispositivo é configurada como um [quiosque](hololens-kiosk.md)de aplicativo único. Observe que o MTP (e a conexão USB em geral) ainda podem ser desabilitados usando a [política AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Corrigido um problema em que os ícones no menu Iniciar eram dimensionados corretamente no modo quiosque.
- Corrigido um problema devido ao cache HTTP interferir no modo de quiosque direcionado para grupos do Azure AD.
- Corrigido um problema em que os usuários não conseguiram usar o botão Emparelhar depois de habilitar o modo desenvolvedor com pacotes de provisionamento, a menos que eles desabilita e reabilitar o modo de Desenvolvedor.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versão 1903 – Atualização de novembro de 2020
- Build 18362.1085

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nosso build de versão de recurso mais recente do Windows Holographic, versão 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versão 2004 – Atualização de outubro de 2020
- Build 19041.1124
 
Melhorias e correções na atualização:

- Remoção de uma verificação desnecessária que causou a falha do sistema de runtime.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versão 1903 – Atualização de outubro de 2020
- Build 18362.1081

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossos builds mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versão 2004 – Atualização de setembro de 2020
- Build 19041.1117

Melhorias e correções na atualização:

- Resolve um problema que impedia Visual Studio depurar um aplicativo quando SupportsMultipleInstances="true" está presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy NCSI para resolver a falha na detecção da Internet por proxy de rede. O NCSI pode usar proxy de computador e proxy por perfil para detecção de conectividade com a Internet. O proxy por usuário terá suporte do NCSI na versão futura.
- Na maioria Windows Mixed Reality dispositivos, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ser holograma aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores forma.
- Maior robustez de acompanhamento de mão que resultará em menos perdas de acompanhamento em cenários específicos.
- Esta versão contém uma correção para melhorar a qualidade do timestamp de áudio que pode ter contribuído para problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versão 1903 – Atualização de setembro de 2020
- Build 18362.1079

Melhorias e correções na atualização:

- Na maioria Windows Mixed Reality dispositivos, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ser holograma aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores forma.
- Maior robustez de acompanhamento de mão que resultará em menos perdas de acompanhamento em cenários específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versão 2004 – Atualização de agosto de 2020
- Build 19041.1113

Melhorias e correções na atualização:

- O aplicativo de configurações não seguirá mais o usuário em Experiências de Registro de Íris ou Calibragem de Acompanhamento Ocular.
- Corrigido um bug em que a aplicação de um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como conectar-se a uma rede) não executaria as outras ações após a reinicialização do dispositivo devido à renomeação.
- Esquema de cores modificado dos fluxos iniciais de instalação do dispositivo para melhorar a qualidade visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versão 1903 – Atualização de agosto de 2020
- Build 18362.1074

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossos builds mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versão 2004 – Atualização de julho de 2020
- Build 19041.1109

Melhorias e correções na atualização:

- Os desenvolvedores agora podem escolher entre habilenciar ou desabilitar a Portal de Dispositivos exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Alteração do brilho da caixa de entrada padrão para 100%.
- Foi resolvido um problema sobre o encaminhamento HTTPS para o Portal de Dispositivos do Windows no HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versão 1903 – Atualização de julho de 2020
- Build 18362.1071

Melhorias e correções na atualização:

- Corrigido um problema que poderia fazer com que os hologramas desaparecessem em aplicativos unity ao perder ou recuperar o controle.
- Corrigido um problema que causava a falha de aplicativos exclusivos do HoloLens no shell ao usar o Emulador do HoloLens com aceleração de hardware em determinados dispositivos.
- Foi resolvido um problema referente ao encaminhamento HTTPS para o Portal de Dispositivos do Windows no HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versão 2004 – Atualização de junho de 2020
- Build 19041.1106

Melhorias e correções na atualização:

- Os gravadores personalizados do MRC agora terão novos valores padrão para determinadas propriedades, caso não sejam especificados.
  - No efeito *de vídeo do MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (headset imersivo))
  - No efeito *de áudio mrc*:
    - LoopbackGain (o valor atual de "Ganho de Áudio do Aplicativo" na página Captura de Realidade Misturada no Portal de Dispositivos do Windows)
    - MicrophoneGain (o valor atual de "Ganho de Áudio de Microfone" na página Captura de Realidade Misturada na Portal de Dispositivos do Windows)
- Correção de um bug para melhorar a qualidade do áudio em cenários de captura de realidade misturada. Especificamente, essa correção deve eliminar falhas de áudio na gravação quando **o** menu Iniciar for exibido.
- Melhor estabilidade do holograma em vídeos gravados.
- Resolvido um problema em que a captura de realidade misturada não podia gravar vídeo depois que o dispositivo era deixado em estado de espera por vários dias.
- A API HolographicSpace.UserPresence geralmente está desabilitada para aplicativos unity. Esse comportamento evita um problema que fez alguns aplicativos pausarem quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" tenha sido habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity e 2019.3.4 e posteriores.
- Quando você acessa Portal de Dispositivos uma conexão Wi-Fi, um navegador da Web pode impedir o acesso a devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo se o certificado do dispositivo fosse confiável anteriormente. Nesse caso, você não pode avançar para Portal de Dispositivos, pois não há nenhuma opção para ignorar avisos de segurança. Essa atualização resolveu o problema. Se o certificado do dispositivo tiver sido baixado anteriormente e for confiável em um computador para remover avisos de segurança do navegador e o erro SSL ocorrer, o novo certificado precisará ser baixado e confiável para resolver os avisos de segurança do navegador.
- Habilitada a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
- Adicionada uma configuração em **configurações** de  >    >  **hologramas** do sistema que permite que os usuários removam automaticamente todos os hologramas de uma realidade misturada em casa quando o dispositivo é desligado.
- Corrigido um problema que fazia com que os aplicativos do HoloLens alterassem seu formato de pixel para renderizar o preto no emulador do HoloLens.
- Correção de um bug que causou uma falha durante o logon da íris.
- Correção de um problema sobre downloads de armazenamento repetidos para aplicativos já atuais.
- Correção de um bug para impedir que aplicativos de imersão Abram o Microsoft Edge repetidamente.
- Foi corrigido um problema com as inicializações do aplicativo fotos na inicialização inicial após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versão 1903 – atualização de junho de 2020
- Build 18362,1064

Melhorias e correções na atualização:

- Os gravadores da MRC personalizados têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (Headset de imersão))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "obter o áudio do aplicativo" na página de captura da realidade misturada no portal de dispositivos do Windows)
    - MicrophoneGain (o valor atual de "lucro de áudio do MIC" na página de captura da realidade misturada no portal de dispositivos do Windows)
- A API HolographicSpace. userpresence geralmente é desabilitada para aplicativos do Unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo que a configuração seja executada em segundo plano esteja habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity, e 2019.3.4 e posterior.
- Corrigido um problema que fazia com que os aplicativos do HoloLens alterassem seu formato de pixel para renderizar o preto no emulador do HoloLens.
- Corrigido um problema sobre as inicializações do aplicativo fotos na inicialização inicial após a atualização da versão 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versão 2004  
- Build-19041,1103

A principal atualização de software de maio de 2020 para o HoloLens 2, o *Windows Holographic, versão 2004* inclui uma série de novos recursos empolgantes, como suporte para o Windows AutoPilot, modo escuro do aplicativo, suporte a Ethernet USB para hotspots 5g/LTE e muito mais. Para atualizar para a versão mais recente, abra o aplicativo **configurações**   , vá para  **Atualizar & segurança** e selecione o botão  **verificar atualizações**   . 

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurar e configurar diretamente novos dispositivos para produção usando o Windows AutoPilot                 |
|       Suporte a FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar diretamente um pacote de provisionamento de uma unidade USB ao seu HoloLens                              |
|       Status de instalação do aplicativo                 |          Verifique se o status de instalação no aplicativo de configurações para aplicativos foi enviado por push para o HoloLens 2 por meio do MDM               |
|       Provedores de serviços de configuração (CSPs)   |          Novos provedores de serviços de configuração adicionados para aprimorar os recursos de controle de administrador                 |
|       Suporte a 5G/LTE USB                       |          O recurso Ethernet USB expandido habilita o suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que dão suporte aos modos escuro e claro, melhorando a experiência de exibição        |
|       Comandos de voz                             |          Suporte para comandos adicionais de voz do sistema para controlar as mãos gratuitas do HoloLens                           |
|       Aprimoramentos de acompanhamento de mão                 |          Melhorias de acompanhamento de mão tornam os botões e as interações de Slate 2D mais precisos                        |
|       Melhorias e correções de qualidade                 |          Vários aprimoramentos de desempenho e confiabilidade do sistema em toda a plataforma                            |

### <a name="support-for-windows-autopilot"></a>Suporte para Windows AutoPilot

O piloto automático do Windows para o HoloLens 2 permite que o canal de vendas do dispositivo Registre previamente o HoloLens em seu locatário do Intune. Quando os dispositivos chegam, eles estão prontos para serem implantados automaticamente como dispositivos compartilhados em seu locatário. Para tirar proveito da autoimplantação, o dispositivo deve se conectar a uma rede durante a primeira tela na instalação usando um USB-C-to-Ethernet.

Depois que um usuário inicia o processo de autoimplantação do AutoPilot, o processo conclui as seguintes etapas:

1. Ingresse o dispositivo no Azure Active Directory (Azure AD).
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe as políticas, os certificados e os perfis de rede direcionados ao dispositivo.
1. Provisionar o dispositivo.
1. Apresente a tela de entrada ao usuário.

Saiba mais no [Guia de avaliação do piloto automático do Windows para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Entre em contato com seu gerente de conta para participar da versão prévia do piloto automático agora. Os dispositivos prontos para o piloto automático começarão a enviar em breve.*

### <a name="fido2-security-key-support"></a>Suporte à chave de segurança do FIDO2

Alguns usuários compartilham um dispositivo HoloLens com outras pessoas em um ambiente corporativo ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. O Fast Identity online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre diretamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação com base em padrões "inphishável" que pode vir em qualquer fator forma. FIDO é um padrão aberto para autenticação com senha. Ele permite que usuários e organizações entrem em seus recursos sem um nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma embutida em um dispositivo.

Para começar, consulte [habilitar a entrada de chave de segurança sem senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Registro de MDM aprimorado por meio do pacote de provisionamento

Os pacotes de provisionamento permitem definir a configuração do HoloLens por meio de um arquivo de configuração, em vez de por meio da experiência inicial do HoloLens. Anteriormente, os pacotes de provisionamento tinham que ser copiados para a memória interna do HoloLens. Agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizar em vários dispositivos HoloLens e você pode provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também dão suporte a um campo para se registrar no gerenciamento de dispositivos, portanto, não há nenhuma configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do Windows Configuration designer da Windows Store no seu PC.
1. Selecione **provisionar dispositivos hololens**  >  **provisionar dispositivos do hololens 2**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C em qualquer HoloLens atualizado. Em seguida, pressione os botões de  +  **energia** volume para baixo para aplicar seu pacote de provisionamento.

### <a name="line-of-business-application-install-status"></a>Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento do aplicativo MDM para aplicativos de linha de negócios são essenciais para o HoloLens. Administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **configurações**  >  **contas**  >  **acesso corporativo ou de estudante**  >  **clique nas informações da sua conta**  >  .

### <a name="additional-csps-and-policies"></a>CSPs e políticas adicionais

Um [provedor de serviços de configuração (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou excluir definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores têm sobre dispositivos HoloLens implantados. Para obter a lista de CSPs com suporte do HoloLens, consulte [CSP do NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novo nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa Configure políticas em dispositivos Windows. Nesta versão, adicionamos novas políticas para o HoloLens, que estão listadas aqui. Para saber mais, confira [CSPs de política com suporte do HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

O provedor de serviços de configuração do NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, confira [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Suporte de Ethernet USB expandido para dispositivos 5G/LTE de compartilhamento de Internet

Foi adicionado suporte para habilitar determinados dispositivos de banda larga móvel, como telefones 5G/LTE e hotspots Wi-Fi, quando eles estão vinculados ao HoloLens 2 via USB. Esses dispositivos agora são exibidos nas **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos de banda larga móvel que exigem um driver externo.) Essa funcionalidade permite conexões de alta largura de banda quando Wi-Fi não está disponível e Wi-Fi compartilhamento de Internet não é um desempenho suficiente. Para saber mais sobre os dispositivos USB com suporte, confira [conectar-se a dispositivos Bluetooth e USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Aprimoramentos de acompanhamento de mão

Esta versão inclui vários aprimoramentos de acompanhamento:

- **Apontando para a estabilidade:** O sistema agora se resiste à curva do dedo do índice quando ele fica obstruído pelo Palm. Essa alteração melhora a exatidão ao enviar botões, digitar, rolar conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Melhoramos a detecção do gesto de toque do ar. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta suas mãos em seus lados.
- **Confiabilidade do comutador do usuário:** O sistema agora é mais rápido e mais confiável na atualização do tamanho da mão quando você compartilha um dispositivo.
- **Roubo reduzido:** Melhoramos o manuseio de casos em que há mais de duas mãos na exibição dos sensores. Se várias pessoas estiverem trabalhando juntas, agora há uma chance muito menor de que a mão controlada vai "saltar" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Corrigido um problema que fazia com que o rastreamento à mão deixasse de funcionar quando o dispositivo está sob carga alta.

### <a name="dark-mode"></a>Modo escuro

Muitos aplicativos do Windows agora dão suporte a modos escuros e leves. Os usuários do HoloLens 2 podem escolher o modo padrão para aplicativos que dão suporte a ambos. Após a atualização, o modo de aplicativo padrão é "escuro", mas você pode alterar facilmente essa configuração: Navegue até **configurações**  >  cores do **sistema**  >    >  **escolha seu modo de aplicativo padrão**. 

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

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, consulte [usar sua voz para operar o HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulte também [idiomas com suporte para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Atualizações da Cortana

O aplicativo atualizado integra-se com o Microsoft 365 para ajudá-lo a fazer mais em seus dispositivos (atualmente em US-English apenas). No HoloLens 2, a Cortana não dá mais suporte a determinados comandos específicos do dispositivo, como ajustar o volume ou reiniciar. Agora, há suporte para essas opções nos novos comandos de voz do sistema. Saiba mais sobre o novo aplicativo Cortana em nosso [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibragem de vídeo ativo. Esse recurso melhora a estabilidade e o alinhamento de hologramas. Agora, eles permanecem em vigor quando você move sua cabeça do lado para o outro.
- Corrigido um bug em que Wi-Fi streaming para o HoloLens foi interrompido periodicamente. Se um aplicativo indicar que ele precisa de streaming de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correção de um dispositivo suspenso que ocorreu durante o streaming no modo de pesquisa.
- Corrigido um bug em que, em alguns casos, o usuário certo não seria exibido na tela de entrada ao retomar uma sessão.
- Corrigido um problema em que os usuários não podiam exportar logs do MDM por meio de **configurações**.
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
- Um problema requer que você inicie o aplicativo Cortana depois de iniciar o dispositivo para usar a ativação de voz "Ei Cortana". Se você atualizou a partir de uma compilação 18362, também poderá ver um bloco do segundo aplicativo para a versão anterior do aplicativo Cortana que não funciona mais no **início**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versão 1903-maio 2020 atualização 
- Build 18362,1061

Essa atualização de qualidade mensal não contém nenhuma alteração notável porque a equipe estava trabalhando no Windows Holographic versão 2004 pode ser atualizada, conforme descrito anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versão 1903 – atualização de abril de 2020
- Build 18362,1059

**Modo escuro para aplicativos com suporte** 

Muitos aplicativos do Windows dão suporte ao modo escuro e leve. Os clientes do HoloLens 2 agora podem escolher o modo padrão para aplicativos que dão suporte a esquemas de cores. Com base nos comentários dos clientes, definimos o modo de aplicativo padrão como "escuro", mas você pode alterar facilmente essa configuração a qualquer momento: Navegue até **configurações > sistema > cores** para localizar **"escolher o modo de aplicativo padrão".**

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
- Build 18362.1056

Melhorias e correções na atualização:

- Melhor estabilidade do holograma na captura de realidade misturada quando o *algoritmo HolographicDepthReprojectionMethod AutoPlanar* é usado.
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

- Estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador do HoloLens 2.

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
- Qualidade visual aprimorada de objetos colocados longe nas versões mais recentes do Unity e do MRTK (Kit de Ferramentas de Realidade Misturada).
- Corrigidos problemas com aplicativos holográficos travando em um estado pausado na inicialização até que o menu Iniciar fosse aberto e fechado.
- Correções e melhorias de conformidade do runtime do OpenXR para o HoloLens 2 e o emulador.
