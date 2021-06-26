---
title: Gerenciar identidade e credenciais do usuário para o HoloLens
description: Saiba como gerenciar a identidade do usuário, suporte a vários usuários, segurança, autenticação corporativa e entrada para dispositivos HoloLens.
keywords: HoloLens, usuário, conta, AAD, Azure AD, ADFS, conta da Microsoft, MSA, credenciais, referência
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
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924410"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gerenciar identidade e credenciais do usuário para o HoloLens

> [!NOTE]
> Este artigo é uma referência técnica para profissionais de ti e entusiastas técnicos. Se você estiver procurando instruções de configuração do HoloLens, leia "[configurando seu hololens (1ª gen)](hololens1-start.md)" ou "[configurando seu hololens 2](hololens2-start.md)".

Assim como outros dispositivos Windows, o HoloLens sempre funciona em um contexto de usuário. Sempre há uma identidade de usuário. O HoloLens trata a identidade quase da mesma maneira que outros dispositivos Windows 10. Este artigo é uma referência aprofundada para identidade no HoloLens e se concentra em como o HoloLens difere de outros dispositivos Windows 10.

O HoloLens dá suporte a vários tipos de identidades de usuário. Você pode usar uma ou mais contas de usuário para entrar. Aqui está uma visão geral dos tipos de identidade e das opções de autenticação no HoloLens:

