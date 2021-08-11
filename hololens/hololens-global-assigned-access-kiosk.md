---
title: Acesso Atribuído Global
description: Introdução ao nosso guia de uso do OMA-URI para Quiosques de Acesso Atribuído Global com o Intune e o designer de configuração do Windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, assigned access, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640416"
---
# <a name="global-assigned-access--kiosk"></a>Acesso Atribuído Global – Quiosque

Este recurso configura o dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todos que entram no dispositivo.

> [!NOTE]
> Atualmente, esse recurso só está disponível em builds do Participante do Programa Windows Insider. Se você quiser experimentar esse recurso antes que ele entre em disponibilidade geral nas versões do HoloLens, leia mais sobre os builds do [Participante do Programa Windows Insider](hololens-insider.md).

## <a name="how-to-use-global-assigned-access-in-intune"></a>Como usar o Acesso Atribuído Global no Intune?

> [!NOTE]
> Lembre-se das áreas marcadas com "<!-". Essas áreas exigem que você faça modificações baseadas nas suas preferências.

1. Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte maneira e aplique-o ao grupo de dispositivos HoloLens:

    Valor do URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Acesso Atribuído Global ao OMA-URI no Intune](images/global-assigned-access-omauri.png)

2. Para obter o valor, atualize e cole o seguinte conteúdo:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Como usar o Acesso Atribuído Global no Designer de Configuração do Windows?

1. Atualize e salve o blob XML mencionado acima como um arquivo XML. 

2. Siga as etapas descritas em [Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou de vários aplicativos](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a seção "Pacote de provisionamento, etapa 2 – Adicionar o arquivo XML de configuração de quiosque a um pacote de provisionamento" e veja o arquivo XML salvo na etapa anterior.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Posso criar uma configuração na qual a configuração global se aplica a todas as pessoas e a separada se aplica a uma conta do Azure AD ou a um grupo do Azure AD? 

Sim, veja o exemplo de blob XML abaixo. O perfil de Acesso Atribuído Global é aplicado no HoloLens quando um perfil específico para o usuário conectado não é encontrado. Portanto, é a configuração do modo de quiosque padrão para o usuário conectado.
Este é um exemplo de blob XML a ser usado:

> [!NOTE]
> Lembre-se das áreas realçadas marcadas com `<!-`. Essas áreas exigem que você faça modificações baseadas nas suas preferências.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Como excluir DeviceOwners do perfil de Acesso Atribuído Global

Esse recurso permite que um usuário considerado “[Proprietário de dispositivo](security-adminless-os.md)” no HoloLens seja excluído do Acesso Atribuído Global. Para aproveitar esse recurso, no blob XML para a configuração de quiosque de vários aplicativos, verifique se as linhas realçadas foram adicionadas:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Exemplos adicionais de Acesso Atribuído Global

Este é um exemplo de quiosque de Acesso Atribuído Global que, quando qualquer usuário se conectar, ele terá um quiosque de vários aplicativos com o aplicativo Configurações, o Hub de Comentários e o Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Este exemplo é um quiosque de Acesso Atribuído Global que exclui o proprietário do dispositivo e que, quando qualquer outro usuário do Azure AD se conectar, ele terá um quiosque de vários aplicativos com o aplicativo Configurações, o Hub de Comentários e o Microsoft Edge. Esse quiosque também inclui uma configuração de quiosque secundária para uma conta de visitante, que pode ser conectada por qualquer pessoa na tela de bloqueio. Quando um usuário entrar na conta de visitante, ele terá um quiosque de vários aplicativos que tem apenas o aplicativo Hub de Comentários.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
