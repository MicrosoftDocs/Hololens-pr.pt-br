---
title: Versão prévia do Insider para Microsoft HoloLens
description: Saiba como começar a usar o Insider compilações e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636071"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="bfc26-103">Versão prévia do Insider para Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfc26-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="bfc26-104">Bem-vindo às compilações mais recentes do insider Preview para HoloLens!</span><span class="sxs-lookup"><span data-stu-id="bfc26-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="bfc26-105">É simples [começar](hololens-insider.md#start-receiving-insider-builds) e fornecer comentários valiosos para nossa próxima atualização principal do sistema operacional para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfc26-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="bfc26-106">Windows Notas de versão do insider</span><span class="sxs-lookup"><span data-stu-id="bfc26-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="bfc26-107">estamos empolgados para começar a comprovar novos recursos para Windows insiders novamente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="bfc26-108">Novas compilações serão comprovadas para os canais de desenvolvimento e beta para as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bfc26-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="bfc26-109">continuaremos a atualizar esta página à medida que adicionamos mais recursos e atualizações às nossas compilações do Windows insider.</span><span class="sxs-lookup"><span data-stu-id="bfc26-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="bfc26-110">Fique empolgado e pronto para misturar essas atualizações em sua realidade.</span><span class="sxs-lookup"><span data-stu-id="bfc26-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="bfc26-111">Recurso</span><span class="sxs-lookup"><span data-stu-id="bfc26-111">Feature</span></span>                 | <span data-ttu-id="bfc26-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="bfc26-112">Description</span></span>                | <span data-ttu-id="bfc26-113">Usuário ou cenário</span><span class="sxs-lookup"><span data-stu-id="bfc26-113">User or Scenario</span></span> | <span data-ttu-id="bfc26-114">Compilação introduzida</span><span class="sxs-lookup"><span data-stu-id="bfc26-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="bfc26-115">alterações do CSP para relatórios HoloLens detalhes</span><span class="sxs-lookup"><span data-stu-id="bfc26-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="bfc26-116">Novos CSPs para a consulta de dados</span><span class="sxs-lookup"><span data-stu-id="bfc26-116">New CSPs for to query data</span></span> | <span data-ttu-id="bfc26-117">Administradores de ti</span><span class="sxs-lookup"><span data-stu-id="bfc26-117">IT Admins</span></span>    | <span data-ttu-id="bfc26-118">20348,1403</span><span class="sxs-lookup"><span data-stu-id="bfc26-118">20348.1403</span></span>                 |
| [<span data-ttu-id="bfc26-119">Política de logon automático controlada pelo CSP</span><span class="sxs-lookup"><span data-stu-id="bfc26-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="bfc26-120">Usado para fazer logon em uma conta automaticamente</span><span class="sxs-lookup"><span data-stu-id="bfc26-120">Used to log in an account automatically</span></span> | <span data-ttu-id="bfc26-121">Administradores de ti</span><span class="sxs-lookup"><span data-stu-id="bfc26-121">IT Admins</span></span> | <span data-ttu-id="bfc26-122">20348,1405</span><span class="sxs-lookup"><span data-stu-id="bfc26-122">20348.1405</span></span> |
| [<span data-ttu-id="bfc26-123">Suporte a arquivos PFX para o Gerenciador de certificados</span><span class="sxs-lookup"><span data-stu-id="bfc26-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="bfc26-124">adicionar certificados PFX por meio da interface do usuário do Configurações</span><span class="sxs-lookup"><span data-stu-id="bfc26-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="bfc26-125">Usuário Final</span><span class="sxs-lookup"><span data-stu-id="bfc26-125">End User</span></span> | <span data-ttu-id="bfc26-126">20348,1405</span><span class="sxs-lookup"><span data-stu-id="bfc26-126">20348.1405</span></span> |
| [<span data-ttu-id="bfc26-127">exibir relatório de diagnóstico avançado no Configurações no HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfc26-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="bfc26-128">Exibir logs de diagnóstico do MDM no dispositivo</span><span class="sxs-lookup"><span data-stu-id="bfc26-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="bfc26-129">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bfc26-129">Troubleshooting</span></span> | <span data-ttu-id="bfc26-130">20348,1405</span><span class="sxs-lookup"><span data-stu-id="bfc26-130">20348.1405</span></span> |
| [<span data-ttu-id="bfc26-131">Notificações de diagnóstico offline</span><span class="sxs-lookup"><span data-stu-id="bfc26-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="bfc26-132">Audiovisual comentários para coleta de log</span><span class="sxs-lookup"><span data-stu-id="bfc26-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="bfc26-133">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bfc26-133">Troubleshooting</span></span> | <span data-ttu-id="bfc26-134">20348,1405</span><span class="sxs-lookup"><span data-stu-id="bfc26-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="bfc26-135">alterações do CSP para relatórios HoloLens detalhes</span><span class="sxs-lookup"><span data-stu-id="bfc26-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="bfc26-136">introduzido na compilação do Windows insider, 20348,1403</span><span class="sxs-lookup"><span data-stu-id="bfc26-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="bfc26-137">os seguintes CSPs foram atualizados com novas maneiras de relatar informações de seus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfc26-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="bfc26-138">CSP DevDetail – gratuito Armazenamento</span><span class="sxs-lookup"><span data-stu-id="bfc26-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="bfc26-139">o CSP DevDetail agora também relata o espaço de armazenamento livre no dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfc26-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="bfc26-140">isso deve corresponder aproximadamente ao valor mostrado na página Armazenamento do aplicativo Configurações.</span><span class="sxs-lookup"><span data-stu-id="bfc26-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="bfc26-141">A seguir está o nó específico que contém essas informações.</span><span class="sxs-lookup"><span data-stu-id="bfc26-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="bfc26-142">./DevDetail/Ext/Microsoft/FreeStorage (somente operação GET)</span><span class="sxs-lookup"><span data-stu-id="bfc26-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="bfc26-143">CSP DeviceStatus-SSID e BSSID</span><span class="sxs-lookup"><span data-stu-id="bfc26-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="bfc26-144">o CSP DeviceStatus agora também relata SSID e BSSID da rede Wi-Fi com a qual o HoloLens está conectado ativamente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="bfc26-145">A seguir estão os nós específicos que contêm essas informações.</span><span class="sxs-lookup"><span data-stu-id="bfc26-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="bfc26-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*endereço MAC do adaptador de Wi-Fi*/SSID</span><span class="sxs-lookup"><span data-stu-id="bfc26-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="bfc26-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*endereço MAC do adaptador de Wi-Fi*/BSSID</span><span class="sxs-lookup"><span data-stu-id="bfc26-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="bfc26-148">Exemplo de blob de SyncML (para fornecedores de MDM) para consultar NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="bfc26-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="bfc26-149">Política de logon automático controlada pelo CSP</span><span class="sxs-lookup"><span data-stu-id="bfc26-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="bfc26-150">Essa nova política AutoLogonUser controla se um usuário será conectado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="bfc26-151">Alguns clientes desejam configurar dispositivos vinculados a uma identidade, mas não querem nenhuma experiência de entrada.</span><span class="sxs-lookup"><span data-stu-id="bfc26-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="bfc26-152">Imagine selecionando um dispositivo e usando a assistência remota imediatamente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="bfc26-153">ou ter um benefício de poder distribuir rapidamente HoloLens dispositivos e habilitar seus usuários finais a agilizar o logon.</span><span class="sxs-lookup"><span data-stu-id="bfc26-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="bfc26-154">Quando a política é definida como um valor não vazio, ela especifica o endereço de email do usuário de logon automático.</span><span class="sxs-lookup"><span data-stu-id="bfc26-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="bfc26-155">O usuário especificado deve fazer logon no dispositivo pelo menos uma vez para habilitar o logon automático.</span><span class="sxs-lookup"><span data-stu-id="bfc26-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="bfc26-156">O OMA-URI do novo valor de cadeia de caracteres de política `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`</span><span class="sxs-lookup"><span data-stu-id="bfc26-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="bfc26-157">O usuário com o mesmo endereço de email terá logon automático habilitado.</span><span class="sxs-lookup"><span data-stu-id="bfc26-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="bfc26-158">Em um dispositivo em que essa política está configurada, o usuário especificado na política precisará fazer logon pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="bfc26-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="bfc26-159">Reinicializações subsequentes do dispositivo após o primeiro logon terão o usuário especificado conectado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="bfc26-160">Há suporte apenas para um único usuário de logon automático.</span><span class="sxs-lookup"><span data-stu-id="bfc26-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="bfc26-161">Uma vez habilitado, o usuário conectado automaticamente não poderá fazer logoff manualmente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="bfc26-162">Para fazer logon como um usuário diferente, a política deve primeiro ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="bfc26-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="bfc26-163">Alguns eventos, como as principais atualizações do sistema operacional, podem exigir que o usuário especificado faça logon no dispositivo novamente para retomar o comportamento de logon automático.</span><span class="sxs-lookup"><span data-stu-id="bfc26-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="bfc26-164">O logon automático só tem suporte para usuários do MSA e do AAD.</span><span class="sxs-lookup"><span data-stu-id="bfc26-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="bfc26-165">Suporte a arquivos PFX para o Gerenciador de certificados</span><span class="sxs-lookup"><span data-stu-id="bfc26-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="bfc26-166">introduzido no Windows insider build 20348,1405.</span><span class="sxs-lookup"><span data-stu-id="bfc26-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="bfc26-167">Adicionamos suporte ao Gerenciador de [certificados](certificate-manager.md) para agora usar certificados. pfx.</span><span class="sxs-lookup"><span data-stu-id="bfc26-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="bfc26-168">quando os usuários navegam para **Configurações**  >  **atualização &**  >  **certificados** de segurança e selecionam **instalar um certificado** , a interface do usuário agora dá suporte ao arquivo de certificado. pfx.</span><span class="sxs-lookup"><span data-stu-id="bfc26-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="bfc26-169">Os usuários podem importar o certificado. pfx, com a chave privada, para o repositório de usuários ou para o repositório de computadores.</span><span class="sxs-lookup"><span data-stu-id="bfc26-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="bfc26-170">exibir relatório de diagnóstico avançado no Configurações no HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfc26-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="bfc26-171">Para dispositivos gerenciados ao solucionar problemas de comportamento, a confirmação de que uma configuração de política esperada é aplicada é uma etapa importante.</span><span class="sxs-lookup"><span data-stu-id="bfc26-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="bfc26-172">antes desse novo recurso, isso tinha que ser feito fora do dispositivo via MDM ou perto do dispositivo depois de exportar os logs de diagnóstico do MDM coletados por meio de **Configurações**  ->  **contas**  >  **acessarem o trabalho ou a escola** e selecionamos **exportar os logs de gerenciamento** e exibidos em um PC próximo.</span><span class="sxs-lookup"><span data-stu-id="bfc26-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="bfc26-173">Agora, o diagnóstico de MDM pode ser exibido no dispositivo usando o navegador Edge.</span><span class="sxs-lookup"><span data-stu-id="bfc26-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="bfc26-174">Para exibir mais facilmente o relatório de diagnóstico do MDM, navegue até a página acessar o trabalho ou a escola e selecione **Exibir relatório de diagnóstico avançado**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="bfc26-175">Isso irá gerar e abrir o relatório em uma nova janela de borda.</span><span class="sxs-lookup"><span data-stu-id="bfc26-175">This will generate and open the report in a new Edge window.</span></span>

![exiba o relatório de diagnóstico avançado no aplicativo Configurações.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="bfc26-177">Notificações de diagnóstico offline</span><span class="sxs-lookup"><span data-stu-id="bfc26-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="bfc26-178">Esta é uma atualização para um recurso existente chamado [diagnóstico offline](hololens-diagnostic-logs.md#offline-diagnostics).</span><span class="sxs-lookup"><span data-stu-id="bfc26-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="bfc26-179">Anteriormente, não havia nenhum indicador claro para os usuários que eles dispararam a coleta de diagnóstico ou que ele tivesse sido concluído.</span><span class="sxs-lookup"><span data-stu-id="bfc26-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="bfc26-180">agora adicionados às compilações do Windows insider, há duas formas de comentários de audiovisual para o diagnóstico Offline.</span><span class="sxs-lookup"><span data-stu-id="bfc26-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="bfc26-181">A primeira vez que as notificações de notificação são exibidas para ambos quando a coleta é iniciada e concluída.</span><span class="sxs-lookup"><span data-stu-id="bfc26-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="bfc26-182">Eles serão exibidos quando o usuário estiver conectado e tiver visuais.</span><span class="sxs-lookup"><span data-stu-id="bfc26-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Notificação para coleta de logs.](./images/logcollection1.jpg)

![Notificação quando a coleta de log for concluída.](./images/logcollection2.jpg)
 
<span data-ttu-id="bfc26-185">Como os usuários geralmente usam o diagnóstico offline como um mecanismo de coleta de logs de fallback para quando eles não têm acesso a uma exibição, não podem fazer logon ou ainda estão no OOBE, também haverá uma indicação de áudio quando os logs forem coletados.</span><span class="sxs-lookup"><span data-stu-id="bfc26-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="bfc26-186">Esse som será reproduzido além da notificação do sistema.</span><span class="sxs-lookup"><span data-stu-id="bfc26-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="bfc26-187">Esse novo recurso será habilitado quando o dispositivo for atualizado e não precisar ser habilitado ou gerenciado.</span><span class="sxs-lookup"><span data-stu-id="bfc26-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="bfc26-188">Em qualquer evento que esse novo comentário não possa ser exibido ou ouvido, os diagnósticos offline ainda serão gerados.</span><span class="sxs-lookup"><span data-stu-id="bfc26-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="bfc26-189">Esperamos que essa adição mais recente de comentários audiovisual seja mais fácil de coletar dados de diagnóstico e ser capaz de solucionar os problemas com mais rapidez.</span><span class="sxs-lookup"><span data-stu-id="bfc26-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="bfc26-190">Correções e aprimoramentos:</span><span class="sxs-lookup"><span data-stu-id="bfc26-190">Fixes and improvements:</span></span>

- <span data-ttu-id="bfc26-191">Correção de um [problema conhecido para o portal do dispositivo em que não havia prompt para baixar arquivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="bfc26-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="bfc26-192">Correção de um [problema conhecido para o portal do dispositivo com tempo limite de upload e download de arquivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="bfc26-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="bfc26-193">Comece a receber compilações do insider</span><span class="sxs-lookup"><span data-stu-id="bfc26-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="bfc26-194">Se você não tiver atualizado recentemente, reinicialize o dispositivo para atualizar o estado e obtenha a compilação mais recente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="bfc26-195">O comando de voz "reinicializar dispositivo" funciona bem.</span><span class="sxs-lookup"><span data-stu-id="bfc26-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="bfc26-196">você também pode escolher o botão reiniciar no programa Configurações/Windows insider.</span><span class="sxs-lookup"><span data-stu-id="bfc26-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="bfc26-197">Tivemos um bug no back-end que você pode ter encontrado e isso o levará de volta ao controle.</span><span class="sxs-lookup"><span data-stu-id="bfc26-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="bfc26-198">em um dispositivo HoloLens 2, acesse **Configurações**  >  **atualização &** o  >  **programa insider Windows** de segurança e selecione **introdução**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="bfc26-199">vincule a conta que você usou para se registrar como um Windows insider.</span><span class="sxs-lookup"><span data-stu-id="bfc26-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="bfc26-200">Windows o insider agora está mudando para os canais.</span><span class="sxs-lookup"><span data-stu-id="bfc26-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="bfc26-201">O anel **rápido** se tornará o **canal de desenvolvimento**, o anel **lento** se tornará o **canal beta** e o anel de **versão prévia** se tornará o **canal versão prévia**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="bfc26-202">Aqui está o que esse mapeamento é semelhante a:</span><span class="sxs-lookup"><span data-stu-id="bfc26-202">Here is what that mapping looks like:</span></span>

![Windows Explicação de canais Insider](images/WindowsInsiderChannels.png)

<span data-ttu-id="bfc26-204">para obter mais informações, consulte [introdução aos canais do Windows insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) em Windows Blogs.</span><span class="sxs-lookup"><span data-stu-id="bfc26-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="bfc26-205">em seguida, selecione **desenvolvimento ativo de Windows**, escolha se deseja receber as compilações de canal de **desenvolvimento** ou **Beta** e examine os termos do programa.</span><span class="sxs-lookup"><span data-stu-id="bfc26-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="bfc26-206">Selecione **confirmar > reiniciar agora** para concluir.</span><span class="sxs-lookup"><span data-stu-id="bfc26-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="bfc26-207">depois que o dispositivo for reinicializado, vá para **Configurações > atualizar & segurança > verificar** se há atualizações para obter a compilação mais recente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="bfc26-208">Erro de atualização 0x80070490 solução alternativa</span><span class="sxs-lookup"><span data-stu-id="bfc26-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="bfc26-209">Se você encontrar um erro de atualização 0x80070490 ao atualizar no canal de desenvolvimento ou beta, tente a seguinte solução alternativa de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="bfc26-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="bfc26-210">Ele envolve mover seu canal Insider, selecionando a atualização e, em seguida, movendo o canal Insider de volta.</span><span class="sxs-lookup"><span data-stu-id="bfc26-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="bfc26-211">Estágio One-Release versão prévia</span><span class="sxs-lookup"><span data-stu-id="bfc26-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="bfc26-212">Configurações, atualize a segurança do &, Windows programa insider, selecione **liberar canal de versão prévia**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="bfc26-213">Configurações, atualize & Security, Windows Update, **verifique se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="bfc26-214">Após a atualização, continue no estágio dois.</span><span class="sxs-lookup"><span data-stu-id="bfc26-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="bfc26-215">Preparar canal de dois desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="bfc26-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="bfc26-216">Configurações, atualize a segurança do &, Windows programa insider, selecione **canal de desenvolvimento**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="bfc26-217">Configurações, atualize & Security, Windows Update, **verifique se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="bfc26-218">Download do FFU e direções do flash</span><span class="sxs-lookup"><span data-stu-id="bfc26-218">FFU download and flash directions</span></span>

<span data-ttu-id="bfc26-219">Para testar com um FFU assinado por voo, primeiro você precisará desbloquear o dispositivo antes de atualizar o FFU assinado por voo.</span><span class="sxs-lookup"><span data-stu-id="bfc26-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="bfc26-220">No PC:</span><span class="sxs-lookup"><span data-stu-id="bfc26-220">On PC:</span></span>
    1. <span data-ttu-id="bfc26-221">Baixe o FFU para o seu PC do [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="bfc26-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="bfc26-222">Instale o ARC (complemento de recuperação avançada) do Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="bfc26-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="bfc26-223">no desbloqueio do HoloLens-Flight: abra **Configurações**  >  **Update & Security**  >  **Windows insider Program** , então, inscreva-se, reinicialize o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfc26-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="bfc26-224">Flash FFU – agora você pode piscar o FFU assinado por voo usando o ARC.</span><span class="sxs-lookup"><span data-stu-id="bfc26-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="bfc26-225">Fornecer comentários e relatar problemas</span><span class="sxs-lookup"><span data-stu-id="bfc26-225">Provide feedback and report issues</span></span>

<span data-ttu-id="bfc26-226">use [o aplicativo de Hub de comentários](hololens-feedback.md) em seu HoloLens para fornecer comentários e relatar problemas.</span><span class="sxs-lookup"><span data-stu-id="bfc26-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="bfc26-227">O uso do hub de comentários garante que todas as informações de diagnóstico necessárias estejam incluídas para ajudar nossos engenheiros a depurar e resolver o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="bfc26-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="bfc26-228">problemas com a versão em chinês e japonês do HoloLens devem ser relatados da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="bfc26-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="bfc26-229">Lembre-se de aceitar o prompt que pergunta se você deseja que o Hub de comentários acesse sua pasta documentos (selecione **Sim** quando solicitado).</span><span class="sxs-lookup"><span data-stu-id="bfc26-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="bfc26-230">Observação para desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="bfc26-230">Note for developers</span></span>

<span data-ttu-id="bfc26-231">Você é bem-vindo e incentivado a tentar desenvolver seus aplicativos usando as compilações do insider de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfc26-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="bfc26-232">confira a [documentação do HoloLens developer](https://developer.microsoft.com/windows/mixed-reality/development) para começar.</span><span class="sxs-lookup"><span data-stu-id="bfc26-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="bfc26-233">Essas mesmas instruções funcionam com compilações internas do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfc26-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="bfc26-234">você pode usar as mesmas compilações do Unity e Visual Studio que já está usando para o desenvolvimento de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfc26-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="bfc26-235">Parar de receber compilações do insider</span><span class="sxs-lookup"><span data-stu-id="bfc26-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="bfc26-236">se você não quiser mais receber compilações do insider de Windows Holographic, poderá recusar quando o HoloLens está executando uma compilação de produção ou pode [recuperar seu dispositivo](hololens-recovery.md) usando o complemento de recuperação avançada para recuperar seu dispositivo para uma versão não insider do Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="bfc26-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="bfc26-237">Há um problema conhecido em que os usuários que cancelam o registro do insider Preview são criados após a reinstalação manual de uma nova versão de visualização que teria uma tela azul.</span><span class="sxs-lookup"><span data-stu-id="bfc26-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="bfc26-238">Depois, eles devem recuperar manualmente seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfc26-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="bfc26-239">Para obter detalhes completos sobre se você for afetado ou não, veja mais sobre esse [problema conhecido](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span><span class="sxs-lookup"><span data-stu-id="bfc26-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="bfc26-240">para verificar se o HoloLens está executando uma compilação de produção:</span><span class="sxs-lookup"><span data-stu-id="bfc26-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="bfc26-241">acesse **Configurações > System > sobre** e localize o número da versão.</span><span class="sxs-lookup"><span data-stu-id="bfc26-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="bfc26-242">[Consulte as notas de versão para obter os números de Build de produção](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="bfc26-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="bfc26-243">Para recusar compilações internas:</span><span class="sxs-lookup"><span data-stu-id="bfc26-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="bfc26-244">em um HoloLens executando uma compilação de produção, vá para **Configurações > atualizar & segurança > programa insider** e selecione **parar compilações do insider**.</span><span class="sxs-lookup"><span data-stu-id="bfc26-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="bfc26-245">Siga as instruções para recusar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bfc26-245">Follow the instructions to opt out your device.</span></span>
