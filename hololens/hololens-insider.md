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
ms.openlocfilehash: 0ca085cfcf96a07b5c022b308a513c895795e945
ms.sourcegitcommit: 81ea187bfd244fb8f489cd8b37c0cc7f6a8bc1cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926596"
---
# Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às versões mais recentes do insider Preview para HoloLens!  É fácil começar e fornecer comentários importantes para a nossa próxima atualização de sistema operacional para o HoloLens.

O Windows Insider agora está migrando para canais. O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta**, e o anel de **versão de pré-lançamento** se tornará o canal de visualização de **lançamento**. Veja como é a aparência do mapeamento:

![Explicação de canais do Windows Insider](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [apresentando os canais do Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos Blogs do Windows.

## Notas da versão do Windows Insider

Se você estiver procurando um recurso que não está mais listado aqui, agora ele estará disponível em geral. Confira as [notas de versão](hololens-release-notes.md) para ver qual versão tem o (s) recurso (s) que você está empolgando. Certifique-se de [atualizar seu HoloLens](hololens-update-hololens.md) para obter todos os recursos mais recentes.

Atualizaremos esta página com novos recursos novamente, pois liberamos essas páginas para as compilações do Windows Insider.

| Recurso                                              | Descrição                                                                                   | Disponível em builds do insider |
|------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| Suporte à posição de olho automático                            | Localiza ativamente posições de olho e habilita o posicionamento preciso do holograma.                       | 19041.1339 +                 |
| Visualizador de certificados                                   | Exiba certificados de usuário e de dispositivo no aplicativo configurações.                                        | 19041.1346 +                 |
| Conexão Wi-Fi e usando o AutoPilot                 | Use o AutoPilot do dispositivo Wi-Fi sem necessidade de adaptador Ethernet.                            | 19041.1364 +                 |
| Políticas do HoloLens                                    | Novas políticas para dispositivos de realidade misturados.                                                       | 19041.1349 +                 |
| Armazenar Associação de grupo no AAD para quiosque offline         | Política de quantos dias o cache de associação do grupo AAD pode ser usado para o modo de quiosque.     | 19041.1356 +                 |
| Novas políticas de restrição de dispositivo para HoloLens 2       | Políticas de gerenciamento de dispositivos habilitadas recentemente para o HoloLens 2.                              | 19041.1349 +                 |
| Novas políticas de energia para HoloLens 2                    | Políticas recém aceitas para configurações de tempo limite de energia.                                          | 19041.1349 +                 |
| Atualizar políticas                                      | Políticas habilitadas recentemente, permitindo o controle de atualizações.                                           | 19041.1352 +                 |
| Visibilidade da página Configurações habilitada para o HoloLens 2      | Política para escolher quais páginas são vistas no aplicativo configurações.                                          | 19041.1349 +                 |
| Acesso Global Atribuído                               | Configure o dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos que se aplica ao nível do sistema.  | 19041.1356 +                 |
| Iniciar automaticamente um aplicativo no quiosque de vários aplicativos                | Define um aplicativo para ser iniciado automaticamente ao entrar em um modo de quiosque de vários aplicativos. | 19041.1346 +                 |
| Alterações de comportamento do modo de quiosque para manipulação de falhas | Alterações de como a falha do modo de quiosque agora é manipulada.                                             | 19041.1356 +                 |

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

### Visualizador de certificados

No Windows Insider Build 19041.1346 + estamos adicionando um visualizador de certificados no aplicativo Configurações do HoloLens 2. Esse recurso oferece uma maneira simples e fácil de verificar certificados em seu dispositivo. Para localizar um certificado específico rapidamente, há opções para classificar por nome, loja ou data de expiração. Os usuários também podem procurar um certificado diretamente. Com o novo Visualizador de certificados, administradores e usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e compatíveis.  Para ver mais sobre um certificado individual, selecione o certificado e clique em informações.

> [!NOTE]
> Há uma limitação conhecida na localização de idioma diferente dos EUA na qual estamos trabalhando para resolver em versões subsequentes do Windows Insider.

-   **Auditoria:** Capacidade de validar se um certificado está implantado corretamente ou para confirmar se foi removido apropriadamente. 
-   **Diagnóstico:** Quando surgem problemas, é possível validar se os certificados apropriados existem no dispositivo poupa tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se o certificado atende à finalidade e é funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em uma escala maior.

Para exibir certificados, vá para **configurações > atualizar & segurança > certificados**.

![Visualizador de certificados no aplicativo configurações](images/hololens-certificate-viewer.png)

### Conexão Wi-Fi e usando o AutoPilot
Agora, durante o OOBE, quando você conectar o HoloLens 2 com WiFi, o OOBE verificará se há um perfil do AutoPilot para o dispositivo. Se um for encontrado, ele será usado para concluir o restante do fluxo do AAD e do fluxo de registro. Em outras palavras, usar Ethernet para USB C ou WiFi para adaptador USB C não é mais necessário, mas continuará a funcionar se fornecido no início do OOBE. Saiba mais sobre o [AutoPilot para dispositivos HoloLens 2](hololens2-autopilot.md).

### Políticas do HoloLens
Novas políticas de realidade mista foram criadas para dispositivos do HoloLens 2 nos Builds 19041.1349 +. As novas configurações controláveis incluem: configuração do brilho, configuração do volume, desativação da gravação de áudio em capturas de realidade mista, configuração quando o diagnóstico pode ser coletado e o cache de associação do grupo AAD.  

| Nova política do HoloLens                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados para que o pressionamento não altere o brilho.       | 1 Sim, 0 não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que os botões de volume sejam desabilitados, portanto, ao pressioná-lo, não muda o volume.               | 1 Sim, 0 não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | Desabilita o microfone para que a gravação de áudio seja possível no HoloLens 2.                      | 1 Sim, 0 não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os logs de diagnóstico podem ser coletados.                               | 0 desativado, 1 habilitado para proprietários de dispositivo, 2 habilitado para todos (padrão) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla quantos dias o cache de associação do grupo AAD é usado para grupos do AAD de direcionamento do quiosque. | Veja abaixo.                                                           |

### Armazenar Associação de grupo no AAD para quiosque offline

Esta política controla o número de dias, o cache de associações do grupo AAD pode ser usado para configurações de acesso atribuídas direcionando grupos do AAD para o usuário conectado. Quando esse valor de política é definido como valor maior que 0 somente, o cache é usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays URI value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín-0 dias  
Máx-60 dias 

Etapas para usar esta política corretamente: 
1. Crie um perfil de configuração de dispositivo para grupos do AAD de direcionamento de quiosque e atribua-o a dispositivo (s) HoloLens (s). 
1. Crie uma configuração de dispositivo baseada em OMA URI, que define esse valor de política como o número desejado de dias (> 0) e atribua-o a dispositivo (s) do HoloLens. 
    1. O valor de URI deve ser inserido na caixa de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre min/max permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Deixe que o usuário do AAD 1 entre quando a Internet estiver disponível, quando o usuário entrar e a associação do grupo AAD for confirmada com êxito, o cache será criado. 
1. Agora o usuário do AAD 1 pode pegar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do AAD. o ponto da chave aqui é que qualquer usuário do AAD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que ele é membro do grupo AAD para o qual a configuração do quiosque está direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja realizada para um usuário do AAD experimentará um comportamento de falha mencionado abaixo em ambientes "desconectados". 

### Novas políticas de restrição de dispositivo para HoloLens 2
Políticas habilitadas recentemente que permitem mais opções de gerenciamento de dispositivos do HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone) 

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

### Políticas de atualização habilitadas recentemente para HoloLens
Essas políticas de atualização agora estão habilitadas em dispositivos HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### Visibilidade da página Configurações habilitada para o HoloLens 2
Agora habilitamos uma política que permite que os administradores de ti impeçam que páginas específicas no aplicativo Configurações do sistema sejam visíveis ou acessíveis, ou que façam isso para todas as páginas, exceto aquelas especificadas. Para saber como personalizar completamente este recurso, clique no link abaixo.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![Captura de tela de horas ativas sendo modificadas no aplicativo configurações](images/hololens-page-visibility-list.jpg)

### Acesso global atribuído – modo de quiosque
Este novo recurso permite que um administrador de ti configure um dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com qualquer identidade no sistema e se aplica a todos os participantes do dispositivo. Leia sobre esse novo recurso em detalhes [aqui](hololens-global-assigned-access-kiosk.md).

### Inicialização automática de um aplicativo no modo de quiosque de vários aplicativos 
Aplica-se somente ao modo de quiosque de vários aplicativos e somente um aplicativo pode ser designado para inicialização automática usando o atributo realçado abaixo na configuração de acesso atribuído. 

O aplicativo é iniciado automaticamente quando o usuário entra. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Alterações de comportamento do modo de quiosque para manipulação de falhas

Antes de encontrar falhas na aplicação do modo de quiosque, o HoloLens é usado para exibir todos os aplicativos no menu iniciar. A partir desta compilação do Windows Insider, no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, conforme mostrado abaixo: 

![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

## Comece a receber Builds do insider

> [!NOTE]
> Se você não atualizou recentemente, reinicialize o seu dispositivo para atualizar o estado e obtenha a compilação mais recente.
> - O comando de voz "reinicializar dispositivo" funciona bem. 
> - Você também pode escolher o botão de reinicialização no programa configurações/Windows Insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso permitirá que você se retorne ao caminho.

Em um dispositivo HoloLens 2, vá para **configurações**  >  **Update &**  >  programa de segurança do**Windows Insider** e selecione **introdução**. Vincule a conta que você usou para se registrar como um Windows Insider.

Em seguida, selecione **desenvolvimento ativo do Windows**, escolha se deseja receber o **canal de dev** ou versões de **canal beta** e examine os termos do programa.

Selecione **confirmar > reiniciar agora** para concluir. Após a reinicialização do seu dispositivo, vá para **configurações > atualização & segurança > verificar se há atualizações** para obter a compilação mais recente.

## FFU de download e trajetos do flash
Para testar com um FFU assinado no Flight, primeiro é preciso desbloquear o dispositivo antes de atualizar o FFU assinado no.
1. No PC:

    1. Faça o download do FFU para o seu PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) na Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. No HoloLens-bloqueio de voo: abrir **configurações**  >  **Atualizar & segurança**  >  **programa do Windows Insider** , em seguida, Inscreva-se, reinicie o dispositivo.

1. Flash FFU-agora você pode fazer o flash do FFU assinado por meio do ARC.

## Fornecer comentários e relatar problemas

Use [o aplicativo Hub de feedback](hololens-feedback.md) no seu HoloLens para fornecer comentários e relatar problemas. Usar o Hub de feedback garante que todas as informações de diagnóstico necessárias estejam incluídas para ajudar nossos engenheiros a depurar e solucionar o problema rapidamente.  Problemas com a versão em chinês e japonês do HoloLens devem ser reportados da mesma maneira.

> [!NOTE]
> Lembre-se de aceitar o prompt que pergunta se você deseja que o Hub de feedback acesse a pasta documentos (selecione **Sim** quando solicitado).

## Observação para desenvolvedores

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando as compilações do Insider do HoloLens.  Confira a [documentação do desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com compilações do Insider do HoloLens.  Você pode usar as mesmas versões do Unity e do Visual Studio que já está usando para o desenvolvimento do HoloLens.

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
