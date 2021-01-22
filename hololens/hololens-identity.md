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
ms.openlocfilehash: d9b7bebd9fd326def4ddfc2982bfecb09cb14186
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283272"
---
# Gerenciar a identidade do usuário e entrar no HoloLens

> [!NOTE]
> Este artigo é uma referência técnica para profissionais de TI e entusiastas de tecnologia. Se você estiver procurando instruções de configuração do HoloLens, leia " Configurando seu[HoloLens (1ª geração)](hololens1-start.md)" ou " Configurando seu[HoloLens 2](hololens2-start.md)".

Como outros dispositivos Windows, o HoloLens sempre opera em um contexto de usuário. Sempre há uma identidade de usuário. O HoloLens trata a identidade quase da mesma maneira que outros dispositivos Windows 10. Este artigo é uma referência profunda de identidade no HoloLens e se concentra em como o HoloLens difere de outros dispositivos Windows 10.

O HoloLens oferece suporte a vários tipos de identidades de usuário. Você pode usar uma ou mais contas de usuário para entrar. Aqui está uma visão geral dos tipos de identidade e das opções de autenticação no HoloLens:

| Tipo de identidade | Contas por dispositivo | Opções de autenticação |
| --- | --- | --- |
| [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Provedor de credenciais da Web do Azure</li><li>Aplicativo Autenticador do Azure</li><li>Biometria &ndash; (Íris) HoloLens 2 somente <sup> 1</sup> </li><li>PIN &ndash; opcional para HoloLens (1ª geração), necessário para o HoloLens 2</li><li>Senha</li></ul> |
| [Conta da Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Somente &ndash; HoloLens 2 biométrico (íris)</li><li>PIN &ndash; opcional para HoloLens (1ª geração), necessário para o HoloLens 2</li><li>Senha</li></ul> |
| [Conta local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Senha |

Contas conectadas à nuvem (Azure AD e MSA) oferecem mais recursos porque podem usar serviços do Azure.  

> [!NOTE]
> 1 - Embora um dispositivo HoloLens 2 possa dar suporte a até 64 contas do Azure AD, apenas 10 dessas contas podem se inscrever na Autenticação de Íris. Isso está alinhado com outras opções de [autenticação biométrica do Windows Hello para Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## Configurando usuários

A maneira mais comum de configurar um novo usuário é durante a configuração do HoloLens (OOBE). Durante a configuração, o HoloLens solicita que um usuário entre usando a conta que deseja usar no dispositivo. Essa conta pode ser uma conta da Microsoft de consumidor ou uma conta corporativa que tenha sido configurada no Azure. Consulte Configurando seu [HoloLens (1ª geração)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

Assim como o Windows em outros dispositivos, entrar durante a instalação cria um perfil de usuário no dispositivo. O perfil de usuário armazena aplicativos e dados. A mesma conta também fornece logon único para aplicativos como o Edge ou o Skype usando as APIs do Gerenciador de Contas do Windows.  

Se você usar uma conta corporativa ou organizacional para entrar no HoloLens, o HoloLens se registrará na infraestrutura de TI da organização. Esse registro permite que o administrador de IT configure o Gerenciamento de Dispositivo Móvel (MDM) para enviar políticas de grupo para o HoloLens.

Por padrão, quanto a outros dispositivos Windows 10, você terá que entrar novamente quando o HoloLens for reiniciado ou retomado do modo de espera. Você pode usar o aplicativo Configurações para alterar esse comportamento ou o comportamento pode ser controlado pela política de grupo.

### Contas vinculadas

Como na versão desktop do Windows, você pode vincular credenciais de conta Web adicionais à sua conta do HoloLens. Essa vinculação facilita o acesso a recursos em aplicativos (como a Loja) ou combinando o acesso a recursos pessoais e de trabalho. Depois de conectar uma conta ao dispositivo, você pode conceder permissão para usar o dispositivo em aplicativos para que você não tenha que entrar em cada aplicativo individualmente.

A vinculação de contas não separa os dados do usuário criados no dispositivo, como imagens ou downloads.  

### Configurando suporte para vários usuários (somente Azure AD)

O HoloLens dá suporte a vários usuários do mesmo locatário do Azure AD. Para usar esse recurso, você deve usar uma conta que pertence à sua organização para configurar o dispositivo. Posteriormente, outros usuários do mesmo locatário podem entrar no dispositivo na tela de entrada ou tocando no lado do usuário no painel Iniciar. Somente um usuário pode entrar por vez. Quando um usuário entrar, o HoloLens des saída do usuário anterior. O primeiro usuário no dispositivo é considerado o proprietário do dispositivo, exceto no caso de ingressar no Azure AD, saiba mais sobre [proprietários de dispositivos.](security-adminless-os.md#device-owner)

Todos os usuários podem usar os aplicativos instalados no dispositivo. No entanto, cada usuário tem seus próprios dados e preferências do aplicativo. Remover um aplicativo do dispositivo o remove para todos os usuários.  

Os dispositivos definidos com contas do Azure AD não permitirão entrar no dispositivo com uma conta da Microsoft. Todas as contas subsequentes usadas devem ser contas do Azure AD do mesmo locatário que o dispositivo. Você ainda pode [entrar usando uma conta da Microsoft para aplicativos](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que a suportam (como a Microsoft Store). Para alterar o uso de contas do Azure AD para contas da Microsoft para entrar no dispositivo, você deve [reflash o dispositivo.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **O HoloLens (1ª geração)** começou a dar suporte a vários usuários do Azure AD na atualização de abril de [2018 do Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) como parte do [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

## Removendo usuários

Você pode remover um usuário do dispositivo indo para **Configurações**  >  **contas de**outras  >  **pessoas**. Essa ação também recupera espaço removendo todos os dados de aplicativo desse usuário do dispositivo.  

## Usando o logor único em um aplicativo

Como desenvolvedor de aplicativos, você pode aproveitar as identidades vinculadas no HoloLens usando as APIs do Gerenciador de Contas do [Windows,](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)assim como faria em outros dispositivos Windows. Alguns exemplos de código para essas APIs estão disponíveis no GitHub: exemplo [de gerenciamento de conta da Web.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Qualquer interrupção de conta que possa ocorrer, como solicitar o consentimento do usuário para informações da conta, autenticação de dois fatores e assim por diante, deve ser tratada quando o aplicativo solicita um token de autenticação.

Se seu aplicativo exigir um tipo de conta específico que não tenha sido vinculado anteriormente, seu aplicativo poderá solicitar ao sistema que o usuário adicione um. Essa solicitação aciona o painel de configurações da conta para ser lançado como um filho modal do seu aplicativo. Para aplicativos 2D, essa janela renderiza diretamente sobre o centro do seu aplicativo. Para aplicativos Unity, essa solicitação brevemente retira o usuário do aplicativo holográfico para renderizar a janela filha. Para obter informações sobre como personalizar os comandos e ações neste painel, consulte [Classe WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Enterprise e outras autenticações

Se seu aplicativo usa outros tipos de autenticação, como NTLM, Basic ou Kerberos, você pode usar a interface do usuário do [Windows Credential](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) para coletar, processar e armazenar as credenciais do usuário. A experiência do usuário para coletar essas credenciais é muito semelhante a outras interrupções de conta orientadas por nuvem e aparece como um aplicativo filho sobre seu aplicativo 2D ou suspende brevemente um aplicativo Unity para mostrar a interface do usuário.

## APIs preterida

Uma maneira pela qual o desenvolvimento para o HoloLens difere do desenvolvimento para área de trabalho é que a API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) não é totalmente suportada. Embora a API retorne um token se a conta principal for de boa fé, interrupções como as descritas neste artigo não exibem nenhuma interface do usuário para o usuário e não conseguem autenticar corretamente a conta.

## Perguntas frequentes

### O Windows Hello para Empresas é suportado no HoloLens (1ª geração)?

O Windows Hello para Empresas (que dá suporte ao uso de um PIN para entrar) é compatível com o HoloLens (1ª geração). Para permitir a login do PIN do Windows Hello para Empresas no HoloLens:

1. O dispositivo HoloLens deve [ser gerenciado pelo MDM](hololens-enroll-mdm.md).
1. Você deve habilitar o Windows Hello para Empresas para o dispositivo. ([Consulte as instruções para o Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. No HoloLens, o usuário **** pode usar Opções de Logon de  >  **Configurações,**  >  **adicionar PIN** para configurar um PIN.

> [!NOTE]
> Os usuários que entrarem usando uma conta da **** Microsoft também podem configurar um PIN em Opções de Login  >  **de Configurações.**  >  **Adicione PIN.** Esse PIN está associado ao [Windows Hello,](https://support.microsoft.com/help/17215/windows-10-what-is-hello)em vez [do Windows Hello para Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### Como a autenticação biométrica de íris é implementada no HoloLens 2?

O HoloLens 2 dá suporte à autenticação de íris. A íris é baseada na tecnologia Windows Hello e é suportada para uso pelo Azure Active Directory e contas da Microsoft. A íris é implementada da mesma maneira que outras tecnologias do Windows Hello e alcança a segurança biométrica de 1/100K.

Consulte os [requisitos biométricos e as especificações do Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obter mais informações. Saiba mais sobre [o Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) e o Windows Hello para [Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### Como o tipo de conta afeta o comportamento de login?

Se você aplicar políticas para entrar, a política sempre é respeitada. Se nenhuma política de login for aplicada, estes são os comportamentos padrão para cada tipo de conta:

- **Azure AD:** solicita autenticação por padrão **** e configurável por Configurações para não solicitar mais autenticação.
- **Conta da Microsoft:** o comportamento de bloqueio é diferente, permitindo o desbloqueio automático, no entanto, a autenticação de entrada ainda é necessária na reinicialização.
- **Conta local:** sempre solicita autenticação na forma de uma senha, não configurável **em Configurações**

> [!NOTE]
> No momento, não há suporte para temporizadores de inatividade, o que significa que a política **AllowIdleReturnWithoutPassword** só é respeitada quando o dispositivo entra em modo de espera.

## Recursos adicionais

Leia muito mais sobre a proteção e a autenticação de identidade do usuário na documentação de segurança [e identidade do Windows 10.](https://docs.microsoft.com/windows/security/identity-protection/)

Saiba mais sobre como configurar a infraestrutura de identidade híbrida completa na [documentação de identidade híbrida do Azure.](https://docs.microsoft.com/azure/active-directory/hybrid/)
