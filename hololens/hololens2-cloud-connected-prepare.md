---
title: Guia de implantação – implantação do HoloLens 2 conectado à nuvem em escala com assistência remota-preparação
description: Como preparar-se para registrar dispositivos HoloLens em uma rede conectada na nuvem
keywords: HoloLens, gerenciamento, nuvem conectada, assistência remota, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a4e99740d985a709683595cd5afef76094faaf76
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253048"
---
# Preparar-guia conectado à nuvem

No final deste artigo, você terá configurado o Azure AD, o MDM e compreender mais sobre o uso de contas e requisitos de rede do Azure AD. Esta seção do guia ajudará você e sua organização a se preparar para implantar o HoloLens 2 na nuvem e usar a assistência remota do Dynamics 365. Ele passará pela importância de cada parte da sua infraestrutura, além de fornecer links para guias para ajudá-lo a configurar esses pedaços conforme necessário.

## Fundamentos da infraestrutura

Para cenários de implantação pessoal e empresarial, um sistema MDM é a infraestrutura essencial necessária para implantar e gerenciar dispositivos do Windows 10 holográfico. Uma assinatura do Azure AD Premium é recomendada como provedor de identidade e necessária para dar suporte a determinados recursos.

### Azure Active Directory

O Azure AD é um serviço de diretório baseado na nuvem que fornece gerenciamento de acesso e identidade. Organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: grátis, Premium P1 e Premium P2 (consulte [edições do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions).) Todas as edições dão suporte ao registro de dispositivos do Azure AD, mas a P1 P1 é necessária para habilitar o registro automático do MDM que usaremos neste guia mais tarde.

> [!IMPORTANT]
> É essencial ter um Azure Active Directory como dispositivos HoloLens não é compatível com o ingresso no AD local. Se você não&#39;já tiver um Azure Active Directory configurado, siga as instruções neste link para começar e [criar um novo locatário no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## Gerenciamento de identidades

Os funcionários podem usar apenas uma conta para inicializar um dispositivo para que&#39;s obrigações de que a sua organização controla qual conta está ativada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento.

Neste guia, escolhemos isso para a [identidade](https://docs.microsoft.com/hololens/hololens-identity) usada, usaremos contas do Azure ad ou contas do Azure Active Directory. Há vários benefícios nas contas do Azure AD que gostaríamos de usar, como:

- Os funcionários usam a conta do Azure AD para registrar o dispositivo no Azure AD e registrá-lo automaticamente com a organização&#39;s MDM solução (Azure AD + MDM – requer o Azure AD Premium).
- As contas do Azure AD dão suporte ao [logon único](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on). Quando um usuário entra na assistência remota, sua identidade do usuário assinado do Azure AD será reconhecida e o usuário será conectado ao aplicativo para obter uma experiência simplificada.
- As contas do Azure AD têm [Opções de autenticação](https://docs.microsoft.com/hololens/hololens-identity) adicionais por meio [do Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Além disso, os usuários de login da íris podem entrar em outro dispositivo ou usar chaves de segurança FIDO.

### Gerenciamento de Dispositivo Móvel

O Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), parte da Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos conectados ao seu locatário. Assim como o Office 365, o Intune usa o Azure AD para gerenciamento de identidades, portanto, os funcionários usam as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. O Intune também dá suporte a dispositivos que executam outros sistemas operacionais, como iOS e Android, para fornecer uma solução completa do MDM. Para os fins deste guia,&#39;mos se concentrar em usar o Intune para habilitar uma implantação de nuvem em escala com o HoloLens 2.

> [!IMPORTANT]
> É essencial ter o gerenciamento de dispositivos móveis. Se você não&#39;a configuração já está configurada siga este guia e [comece a usar o Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os provedores de MDM que dão suporte ao Windows 10 holográfico atualmente incluem: relógio para, MobileIron e outros. A maioria dos fornecedores de MDM líderes do setor já dão suporte à integração com o Azure AD. Você pode encontrar os fornecedores de MDM que dão suporte ao Azure AD em [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Rede

Nesta configuração, antecipamos os dispositivos do HoloLens 2 que se conectam à Internet de qualquer rede Wi-Fi aberta disponível. Como um usuário pode precisar alterar a conexão de rede com base no local, ele deve saber como [conectar dispositivos HoloLens à rede Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Para assistência remota do Dynamics 365, há uma variedade de condições de rede, incluindo largura de banda, latência, tremulação e perda de pacote, que podem afetar sua experiência de chamadas com vídeo. Embora as chamadas de áudio e vídeo possam ser possíveis em ambientes com largura de banda reduzida, você pode enfrentar a degradação do recurso. Ao usar o assistência remota do Dynamics 365 no HoloLens aqui estão os requisitos de rede que devem ser lembrados:

**Mínimo** : 1,5 Mbps up/down são necessários para chamadas com vídeo de qualidade HD ponto a ponto com resolução de HD de 1080p a 30 fps.

**Ideal:** Para chamadas com vídeo de qualidade HD ponto a ponto com resolução de HD de 1080p, 4-5 Mbps para cima/baixo devem ser esperadas.

Mais informações:

- [Requisitos de rede](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendações de otimização de rede](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Opcional: conectar seu HoloLens à VPN

Os dispositivos conectados a este guia serão conectados à rede por meio da rede de nuvem externa. Pode ser que você acesse os recursos da empresa que&#39;precisará para conectar seus dispositivos via VPN. Há várias maneiras diferentes de conectar seus dispositivos à VPN, tanto quando o usuário final pode se conectar via usar a interface do usuário do dispositivo ou os dispositivos podem ser gerenciados e receber o perfil da VPN de um PPKG ou MDM. Como configurar a VPN ganha&#39;t ser abordada neste artigo, portanto, se você&#39;d como saber mais sobre os diferentes protocolos VPN ou maneiras de gerenciar a VPN, acesse [esses guias para obter informações sobre o HoloLens e a VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem-configurar](hololens2-cloud-connected-configure.md)
