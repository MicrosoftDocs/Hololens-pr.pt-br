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
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253198"
---
# Acesso Global Atribuído – Quiosque

Este recurso configura o dispositivo HoloLens 2 para o modo quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todos que fazem login no dispositivo.

> [!NOTE]
> Esse recurso só está disponível em compilações do Participante do Programa Windows Insider. Se você quiser experimentar esse recurso antes que ele esteja disponível em lançamentos do HoloLens, leia mais sobre as compilações do [Participante do Programa Windows Insider](hololens-insider.md).

## Como usar o Acesso Atribuído Global no Intune?

> [!NOTE]
> Lembre-se das áreas marcadas com "<!-". Essas áreas exigem que você faça modificações baseadas nas suas preferências.

1. Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte maneira e aplique-o ao grupo de dispositivos do HoloLens:

    Valor do URI:. Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Acesso global atribuído a OMA-URI no Intune](images/global-assigned-access-omauri.png)

2. Para obter o valor, atualize e cole o seguinte conteúdo:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Como usar o Acesso Atribuído Global no Designer de Configuração do Windows?

1. Atualize e salve o blob XML mencionado acima como arquivo XML. 

2. Siga as etapas em [Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou vários aplicativos](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a seção “pacote de provisionamento, etapa 2 – Adicionar o arquivo XML de configuração do Kiosk a um pacote de provisionamento” e consultar o arquivo XML que foi salvo na etapa anterior.

## Posso criar uma configuração na qual todas as pessoas e configurações separadas aplicam-se à 1 conta do Azure AD ou ao grupo do Microsoft Azure Active Directory? 

Sim, consulte o exemplo de blob XML abaixo. O perfil de Acesso Atribuído Global é aplicado no HoloLens quando um perfil específico para o usuário conectado não é encontrado, portanto, é a configuração do modo quiosque padrão para o usuário conectado.
Aqui está um exemplo de blob XML a ser usado:

> [!NOTE]
> Lembre-se das áreas realçadas marcadas com `<!-`. Essas áreas exigem que você faça modificações baseadas nas suas preferências.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Excluindo DeviceOwners do perfil de acesso global atribuído

Esse recurso permite que um usuário considerado "[Proprietário do dispositivo](security-adminless-os.md)" no HoloLens seja excluído do Acesso Atribuído Global. Para aproveitar esse recurso, no blob XML para a configuração do Kiosk de vários aplicativos, certifique-se de que as linhas destacadas sejam adicionadas:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## Exemplos adicionais de Acesso Global Atribuído

Este é um exemplo de quiosque de Acesso Atribuído Global que, quando qualquer usuário entrar, terá um quiosque de vários aplicativos com o aplicativo Configurações, Hub de Comentários e Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Este exemplo é um quiosque de Acesso Atribuído Global que exclui o proprietário do dispositivo, quando qualquer outro usuário do Microsoft Azure Active Directory entrar, ele terá um quiosque de vários aplicativos com o aplicativo de Configurações, Hub de comentários e Microsoft Edge. Esse quiosque também inclui uma configuração de quiosque secundária para uma Conta de visitante, que pode ser conectada por qualquer pessoa na tela de bloqueio. Quando um usuário entra na conta de Visitante, ele terá um quiosque de vários aplicativos que tem apenas o aplicativo de Hub de Feedback.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
