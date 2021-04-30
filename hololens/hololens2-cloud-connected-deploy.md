---
title: Guia de implantação – implantação do HoloLens 2 em nuvem conectada em escala com a assistência remota-implantar
description: Saiba como validar o registro e o auxílio remoto para dispositivos do HoloLens por meio de uma rede conectada em nuvem.
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308229"
---
# <a name="deploy---cloud-connected-guide"></a>Implantar – guia conectado à nuvem

Agora que você tem tudo configurado, deve estar pronto para distribuir dispositivos. No entanto, agora é quando você deve primeiro validar a configuração. Primeiro, o Azure AD Join e o processo de registro de MDM devem ser validados, seguidos pela verificação de que uma chamada de assistência remota pode ser colocada.

## <a name="enrollment-validation"></a>Validação de registro

Agora que tudo está configurado corretamente para o Azure AD e o registro de MDM, o restante agora deve ser um snap. Você&#39;precisa de uma conexão Wi-Fi e do dispositivo HoloLens, bem como uma das contas de usuário AAD configuradas anteriormente.

Se seu dispositivo não&#39;no momento em um estado de configurações de fábrica, agora seria um bom momento para refazer [o flash do dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Depois que o dispositivo estiver em OOBE, você&#39;precisará começar a interagir e seguir os prompts. 
1. O aviso crítico será quando você for solicitado a **quem pertence este HoloLens?** Selecione **meu trabalho ou escola possui** e insira suas credenciais de conta do Azure AD.
1. Quando o registro for bem-sucedido, você&#39;será solicitado a configurar um PIN. Este PIN é exclusivo para este dispositivo para este usuário. Você também será solicitado a fornecer verificações de íris, dados de voz e configurações de telemetria e&#39;, por fim, poderá aprender a abrir o menu iniciar e concluir o OOBE.
1. Depois que você chegar à página inicial misturada, abra o menu iniciar usando o **gesto de início** que você acabou de aprender.
1. Selecione o aplicativo **configurações** e selecione **sistema.** A primeira informação que você&#39;ver é o nome do seu dispositivo, que para seu dispositivo de HoloLens 2 será &quot; um hololens- &quot; seguido por uma cadeia de seis caracteres.
1. Anote esse nome.

![Configurações de HoloLens 2-sobre](./images/hololens2-settings-about.jpg)

7. Você pode verificar se o dispositivo foi registrado com êxito no Azure AD dentro do aplicativo de configurações. Em **configurações** , selecione **contas**  ->  **acesso corporativo ou de estudante**. Nessa tela, você pode verificar se registrou com êxito ao ver &quot; conectado ao _nameofAAD_&#39;s do Azure AD. Conectado por _seunomedeusuário_ @ _nameofAAD_. onmicrosoft.com &quot; .


Para validar que o dispositivo tenha ingressado no Azure AD, é possível verificar o Azure Active Directory do [portal do Azure](https://portal.azure.com/#home)dispositivos  ->  **Azure Active Directory**  ->    ->  **todos os dispositivos** e pesquisar o nome do dispositivo. Você&#39;ser capaz de ver o dispositivo faz parte do Azure Active Directory.


![Azure Active Directory-dispositivo](./images/aad-enrollment.png)

Em seguida, você&#39;precisa fazer logon no [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Faça logon e selecione **dispositivos** e, em seguida, **todos os dispositivos**. Aqui, você pode pesquisar o seu dispositivo de HoloLens&#39;nome. Você deve ser capaz de ver seu HoloLens listado no Intune.

![Intune-dispositivo](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Validação da chamada de assistência remota

Quando você&#39;verificou que seu dispositivo está registrado no AAD e no MDM, ele&#39;o tempo para fazer uma chamada de assistência remota de teste. Para essa validação, você&#39;precisa ter o dispositivo de HoloLens e um PC com Windows 10, bem como uma segunda conta de usuário do Azure AD para o PC.

Esta etapa de validação assumirá que você concluiu anteriormente a última etapa de validação e que seu dispositivo está registrado e o usuário do Azure AD está no dispositivo.


1. Se você ainda não tiver o Microsoft Teams instalado em seu computador, poderá [baixar as equipes aqui](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Entre em equipes usando a segunda conta de usuário do Azure AD que a que está atualmente conectada ao seu HoloLens. Depois de conectado em seu PC, você estará pronto para receber a chamada.
3. Desbloqueie seu HoloLens e entre.
4. Para iniciar o aplicativo de assistência remota, abra o **menu iniciar** e selecione **assistência remota**. A assistência remota não é agrupada apenas como um aplicativo de caixa de entrada, mas fixada ao menu Iniciar do HoloLens 2&#39;s. Em um evento que você Don&#39;t vê-o fixado no menu iniciar e, em seguida, abra a lista **todos os aplicativos** para procurar por ele.
5. Depois que o auxílio remoto for iniciado, ele deverá identificar o usuário do dispositivo por meio do [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e fazer logon no aplicativo.
6. No aplicativo, selecione **Pesquisar** e procure o segundo usuário no computador. Selecione o usuário para iniciar a chamada.
7. Em seu PC, responda à chamada.

Parabéns, você&#39;ve conectado com êxito e está em sua chamada de assistência remota. Certifique-se de experimentar recursos específicos de assistência remota, como usar:

- [Anotações de tinta](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartilhar um arquivo e uma exibição em realidade misturada](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obter ajuda em outro aplicativo do HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem – manter](hololens2-cloud-connected-maintain.md)