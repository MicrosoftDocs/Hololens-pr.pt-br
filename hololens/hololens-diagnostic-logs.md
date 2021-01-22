---
title: Coletar e usar informações de diagnóstico de dispositivos HoloLens
description: Saiba como coletar, usar e reter informações de diagnóstico de dispositivos HoloLens.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 206a31476820e8722b1b72fbd501345a089379b1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283222"
---
# Coletar e usar informações de diagnóstico de dispositivos HoloLens

Os usuários e administradores do HoloLens podem escolher entre quatro métodos diferentes para coletar informações de diagnóstico do HoloLens:

- Aplicativo Hub de Feedback
- CSP DiagnosticLog
- Aplicativo Configurações

> [!IMPORTANT]  
> Os logs de diagnóstico de dispositivo contêm informações de identificação pessoal (PII), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. Quando vários usuários compartilham um dispositivo HoloLens (por exemplo, os usuários podem entrar no mesmo dispositivo usando contas diferentes do Microsoft Azure Active Directory (Azure AD), os logs de diagnóstico podem conter informações de PII que se apliquem a vários usuários. Para obter mais informações, consulte a Política [de Privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement)

A tabela a seguir compara os três métodos de coleção. Os nomes de método são links para informações mais detalhadas nas seções que seguem a tabela.

|Método |Pré-requisitos |Locais de dados |Acesso e uso de dados |Retenção de dados |
| --- | --- | --- | --- | --- |
|[Hub de Feedback](#feedback-hub) |Rede e conexão com a Internet<br /><br />Aplicativo Hub de Feedback<br /><br />Permissão para carregar arquivos na nuvem da Microsoft |Nuvem da Microsoft<br /><br />Dispositivo HoloLens (opcional) |O usuário solicita assistência, concorda com os termos de uso e carrega os dados<br /><br />Os funcionários da Microsoft visualizam os dados de forma consistente com os termos de uso |Os dados na nuvem são mantidos pelo período definido pela Privacidade de Próxima Geração (NGP). Em seguida, os dados são excluídos automaticamente.<br /><br />Os dados no dispositivo podem ser excluídos a qualquer momento por um usuário que **tenha** permissões de administrador **ou** proprietário do dispositivo. |
|[Solução de problemas de configurações](#settings-troubleshooter) |Aplicativo Configurações |Dispositivo HoloLens<br /><br />Computador conectado (opcional) |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário compartilhe especificamente os dados com outro usuário). |Os dados são mantidos até que o usuário os exclua.* |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Conexão de rede<br /><br />Ambiente MDM que oferece suporte ao CSP DiagnosticLog |O administrador configura locais de armazenamento |No ambiente gerenciado, o usuário consente implicitamente o acesso do administrador aos dados.<br /><br />O administrador configura funções e permissões de acesso. | O administrador configura a política de retenção. |
|[Diagnóstico offline](#offline-diagnostics) |Configuração do dispositivo:<ul><li>Ligado e conectado ao computador</li><li>Botões de energia e volume funcionando</li></ul> |Dispositivo HoloLens<br /><br />Computador conectado |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário compartilhe especificamente os dados com outro usuário). |Os dados são mantidos até que o usuário os exclua. | 


-   O usuário final é responsável por compartilhar os logs de forma responsiva com outra pessoa. Esses arquivos são úteis principalmente para entrar em contato com o atendimento ao cliente e o suporte.  

## Hub de Feedback

Um usuário do HoloLens pode usar o aplicativo da área de trabalho do Hub de Feedback da Microsoft para enviar informações de diagnóstico ao Suporte da Microsoft. Para obter detalhes e instruções completas, consulte [Nos dê comentários.](hololens-feedback.md)  

> [!NOTE]  
> **Usuários comerciais ou corporativos:** Se você usar o aplicativo Hub de Feedback para relatar um problema relacionado ao MDM, ao **** provisionamento ou a qualquer outro aspecto de gerenciamento de dispositivo, altere a categoria do aplicativo para a categoria de Dispositivo de Gerenciamento  >  **Empresarial.**

### Pré-requisitos

- O dispositivo está conectado a uma rede.
- O aplicativo Hub de Feedback está disponível no computador desktop do usuário, e o usuário pode carregar arquivos na nuvem da Microsoft.

### Locais, acesso e retenção de dados

Ao concordar com os termos de uso do Hub de Feedback, o usuário consente explicitamente com o armazenamento e o uso dos dados (conforme definido por esse contrato).

O Hub de Feedback fornece dois locais para o usuário armazenar informações de diagnóstico:

- **A nuvem da Microsoft.** Os dados que o usuário carrega usando o aplicativo Hub de Feedback são armazenados durante o número de dias que são consistentes com os requisitos de Privacidade de Próxima Geração (NGP). Os funcionários da Microsoft podem usar um visualizador compatível com NGP para acessar as informações durante esse período.
   > [!NOTE]  
   > Esses requisitos se aplicam aos dados em todas as categorias do Hub de Feedback.

- **O dispositivo HoloLens**. Durante o arquivamento de um relatório no Hub de Feedback, o usuário pode selecionar Salvar uma cópia local de diagnósticos e anexos criados **ao fazer comentários.** Se o usuário selecionar essa opção, o Hub de Feedback armazenará uma cópia das informações de diagnóstico no dispositivo holoLens. Essas informações permanecem acessíveis ao usuário (ou qualquer pessoa que use essa conta para entrar no HoloLens). Para excluir essas informações, um usuário deve ter permissões **de** administrador ou proprietário **do** dispositivo no dispositivo. Um usuário que tenha as permissões apropriadas pode **** entrar no Hub de Feedback, selecionar Configurações Exibir logs de diagnóstico  >  **e**excluir as informações.

## Solução de problemas de configurações

Um usuário do HoloLens pode usar o aplicativo Configurações no dispositivo para solucionar problemas e coletar informações de diagnóstico. Para fazer isso, siga estas etapas:

1. Abra o aplicativo Configurações e selecione Atualizar & **de**  >  **Problemas de** Segurança.
1. Selecione a área apropriada e selecione **Iniciar.**
1. Reproduza o problema.
1. Depois de reproduzir o problema, retorne a Configurações e selecione **Parar.**

### Pré-requisitos

- O aplicativo Configurações é instalado no dispositivo e está disponível para o usuário.

### Locais, acesso e retenção de dados

Como o usuário inicia a coleta de dados, o usuário consente implicitamente com o armazenamento das informações de diagnóstico. Somente o usuário, ou qualquer pessoa com quem o usuário compartilha os dados, pode acessar os dados.

As informações de diagnóstico são armazenadas no dispositivo. Se o dispositivo estiver conectado ao computador do usuário, as informações também residem no computador no seguinte arquivo:

> This PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Nesse caminho e nome de arquivo, representa o nome do dispositivo HoloLens e representa a data e hora \<*HoloLens device name*> em que o arquivo foi \<*ddmmyyhhmmss*> criado.

As informações de diagnóstico permanecem nesses locais até que o usuário as exclua.

## CSP DiagnosticLog

Em um ambiente de Gerenciamento de Dispositivo Móvel (MDM), o administrador de TI pode usar o provedor de serviços de configuração [(CSP) DiagnosticLog](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) para definir configurações de diagnóstico em dispositivos HoloLens inscritos. O administrador de IT pode definir essas configurações para coletar logs de dispositivos inscritos.

### Pré-requisitos

- O dispositivo está conectado a uma rede.
- O dispositivo está inscrito em um ambiente MDM que dá suporte ao CSP DiagnosticLog.

### Locais, acesso e retenção de dados

Como o dispositivo faz parte do ambiente gerenciado, o usuário consente implicitamente no acesso administrativo às informações de diagnóstico.

O administrador de IT usa o CSP DiagnosticLog para configurar as políticas de armazenamento, retenção e acesso de dados, incluindo as políticas que regem o seguinte:

- A infraestrutura de nuvem que armazena as informações de diagnóstico.
- O período de retenção para as informações de diagnóstico.
- Permissões que controlam o acesso às informações de diagnóstico.

## Diagnóstico offline
Em situações em que o dispositivo não é capaz de coletar diagnósticos por meio do Hub de Feedback ou da Solução de Problemas de Configuração, você pode coletar diagnósticos manualmente. Um cenário em que isso é necessário é quando o dispositivo não pode se conectar ao Wi-Fi. O diagnóstico coleta despejos de falha e logs do dispositivo que ajudam um engenheiro de suporte da Microsoft a isolar problemas.

Isso funciona quando o dispositivo aparece no Explorador de Arquivos depois de conectá-lo a um computador por meio de um cabo USB. 

> [!NOTE]
> A geração e o gerenciamento de Diagnósticos Offline são controlados de forma diferente, dependendo da versão do sistema operacional. Anteriormente, ele era controlado pela configuração de telemetria, mas agora é controlado diretamente por meio da política. 

Comportamento antes do [Windows Holographic, vértice 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - O diagnóstico offline só é habilitado quando o usuário está passando por OOBE ou [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) o valor da política está definido como Completo (Básico é o valor padrão no HoloLens). 
- Para desabilitar o diagnóstico offline, vá para **Configurações do Aplicativo > privacidade** e selecione **Básico** em Dados **de Diagnóstico.** Em builds em que o diagnóstico offline depende da configuração de telemetria, ele só afeta se os logs são coletados ou não. Ele não afeta quais arquivos são coletados.
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

Em builds [do Windows Holographic, vison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) e em diante:
- Quando o Diagnóstico de Fallback estiver habilitado, será controlado por uma política de MDM específica com a configuração [correspondente MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se o dispositivo estiver bloqueado, os logs não aparecerão.


Assista a este vídeo para saber mais. 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estas etapas para coletar diagnósticos:
1.  Conecte o dispositivo com um cabo USB ao computador.
2.  No Explorador de Arquivos em seu computador, navegue até **'Este computador \<hololens-device> \Armazenamento Interno'**.
3.  Se a **pasta Armazenamento** Interno não aparecer, o dispositivo está aguardando um usuário entrar. Entre ou energia do dispositivo mantendo pressionado o botão LIGAR por 10 segundos.
4.  Pressione e solte imediatamente os botões **DE ENERGIA + VOLUME PARA** BAIXO juntos.
5.  Aguarde um minuto para o dispositivo preparar os arquivos zip. (Um arquivo temporário chamado HololensDiagnostics.temp pode se tornar visível enquanto o dispositivo gera os arquivos zip. Não acesse nem salve esse arquivo. Quando o processo terminar, ele será substituído pelos arquivos zip.)
6.  Atualize o Explorador de Arquivos e navegue até a **pasta "\Documentos".**
7.  Copie os arquivos ZIP de diagnóstico e compartilhe-os com a equipe de suporte da Microsoft.

> [!NOTE]
> Alguns dos arquivos ZIP de diagnóstico podem conter informações de identificação pessoal.



