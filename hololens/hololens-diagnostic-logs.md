---
title: Coletar e usar informações de diagnóstico de dispositivos do HoloLens
description: Saiba como coletar, usar e reter informações de diagnóstico de dispositivos do HoloLens.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308215"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Coletar e usar informações de diagnóstico de dispositivos do HoloLens

Os usuários e administradores do HoloLens podem escolher entre quatro métodos diferentes para coletar informações de diagnóstico do HoloLens:

- Aplicativo de Hub de comentários
- CSP DiagnosticLog
- Aplicativo Configurações
- Diagnóstico offline

> [!IMPORTANT]  
> Os logs de diagnóstico do dispositivo contêm informações de identificação pessoal (PII), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. Quando vários usuários compartilham um dispositivo do HoloLens (por exemplo, os usuários entram no mesmo dispositivo usando contas diferentes do Microsoft Azure Active Directory (AD do Azure)), os logs de diagnóstico podem conter informações de PII que se aplicam a vários usuários. Para obter mais informações, consulte a [política de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).

A tabela a seguir compara métodos de coleção diferentes. Os nomes de método vinculam-se a informações mais detalhadas nas seções que seguem a tabela.

|Método |Pré-requisitos |Localizações de dados |Acesso e uso de dados |Retenção de dados |
| --- | --- | --- | --- | --- |
|[Hub de Feedback](#feedback-hub) |Conexão de rede e Internet<br /><br />Aplicativo de Hub de comentários<br /><br />Permissão para carregar arquivos para o Microsoft Cloud |Serviços de nuvem<br /><br />Dispositivo HoloLens (opcional) |O usuário solicita assistência, concorda com os termos de uso e carrega os dados<br /><br />Os funcionários da Microsoft visualizam os dados, como consistentes com os termos de uso |Os dados na nuvem são mantidos pelo período definido pela privacidade da próxima geração (NGP). Em seguida, os dados são excluídos automaticamente.<br /><br />Os dados no dispositivo podem ser excluídos a qualquer momento por um usuário que tenha permissões de **administrador** ou **proprietário do dispositivo** . |
|[Solução de problemas de configurações](#settings-troubleshooter) |Aplicativo Configurações |Dispositivos do HoloLens<br /><br />Computador conectado (opcional) |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário Compartilhe especificamente os dados com outro usuário). |Os dados são mantidos no dispositivo até que o usuário o exclua. * |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Conexão de rede<br /><br />Ambiente MDM que dá suporte ao CSP DiagnosticLog |O administrador configura os locais de armazenamento |No ambiente gerenciado, o usuário implicitamente consente com o acesso de administrador aos dados.<br /><br />O administrador configura as funções e permissões de acesso. | Os dados são retidos no armazenamento em nuvem e o administrador configura a política de retenção. |
|[Diagnóstico offline](#offline-diagnostics) |Configuração do dispositivo:<ul><li>Ligado e conectado ao computador</li><li>Botões de energia e volume funcionando</li></ul> |Dispositivos do HoloLens<br /><br />Computador conectado |O usuário armazena os dados e apenas o usuário acessa os dados (a menos que o usuário Compartilhe especificamente os dados com outro usuário). |Os dados são mantidos no dispositivo até que o usuário o exclua. |

- O usuário final é responsável por compartilhar os logs com responsabilidade com outra pessoa. Esses arquivos são úteis principalmente ao entrar em contato com o atendimento ao cliente e o suporte.  

## <a name="feedback-hub"></a>Hub de Feedback

Um usuário do HoloLens pode usar o aplicativo de área de trabalho do hub de comentários da Microsoft para enviar informações de diagnóstico para Suporte da Microsoft. Para obter detalhes e instruções completas, consulte [fornecer comentários](hololens-feedback.md).  

> [!NOTE]  
> **Usuários comerciais ou empresariais:** Se você usar o aplicativo de Hub de comentários para relatar um problema relacionado ao MDM, ao provisionamento ou a qualquer outro aspecto de gerenciamento de dispositivo, altere a categoria do aplicativo para a categoria de dispositivo de **gerenciamento empresarial**  >  .

### <a name="prerequisites"></a>Pré-requisitos

- O dispositivo está conectado a uma rede.
- O aplicativo de Hub de comentários está disponível no computador desktop do usuário e o usuário pode carregar arquivos para a nuvem da Microsoft.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Ao concordar com os termos de uso do hub de comentários, o usuário consentiu explicitamente o armazenamento e o uso dos dados (conforme definido por esse contrato).

O Hub de comentários fornece dois locais para o usuário armazenar informações de diagnóstico:

- **A nuvem da Microsoft**. Os dados que o usuário carrega usando o aplicativo de Hub de comentários são armazenados pelo número de dias que é consistente com os requisitos de privacidade da próxima geração (NGP). Os funcionários da Microsoft podem usar um visualizador compatível com NGP para acessar as informações durante esse período.
   > [!NOTE]  
   > Esses requisitos se aplicam aos dados em todas as categorias de Hub de comentários.

- **O dispositivo HoloLens**. Ao fazer o arquivamento de um relatório no Hub de comentários, o usuário pode selecionar **salvar uma cópia local de diagnósticos e anexos criados ao fornecer comentários**. Se o usuário selecionar essa opção, o Hub de comentários armazenará uma cópia das informações de diagnóstico no dispositivo do HoloLens. Essas informações permanecem acessíveis para o usuário (ou qualquer pessoa que use essa conta para entrar no HoloLens). Para excluir essas informações, um usuário deve ter permissões de **administrador** ou **proprietário do dispositivo** no dispositivo. Um usuário que tem as permissões apropriadas pode entrar no Hub de comentários, selecionar **configurações**  >  **Exibir logs de diagnóstico** e excluir as informações.

## <a name="settings-troubleshooter"></a>Solução de problemas de configurações

Um usuário do HoloLens pode usar o aplicativo configurações no dispositivo para solucionar problemas e coletar informações de diagnóstico. Para fazer isso, execute estas etapas:

1. Abra o aplicativo Configurações e selecione **Atualizar &**  >  página de **solução de problemas** de segurança.
1. Selecione a área apropriada e selecione **Iniciar**.
1. Reproduza o problema.
1. Depois de reproduzir o problema, retorne às configurações e, em seguida, selecione **parar**.

### <a name="prerequisites"></a>Pré-requisitos

- O aplicativo Configurações está instalado no dispositivo e está disponível para o usuário.

### <a name="data-locations-access-and-retention"></a>Locais de dados, acesso e retenção

Como o usuário inicia a coleta de dados, o usuário implicitamente consenti ao armazenamento das informações de diagnóstico. Somente o usuário ou qualquer pessoa com quem o usuário compartilha os dados pode acessar os dados.

As informações de diagnóstico são armazenadas no dispositivo. Se o dispositivo estiver conectado ao computador do usuário, as informações também residirão no computador no seguinte arquivo:

> Este \\ \<*HoloLens device name*> \\ documento de armazenamento interno do PC \\ documenta o \\ trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> Nesse caminho de arquivo e nome, \<*HoloLens device name*> representa o nome do dispositivo do HoloLens e \<*ddmmyyhhmmss*> representa a data e a hora em que o arquivo foi criado.

As informações de diagnóstico permanecem nesses locais até que o usuário a exclua.

## <a name="diagnosticlog-csp"></a>CSP DiagnosticLog

Em um ambiente de MDM (gerenciamento de dispositivo móvel), o administrador de ti pode usar o [provedor de serviços de configuração do DiagnosticLog (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) para definir as configurações de diagnóstico em dispositivos de HoloLens registrados. O administrador de ti pode definir essas configurações para coletar logs de dispositivos registrados.

Veja mais:
- [Coletar diagnósticos de um dispositivo Windows](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Visualização pública do Intune-diagnóstico de dispositivo do Windows 10](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

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
Em situações em que o dispositivo não é capaz de coletar diagnósticos por meio do hub de comentários ou da solução de problemas de configuração, você pode coletar o diagnóstico manualmente. Um cenário em que isso é necessário é quando o dispositivo não pode se conectar ao Wi-Fi ou você não pode acessar outros métodos mencionados acima. O diagnóstico coleta despejos de memória e logs do dispositivo que ajudam um engenheiro de suporte da Microsoft a isolar problemas.

Isso funciona quando o dispositivo aparece no explorador de arquivos depois de conectá-lo a um PC por meio de um cabo USB.

> [!NOTE]
> A geração e o gerenciamento de diagnósticos offline são controlados de forma diferente, dependendo da versão do seu sistema operacional. Anteriormente, ele era controlado pela configuração de telemetria, mas agora é controlado diretamente por meio da política de MDM. Se desabilitado por meio de configuração ou política de MDM, os logs de diagnóstico não poderão ser coletados usando esse mecanismo.

Comportamento anterior ao [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - O diagnóstico offline só é habilitado quando o usuário está passando por um valor de política OOBE ou [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) está definido como Full (Basic é o valor padrão no HoloLens). 
- Para desabilitar o diagnóstico offline, vá para **configurações aplicativo >** página de privacidade e selecione **básico** em **dados de diagnóstico**. Em compilações em que o diagnóstico offline depende da configuração de telemetria, ele só afetará se algum log for coletado ou não. Ele não afeta quais arquivos são coletados.
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

No Builds [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) e em diante:
- Quando o diagnóstico de fallback estiver habilitado, será controlado pela política de MDM específica com a configuração correspondente [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Se o dispositivo estiver bloqueado, os logs não aparecerão.

Assista a este vídeo para saber mais.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Siga estas etapas para coletar diagnósticos:
1.  Conecte o dispositivo a um cabo USB ao seu PC.
2.  No explorador de arquivos do seu computador, navegue até **"este PC \<hololens-device> \Internal Storage"**.
3.  Se a pasta de **armazenamento interno** não aparecer, o dispositivo está aguardando que um usuário entre. Conecte-se ou desligue o dispositivo mantendo o botão de energia pressionado por 10 segundos.
4.  Pressione e solte imediatamente os botões **Power + volume down** juntos.
5.  Aguarde um minuto para o dispositivo preparar os arquivos zip. (Um arquivo temporário chamado HololensDiagnostics. Temp pode ficar visível enquanto o dispositivo gera os arquivos zip. Não acesse nem salve esse arquivo. Quando o processo for concluído, ele será substituído pelos arquivos zip.)
6.  Atualize o explorador de arquivos e navegue até a pasta **' \Documents '** .
7.  Copie os arquivos ZIP de diagnóstico e compartilhe-os com a equipe de suporte da Microsoft.

> [!NOTE]
> Alguns dos arquivos ZIP de diagnóstico podem conter informações de identificação pessoal.
