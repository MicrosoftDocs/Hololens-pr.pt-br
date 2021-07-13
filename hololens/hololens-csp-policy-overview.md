---
title: Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs
description: Saiba como configurar CSPs, política e gerenciamento de dispositivos usando pacotes de provisionamento e gerenciamento de dispositivos móveis.
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640450"
---
# <a name="configure-csps-and-device-management-overview"></a>Visão geral de Gerenciamento de Dispositivo e Configuração de CSPs

os administradores de ti podem definir e implementar configurações de política no HoloLens 2. As configurações que você usa serão diferentes de acordo com o cenário de implantação, e os dispositivos corporativos oferecerão à TI um controle mais amplo. no Windows 10, os provedores de serviços de configuração (CSP) são uma interface para ler, definir, modificar ou excluir as definições de configuração no dispositivo. Essas configurações são mapeadas para arquivos ou chaves do registro. Alguns provedores de serviços de configuração dão suporte ao formato WAP, alguns dão suporte ao SyncML e alguns dão suporte a ambos.

para obter mais informações sobre os csps de gerenciamento de dispositivos Windows 10 Holographic, consulte a lista completa de [csps com suporte em dispositivos HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#hololens).
os administradores de ti também podem gerenciar o CSP de política nos dispositivos, ver a lista completa de [CSPs de política com suporte pelo HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## <a name="configuration-methods"></a>Métodos de configuração

### <a name="configure-with-mdm"></a>Configurar com MDM

Os CSPs e as políticas podem ser facilmente gerenciados em qualquer dispositivo pessoal ou corporativo registrado em um sistema MDM. Depois que um dispositivo for registrado em sua solução de MDM, você poderá gerenciar esse dispositivo ou o conjunto de dispositivos usando as configurações do dispositivo. saiba mais sobre como [gerenciar seus dispositivos HoloLens por meio do MDM](hololens-mdm-configure.md).

### <a name="configure-with-provisioning-packages"></a>Configurar com pacotes de provisionamento

o HoloLens 2 também dá suporte à definição de um conjunto limitado de configurações de CSP para dispositivos HoloLens 2 por meio de pacotes de provisionamento personalizados. Os pacotes de provisionamento normalmente são utilizados para dispositivos não gerenciados por MDM e precisam ser aplicados manualmente a cada dispositivo. Leia informações sobre como criar [pacotes de provisionamento personalizados para HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Configurações

### <a name="common-device-restrictions"></a>Restrições comuns de dispositivo

Algumas restrições de dispositivo são tão simples e desabilitam uma funcionalidade ou conexão com o dispositivo. Para saber mais sobre essas informações, leia mais sobre as [restrições de dispositivo comuns.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Modos de quiosque

Use o modo de quiosque para controlar quais identidades têm acesso a quais aplicativos por padrão. Os quiosques podem ser usados para um único aplicativo ou uma experiência de interface do usuário de vários aplicativos. As configurações de quiosque variam de um único aplicativo para qualquer pessoa que use o dispositivo, para diferentes seleções de aplicativos para diferentes grupos. O modo de quiosque não impede que "aplicativos permitidos" iniciem outros aplicativos e não tenha sido projetado para nunca. Saiba mais [lendo sobre os modos de quiosque e como usá-los](hololens-kiosk.md).

### <a name="settings-page-visibility"></a>Configurações Visibilidade da página

Use Configurações política de aplicativo para controlar quais identidades têm acesso às configurações por padrão. usando essa política, o aplicativo Configurações pode ser configurado para mostrar apenas as páginas select ou ocultar todas as páginas selecionadas. [Leia sobre como configurar as páginas disponíveis](settings-uri-list.md).

atualmente, esse recurso só está disponível em [builds Windows insider](hololens-insider.md). Verifique se os dispositivos nos quais você pretende usar esse recurso estão no Build 19041.1349 +.

### <a name="wdac"></a>WDAC

Use a configuração WDAC para controlar quais aplicativos/processos são permitidos/desautorizados a serem iniciados independentemente de o sistema estar no modo de quiosque ou não.
[Consulte nossa visão geral para o WDAC.](windows-defender-application-control-wdac.md)
