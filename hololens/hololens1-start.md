---
title: Configurar o HoloLens (1ª geração)
description: Este guia percorre a primeira configuração.  Você precisará de uma rede Wi-Fi e de uma conta Microsoft (MSA) ou do Azure Active Directory (Azure AD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9a20a2ddd52c08a2b44dad452aac07ad9e69de85
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903227"
---
# Configurar seu HoloLens (1ª geração)

Na primeira vez que ligar o HoloLens, você será guiado pela calibragem do dispositivo, configuração do dispositivo e entrada.  Este artigo percorre a experiência de primeira inicialização e configuração do HoloLens (1ª geração).

Na próxima seção, você aprenderá a trabalhar com o HoloLens e interagir com hologramas. Para avançar para esse artigo, veja [introdução ao HoloLens (1ª geração)](hololens1-basic-usage.md).

## Antes de começar

Antes de começar, verifique se você tem o seguinte:

**Um conexão Wi-Fi**. Você deverá conectar o HoloLens a uma rede Wi-Fi para configurá-lo. Na primeira vez que se conectar, você precisará de uma rede aberta ou protegida por senha que não exige a navegação até um site ou usar certificados para se conectar. [Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).

**Uma conta Microsoft ou uma conta corporativa**. Você também precisará usar uma conta Microsoft (ou uma conta corporativa, se a organização for a proprietária do dispositivo) para fazer logon no HoloLens. Se você não tiver uma conta Microsoft, acesse [account.microsoft.com](https://account.microsoft.com) e configure uma gratuitamente.

**Um espaço seguro e bem iluminado sem risco de tropeçar**. [Informações de saúde e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Os acessórios de conforto opcionais** fornecidos com seu HoloLens, para ajudá-lo a ter o máximo de conforto. [Mais sobre ajuste e conforto](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - Na primeira vez que você usar o HoloLens, [a Cortana](hololens-cortana.md) já estará ligada e pronta para orientá-lo (mas ela não poderá responder às suas perguntas depois que você configurar seu dispositivo). Você pode desligar a Cortana a qualquer momento em suas configurações.
> - Para mudar para a versão em chinês ou em japonês do HoloLens, você precisará baixar o build do idioma em um computador e instalá-lo em seu HoloLens. Para obter mais informações, consulte [Instalar versões localizadas do HoloLens (1ª geração)](hololens1-install-localized.md).

## Iniciar seu Hololens e configurar o Windows

Na primeira vez que você iniciar o HoloLens, sua primeira tarefa será configurar o Windows Holographic em seu dispositivo.

1. Conecte-se com a internet (o HoloLens orientará você a selecionar a rede Wi-Fi).

1. Entre em sua conta de usuário. Escolha entre **O proprietário é meu trabalho ou escola** e **Eu sou o proprietário**.
    - Ao escolher **O proprietário é meu trabalho ou escola**, você entra usando uma conta do Azure AD. Se a organização usar o Azure AD Premium e tiver configurado o registro de MDM automático, o HoloLens será automaticamente registrado no MDM. Se a organização não usar o Azure AD Premium, o registro automático no MDM não estará disponível, então você precisará [registrar o HoloLens no gerenciamento de dispositivos manualmente](hololens-enroll-mdm.md#different-ways-to-enroll). Para entrar no seu dispositivo pela primeira vez usando uma conta corporativa ou de estudante, siga estas etapas:
        1. Insira as informações da conta organizacional.
        1. Aceite a declaração de privacidade.
        1. Entre usando as credenciais do Azure AD. Isso pode redirecionar para a página de entrada da organização.
        1. Continue a configuração do dispositivo.
    - Ao escolher **Eu sou o proprietário**, você entra usando uma conta Microsoft. Depois que instalação for concluída, você poderá [registrar o HoloLens no gerenciamento de dispositivos manualmente](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Insira as informações de sua conta Microsoft.
        1. Insira a senha. Se a conta da Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.

1. O dispositivo define o fuso horário com base nas informações que obtém da rede Wi-Fi.

## Calibragem

Depois que Cortana se apresenta, a próxima etapa de instalação é a calibragem. Para obter a melhor experiência de HoloLens, conclua o processo de calibragem durante a instalação.

O HoloLens (1ª geração) usa a distância entre suas pupilas (IPD, ou [distância interpupilar](https://en.wikipedia.org/wiki/Interpupillary_distance)) para fazer com que os hologramas sejam claros e de fácil interação. Se o IPD não estiver correto, os hologramas poderão parecer instáveis ou em uma distância incorreta.

Durante a calibragem, o HoloLens pede para você alinhar o dedo com uma série de seis alvos por olho. O HoloLens usa esse processo para definir o IPD correto para os seus olhos. Se a calibragem tiver de ser atualizada ou ajustada para um novo usuário, o novo usuário poderá executar o aplicativo Calibragem fora da instalação.

![Tela de alinhamento de IPD na segunda etapa](./images/ipd-finger-alignment-300px.jpg)

*Tela de alinhamento de IPD na segunda etapa*

Parabéns! A instalação foi concluída e você pode começar a usar o HoloLens.

## Próximas etapas

> [!div class="nextstepaction"]
> [Introdução ao HoloLens (1ª geração)](hololens1-basic-usage.md)
