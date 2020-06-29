---
title: Problemas conhecidos do HoloLens
description: Esta é a lista de problemas conhecidos que podem afetar os desenvolvedores do HoloLens.
keywords: solução de problemas, problemas conhecidos, ajuda
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: 330a7fd549a2b847f77715ca90d69f1d4df1fb1d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827725"
---
# Problemas conhecidos do HoloLens

Esta é a lista atual de problemas conhecidos para dispositivos do HoloLens. Marque aqui primeiro se você estiver vendo um comportamento estranho. Esta lista será mantida em atualização, pois novos problemas são descobertos ou relatados, ou como problemas são resolvidos nas futuras atualizações de software do HoloLens.

>[!NOTE]
> - Se você descobrir um problema que não está bloqueando você, informe-o no seu dispositivo HoloLens por meio do [Hub de feedback](hololens-feedback.md).
> - Se o problema que você está enfrentando estiver bloqueando você, em uma lista de comentários para o arquivamento, envie [uma solicitação de suporte](https://aka.ms/hlsupport).

- [Problemas conhecidos para todas as gerações do HoloLens](#known-issues-for-all-hololens-generations)
- [Problemas conhecidos de dispositivos do HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problemas conhecidos do HoloLens (1ª gen)](#known-issues-for-hololens-1st-gen)
- [Problemas conhecidos do emulador do HoloLens](#known-issues-for-hololens-emulator)

## Problemas conhecidos para todas as gerações do HoloLens

### Unity

- Consulte [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais recente do Unity recomendada para o desenvolvimento do HoloLens.
- Problemas conhecidos com a visualização técnica do Unity HoloLens são documentados nos [fóruns do HoloLens Unity](https://forum.unity3d.com/threads/known-issues.394627/).

### Windows Device Portal

- O recurso Visualização dinâmica em captura de realidade mista pode apresentar vários segundos de latência.
- Na página de entrada virtual, os controles de rolagem e de rolagem na seção gestos virtuais não são funcionais. Usá-los não terão nenhum efeito. O teclado virtual na mesma página funciona corretamente.
- Depois de habilitar o modo de desenvolvedor nas configurações, pode demorar alguns segundos até que a opção de ativar o Device portal esteja habilitada.

## Problemas conhecidos de dispositivos do HoloLens 2

### A tela azul é mostrada após a cancelamento da compilação do insider preview em um dispositivo reatualizado com uma compilação do insider

Trata-se de um problema que afeta os usuários que estavam em uma compilação do insider Preview, rebaixaram o HoloLens 2 com uma nova compilação do insider Preview e, em seguida, não cadastrada no programa Insider. 

Isso não afeta:
- Usuários que não estão registrados no Windows Insider 
- Insiders
    - Se um dispositivo foi cadastrado desde que as compilações do insider eram da versão 18362. x
    - Se eles atualizaram uma compilação Insider 19041. x e ficar inscrito no programa Insider 

Solução alternativa: 
- Evitar o problema 
    - Piscar um Build não Insider. Uma das atualizações mensais normais. 
    - Permaneça na visualização do Office Insider
- Reflashize o dispositivo
    1. Coloque o [HoloLens 2 no modo flash](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manualmente, desligando completamente enquanto não se conecta. Em seguida, mantendo o volume ativo, toque no botão de energia.
    1. Conecte-se ao computador e abra o complemento avançado de recuperação. 
    1. Atualize o HoloLens 2 para a compilação padrão.   

## Problemas conhecidos do HoloLens (1ª gen)

### Não é possível conectar e implantar o HoloLens pelo Visual Studio

> [!NOTE]
> Última atualização: 8/8 @ 5:11PM-o Visual Studio liberou a versão do VS 2019 16,2, que inclui uma correção para esse problema. Recomendamos que você atualize para esta versão mais recente para evitar que este erro seja apresentado.

O Visual Studio lançou o VS 2019 versão 16,2 que inclui uma correção para esse problema. Recomendamos que você atualize para esta versão mais recente para evitar que este erro seja apresentado.

Causa básica de problemas: os usuários que usaram o Visual Studio 2015 ou versões anteriores do Visual Studio 2017 para implantar e depurar aplicativos em seu HoloLens e, em seguida, usar as versões mais recentes do Visual Studio 2017 ou do Visual Studio 2019 com o mesmo HoloLens serão afetados. As versões mais recentes do Visual Studio implantam uma nova versão de um componente, mas arquivos da versão anterior são deixados no dispositivo, causando a falha da versão mais recente.  Isso causa a seguinte mensagem de erro: DEP0100: Certifique-se de que o dispositivo de destino tenha o modo de desenvolvedor habilitado. Não foi possível obter uma licença de desenvolvedor em \<ip\> devido ao erro 80004005.

#### Solução alternativa

Nossa equipe está trabalhando com uma correção no momento. Enquanto isso, você pode usar as etapas a seguir para solucionar o problema e ajudar a desbloquear a implantação e a depuração:  

1. Abrir o Visual Studio
1. Selecione **arquivo**  >  **novo**  >  **projeto**.
1. Selecione o aplicativo **Visual C#**  >  **Windows Desktop**  >  **console (.NET Framework)**.
1. Dê um nome ao projeto (como "HoloLensDeploymentFix") e certifique-se de que a estrutura esteja definida como pelo menos .NET Framework 4,5 e selecione **OK**.
1. Clique com o botão direito do mouse no nó **referências** no Gerenciador de soluções e adicione as seguintes referências (selecione para a seção **procurar** e selecione **procurar**):

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se você não tiver o 10.0.18362.0 instalado, use a versão mais recente que você tem. 

1. Clique com o botão direito do mouse no projeto no Gerenciador de soluções e selecione **Adicionar**  >  **Item existente**.
1. Navegue até C:\Arquivos de programas (x86) \Windows Kits\10\bin\10.0.18362.0\x86 e altere o filtro para **todos os arquivos (\ *. \ *)**.
1. Selecione ambos SirepClient.dll e SshClient.dll e selecione **Adicionar**.
1. Localize e selecione ambos os arquivos no Gerenciador de soluções (eles devem estar na parte inferior da lista de arquivos) e altere **copiar para diretório de saída** na janela **Propriedades** para **copiar sempre**.
1. Na parte superior do arquivo, adicione o seguinte à lista de `using` instruções existente:

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Em `static void Main(...)` , adicione o seguinte código:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Selecione **Compilar**compilar  >  **solução**.
1. Abra uma janela do prompt de comando e um CD para a pasta que contém o arquivo. exe compilado (por exemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug)
1. Execute o executável e forneça o endereço IP do dispositivo como um argumento de linha de comando. (Se estiver conectado usando USB, você pode usar 127.0.0.1, caso contrário, use o endereço IP Wi-Fi do dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1"

1. Depois que a ferramenta tiver saído sem mensagens (isso só deve levar alguns segundos), agora você poderá implantar e depurar do Visual Studio 2017 ou mais recente.  O uso continuado da ferramenta não é necessário.

Forneceremos mais atualizações à medida que elas forem disponibilizadas.

### Problemas ao iniciar a Microsoft Store e aplicativos no HoloLens

> [!NOTE]
> Última atualização: 4/2 @ 10 AM-problema resolvido. 

Você pode enfrentar problemas ao tentar iniciar a Microsoft Store e aplicativos no HoloLens. Determinamos que o problema ocorre quando atualizações do aplicativo em segundo plano implantam uma versão mais recente de pacotes do Framework em sequências específicas enquanto um ou mais de seus aplicativos dependentes ainda estão em execução. Nesse caso, uma atualização automática de aplicativo forneceu uma nova versão da estrutura nativa .NET (versão 10.0.25531 para 10.0.27413), que causou a atualização correta dos aplicativos que estão sendo executados para todos os aplicativos em execução que consumiram a versão anterior da estrutura.  O fluxo para atualização de estrutura é o seguinte: 

1. O novo pacote de estrutura é baixado da loja e instalado
1. Todos os aplicativos que usam a estrutura mais antiga são ' atualizados ' para usar a versão mais recente

Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais recente não foi registrada falharão ao iniciar no menu iniciar.  Acreditamos que qualquer aplicativo no HoloLens pode ser afetado por esse problema.

Alguns usuários relataram que fechar aplicativos suspensos e iniciar outros aplicativos, como o Hub de feedback, o visualizador 3D ou as fotos resolvem o problema para eles &mdash; , no entanto, isso não funciona 100% do tempo.

A raiz causou que esse problema não era causado pela atualização em si, mas um bug no sistema operacional que resultava na atualização da estrutura nativa do .NET sendo manipulado incorretamente. Estamos satisfeitos em anunciar que identificamos uma correção e lançamos uma atualização (versão do sistema operacional 17763,380) que contém a correção.  

Para ver se o seu dispositivo pode fazer a atualização, por favor:

1. Vá para o aplicativo Configurações e abra **atualização & segurança**.
1. Selecione **verificar se há atualizações**.
1. Se a atualização para o 17763,380 estiver disponível, atualize para esta compilação para receber a correção do bug do App Hang
1. Durante a atualização para esta versão do sistema operacional, os aplicativos devem funcionar como esperado.

Além disso, como fazemos com cada versão do sistema operacional do HoloLens, publicamos a imagem FFU no [centro de download da Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).

Se você não quiser fazer a atualização, lançamos uma nova versão do aplicativo UWP da Microsoft Store a partir do 3/29. Depois de ter a versão atualizada do repositório:

1. Abra a loja e confirme que ela é carregada.
1. Use o gesto de flor para abrir o menu.
1. Tente abrir aplicativos interrompidos anteriormente.
1. Se ainda não for possível iniciar, toque e segure o ícone do aplicativo danificado e selecione Desinstalar.
1. Resinstall esses aplicativos da loja.

Se o seu dispositivo ainda não conseguir carregar os aplicativos, você pode Sideload uma versão da estrutura nativa .NET e tempo de execução por meio do centro de download seguindo estas etapas:

1. Baixe [este arquivo zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) no centro de download da Microsoft. A descompactação produzirá dois arquivos.  Microsoft. NET. Native. Runtime. 1.7. Appx e Microsoft. NET. Native. Framework. 1.7. Appx
1. Verifique se o seu dispositivo está desbloqueado.  Se você ainda não fez isso antes das instruções para isso, [aqui](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)estão.
1. Em seguida, você deseja entrar no Windows Device Portal. Nossa recomendação é fazer isso por USB e fazer isso digitando http://127.0.0.1:10080 no seu navegador.
1. Depois que você tiver o Windows Device portal, precisará de "carregar à direita" os dois arquivos baixados. Para fazer isso, você precisa ficar abaixo da barra lateral esquerda até chegar à seção **aplicativos** e selecionar **aplicativos**.
1. Em seguida, você verá uma tela semelhante à seguinte.  Você deseja ir para a seção que diz **instalar aplicativo** e procurar onde você descompactou os dois arquivos Appx. Você só pode fazer uma por vez; portanto, depois de selecionar o primeiro, clique em "ir" na seção implantar. Em seguida, faça isso para o segundo arquivo APPX.

   ![Windows Device portal para instalar o aplicativo de carregamento lado a lado](images/20190322-DevicePortal.png)
1. Nesse ponto, acreditamos que seus aplicativos comecem a funcionar novamente e que você também possa acessar a loja.
1. Em alguns casos, é necessário executar a etapa adicional de iniciar o aplicativo do 3D Viewer antes que os aplicativos afetados sejam iniciados. 

Agradecemos a sua paciência, pois passamos pelo processo para que esse problema seja resolvido, e esperamos continuar trabalhando com nossa comunidade para criar experiências de realidade misturadas bem-sucedidas.

### Atualização do dispositivo

- 30 segundos após uma nova atualização, o Shell pode desaparecer uma vez. Faça o gesto de **cair** para continuar a sessão.

### Visual Studio

- Confira [instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Visual Studio que é recomendada para o desenvolvimento do HoloLens.
- Ao implantar um aplicativo do Visual Studio em seu HoloLens, você pode ver o erro: **a operação solicitada não pode ser executada em um arquivo com uma seção mapeada pelo usuário aberta. (Exceção de HRESULT: 0x800704C8)**. Se isso acontecer, tente novamente e sua implantação geralmente será bem-sucedida.

### API

- Se o aplicativo definir o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) atrás do usuário ou o normal para a câmera. encaminhar, os hologramas não aparecerão em realidade mista Capture fotos ou vídeos. Até que esse bug seja corrigido no Windows, se os aplicativos definirem ativamente o [ponto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) , eles devem garantir que o plano normal esteja definido na frente oposta da câmera (por exemplo, normal =-Camera. Forward).

### Controlador sem fio do Xbox

- O controlador S sem fio do Xbox deve ser atualizado para poder ser usado com o HoloLens. Certifique-se [de que você esteja atualizado](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) antes de tentar emparelhar o controlador com um HoloLens.
- Se você reinicializar o HoloLens enquanto o controlador sem fio do Xbox estiver conectado, o controlador não será reconectado automaticamente ao HoloLens. A luz do botão guia piscará lentamente até que o controlador seja desligado após 3 minutos. Para reconectar o seu controlador imediatamente, desligue o controlador, segurando o botão do guia até que a luz seja desativada. Quando você religar o controlador, ele se reconectará ao HoloLens.
- Se o seu HoloLens entrar em standby enquanto o controlador sem fio do Xbox estiver conectado, qualquer entrada no controlador ativará o HoloLens. Você pode impedir que isso desligue o seu controlador quando terminar de usá-lo.

## Problemas conhecidos do emulador do HoloLens

- Nem todos os aplicativos da Microsoft Store são compatíveis com o emulador. Por exemplo, Young Conker e fragmentos não são reproduzidos no emulador.
- Não é possível usar a webcam do PC no emulador.
- O recurso Visualização dinâmica do Windows Device portal não funciona com o emulador. Você ainda pode capturar vídeos e imagens de realidade misturada.
