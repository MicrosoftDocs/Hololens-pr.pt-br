---
title: Coletar e usar informações de diagnóstico de dispositivos HoloLens
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
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
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827717"
---
# Coletar e usar informações de diagnóstico de dispositivos HoloLens

Usuários e administradores do HoloLens podem escolher entre quatro métodos diferentes para coletar informações de diagnóstico do HoloLens:

- Aplicativo Hub de feedback
- CSP DiagnosticLog
- Aplicativo Configurações

> [!IMPORTANT]  
> Os logs de diagnóstico de dispositivo contêm informações de identificação pessoal (PII), como, por exemplo, quais processos ou aplicativos são iniciados pelo usuário durante operações típicas. Quando vários usuários compartilham um dispositivo HoloLens (por exemplo, usuários entram no mesmo dispositivo usando contas do Microsoft Azure Active Directory (AAD) diferentes), os logs de diagnóstico podem conter informações PII que se aplicam a vários usuários. Para obter mais informações, consulte [declaração de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).

A tabela a seguir compara os três métodos de coleção. O link nome do método para obter informações mais detalhadas nas seções que seguem a tabela.

|Método |Pré-requisitos |Locais de dados |Acesso e uso de dados |Retenção de dados |
| --- | --- | --- | --- | --- |
|[Hub de Feedback](#feedback-hub) |Conexão de rede e Internet<br /><br />Aplicativo Hub de feedback<br /><br />Permissão para carregar arquivos para o Microsoft Cloud |Microsoft Cloud<br /><br />Dispositivo HoloLens (opcional) |O usuário solicita assistência, concorda com os termos de uso e carrega os dados<br /><br />Os funcionários da Microsoft visualizam os dados, conforme os termos de uso |Os dados na nuvem são mantidos pelo período definido pela NGP (privacidade de próxima geração). Em seguida, os dados são excluídos automaticamente.<br /><br />Os dados no dispositivo podem ser excluídos a qualquer momento por um usuário que tenha permissões de **administrador** ou de **proprietário do dispositivo** . |
|[Solução de problemas de configurações](#settings-troubleshooter) |Aplicativo Configurações |Dispositivo HoloLens<br /><br />Computador conectado (opcional) |O usuário armazena os dados, e somente o usuário acessa os dados (a menos que o usuário principalmente compartilhe os dados com outro usuário). |Os dados são mantidos até que o usuário o exclua. * |
|[CSP DiagnosticLog](#diagnosticlog-csp) |Conexão de rede<br /><br />Ambiente MDM que dá suporte ao CSP DiagnosticLog |O administrador configura locais de armazenamento |No ambiente gerenciado, o usuário implicitamente envia ao administrador o acesso aos dados.<br /><br />O administrador configura funções e permissões de acesso. | O administrador configura a política de retenção. |


-   O usuário final é responsável por compartilhar os logs com responsabilidade com outras pessoas. Esses arquivos são úteis principalmente ao entrar em contato com o serviço de atendimento ao cliente e suporte.  

## Hub de Feedback

Um usuário do HoloLens pode usar o aplicativo de área de trabalho do hub de feedback da Microsoft para enviar informações de diagnóstico para o suporte da Microsoft. Para obter detalhes e instruções completas, consulte [nos fornecer comentários](hololens-feedback.md).  

> [!NOTE]  
> **Usuários comerciais ou empresariais:** Se você usar o aplicativo de Hub de comentários para relatar um problema relacionado ao MDM, ao provisionamento ou a qualquer outro aspecto de gerenciamento de dispositivos, altere a categoria do aplicativo para a categoria de dispositivo de **gerenciamento corporativo**  >  **Device category**.

### Pré-requisitos

- O dispositivo está conectado a uma rede.
- O aplicativo Hub de feedback está disponível no computador da área de trabalho do usuário e o usuário pode carregar arquivos para a nuvem da Microsoft.

### Locais de dados, acesso e retenção

Ao concordar com os termos de uso do hub de feedback, o usuário implicitamente se reenvia ao armazenamento e uso dos dados (conforme definido por esse contrato).

O Hub de feedback fornece dois locais para o usuário armazenar as informações de diagnóstico:

- **A nuvem da Microsoft**. Os dados carregados pelo usuário usando o aplicativo de Hub de feedback são armazenados pelo número de dias que são consistentes com os requisitos de privacidade de próxima geração (NGP). Os funcionários da Microsoft podem usar um visualizador compatível com o NGP para acessar as informações durante esse período.
   > [!NOTE]  
   > Esses requisitos se aplicam aos dados em todas as categorias do hub de feedback.

- **O dispositivo HoloLens**. Durante o arquivamento de um relatório no Hub de feedback, o usuário pode selecionar **salvar uma cópia local do diagnóstico e dos anexos criados ao fazer comentários**. Se o usuário selecionar essa opção, o Hub de feedback armazenará uma cópia das informações de diagnóstico no dispositivo HoloLens. Essas informações permanecem acessíveis para o usuário (ou para qualquer pessoa que use essa conta para entrar no HoloLens). Para excluir essas informações, um usuário deve ter permissões de **administrador** ou de **proprietário do dispositivo** no dispositivo. Um usuário com as permissões apropriadas pode entrar no Hub de feedback, selecionar **configurações**  >  **Exibir logs de diagnóstico**e excluir as informações.

## Solução de problemas de configurações

Um usuário do HoloLens pode usar o aplicativo configurações no dispositivo para solucionar problemas e coletar informações de diagnóstico. Para fazer isso, execute estas etapas:

1. Abra o aplicativo Configurações e selecione **Atualizar &**  >  página de**solução de problemas** de segurança.
1. Selecione a área apropriada e escolha **Iniciar**.
1. Reproduza o problema.
1. Depois de reproduzir o problema, retorne a configurações e, em seguida, escolha **parar**.

### Pré-requisitos

- O aplicativo Configurações está instalado no dispositivo e está disponível para o usuário.

### Locais de dados, acesso e retenção

Como o usuário inicia a coleta de dados, o usuário implicitamente se reenvia ao armazenamento das informações de diagnóstico. Somente o usuário ou qualquer pessoa com quem o usuário compartilhar os dados poderá acessar os dados.

As informações de diagnóstico são armazenadas no dispositivo. Se o dispositivo estiver conectado ao computador do usuário, as informações também serão localizadas no computador no seguinte arquivo:

> Este PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> Nesse nome e caminho de arquivo, \<*HoloLens device name*> representa o nome do dispositivo HoloLens e \<*ddmmyyhhmmss*> representa a data e a hora em que o arquivo foi criado.

As informações de diagnóstico permanecerão nestes locais até que o usuário a exclua.

## CSP DiagnosticLog

Em um ambiente de gerenciamento de dispositivos móveis (MDM), o administrador de ti pode usar o [provedor de serviços de configuração (CSP) do DiagnosticLog](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) para definir as configurações de diagnóstico em dispositivos do HoloLens registrados. O administrador de ti pode definir essas configurações para coletar logs de dispositivos registrados.

### Pré-requisitos

- O dispositivo está conectado a uma rede.
- O dispositivo está registrado em um ambiente MDM que dá suporte ao CSP DiagnosticLog.

### Locais de dados, acesso e retenção

Como o dispositivo faz parte do ambiente gerenciado, o usuário implicitamente envia ao acesso administrativo às informações de diagnóstico.

O administrador de ti usa o CSP DiagnosticLog para configurar as políticas de armazenamento, retenção e acesso a dados, incluindo as políticas que regem o seguinte:

- A infraestrutura de nuvem que armazena as informações de diagnóstico.
- O período de retenção das informações de diagnóstico.
- Permissões que controlam o acesso às informações de diagnóstico.


