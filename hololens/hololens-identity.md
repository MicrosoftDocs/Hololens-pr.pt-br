---
title: Gerenciar identidade e credenciais do usuário para o HoloLens
description: saiba como gerenciar a identidade do usuário, suporte a vários usuários, segurança, autenticação corporativa e entrada para dispositivos HoloLens.
keywords: HoloLens, usuário, conta, AAD, Azure AD, adfs, conta da microsoft, msa, credenciais, referência
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e4c68ad6535293f916cc92c42204954110edc4fe
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189537"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gerenciar identidade e credenciais do usuário para o HoloLens

> [!NOTE]
> Este artigo é uma referência técnica para profissionais de ti e entusiastas técnicos. se você estiver procurando HoloLens instruções de configuração, leia "[configurando seu HoloLens (1ª gen)](hololens1-start.md)" ou "[configurando seu HoloLens 2](hololens2-start.md)".

como outros dispositivos Windows, HoloLens sempre funciona em um contexto de usuário. Sempre há uma identidade de usuário. HoloLens trata a identidade quase da mesma maneira que outros dispositivos Windows. este artigo é uma referência aprofundada para identidade em HoloLens e se concentra em como HoloLens difere de outros dispositivos Windows.

o HoloLens dá suporte a vários tipos de identidades de usuário. Você pode usar uma ou mais contas de usuário para entrar. Aqui está uma visão geral dos tipos de identidade e das opções de autenticação no HoloLens:

