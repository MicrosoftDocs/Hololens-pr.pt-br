---
title: Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs
description: Como configurar CSPs, políticas e gerenciamento de dispositivos.
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
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252772"
---
# Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs

Os administradores de ti podem definir e implementar configurações de política no HoloLens 2. As configurações que você usa serão diferentes de acordo com o cenário de implantação, e os dispositivos corporativos oferecerão à TI um controle mais amplo. No Windows 10, os provedores de serviços de configuração (CSP) são uma interface para ler, definir, modificar ou excluir definições de configuração no dispositivo. Essas configurações mapeiam para arquivos ou chaves do Registro. Alguns provedores de serviços de configuração dão suporte ao formato WAP, alguns dão suporte ao SyncML e alguns dão suporte a ambos.

Para obter mais informações sobre os CSPs de gerenciamento de dispositivos do Windows 10 holográfico, consulte a lista completa de [CSPs com suporte em dispositivos do HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Os administradores de ti também podem gerenciar o CSP de políticas em dispositivos, ver a lista completa de [CSPs de política compatíveis com o HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## Métodos de configuração

### Configurar com o MDM

Provedores e diretivas podem ser facilmente gerenciados em qualquer dispositivo pessoal ou corporativo registrado em um sistema MDM. Depois que um dispositivo estiver registrado na sua solução MDM, você poderá gerenciá-lo ou definir dispositivos usando configurações de dispositivo. Saiba mais sobre como [gerenciar seus dispositivos do HoloLens por meio do MDM](hololens-mdm-configure.md).

### Configurar com pacotes de provisionamento

O HoloLens 2 também oferece suporte à configuração de um conjunto limitado de configurações de CSP para dispositivos do HoloLens 2 por meio de pacotes de provisionamento personalizados. Os pacotes de provisionamento geralmente são aproveitados para dispositivos gerenciados não MDM e exigem que sejam aplicados manualmente a cada dispositivo. Leia informações sobre a criação [de pacotes de aprovisionamento personalizados para o HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).

## Configurações

### Restrições comuns de dispositivo

Algumas restrições de dispositivo são simples e desabilitam uma funcionalidade ou conexão com o dispositivo. Para saber mais sobre essas informações, leia mais sobre as [restrições comuns do dispositivo.](hololens-common-device-restrictions.md)

### Modos de quiosque

Use o modo de quiosque para controlar quais identidades têm acesso a quais aplicativos por padrão. Os quiosques podem ser usados para um único aplicativo ou uma experiência de interface do usuário de vários aplicativos. Configurações do quiosque variam de um único aplicativo para qualquer pessoa que esteja usando o dispositivo, a seleções diferentes de aplicativos para grupos diferentes. O modo de quiosque não interrompe "aplicativos permitidos" de iniciar outros aplicativos e não foi projetado para nunca. Saiba mais em como [ler sobre modos de quiosque e como usá-los](hololens-kiosk.md).

### Visibilidade da página Configurações

Use a política de aplicativos de configurações para controlar quais identidades têm acesso às configurações por padrão. Usando esta política, o aplicativo configurações pode ser configurado para mostrar apenas as páginas selecionadas ou ocultar todas as páginas selecionadas. [Leia sobre como configurar as páginas disponíveis](settings-uri-list.md).

No momento, esse recurso só está disponível em [compilações do Windows Insider](hololens-insider.md). Certifique-se de que os dispositivos que você pretende usar nesse recurso estejam no Build 19041.1349 +.

### WDAC

Use a configuração WDAC para controlar quais aplicativos/processos são permitidos/despermitidos para serem iniciados independentemente de o sistema estar ou não no modo quiosque.
[Veja nossa visão geral para WDAC.](windows-defender-application-control-wdac.md)
