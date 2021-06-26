---
title: Planejando a implantação do HoloLens 2 em um ambiente comercial
description: Saiba mais sobre como implantar e gerenciar o HoloLens em ambientes empresariais, incluindo infraestrutura, Azure Active Directory e gerenciamento de dispositivo móvel.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924597"
---
# <a name="common-deployment-scenarios"></a>Cenários comuns de implantação

## <a name="overview"></a>Visão geral

Esta página fornece uma visão geral da arquitetura de alto nível para três cenários comuns ao implantar e gerenciar Microsoft HoloLens 2 dispositivos dentro da empresa.

Geralmente, a maneira como você gerencia seus dispositivos e acessa os recursos da sua organização é determinada em grande parte pelos fatores já em uso. Com base em sua infraestrutura existente, convidamos você a revisar o MDM (estilo de gerenciamento de dispositivo) comum nos cenários a seguir e, em seguida, ler Planejando implantações do [HoloLens 2](hololens-core-components.md) em um ambiente comercial para determinar qual cenário corresponde às suas necessidades. Também há três guias correspondentes disponíveis para uso durante a implantação.


 1. [Guia de implantação do ambiente conectado à nuvem](hololens2-cloud-connected-overview.md)
     1. [Guia de implantação do ambiente conectado à nuvem (clientes externos)](hololens2-deployment-guide.md)
 1. [Guia de implantação de rede corporativa](hololens2-corp-connected-overview.md)
 1. [Guia de implantação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Cenário A: Implantar em dispositivos conectados à nuvem

Esse cenário é comparável à implantação de dispositivos móveis gerenciados em uma empresa. O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN. 
 * Configurações comuns básicas
   * Wi-Fi redes são normalmente totalmente abertas para os serviços de Internet e Nuvem.
   * Ingressar no Azure AD com o registro automático do MDM (Mobile Gerenciamento de Dispositivos) – MDM (Intune) Gerenciado
   * Os usuários entrarão com sua própria conta corporativa (Azure AD)
     * Usuários individuais ou múltiplos por dispositivo com suporte
   * Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.
   * Um ou mais aplicativos são implantados por meio do MDM

* Desafios comuns
   * Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos do cenário.

[![Cenário Um diagrama ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

O guia conectado à nuvem correspondente aborda como registrar o HoloLens 2 no gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na configuração do dispositivo. Use o guia Clientes Externos para implantar dispositivos em um site remoto para uso externo de curto ou longo prazo.

> [!div class="nextstepaction"]
> [Guia de implantação do ambiente conectado à nuvem](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Guia de implantação do ambiente conectado à nuvem (clientes externos)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Cenário B: Implantar dentro da rede da sua organização

Esse cenário é idêntico a uma implantação clássica para a maioria Windows 10 PCs. O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Serviços de Internet e nuvem podem ser limitados. 

 * Configurações comuns básicas
   * Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.
   * Ingressar no Azure AD com registro automático do MDM
   * MDM (Intune) Gerenciado
   * Os usuários entrarão com sua própria conta corporativa (Azure AD)
     * Usuários individuais ou múltiplos por dispositivo com suporte
   * Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.
   * Um ou mais aplicativos são implantados por meio do MDM

 * Desafios comuns
   * O HoloLens 2 não dá suporte ao SCCM ou ao AD local. Somente a junção do Azure AD ao MDM. Muitas empresas hoje ainda implantam PCs Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo SCCM (System Center Gerenciador de Configurações) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos internos Windows 10 por meio de soluções de MDM baseadas em nuvem.
   * Como o HoloLens 2 é um primeiro dispositivo de nuvem, ele depende muito dos serviços conectados à Internet e à nuvem para autenticação de usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante. Ao se conectar a uma rede corporativa, as regras de Proxy/Firewall provavelmente precisarão ser ajustadas para habilitar o acesso ao HoloLens 2 e aos aplicativos que são executados nele.
   * A Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o usuário na rede. A infraestrutura ou as configurações necessárias para implantar certificados Windows 10 dispositivos por meio do MDM pode ser um desafio para configurar.

[![Diagrama do cenário B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama do cenário B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

O guia de rede corporativa correspondente instrui sobre como registrar o HoloLens 2 em seu gerenciamento de dispositivo existente, aplicar licenças conforme necessário e validar se os usuários finais podem operar um Guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados após a configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implantação de rede corporativa](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Cenário C: Implantar em um ambiente offline seguro

Essa é uma implantação típica para locais altamente seguros ou confidenciais. O HoloLens 2 é implantado para uso principalmente offline sem acesso à rede ou à Internet. 
 * Configurações comuns básicas
   * Wi-Fi conectividade está desabilitada. Ethernet via USB pode ser habilitada para conectividade lan, se necessário.
   * Não Gerenciado.
   * Conta de usuário local para entrada do dispositivo.
     * O HoloLens 2 dá suporte a apenas uma conta local.
   * Níveis variados de configurações de bloqueio de dispositivo são aplicados por meio de Pacotes de Provisionamento com base em casos de uso específicos. Essas configurações normalmente são restritas devido aos requisitos de ambiente seguro.
   * Um ou mais aplicativos são implantados por meio do Pacote de Provisionamento

 * Desafios comuns
   * Há um conjunto limitado de configurações disponíveis por meio de Pacotes de Provisionamento
   * Os serviços de nuvem não podem ser usados, limitando as funcionalidades do HoloLens 2.
   * Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.

[![Diagrama seguro offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

O guia seguro Offline correspondente fornece instruções para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros.

> [!div class="nextstepaction"]
> [Guia de implantação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)


