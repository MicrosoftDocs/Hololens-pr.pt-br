---
title: Guia de Implantação – implantação do HoloLens 2 conectada à nuvem em escala com Assistência Remota - Implantar
description: Saiba como validar o registro e a Assistência Remota para dispositivos HoloLens em uma rede conectada à nuvem.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282932"
---
# Implantar - Guia conectado à nuvem

Agora que você tem tudo configurado, deve estar pronto para distribuir dispositivos. No entanto, agora você deve validar sua configuração pela primeira vez. Primeiro, o processo de inscrição no Azure AD e no MDM deve ser validado, seguido da verificação de que uma chamada de Assistência Remota pode ser feita.

## Validação de registro

Agora que tudo está configurado corretamente para o Registro no Azure AD e no MDM, o restante agora deve ser um snap. Você&#39;uma conexão Wi-Fi e o dispositivo HoloLens, bem como uma das contas de usuário do AAD configuradas anteriormente.

Se seu dispositivo não&#39;atualmente sentado em um estado de configurações de fábrica, agora seria um bom momento para [reflash o dispositivo.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Depois que o dispositivo está na configuração inicial pelo usuário,&#39;precisará começar a interagir e seguir os prompts. 
1. O prompt crítico será quando você for perguntado quem **é o proprietário deste HoloLens?** Selecione **My work or school owns it** and enter your Azure AD account credentials.
1. Quando o registro for bem-sucedido,&#39;você será solicitado a configurar um PIN. Esse PIN é exclusivo deste dispositivo para esse usuário. Você também será solicitado a fazer verificações de íris, dados de voz e configurações de telemetria e, por fim,&#39;poderá aprender a abrir o menu Iniciar e concluir o OOBE.
1. Depois de chegar na Página Inicial da Realidade Misturada, abra o menu Iniciar usando o gesto **de Iniciar** que você acabou de aprender.
1. Selecione o **aplicativo Configurações** e selecione **Sistema.** A primeira informação que você&#39;verá é o nome do dispositivo, que para o dispositivo holoLens 2 será hololens - seguido por uma cadeia de seis &quot; &quot; caracteres.
1. Anote esse nome.

![Configurações do HoloLens 2 - Sobre](./images/hololens2-settings-about.jpg)

7. Você pode verificar se seu dispositivo foi inscrito com êxito no Azure AD dentro do aplicativo Configurações. Nas **Configurações,** selecione **Contas**  ->  **do Access no trabalho ou na escola.** Nesta tela, você pode verificar se está inscrito com êxito ao ver Conectado ao &quot; _nameofAAD_&#39;Azure AD. Conectado pelo _nomedousuáriodeAAD_ @ __.onmicrosoft.com &quot; .


Para validar se o dispositivo tem Ingressado no Azure AD, podemos verificar o Azure Active Directory em todos os dispositivos do [](https://portal.azure.com/#home)  ->  **Azure Active Directory**portal e pesquisar o nome do  ->  ****  ->  **** dispositivo. Você&#39;poderá ver que o dispositivo faz parte do Azure Active Directory.


![Azure Active Directory - Dispositivo](./images/aad-enrollment.png)

Em seguida,&#39;você precisará fazer logoff no centro de administração do [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Faça logoff e selecione **Dispositivos em** **seguida, Todos os dispositivos.** A partir daqui, você pode pesquisar seu dispositivo HoloLens&#39;nome. Você poderá ver seu HoloLens listado no Intune.

![Intune - Dispositivo](./images/endpoint-all-devices-enrolled.png)

## Validação de Chamada de Assistência Remota

Depois de&#39;verificar se seu dispositivo está inscrito no AAD e no MDM, é&#39;fazer uma chamada de Assistência Remota de teste. Para essa validação,&#39;precisará ter o dispositivo HoloLens e um computador Windows 10, bem como uma segunda conta de usuário do Azure AD para o computador.

Esta etapa de validação assumirá que você concluiu anteriormente a última etapa de validação e seu dispositivo está inscrito e seu usuário do Azure AD está no dispositivo.


1. Se você ainda não tiver o Microsoft Teams instalado em seu computador, baixe o [Teams aqui.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Entre no Teams usando a segunda conta de usuário do Azure AD do que a que está atualmente em seu HoloLens. Depois de entrar no computador, você estará pronto para receber a chamada.
3. Desbloqueie seu HoloLens e entre.
4. Para iniciar o aplicativo Assistência Remota, abra o **Menu Iniciar** e selecione **Assistência Remota.** A Assistência Remota não é apenas empacotada como um aplicativo de caixa de entrada, mas fixada no holoLens 2&#39;menu iniciar. Em um evento, você&#39;vê-lo fixado no menu **** Iniciar e, em seguida, abrir a lista Todos os aplicativos para procurar por ela.
5. Depois que a Assistência Remota é iniciada, ela deve identificar o usuário do dispositivo por meio de [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e fazer logoff no aplicativo.
6. No aplicativo, selecione **Pesquisar** e procurar o segundo usuário no computador. Selecione o usuário para iniciar a chamada.
7. No computador, responda à chamada.

Parabéns, você&#39;se conectou com êxito e está em sua chamada de assistência remota. Certifique-se de experimentar recursos específicos de assistência remota, como o uso:

- [Anotações de inking](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartilhar um arquivo e exibição na realidade misturada](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obter ajuda em outro aplicativo do HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem - Manutenção](hololens2-cloud-connected-maintain.md)