---
title: Cenários comuns de implantação da infraestrutura
description: Saiba mais sobre alguns dos cenários de implantação mais comuns com base em diferentes implantações de infraestrutura para realidade misturada.
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283622"
---
# Visão geral de cenários comuns de implantação de infraestrutura

Essas informações a seguir proporcionam uma visão geral da arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 dentro da empresa. Muitas vezes, a maneira como você gerencia seus dispositivos e como acessar os recursos da sua organização é amplamente determinada por fatores já em uso. Com base na infraestrutura existente, convidamos você a revisar o estilo de gerenciamento de dispositivo comum nos cenários a seguir e testar nossos guias para implantação no cenário que corresponde às suas necessidades.

## Cenários

O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2.
![Diagrama de cenários](images/scenarios.jpg)

### Cenário A: Implantar em dispositivos conectados à nuvem

O HoloLens 2 é implantado para uso principalmente em ambientes externos a uma rede corporativa. Os recursos corporativos não são acessados ou podem ser limitados por meio de VPN. Essa implantação é semelhante aos dispositivos móveis gerenciados dentro de uma empresa.
 * Configurações comuns básicas
   * Wi-Fi redes são normalmente totalmente abertas para os serviços de Nuvem e Internet.
   * Ingressar no Azure AD com o registro automático de gerenciamento de dispositivo móvel (MDM) – MDM (Intune) gerenciado
   * Os usuários podem entrar com sua própria conta corporativa (Azure AD)
     * Um ou vários usuários por dispositivo com suporte
   * Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto a Quiosque de Aplicativo Único.
   * Um ou mais aplicativos são implantados via MDM

* Desafios comuns
   * Determinar quais configurações de MDM aplicar ao HoloLens 2 com base nos requisitos de cenário.

Para ver um guia de implantação semelhante ao cenário, confira nosso guia para [o HoloLens 2](hololens2-cloud-connected-overview.md)conectado à nuvem com Assistência Remota.

> [!div class="nextstepaction"]
> [Guia de Implantação – HoloLens 2 conectado à nuvem com Assistência Remota](hololens2-cloud-connected-overview.md)

### Cenário B: Implantar dentro da rede da sua organização

O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Serviços de nuvem e Internet podem ser limitados. Essa implantação é típica para a maioria dos computadores com Windows 10.

 * Configurações comuns básicas
   * Wi-Fi rede é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.
   * Ingressar no Azure AD com o registro automático do MDM
   * MDM (Intune) Gerenciado
   * Os usuários podem entrar com sua própria conta corporativa (Azure AD)
     * Um ou vários usuários por dispositivo com suporte
   * Níveis variáveis de configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, desde Totalmente Aberto a Quiosque de Aplicativo Único.
   * Um ou mais aplicativos são implantados via MDM

 * Desafios comuns
   * O HoloLens 2 não dá suporte ao AD ou SCCM local. Somente o Azure AD entra no MDM. Muitas empresas hoje ainda implantam computadores Windows 10 nesse cenário como dispositivos ingressados no AD local, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Internos do Windows 10 por meio de soluções MDM baseadas em nuvem.
   * Como o HoloLens 2 é um primeiro dispositivo de nuvem, ele depende muito dos serviços conectados à Internet e à nuvem para autenticação do usuário, atualizações do sistema operacional, gerenciamento de MDM e assim por diante. Ao se conectar a uma rede corporativa, as regras de Proxy/Firewall provavelmente precisarão ser ajustadas para habilitar o acesso ao HoloLens 2 e aos aplicativos que são executados nele.
   * A Wi-Fi corporativa geralmente requer certificados para autenticar o dispositivo ou o usuário na rede. A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio do MDM pode ser desafiadora de configurar.

### Cenário C: Implantar em um ambiente offline seguro

O HoloLens 2 é implantado para uso principalmente offline sem acesso à rede ou à Internet. Essa é uma implantação típica para locais altamente seguros ou confidenciais.
 * Configurações comuns básicas
   * Wi-Fi conectividade está desabilitada. Ethernet via USB pode estar habilitada para conectividade lan, se necessário.
   * Não Gerenciado.
   * Conta de usuário local para entrada do dispositivo.
     * O HoloLens 2 dá suporte a apenas uma conta local.
   * Níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de Pacotes de Provisionamento com base em casos de uso específicos. Essas configurações são normalmente restritas devido a requisitos de ambiente seguro.
   * Um ou mais aplicativos são implantados por meio do Pacote de Provisionamento

 * Desafios comuns
   * Há um conjunto limitado de configurações disponíveis por meio de Pacotes de Provisionamento
   * Os serviços de nuvem não podem ser usados, portanto, limitando os recursos do HoloLens 2.
   * Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.

Para obter um guia de implantação semelhante a este cenário, revise nosso Guia [de Implantação Segura Offline.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Guia de Implantação – HoloLens Seguro Offline 2](hololens-common-scenarios-offline-secure.md)
