---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar o Insider compilações e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.
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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977225"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às compilações mais recentes do insider Preview para o HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.

## <a name="windows-insider-release-notes"></a>Notas de versão do Windows Insider

Estamos empolgados para começar a comprovar novos recursos para os insideres do Windows novamente. Novas compilações serão comprovadas para os canais de desenvolvimento e beta para as atualizações mais recentes. Continuaremos a atualizar esta página à medida que adicionamos mais recursos e atualizações para nossas compilações do Windows Insider. Fique empolgado e pronto para misturar essas atualizações em sua realidade.

| Recurso                 | Descrição                | Usuários de destino | Compilação introduzida |
|-------------------------|----------------------------|--------------|------------------|
| Alterações do CSP no HoloLens | Novos CSPs para a consulta de dados | Administradores de ti    | 20348,1403                 |

### <a name="csp-changes-on-hololens"></a>Alterações do CSP no HoloLens

- Introduzido na compilação do Windows Insider, 20348,1403

#### <a name="devdetail-csp"></a>CSP DevDetail

O CSP DevDetail agora também relata o espaço de armazenamento livre no dispositivo de HoloLens. Isso deve corresponder aproximadamente ao valor mostrado na página de armazenamento de configurações do aplicativo. A seguir está o nó específico que contém essas informações.

- ./DevDetail/Ext/Microsoft/FreeStorage (somente operação GET)

#### <a name="devicestatus-csp"></a>CSP DeviceStatus

O CSP DeviceStatus agora também relata o SSID e o BSSID da rede WiFi com o qual o HoloLens está conectado ativamente. A seguir estão os nós específicos que contêm essas informações.

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

### <a name="fixes-and-improvements"></a>Correções e aprimoramentos:

- Correção de um [problema conhecido para o portal do dispositivo em que não havia prompt para baixar arquivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Correção de um [problema conhecido para o portal do dispositivo com tempo limite de upload e download de arquivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Comece a receber compilações do insider
> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize o dispositivo para atualizar o estado e obtenha a compilação mais recente.
> - O comando de voz "reinicializar dispositivo" funciona bem. 
> - Você também pode escolher o botão reiniciar em configurações/programa do Windows Insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso o levará de volta ao controle.

Em um dispositivo de HoloLens 2, vá para **configurações**  >  **atualização &**  >  **programa Windows Insider** de segurança e selecione **introdução**. Vincule a conta que você usou para se registrar como um Windows Insider.
O Windows Insider agora está migrando para os canais. O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta** e o anel de **versão prévia** se tornará o **canal versão prévia**. Esta é a aparência desse mapeamento: os ![ canais do Windows Insider explicações ](images/WindowsInsiderChannels.png) para obter mais informações, consulte [apresentando canais do Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) em Blogs do Windows.
Em seguida, selecione **desenvolvimento ativo do Windows**, escolha se deseja receber as compilações do canal de **desenvolvimento** ou **beta** e examine os termos do programa.
Selecione **confirmar > reiniciar agora** para concluir. Depois que o dispositivo for reinicializado, vá para **configurações > atualização & segurança > verificar se há atualizações** para obter a compilação mais recente.
### <a name="update-error-0x80070490-work-around"></a>Erro de atualização 0x80070490 solução alternativa
Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal de desenvolvimento ou beta, tente a seguinte solução alternativa de curto prazo. Ele envolve mover seu canal Insider, selecionando a atualização e, em seguida, movendo o canal Insider de volta.
#### <a name="stage-one---release-preview"></a>Estágio One-Release versão prévia
1.  Configurações, atualização & segurança, programa Windows Insider, selecione **liberar canal de versão prévia**.
2.  Configurações, atualização & segurança, Windows Update, **verificar se há atualizações**. Após a atualização, continue no estágio dois.
#### <a name="stage-two---dev-channel"></a>Preparar canal de dois desenvolvedores
1. Configurações, atualização & segurança, programa Windows Insider, selecionar **canal de desenvolvimento**.
2. Configurações, atualização & segurança, Windows Update, **verificar se há atualizações**.
## <a name="ffu-download-and-flash-directions"></a>Download do FFU e direções do flash
Para testar com um FFU assinado por voo, primeiro você precisará desbloquear o dispositivo antes de atualizar o FFU assinado por voo.
1. No PC:
    1. Baixe o FFU para o seu PC do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale o ARC (complemento de recuperação avançada) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Em HoloLens-Flight Unlock: Open **Settings**  >  **Update & Security**  >  **Insider Program** , Inscreva-se, reinicie o dispositivo.
1. Flash FFU – agora você pode piscar o FFU assinado por voo usando o ARC.
### <a name="provide-feedback-and-report-issues"></a>Fornecer comentários e relatar problemas
Use [o aplicativo de Hub de comentários](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas. O uso do hub de comentários garante que todas as informações de diagnóstico necessárias estejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.  Problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.
> [!NOTE]
> Lembre-se de aceitar o prompt que pergunta se você deseja que o Hub de comentários acesse sua pasta documentos (selecione **Sim** quando solicitado).
## <a name="note-for-developers"></a>Observação para desenvolvedores
Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando compilações internas do HoloLens.  Confira a [documentação do desenvolvedor do HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para começar. Essas mesmas instruções funcionam com compilações internas do HoloLens.  Você pode usar as mesmas compilações do Unity e do Visual Studio que já está usando para o desenvolvimento do HoloLens.
## <a name="stop-receiving-insider-builds"></a>Parar de receber compilações do insider
Se você não deseja mais receber compilações internas do Windows Holographic, pode recusar quando o seu HoloLens está executando uma compilação de produção ou pode [recuperar seu dispositivo](hololens-recovery.md) usando o complemento de recuperação avançada para recuperar seu dispositivo para uma versão não Insider do Windows Holographic.
> [!CAUTION]
> Há um problema conhecido em que os usuários que cancelam o registro do insider Preview são criados após a reinstalação manual de uma nova versão de visualização que teria uma tela azul. Depois, eles devem recuperar manualmente seu dispositivo. Para obter detalhes completos sobre se você for afetado ou não, veja mais sobre esse [problema conhecido](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).
Para verificar se o seu HoloLens está executando uma compilação de produção:
1. Vá para **configurações > > do sistema** e localize o número da versão.
1. [Consulte as notas de versão para obter os números de Build de produção](hololens-release-notes.md).
Para recusar compilações internas:
1. Em um HoloLens executando uma compilação de produção, vá para **configurações > atualização & segurança > programa Windows Insider** e selecione **parar compilações do insider**.
1. Siga as instruções para recusar seu dispositivo.
