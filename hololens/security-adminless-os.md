---
title: Segurança do sistema operacional sem administrador
description: Saiba mais sobre os sistemas operacionais sem administrador, os proprietários de dispositivos e a segurança em dispositivos de realidade misturada do HoloLens.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034084"
---
# <a name="admin-less-operating-system"></a>Sistema operacional sem administrador

O HoloLens 2 minimiza a área de superfície para o escalonamento de privilégios desabilitando o suporte para o grupo Administradores e limitando todo o código do aplicativo UWP de terceiros a ser executado somente como usuários padrão na área restrita do AppContainer. Esse código só recebe acesso a esses recursos protegidos por funcionalidades explicitamente manifestadas no aplicativo para um usuário sem privilégios elevados, além de recursos acessíveis a todos os AppContainers.
Essas funcionalidades do aplicativo continuam tendo o modelo de classificação de três camadas:
  * Geral
  * Restritos
  * Windows

Os componentes do Windows também podem aproveitar a área restrita do AppContainer por meio do UWPs do sistema. Para saber mais sobre o UWP (Plataforma Windows Universal), confira a [documentação do UWP](/windows/uwp/). Além disso, os componentes do Windows com mais necessidades de redução de privilégios (como páginas de conteúdo do navegador ou analisadores) usam a área restrita do LPAC (AppContainer com menos privilégios), o que reduz o acesso ao conjunto de recursos acessíveis para todos os AppContainers.

## <a name="device-owner"></a>Proprietário do dispositivo

Por fim, a execução de operações específicas de todo o dispositivo, como o ingresso no dispositivo em um locatário ou o gerenciamento de usuários, só é permitida para os “proprietários do dispositivo”. Esse grupo é preenchido por usuários no dispositivo por meio de uma das seguintes etapas:
  * O primeiro usuário no dispositivo sempre é designado como um proprietário. 
> [!IMPORTANT]
>Para os usuários do Azure AD, a exceção a essa regra é se o dispositivo é ingressado no Azure AD por meio do Autopilot ou pelo registro em massa do Azure AD, que usa um usuário não real. Nesse caso, talvez o primeiro usuário do AAD a entrar no dispositivo não se torne o proprietário do dispositivo automaticamente, a menos que esse usuário tenha a função "Administrador global" ou "administrador do dispositivo" atribuída no portal do Azure. Para obter mais informações, confira a observação abaixo.  

  * Quando um usuário é promovido a proprietário por meio da Experiência de Usuário das Configurações por outro proprietário no dispositivo.
  * Se o proprietário do dispositivo não está mais disponível (saiu da empresa) e o dispositivo é ingressado no Azure AD, o administrador de locatários pode alterar o proprietário do dispositivo para um novo usuário no portal do Azure. Os Administradores globais e os Administradores de dispositivos de um locatário do Azure AD estão implicitamente conectados como proprietários no dispositivo sem a necessidade de uma das etapas anteriores.  

 Os administradores de TI podem gerenciar os aplicativos que podem ter acesso por meio das políticas de [Privacidade](/windows/client-management/mdm/policy-csp-privacy). 

> [!NOTE]
> Para entender mais sobre quem se tornou um proprietário do dispositivo em um dispositivo ingressado no Azure AD, confira a [documentação “Atribuir o administrador local”](/azure/active-directory/devices/assign-local-admin) (mas leia 'administrador local' como 'proprietário do dispositivo', pois não há administrador no HoloLens).