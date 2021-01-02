---
title: Limitando o uso de senha
description: limitando o uso de senha para o holoLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, limitando o uso da senha, senha, senha do hololens, entrar, entrando, windows hello, hello, gerenciador de contas do windows, entrar no FIDO2, FIDO 2, WEBAUTHN, conta local, segurança do hololens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 417412e6b7854d9d985faa13bcf072b98e17f264
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11252968"
---
# Limitando o uso de senha

A maioria dos sistemas operacionais para computador da atualidade usa as credenciais do usuário como base para a segurança, tornando-os dependentes de senhas reutilizáveis criadas pelo usuário. Isso resultou em senhas como a causa mais comum de comprometimento de conta e violações de dados. Como exemplo disso, as senhas podem ser interceptadas na transmissão ou roubadas de um servidor (por meio de ataques de phishing ou de pulverização de senha) e ficarem comprometidas para obter acesso a uma conta de usuário.

Para melhorar a proteção de segurança e conta, o HoloLens 2 tem a capacidade de habilitar credenciais seguras, “sem senhas” e respaldadas por hardware (incluindo o Windows Hello) para entrar no dispositivo, oferecendo acesso contínuo em nuvem da Microsoft. 

## Entrada por outro dispositivo

O HoloLens 2 oferece opções de entrada de dispositivo remoto para contas corporativas do Azure Active Directory durante a configuração inicial do dispositivo e a entrada do usuário para reduzir a necessidade de digitar senhas complexas e minimizar a necessidade de senhas como credencial. Usuários e organizações que usam o cartão inteligente para autenticação têm dificuldade para usar essas credenciais em dispositivos como o HoloLens 2 e, muitas vezes, as organizações desenvolvem sistemas complexos e processos caros para solucionar o problema. Para solucionar esse problema, o Microsoft Azure Active Directory oferece duas opções de entrada sem senha no HoloLens 2. 

O primeiro método de autenticação conta com novos recursos do aplicativo Microsoft Authenticator para fornecer autenticação baseada em chave que habilita uma credencial de usuário vinculada a um dispositivo. Uma vez habilitados em um locatário pelo administrador, será exibida uma mensagem aos usuários durante a configuração do dispositivo HoloLens informando-os para tocar um número em seus aplicativos. Eles devem então usar o mesmo número correspondente ao número de seu aplicativo autenticador, escolher Aprovar, fornecer o PIN ou uma autenticação biométrica e completa para o HoloLens prosseguir a configuração. Isso é descrito com maiores detalhes em [entrada sem senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone).

O segundo é um fluxo de código do dispositivo que é intuitivo para os usuários e não exige nenhuma infraestrutura adicional.  Esse comportamento de entrada remota depende de outro dispositivo confiável que dê suporte ao mecanismo de autenticação preferencial da organização e, quando concluído, os tokens serão emitidos de volta para o HoloLens para concluir a entrada ou a configuração do dispositivo. As etapas neste fluxo são:

  1.    Será apresentado ao usuário percorrendo a configuração inicial do dispositivo ou dos fluxos de entrada no OOBE um link "Entrar a partir de outro dispositivo" para ele o tocar. Isso inicia uma sessão de entrada remota.
  2.    Em seguida, é mostrado ao usuário uma página de sondagem que contém um URI curto ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) que aponta para o ponto de extremidade de autenticação do dispositivo para o Serviço de Token Seguro (STS) do Azure AD. É apresentado também ao usuário um código único que é gerado com segurança na nuvem e tem um tempo de vida máximo de 15 minutos. Juntamente com a geração do código, o Microsoft Azure Active Directory também cria uma sessão criptografada durante a inicialização da entrada remota na etapa previamente solicitada e conjuntamente, o URI e o código são usados para aprovar a solicitação de entrada remota. 
  3.    Em seguida, o usuário navega para o URI de outro dispositivo e é solicitado a inserir o código exibido em seu dispositivo HoloLens 2. 
  4.    Após o usuário inserir o código, o Microsoft Azure Active Directory STS exibe uma página indicando o dispositivo HoloLens 2 do usuário que acionou a solicitação de entrada remota e a geração do código. Em seguida, o usuário é instruído a confirmar a prevenção de qualquer ataque de phishing. 
  5.    Se o usuário escolher dar continuidade na entrada no "aplicativo" exibido, o Microsoft Azure Active Directory STS solicitará as credenciais do usuário para. Em uma autenticação bem-sucedida, o Microsoft Azure Active Directory STS atualiza a sessão remota armazenada em cache como “aprovada", juntamente com um código de autorização.
  6.    Por fim, a página de sondagem no dispositivo HoloLens 2 do usuário recebe uma resposta "Autorizado" do Microsoft Azure Active Directory e prossegue para validar o código do usuário, seu associado código de autorização armazenado, e gera tokens OAuth conforme solicitado para concluir a configuração do dispositivo. O token de autenticação criado é válido por 1 hora e o token de atualização tem uma vida útil de 90 dias. 

