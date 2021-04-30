---
title: Atualizar o HoloLens
description: Saiba como verificar seu número de Build do HoloLens, manter-se atualizado com as atualizações do dispositivo, ingressar no programa de pessoas e reverter atualizações.
keywords: como fazer, atualizar, reverter, HoloLens, verificar compilação, número de Build
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308141"
---
# <a name="update-hololens"></a>Atualizar o HoloLens

O HoloLens usa Windows Update, assim como outros dispositivos Windows 10. Seu HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que ele estiver conectado à energia e conectado à Internet, mesmo quando ela estiver em espera.

Este artigo apresentará as ferramentas do HoloLens para:

- exibindo a versão atual do sistema operacional (número da versão)
- verificando se há atualizações
- atualizando manualmente o HoloLens
- reverter para uma atualização mais antiga

## <a name="check-your-operating-system-version-build-number"></a>Verificar a versão do sistema operacional (número da versão)

Você pode verificar o número de versão do sistema, (número da compilação) abrindo o aplicativo Configurações e selecionando **sistema**  >  **sobre**.

## <a name="check-for-updates-and-manually-update"></a>Verificar se há atualizações e atualizar manualmente

Você pode verificar se há atualizações a qualquer momento nas configurações.  Para ver as atualizações disponíveis e verificar se há novas atualizações:

1. Abra o aplicativo **Configurações**.
1. Navegue até **Atualizar & segurança**  >  **Windows Update**.
1. Selecione **Verificar se há atualizações**.

Se uma atualização estiver disponível, ela começará a baixar a nova versão. Após a conclusão do download, selecione o botão **reiniciar agora** para disparar a instalação. Se o dispositivo estiver abaixo de 40% e não conectado, a reinicialização não iniciará a instalação da atualização.

Enquanto o seu HoloLens está instalando a atualização, ele exibirá engrenagens giratórias e um indicador de progresso. Não desative seu HoloLens durante esse tempo. Ele será reiniciado automaticamente após a conclusão da instalação.

O HoloLens aplica uma atualização por vez.  Se o seu HoloLens for mais de uma versão por trás do mais recente, talvez seja necessário executar o processo de atualização várias vezes para atualizá-lo completamente.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Voltar para uma versão anterior – HoloLens 2

Em alguns casos, talvez você queira voltar para uma versão anterior do software do HoloLens. Você pode fazer isso usando o complemento de recuperação avançada para redefinir o HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar para uma versão anterior do HoloLens 2, siga estas etapas:

1. Certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.
1. No seu computador, baixe o [complemento de recuperação avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) do Microsoft Store.
1. Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).
1. Depois de concluir esses downloads, abra o **Explorador de arquivos**  >  **downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.
1. Conecte seu HoloLens ao seu PC usando um USB-a para um cabo USB-C. (Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)
1. O complemento de recuperação avançada detecta automaticamente seu HoloLens. Selecione o bloco **Microsoft HoloLens** .
1. Na próxima tela, selecione **seleção de pacote manual** e, em seguida, selecione o arquivo de instalação contido na pasta que você descompactou na etapa 4. (Procure um arquivo com a extensão. FFU.)
1. Selecione **instalar software** e siga as instruções.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Voltar para uma versão anterior – HoloLens (1ª gen)

Em alguns casos, talvez você queira voltar para uma versão anterior do software do HoloLens. Você pode fazer isso usando a ferramenta de recuperação de dispositivo do Windows para redefinir o HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar para uma versão anterior do HoloLens 1, siga estas etapas:

1. Certifique-se de que você não tem telefones ou dispositivos Windows conectados ao seu PC.
1. Em seu computador, baixe a [ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Baixe o [pacote de recuperação de atualização de aniversário do HoloLens](https://aka.ms/hololensrecovery).
1. Quando o download for concluído, abra o **Explorador de arquivos**  >  **downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  a **extração** para descompactá-la.
1. Conecte seu HoloLens ao seu PC usando o cabo micro USB com o qual ele veio. (Mesmo que você esteja usando outros cabos para conectar seu HoloLens, isso funciona melhor.)
1. O WDRT detectará automaticamente seu HoloLens. Selecione o bloco **Microsoft HoloLens** .
1. Na próxima tela, selecione **seleção de pacote manual** e escolha o arquivo de instalação contido na pasta descompactada na etapa 4. (Procure um arquivo com a extensão. FFU.)
1. Selecione **instalar software** e siga as instruções.

> [!NOTE]
> Se o WDRT não detectar seu HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **meu dispositivo não foi detectado**, selecione **Microsoft HoloLens** e siga as instruções.

## <a name="windows-insider-program-on-hololens"></a>Programa Windows Insider no HoloLens

Deseja ver os recursos mais recentes no HoloLens?  Nesse caso, junte-se ao programa Windows Insider; Você terá acesso a versões prévias de atualizações de software do HoloLens antes que elas estejam disponíveis para o público geral.

[Obtenha o Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).
