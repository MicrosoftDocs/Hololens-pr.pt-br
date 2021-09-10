---
title: Preparar os certificados e os perfis de rede para o HoloLens 2
description: Saiba como configurar, usar, implantar e solucionar problemas de certificados de rede em dispositivos de realidade misturada HoloLens 2.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428314"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Preparar os certificados e os perfis de rede para o HoloLens 2

A autenticação baseada em certificado é um requisito comum para clientes que usam o HoloLens 2. Você pode precisar de certificados para acessar a Wi-Fi, conectar-se a soluções de VPN ou acessar recursos internos de sua organização.

Como os dispositivos HoloLens 2 geralmente são adicionados ao Azure AD (Azure Active Directory) e gerenciados pelo Intune ou por outro provedor de MDM, você precisará implantar esses certificados usando uma infraestrutura de certificado de protocolo SCEP ou PKCS (Padrão de Criptografia por Chave Pública) integrada à sua solução de MDM. 

>[!NOTE]
> Se não tiver um provedor de MDM, você ainda poderá implantar certificados por meio de um [pacote de provisionamento](hololens-provisioning.md#steps-for-creating-provisioning-packages) no [Designer de Configuração do Windows](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) ou por meio do [Gerenciador de Certificados](certificate-manager.md) acessando **Configurações > Atualização e Segurança > Gerenciador de Certificados**.

## <a name="certificate-requirements"></a>Requisitos de certificado
Certificados raiz são necessários para a implantação de certificados por meio de uma infraestrutura de SCEP ou PKCS. Outros aplicativos e serviços em sua organização também podem exigir que certificados raiz sejam implantados em seus dispositivos HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Requisitos de conectividade Wi-Fi
Para permitir que um dispositivo receba automaticamente a configuração de Wi-Fi necessária para sua rede corporativa, você precisará de um perfil de configuração de Wi-Fi. Você pode configurar o Intune ou outro provedor de MDM para implantar esses perfis em seus dispositivos. Se sua segurança de rede exigir que os dispositivos façam parte do domínio local, talvez você precise avaliar a infraestrutura da rede Wi-Fi para verificar se ela é compatível com dispositivos HoloLens 2 (dispositivos HoloLens 2 são adicionados somente ao Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Implantar a infraestrutura de certificado
Se não houver nenhuma infraestrutura de SCEP ou PKCS, você precisará preparar uma. Para dar suporte ao uso de certificados SCEP ou PKCS para autenticação, o Intune requer o uso de um [conector de certificado](/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Ao usar o SCEP com uma AC da Microsoft, você também precisa configurar o [NDES (Serviço de Registro de Dispositivo de Rede)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Para saber mais, confira [Configurar um perfil de certificado para seus dispositivos no Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implantar certificados e o perfil de Wi-Fi/VPN
Para implantar certificados e perfis, siga estas etapas:
1.  Crie um perfil para cada um dos certificados Raiz e Intermediário (confira [Criar perfis de certificado confiáveis](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Cada um desses perfis deve ter uma descrição que inclui uma data de validade no formato DD/MM/AAAA. **Perfis de certificado sem uma data de validade não serão implantados.**
1.  Crie um perfil para cada certificado SCEP ou PKCS (confira [Criar um perfil de certificado SCEP ou Criar um perfil de certificado PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Cada um desses perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/AAAA. **Perfis de certificado sem uma data de validade não serão implantados.**

    > [!NOTE]
    > Como o HoloLens 2 é considerado por muitos como um dispositivo compartilhado, com vários usuários por dispositivo, é recomendável implantar Certificados de dispositivo em vez de Certificados de usuário para autenticação da Wi-Fi quando possível

3.  Crie um perfil para cada rede Wi-Fi corporativa (confira [Configurações de Wi-Fi para o Windows 10 e dispositivos posteriores](/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > É recomendável que o perfil de Wi-Fi seja [atribuído](/mem/intune/configuration/device-profile-assign) a Grupos de dispositivos em vez de Grupos de usuários quando possível. 

    > [!TIP]
    > Você também pode exportar um perfil de Wi-Fi em funcionamento em um computador com Windows 10 em sua rede corporativa. Essa exportação cria um arquivo XML com todas as configurações atuais. Em seguida, importe esse arquivo para o Intune e use-o como perfil de Wi-Fi para os dispositivos HoloLens 2. Confira [Exportar e importar configurações de Wi-Fi para dispositivos Windows.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Crie um perfil para cada VPN corporativa (confira [Configurações de dispositivos com Windows 10 e Windows Holographic para adicionar conexões de VPN usando o Intune](/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Solução de problemas com certificados

Caso você precise validar que um certificado está implantado corretamente, use o [Gerenciador de Certificados](certificate-manager.md) no dispositivo para verificar se o certificado está presente.  

>[!WARNING]
> Embora você possa exibir certificados implantados no MDM no Gerenciador de Certificados, não é possível desinstalá-los lá. Você deve desinstalá-los por meio do MDM.


