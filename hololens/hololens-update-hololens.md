---
title: Atualizar o HoloLens
description: Saiba como verificar o número de build do HoloLens, se manter atualizado com as atualizações de dispositivo, ingressar no Programa Insiders e reverter as atualizações.
keywords: how-to, update, roll back, HoloLens, check build, build number
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283932"
---
# Atualizar o HoloLens

O HoloLens usa o Windows Update, assim como outros dispositivos Windows 10. O HoloLens baixará e instalará automaticamente as atualizações do sistema sempre que estiver conectado à energia e conectado à Internet, mesmo quando estiver em modo de espera.

Este artigo passará pelas ferramentas do HoloLens para:

- exibindo sua versão atual do sistema operacional (número de com build)
- verificando se há atualizações
- atualizar manualmente o HoloLens
- reverter para uma atualização mais antiga

## Verificar a versão do sistema operacional (número de build)

Você pode verificar o número de versão do sistema,(número da com build) abrindo o aplicativo Configurações e selecionando **System**  >  **About**.

## Verificar se há atualizações e atualizar manualmente

Você pode verificar se há atualizações a qualquer momento nas configurações.  Para ver as atualizações disponíveis e verificar se há novas atualizações:

1. Abra o **aplicativo Configurações.**
1. Navegue até **Atualizar & Segurança**do Windows  >  **Update.**
1. Selecione **Verificar se há atualizações.**

Se uma atualização estiver disponível, ela começará a baixar a nova versão. Depois que o download for concluído, selecione o **botão Reiniciar** Agora para disparar a instalação. Se o dispositivo estiver abaixo de 40% e não estiver conectado, a reinicialização não começará a instalar a atualização.

Enquanto o HoloLens estiver instalando a atualização, ele exibirá engrenagens giradas e um indicador de progresso. Não desligue o HoloLens durante esse período. Ele será reiniciado automaticamente depois de concluir a instalação.

O HoloLens aplica uma atualização por vez.  Se o HoloLens estiver mais de uma versão atrás da mais recente, talvez seja necessário executar o processo de atualização várias vezes para que ele fique totalmente atualizado.

## Voltar para uma versão anterior - HoloLens 2

Em alguns casos, talvez você queira voltar a uma versão anterior do software do HoloLens. Você pode fazer isso usando o Advanced Recovery Companion para redefinir seu HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens 2, siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.
1. Em seu computador, baixe o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) da Microsoft Store.
1. Baixe a [versão mais recente do HoloLens 2](https://aka.ms/hololens2download).
1. Quando terminar esses downloads, abra Downloads **do Explorador de**  >  **Arquivos.** Clique com o botão direito do mouse na pasta compactada que você acabou de baixar e selecione **Extrair tudo** > **Extrair** para descompactar.
1. Conecte seu HoloLens ao computador usando um cabo USB-A para USB-C. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).
1. O Advanced Recovery Companion detecta automaticamente seu HoloLens. Selecione o bloco **Microsoft HoloLens**.
1. Na tela seguinte, selecione **Seleção manual** de pacote e, em seguida, selecione o arquivo de instalação contido na pasta que você desempiou na etapa 4. (Procure um arquivo com a extensão .ffu.)
1. Selecione **Instalar software**e siga as instruções.

## Voltar para uma versão anterior - HoloLens (1ª geração)

Em alguns casos, talvez você queira voltar a uma versão anterior do software do HoloLens. Você pode fazer isso usando a Ferramenta de Recuperação de Dispositivos windows para redefinir seu HoloLens para a versão anterior.

> [!NOTE]
> Voltar para uma versão anterior exclui seus arquivos pessoais e configurações.

Para voltar a uma versão anterior do HoloLens 1, siga estas etapas:

1. Certifique-se de que você não tenha telefones ou dispositivos Windows conectados ao computador.
1. Em seu computador, baixe a Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Baixe o [Pacote de recuperação de Atualização de Aniversário do HoloLens](https://aka.ms/hololensrecovery).
1. Quando os downloads terminarem, abra **Downloads do**  >  **Explorador de Arquivos.** Clique com o botão direito do mouse na pasta de recortar que você acabou de baixar e selecione **Extrair tudo**  >  **para** descompcompletá-la.
1. Conecte seu HoloLens ao computador usando o cabo micro USB que ele veio com ele. (Mesmo que você esteja usando outros cabos para conectar o HoloLens, esse funciona melhor).
1. O WDRT detectará automaticamente seu HoloLens. Selecione o bloco **Microsoft HoloLens**.
1. Na tela seguinte, selecione **Seleção manual de** pacote e escolha o arquivo de instalação contido na pasta descortada na etapa 4. (Procure um arquivo com a extensão .ffu.)
1. Selecione **Instalar software**e siga as instruções.

> [!NOTE]
> Se o WDRT não detectar seu HoloLens, tente reiniciar o computador. Se isso não funcionar, selecione **Meu dispositivo não foi detectado**, selecione **Microsoft HoloLens** e siga as instruções.

## Programa Windows Insider no HoloLens

Deseja ver os recursos mais recentes no HoloLens?  Em caso sim, participe do Programa Windows Insider; você terá acesso às builds de visualização das atualizações de software do HoloLens antes que elas tenham acesso ao público em geral.

[Obter a visualização do Windows Insider para Microsoft HoloLens](hololens-insider.md).
