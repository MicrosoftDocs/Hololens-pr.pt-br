---
title: usando o Endpoint Manager Intune da Microsoft para gerenciar dispositivos HoloLens
description: saiba como usar o MDM para configurar o CSP, a política e o gerenciamento HoloLens dispositivos de realidade misturada em escala usando o Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640263"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>usando o Endpoint Manager Intune da Microsoft para gerenciar dispositivos HoloLens

Há várias configurações diferentes que você pode gerenciar por meio do MDM. O uso de dispositivos do Intune pode ser agrupado e as configurações podem ser implantadas nesses grupos de usuários ou dispositivos. Os aplicativos também podem ser implantados e gerenciados, configurar dispositivos para se conectar à sua rede, bem como configurar atualizações para ocorrer no momento desejado e no anel de atualização necessário. 

## <a name="how-to-manage-via-intune"></a>Como gerenciar por meio do Intune

### <a name="device-categories-and-groups"></a>Grupos e categorias de dispositivo
Usando o Intune, você pode criar categorias de dispositivo para adicionar automaticamente dispositivos a grupos com base em categorias criadas por você, como engenharia, medicina, desenvolvedores e assim por diante. A ideia é tornar mais fácil gerenciar seus dispositivos que executam o Windows Holographic for Business.
Leia mais: [categorizar dispositivos em grupos](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Perfis de configuração do dispositivo
O Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos na sua organização. Essas configurações e recursos são gerenciados com o uso de perfis. Por exemplo, você pode criar um perfil que habilite a Cortana ou use a Tela Inteligente do Microsoft Defender em seus dispositivos que executam o Windows Holographic for Business.
Em seus perfis, você pode usar o OMA-URI para personalizar algumas configurações, criar restrições de dispositivo e configurar uma VPN (rede virtual privada) e Wi-Fi.
[Introdução aos perfis de configuração](/mem/intune/configuration/device-profiles)e [visão geral do perfil](/mem/intune/configuration/device-profile-create).

## <a name="examples-of-what-can-be-managed-and-configured"></a>Exemplos de o que pode ser gerenciado e configurado

Usar o MDM para gerenciar dispositivos fornece uma ampla matriz de itens que podem ser selecionados. 

### <a name="wi-fi"></a>Wi-Fi
As [configurações de Wi-Fi](/mem/intune/configuration/wi-fi-settings-configure) atribuem configurações de rede sem fio para usuários e dispositivos. Quando você atribui um perfil de Wi-Fi, os usuários obtêm acesso ao seu Wi-Fi corporativo sem precisar configurá-lo por conta própria.
Saiba mais sobre como [configurar sua rede para HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certificados
Os certificados ajudam a melhorar a segurança fornecendo autenticação de conta, Wi-Fi autenticação, criptografia de VPN e criptografia SSL do conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento, é uma prática recomendada usar seu sistema MDM para gerenciar esses certificados em todo o ciclo de vida – do registro por meio de renovação e revogação. O sistema MDM pode implantar automaticamente esses certificados nos repositórios de certificados dos dispositivos depois de registrar o dispositivo (desde que o sistema MDM ofereça suporte aos padrões de protocolo SCEP ou protocolo SCEP de criptografia de chave pública #12 (PKCS # 12)). O MDM também pode consultar e excluir certificados de cliente registrados ou disparar uma nova solicitação de registro antes que o certificado atual expire. 

### <a name="proxy"></a>Proxy
A maioria das redes de intranet corporativas aproveita um proxy para gerenciar o tráfego interno. com o HoloLens 2, você pode configurar um servidor proxy para conexões ethernet e Wi-Fi. Essas configurações não se aplicam a conexões VPN. para obter mais detalhes sobre as configurações de proxy para Windows 10, consulte [CSP NetworkProxy](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
As organizações costumam usam uma VPN para controlar o acesso a aplicativos e recursos na intranet da empresa. o HoloLens 2 dá suporte a conexões VPN SSL, que exigem um plug-in para download da Microsoft Store e são específicas para o fornecedor de VPN de sua escolha. 
- Leia mais sobre [VPN em HoloLens](hololens-network.md#vpn).
- Para obter mais detalhes sobre perfis de VPN, consulte o [CSP VPNv2](/windows/client-management/mdm/vpnv2-csp).

### <a name="deploy-and-manage-apps"></a>Implantar e gerenciar aplicativos
Usando o Intune, você pode adicionar aplicativos a dispositivos que executam o Windows Holographic for Business. Uma solução de MDM permite que os administradores e tomadores de decisões de ti instalem de forma privada (push) seus aplicativos internos de linha de negócios ou comprem aplicativos por meio da loja para um grupo de usuários. Há várias maneiras de implantar aplicativos, incluindo:
-   [Intune e Portal da Empresa]( app-deploy-intune.md)
-   [Microsoft Store para Empresas]( app-deploy-store-business.md)

Saiba mais sobre o gerenciamento de aplicativos por meio do Intune.
-   [Adicionar aplicativos ao Intune](/mem/intune/apps/apps-add)
-   [Adicionar aplicativos da Microsoft Store](/mem/intune/apps/store-apps-windows)
-   [Adicionar aplicativos que você criar](/mem/intune/apps/lob-apps-windows)
- [Atribuir aplicativos a grupos](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Atualizações de software
O Intune inclui um recurso chamado anéis de atualização para dispositivos Windows 10. Esses anéis de atualização incluem um grupo de configurações que determinam como as atualizações são instaladas. Por exemplo, você pode criar uma janela de manutenção para instalar as atualizações ou optar por reiniciar depois que as atualizações forem instaladas. Um anel de atualização pode ser aplicado a vários dispositivos que executam o Windows Holographic for Business.
leia mais sobre como [gerenciar atualizações de HoloLens](hololens-updates.md) e [gerenciar atualizações de software por meio do Intune](/mem/intune/protect/windows-update-for-business-configure).

### <a name="configure-kiosk-mode"></a>Configurar o modo de quiosque
Usando os recursos de computador compartilhados ou convidados disponíveis no Intune, você pode configurar dispositivos do Windows Holographic for Business para serem executados como um quiosque. Esses dispositivos podem executar um aplicativo (modo de quiosque de aplicativo único) ou vários aplicativos (modo de quiosque de vários aplicativos). O modo de quiosque é uma interface do usuário para controlar quais identidades têm acesso a quais aplicativos por padrão.
saiba como [configurar HoloLens como um quiosque]( hololens-kiosk.md)

