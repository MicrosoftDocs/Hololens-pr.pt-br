---
title: Atestado de integridade e de tempo de execução com suporte para hardware
description: limitando o uso de senha para o holoLens
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, integridade com suporte para hardware, atestado de tempo de execução, UEFI, inicialização segura de UEFI, inicialização segura, TPM, proteção contra ameaças, garantia de antipersistência do Windows, integridade do código, proteção de código,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens 2
ms.openlocfilehash: d1a3fe02b64ce1566806119e5309fd262667b181
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865647"
---
# Atestado de integridade e de tempo de execução com suporte para hardware

A integridade e o atestado de tempo de execução com suporte para hardware protegem contra ameaças que se originam antes do início de um sistema operacional, durante o tempo de execução, quando o dispositivo usa hardware e os serviços de atestado remoto para garantir que a integridade seja mantida durante a inicialização e durante toda a duração do tempo de execução.

## Inicialização segura UEFI

O HoloLens 2 impõe a Inicialização Segura da Interface Unificada de Firmware Extensível (UEFI) e somente a UEFI inicializa o Windows Holographic for Business.
A Inicialização Segura garante que todo o conjunto de inicialização seja verificado quanto à integridade, e que o Windows sempre inicialize com as políticas de segurança corretas. Para saber mais sobre a inicialização segura, clique aqui.

## TPM

O TPM (Trusted Platform Module) é um chip especializado em um dispositivo de ponto de extremidade. O HoloLens 2 usa um TPM 2.0 que fornece o isolamento de chave imposta por hardware.

## Proteção contra ameaças de acesso persistentes

O objetivo da maioria dos ataques cibernéticos é manter o acesso persistente a um dispositivo. Para o crime cibernético, manter essa persistência permite que um dispositivo Windows comprometido participe de um botnet, venda o acesso ao dispositivo para usuários desonestos, ou habilite o roubo repetido de dados. No mundo dos ataques direcionados, a persistência é essencial para um ataque cibernético bem-sucedido, seja em um dispositivo ou (mais comum), em toda a rede.  

Na verdade, os ataques direcionados são considerados "ameaças persistentes avançadas", devido à necessidade estratégica de manter o acesso a um dispositivo de destino ou rede. Por esse motivo, o Windows Holographic for Business considera a defesa contra a persistência absolutamente fundamental e usa a tecnologia de antipersistência para fazer uma promessa de segurança do cliente robusta.

### Inicialização segura 

O HoloLens 2 impõe a Inicialização Segura da Interface Unificada de Firmware Extensível (UEFI) em todo o estado do sistema operacional principal. A UEFI inicializa somente as plataformas confiáveis da Microsoft, garantindo que todo o conjunto de inicialização seja verificado quanto à integridade, e que o Windows sempre inicialize com as políticas de segurança corretas. O HoloLens 2 não segura a inicialização para ser desabilitada, nem permite carregadores de inicialização de terceiros.

> [!Tip]
> Saiba mais sobre a [Inicialização Segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Garantia de antipersistência do Windows

A antipersistência do HoloLens 2 garante que seus usuários, mesmo na situação rara em que um comprometimento de tempo de execução do sistema tenha ocorrido, como uma exploração remota, tal evento seria minimizado com todo o código mal-intencionado removido do sistema, simplesmente removendo o dispositivo. Para reforçar ainda mais a antipersistência, o HoloLens 2 adicionou proteção de integridade avançada e colocou as proteções somente leitura no local.

A persistência aos dados do sistema operacional na forma de dados ainda é possível, a menos que o usuário execute o PBR (botão de redefinição por push) do dispositivo que apaga todas as partições mutais. Embora a persistência a partições imutáveis seja muito mais difícil, o usuário precisa PBR o Hololens 2 para remover qualquer possível persistência de ameaças de partes mutáveis.

## Política de integridade de código 

A integridade de código (CI) é uma importante propriedade de segurança de um sistema operacional moderno. A imposição da CI habilita decisões coerentes de segurança, pois garante que a proveniência do código seja transparente para o usuário e o sistema operacional. A integridade de código completa precisa estender a assinatura além das imagens binárias e incluir imposição de tempo de execução, como a integridade do fluxo de controle e restrições de código dinâmico. A CI é fundamental para a prevenção de várias classes de ataques, incluindo malware com engenharia social, como ransomware, exploits de execução de código remoto e várias outras classes de ataque.