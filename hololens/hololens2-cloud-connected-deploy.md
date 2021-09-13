---
title: guia de implantação – implantação em nuvem HoloLens 2 em escala com a assistência remota-implantar
description: saiba como validar o registro e a assistência remota para dispositivos HoloLens por meio de uma rede conectada em nuvem.
keywords: HoloLens, gerenciamento, nuvem conectada, assistência remota, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
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
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031989"
---
# <a name="deploy---cloud-connected-guide"></a>Implantar – guia conectado à nuvem

Agora que você tem tudo configurado, deve estar pronto para distribuir dispositivos. No entanto, agora é quando você deve primeiro validar a configuração. Primeiro, o Azure AD Join e o processo de registro de MDM devem ser validados, seguidos pela verificação de que uma chamada de assistência remota pode ser colocada.

## <a name="enrollment-validation"></a>Validação de registro

Agora que tudo está configurado corretamente para o Azure AD e o registro de MDM, o restante agora deve ser um snap. você&#39;precisa de uma conexão Wi-Fi e do dispositivo HoloLens, bem como uma das contas de usuário AAD configuradas anteriormente.

Se seu dispositivo não&#39;no momento em um estado de configurações de fábrica, agora seria um bom momento para refazer [o flash do dispositivo](/hololens/hololens-recovery#clean-reflash-the-device).

1. Depois que o dispositivo estiver em OOBE, você&#39;precisará começar a interagir e seguir os prompts. 
1. o aviso crítico será quando você for solicitado **Who a possuir este HoloLens?** Selecione **meu trabalho ou escola possui** e insira suas credenciais de conta do Azure AD.
1. Quando o registro for bem-sucedido, você&#39;será solicitado a configurar um PIN. Este PIN é exclusivo para este dispositivo para este usuário. Você também será solicitado a fornecer verificações de íris, dados de voz e configurações de telemetria e&#39;, por fim, poderá aprender a abrir o menu iniciar e concluir o OOBE.
1. depois que você chegar ao início da realidade misturada, abra o menu Iniciar usando o **gesto de início** que você acabou de aprender.
1. selecione o aplicativo **Configurações** e selecione **sistema.** a primeira informação que você&#39;ver é o nome do dispositivo, que para o dispositivo HoloLens 2 será o &quot; HoloLens- &quot; seguido por uma cadeia de seis caracteres.
1. Anote esse nome.

![HoloLens 2 Configurações.](./images/hololens2-settings-about.jpg)

7. você pode verificar se o dispositivo foi registrado com êxito no Azure AD dentro do aplicativo Configurações. em **Configurações** selecione **contas**  ->  **acesso corporativo ou de estudante**. Nessa tela, você pode verificar se registrou com êxito ao ver &quot; conectado ao _nameofAAD_&#39;s do Azure AD. Conectado por _seunomedeusuário_ @ _nameofAAD_. onmicrosoft.com &quot; .


para validar que o dispositivo tenha ingressado no Azure AD, é possível verificar o Azure Active Directory do [portal do Azure](https://portal.azure.com/#home)dispositivos  ->  **Azure Active Directory**  ->    ->  **todos os dispositivos** e pesquisar o nome do dispositivo. Você&#39;ser capaz de ver o dispositivo faz parte do Azure Active Directory.


![Azure Active Directory-dispositivo.](./images/aad-enrollment.png)

em seguida, você&#39;precisa fazer logon no [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Faça logon e selecione **dispositivos** e, em seguida, **todos os dispositivos**. aqui, você pode pesquisar seu HoloLens dispositivo&#39;nome. você deve ser capaz de ver suas HoloLens listadas no Intune.

![Intune-dispositivo.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Validação da chamada de assistência remota

Quando você&#39;verificou que seu dispositivo está registrado no AAD e no MDM, ele&#39;o tempo para fazer uma chamada de assistência remota de teste. para essa validação, você&#39;precisa ter o dispositivo HoloLens e um Windows 10 pc, bem como uma segunda conta de usuário do Azure AD para o PC.

Esta etapa de validação assumirá que você concluiu anteriormente a última etapa de validação e que seu dispositivo está registrado e o usuário do Azure AD está no dispositivo.


1. se ainda não tiver Microsoft Teams instalado em seu computador, você poderá [baixar Teams aqui](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. entre Teams usando a segunda conta de usuário do Azure AD que está atualmente conectada ao seu HoloLens. Depois de conectado em seu PC, você estará pronto para receber a chamada.
3. desbloqueie seu HoloLens e entre.
4. Para iniciar o aplicativo de assistência remota, abra o **menu iniciar** e selecione **assistência remota**. a assistência remota não é agrupada apenas como um aplicativo de caixa de entrada, mas fixada ao menu iniciar do HoloLens 2&#39;s. em um evento que você don&#39;t vê-lo fixado ao menu Iniciar, abra a lista **todos os aplicativos** para procurar por ele.
5. Depois que o auxílio remoto for iniciado, ele deverá identificar o usuário do dispositivo por meio do [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) e fazer logon no aplicativo.
6. No aplicativo, selecione **Pesquisar** e procure o segundo usuário no computador. Selecione o usuário para iniciar a chamada.
7. Em seu PC, responda à chamada.

Parabéns, você&#39;ve conectado com êxito e está em sua chamada de assistência remota. Certifique-se de experimentar recursos específicos de assistência remota, como usar:

- [Anotações de tinta](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartilhar um arquivo e uma exibição em realidade misturada](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [obter ajuda em outro aplicativo HoloLens](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem – manter](hololens2-cloud-connected-maintain.md)