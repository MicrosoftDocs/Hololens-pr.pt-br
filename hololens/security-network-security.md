---
title: Segurança de rede
description: segurança de rede
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, rede, segurança de rede
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009419"
---
# Segurança de rede

## Protocolos de rede

O NetBIOS (Network Basic Input/Output System) desatualizado era amplamente usado muitas vezes no passado em cenários de LAN – para fornecer resolução de nome para um computador e pastas compartilhadas. No entanto, com o tempo, o NetBIOS provou ser suscetível a vários ataques, e sua relevância diminuída em favor de outros protocolos mais seguros. Para remover esse problema de vulnerabilidade, o HoloLens 2 eliminou o código relacionado a NetBIOS do sistema operacional.

Os protocolos TLS (Transport Layer Security) estão sempre em constante evolução. Para manter-se atualizada com as várias explorações de segurança que foram descobertas nesta área, a indústria de computação se evoluiu em versões mais recentes e mais eficazes. Devido ao tempo necessário para que todas as implantações de servidor adotem as novas versões do protocolo TLS, é possível implementar um mecanismo de fallback que permite que clientes e servidores em diferentes versões padrão do protocolo ainda possam se comunicar durante o período de transição.

## Conectividade segura 

O Windows Defender Firewall oferece funcionalidade fundamental para proteger a conectividade de dispositivos. Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo programaticamente ou por meio da interface do usuário.

A privacidade de acesso remoto e conexão para clientes com dispositivo móvel pode ser garantida pela [plataforma de plug-in VPN UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Provedores de VPN de terceiros podem criar seus próprios plug-ins usando APIs do WinRT que vão rodar dentro da área restrita do AppContainer, eliminando a complexidade e os problemas geralmente associados com a escrita de drivers a nível de sistema.
