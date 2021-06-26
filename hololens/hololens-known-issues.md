---
title: Problemas conhecidos do HoloLens (1ª geração)
description: Mantenha-se atualizado com nossa lista de problemas conhecidos e soluções alternativas que podem afetar os clientes e desenvolvedores do HoloLens usando o Unity e o Portal de Dispositivos do Windows.
keywords: solução de problemas, problema conhecido, ajuda
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923543"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Problemas conhecidos do HoloLens (1ª geração)

Aqui está a lista atual de problemas conhecidos para dispositivos HoloLens. Verifique aqui primeiro se você está vendo um comportamento ímpar. Essa lista será mantida atualizada à medida que novos problemas são descobertos ou relatados ou conforme os problemas são resolvidos em futuras atualizações de software do HoloLens.

>[!NOTE]
> - Se você descobrir um problema que não está bloqueando, informe-o em seu dispositivo HoloLens por meio do [Hub de Comentários.](hololens-feedback.md)
> - Se o problema que você está enfrentando estiver bloqueando você, além de preencher comentários, faça [uma solicitação de suporte](https://aka.ms/hlsupport).


- [Problemas conhecidos para todas as gerações do HoloLens](#known-issues-for-all-hololens-generations)
- [Problemas conhecidos do HoloLens (1ª geração)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Problemas conhecidos para todas as gerações do HoloLens

### <a name="unity"></a>Unity

- Confira [Instalar as ferramentas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Unity recomendada para o desenvolvimento do HoloLens.
- Problemas conhecidos com o Unity HoloLens Technical Preview estão documentados nos fóruns [do HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portal de Dispositivos do Windows

- O recurso De visualização ao vivo na captura de Realidade Misturada pode exibir vários segundos de latência.

- Na página Entrada Virtual, os controles Gesto e Rolagem na seção Gestos Virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de habilitar o Modo de Desenvolvedor em Configurações, pode levar alguns segundos antes que a opção para ativar o Portal de Dispositivos está habilitada.

### <a name="onedrive-camera-upload"></a>Upload da câmera do OneDrive

O aplicativo OneDrive para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante.

Soluções alternativas:

- Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor. Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte a dupla login). No seu perfil conta Microsoft no OneDrive, você pode habilitar o upload automático de rolagem da câmera em segundo plano.

- Se você não puder usar com segurança um conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do aplicativo OneDrive. Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no aplicativo OneDrive. Selecione o **+** botão e escolha **Carregar**. Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.

## <a name="known-issues-for-hololens-1st-gen"></a>Problemas conhecidos do HoloLens (1ª geração)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Não é possível se conectar e implantar no HoloLens por meio Visual Studio

> [!NOTE]
> Última Atualização: 8/8 às 17:11 – o Visual Studio lançou o VS 2019 versão 16.2, que inclui uma correção para esse problema. É recomendável atualizar para essa versão mais recente para evitar esse erro.

Visual Studio lançou o VS 2019 versão 16.2, que inclui uma correção para esse problema. É recomendável atualizar para essa versão mais recente para evitar esse erro.

Causa raiz do problema: os usuários que usaram o Visual Studio 2015 ou as versões anteriores do Visual Studio 2017 para implantar e depurar aplicativos no HoloLens e, em seguida, usaram as versões mais recentes do Visual Studio 2017 ou Visual Studio 2019 com o mesmo HoloLens serão afetados. As versões mais Visual Studio implantam uma nova versão de um componente, mas os arquivos da versão mais antiga são deixados no dispositivo, fazendo com que a versão mais recente falhe.  Isso causa a seguinte mensagem de erro: DEP0100: Verifique se o dispositivo de destino tem o modo de desenvolvedor habilitado. Não foi possível obter uma licença de desenvolvedor \<ip\> no devido ao erro 80004005.

#### <a name="workaround"></a>Solução alternativa

Nossa equipe está trabalhando em uma correção no momento. Enquanto isso, você pode usar as seguintes etapas para resolver o problema e ajudar a desbloquear a implantação e a depuração:  

1. Abra o Visual Studio.

1. Selecione **Arquivo** > **Novo** > **Projeto**.

1. Selecione **Visual C#**  >  **Aplicativo de** Console da Área de Trabalho do Windows  >  **(.NET Framework)**.

1. Dê um nome ao projeto (como "HoloLensDeploymentFix") e certifique-se de que o Framework está definido como pelo menos .NET Framework 4.5 e selecione **OK.**

1. Clique com o **botão** direito do mouse no nó Referências no  Gerenciador de Soluções e adicione as seguintes referências (selecione a seção Procurar e selecione **Procurar**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Se você não tiver o 10.0.18362.0 instalado, use a versão mais recente que você tem.

1. Clique com o botão direito do mouse no projeto no Gerenciador de Soluções e **selecione Adicionar**  >  **Item Existente**.

1. Navegue até C:\Arquivos de Programas (x86)\Windows Kits\10\bin\10.0.18362.0\x86 e altere o filtro para Todos os **Arquivos ( \* . \* )**.

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

Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais nova não foi registrada falharão ao iniciar no menu Iniciar.  Acreditamos que qualquer aplicativo no HoloLens pode ser afetado por esse problema.

Alguns usuários relataram que fechar aplicativos suspensos e iniciar outros aplicativos, como o Hub de Comentários, Visualizador 3D ou Fotos, resolve o problema para eles. No entanto, isso não funciona 100% do tempo.

Causamos raiz que esse problema não causava a atualização em si, mas um bug no sistema operacional que resultou na atualização da estrutura .NET Native está sendo tratada incorretamente. Temos o prazer de anunciar que identificamos uma correção e lançamos uma atualização (versão do sistema operacional 17763.380) que contém a correção.  

Para ver se o dispositivo pode fazer a atualização:

1. Vá para o aplicativo Configurações e abra **Atualizar & Segurança**.

1. Selecione **Verificar se há Atualizações.**

1. Se a atualização para 17763.380 estiver disponível, atualize para este build para receber a correção do bug do Trava do Aplicativo.

1. Após a atualização para esta versão do sistema operacional, os Aplicativos devem funcionar conforme o esperado.

Além disso, como fazemos com todas as versões do sistema operacional HoloLens, postemos a imagem FFU no Centro [de Download da Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Se você não quiser fazer a atualização, lançamos uma nova versão do aplicativo Microsoft Store UWP a partir de 29/3. Depois de ter a versão atualizada da Store:

1. Abra o Store e confirme se ele é carregado.
1. Use o gesto de abrir o menu.
1. Tentativa de abrir aplicativos desfeitos anteriormente.
1. Se ele ainda não puder ser lançado, toque e segure o ícone do aplicativo desfeito e selecione desinstalar.
1. Reinstale esses aplicativos da loja.

Se o dispositivo ainda não puder carregar aplicativos, você poderá fazer sideload de uma versão do .NET Native Framework e Runtime por meio do centro de download seguindo estas etapas:

1. Baixe esse [arquivo zip no](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Centro de Download da Microsoft. O desembaixamento produzirá dois arquivos.  Microsoft .NET.Native.Runtime.1.7.appx e Microsoft .NET.Native.Framework.1.7.appx.

1. Verifique se o dispositivo está desbloqueado em dev.  Se você ainda não fez isso antes, consulte [Usando o Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.

1. Em seguida, você deseja entrar no Portal de Dispositivos do Windows. Nossa recomendação é fazer isso por USB e você faria isso digitando http://127.0.0.1:10080 em seu navegador.

1. Depois que você tiver a Portal de Dispositivos do Windows, será necessário "carregar lado a lado" os dois arquivos baixados. Para fazer isso, você precisa ir para baixo na barra do lado esquerdo até chegar à seção **Aplicativos** e selecionar **Aplicativos**.

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

