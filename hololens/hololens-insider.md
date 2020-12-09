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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 260b195a18ecb7fe05d819fcd3e86d56fc2022bf
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201335"
---
# Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às versões mais recentes do insider Preview para HoloLens! É fácil [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários importantes para a nossa próxima atualização de sistema operacional para o HoloLens.

## Notas da versão do Windows Insider

Recentemente, lançamos todos os recursos do Windows Insider. Como todos esses recursos agora estão disponíveis em geral, recomendamos que você leia nossas [notas de lançamento](hololens-release-notes.md) para ver todos os nossos recursos mais recentes. Continue verificando aqui para ver quando começamos a aprimorar novos recursos interessantes para experimentar!

## Comece a receber Builds do insider

> [!NOTE]
> Se você não atualizou recentemente, reinicialize o seu dispositivo para atualizar o estado e obtenha a compilação mais recente.
> - O comando de voz "reinicializar dispositivo" funciona bem. 
> - Você também pode escolher o botão de reinicialização no programa configurações/Windows Insider.
>
> Tivemos um bug no back-end que você pode ter encontrado e isso permitirá que você se retorne ao caminho.

Em um dispositivo HoloLens 2, vá para **configurações**  >  **Update &**  >  programa de segurança do**Windows Insider** e selecione **introdução**. Vincule a conta que você usou para se registrar como um Windows Insider.

O Windows Insider agora está migrando para canais. O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta**, e o anel de **versão de pré-lançamento** se tornará o canal de visualização de **lançamento**. Veja como é a aparência do mapeamento:

![Explicação de canais do Windows Insider](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [apresentando os canais do Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) nos Blogs do Windows.

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
