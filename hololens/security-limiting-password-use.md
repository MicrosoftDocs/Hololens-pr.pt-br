---
title: Limitando o uso de senha
description: como limitar o uso de senha no HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, limiting password use, password, hololens password, sign-in, signing in, windows hello, hello, windows account manager, FIDO2 sign in, FIDO 2, WEBAUTHN, local account, hololens security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190456"
---
# <a name="limiting-password-use"></a>Limitando o uso de senha

Atualmente, a maioria dos sistemas de computadores usa as credenciais do usuário como base para a segurança, tornando-os dependentes de senhas reutilizáveis criadas pelo usuário. Como resultado, as senhas também passaram a ser a causa mais comum de comprometimento de conta e violações de dados. Um exemplo disso é que as senhas podem ser interceptadas na transmissão ou roubadas de um servidor (por meio de ataques de phishing ou de pulverização de senha) e ficarem comprometidas para obter acesso a uma conta de usuário.

Para aprimorar a segurança e a proteção da conta, o HoloLens 2 tem a capacidade de habilitar credenciais fortes “sem senhas” e apoiados por hardware (incluindo o Windows Hello) para a entrada no dispositivo, oferecendo acesso contínuo à nuvem da Microsoft.

## <a name="signing-in-from-another-device"></a>Entrar de outro dispositivo

O HoloLens 2 oferece opções de entrada de dispositivo remoto para contas corporativas do Azure Active Directory durante a configuração inicial do dispositivo e a entrada do usuário a fim de reduzir a necessidade de digitar senhas complexas e minimizar a necessidade de senhas como credenciais. Os usuários e as organizações que usam cartões inteligentes para autenticação têm dificuldade para usar essas credenciais em dispositivos como o HoloLens 2 e, muitas vezes, as organizações desenvolvem sistemas complexos e processos caros para solucionar o problema. Para resolver esse problema, o Azure AD oferece duas opções de entrada sem senha no HoloLens 2.

O primeiro método de autenticação depende das novas funcionalidades do aplicativo Microsoft Authenticator para fornecer autenticação baseada em chave que habilita uma credencial de usuário vinculada a um dispositivo. Depois de habilitados em um locatário pelo administrador, os usuários verão uma mensagem durante a configuração do dispositivo HoloLens instruindo-os a tocar em um número no aplicativo. Em seguida, eles precisarão usar o mesmo número correspondente ao número do aplicativo autenticador, escolher Aprovar, fornecer o PIN ou uma biometria e concluir a autenticação para prosseguir com a configuração do HoloLens. Isso será descrito mais detalhadamente em [Entrada sem senha](/azure/active-directory/authentication/howto-authentication-passwordless-phone).

O segundo é um fluxo de código do dispositivo que é intuitivo para os usuários e não exige nenhuma infraestrutura adicional.  Esse comportamento de entrada remota depende de outro dispositivo confiável que dê suporte ao mecanismo de autenticação preferencial da organização e, quando concluído, os tokens serão emitidos novamente para o HoloLens para concluir a entrada ou a configuração do dispositivo. As etapas deste fluxo são:

  1. O usuário que segue o passo a passo da configuração inicial do dispositivo ou dos fluxos de entrada no OOBE vê um link “Entrar por meio de outro dispositivo” e toca nele. Isso inicia uma sessão de entrada remota.
  1. Em seguida, o usuário vê uma página de sondagem, que contém um URI curto ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) que aponta para o ponto de extremidade de autenticação do dispositivo do STS (Serviço de Token de Segurança) do Azure AD. O usuário também vê um código único que é gerado com segurança na nuvem e tem um tempo de vida máximo de 15 minutos. Juntamente com a geração do código, o Azure AD também cria uma sessão criptografada durante a inicialização da solicitação de entrada remota na etapa anterior e, em conjunto, o URI e o código são usados para aprovar a solicitação de entrada remota.
  1. Em seguida, o usuário navega até o URI por meio de outro dispositivo e é instruído a inserir o código exibido no dispositivo HoloLens 2.
  1. Depois que o usuário insere o código, o STS do Azure AD exibe uma página indicando o dispositivo HoloLens 2 do usuário que disparou a solicitação de entrada remota e solicitou a geração do código. Em seguida, o usuário é instruído a confirmar a seleção para prevenir ataques de phishing.
  1. Se o usuário optar por dar continuidade na entrada no 'aplicativo' exibido, o STS do Azure AD solicitará as credenciais ao usuário. Em uma autenticação bem-sucedida, o STS do Azure AD atualiza a sessão remota armazenada em cache como 'aprovada', juntamente com um código de autorização.
  1. Por fim, a página de sondagem no dispositivo HoloLens 2 do usuário recebe uma resposta 'Autorizado' do Azure AD e prossegue para validar o código do usuário, o código de autorização associado armazenado e gera tokens OAuth, conforme solicitado, para concluir a configuração do dispositivo. O token de autenticação criado é válido por 1 hora e o token de atualização tem um tempo de vida de 90 dias.

