---
title: Atualizar o HoloLens
description: Verifique o número do Build do seu HoloLens, atualize e Reverta as atualizações.
keywords: instruções, atualizar, reverter, HoloLens, verificar compilação, número da compilação
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827537"
---
# Atualizar o HoloLens

O HoloLens usa o Windows Update, assim como outros dispositivos Windows 10. Seu HoloLens fará automaticamente o download e a instalação das atualizações do sistema sempre que estiver conectado à rede e conectado à Internet, mesmo quando estiver em standby.

Este artigo examinará as ferramentas do HoloLens para:

- exibindo a versão do sistema operacional atual (número da compilação)
- verificando se há atualizações
- atualizando manualmente o HoloLens
- reverter para uma atualização mais antiga

## Verificar a versão do sistema operacional (número da compilação)

Você pode verificar o número da versão do sistema (número do Build) abrindo o aplicativo Configurações e selecionando o **sistema**  >  **About**.

## Verificar se há atualizações e atualizar manualmente

Você pode verificar se há atualizações a qualquer momento em configurações.  Para ver as atualizações disponíveis e verificar se há novas atualizações:

1. Abra o aplicativo **configurações** .
1. Navegue até **Atualizar &**  >  **atualização do Windows**Security.
1. Selecione **verificar se há atualizações**.

Se houver uma atualização disponível, o download da nova versão será iniciado. Depois que o download for concluído, selecione o botão **reiniciar agora** para disparar a instalação. Se o seu dispositivo estiver abaixo de 40% e não estiver conectado, reiniciar não iniciará a instalação da atualização.

Enquanto o HoloLens estiver instalando a atualização, ele exibirá as engrenagens giradas e um indicador de progresso. Não desative seu HoloLens durante esse período. Ele será reiniciado automaticamente quando concluir a instalação.

O HoloLens aplica uma atualização de cada vez.  Se o seu HoloLens for mais de uma versão por trás do mais recente, talvez seja necessário executar o processo de atualização várias vezes para obtê-lo totalmente atualizado.

## Voltar para uma versão anterior-HoloLens 2

Em alguns casos, talvez você queira voltar para uma versão anterior do software HoloLens. Você pode fazer isso usando o complemento de recuperação avançada para redefinir seu HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar para uma versão anterior do HoloLens 2, siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao seu computador.
1. Em seu computador, baixe o [complemento avançado de recuperação](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).
1. Quando tiver terminado esses downloads, abra o download do **Explorador de arquivos**  >  **Downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **Extrair tudo** > **Extrair** para descompactar.
1. Conecte seu HoloLens ao PC usando um cabo USB-A para USB-C. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).
1. O complemento de recuperação avançada detecta automaticamente seu HoloLens. Selecione o bloco **Microsoft HoloLens** .
1. Na tela seguinte, selecione **seleção de pacote manual** e, em seguida, selecione o arquivo de instalação contido na pasta descompactada na etapa 4. (Procure um arquivo com a extensão. FFU.)
1. Selecione **instalar software**e siga as instruções.

## Voltar para uma versão anterior-HoloLens (1ª gen)

Em alguns casos, talvez você queira voltar para uma versão anterior do software HoloLens. Você pode fazer isso usando a ferramenta de recuperação de dispositivos do Windows para redefinir o HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar para uma versão anterior do HoloLens 1, siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao seu computador.
1. Em seu computador, baixe a [ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Baixe o [pacote de recuperação de atualização de aniversários do HoloLens](https://aka.ms/hololensrecovery).
1. Quando o download for concluído, abra o download do **Explorador de arquivos**  >  **Downloads**. Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **extrair toda**  >  **extração** para descompactá-la.
1. Conecte seu HoloLens ao PC usando o cabo micro USB com o qual ele veio. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).
1. O WDRT detectará automaticamente seu HoloLens. Selecione o bloco **Microsoft HoloLens** .
1. Na tela seguinte, selecione **seleção de pacote manual** e escolha o arquivo de instalação contido na pasta descompactada na etapa 4. (Procure um arquivo com a extensão. FFU.)
1. Selecione **instalar software**e siga as instruções.

> [!NOTE]
> Se o WDRT não detectar o seu HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **meu dispositivo não foi detectado**, selecione **Microsoft HoloLens**e siga as instruções.

## Programa Windows Insider no HoloLens

Deseja ver os recursos mais recentes do HoloLens?  Em caso afirmativo, participe do programa Windows Insider; Você obterá acesso às versões prévias das atualizações de software do HoloLens antes que elas estejam disponíveis para o público em geral.

[Obtenha o Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).
