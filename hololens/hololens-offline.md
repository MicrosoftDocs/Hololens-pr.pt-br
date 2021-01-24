---
title: Gerenciar pontos de extremidade de conexão para o HoloLens
description: Aprenda a configurar um HoloLens em uma rede Wi-Fi enquanto gerencia e configura terminais de conexão.
keywords: hololens, off-line, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2208291aea5bfa9cbedd09d40fbbb83b1faa627b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283942"
---
# Gerenciar pontos de extremidade de conexão para o HoloLens

Alguns componentes, aplicativos e serviços relacionados do HoloLens transferem dados aos terminais de rede da Microsoft. Este artigo lista diferentes terminais e URLs que precisam ser permitidos na sua configuração de rede (por exemplo, proxy ou firewall) para que esses componentes funcionem.    

## Configuração quase off-line

O HoloLens suporta um conjunto limitado de experiências off-line para clientes que têm restrições no ambiente de rede. No entanto, o HoloLens precisa de uma conexão de rede para passar pela configuração inicial do dispositivo e as seguintes URLs devem ser ativadas:

| Finalidade | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| Pin de AAD | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| Pin de MSA | https://account.live.com/msangc?fl=enroll |

## Configuração de ponto de extremidade

Além da lista acima, para tirar o máximo proveito da funcionalidade do HoloLens, os seguintes terminais precisam estar ativados na sua configuração de rede.