A geração de código e os algoritmos criptografados usados neste fluxo estão em conformidade com o FIPS. Os dispositivos HoloLens 2 utilizam o TPM para proteger as chaves do dispositivo e criptografar os tokens gerados após a autenticação do usuário usando chaves protegidas por hardware. Mais informações sobre a segurança de token no HoloLens 2 são compartilhadas em [O que é um PRT (Token de Atualização Principal)](/azure/active-directory/devices/concept-primary-refresh-token).

## <a name="device-sign-in-with-windows-hello"></a>Entrada no dispositivo com o Windows Hello

O [Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) oferece opções sem senhas inseridas diretamente no sistema operacional, permitindo que os usuários entrem no dispositivo usando a íris ou o PIN. O PIN está sempre disponível como uma credencial e é necessário para a configuração do dispositivo, enquanto o uso da íris é opcional e pode ser ignorado. Os usuários podem entrar nos dispositivos HoloLens usando as respectivas contas Microsoft ou as [contas corporativas do Azure Active Directory *sem* inserir uma senha](/azure/active-directory/authentication/concept-authentication-passwordless). Opções como essas oferecem aos usuários acesso rápido e protegido em todas as experiências no Windows, em aplicativos, em dados, em sites e em serviços. A estratégia da Microsoft em relação às experiências sem senha é descrita aqui.

Quando uma credencial do Windows Hello é criada, ela estabelece uma relação de confiança com um provedor de identidade e cria um par de chaves assimétricas para a autenticação. Um gesto do Windows Hello (como a íris ou o PIN) fornece entropia para descriptografar uma chave privada apoiada pelo chip do TPM (Trusted Platform Module) do dispositivo. Em seguida, essa chave privada é usada para assinar solicitações enviadas para um servidor de autenticação e após uma autenticação bem-sucedida, o usuário recebe acesso ao email, as imagens e às outras configurações da conta.

Para obter mais informações, confira os seguintes infográficos:

  ![Entrada do Windows Hello.](images/security-hello-sign-in.png)
  
No gráfico apresentado acima, observe que nonce significa “número uma vez” e é um número gerado aleatória ou semialeatoriamente. Depois que a credencial biométrica ou do PIN do Windows Hello é configurada, ela nunca deixa o dispositivo no qual está provisionada. Mesmo que o PIN do Windows Hello do usuário seja roubado, como por meio de um ataque de phishing, ele [é inútil sem o dispositivo físico do usuário](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password).

Para segurança adicional, as credenciais do Windows Hello são protegidas pelo TPM (Trusted Platform Module), de modo que as credenciais sejam resistentes a adulterações e complementadas com proteções anti-hammering contra várias tentativas de entradas incorretas e proteção contra software mal-intencionado para evitar a exposição. Para obter mais informações sobre o SSO (logon único), leia esta [visão geral dos métodos de SSO](/azure/active-directory/manage-apps/what-is-single-sign-on).

A autenticação por meio da íris retorna ao PIN. Para configurar um novo PIN (um autentificador forte) no dispositivo, o usuário precisa ter passado recentemente pela [MFA (autenticação multifator)](/azure/active-directory/authentication/concept-mfa-howitworks) para concluir o processo.

## <a name="single-sign-on-with-web-account-manager"></a>Logon único com o Gerenciador de Contas da Web

