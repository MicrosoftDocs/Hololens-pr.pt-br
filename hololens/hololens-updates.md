---
title: Gerenciar atualizações do HoloLens
description: Os administradores podem usar o gerenciamento de dispositivo móvel para gerenciar as atualizações de dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3a2246296c5ab8aa86dfaa419ed02aa5a961dbfc
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163129"
---
# Gerenciar atualizações do HoloLens

O HoloLens usa o Windows Update da mesma maneira que outros dispositivos do Windows 10. Quando uma atualização estiver disponível, ela será baixada e instalada automaticamente da próxima vez que o dispositivo estiver plugado e conectado à Internet. Este artigo descreve como gerenciar as atualizações em um ambiente corporativo ou outro ambiente gerenciado. Para obter informações sobre o gerenciamento de atualizações para dispositivos HoloLens individuais, confira [Atualizar HoloLens](hololens-update-hololens.md).

## Gerenciar atualizações automaticamente

### Gerenciar atualizações usando o Windows Update para Empresas

O Windows Holographic for Business pode usar o [Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para gerenciar as atualizações. Todos os dispositivos do HoloLens 2 podem usar o Windows Holographic for Business. Certifique-se de que eles usem o Windows Holographic for Business Build 10.0.18362.1042 ou posterior. Se você tiver dispositivos HoloLens (1ª geração), você precisará [atualizá-los para o Windows Holographic for Business](hololens1-upgrade-enterprise.md) para gerenciar as atualizações.

O Windows Update para Empresas conecta dispositivos do HoloLens diretamente ao serviço do Windows Update. Usando o Windows Update para Empresas, você pode controlar vários aspectos do processo de atualização&mdash;ou seja, quais dispositivos recebem quais são as atualizações. Por exemplo, você pode distribuir as atualizações para um subconjunto de dispositivos para teste e, em seguida, distribuir as atualizações para os dispositivos restantes. Ou você pode definir diferentes agendamentos de atualização para diferentes tipos de atualizações.

> [!NOTE]  
> Para dispositivos HoloLens, você pode gerenciar automaticamente as atualizações de recursos (lançadas duas vezes por ano) e atualizações de qualidade (lançadas mensalmente ou conforme necessário, incluindo atualizações de importantes de segurança). Para obter mais informações sobre os tipos de atualização, confira [Tipos de atualizações gerenciados pelo Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Você pode configurar o Windows Update para Empresas para o HoloLens usando políticas em uma solução de Gerenciamento de Dispositivo Móvel (MDM), como o Microsoft Intune.

### Defina as configurações do Windows Update para Empresas usando o Microsoft Intune.

Para obter mais informações sobre como usar o Intune para configurar o Windows Update para Empresas, confira [Gerenciar as atualizações de software do Windows 10 no Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure). Para obter mais informações sobre a funcionalidade específica do Intune compatível com o HoloLens, confira [Funções de gerenciamento de atualização do Intune que o HoloLens oferece suporte](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> O Intune fornece dois tipos de política para o gerenciamento de atualizações: *Anel de atualizações do Windows 10* e *Atualizações de recursos do Windows 10*. O tipo de política de atualização de recursos do Windows 10 está na visualização pública no momento e não tem suporte para o HoloLens.
>  
> Use as políticas de atualização do Windows 10 para gerenciar as atualizações do HoloLens 2.

### Configurar políticas de atualização para o HoloLens 2 ou para o HoloLens (1ª geração)

Esta seção descreve as políticas que você pode usar para gerenciar as atualizações do HoloLens 2 ou do HoloLens (1ª geração). Para saber mais sobre funcionalidades adicionais que estão disponíveis para o HoloLens 2, confira [Planejar e configurar as distribuições de atualização para o HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

A [Política de CSP - Atualização](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) define as políticas que configuram o Windows Update para Empresas.

> [!NOTE]  
> Para obter uma lista de provedores de serviços de configuração de política (CSPs) específicos com suporte em edições específicas do HoloLens, confira [Política de CSPs com dispositivos HoloLens compatíveis](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### Configurar verificações automáticas para atualizações

Você pode usar a política **Update/AllowAutoUpdate** para gerenciar o comportamento de atualização automática, como a verificação, o download e a instalação das atualizações. Para obter mais detalhes sobre as configurações disponíveis para essa política, confira [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> No Microsoft Intune, você pode usar o **Comportamento de Atualização Automática** para alterar essa política. Para obter mais informações, consulte [Gerenciar atualizações de software Windows 10 no Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Configurar um cronograma de atualização

Para configurar como e quando as atualizações serão aplicadas, use as seguintes políticas:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valores: **0**–**7** (0 = todos os dias, 1 = domingo, 7 = sábado)
  - Valor padrão: **0** (todos os dias)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valores: 0 – 23 (0 = meia-noite, 23 = 23:00)
  - Valor padrão: 15:00

#### Configurar o horário ativo
A partir do [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) um Administrador de TI pode especificar o intervalo de horário ativo para dispositivos do HoloLens 2.

O horário ativo identifica o período de tempo em que você espera que o dispositivo esteja em uso. As reinicializações automáticas após uma atualização ocorrerão fora do horário ativo. O intervalo especificado será contado a partir da hora de início do horário ativo. Você pode usar o MDM, conforme descrito em [Configurando o horário ativo com o MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). O MDM usa as configurações Update/ActiveHoursStart, Update/ActiveHoursEnd e Update/ActiveHoursMaxRange no CSP da Política para configurar horários ativos.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) – Esse valor define a hora de término. Há um máximo de 12 horas a partir da hora de início.
    -   Os valores com suporte são 0-23, em que 0 é 12 AM, 1 é 1 AM, etc.
    -   O padrão é 17 (5 PM).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Esse valor define o número máximo de horas ativas a partir da hora de início.
    -   Os valores com suporte são 8-18.
    -   O valor padrão é 18 (horas).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – Esse valor define a hora de início. Há um máximo de 12 horas a partir da hora de término.
    -   Os valores com suporte são 0-23, em que 0 é 12 AM, 1 é 1 AM, etc.
    -   O valor padrão é 8 (8 AM).

#### Para dispositivos que executam o Windows 10, somente a versão 1607

Você pode usar as seguintes políticas de atualização para configurar os dispositivos para obter atualizações do Windows Server Update Services (WSUS), em vez do Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Planejar e configurar as atualizações de atualização do HoloLens 2

O HoloLens 2 oferece suporte a mais recursos de automação de atualização do que o HoloLens (1ª geração). Isso será especialmente útil se você usar o Microsoft Intune para gerenciar as políticas do Windows Update para Empresas. Esses recursos facilitam o planejamento e a implementação de distribuições de atualização em toda a organização.

#### Planejar a estratégia de atualização

O Windows Update para Empresas aceita políticas de adiamento. Após o lançamento da Microsoft, você pode usar uma política de adiamento para definir quanto tempo deve esperar antes de instalar essa atualização nos dispositivos. Ao associar os subconjuntos de seus dispositivos (chamados de *anéis de atualização*) com políticas de adiamento diferentes, você pode coordenar uma estratégia de distribuição de atualização para a sua organização.

Por exemplo, considere uma organização que tenha 1.000 dispositivos e tenha que atualizá-los de cinco maneiras. A organização pode criar cinco anéis de atualização, conforme mostrado na tabela a seguir.

|Grupo |Número de dispositivos |Adiamento (dias) |
| ---| :---: | :---: |
|Grupo 1 (equipe de TI) |5 |0 |
|Grupo 2 (usuário pioneiro) |50 |60 |
|Grupo 3 (principal 1) |250 |120 |
|Grupo 4 (principal 2) |300 |150 |
|Grupo 5 (principal 3) |395 |180 |

Veja como a distribuição avança ao longo do tempo por toda a organização.

![Linha do tempo para implantação de atualizações](./images/hololens-updates-timeline.png)

#### Configurar uma política de adiamento de atualização

Uma política de adiamento especifica o número de dias entre a data em que uma atualização estará disponível e a data em que a atualização será oferecida a um dispositivo.

Você pode configurar adiamentos diferentes para atualizações de recursos e atualizações de qualidade. A tabela a seguir lista as políticas específicas que devem ser usadas para cada tipo, bem como o adiamento máximo de cada uma delas.

|Categoria |Política |Adiamento máximo |
| --- | --- | --- |
|Atualizações de recursos |DeferFeatureUpdatesPeriodInDays |365 dias |
|Atualizações de qualidade |DeferQualityUpdatesPeriodInDays |30 dias |

#### Pausar Atualizações via Dispositivo

Se um usuário não tiver acesso ao MDM, poderá Pausar individualmente as atualizações por até 35 dias manualmente em um dispositivo HoloLens 2 na compilação [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) ou posterior. Os usuários podem acessar esta configuração navegando até **Configurações -> Atualização e Segurança -> Opções avançadas** role para baixo até **Pausar atualizações** e escolha a data e por quais dias as atualizações deverão estar pausadas. Quando um usuário atingir o limite de pausa, o dispositivo precisa receber novas atualizações porque ele pode pausar novamente. 

Starting with [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2), this pause updates fuction can be managed for HoloLens 2 devices. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (padrão) – Habilitado
    - 1 – Desabilitado

#### Funções de gerenciamento de atualização do Intune com suporte do HoloLens

Você pode usar as seguintes funções de gerenciamento de atualização do Intune para gerenciar as atualizações do HoloLens.

- **Criar** e **Atribuir**: essas funções adicionam um anel de atualização do Windows 10 à lista de anéis de atualização. Para obter mais informações, consulte [Criar e atribuir anéis de atualização](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pausar**: Se encontrar um problema ao implantar um recurso ou uma atualização de qualidade, você pode pausar a atualização por 35 dias (a partir de uma data especificada). Essa pausa impede que outros dispositivos instalem a atualização até que você resolva ou atenue o problema. Se você pausar uma atualização de recursos, as atualizações de qualidade ainda serão oferecidas aos dispositivos para garantir que eles permaneçam seguros. Quando um tipo de atualização é pausado, o painel Visão geral exibe quantos dias restam para que o tipo de atualização seja retomado. Após o término do período de tempo especificado, a pausa automaticamente expirará e o processo será reiniciado.

  Enquanto o anel de atualização estiver pausado, você poderá selecionar uma das opções a seguir:

  - **Estender**: Para estender o período de pausa para um tipo de atualização por 35 dias.
  - **Reiniciar**: Restaura as atualizações para aquele anel para operação ativa. Você pode pausar o anel de atualização novamente, se necessário.

  > [!NOTE]  
  > Não há suporte para a operação **Desinstalar** anéis de atualização em dispositivos HoloLens 2.

## Verificar atualizações manualmente

Embora o HoloLens verifique periodicamente se há atualizações do sistema, pode haver circunstâncias em que você deseje verificar manualmente.

Para verificar manualmente se há atualizações, vá para **Configurações** > **Atualização & segurança** > **Verificar se há atualizações**. Se o aplicativo Configurações indicar que seu dispositivo está atualizado, você tem todas as atualizações que estão disponíveis no momento.

## Reverter uma atualização manualmente

Em alguns casos, talvez você queira voltar a uma versão anterior do software do HoloLens. O processo para fazer isso depende se você estiver usando o HoloLens 2 ou o HoloLens (1ª geração).

### Voltar para a versão anterior (HoloLens 2)

Você pode reverter as atualizações e retornar a uma versão anterior do HoloLens 2 usando o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) para retornar seu HoloLens para a versão anterior.

> [!NOTE]
> A reversão para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens 2, siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.
1. No computador, baixe o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) na Microsoft Store.
1. Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).
1. Após concluir os downloads, abra **Explorador de arquivos** > **Downloads**, clique com o botão direito do mouse na pasta compactada (.zip) que você acabou de baixar e, em seguida, selecione **Extrair tudo** > **Extrair** para expandir o arquivo.
1. Use um cabo USB-A para USB-C para conectar o dispositivo do HoloLens ao computador. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse tipo de cabo funciona melhor).
1. O Advanced Recovery Companion detecta automaticamente seu dispositivo do HoloLens. Selecione o bloco **Microsoft HoloLens**.
1. Na tela seguinte, marque a **Seleção de pacote manual** e, em seguida, abra a pasta que você expandiu anteriormente.
1. Selecione o arquivo de instalação (.ffu).
1. Selecione**Instalar software** e siga as instruções.

### Voltar para a versão anterior (HoloLens (1ª geração))

Você pode reverter as atualizações e retornar a uma versão anterior do HoloLens (1ª geração) usando a [Windows Device Recovery Tool](https://support.microsoft.com/help/12379) para retornar o HoloLens para a versão anterior.

> [!NOTE]
> A reversão para uma versão anterior do HoloLens exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens (1ª geração), siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.
1. No computador, baixe a [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Baixe o [Pacote de recuperação de Atualização de Aniversário do HoloLens](https://aka.ms/hololensrecovery).
1. Após concluir os downloads, abra **Explorador de arquivos** > **Downloads**, clique com o botão direito do mouse na pasta compactada (.zip) que você acabou de baixar e, em seguida, selecione **Extrair tudo** > **Extrair** para expandir o arquivo.
1. Use o cabo micro-USB fornecido em conjunto com seu dispositivo do HoloLens para conectar o dispositivo HoloLens ao computador. (Mesmo que você esteja usando outros cabos para conectar o dispositivo HoloLens, esse funciona melhor).
1. O WDRT detecta automaticamente seu dispositivo do HoloLens. Selecione o bloco **Microsoft HoloLens**.
1. Na tela seguinte, marque a **Seleção de pacote manual** e, em seguida, abra a pasta que você expandiu anteriormente.
1. Selecione o arquivo de instalação (.ffu).
1. Selecione**Instalar software** e siga as instruções.

**Se o WDRT não detectar o seu dispositivo**

Se o WDRT não detectar o seu dispositivo HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **Meu dispositivo não foi detectado**, selecione **Microsoft HoloLens** e siga as instruções.

## Artigos relacionados

- [Notas de versão do HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [O que é o Windows Update para Empresas?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Atribuir dispositivos a canais de serviços para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gerenciar as atualizações de software do Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
