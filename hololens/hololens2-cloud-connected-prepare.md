---
title: guia de implantação – implantação em nuvem HoloLens 2 em escala com o auxílio remoto-preparar
description: saiba como se preparar para registrar dispositivos HoloLens em uma rede conectada na nuvem usando o azure active directory e o gerenciamento de identidades.
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
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639651"
---
# <a name="prepare---cloud-connected-guide"></a>Preparar – guia conectado à nuvem

Ao final deste artigo, você terá configurado o Azure AD, o MDM e entender mais sobre o uso de contas e requisitos de rede do Azure AD. esta seção do guia ajudará você e sua organização a se preparar para implantar HoloLens 2 na nuvem e usar o assistente remoto do Dynamics 365. Ele passará pela importância de cada parte da sua infraestrutura, além de fornecer links para guias para ajudá-lo a configurar essas peças conforme necessário.

## <a name="infrastructure-essentials"></a>Conceitos básicos de infraestrutura

para cenários de implantação pessoal e corporativo, um sistema de MDM é a infraestrutura essencial necessária para implantar e gerenciar dispositivos Windows 10 Holographic. Uma assinatura do Azure AD Premium é recomendada como provedor de identidade e necessária para dar suporte a determinados recursos.

### <a name="azure-active-directory"></a>Active Directory do Azure

O Azure AD é um serviço de diretório baseado em nuvem que fornece gerenciamento de identidade e acesso. as organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: gratuita, Premium P1 e Premium P2 (consulte as [edições do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions).) todas as edições dão suporte ao registro de dispositivos do Azure AD, mas Premium P1 é necessário para habilitar o registro automático de MDM que usaremos neste guia posteriormente.

> [!IMPORTANT]
> é essencial ter um Azure Active Directory como dispositivos HoloLens não dão suporte ao ingresso no AD local. se você não&#39;já tiver uma Azure Active Directory configurada, vá para [criar um novo locatário no Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gerenciamento de Identidades

Os funcionários podem usar apenas uma conta para inicializar um dispositivo de modo que&#39;é imperativo que sua organização controla qual conta está habilitada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento.

neste guia, escolhemos que, para a [identidade](/hololens/hololens-identity) usada, usaremos contas do Azure AD ou contas de Azure Active Directory. Há vários benefícios para as contas do Azure AD que gostaríamos de usar, como:

- Os funcionários usam sua conta do Azure AD para registrar o dispositivo no Azure AD e registrá-lo automaticamente com a solução de MDM da organização&#39;s (Azure AD + MDM – requer Azure AD Premium).
- As contas do Azure AD dão suporte ao [logon único](/azure/active-directory/manage-apps/what-is-single-sign-on). Quando um usuário entra no auxílio remoto, sua identidade do usuário conectado do Azure AD será reconhecida e o usuário será conectado ao aplicativo para uma experiência simplificada.
- as contas do Azure AD têm [opções de autenticação](/hololens/hololens-identity) adicionais por meio [do Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Além dos usuários de logon da íris, é possível entrar de outro dispositivo ou usar as chaves de segurança do FIDO.

### <a name="mobile-device-management"></a>Gerenciamento do Dispositivo Móvel

o Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), parte do Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos conectados ao seu locatário. assim como Office 365, o Intune usa o Azure AD para gerenciamento de identidades, de modo que os funcionários usam as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. O Intune também dá suporte a dispositivos que executam outros sistemas operacionais, como iOS e Android, para fornecer uma solução completa de MDM. para os fins deste guia, nós&#39;estamos se concentrando em usar o Intune para habilitar uma implantação em nuvem em escala com o HoloLens 2.

> [!IMPORTANT]
> É essencial ter o gerenciamento de dispositivos móveis. Se você não&#39;já tiver configurado, siga este guia e [comece a](/mem/intune/fundamentals/free-trial-sign-up)usar o Intune.

> [!NOTE]
> Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. os provedores de MDM que dão suporte ao Windows 10 Holographic incluem atualmente: relógio de watch, MobileIron e outros. A maioria dos fornecedores de MDM líderes do setor já dão suporte à integração com o Azure AD. Você pode encontrar os fornecedores de MDM que dão suporte ao Azure AD em [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Rede

nesta configuração, prevemos HoloLens dois dispositivos que se conectam à Internet de qualquer rede aberta Wi-Fi disponível. como um usuário pode precisar alterar a conexão de rede com base no local, ele deve saber como [conectar HoloLens dispositivos ao Wi-Fi.](/hololens/hololens-network)

Para a assistência remota do Dynamics 365, há uma variedade de condições de rede, incluindo largura de banda, latência, tremulação e perda de pacotes, que podem afetar sua experiência de chamada de vídeo. Embora as chamadas de áudio e vídeo possam ser possíveis em ambientes com menor largura de banda, você pode enfrentar a degradação do recurso. ao usar o Dynamics 365 remotamente Assist em HoloLens aqui estão os requisitos de rede a serem considerados:

**Mínimo** : 1,5 Mbps up/down são necessários para a chamada de vídeo de qualidade HD ponto a ponto chamando com a resolução de HD 1080p a 30 fps.

**Ideal:** Para vídeo de qualidade de HD ponto a ponto chamando com a resolução de HD 1080p, 4-5 Mbps up/down devem ser esperados.

Mais informações:

- [Requisitos de rede](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendações de otimização de rede](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>opcional: Conexão seu HoloLens para VPN

Os dispositivos conectados a este guia vão se conectar à rede por meio do e da rede de nuvem externa. Pode ser que você acesse os recursos da empresa que&#39;necessário para conectar seus dispositivos via VPN. Há várias maneiras diferentes de conectar seus dispositivos à VPN, onde o usuário final pode se conectar por meio do uso da interface do usuário do dispositivo, ou os dispositivos podem ser gerenciados e receber o perfil VPN de um PPKG ou MDM. como configurar a VPN ganha&#39;t ser abordado neste artigo, portanto, se você&#39;d como saber mais sobre os diferentes protocolos vpn ou maneiras de gerenciar VPN, visite [estes guias para obter informações sobre HoloLens e vpn.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada na nuvem – configurar](hololens2-cloud-connected-configure.md)
