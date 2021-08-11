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
ms.openlocfilehash: d2747da37ae198f7a2c051593da3ffd4cb4476dfaa7a3078a7749fa1fc912ba2
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665617"
---
# <a name="page-settings-visibility"></a>Visibilidade das Configurações da Página

Um dos recursos gerenciáveis para dispositivos HoloLens está usando a [política Configurações/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas no aplicativo Configurações. PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema ou a todas as páginas, exceto aquelas especificadas.

> [!NOTE]
> Esse recurso só está disponível no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou versões superiores para dispositivos HoloLens 2. Verifique se os dispositivos para os quais você pretende usar estão atualizados.


## <a name="examples"></a>Exemplos
As páginas são identificadas por uma versão abreviada dos URIs publicados, que é o URI menos o prefixo "ms-settings:".

O seguinte exemplo ilustra uma política que permitirá o acesso apenas às páginas Sobre e Bluetooth, que têm os URIs "network-wifi" e "bluetooth", respectivamente:
- `showonly:network-wifi;network-proxy;bluetooth`

O seguinte exemplo ilustra uma política que ocultará a página de redefinição do sistema operacional:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Como implantar esta política por meio do Intune

Estes são os valores de configuração que serão fornecidos ao Intune:

- **Nome:** um nome de exibição preferencial do administrador para o perfil.
- **OMA-URI:** o URI totalmente qualificado da página de configuração, incluindo o [escopo](/windows/client-management/mdm/policy-configuration-service-provider) dele. Os exemplos desta página usam o escopo `./Device`.
- **Valor:** um valor de cadeia de caracteres que indica se *apenas* as páginas especificadas devem ser ocultadas ou mostradas. Os valores possíveis são `hide:<pagename>` e `showonly:<pagename>`. 
 
Várias páginas podem ser especificadas separando-as com um ponto e vírgula, e uma lista de páginas comuns pode ser encontrada abaixo.

1. Crie uma **Política personalizada**.
1. Ao definir o **OMA-URI**, insira o URI de escopo completo. Por exemplo: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Ao escolher a cadeia de dados, escolha: **Cadeia de caracteres**
1. Ao especificar o **Valor**, use as diretrizes acima. Por exemplo: **`showonly:network-wifi;network-proxy;bluetooth`** ou **`hide:reset`** 
> [!IMPORTANT]
> Atribua a configuração personalizada do dispositivo a um grupo ao qual o dispositivo se destina. Se essa etapa não for executada, a política será enviada por push, mas não será aplicada.

Confira [Configuração MDM do HoloLens](hololens-mdm-configure.md) para obter mais informações sobre configurações de dispositivos e grupos do Intune.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Como implantar esta política por meio de um pacote de provisionamento

Estes são os valores de configuração que serão especificados no Designer de Configuração do Windows:

**Valor:** um valor de cadeia de caracteres que indica se *apenas* as páginas especificadas devem ser ocultadas ou mostradas. Os valores possíveis são `hide:<pagename>` e `showonly:<pagename>`. Várias páginas podem ser especificadas separando-as com um ponto e vírgula, e uma lista de páginas comuns pode ser encontrada abaixo.


1. Ao criar seu pacote no Designer de Configuração do Windows, navegue até **Políticas > Configurações > PageVisibilityList**
1. Insira a cadeia de caracteres: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exporte o pacote de provisionamento.
1. Aplique o pacote de provisionamento aos seus dispositivos.
Para obter detalhes completos sobre como criar e aplicar um pacote de provisionamento, acesse [a página de provisionamento do HoloLens](hololens-provisioning.md).


Independentemente do método escolhido, o seu dispositivo agora deve receber as alterações, e os usuários verão o seguinte aplicativo de Configurações.

![Captura de tela do horário ativo sendo modificado no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

Para configurar as páginas do aplicativo Configurações para mostrar ou ocultar a sua própria seleção de páginas, confira as Configurações URIs disponíveis no HoloLens.

## <a name="settings-uris"></a>URIs de configurações

Dispositivos HoloLens e Windows 10 têm uma seleção diferente de páginas no aplicativo Configurações. Nesta página, você encontrará somente as configurações existentes no HoloLens.

### <a name="accounts"></a>Contas
| Página de configurações           | URI                                            |
|-------------------------|------------------------------------------------|
| Acesso corporativo ou de estudante | `workplace`                         |
| Registro da íris       | `signinoptions-launchirisenrollment` |
| Opções de login         | ` signinoptions `                   |

### <a name="apps"></a>Aplicativos
| Página de configurações | URI                          |
|---------------|------------------------------|
| Aplicativos e recursos <sup>2</sup>     | `appsfeatures` <br> |
| Aplicativos e recursos > Opções avançadas <sup>2</sup>     | `appsfeatures-app` <br> |
| Aplicativos e recursos > Mapas offline <sup>2</sup>     | `maps-maps` <br> |
| Aplicativos e recursos > Mapas offline > Fazer download de mapas <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Dispositivos
| Página de configurações | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Mouse <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Privacidade
| Página de configurações            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informações da conta             | `privacy-accountinfo`              |
| Diagnósticos do Aplicativo        | `privacy-appdiagnostics`              |
| Aplicativos em Segundo Plano        | `privacy-backgroundapps`              |
| Calendário                 | `privacy-calendar`                    |
| Histórico de chamadas             | `privacy-callhistory`                 |
| Câmera                   | `privacy-webcam`                      |
| Contatos                 | `privacy-contacts`                    |
| Diagnóstico e Comentários | `privacy-feedback`                    |
| Documentos                | `privacy-documents`                   |
| Email                    | `privacy-email`                       |
| Sistema de arquivos              | `privacy-broadfilesystemaccess`       |
| Geral <sup>2</sup>             | `privacy-general`       |
| Personalização de escrita à tinta e digitação <sup>2</sup>             | `privacy-speechtyping`       |
| Local                 | `privacy-location`                    |
| Mensagens                | `privacy-messaging`                   |
| Microfone               | `privacy-microphone`                  |
| Movimento <sup>2</sup>               | `privacy-motion`                  |
| Notificações            | `privacy-notifications`               |
| Outros dispositivos            | `privacy-customdevices`               |
| Imagens                 | `privacy-pictures`                    |
| Rádios                   | `privacy-radios`                      |
| Bordas da captura de tela <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Capturas de tela e aplicativos <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Fala                   | `privacy-speech`                      |
| Tarefas                    | `privacy-tasks`                       |
| Movimentos do usuário           | `privacy-backgroundspatialperception` |
| vídeos                   | `privacy-videos`                      |
| Ativação por Voz       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Rede e Internet
| Página de configurações | URI                              |
|---------------|----------------------------------|
| Modo Avião <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Sistema
| Página de configurações      | URI                                |
|--------------------|------------------------------------|
| Bateria <sup>2</sup>           | `batterysaver`<br>|
| Bateria <sup>2</sup>           | `batterysaver-settings`<br>|
| Cores             | `colors`<br>`personalization-colors` |
| Hologramas <sup>2</sup>  |  `holograms`  |
| Calibragem <sup>2</sup> |  `calibration` |
| Notificações e ações  | `notifications`          |
| Experiências Compartilhadas | `crossdevice` 
| Som <sup>2</sup>           | `sound`<br>|
| Som > Volume do aplicativo e preferência do dispositivo <sup>2</sup>           | `apps-volume`<br>|
| Som > Gerenciar dispositivos de som <sup>2</sup>           | `sound-devices`<br>|
| Armazenamento            | `storagesense`           |
| Armazenamento > Configurar Sensor de Armazenamento <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Hora e Idioma
| Página de configurações | URI                                           |
|---------------|-----------------------------------------------|
| Data e hora <sup>2</sup> | `dateandtime`                  |
| Teclado <sup>2</sup> | `keyboard`                  |
| Idioma <sup>2</sup> | `language`                  |
| Idioma <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Linguagem      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Região        | `regionformatting`                  |

### <a name="update--security"></a>Atualização e Segurança
| Página de configurações                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opções avançadas                    | `windowsupdate-options`         |
| Redefinir e Recuperar <sup>2</sup>      | `reset`         |
| Programa Windows Insider               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Update – verifica se há atualizações | `windowsupdate-action`          |


- <sup>1</sup> – Para versões anteriores ao Windows Holographic, versão 21H1, os dois URIs a seguir não levam às páginas **Opções avançadas** ou **Opções**. Elas só bloquearão ou mostrarão a página Windows Update principal.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> – Disponível no Windows Holographic 21H1 ou versões superiores.


Para uma lista completa de URIs de configurações do Windows 10, acesse a documentação [Configurações de inicialização](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).
