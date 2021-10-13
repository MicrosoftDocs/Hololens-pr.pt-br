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
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924352"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às compilações mais recentes do insider Preview para HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas de versão do insider

Estamos empolgados em que todos os nossos recursos recentes do insider já ficaram públicos! Se você quiser ler sobre isso, dê uma olhada na [página notas de versão](hololens-release-notes.md)

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
