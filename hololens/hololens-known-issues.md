---
title: Problemas conhecidos para HoloLens (1ª geração)
description: Mantenha-se atualizado com nossa lista de problemas conhecidos e soluções alternativas que podem afetar HoloLens clientes e desenvolvedores que usam o Unity e o Windows Portal de Dispositivos.
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
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031929"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Problemas conhecidos para HoloLens (1ª geração)

Aqui está a lista atual de problemas conhecidos para HoloLens dispositivos. Verifique aqui primeiro se você está vendo um comportamento ímpar. Essa lista será mantida atualizada à medida que novos problemas são descobertos ou relatados ou conforme os problemas são resolvidos em atualizações HoloLens software futuras.

>[!NOTE]
> - Se você descobrir um problema que não está bloqueando, informe-o em seu dispositivo HoloLens por meio do [Hub de Comentários.](hololens-feedback.md)
> - Se o problema que você está enfrentando estiver bloqueando você, além de preencher comentários, faça [uma solicitação de suporte](https://aka.ms/hlsupport).


- [Problemas conhecidos para todas as HoloLens gerações](#known-issues-for-all-hololens-generations)
- [Problemas conhecidos para HoloLens (1ª geração)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Problemas conhecidos para todas as HoloLens gerações

### <a name="unity"></a>Unity

- Confira [Instalar as ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Unity recomendada para HoloLens desenvolvimento.
- Problemas conhecidos com o Unity HoloLens Technical Preview estão documentados nos [fóruns HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portal de Dispositivos do Windows

- O recurso De visualização ao vivo na captura de Realidade Misturada pode exibir vários segundos de latência.

- Na página Entrada Virtual, os controles Gesto e Rolagem na seção Gestos Virtuais não são funcionais. Usá-los não terá nenhum efeito. O teclado virtual na página de entrada virtual funciona corretamente.

- Depois de habilitar o Modo de Desenvolvedor Configurações, pode levar alguns segundos antes que a opção ative a Portal de Dispositivos está habilitada.

### <a name="onedrive-camera-upload"></a>OneDrive upload da câmera

O OneDrive aplicativo para HoloLens não dá suporte ao carregamento automático de câmera para contas de trabalho ou de estudante.

Soluções alternativas:

- Se for viável para sua empresa, há suporte para o carregamento automático de câmera em contas da Microsoft do consumidor. Você pode entrar no seu conta Microsoft além de sua conta de trabalho ou de estudante (o aplicativo OneDrive dá suporte à dupla login). No seu perfil conta Microsoft no OneDrive você pode habilitar o upload automático de rolagem da câmera em segundo plano.

- Se você não puder usar com segurança uma conta de conta Microsoft para carregar suas fotos automaticamente, poderá carregar manualmente fotos em sua conta de trabalho ou de estudante do OneDrive aplicativo. Para fazer isso, certifique-se de que você está entrando em sua conta de trabalho ou de estudante no OneDrive aplicativo. Selecione o **+** botão e escolha **Upload**. Encontre as fotos ou vídeos que você deseja carregar navegando até **Imagens > Camera Roll**. Selecione as fotos ou vídeos que você deseja carregar e, em seguida, selecione o **botão** Abrir.

## <a name="known-issues-for-hololens-1st-gen"></a>Problemas conhecidos para HoloLens (1ª geração)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Não é possível se conectar e implantar no HoloLens por meio Visual Studio

> [!NOTE]
> Última Atualização: 8/8 às 17:11 – o Visual Studio lançou o VS 2019 versão 16.2, que inclui uma correção para esse problema. É recomendável atualizar para essa versão mais recente para evitar esse erro.

Visual Studio lançou o VS 2019 versão 16.2, que inclui uma correção para esse problema. É recomendável atualizar para essa versão mais recente para evitar esse erro.

Causa raiz do problema: os usuários que usaram o Visual Studio 2015 ou as versões anteriores do Visual Studio 2017 para implantar e depurar aplicativos em seu HoloLens e, em seguida, usaram as versões mais recentes do Visual Studio 2017 ou Visual Studio 2019 com o mesmo HoloLens serão afetados. As versões mais Visual Studio implantam uma nova versão de um componente, mas os arquivos da versão mais antiga são deixados no dispositivo, fazendo com que a versão mais recente falhe.  Isso causa a seguinte mensagem de erro: DEP0100: Verifique se o dispositivo de destino tem o modo de desenvolvedor habilitado. Não foi possível obter uma licença de desenvolvedor \<ip\> no devido a erros 80004005.

#### <a name="workaround"></a>Solução alternativa

Nossa equipe está trabalhando em uma correção no momento. Enquanto isso, você pode usar as seguintes etapas para resolver o problema e ajudar a desbloquear a implantação e a depuração:  

1. Abra o Visual Studio.

1. Selecione **Arquivo** > **Novo** > **Projeto**.

1. Selecione **Visual C#**  >  **Windows Aplicativo de** Console da Área de Trabalho  >  **(.NET Framework)**.

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

1. Navegue até C:\Arquivos de Programas (x86)\Windows Kits\10\bin\10.0.18362.0\x86 e altere o filtro para Todos os **Arquivos ( \* . \* )**. .

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

1. Execute o executável e forneça o endereço IP do dispositivo como um argumento de linha de comando. (Se estiver conectado usando USB, você poderá usar 127.0.0.1; caso contrário, use o endereço IP Wi-Fi dispositivo.)  Por exemplo, "HoloLensDeploymentFix 127.0.0.1".

1. Depois que a ferramenta sair sem nenhuma mensagem (isso deve levar apenas alguns segundos), agora você poderá implantar e depurar do Visual Studio 2017 ou mais novo.  O uso contínuo da ferramenta não é necessário.

Forneceremos mais atualizações à medida que elas se tornarem disponíveis.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemas ao iniciar o Microsoft Store aplicativos no HoloLens

> [!NOTE]
> Última Atualização: 02/04 às 10h – Problema resolvido.

Você pode ter problemas ao tentar iniciar o Microsoft Store e aplicativos no HoloLens. Determinamos que o problema ocorre quando as atualizações do aplicativo em segundo plano implantam uma versão mais recente dos pacotes de estrutura em sequências específicas enquanto um ou mais aplicativos dependentes ainda estão em execução. Nesse caso, uma atualização automática de aplicativos entregue uma nova versão do .NET Native Framework (versão 10.0.25531 a 10.0.27413) fez com que os aplicativos que estão em execução não sejam atualizados corretamente para todos os aplicativos em execução consumindo a versão anterior da estrutura.  O fluxo para a atualização da estrutura é o seguinte:

1. O novo pacote de estrutura é baixado da loja e instalado.

1. Todos os apps usando a estrutura mais antiga são 'atualizados' para usar a versão mais recente.

Se a etapa 2 for interrompida antes da conclusão, todos os aplicativos para os quais a estrutura mais nova não foi registrada falharão ao iniciar no menu Iniciar.  Acreditamos que qualquer aplicativo no HoloLens pode ser afetado por esse problema.

Alguns usuários relataram que fechar aplicativos suspensos e iniciar outros aplicativos, como o Hub de Comentários, Visualizador 3D ou Fotos, resolve o problema para eles– no entanto, isso não funciona 100% do tempo.

Causamos raiz que esse problema não causava a atualização em si, mas um bug no sistema operacional que resultou na atualização da estrutura .NET Native está sendo tratada incorretamente. Temos o prazer de anunciar que identificamos uma correção e lançamos uma atualização (versão do sistema operacional 17763.380) que contém a correção.  

Para ver se o dispositivo pode fazer a atualização:

1. Acesse o aplicativo Configurações e abra **Atualizar & Segurança**.

1. Selecione **Verificar se há Atualizações.**

1. Se a atualização para 17763.380 estiver disponível, atualize para este build para receber a correção do bug do Trava do Aplicativo.

1. Após a atualização para esta versão do sistema operacional, os Aplicativos devem funcionar conforme o esperado.

Além disso, como fazemos com cada HoloLens do sistema operacional, postemos a imagem FFU no Centro [de Download da Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Se você não quiser fazer a atualização, lançamos uma nova versão do aplicativo Microsoft Store UWP a partir de 29/3. Depois de ter a versão atualizada da Store:

1. Abra o Store e confirme se ele é carregado.
1. Use o gesto de abrir o menu.
1. Tentativa de abrir aplicativos desfeitos anteriormente.
1. Se ele ainda não puder ser lançado, toque e segure o ícone do aplicativo desfeito e selecione desinstalar.
1. Reinstale esses aplicativos da loja.

Se o dispositivo ainda não puder carregar aplicativos, você poderá fazer sideload de uma versão do .NET Native Framework e runtime por meio do centro de download seguindo estas etapas:

1. Baixe esse [arquivo zip no](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Centro de Download da Microsoft. O desembaixamento produzirá dois arquivos.  Microsoft .NET.Native.Runtime.1.7.appx e Microsoft .NET.Native.Framework.1.7.appx.

1. Verifique se o dispositivo está desbloqueado em dev.  Se você ainda não fez isso antes, consulte [Usando o Windows Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal) para obter instruções.

1. Em seguida, você deseja entrar no Windows Portal de Dispositivos. Nossa recomendação é fazer isso por USB e você faria isso digitando http://127.0.0.1:10080 em seu navegador.

1. Depois que você tiver a Windows Portal de Dispositivos, será necessário "carregar lado a lado" os dois arquivos baixados. Para fazer isso, você precisa ir para a barra do lado esquerdo até chegar à seção **Aplicativos** e selecionar **Aplicativos**.

1. Em seguida, você verá uma tela semelhante à abaixo.  Você deseja ir para a  seção que diz Instalar Aplicativo e navegar até o local em que desemcortou esses dois arquivos APPX. Você só pode fazer um de cada vez, portanto, depois de selecionar o primeiro, clique em "Ir" na seção Implantar. Em seguida, faça isso para o segundo arquivo APPX.

   ![Windows Portal de Dispositivos instalar o Side-Loaded aplicativo.](images/20190322-DevicePortal.png)

1. Neste ponto, acreditamos que seus aplicativos devem começar a funcionar novamente e que você também pode chegar à Store.

1. Em alguns casos, é necessário executar a etapa adicional de iniciar o aplicativo Visualizador 3D antes que os aplicativos afetados sejam lançados.

Agradecemos sua saúde enquanto passamos pelo processo para resolver esse problema e estamos ansiosos para continuar trabalhando com nossa comunidade para criar experiências bem-sucedidas de Realidade Misturada.

### <a name="device-update"></a>Atualização do dispositivo

- 30 segundos após uma nova atualização, o shell pode desaparecer uma vez. Execute o gesto **de bloom** para retomar sua sessão.

### <a name="visual-studio"></a>Visual Studio

- Confira [Instalar as ferramentas](/windows/mixed-reality/install-the-tools) para a versão mais atualizada do Visual Studio recomendada para HoloLens desenvolvimento.

- Ao implantar um aplicativo do Visual Studio para seu HoloLens, você poderá ver o erro: A operação solicitada não pode ser executada em um arquivo com uma seção mapeada **pelo usuário aberta. (Exceção de HRESULT: 0x800704C8)**. Se isso acontecer, tente novamente e sua implantação geralmente terá êxito.

### <a name="api"></a>API

- Se o aplicativo define o ponto [de](/windows/mixed-reality/focus-point-in-unity) foco por trás do usuário ou o normal para camera.forward, os hologramas não aparecerão em Captura de Realidade Misturada ou vídeos. Até que esse bug seja corrigido no Windows, [](/windows/mixed-reality/focus-point-in-unity) se os aplicativos definirem ativamente o ponto de foco, eles deverão garantir que o plano normal seja definido para frente da câmera oposta (por exemplo, normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Controle sem Fio Xbox

- O Controlador Sem Fio do Xbox S deve ser atualizado antes de poder ser usado com HoloLens. Verifique se você [está atualizado antes](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) de tentar emparelhar seu controlador com um HoloLens.

- Se você reinicializar o HoloLens enquanto o Controlador Sem Fio do Xbox estiver conectado, o controlador não se reconectará automaticamente ao HoloLens. A luz do botão Guia piscará lentamente até que o controlador seja desligado após 3 minutos. Para reconectar o controlador imediatamente, desconexe o controlador mantendo o botão Guia pressionado até que a luz seja desligada. Quando você ligar o controlador novamente, ele será reconectado ao HoloLens.

- Se o HoloLens entrar em espera enquanto o Controlador Sem Fio do Xbox estiver conectado, qualquer entrada no controlador ativasá o HoloLens. Você pode evitar isso ao desligar o controlador quando terminar de usá-lo.

