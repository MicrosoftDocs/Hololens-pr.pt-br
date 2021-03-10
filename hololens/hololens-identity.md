---
title: Gerenciar a identidade do usuário e entrar no HoloLens
description: Saiba como gerenciar a identidade do usuário, o suporte a vários usuários, a segurança, a autenticação empresarial e a entrada para dispositivos HoloLens.
keywords: HoloLens, usuário, conta, AAD, Azure AD, adfs, conta da Microsoft, msa, credenciais, referência
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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400681"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gerenciar a identidade do usuário e entrar no HoloLens

> [!NOTE]
> Este artigo é uma referência técnica para profissionais de TI e entusiastas da tecnologia. Se você estiver procurando instruções de configuração do HoloLens, leia " Configurando seu[HoloLens (1ª geração)](hololens1-start.md)" ou " Configurando seu[HoloLens 2](hololens2-start.md)".

Como outros dispositivos Windows, o HoloLens sempre opera em um contexto de usuário. Sempre há uma identidade de usuário. O HoloLens trata a identidade da mesma maneira que outros dispositivos Windows 10. Este artigo é uma referência de profundidade para identidade no HoloLens e se concentra em como o HoloLens difere de outros dispositivos Windows 10.

O HoloLens oferece suporte a vários tipos de identidades de usuário. Você pode usar uma ou mais contas de usuário para entrar. Aqui está uma visão geral dos tipos de identidade e opções de autenticação no HoloLens:

