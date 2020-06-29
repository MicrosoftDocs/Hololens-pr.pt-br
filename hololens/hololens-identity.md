---
title: Gerenciar a identidade do usuário e entrar no HoloLens
description: Gerenciar identidade do usuário, segurança e entrada para o HoloLens.
keywords: HoloLens, usuário, conta, AAD, ADFS, conta da Microsoft, MSA, credenciais, referência
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 1/6/2020
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
ms.openlocfilehash: d21f6be272d0b731b881b69576ae0631aec604ea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827741"
---
# Gerenciar a identidade do usuário e entrar no HoloLens

> [!NOTE]
> Este artigo é uma referência técnica para profissionais de ti e entusiastas técnicos. Se você estiver procurando instruções de configuração do HoloLens, leia "[configurando seu hololens (1ª gen)](hololens1-start.md)" ou "[configurando seu hololens 2](hololens2-start.md)".

Como outros dispositivos Windows, o HoloLens sempre funciona em um contexto de usuário. Sempre existe uma identidade de usuário. O HoloLens trata a identidade praticamente da mesma maneira que outros dispositivos Windows 10. Este artigo é uma referência profunda de identidade no HoloLens e concentra-se em como o HoloLens difere de outros dispositivos Windows 10.

O HoloLens tem suporte para vários tipos de identidades de usuário. Você pode usar uma ou mais contas de usuário para se conectar. Aqui está uma visão geral dos tipos de identidade e opções de autenticação no HoloLens:

