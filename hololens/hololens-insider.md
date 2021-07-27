---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar o Insider compilações e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b7e5a7cbaa746f58fe0344dd8bf5b027e2e8cea7
ms.sourcegitcommit: dc5d6f3802c997749775be04de522af8cb6d0850
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2021
ms.locfileid: "114693709"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às compilações mais recentes do insider Preview para HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de versão do insider

estamos empolgados para começar a comprovar novos recursos para Windows insiders novamente. Novas compilações serão comprovadas para os canais de desenvolvimento e beta para as atualizações mais recentes. continuaremos a atualizar esta página à medida que adicionamos mais recursos e atualizações às nossas compilações do Windows insider. Fique empolgado e pronto para misturar essas atualizações em sua realidade.

| Recurso                 | Descrição                | Usuário ou cenário | Compilação introduzida |
|-------------------------|----------------------------|--------------|------------------|
| [alterações do CSP para relatórios HoloLens detalhes](#csp-changes-for-reporting-hololens-details) | Novos CSPs para a consulta de dados | Administradores de ti    | 20348,1403                 |
| [Política de logon automático controlada pelo CSP](#auto-login-policy-controlled-by-csp) | Usado para fazer logon em uma conta automaticamente | Administradores de ti | 20348,1405 |
| [Suporte a arquivos PFX para o Gerenciador de certificados](#pfx-file-support-for-certificate-manager) | adicionar certificados PFX por meio da interface do usuário do Configurações | Usuário Final | 20348,1405 |
| [exibir relatório de diagnóstico avançado no Configurações no HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Exibir logs de diagnóstico do MDM no dispositivo | Solução de problemas | 20348,1405 |
| [Notificações de diagnóstico offline](#offline-diagnostics-notifications) | Audiovisual comentários para coleta de log | Solução de problemas | 20348,1405 |
| [Usar somente aplicativos de repositório privado somente para Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Configurar o aplicativo da loja para mostrar somente os aplicativos da organização | Administrador de TI | 20348,1408 |
| [Correções e aprimoramentos](hololens-insider.md#fixes-and-improvements) | Correções e aprimoramentos para HoloLens. | Tudo | 20348,1408 |

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
> - Alguns eventos, como as principais atualizações do sistema operacional, podem exigir que o usuário especificado faça logon no dispositivo novamente para retomar o comportamento de logon automático. 
> - O logon automático só tem suporte para usuários do MSA e do AAD.

### <a name="pfx-file-support-for-certificate-manager"></a>Suporte a arquivos PFX para o Gerenciador de certificados

introduzido no Windows insider build 20348,1405. Adicionamos suporte ao Gerenciador de [certificados](certificate-manager.md) para agora usar certificados. pfx. quando os usuários navegam para **Configurações**  >  **atualização &**  >  **certificados** de segurança e selecionam **instalar um certificado** , a interface do usuário agora dá suporte ao arquivo de certificado. pfx.
Os usuários podem importar o certificado. pfx, com a chave privada, para o repositório de usuários ou para o repositório de computadores.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>exibir relatório de diagnóstico avançado no Configurações no HoloLens

Para dispositivos gerenciados ao solucionar problemas de comportamento, a confirmação de que uma configuração de política esperada é aplicada é uma etapa importante. antes desse novo recurso, isso tinha que ser feito fora do dispositivo via MDM ou perto do dispositivo depois de exportar os logs de diagnóstico do MDM coletados por meio de **Configurações**  ->  **contas**  >  **acessarem o trabalho ou a escola** e selecionamos **exportar os logs de gerenciamento** e exibidos em um PC próximo.

Agora, o diagnóstico de MDM pode ser exibido no dispositivo usando o navegador Edge. Para exibir mais facilmente o relatório de diagnóstico do MDM, navegue até a página acessar o trabalho ou a escola e selecione **Exibir relatório de diagnóstico avançado**. Isso irá gerar e abrir o relatório em uma nova janela de borda.

![exiba o relatório de diagnóstico avançado no aplicativo Configurações.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Notificações de diagnóstico offline

Esta é uma atualização para um recurso existente chamado [diagnóstico offline](hololens-diagnostic-logs.md#offline-diagnostics). Anteriormente, não havia nenhum indicador claro para os usuários que eles dispararam a coleta de diagnóstico ou que ele tivesse sido concluído.
agora adicionados às compilações do Windows insider, há duas formas de comentários de audiovisual para o diagnóstico Offline. A primeira vez que as notificações de notificação são exibidas para ambos quando a coleta é iniciada e concluída. Eles serão exibidos quando o usuário estiver conectado e tiver visuais.

![Notificação para coleta de logs.](./images/logcollection1.jpg)

![Notificação quando a coleta de log for concluída.](./images/logcollection2.jpg)
 
Como os usuários geralmente usam o diagnóstico offline como um mecanismo de coleta de logs de fallback para quando eles não têm acesso a uma exibição, não podem fazer logon ou ainda estão no OOBE, também haverá uma indicação de áudio quando os logs forem coletados. Esse som será reproduzido além da notificação do sistema.

Esse novo recurso será habilitado quando o dispositivo for atualizado e não precisar ser habilitado ou gerenciado. Em qualquer evento que esse novo comentário não possa ser exibido ou ouvido, os diagnósticos offline ainda serão gerados.

Esperamos que essa adição mais recente de comentários audiovisual seja mais fácil de coletar dados de diagnóstico e ser capaz de solucionar os problemas com mais rapidez.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar somente aplicativos de repositório particular para Microsoft Store

A política RequirePrivateStoreOnly foi habilitada para HoloLens. essa política permite que o aplicativo Microsoft Store seja configurado para mostrar apenas o repositório privado configurado para sua organização. Limitando o acesso somente aos aplicativos que você disponibiliza.

Saiba mais sobre [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Correções e melhorias:

- Corrigido um [problema conhecido para Portal de Dispositivos em que não havia nenhum prompt baixando arquivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Corrigido um problema conhecido para o Portal de Dispositivos com tempos de carregamento e [download de arquivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Aborda problemas relacionados ao relatório de propriedades de conformidade de HoloLens dispositivos; uma reinicialização pode ser necessária para que o relatório correto seja disparado em builds do Insider.  
- Atualização da versão in-box do Remote Assist instalada em flashes novos.


## <a name="start-receiving-insider-builds"></a>Começar a receber builds do Insider

> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize seu dispositivo para atualizar o estado e obter o build mais recente.
> - O comando de voz "Reinicializar dispositivo" funciona bem. 
> - Você também pode escolher o botão reiniciar Configurações/Windows Programa Insider.
>
> Temos um bug no back-end que você pode ter encontrado e isso fará com que você volte ao caminho certo.

Em um HoloLens 2, vá para Configurações Atualizar &  >  **Segurança**  >  **Windows Programa Insider** e **selecione Começar.** Vincule a conta usada para se registrar como um Windows Insider.

Windows insider agora está mudando para Canais. O **anel Rápido** se tornará o  Canal **deV,** o anel Lento  se tornará o Canal beta **e** o anel versão prévia de versão se tornará **o** Canal de Versão Prévia. Veja a aparência desse mapeamento:

![Windows Explicação dos canais insider](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.
Em seguida, selecione Desenvolvimento **ativo do Windows**, escolha se você gostaria de receber o Canal **de** Desenvolvimento **ou** Canal beta builds e revise os termos do programa.
Selecione **Confirmar > Reiniciar Agora** para concluir. Depois que o dispositivo for reinicializado, vá para Atualizar Configurações > & **Segurança > Verificar** se há atualizações para obter o build mais recente.

### <a name="update-error-0x80070490-work-around"></a>Erro de 0x80070490 para resolver o erro

Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, tente a seguinte explicação de curto prazo. Isso envolve mover seu canal interno, pegar a atualização e, em seguida, mover seu canal insider de volta.

#### <a name="stage-one---release-preview"></a>Estágio um – Versão Prévia

1.  Configurações, Atualizar & Segurança, Windows Programa Insider, selecione Versão Prévia **do Canal**.

2.  Configurações, Atualizar & Segurança, Windows Atualização, **Verificar se há atualizações.** Após a atualização, continue no Estágio dois.

#### <a name="stage-two---dev-channel"></a>Estágio dois – Canal dev

1. Configurações, Atualizar & Segurança, Windows Programa Insider, selecione **Canal deV**.

2. Configurações, Atualizar & Segurança, Windows Atualização, **Verificar se há atualizações.**

## <a name="ffu-download-and-flash-directions"></a>Instruções de download e flash do FFU

Para testar com um voo assinado ffu, primeiro você precisa desbloquear seu dispositivo antes de piscar o voo com sinal ffu.

1. No PC:
    1. Baixe o ffu no seu computador do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. No HoloLens – Desbloqueio de Voo: abra **Configurações** atualização & segurança Windows Programa Insider e, em  >    >   seguida, inscreva-se e reinicialize o dispositivo.

1. Flash FFU – agora você pode piscar o FFU com assinatura de voo usando ARC.

### <a name="provide-feedback-and-report-issues"></a>Fornecer comentários e relatar problemas

Use o [aplicativo Hub de Comentários](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas. Usar o Hub de Comentários garante que todas as informações de diagnóstico necessárias sejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.  Problemas com a versão em chinês e japonês HoloLens devem ser relatados da mesma maneira.

> [!NOTE]
> Certifique-se de aceitar o prompt que pergunta se você gostaria que o Hub de Comentários acessasse sua pasta Documentos (selecione **Sim** quando solicitado).

## <a name="note-for-developers"></a>Observação para desenvolvedores

Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando builds do Insider HoloLens.  Confira a [documentação HoloLens desenvolvedor para](https://developer.microsoft.com/windows/mixed-reality/development) começar. Essas mesmas instruções funcionam com builds do Insider HoloLens.  Você pode usar os mesmos builds do Unity e Visual Studio que já está usando para HoloLens desenvolvimento.

## <a name="stop-receiving-insider-builds"></a>Parar de receber builds do Insider

Se você não quiser mais receber builds insider do Windows Holographic, poderá optar quando o HoloLens estiver [](hololens-recovery.md) executando um build de produção ou recuperar seu dispositivo usando o Advanced Recovery Companion para recuperar seu dispositivo para uma versão não interna do Windows Holographic.

> [!CAUTION]
> Há um problema conhecido em que os usuários que não se registram no Insider Preview são builds depois de reinstalar manualmente um novo build de visualização experimentariam uma tela azul. Posteriormente, eles devem recuperar manualmente o dispositivo. Para obter detalhes completos sobre se você seria afetado ou não, veja mais sobre esse [problema conhecido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para verificar se o HoloLens está executando um build de produção:

1. Vá para **Configurações > Sistema > Sobre** e encontre o número de build.

1. [Consulte as notas de versão para números de build de produção](hololens-release-notes.md).

Para não fazer builds do Insider:

1. Em um HoloLens executando um build de produção, vá para Configurações > Atualizar & **Segurança > Windows Programa Insider** e selecione **Parar Builds do Insider**.

1. Siga as instruções para ressutar seu dispositivo.
