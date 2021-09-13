---
title: Proteção de dados e privacidade do HoloLens 2
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031955"
---
# <a name="hololens-2-privacy-and-data-protection"></a>Proteção de dados e privacidade do HoloLens 2

Um dos principais elementos do GDPR é a ' proteção de dados por design '. esse conceito se aplica especialmente a dispositivos móveis, como o HoloLens 2, devido à sua portabilidade, conexões de internet ilimitadas e canais de comunicação abertos. em consequência, a [segurança](/hololens/security-architecture) de HoloLens 2 foi reprojetada para fornecer segurança avançada, inovadora e proteção de privacidade, de ponta a ponta, incorporando a abordagem da Microsoft às normas de [privacidade e GDPR](https://privacy.microsoft.com/).

 >[!NOTE]
> este documento não se aplica a HoloLens (1ª gen).

## <a name="privacy-overview"></a>Visão geral de privacidade

HoloLens 2 é um computador de Windows autônomo, executando Windows Holographic, que executa aplicativos e soluções em um ambiente de realidade misturada imersiva. Ele pode ser usado como um dispositivo offline seguro ou implantado como um [dispositivo gerenciado](/mem/intune/fundamentals/windows-holographic-for-business) na sua organização. consulte os links a seguir para entender como o HoloLens 2 e a Microsoft usam e protege seus dados:

1. [política de privacidade da Microsoft-HoloLens](https://privacy.microsoft.com/privacystatement) – expanda a seção **Enterprise e desenvolvedor** no menu de navegação à esquerda e selecione **Enterprise e software e dispositivos de desenvolvedor**. vá para a seção **HoloLens** .
2. [Windows 10 e seu serviços online](https://privacy.microsoft.com/windows10privacy)
3. [guia de conformidade de privacidade do Windows 10 &](/windows/privacy/windows-10-and-privacy-compliance)
4. [Dados pessoais e privacidade no Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Segurança de rede
seguindo os cenários de [implantação comuns](/hololens/common-scenarios)do HoloLens 2, seus dados serão protegidos pela [conformidade de nível mundial do Azure](/azure/compliance/) junto com a integração de padrões legais/regulatórios. Se você for novo no Azure AD e no Dynamics 365 Remote Assist, consulte a [lista de verificação de preparação de responsabilidade do Azure e dynamics 365 para o GDPR](/compliance/regulatory/gdpr-arc-azure-dynamics).

além disso, Windows Defender Firewall oferece funcionalidade crítica para proteger a conectividade do dispositivo. Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo por programação ou pela interface do usuário. quando o HoloLens 2 é implantado como um dispositivo gerenciado usando o [Intune](/mem/intune/protect/device-compliance-get-started), mais funcionalidade de conformidade está disponível com a integração para o [ponto de extremidade com Microsoft Intune](/mem/intune/protect/advanced-threat-protection) como uma solução de defesa contra ameaças móveis.

saiba mais sobre a [segurança e a arquitetura](/hololens/security-architecture)do HoloLens 2.

## <a name="os-security"></a>Segurança do so
as atualizações são feitas automaticamente (por padrão) para que o seu HoloLens 2 esteja sempre atualizado com a versão mais recente do Windows Holographic e quaisquer aplicativos instalados. Consulte o seguinte para entender mais sobre como nosso sistema operacional é projetado com segurança:

1. [Separação e isolamento de estado](/hololens/security-state-separation-isolation)
1. [Sistema operacional sem administrador](/hololens/security-adminless-os)
1. [Limitando o uso de senha](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Segurança física
HoloLens 2 tem memória flash protegida pela [criptografia BitLocker](/hololens/security-encryption-data-protection). Seu dispositivo e seus dados locais podem ser offline off-line usando o [complemento de recuperação avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ou apagados remotamente por meio do MDM se ele tiver sido implantado como um dispositivo gerenciado.

## <a name="data-protection"></a>Proteção de dados
Windows atualizações são executadas automaticamente (por padrão) e a [integração do Azure](/hololens/security-encryption-data-protection#Azure-integration) protege os dados que trafegam entre si mesmo e a nuvem.

ao implantar o HoloLens 2 para clientes externos, o dynamic [Assist do Dynamics 365](/hololens/hololens2-deployment-guide) garante que seus dados e recursos da empresa confidenciais sejam separados e seguros.

O compartilhamento de dados de diagnóstico com a Microsoft pode ser configurado manualmente pelo MDM ou pelo usuário durante o OOBE. Há duas opções: dados de diagnóstico opcionais e dados de diagnóstico necessários. se a configuração de diagnóstico original precisar ser alterada posteriormente para fins de solução de problemas, ela poderá ser alterada pelo usuário em **Configurações > privacidade-> diagnóstico & comentários** ou o administrador de ti (MDM) se for um dispositivo gerenciado. Veja mais sobre [diagnósticos, comentários e privacidade em Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Os logs de diagnóstico do dispositivo contêm informações de identificação pessoal (PII), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. quando vários usuários compartilham um dispositivo de HoloLens (por exemplo, os usuários entram no mesmo dispositivo usando contas diferentes do Microsoft Azure Active Directory (AD do Azure)), os logs de diagnóstico podem conter informações de PII que se aplicam a vários usuários.

há [vários métodos de coleta e políticas de retenção de dados](/hololens/hololens-diagnostic-logs) para coletar dados de diagnóstico do HoloLens 2.  para obter mais informações sobre como a Microsoft coleta e usa dados de diagnóstico, consulte [política de privacidade da microsoft-diagnóstico](https://privacy.microsoft.com/privacystatement) -expanda **Windows** no menu de navegação à esquerda e selecione **diagnóstico**. Vá para a seção **diagnóstico** .
