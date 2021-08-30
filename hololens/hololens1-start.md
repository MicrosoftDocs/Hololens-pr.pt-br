---
title: Configurar HoloLens (1ª geração)
description: Saiba como configurar seu HoloLens (1ª geração) pela primeira vez em uma rede Wi-Fi com uma conta microsoft (MSA) ou Azure Active Directory (AAD).
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189861"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configure seu HoloLens (1ª geração)

Na primeira vez que ativar o HoloLens, você será guiado pela calibração do dispositivo, pela configuração do dispositivo e pela entrada.  Este artigo explica a experiência de HoloLens (1ª geração) de início e configuração.

Na próxima seção, você aprenderá a trabalhar com o HoloLens e a interagir com hologramas. Para pular para esse artigo, consulte [Get started with HoloLens (1ª geração)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, verifique se você tem:

**Uma Wi-Fi de dados.** Você precisará conectar seu HoloLens a uma rede Wi-Fi para defini-la. Na primeira vez que se conectar, você precisará de uma rede aberta ou protegida por senha que não exija navegar até um site ou usar certificados para se conectar. [Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).

**Um conta Microsoft ou uma conta de trabalho**. Você também precisará usar uma conta de conta Microsoft (ou uma conta de trabalho, se sua organização tiver o dispositivo) para entrar no HoloLens. Se não tiver uma conta Microsoft, acesse [account.microsoft.com](https://account.microsoft.com) e configure uma gratuitamente.

**Um espaço seguro e bem iluminado em que não haja risco de tropeçar**. [Informações sobre integridade e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Os acessórios opcionais para conforto** que acompanham seu HoloLens, para ajudar você a ajustá-lo da melhor maneira. [Mais informações sobre ajuste e conforto](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - Na primeira vez que você usar seu HoloLens, [Cortana](hololens-cortana.md) já estará pronta para orientá-lo (embora ela não possa responder às suas perguntas até depois de configurar seu dispositivo). Você pode desativar Cortana a qualquer momento Cortana configurações do aplicativo.
> - Para alternar para a versão em chinês ou japonês do HoloLens, você precisará baixar o build para o idioma em um pc e, em seguida, instalá-lo em seu HoloLens. Para obter mais informações, [consulte Instalar versões localizadas do HoloLens (1ª geração)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Inicie o Hololens e Windows

Na primeira vez que você iniciar o HoloLens, sua primeira tarefa será configurar Windows Holographic em seu dispositivo.

1. Conexão para a Internet (HoloLens orienta você a selecionar Wi-Fi rede).

1. Entre em sua conta de usuário. Escolha entre **Meu trabalho ou escola é o proprietário dele** e eu o **possuo.**
    - Ao escolher Minha **empresa ou escola é proprietária** dele, você pode entrar usando uma conta do Azure AD. Se a organização usar o Azure AD Premium e tiver configurado o registro de MDM automático, o HoloLens será registrado automaticamente no MDM. Se sua organização não usar Azure AD Premium, o registro automático do MDM não estará disponível, portanto, você precisará registrar manualmente HoloLens no [gerenciamento de dispositivos.](hololens-enroll-mdm.md#different-ways-to-enroll) Para entrar no dispositivo pela primeira vez usando uma conta de trabalho ou de estudante, siga estas etapas:
        1. Insira as informações de conta de sua organização.
        1. Aceite a política de privacidade.
        1. Entre usando as credenciais do Azure AD. Isso pode redirecionar para a página de entrada da organização.
        1. Continue a configuração do dispositivo.
    - Ao escolher Eu **sou o próprio**, você pode entrar usando um conta Microsoft. Depois que instalação for concluída, você poderá [registrar manualmente o HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Insira as informações de sua conta Microsoft.
        1. Digite sua senha. Se a conta da Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.

1. O dispositivo define seu fuso horário com base nas informações que ele obtém da Wi-Fi rede.

## <a name="calibration"></a>Calibragem

Depois Cortana se apresentar, a próxima etapa de instalação será calibragem. Para a melhor HoloLens, você deve concluir o processo de calibragem durante a instalação.

HoloLens (1ª geração) usa a distância entre seus alunos (IPD ou [distância interpupária)](https://en.wikipedia.org/wiki/Interpupillary_distance)para tornar os hologramas claros e fáceis de interagir. Se o IPD não estiver correto, os hologramas poderão parecer instável ou a uma distância incorreta.

Durante a calibragem, HoloLens solicita que você alinhe o dedo com uma série de seis destinos por olho. HoloLens usa esse processo para definir o IPD correto para seus olhos. Se a calibragem precisar ser atualizada ou ajustada para um novo usuário, o novo usuário poderá executar o aplicativo De calibragem fora da instalação.

![Tela de alinhamento de dedo IPD na segunda etapa.](./images/ipd-finger-alignment-300px.jpg)

*Tela de alinhamento de IPD com o dedo na segunda etapa*

Parabéns! A instalação foi concluída e você pode começar a usar HoloLens.

## <a name="next-steps"></a>Próximas etapas

> [!div class="nextstepaction"]
> [Introdução ao HoloLens (1ª geração)](hololens1-basic-usage.md)
