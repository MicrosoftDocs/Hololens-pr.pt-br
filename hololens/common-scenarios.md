---
title: Cenários comuns de implantação de infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em diferentes implantações de infraestrutura para realidade misturada.
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397407"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Visão geral de cenários comuns de implantação de infraestrutura

Essas informações a seguir fornece uma visão geral da arquitetura de alto nível para três cenários comuns ao implantar e gerenciar Microsoft HoloLens 2 dispositivos dentro da empresa. Geralmente, a maneira como você gerencia seus dispositivos e como acessar os recursos da sua organização é determinada em grande parte pelos fatores já em uso. Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivo comum nos cenários a seguir e experimentar nossos guias para implantação no cenário que corresponde às suas necessidades.

## <a name="scenarios"></a>Cenários

O diagrama a seguir representa dois cenários gerenciados típicos para implantações do HoloLens 2.
 

Também há um terceiro cenário que permite implantações seguras offline.

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Cenário A: Implantar em dispositivos conectados à nuvem

O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN. Essa implantação é semelhante a dispositivos móveis gerenciados em uma empresa.
 * Configurações comuns básicas
   * Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e Nuvem.
   * Ingressar no Azure AD com o registro automático do MDM (Mobile Gerenciamento de Dispositivos) – MDM (Intune) Gerenciado
   * Os usuários entrarão com sua própria conta corporativa (Azure AD)
     * Usuários individuais ou múltiplos por dispositivo com suporte
   * Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.
   * Um ou mais aplicativos são implantados por meio do MDM



* Desafios comuns
   * Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.

[![Cenário de um diagrama ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

Para obter um guia de implantação semelhante a este cenário, consulte o [Guia de implantação do ambiente conectado à nuvem](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guia de implantação do ambiente conectado à nuvem](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [Guia de implantação do ambiente conectado à nuvem (clientes externos)](hololens2-deployment-guide.md)

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

[![Diagrama ](images/deployment-guides-revised-scenario-b-01-1.png) do cenário B1](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama ](images/deployment-guides-revised-scenario-b-02-1.png) de cenário B2](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Para obter um guia de implantação semelhante a este cenário, consulte nosso guia para o [Guia de implantação de rede corporativa](hololens2-corp-connected-overview.md).

> [!div class="nextstepaction"]
> [Guia de implantação de rede corporativa](hololens2-corp-connected-overview.md)

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

[![Diagrama seguro offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Para obter um guia de implantação semelhante a este cenário, examine nosso [Guia de implantação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guia de implantação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)
