---
title: Restrições comuns de dispositivo
description: Mantenha-se atualizado com as configurações e restrições de dispositivo comuns para o dispositivo de realidade misturada do HoloLens.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308038"
---
# <a name="common-device-restrictions"></a>Restrições comuns de dispositivo 

Este guia ajuda os profissionais de ti a compreender as opções de gerenciamento mais usadas disponíveis para o sistema operacional Windows 10 Holographic na empresa. Consulte a documentação de seu sistema MDM para entender como essas políticas são habilitadas por seu fornecedor de MDM. Nem todos os sistemas MDM dão suporte a todas as configurações descritas neste guia. Alguns dão suporte a políticas personalizadas por meio de arquivos XML OMA-URI. Consulte [Suporte do Microsoft Intune para políticas personalizadas](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). As convenções de nomenclatura também podem variar entre os fornecedores de MDM.

## <a name="prevent-changing-of-settings"></a>Impedir alteração das configurações
Geralmente, os funcionários têm permissão para alterar determinadas configurações do dispositivo pessoal que você pode bloquear em dispositivos corporativos. Os funcionários podem ajustar interativamente determinadas configurações do HoloLens por meio da interface do usuário de configurações. Usando o MDM, você pode limitar quais usuários têm permissão para alterar. As listas a seguir geralmente usavam as configurações do MDM que o Windows 10 Holographic dá suporte para definir restrições de configurações:
-   [Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite que o usuário altere as configurações de VPN
-   [Permitir configuração manual de WiFi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os usuários façam conexões Wi-Fi fora das redes provisionadas pelo MDM
-   [Permitir cancelamento de registro manual do MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se os usuários têm permissão para excluir a conta de local de trabalho (ou seja, cancelar o registro do dispositivo do sistema de MDM)

Adicionado no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos do HoloLens 2:
- [Permitir adicionar pacote de provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alternar se os usuários puderem adicionar novos pacotes de provisionamento, substituindo por novos valores.
- [Permitir remover pacote de provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alternar se os usuários puderem remover pacotes de provisionamento, permitindo que eles alternem configurações bloqueadas anteriormente.

Encontre mais detalhes sobre as opções de política nos [CSPs da política](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) com suporte do HoloLens

## <a name="hardware-restrictions"></a>Restrições de hardware
Os dispositivos Windows 10 Holographic usam tecnologia de ponta que inclui recursos de hardware populares, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.
As seguintes listas de configurações de MDM comumente usadas que o Windows 10 Holographic dá suporte para configurar restrições de hardware:

> [!NOTE]
> Algumas dessas restrições de hardware afetam a conectividade e auxiliam na proteção de dados.

-   [Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar a rádio WiFi em seus dispositivos.
-   [Permitir conexão USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não afeta o carregamento de USB.)
-   [Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o rádio Bluetooth em seus dispositivos.
-   [Restringir câmera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica se os aplicativos do Windows podem acessar a câmera.
-   [Restringir microfones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica se os aplicativos do Windows podem acessar o microfone.

Adicionado no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos do HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Definir a quantidade de tempo até que a exibição seja desligada e desativar a exibição, bloqueará o dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Definir a quantidade de tempo até que a exibição seja desligada e desativar a exibição, bloqueará o dispositivo. 
