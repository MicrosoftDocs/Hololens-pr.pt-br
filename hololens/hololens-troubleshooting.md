---
title: HoloLens Solução de problemas de dispositivo
description: mantenha-se atualizado sobre as soluções mais comuns para HoloLens problemas de dispositivo e técnicas de solução de problemas.
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
keywords: problemas, bug, solução de problemas, correção, ajuda, suporte, HoloLens, emulador
ms.openlocfilehash: 5501e036b5852833b7ff26445a98c3378ae6963c96114e26bf588eb33a56f6f0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662872"
---
# <a name="device-troubleshooting"></a>Solução de problemas de dispositivo

este artigo descreve como resolver vários problemas comuns de HoloLens.

>[!IMPORTANT]
> Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de **20% a 40%** da capacidade da bateria, se possível. As [luzes indicadoras de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas sob o botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.

<a id="list"></a>

**Problemas conhecidos**
- [O vídeo da assistência remota congela após 20 minutos](#remote-assist-video-freezes-after-20-minutes)
- [Logon automático solicita o logon](#auto-login-asks-for-log-in)
- [falha ao iniciar o Microsoft Edge](#microsoft-edge-fails-to-launch)
- [O teclado não muda para caracteres especiais](#keyboard-doesnt-switch-to-special-characters)
- [O download de arquivos bloqueados não mostra erro](#downloading-locked-files-doesnt-error)
- [Tempo limite de carregamento/download do arquivo do portal do dispositivo](#device-portal-file-uploaddownload-times-out)
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

um dispositivo HoloLens 2 pode ser configurado para fazer logon automaticamente por meio de opções de entrada de contas de **Configurações**  ->    ->   -> e, em **requerido** , defina o valor como **nunca**. Alguns usuários podem ser solicitados a fazer logon no dispositivo novamente ao atualizar um dispositivo com uma atualização substancialmente grande, como uma atualização de recurso. Esse é um **problema conhecido**.

Exemplo de quando isso pode ocorrer:

- atualizando um dispositivo do Windows Holographic, versão 2004 (build 19041. xxxx) para Windows Holographic, versão 21H1 (build 20346. xxxx)
- atualização de um dispositivo para fazer uma atualização grande na mesma compilação principal, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2
- Atualizando um dispositivo de uma imagem de fábrica para a imagem mais recente

Isso não deve ocorrer durante:

- Dispositivos que levam uma atualização mensal de manutenção

Contornar métodos:

- Métodos de entrada, como PIN, senha, íris, autenticação da Web ou chaves FIDO2.
- Se o PIN do dispositivo não puder ser lembrado e outros métodos de autenticação não estiverem disponíveis, um usuário poderá usar o [modo de reflashing manual](hololens-recovery.md#manual-procedure).

[Voltar para a lista](#list)

## <a name="microsoft-edge-fails-to-launch"></a>falha ao iniciar o Microsoft Edge

> [!NOTE]
> esse problema foi criado originalmente com a versão de envio do Microsoft Edge em mente. Esse problema pode ser resolvido no [novo Microsoft Edge](hololens-new-edge.md). Se não estiver, envie comentários para o arquivo.

alguns clientes relataram um problema em que Microsoft Edge falha ao iniciar. para esses clientes, o problema persiste pela reinicialização e não é resolvido com Windows ou atualizações de aplicativo. se você estiver enfrentando esse problema e tiver confirmado [Windows está atualizado](hololens-updates.md#manually-check-for-updates), registre um bug do [aplicativo de Hub de comentários](hololens-feedback.md) com a seguinte categoria e subcategoria: instalar e atualizar > baixar, instalar e configurar Windows Update.

Não há soluções alternativas conhecidas, pois não conseguimos fazer a raiz causar o problema até o momento. O arquivamento de um bug por meio do hub de comentários ajudará nossa investigação! Esse é um **problema conhecido**.

[Voltar para a lista](#list)

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

[Voltar para a lista](#list)

## <a name="downloading-locked-files-doesnt-error"></a>O download de arquivos bloqueados não é um erro

> [!NOTE]
> esse é um **problema conhecido** que é corrigido no Windows insider build, versão 20348,1403.

em compilações anteriores do Windows Holographic, ao tentar baixar um arquivo bloqueado, o resultado seria uma página de erro HTTP. no Windows Holographic, versão 21H1 update, tentando baixar um arquivo bloqueado resulta em nada que está visível, o arquivo não é baixado e não há erro.

[Voltar para a lista](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Tempo limite de carregamento/download do arquivo do portal do dispositivo
> [!NOTE]
> esse é um **problema conhecido** que é corrigido no Windows insider build, versão 20348,1403. Se você tiver desabilitado anteriormente a conexão SSL como parte da solução alternativa, é altamente recomendável reabilitá-la.


Alguns clientes encontraram, ao tentar carregar ou baixar arquivos, a operação pode parecer parar e expirar ou nunca concluir. isso é separado do[problema conhecido "arquivo bloqueado"](#downloading-locked-files-doesnt-error) – isso afeta Windows Holographic, versões 2004, 20H2 e 21H1 compilações no mercado. O problema foi raiz causado por um bug no tratamento de determinadas solicitações do portal do dispositivo e é mais consistente quando se usa HTTPS, que é o padrão. 

### <a name="workaround"></a>Solução alternativa

Essa solução alternativa, que se aplica igualmente a Wi-Fi e UsbNcm, é desabilitar a opção "obrigatório" em "conexão SSL". Para fazer isso, navegue até portal do dispositivo, **sistema** e selecione a página **preferências** . Na seção **segurança do dispositivo** , localize **conexão SSL** e desmarque para desabilitar **necessário**.

Em seguida, o usuário deve ir para http://, não https://(endereço IP) e recursos como upload de arquivo e download funcionarão.

[Voltar para a lista](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Tela azul após o cancelamento do registro do insider preview em um dispositivo atualizado com uma compilação Insider

esse é um problema que afeta que os usuários que estão em um build do insider preview foram reatualizados com o HoloLens 2 com uma nova compilação do insider preview e, depois, cancelado o registro do programa insider. Esse é um **problema conhecido**.

Isso não afeta:
- usuários que não estão registrados no Windows insider 
- Insiders
    - Se um dispositivo tiver sido registrado desde que as compilações do insider fossem a versão 18362. x
    - Se eles piscaram uma compilação 19041. x assinada Insider e permanecer inscrito no programa Insider

Solução alternativa: 
- Evitar o problema 
    - Pisque um Build não Insider. Uma das atualizações regulares mensais.
    - Mantenha-se no Insider Preview
- Repiscar o dispositivo

    1. coloque o [HoloLens 2 no modo flash](hololens-recovery.md) manualmente, desligando completamente enquanto não se conecta. Em seguida, ao manter o volume ativo, toque no botão de energia.
    
    1. Conexão ao PC e abrir o complemento de recuperação avançada.
    
    1. atualize o HoloLens 2 para a compilação padrão.

[Voltar para a lista](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive não carrega imagens automaticamente

o aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático da câmera para contas corporativas ou de estudante. Esse é um **problema conhecido**.

Soluções alternativas:

- Se for viável para sua empresa, o carregamento automático de câmera terá suporte nas contas de consumidor da Microsoft. você pode entrar em seu conta Microsoft além de sua conta corporativa ou de estudante (o aplicativo OneDrive dá suporte a logon duplo). em seu perfil de conta Microsoft no OneDrive você pode habilitar o carregamento automático de câmera de plano de fundo.

- se você não pode usar com segurança um conta Microsoft de consumidor para carregar suas fotos automaticamente, você pode carregar manualmente as fotos para sua conta corporativa ou de estudante do aplicativo OneDrive. para fazer isso, verifique se você está conectado à sua conta corporativa ou de estudante no aplicativo OneDrive. Selecione o **+** botão e escolha **upload**. Encontre as fotos ou vídeos que você deseja carregar navegando até **imagens > a câmera**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o botão **abrir** .

[Voltar para a lista](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens não está respondendo ou não será iniciado

se seu HoloLens não começar:

- Se os LEDs próximos ao botão de energia não acenderem ou apenas um LED piscar brevemente, talvez seja necessário [cobrar o HoloLens.](hololens2-charging.md#charging-the-device)
- Se os LEDs acenderem quando você pressionar o botão de energia, mas não conseguir ver nada em exibições, [faça uma reinicialização forçada do dispositivo](hololens-recovery.md#hard-reset-procedure).

se seu HoloLens se tornar congelado ou sem resposta:

- desative o HoloLens pressionando o botão de energia até que todos os cinco leds fiquem desligados ou por 15 segundos se os LEDs não responderem. para iniciar o HoloLens, pressione o botão de energia novamente.

se essas etapas não funcionarem, você poderá tentar [recuperar seu dispositivo HoloLens 2](hololens-recovery.md) ou [HoloLens (1ª gen).](hololens1-recovery.md)

[Voltar para a lista](#list)

## <a name="low-disk-space-error"></a>Erro de "pouco espaço em disco"

Você precisará liberar espaço de armazenamento seguindo um ou mais destes procedimentos:

- Exclua alguns espaços não utilizados. acesse **Configurações**  >    >  **espaços** do sistema, selecione um espaço que você não precisa mais e, em seguida, selecione **remover**.
- Remova alguns dos hologramas que você colocou.
- Exclua algumas imagens e vídeos do aplicativo fotos.
- Desinstale alguns aplicativos do seu HoloLens. Na lista **todos os aplicativos** , toque e mantenha o aplicativo que você deseja desinstalar e, em seguida, selecione **desinstalar**.

[Voltar para a lista](#list)

## <a name="calibration-fails"></a>Falha na calibragem

A calibragem deve funcionar para a maioria das pessoas, mas há casos em que a calibragem falha.
  
Alguns motivos possíveis para a falha de calibragem incluem:

- Obtendo distraídos e não seguindo os destinos de calibragem
- Visor ou visor de dispositivo sujo ou arranhado não está posicionado corretamente
- Óculos sujos ou arranhados
- Certos tipos de lentes de contato e óculos (lentes de contato coloridas, algumas lentes de contato toric, óculos de bloqueio de IR, alguns óculos altos de receita, óculos ou semelhante)
- Composição mais pronunciada e algumas extensões Eyelash
- Quadros eyeglass de cabelo ou espesso se estiverem impedindo que o dispositivo Veja seus olhos
- Certos olhos physiologys, condições de olho ou cirurgia de olho, como olhos estreitos, longo eyelashes, amblyopia, Nystagmus, alguns casos de LASIK ou outros olhos Surgeries

Se a calibragem não for bem-sucedida, tente:

- Limpando o visor do dispositivo
- Limpando seus óculos
- Enviando o visor do seu dispositivo o mais próximo possível dos seus olhos
- Movendo objetos no visor fora do caminho (como cabelo)
- Ligando uma luz em sua sala ou saindo da luz solar direta

se você seguiu todas as diretrizes e a calibragem ainda está falhando, você pode desabilitar o prompt de calibragem em Configurações. Também informe-nos ao arquivar comentários no [Hub de comentários](hololens-feedback.md).

Consulte também informações relacionadas para a [solução de problemas de cor ou brilho da imagem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

a configuração de IPD não é aplicável para HoloLens 2, pois as posições de olho são computadas pelo sistema. 

[Voltar para a lista](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>não é possível entrar porque o meu HoloLens foi configurado anteriormente para outra pessoa

Você pode [colocar o dispositivo no **modo flash** e usar o complemento de recuperação avançada](hololens-recovery.md#clean-reflash-the-device) para recuperar o dispositivo.

[Voltar para a lista](#list)


## <a name="unity-isnt-working"></a>O Unity não está funcionando

- consulte [instalar as ferramentas](/windows/mixed-reality/install-the-tools) para obter a versão mais atualizada do Unity recomendada para o desenvolvimento de HoloLens.
- problemas conhecidos com a visualização técnica do unity HoloLens são documentados nos [fóruns do HoloLens unity](https://forum.unity3d.com/threads/known-issues.394627/).

[Voltar para a lista](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows O portal do dispositivo não está funcionando corretamente

- O recurso de visualização dinâmica na captura da realidade misturada pode exibir vários segundos de latência.

- Na página entrada virtual, os controles de gesto e de rolagem na seção gestos virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- depois de habilitar o modo de desenvolvedor no Configurações, pode levar alguns segundos antes que a opção para ativar o Portal do dispositivo esteja habilitada.

[Voltar para a lista](#list)

## <a name="the-hololens-emulator-isnt-working"></a>o Emulator de HoloLens não está funcionando

as informações sobre o emulador de HoloLens estão localizadas em nossa documentação do desenvolvedor.  leia mais sobre como [solucionar problemas do emulador de HoloLens](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).


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

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>os dispositivos listados como disponíveis no Configurações não funcionam

HoloLens (1º gen) não oferece suporte a perfis de áudio Bluetooth. Bluetooth dispositivos de áudio, como alto-falantes e headsets, podem aparecer como disponíveis nas configurações de HoloLens, mas não têm suporte.

o HoloLens 2 dá suporte ao perfil de áudio Bluetooth A2DP para reprodução de estéreo. o perfil Bluetooth hands Free que habilita a captura de microfone de um periférico de Bluetooth não tem suporte no HoloLens 2.

se você tiver problemas ao usar um dispositivo Bluetooth, verifique se ele é um dispositivo com suporte. Os dispositivos com suporte incluem o seguinte:

- os teclados de Bluetooth de QWERTY de idioma inglês (você pode usá-los em qualquer lugar que use o holographic keyboard).
- Bluetoothndo o mouse.
- o [HoloLens clicador](hololens1-clicker.md).

você pode emparelhar outros dispositivos Bluetooth HID e GATT junto com seu HoloLens. no entanto, talvez seja necessário instalar os aplicativos complementares correspondentes de Microsoft Store para realmente usar os dispositivos.

[Voltar para a lista](#list)
