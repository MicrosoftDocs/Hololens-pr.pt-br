---
title: Atestado de runtime e de integridade com suporte para hardware
description: Atestado de runtime e de integridade com suporte para hardware
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: security, hololens, Hardware backed integrity, runtime attestation, UEFI, UEFI secure boot, secure boot, TPM, threat protection, Windows Anti-Persistence Assurance, code integrity, code protection,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034069"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Atestado de runtime e de integridade com suporte para hardware

O atestado de runtime e de integridade com suporte para hardware fornece proteção contra ameaças que se originam antes do início de um sistema operacional, durante o runtime, quando o dispositivo usa um hardware e os serviços de atestado remoto para garantir que a integridade seja mantida durante a inicialização e durante todo o runtime.

## <a name="uefi-secure-boot"></a>Inicialização segura UEFI

O HoloLens 2 sempre impõe a Inicialização Segura UEFI (Unified Extensible Firmware Interface) e somente a UEFI inicializa o Windows Holographic for Business.
A Inicialização Segura garante que toda a cadeia de inicialização seja verificada quanto à integridade e que o Windows seja sempre inicializado com as políticas de segurança corretas aplicadas. Saiba mais sobre a [Inicialização Segura](/windows-hardware/design/device-experiences/oem-secure-boot).

## <a name="tpm"></a>TPM

O TPM (Trusted Platform Module) é um chip especializado em um dispositivo de ponto de extremidade. O HoloLens 2 usa um TPM 2.0, que fornece isolamento de chave imposto por hardware. Saiba mais sobre os [conceitos básicos do TPM](/windows/security/information-protection/tpm/tpm-fundamentals).

## <a name="persistence-access-threat-protection"></a>Proteção contra ameaças de acesso de persistência

A meta da maioria dos ataques cibernéticos é manter o acesso persistente a um dispositivo. Para o crime cibernético, manter essa persistência permite que um dispositivo Windows comprometido seja ingressado em um botnet, venda o acesso ao dispositivo para usuários desonestos ou habilite o roubo repetido de dados. No mundo dos ataques direcionados, a persistência é essencial para um ataque cibernético bem-sucedido, seja em um dispositivo ou (mais comumente) em toda uma rede.  

Na verdade, os ataques direcionados são considerados “ameaças persistentes avançadas”, devido à necessidade estratégica de manter o acesso a um dispositivo ou a uma rede de destino. Por esse motivo, o Windows Holographic for Business considera a proteção contra a persistência absolutamente fundamental e usa a tecnologia de antipersistência para fazer uma promessa de segurança robusta do cliente.

### <a name="secure-boot"></a>Inicialização Segura

O HoloLens 2 impõe a Inicialização Segura UEFI (Unified Extensible Firmware Interface) em todos os estados do sistema operacional principal. A UEFI só inicializa as plataformas confiáveis da Microsoft, o que garante que toda a cadeia de inicialização seja verificada quanto à integridade e que o Windows seja sempre inicializado com as políticas de segurança corretas aplicadas. O HoloLens 2 não desativa a Inicialização Segura nem permite carregadores de inicialização de terceiros.

> [!Tip]
> Saiba mais sobre a [Inicialização Segura](/windows-hardware/design/device-experiences/oem-secure-boot).

### <a name="windows-anti-persistence-assurance"></a>Garantia de antipersistência do Windows

A antipersistência do HoloLens 2 garante aos usuários que, mesmo na rara situação em que tenha ocorrido um comprometimento de runtime do sistema como uma exploração remota, esse evento seja minimizado com todo o código mal-intencionado removido do sistema simplesmente desligando o dispositivo. Para reforçar ainda mais a antipersistência, o HoloLens 2 adicionou uma proteção de integridade avançada e colocou as proteções somente leitura em vigor.

A persistência em dados do sistema operacional na forma de dados ainda é possível, a menos que o usuário execute a PBR (restauração rápida) do dispositivo, que apaga todas as partições mutáveis. Embora a persistência em partições imutáveis ​​seja muito mais difícil, o usuário precisa executar a PBR no HoloLens 2 para remover qualquer possível persistência de ameaças de partes mutáveis.

## <a name="code-integrity-protection"></a>Proteção de integridade de código

A CI (integridade de código) é uma importante propriedade de segurança de um sistema operacional moderno. A imposição da CI habilita decisões coerentes de segurança, pois garante que a proveniência do código seja transparente para o usuário e o sistema operacional. A integridade de código completa precisa estender a assinatura além das imagens binárias e incluir a imposição de runtime, como a integridade do fluxo de controle e as restrições de código dinâmico. A CI é fundamental para a prevenção de várias classes de ataques, incluindo malware com engenharia social, como ransomware, explorações de execução de código remoto e várias outras.
