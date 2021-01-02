---
title: segurança do sistema operacional
description: Sistema operacional sem administrador e segurança hololens
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, sem administrador, menos administrador, sistema operacional, sistema operacional sem administrador, os administrador, so sem administrador, hololens 2, segurança do hololens2,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 79429c960b065e401ef18520350a199704981938
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253078"
---
# Sistema Operacional sem Administrador

O HoloLens 2 minimiza a área de superfície para o escalonamento de privilégios desabilitando o suporte para o grupo administradores e limitando todo o código de aplicativo UWP de terceiros para ser executado somente como usuários padrão dentro da área restrita do AppContainer. Esse código só recebe acesso a esses recursos protegidos por capacidades explicitamente manifestadas no aplicativo para um usuário não elevado, além de recursos acessíveis a todos os AppContainers.
Esses recursos de aplicativos continuam a ter o modelo de classificação de três níveis:
  * Geral
  * Restricted (Restrito)
  * Windows

Os componentes do Windows também podem aproveitar a área restrita do AppContainer por meio do UWPs do sistema. Saiba mais sobre os aplicativos da Plataforma Universal do Windows (UWP), veja [documentação UWP](https://docs.microsoft.com/windows/uwp/). Além disso, os componentes do Windows com mais necessidades de redução de privilégios (por exemplo, páginas de conteúdo do navegador, analisadores) usam a área restrita do Less Privileged AppContainer (LPAC), o que reduz o acesso ao conjunto de recursos acessíveis para todos os AppContainers.

## Proprietário do dispositivo

Por fim, a execução de operações específicas de todo o dispositivo, como ingressar no dispositivo em um locatário ou gerenciamento de usuário, só é permitida para "proprietários de dispositivo". Esse grupo é preenchido por usuários no dispositivo por meio de uma das seguintes etapas:
  * O primeiro usuário no dispositivo sempre é designado como um Proprietário. 
    * A exceção a essa regra é que, se o dispositivo for o Microsoft Azure Active Directory associado, o usuário que realizou a junção será tornado proprietário do dispositivo. Isso é aplicável, por exemplo, se um dispositivo for o Microsoft Azure Active Directory associado via AutoPilot, caso em que o primeiro usuário se conectará ao dispositivo e não oMicrosoft Azure Active Directory entrar no dispositivo e, portanto, não será tornado proprietário do dispositivo. Para entender mais sobre quem se tornou um proprietário de dispositivo em um dispositivo associado ao Microsoft Azure Active Directory, confira a [documentação "atribuir administrador local"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (mas Leia "administrador local como" proprietário do dispositivo ", pois o administrador não existe no HoloLens).
  * Quando um usuário é promovido para ser um proprietário da Experiência do Usuário de configurações por outro proprietário no dispositivo.
  * Se o proprietário do dispositivo não estiver mais disponível (por exemplo, sair da empresa) e o dispositivo ingressado for o Microsoft Azure Active Directory, o administrador do locatário poderá alterar o proprietário do dispositivo para um novo usuário no portal do Azure.
Os Administradores Globais de um locatário do Microsoft Azure Active Directory estão implicitamente conectados como Proprietários no dispositivo sem a necessidade de uma das etapas anteriores. 

Os administradores de TI podem gerenciar quais aplicativos podem acessar através das políticas de [privacidade](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy). 
