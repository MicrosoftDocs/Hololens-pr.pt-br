---
title: Configurar o HoloLens como um quiosque
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308155"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurar o HoloLens como um quiosque

Você pode configurar um dispositivo HoloLens para funcionar como um dispositivo de finalidade fixa, também chamado de *quiosque*, configurando o dispositivo para ser executado no modo de quiosque. O modo de quiosque limita os aplicativos (ou usuários) que estão disponíveis no dispositivo. O modo de quiosque é um recurso conveniente que você pode usar para dedicar um dispositivo de HoloLens para aplicativos de negócios ou para usar o dispositivo HoloLens em uma demonstração de aplicativo.

Este artigo fornece informações sobre aspectos de configuração de quiosque que são específicos para dispositivos HoloLens. Para obter informações gerais sobre os diferentes tipos de quiosques baseados no Windows e como configurá-los, consulte [Configurar quiosques e digital Signs on Windows Desktop Editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> O modo de quiosque determina quais aplicativos estão disponíveis quando um usuário entra no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Ele não interrompe um aplicativo "permitido" de abrir outro aplicativo que não é permitido. Para impedir que aplicativos ou processos sejam abertos, use o [CSP do Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas.
>
> Saiba mais sobre os serviços da Microsoft para fornecer aos usuários um nível avançado de segurança que o HoloLens 2 usa, leia mais sobre [separação de estado e isolamento-defender proteções](security-state-separation-isolation.md#defender-protections). Ou saiba como [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em dispositivos de HoloLens 2 com Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Você pode usar o modo de quiosque em uma configuração de aplicativo único ou de vários aplicativos e pode usar um dos três processos para configurar e implantar a configuração do quiosque.

> [!IMPORTANT]  
> Excluir a configuração de vários aplicativos remove os perfis de bloqueio de usuário que o recurso de acesso atribuído criou. No entanto, ele não reverte todas as alterações de política. Para reverter essas políticas, você precisa redefinir o dispositivo para as configurações de fábrica.

## <a name="plan-the-kiosk-deployment"></a>Planejar a implantação do quiosque

Ao planejar seu quiosque, você precisará ser capaz de responder às perguntas a seguir. Aqui estão algumas decisões a considerar ao ler esta página e algumas considerações para essas perguntas.
1. **Quem usará o quiosque e o [tipo de conta que eles usarão (s)](hololens-identity.md) ?** Essa é uma decisão que você provavelmente já fez e não deve ser ajustada para fins de seu quiosque, mas afetará como o quiosque é atribuído posteriormente.
1. **Você precisa ter diferentes quiosques por usuário/grupo ou um quiosque não habilitado para alguns?** Nesse caso, você desejará criar seu quiosque via XML. 
1. **Quantos aplicativos estarão em seu quiosque?** Se você tiver mais de um aplicativo, precisará de um quiosque com vários aplicativos. 
1. **Quais aplicativos estarão em seu quiosque?** Use nossa lista de AUMIDs abaixo para adicionar qualquer aplicativo In-Box além de seu próprio.
1. **Como você planeja implantar seu quiosque?** Se você estiver registrando o dispositivo no MDM, sugerimos usar o MDM para implantar o quiosque. Se você não estiver usando o MDM, a implantação com o pacote de provisionamento estará disponível.  

### <a name="kiosk-mode-requirements"></a>Requisitos do modo de quiosque

Você pode configurar qualquer dispositivo do HoloLens 2 para usar o modo de quiosque.

> [!IMPORTANT]
> O modo de quiosque só estará disponível se o dispositivo tiver o Windows Holographic for Business. Todos os dispositivos de HoloLens 2 são fornecidos com o Windows Holographic for Business e não há outras edições. Cada dispositivo de HoloLens 2 é capaz de executar o modo de quiosque pronto.
>
> Os dispositivos HoloLens (1º gen) precisam ser atualizados em termos de Build do sistema operacional e edição do sistema operacional. Aqui estão mais informações sobre como atualizar um HoloLens (1º gen) para o [Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Para atualizar um dispositivo HoloLens (1º gen) para usar o modo de quiosque, você deve primeiro certificar-se de que o dispositivo executa o Windows 10, versão 1803 ou uma versão posterior. Se você tiver usado a ferramenta de recuperação de dispositivo do Windows para recuperar seu dispositivo HoloLens (1º gen) para sua compilação padrão ou se tiver instalado as atualizações mais recentes, o dispositivo estará pronto para ser configurado.

> [!IMPORTANT]  
> Para ajudar a proteger os dispositivos executados no modo de quiosque, considere adicionar políticas de gerenciamento de dispositivos que desativem recursos como conectividade USB. Além disso, verifique as configurações de anel de atualização para garantir que as atualizações automáticas não ocorram durante o horário comercial.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Decidir entre um quiosque de aplicativo único ou um quiosque de vários aplicativos

Um quiosque de aplicativo único inicia o aplicativo especificado quando o usuário faz logon no dispositivo. O menu iniciar é desabilitado, assim como o Cortana. Um dispositivo HoloLens 2 não responde ao gesto de [Iniciar](hololens2-basic-usage.md#start-gesture) . Um dispositivo HoloLens (1º gen) não responde ao gesto de [cair](hololens1-basic-usage.md) . Como apenas um aplicativo pode ser executado, o usuário não pode fazer outros aplicativos.

Um quiosque de vários aplicativos exibe o menu iniciar quando o usuário entra no dispositivo. A configuração do quiosque determina quais aplicativos estão disponíveis no menu iniciar. Você pode usar um quiosque de vários aplicativos para fornecer uma experiência fácil de entender aos usuários, apresentando a eles apenas as coisas que eles precisam usar e removendo as coisas que eles não precisam usar.

A tabela a seguir lista os recursos de recurso nos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu de ações rápidas |Câmera e vídeo |Miracast |Cortana |Comandos internos de voz |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Quiosque de aplicativo único |Desabilitado |Desabilitado   |Desabilitado |Desabilitado   |Desabilitado |Habilitado<sup>1</sup> |
|Quiosques de vários aplicativos |Habilitada |Habilitado<sup>2</sup> |Disponível<sup>2</sup> |Disponível<sup>2</sup> |Disponível<sup>2, 3</sup>  |Habilitado<sup>1</sup> |

> <sup>1</sup> os comandos de voz relacionados aos recursos desabilitados não funcionam.  
> <sup>2</sup> para obter mais informações sobre como configurar esses recursos, consulte [selecionar aplicativos de quiosque](#plan-kiosk-apps).  
> <sup>3</sup> mesmo se a Cortana estiver desabilitada, os comandos internos de voz serão habilitados.

A tabela a seguir lista os recursos de suporte do usuário dos diferentes modos de quiosque.

| &nbsp; |Tipos de usuário com suporte | Entrada automática | Vários níveis de acesso |
| --- | --- | --- | --- |
|Quiosque de aplicativo único |MSA (conta de serviço gerenciado) no Azure Active Directory (Azure AD) ou na conta local |Sim |Não |
|Quiosques de vários aplicativos |Conta do AD do Azure |Não |Sim |

Para obter exemplos de como usar esses recursos, consulte a tabela a seguir.

|Use um quiosque de aplicativo único para: |Use um quiosque de vários aplicativos para: |
| --- | --- |
|Um dispositivo que executa apenas um guia do Dynamics 365 para novos funcionários. |Um dispositivo que executa guias e assistência remota para uma variedade de funcionários. |
|Um dispositivo que executa apenas um aplicativo personalizado. |Um dispositivo que funciona como um quiosque para a maioria dos usuários (executando apenas um aplicativo personalizado), mas funciona como um dispositivo padrão para um grupo específico de usuários. |

### <a name="plan-kiosk-apps"></a>Planejar aplicativos de quiosque

Para obter informações gerais sobre como escolher aplicativos de quiosque, consulte [diretrizes para escolher um aplicativo para acesso atribuído (modo de quiosque)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Se você usar o portal de dispositivo do Windows para configurar um quiosque de aplicativo único, selecione o aplicativo durante o processo de instalação.  

Se você usar um sistema de MDM (gerenciamento de dispositivo móvel) ou um pacote de provisionamento para configurar o modo de quiosque, use o [provedor de serviços de configuração do AssignedAccess (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) para especificar aplicativos. O CSP usa [AUMIDs (IDs de modelo de usuário do aplicativo)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar aplicativos. A tabela a seguir lista os AUMIDs de alguns aplicativos na caixa que você pode usar em um quiosque de vários aplicativos.

> [!IMPORTANT]
> O modo de quiosque determina quais aplicativos estão disponíveis quando um usuário entra no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Ele não interrompe um aplicativo "permitido" de abrir outro aplicativo que não é permitido. Como não restringimos esse comportamento, os aplicativos ainda podem ser iniciados a partir do Edge, do explorador de arquivos e dos aplicativos Microsoft Store. Se houver aplicativos específicos que você não deseja que sejam iniciados em um quiosque, use o [CSP do Windows Defender Application Control (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas. 
> 
> Além disso, a página inicial da realidade misturada não pode ser definida como um aplicativo de quiosque.

<a id="aumids"></a>

|Nome do Aplicativo |AUMID |
| --- | --- |
|Visualizador 3D |Microsoft. Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendário |Microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! Microsoft. windowslive. Calendar |
|Câmera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Aplicativo Microsoft. 549981C3F5F10 \_ 8wekyb3d8bbwe \! |
|Seletor de dispositivo no HoloLens (1ª gen) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Seletor de dispositivo no HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. guias \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Hub de comentários &nbsp; |Aplicativo Microsoft. WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Explorador de Arquivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Email |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. windowslive. mail |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|Filmes e TV |Microsoft. ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |aplicativo Microsoft. microsoftskydrive \_ 8wekyb3d8bbwe \! |
|Fotos |Aplicativo Microsoft. Windows. photos \_ 8wekyb3d8bbwe \! |
|Configurações |\_Aplicativo HolographicSystemSettings cw5n1h2txyewy \! |
|Dicas |Microsoft. HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> para habilitar a captura de foto ou de vídeo, você precisa habilitar o aplicativo de câmera como um aplicativo de quiosque.  
> <sup>2</sup> quando você habilitar o aplicativo de câmera, esteja ciente das seguintes condições:
> - O menu ações rápidas inclui os botões de foto e vídeo.  
> - Você também deve habilitar um aplicativo (como fotos, email ou OneDrive) que pode interagir com ou recuperar imagens.  
>  
> <sup>3</sup> mesmo se você não habilitar a Cortana como um aplicativo de quiosque, os comandos de voz internos serão habilitados. No entanto, os comandos relacionados a recursos desabilitados não têm nenhum efeito.  
> <sup>4</sup> você não pode habilitar o Miracast diretamente. Para habilitar o Miracast como um aplicativo de quiosque, habilite o aplicativo de câmera e o aplicativo de seletor de dispositivo.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planejar perfis de quiosque para usuários ou grupos

Ao criar o arquivo XML ou usar a interface do usuário do Intune para configurar um quiosque, você precisará considerar quem será o usuário do quiosque. Uma configuração de quiosque pode ser limitada a uma conta individual ou a grupos do Azure AD. 

Normalmente, os quiosques são habilitados para um usuário ou grupo de usuários. No entanto, se você planeja escrever seu próprio quiosque XML, talvez queira considerar o acesso atribuído global, no qual o quiosque é aplicado no nível do dispositivo, independentemente da identidade. Se isso lhe agradar, [Leia mais sobre os quiosques de acesso atribuídos globalmente.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Se você estiver criando um arquivo XML:
-   Você cria vários perfis de quiosque e atribui cada um a diferentes usuários/grupos. Como um quiosque para seu grupo do Azure AD que tem muitos aplicativos e um visitante que tem um quiosque de vários aplicativos com um aplicativo singular.
-   Sua configuração de quiosque será chamada de **ID de perfil** e terá um GUID.
-   Você atribuirá esse perfil na seção Configurações especificando o tipo de usuário e usando o mesmo GUID para a ID de **DefaultProfile**.
- Um arquivo XML pode ser criado, mas ainda aplicado a um dispositivo via MDM, criando um perfil de configuração de dispositivo OMA URI personalizado e aplicando-o ao grupo de dispositivos do HoloLens usando o valor do URI:./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Se você estiver criando um quiosque no Intune.
-   Cada dispositivo pode receber apenas um único perfil de quiosque, caso contrário, ele criará um conflito e não receberá nenhuma configuração de quiosque. 
    -   Outros tipos de perfis e políticas, como restrições de dispositivo que não estão relacionadas ao perfil de configuração do quiosque, não entram em conflito com o perfil de configuração do quiosque.
-   O quiosque será habilitado para todos os usuários que fazem parte do tipo de logon do usuário, isso será definido com um usuário ou grupo do Azure AD. 
-   Depois que a configuração do quiosque for definida e o **tipo de logon do usuário** (usuários que podem fazer logon no quiosque) e os aplicativos forem selecionados, a configuração do dispositivo ainda deverá ser atribuída a um grupo. Os grupos atribuídos determinam quais dispositivos recebem a configuração do dispositivo de quiosque, no entanto, não interage com se o quiosque estiver habilitado ou não. 
    - Para obter uma discussão completa sobre os efeitos da atribuição de perfis de configuração no Intune, consulte [atribuir perfis de usuário e de dispositivo no Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Selecionar um método de implantação

Você pode selecionar um dos seguintes métodos para implantar configurações de quiosque:

- [Microsoft Intune ou outro serviço de MDM (gerenciamento de dispositivo móvel)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Portal de Dispositivos do Windows](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Como esse método requer que o modo de desenvolvedor esteja habilitado no dispositivo, recomendamos que você o use somente para demonstrações.

A tabela a seguir lista os recursos e os benefícios de cada um dos métodos de implantação.

| &nbsp; |Implantar usando o portal de dispositivos do Windows |Implantar usando um pacote de provisionamento |Implantar usando o MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Implantar quiosques de aplicativo único   | Sim           | Sim                  | Yes  |
|Implantar quiosques de vários aplicativos    | Não            | Sim                  | Yes  |
|Implantar somente em dispositivos locais | Sim           | Sim                  | Não   |
|Implantar usando o modo de desenvolvedor |Obrigatório       | Não é necessária            | Não é necessária   |
|Implantar usando o Azure Active Directory (Azure AD)  | Não é necessária            | Não é necessária                   | Obrigatório  |
|Implantar automaticamente      | Não            | Não                   | Sim  |
|Velocidade de implantação            | Rápido       | Rápido                 | Lento |
|Implantar em escala | Não recomendado    | Recomendadas        | Recomendadas |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usar Microsoft Intune ou outro MDM para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando Microsoft Intune ou outro sistema MDM, siga estas etapas.

1. [Prepare-se para registrar os dispositivos](#mdmenroll).
1. [Crie um perfil de configuração de quiosque](#mdmprofile).
1. Configure o quiosque.
   - [Defina as configurações para um quiosque de aplicativo único](#mdmconfigsingle).
   - [Defina as configurações para um quiosque de vários aplicativos](#mdmconfigmulti).
1. [Atribua o perfil de configuração do quiosque a um grupo](#mdmassign).
1. Implante os dispositivos.
   - [Implante um quiosque de aplicativo único](#mdmsingledeploy).
   - [Implantar um quiosque de vários aplicativos](#mdmmultideploy).

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, etapa 1 &ndash; preparar para registrar os dispositivos

Você pode configurar seu sistema MDM para registrar dispositivos HoloLens automaticamente quando o usuário entrar pela primeira vez ou fazer com que os usuários registrem dispositivos manualmente. Os dispositivos também precisam ser ingressados no domínio do Azure AD e atribuídos aos grupos apropriados.

Para obter mais informações sobre como registrar os dispositivos, consulte [registrar o HoloLens nos](hololens-enroll-mdm.md) [métodos de registro do MDM e do Intune para dispositivos Windows](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, etapa 2 &ndash; criar um perfil de configuração de quiosque

1. Abra o portal [do Azure](https://portal.azure.com/) e entre em sua conta de administrador do Intune.
1. Selecione **Microsoft Intune**  >  **configuração do dispositivo perfis**  >  **Criar perfil**.
1. Insira um nome de perfil.
1. Selecione **plataforma**  >  **Windows 10 e posterior** e, em seguida, selecione **tipo de perfil**  > **restrições de dispositivo**.
1. Selecione **Configurar**  >  **quiosque** e, em seguida, selecione uma das seguintes opções:
   - Para criar um quiosque de aplicativo único, selecione **modo**  >  **de quiosque quiosque de aplicativo único**.
   - Para criar um quiosque de vários aplicativos, selecione **modo**  >  **de quiosque quiosque de vários aplicativos**.
1. Para iniciar a configuração do quiosque, selecione **Adicionar**.

As próximas etapas diferem dependendo do tipo de quiosque que você deseja. Para obter mais informações, selecione uma das seguintes opções:  

- [Quiosque de aplicativo único](#mdmconfigsingle)
- [Quiosques de vários aplicativos](#mdmconfigmulti)

Para obter mais informações sobre como criar um perfil de configuração de quiosque, consulte [configurações de dispositivo Windows 10 e Windows Holographic for Business para executar como um quiosque dedicado usando o Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, etapa 3 (aplicativo único) &ndash;  definir as configurações para um quiosque de aplicativo único

Esta seção resume as configurações exigidas por um quiosque de aplicativo único. Para obter mais detalhes, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte [como configurar o modo de quiosque usando Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as configurações disponíveis para quiosques de um único aplicativo no Intune, consulte [quiosques de aplicativo de tela inteira única](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Para outros serviços de MDM, consulte a documentação do provedor para obter instruções. Se você precisar usar uma configuração XML personalizada para configurar um quiosque em seu serviço MDM, [crie um arquivo XML que define a configuração do quiosque](#ppkioskconfig).

1. Selecione **tipo de logon de usuário**  >  **conta de usuário local** e, em seguida, insira o nome de usuário da conta local (dispositivo) ou da MSA (conta da Microsoft) que pode entrar no quiosque.
   > [!NOTE]  
   > Não há suporte para tipos de conta de usuário de **logon automático** no Windows Holographic for Business.
1. Selecione aplicativo  >  da **loja** de tipos de aplicativos e, em seguida, selecione um aplicativo na lista.

A próxima etapa é [atribuir](#mdmassign) o perfil a um grupo.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, etapa 3 (vários aplicativos) &ndash; definir as configurações para um quiosque de vários aplicativos

Esta seção resume as configurações que um quiosque de vários aplicativos requer. Para informações mais detalhadas, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte [como configurar o modo de quiosque usando Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as configurações disponíveis para quiosques de vários aplicativos no Intune, consulte [quiosques de vários aplicativos](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para outros serviços de MDM, consulte a documentação do provedor para obter instruções. Se você precisar usar uma configuração XML personalizada para configurar um quiosque em seu serviço MDM, [crie um arquivo XML que define a configuração do quiosque](#ppkioskconfig). Se você usar um arquivo XML, certifique-se de incluir o [layout de início](#start-layout-for-hololens).  
- Opcionalmente, você pode usar um layout de início personalizado com o Intune ou outros serviços de MDM. Para obter mais informações, consulte [iniciar o arquivo de layout para MDM (Intune e outros)](#start-layout-file-for-mdm-intune-and-others).

1. Selecione **destino Windows 10 no modo S**  >  **n º** de dispositivos.  
   >[!NOTE]  
   > Não há suporte para o modo S no Windows Holographic for Business.
1. Selecione **tipo de logon**  >  **do usuário Azure ad usuário ou grupo** ou **tipo de logon de usuário**  >  **visitante do HoloLens** e, em seguida, adicione uma ou mais contas ou grupos de usuários.  

   Somente os usuários que pertencem aos grupos ou contas que você especificar no **tipo de logon do usuário** podem usar a experiência de quiosque.

1. Selecione um ou mais aplicativos usando as seguintes opções:
   - Para adicionar um aplicativo de linha de negócios carregado, selecione **Adicionar aplicativo da loja** e, em seguida, selecione o aplicativo desejado.
   - Para adicionar um aplicativo especificando seu AUMID, selecione **Adicionar por AUMID** e, em seguida, insira o AUMID do aplicativo. [Consulte a lista de AUMIDs disponíveis](#aumids)

A próxima etapa é [atribuir](#mdmassign) o perfil a um grupo.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, etapa 4 &ndash; atribuir o perfil de configuração de quiosque a um grupo

Use a página **atribuições** do perfil de configuração do quiosque para definir onde você deseja que a configuração do quiosque seja implantada. No caso mais simples, você atribui o perfil de configuração de quiosque a um grupo que conterá o dispositivo HoloLens quando o dispositivo for registrado no MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, etapa 5 (aplicativo único) &ndash; implantar um quiosque de aplicativo único

Ao usar um sistema MDM, você pode registrar o dispositivo no MDM durante o OOBE. Após a conclusão do OOBE, é fácil entrar no dispositivo.

Durante o OOBE, siga estas etapas:

1. Entre usando a conta que você especificou no perfil de configuração do quiosque.
1. Registre o dispositivo. Verifique se o dispositivo foi adicionado ao grupo ao qual o perfil de configuração do quiosque está atribuído.
1. Aguarde até que o OOBE seja concluído, para o aplicativo da loja baixar e instalar e para as políticas a serem aplicadas. Em seguida, reinicie o dispositivo.

Na próxima vez que você entrar no dispositivo, o aplicativo de quiosque deverá ser iniciado automaticamente.

Se você não vir sua configuração de quiosque neste momento, [Verifique o status da atribuição](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, etapa 5 (vários aplicativos) &ndash; implantar um quiosque de vários aplicativos

Ao usar um sistema MDM, você pode ingressar o dispositivo em seu locatário do Azure AD e registrar o dispositivo no MDM durante o OOBE. Se apropriado, forneça as informações de registro aos usuários para que eles o disponibilizem durante o processo OOBE.

> [!NOTE]  
> Se você tiver atribuído o perfil de configuração de quiosque a um grupo que contém usuários, verifique se uma dessas contas de usuário é a primeira conta para entrar no dispositivo.

Durante o OOBE, siga estas etapas:

1. Entre usando a conta que pertence ao grupo de **tipos de logon do usuário** .
1. Registre o dispositivo.
1. Aguarde todos os aplicativos que fazem parte do perfil de configuração do quiosque para baixar e instalar. Além disso, aguarde até que as políticas sejam aplicadas.  
1. Após a conclusão do OOBE, você pode instalar aplicativos adicionais da Microsoft Store ou do Sideload. [Aplicativos necessários](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) para o grupo que o dispositivo pertence a instalar automaticamente.
1. Após a conclusão da instalação, reinicie o dispositivo.

Na próxima vez que você entrar no dispositivo usando uma conta que pertence ao **tipo de logon do usuário**, o aplicativo de quiosque deverá ser iniciado automaticamente.

Se você não vir sua configuração de quiosque neste momento, [Verifique o status da atribuição](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando um pacote de provisionamento, siga estas etapas.

1. [Crie um arquivo XML que define a configuração do quiosque.](#ppkioskconfig), incluindo um [layout de início](#start-layout-for-hololens).
2. [Adicione o arquivo XML a um pacote de provisionamento.](#ppconfigadd)
3. [Aplique o pacote de provisionamento ao HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Pacote de provisionamento, etapa 1 &ndash; criar um arquivo XML de configuração de quiosque

Siga [as instruções gerais para criar um arquivo XML de configuração de quiosque para a área de trabalho do Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), exceto para o seguinte:

- Não inclua aplicativos clássicos do Windows (Win32). O HoloLens não oferece suporte a esses aplicativos.
- Use o [XML de layout inicial do espaço reservado](#start-layout-for-hololens) para o HoloLens.
- Opcional: adicionar acesso de convidado à configuração de quiosque

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Opcional: adicionar acesso de convidado à configuração de quiosque

Na seção [ **configurações** do arquivo XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), você pode configurar um grupo especial chamado **visitante** para permitir que os convidados usem o quiosque. Quando o quiosque é configurado para dar suporte ao grupo especial do **visitante** , uma opção "**convidado**" é adicionada à página de entrada. A conta de **convidado** não requer uma senha e todos os dados associados à conta são excluídos quando a conta se desconecta.

Para habilitar a conta de **convidado** , adicione o seguinte trecho ao seu XML de configuração de quiosque:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Layout inicial do espaço reservado para o HoloLens

Se você usar um [pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque de vários aplicativos, o procedimento exigirá um layout de início. A personalização do layout inicial não tem suporte no Windows Holographic for Business. Portanto, você precisará usar um layout de início de espaço reservado.

> [!NOTE]  
> Como um quiosque de aplicativo único inicia o aplicativo de quiosque quando um usuário faz logon, ele não usa um menu iniciar e não precisa ter um layout de início.

> [!NOTE]  
> Se você usar o [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque de vários aplicativos, você pode opcionalmente usar um layout de início. Para obter mais informações, consulte [espaço reservado para o arquivo de layout do MDM (Intune e outros)](#start-layout-file-for-mdm-intune-and-others).

Para o layout de início, adicione a seguinte seção **StartLayout** ao arquivo XML de provisionamento de quiosque:

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Arquivo de layout de início do espaço reservado para MDM (Intune e outros)

Salve o exemplo a seguir como um arquivo XML. Você pode usar esse arquivo ao configurar o quiosque de vários aplicativos no Microsoft Intune (ou em outro serviço MDM que forneça um perfil de quiosque).

> [!NOTE]
> Se você precisar usar uma configuração personalizada e uma configuração XML completa para configurar um quiosque em seu serviço MDM, use as [instruções de layout de início para um pacote de provisionamento](#start-layout-for-hololens).

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. pacote, etapa 2 &ndash; Adicionar o arquivo XML de configuração do quiosque a um pacote de provisionamento

1. Abra o [Designer de configuração do Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Selecione **provisionamento avançado**, insira um nome para o seu projeto e, em seguida, selecione **Avançar**.
1. Selecione **Windows 10 Holographic** e, em seguida, selecione **Avançar**.
1. Selecione **Concluir**. O espaço de trabalho para seu pacote é aberto.
1. Selecione **configurações de tempo de execução**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. No painel central, selecione **procurar** para localizar e selecionar o arquivo XML de configuração de quiosque que você criou.

   ![Captura de tela do campo MultiAppAssignedAccessSettings no Designer de Configuração do Windows](./images/multiappassignedaccesssettings.png)

1. **Opcional**. (Se você quiser aplicar o pacote de provisionamento após a configuração inicial do dispositivo e houver um usuário administrador já disponível no dispositivo de quiosque, ignore esta etapa.) Selecione **configurações de tempo de execução** &gt; **contas** &gt; **usuários** e, em seguida, crie uma conta de usuário. Forneça um nome de usuário e uma senha e, em seguida, selecione administradores do **UserGroup**  >  .  
  
     Usando essa conta, você pode exibir o status de provisionamento e os logs.  
1. **Opcional**. (Se você já tiver uma conta que não seja de administrador no dispositivo de quiosque, ignore esta etapa.) Selecione **configurações de tempo de execução** &gt; **contas** &gt; **usuários** e, em seguida, crie uma conta de usuário local. Verifique se o nome de usuário é o mesmo para a conta que você especificar no XML de configuração. Selecione   >  **usuários padrão** do UserGroup.
1. Selecione **arquivo**  >  **salvar**.
1. Selecione **Exportar**  >  **pacote de provisionamento** e selecione **proprietário**  >  **administrador de ti**. Isso define a precedência desse pacote de provisionamento maior do que o provisionamento de pacotes que são aplicados a esse dispositivo de outras fontes.
1. Selecione **Avançar**.
1. Na página **segurança do pacote de provisionamento** , selecione uma opção de segurança.
   > [!IMPORTANT]  
   > Se você selecionar **Habilitar assinatura de pacote**, também precisará selecionar um certificado válido a ser usado para assinar o pacote. Para fazer isso, selecione **procurar** e selecione o certificado que você deseja usar para assinar o pacote.
   
   > [!CAUTION]  
   > Não selecione **habilitar criptografia de pacote**. Em dispositivos HoloLens, essa configuração faz com que o provisionamento falhe.
1. Selecione **Avançar**.
1. Especifique o local de saída onde você deseja que o pacote de provisionamento seja usado quando ele for compilado. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída. Se você quiser alterar o local de saída, selecione **procurar**. Quando tiver terminado, selecione **Avançar**.
1. Selecione **Compilar** para começar a criar o pacote. O pacote de provisionamento não leva muito tempo para compilar. A página de compilação exibe as informações do projeto e a barra de progresso indica o status da compilação.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Pacote de provisionamento, etapa 3 &ndash; aplicar o pacote de provisionamento ao HoloLens

O artigo "configurar o HoloLens usando um pacote de provisionamento" fornece instruções detalhadas para aplicar o pacote de provisionamento nas seguintes circunstâncias:

- Inicialmente, você pode [aplicar um pacote de provisionamento ao HoloLens durante a instalação](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Você também pode [aplicar um pacote de provisionamento ao HoloLens após a instalação](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Usar o portal de dispositivo do Windows para configurar um quiosque de aplicativo único

Para configurar o modo de quiosque usando o portal de dispositivo do Windows, siga estas etapas.

1. [Configure o dispositivo HoloLens para usar o portal do dispositivo Windows](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). O Device Portal é um servidor Web no HoloLens ao qual você pode se conectar usando um navegador da Web em seu computador.

    > [!CAUTION]
    > Ao configurar o HoloLens para usar o portal do dispositivo, você precisa habilitar o modo de desenvolvedor no dispositivo. O modo de desenvolvedor em um dispositivo que tem o Windows Holographic for Business permite que você carregue aplicativos. No entanto, essa configuração cria um risco de que um usuário possa instalar aplicativos que não foram certificados pelo Microsoft Store. Os administradores podem bloquear a capacidade de habilitar o modo de desenvolvedor usando a configuração de **desbloqueio ApplicationManagement/AllowDeveloper** no [CSP de política](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider). [Saiba mais sobre o modo de desenvolvedor.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Em um computador, conecte-se ao HoloLens usando [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Realize um dos seguintes procedimentos:
   - Se você estiver se conectando ao portal de dispositivos do Windows pela primeira vez, [crie um nome de usuário e uma senha](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Insira o nome de usuário e a senha que você configurou anteriormente.

    > [!TIP]
    > Se você vir um erro de certificado no navegador, siga [estas etapas para solução de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. No portal do dispositivo Windows, selecione **modo de quiosque**.

1. Selecione **habilitar modo de quiosque**, selecione um aplicativo para ser executado quando o dispositivo for iniciado e, em seguida, selecione **salvar**.

    ![Modo de quiosque](images/kiosk.png)
1. Reinicie o HoloLens. Se você ainda tiver a página do portal do dispositivo aberta, poderá selecionar **reiniciar** na parte superior da página.

> [!NOTE]
> O modo de quiosque pode ser definido por meio da API REST do portal do dispositivo fazendo um POST para/API/Holographic/KioskMode/Settings com um parâmetro de cadeia de caracteres de consulta necessário ("kioskModeEnabled&quot; com um valor de &quot;true&quot; ou &quot;false") e um parâmetro opcional ("startupApp" com um valor de um nome de pacote). Tenha em mente que o portal do dispositivo destina-se apenas a desenvolvedores e não deve ser habilitado em dispositivos sem desenvolvedores. A API REST está sujeita a alterações em atualizações/versões futuras.

## <a name="more-information"></a>Mais informações

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Assista a como configurar um quiosque usando um pacote de provisionamento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Acesso atribuído global – modo de quiosque
- Gerenciamento de identidades reduzido para quiosque, habilitando o novo método de quiosque que aplica o modo de quiosque no nível do sistema.

Esse novo recurso permite que um administrador de ti configure um dispositivo do HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem nenhuma afinidade com nenhuma identidade no sistema e se aplica a todos que se conectam ao dispositivo. Consulte a documentação do [quiosque de acesso atribuído global do HoloLens](hololens-global-assigned-access-kiosk.md) para obter mais detalhes sobre esse novo recurso.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicialização automática de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada com a inicialização automática do aplicativo, aumentando ainda mais a interface do usuário e as seleções de aplicativo escolhidas para experiências de modo de quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e somente um aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração de acesso atribuída. 

O aplicativo é iniciado automaticamente quando o usuário entra. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações de comportamento do modo de quiosque para tratamento de falhas
- Modo de quiosque mais seguro ao eliminar aplicativos disponíveis em falhas do modo de quiosque. 

Antes de encontrar falhas na aplicação do modo de quiosque, o HoloLens costumava mostrar todos os aplicativos no menu iniciar. Agora no Windows Holographic versão 20H2 no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, como abaixo: 

![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Armazenar em cache a associação de grupo do Azure AD para quiosque offline
- Os quiosques offline habilitados serão usados com grupos do Azure AD por até 60 dias.

Essa política controla por quantos dias o cache de associação de grupo do Azure AD pode ser usado para configurações de acesso atribuídas direcionando grupos do Azure AD para o usuário conectado. Quando esse valor de política for definido como valor maior que 0 somente, o cache será usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays URI value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 dias  
Máx.-60 dias 

Etapas para usar esta política corretamente: 
1. Crie um perfil de configuração de dispositivo para o quiosque de destino de grupos do Azure AD e atribua-o a dispositivos do HoloLens. 
1. Crie uma configuração de dispositivo personalizada de OMA URI que defina esse valor de política para o número de dias desejado (> 0) e atribua-o aos dispositivos do HoloLens. 
    1. O valor do URI deve ser inserido na caixa de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre min/max permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário 1 do Azure AD entre quando a Internet estiver disponível, quando o usuário entrar e a associação de grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário 1 do Azure AD pode colocar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD. o ponto-chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que eles são membros do grupo do Azure AD ao qual a configuração de quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para um usuário do Azure AD passará por um comportamento de falha mencionado em ambientes "desconectados". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Exemplos de código de quiosque XML para o HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Modo de quiosque de vários aplicativos direcionado a um grupo do Azure AD. 
Esse quiosque implanta um quiosque que, para usuários no grupo do Azure AD, terá um quiosque habilitado que inclui os 3 aplicativos: configurações, assistência remota e Hub de comentários. Para modificar este exemplo a ser usado imediatamente, certifique-se de alterar o GUID realçado abaixo para corresponder a um grupo do Azure AD por conta própria. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Vários modos de quiosque de aplicativo direcionados à conta do Azure AD.
Este quiosque implanta um quiosque para um único usuário, ele terá um quiosque habilitado que inclui os 3 aplicativos: configurações, assistência remota e Hub de comentários. Para modificar este exemplo a ser usado imediatamente, certifique-se de alterar a conta realçada abaixo para corresponder a uma conta do Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

