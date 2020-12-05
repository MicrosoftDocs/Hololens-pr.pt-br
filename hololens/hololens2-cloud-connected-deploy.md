---
title: Guia de implantação – implantação do HoloLens 2 conectado à nuvem em escala com assistência remota-implantação
description: Como validar o registro e a assistência remota para dispositivos HoloLens em uma rede conectada na nuvem
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
ms.openlocfilehash: 4f4f787d6db16655d5fe3b54438a4524bc9df78f
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196259"
---
# Implantar-guia conectado à nuvem

Agora que você tem tudo configurado, você deve estar pronto para distribuir dispositivos. No entanto, isso é quando você deve primeiro validar sua configuração. Primeiro, o processo de ingresso no AAD e registro de MDM deve ser validado, seguido verificando se uma chamada de assistência remota pode ser feita.

## Validação de registro

Com tudo configurado corretamente para o AAD e o registro de MDM agora devem ser instantâneos. Você&#39;precisa de uma conexão Wi-Fi e do dispositivo HoloLens, bem como uma das contas de usuário AAD configuradas anteriormente.

Se o seu dispositivo não&#39;não está em um estado de configurações de fábrica, agora seria um bom momento para refazer [o flash do dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Depois que seu dispositivo estiver em OOBE, você&#39;precisará começar a interagir e seguir as instruções. 
1. O aviso crítico será quando você perguntar **quem é o proprietário deste HoloLens?** Selecione **minha empresa ou escola** e insira as credenciais da sua conta do AAD.
1. Quando o registro for bem-sucedido, você&#39;será solicitado a configurar um PIN. Isso é exclusivo para este dispositivo para este usuário. Você também será solicitado a fazer verificações de voz, dados de voz e configurações de telemetria e, por fim,&#39;poderá aprender a abrir o menu iniciar e concluir o OOBE.
1. Depois que você chegar à página inicial do Mixed Reality, abra o menu iniciar usando o **gesto de início** que você acabou de aprender. 
1. Selecione o aplicativo **configurações** e selecione **sistema.** A primeira informação que você&#39;verá é o nome do seu dispositivo, que para o seu dispositivo do HoloLens 2 será &quot; &quot; seguido por uma cadeia de 6 caracteres. 
1. Tome nota desse nome.

![Configurações do HoloLens 2-sobre](./images/hololens2-settings-about.jpg)

7. Você pode verificar se o seu dispositivo foi registrado com êxito no AAD dentro do aplicativo configurações. Em **configurações** selecione **contas**  ->  **acessar trabalho ou escola**. Nesta tela, você pode verificar se inscreveu-se com êxito, conferindo-se &quot; à _nameofAAD_&#39;s do Azure AD. Conectado por _seunomedeusuário_ @ _nameofAAD_. onmicrosoft.com &quot; .

Para validar o ingresso no AAD, é possível verificar o Azure Active Directory dos dispositivos do Azure [portal](https://portal.azure.com/#home)Azure em  ->  **Azure Active Directory**  ->  **Devices**  ->  **todos os dispositivos** e pesquisar o nome do dispositivo. Você&#39;poderá ver que o dispositivo faz parte do Azure Active Directory.

![Active Directory do Azure-dispositivo](./images/aad-enrollment.png)

Em seguida,&#39;precisa conectar-se ao [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Conecte-se e selecione **dispositivos** e, em seguida, em **todos os dispositivos**. Aqui, você pode pesquisar seu dispositivo HoloLens&#39;nome do seu celular. Você deve ser capaz de ver seu HoloLens listado no Intune.

![O dispositivo do Intune](./images/endpoint-all-devices-enrolled.png)

## Validação das chamadas do recurso assistência remota

Depois que você&#39;ve verificado se o seu dispositivo está registrado no AAD e no MDM, ele&#39;o tempo para fazer uma chamada de assistência remota do teste. Para essa validação, você&#39;precisa ter o dispositivo HoloLens e um computador com o Windows 10, bem como uma segunda conta de usuário do AAD para o computador.

Esta etapa de validação presumirá que você concluiu anteriormente a última etapa de validação e seu dispositivo está registrado e o usuário do AAD está no dispositivo.

1. Se você não&#39;o Microsoft Teams já estiver instalado em seu computador, você poderá [baixar as equipes aqui](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Conecte-se ao Teams usando a segunda conta de usuário do AAD do que aquela atualmente conectada ao seu HoloLens. Depois de conectar-se ao seu computador, você estará pronto para receber a chamada.
3. Desbloqueie seu HoloLens e entre.
4. Para iniciar o aplicativo assistência remota, abra o **menu iniciar** e selecione **assistência remota**. A assistência remota não é oferecida apenas como um aplicativo de caixa de entrada, mas está fixada no menu Iniciar do HoloLens 2&#39;s. Em um evento que você Don ' t o&#39;a estar fixado ao menu iniciar e, em seguida, abrir a lista de **todos os aplicativos** para procurá-lo.
5. Depois que o recurso assistência remota iniciar, ele deve identificar o usuário do dispositivo por meio do [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e entrar no aplicativo.
6. No aplicativo, selecione **Pesquisar** e procure o segundo usuário no computador. Selecione o usuário para iniciar a chamada.
7. Do seu computador, atenda a chamada.

Parabéns, você&#39;conectado com sucesso e está em sua chamada de assistência remota. Certifique-se de experimentar recursos específicos do recurso assistência remota, como usar:

- [Anotações à tinta](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartilhar um arquivo e exibi-lo em realidade misturada](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obter ajuda em outro aplicativo do HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem-manter](hololens2-cloud-connected-maintain.md)