| Tipo de identidade | Contas por dispositivo | Opções de autenticação |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Provedor de credenciais da Web do Azure</li><li>Aplicativo Azure Authenticator</li><li>Biometria (íris) &ndash; HoloLens 2 somente</li><li>PIN &ndash; opcional para hololens (1ª gen), obrigatório para hololens 2</li><li>Senha</li></ul> |
| [Conta da Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | um | <ul><li>Biometria (íris) &ndash; HoloLens 2 somente</li><li>PIN &ndash; opcional para hololens (1ª gen), obrigatório para hololens 2</li><li>Senha</li></ul> |
| [Conta local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | um | Senha |

As contas conectadas na nuvem (AAD e MSA) oferecem mais recursos porque podem usar os serviços do Azure.  

## Configurando usuários

A maneira mais comum de configurar um novo usuário é durante a experiência de uso inicial (OOBE) do HoloLens. Durante a instalação, o HoloLens solicita que um usuário entre usando a conta que deseja usar no dispositivo. Essa conta pode ser uma conta da Microsoft para consumidores ou uma conta empresarial que tenha sido configurada no Azure. Confira configurando seu [hololens (1ª gen)](hololens1-start.md) ou [HoloLens 2](hololens2-start.md).

Assim como o Windows em outros dispositivos, entrar durante a instalação cria um perfil de usuário no dispositivo. O perfil de usuário armazena aplicativos e dados. A mesma conta também fornece logon único para aplicativos como o Edge ou o Skype usando as APIs do Gerenciador de contas do Windows.  

Se você usar uma conta corporativa ou organizacional para entrar no HoloLens, o HoloLens será registrado na infraestrutura de ti da organização. Esse registro permite que seu administrador de ti configure o MDM (gerenciamento de dispositivo móvel) para enviar políticas de grupo ao seu HoloLens.

Por padrão, como para outros dispositivos Windows 10, você terá que entrar novamente quando o HoloLens for reiniciado ou retomado do modo de espera. Você pode usar o aplicativo configurações para alterar esse comportamento ou o comportamento pode ser controlado pela política de grupo.

### Contas vinculadas

Como na versão da área de trabalho do Windows, você pode vincular credenciais de conta da Web adicionais à sua conta do HoloLens. Tal vinculação facilita o acesso a recursos nos aplicativos ou em aplicativos (como a loja) ou para combinar o acesso a recursos pessoais e de trabalho. Depois de conectar uma conta ao dispositivo, você pode conceder permissão para usar o dispositivo para aplicativos, para que você não precise entrar em cada aplicativo individualmente.

A vinculação de contas não separa os dados do usuário criados no dispositivo, como imagens ou downloads.  

### Configurando o suporte a vários usuários (somente AAD)

> [!NOTE]
> **HoloLens (1ª gen)** começou a oferecer suporte a vários usuários do AAD na [atualização de abril de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) do Windows como parte do [Windows holográfico for Business](hololens-upgrade-enterprise.md).

O HoloLens dá suporte a vários usuários do mesmo locatário AAD. Para usar esse recurso, você deve usar uma conta que pertence à sua organização para configurar o dispositivo. Subsequentemente, outros usuários do mesmo locatário podem entrar no dispositivo na tela de entrada ou tocando no bloco do usuário no painel Iniciar. Somente um usuário pode ser conectado por vez. Quando um usuário entra, o HoloLens desconecta o usuário anterior.  

Todos os usuários podem usar os aplicativos instalados no dispositivo. No entanto, cada usuário tem seus próprios dados e preferências de aplicativo. Remover um aplicativo do dispositivo remove-o para todos os usuários.  

## Removendo usuários

Você pode remover um usuário do dispositivo acessando contas **configurações**  >  **Accounts**  >  **outras pessoas**. Essa ação também recupera espaço removendo todos os dados do aplicativo daquele usuário do dispositivo.  

## Usar o logon único em um aplicativo

Como um desenvolvedor de aplicativos, você pode aproveitar identidades vinculadas no HoloLens usando as [APIs do Gerenciador de contas do Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core), da mesma forma que faria em outros dispositivos Windows. Alguns exemplos de código para essas APIs estão disponíveis [aqui](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Todas as interrupções de conta que podem ocorrer, como solicitação de consentimento do usuário para informações da conta, autenticação de dois fatores e assim por diante, devem ser manipuladas quando o aplicativo solicita um token de autenticação.

Se seu aplicativo exige um tipo de conta específico que não foi vinculado anteriormente, seu aplicativo pode solicitar que o sistema solicite ao usuário que ele adicione um. Esta solicitação dispara o painel de configurações de conta para ser iniciado como um filho modal do seu aplicativo. Para aplicativos 2D, essa janela é renderizada diretamente sobre o centro do seu aplicativo. Para aplicativos Unity, essa solicitação leva o usuário ao seu aplicativo do holográfico para renderizar a janela filho. Para obter informações sobre como personalizar os comandos e ações nesse painel, consulte [classe WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Empresa e outras autenticações

Se seu aplicativo usa outros tipos de autenticação, como NTLM, básico ou Kerberos, você pode usar a [interface do](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) usuário de credenciais do Windows para coletar, processar e armazenar as credenciais do usuário. A experiência do usuário para coletar essas credenciais é muito parecida com outras interrupções de conta voltada à nuvem e aparece como um aplicativo filho sobre o seu aplicativo 2D ou suspende brevemente um aplicativo Unity para mostrar a interface do usuário.

## APIs preteridas

Uma maneira na qual o desenvolvimento do HoloLens é diferente do desenvolvimento para área de trabalho é que a API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) não é totalmente suportada. Embora a API retorne um token se a conta principal estiver em boas condições, as interrupções como aquelas descritas neste artigo não exibirão qualquer interface do usuário para o usuário e falharão na autenticação correta da conta.

## Perguntas frequentes

### O Windows Hello para empresas é compatível com o HoloLens (1ª gen)?

O Windows Hello para empresas (que suporta o uso de um PIN para entrar) é compatível com o HoloLens (1ª geração). Para permitir a entrada com PIN do Windows Hello para empresas no HoloLens:

1. O dispositivo HoloLens deve ser [gerenciado pelo MDM](hololens-enroll-mdm.md).
1. Você deve habilitar o Windows Hello para empresas para o dispositivo. ([Veja instruções para o Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. No HoloLens, o usuário pode usar as opções de entrada de **configurações**  >  **Sign-in Options**  >  **Adicionar PIN** para configurar um PIN.

> [!NOTE]
> Os usuários que se conectarem usando uma conta da Microsoft também poderão configurar um PIN nas opções de entrada de **configurações**  >  **Sign-in Options**  >  **Adicionar PIN**. Esse pino está associado ao [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), em vez do [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### Como a autenticação biométrica da íris é implementada no HoloLens 2?

O HoloLens 2 dá suporte à autenticação íris. A íris se baseia na tecnologia Windows Hello e é compatível com o uso do Azure Active Directory e das contas da Microsoft. A íris é implementada da mesma maneira que outras tecnologias do Windows Hello e alcança a segurança biométrica longe de 1/100K.

Você pode saber mais sobre requisitos e especificações biométricos do Windows Hello [aqui](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements). Saiba mais sobre o [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) e o [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### Como o tipo de conta afeta o comportamento de entrada?

Se você aplicar políticas para entrar, a política sempre é respeitada. Se nenhuma política para entrada for aplicada, estes são os comportamentos padrão para cada tipo de conta:

- **Azure ad**: solicita autenticação por padrão e configurável por **configurações** não solicita mais autenticação.
- **Conta da Microsoft: o**comportamento de cadeado é diferente, permitindo o desbloqueio automático, mas a autenticação de entrada ainda é necessária na reinicialização.
- **Conta local**: sempre pede autenticação na forma de uma senha, não é configurável em **configurações**

> [!NOTE]
> No momento, não há suporte para timers de inatividade, o que significa que a política **AllowIdleReturnWithoutPassword** só é respeitada quando o dispositivo entra em standby.

## Recursos adicionais

Leia muito mais sobre a proteção e a autenticação de identidade do usuário na [documentação de identidade e segurança do Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

Saiba mais sobre como configurar a infraestrutura de identidade híbrida de forma completa a [documentação de identidade híbrida do Azure](https://docs.microsoft.com/azure/active-directory/hybrid/).
