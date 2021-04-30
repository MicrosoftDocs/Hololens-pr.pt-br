---
title: Configurar o HoloLens (1ª gen)
description: Saiba como configurar seu HoloLens (1º gen) pela primeira vez em Wi-Fi rede com uma conta da Microsoft (MSA) ou do Azure Active Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308104"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configurar seu HoloLens (1ª gen)

Na primeira vez que você ativar o seu HoloLens, você será orientado por meio da calibragem do seu dispositivo, da configuração do dispositivo e da entrada.  Este artigo percorre a primeira experiência de início e instalação do HoloLens (1º gen).

Na próxima seção, você aprenderá a trabalhar com o HoloLens e a interagir com os hologramas. Para pular para esse artigo, consulte Introdução [ao HoloLens (1ª gen)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, verifique se você tem os seguintes itens disponíveis:

**Uma conexão Wi-Fi**. Você precisará conectar seu HoloLens a uma rede Wi-Fi para configurá-lo. Na primeira vez que você se conectar, precisará de uma rede aberta ou protegida por senha que não precise navegar para um site ou usar certificados para se conectar. [Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).

**Uma conta Microsoft ou uma conta corporativa**. Você também precisará usar uma conta Microsoft (ou uma conta de trabalho, se sua organização possuir o dispositivo) para entrar no HoloLens. Se você não tiver um conta Microsoft, vá para [Account.Microsoft.com](https://account.microsoft.com) e configure um gratuitamente.

**Um espaço seguro e bem iluminado sem riscos de ida e vindas**. [Informações de integridade e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Os acessórios opcionais** que acompanham seu HoloLens, para ajudá-lo a se familiarizar mais à vontade. [Mais em ajuste e conforto](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - Na primeira vez que você usar seu HoloLens, a [Cortana](hololens-cortana.md) já estará ativada e pronta para orientá-lo (embora ela não conseguirá responder às suas perguntas até que você configure seu dispositivo). Você pode desativar a Cortana a qualquer momento nas configurações da Cortana.
> - Para alternar para a versão em chinês ou japonês do HoloLens, você precisará baixar o Build para o idioma em um computador e, em seguida, instalá-lo em seu HoloLens. Para obter mais informações, consulte [instalar versões localizadas do HoloLens (1ª gen)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Inicie seu Hololens e configure o Windows

Na primeira vez que você inicia seu HoloLens, sua primeira tarefa é configurar o Windows Holographic em seu dispositivo.

1. Conecte-se à Internet (o HoloLens orienta você a selecionar Wi-Fi rede).

1. Entre na sua conta de usuário. Escolha entre **meu trabalho ou escola e o** proprietário **dele.**
    - Quando você escolhe **meu trabalho ou escola**, você entra usando uma conta do Azure AD. Se sua organização usa Azure AD Premium e configurou o registro automático de MDM, o HoloLens é registrado automaticamente no MDM. Se sua organização não usar Azure AD Premium, o registro automático do MDM não estará disponível, portanto, você precisará [registrar o HoloLens manualmente no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll). Para entrar no seu dispositivo na primeira vez usando uma conta corporativa ou de estudante, siga estas etapas:
        1. Insira as informações da conta institucional.
        1. Aceite a política de privacidade.
        1. Entre usando suas credenciais do Azure AD. Isso pode redirecionar para a página de entrada da organização.
        1. Continue a configurar o dispositivo.
    - Ao escolher o **proprietário dele**, você entra usando uma conta Microsoft. Após a conclusão da instalação, você pode [registrar manualmente o HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Insira suas informações de conta Microsoft.
        1. Digite sua senha. Se a conta da Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.

1. O dispositivo define seu fuso horário com base nas informações obtidas da rede Wi-Fi.

## <a name="calibration"></a>Calibragem

Depois que a Cortana apresenta, a próxima etapa de instalação é a calibragem. Para obter a melhor experiência de HoloLens, você deve concluir o processo de calibragem durante a instalação.

O HoloLens (1º gen) usa a distância entre o Pupils (IPD ou a [distância interpupillary](https://en.wikipedia.org/wiki/Interpupillary_distance)) para tornar os hologramas claros e fáceis de interagir. Se o IPD não estiver correto, os hologramas poderão parecer instáveis ou em uma distância incorreta.

Durante a calibragem, o HoloLens solicita que você alinhe seu dedo com uma série de seis destinos por olho. O HoloLens usa esse processo para definir o IPD correto para seus olhos. Se a calibragem precisar ser atualizada ou ajustada para um novo usuário, o novo usuário poderá executar o aplicativo de calibragem fora da instalação.

![Tela de alinhamento de dedo de IPD na segunda etapa](./images/ipd-finger-alignment-300px.jpg)

*Tela de alinhamento de dedo de IPD na segunda etapa*

Parabéns! A instalação foi concluída e você pode começar a usar o HoloLens.

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Introdução ao HoloLens (1º gen)](hololens1-basic-usage.md)
