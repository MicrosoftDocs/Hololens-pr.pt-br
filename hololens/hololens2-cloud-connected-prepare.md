---
title: Guia de Implantação – implantação do HoloLens 2 conectada à nuvem em escala com Assistência Remota - Preparar
description: Saiba como se preparar para registrar dispositivos HoloLens em uma rede conectada à nuvem usando o Azure Active Directory e o gerenciamento de identidades.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283862"
---
# Preparar - Guia conectado à nuvem

No final deste artigo, você terá definido o Azure AD, o MDM e entendido mais sobre como usar as contas do Azure AD e os requisitos de rede. Esta seção do guia ajudará você e sua organização a se prepararem para implantar o HoloLens 2 na nuvem e usar a Assistência Remota do Dynamics 365. Ele vai além da importância de cada parte da sua infraestrutura, além de fornecer links para guias para ajudá-lo a configurar essas partes conforme necessário.

## Infrastructure Essentials

Para cenários de implantação pessoal e corporativa, um sistema MDM é a infraestrutura essencial necessária para implantar e gerenciar dispositivos Windows 10 Holographic. Uma assinatura do Azure AD Premium é recomendada como provedor de identidade e necessária para dar suporte a determinados recursos.

### Azure Active Directory

O Azure AD é um serviço de diretório baseado na nuvem que fornece gerenciamento de acesso e identidade. As organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: Free, Premium P1 e Premium P2 (confira as edições do [Azure Active Directory.](https://azure.microsoft.com/documentation/articles/active-directory-editions) Todas as edições são suportadas pelo registro de dispositivos do Azure AD, mas o Premium P1 é necessário para habilitar o registro automático do MDM, que será usado neste guia posteriormente.

> [!IMPORTANT]
> É essencial ter um Azure Active Directory, pois os dispositivos do HoloLens não são compatíveis com o AD local. Se você ainda&#39;configurar um Azure Active Directory, siga as instruções neste link para começar e crie um novo locatário no [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## Gerenciamento de Identidades

Os funcionários podem usar apenas uma conta para inicializar um dispositivo para que&#39;imperativo que sua organização controle qual conta é habilitada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento.

Neste guia, optamos [](https://docs.microsoft.com/hololens/hololens-identity) por usar as contas do Azure AD ou as contas do Azure Active Directory para a Identidade usada. Há vários benefícios para contas do Azure AD que queremos usar, como:

- Os funcionários usam a conta do Azure AD para registrar o dispositivo no Azure A&#39;D e registrá-lo automaticamente na solução MDM da organização (Azure AD+MDM – requer o Azure AD Premium).
- As contas do Azure AD [suportam o Single Sign On](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on). Quando um usuário entrar na Assistência Remota, sua Identidade do usuário do Azure AD será reconhecida e o usuário será assinado no aplicativo para uma experiência simplificada.
- As contas do Azure AD têm opções de [autenticação adicionais](https://docs.microsoft.com/hololens/hololens-identity) por meio [do Windows Hello para Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Além dos usuários conectados à Íris, os usuários podem entrar de outro dispositivo ou usar chaves de segurança FIDO.

### Gerenciamento de Dispositivo Móvel

O Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), parte do Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos conectados ao seu locatário. Assim como o Office 365, o Intune usa o Azure AD para gerenciamento de identidades, para que os funcionários usem as mesmas credenciais para registrar dispositivos no Intune que usam para entrar no Office 365. O Intune também dá suporte a dispositivos que executem outros sistemas operacionais, como iOS e Android, para fornecer uma solução MDM completa. Para os fins deste guia,&#39;nos concentraremos no uso do Intune para habilizar uma implantação na nuvem em escala com o HoloLens 2.

> [!IMPORTANT]
> É essencial ter o Gerenciamento de Dispositivo Móvel. Se você não&#39;já a tiver configurada, siga este guia e [começar a trabalhar com o Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os provedores de MDM que atualmente suportam o Windows 10 Holographic incluem: AirWatch, MobileIron e outros. A maioria dos fornecedores de MDM líderes do setor já dão suporte à integração com o Azure AD. Você pode encontrar os fornecedores de MDM que dão suporte ao Azure AD em [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Rede

Nesta configuração, prevemos que os dispositivos holoLens 2 se conectam à Internet de qualquer rede Wi-Fi disponível. Como um usuário pode precisar alterar a conexão de rede com base no local, ele deve aprender a conectar [dispositivos HoloLens ao Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Para a Assistência Remota do Dynamics 365, há uma variedade de condições de rede, incluindo largura de banda, latência, tremida e perda de pacotes, que podem afetar sua experiência de chamada de vídeo. Embora as chamadas de áudio e vídeo possam ser possíveis em ambientes com largura de banda reduzida, você pode experimentar a degradação do recurso. Ao usar a Assistência Remota do Dynamics 365 no HoloLens, aqui estão os requisitos de rede a ter em mente:

**Mínimo** : 1,5 Mbps para cima/para baixo é necessário para chamada de vídeo de qualidade HD ponto a ponto com resolução de HD 1080p a 30 fps.

**Ideal:** Para a chamada de vídeo de qualidade HD ponto a ponto com resolução hd 1080p, 4-5 Mbps para cima/para baixo devem ser esperados.

Mais informações:

- [Requisitos de rede](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendações de otimização de rede](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Opcional: conectar seu HoloLens à VPN

Os dispositivos conectados a este guia se conectarão à rede por meio da rede externa e da nuvem. Pode ser que para acessar os recursos da empresa que&#39;você precisará conectar seus dispositivos via VPN. Há várias maneiras diferentes de conectar seus dispositivos à VPN, onde o usuário final pode se conectar usando a interface do usuário do dispositivo ou os dispositivos podem ser gerenciados e receber o perfil de VPN de um PPKG ou MDM. Como configurar a VPN não&#39;será abordada neste artigo, portanto, se você&#39;quiser saber mais sobre os diferentes protocolos VPN ou maneiras de gerenciar a VPN, visite esses guias para obter informações sobre [o HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) e a VPN.

## Próximas etapas

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem - Configurar](hololens2-cloud-connected-configure.md)
