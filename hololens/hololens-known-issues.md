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
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308153"
---
# <a name="known-issues-for-hololens"></a>Problemas conhecidos do HoloLens

Esta é a lista atual de problemas conhecidos para dispositivos HoloLens. Verifique primeiro se você está vendo um comportamento estranho. Essa lista será mantida atualizada conforme novos problemas forem descobertos ou relatados, ou conforme os problemas forem resolvidos em futuras atualizações de software do HoloLens.

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

- Na página entrada virtual, os controles de gesto e de rolagem na seção gestos virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na mesma página funciona corretamente.

- Depois de habilitar o modo de desenvolvedor em configurações, pode levar alguns segundos antes que a opção para ativar o portal do dispositivo esteja habilitada.

### <a name="onedrive-camera-upload"></a>Carregamento da câmera do OneDrive

O aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas corporativas ou de estudante.

Soluções alternativas:

- Se for viável para sua empresa, o carregamento automático de câmera terá suporte nas contas de consumidor da Microsoft. Você pode entrar em seu conta Microsoft além de sua conta corporativa ou de estudante (o aplicativo OneDrive dá suporte a logon duplo). Em seu perfil de conta Microsoft no OneDrive, você pode habilitar o carregamento automático de câmera em segundo plano.

- Se você não pode usar com segurança um conta Microsoft de consumidor para carregar suas fotos automaticamente, você pode carregar manualmente as fotos para sua conta corporativa ou de estudante do aplicativo OneDrive. Para fazer isso, verifique se você está conectado à sua conta corporativa ou de estudante no aplicativo OneDrive. Selecione o **+** botão e escolha **carregar**. Encontre as fotos ou vídeos que você deseja carregar navegando até **imagens > a câmera**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o botão **abrir** .

## <a name="known-issues-for-hololens-2-devices"></a>Problemas conhecidos para dispositivos do HoloLens 2

### <a name="microsoft-edge-fails-to-launch"></a>Falha ao iniciar o Microsoft Edge

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

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build"></a>A tela azul é mostrada após o cancelamento do registro de builds do insider preview em um dispositivo atualizado com uma compilação Insider

Esse é um problema que afeta que os usuários que estão em uma versão de visualização Insider, reativaram seu HoloLens 2 com uma nova compilação do insider Preview e, depois, cancelaram o registro do programa Insider. 

Isso não afeta:
- Usuários que não estão registrados no Windows Insider 
- Insiders
    - Se um dispositivo tiver sido registrado desde que as compilações do insider fossem a versão 18362. x
    - Se eles piscaram uma compilação 19041. x assinada Insider e permanecer inscrito no programa Insider 

Solução alternativa: 
- Evitar o problema 
    - Pisque um Build não Insider. Uma das atualizações regulares mensais. 
    - Mantenha-se no Insider Preview
