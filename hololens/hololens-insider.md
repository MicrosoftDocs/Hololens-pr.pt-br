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
ms.openlocfilehash: 19035c53fec64ec19243ab5edc79bf77acbf400a
ms.sourcegitcommit: d99de8d5afbe2585fdb5396bd0165ac74734b281
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2021
ms.locfileid: "122277147"
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
| [Detecção e notificações de reinicialização de atualização aprimoradas](#improved-update-restart-detection-and-notifications) | Novas UX e as novas regras habilitadas para atualizações. | Administradores de IT | 20348.1405 |
| [Smart Retry para atualizações de aplicativo](#smart-retry-for-app-updates) | Permite que os administradores de IT agendou as tentarem atualizar aplicativos. | Administradores de IT | 20348.1405 |
| [Use somente aplicativos da loja privada somente para Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurar o aplicativo da loja para mostrar apenas aplicativos da organização | Administrador de TI | 20348.1408 |
| [Correções e melhorias](#fixes-and-improvements) | Correções e melhorias para HoloLens. | Tudo | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Lista de verificação de recursos do Insider do Administrador de IT

✔️ se você quiser definir uma única conta do Azure AD para fazer logon automaticamente, [configure esse novo CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ se você quiser configurar seus aplicativos para tentar atualizar automaticamente após a falha na atualização, de configurar esse novo CSP para [a nova tentativa inteligente.](#smart-retry-for-app-updates) <br>
✔️ se você quiser ter mais controle sobre as atualizações do sistema operacional, confira essas políticas [de atualização habilitadas recentemente.](#improved-update-restart-detection-and-notifications) <br>
✔️ se você precisar disponibilizar os aplicativos da sua organização na loja da empresa por meio do Microsoft Store, mas quiser permitir apenas o acesso aos aplicativos da sua organização e não ao armazenamento completo, de acordo com essa [política.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ se você quiser saber o espaço de armazenamento gratuito, SSID ou BSSID de seus dispositivos HoloLens, confira esses [CSPs de relatório.](#csp-changes-for-reporting-hololens-details)

### <a name="moving-platform-mode"></a>Movendo o modo de plataforma

A partir **do Insider Build 20348.1411,** adicionamos suporte beta para acompanhamento em plataformas móveis de movimento baixo dinâmico no HoloLens 2. Depois de instalar o build e habilenciar o Modo de Plataforma Móvel, você poderá usar o HoloLens 2 em ambientes anteriormente inacessíveis, como grandes navios e grandes navios. Atualmente, o recurso tem como alvo habilbilenciar apenas essas plataformas móveis específicas. Embora nada impeça você de tentar usar o recurso em outros ambientes, o recurso se concentra em adicionar suporte a esses ambientes primeiro.

Para saber mais sobre o que tem suporte e como habilitar esse novo recurso, [visite a página da plataforma móvel.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Suporte a arquivos PFX para o Gerenciador de Certificados

Introduzido no Windows Insider build 20348.1405. Adicionamos suporte ao Gerenciador de [Certificados](certificate-manager.md) para agora usar certificados .pfx. Quando os usuários navegam **Configurações** Atualizar & Certificados de Segurança e selecionam Instalar um certificado, a interface do usuário agora dá suporte ao arquivo de  >    >  certificado .pfx. 
Os usuários podem importar o certificado .pfx, com chave privada, para o armazenamento do usuário ou do computador.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Exibir relatório de diagnóstico avançado em Configurações no HoloLens

Para dispositivos gerenciados ao solucionar problemas de comportamento, confirmar que uma configuração de política esperada é aplicada é uma etapa importante. Anteriormente a esse novo recurso, isso precisava ser feito fora do dispositivo por meio do MDM ou próximo ao dispositivo depois de exportar os logs de diagnóstico do MDM coletados por meio de contas do **Configurações** Acessar o trabalho ou a escola e selecionar Exportar seus logs de gerenciamento e exibidos em um  ->    >  computador próximo. 

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

Em cenários em que um dispositivo parece estar com pouco espaço em disco quando os logs de diagnóstico são coletados, um relatório adicional **chamadoStorageDiagnostics.zip** será criado. o limite de armazenamento baixo é determinado automaticamente pelo [sensor de armazenamento](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)Windows.

### <a name="csp-changes-for-reporting-hololens-details"></a>alterações do CSP para relatórios HoloLens detalhes

- introduzido na compilação do Windows insider, 20348,1403

os seguintes CSPs foram atualizados com novas maneiras de relatar informações de seus dispositivos HoloLens.

#### <a name="devdetail-csp---free-storage"></a>CSP DevDetail – gratuito Armazenamento

o CSP DevDetail agora também relata o espaço de armazenamento livre no dispositivo HoloLens. isso deve corresponder aproximadamente ao valor mostrado na página Armazenamento do aplicativo Configurações. A seguir está o nó específico que contém essas informações.

- ./DevDetail/Ext/Microsoft/FreeStorage (somente operação GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>CSP DeviceStatus-SSID e BSSID

o CSP DeviceStatus agora também relata SSID e BSSID da rede Wi-Fi com a qual o HoloLens está conectado ativamente. A seguir estão os nós específicos que contêm essas informações.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*endereço MAC do adaptador de Wi-Fi*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*endereço MAC do adaptador de Wi-Fi*/BSSID

Exemplo de blob de SyncML (para fornecedores de MDM) para consultar NetworkIdentifiers

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

Essa nova política AutoLogonUser controla se um usuário será conectado automaticamente. Alguns clientes desejam configurar dispositivos vinculados a uma identidade, mas não querem nenhuma experiência de entrada. Imagine selecionando um dispositivo e usando a assistência remota imediatamente. ou ter um benefício de poder distribuir rapidamente HoloLens dispositivos e habilitar seus usuários finais a agilizar o logon.

Quando a política é definida como um valor não vazio, ela especifica o endereço de email do usuário de logon automático. O usuário especificado deve fazer logon no dispositivo pelo menos uma vez para habilitar o logon automático.

O OMA-URI do novo valor de cadeia de caracteres de política `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- O usuário com o mesmo endereço de email terá logon automático habilitado.

Em um dispositivo em que essa política está configurada, o usuário especificado na política precisará fazer logon pelo menos uma vez. Reinicializações subsequentes do dispositivo após o primeiro logon terão o usuário especificado conectado automaticamente. Há suporte apenas para um único usuário de logon automático. Uma vez habilitado, o usuário conectado automaticamente não poderá fazer logoff manualmente. Para fazer logon como um usuário diferente, a política deve primeiro ser desabilitada.

> [!NOTE]
>
> - Alguns eventos, como as principais atualizações do sistema operacional, podem exigir que o usuário especificado faça logon no dispositivo novamente para retomar o comportamento de logon automático.
> - O logon automático só tem suporte para usuários do MSA e do AAD.

### <a name="improved-update-restart-detection-and-notifications"></a>Detecção e notificações de reinício de atualização aprimoradas

entre horas ativas e políticas de tempo de instalação, é possível evitar a reinicialização de dispositivos HoloLens quando eles estão em uso. No entanto, ele também atrasaria a adoção de atualizações se as reinicializações não ocorrerem para concluir a instalação de uma atualização necessária. Agora adicionamos políticas para permitir que ele imponha prazos e reinicializações necessárias e verifique se a instalação de uma atualização foi concluída em tempo hábil. Os usuários podem ser notificados antes da reinicialização que está sendo iniciada e podem atrasar a reinicialização de acordo com a política de ti.

As seguintes políticas de atualização foram adicionadas:

- [Atualizar/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Atualizar/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Atualizar/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Atualizar/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Atualizar/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Atualizar/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="smart-retry-for-app-updates"></a>Repetição inteligente para atualizações de aplicativo

agora habilitado para HoloLens é uma nova política que permite que os administradores de ti definam uma data recorrente ou uma hora para reiniciar os aplicativos cuja atualização falhou porque o aplicativo está sendo usado, permitindo que a atualização seja aplicada. Eles podem ser definidos com base em alguns gatilhos diferentes, como um horário agendado ou entrada. Para saber mais sobre como usar essa política, veja [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar somente aplicativos de repositório particular para Microsoft Store

A política RequirePrivateStoreOnly foi habilitada para HoloLens. essa política permite que o aplicativo Microsoft Store seja configurado para mostrar apenas o repositório privado configurado para sua organização. Limitando o acesso apenas aos aplicativos que você disponibilizou.

Saiba mais sobre o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Correções e aprimoramentos

- Correção de um [problema conhecido para o portal do dispositivo em que não havia prompt para baixar arquivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Correção de um [problema conhecido para o portal do dispositivo com tempo limite de upload e download de arquivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- resolve problemas relacionados a propriedades de conformidade de relatórios de dispositivos HoloLens; uma reinicialização pode ser necessária para que o relatório correto seja disparado em compilações internas.  
- habilitada uma [API de acesso atribuída](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) para que os aplicativos agora possam determinar se um HoloLens está sendo executado em um modo de quiosque para o usuário conectado ao HoloLens.
- Atualização da versão na caixa de assistência remota instalada em flashes atualizados.

## <a name="start-receiving-insider-builds"></a>Comece a receber compilações do insider

> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize o dispositivo para atualizar o estado e obtenha a compilação mais recente.
>
> - O comando de voz "reinicializar dispositivo" funciona bem.
> - você também pode escolher o botão reiniciar no programa Configurações/Windows insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso o levará de volta ao controle.

em um dispositivo HoloLens 2, acesse **Configurações**  >  **atualização &** o  >  **programa insider Windows** de segurança e selecione **introdução**. vincule a conta que você usou para se registrar como um Windows insider.

Windows o insider agora está mudando para os canais. O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta** e o anel de **versão prévia** se tornará o **canal versão prévia**. Aqui está o que esse mapeamento é semelhante a:

![Windows Explicação de canais Insider](images/WindowsInsiderChannels.png)

para obter mais informações, consulte [introdução aos canais do Windows insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) em Windows Blogs.
em seguida, selecione **desenvolvimento ativo de Windows**, escolha se deseja receber as compilações de canal de **desenvolvimento** ou **Beta** e examine os termos do programa.
Selecione **confirmar > reiniciar agora** para concluir. depois que o dispositivo for reinicializado, vá para **Configurações > atualizar & segurança > verificar** se há atualizações para obter a compilação mais recente.

### <a name="update-error-0x80070490-work-around"></a>Erro de atualização 0x80070490 solução alternativa

Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal de desenvolvimento ou beta, tente a seguinte solução alternativa de curto prazo. Ele envolve mover seu canal Insider, selecionando a atualização e, em seguida, movendo o canal Insider de volta.

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

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando as compilações do insider de HoloLens.  Confira a [documentação HoloLens desenvolvedor para](https://developer.microsoft.com/windows/mixed-reality/development) começar. Essas mesmas instruções funcionam com builds do Insider HoloLens.  Você pode usar os mesmos builds do Unity e Visual Studio que já está usando para HoloLens desenvolvimento.

## <a name="stop-receiving-insider-builds"></a>Parar de receber builds do Insider

Se você não quiser mais receber builds insider do Windows Holographic, poderá optar quando o HoloLens estiver [](hololens-recovery.md) executando um build de produção ou recuperar seu dispositivo usando o Advanced Recovery Companion para recuperar seu dispositivo para uma versão não interna do Windows Holographic.

> [!CAUTION]
> Há um problema conhecido em que os usuários que não se registram no Insider Preview são builds após a reinstalação manual de um novo build de visualização experimentariam uma tela azul. Posteriormente, eles devem recuperar manualmente o dispositivo. Para obter detalhes completos sobre se você seria afetado ou não, veja mais sobre esse [problema conhecido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para verificar se o HoloLens está executando um build de produção:

1. Vá para **Configurações > Sistema > Sobre** e encontre o número de build.

1. [Consulte as notas de versão para números de build de produção](hololens-release-notes.md).

Para não fazer builds do Insider:

1. Em um HoloLens executando um build de produção, vá para Configurações > Atualizar & **Segurança > Windows Programa Insider** e selecione **Parar builds do Insider**.

1. Siga as instruções para ressutar seu dispositivo.
