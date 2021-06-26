---
title: Solução de problemas do dispositivo HoloLens
description: Mantenha-se atualizado sobre as soluções mais comuns para problemas de dispositivos de HoloLens e técnicas de solução de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemas, Bug, solução de problemas, correção, ajuda, suporte, HoloLens, emulador
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924614"
---
# <a name="device-troubleshooting"></a>Solução de problemas de dispositivo

Este artigo descreve como resolver vários problemas comuns do HoloLens.

>[!IMPORTANT]
> Antes de iniciar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo seja cobrado de **20 a 40%** da capacidade da bateria, se possível. As [luzes do indicador de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas no botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.

<a id="list"></a>

**Problemas conhecidos**
- [O vídeo da assistência remota congela após 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [Logon automático solicita o logon](#auto-login-asks-for-log-in)
- [Falha ao iniciar o Microsoft Edge](#microsoft-edge-fails-to-launch)
- [O teclado não muda para caracteres especiais](#keyboard-doesnt-switch-to-special-characters)
- [O download de arquivos bloqueados não mostra erro](#downloading-locked-files-doesnt-error)
- [Tempo limite de carregamento/download do arquivo do portal do dispositivo](#device-portal-file-uploaddownload-times-out)
- [Tela azul após o cancelamento do registro do insider preview em um dispositivo atualizado com uma compilação Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [O OneDrive não carrega imagens automaticamente](#onedrive-doesnt-automatically-upload-pictures)

**Geral**
- [O HoloLens não está respondendo ou não será iniciado](#hololens-is-unresponsive-or-wont-start)
- [Erro de "pouco espaço em disco"](#low-disk-space-error)
- [Falha na calibragem](#calibration-fails)
- [Não é possível entrar porque meu HoloLens foi configurado anteriormente para outra pessoa](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [O Unity não está funcionando](#unity-isnt-working)
- [O portal do dispositivo Windows não está funcionando corretamente](#windows-device-portal-isnt-working-correctly)
- [O emulador do HoloLens não está funcionando](#the-hololens-emulator-isnt-working)

**Entrada**
- [Os comandos de voz não estão funcionando](#voice-commands-arent-working)
- [A entrada manual não está funcionando](#hand-input-isnt-working)

**Conectividade**
- [Não é possível conectar-se ao Wi-Fi](#cant-connect-to-wi-fi)

**Dispositivos externos** 
- [Os dispositivos Bluetooth não estão emparelhando](#bluetooth-devices-arent-pairing)
- [O microfone USB-C não está funcionando](#usb-c-microphone-isnt-working)
- [Os dispositivos listados como disponíveis nas configurações não funcionam](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>O vídeo da assistência remota congela após 20 minutos

> [!NOTE]
> Devido à gravidade do problema conhecido, no momento, vamos pausado a disponibilidade do Windows Holographic, versão 21H1. Se você ainda deseja atualizar seus dispositivos para 21H1, consulte [as instruções em nossas notas de versão na parte superior da página.](hololens-release-notes.md)

Na última versão do [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), alguns usuários da assistência remota experimentaram o congelamento do vídeo durante chamadas de 20 minutos. Esse é um **problema conhecido**.

### <a name="workarounds"></a>Soluções Alternativas

#### <a name="restart-in-between-calls"></a>Reinicializar entre chamadas

Se suas chamadas estiverem passando por um período de 20 minutos e você estiver enfrentando esse problema, tente reinicializar o dispositivo. A reinicialização do dispositivo entre as chamadas de assistência remota atualizará o dispositivo e o colocará em um bom estado.

Para reiniciar rapidamente um dispositivo no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) Abra o menu iniciar e selecione o ícone usuário e, em seguida, selecione **reiniciar**.

#### <a name="revert-to-an-older-build"></a>Reverter para uma compilação mais antiga

Alguns clientes descobriram que, ao reverter para uma versão anterior do sistema operacional, eles não mais sofreram esse problema. Se você descobriu que os dispositivos estão enfrentando esse problema, tente estas etapas:


Soluções alternativas:

- Se for viável para sua empresa, o carregamento automático de câmera terá suporte nas contas de consumidor da Microsoft. Você pode entrar em seu conta Microsoft além de sua conta corporativa ou de estudante (o aplicativo OneDrive dá suporte a logon duplo). Em seu perfil de conta Microsoft no OneDrive, você pode habilitar o carregamento automático de câmera em segundo plano.

- Se você não pode usar com segurança um conta Microsoft de consumidor para carregar suas fotos automaticamente, você pode carregar manualmente as fotos para sua conta corporativa ou de estudante do aplicativo OneDrive. Para fazer isso, verifique se você está conectado à sua conta corporativa ou de estudante no aplicativo OneDrive. Selecione o **+** botão e escolha **carregar**. Encontre as fotos ou vídeos que você deseja carregar navegando até **imagens > a câmera**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o botão **abrir** .


1. [Baixe a compilação para o Windows Holographic, versão 20H2 – maio de 2021 atualização](https://aka.ms/hololens2download/10.0.19041.1146)
1. Siga as [instruções retornadas para uma versão anterior do sistema operacional](hololens-update-hololens.md#go-back-to-a-previous-version)
1. [Faça uma pausa nas atualizações do sistema operacional no dispositivo manualmente](hololens-updates.md#pause-updates-via-device) ou para que muitos dispositivos usem o [adiamento por meio do MDM](hololens-updates.md#configure-an-update-deferral-policy).

[Voltar à lista](#list)

## <a name="auto-login-asks-for-log-in"></a>Logon automático solicita o logon

Um dispositivo HoloLens 2 pode ser configurado para fazer logon automaticamente nas opções de entrada das contas de **configurações**  ->    ->   -> e, em **requerido** , defina o valor como **nunca**. Alguns usuários podem ser solicitados a fazer logon no dispositivo novamente ao atualizar um dispositivo com uma atualização substancialmente grande, como uma atualização de recurso. Esse é um **problema conhecido**.

Exemplo de quando isso pode ocorrer:

- Atualizando um dispositivo do Windows Holographic, versão 2004 (Build 19041. xxxx) para o Windows Holographic, versão 21H1 (Build 20346. xxxx)
- Atualização de um dispositivo para fazer uma atualização grande na mesma compilação principal, por exemplo, o Windows Holographic, versão 2004 para o Windows Holographic, versão 20H2
- Atualizando um dispositivo de uma imagem de fábrica para a imagem mais recente

Isso não deve ocorrer durante:

- Dispositivos que levam uma atualização mensal de manutenção

Contornar métodos:

- Métodos de entrada, como PIN, senha, íris, autenticação da Web ou chaves FIDO2.
- Se o PIN do dispositivo não puder ser lembrado e outros métodos de autenticação não estiverem disponíveis, um usuário poderá usar o [modo de reflashing manual](hololens-recovery.md#manual-procedure).

[Voltar à lista](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Falha ao iniciar o Microsoft Edge

> [!NOTE]
> Esse problema foi criado originalmente com a versão de envio do Microsoft Edge em mente. Esse problema pode ser resolvido no [novo Microsoft Edge](hololens-new-edge.md). Se não estiver, envie comentários para o arquivo.

Alguns clientes relataram um problema em que o Microsoft Edge falha ao ser iniciado. Para esses clientes, o problema persiste pela reinicialização e não é resolvido com atualizações do Windows ou do aplicativo. Se você estiver enfrentando esse problema e tiver confirmado que o [Windows está atualizado](hololens-updates.md#manually-check-for-updates), registre um bug do [aplicativo de Hub de comentários](hololens-feedback.md) com a seguinte categoria e subcategoria: instalar e atualizar > baixar, instalar e configurar Windows Update.

Não há soluções alternativas conhecidas, pois não conseguimos fazer a raiz causar o problema até o momento. O arquivamento de um bug por meio do hub de comentários ajudará nossa investigação! Esse é um **problema conhecido**.

[Voltar à lista](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>O teclado não muda para caracteres especiais

Há um problema durante o OOBE, em que, depois que o usuário tiver escolhido uma conta corporativa ou de estudante e estiver inserindo sua senha, tentar alternar para os caracteres especiais no teclado tocando no botão &123 não mudará para caracteres especiais. Esse é um **problema conhecido**.

Solução alternativa:
-   Feche o teclado e reabra-o tocando no campo de texto.
-   Insira incorretamente sua senha. Quando o teclado for reiniciado da próxima vez, ele funcionará conforme o esperado.
- Autenticação na Web, feche o teclado e selecione **entrar em outro dispositivo**.
-   Se inserir apenas números, um usuário poderá pressionar e manter determinadas chaves para abrir um menu expandido.
-   Usando um teclado USB.

Isso não afeta:
- Usuários que optam por usar uma conta pessoal.

[Voltar à lista](#list)


## <a name="downloading-locked-files-doesnt-error"></a>O download de arquivos bloqueados não é um erro
> ! Observe que esse é um **problema conhecido** que é corrigido no Build do Windows Insider, versão 20348,1403.


Em versões anteriores do Windows Holographic, ao tentar baixar um arquivo bloqueado, o resultado seria uma página de erro HTTP. Na atualização do Windows Holographic, versão 21H1, tentar baixar um arquivo bloqueado não resulta em nada visível, o arquivo não é baixado e não há nenhum erro. 

[Voltar à lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal de Dispositivos o tempo de upload/download do arquivo
> ! OBSERVAÇÃO Esse é um **problema conhecido** que é corrigido no build Participante do Programa Windows Insider versão 20348.1403. Se você desabilitou anteriormente a Conexão SSL como parte da solução alternativa, é altamente recomendável habilita-la.


Alguns clientes descobriram que, ao tentar carregar ou baixar arquivos, a operação pode parecer travada e, em seguida, o tempo for concluído ou nunca ser concluído. Isso é separado do problema conhecido 'arquivo[bloqueado'](#downloading-locked-files-doesnt-error) – isso afeta o Windows Holographic, versões 2004, 20H2 e 21H1 builds no mercado. O problema foi causado por um bug na Portal de Dispositivos tratamento de determinadas solicitações e é atingido de forma mais consistente ao usar https, que é o padrão. 

### <a name="workaround"></a>Solução alternativa

Essa solução alternativa, que se aplica igualmente a Wi-Fi e UsbNcm, é desabilitar a opção "obrigatório" em "Conexão SSL". Para fazer isso, navegue até Portal de Dispositivos, **Sistema** e selecione a **página Preferências.** Na seção **Segurança do** Dispositivo, localize Conexão **SSL** e desmarque para desabilitar **Obrigatório.**

Em seguida, o usuário deve ir para http://, não https:// (endereço IP) e recursos como upload e download de arquivo funcionarão.

[Voltar à lista](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Tela azul após o unenrolling da versão prévia do Insider em um dispositivo com um build do Insider

Esse é um problema que afeta os usuários que estavam em um build de visualização do Insider, reemerrou o HoloLens 2 com um novo build de visualização do insider e, em seguida, foi desaloculado do programa Insider. Esse é um **problema conhecido.**

Isso não afeta:
- Usuários que não estão inscritos no Participante do Programa Windows Insider 
- Insiders:
    - Se um dispositivo foi inscrito desde que os builds do Insider eram da versão 18362.x
    - Se eles piscaram um build 19041.x assinado pelo Insider e permanecem inscritos no programa Insider

Work-around: 
- Evitar o problema 
    - Flash de um build não interno. Uma das atualizações mensais regulares.
    - Mantenha-se no Insider Preview
- Reflash o dispositivo

    1. Coloque o [HoloLens 2 no modo de flash](hololens-recovery.md) manualmente, completamente ligado e não se conectando. Em seguida, enquanto Volume up, toque no botão Ligar.
    
    1. Conecte-se ao computador e abra o Advanced Recovery Companion.
    
    1. Flash do HoloLens 2 para o build padrão.

[Voltar à lista](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>O OneDrive não carrega imagens automaticamente

O aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante. Esse é um **problema conhecido.**

Soluções alternativas:

- Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor. Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte a dupla login). No seu perfil conta Microsoft no OneDrive, você pode habilitar o upload automático de rolagem da câmera em segundo plano.

- Se você não puder usar com segurança um conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do aplicativo OneDrive. Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no aplicativo OneDrive. Selecione o **+** botão e escolha **Carregar**. Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.

[Voltar à lista](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>O HoloLens não está respondendo ou não iniciará

Se o HoloLens não for iniciar:

- Se os LEDs ao lado do botão de energia não piscarem ou apenas um LED piscar brevemente, talvez seja necessário cobrar [o HoloLens.](hololens2-charging.md#charging-the-device)
- Se os LEDs se acenderem quando você pressionar o botão de energia, mas você não conseguir ver nada nas exibições, faça uma [redefinição de](hololens-recovery.md#hard-reset-procedure)disco rígido do dispositivo .

Se o HoloLens ficar congelado ou sem resposta:

- Desligue o HoloLens pressionando o botão de energia até que todos os cinco LEDs se desliguem ou por 15 segundos se os LEDs não responderem. Para iniciar o HoloLens, pressione o botão de energia novamente.

Se essas etapas não funcionarem, você poderá tentar recuperar seu dispositivo [HoloLens 2](hololens-recovery.md) ou [o dispositivo HoloLens (1ª geração).](hololens1-recovery.md)

[Voltar à lista](#list)

## <a name="low-disk-space-error"></a>Erro "Espaço em Disco Baixo"

Você precisará liberar algum espaço de armazenamento fazendo um ou mais dos seguintes:

- Exclua alguns espaços nãoutilados. Vá para **Configurações Espaços** do Sistema , selecione um espaço que você não precisa mais  >    >  e, em seguida, **selecione Remover**.
- Remova alguns dos hologramas que você colocou.
- Exclua algumas imagens e vídeos do aplicativo Fotos.
- Desinstale alguns aplicativos do HoloLens. Na lista **Todos os apps,** toque e mantenha o aplicativo que você deseja desinstalar e, em seguida, selecione **Desinstalar**.

[Voltar à lista](#list)

## <a name="calibration-fails"></a>Falha na calibragem

A calibragem deve funcionar para a maioria das pessoas, mas há casos em que a calibragem falha.
  
Alguns possíveis motivos para a falha de calibragem incluem:

- Ficando confuso e não seguindo os destinos de calibragem
- Visor do dispositivo sujo ou com rascunho ou visor do dispositivo não posicionado corretamente
- Óculos sujos ou com rascunho
- Determinados tipos de lentes de contato e óculos (lentes de contato coloridas, algumas lentes de contato tóricas, óculos de bloqueio de IR, alguns óculos de óculos com alta receita, óculos de sol ou semelhantes)
- Mais pronunciada adeção e algumas extensões de cíoa
- Quadros de óculos grandes ou de óculos se eles estão bloqueando o dispositivo de ver seus olhos
- Determinadas coisas de olho, condições de olho ou olho, como olhos estreitos, malhas longas, amblyopia, nystagmus, alguns casos de LASIK ou outras óculos de olho

Se a calibragem não for bem-sucedida, tente:

- Limpando o visor do dispositivo
- Limpando seus óculos
- Esvasar o visor do dispositivo o mais próximo possível dos olhos
- Mover objetos no visor para fora do caminho (como pelos)
- A ligar uma luz em seu quarto ou sair da área de trabalho direta

Se você seguiu todas as diretrizes e a calibragem ainda está falhando, você pode desabilitar o prompt de calibragem em Configurações. Além disso, nos avise fazendo comentários no [Hub de Comentários.](hololens-feedback.md)

Confira também informações relacionadas para a solução de problemas de cor [ou brilho da imagem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

A configuração de IPD não é aplicável ao HoloLens 2, pois as posições de olho são computadas pelo sistema. 

[Voltar à lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Não é possível entrar porque meu HoloLens foi previamente definido para outra pessoa

Você pode [colocar o dispositivo no Modo de Flash **e** usar o Avançado Recovery Companion](hololens-recovery.md#clean-reflash-the-device) para recuperar o dispositivo.

[Voltar à lista](#list)


## <a name="unity-isnt-working"></a>O Unity não está funcionando

- Confira [Instalar as ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Unity recomendada para o desenvolvimento do HoloLens.
- Problemas conhecidos com o Unity HoloLens Technical Preview estão documentados nos fóruns [do HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Voltar à lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Portal de Dispositivos do Windows não está funcionando corretamente

- O recurso De visualização ao vivo na captura de Realidade Misturada pode exibir vários segundos de latência.

- Na página Entrada Virtual, os controles Gesto e Rolagem na seção Gestos Virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de habilitar o Modo de Desenvolvedor em Configurações, pode levar alguns segundos antes que a opção para ativar o Portal de Dispositivos está habilitada.

[Voltar à lista](#list)

## <a name="emulator"></a>Emulador
### <a name="the-hololens-emulator-isnt-working"></a>O emulador do HoloLens não está funcionando

As informações sobre o emulador do HoloLens estão localizadas em nossa documentação do desenvolvedor.  Leia mais sobre como [solucionar problemas do emulador do HoloLens](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).


- Nem todos os aplicativos na Microsoft Store são compatíveis com o emulador. Por exemplo, jovens conkers e fragmentos não são reproduzidos no emulador.
- Não é possível usar a webcam do PC no emulador.
- O recurso de visualização dinâmica do portal do dispositivo Windows não funciona com o emulador. Você ainda pode capturar vídeos e imagens de realidade misturada.

[Voltar à lista](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Não consigo encontrar ou usar o teclado para digitar o emulador do HoloLens 2

*Em breve*

[Voltar à lista](#list)

## <a name="voice-commands-arent-working"></a>Os comandos de voz não estão funcionando

Se a Cortana não estiver respondendo aos seus comandos de voz, verifique se a Cortana está ativada. Na lista todos os aplicativos, selecione o menu **Cortana**  >    >    >  **configurações** do bloco de anotações para fazer alterações. Para saber mais sobre o que você pode dizer, consulte [usar sua voz com o HoloLens](hololens-cortana.md).

No HoloLens (1º gen), o reconhecimento de fala interno não é configurável. Ele está sempre ativado. No HoloLens 2, você pode escolher se deseja ativar o reconhecimento de fala e a Cortana durante a configuração do dispositivo.

Se o seu HoloLens 2 não estiver respondendo à sua voz, verifique se o reconhecimento de fala está ativado. Acesse **Iniciar**  >  **configurações**  >    >  **fala** a privacidade e ative o **reconhecimento de fala**.

[Voltar à lista](#list)

## <a name="hand-input-isnt-working"></a>A entrada manual não está funcionando

Para garantir que o HoloLens possa ver suas mãos, você precisa mantê-las no quadro do gesto.  A página inicial da realidade misturada fornece comentários que permitem que você saiba quando suas mãos são rastreadas.  Os comentários são diferentes em versões diferentes do HoloLens:
- No HoloLens (1º gen), o cursor olhar muda de um ponto para um anel
- No HoloLens 2, um cursor de ponta aparece quando a sua mão está perto de um Tablet, e um raio de lado é exibido quando os slates estão mais distantes

Muitos aplicativos de imersão seguem os padrões de entrada que são semelhantes à realidade misturada em casa.  Saiba mais sobre como usar a entrada manual no [hololens (1ª gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) e o [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Se você estiver gastando luvas, observe que alguns tipos de luvas não funcionam com o rastreamento manual.  Um exemplo comum é o luvas de borracha preta, que tende a absorver a luz infravermelha e não é captado pela câmera de profundidade.  Se seu trabalho envolve um luvas de borracha, é recomendável tentar uma cor mais clara, como azul ou cinza.  Outro exemplo é o luvas de Baggy grande, que tendem a obscurecer a forma de sua mão. É recomendável usar luvas que estejam como o ajuste de forma possível para obter melhores resultados.

Se o visor tiver impressões digitais ou manchas, use o pano de limpeza microfiber que veio com o HoloLens para limpar o visor com cuidado.

[Voltar à lista](#list)

## <a name="cant-connect-to-wi-fi"></a>Não é possível conectar ao Wi-Fi

Aqui estão algumas coisas a serem experimentadas se você não puder conectar seu HoloLens a uma rede Wi-Fi:

- Verifique se Wi-Fi está ativado. Para verificar, use o gesto de início e, em seguida, selecione **configurações**  >  **rede &amp; Internet**  >  **Wi-Fi**. Se Wi-Fi estiver ativado, tente desligá-lo e depois novamente.
- Aproxime-se do roteador ou do ponto de acesso.
- Reinicie o roteador Wi-Fi e [reinicie o HoloLens](hololens-recovery.md). Tente se conectar novamente.
- Se nenhuma dessas coisas funcionar, verifique se o roteador está usando o firmware mais recente. Você pode encontrar essas informações no site do fabricante.

[Voltar à lista](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Os dispositivos Bluetooth não estão emparelhando

Se você estiver tendo problemas [para emparelhar um dispositivo Bluetooth](hololens-connect-devices.md), tente o seguinte:

- Vá para **configurações**  >  **dispositivos** e verifique se o Bluetooth está ativado. Se estiver, desative-o e ative-o novamente.
- Certifique-se de que seu dispositivo Bluetooth seja totalmente cobrado ou que tenha baterias novas.
- Se você ainda não conseguir se conectar, [reinicie o HoloLens](hololens-recovery.md).

[Voltar à lista](#list)

## <a name="usb-c-microphone-isnt-working"></a>O microfone USB-C não está funcionando
Lembre-se de que alguns microfones USB-C se reportam incorretamente como um microlocutor *e* um palestrante. Isso é um problema com o microfone e não com o HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

Em **configurações**  ->    ->  **som** do sistema, defina explicitamente os alto-falantes internos **(driver de áudio de recurso analógico)** como o **dispositivo padrão**. O HoloLens deve se lembrar dessa configuração mesmo que o microfone seja removido e reconectado posteriormente.

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Os dispositivos listados como disponíveis nas configurações não funcionam

O HoloLens (1º gen) não oferece suporte a perfis de áudio Bluetooth. Dispositivos de áudio Bluetooth, como alto-falantes e headsets, podem aparecer como disponíveis nas configurações do HoloLens, mas não têm suporte.

O HoloLens 2 dá suporte ao perfil de áudio Bluetooth A2DP para reprodução de estéreo. O perfil de mãos livres de Bluetooth que habilita a captura de microfone de um periférico Bluetooth não tem suporte no HoloLens 2.

Se você tiver problemas ao usar um dispositivo Bluetooth, verifique se ele é um dispositivo com suporte. Os dispositivos com suporte incluem o seguinte:

- Teclados Bluetooth de QWERTY de língua inglesa (você pode usá-los em qualquer lugar em que use o Holographic Keyboard).
- Mouses Bluetooth.
- O [clicador de HoloLens](hololens1-clicker.md).

Você pode emparelhar outros dispositivos Bluetooth HID e GATT junto com seu HoloLens. No entanto, talvez seja necessário instalar os aplicativos complementares correspondentes de Microsoft Store para realmente usar os dispositivos.

[Voltar à lista](#list)
