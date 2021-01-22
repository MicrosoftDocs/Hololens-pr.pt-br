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
ms.openlocfilehash: 245de50fcaaf1235cce02cd1b6cae921b64f2851
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283982"
---
# Configure o HoloLens como um quiosque

Você pode configurar um dispositivo HoloLens para funcionar como um dispositivo de finalidade fixa, também chamado de *quiosque,* configurando o dispositivo para ser executado no modo de quiosque. O modo de quiosque limita os aplicativos (ou usuários) disponíveis no dispositivo. O modo de quiosque é um recurso conveniente que você pode usar para dedicar um dispositivo HoloLens a aplicativos de negócios ou para usar o dispositivo HoloLens em uma demonstração de aplicativo.

Este artigo fornece informações sobre aspectos da configuração de quiosque específicos para dispositivos HoloLens. Para obter informações gerais sobre os diferentes tipos de quiosques baseados no Windows e como configurá-los, consulte Configurar [quiosques](https://docs.microsoft.com/windows/configuration/kiosk-methods)e sinais digitais em edições desktop do Windows.  

> [!IMPORTANT]  
> O modo de quiosque determina quais aplicativos estarão disponíveis quando um usuário entrar no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Isso não impede que um aplicativo "permitido" abrir outro aplicativo que não é permitido. Para bloquear a abertura de aplicativos ou processos, use o CSP do [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas.
>
> Saiba mais sobre os serviços Microsoft para dar aos usuários um nível avançado de segurança que o HoloLens 2 usa, leia mais sobre separação e isolamento de estado - proteções [do Defender](security-state-separation-isolation.md#defender-protections). Ou saiba como usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em [dispositivos HoloLens 2 com o Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Você pode usar o modo de quiosque em uma configuração de aplicativo único ou de vários aplicativos e pode usar um dos três processos para configurar e implantar a configuração de quiosque.

> [!IMPORTANT]  
> Excluir a configuração de vários aplicativos remove os perfis de bloqueio do usuário que o recurso de acesso atribuído criou. No entanto, ele não reverte todas as alterações de política. Para reverter essas políticas, você precisa redefinir o dispositivo para as configurações de fábrica.

## Planejar a implantação de quiosque

Ao planejar seu Quiosque, você precisará ser capaz de responder às seguintes perguntas. Aqui estão algumas decisões a considerar ao ler esta página e algumas considerações para essas perguntas.
1. **Quem estará usando seu Quiosque e que tipo [de](hololens-identity.md) conta eles usarão?** Esta é uma decisão que você provavelmente já tomou e não deve ser ajustada para o bem do seu Quiosque, mas afetará como o Quiosque será atribuído posteriormente.
1. **Você precisa ter Quiosques diferentes por usuário/grupo ou um Quiosque não habilitado para alguns?** Se sim, você vai querer criar seu Quiosque via XML. 
1. **Quantos aplicativos estarão em seu Quiosque?** Se você tiver mais de 1 aplicativo, precisará de um Quiosque de vários aplicativos. 
1. **Quais aplicativos estarão em seu Quiosque?** Use nossa lista de AUMIDs abaixo para adicionar In-Box aplicativos, além dos seus próprios.
1. **Como você planeja implantar seu Quiosque?** Se você estiver registrando dispositivo no MDM, sugerimos usar o MDM para implantar seu quiosque. Se você não estiver usando o MDM, a implantação com o Pacote de Provisionamento estará disponível.  

### Requisitos do modo de quiosque

Você pode configurar qualquer dispositivo HoloLens 2 para usar o modo de quiosque.

> [!IMPORTANT]
> O modo de quiosque só estará disponível se o dispositivo tiver o Windows Holographic for Business. Todos os dispositivos HoloLens 2 são compatíveis com o Windows Holographic for Business e não há outras edições. Cada dispositivo HoloLens 2 é capaz de executar o modo de quiosque de forma in-loco.
>
> Os dispositivos do HoloLens (1ª geração) precisam ser atualizados em termos de com build do sistema operacional e edição do sistema operacional. Veja mais informações sobre como atualizar um HoloLens (1ª geração) para a [edição Windows Holographic for Business.](hololens1-upgrade-enterprise.md) Para atualizar um dispositivo HoloLens (1ª geração) para usar o modo de quiosque, primeiro você deve certificar-se de que o dispositivo executa o Windows 10, versão 1803 ou uma versão posterior. Se você tiver usado a Ferramenta de Recuperação de Dispositivo do Windows para recuperar seu dispositivo HoloLens (1ª geração) para sua com build padrão ou se tiver instalado as atualizações mais recentes, seu dispositivo estará pronto para ser configurada.

> [!IMPORTANT]  
> Para ajudar a proteger os dispositivos que são executados no modo de quiosque, considere adicionar políticas de gerenciamento de dispositivos que desativarão recursos como conectividade USB. Além disso, verifique as configurações do anel de atualização para garantir que as atualizações automáticas não ocorram durante o horário comercial.

### Decidir entre um quiosque de aplicativo único ou um quiosque de vários aplicativos

Um quiosque de aplicativo único inicia o aplicativo especificado quando o usuário entra no dispositivo. O menu Iniciar está desabilitado, assim como a Cortana. Um dispositivo HoloLens 2 não responde ao [gesto de iniciar.](hololens2-basic-usage.md#start-gesture) Um dispositivo HoloLens (1ª geração) não responde ao gesto [de abrir](hololens1-basic-usage.md) a mão. Como apenas um aplicativo pode ser executado, o usuário não pode colocar outros aplicativos.

Um quiosque de vários aplicativos exibe o menu Iniciar quando o usuário se conectado ao dispositivo. A configuração de quiosque determina quais aplicativos estão disponíveis no menu Iniciar. Você pode usar um quiosque de vários aplicativos para fornecer uma experiência fácil de entender para os usuários apresentando a eles apenas as coisas que eles precisam usar e removendo o que eles não precisam usar.

A tabela a seguir lista os recursos de recursos nos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu Ações Rápidas |Câmera e vídeo |Miracast |Cortana |Comandos de voz internos |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Quiosque de aplicativo único |Desabilitada |Desabilitada   |Desabilitada |Desabilitada   |Desabilitada |Habilitado <sup> 1</sup> |
|Quiosque de vários aplicativos |Habilitado |Habilitado <sup> 2</sup> |Disponível <sup> 2</sup> |Disponível <sup> 2</sup> |Disponível <sup> 2, 3</sup>  |Habilitado <sup> 1</sup> |

> <sup>1 </sup> Comandos de voz relacionados a recursos desabilitados não funcionam.  
> <sup>2 </sup> Para obter mais informações sobre como configurar esses recursos, consulte Selecionar [aplicativos de quiosque.](#plan-kiosk-apps)  
> <sup>3 </sup> Mesmo se a Cortana estiver desabilitada, os comandos de voz integrados serão habilitados.

A tabela a seguir lista os recursos de suporte do usuário dos diferentes modos de quiosque.

| &nbsp; |Tipos de usuário com suporte | Entrada automática | Vários níveis de acesso |
| --- | --- | --- | --- |
|Quiosque de aplicativo único |Conta de Serviço Gerenciado (MSA) no Azure Active Directory (Azure AD) ou conta local |Sim |Não |
|Quiosque de vários aplicativos |Conta do Azure AD |Não |Sim |

Para exemplos de como usar esses recursos, consulte a tabela a seguir.

|Use um quiosque de aplicativo único para: |Use um quiosque de vários aplicativos para: |
| --- | --- |
|Um dispositivo que executa apenas um Guia do Dynamics 365 para novos funcionários. |Um dispositivo que executa guias e assistência remota para uma variedade de funcionários. |
|Um dispositivo que executa apenas um aplicativo personalizado. |Um dispositivo que funciona como um quiosque para a maioria dos usuários (executando apenas um aplicativo personalizado), mas funciona como um dispositivo padrão para um grupo específico de usuários. |

### Planejar aplicativos de quiosque

Para obter informações gerais sobre como escolher aplicativos de quiosque, consulte Diretrizes para escolher um aplicativo para acesso atribuído [(modo de quiosque).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Se você usar o Windows Device Portal para configurar um quiosque de aplicativo único, selecione o aplicativo durante o processo de configuração.  

Se você usar um sistema de Gerenciamento de Dispositivo Móvel (MDM) ou um pacote de provisionamento para configurar o modo de quiosque, use o CSP (Provedor de Serviços de [Configuração) AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) para especificar aplicativos. O CSP usa IDs de modelo de usuário [de aplicativo (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar aplicativos. A tabela a seguir lista as AUMIDs de alguns aplicativos de caixa de correio que você pode usar em um quiosque de vários aplicativos.

> [!IMPORTANT]
> O modo de quiosque determina quais aplicativos estarão disponíveis quando um usuário entrar no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Isso não impede que um aplicativo "permitido" abrir outro aplicativo que não é permitido. Como não restringimos esse comportamento, os aplicativos ainda podem ser lançados no Edge, no Explorador de Arquivos e nos aplicativos da Microsoft Store. Se houver aplicativos específicos que você não deseja que sejam lançados em um Quiosque, use o CSP do [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas. 
> 
> Além disso, a Página Home da Realidade Misturada não pode ser definida como um aplicativo de quiosque.

<a id="aumids"></a>

|Nome do aplicativo |AUMID |
| --- | --- |
|Visualizador 3D |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Calendário |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|Câmera <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! Aplicativo |
|Seletor de Dispositivos no HoloLens (1ª geração) |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|Seletor de Dispositivos no HoloLens 2 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Guias do Dynamics 365 |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Assistência Remota do Dynamics 365 |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|Hub de &nbsp; Feedback |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! Aplicativo |
|Explorador de Arquivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Filmes e TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! Aplicativo |
|Fotos |Microsoft.Windows.Photos\_8wekyb3d8bbwe\! Aplicativo |
|Configurações |HolographicSystemSettings\_cw5n1h2txyewy\! Aplicativo |
|Dicas |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 Para habilitar a captura de fotos ou vídeos, você precisa habilitar o </sup> aplicativo Câmera como um aplicativo de quiosque.  
> <sup>2 </sup> Ao habilitar o aplicativo Câmera, esteja ciente das seguintes condições:
> - O menu Ações Rápidas inclui os botões Foto e Vídeo.  
> - Você também deve habilitar um aplicativo (como Fotos, Email ou OneDrive) que possa interagir ou recuperar imagens.  
>  
> <sup>3 Mesmo que você não habilita a Cortana como um aplicativo de </sup> quiosque, os comandos de voz integrados são habilitados. No entanto, comandos relacionados a recursos desabilitados não têm efeito.  
> <sup>4 </sup> Você não pode habilitar Miracast diretamente. Para habilitar o Miracast como um aplicativo de quiosque, habilita o aplicativo Câmera e o aplicativo Seletor de Dispositivos.

### Planejar perfis de quiosque para usuários ou grupos

Ao criar o arquivo xml ou usar a interface do usuário do Intune para configurar um Quiosque, você precisará considerar quem será o usuário do Quiosque. Uma configuração de Quiosque pode ser limitada a uma conta individual ou a grupos do Azure AD. 

Normalmente, os Quiosques estão habilitados para um usuário ou grupo de usuários. No entanto, se você planeja escrever seu próprio Quiosque XML, considere o Acesso Global Atribuído, no qual o Quiosque é aplicado no nível do dispositivo, independentemente da Identidade. Se isso for atraente para [você, leia mais sobre Os Quiosques](hololens-global-assigned-access-kiosk.md) de Acesso Atribuído Global.

#### Se você estiver criando um arquivo XML:
-   Você pode criar vários perfis de Quiosque e atribuí-los a diferentes usuários/grupos. Como um Quiosque para seu Grupo do Azure AD que tem muitos aplicativos e um Visitante que tem um quiosque de vários aplicativos com um aplicativo singular.
-   Sua configuração de quiosque será chamada de **ID de Perfil** e terá um GUID.
-   Você atribuirá esse Perfil na seção configs especificando o tipo de usuário e usando o mesmo GUID para **a ID de DefaultProfile**.
- Um arquivo XML pode ser criado, mas ainda aplicado a um dispositivo via MDM criando um perfil de configuração de dispositivo OMA URI personalizado e aplicando-o ao grupo de dispositivos do HoloLens usando o valor de URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Se você estiver criando um Quiosque no Intune.
-   Cada dispositivo pode receber apenas um único perfil de Quiosque, caso contrário, ele criará um conflito e não receberá nenhuma configuração de Quiosque. 
    -   Outros tipos de perfis e políticas, como restrições de dispositivo que não estão relacionadas ao perfil de configuração de quiosque, não estão em conflito com o perfil de configuração de quiosque.
-   O Quiosque será habilitado para todos os usuários que fazem parte do tipo de logon do usuário, isso será definido com um usuário ou grupo do Azure AD. 
-   Depois que a configuração de Quiosque for definida e o tipo de logon do usuário (usuários que podem fazer **logon** no Quiosque) e os Aplicativos forem selecionados, a Configuração de Dispositivo ainda deverá ser atribuída a um grupo. Os grupos atribuídos determinam quais dispositivos recebem a configuração do dispositivo de Quiosque, no entanto, não interagem se o Quiosque estiver habilitado ou não. 
    - Para uma discussão completa sobre os efeitos da atribuição de perfis de configuração no Intune, confira Atribuir perfis de usuário e dispositivo [no Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-profile-assign)

### Selecionar um método de implantação

Você pode selecionar um dos seguintes métodos para implantar configurações de quiosque:

- [Microsoft Intune ou outro serviço de gerenciamento de dispositivo móvel (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Como esse método exige que o Modo de Desenvolvedor seja habilitado no dispositivo, recomendamos que você o use somente para demonstrações.

A tabela a seguir lista os recursos e os benefícios de cada um dos métodos de implantação.

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

## Usar o Microsoft Intune ou outro MDM para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando o Microsoft Intune ou outro sistema MDM, siga estas etapas.

1. [Prepare-se para registrar os dispositivos.](#mdmenroll)
1. [Crie um perfil de configuração de quiosque.](#mdmprofile)
1. Configure o quiosque.
   - [Definir as configurações para um quiosque de aplicativo único.](#mdmconfigsingle)
   - [Definir as configurações para um quiosque de vários aplicativos.](#mdmconfigmulti)
1. [Atribua o perfil de configuração de quiosque a um grupo.](#mdmassign)
1. Implante os dispositivos.
   - [Implante um quiosque de aplicativo único.](#mdmsingledeploy)
   - [Implante um quiosque com vários aplicativos.](#mdmmultideploy)

### <a id="mdmenroll"></a>MDM, etapa 1 &ndash; Prepare-se para registrar os dispositivos

Você pode configurar seu sistema MDM para registrar dispositivos HoloLens automaticamente quando o usuário entrar pela primeira vez ou fazer com que os usuários inscrevam dispositivos manualmente. Os dispositivos também devem ser ingressados no domínio do Azure AD e atribuídos aos grupos apropriados.

Para obter mais informações sobre como registrar os dispositivos, consulte Registrar o [HoloLens no MDM](hololens-enroll-mdm.md) e nos métodos de registro do [Intune para dispositivos Windows.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a id="mdmprofile"></a>MDM, etapa 2 &ndash; Criar um perfil de configuração de quiosque

1. Abra o portal [do Azure](https://portal.azure.com/) e entre em sua conta de administrador do Intune.
1. Selecione **a configuração de dispositivo do Microsoft Intune**  >  **-**  >  **Perfis Criar perfil**.
1. Insira um nome de perfil.
1. Selecione **a plataforma**Windows  >  **10 e posterior e,** em seguida, selecione Restrições de dispositivo do **tipo**  > **perfil.**
1. Selecione **Configurar**  >  **Quiosque**e, em seguida, selecione um dos seguintes:
   - Para criar um quiosque de aplicativo único, selecione quiosque de modo de **quiosque**de modo  >  **de quiosque de**aplicativo único.
   - Para criar um quiosque de vários aplicativos, selecione **quiosque**de vários aplicativos do Modo  >  **de Quiosque.**
1. Para começar a configurar o quiosque, selecione **Adicionar**.

As próximas etapas são diferentes, dependendo do tipo de quiosque que você deseja. Para obter mais informações, selecione uma das seguintes opções:  

- [Quiosque de aplicativo único](#mdmconfigsingle)
- [Quiosque de vários aplicativos](#mdmconfigmulti)

Para obter mais informações sobre como criar um perfil de configuração de quiosque, consulte as configurações de dispositivo do Windows 10 e do Windows Holographic for Business para executar como um quiosque dedicado usando o [Intune.](https://docs.microsoft.com/intune/configuration/kiosk-settings)

### <a id="mdmconfigsingle"></a>MDM, etapa 3 (aplicativo único) Definir as configurações para &ndash;  um quiosque de aplicativo único

Esta seção resume as configurações que um quiosque de aplicativo único requer. Para obter mais detalhes, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte Como configurar o modo de [quiosque usando o Microsoft Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Para obter mais informações sobre as configurações disponíveis para quiosques de aplicativo único no Intune, consulte [Quiosques](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) de aplicativo de tela inteira único
- Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções. Se você tiver que usar uma configuração XML personalizada para configurar um quiosque em seu serviço MDM, crie um arquivo XML que defina a configuração de [quiosque.](#ppkioskconfig)

1. Selecione Tipo de **logon**do usuário Conta de usuário local e insira o nome de usuário da conta local (dispositivo) ou conta  >  **** da Microsoft (MSA) que pode entrar no quiosque.
   > [!NOTE]  
   > **Os tipos de conta** de usuário de registro automático não são suportados no Windows Holographic for Business.
1. Selecione **o aplicativo da**Loja do tipo  >  **de**aplicativo e selecione um aplicativo na lista.

Sua próxima etapa é [atribuir o](#mdmassign) perfil a um grupo.

### <a id="mdmconfigmulti"></a>MDM, etapa 3 (vários aplicativos) Definir as configurações para um &ndash; quiosque de vários aplicativos

Esta seção resume as configurações que um quiosque de vários aplicativos requer. Para obter informações mais detalhadas, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte Como configurar o modo de [quiosque usando o Microsoft Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Para obter mais informações sobre as configurações disponíveis para quiosques de vários aplicativos no Intune, consulte [Quiosques de vários aplicativos](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções. Se você precisar usar uma configuração XML personalizada para configurar um quiosque em seu serviço MDM, crie um arquivo XML que defina a configuração de [quiosque.](#ppkioskconfig) Se você usar um arquivo XML, certifique-se de incluir o [layout da iniciar.](#start-layout-for-hololens)  
- Opcionalmente, você pode usar um layout de iniciar personalizado com o Intune ou outros serviços MDM. Para obter mais informações, [consulte o arquivo de layout da iniciar para MDM (Intune e outros).](#start-layout-file-for-mdm-intune-and-others)

1. Select **Target Windows 10 in S mode devices**  >  **No**.  
   >[!NOTE]  
   > O modo S não é suportado no Windows Holographic for Business.
1. Selecione o tipo de **logon**do usuário do  >  **Azure AD** usuário ou grupo ou tipo de **logon**de usuário do  >  **HoloLens**visitante e, em seguida, adicione um ou mais grupos de usuários ou contas.  

   Somente os usuários que pertencem aos grupos ou contas que você especificar no tipo de **logon do** usuário podem usar a experiência de quiosque.

1. Selecione um ou mais aplicativos usando as seguintes opções:
   - Para adicionar um aplicativo de linha de negócios carregado, selecione Adicionar aplicativo **da** Loja e, em seguida, selecione o aplicativo que você deseja.
   - Para adicionar um aplicativo especificando sua AUMID, selecione Adicionar por **AUMID** e insira a AUMID do aplicativo. [Ver a lista de AUMIDs disponíveis](#aumids)

Sua próxima etapa é [atribuir o](#mdmassign) perfil a um grupo.

### <a id="mdmassign"></a>MDM, etapa 4 &ndash; Atribuir o perfil de configuração de quiosque a um grupo

Use a **página Atribuições** do perfil de configuração de quiosque para definir onde você deseja implantar a configuração de quiosque. No caso mais simples, você atribui o perfil de configuração de quiosque a um grupo que conterá o dispositivo HoloLens quando o dispositivo se registrar no MDM.

### <a id="mdmsingledeploy"></a>MDM, etapa 5 (aplicativo único) &ndash; Implantar um quiosque de aplicativo único

Ao usar um sistema MDM, você pode registrar o dispositivo no MDM durante o OOBE. Depois que a OOBE terminar, é fácil entrar no dispositivo.

Durante a OOBE, siga estas etapas:

1. Entre usando a conta especificada no perfil de configuração de quiosque.
1. Registrar o dispositivo. Certifique-se de que o dispositivo seja adicionado ao grupo ao que o perfil de configuração de quiosque está atribuído.
1. Aguarde a OOBE terminar, para que o aplicativo da loja seja baixado e instalado e para que as políticas sejam aplicadas. Em seguida, reinicie o dispositivo.

Na próxima vez que você entrar no dispositivo, o aplicativo de quiosque deverá ser automaticamente iniciar.

Se você não vir sua configuração de quiosque neste ponto, verifique [o status da atribuição.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

### <a id="mdmmultideploy"></a>MDM, etapa 5 (vários aplicativos) Implantar um &ndash; quiosque de vários aplicativos

Ao usar um sistema MDM, você pode ingressar o dispositivo em seu locatário do Azure AD e registrar o dispositivo no MDM durante o OOBE. Se apropriado, forneça as informações de registro aos usuários para que eles as tenham disponíveis durante o processo de OOBE.

> [!NOTE]  
> Se você atribuiu o perfil de configuração de quiosque a um grupo que contém usuários, certifique-se de que uma dessas contas de usuário seja a primeira conta a entrar no dispositivo.

Durante a OOBE, siga estas etapas:

1. Entre usando a conta que pertence ao grupo de tipos **de logon do** usuário.
1. Registrar o dispositivo.
1. Aguarde até que todos os aplicativos que fazem parte do perfil de configuração de quiosque sejam baixados e instalados. Além disso, aguarde a aplicação das políticas.  
1. Depois que a OOBE terminar, você poderá instalar aplicativos adicionais da Microsoft Store ou por sideload. [Aplicativos necessários](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) para o grupo que o dispositivo pertence a instalar automaticamente.
1. Depois que a instalação terminar, reinicie o dispositivo.

Na próxima vez que você entrar no dispositivo usando uma conta que pertence ao tipo de **logon**do usuário, o aplicativo de quiosque deverá ser lançado automaticamente.

Se você não vir sua configuração de quiosque neste ponto, verifique [o status da atribuição.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

## Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando um pacote de provisionamento, siga estas etapas.

1. [Crie um arquivo XML que defina a configuração de quiosque.](#ppkioskconfig), incluindo um [layout de iniciar](#start-layout-for-hololens).
2. [Adicione o arquivo XML a um pacote de provisionamento.](#ppconfigadd)
3. [Aplique o pacote de provisionamento ao HoloLens.](#ppapply)

### <a id="ppkioskconfig"></a>Pacote de provisionamento, etapa 1 &ndash; Criar um arquivo XML de configuração de quiosque

Siga as instruções gerais para criar um arquivo XML de configuração de [quiosque](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)para área de trabalho do Windows, exceto pelo seguinte:

- Não inclua aplicativos Clássicos do Windows (Win32). O HoloLens não dá suporte a esses aplicativos.
- Use o [XML de layout da tela inicial](#start-layout-for-hololens) do espaço reservado para o HoloLens.
- Opcional: Adicionar acesso de convidado à configuração de quiosque

#### <a id="ppkioskguest"></a>Opcional: Adicionar acesso de convidado à configuração de quiosque

Na seção [ **Configs** do arquivo XML,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)você pode configurar um grupo especial chamado **Visitante** para permitir que os convidados usem o quiosque. Quando o quiosque está configurado **** para dar suporte ao grupo especial visitante, uma opção "**Convidado**" é adicionada à página de login. A **conta** de convidado não exige uma senha e todos os dados associados à conta são excluídos quando a conta é desassociada.

Para **habilitar a conta de** Convidado, adicione o seguinte trecho de código ao XML de configuração de quiosque:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Layout da tela inicial do espaço reservado para HoloLens

Se você usar um [pacote de provisionamento para](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) configurar um quiosque de vários aplicativos, o procedimento exigirá um layout de iniciar. A personalização do layout da iniciar não é suportada no Windows Holographic for Business. Portanto, você terá que usar um layout de início de espaço reservado.

> [!NOTE]  
> Como um quiosque de aplicativo único inicia o aplicativo de quiosque quando um usuário entra, ele não usa um menu Iniciar e não precisa ter um layout de iniciar.

> [!NOTE]  
> Se você usar [o MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque de vários aplicativos, opcionalmente poderá usar um layout da iniciar. Para obter mais informações, consulte o arquivo de layout de início de espaço reservado para [MDM (Intune e outros).](#start-layout-file-for-mdm-intune-and-others)

Para o layout da tela inicial, adicione a seguinte **seção StartLayout** ao arquivo XML de provisionamento de quiosque:

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Arquivo de layout da iniciar de espaço reservado para MDM (Intune e outros)

Salve o exemplo a seguir como um arquivo XML. Você pode usar esse arquivo ao configurar o quiosque de vários aplicativos no Microsoft Intune (ou em outro serviço MDM que fornece um perfil de quiosque).

> [!NOTE]
> Se você tiver que usar uma configuração personalizada e uma configuração XML completa para configurar um quiosque em seu serviço MDM, use as instruções de layout da tela inicial para um [pacote de provisionamento.](#start-layout-for-hololens)

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

### <a id="ppconfigadd"></a>Prov. package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package

1. Abra o [Designer de Configuração do Windows.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Selecione **Provisionamento Avançado,** insira um nome para seu projeto e selecione **Avançar.**
1. Selecione **Windows 10 Holographic**e, em seguida, **Next**.
1. Selecione **Concluir**. O espaço de trabalho para seu pacote é aberto.
1. Selecione **configurações de tempo de execução**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. No painel central, selecione **Procurar** para localizar e selecionar o arquivo XML de configuração de quiosque que você criou.

   ![Captura de tela do campo MultiAppAssignedAccessSettings no Designer de Configuração do Windows](./images/multiappassignedaccesssettings.png)

1. **Opcional**. (Se você quiser aplicar o pacote de provisionamento após a configuração inicial do dispositivo e houver um usuário administrador já disponível no dispositivo de quiosque, ignore esta etapa.) Selecione **Configurações de Tempo de Execução** &gt; **Usuários** &gt; **de**Contas e crie uma conta de usuário. Forneça um nome de usuário e senha e selecione **UserGroup**  >  **Administrators**.  
  
     Usando essa conta, você pode exibir o status e os logs de provisionamento.  
1. **Opcional**. (Se você já tiver uma conta de não administrador no dispositivo de quiosque, ignore esta etapa.) Selecione **configurações de Tempo de Execução** &gt; **Contas** &gt; **de Usuários**e crie uma conta de usuário local. Certifique-se de que o nome de usuário seja o mesmo da conta especificada no XML de configuração. Selecione **UserGroup**  >  **Standard Users**.
1. Selecione **Salvar**  >  **Arquivo.**
1. Selecione **Exportar**  >  **pacote de provisionamento**e, em seguida, selecione Administrador **de**IT  >  **do proprietário.** Isso define a precedência desse pacote de provisionamento como mais alta do que os pacotes de provisionamento que são aplicados a esse dispositivo de outras fontes.
1. Selecione **Avançar**.
1. Na página **de segurança do pacote de provisionamento,** selecione uma opção de segurança.
   > [!IMPORTANT]  
   > Se você selecionar **Habilitar assinatura de**pacote, também terá que selecionar um certificado válido a ser usado para assinar o pacote. Para fazer isso, selecione **Procurar** e selecione o certificado que você deseja usar para assinar o pacote.
   
   > [!CAUTION]  
   > Não selecione **Habilitar criptografia de pacote.** Em dispositivos HoloLens, essa configuração causa falha no provisionamento.
1. Selecione **Avançar**.
1. Especifique o local de saída para onde você deseja que o pacote de provisionamento vá quando ele for criado. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída. Se você quiser alterar o local de saída, selecione **Procurar**. Quando terminar, selecione **Next**.
1. Selecione **Build** para começar a criar o pacote. O pacote de provisionamento não leva muito tempo para compilar. A página de com build exibe as informações do projeto e a barra de progresso indica o status da com build.

### <a id="ppapply"></a>Pacote de provisionamento, etapa 3 &ndash; Aplicar o pacote de provisionamento ao HoloLens

O artigo "Configurar o HoloLens usando um pacote de provisionamento" fornece instruções detalhadas para aplicar o pacote de provisionamento nas seguintes circunstâncias:

- Inicialmente, você pode aplicar [um pacote de provisionamento ao HoloLens durante a instalação.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Você também pode [aplicar um pacote de provisionamento ao HoloLens após a instalação.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## Usar o Windows Device Portal para configurar um quiosque de aplicativo único

Para configurar o modo de quiosque usando o Windows Device Portal, siga estas etapas.

1. [Configurar o dispositivo HoloLens para usar o Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). O Device Portal é um servidor Web no HoloLens ao qual você pode se conectar usando um navegador da Web em seu computador.

    > [!CAUTION]
    > Ao configurar o HoloLens para usar o Device Portal, você precisa habilitar o Modo de Desenvolvedor no dispositivo. O Modo de Desenvolvedor em um dispositivo que tenha o Windows Holographic for Business permite que você carregue aplicativos de side load. No entanto, essa configuração cria um risco de que um usuário possa instalar aplicativos que não foram certificados pela Microsoft Store. Os administradores podem bloquear a capacidade de habilitar o Modo de Desenvolvedor usando a configuração **ApplicationManagement/AllowDeveloper Unlock** no [CSP da Política.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Saiba mais sobre o Modo de desenvolvedor.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Em um computador, conecte-se ao HoloLens usando [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Siga um destes procedimentos:
   - Se você estiver se conectando ao Windows Device Portal pela primeira vez, [crie um nome de usuário e senha](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Insira o nome de usuário e a senha que você definiu anteriormente.

    > [!TIP]
    > Se você vir um erro de certificado no navegador, siga [estas etapas para solução de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. No Windows Device Portal, selecione **Modo de Quiosque.**

1. Selecione **Habilitar Modo de Quiosque**, selecione um aplicativo para executar quando o dispositivo for iniciado e, em seguida, **selecione Salvar**.

    ![Modo de quiosque](images/kiosk.png)
1. Reinicie o HoloLens. Se você ainda tiver sua página do **** Device Portal aberta, poderá selecionar Reiniciar na parte superior da página.

> [!NOTE]
> O Modo de Quiosque pode ser definido por meio da API REST do Device Portal fazendo um POST para /api/holographic/kioskmode/settings com um parâmetro de cadeia de caracteres de consulta obrigatório ("kioskModeEnabled" com um valor "true" ou "false") e um parâmetro opcional ("startupApp" com um valor de um nome de pacote). Tenha em mente que o Device Portal destina-se apenas a desenvolvedores e não deve ser habilitado em dispositivos que não sejam desenvolvedores. A API REST está sujeita a alterações em atualizações/versões futuras.

## Mais informações

### Veja como configurar um quiosque usando um pacote de provisionamento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### Acesso Global Atribuído – Modo de Quiosque
- Gerenciamento de identidade reduzido para Quiosque, habilitando o novo método kiosk que aplica o modo de quiosque no nível do sistema.

Esse novo recurso permite que um administrador de IT configure um dispositivo do HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todos que entrarem no dispositivo. Consulte a [documentação do quiosque](hololens-global-assigned-access-kiosk.md) de acesso atribuído global do HoloLens para obter mais detalhes sobre esse novo recurso.

### Início automático de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada na abertura automática de aplicativos, aumentando ainda mais as seleções de interface do usuário e aplicativo escolhidas para experiências do modo quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e apenas 1 aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração de Acesso Atribuído. 

O aplicativo é automaticamente lançado quando o usuário se insiciona. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### Alterações no comportamento do modo de quiosque para o tratamento de falhas
- Modo de Quiosque mais seguro eliminando os aplicativos disponíveis em falhas no modo de quiosque. 

Anteriormente, ao encontrar falhas na aplicação do modo de quiosque, o HoloLens usava para exibir todos os aplicativos no menu Iniciar. Agora, no Windows Holographic versão 20H2 no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, como abaixo: 

![Imagem da aparência do modo de quiosque agora quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### Cache da associação do Grupo do Azure AD para Quiosque offline
- Habilitar os Quiosques Offline a serem usados com grupos do Azure AD por até 60 dias.

Essa política controla por quantos dias o cache de associação de grupo do Azure AD tem permissão para ser usado para configurações de Acesso Atribuído destinados a grupos do Azure AD para o usuário associado. Depois que esse valor de política for definido para um valor maior do que 0, o cache será usado caso contrário, não.  

Nome: AADGroupMembershipCacheValidityInDays Valor do URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 dias  
Máx . 60 dias 

Etapas para usar essa política corretamente: 
1. Crie um perfil de configuração de dispositivo para quiosque voltado para grupos do Azure AD e atribua-o a dispositivos do HoloLens. 
1. Crie uma configuração de dispositivo baseada em OMA URI personalizada que define esse valor de política para o número desejado de dias (> 0) e o atribui aos dispositivos do HoloLens. 
    1. O valor do URI deve ser inserido na caixa de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre mín/ máximo permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário 1 do Azure AD entre quando a Internet estiver disponível, quando o usuário entrar e a associação ao grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário 1 do Azure AD pode deixar o HoloLens offline e usá-lo no modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD N. O ponto chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que ele é membro do grupo do Azure AD para o qual a configuração de Quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para um usuário do Azure AD, o comportamento de falha será mencionado em ambientes "desconectados". 


## Exemplos de código de quiosque XML para HoloLens

### Modo de quiosque de vários aplicativos voltado para um grupo do Azure AD. 
Esse quiosque implanta um Quiosque que, para os usuários no grupo do Azure AD, eles terão um Quiosque habilitado que inclui os três aplicativos: Configurações, Assistência Remota e Hub de Feedback. Para modificar esse exemplo a ser usado imediatamente, altere o GUID realçado abaixo para corresponder a um grupo do Azure AD por conta própria. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### Modo de quiosque de vários aplicativos voltado para a conta do Azure AD.
Esse quiosque implanta um Quiosque para um único usuário, ele terá um Quiosque habilitado que inclui os três aplicativos: Configurações, Assistência Remota e Hub de Feedback. Para modificar esse exemplo a ser usado imediatamente, altere a conta realçada abaixo para corresponder a uma conta do Azure AD por conta própria. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