O SSO (logon único) permite que os usuários sem senha entrem no dispositivo, utilizando a conta pessoal do usuário ou a conta corporativa ou de estudante. O usuário é autorizado automaticamente com o SSO em todos os aplicativos e serviços integrados por meio das [APIs do Gerenciador de Contas da Web](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

Depois que uma identidade for adicionada por meio de um aplicativo, com o consentimento do usuário, ela poderá ficar disponível para todos os aplicativos e serviços que usam a integração no nível do sistema. Isso reduz significativamente a carga de entrada no aplicativo e fornece aos usuários uma experiência de identidade perfeita.

Para obter mais informações sobre como implementar as APIs do Gerenciador de Contas da Web, acesse [Como implementar as APIs do Gerenciador de Contas da Web](/windows/uwp/security/web-account-manager).

  ![API de Segurança.](images/security-api-img.png)
  
Para os pacotes de aplicativos com requisitos de autenticação especializados, a estrutura do WAM (Gerenciador de Contas da Web) é extensível para provedores de identidade personalizados. Os usuários podem baixar o provedor de identidade personalizado, empacotado como um aplicativo UWP (Plataforma Universal do Windows) por meio da Microsoft Store, para habilitar o SSO em outros aplicativos integrados a esse provedor de identidade.

Para obter mais informações sobre como implementar provedores de identidade personalizados do WAM, confira [Referência de API do provedor de identidade personalizado do WAM](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Entrada no Windows Hello e no FIDO2 com o WebAuthn

O HoloLens 2 pode utilizar credenciais do usuário sem senha (como as chaves de segurança do Windows Hello ou do FIDO2) para entrar com segurança na Web usando o Microsoft Edge e os sites que dão suporte ao WebAuthn. O FIDO2 habilita as credenciais do usuário a fim de aproveitar os dispositivos baseados em padrões para autenticação em serviços online.

> [!Note]
> As especificações do [WebAuthn](https://www.w3.org/TR/webauthn/) e do [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) do FIDO2 são implementadas em serviços. Os metadados assinados e especificados pelo WebAuthn e pelo FIDO2 fornecem informações, como a indicação de presença do usuário, e verifica a autenticação por meio do gesto local.

Assim como ocorre com o Windows Hello, quando o usuário cria e registra uma credencial do FIDO2, o dispositivo (HoloLens 2 ou a chave de segurança FIDO2) gera uma chave privada e pública no dispositivo. A chave privada é armazenada com segurança no dispositivo e só pode ser usada depois de ser desbloqueada por meio de um gesto local como uma biometria ou um PIN. Quando a chave privada é armazenada, a chave pública é enviada para o sistema da conta Microsoft na nuvem e é registrada com a conta de usuário associada.

Após a entrada com uma conta MSA e do Azure AD, o sistema envia um número gerado ou uma variável de dados para o dispositivo HoloLens 2 ou FIDO2. O HoloLens 2 ou o dispositivo usa a chave privada para assinar a identificação. A identificação assinada e os metadados são enviados novamente para o sistema da conta Microsoft e verificados por meio da chave pública.

Os dispositivos Windows Hello e FIDO2 implementam credenciais baseadas no dispositivo HoloLens, especificamente no enclave seguro interno do Trusted Platform Module. O enclave do TPM armazena a chave privada e exige uma biometria ou um PIN para desbloqueá-la. Da mesma forma, uma chave de segurança FIDO2 é um pequeno dispositivo externo com um enclave seguro interno que armazena a chave privada e exige uma biometria ou um PIN para desbloqueá-la.

As duas opções oferecem a autenticação de dois fatores em uma só etapa, exigindo tanto um dispositivo registrado quando uma biometria ou um PIN para a entrada bem-sucedida. Para obter mais informações, confira a autenticação forte com o elemento gráfico e o processo da chave de segurança FIDO2 a seguir.

### <a name="strong-authentication-with-fido2-security-key"></a>Autenticação forte com a chave de segurança FIDO2

  ![Imagem do FIDO.](images/security-fido2-whfb-smaller.png)

1. O usuário conecta a chave de segurança FIDO2 ao HoloLens 2
1. O Windows detecta a chave de segurança FIDO2
1. O HoloLens envia a solicitação de autenticação
1. O Azure AD envia o nonce novamente
1. O usuário conclui o gesto para desbloquear a chave privada armazenada no enclave seguro da chave de segurança
1. A chave de segurança FIDO2 assina o nonce com a chave privada
1. A solicitação de token PRT com o nonce assinado é enviada para o Azure AD
1. O Azure AD verifica a chave FIDO
1. O Azure AD retorna o PRT e o TGT para permitir o acesso aos recursos

A MSA e o Azure AD estão entre as primeiras partes confiáveis a dar suporte à autenticação sem senha, implementando o WebAuthn.

Para obter mais informações sobre como usar o WebAuthn com aplicativos e/ou SDKs, acesse [APIs do WebAuthn para autenticação sem senha no Windows 10](/windows/security/identity-protection/hello-for-business/webauthnapis).

O HoloLens 2 dá suporte aos dispositivos de segurança FIDO2 implementados de acordo com a especificação e que atendem aos requisitos listados em [Entrada sem senha do Azure Active Directory – Chaves de segurança FIDO2](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys).

## <a name="local-accounts"></a>Contas locais

Uma conta local individual pode ser configurada para implantações do modo offline. As contas locais não estão habilitadas por padrão e precisam ser configuradas durante o provisionamento de dispositivos. Elas precisam se conectar por meio de uma senha e não dão suporte a métodos de autenticação alternativos (como o [Windows Hello para Empresas](/windows/security/identity-protection/hello-for-business/hello-overview) ou o [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)).

Encontre mais detalhes sobre as contas de usuário do HoloLens em [Identidade do HoloLens](hololens-identity.md).

Os administradores de TI fazem ajustes a fim de indicar se o usuário tem permissão para usar uma conta MSA para autenticação de conexão não relacionada a email e serviços por meio de [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Para obter as políticas de configuração de senha, as políticas de suspensão e as políticas de bloqueio de tela, confira [Bloqueio de dispositivo](/windows/client-management/mdm/policy-csp-devicelock).