| Finalidade | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |   |   |   
|                                                     | ris-prod-atm.trafficmanager.net                                     |   |   |   |
|                                                     | validation-v2.sls.trafficmanager.net                                |   |   |   |
| Autenticação multifator do Azure AD                | https://secure.aadcdn.microsoftonline-p.com                         |   |   |   |
| Configurações do Intune e do MDM                       | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | cdn.onenote.net                                                     |   |   |   |
|                                                     | client.wns.windows.com                                              |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ctldl.windowsupdate.com                                             |   |   |   |
|                                                     | *displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | dm3p.wns.windows.com                                                |   |   |   |
|                                                     | *microsoft.com/pkiops/*                                             |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | r.manage.microsoft.com                                              |   |   |   |
|                                                     | tile-service.weather.microsoft.com                                  |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| Certificados                                        | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | https://www.microsoft.com/pkiops/*                                          |   |   |   |
| Cortana e Pesquisa                                  | store-images.*microsoft.com                                         |   |   |   |
|                                                     | www.bing.com/client                                                 |   |   |   |
|                                                     | www.bing.com                                                        |   |   |   |
|                                                     | www.bing.com/proactive                                              |   |   |   |
|                                                     | www.bing.com/threshold/xls.aspx                                     |   |   |   |
|                                                     | exo-ring.msedge.net                                                 |   |   |   |
|                                                     | fp.msedge.net                                                       |   |   |   |
|                                                     | fp-vp.azureedge.net                                                 |   |   |   |
|                                                     | odinvzc.azureedge.net                                               |   |   |   |
|                                                     | spo-ring.msedge.net                                                 |   |   |   |
| Autenticação de dispositivo                               | login.live.com*                                                     |   |   |   |
| Metadados de dispositivo                                     | dmd.metaservices.microsoft.com                                      |   |   |   |
| Location                                            | inference.location.live.net                                         |   |   |   |
|                                                     | location-inference-westus.cloudapp.net                              |   |   |   |
| Dados de diagnóstico                                     | v10.events.data.microsoft.com                                       |   |   |   |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |   |   |   |
|                                                     | https://www.microsoft.com                                                   |   |   |   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |   |   |   |
|                                                     | cs11.wpc.v0cdn.net                                                  |   |   |   |
|                                                     | cs1137.wpc.gammacdn.net                                             |   |   |   |
|                                                     | modern.watson.data.microsoft.com*                                   |   |   |   |
|                                                     | watson.telemetry.microsoft.com                                      |   |   |   |
| Licenciamento                                           | licensing.mp.microsoft.com                                          |   |   |   |
| Conta da Microsoft                                   | login.msa.akadns6.net                                               |   |   |   |
|                                                     | us.configsvc1.live.com.akadns.net                                   |   |   |   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |   |   |   |
| FWLink (serviço de redirecionamento de link de encaminhamento da Microsoft) | go.microsoft.com                                                    |   |   |   |
| Microsoft Store                                     | *.wns.windows.com                                                   |   |   |   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |   |   |   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |   |   |   |
|                                                     | store-images.microsoft.com                                          |   |   |   |
|                                                     | .md.mp.microsoft.com                                                |   |   |
|                                                     | *displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | pti.store.microsoft.com                                             |   |   |   |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |   |   |   |
|                                                     | markets.books.microsoft.com                                         |   |   |   |
|                                                     | share.microsoft.com                                                 |   |   |   |
| NCSI (Indicador de Status da Conexão de Rede)          | www.msftconnecttest.com*                                            |   |   |   |
| Office                                              | *.c-msedge.net                                                      |   |   |   |
|                                                     | *.e-msedge.net                                                      |   |   |   |
|                                                     | *.s-msedge.net                                                      |   |   |   |
|                                                     | nexusrules.officeapps.live.com                                      |   |   |   |
|                                                     | ocos-office365-s2s.msedge.net                                       |   |   |   |
|                                                     | officeclient.microsoft.com                                          |   |   |   |
|                                                     | outlook.office365.com                                               |   |   |   |
|                                                     | client-office365-tas.msedge.net                                     |   |   |   |
|                                                     | https://www.office.com                                                      |   |   |   |
|                                                     | onecollector.cloudapp.aria                                          |   |   |   |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |   |   |   |
|                                                     | self.events.data.microsoft.com                                      |   |   |   |
|                                                     | to-do.microsoft.com                                                 |   |   |   |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |   |   |   |
|                                                     | msagfx.live.com                                                     |   |   |   |
|                                                     | oneclient.sfx.ms                                                    |   |   |   |
| Aplicativo Fotos                                          | evoke-windowsservices-tas.msedge.net                                |   |   |   |
| Configurações                                            | cy2.settings.data.microsoft.com.akadns.net                          |   |   |   |
|                                                     | settings.data.microsoft.com                                         |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| Windows Defender                                    | wdcp.microsoft.com                                                  |   |   |   |
|                                                     | definitionupdates.microsoft.com                                     |   |   |   |
|                                                     | go.microsoft.com                                                    |   |   |   |
|                                                     | *smartscreen.microsoft.com                                          |   |   |   |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |   |   |   |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |   |   |   |
| Destaque do Windows                                   | *.search.msn.com                                                    |   |   |   |
|                                                     | arc.msn.com                                                         |   |   |   |
|                                                     | g.msn.com*                                                          |   |   |   |
|                                                     | query.prod.cms.rt.microsoft.com                                     |   |   |   |
|                                                     | ris.api.iris.microsoft.com                                          |   |   |   |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |   |   |   |
|                                                     | cs9.wac.phicdn.net                                                  |   |   |   |
|                                                     | emdl.ws.microsoft.com                                               |   |   |   |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |   |   |   |
|                                                     | *.windowsupdate.com                                                 |   |   |   |
|                                                     | *.delivery.mp.microsoft.com                                         |   |   |   |
|                                                     | *.update.microsoft.com                                              |   |   |   |



## Referências

> [!NOTE]
> Se você estiver implantando a Assistência remota do D365t, precisará ativar os terminais nesta [lista](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 
- [Configurar os dados de diagnóstico do Windows em sua organização](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Pontos de extremidade de conexão do Windows 10 Enterprise, versão 1903](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
- [Gerenciar conexões de componentes do sistema operacional Windows 10 com serviços Microsoft](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Gerenciar conexões de componentes do sistema operacional Windows 10 com serviços Microsoft usando o Servidor MDM do Microsoft Intune](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Requisitos de configuração de rede e largura de banda do Intune](https://docs.microsoft.com/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Terminais de rede do Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/intune-endpoints)
- [Intervalos de endereços IP e URLs do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)
- [Pré-requisitos do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## Limitações do HoloLens

Depois de configurar o seu HoloLens, você pode usá-lo sem uma conexão de Wi-Fi, mas aplicativos que usam conexões com a Internet terão capacidades limitadas quando você usar o HoloLens off-line.
