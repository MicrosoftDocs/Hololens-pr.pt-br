---
title: Notas de versão do HoloLens 2
description: Saiba mais sobre atualizações em cada nova versão do HoloLens.
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
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827627"
---
# Notas de versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus dispositivos de HoloLens, continuamos a liberar atualizações de recursos, erros e segurança. Nesta página, você pode saber mais sobre as novidades do HoloLens a cada mês. Se quiser baixar a versão mais recente do FFU 2 para fazer o flash do seu dispositivo via [complemento avançado de recuperação](hololens-recovery.md#clean-reflash-the-device) , você pode baixá-lo [aqui](https://aka.ms/hololens2download). Isso é mantido atualizado e será compatível com a versão mais recente disponível em geral. 

As notas de versão do emulador do HoloLens podem ser encontradas [aqui](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holográfico, versão 2004 – atualização de junho de 2020
- Build 19041,1106

Melhorias e correções na atualização:

- Registros da MRC personalizados têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No efeito de vídeo da MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (fone de ouvido com microfone))
  - No efeito de áudio da MRC:
    - LoopbackGain (o valor atual de "ganho de áudio do aplicativo" na página de captura da realidade misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual de "ganho de áudio do MIC" na página de captura da realidade misturada no Windows Device Portal)
- Esta atualização contém uma correção de bug que melhora a qualidade de áudio em cenários de captura de realidade misturada. Especificamente, ele deve eliminar qualquer falha de áudio na gravação quando o menu iniciar for exibido.
- Estabilidade aprimorada de holograma em vídeos gravados.
- Resolve um problema em que a captura de realidade misturada não pôde gravar vídeo após o dispositivo ser deixado no estado de espera por vários dias.
- A API HolographicSpace. userpresence geralmente é desabilitada para aplicativos Unity para evitar um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração para executar em segundo plano estiver habilitada. A API agora está habilitada para versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Ao acessar o Device portal em uma conexão WiFi, um navegador da Web pode impedir o acesso devido a um certificado inválido, indicando um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo que o certificado do dispositivo tenha sido confiável anteriormente.  Nesse caso, não será possível fazer o andamento do Device portal, pois as opções para ignorar os avisos de segurança não estarão disponíveis.  Esta atualização resolve o problema.  Se o certificado do dispositivo foi baixado anteriormente e confiável em um computador para remover os avisos de segurança do navegador e o erro SSL for encontrado, o novo certificado precisará ser baixado e confiável para corrigir os avisos de segurança do navegador.
- Habilitou a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
- Nova configuração que os usuários podem encontrar em configurações > holograma > do sistema, que permite aos usuários remover automaticamente todos os hologramas da casa misturada quando o dispositivo é desligado.
- Correção de um problema que causava aplicativos HoloLens que alteravam o formato de pixel para renderização em preto no emulador do HoloLens.
- Correção de um bug que causou uma falha durante o logon da íris.
- Corrige um problema em torno de downloads de lojas repetidos para aplicativos já atuais.
- Correção de um bug para impedir que aplicativos imersivas iniciem a borda várias vezes.
- Corrige um problema em torno de inicializações do aplicativo fotos em inicializações iniciais após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## Windows holográfico, versão 1903 – atualização de junho de 2020
- Build 18362,1064

Melhorias e correções na atualização:

- Registros da MRC personalizados têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No efeito de vídeo da MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (fone de ouvido com microfone))
  - No efeito de áudio da MRC:
    - LoopbackGain (o valor atual de "ganho de áudio do aplicativo" na página de captura da realidade misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual de "ganho de áudio do MIC" na página de captura da realidade misturada no Windows Device Portal)
- A API HolographicSpace. userpresence geralmente é desabilitada para aplicativos Unity para evitar um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração para executar em segundo plano estiver habilitada. A API agora está habilitada para versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Correção de um problema que causava aplicativos HoloLens que alteravam o formato de pixel para renderização em preto no emulador do HoloLens.
- Corrige um problema em torno de inicializações do aplicativo fotos em inicializações iniciais após a atualização da versão 1903.

