---
title: Restrições Comuns de Dispositivo
description: Mantenha-se atualizado com restrições e configurações comuns de dispositivos para o dispositivo de realidade misturada do HoloLens.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283352"
---
# Restrições Comuns de Dispositivo 

Este guia ajuda os profissionais de TI a entender as opções de gerenciamento mais comumente usadas disponíveis para o sistema operacional Windows 10 Holographic na empresa. Consulte a documentação de seu sistema MDM para entender como essas políticas são habilitadas por seu fornecedor de MDM. Nem todos os sistemas MDM dão suporte a todas as configurações descritas neste guia. Alguns dão suporte a políticas personalizadas por meio de arquivos XML OMA-URI. Consulte [Suporte do Microsoft Intune para políticas personalizadas](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). As convenções de nomenclatura também podem variar entre os fornecedores de MDM.

## Impedir alteração das configurações
Geralmente, os funcionários têm permissão para alterar determinadas configurações do dispositivo pessoal que você pode bloquear em dispositivos corporativos. Os funcionários podem ajustar interativamente determinadas configurações do HoloLens por meio da interface do usuário de configurações. Usando o MDM, você pode limitar quais usuários têm permissão para alterar. A lista a seguir lista as configurações MDM comumente usadas que o Windows 10 Holographic dá suporte para definir restrições de configurações:
-   [Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite que o usuário altere as configurações de VPN
-   [Permitir configuração de WiFi manual:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os usuários façam conexões Wi-Fi fora das redes provisionadas pelo MDM
-   [Permitir o não-rollamento manual do MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se os usuários têm permissão para excluir a conta do local de trabalho (ou seja, desarmá-lo do sistema MDM)

Adicionado ao [Windows Holographic, versão 20H2 para](hololens-release-notes.md#windows-holographic-version-20h2) dispositivos HoloLens 2:
- [Permitir Adicionar Pacote de Provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alternar se os usuários puderem adicionar novos pacotes de provisionamento, sobrescrevendo com novos valores.
- [Permitir Remover Pacote de Provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alterne se os usuários puderem remover pacotes de provisionamento, permitindo que eles alternem configurações bloqueadas anteriormente.

Encontre mais detalhes sobre as opções de política nos [CSPs](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) de política com suporte do HoloLens

## Restrições de hardware
Os dispositivos Windows 10 Holographic usam tecnologia de última geração que inclui recursos de hardware populares, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.
A lista a seguir lista as configurações MDM comumente usadas que o Windows 10 Holographic suporta para configurar restrições de hardware:

> [!NOTE]
> Algumas dessas restrições de hardware afetam a conectividade e auxiliam na proteção de dados.

-   [Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar o rádio WiFi em seus dispositivos.
-   [Permitir Conexão USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não afeta o carregamento USB).)
-   [Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o rádio Bluetooth em seus dispositivos.
-   [Restringir Câmera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica se os aplicativos do Windows podem acessar a câmera.
-   [Restrinja microfones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica se os aplicativos do Windows podem acessar o microfone.

Adicionado ao [Windows Holographic, vison 20H2 para](hololens-release-notes.md#windows-holographic-version-20h2) dispositivos HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) De definida a quantidade de tempo até que a exibição seja desligada e, ao desligar a tela, bloqueia o dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) De definida a quantidade de tempo até que a exibição seja desligada e, ao desligar a tela, bloqueia o dispositivo. 
