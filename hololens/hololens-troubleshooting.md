---
title: HoloLens Solução de problemas de dispositivo
description: Mantenha-se atualizado sobre as soluções mais comuns para HoloLens de dispositivo e técnicas de solução de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 9/30/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, bug, solução de problemas, correção, ajuda, suporte, HoloLens, emulador
ms.openlocfilehash: 3c4d6e22660e365acd2c3aca3119632c73926391
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364617"
---
# <a name="device-troubleshooting"></a>Solução de problemas de dispositivo

Este artigo descreve como resolver vários problemas HoloLens comuns.

>[!IMPORTANT]
> Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de **20% a 40%** da capacidade da bateria, se possível. As [luzes indicadoras de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas sob o botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.

<a id="list"></a>

**Problemas conhecidos**
- [Sempre que a energia chega a 18%, o dispositivo é desligado automaticamente de repente](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [O vídeo do Remote Assist congela após 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [O logon automático solicita logon](#auto-login-asks-for-log-in)
- [Microsoft Edge falha ao iniciar](#microsoft-edge-fails-to-launch)
- [O teclado não alterna para caracteres especiais](#keyboard-doesnt-switch-to-special-characters)
- [Baixar arquivos bloqueados não mostra o erro](#downloading-locked-files-doesnt-error)
- [Portal de Dispositivos o tempo de upload/download do arquivo](#device-portal-file-uploaddownload-times-out)
- [Tela azul após o unenrolling da versão prévia do Insider em um dispositivo com um build do Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive não carrega imagens automaticamente](#onedrive-doesnt-automatically-upload-pictures)

**Geral**
- [HoloLens está sem resposta ou não iniciará](#hololens-is-unresponsive-or-wont-start)
- [Erro "Espaço em Disco Baixo"](#low-disk-space-error)
- [Falha na calibragem](#calibration-fails)
- [Não é possível entrar porque minha HoloLens foi configurada anteriormente para outra pessoa](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [O Unity não está funcionando](#unity-isnt-working)
- [Windows Portal de Dispositivos está funcionando corretamente](#windows-device-portal-isnt-working-correctly)
- [O HoloLens Emulator não está funcionando](#the-hololens-emulator-isnt-working)

**Entrada**
- [Os comandos de voz não estão funcionando](#voice-commands-arent-working)
- [A entrada da mão não está funcionando](#hand-input-isnt-working)

**Conectividade**
- [Não é possível se conectar ao Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivos externos** 
- [Bluetooth dispositivos não estão emparelhando](#bluetooth-devices-arent-pairing)
- [O microfone USB-C não está funcionando](#usb-c-microphone-isnt-working)
- [Os dispositivos listados como disponíveis Configurações não funcionam](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Sempre que a energia chega a 18%, o dispositivo é desligado automaticamente de repente

Há um problema conhecido em que quando o dispositivo atinge 18% da bateria, ele será desligado inesperadamente. Esse é um problema de software, não um problema de hardware ou bateria, portanto, não troque dispositivos por isso. Se você não tiver certeza se o problema corresponde a esse bug, por favor:

1. Verifique se os diagnósticos opcionais estão habilitados em seus dispositivos
1. Reproduzir o problema
1. Enviar um problema [do Hub de Comentários](hololens-feedback.md)
1. Compartilhar a URL do problema de comentários
1. [Entre em contato com o suporte](https://aka.ms/hololenssupport)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>O vídeo do Remote Assist congela após 20 minutos

> [!NOTE]
> Há uma versão mais recente do Remote Assist que tem uma correção para esse problema. Atualize [o Remote Assist](holographic-store-apps.md#update-apps) para a versão mais recente para evitar esse problema.

> [!NOTE]
> Devido à severidade desse problema conhecido, pausamos temporariamente a disponibilidade do Windows Holographic, versão 21H1. O build 21H1 agora está disponível novamente, portanto, os dispositivos podem ser atualizados novamente para o build 21H1 mais recente.

Na versão mais recente do [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)alguns usuários do Remote Assist experimentaram o congelamento de vídeo durante chamadas por mais de 20 minutos. Esse é um **problema conhecido.**

### <a name="workarounds"></a>Soluções Alternativas

Se você não conseguir atualizar o Remote Assist para um build mais recente, tente a seguinte explicação.

#### <a name="restart-in-between-calls"></a>Reiniciar entre chamadas

Se suas chamadas estão passando por um período de 20 minutos e você estiver enfrentando esse problema, tente reinicializar seu dispositivo. Reinicializar o dispositivo entre chamadas de Assistência Remota atualizará seu dispositivo e o colocará novamente em um bom estado.

Para reiniciar rapidamente um dispositivo no [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1) abra o menu Iniciar e selecione o ícone de usuário e, em seguida, **selecione Reiniciar**.

[Voltar para a lista](#list)

## <a name="auto-login-asks-for-log-in"></a>O logon automático solicita logon

Um HoloLens 2 pode ser configurado para fazer logon automaticamente por meio **de** Configurações Opções de Entrada de Contas  ->    ->    -> e, em Obrigatório, definir o valor como **Nunca**. Alguns usuários podem precisar fazer logoff no dispositivo novamente ao atualizar um dispositivo com uma atualização substancialmente grande, como uma atualização de recurso. Esse é um **problema conhecido.**

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

Alguns clientes relataram um problema em que Microsoft Edge falha ao iniciar. Para esses clientes, o problema persiste por meio da reinicialização e não é resolvido com Windows ou atualizações de aplicativo. Se você estiver enfrentando esse problema e tiver confirmado que o [Windows](hololens-updates.md#manually-check-for-updates)está atualizado, arquiva um bug do aplicativo Hub de [Comentários](hololens-feedback.md) com a seguinte categoria e subgrade: Instalar e atualizar o > Baixando, instalando e configurando a atualização Windows.

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

Em builds anteriores do Windows Holographic, ao tentar baixar um arquivo bloqueado, o resultado seria uma página de erro HTTP. No Windows Holographic, versão 21H1, tentar baixar um arquivo bloqueado não resulta em nada visível que aconteça, o arquivo não é baixado e não há nenhum erro.

[Voltar para a lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal de Dispositivos o tempo de upload/download do arquivo
> [!NOTE]
> Esse é um **problema conhecido** que foi corrigido no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)– Atualização de julho de 2021. Se você desabilitou anteriormente a Conexão SSL como parte da solução alternativa, é altamente recomendável habilita-la.

Alguns clientes descobriram que, ao tentar carregar ou baixar arquivos, a operação pode parecer travada e, em seguida, o tempo for concluído ou nunca ser concluído. Isso é separado do problema conhecido 'arquivo[bloqueado'](#downloading-locked-files-doesnt-error) – isso afeta Windows Holographic, versões 2004, 20H2 e 21H1 builds no mercado. O problema foi causado por um bug Portal de Dispositivos tratamento de determinadas solicitações e é atingido de forma mais consistente ao usar https, que é o padrão.

### <a name="workaround"></a>Solução alternativa

Essa solução alternativa, que se aplica igualmente a Wi-Fi e UsbNcm, é desabilitar a opção "obrigatório" em "Conexão SSL". Para fazer isso, navegue até Portal de Dispositivos, **Sistema** e selecione a **página Preferências.** Na seção **Segurança do** Dispositivo, localize Conexão **SSL** e desmarque para desabilitar **Obrigatório.**

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

O OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante. Esse é um **problema conhecido.**

Soluções alternativas:

- Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor. Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte à dupla login). No seu perfil conta Microsoft no OneDrive você pode habilitar o upload automático de rolagem da câmera em segundo plano.

- Se você não puder usar com segurança um conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do aplicativo OneDrive. Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no OneDrive aplicativo. Selecione o **+** botão e escolha **Upload**. Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.

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

- Exclua alguns espaços nãoutilados. Vá para **Configurações** System Spaces , selecione um espaço que você não precisa mais e, em  >    >  seguida, **selecione Remover**.
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
- Determinados tipos de lentes de contato e óculos (lentes de contato coloridas, algumas lentes de contato tóricas, óculos de bloqueio de IR, alguns óculos de alta receita, óculos de sol ou semelhantes)
- Mais pronunciada adeção e algumas extensões de cíoa
- Quadros de óculos grandes ou de óculos se eles estão bloqueando o dispositivo de ver seus olhos
- Determinadas coisas de olho, condições de olho ou olho, como olhos estreitos, malhas longas, amblyopia, nystagmus, alguns casos de LASIK ou outras óculos de olho

Se a calibragem não for bem-sucedida, tente:

- Limpando o visor do dispositivo
- Limpando seus óculos
- Esvasar o visor do dispositivo o mais próximo possível dos olhos
- Mover objetos no visor para fora do caminho (como pelos)
- A ligar uma luz em seu quarto ou sair da área de trabalho direta

Se você seguiu todas as diretrizes e a calibragem ainda está falhando, você pode desabilitar o prompt de calibragem Configurações. Além disso, nos avise fazendo comentários no [Hub de Comentários.](hololens-feedback.md)

Consulte também informações relacionadas para a solução de problemas de cor [ou brilho da imagem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

A configuração de IPD não é aplicável HoloLens 2, pois as posições dos olhos são computadas pelo sistema. 

[Voltar para a lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Não é possível entrar porque minha HoloLens foi configurada anteriormente para outra pessoa

Você pode [colocar o dispositivo no Modo de Flash **e** usar o Avançado Recovery Companion](hololens-recovery.md#clean-reflash-the-device) para recuperar o dispositivo.

[Voltar para a lista](#list)


## <a name="unity-isnt-working"></a>O Unity não está funcionando

- Confira [Instalar as ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Unity recomendada para HoloLens desenvolvimento.
- Problemas conhecidos com o Unity HoloLens Technical Preview estão documentados nos [fóruns HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Voltar para a lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portal de Dispositivos está funcionando corretamente

- O recurso De visualização ao vivo na captura de Realidade Misturada pode exibir vários segundos de latência.

- Na página Entrada Virtual, os controles Gesto e Rolagem na seção Gestos Virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de habilitar o Modo de Desenvolvedor Configurações, pode levar alguns segundos antes que a opção para ativar o Portal de Dispositivos está habilitada.

[Voltar para a lista](#list)

## <a name="the-hololens-emulator-isnt-working"></a>O HoloLens Emulator não está funcionando

Informações sobre o HoloLens emulador estão localizadas em nossa documentação do desenvolvedor.  Leia mais sobre [como solucionar problemas do HoloLens emulador](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).


- nem todos os aplicativos na Microsoft Store são compatíveis com o emulador. Por exemplo, jovens conkers e fragmentos não são reproduzidos no emulador.
- Você não pode usar a webcam do PC no Emulator.
- o recurso de visualização dinâmica do Portal do dispositivo Windows não funciona com o emulador. Você ainda pode capturar vídeos e imagens de realidade misturada.

[Voltar para a lista](#list)

## <a name="voice-commands-arent-working"></a>Os comandos de voz não estão funcionando

se Cortana não estiver respondendo aos seus comandos de voz, verifique se Cortana está ativado. na lista todos os aplicativos, selecione **Cortana**  >    >  **bloco de anotações** do Menu  >  **Configurações** para fazer alterações. Para saber mais sobre o que você pode dizer, consulte [usar sua voz com HoloLens](hololens-cortana.md).

em HoloLens (1º gen), o reconhecimento de fala interno não é configurável. Ele está sempre ativado. no HoloLens 2, você pode escolher se deseja ativar o reconhecimento de fala e Cortana durante a configuração do dispositivo.

se o seu HoloLens 2 não estiver respondendo à sua voz, verifique se o reconhecimento de fala está ativado. acesse **iniciar**  >  **Configurações** a fala de  >  **privacidade**  >   e ativar o **reconhecimento de fala**.

[Voltar para a lista](#list)

## <a name="hand-input-isnt-working"></a>A entrada manual não está funcionando

para garantir que HoloLens possam ver suas mãos, você precisa mantê-las no quadro do gesto.  A página inicial da realidade misturada fornece comentários que permitem que você saiba quando suas mãos são rastreadas.  Os comentários são diferentes em versões diferentes do HoloLens:

- em HoloLens (1ª gen), o cursor olhar muda de um ponto para um anel
- no HoloLens 2, um cursor de ponta aparece quando a sua mão está perto de um tablet e um raio de lado é exibido quando os slates estão mais distantes

Muitos aplicativos de imersão seguem os padrões de entrada que são semelhantes à realidade misturada em casa.  saiba mais sobre como usar a entrada manual em [HoloLens (1ª gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) e [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se você estiver gastando luvas, observe que alguns tipos de luvas não funcionam com o rastreamento manual.  Um exemplo comum é o luvas de borracha preta, que tende a absorver a luz infravermelha e não é captado pela câmera de profundidade.  Se seu trabalho envolve um luvas de borracha, é recomendável tentar uma cor mais clara, como azul ou cinza.  Outro exemplo é o luvas de Baggy grande, que tendem a obscurecer a forma de sua mão. É recomendável usar luvas que estejam como o ajuste de forma possível para obter melhores resultados.

se o visor tiver impressões digitais ou manchas, use o pano de limpeza microfiber que acompanha o HoloLens para limpar o visor com cuidado.

[Voltar para a lista](#list)

## <a name="cant-connect-to-wi-fi"></a>Não é possível conectar ao Wi-Fi

Aqui estão algumas ações que você pode tentar se não conseguir conectar seu HoloLens a uma rede Wi-Fi:

- Verifique se o Wi-Fi está ligado. para verificar, use o gesto iniciar e, em seguida, selecione **Configurações**  >  **rede &amp; Internet**  >  **Wi-Fi**. Se o Wi-Fi estiver ligado, tente desligá-lo e, em seguida, ligue novamente.
- Aproxime-se do roteador ou do ponto de acesso.
- Reinicie o Wi-Fi roteador e [reinicie o HoloLens](hololens-recovery.md). Tente se conectar novamente.
- Se nenhuma dessas ações funcionar, verifique se o roteador está usando o firmware mais recente. Você pode encontrar essas informações no site do fabricante.

[Voltar para a lista](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth dispositivos não estão emparelhando

se você estiver tendo problemas [para emparelhar um dispositivo Bluetooth](hololens-connect-devices.md), tente o seguinte:

- vá para **Configurações**  >  **dispositivos** e verifique se Bluetooth está ativado. Se estiver, desative-o e ative-o novamente.
- certifique-se de que seu dispositivo de Bluetooth seja totalmente cobrado ou tenha baterias novas.
- Se você ainda não conseguir se conectar, [reinicie o HoloLens](hololens-recovery.md).

[Voltar para a lista](#list)

## <a name="usb-c-microphone-isnt-working"></a>O microfone USB-C não está funcionando

Lembre-se de que alguns microfones USB-C se reportam incorretamente como um microlocutor *e* um palestrante. Esse é um problema com o microfone e não com HoloLens. ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

em **Configurações**  ->    ->  **som** do sistema, defina explicitamente os alto-falantes internos **(Driver de áudio de recurso analógico)** como o **dispositivo padrão**. HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado mais tarde.

![Solução de problemas de microfones USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>os dispositivos listados como disponíveis no Configurações não funcionam

HoloLens (1º gen) não oferece suporte a perfis de áudio Bluetooth. Bluetooth dispositivos de áudio, como alto-falantes e headsets, podem aparecer como disponíveis nas configurações de HoloLens, mas não têm suporte.

o HoloLens 2 dá suporte ao perfil de áudio Bluetooth A2DP para reprodução de estéreo. o perfil Bluetooth hands Free que habilita a captura de microfone de um periférico de Bluetooth não tem suporte no HoloLens 2.

se você tiver problemas ao usar um dispositivo Bluetooth, verifique se ele é um dispositivo com suporte. Os dispositivos com suporte incluem o seguinte:

- os teclados de Bluetooth de QWERTY de idioma inglês (você pode usá-los em qualquer lugar que use o holographic keyboard).
- Bluetoothndo o mouse.
- o [HoloLens clicador](hololens1-clicker.md).

você pode emparelhar outros dispositivos Bluetooth HID e GATT junto com seu HoloLens. no entanto, talvez seja necessário instalar os aplicativos complementares correspondentes de Microsoft Store para realmente usar os dispositivos.

[Voltar para a lista](#list)
