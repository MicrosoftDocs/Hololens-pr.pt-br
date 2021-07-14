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
# <a name="page-settings-visibility"></a><span data-ttu-id="dcd80-104">Visibilidade das Configurações da Página</span><span class="sxs-lookup"><span data-stu-id="dcd80-104">Page Settings Visibility</span></span>

<span data-ttu-id="dcd80-105">Um dos recursos gerenciáveis para dispositivos HoloLens está usando a [política Configurações/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas no aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="dcd80-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="dcd80-106">PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema ou a todas as páginas, exceto aquelas especificadas.</span><span class="sxs-lookup"><span data-stu-id="dcd80-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="dcd80-107">Esse recurso só está disponível no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou versões superiores para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="dcd80-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="dcd80-108">Verifique se os dispositivos para os quais você pretende usar estão atualizados.</span><span class="sxs-lookup"><span data-stu-id="dcd80-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="dcd80-109">O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas Sobre e Bluetooth, que têm URI "ms-settings:network-wifi" e "ms-settings:bluetooth" respectivamente:</span><span class="sxs-lookup"><span data-stu-id="dcd80-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="dcd80-110">Para definir isso por meio de um pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="dcd80-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="dcd80-111">Ao criar seu pacote no Designer de Configuração do Windows, navegue até **Políticas > Configurações > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="dcd80-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="dcd80-112">Insira a cadeia de caracteres: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="dcd80-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="dcd80-113">Exporte o pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="dcd80-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="dcd80-114">Aplique o pacote de provisionamento aos seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dcd80-114">Apply the package to your device.</span></span>
<span data-ttu-id="dcd80-115">Para obter detalhes completos sobre como criar e aplicar um pacote de provisionamento, visite [esta página](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="dcd80-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="dcd80-116">Isso pode ser feito por meio do Intune usando o OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="dcd80-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="dcd80-117">Crie uma **Política personalizada**.</span><span class="sxs-lookup"><span data-stu-id="dcd80-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="dcd80-118">Ao configurar o OMA-URI, use a cadeia de caracteres: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="dcd80-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="dcd80-119">Ao escolher a cadeia de dados, escolha: **Cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="dcd80-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="dcd80-120">Ao digitar o valor, use: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="dcd80-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="dcd80-121">Atribua a configuração personalizada do dispositivo a um grupo ao qual o dispositivo se destina.</span><span class="sxs-lookup"><span data-stu-id="dcd80-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="dcd80-122">Confira [Configuração MDM do HoloLens](hololens-mdm-configure.md) para obter mais informações sobre configurações de dispositivos e grupos do Intune.</span><span class="sxs-lookup"><span data-stu-id="dcd80-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="dcd80-123">Independentemente do método escolhido, o seu dispositivo agora deve receber as alterações, e os usuários verão o seguinte aplicativo de Configurações.</span><span class="sxs-lookup"><span data-stu-id="dcd80-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Captura de tela do horário ativo sendo modificado no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="dcd80-125">Para configurar as páginas do aplicativo Configurações para mostrar ou ocultar a sua própria seleção de páginas, confira as Configurações URIs disponíveis no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dcd80-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="dcd80-126">URIs de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-126">Settings URIs</span></span>

<span data-ttu-id="dcd80-127">Dispositivos HoloLens e Windows 10 têm uma seleção diferente de páginas no aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="dcd80-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="dcd80-128">Nesta página, você encontrará somente as configurações existentes no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dcd80-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="dcd80-129">Contas</span><span class="sxs-lookup"><span data-stu-id="dcd80-129">Accounts</span></span>
| <span data-ttu-id="dcd80-130">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-130">Settings page</span></span>           | <span data-ttu-id="dcd80-131">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="dcd80-132">Acesso corporativo ou de estudante</span><span class="sxs-lookup"><span data-stu-id="dcd80-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="dcd80-133">Registro da íris</span><span class="sxs-lookup"><span data-stu-id="dcd80-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="dcd80-134">Opções de login</span><span class="sxs-lookup"><span data-stu-id="dcd80-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="dcd80-135">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="dcd80-135">Apps</span></span>
| <span data-ttu-id="dcd80-136">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-136">Settings page</span></span> | <span data-ttu-id="dcd80-137">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="dcd80-138">Aplicativos e recursos<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="dcd80-139">Aplicativos e recursos > Opções avançadas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="dcd80-140">Aplicativos e recursos > Mapas offline <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="dcd80-141">Aplicativos e recursos > Mapas offline > Fazer download de mapas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="dcd80-142">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="dcd80-142">Devices</span></span>
| <span data-ttu-id="dcd80-143">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-143">Settings page</span></span> | <span data-ttu-id="dcd80-144">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="dcd80-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="dcd80-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="dcd80-146">Mouse <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="dcd80-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="dcd80-148">Privacidade</span><span class="sxs-lookup"><span data-stu-id="dcd80-148">Privacy</span></span>
| <span data-ttu-id="dcd80-149">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-149">Settings page</span></span>            | <span data-ttu-id="dcd80-150">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="dcd80-151">Informações da conta</span><span class="sxs-lookup"><span data-stu-id="dcd80-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="dcd80-152">Diagnósticos do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="dcd80-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="dcd80-153">Aplicativos em Segundo Plano</span><span class="sxs-lookup"><span data-stu-id="dcd80-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="dcd80-154">Calendário</span><span class="sxs-lookup"><span data-stu-id="dcd80-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="dcd80-155">Histórico de chamadas</span><span class="sxs-lookup"><span data-stu-id="dcd80-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="dcd80-156">Câmera</span><span class="sxs-lookup"><span data-stu-id="dcd80-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="dcd80-157">Contatos</span><span class="sxs-lookup"><span data-stu-id="dcd80-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="dcd80-158">Diagnóstico e Comentários</span><span class="sxs-lookup"><span data-stu-id="dcd80-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="dcd80-159">Documentos</span><span class="sxs-lookup"><span data-stu-id="dcd80-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="dcd80-160">Email</span><span class="sxs-lookup"><span data-stu-id="dcd80-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="dcd80-161">Sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="dcd80-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="dcd80-162">Geral <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="dcd80-163">Personalização de escrita à tinta e digitação <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="dcd80-164">Local</span><span class="sxs-lookup"><span data-stu-id="dcd80-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="dcd80-165">Mensagens</span><span class="sxs-lookup"><span data-stu-id="dcd80-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="dcd80-166">Microfone</span><span class="sxs-lookup"><span data-stu-id="dcd80-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="dcd80-167">Movimento <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="dcd80-168">Notificações</span><span class="sxs-lookup"><span data-stu-id="dcd80-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="dcd80-169">Outros dispositivos</span><span class="sxs-lookup"><span data-stu-id="dcd80-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="dcd80-170">Imagens</span><span class="sxs-lookup"><span data-stu-id="dcd80-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="dcd80-171">Rádios</span><span class="sxs-lookup"><span data-stu-id="dcd80-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="dcd80-172">Bordas da captura de tela <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="dcd80-173">Capturas de tela e aplicativos <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="dcd80-174">Fala</span><span class="sxs-lookup"><span data-stu-id="dcd80-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="dcd80-175">Tarefas</span><span class="sxs-lookup"><span data-stu-id="dcd80-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="dcd80-176">Movimentos do usuário</span><span class="sxs-lookup"><span data-stu-id="dcd80-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="dcd80-177">vídeos</span><span class="sxs-lookup"><span data-stu-id="dcd80-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="dcd80-178">Ativação por Voz</span><span class="sxs-lookup"><span data-stu-id="dcd80-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="dcd80-179">Rede e Internet</span><span class="sxs-lookup"><span data-stu-id="dcd80-179">Network & Internet</span></span>
| <span data-ttu-id="dcd80-180">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-180">Settings page</span></span> | <span data-ttu-id="dcd80-181">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="dcd80-182">Modo Avião <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="dcd80-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="dcd80-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="dcd80-184">VPN</span><span class="sxs-lookup"><span data-stu-id="dcd80-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="dcd80-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="dcd80-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="dcd80-186">Sistema</span><span class="sxs-lookup"><span data-stu-id="dcd80-186">System</span></span>
| <span data-ttu-id="dcd80-187">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-187">Settings page</span></span>      | <span data-ttu-id="dcd80-188">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="dcd80-189">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="dcd80-190">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="dcd80-191">Cores</span><span class="sxs-lookup"><span data-stu-id="dcd80-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="dcd80-192">Hologramas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="dcd80-193">Calibragem <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="dcd80-194">Notificações e ações</span><span class="sxs-lookup"><span data-stu-id="dcd80-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="dcd80-195">Experiências Compartilhadas</span><span class="sxs-lookup"><span data-stu-id="dcd80-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="dcd80-196">Som <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="dcd80-197">Som > Volume do aplicativo e preferência do dispositivo <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="dcd80-198">Som > Gerenciar dispositivos de som <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="dcd80-199">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="dcd80-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="dcd80-200">Armazenamento > Configurar Sensor de Armazenamento <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="dcd80-201">Hora e Idioma</span><span class="sxs-lookup"><span data-stu-id="dcd80-201">Time & Language</span></span>
| <span data-ttu-id="dcd80-202">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-202">Settings page</span></span> | <span data-ttu-id="dcd80-203">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="dcd80-204">Data e hora <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="dcd80-205">Teclado <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="dcd80-206">Idioma <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="dcd80-207">Idioma <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="dcd80-208">Linguagem</span><span class="sxs-lookup"><span data-stu-id="dcd80-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="dcd80-209">Região</span><span class="sxs-lookup"><span data-stu-id="dcd80-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="dcd80-210">Atualização e Segurança</span><span class="sxs-lookup"><span data-stu-id="dcd80-210">Update & Security</span></span>
| <span data-ttu-id="dcd80-211">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="dcd80-211">Settings page</span></span>                         | <span data-ttu-id="dcd80-212">URI</span><span class="sxs-lookup"><span data-stu-id="dcd80-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="dcd80-213">Opções avançadas</span><span class="sxs-lookup"><span data-stu-id="dcd80-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="dcd80-214">Redefinir e Recuperar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="dcd80-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="dcd80-215">Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="dcd80-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="dcd80-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="dcd80-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="dcd80-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="dcd80-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="dcd80-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="dcd80-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="dcd80-219">Windows Update – verifica se há atualizações</span><span class="sxs-lookup"><span data-stu-id="dcd80-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="dcd80-220"><sup>1</sup> – Para versões anteriores ao Windows Holographic, versão 21H1, os dois URIs a seguir não levam às páginas **Opções avançadas** ou **Opções**. Elas só bloquearão ou mostrarão a página Windows Update principal.</span><span class="sxs-lookup"><span data-stu-id="dcd80-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="dcd80-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="dcd80-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="dcd80-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="dcd80-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="dcd80-223"><sup>2</sup> – Disponível no Windows Holographic 21H1 ou versões superiores.</span><span class="sxs-lookup"><span data-stu-id="dcd80-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="dcd80-224">Para uma lista completa de URIs de configurações do Windows 10, acesse a documentação [Configurações de inicialização](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="dcd80-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
