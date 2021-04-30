---
title: Cenários comuns de implantação de infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em implantações de infraestrutura diferentes para realidade misturada.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308133"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Visão geral dos cenários comuns de implantação de infraestrutura

Essas informações a seguir fornecem uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 dentro da empresa. Geralmente, a maneira como você gerencia seus dispositivos e como acessar os recursos de sua organização é basicamente determinado por fatores já estabelecidos. Com base na infraestrutura existente, convidamos você a examinar o estilo comum de gerenciamento de dispositivos nos cenários a seguir e experimentar nossos guias para a implantação no cenário que atenda às suas necessidades.

## <a name="scenarios"></a>Cenários

O diagrama a seguir representa três cenários típicos para implantações do HoloLens 2.
![Diagrama de cenários](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Cenário A: implantar em dispositivos do Cloud Connect

O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN. Essa implantação é semelhante a dispositivos móveis gerenciados dentro de uma empresa.
 * Configurações básicas comuns
   * As redes Wi-Fi normalmente são totalmente abertas na Internet e nos serviços de nuvem.
   * Ingresso no Azure AD com o registro automático de MDM (gerenciamento de dispositivo móvel)--MDM (Intune) gerenciado
   * Os usuários entram com sua própria conta corporativa (Azure AD)
     * Um ou vários usuários por dispositivo com suporte
   * Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente abertas para quiosque de aplicativo único.
   * Um ou mais aplicativos são implantados por meio do MDM

* Desafios comuns
   * Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.

Para obter um guia de implantação semelhante ao cenário A, examine nosso guia para a [nuvem conectada no HoloLens 2 com o auxílio remoto](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guia de implantação – nuvem conectada no Cloud 2 com assistência remota](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Cenário B: implantar dentro da rede da sua organização

O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Serviços de nuvem e Internet podem ser limitados. Essa implantação é uma implantação típica para a maioria dos PCs com Windows 10.

 * Configurações básicas comuns
   * Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.
   * Ingresso no Azure AD com o registro automático do MDM
   * MDM (Intune) gerenciado
   * Os usuários entram com sua própria conta corporativa (Azure AD)
     * Um ou vários usuários por dispositivo com suporte
   * Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente abertas para quiosque de aplicativo único.
   * Um ou mais aplicativos são implantados por meio do MDM

 * Desafios comuns
   * O HoloLens 2 não dá suporte ao ingresso no AD local ou ao SCCM. Somente ingresso no Azure AD com o MDM. Hoje em dia, muitas empresas ainda implantam PCs com Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções de MDM baseadas em nuvem.
   * Como o HoloLens 2 é um dispositivo de nuvem primeiro, ele depende muito da Internet e dos serviços conectados na nuvem para autenticação do usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante. Ao se conectar a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para habilitar o acesso para o HoloLens 2 e os aplicativos executados nele.
   * A conectividade de Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o usuário na rede. A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio do MDM podem ser difíceis de configurar.

> [!div class="nextstepaction"]
> [Guia de implantação – o HoloLens 2 conectado à empresa com guias do Dynamics 365](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Cenário C: implantar em ambiente offline seguro

O HoloLens 2 é implantado para uso principalmente offline, sem acesso à rede ou à Internet. Essa é uma implantação típica para locais altamente seguros ou confidenciais.
 * Configurações básicas comuns
   * A conectividade do Wi-Fi está desabilitada. A Ethernet via USB pode estar habilitada para conectividade de LAN, se necessário.
   * Não gerenciado.
   * Conta de usuário local para entrada do dispositivo.
     * O HoloLens 2 dá suporte a apenas uma conta local.
   * Níveis variados de configurações de bloqueio de dispositivo são aplicadas por meio de pacotes de provisionamento com base em casos de uso específicos. Essas configurações normalmente são restritas devido a requisitos de ambiente seguro.
   * Um ou mais aplicativos são implantados por meio do pacote de provisionamento

 * Desafios comuns
   * Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento
   * Os serviços de nuvem não podem ser usados, portanto limitando os recursos do HoloLens 2.
   * Maior sobrecarga administrativa, uma vez que esses dispositivos precisam ser configurados, configurados e atualizados manualmente.

Para obter um guia de implantação semelhante a este cenário, examine nosso [Guia de implantação seguro offline](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guia de implantação – HoloLens seguro offline 2](hololens-common-scenarios-offline-secure.md)
