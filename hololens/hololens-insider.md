---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar o Insider compilações e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 68485fd0ad7f050748a412da3d57eb8f59e9a685
ms.sourcegitcommit: d09556a101663ef5dfff865d4753e64a41032b78
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "128346737"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às compilações mais recentes do insider Preview para HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de versão do insider

estamos empolgados para começar a comprovar novos recursos para Windows insiders novamente. Novas compilações serão comprovadas para os canais de desenvolvimento e beta para as atualizações mais recentes. continuaremos a atualizar esta página à medida que adicionamos mais recursos e atualizações às nossas compilações do Windows insider. Fique empolgado e pronto para misturar essas atualizações em sua realidade.

Este é o respeito dos relatórios aprimorados de solução de problemas e de dispositivo, alguns bugs fixos no modo de quiosque e o Visualizador de certificado, a superfície de gerenciabilidade expandida e a maior confiabilidade de atualização. um novo recurso principal desta atualização de recurso em HoloLens é nosso modo de plataforma móvel. confira todos os novos recursos incríveis para HoloLens 2!

| Recurso                 | Descrição                | Usuário ou cenário | Compilação introduzida |
|-------------------------|----------------------------|--------------|------------------|
| [Modo de plataforma móvel](#moving-platform-mode) | o apresenta a versão beta do modo de plataforma em movimento, que, quando configurada, permite o uso de HoloLens 2 em grandes embarcações de náuticos com baixa interrupções. | Tudo | 20348,1411 |
| [Suporte a arquivos PFX para o Gerenciador de certificados](#pfx-file-support-for-certificate-manager) | adicionar certificados PFX por meio da interface do usuário do Configurações | Usuário Final | 20348,1405 |
| [exibir relatório de diagnóstico avançado no Configurações no HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Exibir logs de diagnóstico do MDM no dispositivo | Solução de problemas | 20348,1405 |
| [Notificações de diagnóstico offline](#offline-diagnostics-notifications) | Audiovisual comentários para coleta de log | Solução de problemas | 20348,1405 |
| [Melhorias de coleta de log de armazenamento baixo](#low-storage-log-collection-improvements) | Melhorias em cenários de coleta de log durante situações de armazenamento baixo. | Solução de problemas | 20348,1412 |
| [alterações do CSP para relatórios HoloLens detalhes](#csp-changes-for-reporting-hololens-details) | Novos CSPs para a consulta de dados | Administradores de ti    | 20348,1403                 |
| [Política de logon automático controlada pelo CSP](#auto-login-policy-controlled-by-csp) | Usado para fazer logon em uma conta automaticamente | Administradores de ti | 20348,1405 |
| [Detecção e notificações de reinício de atualização aprimoradas](#improved-update-restart-detection-and-notifications) | Novas políticas habilitadas e UX para atualizações. | Administradores de ti | 20348,1405 |
| [Repetição inteligente para atualizações de aplicativo](#smart-retry-for-app-updates) | Permite aos administradores de ti agendarem tentativas para atualizar aplicativos novamente. | Administradores de ti | 20348,1405 |
| [Usar somente aplicativos de repositório privado somente para Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurar o aplicativo da loja para mostrar somente os aplicativos da organização | Administrador de TI | 20348,1408 |
| [Usar aplicativos WDAC e LOB](#use-wdac-and-lob-apps) | Permite que os administradores de ti usem seus próprios aplicativos e ainda usem o WDAC para bloquear outros aplicativos. | Administradores de ti | 20348,1405 |
| [Correções e aprimoramentos](#fixes-and-improvements) | Correções e aprimoramentos para HoloLens. | Tudo | 20348,1411 |

### <a name="it-admin-insider-feature-checklist"></a>Lista de verificação de recursos do IT Admin Insider

✔️ Se você quiser definir uma única conta do Azure AD para fazer logon automaticamente, [Configure esse novo CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Se você quiser configurar seus aplicativos para tentarem atualizar automaticamente após a falha de atualização, [defina esse novo CSP para repetição inteligente.](#smart-retry-for-app-updates) <br>
✔️ Se você quiser ter mais controle sobre as atualizações do sistema operacional, Confira essas [políticas de atualização habilitadas recentemente](#improved-update-restart-detection-and-notifications). <br>
✔️ se você precisar tornar os aplicativos da sua organização disponíveis na loja da empresa por meio do Microsoft Store, mas deseja permitir o acesso somente aos aplicativos da sua organização e não ao armazenamento completo, [defina essa política](#use-only-private-store-apps-for-microsoft-store). <br>
✔️ se você quiser saber o espaço de armazenamento livre, o SSID ou o BSSID de seus dispositivos HoloLens confira esses [CSPs de relatório](#csp-changes-for-reporting-hololens-details). <br>
✔️ Se você quiser usar o WDAC para bloquear a inicialização de aplicativos ou processos, mas também precisar usar sua própria linha de aplicativos bushiness, agora você pode [permitir o LOB em sua política WDAC](#use-wdac-and-lob-apps).

### <a name="moving-platform-mode"></a>Modo de plataforma móvel

a partir do **build insider 20348,1411** , adicionamos suporte beta para acompanhamento de plataformas de movimentação de movimentos dinâmicos no HoloLens 2. depois de instalar a compilação e habilitar o modo de movimentação de plataforma, você poderá usar seu HoloLens 2 em ambientes anteriormente inacessíveis, como grandes lançamentos e embarcações náuticoss grandes. Atualmente, o recurso tem como alvo habilitar apenas essas plataformas móveis específicas. Embora nada impeça você de tentar usar o recurso em outros ambientes, ele se concentra em adicionar suporte a esses ambientes primeiro.

Para saber mais sobre o que é suportado e como habilitar esse novo recurso, [visite a página de plataforma móvel](hololens2-moving-platform.md).

#### <a name="overview-to-try-out-moving-platform-mode"></a>Visão geral para experimentar a movimentação do modo de plataforma

1. [Habilite o modo de desenvolvedor e o portal do dispositivo](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. [Habilite a movimentação do modo de plataforma por meio do portal do dispositivo](hololens2-moving-platform.md#enabling-moving-platform-mode).
1. Leve seu dispositivo para sua plataforma de movimentação grande e observe como os hologramas são estáveis.

### <a name="pfx-file-support-for-certificate-manager"></a>Suporte a arquivos PFX para o Gerenciador de certificados

introduzido no Windows insider build 20348,1405. Adicionamos suporte ao Gerenciador de [certificados](certificate-manager.md) para agora usar certificados. pfx. quando os usuários navegam para **Configurações**  >  **atualização &**  >  **certificados** de segurança e selecionam **instalar um certificado** , a interface do usuário agora dá suporte ao arquivo de certificado. pfx.
Os usuários podem importar o certificado. pfx, com a chave privada, para o repositório de usuários ou para o repositório de computadores.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Visão geral para experimentar arquivos PFX no Gerenciador de certificados

1. Prepare o arquivo PFX.
1. Copie o arquivo para o dispositivo por meio de um cabo USB-C.
1. abra o aplicativo Configurações e navegue até o [gerenciador de certificados](certificate-manager.md) e aplique o certificado.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>exibir relatório de diagnóstico avançado no Configurações no HoloLens

Para dispositivos gerenciados ao solucionar problemas de comportamento, a confirmação de que uma configuração de política esperada é aplicada é uma etapa importante. anteriormente para esse novo recurso, a exibição dessas informações teve que ser feita fora do dispositivo por meio do MDM ou perto do dispositivo depois de exportar os logs de diagnóstico do mdm coletados por meio de **Configurações**  ->  **contas**  >  **acessarem trabalho ou escola** e selecione **exportar os logs de gerenciamento** e exibidos em um PC próximo.

Agora, o diagnóstico de MDM pode ser exibido no dispositivo usando o navegador Edge. Para exibir mais facilmente o relatório de diagnóstico do MDM, navegue até a página acessar o trabalho ou a escola e selecione **Exibir relatório de diagnóstico avançado**. Isso irá gerar e abrir o relatório em uma nova janela de borda.

![exiba o relatório de diagnóstico avançado no aplicativo Configurações.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Visão geral para experimentar o relatório de diagnóstico avançado

1. Abra o aplicativo Configurações.
1. Navegue até a página Contas e clique no novo link **Exportar seus logs de gerenciamento.**
1. Exibir informações avançadas sobre as configurações do dispositivo.

### <a name="offline-diagnostics-notifications"></a>Notificações de diagnóstico offline

Esta é uma atualização para um recurso existente chamado [Diagnóstico Offline.](hololens-diagnostic-logs.md#offline-diagnostics) Anteriormente, não havia nenhum indicador claro para os usuários de que eles dispararam a coleta de diagnóstico ou que ela havia sido concluída.
Agora adicionados Windows builds do Insider, há duas formas de comentários audiovisuais para o Diagnóstico Offline. O primeiro que está sendo notificação é exibido para quando a coleta é iniciada e concluída. Eles serão exibidos quando o usuário estiver conectado e tiver visuais.

![Sistema para coletar logs.](./images/logcollection1.jpg)

![Toast quando a coleta de log for concluída.](./images/logcollection2.jpg)

Como os usuários geralmente usam o Diagnóstico Offline como um mecanismo de coleta de logs de fallback para quando não têm acesso a uma exibição, não é possível fazer logoff ou ainda estão no OOBE, também haverá uma indicação de áudio tocada quando os logs são coletados. Esse som será tocado além da notificação do sistema.

Esse novo recurso será habilitado quando o dispositivo for atualizado e não precisará ser habilitado ou gerenciado. Em qualquer caso em que esse novo comentário não possa ser exibido ou ouvido, o Diagnóstico Offline ainda será gerado.

Esperamos que com essa adição mais nova de comentários audiovisuais seja mais fácil coletar dados de diagnóstico e, mais rapidamente, ser capaz de solucionar seus problemas.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Visão geral para experimentar as notificações de diagnóstico

1. Desbloqueie seu dispositivo e use-o.
1. Pressione a **combinação de** botões **Ligar e Volume down** para coletar o [Diagnóstico Offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Exibir as notificações do sistema e ouvir sinais de áudio para quando o dispositivo é iniciado e termina a coleta de logs.

### <a name="low-storage-log-collection-improvements"></a>Aprimoramentos de coleta de log de armazenamento baixo

Em cenários em que um dispositivo parece estar com pouco espaço em disco quando os logs de diagnóstico são coletados, um relatório adicional chamadoStorageDiagnostics.zip **será** criado. O limite de armazenamento baixo é determinado automaticamente pelo Windows [de armazenamento.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Visão geral para experimentar as melhorias de armazenamento baixas

1. Preencha o espaço de armazenamento do dispositivo.
1. Pressione a **combinação de** botões **Ligar e Volume down** para coletar o [Diagnóstico Offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Observe que há um novo arquivo na coleção de logs armazenados na pasta Documentos do seu HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>Alterações do CSP para relatórios HoloLens detalhes

- Introduzido no Windows Insider Build, 20348.1403

Os CSPs a seguir foram atualizados com novas maneiras de relatar informações de seus HoloLens dispositivos.

#### <a name="devdetail-csp---free-storage"></a>CSP de DevDetail – Armazenamento

O CSP de DevDetail agora também relata espaço de armazenamento livre HoloLens dispositivo. Isso deve corresponder aproximadamente ao valor mostrado na página Configurações aplicativo Armazenamento aplicativo. A seguir está o nó específico que contém essas informações.

- ./DevDetail/Ext/Microsoft/FreeStorage (somente operação GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>CSP do DeviceStatus – SSID e BSSID

O CSP do DeviceStatus agora também relata SSID e BSSID Wi-Fi rede com a qual HoloLens está ativamente conectado. A seguir estão os nós específicos que contêm essas informações.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac address *of Wi-Fi adapter*/BSSID

Exemplo de blob syncml (para fornecedores de MDM) para consultar NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Política de logon automático controlada pelo CSP

Essa nova política AutoLogonUser controla se um usuário será conectado automaticamente. Alguns clientes querem configurar dispositivos que estão vinculados a uma identidade, mas não querem nenhuma experiência de entrada. Imagine pegar um dispositivo e usar a assistência remota imediatamente. Ou ter um benefício de poder distribuir rapidamente HoloLens dispositivos e permitir que os usuários finais agilizarem o logon.

Quando a política é definida como um valor não vazio, ela especifica o endereço de email do usuário de logon automático. O usuário especificado deve fazer logon no dispositivo pelo menos uma vez para habilitar o logon automático.

O OMA-URI do novo valor de cadeia `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` de caracteres de política

- O usuário com o mesmo endereço de email terá o logon automático habilitado.

Em um dispositivo em que essa política está configurada, o usuário especificado na política precisará fazer logon pelo menos uma vez. As reinicializações subsequentes do dispositivo após o primeiro logon terão o usuário especificado conectado automaticamente. Há suporte apenas para um único usuário de logon automático. Depois de habilitado, o usuário conectado automaticamente não poderá fazer logoff manualmente. Para fazer logon como um usuário diferente, a política deve primeiro ser desabilitada.

> [!NOTE]
>
> - Alguns eventos, como as principais atualizações do sistema operacional, podem exigir que o usuário especificado entre no dispositivo novamente para retomar o comportamento de logon automático.
> - O logon automático só tem suporte para usuários do MSA e do AAD.

#### <a name="overview-to-try-auto-logon-csp"></a>Visão geral para experimentar o CSP de logon automático

1. Configure o novo CSP para um usuário desejado [usando uma política personalizada:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Aplique o CSP ao dispositivo por meio [do pacote de provisionamento ou](hololens-provisioning.md) do [MDM.](hololens-mdm-configure.md)
1. Entre na conta especificada.
1. Reinicie o dispositivo e observe que o usuário está conectado automaticamente.

### <a name="improved-update-restart-detection-and-notifications"></a>Detecção e notificações de reinicialização de atualização aprimoradas

Entre as horas ativas e as políticas de tempo de instalação, é possível evitar a reinicialização HoloLens dispositivos quando eles estão em uso. No entanto, isso também atrasaria a adoção de atualizações se as reinicializações não ocorrem para concluir a instalação de uma atualização necessária. Agora adicionamos políticas para permitir que a IT imigr prazos e reinicializações necessárias e garantir que a instalação de uma atualização seja concluída em tempo hábil. Os usuários podem ser notificados antes da reinicialização ser iniciada e podem atrasar a reinicialização de acordo com a política de IT.

As seguintes políticas de atualização foram adicionadas:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>Visão geral para experimentar novas notificações de atualização

1. Configure um dos novos CSPs de atualização por [meio do pacote de provisionamento](hololens-provisioning.md) ou do [MDM](hololens-mdm-configure.md) (consulte a lista de links acima e escolha um).
1. Use o dispositivo durante o horário agendado.
1. Observe que o usuário é notificado sobre a atualização e a necessidade de reiniciar o \* dispositivo.

\* Os resultados podem variar com base nas políticas de atualização usadas.

### <a name="smart-retry-for-app-updates"></a>Smart Retry para atualizações de aplicativo

Agora habilitada para HoloLens é uma nova política que permite aos administradores de IT definir uma data recorrente ou uma vez para reiniciar aplicativos cuja atualização falhou porque o aplicativo está sendo usado, permitindo que a atualização seja aplicada. Eles podem ser definidos com base em alguns gatilhos diferentes, como uma hora agendada ou uma login. Para saber mais sobre como usar essa exibição de política [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Visão geral para experimentar o Smart Retry para atualizações de aplicativo

1. Configure o novo recurso de nova tentativa inteligente.
1. Em um dispositivo que ainda não recebeu seu aplicativo e está configurado corretamente, faça logoff em um ambiente online.
1. Torne o dispositivo incapaz de baixar o aplicativo por meio de desconectá-lo ou desconectá-lo.
1. Faça com que seu dispositivo esteja ligado e conectado à Internet durante o tempo disparado para repetir o download.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar somente aplicativos da loja privada para Microsoft Store

A política RequirePrivateStoreOnly foi habilitada para HoloLens. Essa política permite que o Microsoft Store aplicativo seja configurado para mostrar apenas o armazenamento privado configurado para sua organização por meio [Microsoft Store para Empresas](/microsoft-store/microsoft-store-for-business-overview). Limitando o acesso somente aos aplicativos que você disponibiliza.

Saiba mais sobre [ApplicationManagement/RequirePrivateStoreOnly.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

#### <a name="overview-to-try-only-private-store-apps"></a>Visão geral para experimentar apenas aplicativos da loja privada

1. Configure a nova política para seus dispositivos por meio [do MDM](hololens-mdm-configure.md).
1. Faça logoff em um dispositivo que tenha a política.
1. Abra o Microsoft Store aplicativo e observe que você só pode ver os aplicativos da sua organização.

### <a name="use-wdac-and-lob-apps"></a>Usar aplicativos WDAC e LOB

Agora você pode usar o WDAC para impedir que aplicativos ou processos sejam iniciados e continuem a usar sua própria linha de aplicativos bushiness. Agora você pode permiti-los em sua política WDAC. O uso dessa política envolve a execução de uma linha extra de código no PowerShell ao criar sua política WDAC. [Examine as etapas aqui](/mem/intune/configuration/custom-profile-hololens).

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Visão geral para experimentar seus próprios aplicativos ao usar o WDAC para bloquear outros

1. Reúna o AUMIDs de seu aplicativo LOB e os aplicativos que você pretende bloquear.
1. [Crie uma nova política WDAC](/mem/intune/configuration/custom-profile-hololens) seguindo as novas etapas.
1. [Implante a política usando o MDM](hololens-mdm-configure.md) em seu dispositivo.
1. Entre no dispositivo e observe que você pode iniciar seu aplicativo e bloquear outros.

### <a name="fixes-and-improvements"></a>Correções e aprimoramentos

#### <a name="for-developers"></a>Para desenvolvedores

- Correção de um [problema conhecido para o portal do dispositivo em que não havia prompt para baixar arquivos bloqueados](hololens-troubleshooting.md#downloading-locked-files-doesnt-error).
- Correção de um [problema conhecido para o portal do dispositivo com tempo limite de upload e download de arquivos](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out).
- O processamento de gamepad para aplicativos 2D foi desabilitado em compilações internas. Ao removê-lo, os aplicativos agora estão livres para usar as APIs do gamepad diretamente e ter acesso a todo o conjunto de controles e podem ser desenvolvidos em mente para fazer mais. Os desenvolvedores devem usar as APIs do gamepad para consumir a entrada do gamepad. Aqui está um exemplo para a [classe gamepad (Windows. Gaming. Input)-Windows aplicativos UWP](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true).
- habilitada uma [API de acesso atribuída](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) para que os aplicativos agora possam determinar se um HoloLens está sendo executado em um modo de quiosque para o usuário conectado ao HoloLens.

#### <a name="for-enterprise"></a>Para Enterprise

- resolve problemas relacionados a propriedades de conformidade de relatórios de dispositivos HoloLens; uma reinicialização pode ser necessária para que o relatório correto seja disparado em compilações internas.  
- Atualização da versão na caixa de assistência remota instalada em flashes atualizados.
- Correção de um problema em que, após a primeira entrada do usuário, o OOBE estava sendo encerrado em cenários em que as configurações de quiosque baseadas em grupos do AAD estavam sendo usadas.
- Correção de um problema ao exibir notificações de atualização e prompts de diálogo para reinicialização do dispositivo.
- corrigido um problema em que, após a reinicialização do dispositivo, os controladores Xbox e outros periféricos Bluetooth LE necessários seriam emparelhados novamente para se conectar.

## <a name="start-receiving-insider-builds"></a>Comece a receber compilações do insider

> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize o dispositivo para atualizar o estado e obtenha a compilação mais recente.
>
> - O comando de voz "reinicializar dispositivo" funciona bem.
> - você também pode escolher o botão reiniciar no programa Configurações/Windows insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso o levará de volta ao controle.

em um dispositivo HoloLens 2, acesse **Configurações**  >  **atualização &** o  >  **programa insider Windows** de segurança e selecione **introdução**. vincule a conta que você usou para se registrar como um Windows insider.

> [!NOTE]
> Para registrar seu dispositivo em builds do Insider, você precisará habilitar a telemetria opcional. se você ainda não fez isso, abra o aplicativo Configurações e selecione diagnóstico de **privacidade**  ->  **& comentários** e, em seguida, selecione **dados de diagnóstico opcionais**.

Windows o insider agora está mudando para os canais. O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta** e o anel de **versão prévia** se tornará o **canal versão prévia**. Aqui está o que esse mapeamento é semelhante a:

![Windows Explicação de canais Insider.](images/WindowsInsiderChannels.png)

para obter mais informações, consulte [introdução aos canais do Windows insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) em Windows Blogs.
em seguida, selecione **desenvolvimento ativo de Windows**, escolha se deseja receber as compilações de canal de **desenvolvimento** ou **Beta** e examine os termos do programa.
Selecione **confirmar > reiniciar agora** para concluir. depois que o dispositivo for reinicializado, vá para **Configurações > atualizar & segurança > verificar** se há atualizações para obter a compilação mais recente.

### <a name="update-error-0x80070490-work-around"></a>Erro de atualização 0x80070490 solução alternativa

Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal de desenvolvimento ou beta, experimente a solução alternativa de curto prazo a seguir. Ele envolve mover seu canal Insider, selecionando a atualização e, em seguida, movendo o canal Insider de volta.

#### <a name="stage-one---release-preview"></a>Estágio One-Release versão prévia

1. Configurações, atualize a segurança do &, Windows programa insider, selecione **liberar canal de versão prévia**.

2. Configurações, atualize & Security, Windows Update, **verifique se há atualizações**. Após a atualização, continue no estágio dois.

#### <a name="stage-two---dev-channel"></a>Preparar canal de dois desenvolvedores

1. Configurações, atualize a segurança do &, Windows programa insider, selecione **canal de desenvolvimento**.

2. Configurações, atualize & Security, Windows Update, **verifique se há atualizações**.

## <a name="ffu-download-and-flash-directions"></a>Download do FFU e direções do flash

Para testar com um FFU assinado por voo, primeiro você precisará desbloquear o dispositivo antes de atualizar o FFU assinado por voo.

1. No PC:
    1. Baixe o FFU para o seu PC do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Instale o ARC (complemento de recuperação avançada) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. no desbloqueio do HoloLens-Flight: abra **Configurações**  >  **Update & Security**  >  **Windows insider Program** , então, inscreva-se, reinicialize o dispositivo.

1. Flash FFU – agora você pode piscar o FFU assinado por voo usando o ARC.

### <a name="provide-feedback-and-report-issues"></a>Fornecer comentários e relatar problemas

use [o aplicativo de Hub de comentários](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas. O uso do hub de comentários garante que todas as informações de diagnóstico necessárias estejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.  problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.

> [!NOTE]
> Lembre-se de aceitar o prompt que pergunta se você deseja que o Hub de comentários acesse sua pasta documentos (selecione **Sim** quando solicitado).

## <a name="note-for-developers"></a>Observação para desenvolvedores

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando as compilações do insider de HoloLens.  confira a [documentação do HoloLens developer](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com compilações internas do HoloLens.  você pode usar as mesmas compilações do Unity e Visual Studio que já está usando para o desenvolvimento de HoloLens.

## <a name="stop-receiving-insider-builds"></a>Parar de receber compilações do insider

se você não quiser mais receber compilações do insider de Windows Holographic, poderá recusar quando o HoloLens está executando uma compilação de produção ou pode [recuperar seu dispositivo](hololens-recovery.md) usando o complemento de recuperação avançada para recuperar seu dispositivo para uma versão não insider do Windows Holographic.

> [!CAUTION]
> Há um problema conhecido em que os usuários que cancelam o registro do insider Preview são criados após a reinstalação manual de uma nova versão de visualização que teria uma tela azul. Depois, eles devem recuperar manualmente seu dispositivo. Para obter detalhes completos sobre se você for afetado ou não, veja mais sobre esse [problema conhecido](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).

para verificar se o HoloLens está executando uma compilação de produção:

1. acesse **Configurações > System > sobre** e localize o número da versão.

1. [Consulte as notas de versão para obter os números de Build de produção](hololens-release-notes.md).

Para recusar compilações internas:

1. em um HoloLens executando uma compilação de produção, vá para **Configurações > atualizar & segurança > programa insider** e selecione **parar compilações do insider**.

1. Siga as instruções para recusar seu dispositivo.
