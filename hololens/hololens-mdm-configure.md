---
title: Usar o Intune do Gerenciador de Pontos de Extremidade da Microsoft para gerenciar dispositivos HoloLens
description: Saiba como usar o MDM para configurar o CSP, a política e gerenciar dispositivos de realidade misturada do HoloLens em escala usando o Intune.
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
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283952"
---
# Usar o Intune do Gerenciador de Pontos de Extremidade da Microsoft para gerenciar dispositivos HoloLens

Há várias configurações diferentes que você pode gerenciar por meio do MDM. O uso de dispositivos do Intune pode ser agrupado e as configurações podem ser implantadas nesses grupos de usuários ou dispositivos. Os aplicativos também podem ser implantados e gerenciados, configurando dispositivos para se conectarem à sua rede, bem como configurar as atualizações para que ocorram no momento desejado e no anel de atualização necessário. 

## Como gerenciar por meio do Intune

### Categorias e grupos de dispositivos
Usando o Intune, você pode criar categorias de dispositivo para adicionar automaticamente dispositivos a grupos com base em categorias que você cria, como Engenharia, Médicos, Desenvolvedores e assim por diante. A ideia é facilitar o gerenciamento de seus dispositivos que executam o Windows Holographic for Business.
Leia mais: [Categorizar dispositivos em grupos](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Perfis de configuração do dispositivo
O Intune inclui configurações e recursos que você pode habilitar ou desabilitar em dispositivos diferentes em sua organização. Essas configurações e recursos são gerenciados usando perfis. Por exemplo, você pode criar um perfil que habilita a Cortana ou usa o Microsoft Defender Smart Screen em seus dispositivos que executam o Windows Holographic for Business.
Em seus perfis, você pode usar o OMA-URI para personalizar algumas configurações, criar restrições de dispositivo e configurar uma rede virtual privada (VPN) e Wi-Fi.
[Começar a trabalhar com perfis de configuração](https://docs.microsoft.com/mem/intune/configuration/device-profiles)e visão [geral de perfil.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## Exemplos do que pode ser gerenciado e configurado

Usar o MDM para gerenciar dispositivos oferece uma ampla variedade de itens que podem ser selecionados. 

### Wi-Fi
[As configurações de Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) atribuem configurações de rede sem fio a usuários e dispositivos. Quando você atribui um perfil Wi-Fi usuário, os usuários têm acesso ao seu Wi-Fi corporativo sem precisar configurá-lo por conta própria.
Saiba mais sobre [como configurar sua rede para o HoloLens](hololens-commercial-infrastructure.md)

### Certificados
Os certificados ajudam a melhorar a segurança, fornecendo autenticação de conta, Wi-Fi autenticação, criptografia VPN e criptografia SSL de conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento, é uma prática ideal usar seu sistema MDM para gerenciar esses certificados durante todo o ciclo de vida, desde o registro até a renovação e revogação. Seu sistema MDM pode implantar automaticamente esses certificados nos armazenamentos de certificados dos dispositivos depois de registrar o dispositivo (desde que o sistema MDM suporte o protocolo SCEP ou os padrões de criptografia de chave pública #12 (PKCS#12)). O MDM também pode consultar e excluir certificados de cliente inscritos ou disparar uma nova solicitação de registro antes que o certificado atual seja expirado. 

### Proxy
A maioria das redes de intranet corporativas utiliza um proxy para gerenciar o tráfego interno. Com o HoloLens 2, você pode configurar um servidor proxy para conexões ethernet e Wi-Fi rede. Essas configurações não se aplicam a conexões VPN. Para obter mais detalhes sobre as configurações de proxy para o Windows 10, consulte [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
As organizações costumam usam uma VPN para controlar o acesso a aplicativos e recursos na intranet da empresa. O HoloLens 2 dá suporte a conexões VPN SSL, que exigem um plug-in baixável da Microsoft Store e são específicas para o fornecedor de VPN de sua escolha. 
- Leia mais sobre [VPN no HoloLens.](hololens-network.md#vpn)
- Para obter mais detalhes sobre perfis VPN, consulte o [CSP VPNv2.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### Implantar e gerenciar aplicativos
Usando o Intune, você pode adicionar aplicativos aos seus dispositivos que executam o Windows Holographic for Business. Uma solução MDM permite que os tomadores de decisões de IT e os administradores instalem automaticamente (push) seus aplicativos de linha de negócios internamente ou comprem aplicativos por meio da loja para um grupo de usuários. Há muitas maneiras de implantar aplicativos, incluindo:
-   [Intune e Portal da Empresa]( app-deploy-intune.md)
-   [Microsoft Store para Empresas]( app-deploy-store-business.md)

Saiba mais sobre o gerenciamento de aplicativos por meio do Intune.
-   [Adicionar aplicativos ao Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Adicionar aplicativos da Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Adicionar aplicativos que você criar](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Atribuir aplicativos a grupos](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Atualizações de software
O Intune inclui um recurso chamado anéis de atualização para dispositivos Windows 10. Esses anéis de atualização incluem um grupo de configurações que determinam como as atualizações são instaladas. Por exemplo, você pode criar uma janela de manutenção para instalar atualizações ou optar por reiniciar após atualizar. Um anel de atualização pode ser aplicado a vários dispositivos executando o Windows Holographic for Business.
Leia mais sobre como gerenciar [atualizações do HoloLens e](hololens-updates.md) [gerenciar atualizações de software por meio do Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### Configurar o modo de quiosque
Usando os recursos de computador compartilhado ou convidado disponíveis no Intune, você pode configurar dispositivos Windows Holographic for Business para executar como um quiosque. Esses dispositivos podem executar um aplicativo (modo de quiosque de aplicativo único) ou executar vários aplicativos (modo de quiosque de vários aplicativos). O modo de quiosque é uma interface do usuário para controlar quais identidades têm acesso a quais aplicativos por padrão.
Saiba como [configurar o HoloLens como um quiosque]( hololens-kiosk.md)

