---
title: Gerenciar pontos de extremidade de conexão para o HoloLens
description: Saiba como configurar um HoloLens em uma rede Wi-Fi gerenciando e configurando os terminais de conexão.
keywords: hololens, offline, OOBE
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
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640076"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Gerenciar pontos de extremidade de conexão para o HoloLens

Alguns componentes, aplicativos e serviços relacionados do HoloLens transferem dados aos terminais de rede da Microsoft. Este artigo lista diferentes terminais e URLs que precisam ser permitidos na sua configuração de rede (por exemplo, proxy ou firewall) para que esses componentes funcionem.    

## <a name="near-offline-setup"></a>Configuração quase offline

O HoloLens dá suporte a um conjunto limitado de experiências offline para os clientes que têm restrições no ambiente de rede. No entanto, o HoloLens precisa de uma conexão de rede para passar pela configuração inicial do dispositivo, e as seguintes URLs devem ser habilitadas:

| Finalidade | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| PIN do AAD | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| PIN da MSA | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Configuração de ponto de extremidade

Além da lista acima, para aproveitar ao máximo as funcionalidades do HoloLens, os terminais a seguir precisam estar habilitados na configuração de rede.


| Finalidade | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Autenticação Multifator do Azure AD                | https://secure.aadcdn.microsoftonline-p.com                         |
| Configurações do Intune e do MDM                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Certificados                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana e Pesquisa                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Autenticação de dispositivo                               | login.live.com*                                                     |
| Metadados de dispositivo                                     | dmd.metaservices.microsoft.com                                      |
| Local                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Dados de diagnóstico                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licenças                                           | licensing.mp.microsoft.com                                          |
| Conta da Microsoft                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| FWLink (serviço de redirecionamento de link de encaminhamento da Microsoft) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| NCSI (Indicador de Status da Conexão de Rede)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Aplicativo Fotos                                          | evoke-windowsservices-tas.msedge.net                                |
| Configurações                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Destaque do Windows                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Referências

> [!NOTE]
> Se você estiver implantando o Remote Assist do D365, habilite os pontos de extremidade listados para o SharePoint Online e o OneDrive for Business em [URLs e intervalos de endereços IP do Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- [Configurar os dados de diagnóstico do Windows em sua organização](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Gerenciar pontos de extremidade de conexão do Windows 10 Enterprise, versão 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Gerenciar conexões de componentes do sistema operacional Windows 10 com serviços Microsoft](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Gerenciar conexões de componentes do sistema operacional Windows 10 com serviços Microsoft usando o Servidor MDM do Microsoft Intune](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Largura de banda e requisitos de configuração de rede do Intune](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Pontos de extremidade de rede para o Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [URLs e intervalos de endereços IP do Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Pré-requisitos do Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>Limitações do HoloLens

Depois de configurar o HoloLens, você poderá usá-lo sem uma conexão Wi-Fi, mas os aplicativos que usam conexões com a Internet terão capacidades limitadas quando você usar o HoloLens offline.