| Tipo de identidade | Contas por dispositivo | Opções de autenticação |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (requer o Azure AD Premium) | 64 | <ul><li>Provedor de credenciais da Web do Azure</li><li>Aplicativo autenticador do Azure</li><li>Biometria (Iris) &ndash; HoloLens 2 apenas <sup> 1</sup> </li><li>PIN &ndash; opcional para HoloLens (1ª geração), necessário para o HoloLens 2</li><li>Senha</li></ul> |
| [Conta da Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometria (Iris) &ndash; HoloLens 2 somente</li><li>PIN &ndash; opcional para HoloLens (1ª geração), necessário para o HoloLens 2</li><li>Senha</li></ul> |
| [Conta local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Senha |

Contas conectadas à nuvem (Azure AD e MSA) oferecem mais recursos porque podem usar os serviços do Azure.  

> [!NOTE]
> 1 - Embora um dispositivo holoLens 2 possa suportar até 64 contas do Azure AD, apenas 10 dessas contas podem se registrar na Autenticação Iris. Isso é alinhado com outras opções de [autenticação biométrica para o Windows Hello para Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Configurando usuários

A maneira mais comum de configurar um novo usuário é durante a experiência do HoloLens (OOBE). Durante a instalação, o HoloLens solicita que um usuário entre usando a conta que deseja usar no dispositivo. Essa conta pode ser uma conta da Microsoft de consumidor ou uma conta corporativa que foi configurada no Azure. Consulte Configurando seu [HoloLens (1ª geração)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

Como o Windows em outros dispositivos, entrar durante a instalação cria um perfil de usuário no dispositivo. O perfil de usuário armazena aplicativos e dados. A mesma conta também fornece Logon Único para aplicativos como Edge ou Skype usando as APIs do Gerenciador de Contas do Windows.  

Se você usar uma conta corporativa ou organizacional para entrar no HoloLens, o HoloLens se inscreverá na infraestrutura de TI da organização. Esse registro permite que o administrador de IT configure o Gerenciamento de Dispositivo Móvel (MDM) para enviar políticas de grupo para o HoloLens.

Por padrão, quanto a outros dispositivos Windows 10, você terá que entrar novamente quando o HoloLens reiniciar ou retomar a espera. Você pode usar o aplicativo Configurações para alterar esse comportamento ou o comportamento pode ser controlado pela política de grupo.

### <a name="linked-accounts"></a>Contas vinculadas

Como na versão desktop do Windows, você pode vincular credenciais de conta web adicionais à sua conta do HoloLens. Essa vinculação facilita o acesso a recursos em aplicativos (como a Loja) ou combinando o acesso a recursos pessoais e de trabalho. Depois de conectar uma conta ao dispositivo, você pode conceder permissão para usar o dispositivo em aplicativos para que não seja preciso entrar em cada aplicativo individualmente.

Vincular contas não separa os dados do usuário criados no dispositivo, como imagens ou downloads.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configurando o suporte a vários usuários (somente no Azure AD)

O HoloLens dá suporte a vários usuários do mesmo locatário do Azure AD. Para usar esse recurso, você deve usar uma conta que pertence à sua organização para configurar o dispositivo. Posteriormente, outros usuários do mesmo locatário podem entrar no dispositivo na tela de entrada ou tocando no painel Iniciar. Somente um usuário pode ser assinado por vez. Quando um usuário entrar, o HoloLens assina o usuário anterior. O primeiro usuário no dispositivo é considerado o proprietário do dispositivo, exceto no caso de Ingressar no Azure AD, saiba mais [sobre proprietários de dispositivos](security-adminless-os.md#device-owner).

Todos os usuários podem usar os aplicativos instalados no dispositivo. No entanto, cada usuário tem seus próprios dados de aplicativo e preferências. Remover um aplicativo do dispositivo remove-o para todos os usuários.  

Dispositivos definidos com contas do Azure AD não permitirão entrar no dispositivo com uma conta da Microsoft. Todas as contas subsequentes usadas devem ser contas do Azure AD do mesmo locatário do dispositivo. Você ainda pode [entrar usando uma Conta da Microsoft para aplicativos](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que a suportam (como a Microsoft Store). Para alterar o uso de contas do Azure AD para Contas da Microsoft para entrar no dispositivo, você deve [reabilcar o dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **O HoloLens (1ª geração)** começou a oferecer suporte a vários usuários do Azure AD na Atualização do Windows 10 de abril de [2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) como parte do [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

## <a name="removing-users"></a>Removendo usuários

Você pode remover um usuário do dispositivo indo para **Configurações**  >  **Contas**  >  **Outras pessoas**. Essa ação também recupera espaço removendo todos os dados do aplicativo desse usuário do dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Usando o logom único em um aplicativo

Como desenvolvedor de aplicativos, você pode tirar proveito das identidades vinculadas no HoloLens usando as [APIs](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)do Windows Account Manager , assim como faria em outros dispositivos Windows. Alguns exemplos de código para essas APIs estão disponíveis no GitHub: Exemplo de gerenciamento de contas [da Web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Qualquer interrupção de conta que possa ocorrer, como solicitação de consentimento do usuário para informações da conta, autenticação de dois fatores e assim por diante, deve ser tratada quando o aplicativo solicita um token de autenticação.

Se seu aplicativo exigir um tipo de conta específico que não tenha sido vinculado anteriormente, seu aplicativo poderá solicitar que o sistema peça ao usuário para adicionar um. Essa solicitação aciona o painel de configurações da conta para ser lançado como um filho modal do seu aplicativo. Para aplicativos 2D, essa janela renderiza diretamente sobre o centro do seu aplicativo. Para aplicativos Unity, essa solicitação tira brevemente o usuário do aplicativo holográfico para renderizar a janela filha. Para obter informações sobre como personalizar os comandos e ações neste painel, consulte [WebAccountCommand Class](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise e outras autenticações

Se seu aplicativo usa outros tipos de autenticação, como NTLM, Basic ou Kerberos, você pode usar a interface do usuário do [Windows Credential](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) para coletar, processar e armazenar as credenciais do usuário. A experiência do usuário para coletar essas credenciais é muito semelhante a outras interrupções de conta orientadas por nuvem e aparece como um aplicativo filho em cima do seu aplicativo 2D ou suspende brevemente um aplicativo Unity para mostrar a interface do usuário.

## <a name="deprecated-apis"></a>APIs preterida

Uma maneira na qual o desenvolvimento para o HoloLens difere do desenvolvimento para Área de Trabalho é que a API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) não é totalmente suportada. Embora a API retorne um token se a conta primária estiver em boas condições, as interrupções, como as descritas neste artigo, não exibem nenhuma interface do usuário para o usuário e não conseguem autenticar corretamente a conta.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>O Windows Hello para Empresas tem suporte no HoloLens (1ª Geração)?

O Windows Hello para Empresas (que dá suporte ao uso de um PIN para entrar) é compatível com o HoloLens (1ª Geração). Para permitir a login do PIN do Windows Hello para Empresas no HoloLens:

1. O dispositivo HoloLens deve ser [gerenciado pelo MDM](hololens-enroll-mdm.md).
1. Você deve habilitar o Windows Hello para Empresas para o dispositivo. ([Consulte instruções para o Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. No HoloLens, o usuário pode usar **Configurações**  >  **Opções de Login**Adicionar  >  **PIN** para configurar um PIN.

> [!NOTE]
> Os usuários que entrar usando uma conta da Microsoft também podem configurar um PIN em **Configurações**Opções  >  **de login Adicionar**  >  **PIN**. Esse PIN está associado ao [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), em vez do Windows Hello [para Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Como a autenticação biométrica iris é implementada no HoloLens 2?

O HoloLens 2 dá suporte à autenticação Iris. O Iris é baseado na tecnologia do Windows Hello e tem suporte para uso pelo Azure Active Directory e contas da Microsoft. O Iris é implementado da mesma forma que outras tecnologias do Windows Hello e alcança a segurança biométrica DE 1/100K.

Confira os [requisitos biométricos e especificações do Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obter mais informações. Saiba mais sobre [o Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) e o Windows Hello para [Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Como o tipo de conta afeta o comportamento de entrar?

Se você aplicar políticas para entrar, a política sempre é respeitada. Se nenhuma política de login for aplicada, esses serão os comportamentos padrão para cada tipo de conta:

- **Azure AD**: solicita autenticação por padrão e configurável por **Configurações** para não solicitar mais autenticação.
- **Conta da Microsoft**: o comportamento de bloqueio é diferente, permitindo o desbloqueio automático, no entanto, a autenticação de entrada ainda é necessária na reinicialização.
- **Conta local**: sempre pede autenticação na forma de uma senha, não configurável **em Configurações**

> [!NOTE]
> No momento, os timers de inatividade não são suportados, o que significa que a **política AllowIdleReturnWithoutPassword** só é respeitada quando o dispositivo entra em StandBy.

## <a name="additional-resources"></a>Recursos adicionais

Leia muito mais sobre a proteção e autenticação de identidade do usuário na documentação de segurança [e identidade do Windows 10.](https://docs.microsoft.com/windows/security/identity-protection/)

Saiba mais sobre como configurar a infraestrutura de identidade híbrida completa a documentação de identidade [híbrida do Azure](https://docs.microsoft.com/azure/active-directory/hybrid/).
