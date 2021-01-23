---
title: Problemas conhecidos do HoloLens
description: Mantenha-se atualizado com nossa lista de problemas conhecidos e soluções alternativas que podem afetar os clientes e desenvolvedores do HoloLens usando o Unity e o Windows Device Portal.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284072"
---
# Problemas conhecidos do HoloLens

Esta é a lista atual de problemas conhecidos para dispositivos HoloLens. Verifique aqui primeiro se você está vendo um comportamento ímpar. Essa lista será mantida atualizada à medida que novos problemas são descobertos ou relatados ou conforme os problemas são abordados em futuras atualizações de software do HoloLens.

>[!NOTE]
> - Se você descobrir um problema que não está bloqueando, informe-o em seu dispositivo HoloLens por meio do [Hub de Feedback.](hololens-feedback.md)
> - Se o problema que você está enfrentando estiver bloqueando você, além de preencher comentários, faça uma solicitação [de suporte.](https://aka.ms/hlsupport)

- [Problemas conhecidos de todas as gerações do HoloLens](#known-issues-for-all-hololens-generations)
- [Problemas conhecidos para dispositivos HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problemas conhecidos do HoloLens (1ª geração)](#known-issues-for-hololens-1st-gen)
- [Problemas conhecidos do emulador do HoloLens](#known-issues-for-hololens-emulator)

## Problemas conhecidos de todas as gerações do HoloLens

### Unity

- Confira [Instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Unity recomendada para o desenvolvimento do HoloLens.
- Problemas conhecidos com a Visualização Técnica do Unity HoloLens estão documentados nos [fóruns do HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### Windows Device Portal

- O recurso visualização ao vivo na captura de realidade misturada pode exibir vários segundos de latência.

- Na página Entrada Virtual, os controles Gesto e Rolagem sob a seção Gestos Virtuais não estão funcionais. Usá-los não terá efeito. O teclado virtual na mesma página funciona corretamente.

- Depois de habilitar o Modo de Desenvolvedor em Configurações, pode levar alguns segundos antes que a opção para ativar o Device Portal seja habilitada.

### Carregamento de câmera do OneDrive

O aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas do trabalho ou da escola.

Soluções alternativas:

- Se viável para sua empresa, o carregamento automático de câmera é suportado em contas da Microsoft do consumidor. Você pode entrar em sua conta da Microsoft além de sua conta de trabalho ou de estudante (o aplicativo oneDrive dá suporte à dupla login). No seu perfil de conta da Microsoft no OneDrive, você pode habilitar o carregamento automático da câmera em segundo plano.

- Se você não puder usar com segurança uma conta da Microsoft de consumidor para carregar suas fotos automaticamente, poderá carregar manualmente fotos para sua conta comercial ou de estudante a partir do aplicativo oneDrive. Para fazer isso, certifique-se de estar assinado em sua conta de trabalho ou de estudante no aplicativo oneDrive. Selecione o **+** botão e escolha **Carregar.** Encontre as fotos ou vídeos que você deseja carregar navegando para Imagens **> Câmera.** Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.

## Problemas conhecidos para dispositivos HoloLens 2

### Falha ao iniciar o Microsoft Edge

Alguns clientes relataram um problema em que o Microsoft Edge falha ao iniciar. Para esses clientes, o problema persiste durante a reinicialização e não é resolvido com as atualizações do Windows ou do aplicativo. Se você estiver enfrentando esse problema e tiver confirmado que o [Windows](hololens-updates.md#manually-check-for-updates)está atualizado, arquivo um bug do aplicativo Hub de [Feedback](hololens-feedback.md) com a seguinte categoria e sub-categoria: Instalar e atualizar o > Baixando, instalando e configurando o Windows Update.

Não há soluções alternativas conhecidas, pois não foi possível raiz causar o problema até o momento. Arquivar um bug por meio do Hub de Feedback ajudará nossa investigação!

### O teclado não alterna para caracteres especiais

Há um problema durante a OOBE, em que depois que o usuário escolheu uma conta de trabalho ou de estudante e está inserindo sua senha, tentar alternar para os caracteres especiais no teclado tocando no botão &123 não muda para caracteres especiais. 

Work-arounds:
-   Feche o teclado e reabra-o tocando no campo de texto.
-   Insira sua senha incorretamente. Quando o teclado for relancado na próxima vez, ele funcionará conforme o esperado.
- Autenticação da Web, feche o teclado e selecione **Entrar em outro dispositivo.** 
-   Se digitar apenas números, um usuário poderá pressionar e segurar certas teclas para abrir um menu expandido.
-   Usando um teclado USB.

Isso não afeta:
- Usuários que optam por usar uma conta pessoal.

### Tela azul é mostrada após o não-rolling de builds do Insider Preview em um dispositivo com uma com build do Insider

This is an issue affecting that affects users who are were on an Insider preview build, relashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program. 

Isso não afeta:
- Usuários que não estão inscritos no Windows Insider 
- Insiders:
    - Se um dispositivo tiver sido inscrito desde que os builds do Insider eram da versão 18362.x
    - Se eles piscaram um build 19041.x assinado pelo Insider e permanecem inscritos no programa Insider 

Work-around: 
- Evitar o problema 
    - Flash uma com build não insider. Uma das atualizações mensais regulares. 
    - Fique no Insider Preview
- Reflash the device

    1. Coloque o [HoloLens 2 no modo piscante](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manualmente, desligar totalmente enquanto não estiver conectado. Em seguida, mantendo o volume pressionado, toque no botão Ligar/Desligar.
    
    1. Conecte-se ao computador e abra o Advanced Recovery Companion. 
    
    1. Flash the HoloLens 2 to the default build.   

## Problemas conhecidos do HoloLens (1ª geração)

### Não é possível conectar e implantar o HoloLens por meio do Visual Studio

> [!NOTE]
> Última Atualização: 8/8 às 17:11 - O Visual Studio lançou o VS 2019 versão 16.2, que inclui uma correção para esse problema. É recomendável atualizar para essa versão mais recente para evitar a experiência desse erro.

O Visual Studio lançou o VS 2019 versão 16.2, que inclui uma correção para esse problema. É recomendável atualizar para essa versão mais recente para evitar a experiência desse erro.

Causa raiz do problema: os usuários que usaram o Visual Studio 2015 ou as versões anteriores do Visual Studio 2017 para implantar e depurar aplicativos em seu HoloLens e depois usaram posteriormente as versões mais recentes do Visual Studio 2017 ou do Visual Studio 2019 com o mesmo HoloLens serão afetados. As versões mais novas do Visual Studio implantam uma nova versão de um componente, mas os arquivos da versão mais antiga são deixados no dispositivo, fazendo com que a versão mais recente falhe.  Isso causa a seguinte mensagem de erro: DEP0100: Certifique-se de que o dispositivo de destino tenha o modo de desenvolvedor habilitado. Não foi possível obter uma licença de desenvolvedor \<ip\> devido ao erro 80004005.

#### Solução alternativa

Nossa equipe está trabalhando atualmente em uma correção. Enquanto isso, você pode usar as etapas a seguir para resolver o problema e ajudar a desbloquear a implantação e a depuração:  

1. Abra o Visual Studio.

1. Select **File**  >  **New**  >  **Project**.

1. Selecione **o Aplicativo de**Console da Área de Trabalho do  >  **Windows**  >  **(.NET Framework)** do Visual C#.

1. Dê um nome ao projeto (como "HoloLensDeploymentFix") e certifique-se de que a Estrutura está definida como pelo menos o .NET Framework 4.5 e selecione **OK**.

1. Clique com o **botão** direito do mouse no nó Referências **** no Solution Explorer e adicione as seguintes referências (selecione a seção Procurar e selecione **Procurar**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se você não tiver o 10.0.18362.0 instalado, use a versão mais recente. 

1. Clique com o botão direito do mouse no projeto no Explorador de Soluções e selecione **Adicionar**  >  **Item Existente.**

1. Navegue até C:\Arquivos de Programas (x86)\Windows Kits\10\bin\10.0.18362.0\x86 e altere o filtro para Todos os Arquivos **(\*.\*)**.

1. Selecione SirepClient.dll e SshClient.dll e Selecione **Adicionar.**

1. Localize e selecione ambos os arquivos no Solution Explorer (eles devem estar na parte **** inferior da lista de arquivos) e altere **Copy to Output Directory** na janela Propriedades para **Copiar sempre**.

1. Na parte superior do arquivo, adicione o seguinte à lista de instruções `using` existente:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Dentro `static void Main(...)` de , adicione o seguinte código:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Selecione **Build**  >  **Build Solution**.

1. Abra uma Janela de Prompt de Comando e um cd para a pasta que contém o arquivo .exe compilado (por exemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Execute o executável e forneça o endereço IP do dispositivo como um argumento de linha de comando. (Se conectado usando USB, você pode usar 127.0.0.1; caso contrário, use o endereço IP do Wi-Fi do dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1".

1. Depois que a ferramenta sair sem nenhuma mensagem (isso deve levar apenas alguns segundos), agora você poderá implantar e depurar do Visual Studio 2017 ou mais novo.  O uso contínuo da ferramenta não é necessário.

Forneceremos mais atualizações à medida que elas se tornarem disponíveis.

### Problemas ao iniciar a Microsoft Store e aplicativos no HoloLens

> [!NOTE]
> Última Atualização: 02/04 às 10:00 - Problema resolvido. 

Você pode ter problemas ao tentar iniciar a Microsoft Store e os aplicativos no HoloLens. Determinamos que o problema ocorre quando as atualizações de aplicativos em segundo plano implantam uma versão mais recente dos pacotes de estrutura em sequências específicas enquanto um ou mais aplicativos dependentes ainda estão em execução. Nesse caso, uma atualização automática de aplicativos entregue uma nova versão do .NET Native Framework (versão 10.0.25531 a 10.0.27413) fez com que os aplicativos que estão sendo executados não sejam atualizados corretamente para todos os aplicativos em execução que consomem a versão anterior da estrutura.  O fluxo para atualização de estrutura é o seguinte: 

1. O novo pacote de estrutura é baixado da loja e instalado.

1. Todos os aplicativos que usam a estrutura mais antiga são 'atualizados' para usar a versão mais recente.

Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais nova não foi registrada falharão ao iniciar no menu Iniciar.  Acreditamos que qualquer aplicativo no HoloLens pode ser afetado por esse problema.

Alguns usuários relataram que fechar aplicativos parados e iniciar outros aplicativos, como o Hub de Feedback, o Visualizador 3D ou Fotos, resolve o problema para eles, no entanto, isso não funciona &mdash; 100% do tempo.

Causamos raiz que esse problema não causou a atualização propriamente dita, mas um bug no sistema operacional que resultou na atualização da estrutura do .NET Native foi manipulada incorretamente. É com prazer que anunciamos que identificamos uma correção e lançamos uma atualização (sistema operacional versão 17763.380) contendo a correção.  

Para ver se o dispositivo pode receber a atualização, por favor:

1. Vá para o aplicativo Configurações e abra **Update & Security**.

1. Selecione **Verificar Atualizações.**

1. Se a atualização para 17763.380 estiver disponível, atualize para esta complicação para receber a correção do bug de trava de aplicativo.

1. Após a atualização para essa versão do sistema operacional, os Aplicativos devem funcionar conforme o esperado.

Além disso, como fazemos com cada versão do Sistema Operacional do HoloLens, postemos a imagem FFU no Centro de [Download da Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Se você não quiser receber a atualização, lançamos uma nova versão do aplicativo UWP da Microsoft Store a partir de 29/03. Depois de ter a versão atualizada da Loja:

1. Abra a Loja e confirme se ela é carregada.
1. Use o gesto de abrir o menu.
1. Tente abrir aplicativos quebrados anteriormente.
1. Se ele ainda não puder ser lançado, toque e segure o ícone do aplicativo quebrado e selecione desinstalar.
1. Instale-os de novo na loja.

Se o dispositivo ainda não puder carregar aplicativos, você poderá realizar o sideload de uma versão do .NET Native Framework e do Runtime por meio do centro de download seguindo estas etapas:

1. Baixe esse [arquivo zip no](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Centro de Download da Microsoft. A desembaixamento produzirá dois arquivos.  Microsoft.NET.Native.Runtime.1.7.appx e Microsoft.NET.Native.Framework.1.7.appx.

1. Verifique se o dispositivo está desbloqueado.  Se você ainda não fez isso antes, consulte [Usar o Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.

1. Em seguida, você deseja entrar no Windows Device Portal. Nossa recomendação é fazer isso por USB e você faria isso digitando http://127.0.0.1:10080 em seu navegador.

1. Depois que você tiver o Windows Device Portal, será necessário "side load" nos dois arquivos baixados. Para fazer isso, você precisa ir para a barra lateral esquerda até chegar à seção **Aplicativos** e selecionar **Aplicativos**.

1. Em seguida, você verá uma tela semelhante à abaixo.  Você deseja ir para a seção que diz **Instalar** Aplicativo e navegar até onde você desemcortou esses dois arquivos APPX. Você só pode fazer uma de cada vez, portanto, depois de selecionar a primeira, clique em "Ir" na seção Implantar. Em seguida, faça isso para o segundo arquivo APPX.

   ![Windows Device Portal to Install Side-Loaded app](images/20190322-DevicePortal.png)
   
1. Neste ponto, acreditamos que seus aplicativos devem começar a funcionar novamente e que você também pode chegar à Loja.

1. Em alguns casos, é necessário executar a etapa adicional de iniciar o aplicativo Visualizador 3D antes que os aplicativos afetados sejam lançados. 

Agradecemos sua paciência enquanto passamos pelo processo para resolver esse problema e estamos ansiosos para continuar trabalhando com nossa comunidade para criar experiências de realidade misturada bem-sucedidas.

### Atualização de dispositivo

- 30 segundos após uma nova atualização, o shell pode desaparecer uma vez. Faça o gesto **de abrir a** mão para retomar sua sessão.

### Visual Studio

- Confira [Instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Visual Studio recomendada para o desenvolvimento do HoloLens.

- Ao implantar um aplicativo do Visual Studio em seu HoloLens, você pode ver o erro: a operação solicitada não pode ser executada em um arquivo com uma seção mapeada **pelo usuário aberta. (Exceção de HRESULT: 0x800704C8)**. Se isso acontecer, tente novamente e sua implantação geralmente será bem-sucedida.

### API

- Se o aplicativo [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) define o ponto de foco por trás do usuário ou o normal como camera.forward, os hologramas não aparecerão em fotos ou vídeos de captura de realidade misturada. Até que esse bug seja corrigido no [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) Windows, se os aplicativos definirem ativamente o ponto de foco, eles deverão garantir que o normal do plano seja definido oposto à câmera (por exemplo, normal = -camera.forward).

### Controle sem Fio Xbox

- O controlador sem fio do Xbox S deve ser atualizado antes de poder ser usado com o HoloLens. Certifique-se [de estar atualizado antes](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) de tentar emparelhar seu controlador com um HoloLens.

- Se você reiniciar o HoloLens enquanto o controlador sem fio do Xbox estiver conectado, o controlador não se reconectará automaticamente ao HoloLens. A luz do botão Guia piscará lentamente até o controlador desligar após 3 minutos. Para reconectar o controlador imediatamente, segurando o botão Guia até que a luz seja desligada. Quando você ligar o controlador novamente, ele se reconecta ao HoloLens.

- Se o HoloLens entrar em espera enquanto o controlador sem fio do Xbox estiver conectado, qualquer entrada no controlador a adoçãoá o HoloLens. Você pode evitar isso ao desligar o controlador quando terminar de usá-lo.

## Problemas conhecidos do emulador do HoloLens

- Nem todos os aplicativos na Microsoft Store são compatíveis com o emulador. Por exemplo, Conker e Fragmentos Pequenos não são reproduzíveis no emulador.
- Você não pode usar a webcam do computador no Emulador.
- O recurso Visualização Ao Vivo do Windows Device Portal não funciona com o emulador. Você ainda pode capturar vídeos e imagens de realidade misturada.
