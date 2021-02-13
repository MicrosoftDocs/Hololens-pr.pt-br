---
title: Visibilidade das Configurações da Página
description: Mantenha-se atualizado com nossa lista de URIs com suporte para PageVisibilityList e Guia em dispositivos de realidade misturada do HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque, página de configurações
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327385"
---
# Visibilidade das Configurações da Página

Um dos recursos gerenciáveis para dispositivos do HoloLens está usando as [políticas de configurações/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas nas configurações do aplicativo. PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema, ou para isso, para todas as páginas, exceto aquelas especificadas.

> [!NOTE]
> Este recurso só está disponível no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos do HoloLens 2. Certificar-se de que os dispositivos para os quais você pretende usar são atualizados.

> [!NOTE]
> Mais de 20 novas SettingsURIs serão adicionadas em breve. Exiba [ a página do Windows Insider - Novas SettingsURIs para a visibilidade das configurações de página](hololens-insider.md#new-settingsuris-for-page-settings-visibility) se você estiver interessado em visualizar esta configuração em uma build do [HoloLens Insider](hololens-insider.md).

O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas sobre e Bluetooth, que têm URI "ms-settings:network-wifi" e "ms-settings:bluetooth" respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

Para definir isso por meio de um pacote de provisionamento:

1. Enquanto cria seu pacote no Windows Configuration Designer, navegue até **Políticas > Configurações > PageVisibilityList**
1. Insira a cadeia de caracteres: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportar o pacote de provisionamento.
1. Aplique o pacote de provisionamento aos seus dispositivos.
Para obter detalhes completos sobre como criar e aplicar um pacote de provisionamento visite [esta página](hololens-provisioning.md).

Isso pode ser feito por meio do Intune usando o OMA-URI:

1. Criar uma **política personalizada**.
1. Ao configurar o OMA-URI, use a cadeia de caracteres: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Ao selecionar a cadeia de dados, escolha: **Cadeia de caracteres**
1. Ao digitar o valor, use: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Certifique-se de atribuir a configuração personalizada do dispositivo a um grupo ao qual o dispositivo se destina.

Confira [a configuração MDM do HoloLens](hololens-mdm-configure.md) para obter mais informações sobre grupos do Intune e configurações de dispositivos.

Independentemente do método escolhido, o seu dispositivo agora deve receber as alterações e os usuários verão o seguinte aplicativo de Configurações.

![Captura de tela do horário ativo sendo modificado no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

Para configurar as páginas do aplicativo Configurações para mostrar ou ocultar a sua própria seleção de páginas, dê uma olhada nas Configurações URIs disponíveis no HoloLens.

## URIs de configurações

Dispositivos HoloLens e Windows 10 possuem uma seleção diferente de páginas no aplicativo Configurações. Nesta página, você encontrará somente as configurações existentes no HoloLens.

### Contas
| Página de configurações           | URI                                            |
|-------------------------|------------------------------------------------|
| Opções de entrada         | ` ms-settings:signinoptions `                   |
| Registro da íris       | `ms-settings:signinoptions-launchirisenrollment` |
| Acessar trabalho ou escola | `ms-settings:workplace`                         |

### Dispositivos
| Página de configurações | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### Privacidade
| Página de configurações            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informações da conta             | `ms-settings:privacy-accountinfo`              |
| Diagnósticos do Aplicativo        | `ms-settings:privacy-appdiagnostics`              |
| Aplicativos em segundo plano        | `ms-settings:privacy-backgroundapps`              |
| Movimentos do usuário           | `ms-settings:privacy-backgroundspatialperception` |
| Sistema de arquivos              | `ms-settings:privacy-broadfilesystemaccess`       |
| Calendário                 | `ms-settings:privacy-calendar`                    |
| Histórico de chamadas             | `ms-settings:privacy-callhistory`                 |
| Contatos                 | `ms-settings:privacy-contacts`                    |
| Outros dispositivos            | `ms-settings:privacy-customdevices`               |
| Documentos                | `ms-settings:privacy-documents`                   |
| Email                    | `ms-settings:privacy-email`                       |
| Comentários e diagnóstico | `ms-settings:privacy-feedback`                    |
| Localização                 | `ms-settings:privacy-location`                    |
| Mensagens                | `ms-settings:privacy-messaging`                   |
| Microfone               | `ms-settings:privacy-microphone`                  |
| Notificações            | `ms-settings:privacy-notifications`               |
| Imagens                 | `ms-settings:privacy-pictures`                    |
| Rádios                   | `ms-settings:privacy-radios`                      |
| Fala                   | `ms-settings:privacy-speech`                      |
| Tarefas                    | `ms-settings:privacy-tasks`                       |
| Vídeos                   | `ms-settings:privacy-videos`                      |
| Ativação por voz       | `ms-settings:privacy-voiceactivation`             |
| Câmera                   | `ms-settings:privacy-webcam`                      |

### Rede e Internet
| Página de configurações | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| VPN   | `ms-settings:network-vpn`          |
| Proxy | `ms-settings:network-proxy`        |

### Sistema
| Página de configurações      | URI                                |
|--------------------|------------------------------------|
| Experiências compartilhadas | `ms-settings:crossdevice`            |
| Cores             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Notificações e ações  | `ms-settings:notifications`          |
| Armazenamento            | `ms-settings:storagesense`           |

### Hora e idioma
| Página de configurações | URI                                           |
|---------------|-----------------------------------------------|
| Region        | `ms-settings:regionformatting`                  |
| Idioma      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### Atualização e segurança
| Página de configurações                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programa Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update – verifica se há atualizações | `ms-settings:windowsupdate-action`          |
| Opções Avançadas                    | `ms-settings:windowsupdate-options`         |

>  <sup>1 </sup> Os dois URIS a seguir, na verdade, não levam você para as páginas **Opções avançadas** ou **Opções**, só bloqueiam/mostram a página principal do Windows Update.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Para uma lista completa de URIs de configurações do Windows 10, visite a [documentação de configurações de início.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
