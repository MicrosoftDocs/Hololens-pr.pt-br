---
title: Redes sem fio e Wi-Fi
description: Redes sem fio e Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, sem fio, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865641"
---
# Redes sem fio e Wi-Fi

A conectividade de LAN sem fio do HoloLens 2 oferece suporte a um grande número de padrões de segurança Wi-Fi mais recentes, como:
  * WPA2 (Wi-Fi Protected Access 2)  
  * Protocolo TEAP (Tunnel Extensible Authentication Protocol)  
  * OWE (Opportunistic Wireless Encryption)

TEAP, a próxima geração de autenticação de rede corporativa, proporciona a habilidade de encadear várias credenciais com segurança em uma única transação.  Isso permite aos administradores reforçarem uma melhor postura de segurança, que exige identidades válidas para o computador e o usuário durante a mesma transação de autenticação.

O HoloLens 2 tem protocolos modernos sem fio e Wi-Fi que permitem aos clientes o suporte máximo. O rádio do HoloLens 2 é uma solução Qualcomm WCN3990 oferecendo uma experiência de rádio premium. O Wi-Fi compatível é 802.11 ac/n. A faixa de frequência não é configurável pelo usuário e depende do país de uso. Nos Estados Unidos, o Wi-Fi usa canais de 2.4 GHz (1-11) e canais de 5 GHz (36-64, 100-165). Nem os usuários nem os dispositivos podem fazer listas de permitir/negar para frequências específicas. O Bluetooth SIC Core 5.0 tem uma antena dedicada de 2.4 GHz para Bluetooth que não é compartilhada com o Wi-Fi. A pilha de software do HoloLens 2 aceita vários protocolos e perfis, como HID, HOGP, A2DP e GATT. 

Os administradores de TI podem: 
  * Habilitar ou restringir o [acesso Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)
  * Definir [ Nomes de dispositivos Bluetooth locais](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)
  * Permitir que [dispositivos sejam detectáveis](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)
  * Permite/revogar permissão de [conexões Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 
  * Permite ou revogar permissão à [conexão Wi-Fi fora das redes instaladas pelo servidor MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)
