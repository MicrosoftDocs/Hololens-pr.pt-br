---
title: Reiniciar, redefinir ou recuperar o HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Como usar a Windows Device Recovery Tool para mostrar uma imagem para o HoloLens de 1ª geração.
keywords: como fazer, reinicializar, redefinir, recuperar, reinicialização forçada, reinicialização flexível, ciclo de energia, HoloLens, desligar, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 837a019f110a58c490618d3d5c47e83e58231d18
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827535"
---
# Reiniciar, redefinir ou recuperar o HoloLens de 1ª geração

Se você estiver enfrentando problemas com o seu HoloLens, talvez seja necessário tentar uma reinicialização, redefinição ou, até mesmo, ire-instalar a partir de uma imagem do sistema utilizando a recuperação de dispositivos.

Aqui estão algumas coisas a serem feitas se o seu HoloLens não estiver funcionando corretamente.  Este artigo o orientará pelas etapas de recuperação recomendadas.

Se você estiver tentando recuperar um HoloLens 2, confira a página para [Recuperar um HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), uma vez que há diferenças nos processos.

Esse artigo se concentra no software e dispositivo do HoloLens, se os hologramas não aparecerem corretamente, [este artigo](hololens-environment-considerations.md) fala sobre fatores ambientais que melhoram a qualidade do holograma.

## Reiniciar

### Executar uma reinicialização segura usando a Cortana

A maneira mais segura de reiniciar o HoloLens é usar a Cortana. Geralmente, essa é uma primeira etapa fácil de seguir quando ocorrer um problema com o HoloLens. 

> [!NOTE]
> A Cortana não está disponível em todos os dispositivos. A Cortana está disponível a todos os dispositivos do HoloLens (1ª geração).
> A Cortana está disponível em dispositivos do HoloLens 2 em uma compilação anterior à atualização do Windows Holograpic, versão 2004.

1. Instale no seu dispositivo
1. Certifique-se de que ele está ligado, que um usuário está conectado e o dispositivo não está aguardando que uma senha seja desbloqueada.
1. Diga "Ei Cortana, reinicializar" ou "Ei Cortana, reiniciar".
1. Quando ela reconhecer, solicitará a confirmação. Aguarde um pouco para que um som seja reproduzido após concluir a pergunta, indicando que ele está ouvindo você e, em seguida, diga "Sim".
1. O dispositivo será reiniciado agora.

### Execute uma reinicialização segura usando a Cortana

Se ainda não conseguir reiniciar o dispositivo, você pode tentar reiniciá-lo usando o botão de ligar:

1. Pressione e mantenha pressionado o botão de energia por cinco segundos.
   1. Após um segundo, você verá todos os cinco LEDs iluminando e, em seguida, desativando devagar da direita para a esquerda.
   1. Após cinco segundos, todos os LEDs estarão inativos, indicando que o comando de desligamento foi emitido com sucesso.
   1. Observe que é importante parar de pressionar o botão imediatamente após todos os LEDs terem desativado.
1. Aguarde um minuto para que o desligamento seja bem-sucedido. Observe que o desligamento ainda pode estar em andamento, mesmo que os monitores estejam desativados.
1. Ligue o dispositivo novamente mantendo o botão de ligar por um segundo.

### Executar uma reinicialização segura usando o Portal de Dispositivos do Windows