A geração de código e algoritmos criptografados usados neste fluxo estão em conformidade com o FIPS. Os dispositivos HoloLens 2 utilizam o TPM para proteger chaves do dispositivo e criptografar tokens gerados após a autenticação do usuário usando chaves protegidas por hardware. Mais informações sobre segurança de token no HoloLens 2 são compartilhadas em [O que é um Token de Atualização Primário (PRT)](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token).

## Entrar no dispositivo com o Windows Hello

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) oferece opções sem senhas criadas diretamente no sistema operacional, permitindo que os usuários entrem no dispositivo usando a íris ou o PIN. O PIN está sempre disponível como uma credencial e é necessário para a configuração do dispositivo, enquanto o uso da íris é opcional e pode ser ignorada. Os usuários podem entrar em dispositivos HoloLens usando uma conta Microsoft ou [conta corporativa do Microsoft Azure Active Directory *sem* digitar uma senha](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless). Opções como essas oferecem aos usuários acesso rápido e seguro todas as suas experiências no Windows, aplicativos, dados, sites e serviços. A estratégia da Microsoft em relação a experiências sem senha é descrita aqui.

Quando uma credencial do Windows Hello é criada, ela estabelece uma relação de confiança com o provedor de identidade e cria um par de chaves assimétricas para a autenticação. Um gesto do Windows Hello (como a íris ou o PIN) fornece entropia para descriptografar uma chave privada apoiada pelo chip TPM (Trusted Platform Module) do dispositivo. Essa chave privada é então usada para assinar solicitações enviadas para um servidor de autenticação e após uma autenticação bem-sucedida, o usuário recebe acesso a seu email, imagens e outras configurações de conta. 

Para mais informações, veja os seguintes infográficos:

  ![Entrada do Windows Hello](images/security-hello-sign-in.png)
  
No gráfico apresentado acima, observe que nonce significa "número uma vez" e é uma chave numérica gerada aleatoriamente ou semi-aleatoriamente. Uma vez que a credencial biométrica do Windows Hello ou do PIN é configurada, ela nunca deixará o dispositivo para qual está provisionada. Mesmo que o PIN do usuário do Windows Hello seja roubado, como por meio de um ataque de phishing, ele fica [inútil sem o dispositivo físico do usuário](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password). 

