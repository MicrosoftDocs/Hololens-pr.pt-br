---
title: Coletar e usar informações de diagnóstico de dispositivos HoloLens
description: saiba como coletar, usar e reter informações de diagnóstico de dispositivos HoloLens.
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
ms.openlocfilehash: 2cbf3005293f4fde91b22f3ff87edc6041e53336
ms.sourcegitcommit: 16897df83c309acecf04e2bcfea310891cb6681b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "127817269"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Coletar e usar informações de diagnóstico de dispositivos HoloLens

HoloLens usuários e administradores podem escolher entre quatro métodos diferentes para coletar informações de diagnóstico de HoloLens:

- Aplicativo de Hub de comentários
- CSP DiagnosticLog
- Aplicativo Configurações
- Diagnóstico offline

> [!IMPORTANT]  
> Os logs de diagnóstico do dispositivo contêm informações de identificação pessoal (PII), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. quando vários usuários compartilham um dispositivo de HoloLens (por exemplo, os usuários entram no mesmo dispositivo usando contas diferentes do Microsoft Azure Active Directory (AD do Azure)), os logs de diagnóstico podem conter informações de PII que se aplicam a vários usuários. Para obter mais informações, consulte a [política de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).

A tabela a seguir compara métodos de coleção diferentes. Os nomes de método vinculam-se a informações mais detalhadas nas seções que seguem a tabela.

