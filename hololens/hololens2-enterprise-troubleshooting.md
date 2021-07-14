---
title: Implementação de HoloLens 2 e solução de problemas de dispositivo gerenciado
description: Solução de problemas de dispositivos HoloLens 2 em um ambiente corporativo
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Solucionar problemas
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961494"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Solução de problemas de implementação e dispositivos gerenciados 

Este artigo descreve como resolver vários problemas ou responder a perguntas sobre a implementação e o gerenciamento do HoloLens 2.

>[!IMPORTANT]
> Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de **20% a 40%** da capacidade da bateria, se possível. As [luzes indicadoras de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas sob o botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.


<a id="list"></a>
- [Solução de problemas de EAP](#eap-troubleshooting)
- [Solução de problemas de Wi-Fi](#wi-fi-troubleshooting)
- [Solução de problemas de rede](#network-troubleshooting)
- [Não é possível entrar em um dispositivo HoloLens configurado anteriormente](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Não é possível fazer logon após a atualização para Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Solução de problemas do Autopilot](#autopilot-troubleshooting)
- [Perguntas frequentes sobre dispositivos HoloLens gerenciados](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Solução de problemas de EAP
1. Verifique se o perfil do Wi-Fi tem as configurações corretas:
    - O tipo EAP está configurado corretamente, tipos EAP comuns: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).
    - O nome Wi-Fi SSID está correto e corresponde à cadeia de caracteres hexadecimal.
    - Para EAP-TLS, TrustedRootCA contém o hash SHA-1 do Certificado de Autoridade de Certificação raiz confiável do servidor. No computador Windows, o comando "certutil.exe -dump cert_file_name" mostrará a string de hash SHA-1 de um certificado.
2. Colete a captura de pacotes de rede no Ponto de Acesso ou nos logs do servidor AAA para descobrir onde a sessão EAP falha.
    - Se a identidade EAP fornecida pelo HoloLens não for esperada, verifique se a identidade foi provisionada corretamente por meio do perfil Wi-Fi ou do certificado do cliente.
    - Se o servidor rejeitar o certificado de cliente do HoloLens, verifique se o certificado de cliente necessário foi provisionado no dispositivo.
    - Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de Autoridade de Certificação raiz do servidor foi provisionado no HoloLens.
3. Se o perfil da empresa for provisionado pelo pacote de provisionamento do Wi-Fi, considere a aplicação do pacote de provisionamento em um computador com o Windows 10. Se também falhar no computador com Windows 10, siga o guia de solução de problemas de autenticação 802.1X do cliente Windows.
4. Envie-nos comentários por meio do Hub de Comentários.

[Voltar para a lista](#list)

## <a name="wi-fi-troubleshooting"></a>Solução de problemas de Wi-Fi

Aqui estão algumas ações que você pode tentar se não conseguir conectar seu HoloLens a uma rede Wi-Fi:

1. Verifique se o Wi-Fi está ligado. Para verificar, use o gesto Iniciar e escolha Configurações > Rede e Internet > Wi-Fi. Se o Wi-Fi estiver ligado, tente desligá-lo e, em seguida, ligue novamente.
2. Aproxime-se do roteador ou do ponto de acesso.
3. Reinicie o roteador Wi-Fi e, em seguida, reinicie o HoloLens. Tente se conectar novamente.
4. Se nenhuma dessas ações funcionar, verifique se o roteador está usando o firmware mais recente. Você pode encontrar essas informações no site do fabricante.

Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.

## <a name="network-troubleshooting"></a>Solução de problemas de rede
Se os problemas de rede forem um obstáculo para a implantação e uso bem-sucedido do HoloLens 2 em sua organização, veja como duas ferramentas de diagnóstico de rede conhecidas, Fiddler e Wireshark, podem ajudá-lo a verificar, diagnosticar e identificar problemas. Confira este [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) para obter mais detalhes.

[Voltar para a lista](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Não é possível entrar em um dispositivo HoloLens configurado anteriormente

Se o seu dispositivo foi configurado anteriormente para outra pessoa, seja para um cliente ou ex-funcionário, e você não tem a senha para desbloquear o dispositivo, pode usar o Intune para [limpar](https://docs.microsoft.com/intune/remote-actions/devices-wipe) remotamente o dispositivo. Em seguida, o dispositivo aplica reflash automaticamente.  
> [!IMPORTANT]
> Ao limpar o dispositivo, deixe **Reter estado de inscrição e conta de usuário** desmarcado.
[Voltar para a lista](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Não é possível fazer logon após a atualização para Windows Holographic 21H1

### <a name="symptoms"></a>Sintomas
- O uso do PIN para logon falhará depois de inserir o PIN correto.
- O uso do método de logon da Web falhará depois de entrar com êxito na página da Web.
- O dispositivo não está listado como “Ingressado no Azure Active Directory” no [ portal do Azure ](https://portal.azure.com/) -> Azure Active Directory -> Dispositivos.

### <a name="cause"></a>Causa
O dispositivo afetado pode ter sido excluído do locatário do Azure Active Directory. Por exemplo, isso pode acontecer porque:

- Um administrador ou usuário excluiu o dispositivo no portal do Azure ou usando o PowerShell.
- O dispositivo foi removido do locatário do Azure Active Directory devido à inatividade. Para um ambiente gerenciado com eficiência, normalmente recomendamos que os administradores de TI removam dispositivos antigos e inativos de seu locatário do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).

Quando um dispositivo afetado tentar entrar em contato com o locatário do Azure Active Directory novamente depois que ele tiver sido excluído, ele não será autenticado com o Azure Active Directory. Esse efeito geralmente é invisível para o usuário do dispositivo, pois o logon armazenado em cache via PIN continuará permitindo que o usuário logon.

### <a name="mitigation"></a>Atenuação
Atualmente, não há como adicionar um dispositivo HoloLens excluído de volta ao Azure Active Directory. Os dispositivos afetados precisarão ser limpos novamente seguindo as instruções sobre [como fazer reflash no seu dispositivo](hololens-recovery.md#clean-reflash-the-device).

## <a name="autopilot-troubleshooting"></a>Solução de problemas do Autopilot

Os artigos a seguir podem ser um recurso útil para obter mais informações e solucionar problemas do Autopilot. No entanto, esteja ciente de que esses artigos são baseados no Windows 10 Desktop e nem todas as informações são aplicadas ao HoloLens:

- [Windows Autopilot: problemas conhecidos](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Solucionar problemas de registro de dispositivo Windows no Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: Conflitos de Política](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Perguntas frequentes sobre dispositivos HoloLens gerenciados

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Posso usar o SCCM (System Center Configuration Manager) para gerenciar dispositivos HoloLens?

Não. Você precisa usar um sistema MDM para gerenciar dispositivos HoloLens.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Posso usar o AD DS (Active Directory Domain Services) para gerenciar contas de usuário do HoloLens?

Não. Você precisa usar o Azure Active Directory para gerenciar contas de usuário para dispositivos HoloLens.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>O HoloLens consegue registrar automaticamente o ADCS (Sistemas de Captura de Dados Automatizados)?

Não.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>O HoloLens pode participar da autenticação integrada do Windows?

Não.

### <a name="does-hololens-support-branding"></a>O HoloLens permite identidade visual?

Não. No entanto, você pode contornar esse problema usando uma das seguintes abordagens:

- Crie um aplicativo personalizado e, em seguida, [habilite o modo de quiosque](hololens-kiosk.md). O aplicativo personalizado pode ter identidade visual e pode iniciar outros aplicativos (como o Remote Assist).  
- Mude todas as imagens de perfil do usuário no Azure Active Directory para o logotipo da sua empresa. No entanto, isso pode não ser desejável para todos os cenários.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Quais recursos de registro em log o HoloLens 2 oferece?

O registro em log é limitado a rastreamentos que podem ser capturados em cenários de desenvolvimento ou solução de problemas ou telemetria que os dispositivos enviam aos servidores da Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Perguntas sobre como proteger dispositivos HoloLens

Confira [nossas informações de segurança do HoloLens 2](security-overview.md).
Para dispositivos HoloLens de primeira geração, confira [estas perguntas frequentes](hololens1-faq-security.md).

[Voltar para a lista](#list)
