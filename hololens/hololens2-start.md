---
title: Configurar seu HoloLens 2
description: Saiba como configurar seu HoloLens 2 pela primeira vez em uma rede Wi-Fi com uma conta da Microsoft (MSA) ou do AAD (Azure Active Directory).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189759"
---
# <a name="set-up-your-hololens-2"></a>Configurar seu HoloLens 2

Na primeira vez que ligar o HoloLens, você será orientado para configurar o dispositivo, entrar usando uma conta de usuário e calibrar o HoloLens aos seus olhos.  Esta seção aborda a experiência de configuração inicial do HoloLens 2.

Na próxima seção, você aprenderá a trabalhar com o HoloLens e a interagir com hologramas. Para ir diretamente para esse artigo, confira [Noções básicas sobre o HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Antes de começar

Antes de começar, verifique se você tem:

**Uma conexão de rede**. Você precisará conectar o HoloLens a uma rede para configurá-lo. Com o HoloLens 2, você pode se conectar usando Wi-Fi ou a ethernet (você precisará de um adaptador USB-C para Ethernet). Na primeira vez que se conectar, você precisará de uma rede aberta ou protegida por senha que não exija navegar até um site ou usar certificados para se conectar. [Saiba mais sobre os sites que o HoloLens usa](hololens-offline.md).

**Uma conta Microsoft**. Você também precisará entrar no HoloLens com uma conta Microsoft (ou com sua conta corporativa se a organização for proprietária do dispositivo). Se não tiver uma conta Microsoft, acesse [account.microsoft.com](https://account.microsoft.com) e configure uma gratuitamente.

**Um espaço seguro e bem iluminado em que não haja risco de tropeçar**. [Informações sobre integridade e segurança](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Os acessórios opcionais para conforto** que acompanham seu HoloLens, para ajudar você a ajustá-lo da melhor maneira. [Mais informações sobre ajuste e conforto](hololens2-setup.md#adjust-fit).

## <a name="set-up-windows"></a>Configurar o Windows

Na primeira vez que você iniciar o HoloLens 2, a primeira tarefa será configurar o Windows Holographic.  Ao iniciar o HoloLens, você ouvirá uma música e verá um logotipo da Microsoft.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Você verá um beija-flor voando.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Ele seguirá a sua mão.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Aparecerá um botão com o logotipo da Microsoft. Pressione o botão e o HoloLens 2 percorrerá as seguintes etapas:

1. Selecionar seu idioma.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Selecione sua região.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Calibrar o HoloLens aos seus olhos.  Se optar por ignorar a calibragem, você será avisado na próxima vez em que fizer logon. 

    1. Primeiro, você ajustará o visor.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Para calibrar, você olhará para um conjunto de alvos (chamados de joias). Não há problema se você piscar ou fechar os olhos durante a calibragem, mas tente não olhar fixamente para outros objetos no cômodo ou no espaço físico. O HoloLens usa esse processo para saber mais sobre a posição de seus olhos para que ele possa renderizar melhor seu mundo holográfico. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Após a calibragem, os hologramas serão exibidos corretamente mesmo que o visor mude de posição em sua cabeça. As informações de calibragem são armazenadas localmente no dispositivo e não são associadas a informações de conta. Para saber mais, confira [Dados de calibragem e segurança](hololens-calibration.md#calibration-data-and-security).

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Conecte-se à Internet (selecione Wi-Fi ou sua conexão Ethernet).

     O HoloLens define o fuso horário automaticamente com base nas informações obtidas da rede Wi-Fi. Após a conclusão da configuração, você pode alterar o fuso horário usando o aplicativo Configurações.

    ![Conectar ao Wi-Fi.](images/11-network.png)

    > [!NOTE] 
    > Se você passar da etapa de Wi-Fi e posteriormente precisar alternar para uma rede diferente enquanto ainda estiver na configuração, pressione os botões **Diminuir volume** e **Ligar/Desligar** simultaneamente para retornar a esta etapa se estiver executando uma versão do SO de outubro de 2019 ou posterior. Para versões anteriores, talvez seja necessário [redefinir o dispositivo](hololens-recovery.md) ou reiniciá-lo em uma localização em que a rede Wi-Fi não esteja disponível para impedir a conexão automática.
    > 
    > Observe também que, durante a Instalação do HoloLens, há um tempo limite de credenciais de dois minutos. O nome de usuário e a senha devem ser inseridos dentro de dois minutos, caso contrário, o campo do nome de usuário será limpo automaticamente.

1. O HoloLens 2 pesquisará e aplicará um perfil do Autopilot, se houver. Nenhuma ação é necessária nesta tela.
 
    ![Pesquisa de perfil do Autopilot.](images/autopilot-profile-search.png) 

1. Clique em **Aceitar** na tela de licenciamento.

    ![Contrato de licença do Windows.](images/windows-license-agreement.png)

1. Entre em sua conta de usuário. Você escolherá entre **O proprietário é meu trabalho ou escola** ou **É meu**.

    ![Definir usuário.](images/13-device-owner.png)
    - Ao escolher **O proprietário é meu trabalho ou escola**, você entra usando uma conta do Azure AD. Se a organização usar o Azure AD Premium e tiver configurado o registro de MDM automático, o HoloLens será registrado automaticamente no MDM. Se a organização não usar o Azure AD Premium, o registro de MDM automático não estará disponível. Nesse caso, você precisará [registrar manualmente o HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Insira as informações de conta de sua organização.
        1. Aceite a política de privacidade e o contrato de licença do usuário final.
        1. Entre usando as credenciais do Azure AD. Isso pode redirecionar para a página de entrada da organização.
        1. Continue a configuração do dispositivo.

    - Ao escolher **É meu**, você entra usando uma conta da Microsoft. Depois que instalação for concluída, você poderá [registrar manualmente o HoloLens no gerenciamento de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Insira as informações de sua conta Microsoft.
        2. Digite sua senha. Se a conta da Microsoft exigir uma [verificação em duas etapas (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), conclua o processo de verificação.

        
1. Configure a conexão com a Íris selecionando **Avançar**. Você passará por uma experiência semelhante à de calibragem dos olhos. Selecione **Concluído** quando a varredura for concluída. Você também pode selecionar **Ignorar** para ignorar esta etapa.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Você vai configurar um PIN para fazer logon no dispositivo. Este PIN é específico do dispositivo. 

    ![Configurar o Windows Hello.](images/setup-windows-hello.png)

    ![Configurar o PIN do Windows Hello.](images/windows-hello-pin.png)

    ![Configuração do Windows Hello bem-sucedida.](images/windows-hello-successful.png) 

    
1. Selecione se deseja habilitar a fala no HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Selecione se deseja habilitar a localização no HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Selecione o nível de telemetria. Se possível, habilite a telemetria opcional. Essas informações ajudam muito a equipe de engenharia do HoloLens.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Saiba como usar o gesto de iniciar no HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Parabéns!  A configuração está completa e você está pronto para usar o HoloLens!

## <a name="next-steps"></a>Próximas etapas

1. Comece a interagir imediatamente com a Realidade Misturada do Azure e navegar no Windows 10 com seu HoloLens. Confira no aplicativo **Dicas** para ver tutoriais práticos para interações manuais. Use o gesto de iniciar para voltar ao Início ou diga "Voltar ao início" e escolha Dicas.

1. Clique abaixo para continuar lendo sobre como utilizar o HoloLens 2.

> [!div class="nextstepaction"]
> [Conheça o HoloLens 2](hololens2-basic-usage.md)
