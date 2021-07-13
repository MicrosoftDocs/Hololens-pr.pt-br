---
title: Guia de implantação – Implantação HoloLens 2 conectada à nuvem em escala com o Remote Assist – Implantar
description: Saiba como validar o registro e o Remote Assist para HoloLens em uma rede conectada à nuvem.
keywords: HoloLens, gerenciamento, nuvem conectada, Assistência Remota, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635170"
---
# <a name="deploy---cloud-connected-guide"></a>Implantar – Guia conectado à nuvem

Agora que você tem tudo configurado, deve estar pronto para distribuir dispositivos. No entanto, agora você deve validar sua configuração pela primeira vez. Primeiro, o processo de registro de MDM e junção do Azure AD deve ser validado, seguido da verificação de que uma chamada de Assistência Remota pode ser feita.

## <a name="enrollment-validation"></a>Validação de registro

Agora que tudo está configurado corretamente para o Azure AD e o Registro de MDM, o restante agora deve ser um snap. Você&#39;uma conexão Wi-Fi e o dispositivo HoloLens, bem como uma das contas de usuário do AAD configuradas anteriormente.

Se o dispositivo não&#39;no momento em um estado de configurações de fábrica, agora seria um bom momento para [reflash o dispositivo](/hololens/hololens-recovery#clean-reflash-the-device).

1. Depois que o dispositivo está em OOBE,&#39;precisará começar a interagir e seguir os prompts. 
1. O prompt crítico será quando você for solicitado Who **possui esse HoloLens?** Selecione **Minha empresa ou escola possui e** insira suas credenciais de conta do Azure AD.
1. Quando o registro for bem-sucedido,&#39;será solicitado a configurar um PIN. Esse PIN é exclusivo para esse dispositivo para esse usuário. Você também receberá uma solicitação para verificações de Íris, dados de voz e configurações de telemetria e, por fim,&#39;poderá aprender a abrir o menu Iniciar e concluir o OOBE.
1. Depois de chegar à Página Inicial da Realidade Misturada, abra o menu Iniciar usando o **gesto Iniciar** que você acabou de aprender.
1. Selecione o **Configurações** aplicativo e selecione **Sistema.** A primeira informação&#39;você verá é o Nome do dispositivo, que para o dispositivo HoloLens 2 será HOLOLENS, seguido por uma cadeia de caracteres de seis &quot; &quot; caracteres.
1. Anote esse nome.

![HoloLens 2 Configurações – Sobre](./images/hololens2-settings-about.jpg)

7. Você pode verificar se o dispositivo foi inscrito com êxito no Azure AD dentro do Configurações aplicativo. Na **Configurações** selecione **Contas Acessar trabalho** ou  ->  **escola.** Nesta tela, você pode verificar se está inscrito com êxito vendo Conectado ao &quot; _nameofAAD_&#39;Azure AD. Conectado por _seunome do_ @ _usuárioofAAD_.onmicrosoft.com &quot; .


Para validar se o dispositivo tem o Azure AD [](https://portal.azure.com/#home)Ingressado, podemos verificar o Azure Active Directory do portal do Azure  ->  **Azure Active Directory**  ->  **Dispositivos** Todos os dispositivos e pesquisar o nome  ->  do dispositivo. Você&#39;poderá ver que o dispositivo faz parte do Azure Active Directory.


![Azure Active Directory - Dispositivo](./images/aad-enrollment.png)

Em seguida&#39;você precisará fazer logoff no [centro Microsoft Endpoint Manager administrador.](https://endpoint.microsoft.com/#home) Faça logoff e selecione **Dispositivos e,** em **seguida, Todos os dispositivos**. A partir daqui, você pode pesquisar seu HoloLens dispositivo&#39;nome. Você deve ser capaz de ver seus HoloLens listados no Intune.

![Intune – Dispositivo](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Validação de chamada de assistência remota

Depois que&#39;verificar se o dispositivo está inscrito no AAD e no MDM,&#39;hora de fazer uma chamada de Assistência Remota de teste. Para essa validação,&#39;precisará ter o dispositivo HoloLens e um computador Windows 10, bem como uma segunda conta de usuário do Azure AD para o computador.

Essa etapa de validação assumirá que você concluiu anteriormente a última etapa de validação e seu dispositivo está inscrito e seu usuário do Azure AD está no dispositivo.


1. Se você ainda não tiver Microsoft Teams instalado em seu computador, poderá baixar o [Teams aqui](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Entre Teams usando a segunda conta de usuário do Azure AD que a que está atualmente HoloLens. Depois de entrar no computador, você estará pronto para receber a chamada.
3. Desbloqueie HoloLens e entre.
4. Para iniciar o aplicativo Assistência Remota, abra o **Menu Iniciar** e selecione **Assistência Remota.** O Remote Assist não é empacotado apenas como um aplicativo de caixa de entrada, mas fixado no menu HoloLens 2&#39;menu iniciar. Em um evento,&#39;vê-lo fixado no menu Iniciar, abra a lista **Todos os apps** para procurar por ele.
5. Depois que o Remote Assist é iniciado, ele deve identificar o usuário do dispositivo por [meio de SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) e fazer logoff no aplicativo.
6. De dentro do aplicativo, selecione **Pesquisar** e pesquise o segundo usuário no COMPUTADOR. Selecione o usuário para iniciar a chamada.
7. No computador, responda à chamada.

Parabéns, você&#39;se conectou com êxito e está em sua chamada de assistência remota. Experimente recursos específicos de assistência remota, como o uso de:

- [Anotações de inking](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartilhar um arquivo e exibição na realidade misturada](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obter ajuda em outro HoloLens aplicativo](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem – Manter](hololens2-cloud-connected-maintain.md)