|Método |Pré-requisitos |Localizações de dados |Acesso e uso de dados |Retenção de dados |
| --- | --- | --- | --- | --- |
|[Hub de Feedback](#feedback-hub) |Conexão de rede e Internet<br /><br />Aplicativo de Hub de comentários<br /><br />Permissão para carregar arquivos para o Microsoft Cloud |Serviços de nuvem<br /><br />dispositivo HoloLens (opcional) |O usuário solicita assistência, concorda com os termos de uso e carrega os dados<br /><br />Os funcionários da Microsoft visualizam os dados, como consistentes com os termos de uso |Os dados na nuvem são mantidos pelo período definido pela privacidade da próxima geração (NGP). Em seguida, os dados são excluídos automaticamente.<br /><br />Os dados no dispositivo podem ser excluídos a qualquer momento por um usuário que tenha permissões de **administrador** ou **proprietário do dispositivo** . |
|[Configurações Problemas](#settings-troubleshooter) |Aplicativo Configurações |Dispositivos do HoloLens<br /><br />Computador conectado (opcional) |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário Compartilhe especificamente os dados com outro usuário). |Os dados são mantidos no dispositivo até que o usuário o exclua. * |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Conexão de rede<br /><br />Ambiente MDM que dá suporte ao CSP DiagnosticLog |O administrador configura os locais de armazenamento |No ambiente gerenciado, o usuário implicitamente consente com o acesso de administrador aos dados.<br /><br />O administrador configura as funções e permissões de acesso. | Os dados são retidos no armazenamento em nuvem e o administrador configura a política de retenção. |
|[Diagnóstico offline](#offline-diagnostics) |Configuração do dispositivo:<ul><li>Ligado e conectado ao computador</li><li>Botões de energia e volume funcionando</li></ul> |Dispositivos do HoloLens<br /><br />Computador conectado |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário Compartilhe especificamente os dados com outro usuário). |Os dados são mantidos no dispositivo até que o usuário o exclua. |

* O usuário final é responsável por compartilhar os logs com responsabilidade com outra pessoa. Esses arquivos são úteis principalmente ao entrar em contato com o atendimento ao cliente e o suporte.  

## <a name="feedback-hub"></a>Hub de Feedback

um usuário HoloLens pode usar o aplicativo de área de trabalho do Hub de comentários da Microsoft para enviar informações de diagnóstico para Suporte da Microsoft. Para obter detalhes e instruções completas, consulte [fornecer comentários](hololens-feedback.md).  

> [!NOTE]  
> **Usuários comerciais ou empresariais:** se você usar o aplicativo de Hub de comentários para relatar um problema relacionado ao MDM, ao provisionamento ou a qualquer outro aspecto de gerenciamento de dispositivo, altere a categoria do aplicativo para **Enterprise**  >  **categoria de dispositivo** de gerenciamento.

>[!IMPORTANT]
> Para fornecer os melhores dados possíveis para corrigir problemas, é altamente recomendável que você defina a telemetria do dispositivo como **opcional**. você pode definir esse valor durante o OOBE (check-of-Box-experience) ou usando o aplicativo **Configurações** . para fazer isso usando Configurações, selecione **iniciar > Configurações > privacidade > diagnóstico de aplicativo > em**.

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está conectado a uma rede.
- O aplicativo de Hub de comentários está disponível no computador desktop do usuário e o usuário pode carregar arquivos para a nuvem da Microsoft.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Ao concordar com os termos de uso do hub de comentários, o usuário consentiu explicitamente o armazenamento e o uso dos dados (conforme definido por esse contrato).

O Hub de comentários fornece dois locais para o usuário armazenar informações de diagnóstico:

- **A nuvem da Microsoft**. Os dados que o usuário carrega usando o aplicativo de Hub de comentários são armazenados pelo número de dias que é consistente com os requisitos de privacidade da próxima geração (NGP). Os funcionários da Microsoft podem usar um visualizador compatível com NGP para acessar as informações durante esse período.

   > [!NOTE]  
   > Esses requisitos se aplicam aos dados em todas as categorias de Hub de comentários.

- **o dispositivo HoloLens**. Ao fazer o arquivamento de um relatório no Hub de comentários, o usuário pode selecionar **salvar uma cópia local de diagnósticos e anexos criados ao fornecer comentários**. se o usuário selecionar essa opção, o Hub de comentários armazenará uma cópia das informações de diagnóstico no dispositivo HoloLens. Essas informações permanecem acessíveis para o usuário (ou qualquer pessoa que use essa conta para entrar no HoloLens). Para excluir essas informações, um usuário deve ter permissões de **administrador** ou **proprietário do dispositivo** no dispositivo. um usuário que tem as permissões apropriadas pode entrar no Hub de comentários, selecionar **Configurações**  >  **exibir logs de diagnóstico** e excluir as informações.

## <a name="settings-troubleshooter"></a>Configurações Problemas

um usuário HoloLens pode usar o aplicativo **Configurações** no dispositivo para solucionar problemas e coletar informações de diagnóstico. Para fazer isso, execute estas etapas:

1. abra o aplicativo Configurações e selecione **atualizar &**  >  página de **solução de problemas** de segurança.
1. Selecione a área apropriada e selecione **Iniciar**.
1. Reproduza o problema.
1. depois de reproduzir o problema, retorne para Configurações e, em seguida, selecione **parar**.

um usuário também pode configurar o comportamento do diagnóstico de Fallback do aplicativo **Configurações** . Navegue até a página de **solução de problemas de > de privacidade** para definir essa configuração.
> [!NOTE]
> Se houver uma política de MDM configurada para o dispositivo, o usuário não poderá substituir esse comportamento.

### <a name="os-update-troubleshooter"></a>Solução de problemas de atualização do so
em builds [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante:
- além das soluções de problemas anteriores no aplicativo Configurações, uma nova solução de problemas foi adicionada com a adição do novo aplicativo Configurações para atualizações do sistema operacional. navegue até **Configurações-> atualização & segurança-> solução de problemas-> Windows Update** e selecione **iniciar**. Isso permite que você colete rastreamentos ao reproduzir seu problema com as atualizações do sistema operacional para auxiliar na solução de problemas com sua ti ou suporte.

### <a name="prerequisites"></a>Pré-requisitos

- o aplicativo **Configurações** está instalado no dispositivo e está disponível para o usuário.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Como o usuário inicia a coleta de dados, o usuário implicitamente consenti ao armazenamento das informações de diagnóstico. Somente o usuário ou qualquer pessoa com quem o usuário compartilha os dados pode acessar os dados.

As informações de diagnóstico são armazenadas no dispositivo. Se o dispositivo estiver conectado ao computador do usuário, as informações também residirão no computador no seguinte arquivo:

> este computador \\ \<*HoloLens device name*> \\ interno Armazenamento \\ documentos \\ Trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> nesse caminho de arquivo e nome, \<*HoloLens device name*> representa o nome do dispositivo de HoloLens e \<*ddmmyyhhmmss*> representa a data e a hora em que o arquivo foi criado.

As informações de diagnóstico permanecem nesses locais até que o usuário a exclua.

### <a name="view-diagnostic-report"></a>Exibir relatório de diagnóstico

Para exibir o Diagnóstico de MDM no HoloLens 2, selecione o ícone wi-fi **Configurações,** navegue até Contas de acesso de conta de trabalho ou de estudante e selecione Exportar seus logs de  ->    >   **gerenciamento**. HoloLens envia os arquivos de log para sua conta e exibe sua localização no computador desktop.

## <a name="diagnosticlog-csp"></a>CSP DiagnosticLog

Em um ambiente MDM (Mobile Gerenciamento de Dispositivos), o administrador de TI pode usar o [CSP (provedor](/windows/client-management/mdm/diagnosticlog-csp) de serviços de configuração diagnosticLog) para definir as configurações de diagnóstico em dispositivos HoloLens registro. O administrador de IT pode definir essas configurações para coletar logs de dispositivos inscritos.

Veja mais:
- [Coletar diagnósticos de um dispositivo Windows](/mem/intune/remote-actions/collect-diagnostics)
- [Visualização Pública do Intune – diagnóstico Windows 10 dispositivo](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está conectado a uma rede.
- O dispositivo é inscrito em um ambiente MDM que dá suporte ao CSP diagnosticLog.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Como o dispositivo faz parte do ambiente gerenciado, o usuário consente implicitamente o acesso administrativo às informações de diagnóstico.

O administrador de IT usa o CSP diagnosticLog para configurar as políticas de armazenamento, retenção e acesso de dados, incluindo as políticas que regem o seguinte:

- A infraestrutura de nuvem que armazena as informações de diagnóstico.
- O período de retenção para as informações de diagnóstico.
- Permissões que controlam o acesso às informações de diagnóstico.

## <a name="offline-diagnostics"></a>Diagnóstico offline
Em situações em que o dispositivo não é capaz de coletar diagnósticos por meio do Hub de Comentários ou do Configurações Solução de Problemas, você pode coletar o diagnóstico manualmente. Um cenário em que isso é necessário é quando o dispositivo não pode se conectar ao Wi-Fi ou você não pode acessar outros métodos mencionados acima. O diagnóstico coleta despejos de falha e logs do dispositivo que ajudam um engenheiro de suporte da Microsoft a isolar problemas.

Isso funciona quando o dispositivo aparece no Explorador de Arquivos depois de conectá-lo a um COMPUTADOR por meio de um cabo USB.

> [!NOTE]
> A geração e o gerenciamento de diagnóstico offline são controlados de forma diferente, dependendo da versão do sistema operacional. Anteriormente, ele era controlado pela configuração de telemetria, mas agora é controlado diretamente por meio da política de MDM. Se desabilitado por meio da configuração ou da política de MDM, os logs de diagnóstico não poderão ser coletados usando esse mecanismo.

Comportamento anterior ao [Windows Holographic, versão 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - O diagnóstico offline só é habilitado quando o usuário está passando pelo OOBE ou o valor da política [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) é definido como Completo (Básico é o valor padrão no HoloLens). 
- Para desabilitar o diagnóstico offline, acesse **a página Configurações Aplicativo > Privacidade** e selecione **Básico** em Dados **de Diagnóstico.** Em builds em que o diagnóstico offline depende da configuração de telemetria, ele afeta apenas se os logs são coletados ou não. Ele não afeta quais arquivos são coletados.
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

Em builds [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) e em diante:
- Quando o Diagnóstico de Fallback estiver habilitado será controlado por uma política de MDM específica com a configuração [Correspondente MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

Assista a este vídeo para saber mais.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estas etapas para coletar diagnósticos:

1.  Conexão o dispositivo com um cabo USB para seu computador.

2.  No Explorador de Arquivos no computador, navegue até **'Este \<hololens-device> COMPUTADOR \Interno Armazenamento'.**

3.  Se **a pasta Armazenamento** interna não aparecer, o dispositivo aguardará que um usuário entre. Entre ou ciclo de energia do dispositivo mantendo o botão POWER pressionado por 10 segundos.

4.  Pressione e solte imediatamente os **botões Power + Volume Down** juntos.

5.  Aguarde um minuto até que o dispositivo prepare os arquivos zip. (Um arquivo temporário chamado HololensDiagnostics.temp pode ficar visível enquanto o dispositivo gera os arquivos zip. Não acesse nem salve esse arquivo. Quando o processo for final, ele será substituído pelos arquivos zip.)

6.  Atualize o explorador de arquivos e navegue até a **pasta '\Documents'.**

7.  Copie os arquivos ZIP de diagnóstico e compartilhe-os com a equipe de suporte da Microsoft.

    > [!NOTE]
    > Alguns dos arquivos ZIP de diagnóstico podem conter PII.
