---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar builds do Insider e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 1/21/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: c2d79c9cfbca263a507388227304f9d0dcecd9d0
ms.sourcegitcommit: f30add1d1eb07342e78a6baef87777c4d7123669
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297654"
---
# Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às versões mais recentes do Insider Preview para HoloLens! É simples começar e [fornecer comentários](hololens-insider.md#start-receiving-insider-builds) valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.

## Notas de versão do Windows Insider

Estamos animados em iniciar a versão de versões We will be flighting to the Dev Channel for the latest updates. Continuaremos a atualizar essa página à medida que adicionarmos mais recursos e atualizações às nossas versões do Windows Insider.  Fique animado e pronto para misturar essas atualizações à sua realidade.

| Nome do Recurso                                              | Descrição breve                                                                      | Disponível na com build |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Novo Microsoft Edge](#introducing-the-new-microsoft-edge) | O novo Microsoft Edge baseado no Chromium já está disponível para o HoloLens 2                         | 20279.1006 |
| [Novo aplicativo Configurações](#new-settings-app)                     | O aplicativo Configurações herdado está sendo substituído por uma versão atualizada com novos recursos e configurações | 20279.1006 |
| [Se picker de aplicativo padrão](#default-app-picker)                 | Escolha qual aplicativo deve ser lançado para cada arquivo ou tipo de link                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Um atalho para o Office Web App agora está listado em "Todos os aplicativos"                                   | 20279.1006 |
| [Deslizar o dedo para digitar](#swipe-to-type)                           | Use a ponta do dedo para "passar o dedo" palavras no teclado holográfico                        | 20279.1006 |
| [Suporte para microfone externo USB-C](#usb-c-external-microphone-support) | Use microfones USB-C para aplicativos e/ou Assistência Remota.| 20279.1006 |
| [Novas AUMIDs para novos aplicativos no modo quiosque](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs para novos aplicativos de Configurações e Borda | 20279.1006 |
| [Entrega de falha no modo quiosque aprimorado](#kiosk-mode-behavior-changes-for-handling-of-failures) | O modo de quiosque procura acesso global atribuído antes do menu Iniciar vazio. | 20279.1006 |
| [Configurar Diagnóstico de Fallback](#configuring-fallback-diagnostics-via-settings-app) | Configurando o comportamento de diagnóstico de fallback no aplicativo Configurações | 20279.1006 |

### Apresentando o novo Microsoft Edge

![Animação do logotipo herddo do Microsoft Edge para o novo logotipo do Microsoft Edge](images/new-edge.gif)

O novo Microsoft Edge adota o projeto de software livre [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para criar melhor compatibilidade para clientes e menos fragmentação da Web para desenvolvedores da Web.

Com essa visualização do Insider, o novo Microsoft Edge está disponível para clientes do HoloLens 2 pela primeira vez! Embora o novo Microsoft Edge eventualmente substitua o Microsoft Edge herdada no HoloLens 2, ambos os navegadores estão atualmente disponíveis para Participantes do Programa Insider. Compartilhe comentários e bugs com nossa equipe por meio do recurso **Enviar Comentários** no novo Microsoft Edge ou por meio do Hub [de Feedback.](hololens-feedback.md)

![Captura de tela do Novo Microsoft Edge](images/new-edge-ui.png)

#### Iniciando o novo Microsoft Edge

Há duas versões do Microsoft Edge disponíveis para os Insiders: o novo ícone do Microsoft Edge (representado por um ícone azul e verde) e o Microsoft Edge herdado (representado pelo ícone ![ ](images/new_edge_logo.png) "e" branco). O novo Microsoft Edge é fixado no menu Iniciar e será aberto automaticamente quando você ativar um link da Web. Se você quiser reverter para usar o Microsoft Edge herdado como navegador da Web padrão, consulte as instruções abaixo para redefinir aplicativos [padrão.](#default-app-picker)

> [!NOTE]
> Quando você iniciar pela primeira vez o novo Microsoft Edge no HoloLens 2, suas configurações e dados serão importados do Microsoft Edge herdada. Se você continuar a usar o Microsoft Edge herdado após iniciar o novo Microsoft Edge, esses novos dados não serão sincronizados do Microsoft Edge herdado para o novo Microsoft Edge.

#### Definindo configurações de política para o novo Microsoft Edge

O novo Microsoft Edge oferece aos administradores de IT um conjunto muito mais amplo de políticas de navegador no HoloLens 2 do que estava disponível anteriormente com o Microsoft Edge herdado.

Aqui estão alguns recursos úteis para saber mais sobre como gerenciar configurações de política para o novo Microsoft Edge:

- [Definir as configurações de política do Microsoft Edge com o Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Mapeamento de políticas do Microsoft Edge Legacy para o Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapeamento de políticas do Google Chrome para o Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentação [completa do Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Devido ao volume de políticas de navegador suportadas pelo novo Microsoft Edge, nossa equipe não consegue garantir que cada nova política funcione no HoloLens 2. No entanto, testamos e confirmamos que o novo equivalente do Microsoft Edge a cada política herdada do Microsoft Edge anteriormente suportada no HoloLens 2 funciona como esperado. Consulte [a Versão Herdada](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) do Microsoft Edge para o mapeamento de políticas do Microsoft Edge para encontrar o novo equivalente do Microsoft Edge de cada política de navegador herdada do Microsoft Edge que você estava usando com o HoloLens 2.
>
> Existem pelo menos duas novas políticas do Microsoft Edge que sabemos *que não funcionarão* com o HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### O que esperar do novo Microsoft Edge no HoloLens 2

Como o novo Microsoft Edge é um aplicativo Win32 nativo com uma nova camada de adaptador UWP permitindo que ele seja executado em dispositivos somente UWP como o HoloLens 2, alguns recursos podem não estar disponíveis imediatamente. Vamos dar suporte a novos cenários e recursos nos próximos meses, portanto, verifique esse espaço para obter informações atualizadas.

**Cenários e recursos esperados para funcionar:**
- Experiência de primeira executar, entrar no perfil e sincronizar
- Os sites devem renderizar e se comportar conforme o esperado
- A maioria das funcionalidades do navegador (Favoritos, Histórico, etc.) deve funcionar conforme o esperado
- Modo escuro
- Instalando aplicativos Web no dispositivo
- Instalação de extensões (informa-nos se você usa extensões que não funcionam corretamente no HoloLens 2)
- Exibindo e marcando um PDF
- Som espacial de uma única janela do navegador
- Atualização automática e manual do navegador
- Salvar um PDF no menu Imprimir (usando a opção "Salvar em PDF" )

**Cenários e recursos em breve:**
- Extensão WebXR e Visualizador 360
- Restauração de conteúdo para corrigir a janela ao navegar entre várias janelas colocadas em seu ambiente
- Ingressar em uma chamada do Microsoft Teams por meio do navegador com vídeo, captura de realidade misturada ou compartilhamento de tela (participar de chamadas com áudio funciona bem)

**Cenários e recursos que não devem funcionar:**
- Som espacial de várias janelas com fluxos de áudio simultâneos
- "See it, say it"
- Impressão

**Principais problemas conhecidos do navegador:**
- Redefinir seu dispositivo removerá o novo Microsoft Edge
- A visualização da lupa no teclado holográfico mostra conteúdo incorreto

#### Canais do Microsoft Edge Insider

A equipe do Microsoft Edge disponibiliza três canais de visualização para a comunidade do Edge Insider: Beta, Dev e Canary. Instalar um canal de visualização não desinstala a versão lançada do Microsoft Edge em seu HoloLens 2, e você pode instalar mais de uma ao mesmo tempo. 

Visite a [home page do Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para saber mais sobre a comunidade do Edge Insider. Para saber mais sobre os diferentes canais do Edge Insider e começar, visite a página de download do [Participante do Insider Edge.](https://www.microsoftedgeinsider.com/download)

Há alguns métodos disponíveis para instalar canais do Microsoft Edge Insider no HoloLens 2:

**Instalação direta no dispositivo (atualmente disponível apenas para dispositivos não-manageados)**
  1. Em seu HoloLens 2, visite a [página de download do Edge Insider](https://www.microsoftedgeinsider.com/download)
  1. Selecione o **botão Baixar para HoloLens 2** para o canal do Insider Edge que você deseja instalar
  1. Iniciar o arquivo .msix baixado da fila de download do Edge ou da pasta "Downloads" do seu dispositivo (usando o Explorador de Arquivos)
  1. [O instalador de aplicativo](app-deploy-app-installer.md) será lançado
  1. Selecione o **botão** Instalar
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge Beta, **** Dev ou Canary como uma entrada separada na lista Todos os aplicativos do menu Iniciar

**Instalar via computador com o Windows Device Portal (requer que o modo [de](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) desenvolvedor seja habilitado no HoloLens 2)**
  1. Em seu computador, visite a [página de download do Edge Insider](https://www.microsoftedgeinsider.com/download)
  1. Selecione o **botão de seta para** baixo ao lado do botão "Baixar para Windows 10" para o canal do Insider Edge que você deseja instalar
  1. Selecione **o HoloLens 2** no menu suspenso
  1. Salve o arquivo .msix na pasta "Downloads" do computador (ou em outra pasta que você possa encontrar facilmente)
  1. Usar [o Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) em seu computador para instalar o arquivo .msix baixado no HoloLens 2
  1. Após a instalação bem-sucedida, você encontrará o Microsoft Edge Beta, **** Dev ou Canary como uma entrada separada na lista Todos os aplicativos do menu Iniciar

> [!NOTE]
> Durante a visualização do Windows Insider para HoloLens 2, a versão do Microsoft Edge em seu dispositivo pode ser superior à disponível em alguns (ou todos) dos canais do Microsoft Edge Insider. Isso é para garantir que novos recursos e correções especificamente voltados para o navegador da Web no HoloLens 2 estão chegando aos participantes do Programa Windows Insider o mais rápido possível. Logo após o lançamento público da próxima atualização do Windows, os builds do canal do Microsoft Edge Insider ultrapassarão e se manterão à frente da versão do Microsoft Edge em seu HoloLens 2.

### Novo aplicativo Configurações

Com esta versão, lançaremos uma nova versão do aplicativo Configurações. O novo aplicativo Configurações inclui novos recursos e configurações expandidas para o HoloLens 2 nas seguintes áreas: Som, avaliação do Power &, Rede & Internet, Aplicativos, Contas, Facilidade de Acesso e muito mais.

> [!NOTE]
> Como o novo aplicativo Configurações é diferente do aplicativo Configurações herdado, todas as janelas de configurações que você colocou anteriormente em seu ambiente serão removidas após a atualização.

![Home page do aplicativo Novas Configurações](images/new-settings-app.png)

**Novos recursos e configurações**
- Pesquisa de configurações: pesquise configurações da home page Configurações usando palavras-chave ou o nome da configuração
- Som > sistema:
  - Dispositivos de áudio de entrada e saída: escolha independentemente seus dispositivos de áudio de entrada e saída (por exemplo, ouça áudio via fones de ouvido Bluetooth ou use um microfone USB-C para entrada de áudio). Observação: não há suporte para microfones Bluetooth no HoloLens 2.
  - Volume do aplicativo: ajustar independentemente o volume de cada aplicativo
- Sistema > energia & atividade: escolha quando o dispositivo deve entrar em atividade após um período de inatividade
- Sistema > bateria: habilitar manualmente o modo de economia de bateria ou definir um limite de bateria no ponto em que o modo de economia de bateria é ativado automaticamente
- Dispositivos > USB: você pode desabilitar conexões USB por padrão
- Rede & Internet:
  - Os adaptadores Ethernet USB-C agora aparecerão na Rede & Internet
  - As configurações do adaptador Ethernet USB-C agora estão disponíveis, incluindo seu endereço IP
  - Agora você pode habilitar o modo avião no HoloLens 2
- Aplicativos: você pode redefinir os aplicativos padrão usados para tipos de arquivo e link. Consulte [o selador de aplicativo padrão](#default-app-picker) para obter mais informações.
- Contas > outros usuários: os proprietários de dispositivos podem adicionar usuários, atualizar usuários padrão para proprietários de dispositivos, fazer downgrade de proprietários de dispositivos para usuários padrão e remover usuários.
- Facilidade de Acesso: alterar o tamanho do texto e alguns efeitos visuais

**Problemas conhecidos**
- As janelas configurações colocadas anteriormente serão removidas (veja a observação acima)
- A visita à página Notificações pode falhar no aplicativo Configurações (investigando)
- No momento, a página Ethernet não aparece (a ser corrigida em breve)
- O uso da bateria para o novo Microsoft Edge pode não ser preciso, devido à sua natureza como um aplicativo da área de trabalho Win32 com suporte por uma camada de adaptador UWP (nenhuma correção antecipada em breve)

### Se picker de aplicativo padrão

Ao ativar um hiperlink ou abrir um tipo de arquivo com mais de um aplicativo instalado que oferece suporte a ele, você verá uma nova janela aberta solicitando que você selecione qual aplicativo instalado deve manipular o arquivo ou o tipo de link. Nessa janela, você também pode optar por fazer com que o aplicativo selecionado manipular o arquivo ou o tipo de link "Uma vez" ou "Sempre".

![Janela do selador de aplicativos](images/default-app-picker.png)

Se você escolher "Sempre", mas posteriormente quiser alterar qual aplicativo manipulará um determinado arquivo ou tipo de link, poderá redefinir os padrões salvos em Configurações **> Aplicativos.** Role até a parte inferior **** da página e selecione o botão Limpar em "Aplicativos padrão para tipos de arquivo" e/ou "Aplicativos padrão para tipos de link". Ao contrário da configuração semelhante em computadores desktop, você não pode redefinir padrões de tipo de arquivo individuais.

### Office Web App

O Aplicativo Web do Office foi adicionado à lista "Todos os aplicativos" no menu Iniciar. Esse aplicativo Web também pode ser fixado em Iniciar ou desinstalado. Como se trata de um aplicativo Web, sua funcionalidade corresponde exatamente ao que você experimentaria https://www.office.com visitando. A funcionalidade do aplicativo Web do Office só estará disponível quando o HoloLens 2 tiver uma conexão de Internet ativa.

### Deslizar o dedo para digitar

Alguns clientes acham mais rápido "digitar" em teclados virtuais ao girar a forma da palavra que pretendem digitar, e estamos visualizando esse recurso para o teclado holográfico. Você pode passar o dedo uma palavra por vez passando a ponta do dedo pelo plano do teclado holográfico, passando o dedo para a forma da palavra e, em seguida, retirando a ponta do dedo do plano do teclado. Você pode passar o dedo em palavras de acompanhamento sem precisar pressionar a barra de espaços removendo o dedo do teclado entre as palavras. Você vai saber que o recurso está funcionando se vir uma trilha de passar o dedo seguindo o movimento do dedo no teclado.

Observe que esse recurso pode ser complicado de usar e ser mestre devido à natureza de um teclado holográfico em que você não sente resistência ao dedo (ao contrário de uma tela de telefone celular). Estamos avaliando esse recurso para lançamento público, portanto, seus comentários são importantes; se você achar o recurso útil ou se tiver comentários interessantes, diga-nos por meio do [Hub de Feedback.](hololens-feedback.md)

### Suporte para microfone externo USB-C

> [!IMPORTANT]
> Conectar um **microfone USB não o definirá automaticamente como o dispositivo de entrada.** Ao conectar um conjunto de fones de ouvido USB-C, os usuários observarão que o áudio do fone de ouvido será redirecionado automaticamente para os fones de ouvido, mas o sistema operacional holoLens prioriza a matriz de microfone interna acima de qualquer outro dispositivo de entrada. **Para usar um microfone USB-C, siga as etapas abaixo.**

Os usuários podem selecionar microfones externos conectados usb-C usando **o painel de configurações** de som. Microfones USB-C podem ser usados para chamada, gravação, etc.

Abra o **aplicativo Configurações** e selecione **Som do**  ->  **Sistema.**

![Definições de Som](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar microfones externos com **a**Assistência Remota, os usuários precisarão clicar no hiperlink "Gerenciar dispositivos de som".
>
> Em seguida, use o drop-down para definir o microfone externo como **Padrão** ou **Padrão de Comunicações.** Escolher **Padrão significa** que o microfone externo será usado em todos os lugares.
>
> Escolher **o Padrão de** Comunicação significa que o microfone externo será usado na Assistência Remota e em outros aplicativos de comunicação, mas a matriz de microfone do HoloLens ainda pode ser usada para outras tarefas.

![Gerenciar dispositivos de som](images/usbc-mic-2.png)

<br>

![Definir o padrão do microfone](images/usbc-mic-3.jpg)

#### E quanto ao suporte a microfone Bluetooth?

Infelizmente, os microfones Bluetooth ainda não têm suporte no HoloLens 2.

#### Solução de problemas de microfones USB-C

Esteja ciente de que alguns microfones USB-C relatam a si mesmos incorretamente como um microfone *e um* alto-falante. Esse é um problema com o microfone e não com o HoloLens. Ao conectar um desses microfones ao HoloLens, o som pode ser perdido. Felizmente, há uma correção simples.  

Em **Configurações**de Som do Sistema , de definir explicitamente  ->  ****  ->  **** os alto-falantes integrados (Driver de áudio de **recurso analógico)** como o dispositivo **padrão.** O HoloLens deve se lembrar dessa configuração mesmo se o microfone for removido e reconectado mais tarde.

![Solução de problemas de microfones USB-C](images/usbc-mic-4.png)

### Usar os novos aplicativos configurações e borda nos modos de quiosque

Ao incluir aplicativos em [Quiosques,](hololens-kiosk.md)um administrador de IT geralmente adiciona o aplicativo ao Quiosque, mas usando sua ID de Modelo de Usuário de Aplicativo (AUMID). Como o aplicativo Configurações e o aplicativo Microsoft Edge são considerados novos aplicativos e diferentes, os Quiosques de aplicativos mais antigos que usam AUMIDs para esses aplicativos precisarão ser atualizados para usar a nova AUMID.

Ao modificar um Quiosque para incluir os novos aplicativos, recomendamos adicionar a nova AUMID, bem como deixar a antiga. Isso criará uma transição fácil quando os usuários atualizarem o sistema operacional e não precisarão receber novas políticas para continuar usando o Quiosque conforme o esperado.

| Aplicativo                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicativo Configurações Antigas       | HolographicSystemSettings_cw5n1h2txyewy! Aplicativo            |
| Novo aplicativo Configurações       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicativo |
| Aplicativo Antigo do Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Novo aplicativo Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### Alterações no comportamento do modo de quiosque para o tratamento de falhas

Em versões mais antigas, se um dispositivo tivesse uma configuração de quiosque, que é uma combinação de acesso global atribuído e acesso atribuído ao membro do grupo AAD, se a determinação da associação de grupo do AAD falhasse, o usuário verá["](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)nada mostrado no menu Iniciar ".

A partir do lançamento do Windows Insider, a experiência de quiosque será fallback para a configuração de quiosque global (se presente) em caso de falhas durante o modo de quiosque de grupo do AAD.

### Configurando o Diagnóstico de Fallback por meio do aplicativo Configurações

Agora, no aplicativo Configurações, um usuário pode configurar o comportamento de [Diagnóstico de Fallback.](hololens-diagnostic-logs.md) No aplicativo Configurações, navegue até a **página Solução**de  ->  **Problemas de** Privacidade para definir essa configuração.

> [!NOTE]
> Se houver uma política MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.  






## Começar a receber builds do Insider

> [!NOTE]
> Se você ainda não tiver atualizado recentemente, reinicie seu dispositivo para atualizar o estado e obter a versão mais recente.
> - O comando de voz "Reiniciar dispositivo" funciona bem. 
> - Você também pode escolher o botão reiniciar em Configurações/Programa Windows Insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso o acompanhará novamente.

Em um dispositivo HoloLens **** 2, vá para Atualização de Configurações & Programa Windows Insider de Segurança e  >  ****  >  **** **selecione Começar.** Vincule a conta que você usou para se registrar como um Windows Insider.

O Windows Insider agora está mudando para Canais. O **anel Modo** Rápido se tornará **** o Canal de **Desenvolvedor,** **** o anel Modo Lento se tornará o Canal **Beta**e o anel de Visualização de Versão se tornará o Canal de Visualização de **Versão.** Esta é a aparência desse mapeamento:

![Explicação dos Canais do Windows Insider](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [Apresentando canais do Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos blogs do Windows.

Em seguida, selecione Desenvolvimento ativo do **Windows,** **** escolha se você gostaria de receber builds do Canal de Desenvolvimento ou do Canal **Beta** e revise os termos do programa.

Selecione **Confirmar > Reiniciar Agora** para terminar. Depois que o dispositivo for reiniciado, vá para Configurações > **Atualização & segurança >** verificar se há atualizações para obter a versão mais recente.

### Erro de atualização 0x80070490 work-around
Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, tente o seguinte trabalho em curto prazo. Isso envolve mover o canal do insider, receber a atualização e, em seguida, mover o canal do Insider de volta.

#### Estágio um - Versão Prévia
1.  Configurações, Atualização & Segurança, Programa Windows Insider, selecione **Canal de Visualização de Versão.**
2.  Configurações, Atualização & Segurança, Windows Update, **Verificar se há atualizações.** Após a atualização, continue no Estágio dois.

#### Estágio dois - Canal deV
1. Configurações, Atualização & Segurança, Programa Windows Insider, selecione **Canal deV.**
2. Configurações, Atualização & Segurança, Windows Update, **Verificar se há atualizações.**

## FFU download and flash directions
Para testar com um ffu assinado de voo, primeiro você precisa desbloquear seu dispositivo antes de piscar o ffu assinado da voo.
1. No computador:

    1. Baixe ffu em seu computador de [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) da Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. No HoloLens - Desbloqueio da Versão de Pré-voo: Abra a Atualização de Configurações ****& Programa Windows Insider de Segurança e, em  >  ****  >  **** seguida, inscreva-se e reinicie o dispositivo.

1. Flash FFU - Agora você pode piscar a FFU assinada de voo usando o ARC.

## Fornecer comentários e relatar problemas

Use o [aplicativo Hub de Feedback](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas. O uso do Hub de Feedback garante que todas as informações de diagnóstico necessárias sejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.  Problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.

> [!NOTE]
> Certifique-se de aceitar o prompt que pergunta se você gostaria que o Hub de Feedback acessasse sua pasta Documentos (selecione **Sim** quando solicitado).

## Observação para desenvolvedores

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando builds do Insider do HoloLens.  Confira a [Documentação do Desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com builds do Insider do HoloLens.  Você pode usar as mesmas builds do Unity e do Visual Studio que já está usando para o desenvolvimento do HoloLens.

## Parar de receber builds do Insider

Se você não quiser mais receber builds do Insider do Windows Holographic, poderá re optá-lo quando o HoloLens estiver executando uma com build de produção ou pode recuperar seu dispositivo usando o Advanced Recovery Companion para recuperar seu dispositivo para uma versão não Insider do Windows Holographic. [](hololens-recovery.md)

> [!CAUTION]
> Há um problema conhecido em que os usuários que não se registram nos builds do Insider Preview depois de reinstalar manualmente uma nova versão prévia experimentariam uma tela azul. Posteriormente, eles devem recuperar manualmente o dispositivo. Para obter detalhes completos sobre se você seria afetado ou não, veja mais sobre esse [problema conhecido.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Para verificar se o HoloLens está executando uma com build de produção:

1. Vá para **Configurações > Sistema > Sobre**e encontre o número do build.

1. [Consulte as notas de versão para números de build de produção.](hololens-release-notes.md)

Para optar por não ter builds do Insider:

1. Em um HoloLens executando uma com build de produção, vá para Configurações > Atualizar & Segurança > Programa Windows Insider e selecione Interromper **builds do Insider.** ****

1. Siga as instruções para optar por não ter seu dispositivo.
