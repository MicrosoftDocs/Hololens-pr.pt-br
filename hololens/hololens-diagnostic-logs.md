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
ms.openlocfilehash: 4a360e99a45b855957e36dd6ba31ede3da9631ba
ms.sourcegitcommit: b5f1b7c197cb58b746efc3809c61cf7a2e8c08ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11399803"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Coletar e usar informações de diagnóstico de dispositivos HoloLens

Os usuários e administradores do HoloLens podem escolher entre quatro métodos diferentes para coletar informações de diagnóstico do HoloLens:

- Aplicativo hub de feedback
- CSP DiagnosticLog
- Aplicativo Configurações
- Diagnóstico Offline

> [!IMPORTANT]  
> Os logs de diagnóstico de dispositivo contêm informações de identificação pessoal (PII), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. Quando vários usuários compartilham um dispositivo HoloLens (por exemplo, os usuários entrar no mesmo dispositivo usando contas do Microsoft Azure Active Directory (Azure AD) diferentes, os logs de diagnóstico podem conter informações de PII que se apliquem a vários usuários. Para obter mais informações, consulte [Política de Privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement)

A tabela a seguir compara diferentes métodos de coleção. Os nomes de método se vinculam a informações mais detalhadas nas seções que seguem a tabela.

|Método |Pré-requisitos |Locais de dados |Acesso e uso de dados |Retenção de dados |
| --- | --- | --- | --- | --- |
|[Hub de Feedback](#feedback-hub) |Conexão de rede e internet<br /><br />Aplicativo hub de feedback<br /><br />Permissão para carregar arquivos na nuvem da Microsoft |Nuvem da Microsoft<br /><br />Dispositivo HoloLens (opcional) |O usuário solicita assistência, concorda com os termos de uso e carrega os dados<br /><br />Os funcionários da Microsoft visualizam os dados, de acordo com os termos de uso |Os dados na nuvem são mantidos para o período definido pela Privacidade de Próxima Geração (NGP). Em seguida, os dados são excluídos automaticamente.<br /><br />Os dados no dispositivo podem ser excluídos a qualquer momento por um usuário que tenha permissões **de** administrador **ou** proprietário do dispositivo. |
|[Solução de problemas de configurações](#settings-troubleshooter) |Aplicativo Configurações |Dispositivo HoloLens<br /><br />Computador conectado (opcional) |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário compartilhe especificamente os dados com outro usuário). |Os dados são mantidos no dispositivo até que o usuário os exclua.* |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Conexão de rede<br /><br />Ambiente MDM que oferece suporte ao CSP DiagnosticLog |O administrador configura locais de armazenamento |No ambiente gerenciado, o usuário consente implicitamente o acesso do administrador aos dados.<br /><br />O administrador configura funções e permissões de acesso. | Os dados são mantidos no armazenamento na nuvem e o Administrador configura a política de retenção. |
|[Diagnóstico offline](#offline-diagnostics) |Configuração do dispositivo:<ul><li>Ligado e conectado ao computador</li><li>Botões de energia e volume funcionando</li></ul> |Dispositivo HoloLens<br /><br />Computador conectado |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário compartilhe especificamente os dados com outro usuário). |Os dados são mantidos no dispositivo até que o usuário os exclua. |

- O usuário final é responsável por compartilhar os logs de forma responsável com outra pessoa. Esses arquivos são principalmente úteis ao contatar o serviço e o suporte do cliente.  

## <a name="feedback-hub"></a>Hub de Feedback

Um usuário do HoloLens pode usar o aplicativo da área de trabalho do Microsoft Feedback Hub para enviar informações de diagnóstico para o Suporte da Microsoft. Para obter detalhes e instruções completas, consulte [Nos comentários](hololens-feedback.md).  

> [!NOTE]  
> **Usuários comerciais ou corporativos:** Se você usar o aplicativo Hub de Feedback para relatar um problema relacionado ao MDM, ao **** provisionamento ou a qualquer outro aspecto de gerenciamento de dispositivo, altere a categoria do aplicativo para a categoria dispositivo de gerenciamento  >  **empresarial**.

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está conectado a uma rede.
- O aplicativo Hub de Feedback está disponível no computador da área de trabalho do usuário, e o usuário pode carregar arquivos na nuvem da Microsoft.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Ao concordar com os termos de uso do Hub de Feedback, o usuário consente explicitamente com o armazenamento e o uso dos dados (conforme definido por esse contrato).

O Hub de Feedback fornece dois locais para o usuário armazenar informações de diagnóstico:

- **A nuvem da Microsoft**. Os dados que o usuário carrega usando o aplicativo Hub de Feedback são armazenados pelo número de dias consistentes com os requisitos de Privacidade de Próxima Geração (NGP). Os funcionários da Microsoft podem usar um visualizador compatível com NGP para acessar as informações durante esse período.
   > [!NOTE]  
   > Esses requisitos se aplicam aos dados em todas as categorias do Hub de Feedback.

- **O dispositivo HoloLens**. Ao arquivar um relatório no Hub de Feedback, o usuário pode selecionar Salvar uma cópia local de diagnósticos e anexos criados **ao dar comentários.** Se o usuário selecionar essa opção, o Hub de Feedback armazenará uma cópia das informações de diagnóstico no dispositivo HoloLens. Essas informações permanecem acessíveis para o usuário (ou qualquer pessoa que use essa conta para entrar no HoloLens). Para excluir essas informações, um usuário deve ter permissões **de** administrador ou proprietário **do** dispositivo no dispositivo. Um usuário com as permissões apropriadas pode entrar no Hub de Comentários, selecionar **Configurações**Exibir logs de diagnóstico e  >  **** excluir as informações.

## <a name="settings-troubleshooter"></a>Solução de problemas de configurações

Um usuário do HoloLens pode usar o aplicativo Configurações no dispositivo para solucionar problemas e coletar informações de diagnóstico. Para fazer isso, siga estas etapas:

1. Abra o aplicativo Configurações e selecione Atualizar & **Solução de**  >  **Problemas de** Segurança.
1. Selecione a área apropriada e selecione **Iniciar**.
1. Reproduza o problema.
1. Depois de reproduzir o problema, volte para Configurações e selecione **Parar**.

### <a name="prerequisites"></a>Pré-requisitos

- O aplicativo Configurações é instalado no dispositivo e está disponível para o usuário.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Como o usuário inicia a coleta de dados, o usuário consente implicitamente no armazenamento das informações de diagnóstico. Somente o usuário, ou qualquer pessoa com quem o usuário compartilha os dados, pode acessar os dados.

As informações de diagnóstico são armazenadas no dispositivo. Se o dispositivo estiver conectado ao computador do usuário, as informações também residem no computador no seguinte arquivo:

> Este COMPUTADOR\\ \<*HoloLens device name*> \\Armazenamento Interno\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Neste caminho e nome do arquivo, representa o nome do dispositivo HoloLens e representa a data e a hora \<*HoloLens device name*> em que o arquivo foi \<*ddmmyyhhmmss*> criado.

As informações de diagnóstico permanecem nesses locais até que o usuário as exclua.

## <a name="diagnosticlog-csp"></a>CSP DiagnosticLog

Em um ambiente de Gerenciamento de Dispositivo Móvel (MDM), o administrador de TI pode usar o provedor de serviços de configuração [diagnosticLog (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) para definir configurações de diagnóstico em dispositivos HoloLens inscritos. O administrador de IT pode configurar essas configurações para coletar logs de dispositivos inscritos.

Veja mais:
- [Coletar diagnósticos de um dispositivo Windows](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Visualização Pública do Intune - Diagnóstico do Dispositivo Windows 10](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está conectado a uma rede.
- O dispositivo está inscrito em um ambiente MDM que oferece suporte ao CSP DiagnosticLog.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Como o dispositivo faz parte do ambiente gerenciado, o usuário consente implicitamente o acesso administrativo às informações de diagnóstico.

O administrador de IT usa o CSP DiagnosticLog para configurar as políticas de armazenamento, retenção e acesso de dados, incluindo as políticas que regem o seguinte:

- A infraestrutura de nuvem que armazena as informações de diagnóstico.
- O período de retenção das informações de diagnóstico.
- Permissões que controlam o acesso às informações de diagnóstico.

## <a name="offline-diagnostics"></a>Diagnóstico offline
Em situações em que o dispositivo não é capaz de coletar diagnósticos por meio do Hub de Feedback ou do Solucionador de Configuração, você pode coletar diagnósticos manualmente. Um cenário em que isso é necessário é quando o dispositivo não pode se conectar ao Wi-Fi ou você não pode acessar outros métodos mencionados acima. Os diagnósticos coletam despejos de falha e logs do dispositivo que ajudam um engenheiro de suporte da Microsoft a isolar problemas.

Isso funciona quando o dispositivo aparece no Explorador de Arquivos depois de conectá-lo a um computador por meio de um cabo USB.

> [!NOTE]
> A geração e o gerenciamento de diagnóstico offline são controlados de forma diferente, dependendo da versão do sistema operacional. Anteriormente, ele era controlado pela configuração de telemetria, mas agora é controlado diretamente por meio da política MDM. Se desabilitado por meio da configuração ou da política MDM, os logs de diagnóstico não poderão ser coletados usando esse mecanismo.

Comportamento Antes do [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - O diagnóstico offline só é habilitado quando o usuário está passando por OOBE ou [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) valor de política é definido como Completo (Basic é o valor padrão no HoloLens). 
- Para desabilitar o diagnóstico offline, acesse **Configurações Aplicativo > Página Privacidade** e selecione **Básico** em Dados **de Diagnóstico.** Em builds em que o diagnóstico offline depende da configuração de telemetria, afeta apenas se os logs são coletados ou não. Não afeta quais arquivos são coletados.
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

On cria [o Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) e em diante:
- Quando o Diagnóstico de Fallback estiver habilitado será controlado por uma política MDM específica com a configuração [correspondente MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

Assista a este vídeo para saber mais.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estas etapas para coletar diagnósticos:
1.  Conecte o dispositivo com um cabo USB ao computador.
2.  No Explorador de Arquivos em seu computador, navegue até **'Este computador \<hololens-device> \Armazenamento Interno'**.
3.  Se a **pasta Armazenamento Interno** não aparecer, o dispositivo aguardará que um usuário entre. Entre ou faça o ciclo de energia do dispositivo segurando o botão POWER para baixo por 10 segundos.
4.  Pressione e solte imediatamente os **botões POWER + VOLUME DOWN** juntos.
5.  Aguarde um minuto até que o dispositivo prepare os arquivos zip. (Um arquivo temporário chamado HololensDiagnostics.temp pode ficar visível enquanto o dispositivo gera os arquivos zip. Não acesse ou salve esse arquivo. Quando o processo terminar, ele será substituído pelos arquivos zip.)
6.  Atualize o explorador de arquivos e navegue até a **pasta '\Documents'.**
7.  Copie os arquivos ZIP de diagnóstico e compartilhe-os com a equipe de suporte da Microsoft.

> [!NOTE]
> Alguns dos arquivos ZIP de diagnóstico podem conter informações de identificação pessoal.
