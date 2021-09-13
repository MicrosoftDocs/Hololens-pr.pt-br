---
title: Restrições comuns de dispositivo
description: Mantenha-se atualizado com restrições e configurações comuns de dispositivo para o HoloLens de realidade misturada.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031940"
---
# <a name="common-device-restrictions"></a>Restrições comuns de dispositivo 

Este guia ajuda os profissionais de TI a entender as opções de gerenciamento mais usadas disponíveis para Windows 10 Holographic sistema operacional na empresa. Consulte a documentação de seu sistema MDM para entender como essas políticas são habilitadas por seu fornecedor de MDM. Nem todos os sistemas MDM dão suporte a todas as configurações descritas neste guia. Alguns dão suporte a políticas personalizadas por meio de arquivos XML OMA-URI. Consulte [Suporte do Microsoft Intune para políticas personalizadas](/mem/intune/configuration/custom-settings-windows-10). As convenções de nomenclatura também podem variar entre os fornecedores de MDM.

## <a name="prevent-changing-of-settings"></a>Impedir alteração das configurações
Geralmente, os funcionários têm permissão para alterar determinadas configurações do dispositivo pessoal que você pode bloquear em dispositivos corporativos. Os funcionários podem ajustar interativamente determinadas configurações do HoloLens por meio da interface do usuário de configurações. Usando o MDM, você pode limitar quais usuários têm permissão para alterar. As seguintes listas listam as configurações de MDM usadas com Windows 10 Holographic suporte para definir restrições de configurações:
-   [Permitir VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite que o usuário altere as configurações de VPN
-   [Permitir Configuração De WiFi Manual:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os usuários façam conexões Wi-Fi fora das redes provisionadas do MDM
-   [Permitir o unenrollment](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) manual do MDM Se os usuários têm permissão para excluir a conta do local de trabalho (ou seja, desincluem o dispositivo do sistema MDM)

Adicionado no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos:
- [Permitir Adicionar Pacote de Provisionamento:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alterne se os usuários puderem adicionar novos pacotes de provisionamento, substituição por novos valores.
- [Permitir Remover Pacote de Provisionamento:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alterne se os usuários puderem remover pacotes de provisionamento, permitindo que eles alternem as configurações bloqueadas anteriormente.

Encontre mais detalhes sobre as opções de política HoloLens [CSPs de política com suporte](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Restrições de hardware
Windows 10 Holographic dispositivos usam tecnologia de última geração que inclui recursos de hardware populares, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.
As seguintes listas listam as configurações de MDM usadas com Windows 10 Holographic suporte para configurar restrições de hardware:

> [!NOTE]
> Algumas dessas restrições de hardware afetam a conectividade e auxiliam na proteção de dados.

-   [Permitir Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar o rádio WiFi em seus dispositivos.
-   [Permitir conexão USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não afeta a carga USB).)
-   [Permitir Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o Bluetooth em seus dispositivos.
-   [Restringir Câmera:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica se Windows aplicativos podem acessar a câmera.
-   [Restringir microfones:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica se Windows aplicativos podem acessar o microfone.

Adicionado no [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Definir o tempo até que a exibição seja desligada e, ao desligar a exibição, bloqueia o dispositivo. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Definir o tempo até que a exibição seja desligada e, ao desligar a exibição, bloqueia o dispositivo. 
