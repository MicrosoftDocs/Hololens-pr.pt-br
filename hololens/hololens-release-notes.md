---
title: Notas sobre a versão do HoloLens 2
description: Mantenha-se atualizado com todas as atualizações em cada nova HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/8/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f27a469e76df1ccf29a2823b48f3640bdf414050
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032022"
---
# <a name="hololens-2-release-notes"></a>Notas sobre a versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus HoloLens, continuamos a lançar atualizações de recursos, bugs e segurança. Nesta página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização HoloLens 2 mais recente, você pode verificar se há atualizações e atualizar [manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a FFU (Atualização flash completa) para piscar seu dispositivo por meio do [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). O [download](https://aka.ms/hololens2download) é mantido atualizado e fornece o build mais recente disponível.

> [!NOTE]
> O comunicado recente do Windows 11 se concentrou na versão do Windows para computadores. Recentemente, lançamos uma [grande atualização do sistema operacional](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) para o HoloLens 2 em maio de 2021 e estamos trabalhando em uma próxima versão com base nos comentários dos clientes para o segundo semestre.

> [!IMPORTANT]
> Devido a um problema conhecido agora resolvido em nosso [build do 21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)que estava afetando os usuários do Remote Assist, pausamos temporalmente a oferta de atualizações do Windows Holographic, versão 21H1. Também mudamos o build padrão do ARC (Advanced Recovery Companion) para o Windows Holographic, versão 20H2 – Atualização de junho de [2021.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) O build arc agora retomará direcionando o build 21H1.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, versão 21H1 – Atualização de agosto de 2021

- Build 20348.1014

Melhorias e correções na atualização:

- Corrigido um problema que impedia os controladores Xbox de trabalharem em aplicativos imersivos com suporte ao controlador.
- Diagnóstico aprimorado para falhas de atualização do dispositivo.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de agosto de 2021

- Build 19041.1161

Melhorias e correções na atualização:

- Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nosso build mais recente, Windows Holographic, versão 21H1.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, versão 21H1 – Atualização de julho de 2021

- Build 20348.1010

Melhorias e correções na atualização:

- Portal de Dispositivos métodos aprimorados para notificar o cliente quando Explorador de Arquivos problemas ao abrir arquivos bloqueados.
- O upload, o download, a renomear e a exclusão de arquivos agora são corrigidos ao usar https em todos os navegadores com suporte.
- Correção do problema em que Wi-Fi proxy não pode ser salvo quando a interface do usuário de propriedades do Wi-Fi é lançada do Configurações **-> Network & Internet -> Status -> Properties**.
- Foi resolvido um problema em torno da remoção de certificados eSIM em atualizações do sistema operacional. Essa correção garante que os certificados eSIM e os componentes relacionados sejam removidos ao atualizar para a versão 21H1.
- Corrigido um problema que afeta os aplicativos pré-instalados nas redefinições do sistema operacional.
- Desempenho de carregamento da bateria ajustado para aumentar o runtime ao carregar com o carregamento de CPU aumentado. Ao carregar HoloLens 2 dispositivos, se for detectado que o dispositivo está em execução quente, a bateria interna será carregada mais lentamente para reduzir o calor. A recompensa positiva é que um dispositivo tem menos probabilidade de ser desligado devido a problemas de calor, com o impacto é que o dispositivo é executado por mais tempo. Se o dispositivo estiver em execução eso, a taxa de cobrança não será afetada.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, versão 20H2 – Atualização de julho de 2021

- Build 19041.1157

Melhorias e correções na atualização:

- Portal de Dispositivos métodos aprimorados para notificar o cliente quando Explorador de Arquivos problemas ao abrir arquivos bloqueados.
- O upload, o download, a renomear e a exclusão de arquivos agora são corrigidos ao usar https em todos os navegadores com suporte.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, versão 21H1 – Atualização de junho de 2021

- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive para upload de roll de câmera de trabalho ou de estudante

Adicionamos um novo recurso ao aplicativo HoloLens 2 Configurações, que permite que os clientes carreguem automaticamente fotos e vídeos de realidade misturada da pasta Imagens > Camera Roll do dispositivo para a pasta OneDrive correspondente para trabalho ou escola. Esse recurso aborda uma lacuna de recursos dentro do aplicativo [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) no HoloLens 2, que dá suporte apenas ao upload automático do Roll da Câmera para o sistema conta Microsoft pessoal do cliente (e não sua conta de trabalho ou de estudante).

**Como funciona**

- Visite **Configurações > sistema > Câmera de Realidade Misturada** para habilitar o "Upload da câmera".
- Ao definir esse  recurso para a posição Ativado, todas as fotos ou vídeos de realidade misturada capturados em seu dispositivo serão automaticamente na fila para upload para a pasta Imagens > Camera Roll do seu OneDrive para a conta de trabalho ou de estudante.
    >[!NOTE]
    >Fotos e vídeos capturados antes  da habilitação desse recurso não serão na fila para upload e ainda precisarão ser carregados manualmente.
- Uma mensagem de status na página Configurações exibirá o número de arquivos pendentes de upload (ou lerá "OneDrive está atualizado" quando todos os arquivos pendentes foram carregados).
- Se você estiver preocupado com a largura de banda ou quiser "pausar" o upload por qualquer motivo, poderá alternar o recurso para a **posição** Desligado. Desabilitar temporariamente o recurso garante que a fila de upload continuará aumentando conforme você adicionar novos arquivos à pasta Roll da Câmera, mas os arquivos não serão carregados até que você habilita o recurso.
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

