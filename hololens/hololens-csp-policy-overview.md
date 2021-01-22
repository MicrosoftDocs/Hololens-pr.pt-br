---
title: Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs
description: Saiba como configurar CSPs, política e gerenciamento de dispositivos usando o Gerenciamento de Dispositivo Móvel e pacotes de provisionamento.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283242"
---
# Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs

Os administradores de IT podem definir e implementar configurações de política no HoloLens 2. As configurações que você usa serão diferentes de acordo com o cenário de implantação, e os dispositivos corporativos oferecerão à TI um controle mais amplo. No Windows 10, os Provedores de Serviços de Configuração (CSP) são uma interface para ler, definir, modificar ou excluir definições de configuração no dispositivo. Essas configurações mapeiam para arquivos ou chaves do Registro. Alguns provedores de serviços de configuração suportam o formato WAP, alguns suportam SyncML e alguns suportam ambos.

Para obter mais informações sobre CSPs de gerenciamento de dispositivos holográficos do Windows 10, consulte a lista completa de CSPs com suporte em [dispositivos HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
Os administradores de IT também podem gerenciar csp de política em dispositivos, consulte a lista completa de CSPs de política com suporte [pelo HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## Métodos de configuração

### Configurar com MDM

CSPs e Políticas podem ser facilmente gerenciados em qualquer dispositivo pessoal ou corporativo inscrito em um sistema MDM. Depois que um dispositivo for inscrito em sua solução MDM, você poderá gerenciar esse dispositivo ou um conjunto de dispositivos usando configurações de dispositivo. Saiba mais sobre como gerenciar [seus dispositivos HoloLens por meio do MDM.](hololens-mdm-configure.md)

### Configurar com pacotes de provisionamento

O HoloLens 2 também dá suporte à definição de um conjunto limitado de configurações de CSP para dispositivos HoloLens 2 por meio de Pacotes de Provisionamento personalizados. Os pacotes de provisionamento são geralmente aproveitados para dispositivos gerenciados não MDM e precisam ser aplicados manualmente a cada dispositivo. Leia as informações sobre como criar pacotes [de provisionamento personalizados para HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Configurações

### Restrições comuns de dispositivos

Algumas restrições de dispositivo são tão simples quanto desabilitar uma funcionalidade ou conexão com o dispositivo. Para saber mais sobre eles, leia mais sobre [restrições comuns de dispositivos.](hololens-common-device-restrictions.md)

### Modos de quiosque

Use o modo quiosque para controlar quais identidades têm acesso a quais aplicativos por padrão. Os quiosques podem ser usados para um único aplicativo ou experiência de interface do usuário de vários aplicativos. As configurações de quiosque variam de um único aplicativo para qualquer pessoa que usa o dispositivo até seleções diferentes de aplicativos para grupos diferentes. O modo de quiosque não impede que "aplicativos permitidos" iniciam outros aplicativos e não foi planejado para nunca. Saiba mais lendo [sobre modos de quiosque e como usá-los.](hololens-kiosk.md)

### Visibilidade da página de configurações

Use a política de aplicativo Configurações para controlar quais identidades têm acesso às configurações por padrão. Usando essa política, o aplicativo Configurações pode ser configurado para mostrar somente as páginas selecionadas ou ocultar todas as páginas selecionadas. [Leia sobre como configurar as páginas disponíveis.](settings-uri-list.md)

No momento, esse recurso só está disponível em [builds do Windows Insider.](hololens-insider.md) Certifique-se de que os dispositivos para os que você pretende usar esse recurso estão no build 19041.1349+.

### WDAC

Use a configuração do WDAC para controlar quais aplicativos/processos são permitidos/não podem ser lançados independentemente de o sistema estar ou não no modo de quiosque.
[Consulte nossa visão geral do WDAC.](windows-defender-application-control-wdac.md)
