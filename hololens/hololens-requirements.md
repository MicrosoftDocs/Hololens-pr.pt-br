---
title: Cenários comuns de implantação
description: saiba mais sobre como implantar e gerenciar HoloLens em ambientes corporativos, incluindo infraestrutura, Azure Active Directory e gerenciamento de dispositivos móveis.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032021"
---
# <a name="common-deployment-scenarios"></a>Cenários comuns de implantação

## <a name="overview"></a>Visão geral

Descobrir como implantar um novo dispositivo pode ser um esforço ao experimentá-lo pela primeira vez. aqui, compartilhamos maneiras diferentes de implantar e gerenciar Microsoft HoloLens 2 dispositivos na organização.

Você deseja que as soluções sejam implantadas em escala. Queremos colocá-lo lá. Primeiro, vamos falar sobre as etapas para implantar dispositivos, portanto hologramas, para obter valor para seu cenário de realidade misturada de destino, se você estiver usando a assistência remota D365, guias ou um aplicativo habilitado para serviço de realidade mista do Azure que você criou.

você pode ser um tomador de decisões de negócios, profissional de ti ou uma equipe de inovação que busca adotar HoloLens em sua organização. à medida que você cria uma prova de conceito para uma implantação dimensionada, nossos guias de implantação fazem sentido de HoloLens em sua infraestrutura de ti, independentemente de quão grande ou pequena. Os seguintes cenários de implantação são os mais comuns:

| Cenário |Uso | Pontos-chave |
|---------|---------|---------|
| [Cenário A: dispositivos conectados na nuvem](hololens2-cloud-connected-overview.md) | Quando você inicia a implantação pela primeira vez, pode começar pequeno e implantar um único dispositivo conectado à nuvem apenas para ver o processo básico. | Os dispositivos serão conectados aos serviços de nuvem e à Internet pública. Isso é mais adequado para casos de uso do cliente, serviços de campo e prova de conceito.|
| [Cenário B: rede da organização](hololens2-corp-connected-overview.md) | Conforme você implanta na produção em escala, talvez seja necessário integrá-la à rede de sua própria organização. | Os dispositivos serão conectados a uma rede Wi-Fi "corporativa". Isso é mais adequado para usuários internos ou para uso no ambiente corporativo.|
| [Cenário C: ambiente seguro offline](hololens-common-scenarios-offline-secure.md) | Alguns processos de missão crítica ou algumas políticas corporativas podem exigir o uso de ambientes offline. | Os dispositivos serão conectados a uma rede altamente restritiva ou serão puramente dispositivos offline. Isso é mais adequado para ambientes altamente seguros ou restrições de conectividade com a Internet em áreas remotas. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Cenário A: implantar em dispositivos conectados na nuvem

Esse cenário é comparável à implantação de dispositivos móveis gerenciados dentro de uma empresa. o HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN.

[![Cenário um diagrama.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Quando usar

Considere este modelo de implantação para:

* Implantando prova de conceito, pilotos e serviços de campo
* Implantando a [assistência remota](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Configurações básicas comuns

* As redes Wi-Fi normalmente são totalmente abertas na Internet e nos serviços de nuvem
* Ingresso no Azure AD com o registro automático de MDM (gerenciamento de dispositivo móvel)--MDM (Intune) gerenciado
* Os usuários entram com sua própria conta corporativa (Azure AD)
  * Um ou vários usuários por dispositivo com suporte
* Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente abertas para quiosque de aplicativo único.
* Um ou mais aplicativos são implantados por meio do MDM

### <a name="common-challenges"></a>Desafios comuns

* determinando quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos de cenário

o guia conectado na nuvem correspondente aborda como registrar HoloLens 2 em seu gerenciamento de dispositivo, aplicar licenças conforme necessário e validar que os usuários finais podem usar imediatamente a assistência remota após a configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implantação conectada na nuvem](hololens2-cloud-connected-overview.md)

Use o guia de clientes externos para implantar dispositivos em um site remoto para uso externo de curto ou longo prazo.

> [!div class="nextstepaction"]
> [Guia de implantação (clientes externos) conectados à nuvem](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Cenário B: implantar dentro da rede da sua organização

esse cenário é idêntico a uma implantação clássica para a maioria dos Windows 10 PCs. o HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Serviços de nuvem e Internet podem ser limitados. 

[![Diagrama de cenário B1.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama de cenário B2.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Quando usar

Considere este modelo de implantação para:

* Usuários internos
* Implantando em escala (piloto e produção) no ambiente corporativo

### <a name="basic-common-configurations"></a>Configurações básicas comuns

* Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.
* Ingresso no Azure AD com o registro automático do MDM
* MDM (Intune) gerenciado
* Os usuários entram com sua própria conta corporativa (Azure AD)
  * Um ou vários usuários por dispositivo com suporte
* Níveis variados de configurações de bloqueio de dispositivo são aplicadas com base em casos de uso específicos, de totalmente abertas para quiosque de aplicativo único.
* Um ou mais aplicativos são implantados por meio do MDM

### <a name="common-challenges"></a>Desafios comuns

* o HoloLens 2 não dá suporte a ingresso no AD local ou System Center Configuration Manager (SCCM). Somente ingresso no Azure AD com o MDM. hoje em dia, muitas empresas ainda implantam Windows 10 PCs nesse cenário como dispositivos ingressados no AD local, gerenciados pelo SCCM e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções de MDM baseadas em nuvem.
* como HoloLens 2 é um dispositivo de nuvem primeiro, ele depende muito da internet e dos serviços conectados na nuvem para autenticação de usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante. ao se conectar a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para habilitar o acesso para HoloLens 2 e os aplicativos executados nele.
* A conectividade de Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o usuário na rede. a infraestrutura ou as configurações necessárias para implantar certificados para Windows 10 dispositivos por meio do MDM podem ser difíceis de configurar.

o guia corporativo conectado correspondente instrui sobre como registrar HoloLens 2 em seu gerenciamento de dispositivo existente, aplicar licenças conforme necessário e validar que os usuários finais podem operar um guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados após a configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implantação corporativo conectado](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Cenário C: implantar em ambiente offline seguro

Essa é uma implantação típica para locais altamente seguros ou confidenciais. o HoloLens 2 é implantado para uso principalmente offline, sem acesso à rede ou à internet.

[![Diagrama seguro offline 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Quando usar

Considere este modelo de implantação para:

* Ambientes altamente seguros em que os dados precisam ser mantidos em casa
* "Experiências" em que o público usará os dispositivos
* Problema de conectividade com a Internet na área remota

### <a name="basic-common-configurations"></a>Configurações básicas comuns

* A conectividade do Wi-Fi está desabilitada. A Ethernet via USB pode estar habilitada para conectividade de LAN, se necessário
* Não gerenciado
* Conta de usuário local para entrada do dispositivo
  * o HoloLens 2 dá suporte a apenas uma conta local
* Níveis variados de configurações de bloqueio de dispositivo são aplicadas por meio de pacotes de provisionamento com base em casos de uso específicos. Essas configurações normalmente são restritas devido a requisitos de ambiente seguro
* Um ou mais aplicativos são implantados por meio do pacote de provisionamento

### <a name="common-challenges"></a>Desafios comuns

* Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento
* os serviços de nuvem não podem ser usados, portanto limitando os recursos de HoloLens 2.
* Maior sobrecarga administrativa, uma vez que esses dispositivos precisam ser configurados, configurados e atualizados manualmente.

o guia seguro Offline correspondente fornece instruções para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros.

> [!div class="nextstepaction"]
> [Guia de implantação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)
