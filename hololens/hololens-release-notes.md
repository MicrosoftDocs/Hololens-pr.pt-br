---
title: Notas de versão do HoloLens 2
description: Saiba mais sobre atualizações em cada nova versão do HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 0fe78d4b668523de4faa66a64f54c14760a81b12
ms.sourcegitcommit: bddd470ac475dd8fc7b69e8904d18082a83f39e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2020
ms.locfileid: "10997212"
---
# Notas de versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus dispositivos de HoloLens, continuamos a liberar recursos, erros e atualizações de segurança. Nesta página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização do flash completo do HoloLens 2 (FFU) para fazer o [flash do seu dispositivo via complemento avançado de recuperação](hololens-recovery.md#clean-reflash-the-device), [Baixe-o aqui](https://aka.ms/hololens2download). O download é mantido atualizado e fornece a versão mais recente disponível no momento.

>[!NOTE]
> Para ler as notas de versão do emulador do HoloLens, [acesse o arquivo morto](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holográfico, versão 2004 – atualização de setembro de 2020
- Build 19041,1117

Melhorias e correções na atualização:

- Trata de um problema que impedia o Visual Studio de depurar um aplicativo quando SupportsMultipleInstances = "true" está presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy do NCSI para resolver a falha na detecção pela Internet em um proxy de rede. O NCSI pode usar proxy de computador e proxy por perfil para detecção de conectividade à Internet. O proxy por usuário será compatível com o NCSI em lançamento futuro.
- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao terra quando a cabeça do usuário está em uma posição neutra, olhando para a frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ficar perpendicular aos painéis de exibição em vez disso, o que é inclinado para baixo alguns graus em relação à orientação ideal. As versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre fatores forma.
- Melhor controle da mão, o que resulta em menos perdas de controle em cenários específicos.
- Este lançamento contém uma correção para melhorar a qualidade do carimbo de data e hora que pode ter contribuído com problemas de captura de vídeo.

## Windows holográfico, versão 1903 – atualização de setembro de 2020
- Build 18362,1079

Melhorias e correções na atualização:

- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao terra quando a cabeça do usuário está em uma posição neutra, olhando para a frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ficar perpendicular aos painéis de exibição em vez disso, o que é inclinado para baixo alguns graus em relação à orientação ideal. As versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre fatores forma.
- Melhor controle da mão, o que resulta em menos perdas de controle em cenários específicos.

## Windows holográfico, versão 2004 – atualização de agosto de 2020
- Build 19041,1113

Melhorias e correções na atualização:

- O aplicativo configurações não acompanhará mais o usuário em experiências de calibragem de rastreamento de olho ou de acompanhamento da íris.
- Correção de um bug em que a aplicação de um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como conectar-se a uma rede) falhava ao executar as outras ações após a reinicialização do dispositivo devido ao renomeação.
- Esquema de cores modificado para fluxos iniciais de configuração de dispositivos para melhorar a qualidade visual.

## Windows holográfico, versão 1903 – atualização de agosto de 2020
- Build 18362,1074

Esta atualização de qualidade mensal não contém alterações notáveis, incentivamos você a experimentar nossas versões mais recentes para Windows holográfico, versão 2004.

## Windows holográfico, versão 2004-atualização de julho de 2020
- Build 19041,1109

Melhorias e correções na atualização:

- Os desenvolvedores agora podem escolher entre habilitar ou desabilitar o Device portal para exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Brilho da caixa de entrada padrão alterado para 100%.
- Foi corrigido um problema sobre o encaminhamento de HTTPS para o Windows Device portal no HoloLens 2.

## Windows holográfico, versão 1903-atualização de julho de 2020
- Build 18362,1071

Melhorias e correções na atualização:

- Correção de um problema que pode fazer com que os hologramas desapareçam em aplicativos do Unity ao perder ou recuperar o controle.
- Correção de um problema que causava o failback de aplicativos exclusivos do HoloLens para o Shell enquanto uso o emulador do HoloLens com aceleração de hardware em certos dispositivos.
- Foi corrigido um problema relacionado ao encaminhamento HTTPS para o Windows Device portal no HoloLens 2.

## Windows holográfico, versão 2004 – atualização de junho de 2020
- Build 19041,1106

Melhorias e correções na atualização:

