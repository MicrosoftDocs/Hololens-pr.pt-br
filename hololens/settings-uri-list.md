---
title: URIs de configurações
description: Lista de URIs de HoloLens suportados pela PageVisibilityList
author: evmill
ms.author: v-evmill
ms.date: 09/16/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque, página de configurações
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 17959fa25763d2c6b89d0956f29b9999b3012e60
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016695"
---
# URIs de configurações

Um dos recursos gerenciáveis para dispositivos do HoloLens está usando as [políticas de configurações/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas nas configurações do aplicativo. PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema, ou para isso, para todas as páginas, exceto aquelas especificadas. 

> [!IMPORTANT]
> No momento, esse recurso só está disponível na [Windows Insider builds](hololens-insider.md). Certifique-se de que os dispositivos em que você pretenda usar, sejam no Build 19041.1349+.

O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas sobre e Bluetooth, que têm URI "ms-settings:network-wifi" e "ms-settings:bluetooth" respectivamente:
- showonly:network-wifi;network-proxy;bluetooth

Para definir isso por meio de um pacote Provsioning: 
1. Enquanto cria seu pacote no Windows Configuration Designer, navegue até **Políticas > Configurações > PageVisibilityList**
1. Insira a cadeia de caracteres: **mostrarsomente:network-wifi;network-proxy;bluetooth**
1. Exportar o pacote Provsioning.
1. Aplique o pacote de provisionamento aos seus dispositivos. Para obter detalhes completos sobre como criar e aplicar um pacote provsioning visite [esta página](hololens-provisioning.md). 

Isso pode ser feito por meio do Intune usando o OMA-URI.
1. Criar uma **política personalizada**.
1. Ao configurar o OMA-URI use a cadeia de caracteres: **./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList**
1. Ao selecionar a cadeia de dados, escolha: **Cadeia de caracteres**
1. Ao digitar o valor, use: **mostrarsomente:network-wifi;network-proxy;bluetooth**
1. Certifique-se de atribuir a configuração de dispositivo personalizado ao grupo a que o dispositivo se destina.
Para obter mais informações sobre as configurações de dispositivos e grupos do Intune, [acesse](hololens-mdm-configure.md).

Independentemente do método escolhido, o dispositivo deve agora receber as alterações, e os usuários serão apresentados com o Aplicativo Configurações a seguir. 

![Captura de tela da modificação das horas ativas no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

Para definir as páginas de Configurações de aplicativos para mostrar ou ocultar sua própria seleção de páginas, Confira as configurações URIs disponíveis no HoloLens. 

## URIs de configurações

Os dispositivos do HoloLens e com Windows 10 possuem uma seleção diferente de páginas das configurações do aplicativo. Nesta página, você encontrará somente as configurações existentes no HoloLens. 

### Contas
| Página de configurações           | URI                                            |
|-------------------------|------------------------------------------------|
| Opções de entrada         | ms-settings:signinoptions                      |
| Registro da íris       | ms-settings:signinoptions-launchirisenrollment |
| Acessar trabalho ou escola | ms-settings:workplace                          |

### Devices
| Página de configurações | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### Privacidade
| Página de configurações            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informações da conta             | ms-settings:privacy-accountinfo                 |
| Diagnósticos do Aplicativo        | ms-settings:privacy-appdiagnostics              |
| Aplicativos em segundo plano        | ms-settings:privacy-backgroundapps              |
| Movimentos do usuário           | ms-settings:privacy-backgroundspatialperception |
| Sistema de arquivos              | ms-settings:privacy-broadfilesystemaccess       |
| Calendário                 | ms-settings:privacy-calendar                    |
| Histórico de chamadas             | ms-settings:privacy-callhistory                 |
| Contatos                 | ms-settings:privacy-contacts                    |
| Outros dispositivos            | ms-settings:privacy-customdevices               |
| Documentos                | ms-settings:privacy-documents                   |
| Email                    | ms-settings:privacy-email                       |
| Comentários e diagnóstico | ms-settings:privacy-feedback                    |
| Location                 | ms-settings:privacy-location                    |
| Mensagens                | ms-settings:privacy-messaging                   |
| Microfone               | ms-settings:privacy-microphone                  |
| Notificações            | ms-settings:privacy-notifications               |
| Imagens                 | ms-settings:privacy-pictures                    |
| Rádios                   | ms-settings:privacy-radios                      |
| Controle por voz                   | ms-settings:privacy-speech                      |
| Tarefas                    | ms-settings:privacy-tasks                       |
| Vídeos                   | ms-settings:privacy-videos                      |
| Ativação por voz       | ms-settings:privacy-voiceactivation             |
| Câmera                   | ms-settings:privacy-webcam                      |

### Rede e Internet
| Página de configurações | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| Proxy | ms-settings:network-proxy        |

### Sistema
| Página de configurações      | URI                                |
|--------------------|------------------------------------|
| Experiências compartilhadas | ms-settings:crossdevice            |
| Cores             | ms-settings:colors<br>ms-settings:personalization-colors |
| Notificações e ações  | ms-settings:notifications          |
| Armazenamento            | ms-settings:storagesense           |

### Hora e idioma
| Página de configurações | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| Idioma      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### Atualização e segurança
| Página de configurações                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Programa Windows Insider               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update – verifica atualizações | ms-settings:windowsupdate-action          |
| Opções Avançadas                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 Os dois URIS a seguir, na verdade, não levam você para a página Opções avançadas ou Opções, só bloqueiam/mostram a página principal do Windows Update. 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Para obter uma lista completa de URIs de configurações do Windows 10, acesse [aqui](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference). 
