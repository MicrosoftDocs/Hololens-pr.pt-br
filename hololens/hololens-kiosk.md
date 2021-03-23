---
title: Configure o HoloLens como um quiosque
description: Saiba como configurar e usar uma configuração de quiosque para bloquear os aplicativos em dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: e1dd3d79d763d02d4fe04c82d8f49e8f9d85ee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445371"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configure o HoloLens como um quiosque

Você pode configurar um dispositivo HoloLens para funcionar como um dispositivo de finalidade fixa, também chamado de *quiosque,* configurando o dispositivo para ser executado no modo quiosque. O modo quiosque limita os aplicativos (ou usuários) disponíveis no dispositivo. O modo quiosque é um recurso conveniente que você pode usar para dedicar um dispositivo HoloLens a aplicativos de negócios ou para usar o dispositivo HoloLens em uma demonstração de aplicativo.

Este artigo fornece informações sobre aspectos da configuração de quiosque específicos para dispositivos HoloLens. Para obter informações gerais sobre os diferentes tipos de quiosques baseados no Windows e como configurá-los, consulte [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> O modo quiosque determina quais aplicativos estarão disponíveis quando um usuário entrar no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Isso não impede que um aplicativo "permitido" seja aberto a outro aplicativo que não seja permitido. Para impedir a abertura de aplicativos ou processos, use [Windows Defender CSP do WDAC (Application Control)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas.
>
> Saiba mais sobre os serviços da Microsoft para dar aos usuários um nível avançado de segurança que o HoloLens 2 usa, leia mais sobre a separação e isolamento de estado [- Proteções do Defender.](security-state-separation-isolation.md#defender-protections) Ou saiba como usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em [dispositivos HoloLens 2 com o Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Você pode usar o modo de quiosque em um único aplicativo ou em uma configuração de vários aplicativos e pode usar um dos três processos para configurar e implantar a configuração de quiosque.

> [!IMPORTANT]  
> Excluir a configuração de vários aplicativos remove os perfis de bloqueio do usuário que o recurso de acesso atribuído criou. No entanto, ele não reverte todas as alterações de política. Para reverter essas políticas, você precisa redefinir o dispositivo para as configurações de fábrica.

## <a name="plan-the-kiosk-deployment"></a>Planejar a implantação de quiosque

Ao planejar seu Quiosque, você precisará responder às seguintes perguntas. Aqui estão algumas decisões a ser tomadas durante a leitura desta página e algumas considerações para essas perguntas.
1. **Quem estará usando seu Quiosque e quais [tipos](hololens-identity.md) de conta estarão usando?** Esta é uma decisão que você provavelmente já tomou e não deve ser ajustada para o bem do seu Quiosque, mas afetará como o Quiosque é atribuído posteriormente.
1. **Você precisa ter quiosques diferentes por usuário/grupo ou um Quiosque não habilitado para alguns?** Em caso afirmado, você vai querer criar seu Quiosque via XML. 
1. **Quantos aplicativos estarão em seu Quiosque?** Se você tiver mais de 1 aplicativo, precisará de um Quiosque de vários aplicativos. 
1. **Quais aplicativos estarão em seu Quiosque?** Use nossa lista de AUMIDs abaixo para adicionar In-Box aplicativos além dos seus.
1. **Como você planeja implantar seu Quiosque?** Se você estiver registrando o dispositivo no MDM, sugerimos usar o MDM para implantar seu Quiosque. Se você não estiver usando o MDM, a implantação com o Pacote de Provisionamento estará disponível.  

### <a name="kiosk-mode-requirements"></a>Requisitos do modo quiosque

Você pode configurar qualquer dispositivo HoloLens 2 para usar o modo quiosque.

> [!IMPORTANT]
> O modo quiosque só estará disponível se o dispositivo tiver o Windows Holographic for Business. Todos os dispositivos HoloLens 2 são navegados com o Windows Holographic for Business e não há outras edições. Todos os dispositivos HoloLens 2 podem executar o modo Quiosque fora da caixa.
>
> Os dispositivos HoloLens (1ª geração) precisam ser atualizados em termos de com build do sistema operacional e edição do sistema operacional. Aqui estão mais informações sobre como atualizar um HoloLens (1ª geração) para a [edição do Windows Holographic for Business.](hololens1-upgrade-enterprise.md) Para atualizar um dispositivo HoloLens (1ª geração) para usar o modo quiosque, você deve primeiro certificar-se de que o dispositivo executa o Windows 10, versão 1803 ou uma versão posterior. Se você tiver usado a Ferramenta de Recuperação de Dispositivos windows para recuperar seu dispositivo HoloLens (1ª geração) para sua com build padrão ou se tiver instalado as atualizações mais recentes, seu dispositivo estará pronto para configurar.

> [!IMPORTANT]  
> Para ajudar a proteger dispositivos executados no modo de quiosque, considere adicionar políticas de gerenciamento de dispositivos que desativarão recursos como conectividade USB. Além disso, verifique as configurações do anel de atualização para garantir que as atualizações automáticas não ocorram durante o horário comercial.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Decidir entre um quiosque de aplicativo único ou um quiosque de vários aplicativos

Um quiosque de aplicativo único inicia o aplicativo especificado quando o usuário entra no dispositivo. O menu Iniciar está desabilitado, assim como a Cortana. Um dispositivo HoloLens 2 não responde ao [gesto Iniciar.](hololens2-basic-usage.md#start-gesture) Um dispositivo HoloLens (1ª geração) não responde ao gesto [de flor.](hololens1-basic-usage.md) Como apenas um aplicativo pode ser executado, o usuário não pode colocar outros aplicativos.

Um quiosque com vários aplicativos exibe o menu Iniciar quando o usuário entrar no dispositivo. A configuração do quiosque determina quais aplicativos estão disponíveis no menu Iniciar. Você pode usar um quiosque de vários aplicativos para oferecer uma experiência fácil de entender para os usuários, apresentando a eles apenas as coisas que eles precisam usar e removendo as coisas que não precisam usar.

A tabela a seguir lista os recursos dos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu Ações Rápidas |Câmera e vídeo |Miracast |Cortana |Comandos de voz internos |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Quiosque de aplicativo único |Desabilitada |Desabilitada   |Desabilitada |Desabilitada   |Desabilitada |Habilitado <sup> 1</sup> |
|Quiosque de vários aplicativos |Habilitada |Habilitado <sup> 2</sup> |Disponível <sup> 2</sup> |Disponível <sup> 2</sup> |Disponível <sup> 2, 3</sup>  |Habilitado <sup> 1</sup> |

> <sup>1 </sup> Os comandos de voz relacionados aos recursos desabilitados não funcionam.  
> <sup>2 </sup> Para obter mais informações sobre como configurar esses recursos, consulte Selecionar [aplicativos de quiosque](#plan-kiosk-apps).  
> <sup>3 </sup> Mesmo se a Cortana estiver desabilitada, os comandos de voz integrados serão habilitados.

A tabela a seguir lista os recursos de suporte do usuário dos diferentes modos de quiosque.

| &nbsp; |Tipos de usuário com suporte | Entrada automática | Vários níveis de acesso |
| --- | --- | --- | --- |
|Quiosque de aplicativo único |Conta de Serviço Gerenciado (MSA) no Azure Active Directory (Azure AD) ou conta local |Sim |Não |
|Quiosque de vários aplicativos |Conta do Azure AD |Não |Sim |

Para exemplos de como usar esses recursos, consulte a tabela a seguir.

|Use um quiosque de aplicativo único para: |Use um quiosque de vários aplicativos para: |
| --- | --- |
|Um dispositivo que executa apenas um Guia do Dynamics 365 para novos funcionários. |Um dispositivo que executa guias e assistência remota para um intervalo de funcionários. |
|Um dispositivo que executa apenas um aplicativo personalizado. |Um dispositivo que funciona como um quiosque para a maioria dos usuários (executando apenas um aplicativo personalizado), mas funciona como um dispositivo padrão para um grupo específico de usuários. |

### <a name="plan-kiosk-apps"></a>Planejar aplicativos de quiosque

Para obter informações gerais sobre como escolher aplicativos de quiosque, consulte Diretrizes para escolher um aplicativo para acesso atribuído [(modo de quiosque).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Se você usar o Windows Device Portal para configurar um quiosque de aplicativo único, selecione o aplicativo durante o processo de instalação.  

Se você usar um sistema de Gerenciamento de Dispositivo Móvel (MDM) ou um pacote de provisionamento para configurar o modo de quiosque, use o Provedor de Serviços de Configuração [(CSP) AssignedAccess para especificar aplicativos.](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) O CSP usa IDs de Modelo de Usuário de Aplicativo [(AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar aplicativos. A tabela a seguir lista os AUMIDs de alguns aplicativos in-box que você pode usar em um quiosque de vários aplicativos.

> [!IMPORTANT]
> O modo quiosque determina quais aplicativos estarão disponíveis quando um usuário entrar no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Isso não impede que um aplicativo "permitido" seja aberto a outro aplicativo que não seja permitido. Como não restringimos esse comportamento, os aplicativos ainda podem ser lançados do Edge, do Explorador de Arquivos e dos aplicativos da Microsoft Store. Se houver aplicativos específicos que você não deseja que sejam lançados a partir de um Quiosque, use o [CSP Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas. 
> 
> Além disso, o Mixed Reality Home não é capaz de ser definido como um aplicativo de quiosque.

<a id="aumids"></a>

|Nome do aplicativo |AUMID |
| --- | --- |
|Visualizador 3D |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Calendário |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|Câmera <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! Aplicativo |
|Seletor de dispositivos no HoloLens (1ª geração) |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|Seletor de Dispositivos no HoloLens 2 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Guias do Dynamics 365 |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|Hub &nbsp; de Feedback |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! Aplicativo |
|Explorador de Arquivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Filmes e TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! Aplicativo |
|Fotos |Microsoft.Windows.Photos\_8wekyb3d8bbwe\! Aplicativo |
|Configurações |HolographicSystemSettings\_cw5n1h2txyewy\! Aplicativo |
|Dicas |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 Para habilitar a captura de fotos ou vídeos, você </sup> precisa habilitar o aplicativo Câmera como um aplicativo de quiosque.  
> <sup>2 </sup> Quando você habilitar o aplicativo Câmera, esteja ciente das seguintes condições:
> - O menu Ações Rápidas inclui os botões Foto e Vídeo.  
> - Você também deve habilitar um aplicativo (como Fotos, Email ou OneDrive) que possa interagir ou recuperar imagens.  
>  
> <sup>3 Mesmo se você não habilitar a Cortana como um aplicativo de quiosque, os comandos de voz </sup> integrados serão habilitados. No entanto, comandos relacionados a recursos desabilitados não têm efeito.  
> <sup>4 </sup> Não é possível habilitar o Miracast diretamente. Para habilitar o Miracast como um aplicativo de quiosque, habilita o aplicativo Câmera e o aplicativo Seletor de Dispositivos.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planejar perfis de quiosque para usuários ou grupos

Ao criar o arquivo xml ou usar a interface do usuário do Intune para configurar um Quiosque, você precisará considerar quem será usuário do Quiosque. Uma configuração de Quiosque pode ser limitada a uma conta individual ou a grupos do Azure AD. 

Normalmente, os Quiosques são habilitados para um usuário ou grupo de usuários. No entanto, se você planeja escrever seu próprio Quiosque XML, talvez queira considerar o Acesso Atribuído Global, no qual o Quiosque é aplicado no nível do dispositivo, independentemente da Identidade. Se isso apela para [você, leia mais sobre Os Quiosques](hololens-global-assigned-access-kiosk.md) de Acesso Atribuído Global.

#### <a name="if-you-are-creating-an-xml-file"></a>Se você estiver criando um arquivo XML:
-   Muitos criam vários perfis de Quiosque e atribuem cada um a diferentes usuários/grupos. Como um Quiosque para seu Grupo do Azure AD que tem muitos aplicativos e um Visitante que tem um quiosque de vários aplicativos com um aplicativo singular.
-   Sua configuração de quiosque será chamada de **ID de Perfil** e terá um GUID.
-   Você atribuirá esse Perfil na seção configs especificando o tipo de usuário e usando o mesmo GUID para a **Id DefaultProfile**.
- Um arquivo XML pode ser criado, mas ainda aplicado a um dispositivo via MDM criando um perfil de configuração de dispositivo OMA URI personalizado e aplicando-o ao grupo de dispositivos holoLens usando o valor de URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Se você estiver criando um Quiosque no Intune.
-   Cada dispositivo pode receber apenas um único perfil de Quiosque, caso contrário, ele criará um conflito e não receberá nenhuma configuração de Quiosque. 
    -   Outros tipos de perfis e políticas, como restrições de dispositivo que não estão relacionadas ao perfil de configuração de quiosque, não conflitam com o perfil de configuração de quiosque.
-   O Quiosque será habilitado para todos os usuários que fazem parte do tipo de logon do Usuário, isso será definido com um usuário ou grupo do Azure AD. 
-   Depois que a configuração do Quiosque for definida e o tipo de **logon** do usuário (usuários que podem fazer logon no Quiosque) e os Aplicativos forem selecionados, a Configuração do Dispositivo ainda deverá ser atribuída a um grupo. Os grupos atribuídos determinam quais dispositivos recebem a configuração do dispositivo Kiosk, no entanto, não interagem se o Quiosque está habilitado ou não. 
    - Para uma discussão completa sobre os efeitos da atribuição de perfis de configuração no Intune, consulte Atribuir perfis de usuário e [dispositivo no Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Selecionar um método de implantação

Você pode selecionar um dos seguintes métodos para implantar configurações de quiosque:

- [Microsoft Intune ou outro serviço de gerenciamento de dispositivo móvel (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Como esse método exige que o Modo de Desenvolvedor seja habilitado no dispositivo, recomendamos que você o use apenas para demonstrações.

A tabela a seguir lista os recursos e benefícios de cada um dos métodos de implantação.

| &nbsp; |Implantar usando o Windows Device Portal |Implantar usando um pacote de provisionamento |Implantar usando o MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Implantar quiosques de aplicativo único   | Sim           | Sim                  | Sim  |
|Implantar quiosques de vários aplicativos    | Não            | Sim                  | Sim  |
|Implantar somente em dispositivos locais | Sim           | Sim                  | Não   |
|Implantar usando o Modo de Desenvolvedor |Obrigatório       | Não necessário            | Não necessário   |
|Implantar usando o Azure Active Directory (Azure AD)  | Não necessário            | Não necessário                   | Obrigatório  |
|Implantar automaticamente      | Não            | Não                   | Sim  |
|Velocidade de implantação            | Rápido       | Rápido                 | Modo Lento |
|Implantar em escala | Não recomendado    | Recomendações        | Recomendações |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Use o Microsoft Intune ou outro MDM para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando o Microsoft Intune ou outro sistema MDM, siga estas etapas.

1. [Prepare-se para registrar os dispositivos](#mdmenroll).
1. [Crie um perfil de configuração de quiosque.](#mdmprofile)
1. Configure o quiosque.
   - [Configure as configurações para um quiosque](#mdmconfigsingle)de aplicativo único.
   - [Configure as configurações para um quiosque de vários aplicativos.](#mdmconfigmulti)
1. [Atribua o perfil de configuração de quiosque a um grupo](#mdmassign).
1. Implante os dispositivos.
   - [Implantar um quiosque de aplicativo único.](#mdmsingledeploy)
   - [Implantar um quiosque de vários aplicativos.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, etapa 1 &ndash; Preparar para registrar os dispositivos

Você pode configurar seu sistema MDM para registrar dispositivos HoloLens automaticamente quando o usuário entrar pela primeira vez ou fazer com que os usuários inscrevam dispositivos manualmente. Os dispositivos também devem ser ingressados no domínio do Azure AD e atribuídos aos grupos apropriados.

Para obter mais informações sobre como registrar os [dispositivos, consulte Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, etapa 2 &ndash; Criar um perfil de configuração de quiosque

1. Abra o portal [do Azure](https://portal.azure.com/) e entre na sua conta de administrador do Intune.
1. Selecione **Configuração do dispositivo Microsoft Intune**  >  **-**  >  **Perfis Criar perfil**.
1. Insira um nome de perfil.
1. Selecione **Plataforma**  >  **Windows 10 e posterior e**selecione Tipo **de**perfil  > **Restrições de dispositivo**.
1. Selecione **Configurar**  >  **Quiosque**e selecione um dos seguintes:
   - Para criar um quiosque de aplicativo único, selecione **Quiosque**de modo de  >  **Quiosque único.**
   - Para criar um quiosque de vários aplicativos, selecione **Quiosque**multi app modo  >  **de quiosque**.
1. Para começar a configurar o quiosque, selecione **Adicionar**.

Suas próximas etapas diferem dependendo do tipo de quiosque que você deseja. Para obter mais informações, selecione uma das seguintes opções:  

- [Quiosque de aplicativo único](#mdmconfigsingle)
- [Quiosque de vários aplicativos](#mdmconfigmulti)

Para obter mais informações sobre como criar um perfil de configuração de quiosque, consulte Configurações do dispositivo Windows 10 e Windows Holographic for Business para ser executado como um quiosque dedicado usando [o Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, etapa 3 (aplicativo único) Configurar as configurações &ndash;  para um quiosque de aplicativo único

Esta seção resume as configurações que um quiosque de aplicativo único requer. Para obter mais detalhes, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as configurações disponíveis para quiosques de aplicativo único no Intune, consulte [Quiosques](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) de aplicativo de tela inteira único
- Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções. Se você tiver que usar uma configuração XML personalizada para configurar um quiosque em seu serviço MDM, crie um arquivo XML que defina a configuração de [quiosque](#ppkioskconfig).

1. Selecione **Tipo de logon**de usuário Conta de usuário local e insira o nome de usuário da conta local (dispositivo) ou conta da Microsoft  >  ****(MSA) que pode entrar no quiosque.
   > [!NOTE]  
   > **Os tipos de conta** de usuário de registro automático não são suportados no Windows Holographic for Business.
1. Selecione **Aplicativo tipo**De aplicativo  >  **Store**e selecione um aplicativo na lista.

Sua próxima etapa é [atribuir o](#mdmassign) perfil a um grupo.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, etapa 3 (multi app) &ndash; Configure the settings for a multi-app kiosk

Esta seção resume as configurações que um quiosque de vários aplicativos requer. Para obter informações mais detalhadas, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as configurações disponíveis para quiosques de vários aplicativos no Intune, consulte [Quiosques de vários aplicativos](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções. Se você precisar usar uma configuração XML personalizada para configurar um [quiosque](#ppkioskconfig)em seu serviço MDM, crie um arquivo XML que defina a configuração de quiosque . Se você usar um arquivo XML, certifique-se de incluir o [layout iniciar](#start-layout-for-hololens).  
- Opcionalmente, você pode usar um layout inicial personalizado com o Intune ou outros serviços MDM. Para obter mais informações, consulte [Iniciar arquivo de layout para MDM (Intune e outros)](#start-layout-file-for-mdm-intune-and-others).

1. Selecione **Destino do Windows 10 em dispositivos de modo S**  >  **Não**.  
   >[!NOTE]  
   > O modo S não é suportado no Windows Holographic for Business.
1. Selecione **Tipo de logon**do usuário O usuário ou grupo do  >  **Azure AD** ou o tipo de **logon**do usuário  >  **do HoloLens**visitante e adicione um ou mais grupos de usuários ou contas.  

   Somente os usuários que pertencem aos grupos ou contas que você especificar no **tipo de logon do** usuário podem usar a experiência de quiosque.

1. Selecione um ou mais aplicativos usando as seguintes opções:
   - Para adicionar um aplicativo de linha de negócios carregado, selecione **Adicionar aplicativo da loja** e selecione o aplicativo que você deseja.
   - Para adicionar um aplicativo especificando seu AUMID, selecione Adicionar por **AUMID** e insira o AUMID do aplicativo. [Consulte a lista de AUMIDs disponíveis](#aumids)

Sua próxima etapa é [atribuir o](#mdmassign) perfil a um grupo.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, etapa 4 Atribuir o perfil de configuração de &ndash; quiosque a um grupo

Use a **página Atribuições** do perfil de configuração de quiosque para definir onde você deseja implantar a configuração de quiosque. No caso mais simples, você atribui o perfil de configuração de quiosque a um grupo que conterá o dispositivo HoloLens quando o dispositivo se registrar no MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, etapa 5 (aplicativo único) &ndash; Implantar um quiosque de aplicativo único

Ao usar um sistema MDM, você pode registrar o dispositivo no MDM durante o OOBE. Depois que o OOBE terminar, entrar no dispositivo será fácil.

Durante o OOBE, siga estas etapas:

1. Entre usando a conta especificada no perfil de configuração do quiosque.
1. Registrar o dispositivo. Certifique-se de que o dispositivo seja adicionado ao grupo ao que o perfil de configuração de quiosque está atribuído.
1. Aguarde o fim do OOBE, para que o aplicativo da loja baixe e instale e que as políticas sejam aplicadas. Em seguida, reinicie o dispositivo.

Na próxima vez em que você entrar no dispositivo, o aplicativo de quiosque deve ser automaticamente a ser ativado.

Se você não vir sua configuração de quiosque neste ponto, [verifique o status da atribuição](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, etapa 5 (vários aplicativos) &ndash; Implantar um quiosque de vários aplicativos

Ao usar um sistema MDM, você pode ingressar o dispositivo no locatário do Azure AD e registrar o dispositivo no MDM durante o OOBE. Se apropriado, forneça as informações de registro aos usuários para que eles as tenham disponíveis durante o processo OOBE.

> [!NOTE]  
> Se você atribuiu o perfil de configuração de quiosque a um grupo que contém usuários, certifique-se de que uma dessas contas de usuário seja a primeira conta a entrar no dispositivo.

Durante o OOBE, siga estas etapas:

1. Entre usando a conta que pertence ao grupo de tipo **de logon do** usuário.
1. Registrar o dispositivo.
1. Aguarde que todos os aplicativos que fazem parte do perfil de configuração de quiosque baixem e instalem. Além disso, aguarde que as políticas sejam aplicadas.  
1. Após a finalização do OOBE, você pode instalar aplicativos adicionais da Microsoft Store ou sideloading. [Aplicativos necessários](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) para o grupo que o dispositivo pertence a instalar automaticamente.
1. Depois que a instalação terminar, reinicie o dispositivo.

Na próxima vez que você entrar no dispositivo usando uma conta que pertence ao tipo de **logon**do usuário, o aplicativo de quiosque deve ser acionada automaticamente.

Se você não vir sua configuração de quiosque neste ponto, [verifique o status da atribuição](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando um pacote de provisionamento, siga estas etapas.

1. [Crie um arquivo XML que define a configuração do quiosque.](#ppkioskconfig), incluindo um [layout de início.](#start-layout-for-hololens)
2. [Adicione o arquivo XML a um pacote de provisionamento.](#ppconfigadd)
3. [Aplique o pacote de provisionamento ao HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Pacote de provisionamento, etapa 1 &ndash; Criar um arquivo XML de configuração de quiosque

Siga as instruções gerais para criar um arquivo XML de configuração de [quiosque](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)para área de trabalho do Windows, exceto pelo seguinte:

- Não inclua aplicativos Clássicos do Windows (Win32). O HoloLens não dá suporte a esses aplicativos.
- Use o [XML de layout inicial do espaço reservado](#start-layout-for-hololens) para o HoloLens.
- Opcional: Adicionar acesso de convidado à configuração do quiosque

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Opcional: Adicionar acesso de convidado à configuração do quiosque

Na seção [ **Configs** do arquivo XML,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)você pode configurar um grupo especial chamado **Visitante** para permitir que os convidados usem o quiosque. Quando o quiosque é configurado **** para dar suporte ao grupo especial visitante, uma opção "**Guest**" é adicionada à página de login. A **conta** de convidado não exige uma senha e os dados associados à conta são excluídos quando a conta sai.

Para **habilitar a conta de** convidado, adicione o seguinte trecho ao XML de configuração do quiosque:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Layout inicial de espaço reservado para HoloLens

Se você usar um [pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque de vários aplicativos, o procedimento exigirá um layout iniciar. A personalização do layout inicial não é suportada no Windows Holographic for Business. Portanto, você terá que usar um layout inicial de espaço reservado.

> [!NOTE]  
> Como um quiosque de aplicativo único inicia o aplicativo de quiosque quando um usuário entra, ele não usa um menu Iniciar e não precisa ter um layout iniciar.

> [!NOTE]  
> Se você usar [o MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque de vários aplicativos, poderá usar opcionalmente um layout iniciar. Para obter mais informações, [consulte Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).

Para o layout iniciar, adicione a seguinte **seção StartLayout** ao arquivo XML de provisionamento de quiosque:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Arquivo de layout inicial de espaço reservado para MDM (Intune e outros)

Salve o exemplo a seguir como um arquivo XML. Você pode usar esse arquivo ao configurar o quiosque de vários aplicativos no Microsoft Intune (ou em outro serviço MDM que fornece um perfil de quiosque).

> [!NOTE]
> Se você tiver que usar uma configuração XML personalizada e completa para configurar um quiosque em seu serviço MDM, use as instruções de layout iniciar para um pacote [de provisionamento](#start-layout-for-hololens).

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package

1. Abra [o Designer de Configuração do Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Selecione **Provisionamento Avançado**, insira um nome para seu projeto e selecione **Avançar**.
1. Selecione **Windows 10 Holographic**e, em seguida, selecione **Next**.
1. Selecione **Concluir**. O espaço de trabalho para seu pacote é aberto.
1. Selecione **Configurações de tempo de execução**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. No painel central, selecione **Procurar para** localizar e selecionar o arquivo XML de configuração de quiosque que você criou.

   ![Captura de tela do campo MultiAppAssignedAccessSettings no Designer de Configuração do Windows](./images/multiappassignedaccesssettings.png)

1. **Opcional**. (Se você quiser aplicar o pacote de provisionamento após a configuração inicial do dispositivo e houver um usuário de administração já disponível no dispositivo de quiosque, ignore esta etapa.) Selecione **Configurações de tempo de execução** &gt; **Contas** &gt; **Usuários**e crie uma conta de usuário. Forneça um nome de usuário e uma senha e selecione **Administradores de Grupo**  >  **de Usuários.**  
  
     Usando essa conta, você pode exibir o status e os logs de provisionamento.  
1. **Opcional**. (Se você já tiver uma conta não administrativa no dispositivo de quiosque, ignore esta etapa.) Selecione **Configurações de tempo de execução** &gt; **Contas** &gt; **Usuários**e crie uma conta de usuário local. Certifique-se de que o nome de usuário seja o mesmo da conta especificada no XML de configuração. Selecione **UserGroup**  >  **Standard Users**.
1. Selecione **Salvar**  >  **arquivo**.
1. Selecione **Exportar**  >  **pacote de Provisionamento**e selecione Administrador **de**IT  >  **do Proprietário.** Isso define a precedência desse pacote de provisionamento maior do que os pacotes de provisionamento que são aplicados a esse dispositivo de outras fontes.
1. Selecione **Avançar**.
1. Na página **Segurança do pacote de provisionamento,** selecione uma opção de segurança.
   > [!IMPORTANT]  
   > Se você selecionar **Habilitar**assinatura de pacote, você também terá que selecionar um certificado válido a ser usado para assinar o pacote. Para fazer isso, selecione **Procurar** e selecione o certificado que você deseja usar para assinar o pacote.
   
   > [!CAUTION]  
   > Não selecione **Habilitar criptografia de pacote**. Em dispositivos HoloLens, essa configuração causa falha no provisionamento.
1. Selecione **Avançar**.
1. Especifique o local de saída onde você deseja que o pacote de provisionamento vá quando ele for criado. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída. Se você quiser alterar o local de saída, selecione **Procurar**. Quando terminar, selecione **Next**.
1. Selecione **Criar** para começar a criar o pacote. O pacote de provisionamento não leva muito tempo para compilar. A página de com build exibe as informações do projeto e a barra de progresso indica o status da com build.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Pacote de provisionamento, etapa 3 &ndash; Aplicar o pacote de provisionamento ao HoloLens

O artigo "Configurar o HoloLens usando um pacote de provisionamento" fornece instruções detalhadas para aplicar o pacote de provisionamento nas seguintes circunstâncias:

- Inicialmente, você pode [aplicar um pacote de provisionamento ao HoloLens durante a instalação.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Você também pode [aplicar um pacote de provisionamento ao HoloLens após a instalação](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Usar o Windows Device Portal para configurar um quiosque de aplicativo único

Para configurar o modo de quiosque usando o Windows Device Portal, siga estas etapas.

1. [Configurar o dispositivo HoloLens para usar o Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). O Device Portal é um servidor Web no HoloLens ao qual você pode se conectar usando um navegador da Web em seu computador.

    > [!CAUTION]
    > Ao configurar o HoloLens para usar o Portal de Dispositivos, você precisa habilitar o Modo de Desenvolvedor no dispositivo. O Modo de Desenvolvedor em um dispositivo que tenha o Windows Holographic for Business permite que você carregue aplicativos de side load. No entanto, essa configuração cria um risco de que um usuário possa instalar aplicativos que não foram certificados pela Microsoft Store. Os administradores podem bloquear a capacidade de habilitar o Modo de Desenvolvedor usando a configuração **ApplicationManagement/AllowDeveloper Unlock** no [CSP de Política](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider). [Saiba mais sobre o Modo de desenvolvedor.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Em um computador, conecte-se ao HoloLens usando [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Siga um destes procedimentos:
   - Se você estiver se conectando ao Windows Device Portal pela primeira vez, [crie um nome de usuário e uma senha](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Insira o nome de usuário e a senha que você definiu anteriormente.

    > [!TIP]
    > Se você vir um erro de certificado no navegador, siga [estas etapas para solução de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. No Portal de Dispositivos do Windows, selecione **Modo quiosque**.

1. Selecione **Habilitar Modo de Quiosque,** selecione um aplicativo a ser executado quando o dispositivo for iniciado e selecione **Salvar**.

    ![Modo de quiosque](images/kiosk.png)
1. Reinicie o HoloLens. Se você ainda tiver sua página do Portal de Dispositivo aberta, poderá selecionar **Reiniciar** na parte superior da página.

> [!NOTE]
> O modo de quiosque pode ser definido por meio da API REST do Device Portal fazendo um POST para /api/holographic/kioskmode/settings com um parâmetro de cadeia de caracteres de consulta obrigatório ("kioskModeEnabled" com um valor "verdadeiro" ou "false") e um parâmetro opcional ("startupApp" com um valor de um nome de pacote). Lembre-se de que o Device Portal destina-se apenas a desenvolvedores e não deve ser habilitado em dispositivos que não sejam desenvolvedores. A API REST está sujeita a alterações em atualizações/versões futuras.

## <a name="more-information"></a>Mais informações

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Assista como configurar um quiosque usando um pacote de provisionamento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Acesso Atribuído Global – Modo de Quiosque
- Gerenciamento de Identidade Reduzida para Quiosque, habilitando o novo método Kiosk que aplica o modo Quiosque no nível do sistema.

Esse novo recurso permite que um administrador de IT configure um dispositivo do HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com qualquer identidade no sistema e se aplica a todos que se insinuem no dispositivo. Consulte a [documentação de quiosque](hololens-global-assigned-access-kiosk.md) de acesso atribuído global do HoloLens para obter mais detalhes sobre esse novo recurso.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Início automático de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada com o lançamento automático de aplicativos, aumentando ainda mais as seleções de interface do usuário e aplicativo escolhidas para experiências de modo Quiosque.

Aplica-se apenas ao modo de quiosque de vários aplicativos e apenas 1 aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração do Acesso Atribuído. 

O aplicativo é automaticamente lançado quando o usuário faz logor. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações no comportamento do modo quiosque para tratamento de falhas
- Modo Quiosque mais seguro eliminando aplicativos disponíveis em falhas no modo Quiosque. 

Anteriormente, ao encontrar falhas na aplicação do modo quiosque, o HoloLens era usado para mostrar todos os aplicativos no menu iniciar. Agora, no Windows Holographic versão 20H2, no caso de falhas, nenhum aplicativo será mostrado no menu iniciar como abaixo: 

![Imagem da aparência do modo Quiosque agora quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cache Azure AD Group membership for offline Kiosk
- Quiosques offline habilitados para uso com grupos do Azure AD por até 60 dias.

Essa política controla por quantos dias, o cache de associação de grupo do Azure AD tem permissão para ser usado para configurações de Acesso Atribuído destinados a grupos do Azure AD para usuários assinados. Depois que esse valor de política for definido como valor maior do que 0, o cache será usado caso contrário, não.  

Nome: AADGroupMembershipCacheValidityInDays Valor de URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 dias  
Max - 60 dias 

Etapas para usar essa política corretamente: 
1. Crie um perfil de configuração de dispositivo para grupos de quiosque destinados ao Azure AD e atribua-o aos dispositivos do HoloLens. 
1. Crie uma configuração de dispositivo baseado em URI OMA personalizada que define esse valor de política como o número desejado de dias (> 0) e atribua-o aos dispositivos HoloLens. 
    1. O valor de URI deve ser inserido na caixa de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre mín/máximo permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário do Azure AD 1 entre quando a Internet estiver disponível, quando o usuário entrar e a associação ao grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário do Azure AD 1 pode deixar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita o número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD N. O ponto chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet para que, pelo menos uma vez, possamos determinar que ele é membro do grupo do Azure AD para o qual a configuração do Quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para que um usuário do Azure AD experimente o comportamento de falha mencionado em ambientes "desconectados". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Exemplos de código de quiosque XML para HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Modo de quiosque de vários aplicativos destinado a um grupo do Azure AD. 
Este quiosque implanta um Quiosque que, para usuários no grupo do Azure AD, terá um Quiosque habilitado que inclui os três aplicativos: Configurações, Assistência Remota e Hub de Feedback. Para modificar esse exemplo a ser usado imediatamente, certifique-se de alterar o GUID realçado abaixo para corresponder a um grupo do Azure AD por conta própria. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Modo de quiosque de vários aplicativos destinado à conta do Azure AD.
Esse quiosque implanta um Quiosque para um único usuário, ele terá um Quiosque habilitado que inclui os três aplicativos: Configurações, Assistência Remota e Hub de Feedback. Para modificar esse exemplo a ser usado imediatamente, certifique-se de alterar a conta realçada abaixo para corresponder a uma conta do Azure AD própria. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

