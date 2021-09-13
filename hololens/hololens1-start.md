---
title: configurar HoloLens (1ª gen)
description: saiba como configurar sua HoloLens (1ª gen) pela primeira vez em Wi-Fi rede com uma conta da Microsoft (MSA) ou Azure Active Directory (AAD).
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
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031999"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configure seu HoloLens (1ª geração)

na primeira vez que você ligar seu HoloLens, você será orientado por meio da calibragem do seu dispositivo, da configuração do dispositivo e da entrada.  este artigo descreve a primeira experiência de início e instalação do HoloLens (1ª gen).

Na próxima seção, você aprenderá a trabalhar com o HoloLens e a interagir com hologramas. para ir adiante para esse artigo, consulte introdução [ao HoloLens (1ª gen)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, verifique se você tem:

**Uma conexão Wi-Fi**. você precisará conectar seu HoloLens a uma rede de Wi-Fi para configurá-lo. Na primeira vez que se conectar, você precisará de uma rede aberta ou protegida por senha que não exija navegar até um site ou usar certificados para se conectar. [Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).

**Uma conta Microsoft ou uma conta corporativa**. Você também precisará usar uma conta Microsoft (ou uma conta de trabalho, se sua organização possuir o dispositivo) para entrar no HoloLens. Se não tiver uma conta Microsoft, acesse [account.microsoft.com](https://account.microsoft.com) e configure uma gratuitamente.

**Um espaço seguro e bem iluminado em que não haja risco de tropeçar**. [Informações sobre integridade e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Os acessórios opcionais para conforto** que acompanham seu HoloLens, para ajudar você a ajustá-lo da melhor maneira. [Mais informações sobre ajuste e conforto](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - na primeira vez que você usar o HoloLens, [Cortana](hololens-cortana.md) já está ativado e pronto para orientá-lo (embora ela não conseguirá responder às suas perguntas até que você configure o dispositivo). você pode desativar Cortana a qualquer momento nas configurações do Cortana.
> - para alternar para a versão em chinês ou japonês do HoloLens, você precisará baixar a compilação do idioma em um computador e instalá-lo em seu HoloLens. para obter mais informações, consulte [instalar versões localizadas do HoloLens (1ª gen)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Inicie seu Hololens e configure Windows

na primeira vez que você iniciar o HoloLens, sua primeira tarefa será configurar Windows Holographic em seu dispositivo.

1. Conexão à internet (HoloLens o guia para selecionar Wi-Fi rede).

1. Entre em sua conta de usuário. Escolha entre **meu trabalho ou escola e o** proprietário **dele.**
    - Quando você escolhe **meu trabalho ou escola**, você entra usando uma conta do Azure AD. Se a organização usar o Azure AD Premium e tiver configurado o registro de MDM automático, o HoloLens será registrado automaticamente no MDM. se sua organização não usar Azure AD Premium, o registro automático do MDM não estará disponível, portanto, você precisará registrar-se [manualmente HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll). Para entrar no seu dispositivo na primeira vez usando uma conta corporativa ou de estudante, siga estas etapas:
        1. Insira as informações de conta de sua organização.
        1. Aceite a política de privacidade.
        1. Entre usando as credenciais do Azure AD. Isso pode redirecionar para a página de entrada da organização.
        1. Continue a configuração do dispositivo.
    - Ao escolher o **proprietário dele**, você entra usando uma conta Microsoft. Depois que instalação for concluída, você poderá [registrar manualmente o HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Insira as informações de sua conta Microsoft.
        1. Digite sua senha. Se a conta da Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.

1. O dispositivo define seu fuso horário com base nas informações obtidas da rede Wi-Fi.

## <a name="calibration"></a>Calibragem

depois que Cortana apresenta, a próxima etapa de instalação é a calibragem. para obter a melhor experiência de HoloLens, você deve concluir o processo de calibragem durante a instalação.

HoloLens (1º gen) usa a distância entre o pupils (IPD ou a [distância do interpupillary](https://en.wikipedia.org/wiki/Interpupillary_distance)) para tornar os hologramas claros e fáceis de interagir. Se o IPD não estiver correto, os hologramas poderão parecer instáveis ou em uma distância incorreta.

durante a calibragem, HoloLens solicita que você alinhe seu dedo com uma série de seis destinos por olho. HoloLens usa esse processo para definir o IPD correto para seus olhos. Se a calibragem precisar ser atualizada ou ajustada para um novo usuário, o novo usuário poderá executar o aplicativo de calibragem fora da instalação.

![Tela de alinhamento de IPD com o dedo na segunda etapa.](./images/ipd-finger-alignment-300px.jpg)

*Tela de alinhamento de dedo de IPD na segunda etapa*

Parabéns! A instalação foi concluída e você pode começar a usar HoloLens.

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Introdução ao HoloLens (1ª geração)](hololens1-basic-usage.md)