Para segurança adicional, as credenciais do Windows Hello são protegidas pelo Trusted Platform Module (TPM) para que as credenciais sejam resistentes a adulterações e complementadas com proteções anti-hammering contra várias tentativas de entradas incorretas e proteção contra software mal intencionado para evitar a exposição. Para mais informações sobre o logon único (SSO), leia esta [visão geral dos métodos SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

A autenticação através da íris regressa ao PIN. Para configurar um novo PIN (um autentificador forte) no dispositivo, o usuário deve ter passado recentemente por [Autentificação Multifator (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) para concluir o processo.

## Logon único com o Gerenciador de Contas da Web 

O logon único (SSO) permite que usuários sem senha entrem ao dispositivo, utilizando a conta de usuário pessoal ou a conta corporativa ou a conta de estudante. O usuário é automaticamente autorizado com o SSO em todos os aplicativos e serviços integrados através dos [APIs do Gerenciador de Contas da Web](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

Uma vez que uma identidade foi acrescentada por meio de um aplicativo, com consentimento do usuário, ela se torna disponível para todos os aplicativos e serviços que usam a integração a nível do sistema. Isso reduz a carga na entrada do aplicativo significativamente e oferece aos usuários uma experiência com identificação contínua.

Para mais informações sobre como implementar APIs do Gerenciador de Contas da Web, acesse [APIs do Gerenciador de contas da Web](https://docs.microsoft.com/windows/uwp/security/web-account-manager).

  ![API de segurança](images/security-api-img.png)
  
Para pacotes de aplicativos com requisitos de autenticação especializados, a estrutura do Gerenciador de Contas da Web (WAM) é expansível para provedores de identidade personalizada. Os usuários podem baixar o provedor de identidade personalizada, empacotado como um aplicativo de Plataforma Universal do Windows (UWP) no Microsoft Store, para habilitar o SSO em outros aplicativos integrados a esse provedor de identidade. 

Para mais informações sobre como implementar provedores de identidade do WAM personalizados, veja [referência sobre API do Provedor de Identidade Personalizada do WAM](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## Entrada do Windows Hello e FIDO2 com WebAuthn

O HoloLens 2 pode utilizar credenciais de usuário sem senha (como as chaves de segurança do Windows Hello ou FIDO2) para entrar com segurança na web usando o Microsoft Edge e os sites que são compatíveis com o WebAuthn. O FIDO2 habilita as credenciais do usuário para tirar proveito dos dispositivos baseados em padrões para autenticação em serviços online.

> [!Note] 
> As especificações [WebAuthn](https://www.w3.org/TR/webauthn/) e FIDO2[CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) são implementadas nos serviços. Os metadados assinados e especificados pelo WebAuthn e FIDO2 fornecem informações, como a que informa se o usuário estava presente, e verifica a autenticação por meio do gesto local.

Assim como no Windows Hello, quando o usuário cria e registra uma credencial FIDO2, o dispositivo (HoloLens 2 ou a chave de segurança do FIDO2), gera uma chave privada e pública no dispositivo. A chave privada é armazenada com segurança no dispositivo e só pode ser usada depois de ser desbloqueada usando um gesto local como uma biometria ou um PIN. Quando a chave privada é armazenada, a chave pública é enviada para o sistema de conta Microsoft na nuvem e registrada com a conta de usuário associada.

Depois de entrar com uma conta do MSA e do Microsoft Azure Active Directory, o sistema envia um número gerado ou uma variável de dados para o dispositivo HoloLens 2 ou FIDO2. O HoloLens 2 ou dispositivo usa a chave privada para assinar a identificação. A identificação assinada e os metadados são enviados de volta para o sistema de conta Microsoft e verificados usando a chave pública.

Os dispositivos Windows Hello e FIDO2 implementam credenciais baseadas no dispositivo HoloLens, especificamente no enclave seguro interno do Trusted Platform Module. O enclave do TPM armazena a chave privada e requer uma biometria ou um PIN para desbloqueá-lo. Da mesma forma, uma chave de segurança FIDO2 é um pequeno dispositivo externo com uma enclave de segurança interna que armazena a chave privada e requer uma biometria ou um PIN para desbloqueá-lo.

As duas opções oferecem autenticação de dois fatores em uma etapa, exigindo tanto um dispositivo registrado como uma biometria ou PIN para entrar com êxito. Para mais informações, veja o gráfico de autenticação forte com segurança FIDO2, que segue:

  ![FIDO img](images/security-fido2-whfb.png)

O MSA e o Microsoft Azure Active Directory estão entre as primeiras partes confiantes para dar suporte à autenticação sem senha implementando WebAuthn. 

Para mais informações sobre como usar o WebAuthn com aplicativos e/ou SDKs, acesse [WebAuthn APIs para autenticação sem senha no Windows 10](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis).

## Contas locais

Uma única conta local pode ser configurada para implantações do modo offline. As contas locais não são ativadas por padrão e devem ser configuradas durante o provisionamento do dispositivo. Elas têm que entrar usando uma senha e não dar suporte a métodos de autenticação alternativos (como [Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) ou [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)). 

Mais detalhes sobre as contas de usuário do HoloLens podem ser encontrados em [Identidade do HoloLens](https://docs.microsoft.com/hololens/hololens-identity). 

Administradores de TI fazem os ajustes se o usuário tem permissão para usar uma conta MSA para autenticação de conexão não relacionada a email e serviços através de [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Para políticas de configuração de senha, políticas de suspensão e políticas de bloqueio de tela, veja [Bloqueio de Dispositivo](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock). 
