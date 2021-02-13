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
# <span data-ttu-id="0ebb2-104">Visibilidade das Configurações da Página</span><span class="sxs-lookup"><span data-stu-id="0ebb2-104">Page Settings Visibility</span></span>

<span data-ttu-id="0ebb2-105">Um dos recursos gerenciáveis para dispositivos do HoloLens está usando as [políticas de configurações/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir as páginas vistas nas configurações do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="0ebb2-106">PageVisibilityList é uma política que permite que os administradores de TI impeçam a visibilidade ou o acesso a páginas específicas do aplicativo de configurações do sistema, ou para isso, para todas as páginas, exceto aquelas especificadas.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="0ebb2-107">Este recurso só está disponível no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="0ebb2-108">Certificar-se de que os dispositivos para os quais você pretende usar são atualizados.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="0ebb2-109">Mais de 20 novas SettingsURIs serão adicionadas em breve.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="0ebb2-110">Exiba [ a página do Windows Insider - Novas SettingsURIs para a visibilidade das configurações de página](hololens-insider.md#new-settingsuris-for-page-settings-visibility) se você estiver interessado em visualizar esta configuração em uma build do [HoloLens Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="0ebb2-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="0ebb2-111">O exemplo a seguir ilustra uma política que permitiria o acesso apenas às páginas sobre e Bluetooth, que têm URI "ms-settings:network-wifi" e "ms-settings:bluetooth" respectivamente:</span><span class="sxs-lookup"><span data-stu-id="0ebb2-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="0ebb2-112">Para definir isso por meio de um pacote de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="0ebb2-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="0ebb2-113">Enquanto cria seu pacote no Windows Configuration Designer, navegue até **Políticas > Configurações > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="0ebb2-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="0ebb2-114">Insira a cadeia de caracteres: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="0ebb2-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="0ebb2-115">Exportar o pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="0ebb2-116">Aplique o pacote de provisionamento aos seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-116">Apply the package to your device.</span></span>
<span data-ttu-id="0ebb2-117">Para obter detalhes completos sobre como criar e aplicar um pacote de provisionamento visite [esta página](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="0ebb2-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="0ebb2-118">Isso pode ser feito por meio do Intune usando o OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="0ebb2-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="0ebb2-119">Criar uma **política personalizada**.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="0ebb2-120">Ao configurar o OMA-URI, use a cadeia de caracteres: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="0ebb2-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="0ebb2-121">Ao selecionar a cadeia de dados, escolha: **Cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="0ebb2-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="0ebb2-122">Ao digitar o valor, use: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="0ebb2-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="0ebb2-123">Certifique-se de atribuir a configuração personalizada do dispositivo a um grupo ao qual o dispositivo se destina.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="0ebb2-124">Confira [a configuração MDM do HoloLens](hololens-mdm-configure.md) para obter mais informações sobre grupos do Intune e configurações de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="0ebb2-125">Independentemente do método escolhido, o seu dispositivo agora deve receber as alterações e os usuários verão o seguinte aplicativo de Configurações.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Captura de tela do horário ativo sendo modificado no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="0ebb2-127">Para configurar as páginas do aplicativo Configurações para mostrar ou ocultar a sua própria seleção de páginas, dê uma olhada nas Configurações URIs disponíveis no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="0ebb2-128">URIs de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-128">Settings URIs</span></span>

<span data-ttu-id="0ebb2-129">Dispositivos HoloLens e Windows 10 possuem uma seleção diferente de páginas no aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="0ebb2-130">Nesta página, você encontrará somente as configurações existentes no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="0ebb2-131">Contas</span><span class="sxs-lookup"><span data-stu-id="0ebb2-131">Accounts</span></span>
| <span data-ttu-id="0ebb2-132">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-132">Settings page</span></span>           | <span data-ttu-id="0ebb2-133">URI</span><span class="sxs-lookup"><span data-stu-id="0ebb2-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="0ebb2-134">Opções de entrada</span><span class="sxs-lookup"><span data-stu-id="0ebb2-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="0ebb2-135">Registro da íris</span><span class="sxs-lookup"><span data-stu-id="0ebb2-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="0ebb2-136">Acessar trabalho ou escola</span><span class="sxs-lookup"><span data-stu-id="0ebb2-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="0ebb2-137">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="0ebb2-137">Devices</span></span>
| <span data-ttu-id="0ebb2-138">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-138">Settings page</span></span> | <span data-ttu-id="0ebb2-139">URI</span><span class="sxs-lookup"><span data-stu-id="0ebb2-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="0ebb2-140">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="0ebb2-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="0ebb2-141">Privacidade</span><span class="sxs-lookup"><span data-stu-id="0ebb2-141">Privacy</span></span>
| <span data-ttu-id="0ebb2-142">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-142">Settings page</span></span>            | <span data-ttu-id="0ebb2-143">URI</span><span class="sxs-lookup"><span data-stu-id="0ebb2-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="0ebb2-144">Informações da conta</span><span class="sxs-lookup"><span data-stu-id="0ebb2-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="0ebb2-145">Diagnósticos do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="0ebb2-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="0ebb2-146">Aplicativos em segundo plano</span><span class="sxs-lookup"><span data-stu-id="0ebb2-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="0ebb2-147">Movimentos do usuário</span><span class="sxs-lookup"><span data-stu-id="0ebb2-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="0ebb2-148">Sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="0ebb2-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="0ebb2-149">Calendário</span><span class="sxs-lookup"><span data-stu-id="0ebb2-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="0ebb2-150">Histórico de chamadas</span><span class="sxs-lookup"><span data-stu-id="0ebb2-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="0ebb2-151">Contatos</span><span class="sxs-lookup"><span data-stu-id="0ebb2-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="0ebb2-152">Outros dispositivos</span><span class="sxs-lookup"><span data-stu-id="0ebb2-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="0ebb2-153">Documentos</span><span class="sxs-lookup"><span data-stu-id="0ebb2-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="0ebb2-154">Email</span><span class="sxs-lookup"><span data-stu-id="0ebb2-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="0ebb2-155">Comentários e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0ebb2-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="0ebb2-156">Localização</span><span class="sxs-lookup"><span data-stu-id="0ebb2-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="0ebb2-157">Mensagens</span><span class="sxs-lookup"><span data-stu-id="0ebb2-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="0ebb2-158">Microfone</span><span class="sxs-lookup"><span data-stu-id="0ebb2-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="0ebb2-159">Notificações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="0ebb2-160">Imagens</span><span class="sxs-lookup"><span data-stu-id="0ebb2-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="0ebb2-161">Rádios</span><span class="sxs-lookup"><span data-stu-id="0ebb2-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="0ebb2-162">Fala</span><span class="sxs-lookup"><span data-stu-id="0ebb2-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="0ebb2-163">Tarefas</span><span class="sxs-lookup"><span data-stu-id="0ebb2-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="0ebb2-164">Vídeos</span><span class="sxs-lookup"><span data-stu-id="0ebb2-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="0ebb2-165">Ativação por voz</span><span class="sxs-lookup"><span data-stu-id="0ebb2-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="0ebb2-166">Câmera</span><span class="sxs-lookup"><span data-stu-id="0ebb2-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="0ebb2-167">Rede e Internet</span><span class="sxs-lookup"><span data-stu-id="0ebb2-167">Network & Internet</span></span>
| <span data-ttu-id="0ebb2-168">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-168">Settings page</span></span> | <span data-ttu-id="0ebb2-169">URI</span><span class="sxs-lookup"><span data-stu-id="0ebb2-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="0ebb2-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0ebb2-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="0ebb2-171">VPN</span><span class="sxs-lookup"><span data-stu-id="0ebb2-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="0ebb2-172">Proxy</span><span class="sxs-lookup"><span data-stu-id="0ebb2-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="0ebb2-173">Sistema</span><span class="sxs-lookup"><span data-stu-id="0ebb2-173">System</span></span>
| <span data-ttu-id="0ebb2-174">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-174">Settings page</span></span>      | <span data-ttu-id="0ebb2-175">URI</span><span class="sxs-lookup"><span data-stu-id="0ebb2-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="0ebb2-176">Experiências compartilhadas</span><span class="sxs-lookup"><span data-stu-id="0ebb2-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="0ebb2-177">Cores</span><span class="sxs-lookup"><span data-stu-id="0ebb2-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="0ebb2-178">Notificações e ações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="0ebb2-179">Armazenamento</span><span class="sxs-lookup"><span data-stu-id="0ebb2-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="0ebb2-180">Hora e idioma</span><span class="sxs-lookup"><span data-stu-id="0ebb2-180">Time & Language</span></span>
| <span data-ttu-id="0ebb2-181">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-181">Settings page</span></span> | <span data-ttu-id="0ebb2-182">URI</span><span class="sxs-lookup"><span data-stu-id="0ebb2-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="0ebb2-183">Region</span><span class="sxs-lookup"><span data-stu-id="0ebb2-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="0ebb2-184">Idioma</span><span class="sxs-lookup"><span data-stu-id="0ebb2-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="0ebb2-185">Atualização e segurança</span><span class="sxs-lookup"><span data-stu-id="0ebb2-185">Update & Security</span></span>
| <span data-ttu-id="0ebb2-186">Página de configurações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-186">Settings page</span></span>                         | <span data-ttu-id="0ebb2-187">URI</span><span class="sxs-lookup"><span data-stu-id="0ebb2-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="0ebb2-188">Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="0ebb2-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="0ebb2-189">Windows Update</span><span class="sxs-lookup"><span data-stu-id="0ebb2-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="0ebb2-190">1</span><span class="sxs-lookup"><span data-stu-id="0ebb2-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="0ebb2-191">1</span><span class="sxs-lookup"><span data-stu-id="0ebb2-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="0ebb2-192">Windows Update – verifica se há atualizações</span><span class="sxs-lookup"><span data-stu-id="0ebb2-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="0ebb2-193">Opções Avançadas</span><span class="sxs-lookup"><span data-stu-id="0ebb2-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="0ebb2-194">1 </sup> Os dois URIS a seguir, na verdade, não levam você para as páginas **Opções avançadas** ou **Opções**, só bloqueiam/mostram a página principal do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0ebb2-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="0ebb2-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="0ebb2-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="0ebb2-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="0ebb2-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="0ebb2-197">Para uma lista completa de URIs de configurações do Windows 10, visite a [documentação de configurações de início.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="0ebb2-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
