---
title: Gerenciar identidade e credenciais do usuário para o HoloLens
description: Saiba como gerenciar a identidade do usuário, o suporte a vários usuários, a segurança, a autenticação corporativa e a entrada para HoloLens dispositivos.
keywords: HoloLens, usuário, conta, AAD, Azure AD, adfs, conta microsoft, msa, credenciais, referência
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
ms.openlocfilehash: 1081ed512183592e66e65f2e69323752b822f1c1
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659175"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gerenciar identidade e credenciais do usuário para o HoloLens

> [!NOTE]
> Este artigo é uma referência técnica para profissionais de TI e fãs de tecnologia. Se você estiver procurando instruções HoloLens configuração, leia " Configurando seu[HoloLens (1ª geração)](hololens1-start.md)" ou " Configurando seu[HoloLens 2](hololens2-start.md)".

Como outros Windows, o HoloLens sempre opera em um contexto de usuário. Sempre há uma identidade de usuário. HoloLens trata a identidade quase da mesma maneira que outros Windows 10 dispositivos. Este artigo é uma referência de profundidade para a identidade no HoloLens e se concentra em como HoloLens é diferente de outros Windows 10 dispositivos.

HoloLens dá suporte a vários tipos de identidades de usuário. Você pode usar uma ou mais contas de usuário para entrar. Aqui está uma visão geral dos tipos de identidade e das opções de autenticação HoloLens:

