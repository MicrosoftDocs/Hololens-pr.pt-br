---
title: Cenários comuns de implantação
description: Saiba mais sobre como implantar e gerenciar HoloLens em ambientes corporativos, incluindo infraestrutura, Azure Active Directory e gerenciamento de dispositivo móvel.
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
ms.openlocfilehash: 529dde590c30d4a51fa8ae61e9d37d22170dc271
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659056"
---
# <a name="common-deployment-scenarios"></a>Cenários comuns de implantação

## <a name="overview"></a>Visão geral

Descobrir como implantar um novo dispositivo pode ser uma dificuldade quando você o experimenta pela primeira vez. Aqui, compartilhamos diferentes maneiras de implantar e gerenciar Microsoft HoloLens 2 dispositivos dentro da organização.

Você deseja soluções – implantadas em escala. Queremos que você vá para lá. Primeiro, vamos falar sobre as etapas para implantar dispositivos, portanto hologramas, para obter valor para seu cenário de realidade misturada de destino, independentemente de você estar usando o D365 Remote Assist, Guides ou um aplicativo habilitado para serviço de realidade misturada do Azure que você criou.

Você pode ser um tomadores de decisões de negócios, profissional de TI ou uma equipe de inovação que quer adotar HoloLens dentro de sua organização. À medida que você cria da prova de conceito para uma implantação dimensionada, nossos guias de implantação fazem sentido HoloLens sua infraestrutura de TI, independentemente de quão grande ou pequeno. Os seguintes cenários de implantação são os mais comuns:

| Cenário |Uso | Pontos-chave |
|---------|---------|---------|
| [Cenário A: Dispositivos conectados à nuvem](hololens2-cloud-connected-overview.md) | Quando você inicia a implantação pela primeira vez, pode começar pequeno e implantar um único dispositivo conectado à nuvem apenas para ver o processo básico. | Os dispositivos serão conectados aos serviços de nuvem e à Internet pública. Isso é mais adequado para casos de uso do cliente, serviços de campo e prova de conceito.|
| [Cenário B: Rede da organização](hololens2-corp-connected-overview.md) | Conforme você implanta em produção em escala, talvez seja necessário integrar-se à rede da sua própria organização. | Os dispositivos serão conectados a uma rede wi-fi "Corporativa". Isso é mais adequado para usuários internos ou para uso no ambiente corporativo.|
| [Cenário C: Ambiente seguro offline](hololens-common-scenarios-offline-secure.md) | Alguns processos críticos ou algumas políticas corporativas podem exigir o uso de ambientes offline. | Os dispositivos serão conectados a uma rede altamente restritiva ou serão dispositivos puramente offline. Isso é mais adequado para ambientes altamente seguros ou restrições de conectividade com a Internet em áreas remotas. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Cenário A: Implantar em dispositivos conectados à nuvem

Esse cenário é comparável à implantação de dispositivos móveis gerenciados em uma empresa. HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN.

