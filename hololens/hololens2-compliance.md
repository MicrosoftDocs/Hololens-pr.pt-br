---
title: Conformidade e RGPD do HoloLens 2
description: Documentação do RGPD
keywords: HoloLens, RGPD, privacidade, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324864"
---
# Política de Privacidade do HoloLens 2

Um dos principais elementos do RGPD é a "proteção de dados por design". Esse conceito se aplica especialmente a dispositivos móveis, como o HoloLens 2, devido à sua portabilidade, conexões ilimitadas com a Internet e canais de comunicação abertos. Como resultado, a segurança do HoloLens 2 foi reprojetada para fornecer proteção avançada e inovadora de segurança e privacidade, de ponta a ponta, incorporando a abordagem da Microsoft à privacidade e aos regulamentos do [RGPD.](https://privacy.microsoft.com/) [](https://docs.microsoft.com/hololens/security-architecture)

 >[!NOTE]
> Este documento não se aplica ao HoloLens (1ª geração).

## Visão geral da privacidade

O HoloLens 2 é um computador Windows autônomo, executando o Windows Holographic, que executa aplicativos e soluções em um ambiente imersivo de realidade misturada. Ele pode ser usado como um dispositivo offline seguro ou implantado como um [dispositivo gerenciado](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) em sua organização. Confira os links a seguir para entender como o HoloLens 2 e a Microsoft usam e protegem seus dados:
1. [Política de Privacidade da Microsoft – HoloLens](https://privacy.microsoft.com/privacystatement) – expanda a seção Enterprise e **desenvolvedor** no menu de navegação esquerdo e selecione software e **dispositivos corporativos**e de desenvolvedor. Vá para a **seção HoloLens.**
2.  [Windows 10 e seus serviços online](https://privacy.microsoft.com/windows10privacy)
3.  [Guia Windows 10 e conformidade com a privacidade](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Privacidade e dados pessoais no Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## Segurança de rede
Seguindo os [cenários](https://docs.microsoft.com/hololens/common-scenarios)de implantação comuns do HoloLens 2, seus dados serão protegidos pela conformidade mundial do [Azure,](https://docs.microsoft.com/azure/compliance/) juntamente com a integração de padrões legais/regulamentadores. Se você for novo no Azure AD e na Assistência Remota do Dynamics 365, consulte a lista de verificação de preparação de responsabilidade do Azure e do [Dynamics 365](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)para o RGPD.

Além disso, o Windows Defender Firewall oferece funcionalidades críticas para proteger a conectividade do dispositivo. Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo programaticamente ou por meio da interface do usuário. Quando o HoloLens 2 é implantado como um dispositivo gerenciado usando o [Intune,](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)mais funcionalidade de conformidade está disponível com a integração do ponto de extremidade com o [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) como uma solução de defesa contra ameaças móveis. 

Saiba mais sobre a arquitetura e segurança do HoloLens [2.](https://docs.microsoft.com/hololens/security-architecture)

## Segurança do sistema operacional
As atualizações são feitas automaticamente (por padrão) para que o HoloLens 2 sempre seja atualizado com a versão mais recente do Windows Holographic e de todos os aplicativos instalados. Consulte o seguinte para entender mais sobre como nosso sistema operacional foi projetado com segurança:
1. [Separação e isolamento de estado](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Sistema Operacional sem Administrador](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Limitando o uso de senha](https://docs.microsoft.com/hololens/security-limiting-password-use)

## Segurança física
O HoloLens 2 tem memória flash protegida pela [criptografia BitLocker.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Seu dispositivo e seus dados locais podem ser piscados offline usando o [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ou apagados remotamente via MDM se ele tiver sido implantado como um dispositivo gerenciado.

## Proteção de dados
As atualizações do Windows são executados automaticamente (por padrão) e a integração com o [Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) protege os dados que viajam entre si e a nuvem. 

Ao implantar o HoloLens 2 em clientes externos, a Assistência Remota do [Dynamics 365](https://docs.microsoft.com/hololens/hololens2-deployment-guide) garante que os dados e recursos confidenciais da empresa sejam separados e seguros. 

O compartilhamento de dados de diagnóstico com a Microsoft pode ser configurado manualmente pelo MDM ou pelo usuário durante o OOBE. Há duas opções: dados de diagnóstico opcionais e dados de diagnóstico obrigatórios. Se a configuração de diagnóstico original precisar ser alterada posteriormente para fins de solução de problemas, ela poderá ser alterada pelo usuário em Configurações -> Privacidade -> Comentários sobre **diagnósticos &** ou administrador de IT (MDM) se for um dispositivo gerenciado. Veja mais sobre [diagnóstico, comentários e privacidade no Windows 10.](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> Os logs de diagnóstico de dispositivo contêm informações de identificação pessoal (PII), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. Quando vários usuários compartilham um dispositivo HoloLens (por exemplo, os usuários podem entrar no mesmo dispositivo usando contas diferentes do Microsoft Azure Active Directory (Azure AD), os logs de diagnóstico podem conter informações de PII que se apliquem a vários usuários.

 

Há vários [métodos de coleta e políticas de retenção de dados para](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) coletar dados de diagnóstico do HoloLens 2.  Para obter mais informações sobre como a [Microsoft](https://privacy.microsoft.com/privacystatement) coleta e usa dados de diagnóstico, consulte a Política de Privacidade da Microsoft - Diagnóstico - expanda **o Windows** no menu de navegação esquerdo e selecione **Diagnóstico.** Vá para a **seção Diagnóstico.**