| Tipo de identidade | Contas por dispositivo | Opções de autenticação |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Provedor de credenciais da Web do Azure</li><li>Azure Authenticator aplicativo</li><li>Biométrico (íris) &ndash; HoloLens 2 somente<sup>2</sup> </li><li>PIN &ndash; opcional para hololens (1º gen), necessário para o hololens 2</li><li>Senha</li></ul> |
| [MSA (conta da Microsoft)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biométrico (íris) &ndash; somente HoloLens 2</li><li>PIN &ndash; opcional para hololens (1º gen), necessário para o hololens 2</li><li>Senha</li></ul> |
| [Conta local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Senha |

As contas conectadas à nuvem (Azure AD e MSA) oferecem mais recursos porque podem usar os serviços do Azure.  
> [!IMPORTANT]
> 1-não é necessário um Azure AD Premium para entrar no dispositivo. No entanto, ele é necessário para outros recursos de uma implantação baseada em nuvem de baixo toque, como registro automático e AutoPilot.

> [!NOTE]
> 2-embora um dispositivo HoloLens 2 possa dar suporte a até 64 contas do Azure AD, somente 10 dessas contas podem se registrar na autenticação de íris. Isso está alinhado com outras [Opções de autenticação biométrica para o Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

## <a name="setting-up-users"></a>Configurando usuários

A maneira mais comum de configurar um novo usuário é durante a configuração inicial pelo usuário do HoloLens (OOBE). Durante a instalação, o HoloLens solicita que um usuário entre usando a conta que deseja usar no dispositivo. Essa conta pode ser um conta Microsoft de consumidor ou uma conta empresarial que foi configurada no Azure. Consulte Configurando seu [hololens (1º gen)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

Como o Windows em outros dispositivos, entrar durante a instalação cria um perfil de usuário no dispositivo. O perfil de usuário armazena aplicativos e dados. A mesma conta também fornece logon único para aplicativos, como o Edge ou o Microsoft Store, usando as APIs do Gerenciador de contas do Windows.  

Se você usar uma conta corporativa ou organizacional para entrar no HoloLens, o HoloLens será registrado na infraestrutura de ti da organização. Esse registro permite que o administrador de ti configure o MDM (gerenciamento de dispositivo móvel) para enviar políticas de grupo ao seu HoloLens.

Por padrão, como em outros dispositivos Windows 10, você precisará entrar novamente quando o HoloLens for reiniciado ou retomado do modo de espera. Você pode usar o aplicativo configurações para alterar esse comportamento ou o comportamento pode ser controlado pela diretiva de grupo.

### <a name="linked-accounts"></a>Contas vinculadas

Como na versão da área de trabalho do Windows, você pode vincular credenciais de conta da Web adicionais à sua conta do HoloLens. Essa vinculação facilita o acesso a recursos entre os aplicativos (como a loja) ou a combinação de acesso a recursos pessoais e de trabalho. Depois de conectar uma conta ao dispositivo, você pode conceder permissão para usar o dispositivo para aplicativos para que você não precise entrar em cada aplicativo individualmente.

A vinculação de contas não separa os dados do usuário criados no dispositivo, como imagens ou downloads.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configurando o suporte a vários usuários (somente Azure AD)

O HoloLens dá suporte a vários usuários do mesmo locatário do Azure AD. Para usar esse recurso, você deve usar uma conta que pertença à sua organização para configurar o dispositivo. Subsequentemente, outros usuários do mesmo locatário podem entrar no dispositivo na tela de entrada ou tocando no bloco do usuário no painel Iniciar. Somente um usuário pode ser conectado por vez. Quando um usuário entra, o HoloLens desconecta o usuário anterior. O primeiro usuário no dispositivo é considerado o proprietário do dispositivo, exceto no caso de ingresso no Azure AD, [saiba mais sobre os proprietários do dispositivo](security-adminless-os.md#device-owner).

Todos os usuários podem usar os aplicativos instalados no dispositivo. No entanto, cada usuário tem seus próprios dados e preferências de aplicativo. A remoção de um aplicativo do dispositivo o Remove para todos os usuários.  

Os dispositivos configurados com as contas do Azure AD não permitirão entrar no dispositivo com uma conta da Microsoft. Todas as contas subsequentes usadas devem ser contas do Azure AD do mesmo locatário que o dispositivo. Você ainda pode [entrar usando uma conta da Microsoft para aplicativos](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que dão suporte a ela (como o Microsoft Store). Para alterar o uso de contas do Azure AD para contas da Microsoft para entrar no dispositivo, você deve refazer [o flash do dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> O **HoloLens (1º gen)** começou a dar suporte a vários usuários do Azure ad na [atualização do Windows 10 de abril de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) como parte do [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Vários usuários listados na tela de entrada

Anteriormente, a tela de entrada mostrou apenas o usuário conectado mais recentemente, bem como um ponto de entrada de "outro usuário". Recebemos comentários dos clientes de que isso não é suficiente se vários usuários tiverem entrado no dispositivo. Eles ainda eram solicitados a digitar novamente o nome de usuário, etc.

Introduzido no [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), ao selecionar **outro usuário** que está localizado à direita do campo de entrada de PIN, a tela de entrada exibirá vários usuários com o conectado anteriormente ao dispositivo. Isso permite que os usuários selecionem seu perfil de usuário e, em seguida, entrem usando suas credenciais do Windows Hello. Um novo usuário também pode ser adicionado ao dispositivo por meio dessa página de outros usuários por meio do botão **adicionar conta** .

Quando estiver no menu outros usuários, o botão outros usuários exibirá o último usuário conectado ao dispositivo. Selecione este botão para retornar à tela de entrada deste usuário.

![Padrão da tela de entrada](./images/multiusers1.jpg)

<br>

![Tela de entrada de outros usuários](./images/multiusers2.jpg)

## <a name="removing-users"></a>Removendo usuários

Você pode remover um usuário do dispositivo acessando **configurações**  >  **contas**  >  **outras pessoas**. Essa ação também recupera espaço removendo todos os dados de aplicativo do usuário do dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Usando o logon único em um aplicativo

Como desenvolvedor de aplicativos, você pode aproveitar as identidades vinculadas no HoloLens usando as [APIs do Gerenciador de contas do Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core), assim como faria em outros dispositivos Windows. Alguns exemplos de código para essas APIs estão disponíveis no GitHub: [exemplo de gerenciamento de contas da Web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Qualquer interrupção de conta que possa ocorrer, como solicitação de consentimento do usuário para informações de conta, autenticação de dois fatores e assim por diante, deve ser tratada quando o aplicativo solicita um token de autenticação.

Se seu aplicativo exigir um tipo de conta específico que não tenha sido vinculado anteriormente, seu aplicativo poderá solicitar que o sistema solicite ao usuário para adicionar um. Essa solicitação dispara o painel de configurações de conta para iniciar como um filho modal de seu aplicativo. Para aplicativos 2D, essa janela é renderizada diretamente sobre o centro do seu aplicativo. Para aplicativos do Unity, essa solicitação retira brevemente o usuário do seu aplicativo Holographic para renderizar a janela filho. Para obter informações sobre como personalizar os comandos e ações nesse painel, consulte [classe WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise e outras autenticações

Se o seu aplicativo usar outros tipos de autenticação, como NTLM, básico ou Kerberos, você poderá usar a [interface do usuário da credencial do Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) para coletar, processar e armazenar as credenciais dos usuários. A experiência do usuário para coletar essas credenciais é muito semelhante a outras interrupções de conta voltadas para a nuvem e aparece como um aplicativo filho sobre seu aplicativo 2D ou suspende brevemente um aplicativo do Unity para mostrar a interface do usuário.

## <a name="deprecated-apis"></a>APIs obsoletas

Uma maneira na qual o desenvolvimento para o HoloLens difere do desenvolvimento para área de trabalho é que a API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) não tem suporte total. Embora a API retorne um token se a conta principal estiver em boas condições, as interrupções, como as descritas neste artigo, não exibirão nenhuma interface do usuário e falharão ao autenticar corretamente a conta.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>O Windows Hello para empresas é compatível com o HoloLens (1º gen)?

O Windows Hello para empresas (que dá suporte ao uso de um PIN para entrar) tem suporte para o HoloLens (1º gen). Para permitir a entrada do PIN do Windows Hello para empresas no HoloLens:

1. O dispositivo HoloLens deve ser [gerenciado pelo MDM](hololens-enroll-mdm.md).
1. Você deve habilitar o Windows Hello para empresas para o dispositivo. ([Consulte as instruções para Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. No HoloLens, o usuário pode usar **configurações**  >  **Opções de entrada**  >  **Adicionar PIN** para configurar um PIN.

> [!NOTE]
> Os usuários que entram usando um conta Microsoft também podem configurar um PIN em **configurações**  >  **Opções de entrada**  >  **Adicionar PIN**. Esse PIN é associado ao [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), em vez do [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Como a autenticação biométrica da íris é implementada no HoloLens 2?

O HoloLens 2 dá suporte à autenticação de íris. A íris se baseia na tecnologia do Windows Hello e tem suporte para uso por contas Azure Active Directory e da Microsoft. A íris é implementada da mesma forma que outras tecnologias do Windows Hello e atinge a segurança de biometria longe de 1/100 mil.

Consulte os [requisitos e as especificações biométricas do Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obter mais informações. Saiba mais sobre o [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) e o [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Como o tipo de conta afeta o comportamento de entrada?

Se você aplicar políticas para entrar, a política sempre é respeitada. Se nenhuma política de entrada for aplicada, esses serão os comportamentos padrão para cada tipo de conta:

- **Azure ad**: solicita autenticação por padrão e configurável por **configurações** para não solicitar mais autenticação.
- **Conta Microsoft**: o comportamento de bloqueio é diferente permitindo o desbloqueio automático. no entanto, a autenticação de entrada ainda é necessária na reinicialização.
- **Conta local**: sempre solicita autenticação na forma de uma senha, não configurável em **configurações**

> [!NOTE]
> Atualmente, não há suporte para timers de inatividade, o que significa que a política **AllowIdleReturnWithoutPassword** só será respeitada quando o dispositivo entrar em espera.

## <a name="additional-resources"></a>Recursos adicionais

Leia muito mais sobre a proteção de identidade do usuário e a autenticação na [documentação de identidade e segurança do Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

Saiba mais sobre como configurar a infraestrutura de identidade híbrida de forma completa a [documentação de identidade híbrida do Azure](https://docs.microsoft.com/azure/active-directory/hybrid/).
