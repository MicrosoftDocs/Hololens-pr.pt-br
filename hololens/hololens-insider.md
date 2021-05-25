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
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397817"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versão prévia do Insider para Microsoft HoloLens

Bem-vindo às compilações mais recentes do insider Preview para o HoloLens! É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para o HoloLens.

## <a name="windows-insider-release-notes"></a>Notas de versão do Windows Insider

Estamos empolgados para começar a comprovar novos recursos para os insideres do Windows novamente. Novas compilações serão comprovadas para os canais de desenvolvimento e beta para as atualizações mais recentes. Continuaremos a atualizar esta página à medida que adicionamos mais recursos e atualizações para nossas compilações do Windows Insider. Fique empolgado e pronto para misturar essas atualizações em sua realidade. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>Carregamento de rolo de câmera do OneDrive for Work ou School

*Introduzido na Build 20346,1402*

Adicionamos um novo recurso ao aplicativo de configurações do HoloLens 2, que permite aos clientes carregar automaticamente fotos e vídeos de realidade misturada das imagens do dispositivo > pasta de rolagem da câmera para a pasta do OneDrive for Work ou School correspondente. Esse recurso aborda uma [lacuna de recursos no aplicativo onedrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) no HoloLens 2, que dá suporte apenas ao carregamento automático da câmera para o conta Microsoft pessoal de um cliente (e não a sua conta corporativa ou de estudante).

**Como funciona**

- Visite **configurações > sistema > a câmera de realidade mista** para habilitar o "carregamento da câmera".
- Ao definir esse recurso como a posição **on** , qualquer foto ou vídeo da realidade misturada capturada em seu dispositivo será automaticamente enfileirado para carregamento para as imagens > pasta de distribuição da câmera de sua conta do onedrive for Work ou School.
    >[!NOTE]
    >Fotos e vídeos capturados antes de habilitar esse recurso *não serão* enfileirados para carregamento e ainda precisarão ser carregados manualmente.
- Uma mensagem de status na página Configurações exibirá o número de arquivos com carregamento pendente (ou leitura "o OneDrive está atualizado" quando todos os arquivos pendentes tiverem sido carregados).
- Se estiver preocupado com a largura de banda ou se quiser fazer o upload de "pausa" por qualquer motivo, você poderá alternar o recurso para a posição **desativado** . Desabilitar temporariamente o recurso garante que a fila de upload continuará aumentando conforme você adicionar novos arquivos à pasta Roll da Câmera, mas os arquivos não serão carregados até que você reabilitar o recurso.
- Os arquivos mais novos serão carregados primeiro (último a entrar, primeiro a sair).
- Se sua conta do OneDrive tiver problemas (por exemplo, após **a** alteração da senha), um botão Corrigir agora será exibido na página Configurações.
- Não há nenhum tamanho máximo de arquivo, mas observe que arquivos grandes levarão mais tempo para carregar (especialmente se a largura de banda de upload estiver restrita). Se você "pausar" ou desativar o upload enquanto um arquivo grande estiver sendo carregado, ele cancelará imediatamente o upload. O upload será reiniciado quando você reabilitar o recurso; você não perderá nenhum arquivo, mas o upload parcial será descartado.

**Problemas conhecidos e advertências**

- Essa configuração não tem limitação criada com base no uso de largura de banda atual. Se você precisar maximizar a largura de banda para outro cenário, desligue a configuração manualmente. O upload será pausado, mas o recurso continuará a monitorar os arquivos recém-adicionados ao Roll da Câmera. Reabilitar o upload quando estiver pronto para continuar.
- Esse recurso deve ser habilitado para cada conta de usuário no dispositivo e só pode carregar ativamente arquivos para o usuário conectado no momento ao dispositivo.
- Se você estiver fazendo fotos ou vídeos enquanto observa a contagem de upload na página Configurações em tempo real, observe que a contagem de arquivos pendentes pode não mudar até que o arquivo atual tenha concluído o carregamento.
- O upload será pausado se o dispositivo ficar inodor ou estiver desligado. Para garantir que os uploads pendentes são concluídos, use ativamente o dispositivo até que a página Configurações leia "O OneDrive está atualizado" ou ajuste as configurações de sleep **do Power &.**

## <a name="start-receiving-insider-builds"></a>Começar a receber builds do Insider
> [!NOTE]
> Se você não tiver atualizado recentemente, reinicialize seu dispositivo para atualizar o estado e obter o build mais recente.
> - O comando de voz "Reinicializar dispositivo" funciona bem. 
> - Você também pode escolher o botão reiniciar em Configurações/Programa Windows Insider.
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
> Há um problema conhecido em que os usuários que não se registram no Insider Preview são builds depois de reinstalar manualmente um novo build de visualização experimentariam uma tela azul. Posteriormente, eles devem recuperar manualmente o dispositivo. Para obter detalhes completos sobre se você for afetado ou não, veja mais sobre esse [problema conhecido](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).
Para verificar se o seu HoloLens está executando uma compilação de produção:
1. Vá para **configurações > > do sistema** e localize o número da versão.
1. [Consulte as notas de versão para obter os números de Build de produção](hololens-release-notes.md).
Para recusar compilações internas:
1. Em um HoloLens executando uma compilação de produção, vá para **configurações > atualização & segurança > programa Windows Insider** e selecione **parar compilações do insider**.
1. Siga as instruções para recusar seu dispositivo.
