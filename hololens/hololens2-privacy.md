---
title: HoloLens 2 Privacidade e Proteção de Dados
description: Documentação de privacidade
keywords: HoloLens, GDPR, privacidade, PII, proteção de dados
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: 548550f309010fa95f674a7ff688166a31cf1963
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2021
ms.locfileid: "122336728"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 Privacidade e Proteção de Dados

Um dos principais elementos do GDPR é a "proteção de dados por design". Esse conceito se aplica especialmente a dispositivos móveis, como o HoloLens 2, devido à portabilidade, conexões ilimitadas à Internet e canais de comunicação abertos. Como resultado, a segurança do HoloLens [](/hololens/security-architecture) 2 foi reprojetada para fornecer proteção avançada e inovadora de segurança e privacidade, de ponta a ponta, incorporando a abordagem da Microsoft aos regulamentos de privacidade e [GDPR.](https://privacy.microsoft.com/)

 >[!NOTE]
> Este documento não se aplica a HoloLens (1ª geração).

## <a name="privacy-overview"></a>Visão geral da privacidade

HoloLens 2 é um computador autônomo Windows, executando o Windows Holographic, que executa aplicativos e soluções em um ambiente imersivo de realidade misturada. Ele pode ser usado como um dispositivo offline seguro ou implantado como um [dispositivo gerenciado](/mem/intune/fundamentals/windows-holographic-for-business) em sua organização. Consulte os links a seguir para entender como o HoloLens 2 e a Microsoft usa e protege seus dados:

1. [Política de Privacidade](https://privacy.microsoft.com/privacystatement) da Microsoft –  HoloLens – expanda a seção Enterprise e desenvolvedor no menu de navegação à esquerda e selecione Enterprise software e dispositivos para **desenvolvedores.** Vá para a **HoloLens.**
2. [Windows 10 e seu serviços online](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & De conformidade de privacidade do Windows 10 &](/windows/privacy/windows-10-and-privacy-compliance)
4. [Dados pessoais e privacidade no Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Segurança de rede
Seguindo o HoloLens 2 [Cenários](/hololens/common-scenarios)comuns de implantação, seus dados serão protegidos pela conformidade de nível mundial do [Azure,](/azure/compliance/) juntamente com a integração de padrões legais/regulatórios. Se você for novo no Azure AD e no Dynamics 365 Remote Assist, consulte a lista de verificação de preparação de responsabilidade do [Azure e do Dynamics 365](/compliance/regulatory/gdpr-arc-azure-dynamics)para o GDPR.

Além disso, Windows Defender Firewall fornece funcionalidade crítica para proteger a conectividade do dispositivo. Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo por programação ou pela interface do usuário. Quando o HoloLens 2 é implantado como um dispositivo gerenciado usando o [Intune,](/mem/intune/protect/device-compliance-get-started)mais funcionalidades de conformidade estão disponíveis com a integração do Ponto de Extremidade com o [Microsoft Intune](/mem/intune/protect/advanced-threat-protection) como uma solução de Defesa contra Ameaças Móveis.

Saiba mais sobre a segurança HoloLens 2 [e a arquitetura do](/hololens/security-architecture).

## <a name="os-security"></a>Segurança do sistema operacional
As atualizações são feitas automaticamente (por padrão) para que o HoloLens 2 sempre seja atualizado com a versão mais recente do Windows Holographic e todos os aplicativos instalados. Confira o seguinte para entender mais sobre como nosso sistema operacional foi projetado com segurança:

1. [Separação e isolamento de estado](/hololens/security-state-separation-isolation)
1. [Sistema operacional sem administrador](/hololens/security-adminless-os)
1. [Limitando o uso de senha](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Segurança física
HoloLens 2 tem memória flash protegida pela [criptografia BitLocker](/hololens/security-encryption-data-protection). Seu dispositivo e seus dados locais poderão ser flashados offline usando o Advanced [Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ou apagados remotamente por meio do MDM se ele tiver sido implantado como um dispositivo gerenciado.

## <a name="data-protection"></a>Proteção de dados
Windows atualizações são executados automaticamente (por padrão) e a integração do [Azure](/hololens/security-encryption-data-protection#Azure-integration) protege os dados que viajam entre si e a nuvem.

Ao implantar o HoloLens 2 em clientes [externos, o Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) garante que os dados e os recursos confidenciais da empresa sejam separados e seguros.

O compartilhamento de dados de diagnóstico com a Microsoft pode ser configurado manualmente pelo MDM ou pelo usuário durante o OOBE. Há duas opções: Dados de diagnóstico opcionais e Dados de diagnóstico necessários. Se a configuração de diagnóstico original precisar ser alterada posteriormente para fins de solução de problemas, ela poderá ser alterada pelo usuário no **Configurações -> Privacy -> Diagnostics & Feedback** ou o MDM (Administrador de IT) se for um dispositivo gerenciado. Consulte mais sobre [Diagnóstico, comentários e privacidade no Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Os logs de diagnóstico do dispositivo contêm PII (informações de identificação pessoal), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. Quando vários usuários compartilham um dispositivo HoloLens (por exemplo, os usuários entra no mesmo dispositivo usando contas do Azure AD (Microsoft Azure Active Directory) diferentes), os logs de diagnóstico podem conter informações de PII que se aplica a vários usuários.

Há vários [métodos de coleta e políticas de retenção de dados](/hololens/hololens-diagnostic-logs) para coletar dados de diagnóstico do HoloLens 2.  Para obter mais informações sobre como **a** [Microsoft](https://privacy.microsoft.com/privacystatement) coleta e usa dados de diagnóstico, consulte Política de Privacidade da Microsoft – Diagnóstico – expanda Windows no menu de navegação à esquerda e selecione **Diagnóstico**. Vá para a **seção Diagnóstico.**
