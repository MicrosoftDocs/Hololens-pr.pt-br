---
title: Configurar o HoloLens em um ambiente comercial
description: Saiba mais sobre a implantação e o gerenciamento do HoloLens em ambientes empresariais.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865560"
---
# Implantar o HoloLens em um ambiente comercial

Você pode implantar e configurar o HoloLens em escala em uma configuração comercial. Este artigo fornece instruções para a implantação de dispositivos HoloLens em um ambiente comercial. Este guia pressupõe familiaridade básica com o HoloLens. Siga o [Guia de introdução](hololens1-setup.md) para configurar o HoloLens pela primeira vez.

Este documento também pressupõe que o HoloLens foi avaliado por equipes de segurança como seguras para uso na rede da empresa.  
> [!Tip]
> Saiba mais sobre a [segurança do HoloLens](security-overview.md).
> Para a segurança do HoloLens (1ª gen), consulte [estas perguntas frequentes](hololens1-faq-security.md).

## Visão geral das etapas de implantação

1. [Determinar quais recursos você precisa](hololens-requirements.md#step-1-determine-what-you-need)
1. [Determinar quais são as licenças necessárias](hololens-licenses-requirements.md)
1. [Configurar sua rede para o HoloLens](hololens-commercial-infrastructure.md).
    1. Esta seção inclui requisitos de largura de banda, URL e portas que precisam ser permitidos no seu firewall; Orientação do Azure AD; Orientação sobre o gerenciamento de dispositivos móveis (MDM); Diretrizes de implantação/gerenciamento de aplicativos; e a orientação do certificado.
1. Adicionais [Configurar o HoloLens usando um pacote de provisionamento](hololens-provisioning.md)
1. [Registrar dispositivo](hololens-enroll-mdm.md)
1. [Configurar atualizações com base em anel para HoloLens](hololens-updates.md)
1. [Habilitar criptografia de dispositivo do Bitlocker para HoloLens](security-encryption-data-protection.md)

## Etapa 1. Determinar o que você precisa

Antes de implantar o HoloLens em seu ambiente, é importante determinar quais recursos, aplicativos e tipos de identidade são necessários primeiro. Também é importante garantir que sua equipe de segurança tenha aprovado pelo uso do HoloLens na rede da empresa. Consulte o [HoloLens2 Security](security-overview.md) para obter informações de segurança adicionais.

### Tipo de identidade

Determine o tipo de identidade que será usado para entrar no dispositivo.

1. **Contas locais:** Essa conta é local para o dispositivo (como uma conta de administrador local em um computador Windows). Isso permitirá que apenas 1 usuário conecte-se ao dispositivo.
2. **MSA:** Esta é uma conta pessoal (como o Outlook, o hotmail, o Gmail, o Yahoo, etc.) Isso permitirá que apenas 1 usuário conecte-se ao dispositivo.
3. **Contas do Azure Active Directory (Azure AD):** Esta é uma conta criada no Azure AD. Isso concede à sua empresa a capacidade de gerenciar o dispositivo HoloLens. Isso permitirá que vários usuários conectem-se ao pacote comercial do HoloLens da 1ª Gen/do dispositivo HoloLens 2.

Para obter informações mais detalhadas sobre os tipos de identidade, acesse nosso artigo de [identidade do HoloLens](hololens-identity.md) .

### Tipo de recursos

Seus requisitos de recursos determinarão o HoloLens que você precisa. Um recurso conhecido que vemos implantar em ambientes de cliente com frequência é o modo de quiosque. Uma lista de recursos chave do HoloLens e as edições do HoloLens que dão suporte a eles podem ser encontradas [aqui](hololens-commercial-features.md).

**O que é o modo de quiosque?**

O modo de quiosque é uma maneira de restringir os aplicativos aos quais um usuário tem acesso. Isso significa que os usuários só poderão acessar determinados aplicativos.

**Qual é o modo de quiosque necessário?**

Há dois tipos de modos de quiosque: aplicativo único e vários aplicativos. O modo de quiosque de aplicativo único permite que o usuário acesse apenas um aplicativo enquanto o modo de quiosque de vários aplicativos permite que os usuários acessem vários aplicativos especificados. Para determinar qual é o modo de quiosque correto para sua empresa, as duas perguntas a seguir precisam ser respondidas:

1. **Os diferentes usuários exigem experiências/restrições diferentes?** Considere o exemplo a seguir: o usuário A é um engenheiro de serviços de campo que só precisa de acesso à assistência remota. O usuário B é um estagiário que só precisa de acesso a guias.
    1. Em caso afirmativo, você precisará do seguinte:
        1. Contas do Azure AD como o método de inscrição no dispositivo.
        1. Modo **de quiosque de vários aplicativos** .
    1. Se não, continue com a pergunta dois
1. **Você precisa de experiência com vários aplicativos?**
    1. Se sim, o quiosque **de vários aplicativos** é o modo necessário
    1. Se a sua resposta para as perguntas 1 e 2 não for o modo de quiosque de **aplicativo único** pode ser usado

**Como configurar o modo de quiosque:**

Há duas maneiras principais ([pacotes de provisionamento](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) para implantar o modo de quiosque para o HoloLens. Essas opções serão discutidas mais tarde no documento; no entanto, você pode usar os links acima para saltar para as respectivas seções neste documento.

### Aplicativos e cenários específicos do aplicativo

A maioria das etapas encontradas neste documento também será aplicada aos seguintes aplicativos:

| Aplicativo | Cenários específicos do aplicativo |
| --- | --- |
| Assistência remota | [Comunicação entre os locatários](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| Guias  | *Em breve* |
|Aplicativos personalizados | *Em breve* |

### Determinar o método de registro

1. Registro em massa com um token de segurança em um pacote de provisionamento.  
  Prós: esta é a abordagem mais automatizada \
  Desvantagens: retira a configuração inicial do lado do servidor  
1. Inscrição automática na entrada do usuário.  
  Prós: abordagem mais fácil  
  Contras: os usuários precisarão concluir a configuração após a aplicação do pacote de provisionamento
1. _não recomendado_ -Registre a pós-instalação manualmente.  
  Prós: possível se inscrever após a configuração  
  Desvantagens: a maioria dos dispositivos e a abordagem manual não são gerenciáveis de maneira centralizada até que sejam manualmente registrados.

  Mais informações podem ser encontradas [aqui](hololens-enroll-mdm.md)

### Determinar se você precisa criar um pacote de provisionamento

Há dois métodos para configurar um dispositivo HoloLens (pacotes de provisionamento e MDMs). Sugerimos usar o MDM para configurar seu dispositivo HoloLens. No entanto, há alguns cenários em que usar um pacote de provisionamento é a melhor opção:

1. Você deseja configurar o HoloLens para ignorar a experiência inicial (OOBE)
1. Você está tendo problemas para implantar o certificado em uma rede complexa. Na maioria das vezes, você pode implantar certificados usando o MDM (mesmo em ambientes complexos). No entanto, alguns cenários exigem que os certificados sejam implantados por meio do pacote de provisionamento.

Algumas das configurações do HoloLens que é possível aplicar em um pacote de provisionamento:

- Aplicar certificados ao dispositivo
- Configurar uma conexão Wi-Fi
- Pré-configurar as caixas de perguntas, como idioma e localidade
- (HoloLens 2) Registrar-se em massa no gerenciamento de dispositivo móvel 
- (HoloLens v1) Aplicar chave para habilitar o Holographic for Business do Windows

Se você decidir usar pacotes de provisionamento, siga [este guia](hololens-provisioning.md).

## Obter suporte

Obtenha suporte por meio do site de suporte da Microsoft.

[Arquivar uma solicitação de suporte](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