> [!NOTE]
> Para fazer isso, o HoloLens deve ser configurado como um dispositivo desenvolvedor.  
> Leia mais sobre [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Se o procedimento anterior não funcionar, você pode tentar reiniciar o dispositivo usando [Portal de Dispositivos do Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). No canto superior direito, há uma opção para reiniciar ou desligar o dispositivo.

### Executar uma reinicialização forçada sem segurança

Caso nenhum dos métodos anteriores conseguir reiniciar o dispositivo com êxito, você pode forçar uma reinicialização. Esse método é equivalente a puxar a bateria do HoloLens.  É uma operação perigosa, o que pode deixar o seu dispositivo em um estado corrompido.  Se isso acontecer, você precisará ligar e desligar o seu HoloLens.  

> [!WARNING]
> Esse é um método potencialmente nocivo e só deve ser usado no caso de nenhum dos métodos acima.

1. Pressione e mantenha pressionado o botão de energia por pelo menos dez segundos.
   - Não há problema em manter o botão por mais de 10 segundos.
   - É seguro ignorar qualquer atividade do LED.
1. Solte o botão e aguarde dois ou três segundos.
1. Ligue o dispositivo novamente mantendo o botão de ligar por um segundo.
Se você ainda estiver enfrentando problemas, pressione o botão de ligar por quatro segundos até que todos os indicadores de bateria apareçam gradualmente e a tela pare de exibir os hologramas. Aguarde um minuto e, em seguida, pressione o botão de ligar novamente para ativar o dispositivo.

## Redefinir para as configurações de fábrica

> [!NOTE]
> A bateria precisa de pelo menos 40% da carga para redefinir.

Se o seu HoloLens ainda estiver enfrentando problemas após reiniciar, tente redefini-lo para as configurações de fábrica.  A redefinição do HoloLens mantém a versão do software do Windows Holographic que está instalada nele e retorna tudo para as configurações de fábrica.

Se você reiniciar seu dispositivo, todos os seus dados pessoais, aplicativos e configurações serão apagados, incluindo a redefinição do TPM. A redefinição instalará apenas a versão mais recente do Windows Holographic e será preciso refazer todas as etapas de inicialização (calibragem, conectar ao Wi-Fi, criar uma conta de usuário, baixar aplicativos e assim por diante).

1. Inicie o aplicativo de Configurações e, em seguida, selecione **Atualizar** > **Redefinir**.
1. Selecione a opção **Redefinir dispositivo** e leia a mensagem de confirmação.
1. Se você concordar em reiniciar seu dispositivo, ele será reiniciado e exibirá um conjunto de engrenagens giradas com uma barra de progresso.
1. Aguarde cerca de trinta minutos para a conclusão desse processo.
1. A redefinição será concluída, e o dispositivo será reiniciado para a configuração inicial.

## Re-instalar o sistema operacional

Se o dispositivo ainda estiver com problemas após a reinicialização e a redefinição, você pode usar uma ferramenta de recuperação no computador para reinstalar o firmware e o sistema operacional do HoloLens.  

Todos os dados do HoloLens devem ser redefinidos em uma Atualização Completa do Flash (FFU).  Isso é semelhante a um ISO, WIM ou VHD.  [Saiba mais sobre os formatos de arquivo de imagem do FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Se necessário, você pode instalar um sistema operacional completamente novo em seu HoloLens (1ª geração) com a Windows Device Recovery Tool.

Antes de usar essa ferramenta, determine se reiniciar ou redefinir seu HoloLens corrige o problema. O processo de recuperação pode demorar um pouco.  Quando terminar, a versão mais recente do software Windows Holographic aprovado para o seu HoloLens será instalada.

Para usar a ferramenta, você precisará de um computador que esteja executando o Windows 10 ou posterior, com pelo menos 4 GB de espaço de armazenamento disponível.  Observe que você não pode executar essa ferramenta em uma máquina virtual.

### Recuperar seu HoloLens 2:

1. No computador, baixe e instale a [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
1. Conecte o HoloLens (1ª geração) ao seu computador usando o cabo micro USB que veio com o seu HoloLens.
1. Execute a Windows Device Recovery Tool e siga as instruções.

Se o HoloLens (1ª geração) não for detectado automaticamente, selecione **Meu dispositivo não foi detectado** e siga as instruções para colocar o dispositivo no modo de recuperação.

### Modo de Piscar Manualmente:

No caso de o seu dispositivo não estar sendo detectado, use o seguinte método para inseri-lo manualmente no modo de piscar.

1. Desconecte o dispositivo de todas as fontes de alimentação.
1. Se o dispositivo estiver ligado, mantenha pressionado o botão de ligar até que ele desligue completamente.
1. Segure o botão **Aumentar o volume** e toque brevemente no botão **Ligar**. 
1. O dispositivo deve ser inicializado e, em seguida, exibir apenas a luz LED central.
1. Conecte o dispositivo em seu PC.
1. Iniciar a Windows Device Recovery Tool.
1. Será necessário selecionar *Meu dispositivo não foi detectado** e, em seguida, selecionar **HoloLens**. 
1. Siga as instruções para recuperar seu dispositivo.