| Tipo de identidade | Contas por dispositivo | Opções de autenticação |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Provedor de credenciais da Web do Azure</li><li>Aplicativo de Authenticator Azure</li><li>Biometria &ndash; (Íris) HoloLens 2 apenas<sup>2</sup> </li><li>PIN &ndash; opcional para HoloLens (1ª geração), necessário para HoloLens 2</li><li>Senha</li></ul> |
| [Conta microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometria &ndash; (Íris) HoloLens somente 2</li><li>PIN &ndash; opcional para HoloLens (1ª geração), necessário para HoloLens 2</li><li>Senha</li></ul> |
| [Conta local](/windows/security/identity-protection/access-control/local-accounts) | 1 | Senha |

As contas conectadas à nuvem (Azure AD e MSA) oferecem mais recursos porque podem usar os serviços do Azure.  
> [!IMPORTANT]
> 1 - Azure AD Premium não é necessário entrar no dispositivo. No entanto, ele é necessário para outros recursos de uma implantação baseada em nuvem de baixo toque, como Registro automático e Autopilot.

> [!NOTE]
> 2 - Embora um HoloLens 2 possa dar suporte a até 64 contas do Azure AD, apenas 31 dessas contas podem ser inscritas na Autenticação Iris. Isso é alinhado com outras opções [de autenticação biométrica para Windows Hello para Empresas.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Configurando usuários

A maneira mais comum de configurar um novo usuário é durante a HoloLens OOBE (experiência de configuração). Durante a instalação, HoloLens solicita que um usuário entre usando a conta que deseja usar no dispositivo. Essa conta pode ser um conta Microsoft ou uma conta corporativa que foi configurada no Azure. Consulte Configurando seu [HoloLens (1ª geração)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

Como Windows em outros dispositivos, entrar durante a instalação cria um perfil de usuário no dispositivo. O perfil do usuário armazena aplicativos e dados. A mesma conta também fornece logon único para aplicativos, como o Edge ou o Microsoft Store, usando as APIs Windows Account Manager.  

Se você usar uma conta corporativa ou organizacional para entrar no HoloLens, HoloLens se registrará na infraestrutura de TI da organização. Esse registro permite que o administrador de IT configure o MDM (Mobile Gerenciamento de Dispositivos) para enviar políticas de grupo para seu HoloLens.

Por padrão, quanto a Windows 10 dispositivos de Windows 10, você terá que entrar novamente quando HoloLens é reiniciado ou retomado do modo de espera. Você pode usar o Configurações aplicativo para alterar esse comportamento ou o comportamento pode ser controlado pela política de grupo.

### <a name="linked-accounts"></a>Contas vinculadas

Assim como na versão desktop do Windows, você pode vincular credenciais adicionais da conta Web à sua HoloLens. Essa vinculação facilita o acesso a recursos entre aplicativos (como a Store) ou combinar o acesso a recursos pessoais e de trabalho. Depois de conectar uma conta ao dispositivo, você pode conceder permissão para usar o dispositivo em aplicativos para que não seja preciso entrar em cada aplicativo individualmente.

A vinculação de contas não separa os dados de usuário criados no dispositivo, como imagens ou downloads.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configurando o suporte a vários usuários (somente no Azure AD)

HoloLens dá suporte a vários usuários do mesmo locatário do Azure AD. Para usar esse recurso, você deve usar uma conta que pertence à sua organização para configurar o dispositivo. Posteriormente, outros usuários do mesmo locatário podem entrar no dispositivo na tela de entrada ou tocando no lado do usuário no painel Iniciar. Somente um usuário pode ser assinado por vez. Quando um usuário entrar, HoloLens o usuário anterior. O primeiro usuário no dispositivo é considerado o proprietário do dispositivo, exceto no caso do Azure AD Join, saiba mais sobre [os proprietários do dispositivo.](security-adminless-os.md#device-owner)

Todos os usuários podem usar os aplicativos instalados no dispositivo. No entanto, cada usuário tem seus próprios dados e preferências de aplicativo. Remover um aplicativo do dispositivo o remove para todos os usuários.  

Dispositivos definidos com contas do Azure AD não permitirão a entrada no dispositivo com uma Conta da Microsoft. Todas as contas subsequentes usadas devem ser contas do Azure AD do mesmo locatário que o dispositivo. Você ainda pode [entrar usando uma Conta da Microsoft para aplicativos](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que a suportam (como o Microsoft Store). Para alterar o uso de contas do Azure AD para contas da Microsoft para entrar no dispositivo, você deve [reflash o dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1ª geração)** começou a dar suporte a vários usuários do Azure AD na atualização de abril de [2018](/windows/mixed-reality/release-notes-april-2018) do Windows 10 como parte [do Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela Entrar

Anteriormente, a tela Entrar mostrava apenas o usuário que entrou mais recentemente, bem como um ponto de entrada "Outro usuário". Recebemos comentários dos clientes de que isso não é suficiente se vários usuários entraram no dispositivo. Eles ainda eram necessários para novo tipo de nome de usuário etc.

Introduzido no [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)ao selecionar Outro usuário localizado à direita do campo de entrada do PIN, a tela Entrar exibirá vários usuários com já conectados ao dispositivo.  Isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entre usando suas Windows Hello credenciais. Um novo usuário também pode ser adicionado ao dispositivo desta página Outros usuários por meio do **botão Adicionar conta.**

Quando estiver no menu Outros usuários, o botão Outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela Entrar para esse usuário.

![Padrão da tela de login](./images/multiusers1.jpg)

<br>

![Tela de login de outros usuários](./images/multiusers2.jpg)

## <a name="removing-users"></a>Removendo usuários

Você pode remover um usuário do dispositivo indo para contas **Configurações**  >    >  **Outras pessoas**. Essa ação também recupera espaço removendo todos os dados do aplicativo desse usuário do dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Usando o logom único dentro de um aplicativo

Como desenvolvedor de aplicativos, você pode aproveitar as identidades vinculadas no HoloLens usando as APIs do Gerenciador de Contas do [Windows,](/uwp/api/Windows.Security.Authentication.Web.Core)assim como faria em outros Windows dispositivos. Alguns exemplos de código para essas APIs estão disponíveis no GitHub: exemplo de [gerenciamento de conta Web.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Quaisquer interrupções de conta que possam ocorrer, como solicitar consentimento do usuário para informações de conta, autenticação de dois fatores e assim por diante, devem ser tratadas quando o aplicativo solicita um token de autenticação.

Se seu aplicativo exigir um tipo de conta específico que não tenha sido vinculado anteriormente, seu aplicativo poderá solicitar ao sistema que o usuário adicione um. Essa solicitação dispara o painel de configurações de conta para iniciar como um filho modal do seu aplicativo. Para aplicativos 2D, essa janela é renderiza diretamente sobre o centro do aplicativo. Para aplicativos unity, essa solicitação tira brevemente o usuário do seu aplicativo holográfico para renderizar a janela filho. Para obter informações sobre como personalizar os comandos e ações nesse painel, consulte [Classe WebAccountCommand](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise e outras autenticações

Se seu aplicativo usar outros tipos de autenticação, como NTLM, Basic ou Kerberos, você poderá usar a interface do usuário de credencial do [Windows](/uwp/api/Windows.Security.Credentials.UI) para coletar, processar e armazenar as credenciais do usuário. A experiência do usuário para coletar essas credenciais é muito semelhante a outras interrupções de conta controladas por nuvem e aparece como um aplicativo filho sobre seu aplicativo 2D ou suspende brevemente um aplicativo unity para mostrar a interface do usuário.

## <a name="deprecated-apis"></a>APIs obsoletas

Uma maneira na qual o desenvolvimento para HoloLens é diferente do desenvolvimento para a Área de Trabalho é que a API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) não tem suporte total. Embora a API retorne um token se a conta primária estiver em boas condições, interrupções como as descritas neste artigo não exibem nenhuma interface do usuário para o usuário e falham ao autenticar corretamente a conta.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Há Windows Hello para Empresas com suporte HoloLens (1ª geração)?

Windows Hello for Business (que dá suporte ao uso de um PIN para entrar) tem suporte para HoloLens (1ª geração). para permitir a entrada de PIN do Windows Hello for Business no HoloLens:

1. o dispositivo de HoloLens deve ser [gerenciado pelo MDM](hololens-enroll-mdm.md).
1. você deve habilitar a Windows Hello para empresas para o dispositivo. ([Consulte as instruções para Microsoft Intune.](/intune/windows-hello))
1. em HoloLens, o usuário pode usar **Configurações**  >  **opções de entrada**  >  **adicionar pin** para configurar um pin.

> [!NOTE]
> os usuários que entram usando um conta Microsoft também podem configurar um pin nas opções de   >  **entrada** Configurações  >  **adicionar pin**. esse PIN é associado a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), em vez de [Windows Hello para negócios](/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>como a autenticação biométrica da íris é implementada no HoloLens 2?

HoloLens 2 dá suporte à autenticação de íris. a íris se baseia na tecnologia de Windows Hello e tem suporte para uso por contas Azure Active Directory e da Microsoft. a íris é implementada da mesma maneira que outras tecnologias de Windows Hello e atinge a segurança de biometria longe de 1/100 mil.

consulte os [requisitos e especificações biométricas para Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obter mais informações. saiba mais sobre [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) e [Windows Hello para negócios](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Como o tipo de conta afeta o comportamento de entrada?

Se você aplicar políticas para entrar, a política sempre é respeitada. Se nenhuma política de entrada for aplicada, esses serão os comportamentos padrão para cada tipo de conta:

- **Azure AD**: solicita autenticação por padrão e pode ser configurada pelo **Configurações** para não solicitar mais autenticação.
- **Conta Microsoft**: o comportamento de bloqueio é diferente permitindo o desbloqueio automático. no entanto, a autenticação de entrada ainda é necessária na reinicialização.
- **conta Local**: sempre solicita autenticação na forma de uma senha, não configurável no **Configurações**

> [!NOTE]
> Atualmente, não há suporte para timers de inatividade, o que significa que a política **AllowIdleReturnWithoutPassword** só será respeitada quando o dispositivo entrar em espera.

## <a name="additional-resources"></a>Recursos adicionais

leia muito mais sobre a proteção de identidade do usuário e a autenticação na [documentação Windows 10 segurança e identidade](/windows/security/identity-protection/).

Saiba mais sobre como configurar a infraestrutura de identidade híbrida de forma completa a [documentação de identidade híbrida do Azure](/azure/active-directory/hybrid/).
