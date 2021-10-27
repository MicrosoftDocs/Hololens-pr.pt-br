---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar builds do Insider e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.
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
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351627"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às versões mais recentes do Insider Preview para HoloLens! É simples começar e [fornecer comentários](hololens-insider.md#start-receiving-insider-builds) valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Notas sobre a versão do Insider

O que há de novo e no horizonte para HoloLens? Confira essas novas atualizações que chegarão HoloLens!

### <a name="colorblind-mode"></a>Modo colorblind

Adicionado no insider build 20348.1463

O modo colorblind é útil um ótimo recurso que torna HoloLens mais acessível. O novo modo colorblind pode ser encontrado no aplicativo Configurações **em** Configurações Facilidade de Acesso  ->    ->  **Filtros de cores**. Vários novos filtros estão disponíveis. Aqui está um exemplo visual de alguns dos filtros disponíveis.

| Desativado | Cinzentos | Tritanopia |
|-----|-----------|------------|
| ![Filtro de cores desligado](images/colorblind-off.png)   | ![Escala de cinza do filtro de cores](images/colorblind-greyscale.png)         | ![Trianopia do filtro de cores](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>Correções e melhorias

- Corrigido um problema conhecido em que sempre que a energia chega [a 18%, o dispositivo desliga automaticamente de repente.](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- Melhorias ao mover o modo de plataforma ao detectar a direção para baixo.
- Corrigido um problema em torno de caixas de diálogo de atualização.
- Atualização da versão do Microsoft Edge navegador.
- Corrigido um problema em que a agregação de dados de diagnóstico opcionais não persistia a configuração escolhida na página de configurações de telemetria após uma reinicialização.
- Corrigido o problema em que os códigos QR não eram reconhecidos quando eram girados em um ângulo de 45 graus em relação ao dispositivo.

## <a name="start-receiving-insider-builds"></a>Começar a receber builds do Insider

> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize seu dispositivo para atualizar o estado e obter o build mais recente.
>
> - O comando de voz "Reinicializar dispositivo" funciona bem.
> - Você também pode escolher o botão reiniciar Configurações/Windows Programa Insider.
>
> Temos um bug no back-end que você pode ter encontrado e isso fará com que você volte ao caminho certo.

Em um HoloLens 2, vá para Configurações Atualizar &  >  **Segurança**  >  **Windows Programa Insider** e **selecione Começar.** Vincule a conta usada para se registrar como um Windows Insider.

> [!NOTE]
> Para registrar seu dispositivo em builds do Insider, você precisará habilitar a telemetria opcional. Se você ainda não tiver feito isso, abra o aplicativo Configurações, selecione Diagnóstico de Privacidade & comentários e, em seguida, selecione  ->   Dados de **diagnóstico opcionais**.

Windows insider agora está mudando para Canais. O **anel Rápido** se tornará o  Canal **deV,** o anel  Lento se tornará o Canal beta **e** o anel versão prévia se tornará o Canal de Versão **Prévia.** Veja a aparência desse mapeamento:

![Windows Explicação dos canais insider.](images/WindowsInsiderChannels.png)

Para obter mais informações, consulte [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.
Em seguida, selecione Desenvolvimento ativo **do Windows**, escolha se você gostaria de receber o Canal **de** Desenvolvimento ou Canal beta **builds** e revise os termos do programa.
Selecione **Confirmar > Reiniciar Agora** para concluir. Depois que o dispositivo for reinicializado, vá para Atualizar Configurações > & **Segurança > Verificar** se há atualizações para obter o build mais recente.

### <a name="update-error-0x80070490-work-around"></a>Erro de atualização 0x80070490 de trabalho

Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal Dev ou Beta, tente o seguinte work-around de curto prazo. Isso envolve mover seu canal interno, pegar a atualização e, em seguida, mover seu canal insider de volta.

#### <a name="stage-one---release-preview"></a>Estágio um – Versão Prévia

1. Configurações, Atualizar & Segurança, Windows Programa Insider, selecione Versão Prévia **do Canal**.

2. Configurações, Atualizar & Segurança, Windows Atualização, Verificar **se há atualizações.** Após a atualização, continue no Estágio dois.

#### <a name="stage-two---dev-channel"></a>Estágio dois – Canal dev

1. Configurações, Atualizar & Segurança, Windows Programa Insider, selecione **Canal deV**.

2. Configurações, Atualizar & Segurança, Windows Atualização, Verificar **se há atualizações.**

## <a name="ffu-download-and-flash-directions"></a>Instruções de download e flash do FFU

Para testar com um voo assinado ffu, primeiro você precisa desbloquear seu dispositivo antes de piscar o voo com sinal ffu.

1. No PC:
    1. Baixe o ffu no seu computador do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Instale o ARC (Advanced Recovery Companion) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. No HoloLens – Desbloqueio de Voo: abra Configurações Atualização & Segurança Windows Programa Insider e, em  >    >   seguida, inscreva-se e reinicialize o dispositivo.

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
> Há um problema conhecido em que os usuários que não se registram no Insider Preview são builds após a reinstalação manual de um novo build de visualização experimentariam uma tela azul. Posteriormente, eles devem recuperar manualmente o dispositivo. Para obter detalhes completos sobre se você seria afetado ou não, veja mais sobre esse [problema conhecido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Para verificar se o HoloLens está executando um build de produção:

1. Vá para **Configurações > Sistema > Sobre** e encontre o número de build.

1. [Consulte as notas de versão para números de build de produção](hololens-release-notes.md).

Para não fazer builds do Insider:

1. Em um HoloLens executando um build de produção, acesse Configurações > Atualizar & **Segurança > Windows Programa Insider** e selecione **Parar builds do Insider**.

1. Siga as instruções para ressutar seu dispositivo.
