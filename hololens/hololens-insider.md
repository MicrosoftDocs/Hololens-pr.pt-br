---
title: Versão prévia do Insider para Microsoft HoloLens
description: É fácil começar a usar as compilações do insider e fornecer comentários importantes para a nossa próxima atualização de sistema operacional para o HoloLens.
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
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 879ff13b30fdce77d823b66035cd59fa0e217c5f
ms.sourcegitcommit: 209247c83eff5cbabbbdecb8cf6e974eabcb36ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "10883363"
---
# Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às versões mais recentes do insider Preview para HoloLens!  É fácil começar e fornecer comentários importantes para a nossa próxima atualização de sistema operacional para o HoloLens.

O Windows Insider agora está migrando para canais. O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta**, e o anel de **versão de pré-lançamento** se tornará o canal de visualização de **lançamento**. Veja como é a aparência do mapeamento:

![Explicação de canais do Windows Insider](images/WindowsInsiderChannels.png)

Para obter mais informações: [entrada de blog do Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## Comece a receber Builds do insider

Em um dispositivo HoloLens 2, vá para **configurações**  ->  **Update &**  ->  programa de segurança do**Windows Insider** e selecione **introdução**. Vincule a conta que você usou para se registrar como um Windows Insider.

Em seguida, selecione **desenvolvimento ativo do Windows**, escolha se deseja receber o **canal de dev** ou versões de **canal beta** e examine os termos do programa.

Selecione **confirmar-> reiniciar agora** para concluir. Após a reinicialização do seu dispositivo, vá para **configurações-> atualização & segurança-> verificar** se há atualizações para obter a compilação mais recente.

## Parar de receber compilações do insider

Se você não quiser mais receber compilações do Insider do Windows holográfico, poderá cancelar quando o seu HoloLens está executando uma compilação de produção ou pode [recuperar seu dispositivo](hololens-recovery.md) usando o complemento avançado de recuperação para recuperar seu dispositivo para uma versão não Insider do Windows holográfico.

> [!CAUTION]
> Há um problema conhecido em que os usuários que não se inscrevem em compilações do insider Preview após a reinstalação manual de uma nova versão prévia teria uma tela azul. Depois disso, eles devem recuperar manualmente seus dispositivos. Para obter detalhes completos sobre se você for afetado ou não, veja mais sobre esse [problema conhecido](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Para verificar se o seu HoloLens está executando uma compilação de produção:

1. Vá para **configurações > > do sistema**e localize o número do Build.

1. [Consulte as notas de versão para números de Build de produção](hololens-release-notes.md).

Para recusar as compilações do insider:

1. Em um HoloLens executando uma compilação de produção, acesse **configurações > atualização & segurança > programa Windows Insider**e selecione **parar compilações**do Office Insider.

1. Siga as instruções para recusar seu dispositivo.


## Fornecer comentários e relatar problemas

Use [o aplicativo Hub de feedback](hololens-feedback.md) no seu HoloLens para fornecer comentários e relatar problemas. Usar o Hub de feedback garante que todas as informações de diagnóstico necessárias estejam incluídas para ajudar nossos engenheiros a depurar e solucionar o problema rapidamente.  Problemas com a versão em chinês e japonês do HoloLens devem ser reportados da mesma maneira.

> [!NOTE]
> Lembre-se de aceitar o prompt que pergunta se você deseja que o Hub de feedback acesse a pasta documentos (selecione **Sim** quando solicitado).

## Observação para desenvolvedores

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando as compilações do Insider do HoloLens.  Confira a [documentação do desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com compilações do Insider do HoloLens.  Você pode usar as mesmas versões do Unity e do Visual Studio que já está usando para o desenvolvimento do HoloLens.


## Notas da versão do Windows Insider

Se você estiver procurando um recurso que não está mais listado aqui, agora ele estará disponível em geral. Confira as [notas de versão](hololens-release-notes.md) para ver qual versão tem o (s) recurso (s) que você está empolgando. Certifique-se de [atualizar seu HoloLens](hololens-update-hololens.md) para obter todos os recursos mais recentes.

Atualizaremos esta página com novos recursos novamente, pois liberamos essas páginas para as compilações do Windows Insider.

| Recurso                               | Descrição                                                                                   | Disponível em builds do insider |
|---------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| Suporte à posição de olho automático             | Localiza ativamente posições de olho e habilita o posicionamento preciso do holograma.                       | 19041.1339 +                 |
| Acesso Global Atribuído                | Configure o dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos que se aplica ao nível do sistema.  | 19041.1346 +                 |
| Iniciar automaticamente um aplicativo no quiosque de vários aplicativos | Define um aplicativo para ser iniciado automaticamente ao entrar em um modo de quiosque de vários aplicativos. | 19041.1346 +                 |
| Novas políticas de energia para Hololens 2     | Políticas recém aceitas para configurações de tempo limite de energia.                                          | 19041.1349 +                 |
| Visualizador de certificados                    | Exiba certificados de usuário e de dispositivo no aplicativo configurações.                                        | 19041.1346 +                 |

### Suporte à posição de olho automático

No HoloLens 2, as posições de olho permitem o posicionamento preciso do holograma, a experiência de exibição confortável e a qualidade de exibição aprimorada. As posições de olho são calculadas como parte do resultado do controle de olho. No entanto, isso exige que cada usuário passe pela calibragem de rastreamento ocular, mesmo quando a experiência não requer entrada olhar olho.

A **posição de olho automático (AEP)** habilita esses cenários com uma maneira sem interação de calcular posições de olho para o usuário.  A posição de olho automático começa a trabalhar em segundo plano automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de rastreamento de olho anterior, a posição de olho automático começará a fornecer as posições de olho do usuário para o sistema de exibição após um pequeno período de processamento. Esse tempo de processamento geralmente está entre 20-60 segundos. Os dados do usuário não são mantidos no dispositivo e, portanto, esse processo é repetido se o usuário retomar e colocar o dispositivo novamente ou se o dispositivo for reinicializado ou ativado do modo de suspensão.  

Há algumas mudanças de comportamento do sistema com o recurso de posição de olho automático quando um usuário não calibrado coloca no dispositivo. Um usuário sem calibragem refere-se a alguém que não passou pelo processo de calibragem de rastreamento ocular no dispositivo anteriormente.

|     Aplicativo ativo                           |     Comportamento atual                                   |     Comportamento da compilação do Windows Insider 19041.1339 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     Aplicativo não compatível com olhar ou shell holográfico    |     Solicitação de calibragem de rastreamento ocular será exibida.    |     Nenhum aviso é exibido.                                                                                |
|     Aplicativo habilitado para olhar                             |     Solicitação de calibragem de rastreamento ocular será exibida.    |     O aviso de calibragem de rastreamento ocular é exibido apenas quando o aplicativo acessa o fluxo de olhar de olho.     |

 Se o usuário mudar de um aplicativo não olhar habilitado para um que acesse os dados do olhar, o prompt de calibragem será exibido. Não haverá nenhuma alteração para o fluxo de experiência inicial na caixa. 
 
Para experiências que exigem dados de olho olhar ou posicionamento muito preciso do holograma, recomendamos que os usuários não calibrados executem a calibragem de rastreamento ocular no prompt de calibragem de rastreamento ocular ou iniciem o aplicativo configurações no menu iniciar e, em seguida, selecione **sistema > Calibragem > Calibragem > executar calibragem de olho**.

**Problemas conhecidos**
 - Estamos investigando um problema em que o processo de host do driver do rastreador ocular pode falhar ao executar em carga de memória pesada. O processo de host do driver de controle ocular deve ser recuperado automaticamente.

### Acesso global atribuído – modo de quiosque
Este novo recurso permite que um administrador de ti configure um dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com qualquer identidade no sistema e se aplica a todos os participantes do dispositivo. Leia sobre esse novo recurso em detalhes [aqui](hololens-global-assigned-access-kiosk.md).

### Inicialização automática de um aplicativo no modo de quiosque de vários aplicativos 
Aplica-se somente ao modo de quiosque de vários aplicativos e somente um aplicativo pode ser designado para inicialização automática usando o atributo realçado abaixo na configuração de acesso atribuído. 

O aplicativo é iniciado automaticamente quando o usuário entra. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Novas políticas de energia para Hololens 2
Essas políticas adicionadas recentemente permitem que os administradores controlem os Estados de energia, como tempo limite ocioso. Para ler mais sobre cada política individual, clique no link para essa política.

|     Link de documentação da política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### Visualizador de certificados

No Windows Insider Build 19041.1346 + estamos adicionando um visualizador de certificados no aplicativo Configurações do HoloLens 2. Esse recurso oferece uma maneira simples e fácil de verificar certificados em seu dispositivo. Para localizar um certificado específico rapidamente, há opções para classificar por nome, loja ou data de expiração. Os usuários também podem procurar um certificado diretamente. Com o novo Visualizador de certificados, administradores e usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e compatíveis.  Para ver mais sobre um certificado individual, selecione o certificado e clique em informações.

> [!NOTE]
> Há uma limitação conhecida na localização de idioma diferente dos EUA na qual estamos trabalhando para resolver em versões subsequentes do Windows Insider.

-   **Auditoria:** Capacidade de validar se um certificado está implantado corretamente ou para confirmar se foi removido apropriadamente. 
-   **Diagnóstico:** Quando surgem problemas, é possível validar se os certificados apropriados existem no dispositivo poupa tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se o certificado atende à finalidade e é funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em uma escala maior.

Para exibir certificados, vá para **configurações > atualizar & segurança > certificados**.

![Visualizador de certificados no aplicativo configurações](images/hololens-certificate-viewer.png)

## FFU de download e trajetos do flash
Para testar com um FFU assinado no Flight, primeiro é preciso desbloquear o dispositivo antes de atualizar o FFU assinado no.
1. No PC:

    1. Faça o download do FFU para o seu PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) na Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. No HoloLens-bloqueio de voo: abrir **configurações**  >  **Atualizar & segurança**  >  **programa do Windows Insider** , em seguida, Inscreva-se, reinicie o dispositivo.

1. Flash FFU-agora você pode fazer o flash do FFU assinado por meio do ARC.