| Tipo de identidade | Contas por dispositivo | Opções de autenticação |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Provedor de credenciais da Web do Azure</li><li>Azure Authenticator aplicativo</li><li>biometria (íris) &ndash; HoloLens 2 somente<sup>2</sup> </li><li>Chave de segurança do FIDO2</li><li>PIN &ndash; opcional para HoloLens (1º gen), necessário para HoloLens 2</li><li>Senha</li></ul> |
| [MSA (conta Microsoft)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>biometria (íris) &ndash; HoloLens apenas 2</li><li>PIN &ndash; opcional para HoloLens (1º gen), necessário para HoloLens 2</li><li>Senha</li></ul> |
| [Conta local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Senha |

As contas conectadas à nuvem (Azure AD e MSA) oferecem mais recursos porque podem usar os serviços do Azure.  
> [!IMPORTANT]
> 1-não é necessário um Azure AD Premium para entrar no dispositivo. No entanto, ele é necessário para outros recursos de uma implantação baseada em nuvem de baixo toque, como registro automático e AutoPilot.

> [!NOTE]
> 2-embora um dispositivo HoloLens 2 possa dar suporte a até 64 contas do Azure AD, somente 31 dessas contas podem se registrar na autenticação da íris. isso é alinhado com outras [opções de autenticação biométrica para Windows Hello para negócios](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

> [!IMPORTANT]
> 3-uma conta local só pode ser configurada em um dispositivo [por meio de um pacote de provisionamento durante o OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup), ela não pode ser adicionada posteriormente no aplicativo de configurações. Se você quiser usar uma conta local em um dispositivo que já esteja configurado, será necessário refazer [o flash ou redefinir o dispositivo.](hololens-recovery.md)

## <a name="setting-up-users"></a>Configurando usuários

Há duas maneiras de configurar um novo usuário na HoloLens. a maneira mais comum é durante o HoloLens a OOBE (experiência inicial no uso). se estiver usando Azure Active Directory, [outros usuários poderão fazer logon](#setting-up-multi-user-support-azure-ad-only) após o OOBE usando suas credenciais do Azure AD. HoloLens dispositivos que são inicialmente configurados com uma conta do MSA ou local durante o OOBE não terão suporte para vários usuários. consulte configurando sua [HoloLens (1ª gen)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

se você usar uma conta corporativa ou organizacional para entrar no HoloLens, o HoloLens se registrará na infraestrutura de ti da organização. Esse registro permite que o administrador de ti configure o MDM (gerenciamento de dispositivo móvel) para enviar políticas de grupo para seu HoloLens.

assim como Windows em outros dispositivos, entrar durante a instalação cria um perfil de usuário no dispositivo. O perfil de usuário armazena aplicativos e dados. a mesma conta também fornece logon único para aplicativos, como o Edge ou o Microsoft Store, usando as APIs do gerenciador de contas do Windows.

por padrão, como em outros dispositivos Windows 10, você terá que entrar novamente quando HoloLens reinicializar ou retomar do modo de espera. você pode usar o aplicativo Configurações para alterar esse comportamento ou o comportamento pode ser controlado pela diretiva de grupo.

### <a name="linked-accounts"></a>Contas vinculadas

como na versão da área de trabalho do Windows, você pode vincular credenciais de conta da web adicionais à sua conta do HoloLens. Essa vinculação facilita o acesso a recursos entre os aplicativos (como a loja) ou a combinação de acesso a recursos pessoais e de trabalho. Depois de conectar uma conta ao dispositivo, você pode conceder permissão para usar o dispositivo para aplicativos para que você não precise entrar em cada aplicativo individualmente.

A vinculação de contas não separa os dados do usuário criados no dispositivo, como imagens ou downloads.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configurando o suporte a vários usuários (somente Azure AD)

o HoloLens dá suporte a vários usuários do mesmo locatário do Azure AD. Para usar esse recurso, você deve usar uma conta que pertença à sua organização para configurar o dispositivo. Subsequentemente, outros usuários do mesmo locatário podem entrar no dispositivo na tela de entrada ou tocando no bloco do usuário no painel Iniciar. Somente um usuário pode ser conectado por vez. quando um usuário entra, HoloLens desconecta o usuário anterior. 

>[!IMPORTANT]
> O primeiro usuário no dispositivo é considerado o proprietário do dispositivo, exceto no caso de ingresso no Azure AD, [saiba mais sobre os proprietários do dispositivo](security-adminless-os.md#device-owner).

Todos os usuários podem usar os aplicativos instalados no dispositivo. No entanto, cada usuário tem seus próprios dados e preferências de aplicativo. A remoção de um aplicativo do dispositivo o Remove para todos os usuários.  

Os dispositivos configurados com as contas do Azure AD não permitirão entrar no dispositivo com uma conta da Microsoft. Todas as contas subsequentes usadas devem ser contas do Azure AD do mesmo locatário que o dispositivo. Você ainda pode [entrar usando uma conta da Microsoft para aplicativos](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que dão suporte a ela (como o Microsoft Store). Para alterar o uso de contas do Azure AD para contas da Microsoft para entrar no dispositivo, você deve refazer [o flash do dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1º gen)** começou a dar suporte a vários usuários do Azure AD na [atualização Windows 10 abril de 2018](/windows/mixed-reality/release-notes-april-2018) como parte do [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela de entrada

Anteriormente, a tela de entrada mostrou apenas o usuário conectado mais recentemente, bem como um ponto de entrada de "outro usuário". Recebemos comentários dos clientes de que isso não é suficiente se vários usuários tiverem entrado no dispositivo. Eles ainda eram solicitados a digitar novamente o nome de usuário, etc.

introduzido no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), ao selecionar **outro usuário** que está localizado à direita do campo de entrada de PIN, a tela de entrada exibirá vários usuários com o conectado anteriormente ao dispositivo. isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entrem usando suas credenciais de Windows Hello. Um novo usuário também pode ser adicionado ao dispositivo por meio dessa página de outros usuários por meio do botão **adicionar conta** .

Quando estiver no menu outros usuários, o botão outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela de entrada deste usuário.

![Padrão da tela de entrada.](./images/multiusers1.jpg)

<br>

![Tela de entrada de outros usuários.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Removendo usuários

você pode remover um usuário do dispositivo acessando **Configurações**  >  **contas**  >  **outras pessoas**. Essa ação também recupera espaço removendo todos os dados de aplicativo do usuário do dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Usando o logon único em um aplicativo

como desenvolvedor de aplicativos, você pode aproveitar as identidades vinculadas no HoloLens usando as [APIs do gerenciador de contas do Windows](/uwp/api/Windows.Security.Authentication.Web.Core), assim como faria em outros dispositivos Windows. alguns exemplos de código para essas APIs estão disponíveis em GitHub: [exemplo de gerenciamento de contas da Web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Qualquer interrupção de conta que possa ocorrer, como solicitação de consentimento do usuário para informações de conta, autenticação de dois fatores e assim por diante, deve ser tratada quando o aplicativo solicita um token de autenticação.

Se seu aplicativo exigir um tipo de conta específico que não tenha sido vinculado anteriormente, seu aplicativo poderá solicitar que o sistema solicite ao usuário para adicionar um. Essa solicitação dispara o painel de configurações de conta para iniciar como um filho modal de seu aplicativo. Para aplicativos 2D, essa janela é renderizada diretamente sobre o centro do seu aplicativo. Para aplicativos do Unity, essa solicitação retira brevemente o usuário do seu aplicativo Holographic para renderizar a janela filho. Para obter informações sobre como personalizar os comandos e ações nesse painel, consulte [classe WebAccountCommand](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise e outras autenticações

se seu aplicativo usar outros tipos de autenticação, como NTLM, básico ou Kerberos, você poderá usar [Windows interface do usuário de credencial](/uwp/api/Windows.Security.Credentials.UI) para coletar, processar e armazenar as credenciais do usuário. A experiência do usuário para coletar essas credenciais é muito semelhante a outras interrupções de conta voltadas para a nuvem e aparece como um aplicativo filho sobre seu aplicativo 2D ou suspende brevemente um aplicativo do Unity para mostrar a interface do usuário.

## <a name="deprecated-apis"></a>APIs obsoletas

uma maneira na qual o desenvolvimento para HoloLens difere do desenvolvimento para área de trabalho é que a API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) não tem suporte total. Embora a API retorne um token se a conta primária estiver em boas condições, interrupções como as descritas neste artigo não exibem nenhuma interface do usuário para o usuário e não autenticam corretamente a conta.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Há Windows Hello para Empresas com suporte HoloLens (1ª geração)?

Windows Hello for Business (que dá suporte ao uso de um PIN para entrar) tem suporte para HoloLens (1ª geração). Para permitir Windows Hello para a assinatura do PIN de Negócios no HoloLens:

1. O HoloLens dispositivo deve ser [gerenciado pelo MDM.](hololens-enroll-mdm.md)
1. Você deve habilitar Windows Hello para Empresas para o dispositivo. ([Consulte instruções para Microsoft Intune.](/intune/windows-hello))
1. No HoloLens, o usuário pode usar Configurações Opções de Logon  >    >  **Adicionam PIN** para configurar um PIN.

> [!NOTE]
> Os usuários que entrarem usando um conta Microsoft também podem configurar um PIN **Configurações** opções de login  >    >  **Adicionar PIN.** Esse PIN está associado ao [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), em vez [Windows Hello para Empresas.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Como a autenticação biométrica iris é implementada no HoloLens 2?

HoloLens 2 dá suporte à autenticação Iris. O Iris é baseado Windows Hello tecnologia e tem suporte para uso por contas Azure Active Directory e Microsoft. O Iris é implementado da mesma maneira que outras tecnologias Windows Hello e atinge a segurança de biometria DISTANTE de [1/100 mil.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)

Confira os [requisitos biométricos e as especificações Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obter mais informações. Saiba mais sobre [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) e [Windows Hello para Empresas.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="where-is-iris-biometric-information-stored"></a>Onde as informações biométricas do Iris são armazenadas?

As informações biométricas de íris são armazenadas localmente em cada HoloLens por [Windows Hello especificações .](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored) Ele não é compartilhado e é protegido por duas camadas de criptografia. Ele não está acessível a outros usuários, até mesmo a um administrador, porque não há nenhuma conta de administrador em um HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Preciso usar a autenticação Iris?
Não, você pode ignorar esta etapa durante a instalação. 

![Configurar o Iris.](./images/setup-iris.png)

HoloLens 2 fornece muitas opções diferentes para autenticação, incluindo chaves de segurança FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>As informações do Iris podem ser removidas do HoloLens?
Sim, você pode removê-lo manualmente Configurações.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Como o tipo de conta afeta o comportamento de login?

Se você aplicar políticas para entrar, a política sempre é respeitada. Se nenhuma política de login for aplicada, estes são os comportamentos padrão para cada tipo de conta:

- **Azure AD**: solicita autenticação por padrão e configurável por Configurações **para** não solicitar mais autenticação.
- **conta Microsoft**: o comportamento de bloqueio é diferente, permitindo o desbloqueio automático, no entanto, a autenticação de entrada ainda é necessária na reinicialização.
- **Conta local**: sempre solicita autenticação na forma de uma senha, não configurável em **Configurações**

> [!NOTE]
> Atualmente, não há suporte para temporizadores de inatividade, o que significa que a **política AllowIdleReturnWithoutPassword** só é respeitada quando o dispositivo entra em espera.

## <a name="additional-resources"></a>Recursos adicionais

Leia muito mais sobre a proteção de identidade do usuário e a autenticação [na documentação Windows 10 segurança e identidade](/windows/security/identity-protection/)do .

Saiba mais sobre como configurar a infraestrutura de identidade híbrida por completo na [documentação de identidade híbrida do Azure.](/azure/active-directory/hybrid/)