## Windows holográfico, versão 2004  
Build-19041,1103

Ficamos felizes em anunciar nossa importante atualização do software de maio de 2020 para o HoloLens 2, **Windows holográfico, versão 2004**. Esta versão inclui uma grande variedade de novos recursos incríveis, como suporte para o piloto automático do Windows, modo escuro do aplicativo, suporte para Ethernet USB para pontos de acesso 5G/LTE e muito mais. Para atualizar para a versão mais recente, abra o **aplicativo Configurações**, vá para **Atualizar & segurança**e, em seguida, selecione o botão verificar se há **atualizações**   . 

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurar e configurar tranqüilamente novos dispositivos para produção com o AutoPilot do Windows                 |
|       Suporte do FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar integralmente um pacote de provisionamento de uma unidade USB ao seu HoloLens                              |
|       Status de instalação do aplicativo                 |          Verificar se o status de instalação de aplicativos foi enviado para o HoloLens 2 via MDM, no aplicativo configurações              |
|       Provedores de serviços de configuração (CSPs)   |          Novos provedores de serviços de configuração (CSPs) adicionados aprimorando recursos de controle de administração.                 |
|       Suporte a USB 5G/LTE                       |          O recurso Ethernet USB expandida permite suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro para aplicativos que dão suporte a modos escuros e leves, melhorando a experiência de visualização        |
|       Comandos de voz                             |          Suporte para comandos de voz do sistema adicionais para controlar o HoloLens, sem mãos                           |
|       Melhorias no controle de mão                 |          Melhorias de rastreamento de mão tornam os botões e as interações de ardósia 2D mais precisos                        |
|       Melhorias e correções de qualidade                 |          Vários aprimoramentos de desempenho do sistema e confiabilidade em toda a plataforma                            |

### Suporte para o piloto automático do Windows 

O piloto automático do Windows para o HoloLens 2 permite que o canal de vendas do dispositivo tenha cancelamento de registro do HoloLens em seu locatário do Intune.  Quando os dispositivos chegam, eles estão prontos para serem implantados como dispositivos compartilhados em seu locatário. Para tirar proveito da autoimplantação, os dispositivos precisarão se conectar a uma rede durante a primeira tela no programa de instalação usando um adaptador USB-C para Ethernet ou o dongle USB-C para o dongle LTE. 

Quando um usuário iniciar o processo de autoimplantação do piloto automático, o processo concluirá as etapas a seguir: 

1. Ingresso do dispositivo no Azure Active Directory (Azure AD) 
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM). 
1. Baixe os perfis de rede, certificados e políticas direcionados aos dispositivos. 
1. Provisione este dispositivo. 
1. Apresente a tela de entrada ao usuário. 

