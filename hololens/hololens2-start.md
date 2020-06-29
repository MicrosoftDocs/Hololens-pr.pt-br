---
title: Configurar seu HoloLens 2
description: Este guia aborda a primeira configuração.  Você precisará de uma rede Wi-Fi e de uma conta Microsoft (MSA) ou do Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8c3d9a10533432b3e8489ffa297c16061abb9eaf
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827613"
---
# Configurar seu HoloLens 2

Na primeira vez que ligar o HoloLens, você será orientado para configurar seu dispositivo, entrar com uma conta de usuário e calibrar o HoloLens aos seus olhos.  Esta seção aborda a experiência de configuração inicial do HoloLens 2.

Na próxima seção, você aprenderá a trabalhar com o HoloLens e interagir com hologramas. Para avançar para esse artigo, consulte [Introdução ao HoloLens 2](hololens2-basic-usage.md).

## Antes de começar

Antes de começar, verifique se você tem o seguinte disponível:

**Uma conexão de rede**. Você precisará conectar o HoloLens a uma rede para configurá-lo. Com o HoloLens 2, você pode se conectar ao Wi-Fi ou usando Ethernet (você precisará de um adaptador USB-C para Ethernet). Na primeira vez que se conectar, você precisará de uma rede aberta ou protegida por senha que não exige a navegação até um site ou usar certificados para se conectar. [Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).

**Uma conta Microsoft**. Você também precisará entrar no HoloLens com uma conta Microsoft (ou com sua conta corporativa, se a organização possuir o dispositivo). Se você não tiver uma conta Microsoft, acesse [account.microsoft.com](https://account.microsoft.com) e configure uma gratuitamente.

**Um espaço seguro e bem iluminado sem risco de tropeçar**. [Informações de saúde e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Os acessórios de conforto opcionais** que vieram com o HoloLens, para ajudá-lo a obter o mais confortável. [Mais sobre ajuste e conforto](hololens2-setup.md#adjust-fit).

## Configurar o Windows

Na primeira vez que você iniciar o HoloLens 2, a primeira tarefa será configurar o Windows Holographic.  Ao iniciar o HoloLens, você ouvirá uma música e verá um logotipo do Windows.

![Primeira tela durante a primeira inicialização](images/01-magic-moment.png)

O HoloLens 2 abordará as seguintes etapas:

1. Selecione seu idioma.
    ![Selecionar idioma](images/04-language.png)

1. Selecione sua região.
    ![Selecionar região](images/05-region.png)

1. Calibre o HoloLens aos seus olhos.  Se optar por ignorar a calibragem, você será avisado na próxima vez em que fizer logon.

    Para calibrar, você verá um conjunto de alvos (chamados de gems). Não há problema se você piscar ou fechar os olhos durante a calibragem, mas não olhe para outros objetos no cômodo ou no espaço físico. O HoloLens usa esse processo para saber mais sobre a posição de seus olhos, para que você possa renderizar melhor o mundo holográfico. Após a calibragem, os hologramas serão exibidos corretamente, mesmo que o visor mude de posição em sua cabeça.

    As informações de calibragem são armazenadas localmente no dispositivo e não são associadas a informações de conta. Para obter mais informações, consulte [Segurança e dados de calibragem](hololens-calibration.md#calibration-data-and-security).

    ![Tela de seleção da calibragem](images/06-et-corners.png)

1. Conecte-se à Internet (selecione Wi-Fi ou sua conexão Ethernet).
     O HoloLens define o fuso horário automaticamente com base nas informações obtidas da rede Wi-Fi. Após a conclusão da configuração, você pode alterar o fuso horário usando o aplicativo Configurações.

    ![Conectar-se ao Wi-Fi](images/11-network.png)
> [!NOTE] 
> Se você passar da etapa de Wi-Fi e posteriormente precisar alternar para uma rede diferente enquanto ainda estiver na configuração, pressione os botões **Diminuir o Volume** e **Ligar/Desligar** simultaneamente para retornar a esta etapa se estiver executando uma versão do SO de outubro de 2019 ou posterior. Para versões anteriores, talvez seja necessário [redefinir o dispositivo](hololens-recovery.md) ou reiniciá-lo em um local em que a rede Wi-Fi não esteja disponível para impedir a conexão automática.
> 
> Observe também que, durante a Instalação do HoloLens, há um tempo limite de credenciais de dois minutos. O nome de usuário e a senha devem ser inseridos dentro de dois minutos, caso contrário, o campo do nome de usuário será automaticamente limpo.

1. Entre em sua conta de usuário. Você escolherá entre **O proprietário é meu trabalho ou escola** e **Sou o proprietário**.
    - Ao escolher **O proprietário é meu trabalho ou escola**, você entra usando uma conta do Azure AD. Se a organização usar o Azure AD Premium e tiver configurado o registro de MDM automático, o HoloLens será registrado automaticamente no MDM. Se a organização não usar o Azure AD Premium, o registro de MDM automático não estará disponível. Nesse caso, você precisará [registrar o HoloLens no gerenciamento de dispositivo manualmente](hololens-enroll-mdm.md#enroll-through-settings-app).
        1. Insira as informações de sua conta organizacional.
        1. Aceite a política de privacidade e o contrato de licença do usuário final.
        1. Entre usando as credenciais do Azure AD. Isso pode redirecionar para a página de entrada da organização.
        1. Continue a configuração do dispositivo.
    - Ao escolher **É meu**, você entra usando uma conta Microsoft. Depois que instalação for concluída, você poderá [registrar o HoloLens no gerenciamento de dispositivo manualmente](hololens-enroll-mdm.md#enroll-through-settings-app).
        1. Insira as informações de sua conta Microsoft.
        2. Insira a senha. Se a conta Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.

    ![Definir o usuário](images/13-device-owner.png)

1. Escolha se deseja habilitar o controle por voz no HoloLens 2 e se deseja enviar telemetria de diagnóstico.
    ![Habilitar a Cortana](images/22-do-more-with-voice.png)

1. Selecione o nível de telemetria. Se possível, habilite a telemetria completa. Essas informações ajudam muito a equipe de engenharia do HoloLens.
     ![Nível de telemetria](images/24-telemetry.png)

1. Saiba como usar o gesto de iniciar no HoloLens 2.
     ![Saiba como usar o gesto de iniciar, imagem 1](images/26-01-startmenu-learning.png) ![Saiba como usar o gesto de iniciar, imagem 2](images/26-02-startmenu-learning.png)

Parabéns!  A configuração está completa, e você está pronto para usar o HoloLens!

## Próximas etapas

> [!div class="nextstepaction"]
> [Introdução ao HoloLens 2.](hololens2-basic-usage.md)
