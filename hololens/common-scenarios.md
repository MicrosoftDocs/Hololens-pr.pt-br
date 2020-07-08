---
title: Cenários comuns de implantação de infraestrutura
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857859"
---
# Cenários comuns de implantação de infraestrutura
Essas informações a seguir fornecem uma visão geral de arquitetura de alto nível para três cenários comuns ao implantar e gerenciar dispositivos Microsoft HoloLens 2 na empresa.

## Cenários

O diagrama abaixo representa três cenários típicos para implantações do HoloLens 2. 
![possíveis](images/scenarios.jpg)

### Cenário A

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

### Cenário B

O HoloLens 2 é implantado para uso principalmente na rede corporativa com acesso a recursos corporativos internos. Os serviços de nuvem e Internet podem ser limitados. Esta é uma implantação típica para a maioria dos computadores com Windows 10.
 * Configurações básicas básicas
   * A rede Wi-Fi é uma rede corporativa interna com acesso a recursos internos e acesso limitado à Internet ou aos serviços de nuvem.
   * Ingressar no Azure AD com o registro automático do MDM 
   * Gerenciamento de MDM (Intune)
   * Os usuários entram com sua própria conta corporativa (AAD)
     * Suporte para um ou vários usuários por dispositivo
   * Os níveis variáveis das configurações de bloqueio de dispositivo são aplicados com base em casos de uso específicos, de totalmente abertos para o quiosque de aplicativo único.
   * Um ou mais aplicativos são implantados via MDM

 * Desafios comuns
   * O HoloLens 2 não é compatível com o ingresso no AD local ou SCCM. Somente ingresso do Azure AD com MDM. Hoje em dia, muitas empresas ainda implantam computadores Windows 10 nesse cenário, como os dispositivos ingressados no AD, gerenciados pelo System Center Configuration Manager (SCCM) e podem não ter a infraestrutura implantada/configurada para gerenciar dispositivos Windows 10 internos por meio de soluções MDM baseadas em nuvem.
   * Como o HoloLens 2 é um dispositivo de nuvem, ele depende muito de serviços conectados à Internet e na nuvem para autenticação de usuários, atualizações de so, gerenciamento de MDM, etc. Ao conectar-se a uma rede corporativa, as regras de proxy/firewall provavelmente precisarão ser ajustadas para permitir o acesso para o HoloLens 2 e os aplicativos que são executados nele. 
   * Geralmente, a conectividade Wi-Fi corporativa requer certificados para autenticar o dispositivo ou o usuário na rede. A infraestrutura ou as configurações necessárias para implantar certificados em dispositivos Windows 10 por meio de MDM podem ser difíceis de configurar.

### Cenário C

O HoloLens 2 é implantado para ser usado principalmente offline sem acesso à Internet ou à rede. Esta é uma implantação típica para locais altamente seguros ou confidenciais.
 * Configurações básicas básicas
   * A conectividade de Wi-Fi está desabilitada. A Ethernet via USB pode estar ativada para conectividade de LAN, se necessário.
   * Não gerenciado.
   * Conta de usuário local para entrada de dispositivo.
     * O HoloLens 2 oferece suporte a apenas 1 conta local.
   * Os níveis variáveis de configurações de bloqueio de dispositivo são aplicados por meio de pacotes de provisionamento com base em casos de uso específicos. Essas configurações geralmente são muito restritas devido a requisitos de ambiente seguro.
   * Um ou mais aplicativos são implantados por meio do pacote de provisionamento

 * Desafios comuns
   * Há um conjunto limitado de configurações disponíveis por meio de pacotes de provisionamento
   * Os serviços de nuvem não podem ser aproveitados, portanto limitando os recursos do HoloLens 2.
   * Maior sobrecarga administrativa, pois esses dispositivos devem ser configurados, configurados e atualizados manualmente.
