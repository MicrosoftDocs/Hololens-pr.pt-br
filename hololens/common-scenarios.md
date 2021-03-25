---
title: Cenários comuns de implantação da infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em implantações de infraestrutura diferentes para realidade mista.
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448489"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Visão geral dos cenários comuns de implantação de infraestrutura

Essas informações a seguir fornece uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos do Microsoft HoloLens 2 dentro da empresa. Geralmente, a maneira como você gerencia seus dispositivos e como acessar os recursos da sua organização é amplamente determinada por fatores já em uso. Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivo comum nos cenários a seguir e experimentar nossos guias para implantar no cenário que corresponde às suas necessidades.

## <a name="scenarios"></a>Cenários

O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2.
![Diagrama de cenários](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Cenário A: Implantar em dispositivos de conexão na nuvem

O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN. Essa implantação é semelhante a dispositivos móveis gerenciados em uma empresa.
 * Configurações Comuns Básicas
   * Wi-Fi redes normalmente estão totalmente abertas para os serviços de Internet e Nuvem.
   * Participação automática do Azure AD com o Registro Automático de Gerenciamento de Dispositivo Móvel (MDM), MDM (Intune) Gerenciado
   * Os usuários entrar com sua própria conta corporativa (Azure AD)
     * Usuários individuais ou múltiplos por dispositivo com suporte
   * Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto até Quiosque de Aplicativo Único.
   * Um ou mais aplicativos são implantados por meio do MDM

* Desafios comuns
   * Determinando quais configurações de MDM serão aplicadas ao HoloLens 2 com base nos requisitos de cenário.

Para um guia de implantação semelhante ao cenário Uma revisão do nosso guia para [o HoloLens 2](hololens2-cloud-connected-overview.md)conectado à nuvem com Assistência Remota.

> [!div class="nextstepaction"]
> [Guia de Implantação – HoloLens 2 conectado à nuvem com Assistência Remota](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Cenário B: Implantar dentro da rede da sua organização

O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Os serviços de Internet e nuvem podem ser limitados. Essa implantação é uma implantação típica para a maioria dos computadores windows 10.

 * Configurações Comuns Básicas
   * Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de Nuvem.
   * Azure AD Join with MDM Auto Enrollment
   * MDM (Intune) Gerenciado
   * Os usuários entrar com sua própria conta corporativa (Azure AD)
     * Usuários individuais ou múltiplos por dispositivo com suporte
   * Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto até Quiosque de Aplicativo Único.
   * Um ou mais aplicativos são implantados por meio do MDM

 * Desafios comuns
   * O HoloLens 2 não dá suporte ao AD join ou SCCM local. Somente o Azure AD ingressará no MDM. Muitas empresas ainda implantam computadores windows 10 neste cenário como dispositivos ingressados no AD local, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos internos do Windows 10 por meio de soluções MDM baseadas em nuvem.
   * Como o HoloLens 2 é um primeiro dispositivo de nuvem, ele depende muito dos serviços conectados à Internet e à nuvem para autenticação do usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante. Ao se conectar a uma rede corporativa, as regras de Proxy/Firewall provavelmente precisarão ser ajustadas para habilitar o acesso para o HoloLens 2 e os aplicativos que são executados nele.
   * A Wi-Fi conectividade corporativa normalmente exige certificados para autenticar o dispositivo ou o usuário na rede. A infraestrutura ou configurações necessárias para implantar certificados em dispositivos Windows 10 por meio do MDM pode ser um desafio para configurar.

> [!div class="nextstepaction"]
> [Guia de Implantação – HoloLens 2 conectado corporativo com Guias do Dynamics 365](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Cenário C: Implantar em ambiente offline seguro

O HoloLens 2 é implantado para uso principalmente offline sem acesso à rede ou à Internet. Essa é uma implantação típica para locais altamente seguros ou confidenciais.
 * Configurações Comuns Básicas
   * Wi-Fi conectividade está desabilitada. Ethernet via USB pode estar habilitada para conectividade lan, se necessário.
   * Não Gerenciado.
   * Conta de usuário local para entrada de dispositivo.
     * O HoloLens 2 dá suporte a apenas uma conta local.
   * Níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de Pacotes de Provisionamento com base em casos de uso específicos. Essas configurações geralmente são restritas devido aos requisitos de ambiente seguro.
   * Um ou mais aplicativos são implantados por meio do Pacote de Provisionamento

 * Desafios comuns
   * Há um conjunto limitado de configurações disponíveis por meio de Pacotes de Provisionamento
   * Os serviços de nuvem não podem ser usados, portanto, limitando os recursos do HoloLens 2.
   * Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.

Para obter um guia de implantação semelhante a esse cenário, revise nosso [Guia de Implantação Segura Offline.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Guia de Implantação – HoloLens Seguro Offline 2](hololens-common-scenarios-offline-secure.md)
