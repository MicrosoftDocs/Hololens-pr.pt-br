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
ms.openlocfilehash: ea35012e63f4c0d8868f9604809c1552c3212e72
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016635"
---
# Sistema Operacional sem Administrador

O HoloLens 2 minimiza a área de superfície para o escalonamento de privilégios desabilitando o suporte para o grupo administradores e limitando todo o código de aplicativo UWP de terceiros para ser executado somente como usuários padrão dentro da área restrita do AppContainer. Esse código só recebe acesso a esses recursos protegidos por capacidades explicitamente manifestadas no aplicativo para um usuário não elevado, além de recursos acessíveis a todos os AppContainers.
Esses recursos de aplicativos continuam a ter o modelo de classificação de três níveis:
  * Geral
  * Restricted (Restrito)
  * Windows

Os componentes do Windows também podem aproveitar a área restrita do AppContainer por meio do UWPs do sistema. Saiba mais sobre os aplicativos da Plataforma Universal do Windows (UWP), veja [documentação UWP](https://docs.microsoft.com/windows/uwp/). Além disso, os componentes do Windows com mais necessidades de redução de privilégios (por exemplo, páginas de conteúdo do navegador, analisadores) usam a área restrita do Less Privileged AppContainer (LPAC), o que reduz o acesso ao conjunto de recursos acessíveis para todos os AppContainers.

Por fim, a execução de operações específicas de todo o dispositivo, como ingressar no dispositivo em um locatário ou gerenciamento de usuário, só é permitida para "proprietários de dispositivo". Esse grupo é preenchido por usuários no dispositivo por meio de uma das seguintes etapas:
  * O primeiro usuário no dispositivo sempre é designado como um proprietário. 
    * A exceção a essa regra é que, se o dispositivo for ingressado no AAD, o usuário que executou a junção se torna proprietário do dispositivo. Isso é aplicável, por exemplo, se um dispositivo for ingressado no AAD pelo piloto automático, caso o primeiro usuário entre no dispositivo não ingressado no AAD e, portanto, não se torna proprietário de um dispositivo. Para saber mais sobre quem se torna um proprietário de um dispositivo ingressado no AAD, confira a documentação ["atribuir administrador local"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (mas leia ‘admin local’ como ‘proprietário do dispositivo’ já o administrador não existe no HoloLens).
  * Quando um usuário é promovido para ser um proprietário da UX de configurações por outro proprietário no dispositivo.
  * Se o proprietário do dispositivo não estiver mais disponível (por exemplo, sair da empresa) e o dispositivo for ingressado no AAD, o administrador do locatário poderá alterar o proprietário do dispositivo para um novo usuário no portal do Azure.
Os administradores globais de um locatário do Azure AD estão implicitamente conectados como proprietários no dispositivo sem a necessidade de uma das etapas anteriores. 

Os administradores de TI podem gerenciar quais aplicativos podem acessar através das políticas de [privacidade](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy). 
