---
title: Gerenciar atualizações do HoloLens
description: Saiba como os administradores podem usar o gerenciamento de dispositivos móveis para gerenciar atualizações em dispositivos HoloLens.
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427930"
---
# <a name="manage-hololens-updates"></a>Gerenciar atualizações do HoloLens

O HoloLens usa o Windows Update da mesma maneira que outros dispositivos do Windows 10. Quando uma atualização estiver disponível, ela será baixada e instalada automaticamente da próxima vez que o dispositivo estiver plugado e conectado à Internet. Este artigo descreve como gerenciar as atualizações em um ambiente corporativo ou outro ambiente gerenciado. Para obter informações sobre o gerenciamento de atualizações para dispositivos HoloLens individuais, confira [Atualizar HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Gerenciar atualizações automaticamente

### <a name="managing-updates-by-using-windows-update-for-business"></a>Gerenciar atualizações usando o Windows Update para Empresas

O Windows Holographic for Business pode usar o [Windows Update para Empresas](/windows/deployment/update/waas-manage-updates-wufb) para gerenciar atualizações. Todos os dispositivos do HoloLens 2 podem usar o Windows Holographic for Business. Eles devem usar o Windows Holographic for Business Build 10.0.18362.1042 ou posterior. Se você tiver dispositivos HoloLens (1ª geração), precisará [atualizá-los para Windows Holographic for Business](hololens1-upgrade-enterprise.md) para gerenciar suas atualizações.

O Windows Update para Empresas conecta dispositivos do HoloLens diretamente ao serviço do Windows Update. Usando o Windows Update para Empresas, você pode controlar vários aspectos do processo de atualização&mdash;ou seja, quais dispositivos recebem quais são as atualizações. Por exemplo, você pode distribuir as atualizações para um subconjunto de dispositivos para teste e, em seguida, distribuir as atualizações para os dispositivos restantes. Ou você pode definir diferentes agendamentos de atualização para diferentes tipos de atualizações.

> [!NOTE]  
> Para dispositivos HoloLens, você pode gerenciar automaticamente as atualizações de recursos (lançadas duas vezes por ano) e atualizações de qualidade (lançadas mensalmente ou conforme necessário, incluindo atualizações de importantes de segurança). Para obter mais informações sobre os tipos de atualização, confira [Tipos de atualizações gerenciadas pelo Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Você pode configurar o Windows Update para Empresas para o HoloLens usando políticas em uma solução de Gerenciamento de Dispositivo Móvel (MDM), como o Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Definir as configurações do Windows Update para Empresas usando o Microsoft Intune

Para conferir uma discussão detalhada sobre como usar o Intune para configurar o Windows Update para Empresas, confira [Gerenciar atualizações de software do Windows 10 no Intune](/intune/protect/windows-update-for-business-configure). Para obter mais informações sobre a funcionalidade específica do Intune com a qual o HoloLens é compatível, confira [Funções de gerenciamento de atualizações do Intune com as quais o HoloLens é compatível](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> O Intune apresenta dois tipos de política para gerenciar atualizações: *Grupo de atualização do Windows 10* e *atualização de recursos do Windows 10*. O tipo de política de atualização de recursos do Windows 10 está na versão preliminar pública no momento e não é compatível com o HoloLens.
>  
> Use as políticas de atualização do Windows 10 para gerenciar as atualizações do HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Configurar políticas de atualização para o HoloLens 2 ou para o HoloLens (1ª geração)

Esta seção descreve as políticas que você pode usar para gerenciar as atualizações do HoloLens 2 ou do HoloLens (1ª geração). Para obter mais informações sobre a funcionalidade que está disponível para o HoloLens 2, confira [Planejar e configurar distribuições de atualização para o HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

O [Provedor de Soluções na Nuvem de Política – atualizações](/windows/client-management/mdm/policy-csp-update) define as políticas que configuram o Windows Update para Empresas.

> [!NOTE]  
> Para obter uma lista de CSPs (Provedores de Soluções na Nuvem) específicos da política compatíveis com edições específicas do HoloLens, confira [CSPs de política compatíveis com dispositivos HoloLens](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Configurar verificações automáticas para atualizações

Você pode usar a política **Update/AllowAutoUpdate** para gerenciar o comportamento de atualização automática, como a verificação, o download e a instalação das atualizações. Para obter mais informações sobre as configurações disponíveis para essa política, confira [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> No Microsoft Intune, você pode usar o **Comportamento de atualização automática** para alterar essa política. Para obter mais informações, confira [Gerenciar as atualizações de software do Windows 10 no Intune](/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Configurar um cronograma de atualização

Para configurar como e quando as atualizações serão aplicadas, use as seguintes políticas:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valores: **0**–**7** (0 = todos os dias, 1 = domingo, 7 = sábado)
  - Valor padrão: **0** (todos os dias)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valores: 0–23 (0 = meia-noite, 23 = 11 PM)
  - Valor padrão: 3 AM

#### <a name="configure-active-hours"></a>Configurar o horário ativo
A partir do [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2), um administrador de TI pode especificar o intervalo de horas ativas para dispositivos HoloLens 2.

Horário ativo identifica o período de tempo em que você espera que o dispositivo esteja em uso. As reinicializações automáticas após uma atualização ocorrerão fora do horário ativo. O intervalo especificado será contado a partir da hora de início do horário ativo. Você pode usar o MDM, conforme descrito em [Configurando o horário ativo com o MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). O MDM usa as configurações ActiveHoursStart/Update e Update/ActiveHoursEnd e Update/ActiveHoursMaxRange do CSP da Política para configurar o horário ativo.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend): esse valor define a hora de término. Há um máximo de 12 horas a partir da hora de início.
    -   Os valores compatíveis são 0-23, em que 0 é 12 AM, 1 é 1 AM etc.
    -   O padrão é 17 (5 PM).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange): esse valor define o número máximo de horas ativas a partir da hora de início.
    -   Os valores compatíveis estão entre 8 e 18.
    -   O valor padrão é 18 (2 horas).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart): esse valor define a hora de início. Há um máximo de 12 horas a partir da hora de término.
    -   Os valores compatíveis são 0-23, em que 0 é 12 AM, 1 é 1 AM etc.
    -   O valor padrão é 8 (8 AM).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Para dispositivos que executam o Windows 10, somente a versão 1607

Você pode usar as seguintes políticas de atualização para configurar os dispositivos para obter atualizações do Windows Server Update Services (WSUS), em vez do Windows Update:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planejar e configurar as atualizações de atualização do HoloLens 2

O HoloLens 2 oferece suporte a mais recursos de automação de atualização do que o HoloLens (1ª geração). Isso será especialmente útil se você usar o Microsoft Intune para gerenciar as políticas do Windows Update para Empresas. Esses recursos facilitam o planejamento e a implementação de distribuições de atualização em toda a organização.

#### <a name="plan-the-update-strategy"></a>Planejar a estratégia de atualização

O Windows Update para Empresas aceita políticas de adiamento. Após o lançamento da Microsoft, você pode usar uma política de adiamento para definir quanto tempo deve esperar antes de instalar essa atualização nos dispositivos. Ao associar os subconjuntos de seus dispositivos (chamados de *grupos de atualização*) com políticas de adiamento diferentes, você pode coordenar uma estratégia de distribuição de atualização para a sua organização.

Por exemplo, considere uma organização que tenha 1.000 dispositivos e tenha que atualizá-los de cinco maneiras. A organização pode criar cinco anéis de atualização, conforme mostrado na tabela a seguir.

|Grupo |Número de dispositivos |Adiamento (dias) |
| ---| :---: | :---: |
|Grp 1 (equipe de TI) |5 |0 |
|Grp 2 (usuários pioneiros) |50 |60 |
|Grp 3 (principal 1) |250 |120 |
|Grp 4 (principal 2) |300 |150 |
|Grp 5 (principal 3) |395 |180 |

Veja como a distribuição avança ao longo do tempo por toda a organização.

![Linha do tempo para implantação de atualizações.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Configurar uma política de adiamento de atualização

Uma política de adiamento especifica o número de dias entre a data em que uma atualização estará disponível e a data em que a atualização será oferecida a um dispositivo.

Você pode configurar adiamentos diferentes para atualizações de recursos e atualizações de qualidade. A tabela a seguir lista as políticas específicas que devem ser usadas para cada tipo, bem como o adiamento máximo de cada uma delas.

|Categoria |Política |Adiamento máximo |
| --- | --- | --- |
|Atualizações de recursos |DeferFeatureUpdatesPeriodInDays |365 dias |
|Atualizações de qualidade |DeferQualityUpdatesPeriodInDays |30 dias |

#### <a name="pause-updates-via-device"></a>Pausar Atualizações via Dispositivo

Se um usuário não tiver acesso ao MDM, poderá Pausar individualmente as atualizações por até 35 dias manualmente em um dispositivo HoloLens 2 na build [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) ou posterior. Os usuários podem acessar essa configuração navegando até **Configurações > Atualização e Segurança > Opções avançadas**  rolando para baixo até **Pausar atualizações** e escolhendo a data até a qual as atualizações serão pausadas. Quando um usuário atingir o limite de pausa, o dispositivo precisa receber novas atualizações porque ele pode pausar novamente. 

A partir do [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2), essa função de atualização de pausa pode ser gerenciada para dispositivos HoloLens 2. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (padrão) = Habilitada
    - 1: desabilitado

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funções de gerenciamento de atualização do Intune com suporte do HoloLens

Você pode usar as seguintes funções de gerenciamento de atualização do Intune para gerenciar as atualizações do HoloLens.

- **Criar** e **Atribuir**: essas funções adicionam um anel de atualização do Windows 10 à lista de grupos de atualização. Para obter mais informações, confira [Criar e atribuir grupos de atualização](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pausar**: se encontrar um problema ao implantar um recurso ou uma atualização de qualidade, você pode pausar a atualização por 35 dias (a partir de uma data especificada). Essa pausa impede que outros dispositivos instalem a atualização até que você resolva ou atenue o problema. Se você pausar uma atualização de recursos, as atualizações de qualidade ainda serão oferecidas aos dispositivos para garantir que eles permaneçam seguros. Quando um tipo de atualização é pausado, o painel Visão geral desse anel exibe os dias restantes até que o tipo de atualização seja retomado. Após o término do período especificado, a pausa automaticamente expirará e o processo será reiniciado.

  Enquanto o anel de atualização estiver pausado, você poderá escolher uma das opções a seguir:

  - **Estender**: para estender o período de pausa para um tipo de atualização por 35 dias.
  - **Retomar**: restaura as atualizações para aquele anel para operação ativa. Você pode pausar o anel de atualização novamente, se necessário.

  > [!NOTE]  
  > Não há suporte para a operação **Desinstalar** grupos de atualização em dispositivos HoloLens 2.

### <a name="delivery-optimization-preview"></a>Versão prévia de otimização de entrega

O [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) habilitou uma versão prévia antecipada para configurações de otimização de entrega para reduzir o consumo de largura de banda para downloads de vários dispositivos HoloLens. Uma descrição mais completa dessa funcionalidade com a configuração de rede recomendada está disponível aqui: [Otimização de entrega para atualizações do Windows 10](/windows/deployment/update/waas-delivery-optimization).

As seguintes configurações são habilitadas como parte da superfície de gerenciamento e [podem ser configuradas no Intune](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algumas advertências sobre essa oferta de versão prévia:

- O suporte do HoloLens é limitado nesta versão prévia apenas a atualizações do sistema operacional.
- O Windows Holographic for Business permite apenas modos de download HTTP e downloads de um [ponto de extremidade do Cache Conectado da Microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). Não há compatibilidade com modos de download ponto a ponto e atribuições de grupo em dispositivos HoloLens no momento.
- O HoloLens é compatível com a implantação ou a otimização de entrega para pontos de extremidade do Windows Server Update Services.
- A solução de problemas exigirá o diagnóstico no servidor Cache Conectado ou a coleta de um rastreamento no HoloLens no HoloLens por meio do **Configurações** > **Atualização e Segurança** >  **Solução de problemas** >  **Windows Update**.

## <a name="manually-check-for-updates"></a>Verificar atualizações manualmente

Embora o HoloLens verifique periodicamente se há atualizações do sistema, pode haver circunstâncias em que você deseje verificar manualmente.

Para verificar manualmente se há atualizações, acesse **Configurações** > **Atualização e Segurança** > **Verificação de segurança**. Se o aplicativo Configurações indicar que seu dispositivo está atualizado, você tem todas as atualizações que estão disponíveis no momento.

## <a name="manually-roll-back-an-update"></a>Reverter uma atualização manualmente

Em alguns casos, talvez você queira voltar a uma versão anterior do software do HoloLens. O processo para fazer isso depende se você estiver usando o HoloLens 2 ou o HoloLens (1ª geração).

### <a name="revert-to-a-previous-version-hololens-2"></a>Voltar para a versão anterior (HoloLens 2)

Você pode reverter as atualizações e retornar a uma versão anterior do HoloLens 2 usando o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) para retornar seu HoloLens para a versão anterior.

> [!NOTE]
> A reversão para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens 2, siga estas etapas:

1. Você não deve ter telefones ou dispositivos Windows conectados ao computador.
1. No computador, faça download do [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) na Microsoft Store.
1. Faça download da [versão do HoloLens 2 mais recente](https://aka.ms/hololens2download).
1. Após a conclusão dos downloads, abra o **Explorador de Arquivos** > **Downloads**, clique com o botão direito do mouse na pasta compactada (.zip) que você acabou de baixar e escolha **Extrair todos**  > **Extrair** para expandir o arquivo.
1. Use um cabo USB-A para USB-C para conectar o dispositivo do HoloLens ao computador. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse tipo de cabo funciona melhor).
1. O Advanced Recovery Companion detecta automaticamente seu dispositivo do HoloLens. Escolha o bloco **Microsoft HoloLens**.
1. Na tela seguinte, escolha **Seleção manual de pacote** e, em seguida, abra a pasta que você expandiu anteriormente.
1. Escolha o arquivo de instalação (.ffu).
1. Escolha **Instalar software** e siga as instruções.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Voltar para a versão anterior [HoloLens (1ª geração)]

Você pode reverter as atualizações e retornar a uma versão anterior do HoloLens (1ª geração) usando a [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) para retornar o HoloLens para a versão anterior.

> [!NOTE]
> A reversão para uma versão anterior do HoloLens exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens (1ª geração), siga estas etapas:

1. Você não deve ter telefones ou dispositivos Windows conectados ao computador.
1. Em seu computador, faça download da [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Faça download do [pacote de recuperação HoloLens Anniversary Update](https://aka.ms/hololensrecovery).
1. Após a conclusão dos downloads, abra o **Explorador de Arquivos** > **Downloads**, clique com o botão direito do mouse na pasta compactada (.zip) que você acabou de baixar e escolha **Extrair todos**  > **Extrair** para expandir o arquivo.
1. Use o cabo micro-USB fornecido em conjunto com seu dispositivo do HoloLens para conectar o dispositivo HoloLens ao computador. (Mesmo que você esteja usando outros cabos para conectar o dispositivo HoloLens, esse funciona melhor).
1. O WDRT detecta automaticamente seu dispositivo do HoloLens. Escolha o bloco **Microsoft HoloLens**.
1. Na tela seguinte, escolha **Seleção manual de pacote** e, em seguida, abra a pasta que você expandiu anteriormente.
1. Escolha o arquivo de instalação (.ffu).
1. Escolha **Instalar software** e siga as instruções.

**Se o WDRT não detectar o seu dispositivo**

Se o WDRT não detectar o seu dispositivo HoloLens, tente reiniciar o computador. Se isso não funcionar, escolha **Meu dispositivo não foi detectado**, **Microsoft HoloLens** e siga as instruções.

## <a name="related-articles"></a>Artigos relacionados

- [Notas sobre a versão do HoloLens 2](hololens-release-notes.md)
- [O que é o Windows Update para Empresas?](/windows/deployment/update/waas-manage-updates-wufb)
- [Atribuir dispositivos a canais de serviços para atualizações do Windows 10](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gerenciar atualizações de software do Windows 10 no Intune](/mem/intune/protect/windows-update-for-business-configure)
