---
title: Coletar e usar informações de diagnóstico de dispositivos HoloLens
description: Saiba como coletar, usar e reter informações de diagnóstico de HoloLens dispositivos.
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
ms.openlocfilehash: 082a263bdd7eba694c13124abf40763644c83dfa
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640433"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Coletar e usar informações de diagnóstico de dispositivos HoloLens

HoloLens usuários e administradores podem escolher entre quatro métodos diferentes para coletar informações de diagnóstico de HoloLens:

- Aplicativo hub de comentários
- CSP DiagnosticLog
- Aplicativo Configurações
- Diagnóstico offline

> [!IMPORTANT]  
> Os logs de diagnóstico do dispositivo contêm PII (informações de identificação pessoal), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. Quando vários usuários compartilham um dispositivo HoloLens (por exemplo, os usuários entra no mesmo dispositivo usando contas do Azure AD (Microsoft Azure Active Directory) diferentes), os logs de diagnóstico podem conter informações de PII que se aplica a vários usuários. Para obter mais informações, consulte [Política de privacidade da Microsoft.](https://privacy.microsoft.com/privacystatement)

A tabela a seguir compara diferentes métodos de coleção. Os nomes de método se vinculam a informações mais detalhadas nas seções que seguem a tabela.

|Método |Pré-requisitos |Localizações de dados |Acesso e uso de dados |Retenção de dados |
| --- | --- | --- | --- | --- |
|[Hub de Feedback](#feedback-hub) |Conexão de rede e Internet<br /><br />Aplicativo hub de comentários<br /><br />Permissão para carregar arquivos na nuvem da Microsoft |Serviços de nuvem<br /><br />HoloLens dispositivo (opcional) |O usuário solicita assistência, concorda com os termos de uso e carrega os dados<br /><br />Os funcionários da Microsoft visualizam os dados de forma consistente com os termos de uso |Os dados na nuvem são retidos pelo período definido pelo NGP (Privacidade da Próxima Geração). Em seguida, os dados são excluídos automaticamente.<br /><br />Os dados no dispositivo podem ser excluídos a qualquer momento por um usuário que tenha permissões de Proprietário **do** dispositivo **ou** Administrador. |
|[Configurações Problemas](#settings-troubleshooter) |Aplicativo Configurações |Dispositivos do HoloLens<br /><br />Computador conectado (opcional) |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário compartilhe especificamente os dados com outro usuário). |Os dados são retidos no dispositivo até que o usuário os exclua.* |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Conexão de rede<br /><br />Ambiente MDM que dá suporte ao CSP diagnosticLog |O administrador configura locais de armazenamento |No ambiente gerenciado, o usuário consente implicitamente o acesso de administrador aos dados.<br /><br />O administrador configura funções de acesso e permissões. | Os dados são retidos no armazenamento em nuvem e o Administrador configura a política de retenção. |
|[Diagnóstico offline](#offline-diagnostics) |Configuração do dispositivo:<ul><li>Ligado e conectado ao computador</li><li>Botões de energia e volume funcionando</li></ul> |Dispositivos do HoloLens<br /><br />Computador conectado |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário compartilhe especificamente os dados com outro usuário). |Os dados são mantidos no dispositivo até que o usuário os exclua. |

* O usuário final é responsável por compartilhar os logs com responsabilidade com outra pessoa. Esses arquivos são úteis principalmente ao entrar em contato com o atendimento ao cliente e o suporte.  

## <a name="feedback-hub"></a>Hub de Feedback

Um HoloLens usuário pode usar o aplicativo da área de trabalho do Hub de Comentários da Microsoft para enviar informações de diagnóstico para Suporte da Microsoft. Para obter detalhes e instruções completas, consulte [Nos comentários](hololens-feedback.md).  

> [!NOTE]  
> **Usuários comerciais ou corporativos:** Se você usar o aplicativo Hub de Comentários para relatar um problema relacionado ao MDM, ao provisionamento ou a qualquer outro aspecto de gerenciamento de dispositivo, altere a categoria de aplicativo para **Enterprise de** Dispositivo de Gerenciamento  >  .

>[!IMPORTANT]
> Para fornecer os melhores dados possíveis para corrigir problemas, é altamente recomendável definir a telemetria do dispositivo como **Opcional.** Você pode definir esse valor durante a OOBE (Experiência Desemanada) ou usando o **Configurações** aplicativo. Para fazer isso usando o Configurações, selecione Iniciar > Configurações > Privacidade > Diagnóstico **do Aplicativo > Em**.
### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está conectado a uma rede.
- O aplicativo Hub de Comentários está disponível no computador desktop do usuário e o usuário pode carregar arquivos na nuvem da Microsoft.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Ao concordar com os termos de uso do Hub de Comentários, o usuário consente explicitamente com o armazenamento e o uso dos dados (conforme definido por esse contrato).

O Hub de Comentários fornece dois locais para o usuário armazenar informações de diagnóstico:

- **A nuvem da Microsoft.** Os dados carregados pelo usuário usando o aplicativo Hub de Comentários são armazenados pelo número de dias que são consistentes com os requisitos de NGP (Privacidade da Próxima Geração). Os funcionários da Microsoft podem usar um visualizador compatível com NGP para acessar as informações durante esse período.

   > [!NOTE]  
   > Esses requisitos se aplicam aos dados em todas as categorias do Hub de Comentários.

- **O HoloLens dispositivo .** Ao preencher um relatório no Hub de Comentários, o usuário pode selecionar Salvar uma cópia local de diagnósticos e **anexos criados ao dar comentários.** Se o usuário selecionar essa opção, o Hub de Comentários armazenará uma cópia das informações de diagnóstico no HoloLens dispositivo. Essas informações permanecem acessíveis para o usuário (ou qualquer pessoa que use essa conta para entrar no HoloLens). Para excluir essas informações, um usuário  deve ter **permissões de** Proprietário do dispositivo ou Administrador no dispositivo. Um usuário que tem as permissões apropriadas pode entrar no Hub de Comentários, **selecionar Configurações** Exibir logs de diagnóstico e excluir as  >  informações.

## <a name="settings-troubleshooter"></a>Configurações Problemas

Um HoloLens usuário pode usar o **aplicativo Configurações** no dispositivo para solucionar problemas e coletar informações de diagnóstico. Para fazer isso, execute estas etapas:

1. Abra o aplicativo Configurações e selecione Atualizar & **solução de** problemas  >  **de** segurança.
1. Selecione a área apropriada e selecione **Iniciar**.
1. Reproduza o problema.
1. Depois de reproduzir o problema, retorne ao Configurações e selecione **Parar**.

Um usuário também pode configurar o comportamento do Diagnóstico de Fallback do **Configurações** aplicativo. Navegue **até Privacidade -> solução de** problemas para definir essa configuração.
> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.

### <a name="os-update-troubleshooter"></a>Solução de problemas de atualização do sistema operacional
Em builds [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante:
- Além das soluções de problemas anteriores no aplicativo Configurações, uma nova solução de problemas foi adicionada com a adição do novo aplicativo Configurações para atualizações do sistema operacional. Navegue até Configurações -> Atualização **& Segurança -> Solução** de Problemas -> Windows Atualizar e selecione **Iniciar**. Isso permite coletar rastreamentos ao reproduzir seu problema com atualizações do sistema operacional para ajudar melhor na solução de problemas com sua TI ou suporte.
### <a name="prerequisites"></a>Pré-requisitos

- O **Configurações** aplicativo está instalado no dispositivo e está disponível para o usuário.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Como o usuário inicia a coleta de dados, o usuário consente implicitamente no armazenamento das informações de diagnóstico. Somente o usuário ou qualquer pessoa com quem o usuário compartilha os dados pode acessar os dados.

As informações de diagnóstico são armazenadas no dispositivo. Se o dispositivo estiver conectado ao computador do usuário, as informações também residirão no computador no seguinte arquivo:

> Este computador \\ \<*HoloLens device name*> \\ interno Armazenamento rastreamento \\ de documentos \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Nesse nome e caminho do arquivo, representa o nome do dispositivo HoloLens e representa a data e a hora em que o arquivo \<*HoloLens device name*> \<*ddmmyyhhmmss*> foi criado.

As informações de diagnóstico permanecem nesses locais até que o usuário as exclua.

## <a name="diagnosticlog-csp"></a>CSP DiagnosticLog

em um ambiente de MDM (gerenciamento de dispositivo móvel), o administrador de ti pode usar o [provedor de serviços de configuração do DiagnosticLog (CSP)](/windows/client-management/mdm/diagnosticlog-csp) para definir as configurações de diagnóstico em dispositivos HoloLens registrados. O administrador de ti pode definir essas configurações para coletar logs de dispositivos registrados.

Veja mais:
- [Coletar diagnósticos de um dispositivo Windows](/mem/intune/remote-actions/collect-diagnostics)
- [visualização pública do Intune – diagnóstico do dispositivo Windows 10](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está conectado a uma rede.
- O dispositivo é registrado em um ambiente MDM que dá suporte ao CSP DiagnosticLog.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Como o dispositivo faz parte do ambiente gerenciado, o usuário implicitamente consente o acesso administrativo às informações de diagnóstico.

O administrador de ti usa o CSP DiagnosticLog para configurar o armazenamento de dados, a retenção e as políticas de acesso, incluindo as políticas que regem o seguinte:

- A infraestrutura de nuvem que armazena as informações de diagnóstico.
- O período de retenção das informações de diagnóstico.
- Permissões que controlam o acesso às informações de diagnóstico.

## <a name="offline-diagnostics"></a>Diagnóstico offline
em situações em que o dispositivo não é capaz de coletar diagnósticos por meio do Hub de comentários ou da solução de problemas de Configurações, você pode coletar o diagnóstico manualmente. Um cenário em que isso é necessário é quando o dispositivo não pode se conectar ao Wi-Fi ou você não pode acessar outros métodos mencionados acima. O diagnóstico coleta despejos de memória e logs do dispositivo que ajudam um engenheiro de suporte da Microsoft a isolar problemas.

Isso funciona quando o dispositivo aparece no explorador de arquivos depois de conectá-lo a um PC por meio de um cabo USB.

> [!NOTE]
> A geração e o gerenciamento de diagnósticos offline são controlados de forma diferente, dependendo da versão do seu sistema operacional. Anteriormente, ele era controlado pela configuração de telemetria, mas agora é controlado diretamente por meio da política de MDM. Se desabilitado por meio de configuração ou política de MDM, os logs de diagnóstico não poderão ser coletados usando esse mecanismo.

comportamento anterior à [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - O diagnóstico offline só é habilitado quando o usuário está passando por um valor de política OOBE ou [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) está definido como Full (Basic é o valor padrão em HoloLens). 
- para desabilitar o diagnóstico Offline, vá para **Configurações aplicativo >** página de privacidade e selecione **básico** em **dados de diagnóstico**. Em compilações em que o diagnóstico offline depende da configuração de telemetria, ele só afetará se algum log for coletado ou não. Ele não afeta quais arquivos são coletados.
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

em builds [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) e em diante:
- Quando o diagnóstico de fallback estiver habilitado, será controlado pela política de MDM específica com a configuração correspondente [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

Assista a este vídeo para saber mais.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estas etapas para coletar diagnósticos:
1.  Conexão o dispositivo com um cabo USB para seu PC.
2.  no explorador de arquivos do seu computador, navegue até **' este PC \<hololens-device> \Internal Armazenamento '**.
3.  se a pasta **Armazenamento interna** não aparecer, o dispositivo está aguardando que um usuário entre. Conecte-se ou desligue o dispositivo mantendo o botão de energia pressionado por 10 segundos.
4.  Pressione e solte imediatamente os botões **Power + volume down** juntos.
5.  Aguarde um minuto para o dispositivo preparar os arquivos zip. (Um arquivo temporário chamado HololensDiagnostics. Temp pode ficar visível enquanto o dispositivo gera os arquivos zip. Não acesse nem salve esse arquivo. Quando o processo for concluído, ele será substituído pelos arquivos zip.)
6.  Atualize o explorador de arquivos e navegue até a pasta **' \Documents '** .
7.  Copie os arquivos ZIP de diagnóstico e compartilhe-os com a equipe de suporte da Microsoft.

> [!NOTE]
> Alguns dos arquivos ZIP de diagnóstico podem conter PII.
