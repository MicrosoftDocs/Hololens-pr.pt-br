---
title: Microsoft Store para Empresas
description: saiba como trabalhar com os Microsoft Store para Empresas para publicar seus aplicativos de realidade misturada em seus negócios.
keywords: Microsoft Store para Empresas, msfb, implantação de aplicativo, loja
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924331"
---
# <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

o [Microsoft Store para Empresas](/microsoft-store/microsoft-store-for-business-overview) é projetado principalmente para responsáveis por decisões de ti e administradores em empresas ou organizações com uma maneira flexível de localizar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos em select markets para Windows 10 dispositivos em volume. 

você pode gerenciar aplicativos Microsoft Store e aplicativos de linha de negócios privados em um único inventário e atribuir e reutilizar licenças conforme necessário. você também pode escolher o melhor método de distribuição para sua organização: atribuir diretamente aplicativos a indivíduos e equipes, publicar aplicativos em páginas privadas no Microsoft Store ou conectar-se com soluções de gerenciamento para obter mais opções.

quando Microsoft Store para Empresas for usado por um usuário final, ele iniciará o aplicativo Microsoft Store. Depois de iniciado, o usuário poderá selecionar a guia com o nome de sua organização. em seguida, eles serão apresentados com os aplicativos disponíveis para eles ou para esse dispositivo.

> [!Note]
> o Microsoft Store para Empresas não baixa automaticamente os aplicativos (push) para os dispositivos. no entanto, os aplicativos da Microsoft Store para Empresas podem ser associados ao seu servidor de gerenciamento de dispositivo (MDM) para direcionar e sincronizar aplicativos com dispositivos.

visite as páginas a seguir para saber mais sobre como usar o Microsoft Store para Empresas:

* [Níveis de permissões usadas para instalar aplicativos](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Como adicionar um aplicativo à sua loja para empresas](/mem/intune/apps/store-apps-windows)
* [Como atribuir aplicativos a grupos de funcionários](/mem/intune/apps/windows-store-for-business)

para associar seu Microsoft Store para Empresas, visite [associar seu Microsoft Store para Empresas ao Intune](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune).

> [!Tip]
> saiba mais sobre como [distribuir aplicativos offline](/microsoft-store/distribute-offline-apps) ao usar aplicativos como complemento de recuperação avançada (ARC) e Windows Designer de configuração (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar somente aplicativos de repositório particular para Microsoft Store

- introduzido no [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

A política RequirePrivateStoreOnly foi habilitada para HoloLens. essa política permite que o aplicativo Microsoft Store seja configurado para mostrar apenas o repositório privado configurado para sua organização. Limitando o acesso apenas aos aplicativos que você disponibilizou.

Saiba mais sobre o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Repetição inteligente para atualizações de aplicativo

- introduzido no [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

agora habilitado para HoloLens é uma nova política que permite que os administradores de ti definam uma data recorrente ou uma hora para reiniciar os aplicativos cuja atualização falhou porque o aplicativo está sendo usado, permitindo que a atualização seja aplicada. Eles podem ser definidos com base em alguns gatilhos diferentes, como um horário agendado ou entrada. Para saber mais sobre como usar essa política, veja [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).