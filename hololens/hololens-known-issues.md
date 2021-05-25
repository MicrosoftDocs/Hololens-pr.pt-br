---
title: Problemas conhecidos do HoloLens
description: Mantenha-se atualizado com nossa lista de problemas conhecidos e soluções alternativas que podem afetar clientes e desenvolvedores do HoloLens usando o Unity e o portal do dispositivo Windows.
keywords: solução de problemas, problema conhecido, ajuda
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397777"
---
# <a name="known-issues-for-hololens"></a>Problemas conhecidos do HoloLens

Aqui está a lista atual de problemas conhecidos para dispositivos HoloLens. Verifique primeiro se você está vendo um comportamento estranho. Essa lista será mantida atualizada conforme novos problemas forem descobertos ou relatados, ou conforme os problemas forem resolvidos em futuras atualizações de software do HoloLens.

>[!NOTE]
> - Se você descobrir um problema que não está bloqueando, informe-o em seu dispositivo de HoloLens por meio do [Hub de comentários](hololens-feedback.md).
> - Se o problema que você está enfrentando está bloqueando você, além de fazer o arquivamento de comentários, registre [uma solicitação de suporte](https://aka.ms/hlsupport).

- [Problemas conhecidos para todas as gerações de HoloLens](#known-issues-for-all-hololens-generations)
- [Problemas conhecidos para dispositivos do HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problemas conhecidos do HoloLens (1ª gen)](#known-issues-for-hololens-1st-gen)
- [Problemas conhecidos do emulador do HoloLens](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Problemas conhecidos para todas as gerações de HoloLens

### <a name="unity"></a>Unity

- Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obter a versão mais atualizada do Unity recomendada para o desenvolvimento do HoloLens.
- Problemas conhecidos com a visualização técnica do Unity HoloLens são documentados nos [fóruns do Hololens Unity](https://forum.unity3d.com/threads/known-issues.394627/).

### <a name="windows-device-portal"></a>Portal de Dispositivos do Windows

- O recurso de visualização dinâmica na captura da realidade misturada pode exibir vários segundos de latência.

- Na página entrada virtual, os controles de gesto e de rolagem na seção gestos virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de habilitar o Modo de Desenvolvedor em Configurações, pode levar alguns segundos antes que a opção para ativar o Portal de Dispositivos está habilitada.

### <a name="onedrive-camera-upload"></a>Upload da câmera do OneDrive

O aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante.

Soluções alternativas:

- Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor. Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte a dupla login). No seu perfil conta Microsoft no OneDrive, você pode habilitar o upload automático de rolagem da câmera em segundo plano.

- Se você não puder usar com segurança um conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do aplicativo OneDrive. Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no aplicativo OneDrive. Selecione o **+** botão e escolha **Carregar**. Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.

## <a name="known-issues-for-hololens-2-devices"></a>Problemas conhecidos para dispositivos HoloLens 2

### <a name="device-using-auto-login-asks-for-log-in"></a>O dispositivo que usa o logon automático solicita logon

Um dispositivo HoloLens 2 pode ser configurado para fazer logon automaticamente por meio de Opções de Entrada de Contas de Configurações -> e, em Obrigatório, definir o valor  ->    ->   como **Nunca**.  Alguns usuários podem precisar fazer logoff no dispositivo novamente ao atualizar um dispositivo com uma atualização substancialmente grande, como uma atualização de recurso.

Exemplo de quando isso pode ocorrer:

- Atualizando um dispositivo do Windows Holographic, versão 2004 (Build 19041.xxxx) para o Windows Holographic, versão 21H1 (Build 20346.xxxx)
- Atualizando um dispositivo para fazer uma grande atualização no mesmo build principal, por exemplo, Windows Holographic, versão 2004 para Windows Holographic, versão 20H2
- Atualizando um dispositivo de uma imagem de fábrica para a imagem mais recente

Isso não deve ocorrer durante:

- Dispositivos que levam uma atualização mensal de manutenção

Contornar métodos:

- Métodos de entrada, como PIN, senha, íris, autenticação da Web ou chaves FIDO2.
- Se o PIN do dispositivo não puder ser lembrado e outros métodos de autenticação não estiverem disponíveis, um usuário poderá usar o [modo de reflashing manual](hololens-recovery.md#manual-procedure).

### <a name="microsoft-edge-fails-to-launch"></a>Falha ao iniciar o Microsoft Edge

> [!NOTE]
> Esse problema foi criado originalmente com a versão de envio do Microsoft Edge em mente. Esse problema pode ser resolvido no [novo Microsoft Edge](hololens-new-edge.md). Se não estiver, envie comentários para o arquivo.

Alguns clientes relataram um problema em que o Microsoft Edge falha ao ser iniciado. Para esses clientes, o problema persiste pela reinicialização e não é resolvido com atualizações do Windows ou do aplicativo. Se você estiver enfrentando esse problema e tiver confirmado que o [Windows está atualizado](hololens-updates.md#manually-check-for-updates), registre um bug do [aplicativo de Hub de comentários](hololens-feedback.md) com a seguinte categoria e subcategoria: instalar e atualizar > baixar, instalar e configurar Windows Update.

Não há soluções alternativas conhecidas, pois não conseguimos fazer a raiz causar o problema até o momento. O arquivamento de um bug por meio do hub de comentários ajudará nossa investigação!

### <a name="keyboard-does-not-switch-to-special-characters"></a>O teclado não muda para caracteres especiais

Há um problema durante o OOBE, em que, depois que o usuário tiver escolhido uma conta corporativa ou de estudante e estiver inserindo sua senha, tentar alternar para os caracteres especiais no teclado tocando no botão &123 não mudará para caracteres especiais.

Solução alternativa:
-   Feche o teclado e reabra-o tocando no campo de texto.
-   Insira incorretamente sua senha. Quando o teclado for reiniciado da próxima vez, ele funcionará conforme o esperado.
- Autenticação na Web, feche o teclado e selecione **entrar em outro dispositivo**.
-   Se inserir apenas números, um usuário poderá pressionar e manter determinadas chaves para abrir um menu expandido.
-   Usando um teclado USB.

Isso não afeta:
- Usuários que optam por usar uma conta pessoal.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>A tela azul é mostrada após o desenrolamento de builds de visualização do Insider em um dispositivo com um build do Insider

Esse é um problema que afeta os usuários que estavam em um build de visualização do Insider, reemerrou o HoloLens 2 com um novo build de visualização do insider e, em seguida, foi desaloculado do programa Insider.

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

    1. Coloque o [HoloLens 2 no modo de flash](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manualmente, completamente ligado e não se conectando. Em seguida, enquanto Volume up, toque no botão Ligar.
    
    1. Conecte-se ao computador e abra o Advanced Recovery Companion.
    
    1. Atualize o HoloLens 2 para a compilação padrão.

## <a name="known-issues-for-hololens-1st-gen"></a>Problemas conhecidos do HoloLens (1ª gen)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Não é possível conectar e implantar no HoloLens por meio do Visual Studio

> [!NOTE]
> Última atualização: 8/8 @ 5:23h-o Visual Studio lançou o VS 2019 versão 16,2, que inclui uma correção para esse problema. É recomendável atualizar para esta versão mais recente para evitar que esse erro seja apresentado.

O Visual Studio lançou o VS 2019 versão 16,2, que inclui uma correção para esse problema. É recomendável atualizar para esta versão mais recente para evitar que esse erro seja apresentado.

Causa raiz do problema: os usuários que usaram o Visual Studio 2015 ou versões anteriores do Visual Studio 2017 para implantar e depurar aplicativos em seu HoloLens e, posteriormente, usaram as versões mais recentes do Visual Studio 2017 ou do Visual Studio 2019 com o mesmo HoloLens serão afetados. As versões mais recentes do Visual Studio implantam uma nova versão de um componente, mas os arquivos da versão mais antiga são deixados no dispositivo, fazendo com que a versão mais recente falhe.  Isso causa a seguinte mensagem de erro: DEP0100: Verifique se o dispositivo de destino tem o modo de desenvolvedor habilitado. Não foi possível obter uma licença de desenvolvedor em \<ip\> devido ao erro 80004005.

#### <a name="workaround"></a>Solução alternativa

Nossa equipe está trabalhando em uma correção no momento. Enquanto isso, você pode usar as etapas a seguir para contornar o problema e ajudar a desbloquear a implantação e a depuração:  

1. Abra o Visual Studio.

1. Selecione **Arquivo** > **Novo** > **Projeto**.

1. Selecione **Visual C#**  >  **Windows Desktop**  >  **console app (.NET Framework)**.

1. Dê um nome ao projeto (como "HoloLensDeploymentFix") e verifique se a estrutura está definida para pelo menos .NET Framework 4,5 e, em seguida, selecione **OK**.

1. Clique com o botão direito do mouse no nó **referências** em Gerenciador de soluções e adicione as seguintes referências (selecione para a seção **procurar** e selecione **procurar**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se você não tiver o 10.0.18362.0 instalado, use a versão mais recente que você tem. 

1. Clique com o botão direito do mouse no projeto em Gerenciador de soluções e selecione **Adicionar**  >  **Item existente**.

1. Navegue até C:\Arquivos de programas (x86) \Windows Kits\10\bin\10.0.18362.0\x86 e altere o filtro para **todos os arquivos ( \* . \* )**.

1. Selecione SirepClient.dll e SshClient.dll e Selecione **Adicionar**.

1. Localize e selecione os dois arquivos Gerenciador de Soluções (eles devem estar na parte inferior da lista  de arquivos) e **altere** Copiar para Diretório de Saída na janela Propriedades para Copiar **sempre**.

1. Na parte superior do arquivo, adicione o seguinte à lista de instruções `using` existente:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Dentro de `static void Main(...)` , adicione o seguinte código:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Selecione **Compilar** > **Compilar Solução**.

1. Abra uma Janela do Prompt de Comando e o cd para a pasta que contém o arquivo .exe compilado (por exemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Execute o executável e forneça o endereço IP do dispositivo como um argumento de linha de comando. (Se conectado usando USB, você pode usar 127.0.0.1; caso contrário, use o endereço IP Wi-Fi do dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1".

1. Depois que a ferramenta sair sem nenhuma mensagem (isso deve levar apenas alguns segundos), agora você poderá implantar e depurar do Visual Studio 2017 ou mais novo.  O uso contínuo da ferramenta não é necessário.

Forneceremos mais atualizações à medida que elas se tornarem disponíveis.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemas ao iniciar o Microsoft Store e aplicativos no HoloLens

> [!NOTE]
> Última Atualização: 02/04 às 10h – Problema resolvido.

Você pode ter problemas ao tentar iniciar o Microsoft Store e aplicativos no HoloLens. Determinamos que o problema ocorre quando as atualizações do aplicativo em segundo plano implantam uma versão mais recente dos pacotes de estrutura em sequências específicas enquanto um ou mais aplicativos dependentes ainda estão em execução. Nesse caso, uma atualização automática de aplicativos entregue uma nova versão do .NET Native Framework (versão 10.0.25531 a 10.0.27413) fez com que os aplicativos que estão em execução não sejam atualizados corretamente para todos os aplicativos em execução consumindo a versão anterior da estrutura.  O fluxo para a atualização da estrutura é o seguinte:

1. O novo pacote de estrutura é baixado da loja e instalado.

1. Todos os apps usando a estrutura mais antiga são 'atualizados' para usar a versão mais recente.

Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais nova não foi registrada falharão ao iniciar no menu Iniciar.  Acreditamos que qualquer aplicativo no HoloLens poderia ser afetado por esse problema.

Alguns usuários relataram que o fechamento de aplicativos suspensos e a inicialização de outros aplicativos, como hub de comentários, visualizador 3D ou fotos, resolve o problema para eles-no entanto, isso não funciona 100% do tempo.

Temos a raiz causada que esse problema não foi causado pela atualização em si, mas um bug no sistema operacional que resultou na atualização do .NET Native Framework sendo tratada incorretamente. Temos o prazer de anunciar que identificamos uma correção e lançamos uma atualização (versão do sistema operacional 17763,380) que contém a correção.  

Para ver se o dispositivo pode executar a atualização:

1. Vá para o aplicativo Configurações e abra **atualizar & segurança**.

1. Selecione **verificar se há atualizações**.

1. Se a atualização para 17763,380 estiver disponível, atualize para esse Build para receber a correção para o bug de parada do aplicativo.

1. Após a atualização para esta versão do sistema operacional, os aplicativos devem funcionar conforme o esperado.

Além disso, como fazemos com cada versão do sistema operacional do HoloLens, publicamos a imagem FFU no [centro de download da Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).

Se você não quiser fazer a atualização, lançamos uma nova versão do aplicativo Microsoft Store UWP a partir de 3/29. Depois de ter a versão atualizada do repositório:

1. Abra o repositório e confirme se ele é carregado.
1. Use o gesto de flor para abrir o menu.
1. Tentativa de abrir aplicativos interrompidos anteriormente.
1. Se ainda não puder ser iniciado, toque e mantenha o ícone do aplicativo interrompido e selecione Desinstalar.
1. Reinstale esses aplicativos da loja.

Se o dispositivo ainda não puder carregar aplicativos, você poderá Sideload uma versão do .NET Native Framework e tempo de execução por meio do centro de download seguindo estas etapas:

1. Baixe [este arquivo zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) do centro de download da Microsoft. O descompactar produzirá dois arquivos.  Microsoft .NET.Native.Runtime.1.7.appx e Microsoft .NET.Native.Framework.1.7.appx.

1. Verifique se o dispositivo está desbloqueado em dev.  Se você ainda não fez isso antes, consulte [Usando o Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.

1. Em seguida, você deseja entrar no Portal de Dispositivos do Windows. Nossa recomendação é fazer isso por USB e você faria isso digitando http://127.0.0.1:10080 em seu navegador.

1. Depois que você tiver a Portal de Dispositivos do Windows, será necessário "carregar lado a lado" os dois arquivos baixados. Para fazer isso, você precisa ir para baixo na barra do lado esquerdo até chegar à seção **Aplicativos** e selecionar **Aplicativos**.

1. Em seguida, você verá uma tela semelhante à abaixo.  Você deseja ir para a  seção que diz Instalar Aplicativo e navegar até o local em que desemcortou esses dois arquivos APPX. Você só pode fazer um de cada vez, portanto, depois de selecionar o primeiro, clique em "Ir" na seção Implantar. Em seguida, faça isso para o segundo arquivo APPX.

   ![Portal de Dispositivos do Windows instalar o Side-Loaded aplicativo](images/20190322-DevicePortal.png)
   
1. Neste ponto, acreditamos que seus aplicativos devem começar a funcionar novamente e que você também pode chegar à Store.

1. Em alguns casos, é necessário executar a etapa adicional de iniciar o aplicativo Visualizador 3D antes que os aplicativos afetados sejam lançados. 

Agradecemos sua saúde enquanto passamos pelo processo para resolver esse problema e estamos ansiosos para continuar trabalhando com nossa comunidade para criar experiências bem-sucedidas de Realidade Misturada.

### <a name="device-update"></a>Atualização do dispositivo

- 30 segundos após uma nova atualização, o shell pode desaparecer uma vez. Execute o gesto **de bloom** para retomar sua sessão.

### <a name="visual-studio"></a>Visual Studio

- Confira [Instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Visual Studio recomendada para o desenvolvimento do HoloLens.

- Ao implantar um aplicativo do Visual Studio em seu HoloLens, você poderá ver o erro: A operação solicitada não pode ser executada em um arquivo com uma seção mapeada **pelo usuário aberta. (Exceção de HRESULT: 0x800704C8)**. Se isso acontecer, tente novamente e sua implantação geralmente terá êxito.

### <a name="api"></a>API

- Se o aplicativo definir o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) por trás do usuário ou o normal para a câmera. encaminhar, os hologramas não aparecerão em fotos ou vídeos de captura de realidade misturada. Até que esse bug seja corrigido no Windows, se os aplicativos definirem ativamente o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) , eles devem garantir que o plano normal esteja definido na frente da câmera oposta (por exemplo, normal =-Camera. Forward).

### <a name="xbox-wireless-controller"></a>Controle sem Fio Xbox

- Os S do controlador sem fio do Xbox devem ser atualizados para que possam ser usados com o HoloLens. Verifique se você está [atualizado](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) antes de tentar emparelhar seu controlador com um HoloLens.

- Se você reinicializar o HoloLens enquanto o controlador sem fio do Xbox estiver conectado, o controlador não será reconectado automaticamente ao HoloLens. A luz do botão de guia piscará lentamente até que o controlador seja desligado após 3 minutos. Para reconectar o controlador imediatamente, desligue o controlador mantendo o botão guia até que a luz se apague. Quando você ligar o controlador novamente, ele se reconectará ao HoloLens.

- Se o seu HoloLens entrar em espera enquanto o controlador sem fio do Xbox estiver conectado, qualquer entrada no controlador ativará o HoloLens. Você pode evitar isso desligando o controlador quando terminar de usá-lo.

## <a name="known-issues-for-hololens-emulator"></a>Problemas conhecidos do emulador do HoloLens

- Nem todos os aplicativos na Microsoft Store são compatíveis com o emulador. Por exemplo, jovens conkers e fragmentos não são reproduzidos no emulador.
- Não é possível usar a webcam do PC no emulador.
- O recurso de visualização dinâmica do portal do dispositivo Windows não funciona com o emulador. Você ainda pode capturar vídeos e imagens de realidade misturada.
