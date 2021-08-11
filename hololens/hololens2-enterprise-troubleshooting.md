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
ms.openlocfilehash: f038cbf58b6dfaef0395a1ea5b406cce23e4e3fe0464c6bfc1162518f9caf3ff
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659775"
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

[Voltar para a lista](#list)

## <a name="network-troubleshooting"></a>Solução de problemas de rede
Se os problemas de rede são um obstáculo para implantar e usar o HoloLens 2 na sua organização de maneira bem-sucedida, configure o Fiddler e/ou o Wireshark para capturar e analisar o tráfego HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Configurar o Fiddler para capturar o tráfego HTTP
O Fiddler é um proxy de depuração da Web usado para solucionar problemas de HTTP(S). Ele captura todas as solicitações HTTP feitas pelo computador e registra tudo associado a elas. A descoberta de problemas de autenticação do usuário final para seus aplicativos HTTPS gera melhor produtividade e eficiência para seus casos de uso de destino do HoloLens 2. 

#### <a name="prerequisites"></a>Pré-requisitos
 
- Os dispositivos HoloLens 2 e o computador precisam estar na mesma rede
- Anote o endereço IP do computador

#### <a name="install-and-configure-fiddler"></a>Instalar e configurar o Fiddler

1. No computador, [instale](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) e inicie o Fiddler.  
1. No computador, configure o Fiddler para permitir a conexão de computadores remotos.
    1. Acesse Configurações do Fiddler -> Conexões
    1. Anote a porta de escuta do Fiddler (o padrão é 8866)
    1. Marque a opção Permitir a conexão de computadores remotos
    1. Clique em Salvar
3. No HoloLens 2, configure o Fiddler como o servidor proxy<sup>1</sup>:
    1. Abra o menu Iniciar e selecione Configurações
    1. Escolha Rede e Internet e, depois, Proxy no menu à esquerda
    1. Role a página para baixo até Configuração de proxy manual e alterne a opção Usar um servidor proxy para Ativado
    1. Insira o endereço IP do computador em que o Fiddler está instalado
    1. Insira o número da porta indicado acima (o padrão é 8866)
    1. Clique em Salvar

<sup>1</sup> Para builds 20279.1006 e superior (Participantes do Programa Windows Insider e a versão futura), use as seguintes etapas para configurar o proxy:
1. Abra o menu Iniciar e acesse a página Propriedades da rede Wi-Fi 
1. Role até Proxy
1. Altere para Configuração manual
1. Insira o endereço IP do computador em que o Fiddler está instalado
1. Insira o número da porta indicado acima. (O padrão é 8866)
1. Clique em Aplicar
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Descriptografar o tráfego HTTPS por meio do HoloLens 2

1. No computador, exporte o certificado do Fiddler.
    1. Acesse Configurações do Fiddler -> HTTPS e expanda Configurações Avançadas
    2. Clique em Exportar certificado do Fiddler. Ele será salvo na área de trabalho
    3. Mova o certificado para a pasta Downloads no HoloLens 2

2.  No HoloLens 2, importe o certificado do Fiddler.
    1. Acesse Configurações -> Atualização e Segurança -> Certificados
    2. Clique em Instalar Certificado, procure a pasta Downloads e selecione o certificado do Fiddler
    3. Altere a localização do armazenamento para o computador local
    4. Altere o repositório de certificados para a raiz
    5. Selecione Instalar
    6. Confirme se o certificado é exibido na lista de certificados. Caso contrário, repita as etapas acima

#### <a name="inspect-https-sessions"></a>Inspecione as sessões HTTP(S)

No computador, o Fiddler mostrará as sessões ativas do HTTP(S) do HoloLens 2. O painel Inspetores do Fiddler pode mostrar a solicitação/a resposta HTTP(S) em diferentes exibições. Por exemplo, a exibição “Bruto” mostra a solicitação bruta ou a resposta em texto sem formatação. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Configurar o Wireshark para capturar o tráfego de rede
O Wireshark é um analisador de protocolo de rede usado para inspecionar o tráfego TCP/UDP entre seus dispositivos HoloLens 2. Isso facilita a identificação de qual tráfego está atravessando a rede para o HoloLens 2, a quantidade, a frequência, a latência entre determinados saltos etc.

#### <a name="prerequisites"></a>Pré-requisitos:
- O computador precisa ter acesso à Internet e dar suporte ao compartilhamento de Internet Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Instalar e configurar o Wireshark
1. No computador, instale o [Wireshark](https://www.wireshark.org/#download) 
1. No computador, habilite o hotspot móvel para compartilhar sua conexão com a Internet por meio do Wi-Fi.
1. No computador, inicie o Wireshark e capture o tráfego por meio da interface do hotspot móvel. 
1. No HoloLens 2, altere a rede Wi-Fi para o hotspot móvel do computador. O tráfego IP do HoloLens 2 será exibido no Wireshark.

#### <a name="analyze-wireshark-logs"></a>Analisar os logs do Wireshark
Os filtros do Wireshark podem ajudar a filtrar os pacotes de interesse. 

Confira o [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) original.

[Voltar para a lista](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Não é possível entrar em um dispositivo HoloLens configurado anteriormente

Se o seu dispositivo foi configurado anteriormente para outra pessoa, seja para um cliente ou ex-funcionário, e você não tem a senha para desbloquear o dispositivo, pode usar o Intune para [limpar](/intune/remote-actions/devices-wipe) remotamente o dispositivo. Em seguida, o dispositivo aplica reflash automaticamente.  
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
- O dispositivo foi removido do locatário do Azure Active Directory devido à inatividade. Para um ambiente gerenciado com eficiência, normalmente recomendamos que os administradores de TI removam dispositivos antigos e inativos de seu locatário do [Azure Active Directory](/azure/active-directory/devices/manage-stale-devices).

Quando um dispositivo afetado tentar entrar em contato com o locatário do Azure Active Directory novamente depois que ele tiver sido excluído, ele não será autenticado com o Azure Active Directory. Esse efeito geralmente é invisível para o usuário do dispositivo, pois o logon armazenado em cache via PIN continuará permitindo que o usuário logon.

### <a name="mitigation"></a>Atenuação
Atualmente, não há como adicionar um dispositivo HoloLens excluído de volta ao Azure Active Directory. Os dispositivos afetados precisarão ser limpos novamente seguindo as instruções sobre [como fazer reflash no seu dispositivo](hololens-recovery.md#clean-reflash-the-device).

[Voltar para a lista](#list)

## <a name="autopilot-troubleshooting"></a>Solução de problemas do Autopilot

Os artigos a seguir podem ser um recurso útil para obter mais informações e solucionar problemas do Autopilot. No entanto, esteja ciente de que esses artigos são baseados no Windows 10 Desktop e nem todas as informações são aplicadas ao HoloLens:

- [Windows Autopilot: problemas conhecidos](/mem/autopilot/known-issues)
- [Solucionar problemas de registro de dispositivo Windows no Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: Conflitos de Política](/mem/autopilot/policy-conflicts)

[Voltar para a lista](#list)

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
Para dispositivos HoloLens de primeira geração, confira [estas perguntas frequentes](hololens1-faq-security.yml).

[Voltar para a lista](#list)