- Registros da MRC personalizados agora têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (fone de ouvido com microfone))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "ganho de áudio do aplicativo" na página de captura da realidade misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual de "ganho de áudio do MIC" na página de captura da realidade misturada no Windows Device Portal)
- Correção de um bug para melhorar a qualidade de áudio em cenários de captura de realidade misturada. Especificamente, esta correção deve eliminar a falha de áudio na gravação quando o menu **Iniciar** é exibido.
- Estabilidade aprimorada de holograma em vídeos gravados.
- Corrigido um problema em que a captura de realidade misturada não pôde gravar vídeo após o dispositivo ter sido deixado em estado de espera por vários dias.
- A API HolographicSpace. userpresence geralmente está desabilitada para aplicativos Unity. Esse comportamento evita um problema que fez com que alguns aplicativos pausem quando o visor foi invertido, mesmo se a configuração "executar em segundo plano" estivesse habilitada. A API agora está habilitada para versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Quando você acessa o Device portal em uma conexão Wi-Fi, um navegador da Web pode impedir o acesso devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo se o certificado do dispositivo era confiável anteriormente. Nesse caso, você não pode progredir para o Device portal, pois não há a opção de ignorar avisos de segurança. Esta atualização resolveu o problema. Se o certificado do dispositivo foi baixado anteriormente e confiável em um computador para remover avisos de segurança do navegador e o erro SSL ocorrer, o novo certificado precisará ser baixado e confiável para corrigir os avisos de segurança do navegador.
- Habilitou a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
- Foi adicionada uma configuração em **configurações**de  >  **System**  >  **hologramas** do sistema que permite aos usuários remover automaticamente todos os hologramas de casa misturada da realidade quando o dispositivo é desligado.
- Correção de um problema que causava aplicativos HoloLens que alteravam o formato de pixel para renderização em preto no emulador do HoloLens.
- Correção de um bug que causou uma falha durante o logon íris.
- Correção de um problema sobre downloads de lojas repetidos para aplicativos já existentes.
- Correção de um bug para impedir que aplicativos imersivas Abram o Microsoft Edge repetidamente.
- Correção de um problema com as inicializações do aplicativo fotos em inicializações iniciais após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## Windows holográfico, versão 1903 – atualização de junho de 2020
- Build 18362,1064

Melhorias e correções na atualização:

- Registros da MRC personalizados têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (fone de ouvido com microfone))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "ganho de áudio do aplicativo" na página de captura da realidade misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual de "ganho de áudio do MIC" na página de captura da realidade misturada no Windows Device Portal)
- A API HolographicSpace. userpresence geralmente está desabilitada para aplicativos Unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração para executar em segundo plano estiver habilitada. A API agora está habilitada para versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Correção de um problema que causava aplicativos HoloLens que alteravam o formato de pixel para renderização em preto no emulador do HoloLens.
- Correção de um problema sobre as inicializações do aplicativo fotos em inicializações iniciais após a atualização da versão 1903.

## Windows holográfico, versão 2004  
- Build-19041,1103

A atualização de software principal de maio de 2020 para o HoloLens 2, o *Windows holográfico, versão 2004* inclui um host de novos recursos incríveis, como suporte para o piloto automático do Windows, modo escuro do aplicativo, suporte para Ethernet USB para pontos de acesso 5g/LTE e muito mais. Para atualizar para a versão mais recente, abra o aplicativo **configurações**   , vá para **Atualizar & segurança**e selecione o botão verificar se há **atualizações**   . 

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurar e configurar tranqüilamente novos dispositivos para produção usando o piloto automático do Windows                 |
|       Suporte do FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar integralmente um pacote de provisionamento de uma unidade USB ao seu HoloLens                              |
|       Status de instalação do aplicativo                 |          Verificar se o status de instalação no aplicativo configurações para aplicativos foi enviado por push para o HoloLens 2 via MDM               |
|       Provedores de serviços de configuração (CSPs)   |          Novos provedores de serviços de configuração adicionados para melhorar os recursos de controle de administração                 |
|       Suporte a USB 5G/LTE                       |          O recurso Ethernet USB expandida permite suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que dão suporte a modos escuros e leves, melhorando a experiência de visualização        |
|       Comandos de voz                             |          Suporte para comandos de voz do sistema adicionais para controlar o HoloLens-sem viva-voz                           |
|       Melhorias no controle de mão                 |          Melhorias de rastreamento de mão tornam os botões e as interações de ardósia 2D mais precisos                        |
|       Melhorias e correções de qualidade                 |          Vários aprimoramentos de desempenho do sistema e confiabilidade em toda a plataforma                            |

