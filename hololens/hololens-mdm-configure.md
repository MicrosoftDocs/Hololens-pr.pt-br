---
title: Usando o Endpoint Manager do Microsoft Intune para gerenciar dispositivos HoloLens
description: Usar o MDM para configurar o CSP e a política e gerenciar o HoloLens em escala.
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
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009629"
---
# Usando o Endpoint Manager do Microsoft Intune para gerenciar dispositivos HoloLens

Há várias configurações diferentes que você pode gerenciar por meio de MDM. Usar dispositivos do Intune pode ser agrupado e as configurações podem ser implantadas nesses grupos de usuários ou dispositivos. Os aplicativos também podem ser implantados e gerenciados, configurar dispositivos para se conectar à sua rede, bem como configurar atualizações para ocorrer no momento desejado e no anel de atualização necessário. 

## Como gerenciar pelo Intune

### Categorias e grupos de dispositivos
Usando o Intune, você pode criar categorias de dispositivos para adicionar dispositivos a grupos automaticamente com base em categorias que você cria, como engenharia, medicina, desenvolvedores e assim por diante. A ideia é facilitar o gerenciamento de seus dispositivos que executam o Windows holográfico for Business.
Leia mais: [categorizar os dispositivos em grupos](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Perfis de configuração de dispositivo
O Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos em sua organização. Essas configurações e recursos são gerenciados usando perfis. Por exemplo, você pode criar um perfil que habilite a Cortana ou use a tela inteligente do Microsoft defender em seus dispositivos que executam o Windows holográfico for Business.
Em seus perfis, você pode usar o OMA-URI para personalizar algumas configurações, criar restrições de dispositivo e configurar uma rede virtual privada (VPN) e Wi-Fi.
Comece [a usar perfis de configuração e a](https://docs.microsoft.com/mem/intune/configuration/device-profiles) [visão geral do perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-create).

## Exemplos do que podem ser gerenciados e configurados

Usar o MDM para gerenciar dispositivos oferece uma ampla variedade de itens que podem ser selecionados. 

### Wi-Fi
[As configurações de Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) atribui configurações de rede sem fio a usuários e dispositivos. Quando você atribui um perfil de Wi-Fi, os usuários obtêm acesso à sua rede Wi-Fi corporativa sem precisar configurá-la.
Saiba mais sobre como [configurar sua rede para o HoloLens](hololens-commercial-infrastructure.md)

### Certificados
Os certificados ajudam a melhorar a segurança fornecendo autenticação de conta, autenticação de Wi-Fi, criptografia de VPN e criptografia SSL do conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento, é uma prática recomendada usar seu sistema de MDM para gerenciar esses certificados durante todo o ciclo de vida deles, desde a inscrição até a renovação e a revogação. Seu sistema MDM pode implantar automaticamente esses certificados nos repositórios de certificados dos dispositivos após a inscrição do dispositivo (desde que o sistema MDM dê suporte ao protocolo de registro de certificado simples (SCEP) ou aos padrões de criptografia de chave pública #12 (PKCS # 12)). O MDM também pode consultar e excluir certificados de cliente registrados ou disparar uma nova solicitação de inscrição antes que o certificado atual expire. 

### Proxy
A maioria das redes de intranet corporativas aproveita um proxy para gerenciar o tráfego interno. Com o HoloLens 2, você pode configurar um servidor proxy para conexões Ethernet e Wi-Fi. Essas configurações não se aplicam a conexões VPN. Para obter mais detalhes sobre as configurações de proxy para o Windows 10, consulte [CSP do NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
As organizações costumam usam uma VPN para controlar o acesso a aplicativos e recursos na intranet da empresa. O HoloLens 2 dá suporte a conexões VPN SSL, que exigem um plug-in para download da Microsoft Store e são específicas do fornecedor de VPN de sua preferência. 
- Leia mais sobre [VPN no HoloLens](hololens-network.md#vpn).
- Para obter mais detalhes sobre perfis VPN, consulte o [CSP VPNv2](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

### Implantar e gerenciar aplicativos
Usando o Intune, você pode adicionar aplicativos a seus dispositivos que executam o Windows holográfico for Business. Uma solução MDM permite que os responsáveis por decisões e administradores de ti sejam instalados de forma privada (push) em seus aplicativos internos, de linha de negócios ou comprar aplicativos por meio da loja para um grupo de usuários. Há muitas maneiras de implantar aplicativos, incluindo:
-   [Portal do Intune e da empresa]( app-deploy-intune.md)
-   [Microsoft Store para Empresas]( app-deploy-store-business.md)

Saiba mais sobre o gerenciamento de aplicativos pelo Intune.
-   [Adicionar aplicativos ao Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Adicionar aplicativos da Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Adicionar aplicativos que você cria](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Atribuir aplicativos a grupos](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Atualizações de software
O Intune inclui um recurso chamado Update anéis para dispositivos Windows 10. Esses toques de atualização incluem um grupo de configurações que determinam como as atualizações são instaladas. Por exemplo, você pode criar uma janela de manutenção para instalar atualizações ou optar por reiniciar após atualizar. Um anel de atualização pode ser aplicado a vários dispositivos que executam o Windows holográfico for Business.
Leia mais sobre como [gerenciar as atualizações do HoloLens](hololens-updates.md) e [gerenciar atualizações de software via Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

### Configurar o modo de quiosque
Usando os recursos de PC compartilhado ou convidado disponíveis no Intune, você pode configurar os dispositivos Windows holográfico para empresas para serem executados como quiosque. Esses dispositivos podem executar um aplicativo (modo de quiosque do aplicativo único) ou executar vários aplicativos (modo de quiosque de vários aplicativos). O modo de quiosque é uma interface do usuário para controlar quais identidades têm acesso a quais aplicativos por padrão.
Saiba como [Configurar o HoloLens como um quiosque]( hololens-kiosk.md)

