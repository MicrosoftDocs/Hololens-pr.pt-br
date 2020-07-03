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
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3de48a913779f124c1cee21791af256a41bf45f8
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827542"
---
# Gerenciar atualizações do HoloLens

O HoloLens usa o Windows Update da mesma maneira que outros dispositivos do Windows 10. Quando uma atualização estiver disponível, ela será baixada e instalada automaticamente da próxima vez que o dispositivo estiver plugado e conectado à Internet. Este artigo descreve como gerenciar as atualizações em um ambiente corporativo ou outro ambiente gerenciado. Para obter informações sobre o gerenciamento de atualizações para dispositivos HoloLens individuais, confira [Atualizar HoloLens](hololens-update-hololens.md).

## Gerenciar atualizações automaticamente

O Windows Holographic for Business pode usar o [Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para gerenciar as atualizações. Todos os dispositivos do HoloLens 2 podem usar o Windows Holographic for Business. Certifique-se de que eles usem o Windows Holographic for Business Build 10.0.18362.1042 ou posterior. Se você tiver dispositivos HoloLens (1ª geração), você precisará [atualizá-los para o Windows Holographic for Business](hololens1-upgrade-enterprise.md) para gerenciar as atualizações.

O Windows Update para Empresas conecta dispositivos do HoloLens diretamente ao serviço do Windows Update. Usando o Windows Update para Empresas, você pode controlar vários aspectos do processo de atualização&mdash;ou seja, quais dispositivos recebem quais são as atualizações. Por exemplo, você pode distribuir as atualizações para um subconjunto de dispositivos para teste e, em seguida, distribuir as atualizações para os dispositivos restantes posteriormente. Ou você pode definir diferentes agendamentos de atualização para diferentes tipos de atualizações.

> [!NOTE]  
> Para dispositivos HoloLens, você pode gerenciar automaticamente as atualizações de recursos (lançadas duas vezes por ano) e atualizações de qualidade (lançadas mensalmente ou conforme necessário, incluindo atualizações de importantes de segurança). Para obter mais informações sobre os tipos de atualização, confira [Tipos de atualizações gerenciados pelo Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Você pode configurar o Windows Update para Empresas para o HoloLens usando políticas em uma solução de Gerenciamento de Dispositivo Móvel (MDM), como o Microsoft Intune.

Para obter mais informações sobre como usar o Intune para configurar o Windows Update para Empresas, confira [Gerenciar as atualizações de software do Windows 10 no Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).

> [!IMPORTANT]  
> O Intune fornece dois tipos de política para o gerenciamento de atualizações: *Anel de atualizações do Windows 10* e *Atualizações de recursos do Windows 10*. O tipo de política de atualização de recursos do Windows 10 está na visualização pública no momento e não tem suporte para o HoloLens.
>  
> Use as políticas de atualização do Windows 10 para gerenciar as atualizações do HoloLens 2.

### Configurar políticas de atualização para o HoloLens 2 ou para o HoloLens (1ª geração)

Esta seção descreve as políticas que você pode usar para gerenciar as atualizações do HoloLens 2 ou do HoloLens (1ª geração). Para saber mais sobre funcionalidades adicionais que estão disponíveis para o HoloLens 2, confira [Planejar e configurar as distribuições de atualização para o HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

O [Provedor de serviços de configuração de política (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) define as políticas que configuram o Windows Update para Empresas.

> [!NOTE]  
> Para obter detalhes sobre políticas específicas que têm suporte em edições específicas do HoloLens, confira [Políticas com suporte para dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).

#### Configurar verificações automáticas para atualizações

Você pode usar a política **Update/AllowAutoUpdate** para gerenciar o comportamento de atualização automática, como a verificação, o download e a instalação das atualizações.

Essa política suporta os seguintes valores:

- **0**- Notificar o usuário quando houver uma atualização pronta para download que se aplique ao dispositivo.
- **1**- Instalar automaticamente a atualização e, em seguida, notificar o usuário para agendar a reinicialização do dispositivo.  
- **2**- Instalar automaticamente a atualização e, em seguida, reiniciar o dispositivo. Esse é o valor recomendado e é o valor padrão para esta política.  

- **3**- Instalar automaticamente a atualização e, em seguida, reiniciar em uma hora específica. Especificar o dia e a hora da instalação. Se nenhum dia e hora forem especificados, o padrão é diariamente às 3h  

- **4**- Instalar automaticamente a atualização e, em seguida, reiniciar o dispositivo. Essa opção também define a página de configurações como somente leitura.

- **5**- Desativar as atualizações automáticas.

Para obter mais detalhes sobre as configurações disponíveis para essa política, confira [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> No Microsoft Intune, você pode usar o **Comportamento de Atualização Automática** para alterar essa política. Para obter mais informações, consulte [Gerenciar atualizações de software no Microsoft Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Configurar um cronograma de atualização

Para configurar como e quando as atualizações serão aplicadas, use as seguintes políticas:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).  
   - Valores: **0**–**7** (0 = todos os dias, 1 = domingo, 7 = sábado)
   - Valor padrão: **0** (todos os dias)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).
   - Valores: 0 – 23 (0 = meia-noite, 23 = 23:00)
   - Valor padrão: 15:00

#### Para dispositivos que executam o Windows 10, somente a versão 1607

Você pode usar as seguintes políticas de atualização para configurar os dispositivos para obter atualizações do Windows Server Update Services (WSUS), em vez do Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Planejar e configurar as atualizações de atualização do HoloLens 2

O HoloLens 2 oferece suporte a mais recursos de automação de atualização do que o HoloLens (1ª geração). isso será especialmente útil se você usar o Microsoft Intune para gerenciar a política do Windows Update para Empresas. Esses recursos facilitam o planejamento e a implementação de distribuições de atualização em toda a organização.

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

####  Exemplos: usar o Intune para gerenciar atualizações

**Exemplo 1: criar e atribuir um anel de atualização**

Para obter uma versão mais detalhada deste exemplo, confira [criar e atribuir anéis de atualização](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

1. Entre no [Centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)e navegue até seus perfis do Intune.
1. Selecione **Atualizações de Software** > ** Anéis de atualização do Windows 10** > **Criar**.
1. Em **Básicos**, especifique um nome e uma descrição (opcional) e, em seguida, selecione **Próximo**.
1. Em **Configurações de anel de atualização**, para **Canal de manutenção**, selecione **Canal Semestral**e, em seguida, altere **Período de adiamento de atualização de recursos** para **120**. Em seguida, selecione **Próximo**.
1. Em **Atribuições**, selecione **+ Selecionar grupos para incluir**e atribua o anel de atualização a um ou mais grupos. Use **+ Selecionar grupos para excluir** para ajustar as tarefas. Em seguida, selecione **Próximo**.
1. Em **Revisar + criar**, revise as configurações. Quando estiver pronto para salvar a configuração do anel de atualização, selecione **Criar**.

A lista de chamadas de atualização agora inclui o novo anel de atualização do Windows 10.

**Exemplo 2: pausar um anel de atualização**

Se encontrar um problema ao implantar um recurso ou uma atualização de qualidade, você pode pausar a atualização por 35 dias (a partir de uma data especificada). Essa pausa impede que outros dispositivos instalem a atualização até que você resolva ou atenue o problema. Se você pausar uma atualização de recursos, as atualizações de qualidade ainda serão oferecidas aos dispositivos para garantir que eles permaneçam seguros. Após o término do período de tempo especificado, a pausa automaticamente expirará. Neste ponto, o processo de atualização é retomado.

Para pausar um anel de atualização no Intune, siga estas etapas:

1. Na página de visão geral do anel de atualização, marque **Pausar**.
1. Selecione o tipo de atualização (**Recurso** ou **Qualidade**) para pausar e, em seguida, selecione **OK**.

Quando um tipo de atualização é pausado, o painel Visão geral exibe quantos dias restam para que o tipo de atualização seja retomado.

Enquanto o anel de atualização estiver pausado, você poderá selecionar uma das opções a seguir:

- Para estender o período de pausa de um tipo de atualização por 35 dias, selecione **Estender**.
- Para restaurar as atualizações para esse anel para a operação ativa, selecione **Retomar**. Você pode pausar o anel de atualização novamente se necessário.

> [!NOTE]  
> Não há suporte para a operação **Desinstalar** anéis de atualização em dispositivos HoloLens 2.

## Verificar atualizações manualmente

Embora o HoloLens verifique periodicamente se há atualizações do sistema para que você não precise fazer isso, pode haver circunstâncias em que você deseje verificar manualmente.

Para verificar manualmente se há atualizações, vá para **Configurações** > **Atualização & segurança** > **Verificar se há atualizações**. Se o aplicativo Configurações indicar que seu dispositivo está atualizado, você tem todas as atualizações que estão disponíveis no momento.

## Reverter uma atualização manualmente

Em alguns casos, talvez você queira voltar a uma versão anterior do software do HoloLens. O processo para fazer isso depende se você estiver usando o HoloLens 2 ou o HoloLens (1ª geração).

### Voltar para a versão anterior (HoloLens 2)

Você pode reverter as atualizações e retornar a uma versão anterior do HoloLens 2 usando o Advanced Recovery Companion para retornar seu HoloLens para a versão anterior.

> [!NOTE]
> A reversão para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens 2, siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.
1. No computador, baixe o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) na Microsoft Store.
1. Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).
1. Quando tiver terminado esses downloads, abra o **Explorador de Arquivos** > **Downloads**, clique com o botão direito do mouse na pasta compactada (zipada) que você acabou de baixar e, em seguida, selecione **Extrair todos** > **Extrair** para expandir o arquivo.
1. Use um cabo USB-A para USB-C para conectar o dispositivo do HoloLens ao computador. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse tipo de cabo funciona melhor).
1. O Advanced Recovery Companion detecta automaticamente seu dispositivo do HoloLens. Selecione o bloco **Microsoft HoloLens**.
1. Na tela seguinte, marque a **Seleção de pacote manual** e, em seguida, abra a pasta que você expandiu anteriormente. 
1. Selecione o arquivo de instalação (o arquivo com uma extensão .ffu).
1. Selecione**Instalar software** e siga as instruções.

### Voltar para a versão anterior (HoloLens (1ª geração))

Você pode reverter as atualizações e retornar a uma versão anterior do HoloLens (1ª geração) usando a Windows Device Recovery Tool para retornar o HoloLens para a versão anterior.

> [!NOTE]
> A reversão para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens (1ª geração), siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.
1. No computador, baixe a [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Baixe o [Pacote de recuperação de Atualização de Aniversário do HoloLens](https://aka.ms/hololensrecovery).
1. Após concluir os downloads, abra **Explorador de arquivos** > **Downloads**, clique com o botão direito do mouse na pasta compactada (zipada) que você acabou de baixar e, em seguida, selecione **Extrair tudo** > **Extrair** para expandir o arquivo.
1. Use o cabo micro-USB fornecido em conjunto com seu dispositivo do HoloLens para conectar o dispositivo HoloLens ao computador. (Mesmo que você esteja usando outros cabos para conectar o dispositivo HoloLens, esse funciona melhor).
1. O WDRT detecta automaticamente seu dispositivo do HoloLens. Selecione o bloco **Microsoft HoloLens**.
1. Na tela seguinte, marque a **Seleção de pacote manual** e, em seguida, abra a pasta que você expandiu anteriormente. 
1. Selecione o arquivo de instalação (o arquivo com uma extensão .ffu).
1. Selecione**Instalar software** e siga as instruções.

> [!NOTE]
> Se o WDRT não detectar o seu dispositivo HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **Meu dispositivo não foi detectado**, selecione **Microsoft HoloLens** e siga as instruções.

## Artigos relacionados

- [Implantar atualizações usando o Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Atribuir dispositivos a canais de serviços para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Gerenciar as atualizações de software do Windows 10 no Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
