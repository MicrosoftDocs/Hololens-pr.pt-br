---
title: Guia de implantação – Implantação do HoloLens 2 conectada à nuvem em escala com o Remote Assist – Preparar
description: Saiba como se preparar para registrar dispositivos HoloLens em uma rede conectada à nuvem usando o Azure Active Directory e o gerenciamento de identidades.
keywords: HoloLens, gerenciamento, conectado à nuvem, Assistência Remota, AAD, Azure AD, MDM, Dispositivos móveis Gerenciamento de Dispositivos
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
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924563"
---
# <a name="prepare---cloud-connected-guide"></a>Preparar – Guia conectado à nuvem

Ao final deste artigo, você terá configurar o Azure AD, o MDM e entender mais sobre como usar as contas do Azure AD e os requisitos de rede. Esta seção do guia ajudará você e sua organização a se prepararem para implantar o HoloLens 2 na nuvem e usar o Dynamics 365 Remote Assist. Ele vai sobre a importância de cada parte de sua infraestrutura, bem como fornecer links para guias para ajudá-lo a configurar essas partes conforme necessário.

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

Para cenários de implantação pessoal e corporativa, um sistema MDM é a infraestrutura essencial necessária para implantar e gerenciar Windows 10 Holographic dispositivos. Uma assinatura do Azure AD Premium é recomendada como provedor de identidade e necessária para dar suporte a determinados recursos.

### <a name="azure-active-directory"></a>Azure Active Directory

O Azure AD é um serviço de diretório baseado em nuvem que fornece gerenciamento de identidade e acesso. As organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: Gratuita, Premium P1 e Premium P2 (consulte [Azure Active Directory edições](https://azure.microsoft.com/documentation/articles/active-directory-editions).) Todas as edições são suportadas pelo registro de dispositivo do Azure AD, mas o Premium P1 é necessário para habilitar o registro automático do MDM, que será usado neste guia posteriormente.

> [!IMPORTANT]
> É essencial ter um Azure Active Directory, pois os dispositivos HoloLens não são compatíveis com a junção do AD local. Se você ainda&#39;tiver uma Azure Active Directory configurada, acesse Criar um novo locatário [no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gerenciamento de Identidades

Os funcionários podem usar apenas uma conta para inicializar um dispositivo,&#39;que sua organização controle qual conta está habilitada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento.

Neste guia, optemos por que, para a [Identidade](https://docs.microsoft.com/hololens/hololens-identity) usada, usaremos contas do Azure AD ou Azure Active Directory contas. Há vários benefícios para contas do Azure AD que queremos usar, como:

- Os funcionários usam sua conta do Azure AD para registrar o dispositivo no Azure AD e registrá-lo automaticamente na solução de MDM do&#39;da organização (Azure AD+MDM – requer Azure AD Premium).
- As contas do Azure AD são [suportadas pelo Single Sign On](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on). Quando um usuário entra no Remote Assist, sua Identidade do usuário do Azure AD assinado será reconhecida e o usuário será assinado no aplicativo para uma experiência simplificada.
- As contas do Azure AD têm opções de [autenticação adicionais](https://docs.microsoft.com/hololens/hololens-identity) [por meio Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Além do Iris, os usuários de logoff podem entrar de outro dispositivo ou usar chaves de segurança FIDO.

### <a name="mobile-device-management"></a>Gerenciamento do Dispositivo Móvel

O Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), parte do Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos conectados ao seu locatário. Assim como o Office 365, o Intune usa o Azure AD para gerenciamento de identidades, portanto, os funcionários usam as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. O Intune também dá suporte a dispositivos que executem outros sistemas operacionais, como iOS e Android, para fornecer uma solução de MDM completa. Para os fins deste guia,&#39;nos concentraremos no uso do Intune para habilizar uma implantação de nuvem em escala com o HoloLens 2.

> [!IMPORTANT]
> É essencial ter dispositivos móveis Gerenciamento de Dispositivos. Se você ainda&#39;já o tiver definido, siga este guia e [Começar a trabalhar com o Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os provedores de MDM que Windows 10 Holographic atualmente incluem: AirWatch, MobileIron e outros. A maioria dos fornecedores de MDM líderes do setor já dão suporte à integração com o Azure AD. Você pode encontrar os fornecedores de MDM que dão suporte ao Azure AD em [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Rede

Nesta configuração, prevemos que os dispositivos HoloLens 2 se conectam à Internet de qualquer rede Wi-Fi aberta disponível. Como um usuário pode precisar alterar a conexão de rede com base na localização, ele deve aprender a conectar [dispositivos HoloLens ao Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Para o Dynamics 365 Remote Assist, há uma variedade de condições de rede, incluindo largura de banda, latência, tremibilidade e perda de pacotes, que podem afetar sua experiência de chamada de vídeo. Embora as chamadas de áudio e vídeo possam ser possíveis em ambientes com largura de banda reduzida, você pode ter degradação de recursos. Ao usar o Dynamics 365 Remote Assist no HoloLens, aqui estão os requisitos de rede para ter em mente:

**Mínimo:** 1,5 Mbps para cima/para baixo é necessário para a chamada de vídeo de qualidade de HD ponto a ponto com resolução de HD 1080p a 30 fps.

**Ideal:** Para a chamada de vídeo de qualidade HD ponto a ponto com resolução de HD 1080p, 4 a 5 Mbps para cima/para baixo devem ser esperados.

Mais informações:

- [Requisitos de rede](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendações de otimização de rede](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Opcional: Conectar o HoloLens à VPN

Os dispositivos que estão sendo conectados a este guia se conectarão à rede por meio da rede externa e da rede de nuvem externa. Pode ser que para acessar os recursos da empresa&#39;você precisará conectar seus dispositivos por meio de VPN. Há várias maneiras diferentes de conectar seus dispositivos à VPN, em que o usuário final pode se conectar usando a interface do usuário do dispositivo ou os dispositivos podem ser gerenciados e receber o perfil VPN de um PPKG ou MDM. Como configurar a VPN não&#39;será abordado neste artigo, portanto, se você&#39;quiser saber mais sobre os diferentes protocolos VPN ou maneiras de gerenciar a VPN, visite estes guias para obter informações sobre [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) e VPN.

## <a name="next-step"></a>Próxima etapa

> [!div class="nextstepaction"]
> [Implantação conectada à nuvem – Configurar](hololens2-cloud-connected-configure.md)
