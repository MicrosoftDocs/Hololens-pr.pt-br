---
title: Configure o HoloLens como um quiosque
description: Use uma configuração de quiosque para bloquear os aplicativos no HoloLens.
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
ms.openlocfilehash: f560dae725cbce8658bdf2a135c5061b5332f797
ms.sourcegitcommit: 456a88907d606f4c4532b153d5a848e214b6b8e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "11182002"
---
# Configure o HoloLens como um quiosque

Você pode configurar um dispositivo HoloLens para funcionar como um dispositivo de finalidade fixa, também chamado de *quiosque*, configurando o dispositivo para ser executado no modo de quiosque. O modo de quiosque limita os aplicativos (ou usuários) que estão disponíveis no dispositivo. O modo de quiosque é um recurso conveniente que você pode usar para dedicar um dispositivo HoloLens a aplicativos comerciais ou usar o dispositivo HoloLens em uma demonstração do aplicativo.

Este artigo fornece informações sobre os aspectos da configuração do quiosque que são específicos para dispositivos HoloLens. Para obter informações gerais sobre os diferentes tipos de quiosques baseados no Windows e como configurá-los, consulte [Configurar quiosques e sinais digitais em edições do Windows Desktop](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> O modo de quiosque determina quais aplicativos estão disponíveis quando um usuário entra no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Ele não interrompe um aplicativo "permitido" de abrir outro aplicativo que não é permitido. Para impedir a abertura de aplicativos ou processos, use o [CSP WDAC (controle de aplicativos do Windows Defender)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas.
>
> Saiba mais sobre os serviços da Microsoft para dar aos usuários um nível avançado de segurança que o HoloLens 2 usa, leia mais sobre a [separação de estado e proteções de isolamento e isolamento](security-state-separation-isolation.md#defender-protections). Ou aprenda a [usar o WDAC e o Windows PowerShell para permitir ou bloquear aplicativos em dispositivos do HoloLens 2 com o Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Você pode usar o modo de quiosque em uma configuração de aplicativo único ou de vários aplicativos, e você pode usar um dos três processos para configurar e implantar a configuração do quiosque.

> [!IMPORTANT]  
> Excluir a configuração de vários aplicativos remove os perfis de bloqueio de usuário que o recurso de acesso atribuído criou. No entanto, ele não reverte todas as alterações de política. Para reverter essas políticas, você precisa redefinir o dispositivo para as configurações de fábrica.

## Planejar a implantação do quiosque

Ao planejar seu quiosque, você precisará ser capaz de atender às seguintes perguntas. Aqui estão algumas decisões a serem pensadas durante a leitura desta página e algumas considerações para essas perguntas.
1. **Quem usará o seu quiosque e que [tipo de conta](hololens-identity.md) ele vai usar?** Esta é uma decisão que você já deve ter feito e não deve ser ajustada para o seu quiosque, mas afetará como o quiosque será atribuído mais tarde.
1. **Você precisa ter quiosques diferentes por usuário/grupo ou um quiosque não está habilitado para alguns?** Em caso afirmativo, você desejará criar seu quiosque via XML. 
1. **Quantos aplicativos estarão em seu quiosque?** Se você tiver mais de um aplicativo, precisará de um quiosque de vários aplicativos. 
1. **Quais são os aplicativos do seu quiosque?** Use nossa lista de AUMIDs abaixo para adicionar qualquer aplicativo In-Box além de seu próprio.
1. **Como você planeja implantar seu quiosque?** Se você estiver registrando o dispositivo no MDM, sugerimos usar o MDM para implantar seu quiosque. Se você não estiver usando o MDM, a implantação com o pacote de provisionamento estará disponível.  

### Requisitos do modo de quiosque

Você pode configurar qualquer dispositivo HoloLens 2 para usar o modo de quiosque.

> [!IMPORTANT]
> O modo de quiosque estará disponível somente se o dispositivo tiver o Windows holográfico for Business. Todos os dispositivos do HoloLens 2 são fornecidos com o Windows holográfico para empresas e não há outras versões. Todos os dispositivos HoloLens 2 podem executar o modo de quiosque.
>
> Dispositivos HoloLens (1ª gen) precisam ser atualizados tanto em termos de compilação do sistema operacional quanto na edição do sistema operacional. Veja mais informações sobre como atualizar um HoloLens (1ª gen) para o [Windows holográfico for Business](hololens1-upgrade-enterprise.md) Edition. Para atualizar um dispositivo HoloLens (1ª gen) para usar o modo de quiosque, primeiro você deve ter certeza de que o dispositivo executa o Windows 10, versão 1803 ou uma versão posterior. Se você tiver usado a ferramenta de recuperação de dispositivos do Windows para recuperar seu dispositivo HoloLens (1ª gen) para a compilação padrão ou se tiver instalado as atualizações mais recentes, o dispositivo estará pronto para ser configurado.

> [!IMPORTANT]  
> Para ajudar a proteger dispositivos executados no modo de quiosque, considere adicionar políticas de gerenciamento de dispositivos que desativem recursos como a conectividade USB. Além disso, verifique as configurações de toques de atualização para garantir que as atualizações automáticas não ocorram durante o horário comercial.

### Decidir entre um quiosque de aplicativo único ou um quiosque de vários aplicativos

Um quiosque de aplicativo único inicia o aplicativo especificado quando o usuário entra no dispositivo. O menu iniciar está desabilitado, assim como a Cortana. Um dispositivo HoloLens 2 não responde ao gesto de [Iniciar](hololens2-basic-usage.md#start-gesture) . Um dispositivo HoloLens (1ª gen) não responde ao gesto de [cair](hololens1-basic-usage.md) . Como somente um aplicativo pode ser executado, o usuário não pode colocar outros aplicativos.

Um quiosque de vários aplicativos exibe o menu iniciar quando o usuário entra no dispositivo. A configuração do quiosque determina quais aplicativos estão disponíveis no menu iniciar. Você pode usar um quiosque de vários aplicativos para fornecer uma experiência fácil de entender para os usuários, apresentando a eles apenas as coisas que eles precisam usar e removendo os itens que eles não precisam usar.

A tabela a seguir lista os recursos de recursos nos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu ações rápidas |Câmera e vídeo |Miracast |Cortana |Comandos de voz internos |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Quiosque de aplicativo único |Desabilitada |Desabilitada   |Desabilitada |Desabilitada   |Desabilitada |Habilitado <sup> 1</sup> |
|Quiosque de vários aplicativos |Habilitado |Habilitado <sup> 2</sup> |Disponível <sup> 2</sup> |Disponível <sup> 2</sup> |Disponível <sup> 2, 3</sup>  |Habilitado <sup> 1</sup> |

> <sup>1 os </sup> comandos de voz relacionados a recursos desabilitados não funcionam.  
> <sup>2 </sup> para obter mais informações sobre como configurar esses recursos, consulte [selecionar aplicativos quiosque](#plan-kiosk-apps).  
> <sup>3 </sup> mesmo se a Cortana estiver desabilitada, os comandos de voz internos serão habilitados.

A tabela a seguir lista os recursos de suporte do usuário dos diferentes modos de quiosque.

| &nbsp; |Tipos de usuários com suporte | Entrada automática | Vários níveis de acesso |
| --- | --- | --- | --- |
|Quiosque de aplicativo único |MSA (conta de serviço gerenciado) no Azure Active Directory (AAD) ou conta local |Sim |Não |
|Quiosque de vários aplicativos |Conta do AAD |Não |Sim |

Para obter exemplos de como usar esses recursos, consulte a tabela a seguir.

|Use um quiosque de aplicativo único para: |Use um quiosque de vários aplicativos para: |
| --- | --- |
|Um dispositivo que executa apenas um guia do Dynamics 365 para novos funcionários. |Um dispositivo que executa tanto guias quanto assistência remota para vários funcionários. |
|Um dispositivo que executa apenas um aplicativo personalizado. |Um dispositivo que funciona como um quiosque para a maioria dos usuários (executando somente um aplicativo personalizado), mas funciona como um dispositivo padrão para um grupo específico de usuários. |

### Planejar aplicativos quiosque

Para obter informações gerais sobre como escolher os aplicativos de quiosque, consulte [diretrizes para escolher um aplicativo para acesso atribuído (modo de quiosque)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Se você usar o Windows Device portal para configurar um quiosque de aplicativo único, selecione o aplicativo durante o processo de instalação.  

Se você usa um sistema de gerenciamento de dispositivos móveis (MDM) ou um pacote de provisionamento para configurar o modo de quiosque, use o [provedor de serviços de configuração (CSP) do AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) para especificar aplicativos. O CSP usa [IDs do modelo de usuário do aplicativo (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar aplicativos. A tabela a seguir lista os AUMIDs de alguns aplicativos in-box que você pode usar em um quiosque de vários aplicativos.

> [!IMPORTANT]
> O modo de quiosque determina quais aplicativos estão disponíveis quando um usuário entra no dispositivo. No entanto, o modo de quiosque não é um método de segurança. Ele não interrompe um aplicativo "permitido" de abrir outro aplicativo que não é permitido. Como não restringem esse comportamento, os aplicativos ainda podem ser iniciados a partir do Edge, do explorador de arquivos e dos aplicativos da Microsoft Store. Se houver aplicativos específicos que você não deseja que sejam iniciados em um quiosque, use o [CSP WDAC (controle de aplicativos do Windows Defender)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para criar políticas apropriadas. 
> 
> Além disso, a página inicial da realidade misturada não pode ser definida como um aplicativo quiosque.

<a id="aumids"></a>

|Nome do aplicativo |AUMID |
| --- | --- |
|Visualizador 3D |Microsoft. Microsoft3DViewer \ _8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendário |Microsoft. windowscommunicationsapps \ _8wekyb3d8bbwe \! Microsoft. windowslive. Calendar |
|Câmera <sup> 1, 2</sup> |HoloCamera \ _cw5n1h2txyewy \! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft. 549981C3F5F10 \ _8wekyb3d8bbwe \! AppV |
|Seletor de dispositivo no HoloLens (1ª gen) |HoloDevicesFlow \ _cw5n1h2txyewy \! HoloDevicesFlow |
|Seletor de dispositivo no HoloLens 2 |Microsoft. Windows. DevicesFlowHost \ _cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Guias do Dynamics 365 |Microsoft. Dynamics365. guias \ _8wekyb3d8bbwe \! MicrosoftGuides |
|Assistência Remota do Dynamics 365 |Microsoft. MicrosoftRemoteAssist \ _8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Hub de feedback &nbsp; |Microsoft. WindowsFeedbackHub \ _8wekyb3d8bbwe \! AppV |
|Explorador de Arquivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. windowslive. mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Filmes e TV |Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |Microsoft. microsoftskydrive \ _8wekyb3d8bbwe \! AppV |
|Fotos |Microsoft. Windows. photos \ _8wekyb3d8bbwe \! AppV |
|Configurações |HolographicSystemSettings \ _cw5n1h2txyewy \! AppV |
|Dicas |Microsoft. HoloLensTips \ _8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 </sup> para habilitar a captura de fotos ou vídeos, você precisa habilitar o aplicativo de câmera como um aplicativo de quiosque.  
> <sup>2 </sup> ao habilitar o aplicativo câmera, lembre-se das seguintes condições:
> - O menu ações rápidas inclui os botões foto e vídeo.  
> - Você também deve habilitar um aplicativo (como fotos, email ou OneDrive) que pode interagir ou recuperar imagens.  
>  
> <sup>3 </sup> mesmo se você não habilitar a Cortana como um aplicativo quiosque, os comandos de voz internos serão habilitados. No entanto, os comandos relacionados a recursos desabilitados não têm efeito.  
> <sup>4 </sup> você não pode habilitar o Miracast diretamente. Para habilitar o Miracast como um aplicativo quiosque, habilite o aplicativo câmera e o aplicativo seletor de dispositivo.

### Planejar perfis do quiosque para usuários ou grupos

Ao criar o arquivo XML ou usar a interface do usuário do Intune para configurar um quiosque, você precisará considerar quem será usuário o quiosque. Uma configuração de quiosque pode ser limitada a uma conta individual ou a grupos do Azure AD. 

Geralmente, os quiosques são habilitados para um usuário ou grupo de usuários. No entanto, se você planeja escrever seu próprio quiosque XML, talvez queira considerar o acesso atribuído global, no qual o quiosque é aplicado no nível do dispositivo independentemente da identidade. Se este apelo você [ler mais sobre os quiosques de acesso atribuídos globalmente.](hololens-global-assigned-access-kiosk.md)

#### Se você estiver criando um arquivo XML:
-   Você cria vários perfis de quiosque e os atribui a usuários/grupos diferentes. Como um quiosque para o grupo AAD que tem muitos aplicativos e um visitante que tenha um quiosque de vários aplicativos com um aplicativo singular.
-   Sua configuração de quiosque será chamada de **ID de perfil** e terá um GUID.
-   Você atribuirá esse perfil na seção Configurações especificando o tipo de usuário e usando o mesmo GUID para a ID de **DefaultProfile**.
- Um arquivo XML pode ser criado, mas ainda aplicado a um dispositivo por meio de MDM, criando um perfil de configuração de dispositivo OMA URI personalizado e aplicando-o ao grupo de dispositivos HoloLens usando o valor de URI:./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Se você estiver criando um quiosque no Intune.
-   Cada dispositivo pode receber apenas um perfil de quiosque único, caso contrário, criará um conflito e não receberá configurações de quiosque. 
    -   Outros tipos de perfis e políticas, como restrições de dispositivo que não estão relacionados ao perfil de configuração do quiosque, não entram em conflito com o perfil de configuração do quiosque.
-   O quiosque será habilitado para todos os usuários que fazem parte do tipo de logon do usuário, ele será definido com um usuário ou grupo do AAD. 
-   Depois que a configuração do quiosque é definida e o **tipo de logon do usuário** (usuários que podem entrar no quiosque) e os aplicativos são selecionados, a configuração do dispositivo ainda deve ser atribuída a um grupo. O (s) grupo (s) atribuído determina quais dispositivos recebem a configuração do dispositivo de quiosque, mas não interage com se o quiosque estiver habilitado ou não. 
    - Para obter uma discussão completa dos efeitos de atribuir perfis de configuração no Intune, consulte [atribuir perfis de usuário e de dispositivo no Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### Selecionar um método de implantação

Você pode selecionar um dos seguintes métodos para implantar as configurações do quiosque:

- [Microsoft Intune ou outro serviço de gerenciamento de dispositivo móvel (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Como esse método requer que o modo de desenvolvedor seja habilitado no dispositivo, recomendamos que você o use apenas para demonstrações.

A tabela a seguir lista as funcionalidades e os benefícios de cada um dos métodos de implantação.

| &nbsp; |Implantar usando o Windows Device Portal |Implantar usando um pacote de provisionamento |Implantar usando o MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Implantar quiosques de aplicativo único   | Sim           | Sim                  | Sim  |
|Implantar quiosques de vários aplicativos    | Não            | Sim                  | Sim  |
|Implantar somente em dispositivos locais | Sim           | Sim                  | Não   |
|Implantar usando o modo de desenvolvedor |Obrigatório       | Não necessário            | Não necessário   |
|Implantar usando o Azure Active Directory (AAD)  | Não necessário            | Não necessário                   | Obrigatório  |
|Implantar automaticamente      | Não            | Não                   | Sim  |
|Velocidade de implantação            | Rápido       | Rápido                 | Modo Lento |
|Implantar em escala | Não recomendado    | Recomendações        | Recomendações |

## Usar o Microsoft Intune ou outro MDM para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando o Microsoft Intune ou outro sistema MDM, siga estas etapas.

1. [Prepare-se para registrar os dispositivos](#mdmenroll).
1. [Crie um perfil de configuração de quiosque](#mdmprofile).
1. Configurar o quiosque.
   - [Defina as configurações para um quiosque de aplicativo único](#mdmconfigsingle).
   - [Defina as configurações para um quiosque de vários aplicativos](#mdmconfigmulti).
1. [Atribua o perfil de configuração do quiosque a um grupo](#mdmassign).
1. Implantar os dispositivos.
   - [Implantar um quiosque de aplicativo único](#mdmsingledeploy).
   - [Implantar um quiosque de vários aplicativos](#mdmmultideploy).

### <a id="mdmenroll"></a>MDM, etapa 1 &ndash; preparar-se para registrar os dispositivos

Você pode configurar seu sistema MDM para registrar dispositivos HoloLens automaticamente quando o usuário entrar pela primeira vez ou fazer com que os usuários registrem dispositivos manualmente. Os dispositivos também precisam estar associados ao seu domínio do Azure AD e atribuídos aos grupos apropriados.

Para obter mais informações sobre como registrar os dispositivos, consulte [registrar o HoloLens nos](hololens-enroll-mdm.md) métodos de registro do MDM e [do Intune para dispositivos Windows](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a id="mdmprofile"></a>MDM, etapa 2 &ndash; criar um perfil de configuração de quiosque

1. Abra o portal [do Azure](https://portal.azure.com/) e entre em sua conta de administrador do Intune.
1. Selecione configuração de dispositivo **do Microsoft Intune**  >  **-perfis**  >  **Create Profile**.
1. Digite um nome de perfil.
1. Selecione **plataforma**  >  **Windows 10 e posterior**e, em seguida, selecione **tipo de perfil**  > **restrições de dispositivo**.
1. Selecione **Configurar**  >  **quiosque**e, em seguida, selecione uma das seguintes opções:
   - Para criar um quiosque de aplicativo único, selecione **Kiosk Mode**o  >  **quiosque do aplicativo único**do modo de quiosque.
   - Para criar um quiosque de vários aplicativos, selecione **Kiosk Mode**  >  **quiosque de vários aplicativos**do modo de quiosque.
1. Para começar a configurar o quiosque, selecione **Adicionar**.

As próximas etapas são diferentes dependendo do tipo de quiosque que você deseja. Para obter mais informações, selecione uma das seguintes opções:  

- [Quiosque de aplicativo único](#mdmconfigsingle)
- [Quiosque de vários aplicativos](#mdmconfigmulti)

Para obter mais informações sobre como criar um perfil de configuração de quiosque, consulte [configurações de dispositivos Windows 10 e Windows holográfico para empresas para executar como quiosque dedicado usando o Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a id="mdmconfigsingle"></a>MDM, etapa 3 (aplicativo único) &ndash;  configurar as definições para um quiosque de aplicativo único

Esta seção resume as configurações necessárias para um quiosque de aplicativo único. Para obter mais detalhes, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte [como configurar o modo de quiosque usando o Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as configurações disponíveis para quiosques de aplicativo único no Intune, consulte [quiosques de aplicativos de tela inteira](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções. Se você precisar usar uma configuração XML personalizada para configurar um quiosque em seu serviço de MDM, [crie um arquivo XML que define a configuração do quiosque](#ppkioskconfig).

1. Selecione **tipo de logon de usuário**  >  **conta de usuário local**e insira o nome de usuário da conta local (dispositivo) ou da conta da Microsoft (MSA) que pode entrar no quiosque.
   > [!NOTE]  
   > Os tipos de conta de usuário de **logon automático** não são compatíveis com o Windows holográfico para empresas.
1. Selecione aplicativo **Application Type**  >  **Store**e, em seguida, selecione um aplicativo na lista.

A próxima etapa é [atribuir](#mdmassign) o perfil a um grupo.

### <a id="mdmconfigmulti"></a>MDM, etapa 3 (vários aplicativos) &ndash; configurar as definições para um quiosque de vários aplicativos

Esta seção resume as configurações necessárias para um quiosque de vários aplicativos. Para obter informações mais detalhadas, consulte os seguintes artigos:

- Para obter informações sobre como configurar um perfil de configuração de quiosque no Intune, consulte [como configurar o modo de quiosque usando o Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obter mais informações sobre as configurações disponíveis para quiosques de vários aplicativos no Intune, consulte [quiosques de vários aplicativos](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções. Se você precisar usar uma configuração XML personalizada para configurar um quiosque em seu serviço de MDM, [crie um arquivo XML que define a configuração do quiosque](#ppkioskconfig). Se você usar um arquivo XML, certifique-se de incluir o [layout de início](#start-layout-for-hololens).  
- Opcionalmente, você pode usar um layout de início personalizado com o Intune ou outros serviços de MDM. Para obter mais informações, consulte [iniciar o arquivo de layout para MDM (Intune e outros)](#start-layout-file-for-mdm-intune-and-others).

1. Selecione **destino Windows 10 no modo S dispositivos S**  >  **No**.  
   >[!NOTE]  
   > O modo S não é compatível com o Windows holográfico para empresas.
1. Selecione **tipo de logon**  >  **do usuário, usuário ou grupo do Azure ad ou grupo** de logon do **usuário**  >  ,**visitante**do Azure e adicione um ou mais grupos ou contas de usuário.  

   Somente os usuários que pertencem aos grupos ou contas que você especificar no **tipo de logon do usuário** podem usar a experiência de quiosque.

1. Selecione um ou mais aplicativos usando as seguintes opções:
   - Para adicionar um aplicativo de linha de negócios carregado, selecione **Adicionar aplicativo da loja** e selecione o aplicativo desejado.
   - Para adicionar um aplicativo especificando seu AUMID, selecione **Adicionar por AUMID** e, em seguida, insira o AUMID do aplicativo. [Veja a lista de AUMIDs disponíveis](#aumids)

A próxima etapa é [atribuir](#mdmassign) o perfil a um grupo.

### <a id="mdmassign"></a>MDM, etapa 4 &ndash; atribuir o perfil de configuração do quiosque a um grupo

Use a página de **atribuições** do perfil de configuração do quiosque para definir onde você deseja que a configuração do quiosque seja implantada. No caso mais simples, você atribui o perfil de configuração do quiosque a um grupo que conterá o dispositivo HoloLens quando o dispositivo for registrado no MDM.

### <a id="mdmsingledeploy"></a>MDM, etapa 5 (aplicativo único) &ndash; implantar um quiosque de aplicativo único

Ao usar um sistema MDM, você pode registrar o dispositivo no MDM durante OOBE. Após o OOBE terminar, é fácil conectar-se ao dispositivo.

Durante o OOBE, siga estas etapas:

1. Entre usando a conta que você especificou no perfil de configuração do quiosque.
1. Registrar o dispositivo. Verifique se o dispositivo foi adicionado ao grupo ao qual o perfil de configuração do quiosque está atribuído.
1. Aguarde até que o OOBE seja concluído, para que o aplicativo da loja seja baixado e instalado, e para que as políticas sejam aplicadas. Em seguida, reinicie o dispositivo.

Na próxima vez que você entrar no dispositivo, o aplicativo quiosque será iniciado automaticamente.

Se você não vir a configuração do quiosque nesse ponto, [Verifique o status da tarefa](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a id="mdmmultideploy"></a>MDM, etapa 5 (vários aplicativos) &ndash; implantar um quiosque de vários aplicativos

Ao usar um sistema MDM, você pode ingressar no dispositivo em seu locatário do Azure AD e registrar o dispositivo no MDM durante o OOBE. Se for apropriado, forneça as informações de registro aos usuários para que elas o disponibilizem durante o processo OOBE.

> [!NOTE]  
> Se você tiver atribuído o perfil de configuração do quiosque a um grupo que contém usuários, verifique se uma dessas contas de usuário é a primeira conta para entrar no dispositivo.

Durante o OOBE, siga estas etapas:

1. Entre usando a conta que pertence ao grupo tipo de **logon de usuário** .
1. Registrar o dispositivo.
1. Aguarde todos os aplicativos que fazem parte do perfil de configuração do quiosque baixar e instalar. Além disso, aguarde até que as políticas sejam aplicadas.  
1. Após a conclusão do OOBE, você pode instalar aplicativos adicionais da Microsoft Store ou de Sideload. [Aplicativos obrigatórios](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) para o grupo que o dispositivo pertence a instalar automaticamente.
1. Após a conclusão da instalação, reinicie o dispositivo.

Na próxima vez que você entrar no dispositivo usando uma conta que pertence ao **tipo de logon do usuário**, o aplicativo quiosque deve ser iniciado automaticamente.

Se você não vir a configuração do quiosque nesse ponto, [Verifique o status da tarefa](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou de vários aplicativos

Para configurar o modo de quiosque usando um pacote de provisionamento, siga estas etapas.

1. [Crie um arquivo XML que define a configuração do quiosque.](#ppkioskconfig), incluindo um [layout de início](#start-layout-for-hololens).
2. [Adicione o arquivo XML a um pacote de provisionamento.](#ppconfigadd)
3. [Aplicar o pacote de provisionamento ao HoloLens.](#ppapply)

### <a id="ppkioskconfig"></a>Pacote de provisionamento, etapa 1 &ndash; criar um arquivo XML de configuração de quiosque

Siga [as instruções gerais para criar um arquivo XML de configuração de quiosque para a área de trabalho do Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), exceto para o seguinte:

- Não inclua aplicativos clássicos do Windows (Win32). O HoloLens não é compatível com esses aplicativos.
- Use o [XML de layout de início do espaço reservado](#start-layout-for-hololens) para o HoloLens.
- Opcional: adicionar acesso de convidado à configuração do quiosque

#### <a id="ppkioskguest"></a>Opcional: adicionar acesso de convidado à configuração do quiosque

Na seção [ **configurações** do arquivo XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), você pode configurar um grupo especial chamado **visitante** para permitir que os convidados usem o quiosque. Quando o quiosque está configurado para dar suporte ao grupo especial de **visitante** , uma opção de "**convidado**" é adicionada à página de entrada. A conta de **convidado** não requer uma senha, e todos os dados associados à conta são excluídos quando a conta se desconecta.

Para habilitar a conta de **convidado** , adicione o seguinte snippet ao seu XML de configuração do quiosque:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Layout inicial do espaço reservado para HoloLens

Se você usar um [pacote de provisionamento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque de vários aplicativos, o procedimento exigirá um layout de início. A personalização do layout de início não é compatível com o Windows holográfico para empresas. Portanto, você precisará usar um layout de início de espaço reservado.

> [!NOTE]  
> Como um quiosque de aplicativo único inicia o aplicativo quiosque quando um usuário entra, ele não usa um menu iniciar e não precisa ter um layout de início.

> [!NOTE]  
> Se você usar o [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) para configurar um quiosque de vários aplicativos, você pode usar opcionalmente um layout de início. Para obter mais informações, consulte [arquivo de layout do início do espaço reservado para MDM (Intune e outros)](#start-layout-file-for-mdm-intune-and-others).

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Espaço reservado para o arquivo de layout do MDM (Intune e outros)

Salve o exemplo a seguir como um arquivo XML. Você pode usar esse arquivo quando configurar o quiosque de vários aplicativos no Microsoft Intune (ou em outro serviço do MDM que forneça um perfil de quiosque).

> [!NOTE]
> Se você precisar usar uma configuração personalizada e uma configuração XML completa para configurar um quiosque em seu serviço de MDM, use as [instruções de início do layout para um pacote de provisionamento](#start-layout-for-hololens).

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

### <a id="ppconfigadd"></a>Provavelmente. pacote, etapa 2 &ndash; Adicionar o arquivo XML de configuração do quiosque a um pacote de provisionamento

1. Abra o [Designer de configuração do Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Selecione **aprovisionamento avançado**, insira um nome para o seu projeto e selecione **Avançar**.
1. Selecione **Windows 10 holográfico**e, em seguida, selecione **Avançar**.
1. Selecione **concluir**. O espaço de trabalho para seu pacote é aberto.
1. Selecione **configurações de tempo de execução**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. No painel central, selecione **procurar** para localizar e selecionar o arquivo XML de configuração do quiosque que você criou.

   ![Captura de tela do campo MultiAppAssignedAccessSettings no Designer de Configuração do Windows](./images/multiappassignedaccesssettings.png)

1. **Opcional**. (Se você quiser aplicar o pacote de provisionamento após a configuração inicial do dispositivo e houver um usuário administrador já disponível no dispositivo quiosque, pule esta etapa.) Selecione **configurações de tempo de execução** &gt; **contas** &gt; **usuários**e, em seguida, crie uma conta de usuário. Forneça um nome de usuário e uma senha e selecione administradores do **UserGroup**  >  **Administrators**.  
  
     Ao usar esta conta, você pode exibir o status e os logs de provisionamento.  
1. **Opcional**. (Se você já tiver uma conta que não é de administrador no dispositivo quiosque, pule esta etapa.) Selecione **configurações de tempo de execução** &gt; **contas** &gt; **usuários**e, em seguida, crie uma conta de usuário local. Verifique se o nome de usuário é o mesmo para a conta que você especificar no XML de configuração. Selecione **UserGroup**  >  **usuários padrão**do UserGroup.
1. Selecione **arquivo**  >  **salvar**.
1. Selecione **Exportar**  >  **pacote de provisionamento**e selecione **proprietário**  >  **administrador de ti**. Isso define a precedência deste pacote de provisionamento superior ao provisionamento de pacotes que são aplicados a este dispositivo de outras fontes.
1. Selecione **Avançar**.
1. Na página **segurança do pacote de provisionamento** , selecione uma opção de segurança.
   > [!IMPORTANT]  
   > Se você selecionar **Habilitar assinatura de pacote**, também terá que selecionar um certificado válido para assinar o pacote. Para fazer isso, selecione **procurar** e selecione o certificado que você deseja usar para assinar o pacote.
   
   > [!CAUTION]  
   > Não selecione **habilitar a criptografia do pacote**. Em dispositivos HoloLens, essa configuração provoca uma falha no provisionamento.
1. Selecione **Avançar**.
1. Especifique o local de saída onde você deseja que o pacote de provisionamento passe quando for criado. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída. Se você quiser alterar o local de saída, selecione **procurar**. Quando terminar, selecione **Avançar**.
1. Selecione **Compilar** para começar a criar o pacote. O pacote de provisionamento não leva muito tempo para compilar. A página construir exibe as informações do projeto e a barra de progresso indica o status da compilação.

### <a id="ppapply"></a>Pacote de provisionamento, etapa 3 &ndash; aplicar o pacote de provisionamento ao HoloLens

O artigo "configurar o HoloLens usando um pacote de provisionamento" fornece instruções detalhadas para aplicar o pacote de provisionamento nas seguintes circunstâncias:

- Inicialmente, você pode [aplicar um pacote de provisionamento ao HoloLens durante a instalação](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Você também pode [aplicar um pacote de provisionamento ao HoloLens após a configuração](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).

## Usar o Windows Device portal para configurar um quiosque de aplicativo único

Para configurar o modo de quiosque usando o Windows Device portal, siga estas etapas.

1. [Configure o dispositivo HoloLens para usar o Windows Device portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). O Device Portal é um servidor Web no HoloLens ao qual você pode se conectar usando um navegador da Web em seu computador.

    > [!CAUTION]
    > Ao configurar o HoloLens para usar o Device portal, você precisa habilitar o modo de desenvolvedor no dispositivo. O modo de desenvolvedor em um dispositivo com o Windows holográfico for Business permite que você carregue aplicativos. No entanto, essa configuração cria um risco de que um usuário possa instalar aplicativos que não foram certificados pela Microsoft Store. Os administradores podem bloquear a capacidade de habilitar o modo de desenvolvedor usando a configuração de **desbloqueio ApplicationManagement/AllowDeveloper** no [CSP da política](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider). [Saiba mais sobre o Modo de desenvolvedor.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Em um computador, conecte-se ao HoloLens usando [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) ou [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Siga um destes procedimentos:
   - Se você estiver se conectando ao Windows Device portal pela primeira vez, [crie um nome de usuário e uma senha](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Digite o nome de usuário e a senha que você configurou anteriormente.

    > [!TIP]
    > Se você vir um erro de certificado no navegador, siga [estas etapas para solução de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).

1. No Windows Device portal, selecione **modo de quiosque**.

1. Selecione **habilitar o modo de quiosque**, selecione um aplicativo para ser executado quando o dispositivo for iniciado e selecione **salvar**.

    ![Modo de quiosque](images/kiosk.png)
1. Reinicie o HoloLens. Se a página do Device portal ainda estiver aberta, você poderá selecionar **reiniciar** na parte superior da página.

> [!NOTE]
> O modo de quiosque pode ser definido via API REST do Device portal fazendo uma POSTAgem para/API/Holographic/KioskMode/Settings com um parâmetro de cadeia de consulta obrigatório ("kioskModeEnabled" com um valor de "true" ou "false") e um parâmetro opcional ("startupApp" com um valor de um nome de pacote). Lembre-se de que o Device portal destina-se apenas aos desenvolvedores e não deve ser habilitado em dispositivos que não sejam desenvolvedores. A API REST está sujeita a alterações em atualizações/versões futuras.

## Mais informações

### Veja como configurar um quiosque usando um pacote de provisionamento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### Acesso global atribuído – modo de quiosque
- Gerenciamento de identidades reduzido para o quiosque, habilitando o novo método quiosque que aplica o modo de quiosque no nível do sistema.

Este novo recurso permite que um administrador de ti configure um dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com qualquer identidade no sistema e se aplica a todos os participantes do dispositivo. Leia sobre esse novo recurso em detalhes [aqui](hololens-global-assigned-access-kiosk.md).

### Inicialização automática de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência destaques com o lançamento automático do aplicativo, melhorando ainda mais a interface do usuário e as seleções de aplicativos escolhidas para experiências do modo de quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e somente um aplicativo pode ser designado para inicialização automática usando o atributo realçado abaixo na configuração de acesso atribuído. 

O aplicativo é iniciado automaticamente quando o usuário entra. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### Alterações de comportamento do modo de quiosque para manipulação de falhas
- Modo de quiosque mais seguro eliminando aplicativos disponíveis em falhas do modo de quiosque. 

Antes de encontrar falhas na aplicação do modo de quiosque, o HoloLens é usado para exibir todos os aplicativos no menu iniciar. Agora, no Windows holográfico Version 20H2, no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, como a seguir: 

![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### Armazenar Associação de grupo no AAD para quiosque offline
- Foram habilitados quiosques offline para serem usados com grupos AAD por até 60 dias.

Esta política controla o número de dias, o cache de associações do grupo AAD pode ser usado para configurações de acesso atribuídas direcionando grupos do AAD para o usuário conectado. Quando esse valor de política é definido como valor maior que 0 somente, o cache é usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays URI value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín-0 dias  
Máx-60 dias 

Etapas para usar esta política corretamente: 
1. Crie um perfil de configuração de dispositivo para grupos do AAD de direcionamento de quiosque e atribua-o a dispositivo (s) HoloLens (s). 
1. Crie uma configuração de dispositivo baseada em OMA URI, que define esse valor de política como o número desejado de dias (> 0) e atribua-o a dispositivo (s) do HoloLens. 
    1. O valor de URI deve ser inserido na caixa de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre min/max permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Deixe que o usuário do AAD 1 entre quando a Internet estiver disponível, quando o usuário entrar e a associação do grupo AAD for confirmada com êxito, o cache será criado. 
1. Agora o usuário do AAD 1 pode pegar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do AAD. o ponto da chave aqui é que qualquer usuário do AAD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que ele é membro do grupo AAD para o qual a configuração do quiosque está direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja realizada para um usuário do AAD experimentará um comportamento de falha mencionado em ambientes "desconectados". 


## Exemplos de códigos de quiosque XML para HoloLens

### Modo de quiosque de vários aplicativos direcionado a um grupo do AAD. 
Este quiosque implanta um quiosque que para usuários no grupo AAD, ele terá um quiosque habilitado que inclui os 3 aplicativos: configurações, assistência remota e Hub de feedback. Para modificar esse exemplo para ser usado imediatamente, certifique-se de alterar o GUID realçado abaixo para corresponder a um grupo do AAD de sua preferência. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### Modo de quiosque de aplicativo múltiplo de direcionamento de conta do AAD.
Esse quiosque implanta um quiosque para um único usuário, ele terá um quiosque habilitado que inclui os 3 aplicativos: configurações, assistência remota e Hub de feedback. Para modificar esse exemplo para ser usado imediatamente, altere a conta realçada abaixo para corresponder a uma conta do AAD do seu. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

