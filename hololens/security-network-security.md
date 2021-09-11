---
title: Segurança de rede
description: segurança de rede
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, network, network security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427052"
---
# <a name="network-security"></a>Segurança de rede

## <a name="network-protocols"></a>Protocolos de rede

O desatualizado NetBIOS era amplamente usado muitas vezes no passado em cenários de LAN a fim de fornecer resolução de nomes para um computador e pastas compartilhadas. No entanto, com o tempo, o NetBIOS provou ser suscetível a vários ataques e a relevância dele diminuiu em relação a outros protocolos mais seguros. Para remover esse problema de vulnerabilidade, o HoloLens 2 eliminou o código relacionado ao NetBIOS do sistema operacional.

Os protocolos TLS estão em constante evolução. Para se manter atualizada com as várias explorações de segurança descobertas nessa área, a indústria de computação passou a usar versões mais recentes e mais efetivas. Devido ao tempo necessário para que todas as implantações de servidor adotem as novas versões do protocolo TLS, é possível implementar um mecanismo de fallback que permita que os clientes e os servidores em diferentes versões padrão do protocolo ainda possam se comunicar durante o período de transição.

## <a name="secure-connectivity"></a>Conectividade segura 

O Windows Defender Firewall oferece funcionalidade crítica para proteger a conectividade de dispositivos. Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo por programação ou pela interface do usuário.

A privacidade do acesso remoto e da conexão para clientes móveis pode ser garantida pela [plataforma de plug-in de VPN do UWP](/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Os provedores de VPN de terceiros podem criar plug-ins próprios usando as APIs do WinRT, que serão executadas na área restrita do AppContainer, eliminando a complexidade e os problemas geralmente associados à gravação de drivers no nível do sistema.