- Repiscar o dispositivo

    1. Coloque o [HoloLens 2 no modo flash](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manualmente, desligando completamente enquanto não se conecta. Em seguida, ao manter o volume ativo, toque no botão de energia.
    
    1. Conecte-se ao PC e abra o complemento de recuperação avançada. 
    
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

1. Selecione SirepClient.dll e SshClient.dll e selecione **Adicionar**.

1. Localize e selecione ambos os arquivos em Gerenciador de Soluções (eles devem estar na parte inferior da lista de arquivos) e altere **copiar para diretório de saída** na janela **Propriedades** para **copiar sempre**.

1. Na parte superior do arquivo, adicione o seguinte à lista de `using` instruções existente:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Dentro do `static void Main(...)` , adicione o seguinte código:

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

1. Abra uma janela de prompt de comando e CD para a pasta que contém o arquivo. exe compilado (por exemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Execute o executável e forneça o endereço IP do dispositivo como um argumento de linha de comando. (Se conectado usando USB, você pode usar 127.0.0.1, caso contrário, use o endereço IP Wi-Fi do dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1".

1. Depois que a ferramenta for encerrada sem nenhuma mensagem (isso deve levar apenas alguns segundos), agora você poderá implantar e depurar do Visual Studio 2017 ou mais recente.  O uso contínuo da ferramenta não é necessário.

Forneceremos mais atualizações à medida que forem disponibilizadas.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemas ao iniciar o Microsoft Store e os aplicativos no HoloLens

> [!NOTE]
> Última atualização: 4/2 @ 10-problema resolvido. 

Você pode enfrentar problemas ao tentar iniciar o Microsoft Store e os aplicativos no HoloLens. Determinamos que o problema ocorre quando as atualizações do aplicativo em segundo plano implantam uma versão mais recente dos pacotes do Framework em sequências específicas, enquanto um ou mais de seus aplicativos dependentes ainda estão em execução. Nesse caso, uma atualização automática de aplicativo forneceu uma nova versão do .NET Native Framework (versão 10.0.25531 para 10.0.27413) fez com que os aplicativos que estão sendo executados não sejam atualizados corretamente para todos os aplicativos em execução que consomem a versão anterior do Framework.  A atualização do Flow for Framework é a seguinte: 

1. O novo pacote de estrutura é baixado da loja e instalado.

1. Todos os aplicativos que usam a estrutura mais antiga são "atualizados" para usar a versão mais recente.

Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais recente não foi registrada falharão ao iniciar no menu iniciar.  Acreditamos que qualquer aplicativo no HoloLens poderia ser afetado por esse problema.

Alguns usuários relataram que o fechamento de aplicativos suspensos e a inicialização de outros aplicativos, como hub de comentários, visualizador 3D ou fotos, resolve o problema para eles &mdash; no entanto, isso não funciona 100% do tempo.

Temos a raiz causada que esse problema não foi causado pela atualização em si, mas um bug no sistema operacional que resultou na atualização do .NET Native Framework sendo tratada incorretamente. Temos o prazer de anunciar que identificamos uma correção e lançamos uma atualização (versão do sistema operacional 17763,380) que contém a correção.  

Para ver se o dispositivo pode executar a atualização, por favor:

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

1. Baixe [este arquivo zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) do centro de download da Microsoft. O descompactar produzirá dois arquivos.  Microsoft. NET. Native. Runtime. 1.7. Appx e Microsoft. NET. Native. Framework. 1.7. Appx.

1. Verifique se o dispositivo está desbloqueado.  Se você ainda não fez isso, consulte [usando o portal de dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.

1. Em seguida, você deseja entrar no portal do dispositivo Windows. Nossa recomendação é fazer isso por USB e fazer isso digitando http://127.0.0.1:10080 em seu navegador.

1. Depois de ter o portal do dispositivo Windows, precisamos que você "carregue" os dois arquivos que você baixou. Para fazer isso, você precisa descer a barra do lado esquerdo até chegar à seção de **aplicativos** e selecionar **aplicativos**.

1. Em seguida, você verá uma tela semelhante à mostrada abaixo.  Você deseja ir para a seção que diz **instalar aplicativo** e procurar onde você descompactou esses dois arquivos Appx. Você só pode fazer uma por vez, portanto, depois de selecionar a primeira, clique em "ir" na seção implantar. Em seguida, faça isso para o segundo arquivo APPX.

   ![Portal de dispositivos Windows para instalar Side-Loaded aplicativo](images/20190322-DevicePortal.png)
   
1. Neste ponto, acreditamos que seus aplicativos devem começar a funcionar novamente e que você também pode chegar à loja.

1. Em alguns casos, é necessário executar a etapa adicional de iniciar o aplicativo do visualizador 3D antes que os aplicativos afetados sejam iniciados. 

Agradecemos sua paciência, já que passamos pelo processo para resolver esse problema, e esperamos continuar trabalhando com nossa comunidade para criar experiências de realidade misturadas bem-sucedidas.

### <a name="device-update"></a>Atualização do dispositivo

- 30 segundos após uma nova atualização, o Shell pode desaparecer uma vez. Execute o gesto de **cair** para continuar a sessão.

### <a name="visual-studio"></a>Visual Studio

- Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obter a versão mais atualizada do Visual Studio que é recomendada para o desenvolvimento do HoloLens.

- Ao implantar um aplicativo do Visual Studio em seu HoloLens, você poderá ver o erro: **a operação solicitada não pode ser executada em um arquivo com uma seção mapeada pelo usuário aberta. (Exceção de HRESULT: 0x800704C8)**. Se isso acontecer, tente novamente e sua implantação geralmente terá sucesso.

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