Essa atualização contém recursos para dois públicos-alvo; recursos que podem ser usados por qualquer pessoa em um dispositivo pelo Usuário Final e novas opções de gerenciamento de dispositivo que podem ser configuradas por administradores de IT. A tabela a seguir especifica os recursos relevantes para cada público-alvo. Se você for um Administrador de TI, dê uma olhada em nosso Administrador [de TI – Atualizar Lista de Verificação.](#it-admin---update-checklist)
>[!IMPORTANT]
>Para atualizar para esse build, HoloLens 2 dispositivos devem estar executando a atualização de fevereiro de 2021 (build 19041.1136) ou mais recente. Se você não estiver vendo essa atualização de recurso disponível, atualize seu dispositivo primeiro e tente novamente.

>[!NOTE]
>Atualmente, Microsoft HoloLens 2 dá suporte a atualizações mensais de manutenção (correções de bugs e segurança) para as seguintes versões:
>- Windows Holographic, versão 20H2 (Build 19041.1128 +)
>- Windows Holographic, versão 2004 (Build 19041.1103 +)
>- Windows Holographic, versão 1903 (Build 18362 +)
>
> com a introdução do Windows Holographic versão 21H1, **estamos descontinuando as atualizações de manutenção mensal para Windows Holographic versão 1903**. Isso nos permite focar em versões mais recentes e continuar a fornecer melhorias valiosas.


| Nome do recurso                                              | Descrição breve                                                                      | Público-alvo | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Novo Microsoft Edge](#introducing-the-new-microsoft-edge)  | o novo Microsoft Edge baseado em Chromium agora está disponível para o HoloLens 2. | Usuário Final | 
[WebXR e Visualizador 360](#webxr-and-360-viewer) | Experimente experiências de imersão da Web e reprodução de vídeo 360. | Usuário Final | 
[Novo aplicativo Configurações](#new-settings-app) | o aplicativo Configurações herdado está sendo substituído por uma versão atualizada com novos recursos e configurações. | Usuário Final |
[Exibir calibragem de cor](#display-color-calibration) | Selecione um perfil de cor alternativo para a exibição do HoloLens 2. | Usuário Final |
[Seletor de aplicativo padrão](#default-app-picker) | Escolha qual aplicativo deve ser iniciado para cada arquivo ou tipo de link. | Usuário Final |
[Controle de volume por aplicativo](#per-app-volume-control) | Controlar o volume de nível do aplicativo independentemente do volume do sistema. | Usuário Final |
[Instalar aplicativos Web](#install-web-apps) | instale os aplicativos web no HoloLens 2, como Microsoft Office, com o novo navegador Microsoft Edge. | Usuário Final |
[Deslizar para tipo](#swipe-to-type) | Use a ponta do dedo para "deslizar" palavras no teclado Holographic. | Usuário Final |
[Menu de energia do Início](#power-menu-from-start) | no Menu iniciar, reinicie e desligue HoloLens dispositivo. | Usuário Final |
[Vários usuários listados na tela de entrada](#multiple-users-listed-on-sign-in-screen) | Exibe várias contas de usuário na tela de entrada. | Usuário Final |
[Suporte para microfone externo USB-C](#usb-c-external-microphone-support) | Use microfones USB-C para aplicativos e/ou assistência remota. | Usuário Final |
[Logon automático do visitante para quiosques](#visitor-auto-logon-for-kiosks) | Permite que o logon automático em contas de visitante seja usado para modos de quiosque. | Administrador de TI |
[Novo AUMIDs para novos aplicativos no modo de quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs para novos aplicativos de Configurações e borda. | Administrador de TI |
[Falha na entrega do modo de quiosque aprimorado](#kiosk-mode-behavior-changes-for-handling-of-failures) | O modo de quiosque procura acesso global atribuído antes do menu iniciar vazio. | Administrador de TI |
[novo SettingsURIs para a visibilidade da Configurações de página](#new-settings-uris-for-page-settings-visibility) | 20 + novo SettingsURIs para a política de/PageVisibilityList de Configurações. | Administrador de TI |
[Configurar o diagnóstico de fallback](#configuring-fallback-diagnostics-via-settings-app) | definindo o comportamento de diagnóstico de Fallback no aplicativo Configurações. | Administrador de TI |
[Compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices) | compartilhar arquivos ou URLs de um HoloLens para um PC. | Tudo |
[Novos rastreamentos de diagnóstico do sistema operacional](#new-os-diagnostic-traces) | nova solução de problemas no Configurações para atualizações do sistema operacional. | Administrador de TI |
[Versão prévia de otimização de entrega](#delivery-optimization-preview) | reduza o consumo de largura de banda para downloads de vários dispositivos HoloLens. | Administrador de TI |

Confira as notas de versão relacionadas:

- [visite o arquivo morto do HoloLens Emulator](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Apresentando o novo Microsoft Edge

![Animação do logotipo do Microsoft Edge herdado para o logotipo do novo Microsoft Edge.](images/new-edge.gif)

O novo Microsoft Edge [adota o projeto de software livre Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para que haja uma melhor compatibilidade para os clientes e menos fragmentação da Web para os desenvolvedores Web.

> [!IMPORTANT]
> Esse novo Microsoft Edge substitui automaticamente o Microsoft Edge herdado, que [não tem mais suporte](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) em novas versões.

![Captura de tela do novo Microsoft Edge.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Iniciando o novo Microsoft Edge

O novo Microsoft Edge ![O ícone do novo Microsoft Edge.](images/new_edge_logo.png) (representado por um ícone de espiral azul e verde) está fixado no menu Iniciar e será iniciado automaticamente quando você ativar um link da Web.

> [!NOTE]
> Quando você iniciar pela primeira vez o novo Microsoft Edge no HoloLens 2, suas configurações e dados serão importados do Microsoft Edge herdado. se você continuar a usar o Microsoft Edge herdado depois de iniciar o novo Microsoft Edge, esses novos dados não serão sincronizados do Microsoft Edge herdado para o novo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Definindo as configurações de política para o novo Microsoft Edge

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

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>O que esperar do novo Microsoft Edge no HoloLens 2

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
- Ao reproduzir áudio de uma janela do navegador no [modo "Follow-me"](hololens2-basic-usage.md#follow-me-stop-following), o áudio continuará a ser reproduzido se você desabilitar o modo "Siga eu". Você pode contornar esse problema interrompendo a reprodução de áudio antes de desabilitar o modo "Follow-me" ou fechando a janela com o botão **X** .
- A interação com janelas ativas do Microsoft Edge pode fazer com que outras janelas de aplicativo 2D fiquem inativas inesperadamente. Você pode reativar essas janelas interagindo com elas novamente.

#### <a name="microsoft-edge-insider-channels"></a>Canais do Microsoft Edge Insider

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

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Usando o WDAC para bloquear o novo Microsoft Edge

Para administradores de TI que desejam atualizar sua [política do WDAC](windows-defender-application-control-wdac.md) para bloquear o novo aplicativo Microsoft Edge, adicione o código a seguir à política.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Gerenciando pontos de extremidade para o novo Microsoft Edge

Alguns ambientes podem ter restrições de rede a serem consideradas. Para garantir uma experiência tranquila com o novo Edge, [habilite esses pontos de extremidade da Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Leia mais sobre os [pontos de extremidade para o HoloLens](hololens-offline.md) no momento.

### <a name="install-web-apps"></a>Instalar aplicativos Web
 > [!Note]
>Começando na [versão 21H1 do Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h1), o aplicativo Web do Office não será mais pré-instalado.

Você pode usar o novo Edge para instalar aplicativos Web com aplicativos da Microsoft Store. Por exemplo, você pode instalar o aplicativo Web do Microsoft Office para exibir e editar arquivos hospedados no SharePoint ou no OneDrive. Para instalar o aplicativo Web do Office, visite https://www.office.com e selecione o botão **Aplicativo Disponível** ou **Instalar o Office** na barra de endereços. Selecione **Instalar** para confirmar.

> [!IMPORTANT]
> A funcionalidade do aplicativo Web do Office fica disponível somente quando o HoloLens 2 tem uma conexão ativa com a Internet.

### <a name="webxr-and-360-viewer"></a>WebXR e Visualizador 360

O novo Microsoft Edge inclui suporte para o WebXR, que é o novo padrão para a criação de experiências imersivas na Web (substituindo o WebVR). Muitas experiências da Web imersivas foram projetadas com a VR em mente (elas substituem seu campo de visão por um ambiente virtual), mas também há suporte para essas experiências no HoloLens 2. O padrão WebXR também habilita experiências da Web imersivas aumentadas e de realidade misturada que usam seu ambiente físico. Esperamos que, conforme os desenvolvedores passarem mais tempo com o WebXR, novas experiências imersivas aumentadas e de realidade misturada cheguem para os clientes do HoloLens 2 experimentarem!

A extensão do Visualizador 360 é baseada no WebXR e é instalada automaticamente com o novo Microsoft Edge no HoloLens 2. Essa extensão da Web permite que você mergulhe em vídeos em 360 graus. O YouTube oferece a maior seleção de vídeos 360, portanto incentivamos você a começar por lá.

#### <a name="how-to-use-webxr"></a>Como usar o WebXR

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

#### <a name="how-to-use-360-viewer"></a>Como usar o Visualizador 360

1. Navegue até um vídeo com 360 graus no YouTube.
1. No quadro de vídeo, selecione o botão de headset de realidade misturada:

    ![Botão para ativar o Visualizador 360.](images/enter-360-viewer.jpg)

1. Na primeira vez que você tentar iniciar uma experiência do Visualizador 360 em um domínio específico, o navegador solicitará consentimento para entrar em uma exibição imersiva. selecione **Permitir**.
1. Com um gesto de [fechar e abrir dedos indicador e polegar](hololens2-basic-usage.md#select-using-air-tap), abra os controles de reprodução. Use gestos de [hand rays e fechar e abrir dedos indicador e polegar](hololens2-basic-usage.md#select-using-air-tap) para reproduzir/pausar, acelerar/voltar, ativar/desativar legendas ou parar a experiência (que sai da exibição imersiva). Os controles de reprodução desaparecem após alguns segundos de inatividade.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principais problemas conhecidos do WebXR e do Visualizador 360
- Dependendo da complexidade da experiência no WebXR, a taxa de quadros poderá cair ou travar.
- O suporte para articulações de mão com movimento no WebXR não está habilitado por padrão. Os desenvolvedores podem habilitar o suporte via `edge://flags` ativando a "entrada do WebXR Hand".
- Vídeos em 360 de sites diferentes do YouTube podem não funcionar conforme o esperado.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Fornecendo comentários sobre o WebXR e o Visualizador 360

Compartilhe comentários e bugs com nossa equipe por meio do recurso **Enviar Comentários** no novo Microsoft Edge.

### <a name="new-settings-app"></a>Novo aplicativo Configurações

com esta versão, estamos introduzindo uma nova versão do aplicativo Configurações. O novo aplicativo Configurações inclui novos recursos e configurações expandidas para o HoloLens 2 nas seguintes áreas: Som, Energia e suspensão, Rede e Internet, Aplicativos, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Como o novo aplicativo Configurações é diferente do aplicativo Configurações herdado, as janelas de Configurações que você colocou em seu ambiente serão removidas após a atualização.

![Home page do novo aplicativo Configurações.](images/new-settings-app.png)

**Novos recursos e configurações**
- Pesquisa de Configurações: pesquise por configurações na home page de Configurações usando palavras-chave ou o nome da configuração.
- Sistema > Som:
  - dispositivos de áudio de entrada e saída: escolha independentemente seus dispositivos de áudio de entrada e saída (por exemplo, ouça áudio com fones de ouvido Bluetooth ou use um microfone USB-C para entrada de áudio).
    > [!NOTE]
    > Microfones Bluetooth não têm suporte do HoloLens 2.
  - Volume do aplicativo: ajuste o volume de cada aplicativo de maneira independente. Confira [controle de volume por aplicativo](#per-app-volume-control).
- Sistema > Energia e suspensão: escolha quando o dispositivo deve entrar em suspensão após um período de inatividade.
- Sistema > Bateria: habilite manualmente o modo de economia de bateria ou defina um limite de bateria no qual o modo de economia de bateria é ativado automaticamente.
- Dispositivos > USB: você pode desabilitar conexões USB por padrão.
- Rede e Internet:
  - agora, adaptadores USB-C para Ethernet aparecerão em Rede e Internet.
  - Configurações do adaptador USB-C para Ethernet estão disponíveis, incluindo o endereço IP dele.
  - Agora, você pode habilitar o modo avião no HoloLens 2.
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Para obter mais informações, confira [Seletor de aplicativos padrão](#default-app-picker).
- Contas > Outros usuários: os proprietários dos dispositivos podem adicionar usuários, atualizar usuários padrão para proprietários do dispositivo, fazer downgrade de proprietários de dispositivo para usuários padrão e remover usuários.
- Facilidade de Acesso: altere o tamanho do texto e alguns efeitos visuais.

**Problemas conhecidos**
- Janelas de Configurações fixadas anteriormente serão removidas (veja a observação acima).
- Você não pode mais renomear o dispositivo usando o aplicativo Configurações. Os administradores de TI podem renomear dispositivos usando o modelo de nome de dispositivo do [Windows Autopilot para HoloLens 2](hololens2-autopilot.md) ou o nó Ext/Microsoft/DNSComputerName do [CSP DevDetail](/windows/client-management/mdm/devdetail-csp) do MDM.
- A página Ethernet mostra um dispositivo de Ethernet virtual ("UsbNcm") o tempo todo.
- O uso da bateria no novo Microsoft Edge pode não estar preciso devido à sua natureza de aplicativo de área de trabalho Win32 com suporte de uma camada de adaptador da UWP (nenhuma correção prevista para o futuro próximo).

#### <a name="display-color-calibration"></a>Exibir calibragem de cores



Com essa nova configuração, você pode selecionar um perfil de cor alternativo para a exibição HoloLens 2. Isso pode ajudar as cores a aparecerem mais precisas, especialmente em níveis de brilho de exibição inferiores. A calibragem de cores de exibição pode ser encontrada no aplicativo Configurações, na página Calibragem > Sistema.

> [!NOTE]
> Como essa configuração salva um novo perfil de cor no firmware de exibição, trata-se de uma configuração por dispositivo (e não exclusiva para cada conta de usuário).

##### <a name="how-to-use-display-color-calibration"></a>Como usar a calibragem de cores de exibição

1. Inicie o aplicativo **Configurações** e navegue até **Sistema > Calibragem**.
1. Em **Exibir calibragem de cores**, escolha o botão **Executar calibragem de cores de exibição**.
1. A experiência de calibragem de cores de exibição será lançada e o incentivará a garantir que o visor esteja na posição correta.
1. Depois de prosseguir com as caixas de diálogo de instrução, a exibição será esmaecida automaticamente para 30% de brilho.
    > [!TIP]
    > Se você estiver tendo problemas para ver a cena esmaecida em seu ambiente, poderá ajustar manualmente o nível de brilho do HoloLens 2 usando os botões de brilho no lado esquerdo do dispositivo.
1. Escolha os botões de 1 a 6 para experimentar instantaneamente cada perfil de cor e encontre um que seja melhor para seus olhos (isso geralmente significa o perfil que ajuda a cena a parecer mais neutra, com o padrão de escala de cinza e os tons de pele com a aparência esperada.)

    ![Exibir cena de calibragem de cores.](images/color-cal-ui.png)
    
1. Quando estiver satisfeito com o perfil escolhido, escolha o botão **Salvar e Sair**
1. Se você preferir não fazer alterações, escolha o botão **Cancelar e Sair**, e as alterações serão revertidas

> [!TIP]
> Aqui estão algumas dicas úteis para ter em mente ao usar a configuração de calibragem de cores de exibição:
> - Você pode executar a calibragem de cores de exibição em Configurações sempre que quiser
> - Se alguém no dispositivo tiver usado anteriormente a configuração para alterar perfis de cor, a data/hora da alteração mais recente será refletida na página Configurações
> - Quando você executar a calibragem de cores de exibição, o perfil de cor salvo anteriormente será realçado, e o Perfil 0 não será exibido (pois o Perfil 0 representa o perfil de cores original da exibição)
> - Se você quiser reverter para o perfil de cores original da exibição, poderá fazer isso na página Configurações (confira [como redefinir o perfil de cores](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Como redefinir o perfil de cores 

Se você não estiver satisfeito com o perfil de cores personalizado salvo no HoloLens 2, poderá restaurar o perfil de cores original do dispositivo:
1. Inicie o aplicativo **Configurações** e navegue até **Sistema > Calibragem**.
1. Em **Exibir calibragem de cores**, escolha o botão **Redefinir para o perfil de cores padrão**.
1. Quando a caixa de diálogo for aberta, escolha **Reiniciar** se você estiver pronto para reiniciar o HoloLens 2 e aplicar as alterações.

#### <a name="top-display-color-calibration-known-issues"></a>Principais problemas conhecidos de calibragem de cores de exibição

- Na página Configurações, a cadeia de caracteres de status que informa quando o perfil de cor foi alterado pela última vez ficará des date até que você recarregue essa página Configurações.
    - Solução alternativa: escolha outra página Configurações e, em seguida, escolha a página Calibragem.

#### <a name="default-app-picker"></a>Seletor de aplicativo padrão

Ao ativar um hiperlink ou abrir um tipo de arquivo com mais de um aplicativo instalado, que dá suporte a ele, você verá uma nova janela aberta solicitando que você selecione qual aplicativo instalado deve lidar com o tipo de arquivo ou link. Nessa janela, você também pode optar por fazer com que o aplicativo escolhido manipule o tipo de arquivo ou link "Uma vez" ou "Sempre".

Se você escolher "Sempre", mas posteriormente quiser mudar qual aplicativo trata um determinado arquivo ou tipo de link, poderá redefinir os padrões salvos em **Configurações > Apps**. Role até a parte inferior da página e escolha o botão **Limpar** em "Aplicativos padrão para tipos de arquivo" e/ou "Aplicativos padrão para tipos de link". Ao contrário da configuração semelhante em computadores desktop, não é possível redefinir padrões de tipo de arquivo individuais.

#### <a name="per-app-volume-control"></a>Controle de volume por aplicativo

Agora, neste Windows build, os usuários podem ajustar manualmente o nível de volume de cada aplicativo. Isso permite que os usuários se concentrem melhor nos aplicativos que precisam ou se ouvir melhor ao usar vários aplicativos. Por exemplo, a necessidade de desativar o volume de um aplicativo ao chamar outra pessoa para assistência remota em outro.

Para definir o volume de um aplicativo individual, navegue até **Configurações**  -> **Sistema** -> **Som** e, em Opções avançadas de som, escolha **Volume do aplicativo e preferências do dispositivo**.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Deslizar para tipo

Alguns clientes acham mais rápido "digitar" em teclados virtuais ao deslizar a forma da palavra que pretendem digitar e estamos visualizando esse recurso para o teclado holográfico. Você pode passar uma palavra por vez passando a ponta do dedo pelo plano do teclado holográfico, passando a forma da palavra e, em seguida, retirando a ponta do dedo do plano do teclado. Você pode deslizar as palavras seguintes sem precisar pressionar a barra de espaço removendo o dedo do teclado entre as palavras. Você saberá que o recurso está funcionando se vir uma trilha do dedo após o movimento do dedo no teclado.

Observe que esse recurso pode ser difícil de usar e dominar por causa da natureza de um teclado holográfico, em que você não sente a resistência contra o dedo (ao contrário de uma tela de telefone celular). 

### <a name="power-menu-from-start"></a>Menu de energia do Início

Um novo menu que permite ao usuário sair, desligar e reiniciar o dispositivo. Um indicador na tela Iniciar HoloLens que mostra quando uma atualização do sistema está disponível.

#### <a name="how-to-use"></a>Como usar

1. Abra a tela Iniciar HoloLens usando o [gesto Iniciar](hololens2-basic-usage.md#start-gesture) ou dizendo "Voltar ao início".

2. Observe o ícone de reticências (…) ao lado da imagem de perfil do usuário:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Escolha a imagem de perfil do usuário usando suas mãos ou o comando de voz "Ligar/Desligar".

4. Um menu é exibido com opções para sair, reiniciar ou desligar o dispositivo:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Escolha as opções de menu para sair, reiniciar ou desligar o HoloLens. A opção Sair pode não estar disponível se o dispositivo estiver configurado para uma [única Conta da Microsoft (MSA) ou conta local](hololens-identity.md).

6. Descarte o menu tocando em qualquer outro lugar ou fechando o menu Iniciar com o gesto de início.

#### <a name="update-indicator"></a>Indicador de atualização

Quando uma atualização estiver disponível, o ícone de reellipse será aluminado para indicar que uma reinicialização instalará a atualização As opções de menu também mudam para refletir a presença da atualização.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela Entrar

Anteriormente, a tela Entrar mostrava apenas o usuário que entrou mais recentemente, bem como um ponto de entrada "Outro usuário". Recebemos comentários dos clientes de que isso não é suficiente se vários usuários entraram no dispositivo. Eles ainda eram necessários para novo tipo de nome de usuário etc.

Introduzido neste build Windows, ao  selecionar Outro usuário localizado à direita do campo de entrada pin, a tela Entrar exibirá vários usuários com já conectados ao dispositivo. Isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entre usando suas Windows Hello credenciais. Um novo usuário também pode ser adicionado ao dispositivo desta página Outros usuários por meio do **botão Adicionar conta.**

Quando estiver no menu Outros usuários, o botão Outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela Entrar para esse usuário.

![Padrão da tela de login.](./images/multiusers1.jpg)

<br>

![Tela de login de outros usuários.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Suporte para microfone externo USB-C

> [!IMPORTANT]
> Conectar **um microfone USB não o definirá automaticamente como o dispositivo de entrada**. Ao conectar um conjunto de fones de ouvido USB-C, os usuários observarão que o áudio do fone de ouvido será redirecionado automaticamente para os fones de ouvido, mas o sistema operacional HoloLens prioriza a matriz de microfone interno acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

Os usuários podem escolher microfones externos conectados por USB-C usando o painel de configurações de **Som**. Os microfones USB-C podem ser usados para fazer chamadas, gravar etc.

Abra o aplicativo **Configurações** e escolha **Sistema** > **Som**.

![Configurações de Som.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com o **Remote Assist**, os usuários precisarão clicar no hiperlink "Gerenciar dispositivos de som".
>
> Em seguida, use o menu suspenso para definir o microfone externo como **Padrão** ou **Padrão de Comunicações**. Escolher **Padrão** significa que o microfone externo será usado em todos os lugares.
>
> Escolher **Padrão de Comunicações** significa que o microfone externo será usado no Remote Assist e em outros aplicativos de comunicação, mas a matriz de microfones do HoloLens ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som.](images/usbc-mic-2.png)

<br>

![Definir o padrão do microfone.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>E quanto ao suporte para microfone Bluetooth?

Infelizmente, Bluetooth ainda não há suporte para microfones no HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solução de problemas de microfones USB-C

Esteja ciente de que alguns microfones USB-C relatam-se incorretamente como um microfone *e um* alto-falante. Esse é um problema com o microfone e não com HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

No **Configurações** Do Sistema , de definir explicitamente os  ->    ->  alto-falantes integrados **(Driver de** Áudio de Recurso Análogo) como **o dispositivo padrão**. HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado posteriormente.

![Solução de problemas de microfones USB-C.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Logon automático do Visitante para Quiosques

Esse novo recurso permite que o logon automático em contas de Visitante seja usado para modos de quiosque.

Para uma configuração não AAD, para configurar um dispositivo para logon automático de visitante:

1. Crie um pacote de provisionamento que:
    1. Define as **configurações de Runtime/AssignedAccess** para permitir contas de Visitante.
    1. Opcionalmente, registra o dispositivo no MDM **(configurações de runtime/Workplace/Enrollments)** para que ele possa ser gerenciado posteriormente.
    1. Não crie uma conta local
1. [Aplique o pacote de provisionamento](hololens-provisioning.md).

Para uma configuração do AAD, os usuários podem obter algo semelhante a isso hoje sem essa alteração. Dispositivos ingressados no AAD configurados para o modo de quiosque podem entrar em uma conta de Visitante com um único toque de botão na tela de entrada. Depois de conectado à conta de visitante, o dispositivo não solicitará a entrada novamente até que o Visitante seja explicitamente conectado no menu iniciar ou o dispositivo seja reiniciado.

O logon automático do Visitante pode ser gerenciado por meio da [política personalizada de OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Valor do URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

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

Em builds mais antigos, se um dispositivo tivesse uma configuração de quiosque, que é uma combinação de acesso atribuído global e acesso atribuído ao membro do grupo do AAD, se a determinação da associação ao grupo do AAD falhasse, o usuário verá[o](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)menu " nada mostrado no menu iniciar ".

A partir desta Windows, a experiência de quiosque fará fallback para a configuração de quiosque global (se presente) em caso de falhas durante o modo de quiosque do grupo do AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Novos URIs Configurações para visibilidade de Configurações página

No [Windows Holographic, versão 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) adicionamos a política [Configurações/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas dentro do Configurações aplicativo. PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema ou a todas as páginas, exceto aquelas especificadas.

Se você visitar [a Página Configurações Visibilidade,](settings-uri-list.md)poderá encontrar instruções para usar esse CSP e a lista de URIs disponíveis nas versões anteriores.

Estamos expandindo a lista de urIs Configurações disponíveis, que os administradores de IT podem gerenciar. Alguns desses URIs são para áreas recém-disponíveis no novo Configurações aplicativo. Se você estiver usando Configurações/PageVisibilityList, revise a lista a seguir e ajuste suas páginas permitidas ou bloqueadas conforme necessário.

> [!NOTE]
> **Preterido: ms-settings:network-proxy**
>
> Uma página de configurações foi preterida nesses builds mais novos. A página **de Proxy de Internet &** rede antiga não está mais disponível como uma  >   configuração global. As novas configurações de proxy por conexão podem ser encontradas em Propriedades de Rede **&**  >  **Wi-Fi** da Internet ou Propriedades de Rede  >   & **Ethernet** da Internet  >    >  .

<br>

| Página de configurações                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplicativos > aplicativos & recursos                               | `ms-settings:appsfeatures`                         |
| Aplicativos > aplicativos & recursos > opções avançadas          | `ms-settings:appsfeatures-app`                     |
| Aplicativos > mapas offline                                  | `ms-settings:maps`                                 |
| Aplicativos > mapas offline > download de mapas                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > Mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Rede & internet > modo avião                   | `ms-settings:network-airplanemode`                 |
| Privacidade > geral                                    | `ms-settings:privacy-general`                      |
| Privacidade > de & digitando a personalização             | `ms-settings:privacy-speechtyping`                 |
| Movimento de > privacidade                                     | `ms-settings:privacy-motion`                       |
| Limites de > de captura de tela                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Capturas de > privacidade e aplicativos                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Bateria > sistema                                     | `ms-settings:batterysaver`                         |
| Bateria > sistema                                     | `ms-settings:batterysaver-settings`                |
| Som > sistema                                       | `ms-settings:sound`                                |
| Sistema > som > de aplicativo e preferências do dispositivo | `ms-settings:apps-volume`                          |
| Sistema > som > gerenciar dispositivos de som              | `ms-settings:sound-devices`                        |
| Configuração > Armazenamento > sistema Armazenamento Sense         | `ms-settings:storagepolicies`                      |
| Hora & de > data & hora                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Linguagem & de > tempo                           | `ms-settings:language`                             |
| Linguagem & de > tempo                           | `ms-settings:regionlanguage-languageoptions`       |
| Atualizar & segurança > redefinir & recuperação               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URIs atualizados

Anteriormente, os dois URIs a seguir não levariam um usuário diretamente para as páginas indicadas, mas apenas bloqueariam a página de atualizações principal. Os seguintes itens foram atualizados para direcionar para suas páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configurando o Diagnóstico de Fallback por meio Configurações aplicativo

Agora, no Configurações, um usuário pode configurar o comportamento do [Diagnóstico de Fallback.](hololens-diagnostic-logs.md) No aplicativo Configurações, navegue até **a página Solução** de problemas  ->  **de** privacidade para definir essa configuração.

> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.  

### <a name="share-things-with-nearby-devices"></a>Compartilhar coisas com dispositivos próximos

Compartilhe coisas com dispositivos Windows 10, incluindo PCs e outros HoloLens 2 dispositivos. Você pode experimentar em experiências **compartilhadas** Configurações sistema para compartilhar arquivos ou  ->    ->   URLs de um HoloLens para um PC. Para obter mais detalhes, leia mais sobre como compartilhar [coisas com dispositivos próximos no Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esse recurso pode ser gerenciado por [meio de Conectividade/AllowConnectedDevices.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Novos rastreamentos de diagnóstico do sistema operacional

além das soluções de problemas anteriores no aplicativo Configurações, uma nova solução de problemas foi adicionada com a adição do novo aplicativo Configurações para atualizações do sistema operacional. navegue até **Configurações**  ->  **atualização &amp;** de solução de problemas de segurança  >    >  **Windows Update** e selecione **iniciar**. Isso permite que você colete rastreamentos ao reproduzir seu problema com as atualizações do sistema operacional para auxiliar na solução de problemas com sua ti ou suporte.

### <a name="delivery-optimization-preview"></a>Versão prévia de otimização de entrega

com essa atualização de HoloLens, Windows Holographic for Business permite que as configurações de otimização de entrega reduzam o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa dessa funcionalidade com a configuração de rede recomendada está disponível aqui: [Otimização de entrega para atualizações do Windows 10](/windows/deployment/update/waas-delivery-optimization).

As seguintes configurações são habilitadas como parte da superfície de gerenciamento e [podem ser configuradas no Intune](/mem/intune/configuration/delivery-optimization-settings):

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

Algumas advertências sobre essa oferta de versão prévia:

- O suporte do HoloLens é limitado nesta versão prévia apenas a atualizações do sistema operacional.
- O Windows Holographic for Business permite apenas modos de download HTTP e downloads de um [ponto de extremidade do Cache Conectado da Microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). Não há compatibilidade com modos de download ponto a ponto e atribuições de grupo em dispositivos HoloLens no momento.
- O HoloLens é compatível com a implantação ou a otimização de entrega para pontos de extremidade do Windows Server Update Services.
- A solução de problemas exigirá o diagnóstico no servidor Cache Conectado ou a coleta de um rastreamento no HoloLens no HoloLens por meio do **Configurações** > **Atualização e Segurança** >  **Solução de problemas** >  **Windows Update**.

### <a name="it-admin---update-checklist"></a>Administrador de ti – lista de verificação de atualização

Esta lista de verificação ajudará você a saber os novos itens que os recursos que estão sendo adicionados nesta atualização de recurso podem afetar suas configurações atuais de gerenciamento de dispositivo ou os novos recursos que você pode querer começar a usar.

#### <a name="updates-to-kiosk-mode"></a>Atualizações para o modo de quiosque

✔️ [**novo AUMIDs para novos aplicativos no modo de quiosque**](#use-the-new-settings-and-edge-apps-in-kiosk-modes):

se você estava usando anteriormente o aplicativo Configurações ou Microsoft Edge aplicativo em um quiosque, substituímos esses aplicativos por novos aplicativos que usam uma ID de aplicativo diferente. É altamente recomendável que você leia [novos AUMIDs para novos aplicativos no modo de quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) abaixo. isso garantirá que você continue a ter o aplicativo Configurações em seu quiosque ou inclua o novo aplicativo Microsoft Edge. Essas alterações podem ser feitas agora e implantadas em todos os dispositivos e permitem uma transição mais suave na atualização.

[**logon automático do visitante do ✔️ para quiosques**](#visitor-auto-logon-for-kiosks): 

Os visitantes agora podem ser conectados automaticamente a um quiosque. Esse comportamento é ativado por padrão, mas pode ser gerenciado e desabilitado.

✔️ [**envio de falha do modo de quiosque aprimorado**](#kiosk-mode-behavior-changes-for-handling-of-failures):

Se a associação de grupo do AAD do usuário conectado do AAD não for determinada com êxito, a configuração de quiosque global será usada para o menu iniciar (se houver) caso contrário, o usuário será apresentado com o menu iniciar vazio. Embora o menu iniciar vazio não seja uma configuração que você possa definir diretamente, essa nova manipulação pode ser algo para informar o departamento de suporte de se você estiver usando quiosques, pois isso pode se aplicar às suas configurações ou você talvez queira fazer novos ajustes nas suas configurações de acesso atribuídas.

#### <a name="updates-to-page-settings-visibility"></a>atualizações da visibilidade da Configurações de página

✔️ [**novos URIs de Configurações para visibilidade de Configurações de página**](#new-settings-uris-for-page-settings-visibility)

se você estiver usando a [visibilidade de Configurações de página](settings-uri-list.md) no momento, talvez queira fazer ajustes em seus URIs existentes que você tenha permitido ou bloqueado.

#### <a name="updates-for-your-wdac-policy"></a>Atualizações para sua política WDAC
✔️ se você estava bloqueando anteriormente Microsoft Edge via WDAC, convém atualizar sua política WDAC. Examine o seguinte e use o código de exemplo fornecido.
#### <a name="enable-new-endpoints-for-edge"></a>Habilitar novos pontos de extremidade para o Edge
✔️ se você tiver uma infraestrutura que envolve a configuração de pontos de extremidade de rede, como proxy ou firewall, habilite esses novos pontos de extremidade para o novo aplicativo Microsoft Edge.

#### <a name="newly-configurable-items"></a>Itens configuráveis recentemente

✔️ [Configurar o diagnóstico de fallback](#configuring-fallback-diagnostics-via-settings-app): você pode configurar se e quem pode coletar diagnósticos de fallback.

✔️[compartilhar coisas com dispositivos próximos](#share-things-with-nearby-devices): você pode desabilitar o novo recurso de compartilhamento próximo.

✔️ [definir configurações de política para o novo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge): examine as configurações recentes disponíveis para Microsoft Edge.

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
- essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa compilação mais recente, Windows Holographic, versão 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, versão 1903 – maio de 2021 atualização
- Build 18362,1110

Melhorias e correções na atualização:
- Essa atualização de qualidade mensal não contém nenhuma alteração notável. **Essa compilação não receberá mais atualizações de serviço mensais**. incentivamos você a experimentar nossa compilação mais recente, Windows Holographic, versão 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versão 20H2-atualização de abril de 2021
- Build 19041,1144

Melhorias e correções na atualização:

- Corrige um problema em torno da linha de relatórios de status de instalação do aplicativo de negócios.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versão 1903 – atualização de abril de 2021
- Build 18362,1108

Melhorias e correções na atualização:

- resolve um problema em que o aplicativo Configurações falha ao tentar alterar uma senha para uma conta local.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versão 20H2-atualização de março de 2021
- Build 19041,1140

Melhorias e correções na atualização:

- os clientes que usam AdvancedPhotoCapture ou LowLagPhotoCapture para capturar fotos com HoloLens 2 agora podem recuperar a câmera até 3 segundos após a captura da foto.
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
- aborda um problema em relação a atualizações e voos para versões mais recentes do HoloLens.
- foram removidos certificados pré-instalados não utilizados do armazenamento raiz do eSIM de dispositivos HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versão 1903-atualização de fevereiro de 2021
- Build 18362,1098

essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas compilações mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versão 20H2-atualização de janeiro de 2021
- Build 19041,1134

Melhorias e correções na atualização:

- Desempenho aprimorado durante a inicialização, retomada e troca de usuário quando há muitos usuários no dispositivo.
- Adicionado suporte arm32 para o [modo de pesquisa](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versão 1903 – atualização de janeiro de 2021
- Build 18362,1091

essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas compilações mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versão 20H2 – atualização de dezembro de 2020
- Build 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>instalar aplicativos no HoloLens 2 por meio do instalador de aplicativo

estamos **adicionando um novo recurso (instalador do aplicativo) para permitir que você instale aplicativos com mais perfeição** em seus dispositivos HoloLens 2. O recurso estará **ativado por padrão para dispositivos não gerenciados**. Para evitar a interrupção para as empresas, o instalador **de aplicativos não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:
- MDM [registrado](hololens-enroll-mdm.md)
- Configurado com [pacote de provisionamento](hololens-provisioning.md)
- A [identidade](hololens-identity.md) do usuário é Azure AD

Agora você pode instalar aplicativos sem a necessidade de habilitar o modo de desenvolvedor ou usar o portal do dispositivo.  Basta baixar (por USB ou por borda) o pacote Appx para seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.  Como alternativa, [inicie uma instalação de uma página da Web](/windows/msix/app-installer/installing-windows10-apps-web).  assim como os aplicativos que você instala do Microsoft Store ou sideload usando o recurso de implantação de aplicativo de LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiável](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo de HoloLens antes que o aplicativo possa ser implantado.

**Instruções de instalação do aplicativo.**

1.  Certifique-se de que seu dispositivo não seja considerado gerenciado
1.  verifique se o dispositivo HoloLens 2 está ligado e conectado ao seu PC
1.  verifique se você está conectado ao dispositivo HoloLens 2
1.  em seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Armazenamento \Downloads.   Depois de terminar de copiar o arquivo, você pode desconectar seu dispositivo
1.  em seu dispositivo HoloLens 2, abra o Menu iniciar, selecione todos os aplicativos e inicie o aplicativo explorador de arquivos.
1.  Navegue até a pasta downloads. Talvez seja necessário no painel esquerdo do aplicativo selecione primeiro este dispositivo e, em seguida, navegue até downloads.
1.  Selecione o arquivo yourapp. appxbundle.
1.  O instalador do aplicativo será iniciado. Selecione o botão instalar para instalar o aplicativo.
O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.

você pode encontrar aplicativos de exemplo em [Windows exemplos universais GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar esse fluxo.

leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o instalador do aplicativo](app-deploy-app-installer.md).  

![Instalando exemplos do MRTK por meio do instalador do aplicativo.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O rastreamento manual agora mantém o controle em vários novos casos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, apenas a posição Palm continua a ser atualizada com base na disponibilidade do usuário, enquanto as outras junções são inferidas com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência de rastreamento em movimentos como pregaria, lançando, scooping e Clapping.  Também ajuda nos casos em que a mão está perto de uma superfície ou segurando um objeto.  Quando as junções de mão estão sendo inferidas, o valor de [precisão por](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) conjunto será definido como "aproximado" em vez de "alto".
- Correção de um problema em que o PIN redefinido para contas do Azure AD mostraria um erro "algo deu errado.
- Os usuários devem ver muito menos falhas no OOBE após a inicialização de ET, íris no aplicativo de configurações, novo usuário ou notificação do sistema.
- Os usuários devem ter o fuso horário correto saindo do OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versão 1903 – atualização de dezembro de 2020
- Build 18362,1088

essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa última Windows Holographic, versão 20H2 – atualização de dezembro de 2020 e o novo recurso instalador de aplicativo adicionado na compilação.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versão 20H2
- Build 19041,1128

Windows Holographic, a versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para HoloLens 2 usuários e profissionais de ti. do posicionamento de olho automático, para o gerenciador de certificados no Configurações, para aprimorar a funcionalidade do modo de quiosque e para novos recursos de instalação do autopilot. essa nova atualização permite que as equipes de ti adotem um controle mais granular para configurar e gerenciar dispositivos HoloLens e oferece aos usuários experiências holographics ainda mais diretas. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. o número de build principal permanecerá o mesmo e Windows Update indicará uma versão mensal para a versão 2004 (build 19041). você pode examinar o número da sua versão no seu Configurações > tela sobre para confirmar se está no Build 19041.1128 + do mais recente disponível. para atualizar para a versão mais recente, abra o aplicativo Configurações, vá para atualização & segurança e toque em verificar se há atualizações. para obter mais informações sobre como gerenciar atualizações de HoloLens, visite [gerenciar HoloLens atualizações](hololens-updates.md).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>o que há de novo no Windows Holographic, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte Automático de Posição Ocular](hololens-release-notes.md#auto-eye-position-support) | Computa ativamente posições de olho sem que os usuários passem pela calibragem de controle ocular.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | permite que novos métodos mais simples instalem e removam certificados do aplicativo Configurações.     |
| [Inicialização automática do provisionamento de USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | O provisionamento de pacotes em unidades USB solicita automaticamente a página de provisionamento no OOBE.                                                         |
| [Confirmar automaticamente os pacotes de provisionamento no OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante o OOBE da página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a inicialização automática de provisionamento e a confirmação automática em conjunto. |
| [Usando o piloto automático com conexão Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o AutoPilot do dispositivo Wi-Fi sem a necessidade do adaptador Ethernet. |
| [CSP TenantLockdown e Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após o registro do locatário e a política ser aplicada, o dispositivo só poderá ser registrado nesse locatário sempre que o dispositivo for redefinido ou atualizado novamente. |
| [Acesso Atribuído Global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para vários modos de quiosque de aplicativo que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
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

### <a name="auto-eye-position-support"></a>Suporte Automático de Posição Ocular

no HoloLens 2, as posições de olho permitem o posicionamento preciso do holograma, a experiência de exibição confortável e a qualidade de exibição aprimorada. As posições do olho são calculadas internamente como parte da computação de rastreamento ocular. Entretanto, isso requer que cada usuário passe pela calibragem de rastreamento ocular, mesmo quando a experiência possa não requerer a entrada do olhar fixo.

A **AEP (Posição Automática dos Olhos)** habilita esses cenários com uma forma livre de interação para calcular as posições dos olhos para o usuário. A Posição Ocular Automática começa a funcionar em segundo plano automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de acompanhamento ocular anterior, a Posição Ocular Automática começará a fornecer as posições de olho do usuário para o sistema de exibição após um tempo de processamento de 20 a 30 segundos. Os dados do usuário não são persistentes no dispositivo e, portanto, esse processo será repetido se o usuário sair e colocar o dispositivo novamente ou se o dispositivo reiniciar ou sair do modo de sleep.

Há algumas alterações de comportamento do sistema com o recurso Posição Automática Ocular quando um usuário não calibrado coloca o dispositivo. Nesse contexto, um usuário nãocalibizado refere-se a alguém que não passou pelo processo de calibragem de acompanhamento ocular no dispositivo anteriormente.

| Aplicativo Ativo | Comportamento Anterior | Comportamento do Windows Holográfico, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo não habilitado para olhar ou o Shell Holográfico |A caixa de diálogo do prompt de calibragem do rastreamento ocular é exibida. | Nenhum prompt é exibido. |
| Aplicativo habilitado para olhar | A caixa de diálogo do prompt de calibragem do rastreamento ocular é exibida. | O prompt de calibragem de rastreamento ocular é exibido apenas quando o aplicativo acessa o fluxo do olhar fixo. |

Se o usuário fizer a transição de um aplicativo não habilitado para olhar para um que acesse os dados do olhar, o prompt de calibragem será exibido. 

Todos os outros comportamentos do sistema serão semelhantes a quando o usuário atual não tiver uma calibragem ativa de acompanhamento ocular. Por exemplo, o gesto De início com uma mão não será habilitado. Não haverá nenhuma alteração na Experiência Inicial do programa de instalação inicial.

Para experiências que exigem dados de olhar com o olhar ou posicionamento de holograma muito preciso, recomendamos que usuários nãocalibados executem a calibragem de acompanhamento ocular. Ele pode ser acessado no prompt de calibragem de acompanhamento ocular ou iniciando o aplicativo Configurações no menu iniciar e, em seguida, selecionando Calibragem do > > calibragem ocular **> Calibragem** de olho.

Essas informações podem ser encontradas posteriormente com [outras informações de calibragem](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança e conformidade do dispositivo por meio do novo Gerenciador de Certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

Na Windows Holographic versão 20H2, estamos adicionando um Gerenciador de Certificados no HoloLens 2 Configurações aplicativo. Vá para **Configurações > atualizar & certificados > segurança.** Esse recurso fornece uma maneira simples e amigável de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de Certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar se um certificado foi implantado corretamente ou para confirmar que ele foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, validar que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade pretendido e é funcional pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar um certificado específico na lista rapidamente, há opções para classificar por nome, armazenamento ou data de validade. Os usuários também podem pesquisar diretamente um certificado. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **Informações.** 

Atualmente, a instalação do certificado dá suporte a arquivos .cer e .crt. Os proprietários do dispositivo podem instalar certificados no Computador Local e no Usuário Atual;  todos os outros usuários só podem instalar no Usuário Atual. Os usuários só podem remover certificados instalados diretamente da Configurações interface do usuário. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Conexão seu HoloLens 2 em um computador.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.
1.  Navegue **até Configurações Aplicativo > Atualizar & Certificados**> Segurança e selecione Instalar um certificado.
1.  Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione **Local do Armazenamento**.
1.  Selecione **Armazenamento de Certificados**.
1.  Clique em **Instalar**.

O certificado agora deve ser instalado no dispositivo.

#### <a name="to-remove-a-certificate"></a>Para remover um certificado: 
1. Navegue **até Configurações aplicativo > certificados de atualização e > segurança.**
1. Pesquise o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **Remover**
1. Selecione **Sim** quando solicitada a confirmação.

![Visualizador de certificados no Configurações aplicativo.](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado.](images/certificate-device-install.jpg)

Essas informações podem ser encontradas [posteriormente em uma nova página do Gerenciador de Certificados](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Provisionamento de início automático de USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante o OOBE.

Antes desta versão, os usuários tinham que iniciar a tela de provisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora os usuários podem ignorar a combinação de botões usando um Pacote de Provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagido do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB for deixada conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como observará se há outros que estão conectados.

Para obter mais informações sobre como aplicar pacotes de provisionamento durante o OOBE, visite a [documentação HoloLens de provisionamento.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Informações adicionais [sobre o provisionamento de](hololens-provisioning.md#auto-launch-provisioning-from-usb) início automático de um USB podem ser encontradas na documentação HoloLens provisionamento.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmar automaticamente os pacotes de provisionamento no OOBE
- Processo automatizado permitindo menos interação do usuário, quando a página Pacote de Provisionamento for exibida, ele aplicará automaticamente todos os pacotes listados.

Quando a tela principal de provisionamento aparecer, o OOBE contará 10 segundos antes de iniciar automaticamente a aplicação de todos os pacotes de provisionamento. Os usuários ainda [podem confirmar ou cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dentro de 10 segundos depois de verificar os pacotes esperados.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para interações de dispositivo reduzidas para provisionamento. 

Combinando o início automático do provisionamento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um usuário pode provisionar HoloLens 2 dispositivos automaticamente sem usar a interface do usuário do dispositivo ou até mesmo usar o dispositivo. Você pode continuar a usar a mesma unidade USB e o mesmo pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos ao mesmo tempo na mesma área. 

1. [Crie um pacote de provisionamento usando](hololens-provisioning.md) [Windows Designer de Configuração do](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie o pacote para uma unidade de armazenamento USB.
1. [Flash do HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) para [19041.1361 ou build mais novo.](https://aka.ms/hololens2previewdownload) 
1. Quando [o Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) tiver concluído a exibição do dispositivo, desconectar o cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. Quando o HoloLens 2 for inicializado no OOBE, ele detectará automaticamente o pacote de provisionamento na unidade USB e iniciará a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Seu dispositivo agora está configurado e [exibirá a tela Provisionamento bem-sucedido](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Usando o Autopilot com Wi-Fi conexão
- Remoção da necessidade de adaptadores USB-C para ethernet reduzindo as necessidades de hardware, permitindo que o Autopilot funcione em Wi-Fi conectados.

Agora, durante o OOBE, depois de se conectar HoloLens 2 com o Wi-Fi, o OOBE verificará se há um perfil do Autopilot para o dispositivo. Se for encontrado, ele será usado para concluir o restante do fluxo de registro e junção do AAD. Em outras palavras, o uso de ethernet para USB-C ou Wi-Fi adaptador usb-C não é mais um requisito, no entanto, eles continuam a funcionar se fornecidos no início do OOBE. Saiba mais sobre [o Autopilot para HoloLens 2 dispositivos](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP TenantLockdown e Autopilot
- Mantém os dispositivos no locatário da organização ao bloqueá-los para o locatário, mesmo por meio da redefinição ou reflash do dispositivo. Com mais segurança, não permitir a criação de conta no por meio do provisionamento. 

HoloLens 2 dispositivos agora são compatíveis com o CSP tenantLockdown [Windows holographic versão 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

O CSP [TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) permite que o HoloLens 2 seja vinculado ao registro do MDM usando apenas o Autopilot. Após o nó RequireNetworkInOOBE do CSP TenantLockdown ser definido com um valor de verdadeiro ou falso (definido inicialmente) no HoloLens 2, esse valor permanece no dispositivo mesmo que haja reinstalações da imagem, atualizações do sistema operacional etc. 

Após o nó RequireNetworkInOOBE do CSP TenantLockdown ser definido como verdadeiro no HoloLens 2, o OOBE aguarda indefinidamente que o perfil do Autopilot seja baixado e aplicado com sucesso após a conexão com a rede. 

Após o nó RequireNetworkInOOBE do CSP TenantLockdown ser definido como verdadeiro no HoloLens 2, as seguintes operações deixam de ser permitidas no OOBE: 
- Criação de usuário local usando provisionamento no runtime 
- Execução de uma operação de adição no Azure AD por meio de provisionamento no runtime 
- Seleção de proprietários do dispositivo na experiência do OOBE 

#### <a name="how-to-set-this-using-intune"></a>Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique verdadeiro para o nó RequireNetworkInOOBE, conforme mostrado a seguir.
O valor do OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuração do bloqueio de locatário via OMA-URI.](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Depois que essa configuração de dispositivo for aplicada com sucesso ao dispositivo HoloLens 2, os efeitos do TenantLockdown ficarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Como remover definição de RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune? 
1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração de dispositivos criada acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em OMA-URI personalizado e especifique falso para RequireNetworkInOOBE, como mostrado a seguir. O valor do OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE como falso via OMA-URI no Intune.](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos.

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Depois que essa configuração de dispositivo for aplicada com sucesso ao dispositivo HoloLens 2, os efeitos do TenantLockdown ficarão inativos.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>O que aconteceria durante o OOBE se o perfil do Autopilot não estivesse atribuído em um HoloLens após TenantLockdown ter sido definido como verdadeiro? 
O OOBE aguardaria indefinidamente o download do perfil do Autopilot e a caixa de diálogo a seguir seria apresentada. Para remover os efeitos do TenantLockdown, o dispositivo precisa ser registrado com seu locatário original usando apenas o Autopilot e RequireNetworkInOOBE precisa ter a definição removida, conforme descrito na etapa anterior, antes que as restrições introduzidas pelo CSP TenantLockdown sejam removidas.

![Exibição no dispositivo de quando a política é imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

Essas informações agora podem ser encontradas junto com o restante do piloto automático em [TENANTLOCKDOWN CSP e AutoPilot](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Acesso atribuído global – modo de quiosque
- Gerenciamento de identidades reduzido para quiosque, habilitando o novo método de quiosque que aplica o modo de quiosque no nível do sistema.

esse novo recurso permite que um administrador de ti configure um dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos que é aplicável no nível do sistema, não tem nenhuma afinidade com nenhuma identidade no sistema e se aplica a todos que se conectam ao dispositivo. leia sobre esse novo recurso em detalhes no [modo de quiosque de HoloLens](hololens-kiosk.md).

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

antes de encontrar falhas na aplicação do modo de quiosque, HoloLens usado para mostrar todos os aplicativos no menu iniciar. agora no Windows Holographic versão 20H2 no caso de falhas, nenhum aplicativo será mostrado no menu iniciar, como abaixo:

![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Policie

- opções de gerenciamento de dispositivo especificamente para HoloLens criadas para gerenciar o dispositivo. 

novas políticas de realidade misturada foram criadas para dispositivos HoloLens 2 no Windows Holographic versão 20H2. As novas configurações controláveis incluem: definir o brilho, definir o volume, desabilitar a gravação de áudio em capturas de realidade misturada, definir quando o diagnóstico pode ser coletado e o cache de associação do grupo do AAD.  

| nova política de HoloLens                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados e, portanto, pressioná-lo não altera o brilho.       | 1 Sim, 0 não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que os botões de volume sejam desabilitados e, portanto, pressionados não altera o volume.               | 1 Sim, 0 não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | desabilita o microfone, portanto, não é possível gravar áudio no HoloLens 2.                      | 1 Sim, 0 não (padrão)                                                |
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
1. crie um perfil de configuração de dispositivo para o quiosque de destino de grupos do Azure AD e atribua-o a HoloLens dispositivo (s). 
1. crie uma configuração de dispositivo personalizada com base em OMA URI que defina esse valor de política para o número de dias desejado (> 0) e atribua-o a HoloLens dispositivo (s). 
    1. O valor do URI deve ser inserido na caixa de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre min/max permitido.
1. registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário 1 do Azure AD entre quando a Internet estiver disponível, quando o usuário entrar e a associação de grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. agora, o usuário 1 do Azure AD pode colocar HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD. o ponto-chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que eles são membros do grupo do Azure AD ao qual a configuração de quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para um usuário do Azure AD passará por um comportamento de falha mencionado em ambientes "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>novas políticas de restrição de dispositivo para o HoloLens 2
- Permite que os usuários gerenciem políticas específicas de gerenciamento de dispositivos, como bloquear a adição ou remoção de pacotes de provisionamento.

políticas habilitadas recentemente que permitem mais opções de gerenciamento de dispositivos HoloLens 2. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Essas duas novas políticas para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> em relação ao [RemoteLock](/windows/client-management/mdm/remotelock-csp), HoloLens dará suporte apenas à configuração./Vendor/MSFT/RemoteLock/Lock. Não há suporte para as configurações que lidam com PIN como redefinição e recuperação.

### <a name="new-power-policies-for-hololens-2"></a>novas políticas de energia para o HoloLens 2
- mais opções para quando HoloLens suspenso ou trava por meio de políticas de energia. 

Essas políticas adicionadas recentemente permitem que os administradores controlem os Estados de energia, como tempo limite de ociosidade. Para ler mais sobre cada política individual, clique no link para essa política.

|     Link de documentação da política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     valor de exemplo a ser usado no Designer de configuração Windows, ou seja,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     valor de exemplo a ser usado no Designer de configuração Windows, ou seja,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  valor de exemplo a ser usado no Designer de configuração Windows, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     valor de exemplo a ser usado no Designer de configuração Windows, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     valor de exemplo a ser usado no Designer de configuração Windows, ou seja,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     valor de exemplo a ser usado no Designer de configuração Windows, ou seja,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas políticas para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> para uma experiência consistente no HoloLens 2, verifique se os valores de DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery estão definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Consulte os [temporizadores ociosos de exibição, suspensão e hibernação](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre o modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Políticas de atualização habilitadas recentemente para HoloLens
- Mais opções para quando as atualizações são instaladas ou a desabilitação do botão Pausar atualizações para garantir as atualizações.

essas políticas de atualização agora estão habilitadas em dispositivos HoloLens 2:
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Atualizar/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Atualizar/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

detalhes completos sobre essas políticas de atualização e como usá-las para dispositivos HoloLens podem ser lidos aqui em [gerenciar atualizações de HoloLens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Configurações visibilidade da página habilitada para HoloLens 2
- controle de interface do usuário aumentado no aplicativo Configurações, que pode ser confundido para mostrar uma seleção limitada de páginas.

agora habilitamos uma política que permite que os administradores de ti impeçam que páginas específicas no sistema Configurações aplicativo sejam visíveis ou acessíveis, ou que façam isso para todas as páginas, exceto aquelas especificadas. Para saber como personalizar totalmente esse recurso, clique no link abaixo.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

para saber quais configurações de página você pode personalizar no HoloLens 2, visite nossa [página URIs de Configurações](settings-uri-list.md). 
 
![Captura de tela do horário ativo sendo modificado no aplicativo Configurações.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de pesquisa
no modo de pesquisa, o HoloLens 2 se torna uma ferramenta potente para pesquisa visual computacional. em comparação com as edições anteriores, o modo de pesquisa para HoloLens 2 tem as seguintes vantagens:
-   além dos sensores expostos no modo de pesquisa HoloLens (1ª gen), agora fornecemos acesso de sensor IMU, incluindo acelerômetro, giroscópio e magnetômetro.
-   o HoloLens 2 fornece novos recursos que podem ser usados juntamente com o modo de pesquisa. Especificamente, o acesso a APIs articuladas de acompanhamento de mão e acompanhamento de olho que podem oferecer um conjunto mais rico de experimentos.

os pesquisadores agora têm a opção de habilitar o modo de pesquisa em seus dispositivos HoloLens para acessar todos esses fluxos de sensores de imagem bruta externa voltados para o. o modo de pesquisa para HoloLens 2 também fornece acesso às leituras acelerômetro, giroscópio e magnetômetro. Para proteger a privacidade dos usuários, as imagens de câmera de controle de olho bruto não estão disponíveis por meio do modo de pesquisa, mas a direção olhar está disponível por meio de APIs existentes.

Confira a [documentação do modo de pesquisa](/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

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
- foi resolvido um problema que impedia a exibição de um dispositivo HoloLens no explorador de arquivos sobre o MTP (protocolo de transferência de mídia) quando o dispositivo é configurado como um [quiosque de aplicativo único](hololens-kiosk.md). Observe que o MTP (e a conexão USB em geral) ainda podem ser desabilitados usando a política [AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
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
- adicionada uma configuração em **Configurações**  >  **sistema**  >  **Hologramas** que permite que os usuários removam automaticamente todos os hologramas de uma casa mista de realidade quando o dispositivo é desligado.
- corrigido um problema que causava HoloLens aplicativos que alteram seu formato de pixel para renderizar preto no emulador de HoloLens.
- Correção de um bug que causou uma falha durante o logon da íris.
- Correção de um problema sobre downloads de armazenamento repetidos para aplicativos já atuais.
- correção de um bug para impedir que aplicativos de imersão abram Microsoft Edge repetidamente.
- Foi corrigido um problema com as inicializações do aplicativo fotos na inicialização inicial após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versão 1903 – atualização de junho de 2020
- Build 18362,1064

Melhorias e correções na atualização:

- Os gravadores da MRC personalizados têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (headset de imersão))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "obter o áudio do aplicativo" na página de captura da realidade misturada no Portal do dispositivo Windows)
    - MicrophoneGain (o valor atual de "lucro de áudio do Mic" na página de captura da realidade misturada no Portal do dispositivo Windows)
- A API HolographicSpace. userpresence geralmente é desabilitada para aplicativos do Unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo que a configuração seja executada em segundo plano esteja habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity, e 2019.3.4 e posterior.
- corrigido um problema que causava HoloLens aplicativos que alteram seu formato de pixel para renderizar preto no Emulator de HoloLens.
- Corrigido um problema sobre as inicializações do aplicativo fotos na inicialização inicial após a atualização da versão 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versão 2004  
- Build-19041,1103

a principal atualização de software 2020 de maio para o HoloLens 2, *Windows Holographic, versão 2004* inclui um host de novos recursos empolgantes, como suporte para Windows o piloto automático, modo escuro do aplicativo, suporte Ethernet USB para hotspots 5G/LTE e muito mais. para atualizar para a versão mais recente, abra o aplicativo **Configurações**   , vá para  **atualização & segurança** e selecione o botão  **verificar atualizações**   . 

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          pré-configurar e configurar diretamente os novos dispositivos para produção usando Windows autopilot                 |
|       Suporte a FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplique diretamente um pacote de provisionamento de uma unidade USB ao seu HoloLens                              |
|       Status de instalação do aplicativo                 |          verifique se o status de instalação no aplicativo Configurações para aplicativos foi enviado por push para HoloLens 2 via MDM               |
|       Provedores de serviços de configuração (CSPs)   |          Novos provedores de serviços de configuração adicionados para aprimorar os recursos de controle de administrador                 |
|       Suporte a 5G/LTE USB                       |          O recurso Ethernet USB expandido habilita o suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que dão suporte aos modos escuro e claro, melhorando a experiência de exibição        |
|       Comandos de voz                             |          suporte para comandos adicionais de voz do sistema para controlar HoloLens sem intervenção                           |
|       Aprimoramentos de acompanhamento de mão                 |          Melhorias de acompanhamento de mão tornam os botões e as interações de Slate 2D mais precisos                        |
|       Melhorias e correções de qualidade                 |          Vários aprimoramentos de desempenho e confiabilidade do sistema em toda a plataforma                            |

### <a name="support-for-windows-autopilot"></a>suporte para Windows autopilot

Windows o piloto automático para o HoloLens 2 permite que o canal de vendas do dispositivo registre previamente HoloLens em seu locatário do Intune. Quando os dispositivos chegam, eles estão prontos para serem implantados automaticamente como dispositivos compartilhados em seu locatário. Para tirar proveito da autoimplantação, o dispositivo deve se conectar a uma rede durante a primeira tela na instalação usando um USB-C-to-Ethernet.

Depois que um usuário inicia o processo de autoimplantação do AutoPilot, o processo conclui as seguintes etapas:

1. Adicionar o dispositivo ao Azure AD (Azure Active Directory).
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe as políticas, os certificados e os perfis de rede direcionados ao dispositivo.
1. Provisionar o dispositivo.
1. Apresentar a tela de conexão ao usuário.

saiba mais no [guia de avaliação do Windows autopilot para HoloLens 2](hololens2-autopilot.md).

*Entre em contato com seu gerente de conta para participar da versão prévia do piloto automático agora. Os dispositivos prontos para o piloto automático começarão a enviar em breve.*

### <a name="fido2-security-key-support"></a>Suporte à chave de segurança do FIDO2

alguns usuários compartilham um dispositivo HoloLens com outras pessoas em um ambiente corporativo ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. o Fast Identity Online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre diretamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação com base em padrões "inphishável" que pode vir em qualquer fator forma. FIDO é um padrão aberto para autenticação com senha. Ele permite que usuários e organizações entrem em seus recursos sem um nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma embutida em um dispositivo.

Para começar, consulte [habilitar a entrada de chave de segurança sem senha](/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Registro de MDM aprimorado por meio do pacote de provisionamento

os pacotes de provisionamento permitem definir HoloLens configuração por meio de um arquivo de configuração, e não por meio da experiência de HoloLens pronta para uso. anteriormente, os pacotes de provisionamento tinham que ser copiados para o HoloLens memória interna. agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizar em vários dispositivos HoloLens e você pode provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também suportam um campo para se registrar no gerenciamento de dispositivos, portanto, não há nenhuma configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do Windows Configuration Designer do Windows em seu computador.
1. Selecione **Provisionamento HoloLens**  >  **Dispositivos provisionados HoloLens 2 dispositivos**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C em qualquer dispositivo com flash HoloLens. Em seguida, pressione **os botões de** energia para baixo do volume para aplicar o pacote de  +   provisionamento.

### <a name="line-of-business-application-install-status"></a>Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento de aplicativos MDM para aplicativos de linha de negócios é essencial para HoloLens. Administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **Contas** de Configurações Acesso ao trabalho ou à escola  >    >    >  **Clique em suas Informações da**  >  **conta.**

### <a name="additional-csps-and-policies"></a>CSPs e políticas adicionais

Um [CSP (provedor de serviços de configuração)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou excluir definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores implantaram em HoloLens dispositivos. Para ver a lista de CSPs com suporte HoloLens, consulte [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

Novidades nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa configure políticas em Windows dispositivos. Nesta versão, adicionamos novas políticas para HoloLens, que estão listadas aqui. Para saber mais, confira [CSPs de política com suporte HoloLens 2](/windows/client-management/mdm/policies-supported-by-hololens2).  

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

O provedor de serviços de configuração NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, confira [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Suporte expandido de Ethernet USB para dispositivos conectados a 5G/LTE

Foi adicionado suporte para habilitar determinados dispositivos de banda larga móvel, como telefones 5G/LTE e hotspots Wi-Fi, quando eles são conectados ao HoloLens 2 via USB. Esses dispositivos agora são exibidos nas **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos móveis de banda larga que exigem um driver externo.) Essa funcionalidade habilita conexões de alta largura de banda quando Wi-Fi não está disponível e Wi-Fi a conexões não tem desempenho suficiente. Para saber mais sobre dispositivos USB com suporte, [consulte Conexão para Bluetooth dispositivos USB-C e](hololens-connect-devices.md).  

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

![Janelas de modo escuro lado a lado.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, [consulte Usar sua voz para operar HoloLens](hololens-cortana.md). Consulte também [Idiomas com suporte para HoloLens 2](hololens2-language-support.md).  

### <a name="cortana-updates"></a>Cortana atualizações

O aplicativo atualizado se integra ao Microsoft 365 para ajudá-lo a fazer mais em seus dispositivos (atualmente, US-English apenas). No HoloLens 2, Cortana dá mais suporte a determinados comandos específicos do dispositivo, como ajustar o volume ou reiniciar. Essas opções agora são suportadas pelos novos comandos de voz do sistema. Saiba mais sobre o novo Cortana em nosso [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibragem de exibição ativo. Esse recurso melhora a estabilidade e o alinhamento dos hologramas. Agora eles permanecem no local quando você move a cabeça de um lado para outro.
- Corrigido um bug em que Wi-Fi streaming para HoloLens interrompido periodicamente. Se um aplicativo indicar que ele precisa de streaming de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Corrigida uma trava de dispositivo que ocorreu durante o streaming no modo de pesquisa.
- Corrigido um bug em que, em alguns casos, o usuário correto não seria exibido na tela de logon ao retomar uma sessão.
- Corrigido um problema em que os usuários não podiam exportar logs de MDM por meio **Configurações**.
- Corrigido um problema em que a precisão do acompanhamento ocular imediatamente após a configuração pronta para uso poderia ser menor do que o esperado.
- Corrigido um problema em que o subsistema de acompanhamento ocular falhava ao inicializar ou executar a calibragem em determinadas condições.
- Corrigido um problema em que a calibragem ocular seria solicitado a um usuário já calibrado.
- Corrigido um problema em que um driver falhava durante a calibragem ocular.
- Corrigido um problema em que pressionamentos repetidos do botão de energia podiam causar um tempo de tempo de sistema de 60 segundos e uma falha de shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um **botão Compartilhar** no Hub de Comentários para que os usuários possam compartilhar comentários com mais facilidade.
- Corrigido um bug em que o RoboRaid wan não estava instalado corretamente.

### <a name="known-issues"></a>Problemas conhecidos

- Um problema com a linguagem do sistema zh-CN impede que os comandos de voz capturem uma realidade misturada ou exibem o endereço IP do dispositivo.
- Um problema exige que você iniciar o aplicativo Cortana depois de iniciar o dispositivo para usar a ativação de voz "Hey Cortana". Se você tiver atualizado de um build 18362, também poderá ver um segundo peças de aplicativo para a versão anterior do aplicativo Cortana que não funciona mais em **Iniciar**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versão 1903 – Atualização de maio de 2020 
- Build 18362.1061

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