[![Cenário Um diagrama](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Quando usar

Considere este modelo de implantação para:

* Implantando uma prova de conceito, equipes e serviços de campo
* Implantando [o Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Configurações comuns básicas

* Wi-Fi redes são normalmente totalmente abertas para a Internet e os serviços de nuvem
* Ingressar no Azure AD com o registro automático do MDM (Mobile Gerenciamento de Dispositivos) – MDM (Intune) Gerenciado
* Os usuários entrarão com sua própria conta corporativa (Azure AD)
  * Usuários individuais ou múltiplos por dispositivo com suporte
* Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.
* Um ou mais aplicativos são implantados por meio do MDM

### <a name="common-challenges"></a>Desafios comuns

* Determinando quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos do cenário

O guia conectado à nuvem correspondente aborda como registrar o HoloLens 2 em seu gerenciamento de dispositivos, aplicar licenças conforme necessário e validar se os usuários finais podem usar imediatamente a Assistência Remota na configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implantação conectado à nuvem](hololens2-cloud-connected-overview.md)

Use o guia Clientes Externos para implantar dispositivos em um site remoto para uso externo de curto ou longo prazo.

> [!div class="nextstepaction"]
> [Guia de implantação do Cloud Connected (Clientes Externos)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Cenário B: Implantar dentro da rede da sua organização

Esse cenário é idêntico a uma implantação clássica para a maioria Windows 10 PCs. HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Serviços de Internet e nuvem podem ser limitados. 

[![Diagrama do cenário B1](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama do cenário B2](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Quando usar

Considere este modelo de implantação para:

* Usuários internos
* Implantação em escala (Piloto e Produção) no ambiente corporativo

### <a name="basic-common-configurations"></a>Configurações comuns básicas

* Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.
* Ingressar no Azure AD com registro automático do MDM
* MDM (Intune) Gerenciado
* Os usuários entrarão com sua própria conta corporativa (Azure AD)
  * Usuários individuais ou múltiplos por dispositivo com suporte
* Níveis variados de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, do Totalmente Aberto ao Quiosque de Aplicativo Único.
* Um ou mais aplicativos são implantados por meio do MDM

### <a name="common-challenges"></a>Desafios comuns

* HoloLens 2 não dá suporte ao SCCM (AD join ou System Center Configuration Manager) local. Somente a junção do Azure AD ao MDM. Muitas empresas hoje ainda implantam PCs Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo SCCM e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos internos Windows 10 por meio de soluções de MDM baseadas em nuvem.
* Como HoloLens 2 é um primeiro dispositivo de nuvem, ele depende muito dos serviços conectados à Internet e à nuvem para autenticação de usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante. Ao se conectar a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para habilitar o acesso para o HoloLens 2 e os aplicativos que são executados nele.
* A Wi-Fi corporativa normalmente requer certificados para autenticar o dispositivo ou o usuário na rede. A infraestrutura ou as configurações necessárias para implantar certificados Windows 10 dispositivos por meio do MDM pode ser um desafio para configurar.

O guia Conectado Corporativo correspondente instrui sobre como registrar o HoloLens 2 em seu gerenciamento de dispositivo existente, aplicar licenças conforme necessário e validar se os usuários finais podem operar um Guia do Dynamics 365, bem como usar aplicativos de linha de negócios personalizados, após a configuração do dispositivo.

> [!div class="nextstepaction"]
> [Guia de implantação conectada corporativa](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Cenário C: Implantar em um ambiente offline seguro

Essa é uma implantação típica para locais altamente seguros ou confidenciais. HoloLens 2 é implantado para uso principalmente offline sem acesso à rede ou à Internet.

[![Diagrama seguro offline 1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Quando usar

Considere este modelo de implantação para:

* Ambientes altamente seguros em que os dados precisam ser mantidos em casa
* "Experiências" em que o público estará usando os dispositivos
* Problema de conectividade com a Internet na área remota

### <a name="basic-common-configurations"></a>Configurações comuns básicas

* Wi-Fi conectividade está desabilitada. Ethernet via USB pode ser habilitada para conectividade lan, se necessário
* Não Gerenciado
* Conta de usuário local para entrada do dispositivo
  * HoloLens 2 dá suporte a apenas uma conta local
* Níveis variados de configurações de bloqueio de dispositivo são aplicados por meio de Pacotes de Provisionamento com base em casos de uso específicos. Essas configurações normalmente são restritas devido a requisitos de ambiente seguro
* Um ou mais aplicativos são implantados por meio do Pacote de Provisionamento

### <a name="common-challenges"></a>Desafios comuns

* Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento
* Os serviços de nuvem não podem ser usados, portanto, limitando as HoloLens 2.
* Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.

O guia seguro offline correspondente fornece instruções para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros.

> [!div class="nextstepaction"]
> [Guia de implantação de ambiente seguro offline](hololens-common-scenarios-offline-secure.md)
