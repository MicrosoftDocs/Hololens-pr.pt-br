---
title: Arquitetura de segurança do HoloLens
description: Arquitetura de segurança
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, hololens 2, segurança do hololens2, visão geral da segurança, arquitetura de segurança, arquitetura, arquitetura do hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8045f534926e0719bd2f8e448809b5a2965346c4
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865646"
---
# Visão geral e arquitetura

A arquitetura de segurança do HoloLens 2 foi projetada e desenvolvida desde o início para ser isenta de problemas de segurança herdados, ao mesmo tempo em que cria uma superfície de ataque minimizada. Esta nova arquitetura inovadora oferece locais de armazenamento seguros e elementos de segurança avançada, com mecanismos capazes de blindar sistemas operacionais contra possíveis ameaças e vulnerabilidades.

O HoloLens 2 combina hardware, software, rede e serviços para oferecer segurança ponta a ponta, oferecendo ao usuário uma experiência ideal. Com o HoloLens 2, a grande maioria dos recursos de segurança agora está ativada automaticamente, minimizando o esforço necessário para configurar corretamente o sistema operacional.

O Windows HoloLens 2 e a arquitetura do sistema operacional oferecem esses recursos inovadores de segurança:

  * **Separação e isolamento de estado**:  Essa nova arquitetura protege partes críticas do sistema operacional do Hololens 2 contra mudanças, como as necessárias para que o sistema operacional central seja inicializado em um estado confiável. A tecnologia de isolamento é usada para restringir aplicativos não confiáveis em uma área restrita, garantindo que eles não tenham impacto na segurança do sistema. O sistema operacional inteiro é segmentado em seções seguras, com cada seção blindada por uma combinação de diferentes tecnologias de segurança.
  
  * **Proteção de Dados**: Se o dispositivo do usuário for perdido ou roubado, o HoloLens 2 impedirá que aplicativos não autorizados leiam informações confidenciais apoiado na criptografia de dados BitLocker. 
  
  * **Sistema operacional livre de senhas**:  Os sistemas operacionais mais antigos e baseados em senhas podem expor inadvertidamente os usuários a ameaças de phishing e eram frequentemente responsáveis por contas comprometidas. O Windows Holographic for Business elimina o uso de senhas para entrar através de MSA e AAD e reforça a proteção de identidade do usuário com a entrada através do Windows Hello™ e do FIDO2. 
  
    > [!NOTE]
    > Para ter o suporte do FIDO2, o dispositivo deve estar na Compilação 19041 ou superior. 

  * **Segurança de rede**: O HoloLens 2 oferece ao usuário maior a segurança de rede por meio de protocolos e configurações padrão aprimorados.