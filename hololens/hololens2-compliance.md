---
title: Conformidade e GDPR do HoloLens 2
description: Documentação do GDPR
keywords: HoloLens, GDPR, privacidade, PII
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308253"
---
# <a name="hololens-2-privacy-statement"></a>Política de privacidade do HoloLens 2

Um dos principais elementos do GDPR é a ' proteção de dados por design '. Esse conceito se aplica especialmente a dispositivos móveis, como o HoloLens 2, devido à sua portabilidade, conexões de Internet ilimitadas e canais de comunicação abertos. Por conseqüência, a [segurança](https://docs.microsoft.com/hololens/security-architecture) do HoloLens 2 foi reprojetada para fornecer segurança avançada, inovadora e proteção de privacidade, de ponta a ponta, incorporando a abordagem da Microsoft às [normas de privacidade e GDPR](https://privacy.microsoft.com/).

 >[!NOTE]
> Este documento não se aplica ao HoloLens (1ª gen).

## <a name="privacy-overview"></a>Visão geral de privacidade

O HoloLens 2 é um computador independente do Windows, executando o Windows Holographic, que executa aplicativos e soluções em um ambiente de realidade misturada imersiva. Ele pode ser usado como um dispositivo offline seguro ou implantado como um [dispositivo gerenciado](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) na sua organização. Consulte os links a seguir para entender como o HoloLens 2 e a Microsoft usam e protege seus dados:
1. [Política de privacidade da Microsoft-HoloLens](https://privacy.microsoft.com/privacystatement) – expanda a seção **Enterprise e Developer** no menu de navegação à esquerda e selecione **software e dispositivos empresariais e de desenvolvedor**. Vá para a seção **HoloLens** .
2.  [Windows 10 e seu serviços online](https://privacy.microsoft.com/windows10privacy)
3.  [Guia de conformidade de privacidade do Windows 10 &](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Dados pessoais e privacidade no Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Segurança de rede
Seguindo os cenários de [implantação comum](https://docs.microsoft.com/hololens/common-scenarios)do HoloLens 2, seus dados serão protegidos pela [conformidade de nível mundial do Azure](https://docs.microsoft.com/azure/compliance/) junto com a integração de padrões legais/regulatórios. Se você for novo no Azure AD e no Dynamics 365 Remote Assist, consulte a [lista de verificação de preparação de responsabilidade do Azure e dynamics 365 para o GDPR](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics).

Além disso, o Windows Defender Firewall oferece funcionalidade crítica para proteger a conectividade do dispositivo. Com o HoloLens 2, o firewall está sempre habilitado e não há maneiras de desabilitá-lo programaticamente ou por meio da interface do usuário. Quando o HoloLens 2 é implantado como um dispositivo gerenciado usando o [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started), mais funcionalidade de conformidade está disponível com a integração para o [ponto de extremidade com o Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) como uma solução de defesa contra ameaças móveis. 

Saiba mais sobre a [segurança e a arquitetura](https://docs.microsoft.com/hololens/security-architecture)do HoloLens 2.

## <a name="os-security"></a>Segurança do so
As atualizações são feitas automaticamente (por padrão) para que seu HoloLens 2 esteja sempre atualizado com a versão mais recente do Windows Holographic e todos os aplicativos instalados. Consulte o seguinte para entender mais sobre como nosso sistema operacional é projetado com segurança:
1. [Separação de estado e isolamento](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Sistema operacional sem administrador](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Limitando o uso de senha](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Segurança física
O HoloLens 2 tem memória flash protegida pela [criptografia BitLocker](https://docs.microsoft.com/hololens/security-encryption-data-protection). Seu dispositivo e seus dados locais podem ser offline off-line usando o [complemento de recuperação avançada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) ou apagados remotamente por meio do MDM se ele tiver sido implantado como um dispositivo gerenciado.

## <a name="data-protection"></a>Proteção de dados
As atualizações do Windows são executadas automaticamente (por padrão) e a [integração do Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) protege os dados que trafegam entre si e a nuvem. 

Ao implantar o HoloLens 2 em clientes externos, a [assistência remota do Dynamics 365](https://docs.microsoft.com/hololens/hololens2-deployment-guide) garante que seus dados e recursos da empresa confidenciais sejam separados e seguros. 

O compartilhamento de dados de diagnóstico com a Microsoft pode ser configurado manualmente pelo MDM ou pelo usuário durante o OOBE. Há duas opções: dados de diagnóstico opcionais e dados de diagnóstico necessários. Se a configuração de diagnóstico original precisar ser alterada posteriormente para fins de solução de problemas, ela poderá ser alterada pelo usuário em **configurações-> privacidade-> diagnóstico & comentários** ou o administrador de ti (MDM) se for um dispositivo gerenciado. Veja mais sobre [diagnósticos, comentários e privacidade no Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Os logs de diagnóstico do dispositivo contêm informações de identificação pessoal (PII), como sobre quais processos ou aplicativos o usuário inicia durante operações típicas. Quando vários usuários compartilham um dispositivo do HoloLens (por exemplo, os usuários entram no mesmo dispositivo usando contas diferentes do Microsoft Azure Active Directory (AD do Azure)), os logs de diagnóstico podem conter informações de PII que se aplicam a vários usuários.

 

Há [vários métodos de coleta e políticas de retenção de dados](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) para coletar dados de diagnóstico do HoloLens 2.  Para obter mais informações sobre como a Microsoft coleta e usa dados de diagnóstico, consulte [política de privacidade da Microsoft-diagnóstico](https://privacy.microsoft.com/privacystatement) -expanda **Windows** no menu de navegação à esquerda e selecione **diagnóstico**. Vá para a seção **diagnóstico** .
