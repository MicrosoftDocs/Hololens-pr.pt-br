---
title: Atestado de integridade e de tempo de execução com suporte para hardware
description: Atestado de integridade e de tempo de execução com suporte para hardware
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: segurança, hololens, integridade com suporte para hardware, atestado de tempo de execução, UEFI, inicialização segura de UEFI, inicialização segura, TPM, proteção contra ameaças, garantia de antipersistência do Windows, integridade do código, proteção de código,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340520"
---
# Atestado de integridade e de tempo de execução com suporte para hardware

A integridade e o atestado de tempo de execução com suporte para hardware protegem contra ameaças que se originam antes do início de um sistema operacional, durante o tempo de execução, quando o dispositivo usa hardware e os serviços de atestado remoto para garantir que a integridade seja mantida durante a inicialização e durante toda a duração do tempo de execução.

## Inicialização segura UEFI

O HoloLens 2 sempre impõe a Inicialização segura da Interface Unificada de Firmware Extensível (UEFI), e somente a UEFI inicializa o Windows Holographic for Business.
A Inicialização Segura garante que todo o conjunto de inicialização seja verificado quanto à integridade, e que o Windows sempre inicialize com as políticas de segurança corretas. Saiba mais sobre a [Inicialização segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

## TPM

O TPM (Trusted Platform Module) é um chip especializado em um dispositivo de ponto de extremidade. O HoloLens 2 usa um TPM 2.0 que fornece isolamento de chave imposta por hardware. Saiba mais sobre os [conceitos básicos do TPM](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals).

## Proteção contra ameaças de acesso persistente

O objetivo da maioria dos ataques cibernéticos é manter o acesso persistente a um dispositivo. Para o crime cibernético, manter essa persistência permite que um dispositivo Windows comprometido participe de um botnet, venda o acesso ao dispositivo para usuários desonestos, ou habilite o roubo repetido de dados. No mundo dos ataques direcionados, a persistência é essencial para um ataque cibernético bem-sucedido, seja em um dispositivo ou (mais comum), em toda a rede.  

Na verdade, os ataques direcionados são considerados "ameaças persistentes avançadas", devido à necessidade estratégica de manter o acesso a um dispositivo de destino ou rede. Por esse motivo, o Windows Holographic for Business considera a defesa contra a persistência absolutamente fundamental e usa a tecnologia de antipersistência para fazer uma promessa de segurança do cliente robusta.

### Inicialização segura

O HoloLens 2 impõe a Inicialização segura da Interface Unificada de Firmware Extensível (UEFI) em todos os estados do sistema operacional principal. Somente a UEFI inicializa as plataformas confiáveis da Microsoft, o que garante que toda a cadeia de inicialização seja verificada quanto à integridade, e que o Windows seja sempre inicializado com as políticas de segurança corretas aplicadas a ela. O HoloLens 2 não desativa a Inicialização segura, nem permite carregadores de inicialização de terceiros.

> [!Tip]
> Saiba mais sobre a [Inicialização Segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Garantia de antipersistência do Windows

A antipersistência do HoloLens 2 garante que seus usuários, mesmo na situação rara em que um comprometimento de tempo de execução do sistema tenha ocorrido, como uma exploração remota, tal evento seria minimizado com todo o código mal-intencionado removido do sistema, simplesmente removendo o dispositivo. Para reforçar ainda mais a antipersistência, o HoloLens 2 adicionou proteção de integridade avançada e colocou as proteções somente leitura no local.

A persistência aos dados do sistema operacional na forma de dados ainda é possível, a menos que o usuário execute o PBR (botão de redefinição por push) do dispositivo que apaga todas as partições mutais. Embora a persistência em partições imutáveis ​​seja muito mais difícil, o usuário precisa executar o PBR do HoloLens 2 para remover qualquer possível persistência de ameaças de partes mutáveis.

## Política de integridade de código

A integridade de código (CI) é uma importante propriedade de segurança de um sistema operacional moderno. A imposição da CI habilita decisões coerentes de segurança, pois garante que a proveniência do código seja transparente para o usuário e o sistema operacional. A integridade de código completa precisa estender a assinatura além das imagens binárias e incluir imposição de tempo de execução, como a integridade do fluxo de controle e restrições de código dinâmico. A CI é fundamental para a prevenção de várias classes de ataques, incluindo malware com engenharia social, como ransomware, exploits de execução de código remoto e várias outras classes de ataque.
