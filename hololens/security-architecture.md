---
title: Arquitetura de segurança do HoloLens
description: Arquitetura de segurança
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, hololens 2, segurança do hololens2, visão geral da segurança, arquitetura de segurança, arquitetura, arquitetura do hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034083"
---
# <a name="security-overview-and-architecture"></a>Visão geral e arquitetura de segurança

A arquitetura de segurança do HoloLens 2 foi projetada e desenvolvida desde o início para não apresentar problemas de segurança herdados e, ao mesmo tempo, criar uma superfície de ataque minimizada. Esta nova arquitetura inovadora oferece locais de armazenamento seguros e elementos de segurança avançada, com mecanismos capazes de blindar sistemas operacionais contra possíveis ameaças e vulnerabilidades.

O HoloLens 2 combina hardware, software, rede e serviços para fornecer segurança de ponta a ponta, oferecendo ao usuário uma experiência ideal. Com o HoloLens 2, a grande maioria dos recursos de segurança agora é ativada automaticamente, minimizando o esforço necessário para configurar corretamente o sistema operacional.

O Windows para o HoloLens 2 e a arquitetura do sistema operacional oferecem os seguintes recursos inovadores de segurança:

  * **Separação e o isolamento de estado**: essa nova arquitetura protege partes críticas do sistema operacional do HoloLens 2 contra alterações, como aquelas necessárias para que o sistema operacional principal seja inicializado em um estado confiável. A tecnologia de isolamento é usada para limitar aplicativos não confiáveis a uma área restrita, garantindo que eles não tenham impacto na segurança do sistema. O sistema operacional inteiro é segmentado em seções seguras, com cada seção blindada por uma combinação de diferentes tecnologias de segurança.
  
  * **Proteção de dados**: se o dispositivo do usuário for perdido ou roubado, o HoloLens 2 impedirá que aplicativos não autorizados leiam informações confidenciais apoiado na criptografia de dados BitLocker. 
  
  * **Sistema operacional sem senha**: os sistemas operacionais mais antigos e baseados em senhas poderiam expor inadvertidamente os usuários a ameaças de phishing e eram frequentemente responsáveis por contas comprometidas. O Windows Holographic for Business elimina o uso de senhas para a entrada no MSA e no AAD, além de fortalecer a proteção da identidade do usuário com o logon do Windows Hello™ e FIDO2. 
  
    > [!NOTE]
    > Para ter o suporte do FIDO2, o dispositivo deve estar no Build 19041 ou superior. 

  * **Segurança de rede**: o HoloLens 2 oferece ao usuário maior segurança de rede por meio de configurações padrão e protocolos aprimorados.
