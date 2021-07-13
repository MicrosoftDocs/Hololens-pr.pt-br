---
title: Restrições comuns de dispositivo
description: mantenha-se atualizado com as configurações e restrições de dispositivo comuns para o dispositivo HoloLens realidade misturada.
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
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639209"
---
# <a name="common-device-restrictions"></a>Restrições comuns de dispositivo 

este guia ajuda os profissionais de ti a compreender as opções de gerenciamento mais usadas disponíveis para o sistema operacional Windows 10 Holographic na empresa. Consulte a documentação de seu sistema MDM para entender como essas políticas são habilitadas por seu fornecedor de MDM. Nem todos os sistemas MDM dão suporte a todas as configurações descritas neste guia. Alguns dão suporte a políticas personalizadas por meio de arquivos XML OMA-URI. Consulte [Suporte do Microsoft Intune para políticas personalizadas](/mem/intune/configuration/custom-settings-windows-10). As convenções de nomenclatura também podem variar entre os fornecedores de MDM.

## <a name="prevent-changing-of-settings"></a>Impedir alteração das configurações
Geralmente, os funcionários têm permissão para alterar determinadas configurações do dispositivo pessoal que você pode bloquear em dispositivos corporativos. os funcionários podem ajustar interativamente determinadas configurações do HoloLens por meio da interface do usuário de configurações. Usando o MDM, você pode limitar quais usuários têm permissão para alterar. as listas a seguir costumam usar as configurações do MDM que Windows 10 Holographic suporte para definir restrições de configurações:
-   [Permitir VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite que o usuário altere as configurações de VPN
-   [Permitir configuração manual de WiFi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os usuários façam conexões Wi-Fi fora das redes provisionadas pelo MDM
-   [Permitir cancelamento de registro manual do MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se os usuários têm permissão para excluir a conta de local de trabalho (ou seja, cancelar o registro do dispositivo do sistema de MDM)

adicionado no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2:
- [Permitir adicionar pacote de provisionamento:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alternar se os usuários puderem adicionar novos pacotes de provisionamento, substituindo por novos valores.
- [Permitir remover pacote de provisionamento:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alternar se os usuários puderem remover pacotes de provisionamento, permitindo que eles alternem configurações bloqueadas anteriormente.

encontre mais detalhes sobre as opções de política no HoloLens [CSPs de política](/windows/client-management/mdm/policy-csps-supported-by-hololens2) com suporte

## <a name="hardware-restrictions"></a>Restrições de hardware
Windows 10 Holographic dispositivos usam tecnologia de ponta que inclui recursos populares de hardware, como câmeras, microfones, palestras, interfaces USB, interfaces de Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.
as listas a seguir costumam usar as configurações do MDM que Windows 10 Holographic suporte para configurar as restrições de hardware:

> [!NOTE]
> Algumas dessas restrições de hardware afetam a conectividade e auxiliam na proteção de dados.

-   [Permitir Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar a rádio WiFi em seus dispositivos.
-   [Permitir conexão USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não afeta o carregamento de USB.)
-   [Permitir Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) se os usuários podem habilitar e usar o Bluetooth rádio em seus dispositivos.
-   [Restringir câmera:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) especifica se Windows aplicativos podem acessar a câmera.
-   [Restringir microfones:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) especifica se Windows aplicativos podem acessar o microfone.

adicionado em [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Definir a quantidade de tempo até que a exibição seja desligada e desativar a exibição, bloqueará o dispositivo. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Definir a quantidade de tempo até que a exibição seja desligada e desativar a exibição, bloqueará o dispositivo. 
