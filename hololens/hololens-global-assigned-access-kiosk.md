---
title: Acesso Global Atribuído
description: Guia de como usar o OMA-URI para quiosques de Acesso Global Atribuído
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9c7e4e37b54e6dd81341a64165e1e742a2242d00
ms.sourcegitcommit: a0f6ff5c36aab0ed94e16e136728e4b8753203db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "11093931"
---
# Acesso Global Atribuído – Quiosque

Esse recurso configura o dispositivo Hololens 2 para o modo de quiosque para vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todas as pessoas que se inscrevem no dispositivo. 

> [!NOTE]
> No momento, esse recurso só é disponível na compilação do Windows Insider. Se você deseja testar esse recurso antes que ele seja geralmente disponível nas versões do HoloLens, leia mais sobre compilações do[Windows Insider](hololens-insider.md).
 
## Como usar isso no Intune? 

> [!NOTE]
> Lembre-se das áreas marcadas com "<!-". Essas áreas exigem que você faça modificações baseadas nas suas preferências. 

1.  Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte maneira e aplique-o ao grupo de dispositivos do HoloLens: 

    Valor do URI:. Device/Vendor/MSFT/AssignedAccess/Configuration
   
    > [!div class="mx-imgBorder"]
    > ![Acesso global atribuído a OMA-URI no Intune](images/global-assigned-access-omauri.png)

2.  Para obter o valor, atualize e cole o seguinte conteúdo: 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Como usar esse suplemento no Designer de Configuração do Windows? 
 
1.  Atualize e salve o blob XML mencionado acima como arquivo XML. 

2.  Siga as etapas em [Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou vários aplicativos](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a seção “pacote de provisionamento, etapa 2 – Adicionar o arquivo XML de configuração do Kiosk a um pacote de provisionamento” e consultar o arquivo XML que foi salvo na etapa anterior. 

## Posso criar uma configuração em que o acesso global se aplica a todos, e configurações separadas se apliquem a 1 conta AAD ou grupo AAD? 

Sim, consulte o exemplo de blob XML abaixo. Os perfis de Acesso Global Atribuídos são aplicados no Hololens quando um perfil determinado para o usuário conectado não é encontrado, portanto, é a configuração padrão de modo de quiosque para o usuário conectado. Aqui está um exemplo de blob XML a ser usado: 

> [!NOTE]
> Lembre-se das áreas realçadas marcadas com `<!-`. Essas áreas exigem que você faça modificações baseadas nas suas preferências. 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Excluindo DeviceOwners do perfil de acesso global atribuído

Esse recurso permite a um usuário que é considerado "[Proprietário do dispositivo](security-adminless-os.md)" no Hololens de ser excluído do acesso global atribuído. Para aproveitar esse recurso, no blob XML para a configuração do Kiosk de vários aplicativos, certifique-se de que as linhas destacadas sejam adicionadas: 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
