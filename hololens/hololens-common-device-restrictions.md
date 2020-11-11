---
title: Restrições Comuns de Dispositivo
description: O dispositivo restrctions comumente definido no HoloLens.
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
ms.openlocfilehash: 744d54a344867c5c38681781580f5357e0a0da70
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162966"
---
# Restrições Comuns de Dispositivo 

Este guia ajuda os profissionais de ti a entenderem as opções de gerenciamento mais comuns disponíveis para o Windows 10 holográfico o sistema operacional da empresa. Consulte a documentação de seu sistema MDM para entender como essas políticas são habilitadas por seu fornecedor de MDM. Nem todos os sistemas MDM dão suporte a todas as configurações descritas neste guia. Alguns dão suporte a políticas personalizadas por meio de arquivos XML OMA-URI. Consulte [Suporte do Microsoft Intune para políticas personalizadas](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). As convenções de nomenclatura também podem variar entre os fornecedores de MDM.

## Impedir alteração das configurações
Geralmente, os funcionários têm permissão para alterar determinadas configurações do dispositivo pessoal que você pode bloquear em dispositivos corporativos. Os funcionários podem ajustar interativamente determinadas configurações do HoloLens por meio da interface do usuário de configurações. Usando o MDM, você pode limitar quais usuários têm permissão para alterar. A seguir lista as configurações de MDM comumente usadas que o Windows 10 holográfico suporta para configurar restrições de configurações:
-   [Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite que o usuário altere as configurações de VPN
-   [Permitir configuração manual WiFi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite que os usuários façam conexões Wi-Fi fora das redes provisionadas pelo MDM
-   [Permitir cancelamento de registro do MDM manual](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Se os usuários podem excluir a conta do local de trabalho (ou seja, cancelar o registro do dispositivo do sistema MDM)

Adicionado no [Windows holográfico, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos do HoloLens 2:
- [Permitir adicionar pacote de provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alternar se os usuários podem adicionar novos pacotes de provisionamento, substituindo por novos valores.
- [Permitir remover pacote de provisionamento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alternar se os usuários puderem remover os pacotes de provisionamento, permitindo que eles ativem as configurações bloqueadas anteriormente.

Encontre mais detalhes sobre as opções de política nos [CSPs de política](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) com suporte do HoloLens

## Restrições de hardware
Os dispositivos Windows 10 holográfico usam a tecnologia de ponta que inclui recursos de hardware populares, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.
A seguir lista as configurações de MDM comumente usadas que o Windows 10 holográfico suporta para configurar restrições de hardware:

> [!NOTE]
> Algumas dessas restrições de hardware afetam a conectividade e ajudam na proteção de dados.

-   [Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar o rádio WiFi em seus dispositivos.
-   [Permitir conexão USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não afeta o carregamento USB.)
-   [Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o rádio Bluetooth em seus dispositivos.
-   [Restringe câmera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica se os aplicativos do Windows podem acessar a câmera.
-   [Restringir microfones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica se os aplicativos do Windows podem acessar o microfone.

Adicionado no [Windows holográfico, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos do HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Defina a quantidade de tempo até que a exibição seja desativada e desative a tela, bloqueia o dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Defina a quantidade de tempo até que a exibição seja desativada e desative a tela, bloqueia o dispositivo. 
