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
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924325"
---
# <a name="page-settings-visibility"></a>Visibilidade das Configurações da Página

Um dos recursos gerenciáveis para dispositivos HoloLens está usando a [política Configurações/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas no aplicativo Configurações. PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema ou a todas as páginas, exceto aquelas especificadas.

> [!NOTE]
> Esse recurso só está disponível no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou versões superiores para dispositivos HoloLens 2. Verifique se os dispositivos para os quais você pretende usar estão atualizados.

O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas Sobre e Bluetooth, que têm URI "ms-settings:network-wifi" e "ms-settings:bluetooth" respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

Para definir isso por meio de um pacote de provisionamento:

1. Ao criar seu pacote no Designer de Configuração do Windows, navegue até **Políticas > Configurações > PageVisibilityList**
1. Insira a cadeia de caracteres: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exporte o pacote de provisionamento.
1. Aplique o pacote de provisionamento aos seus dispositivos.
Para obter detalhes completos sobre como criar e aplicar um pacote de provisionamento, visite [esta página](hololens-provisioning.md).

Isso pode ser feito por meio do Intune usando o OMA-URI:

1. Crie uma **Política personalizada**.
1. Ao configurar o OMA-URI, use a cadeia de caracteres: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Ao escolher a cadeia de dados, escolha: **Cadeia de caracteres**
1. Ao digitar o valor, use: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Atribua a configuração personalizada do dispositivo a um grupo ao qual o dispositivo se destina.

Confira [Configuração MDM do HoloLens](hololens-mdm-configure.md) para obter mais informações sobre configurações de dispositivos e grupos do Intune.

Independentemente do método escolhido, o seu dispositivo agora deve receber as alterações, e os usuários verão o seguinte aplicativo de Configurações.

![Captura de tela do horário ativo sendo modificado no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

Para configurar as páginas do aplicativo Configurações para mostrar ou ocultar a sua própria seleção de páginas, confira as Configurações URIs disponíveis no HoloLens.

## <a name="settings-uris"></a>URIs de configurações

Dispositivos HoloLens e Windows 10 têm uma seleção diferente de páginas no aplicativo Configurações. Nesta página, você encontrará somente as configurações existentes no HoloLens.

### <a name="accounts"></a>Contas
| Página de configurações           | URI                                            |
|-------------------------|------------------------------------------------|
| Acesso corporativo ou de estudante | `ms-settings:workplace`                         |
| Registro da íris       | `ms-settings:signinoptions-launchirisenrollment` |
| Opções de login         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Aplicativos
| Página de configurações | URI                          |
|---------------|------------------------------|
| Aplicativos e recursos<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Aplicativos e recursos > Opções avançadas <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Aplicativos e recursos > Mapas offline <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Aplicativos e recursos > Mapas offline > Fazer download de mapas <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivos
| Página de configurações | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Mouse <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Privacidade
| Página de configurações            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informações da conta             | `ms-settings:privacy-accountinfo`              |
| Diagnósticos do Aplicativo        | `ms-settings:privacy-appdiagnostics`              |
| Aplicativos em Segundo Plano        | `ms-settings:privacy-backgroundapps`              |
| Calendário                 | `ms-settings:privacy-calendar`                    |
| Histórico de chamadas             | `ms-settings:privacy-callhistory`                 |
| Câmera                   | `ms-settings:privacy-webcam`                      |
| Contatos                 | `ms-settings:privacy-contacts`                    |
| Diagnóstico e Comentários | `ms-settings:privacy-feedback`                    |
| Documentos                | `ms-settings:privacy-documents`                   |
| Email                    | `ms-settings:privacy-email`                       |
| Sistema de arquivos              | `ms-settings:privacy-broadfilesystemaccess`       |
| Geral <sup>2</sup>             | `ms-settings:privacy-general`       |
| Personalização de escrita à tinta e digitação <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Local                 | `ms-settings:privacy-location`                    |
| Mensagens                | `ms-settings:privacy-messaging`                   |
| Microfone               | `ms-settings:privacy-microphone`                  |
| Movimento <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Notificações            | `ms-settings:privacy-notifications`               |
| Outros dispositivos            | `ms-settings:privacy-customdevices`               |
| Imagens                 | `ms-settings:privacy-pictures`                    |
| Rádios                   | `ms-settings:privacy-radios`                      |
| Bordas da captura de tela <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Capturas de tela e aplicativos <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Fala                   | `ms-settings:privacy-speech`                      |
| Tarefas                    | `ms-settings:privacy-tasks`                       |
| Movimentos do usuário           | `ms-settings:privacy-backgroundspatialperception` |
| vídeos                   | `ms-settings:privacy-videos`                      |
| Ativação por Voz       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Rede e Internet
| Página de configurações | URI                              |
|---------------|----------------------------------|
| Modo Avião <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Sistema
| Página de configurações      | URI                                |
|--------------------|------------------------------------|
| Bateria <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Bateria <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Cores             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologramas <sup>2</sup>  |  `ms-settings:holograms`  |
| Calibragem <sup>2</sup> |  `ms-settings:calibration` |
| Notificações e ações  | `ms-settings:notifications`          |
| Experiências Compartilhadas | `ms-settings:crossdevice` 
| Som <sup>2</sup>           | `ms-settings:sound`<br>|
| Som > Volume do aplicativo e preferência do dispositivo <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Som > Gerenciar dispositivos de som <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Armazenamento            | `ms-settings:storagesense`           |
| Armazenamento > Configurar Sensor de Armazenamento <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Hora e Idioma
| Página de configurações | URI                                           |
|---------------|-----------------------------------------------|
| Data e hora <sup>2</sup> | `ms-settings:dateandtime`                  |
| Teclado <sup>2</sup> | `ms-settings:keyboard`                  |
| Idioma <sup>2</sup> | `ms-settings:language`                  |
| Idioma <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Linguagem      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Região        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Atualização e Segurança
| Página de configurações                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opções avançadas                    | `ms-settings:windowsupdate-options`         |
| Redefinir e Recuperar <sup>2</sup>      | `ms-settings:reset`         |
| Programa Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update – verifica se há atualizações | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> – Para versões anteriores ao Windows Holographic, versão 21H1, os dois URIs a seguir não levam às páginas **Opções avançadas** ou **Opções**. Elas só bloquearão ou mostrarão a página Windows Update principal.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> – Disponível no Windows Holographic 21H1 ou versões superiores.


Para uma lista completa de URIs de configurações do Windows 10, acesse a documentação [Configurações de inicialização](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