### Suporte para o piloto automático do Windows

O piloto automático do Windows para o HoloLens 2 permite que o canal de vendas do dispositivo tenha cancelamento de registro do HoloLens em seu locatário do Intune. Quando os dispositivos chegam, eles estão prontos para serem implantados como dispositivos compartilhados em seu locatário. Para tirar proveito da autoimplantação, o dispositivo deve se conectar a uma rede durante a primeira tela da instalação usando um dongle USB-C-to-Ethernet ou USB-C-to-LTE.

Depois que um usuário iniciar o processo de implantação automática do AutoPilot, o processo concluirá as seguintes etapas:

1. Ingresso do dispositivo no Azure Active Directory (Azure AD)
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe os perfis de rede, certificados e políticas direcionados aos dispositivos.
1. Provisione este dispositivo.
1. Apresente a tela de entrada ao usuário.

Saiba mais no [Guia de avaliação do Windows AutoPilot para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Entre em contato com seu gerente de conta para participar da visualização do AutoPilot agora. Os dispositivos prontos para o AutoPilot começarão a ser entregues em breve.*

### Suporte a chave de segurança FIDO2

Alguns usuários compartilham um dispositivo HoloLens com outras pessoas em um ambiente de trabalho ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. A rápida identidade online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre diretamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação com senha baseada em padrões "não Phish" que pode ser inserido em qualquer fator forma. FIDO é um padrão aberto para autenticação com senha inexistente. Ele permite que usuários e organizações se conectem a seus recursos sem nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma integrada a um dispositivo.

Para começar, consulte [Habilitar entrada de chave de segurança sem senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### Registro de MDM aprimorado via pacote de provisionamento

Os pacotes de provisionamento permitem que você defina a configuração do HoloLens por meio de um arquivo de configuração, em vez de usar a experiência inicial pelo HoloLens. Anteriormente, os pacotes de provisionamento precisavam ser copiados para a memória interna do HoloLens. Agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizá-los em vários dispositivos HoloLens e você possa provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também dão suporte a um campo para inscrição no gerenciamento de dispositivos, portanto, não há configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do designer de configuração do Windows na Windows Store em seu computador.
1. Selecione **provisionar dispositivos hololens**para  >  **configurar dispositivos hololens 2**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C em qualquer HoloLens atualizado. Em seguida, pressione os botões de energia para **baixo volume**  +  **power** para aplicar seu pacote de provisionamento.

### Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento de aplicativos MDM para aplicativos de linha de negócios são essenciais para o HoloLens. Administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **configurações**  >  **contas**  >  **acessar trabalho ou escola**  >  **clique nas informações da sua conta**  >  **Info**.

### Provedores e políticas adicionais

Um [provedor de serviços de configuração (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface que lê, define, modifica ou exclui definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores têm sobre dispositivos HoloLens implantados. Para obter a lista de provedores compatíveis com o HoloLens, consulte [CSP do NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novo nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa Configure políticas em dispositivos Windows. Nesta versão, adicionamos novas políticas para HoloLens, que estão listadas aqui. Para saber mais, consulte [CSPs de política com suporte pelo HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

O provedor de serviços de configuração do NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, consulte [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Suporte a Ethernet USB expandido para dispositivos 5G/LTE para compartilhamento de

O suporte foi adicionado para habilitar certos dispositivos de banda larga móvel, como telefones 5G/LTE e Wi-Fi hotpots, quando eles estiverem no compartilhamento de Internet para o HoloLens 2 via USB. Esses dispositivos agora são exibidos em **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos de banda larga móvel que exijam um driver externo). Essa funcionalidade permite conexões de alta largura de banda quando o Wi-Fi não está disponível e o compartilhamento de compartilhamento de Wi-Fi não é o suficiente. Para saber mais sobre os dispositivos USB com suporte, consulte [conectar a dispositivos Bluetooth e USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Melhorias no controle de mão

Esta versão inclui vários aprimoramentos de controle de mão:

- **Ponteiro de pose:** O sistema agora se resiste à curva do dedo do índice quando ele é obstruídado pelo Palm. Essa alteração melhora a precisão ao enviar botões, digitar, rolar conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Aprimoramos a detecção do gesto de tocar no ar. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta suas mãos em seus lados.
- **Confiabilidade da opção do usuário:** O sistema agora é mais rápido e mais confiável na atualização do tamanho da mão quando você compartilha um dispositivo.
- **Roubo reduzido:** Aprimoramos a manipulação de casos em que há mais de duas mãos em vista dos sensores. Se várias pessoas estiverem trabalhando juntas, há agora uma chance muito menor de que a mão rastreada vai "saltar" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Correção de um problema que causava o rastreamento da mão para parar de funcionar quando o dispositivo está sob carga elevada.

### Modo escuro

Muitos aplicativos do Windows agora dão suporte a modos escuros e leves. Usuários do HoloLens 2 podem escolher o modo padrão para aplicativos que dão suporte a ambos. Após a atualização, o modo de aplicativo padrão é "escuro", mas você pode facilmente alterar essa configuração: Navegue até **configurações**  >  cores do**sistema**  >  **Colors**  >  **escolha o modo de aplicativo padrão**. 

Estes aplicativos "in-box" dão suporte ao modo escuro: 

- Configurações 
- Microsoft Store 
- Mail 
- Calendário 
- Explorador de Arquivos 
- Hub de Feedback 
- OneDrive 
- Fotos 
- Visualizador 3D 
- Filmes e TV 

![Lado a lado do Windows em modo escuro](images/DarkMode.jpg)

### Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, consulte [usar sua voz para operar com o HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulte também [idiomas com suporte para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Atualizações da Cortana

O aplicativo atualizado integra-se com o Microsoft 365 para ajudá-lo a realizar mais em seus dispositivos (atualmente em inglês dos EUA – somente em inglês). No HoloLens 2, a Cortana não dá mais suporte a determinados comandos específicos do dispositivo, como o ajuste de volume ou a reinicialização. Essas opções agora são suportadas pelos novos comandos de voz do sistema. Saiba mais sobre o novo aplicativo da Cortana em nosso [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibragem de vídeo ativo. Esse recurso melhora a estabilidade e o alinhamento de hologramas. Agora, eles permanecem no lugar quando você move sua cabeça de um lado para outro.
- Correção de um bug em que o streaming de Wi-Fi para HoloLens foi interrompido periodicamente. Se um aplicativo indicar que precisa de transmissão de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Foi corrigido um dispositivo que ocorreu durante o streaming no modo de pesquisa.
- Correção de um bug em alguns casos em que o usuário certo não será exibido na tela de entrada ao retomar uma sessão.
- Correção de um problema em que os usuários não puderam exportar logs do MDM por meio **das configurações**.
- Correção de um problema em que a precisão do controle de olho logo após a configuração imediata pode ser menor do que o esperado.
- Correção de um problema em que o subsistema de acompanhamento de olho falhou ao inicializar ou executar a calibragem em determinadas condições.
- Correção de um problema em que a calibragem de olho seria solicitada para um usuário já calibrado.
- Correção de um problema em que um driver falhava durante a calibragem de olho.
- Correção de um problema em que as prensas do botão de energia repetidas podem causar um tempo limite do sistema de 60 a um segundo e falha de Shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um botão **compartilhar** no Hub de feedback para que os usuários possam compartilhar os comentários com mais facilidade.
- Correção de um bug em que o RoboRaid wan't instalado corretamente.

### Problemas conhecidos

- Um problema com o idioma do sistema zh-CN impede que os comandos de voz tenham uma captura de realidade mista ou exibam o endereço IP do dispositivo.
- Um problema exige que você inicie o aplicativo da Cortana após iniciar o dispositivo para usar a ativação de voz "Ei Cortana". Se você atualizou a partir de uma compilação do 18362, você também pode ver um segundo bloco do aplicativo para a versão anterior do aplicativo da Cortana que não funciona mais em **início**.

## Windows holográfico, versão 1903 – maio de 2020 Update 
- Build 18362,1061

Esta atualização de qualidade mensal não contém alterações notáveis porque a equipe estava trabalhando na versão 2004 do Windows holográfico pode ser atualizada, conforme descrito anteriormente.

## Windows holográfico, versão 1903 – atualização de abril de 2020
- Build 18362,1059

**Modo escuro para aplicativos com suporte** 

Muitos aplicativos do Windows dão suporte ao modo escuro e Light. Os clientes do HoloLens 2 agora podem escolher o modo padrão para aplicativos compatíveis com o esquema de cores. Com base nos comentários dos clientes, definimos o modo de aplicativo padrão como "escuro", mas você pode facilmente alterar essa configuração a qualquer momento: Navegue até **configurações > sistema > cores** para localizar **"escolher o modo de aplicativo padrão".**

Estes aplicativos "in-box" dão suporte ao modo escuro:
- Configurações
- Microsoft Store
- Mail
- Calendário
- Explorador de Arquivos
- Hub de Feedback
- OneDrive
- Fotos
- Visualizador 3D
- Filmes e TV

**Melhorias e correções também na atualização:** 
- Verificado se as sobreposições do Shell estão incluídas em capturas de realidade misturadas.
- Agora, os desenvolvedores não reais podem usar a página modo de exibição 3D no Device portal para testar e depurar seus aplicativos.
- Estabilidade aprimorada do holograma em captura de realidade mista quando o algoritmo *HolographicDepthReprojectionMethod DepthReprojection* é usado.
- Foi corrigido o erro "classe de API do WinRT IStreamSocketListener não registrada" em aplicativos ARM de 32 bits.

## Windows holográfico, versão 1903-atualização de março de 2020 
- Build 18362,1056

Melhorias e correções na atualização:

- Estabilidade aprimorada do holograma em captura de realidade mista quando o algoritmo de *autoplanar do HolographicDepthReprojectionMethod* é usado.
- Verificado se o sistema de coordenadas anexado a um exemplo de MF de profundidade é consistente com a documentação pública.
- Maior produtividade do desenvolvedor ao permitir que os clientes colem grandes quantidades de texto por meio do Device Portal.

## Windows holográfico, versão 1903 – atualização de fevereiro de 2020 
- Build 18362,1053

Melhorias e correções na atualização:

- Desativada temporariamente a API HolographicSpace. userpresence para aplicativos Unity. Essa alteração evita um problema que causava pausa em alguns aplicativos quando o visor foi invertido, mesmo se a configuração "executar em segundo plano" estivesse habilitada.
- Correção de uma falha aleatória HUP causada pelo acompanhamento à mão, em que o usuário observou um congelamento da interface do usuário e, em seguida, voltou para o Shell após vários segundos.
- Controle de mão aprimorado para que, quando você fizer a reportar com o seu índice, a parte superior do dedo seja menos provável de ser deondulado inesperadamente.
- Maior confiabilidade de controle de cabeçotes, associação espacial e outros tempos de execução.

## Windows holográfico, versão 1903 – atualização de janeiro de 2020 
- Build 18362,1043
 
Melhorias e correções na atualização:

- Estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador do HoloLens 2.

## Windows holográfico, versão 1903 – atualização de dezembro de 2019 
- Build 18362,1042

Melhorias e correções na atualização:

- Foram introduzidas correções de reprodução do último estágio (LSR). Renderização visual aprimorada de hologramas para parecer mais estável e mais nítido por uma contabilidade mais precisa de sua profundidade. Esse sintoma será mais perceptível após essa atualização se os aplicativos não definirem a profundidade dos hologramas corretamente.
- Correção da estabilidade de aplicativos exclusivos e navegação entre aplicativos exclusivos.
- Corrigido um problema em que a captura de realidade misturada não pôde gravar vídeo após o dispositivo estar em estado de espera por vários dias.
- Estabilidade aprimorada do holograma.

## Windows holográfico, versão 1903 – atualização de novembro de 2019 
- Build 18362,1039

Melhorias e correções na atualização:

- Funcionalidade corrigida de **selecionar** comandos de voz durante a configuração inicial para en-CA e en-au.
- Melhor qualidade visual dos objetos colocados na versão mais recente do Unity e do kit de ferramentas de realidade mista (MRTK).
- Problemas de endereçamento corrigidos com os aplicativos do holográfico ficam presos em um estado pausado na inicialização até que o menu iniciar tenha sido aberto e depois fechado.
- OpenXR correções e melhorias de conformidade do tempo de execução do HoloLens 2 e do emulador.
