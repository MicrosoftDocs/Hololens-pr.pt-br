---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar builds do Insider e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.
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
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 80346fd74c9b38ed557d815ed138b1da5702609e
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859010"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às versões mais recentes do Insider Preview para HoloLens! É simples começar e [fornecer comentários](hololens-insider.md#start-receiving-insider-builds) valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas sobre a versão do Insider

Estamos empolgados em iniciar o voo de novos recursos para Windows Insiders novamente. Novos builds serão disponibilizados para os Canais Dev e Beta para as atualizações mais recentes. Continuaremos a atualizar essa página à medida que adicionarmos mais recursos e atualizações aos builds Windows Insider. Fique animado e pronto para misturar essas atualizações em sua realidade.

Trata-se da solução de problemas aprimorada e relatórios de dispositivos, alguns bugs corrigidos no modo de quiosque e o visualizador de certificados, a superfície de capacidade de gerenciamento expandida e a maior confiabilidade da atualização. Um novo recurso principal dessa atualização de recurso que chega ao HoloLens é nosso Modo de Plataforma Móvel. Confira todos os novos recursos excelentes para HoloLens 2!

| Recurso                 | Descrição                | Usuário ou cenário | Build introduzido |
|-------------------------|----------------------------|--------------|------------------|
| [Movendo o modo de plataforma](#moving-platform-mode) | Apresenta o Modo de Plataforma Móvel beta, que, quando configurado, permite o uso de HoloLens 2 em grandes recipientes de animais que apresentam movimento de baixa dinâmica. | Tudo | 20348.1411 |
| [Suporte a arquivos PFX para o Gerenciador de Certificados](#pfx-file-support-for-certificate-manager) | Adicionar certificados PFX por meio Configurações interface do usuário | Usuário Final | 20348.1405 |
| [Exibir relatório de diagnóstico avançado em Configurações no HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Exibir logs de diagnóstico do MDM no dispositivo | Solução de problemas | 20348.1405 |
| [Notificações de diagnóstico offline](#offline-diagnostics-notifications) | Comentários audiovisuais para coleta de log | Solução de problemas | 20348.1405 |
| [Aprimoramentos de coleta de log de armazenamento baixo](#low-storage-log-collection-improvements) | Melhorias em cenários de coleta de log durante situações de baixo armazenamento. | Solução de problemas | 20348.1412 |
| [Alterações do CSP para relatórios HoloLens detalhes](#csp-changes-for-reporting-hololens-details) | Novos CSPs para consultar dados | Administradores de IT    | 20348.1403                 |
| [Política de logon automático controlada pelo CSP](#auto-login-policy-controlled-by-csp) | Usado para fazer logoff em uma conta automaticamente | Administradores de IT | 20348.1405 |
| [Detecção e notificações de reinicialização de atualização aprimoradas](#improved-update-restart-detection-and-notifications) | Novas políticas habilitadas e UX para atualizações. | Administradores de IT | 20348.1405 |
| [Smart Retry para atualizações de aplicativo](#smart-retry-for-app-updates) | Permite que os administradores de IT agendou as tentarem atualizar aplicativos. | Administradores de IT | 20348.1405 |
| [Use somente aplicativos da loja privada somente para Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurar o aplicativo da loja para mostrar apenas aplicativos da organização | Administrador de TI | 20348.1408 |
| [Usar aplicativos WDAC e LOB](#use-wdac-and-lob-apps) | Permite que os administradores de IT usem seus próprios aplicativos e ainda usem o WDAC para bloquear outros aplicativos. | Administradores de IT | 20348.1405 |
| [Correções e melhorias](#fixes-and-improvements) | Correções e melhorias para HoloLens. | Tudo | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Lista de verificação de recursos do Insider do Administrador de IT

✔️ se você quiser definir uma única conta do Azure AD para fazer logon automaticamente, [configure esse novo CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ se você quiser configurar seus aplicativos para tentar atualizar automaticamente após a falha na atualização, de configurar esse novo CSP para [a nova tentativa inteligente.](#smart-retry-for-app-updates) <br>
✔️ se você quiser ter mais controle sobre as atualizações do sistema operacional, confira essas políticas [de atualização habilitadas recentemente.](#improved-update-restart-detection-and-notifications) <br>
✔️ se você precisar disponibilizar os aplicativos da sua organização na loja da empresa por meio do Microsoft Store, mas quiser permitir apenas o acesso aos aplicativos da sua organização e não ao armazenamento completo, de acordo com essa [política.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ se você quiser saber o espaço de armazenamento gratuito, SSID ou BSSID de seus dispositivos HoloLens, confira esses [CSPs de relatório.](#csp-changes-for-reporting-hololens-details) <br>
✔️ se você quiser usar o WDAC para bloquear a iniciação de aplicativos ou processos, mas também precisar usar seus próprios aplicativos de linha de negócios, agora você pode permitir o LOB em sua [política WDAC](#use-wdac-and-lob-apps).

### <a name="moving-platform-mode"></a>Movendo o modo de plataforma

A partir **do Insider Build 20348.1411,** adicionamos suporte beta para acompanhamento em plataformas móveis de movimento baixo dinâmico no HoloLens 2. Depois de instalar o build e habilenciar o Modo de Plataforma Móvel, você poderá usar o HoloLens 2 em ambientes anteriormente inacessíveis, como grandes navios e grandes navios. Atualmente, o recurso tem como alvo habilitar apenas essas plataformas móveis específicas. Embora nada impeça você de tentar usar o recurso em outros ambientes, ele se concentra em adicionar suporte a esses ambientes primeiro.

Para saber mais sobre o que tem suporte e como habilitar esse novo recurso, [visite a página da plataforma móvel.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Suporte a arquivos PFX para o Gerenciador de Certificados

Introduzido no Windows Insider Build 20348.1405. Adicionamos suporte ao Gerenciador de [Certificados](certificate-manager.md) para agora usar certificados .pfx. Quando os usuários navegam **Configurações** Atualizar & certificados de segurança e selecionam Instalar um certificado, a interface do usuário agora dá suporte ao arquivo de  >    >  certificado .pfx. 
Os usuários podem importar o certificado .pfx, com chave privada, para o armazenamento do usuário ou do computador.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Exibir relatório de diagnóstico avançado em Configurações no HoloLens

Para dispositivos gerenciados ao solucionar problemas de comportamento, confirmar que uma configuração de política esperada é aplicada é uma etapa importante. Anteriormente a esse novo recurso, a exibição de essas informações precisava ser feita fora do dispositivo por meio do MDM ou próximo ao dispositivo depois de exportar os logs de diagnóstico do MDM coletados por meio do acesso de contas do **Configurações** ao trabalho ou à escola e selecione Exportar seus logs de gerenciamento e exibidos em um  ->    >  computador próximo. 

Agora, o Diagnóstico de MDM pode ser exibido no dispositivo usando o navegador Edge. Para exibir mais facilmente o relatório de Diagnóstico do MDM, navegue até a página Acessar trabalho ou escola e selecione **Exibir relatório de diagnóstico avançado**. Isso gerará e abrirá o relatório em uma nova janela do Edge.

![Exibir relatório de diagnóstico avançado no Configurações aplicativo.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notificações de diagnóstico offline

Esta é uma atualização para um recurso existente chamado [Diagnóstico Offline.](hololens-diagnostic-logs.md#offline-diagnostics) Anteriormente, não havia nenhum indicador claro para os usuários de que eles dispararam a coleta de diagnóstico ou que ela havia sido concluída.
Agora adicionados Windows builds do Insider, há duas formas de comentários audiovisuais para o Diagnóstico Offline. O primeiro que está sendo notificação é exibido para quando a coleta é iniciada e concluída. Eles serão exibidos quando o usuário estiver conectado e tiver visuais.

![Sistema para coletar logs.](./images/logcollection1.jpg)

![Toast quando a coleta de log for concluída.](./images/logcollection2.jpg)

Como os usuários geralmente usam o Diagnóstico Offline como um mecanismo de coleta de logs de fallback para quando não têm acesso a uma exibição, não é possível fazer logoff ou ainda estão no OOBE, também haverá uma indicação de áudio tocada quando os logs são coletados. Esse som será tocado além da notificação do sistema.

Esse novo recurso será habilitado quando o dispositivo for atualizado e não precisará ser habilitado ou gerenciado. Em qualquer caso em que esse novo comentário não possa ser exibido ou ouvido, o Diagnóstico Offline ainda será gerado.

Esperamos que com essa adição mais nova de comentários audiovisuais seja mais fácil coletar dados de diagnóstico e, mais rapidamente, ser capaz de solucionar seus problemas.

### <a name="low-storage-log-collection-improvements"></a>Aprimoramentos de coleta de log de armazenamento baixo

Em cenários em que um dispositivo parece estar com pouco espaço em disco quando os logs de diagnóstico são coletados, um relatório adicional **chamado** StorageDiagnostics.zipserá criado. O limite de armazenamento baixo é determinado automaticamente pelo Windows [de armazenamento.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="csp-changes-for-reporting-hololens-details"></a>Alterações do CSP para relatórios HoloLens detalhes

- Introduzido no Windows Insider Build, 20348.1403

Os CSPs a seguir foram atualizados com novas maneiras de relatar informações de seus HoloLens dispositivos.

#### <a name="devdetail-csp---free-storage"></a>CSP de DevDetail – versão Armazenamento

O CSP de DevDetail agora também relata espaço de armazenamento livre HoloLens dispositivo. Isso deve corresponder aproximadamente ao valor mostrado na Configurações do aplicativo Armazenamento aplicativo. A seguir está o nó específico que contém essas informações.

- ./DevDetail/Ext/Microsoft/FreeStorage (somente operação GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>CSP do DeviceStatus – SSID e BSSID

O CSP do DeviceStatus agora também relata SSID e BSSID Wi-Fi rede com a qual HoloLens está ativamente conectado. A seguir estão os nós específicos que contêm essas informações.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ mac address *of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ mac address *of Wi-Fi adapter*/BSSID

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

### <a name="smart-retry-for-app-updates"></a>Smart Retry para atualizações de aplicativo

Agora habilitada para HoloLens é uma nova política que permite aos administradores de IT definir uma data recorrente ou única para reiniciar aplicativos cuja atualização falhou porque o aplicativo está sendo usado, permitindo que a atualização seja aplicada. Eles podem ser definidos com base em alguns gatilhos diferentes, como uma hora agendada ou uma login. Para saber mais sobre como usar essa exibição de política [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar somente aplicativos da loja privada para Microsoft Store

A política RequirePrivateStoreOnly foi habilitada para HoloLens. Essa política permite que o Microsoft Store aplicativo seja configurado para mostrar apenas o armazenamento privado configurado para sua organização. Limitando o acesso somente aos aplicativos que você disponibiliza.

Saiba mais sobre [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>Usar aplicativos WDAC e LOB

Agora você pode usar o WDAC para bloquear a iniciação de aplicativos ou processos e continuar a usar sua própria linha de aplicativos de preparação. agora você pode permitir em sua política WDAC. O uso dessa política envolve a execução de uma linha extra de código no PowerShell ao criar sua política do WDAC. [Revise as etapas aqui.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>Correções e melhorias

- Corrigido um [problema conhecido para Portal de Dispositivos em que não havia nenhum prompt baixando arquivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Corrigido um problema conhecido para Portal de Dispositivos com tempos de carregamento e [download de arquivo.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Aborda problemas relacionados ao relatório de propriedades de conformidade de HoloLens dispositivos; uma reinicialização pode ser necessária para que o relatório correto seja disparado em builds do Insider.  
- Habilitada [uma API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) de Acesso Atribuído para que os aplicativos agora possam determinar se um HoloLens está em execução em um modo de Quiosque para o usuário conectado ao HoloLens.
- Atualização da versão in-box do Remote Assist instalada em flashes novos.

## <a name="start-receiving-insider-builds"></a>Começar a receber builds do Insider

> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize seu dispositivo para atualizar o estado e obter o build mais recente.
>
> - O comando de voz "Reinicializar dispositivo" funciona bem.
> - Você também pode escolher o botão reiniciar Configurações/Windows Programa Insider.
>
> Temos um bug no back-end que você pode ter encontrado e isso fará com que você volte ao caminho certo.

Em um HoloLens 2, vá para Atualizar Configurações &  >  **Segurança**  >  **Windows Programa Insider** e **selecione Começar.** Vincule a conta usada para se registrar como um Windows Insider.

Windows insider agora está mudando para Canais. O **anel Rápido** se tornará o  Canal **deV,** o anel Lento  se tornará o Canal beta **e** o anel versão prévia de versão se tornará **o** Canal de Versão Prévia. Veja a aparência desse mapeamento:

![Windows Explicação dos canais insider](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.
Em seguida, selecione Desenvolvimento **ativo do Windows**, escolha se você gostaria de receber o Canal **de** Desenvolvimento **ou** Canal beta builds e revise os termos do programa.
Selecione **Confirmar > Reiniciar Agora** para concluir. Depois que o dispositivo for reinicializado, vá para Atualizar Configurações > & **Segurança > Verificar** se há atualizações para obter o build mais recente.

### <a name="update-error-0x80070490-work-around"></a>Erro de atualização 0x80070490 de trabalho

Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, tente o seguinte work-around de curto prazo. Isso envolve mover seu canal interno, pegar a atualização e, em seguida, mover seu canal insider de volta.

#### <a name="stage-one---release-preview"></a>Estágio um – Versão Prévia

1. Configurações, Atualizar & Segurança, Windows Programa Insider, selecione Versão Prévia **do Canal**.

2. Configurações, Atualizar & Segurança, Windows Atualização, **Verificar se há atualizações.** Após a atualização, continue no Estágio dois.

#### <a name="stage-two---dev-channel"></a>Estágio dois – Canal dev

1. Configurações, Atualizar & Segurança, Windows Programa Insider, selecione **Canal deV**.

2. Configurações, Atualizar & Segurança, Windows Atualização, **Verificar se há atualizações.**

## <a name="ffu-download-and-flash-directions"></a>Instruções de download e flash do FFU

Para testar com um voo assinado ffu, primeiro você precisa desbloquear seu dispositivo antes de piscar o voo com sinal ffu.

1. No PC:
    1. Baixe o ffu no seu computador do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

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