Saiba mais no [Guia de avaliação do Windows AutoPilot para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

**Entre em contato com seu gerente de conta para participar da visualização do AutoPilot agora. Os dispositivos prontos para o AutoPilot começarão a ser entregues em breve.**

### Suporte a chave de segurança FIDO2 

Muitas pessoas compartilham um dispositivo HoloLens com muitas pessoas em um ambiente de trabalho ou de estudante. Se os dispositivos são compartilhados entre alunos em uma sala de aula ou se estão com check-out em um armário de dispositivo, é importante poder alterar os usuários de forma rápida e fácil sem digitar nomes de usuário e senhas longos. 

FIDO permite que qualquer pessoa em sua organização (locatário do AAD) Conecte-se perfeitamente a um HoloLens sem digitar um nome de usuário ou senha. 

As chaves de segurança FIDO2 são um método de autenticaçãoless com senha com base em padrões que pode ser redirecionado em qualquer fator forma. O Fast Identity online (FIDO) é um padrão aberto para autenticação por senha. O FIDO permite que usuários e organizações aproveitem o padrão para entrar em seus recursos sem nome de usuário ou senha usando uma chave de segurança externa ou uma chave de plataforma integrada a um dispositivo. 

Leia os [documentos de segurança com senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) para começar. 

### Registro de MDM aprimorado via pacote de provisionamento 

Os pacotes de provisionamento permitem que você defina a configuração do HoloLens por meio de um arquivo de configuração, em vez de passar pela experiência inicial do HoloLens. Anteriormente, os pacotes de provisionamento precisavam ser copiados para a memória interna do HoloLens, agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizar em vários HoloLenss e para que mais pessoas possam provisionar o HoloLens em paralelo.  Além disso, os pacotes de provisionamento dão suporte a um novo campo para se inscrever no gerenciamento de dispositivos, para que não haja uma configuração manual de configuração posterior. 

1. Para experimentar, baixe a versão mais recente do designer de configuração do Windows na Windows Store para seu PC. 
1. Selecione **provisionar dispositivos hololens** > selecionar **configurar dispositivos hololens 2** 
1. Crie seu perfil de configuração e, quando terminar, copie todos os arquivos criados para um dispositivo de armazenamento USB-C. 
1. Conecte-a a qualquer HoloLens atualizado e pressione **volume + energia** para aplicar seu pacote de provisionamento. 

### Status de instalação do aplicativo de linha de negócios 

A implantação e o gerenciamento de aplicativos MDM para aplicativos de linha de negócios (LOB) são essenciais para nossos clientes. Administradores e usuários precisam ser capazes de exibir o status de instalação do aplicativo, para fins de auditoria e diagnóstico. Neste lançamento, adicionamos mais detalhes em **configurações > contas > acessar o trabalho ou escola > clique na sua conta > informações.**

### Provedores e políticas adicionais 

Um [provedor de serviços de configuração (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface que lê, define, modifica ou exclui definições de configuração em um dispositivo. Neste lançamento, estamos adicionando suporte para mais políticas, aumentando os administradores de controle que têm sobre dispositivos HoloLens implantados. Para obter a lista de CSPs com suporte do HoloLens, acesse este [link](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Novo nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa Configure políticas em dispositivos Windows. Nesta versão, estamos adicionando novas políticas para o HoloLens, listadas abaixo. Você pode saber mais sobre as políticas com suporte [aqui](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

**CSP NetworkQoSPolicy** O provedor de serviços de configuração do NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Você pode saber mais sobre essa política [aqui](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). 

### Suporte a Ethernet USB expandido para dispositivos 5G/LTE para compartilhamento de

O suporte foi adicionado para habilitar certos dispositivos de banda larga móvel, como telefones 5G/LTE e WiFi hotpots, quando o compartilhamento de Internet para o HoloLens 2 via USB. Esses dispositivos serão exibidos nas configurações de rede como outra conexão Ethernet. Não há suporte para dispositivos de banda larga móvel que exijam um driver externo. Isso permite conexões de alta largura de banda em cenários em que o WiFi não está disponível, e o compartilhamento de conexão WiFi não é suficiente. Você pode saber mais sobre os dispositivos USB suportados [aqui](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Melhorias no controle de mão

O controle de mão recebeu várias melhorias nesta versão. 

- **Ponteiro de pose:** Agora, o sistema resistirá entortando o dedo do índice quando ele se tornar obstruída pela Palm.  Isso melhora a precisão ao pressionar botões, digitar, rolar conteúdo e muito mais! 
- **Toques acidentais reduzidos:** Aprimoramos a detecção do gesto AirTap.  Agora há menos ativações acidentais em vários casos comuns, como, por exemplo, descartando suas mãos para o seu lado. 
- **Confiabilidade da opção do usuário:** Agora o sistema está mais rápido e mais confiável na atualização do tamanho da mão ao compartilhar um dispositivo. 
- **Roubo reduzido:** Aprimoramos a manipulação de casos em que há mais de duas mãos na exibição dos sensores.  Se várias pessoas estiverem trabalhando juntas, agora há uma chance muito menor de que a mão rastreada passará do usuário para a mão de outra pessoa na cena. 
- **Confiabilidade do sistema:** Correção de um problema que causava o rastreamento de mão para parar de funcionar por um período se o dispositivo estiver em alta carga. 

### Modo escuro

Muitos aplicativos do Windows agora dão suporte a modos escuros e leves, e os clientes do HoloLens 2 podem escolher o modo padrão para aplicativos que dão suporte a ambos. Uma vez atualizado, o modo de aplicativo padrão será "escuro", mas pode ser alterado facilmente. Navegue até configurações > sistema > cores para localizar "escolher o modo de aplicativo padrão". Aqui estão alguns dos aplicativos em caixa que dão suporte ao modo escuro: 

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

Agora você pode acessar e usar rapidamente os comandos com sua voz ao usar qualquer aplicativo no dispositivo. Se você estiver executando o sistema com um idioma diferente, tente os comandos apropriados nesse idioma. Para obter mais detalhes sobre os comandos e como usá-los, consulte a nossa documentação [aqui](https://docs.microsoft.com/hololens/hololens-cortana).  

### Atualizações da Cortana 

O aplicativo atualizado integra-se com o Microsoft 365, atualmente em inglês (Estados Unidos) apenas, para ajudá-lo a realizar mais em seus dispositivos. No HoloLens 2, a Cortana deixará de dar suporte a certos comandos específicos do dispositivo, como ajustar o volume ou reiniciar o dispositivo, que agora são compatíveis com os novos comandos de voz do sistema mencionados acima. Saiba mais sobre o novo aplicativo da Cortana e sua direção no nosso blog [aqui](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

### Melhorias e correções de qualidade 

Melhorias e correções também na atualização:  
- A atualização introduz um sistema de calibragem de vídeo ativo. Isso melhora a estabilidade e o alinhamento de hologramas, o que o ajuda a ficar em vigor ao mover sua cabeça para a frente. 
- Correção de um bug em que o streaming de Wi-Fi para HoloLens é interrompido periodicamente. Se um aplicativo indicar que ele precisa de transmissão de baixa latência, esta correção pode ser realizada chamando [essa função](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode). 
- Correção de um problema em que o dispositivo pode travar durante o streaming no modo de pesquisa. 
- Correção de um bug em alguns casos, o usuário certo não será exibido na tela de entrada ao retomar a sessão. 
- Correção de um problema em que os usuários não puderam exportar logs do MDM por meio das configurações. 
- Correção de um problema em que a precisão do controle ocular logo após a configuração imediata pode ser menor do que a especificação. 
- Correção de um problema em que o subsistema de acompanhamento ocular falhava ao inicializar e/ou executar a calibragem em determinadas condições. 
- Correção de um problema em que a calibragem de olho seria solicitada a um usuário já calibrado. 
- Correção de um problema em que um driver falhava durante a calibragem de olho. 
- Correção de um problema em que as prensas do botão de energia repetidas podem causar uma falha de tempo limite do sistema de 60 segundos e falha no Shell. 
- Estabilidade aprimorada para buffers de profundidade. 
- Botão "compartilhar" adicionado no Hub de feedback para que os usuários possam compartilhar seus comentários com mais facilidade. 
- Correção de um bug em que o RoboRaid não foi instalado corretamente. 

### Problemas conhecidos

- Estamos investigando um problema que envolve o uso da linguagem de sistema zh-CN que impede os comandos de voz para fazer uma captura de realidade mista ou exibir o endereço IP do dispositivo do trabalho.
- Estamos investigando um problema que exige que você inicie o aplicativo da Cortana após a inicialização do dispositivo para usar a ativação de voz "Ei Cortana" e, se você tiver atualizado a partir de uma compilação do 18362, poderá ver um segundo bloco do aplicativo para a versão anterior do aplicativo da Cortana em iniciar que não funciona mais. 

## Windows holográfico, versão 1903 – maio de 2020 Update 
- Build 18362,1061

Esta atualização de qualidade mensal não contém nenhuma alteração de nota porque a equipe tem se concentrado em oferecer a você a atualização de recursos de alta qualidade agora disponível no Windows holográfico, a versão 2004 pode ser atualizada detalhadamente. Aproveite esta oportunidade para passar para a atualização de recursos mais recente para ter uma infinidade de novas alterações incríveis.

## Windows holográfico, versão 1903 – atualização de abril de 2020
- Build 18362,1059

**Modo escuro para aplicativos com suporte** 

Muitos aplicativos do Windows dão suporte a modos escuros e leves, e logo os 2 usuários do HoloLens 2 podem escolher o modo padrão para aplicativos que dão suporte a ambos os esquemas de cores! Com base no feedback intensamente positivo do cliente, com esta atualização, estamos definindo o modo de aplicativo padrão como "escuro", mas você pode facilmente alterar essa configuração a qualquer momento.
Navegue até **configurações > sistema > cores** para localizar **"escolher o modo de aplicativo padrão".**

Aqui estão alguns dos aplicativos em caixa que dão suporte ao modo escuro:
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
- Verifique se as sobreposições do Shell estão incluídas em capturas de realidade misturadas.
- Os desenvolvedores desreales podem usar a página modo de exibição 3D no Device portal para testar e depurar seus aplicativos.
- Melhore a estabilidade do holograma em captura de realidade mista quando o algoritmo HolographicDepthReprojectionMethod DepthReprojection é usado.
- Erro de classe de API IStreamSocketListener do WinRT corrigido no aplicativo ARM de 32 bits.

## Windows holográfico, versão 1903-atualização de março de 2020 
- Build 18362,1056

Melhorias e correções na atualização:

- Melhorar a estabilidade do holograma em uma captura de realidade mista quando o algoritmo de autoplanar do HolographicDepthReprojectionMethod for usado.
- Garante que o sistema de coordenadas anexado a um exemplo de MF de profundidade seja consistente com a documentação pública.
- Melhoria da produtividade dos desenvolvedores ao permitir que os clientes colem uma grande quantidade de texto por meio do Device Portal.

## Windows holográfico, versão 1903 – atualização de fevereiro de 2020 
- Build 18362,1053

Melhorias e correções na atualização:

- Desabilite temporariamente a API HolographicSpace. userpresence para aplicativos Unity para evitar um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração para executar em segundo plano estiver habilitada.
- Correção de uma falha aleatória HUP em um controle à mão, em que o usuário notará um congelamento da interface do usuário e, em seguida, de volta para o Shell após vários segundos.
- Fizemos um aperfeiçoamento no acompanhamento para que, ao mesmo tempo em que estiver usando o dedo, a parte superior do dedo será menos provável de ser enrolada inesperadamente.
- Maior confiabilidade de controle de cabeçotes, associação espacial e outros tempos de execução.

## Windows holográfico, versão 1903 – atualização de janeiro de 2020 
- Build 18362,1043

Melhoria na atualização:

- Melhorias de estabilidade para aplicativos exclusivos ao trabalhar com o emulador do HoloLens 2.

## Windows holográfico, versão 1903 – atualização de dezembro de 2019 
- Build 18362,1042

Melhorias e correções na atualização:

- Introduz correções de LSR (última reprodução de estágio). Aprimora a renderização visual dos hologramas para que pareçam mais estáveis e nítidas por uma contabilidade mais precisa da sua profundidade. Isso será mais perceptível se os aplicativos não definirem a profundidade dos hologramas corretamente, após a atualização.
- Corrige estabilidade de aplicativos exclusivos e navegação entre aplicativos exclusivos.
- Resolve um problema em que a captura de realidade misturada não pôde gravar vídeo após o dispositivo ser deixado no estado de espera por vários dias.
- Melhora a estabilidade do holograma.

## Windows holográfico, versão 1903 – atualização de novembro de 2019 
- Build 18362,1039

Melhorias e correções na atualização:

- Correções para os comandos de voz **"selecionar"** durante a configuração inicial para en-CA e en-au.
- Melhorias na qualidade visual dos objetos colocados longe das versões mais recentes do Unity e do MRTK.
- Corrige problemas de endereçamento com aplicativos do holográfico travados em um estado pausado durante o lançamento até que o painel Pins seja colocado e ignorado novamente.
- OpenXR correções e melhorias de conformidade do tempo de execução do HoloLens 2 e do emulador.


