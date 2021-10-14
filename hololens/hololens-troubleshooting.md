---
title: HoloLens Solução de problemas de dispositivo
description: mantenha-se atualizado sobre as soluções mais comuns para HoloLens problemas de dispositivo e técnicas de solução de problemas.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, bug, solução de problemas, correção, ajuda, suporte, HoloLens, emulador
ms.openlocfilehash: 247cf9d34da723e587f6796178ad9a917b93ac08
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964557"
---
# <a name="device-troubleshooting"></a>Solução de problemas de dispositivo

este artigo descreve como resolver vários problemas comuns de HoloLens.

>[!IMPORTANT]
> Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de **20% a 40%** da capacidade da bateria, se possível. As [luzes indicadoras de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas sob o botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.

<a id="list"></a>

**Problemas conhecidos**
- [Toda vez que a potência vai para 18%, o dispositivo é encerrado repentinamente automaticamente](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive O aplicativo UWP não funciona para usuários do Azure AD](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Por que vejo 0x80180014 durante o piloto automático?](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store código de erro 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge falha ao iniciar o microfone](#microsoft-edge-fails-to-start-the-microphone)
- [**Fixo** -o vídeo da assistência remota é congelado após 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [Logon automático solicita o logon](#auto-login-asks-for-log-in)
- [falha ao iniciar o Microsoft Edge](#microsoft-edge-fails-to-launch)
- [O teclado não muda para caracteres especiais](#keyboard-doesnt-switch-to-special-characters)
- [**Corrigido** – o download de arquivos bloqueados não mostra erro](#downloading-locked-files-doesnt-error)
- [Tempo limite de carregamento/download do arquivo do portal do dispositivo **fixo**](#device-portal-file-uploaddownload-times-out)
- [Tela azul após o cancelamento do registro do insider preview em um dispositivo atualizado com uma compilação Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive não carrega imagens automaticamente](#onedrive-doesnt-automatically-upload-pictures)

**Geral**
- [HoloLens não está respondendo ou não será iniciado](#hololens-is-unresponsive-or-wont-start)
- [Erro de "pouco espaço em disco"](#low-disk-space-error)
- [Falha na calibragem](#calibration-fails)
- [não é possível entrar porque o meu HoloLens foi configurado anteriormente para outra pessoa](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [O Unity não está funcionando](#unity-isnt-working)
- [Windows O portal do dispositivo não está funcionando corretamente](#windows-device-portal-isnt-working-correctly)
- [o Emulator de HoloLens não está funcionando](#the-hololens-emulator-isnt-working)

**Entrada**
- [Os comandos de voz não estão funcionando](#voice-commands-arent-working)
- [A entrada manual não está funcionando](#hand-input-isnt-working)

**Conectividade**
- [Não é possível conectar-se ao Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivos externos** 
- [Bluetooth dispositivos não estão emparelhando](#bluetooth-devices-arent-pairing)
- [O microfone USB-C não está funcionando](#usb-c-microphone-isnt-working)
- [os dispositivos listados como disponíveis no Configurações não funcionam](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Toda vez que a potência vai para 18%, o dispositivo é encerrado repentinamente automaticamente

Há uma questão conhecida conhecida em que quando o dispositivo atinge 18% da bateria, ele será desligado inesperadamente. Esse é um problema de software, não um problema de hardware ou bateria; portanto, não troque os dispositivos por isso. Se você não tiver certeza se o problema corresponde a esse bug, por favor:

1. Garantir que os diagnósticos opcionais estejam habilitados em seus dispositivos
1. Reproduzir o problema
1. Enviar um problema de [Hub de comentários](hololens-feedback.md)
1. Compartilhar a URL do problema de comentários
1. [Entre em contato com o suporte](https://aka.ms/hololenssupport)

[Voltar para a lista](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive O aplicativo UWP não funciona para usuários do Azure AD

se você usar OneDrive para negócios usando sua conta do Azure AD, você poderá ter encontrado um erro ao entrar em sua caixa de entrada OneDrive aplicativo. não ser capaz de entrar no OneDrive aplicativo não afeta os carregamentos automáticos de imagens e vídeos capturados pelo aplicativo de câmera. seus arquivos ainda podem ser salvos e acessados a partir do OneDrive for Business armazenamento em nuvem. as equipes de OneDrive e HoloLens estão trabalhando no problema.

### <a name="workarounds"></a>Soluções Alternativas

pré-requisito: os clientes podem usar Microsoft Edge e o so do dispositivo é atualizado para um Windows Holographic, 21H1 build ou mais recente.

Se você estiver enfrentando esse problema, tente um dos seguintes:

- os usuários podem acessar diretamente o OneDrive For Business de Microsoft Edge e interagir com seus arquivos no navegador.
- os usuários podem instalar o aplicativo OneDrive PWA no HoloLens baixando-o do Microsoft Edge. Isso permitirá que os usuários exibam e gerenciem arquivos no dispositivo novamente. leia e siga estas [instruções para instalar o aplicativo OneDrive PWA no seu HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Voltar para a lista](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Por que vejo 0x80180014 durante o piloto automático?

esse erro normalmente é encontrado durante a redefinição do dispositivo e o reuso de fluxos em que um dispositivo HoloLens passou por meio do piloto automático pelo menos uma vez. para resolver esse problema, [exclua o dispositivo de Microsoft Intune](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) e redefina-o novamente para concluir o fluxo do autopilot.

Para obter mais informações, consulte [as etapas de solução de problemas na página do piloto automático.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store código de erro 0x80131500

alguns usuários podem experimentar o Microsoft Store funcionar não conforme o esperado e ver o código de erro 0x80131500. esse é um problema causado pela região definida no HoloLens não estar disponível no aplicativo Microsoft Store no HoloLens. Se você encontrar o código de erro 0x80131500, para solucionar o problema:

1. defina Configurações > hora & idioma > região > país ou região, para um dos seguintes:
    - Estados Unidos, Japão, China, Alemanha, Canadá, Reino Unido, Irlanda, França, Austrália, Nova Zelândia.
1. Reinicie o aplicativo da loja.
1. Para que o dispositivo inteiro reflita a alteração, será necessário reiniciar o dispositivo.

a equipe de HoloLens está trabalhando para adicionar suporte para mais regiões.

veja aqui os [países para comprar HoloLens 2.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge falha ao iniciar o microfone

quando os usuários que usam o Microsoft Edge o microfone pode falhar ao iniciar, portanto não podem ser usados para interagir com o Edge no HoloLens. esse problema conhecido está relacionado à versão do aplicativo Microsoft Edge, não repare seu dispositivo para uma versão anterior, pois isso não corrigirá esse problema.

### <a name="who-is-affected"></a>Who é afetado?

usuários que têm Microsoft Edge versão 93, 94 ou 95.
você pode verificar qual versão do Microsoft Edge você tem usando o aplicativo Microsoft Store e, em seguida, selecione o botão "ver mais" representado pelo **...** em seguida, selecione **Downloads e atualizações**.

### <a name="work-around"></a>Solução alternativa

a correção atual está na versão 96, que está disponível para os usuários que se registraram no Microsoft Edge insiders. isso é diferente de registrar seu dispositivo como um Windows insider. Leia estas instruções para obter detalhes sobre [como se registrar no programa Insider do Edge.](hololens-new-edge.md#microsoft-edge-insider-channels)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>O vídeo da assistência remota congela após 20 minutos

> [!NOTE]
> Há uma versão mais recente do auxílio remoto que tem uma correção para esse problema. [Atualize o auxílio remoto](holographic-store-apps.md#update-apps) para a versão mais recente para evitar esse problema.

> [!NOTE]
> devido a essa gravidade do problema conhecido, fizemos temporariamente uma pausa na disponibilidade de Windows Holographic, versão 21H1. A compilação 21H1 agora está disponível novamente, portanto, os dispositivos podem ser novamente atualizados para a compilação de 21H1 mais recente.

na última versão do [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), alguns usuários da assistência remota experimentaram o congelamento do vídeo durante chamadas de 20 minutos. Esse é um **problema conhecido**.

### <a name="workarounds"></a>Soluções Alternativas

Se não for possível atualizar o auxílio remoto para uma compilação mais nova, tente a seguinte solução alternativa.

#### <a name="restart-in-between-calls"></a>Reinicializar entre chamadas

Se suas chamadas estiverem passando por um período de 20 minutos e você estiver enfrentando esse problema, tente reinicializar o dispositivo. A reinicialização do dispositivo entre as chamadas de assistência remota atualizará o dispositivo e o colocará em um bom estado.

para reiniciar rapidamente um dispositivo no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) abra o menu iniciar e selecione o ícone usuário e, em seguida, selecione **reiniciar**.

[Voltar para a lista](#list)

## <a name="auto-login-asks-for-log-in"></a>Logon automático solicita o logon

Um HoloLens 2 pode ser configurado para fazer logon automaticamente por meio de opções de entrada de contas do **Configurações**  ->    ->    -> e, em Obrigatório, definir o valor como **Nunca**. Alguns usuários podem precisar fazer logoff no dispositivo novamente ao atualizar um dispositivo com uma atualização substancialmente grande, como uma atualização de recurso. Esse é um **problema conhecido.**

Exemplo de quando isso pode ocorrer:

- Atualizando um dispositivo do Windows Holographic, versão 2004 (Build 19041.xxxx) para Windows Holographic, versão 21H1 (Build 20346.xxxx)
- Atualizando um dispositivo para fazer uma grande atualização no mesmo build principal, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2
- Atualizando um dispositivo de uma imagem de fábrica para a imagem mais recente

Isso não deve ocorrer durante:

- Dispositivos que estão fazendo uma atualização de manutenção mensal

Trabalhar em torno de métodos:

- Métodos de login, como PIN, Senha, Íris, Autenticação da Web ou chaves FIDO2.
- Se o PIN do dispositivo não puder ser lembrado e outros métodos de autenticação não estão disponíveis, um usuário poderá usar o modo [de reflashing manual](hololens-recovery.md#manual-procedure).

[Voltar para a lista](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge falha ao iniciar

> [!NOTE]
> Esse problema foi criado originalmente com a versão de envio Microsoft Edge em mente. Esse problema pode ser resolvido na [nova Microsoft Edge](hololens-new-edge.md). Se não estiver, faça comentários.

Alguns clientes relataram um problema em que Microsoft Edge falha ao iniciar. Para esses clientes, o problema persiste por meio da reinicialização e não é resolvido com Windows ou atualizações de aplicativo. Se você estiver enfrentando esse problema e tiver confirmado que o [Windows](hololens-updates.md#manually-check-for-updates)está atualizado, arquiva um bug do aplicativo Hub de [Comentários](hololens-feedback.md) com a seguinte categoria e sub-categoria: Instalar e atualizar o > Baixando, instalando e configurando a atualização Windows.

Não há soluções alternativas conhecidas, pois não foi possível raizizar o problema até o momento. Arquivar um bug por meio do Hub de Comentários ajudará nossa investigação! Esse é um **problema conhecido.**

[Voltar para a lista](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>O teclado não alterna para caracteres especiais

Há um problema durante o OOBE, em que quando o usuário escolheu uma conta de trabalho ou de estudante e está inserindo sua senha, tentar alternar para os caracteres especiais no teclado tocando no botão &123 não muda para caracteres especiais. Esse é um **problema conhecido.**

Work-arounds:

- Feche o teclado e reabra-o tocando no campo de texto.
- Insira incorretamente sua senha. Quando o teclado for relançado na próxima vez, ele funcionará conforme o esperado.
- Autenticação da Web, feche o teclado e **selecione Entrar de outro dispositivo.**
- Se inserir apenas números, um usuário poderá pressionar e manter determinadas chaves para abrir um menu expandido.
- Usando um teclado USB.

Isso não afeta:

- Usuários que optam por usar uma conta pessoal.

[Voltar para a lista](#list)

## <a name="downloading-locked-files-doesnt-error"></a>O download de arquivos bloqueados não é um erro

> [!NOTE]
> Esse é um **problema conhecido** que foi corrigido no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)– Atualização de julho de 2021.

Nos builds anteriores do Windows Holographic, ao tentar baixar um arquivo bloqueado, o resultado seria uma página de erro HTTP. No Windows Holographic, versão 21H1, a tentativa de baixar um arquivo bloqueado não resulta em nada visível, o arquivo não é baixado e não há nenhum erro.

[Voltar para a lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal de Dispositivos o tempo de upload/download do arquivo
> [!NOTE]
> Esse é um **problema conhecido** que foi corrigido no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)– Atualização de julho de 2021. Se você desabilitou anteriormente a Conexão SSL como parte da solução alternativa, é altamente recomendável habilita-la.

Alguns clientes descobriram que, ao tentar carregar ou baixar arquivos, a operação pode parecer travada e, em seguida, o tempo for concluído ou nunca ser concluído. Isso é separado do problema conhecido 'arquivo[bloqueado'](#downloading-locked-files-doesnt-error) – isso afeta Windows Holographic, versões 2004, 20H2 e 21H1 builds no mercado. O problema foi causado por um bug Portal de Dispositivos tratamento de determinadas solicitações e é atingido de forma mais consistente ao usar https, que é o padrão.

### <a name="workaround"></a>Solução alternativa

Essa solução alternativa, que se aplica igualmente Wi-Fi e UsbNcm, é desabilitar a opção "obrigatório" em "Conexão SSL". Para fazer isso, navegue até Portal de Dispositivos, **Sistema** e selecione a **página Preferências.** Na seção **Segurança do** Dispositivo, localize Conexão **SSL** e desmarque para desabilitar **Obrigatório.**

Em seguida, o usuário deve ir para http://, não https:// (endereço IP) e recursos como upload e download de arquivo funcionarão.

[Voltar para a lista](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Tela azul após o unenrolling da versão prévia do Insider em um dispositivo com um build do Insider

Esse é um problema que afeta os usuários que estavam em um build de visualização do Insider, reemerrou o HoloLens 2 com um novo build de visualização do insider e, em seguida, foi desaloculado do programa Insider. Esse é um **problema conhecido.**

Isso não afeta:

- Usuários que não estão inscritos no Windows Insider
- Insiders:
    - Se um dispositivo tiver sido inscrito desde que os builds do Insider eram da versão 18362.x
    - Se eles piscaram um build 19041.x assinado pelo Insider e permanecem inscritos no programa Insider

Work-around:

- Evitar o problema
    - Flash de um build não interno. Uma das atualizações mensais regulares.
    - Mantenha-se no Insider Preview
- Reflash o dispositivo

    1. Coloque o [HoloLens 2 no modo de flash](hololens-recovery.md) manualmente, completamente ligado enquanto não se conecta. Em seguida, enquanto Volume up, toque no botão Ligar.

    1. Conexão no computador e abra o Advanced Recovery Companion.

    1. Flash do HoloLens 2 para o build padrão.

[Voltar para a lista](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive não carrega imagens automaticamente

O OneDrive aplicativo para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante. Esse é um **problema conhecido.**

Soluções alternativas:

- Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor. Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte à dupla login). No seu perfil conta Microsoft no OneDrive você pode habilitar o upload automático de rolagem da câmera em segundo plano.

- Se você não puder usar com segurança uma conta de conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do OneDrive aplicativo. Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no OneDrive aplicativo. Selecione o **+** botão e escolha **Upload**. Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.

[Voltar para a lista](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens está sem resposta ou não iniciará

Se o HoloLens não for iniciar:

- Se os LEDs ao lado do botão de energia não piscarem ou apenas um LED piscar brevemente, talvez seja necessário cobrar o [HoloLens.](hololens2-charging.md#charging-the-device)
- Se os LEDs se acenderem quando você pressionar o botão de energia, mas você não conseguir ver nada nas exibições, faça uma [redefinição de](hololens-recovery.md#hard-reset-procedure)disco rígido do dispositivo .

Se o HoloLens ficar congelado ou sem resposta:

- Desligue o HoloLens pressionando o botão de energia até que todos os cinco LEDs se desliguem ou por 15 segundos se os LEDs não responderem. Para iniciar o HoloLens, pressione o botão de energia novamente.

Se essas etapas não funcionarem, você poderá tentar recuperar seu dispositivo [HoloLens 2](hololens-recovery.md) ou [HoloLens (1ª geração).](hololens1-recovery.md)

[Voltar para a lista](#list)

## <a name="low-disk-space-error"></a>Erro "Espaço em Disco Baixo"

Você precisará liberar algum espaço de armazenamento fazendo um ou mais dos seguintes:

- Exclua alguns espaços nãoutilados. Vá para **Configurações** System Spaces , selecione um espaço que você não precisa mais  >    >  e, em seguida, selecione **Remover**.
- Remova alguns dos hologramas que você colocou.
- Exclua algumas imagens e vídeos do aplicativo Fotos.
- Desinstale alguns aplicativos do HoloLens. Na lista **Todos os apps,** toque e mantenha o aplicativo que você deseja desinstalar e, em seguida, selecione **Desinstalar**.

[Voltar para a lista](#list)

## <a name="calibration-fails"></a>Falha na calibragem

A calibragem deve funcionar para a maioria das pessoas, mas há casos em que a calibragem falha.
  
Alguns possíveis motivos para a falha de calibragem incluem:

- Ficando confuso e não seguindo os destinos de calibragem
- Visor do dispositivo sujo ou com rascunho ou visor do dispositivo não posicionado corretamente
- Óculos sujos ou com rascunho
- Determinados tipos de lentes de contato e óculos (lentes de contato coloridas, algumas lentes de contato tóricas, óculos de bloqueio de IR, alguns óculos de alta receita, óculos escuros ou semelhantes)
- Mais pronunciada adeção e algumas extensões de cíoa
- Quadros de óculos grandes ou de óculos se eles estão bloqueando o dispositivo de ver seus olhos
- Determinadas coisas de olho, condições de olho ou olho, como olhos estreitos, malhas longas, amblyopia, nystagmus, alguns casos de LASIK ou outras óculos de olho

Se a calibragem não for bem-sucedida, tente:

- Limpando o visor do dispositivo
- Limpando seus óculos
- Esvasar o visor do dispositivo o mais próximo possível dos olhos
- Mover objetos no visor para fora do caminho (como pelos)
- A ligar uma luz em seu quarto ou sair da área de trabalho direta

Se você seguiu todas as diretrizes e a calibragem ainda está falhando, desabilite o prompt de calibragem Configurações. Além disso, nos avise fazendo comentários no [Hub de Comentários.](hololens-feedback.md)

Confira também informações relacionadas para a solução de problemas de cor [ou brilho da imagem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

A configuração de IPD não é aplicável HoloLens 2, pois as posições dos olhos são computadas pelo sistema. 

[Voltar para a lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Não é possível entrar porque minha HoloLens foi configurada anteriormente para outra pessoa

Você pode [colocar o dispositivo no Modo de Flash **e** usar o Avançado Recovery Companion](hololens-recovery.md#clean-reflash-the-device) para recuperar o dispositivo.

[Voltar para a lista](#list)


## <a name="unity-isnt-working"></a>O Unity não está funcionando

- Confira [Instalar as ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Unity recomendada para HoloLens desenvolvimento.
- Problemas conhecidos com o Unity HoloLens Technical Preview estão documentados [nos HoloLens do Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Voltar para a lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portal de Dispositivos está funcionando corretamente

- O recurso De visualização ao vivo na captura de Realidade Misturada pode exibir vários segundos de latência.

- Na página Entrada Virtual, os controles Gesto e Rolagem na seção Gestos Virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de habilitar o Modo de Desenvolvedor Configurações, pode levar alguns segundos antes que a opção para ativar o Portal de Dispositivos seja habilitada.

[Voltar para a lista](#list)

## <a name="the-hololens-emulator-isnt-working"></a>O HoloLens Emulator não está funcionando

Informações sobre o HoloLens emulador estão localizadas em nossa documentação do desenvolvedor.  Leia mais sobre [como solucionar problemas do HoloLens emulador](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).


- Nem todos os aplicativos no Microsoft Store são compatíveis com o emulador. Por exemplo, Conker e Fragmentos Não são reproduzíveis no emulador.
- Você não pode usar a webcam do computador no Emulator.
- O recurso Live Preview do Windows Portal de Dispositivos não funciona com o emulador. Você ainda pode capturar vídeos e imagens de Realidade Misturada.

[Voltar para a lista](#list)

## <a name="voice-commands-arent-working"></a>Os comandos de voz não estão funcionando

Se Cortana estiver respondendo aos comandos de voz, certifique-se de Cortana está ligado. Na lista Todos os apps, selecione **Cortana**  >    >  **Menu Notebook Configurações** para fazer  >   alterações. Para saber mais sobre o que você pode dizer, [consulte Usar sua voz com HoloLens](hololens-cortana.md).

No HoloLens (1ª geração), o reconhecimento de fala integrado não é configurável. Ele está sempre ligado. No HoloLens 2, você pode optar por ativar o reconhecimento de fala e Cortana durante a instalação do dispositivo.

Se o HoloLens 2 não estiver respondendo à sua voz, certifique-se de que o reconhecimento de fala está ligado. Vá para **Iniciar Configurações**  >    >  **De**  >  **Privacidade e** a ligue o **Reconhecimento de Fala.**

[Voltar para a lista](#list)

## <a name="hand-input-isnt-working"></a>A entrada da mão não está funcionando

Para garantir que HoloLens possa ver suas mãos, você precisa mantê-las no quadro de gestos.  A Página De Realidade Misturada fornece comentários que permitem saber quando suas mãos são rastreadas.  Os comentários são diferentes em diferentes versões do HoloLens:

- No HoloLens (1ª geração), o cursor de olhar muda de um ponto para um anel
- No HoloLens 2, um cursor de ponta do dedo é exibido quando sua mão está perto de um slate e um raio de mão aparece quando os slates estão mais distantes

Muitos aplicativos imersivos seguem padrões de entrada semelhantes à Home de Realidade Misturada.  Saiba mais sobre como usar a entrada manual [HoloLens (1ª geração)](hololens1-basic-usage.md#use-hololens-with-your-hands) [e HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se você estiver usando óculos, observe que alguns tipos de óculos não funcionam com o acompanhamento de mão.  Um exemplo comum são as máscaras de borracha preta, que tendem a absorver a luz e não são escolhidas pela câmera de profundidade.  Se seu trabalho envolve óculos de borracha, recomendamos tentar uma cor mais clara, como azul ou cinza.  Outro exemplo são grandes óculos de escuro, que tendem a obscurecer a forma da sua mão. Recomendamos o uso de máscaras que sejam o mais adequado possível para melhores resultados.

Se o visor tiver impressões digitais ou impressões digitais, use a limpeza de microfibra que veio com a HoloLens para limpar a luz do visor.

[Voltar para a lista](#list)

## <a name="cant-connect-to-wi-fi"></a>Não é possível se conectar ao Wi-Fi

Aqui estão algumas ações que você pode tentar se não conseguir conectar seu HoloLens a uma rede Wi-Fi:

- Verifique se o Wi-Fi está ligado. Para verificar, use o gesto Iniciar e, em seguida, **selecione Configurações**  >  **Rede &amp;**  >  **Wi-Fi da Internet.** Se o Wi-Fi estiver ligado, tente desligá-lo e, em seguida, ligue novamente.
- Aproxime-se do roteador ou do ponto de acesso.
- Reinicie o roteador Wi-Fi e, em [seguida, reinicie HoloLens](hololens-recovery.md). Tente se conectar novamente.
- Se nenhuma dessas ações funcionar, verifique se o roteador está usando o firmware mais recente. Você pode encontrar essas informações no site do fabricante.

[Voltar para a lista](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth dispositivos não estão emparelhando

Se você estiver tendo problemas para [emparelhar um dispositivo Bluetooth ,](hololens-connect-devices.md)tente o seguinte:

- Vá para **Configurações**  >  **Dispositivos** e certifique-se de que Bluetooth está ligado. Se estiver, desligue-o e ligue-o novamente.
- Certifique-se de que seu Bluetooth dispositivo está totalmente carregado ou se tem baterias novas.
- Se você ainda não conseguir se conectar, [reinicie o HoloLens](hololens-recovery.md).

[Voltar para a lista](#list)

## <a name="usb-c-microphone-isnt-working"></a>O microfone USB-C não está funcionando

Esteja ciente de que alguns microfones USB-C relatam-se incorretamente como um microfone *e um* alto-falante. Esse é um problema com o microfone e não com HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

No **Configurações** do sistema, de definido explicitamente os  ->    ->  alto-falantes integrados **(Driver de** Áudio de Recurso Análogo) como **o dispositivo padrão**. HoloLens deve se lembrar dessa configuração mesmo se o microfone for removido e reconectado posteriormente.

![Solução de problemas de microfones USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Os dispositivos listados como disponíveis Configurações não funcionam

HoloLens (1ª geração) não dá suporte a Bluetooth de áudio. Bluetooth de áudio, como alto-falantes e headsets, podem aparecer como disponíveis em HoloLens configurações, mas não têm suporte.

HoloLens 2 dá suporte à Bluetooth de áudio A2DP para reprodução estéreo. O Bluetooth de mãos livres que permite a captura de microfone de um periférico Bluetooth não tem suporte no HoloLens 2.

Se você estiver tendo problemas para usar um Bluetooth, certifique-se de que ele seja um dispositivo com suporte. Os dispositivos com suporte incluem o seguinte:

- Teclados QWERTY Bluetooth idioma inglês (você pode usá-lo em qualquer lugar em que use o teclado holográfico).
- Bluetooth mouses.
- O [HoloLens clique em](hololens1-clicker.md).

Você pode emparelhar outros Bluetooth dispositivos HID e GATT com seus HoloLens. No entanto, talvez seja preciso instalar aplicativos de parceiros correspondentes do Microsoft Store para realmente usar os dispositivos.

[Voltar para a lista](#list)
