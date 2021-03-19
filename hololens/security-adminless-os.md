---
title: Segurança do sistema operacional sem administrador
description: Saiba mais sobre sistemas operacionais sem administrador, proprietários de dispositivos e segurança em dispositivos de realidade misturada do HoloLens.
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
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440332"
---
# <a name="admin-less-operating-system"></a>Sistema Operacional sem Administrador

O HoloLens 2 minimiza a área de superfície para o escalonamento de privilégios desabilitando o suporte para o grupo administradores e limitando todo o código de aplicativo UWP de terceiros para ser executado somente como usuários padrão dentro da área restrita do AppContainer. Esse código só recebe acesso a esses recursos protegidos por capacidades explicitamente manifestadas no aplicativo para um usuário não elevado, além de recursos acessíveis a todos os AppContainers.
Esses recursos de aplicativos continuam a ter o modelo de classificação de três níveis:
  * Geral
  * Restricted (Restrito)
  * Windows

Os componentes do Windows também podem aproveitar a área restrita do AppContainer por meio do UWPs do sistema. Saiba mais sobre a Plataforma Universal do Windows (UWP), confira a [documentação UWP](https://docs.microsoft.com/windows/uwp/). Além disso, os componentes do Windows com mais necessidades de redução de privilégios (como páginas de conteúdo do navegador, analisadores) usam a área restrita do Less Privileged AppContainer (LPAC), o que reduz o acesso ao conjunto de recursos acessíveis para todos os AppContainers.

## <a name="device-owner"></a>Proprietário do dispositivo

Por fim, a execução de operações específicas de todo o dispositivo, como ingressar no dispositivo em um locatário ou gerenciamento de usuário, só é permitida para "proprietários de dispositivo". Esse grupo é preenchido por usuários no dispositivo por meio de uma das seguintes etapas:
  * O primeiro usuário no dispositivo sempre é designado como um proprietário. 
> [!IMPORTANT]
>Para usuários do Azure AD, a exceção a essa regra é que se o dispositivo for ingressado no Azure AD por meio do Autopilot ou inscrição em massa do Azure AD, que usa um usuário não real. Nesse caso, o primeiro usuário do AAD a entrar no dispositivo não pode se tornar proprietário do dispositivo automaticamente, a menos que esse usuário tenha a função de "administrador global" ou "administrador do dispositivo" atribuída no portal do Azure. Para obter mais informações, confira a observação abaixo.  

  * Quando um usuário é promovido a proprietário da experiência de usuário de configurações por outro proprietário no dispositivo.
  * Se o proprietário do dispositivo não estiver mais disponível (saiu da empresa) e o dispositivo for ingressado no Azure AD, o administrador do locatário poderá alterar o proprietário do dispositivo para um novo usuário no portal do Azure. Os administradores globais e os administradores de dispositivos de um locatário do Azure AD estão implicitamente conectados como proprietários no dispositivo sem a necessidade de uma das etapas anteriores.  

 Os administradores de TI podem gerenciar quais aplicativos podem acessar através das políticas de [Privacidade](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy). 

> [!NOTE]
> Para entender mais sobre quem se tornou um proprietário de dispositivo em um dispositivo associado ao Microsoft Azure Active Directory, confira a [documentação "atribuir administrador local"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (mas Leia "administrador local como" proprietário do dispositivo ", pois o administrador não existe no HoloLens).