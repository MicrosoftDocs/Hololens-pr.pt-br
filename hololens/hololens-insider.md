---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar builds do Insider e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924359"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo aos builds mais recentes do Insider Preview para HoloLens! É simples começar e [fornecer comentários](hololens-insider.md#start-receiving-insider-builds) valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.

## <a name="windows-insider-release-notes"></a>notas Participante do Programa Windows Insider versão do Participante do Programa Windows Insider

Estamos empolgados em iniciar o voo de novos recursos para o Windows Insiders novamente. Novos builds serão disponibilizados para os Canais Dev e Beta para as atualizações mais recentes. Continuaremos a atualizar essa página à medida que adicionarmos mais recursos e atualizações às nossas Participante do Programa Windows Insider builds. Fique animado e pronto para misturar essas atualizações em sua realidade. 

### <a name="csp-changes-on-hololens"></a>Alterações do CSP no HoloLens
 
- Introduzido no Participante do Programa Windows Insider build, 20348.1403

#### <a name="devdetail-csp"></a>CSP DevDetail

O CSP de DevDetail agora também relata espaço de armazenamento livre no dispositivo HoloLens. Isso deve corresponder aproximadamente ao valor mostrado na página Armazenamento do Aplicativo de Configurações. A seguir está o nó específico que contém essas informações.

- ./DevDetail/Ext/Microsoft/FreeStorage (somente operação GET)

#### <a name="devicestatus-csp"></a>CSP DeviceStatus

O CSP do DeviceStatus agora também relata SSID e BSSID da rede Wifi com a qual o HoloLens está conectado ativamente. A seguir estão os nós específicos que contêm essas informações.

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

### <a name="fixes-and-improvements"></a>Correções e melhorias:

- Corrigido um [problema conhecido para Portal de Dispositivos em que não havia nenhum prompt baixando arquivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Corrigido um problema conhecido para o Portal de Dispositivos com tempos de carregamento e [download de arquivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Começar a receber builds do Insider
> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize seu dispositivo para atualizar o estado e obter o build mais recente.
> - O comando de voz "Reinicializar dispositivo" funciona bem. 
> - Você também pode escolher o botão reiniciar em Configurações/Programa Windows Insider.
>
> Temos um bug no back-end que você pode ter encontrado e isso fará com que você volte ao caminho certo.

Em um dispositivo HoloLens 2, vá para **Configurações** Atualizar  >  **& segurança**  >  **Programa Windows Insider** e **selecione Começar.** Vincule a conta usada para se registrar como um Participante do Programa Windows Insider.
O Windows Insider agora está mudando para Canais. O **anel Rápido** se tornará o  Canal **deV,** o anel Lento  se tornará o Canal beta **e** o anel versão prévia de versão se tornará **o** Canal de Versão Prévia. Veja a aparência desse mapeamento: explicação Participante do Programa Windows Insider Canais para obter mais informações, consulte ![ ](images/WindowsInsiderChannels.png) Introdução Participante do Programa Windows Insider [canais](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) em blogs do Windows.
Em seguida, selecione Desenvolvimento ativo do **Windows,** escolha se você gostaria de receber o Canal **de** Desenvolvimento **ou** Canal beta builds e revise os termos do programa.
Selecione **Confirmar > Reiniciar Agora** para concluir. Depois que o dispositivo for reinicializado, vá para Configurações > Atualizar & **Segurança > Verificar** se há atualizações para obter o build mais recente.
### <a name="update-error-0x80070490-work-around"></a>Erro de 0x80070490 para resolver o erro
Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, tente a seguinte explicação de curto prazo. Isso envolve mover seu canal interno, pegar a atualização e, em seguida, mover seu canal insider de volta.
#### <a name="stage-one---release-preview"></a>Estágio um – Versão Prévia
1.  Configurações, Atualizar & Segurança, Programa Windows Insider, selecione **Versão** Prévia do Canal .
2.  Configurações, Atualizar & Segurança, Windows Update, **Verificar se há atualizações.** Após a atualização, continue no Estágio dois.
#### <a name="stage-two---dev-channel"></a>Estágio dois – Canal dev
1. Configurações, Atualizar & Segurança, Programa Windows Insider, selecione **Canal deV**.
2. Configurações, Atualizar & Segurança, Windows Update, **Verificar se há atualizações.**
## <a name="ffu-download-and-flash-directions"></a>Instruções de download e flash do FFU
Para testar com um voo assinado ffu, primeiro você precisa desbloquear seu dispositivo antes de piscar o voo com sinal ffu.
1. No PC:
    1. Baixe o ffu no seu computador do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (Advanced Recovery Companion) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. No HoloLens – Desbloqueio de Voo: Abrir Configurações Atualize &   >  **Segurança**  >  **Programa Windows Insider,** em seguida, inscreva-se e reinicialize o dispositivo.
1. Flash FFU – agora você pode piscar o FFU com assinatura de voo usando ARC.
### <a name="provide-feedback-and-report-issues"></a>Fornecer comentários e relatar problemas
Use o [aplicativo Hub de Comentários](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas. Usar o Hub de Comentários garante que todas as informações de diagnóstico necessárias sejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.  Problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.
> [!NOTE]
> Certifique-se de aceitar o prompt que pergunta se você gostaria que o Hub de Comentários acessasse sua pasta Documentos (selecione **Sim** quando solicitado).
## <a name="note-for-developers"></a>Observação para desenvolvedores
Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando builds insider do HoloLens.  Confira a [Documentação do Desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com builds insider do HoloLens.  Você pode usar os mesmos builds do Unity e Visual Studio que já está usando para o desenvolvimento do HoloLens.
## <a name="stop-receiving-insider-builds"></a>Parar de receber builds do Insider
Se você não quiser mais receber builds insider do Windows Holographic, poderá optar quando o [](hololens-recovery.md) HoloLens estiver executando um build de produção ou recuperar seu dispositivo usando o Advanced Recovery Companion para recuperar seu dispositivo para uma versão não insider do Windows Holographic.
> [!CAUTION]
> Há um problema conhecido em que os usuários que não se registram no Insider Preview são builds depois de reinstalar manualmente um novo build de visualização experimentariam uma tela azul. Posteriormente, eles devem recuperar manualmente o dispositivo. Para obter detalhes completos sobre se você seria afetado ou não, veja mais sobre esse [problema conhecido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Para verificar se o HoloLens está executando um build de produção:
1. Vá para **Configurações > Sistema > Sobre** e encontre o número de build.
1. [Consulte as notas de versão para números de build de produção](hololens-release-notes.md).
Para não fazer builds do Insider:
1. Em um HoloLens executando um build de produção, acesse Configurações > Atualizar & **Segurança > Programa Windows Insider** e selecione **Parar Builds do Insider**.
1. Siga as instruções para ressutar seu dispositivo.
