---
title: Cenários comuns de implantação da infraestrutura
description: Alguns cenários comuns de implantação baseados em infra-estruturas comuns diferentes
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195564"
---
# Visão geral dos cenários comuns de implantação de infraestrutura

Essas informações a seguir fornecem uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 na empresa. Muitas vezes, como você gerencia seus dispositivos e como o acesso aos recursos da sua organização é determinado por fatores que já estão em vigor. Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivos comuns nos seguintes cenários e experimentar nossos guias para a implantação no cenário que atenda às suas necessidades.

## Cenários

O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2.
![Diagrama de cenários](images/scenarios.jpg)

### Cenário A: implantar em dispositivos de conexão em nuvem

O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados pela VPN. Isso é uma implantação muito semelhante a dispositivos móveis gerenciados dentro de uma empresa.
 * Configurações básicas básicas
   * Geralmente, as redes Wi-Fi são totalmente abertas para a Internet e os serviços de nuvem.
   * Ingressar no Azure AD com o registro automático do MDM--gerenciamento de MDM (Intune)
   * Os usuários entram com sua própria conta corporativa (AAD)
     * Suporte para um ou vários usuários por dispositivo
   * Os níveis variáveis das configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, de totalmente abertos para o quiosque de aplicativo único.
   * Um ou mais aplicativos são implantados via MDM

* Desafios comuns
   * Determinar quais configurações do MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.

Para um guia de implantação semelhante a este cenário, consulte o nosso guia para o [HoloLens conectado à nuvem 2 com assistência remota](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guia de implantação – HoloLens conectado à nuvem 2 com assistência remota](hololens2-cloud-connected-overview.md)

### Cenário B: implantar dentro da rede da sua organização

O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Os serviços de nuvem e Internet podem ser limitados. Esta é uma implantação típica para a maioria dos computadores com Windows 10.
 * Configurações básicas básicas
   * Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.
   * Ingressar no Azure AD com o registro automático do MDM
   * Gerenciamento de MDM (Intune)
   * Os usuários entram com sua própria conta corporativa (AAD)
     * Suporte para um ou vários usuários por dispositivo
   * Os níveis variáveis das configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, de totalmente abertos para o quiosque de aplicativo único.
   * Um ou mais aplicativos são implantados via MDM

 * Desafios comuns
   * O HoloLens 2 não é compatível com o ingresso no AD local ou SCCM. Somente ingresso do Azure AD com MDM. Hoje em dia, muitas empresas ainda implantam computadores Windows 10 nesse cenário, como os dispositivos ingressados no AD, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções MDM baseadas em nuvem.
   * Como o HoloLens 2 é um dispositivo de nuvem, ele depende muito de serviços conectados à Internet e na nuvem para autenticação de usuários, atualizações de so, gerenciamento de MDM, etc. Ao conectar-se a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para permitir o acesso para o HoloLens 2 e os aplicativos que são executados nele.
   * Geralmente, a conectividade com Wi-Fi corporativos requer certificados para autenticar o dispositivo ou o usuário na rede. A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio de MDM podem ser difíceis de configurar.

### Cenário C: implantar no ambiente offline seguro

O HoloLens 2 é implantado para ser usado principalmente offline sem acesso à Internet ou à rede. Esta é uma implantação típica para locais altamente seguros ou confidenciais.
 * Configurações básicas básicas
   * Wi-Fi conectividade está desabilitada. A Ethernet via USB pode estar ativada para conectividade de LAN, se necessário.
   * Não gerenciado.
   * Conta de usuário local para entrada de dispositivo.
     * O HoloLens 2 oferece suporte a apenas 1 conta local.
   * Os níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de pacotes de provisionamento com base em casos de uso específicos. Essas configurações geralmente são muito restritas devido a requisitos de ambiente seguro.
   * Um ou mais aplicativos são implantados por meio do pacote de provisionamento

 * Desafios comuns
   * Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento
   * Os serviços de nuvem não podem ser aproveitados, portanto limitando os recursos do HoloLens 2.
   * Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.

Para obter um guia de implantação semelhante a este cenário, consulte o nosso [Guia de implantação seguro offline](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guia de implantação – HoloLens offline seguro 2](hololens-common-scenarios-offline-secure.md)
