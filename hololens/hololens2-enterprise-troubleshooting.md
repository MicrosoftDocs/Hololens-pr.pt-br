---
title: Implementação de HoloLens 2 e solução de problemas de dispositivo gerenciado
description: Solução de problemas de dispositivos HoloLens 2 em um ambiente corporativo
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Solucionar problemas
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961494"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="03b4c-104">Solução de problemas de implementação e dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="03b4c-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="03b4c-105">Este artigo descreve como resolver vários problemas ou responder a perguntas sobre a implementação e o gerenciamento do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="03b4c-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="03b4c-106">Antes de começar qualquer procedimento de solução de problemas, certifique-se de que seu dispositivo tenha de **20% a 40%** da capacidade da bateria, se possível.</span><span class="sxs-lookup"><span data-stu-id="03b4c-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="03b4c-107">As [luzes indicadoras de bateria](hololens2-setup.md#lights-that-indicate-the-battery-level) localizadas sob o botão de energia são uma maneira rápida de verificar a capacidade da bateria sem fazer logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="03b4c-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="03b4c-108">Solução de problemas de EAP</span><span class="sxs-lookup"><span data-stu-id="03b4c-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="03b4c-109">Solução de problemas de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="03b4c-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="03b4c-110">Solução de problemas de rede</span><span class="sxs-lookup"><span data-stu-id="03b4c-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="03b4c-111">Não é possível entrar em um dispositivo HoloLens configurado anteriormente</span><span class="sxs-lookup"><span data-stu-id="03b4c-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="03b4c-112">Não é possível fazer logon após a atualização para Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="03b4c-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="03b4c-113">Solução de problemas do Autopilot</span><span class="sxs-lookup"><span data-stu-id="03b4c-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="03b4c-114">Perguntas frequentes sobre dispositivos HoloLens gerenciados</span><span class="sxs-lookup"><span data-stu-id="03b4c-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="03b4c-115">Solução de problemas de EAP</span><span class="sxs-lookup"><span data-stu-id="03b4c-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="03b4c-116">Verifique se o perfil do Wi-Fi tem as configurações corretas:</span><span class="sxs-lookup"><span data-stu-id="03b4c-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="03b4c-117">O tipo EAP está configurado corretamente, tipos EAP comuns: EAP-TLS (13), EAP-TTLS (21) e PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="03b4c-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="03b4c-118">O nome Wi-Fi SSID está correto e corresponde à cadeia de caracteres hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="03b4c-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="03b4c-119">Para EAP-TLS, TrustedRootCA contém o hash SHA-1 do Certificado de Autoridade de Certificação raiz confiável do servidor.</span><span class="sxs-lookup"><span data-stu-id="03b4c-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="03b4c-120">No computador Windows, o comando "certutil.exe -dump cert_file_name" mostrará a string de hash SHA-1 de um certificado.</span><span class="sxs-lookup"><span data-stu-id="03b4c-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="03b4c-121">Colete a captura de pacotes de rede no Ponto de Acesso ou nos logs do servidor AAA para descobrir onde a sessão EAP falha.</span><span class="sxs-lookup"><span data-stu-id="03b4c-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="03b4c-122">Se a identidade EAP fornecida pelo HoloLens não for esperada, verifique se a identidade foi provisionada corretamente por meio do perfil Wi-Fi ou do certificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="03b4c-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="03b4c-123">Se o servidor rejeitar o certificado de cliente do HoloLens, verifique se o certificado de cliente necessário foi provisionado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="03b4c-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="03b4c-124">Se o HoloLens rejeitar o certificado do servidor, verifique se o certificado de Autoridade de Certificação raiz do servidor foi provisionado no HoloLens.</span><span class="sxs-lookup"><span data-stu-id="03b4c-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="03b4c-125">Se o perfil da empresa for provisionado pelo pacote de provisionamento do Wi-Fi, considere a aplicação do pacote de provisionamento em um computador com o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="03b4c-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="03b4c-126">Se também falhar no computador com Windows 10, siga o guia de solução de problemas de autenticação 802.1X do cliente Windows.</span><span class="sxs-lookup"><span data-stu-id="03b4c-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="03b4c-127">Envie-nos comentários por meio do Hub de Comentários.</span><span class="sxs-lookup"><span data-stu-id="03b4c-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="03b4c-128">Voltar para a lista</span><span class="sxs-lookup"><span data-stu-id="03b4c-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="03b4c-129">Solução de problemas de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="03b4c-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="03b4c-130">Aqui estão algumas ações que você pode tentar se não conseguir conectar seu HoloLens a uma rede Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="03b4c-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="03b4c-131">Verifique se o Wi-Fi está ligado.</span><span class="sxs-lookup"><span data-stu-id="03b4c-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="03b4c-132">Para verificar, use o gesto Iniciar e escolha Configurações > Rede e Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="03b4c-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="03b4c-133">Se o Wi-Fi estiver ligado, tente desligá-lo e, em seguida, ligue novamente.</span><span class="sxs-lookup"><span data-stu-id="03b4c-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="03b4c-134">Aproxime-se do roteador ou do ponto de acesso.</span><span class="sxs-lookup"><span data-stu-id="03b4c-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="03b4c-135">Reinicie o roteador Wi-Fi e, em seguida, reinicie o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="03b4c-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="03b4c-136">Tente se conectar novamente.</span><span class="sxs-lookup"><span data-stu-id="03b4c-136">Try connecting again.</span></span>
4. <span data-ttu-id="03b4c-137">Se nenhuma dessas ações funcionar, verifique se o roteador está usando o firmware mais recente.</span><span class="sxs-lookup"><span data-stu-id="03b4c-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="03b4c-138">Você pode encontrar essas informações no site do fabricante.</span><span class="sxs-lookup"><span data-stu-id="03b4c-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="03b4c-139">Quando você entra em uma conta corporativa ou organizacional no dispositivo, ele também pode aplicar a política de Gerenciamento de Dispositivo Móvel (MDM), se a política for configurada pelo administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="03b4c-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="03b4c-140">Solução de problemas de rede</span><span class="sxs-lookup"><span data-stu-id="03b4c-140">Network Troubleshooting</span></span>
<span data-ttu-id="03b4c-141">Se os problemas de rede forem um obstáculo para a implantação e uso bem-sucedido do HoloLens 2 em sua organização, veja como duas ferramentas de diagnóstico de rede conhecidas, Fiddler e Wireshark, podem ajudá-lo a verificar, diagnosticar e identificar problemas.</span><span class="sxs-lookup"><span data-stu-id="03b4c-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="03b4c-142">Confira este [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="03b4c-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="03b4c-143">Voltar para a lista</span><span class="sxs-lookup"><span data-stu-id="03b4c-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="03b4c-144">Não é possível entrar em um dispositivo HoloLens configurado anteriormente</span><span class="sxs-lookup"><span data-stu-id="03b4c-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="03b4c-145">Se o seu dispositivo foi configurado anteriormente para outra pessoa, seja para um cliente ou ex-funcionário, e você não tem a senha para desbloquear o dispositivo, pode usar o Intune para [limpar](https://docs.microsoft.com/intune/remote-actions/devices-wipe) remotamente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="03b4c-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="03b4c-146">Em seguida, o dispositivo aplica reflash automaticamente.</span><span class="sxs-lookup"><span data-stu-id="03b4c-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="03b4c-147">Ao limpar o dispositivo, deixe **Reter estado de inscrição e conta de usuário** desmarcado.</span><span class="sxs-lookup"><span data-stu-id="03b4c-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="03b4c-148">Voltar para a lista</span><span class="sxs-lookup"><span data-stu-id="03b4c-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="03b4c-149">Não é possível fazer logon após a atualização para Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="03b4c-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="03b4c-150">Sintomas</span><span class="sxs-lookup"><span data-stu-id="03b4c-150">Symptoms</span></span>
- <span data-ttu-id="03b4c-151">O uso do PIN para logon falhará depois de inserir o PIN correto.</span><span class="sxs-lookup"><span data-stu-id="03b4c-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="03b4c-152">O uso do método de logon da Web falhará depois de entrar com êxito na página da Web.</span><span class="sxs-lookup"><span data-stu-id="03b4c-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="03b4c-153">O dispositivo não está listado como “Ingressado no Azure Active Directory” no [ portal do Azure ](https://portal.azure.com/) -> Azure Active Directory -> Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="03b4c-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="03b4c-154">Causa</span><span class="sxs-lookup"><span data-stu-id="03b4c-154">Cause</span></span>
<span data-ttu-id="03b4c-155">O dispositivo afetado pode ter sido excluído do locatário do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03b4c-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="03b4c-156">Por exemplo, isso pode acontecer porque:</span><span class="sxs-lookup"><span data-stu-id="03b4c-156">For example, this may happen because:</span></span>

- <span data-ttu-id="03b4c-157">Um administrador ou usuário excluiu o dispositivo no portal do Azure ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03b4c-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="03b4c-158">O dispositivo foi removido do locatário do Azure Active Directory devido à inatividade.</span><span class="sxs-lookup"><span data-stu-id="03b4c-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="03b4c-159">Para um ambiente gerenciado com eficiência, normalmente recomendamos que os administradores de TI removam dispositivos antigos e inativos de seu locatário do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span><span class="sxs-lookup"><span data-stu-id="03b4c-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="03b4c-160">Quando um dispositivo afetado tentar entrar em contato com o locatário do Azure Active Directory novamente depois que ele tiver sido excluído, ele não será autenticado com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03b4c-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="03b4c-161">Esse efeito geralmente é invisível para o usuário do dispositivo, pois o logon armazenado em cache via PIN continuará permitindo que o usuário logon.</span><span class="sxs-lookup"><span data-stu-id="03b4c-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="03b4c-162">Atenuação</span><span class="sxs-lookup"><span data-stu-id="03b4c-162">Mitigation</span></span>
<span data-ttu-id="03b4c-163">Atualmente, não há como adicionar um dispositivo HoloLens excluído de volta ao Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03b4c-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="03b4c-164">Os dispositivos afetados precisarão ser limpos novamente seguindo as instruções sobre [como fazer reflash no seu dispositivo](hololens-recovery.md#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="03b4c-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="03b4c-165">Solução de problemas do Autopilot</span><span class="sxs-lookup"><span data-stu-id="03b4c-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="03b4c-166">Os artigos a seguir podem ser um recurso útil para obter mais informações e solucionar problemas do Autopilot. No entanto, esteja ciente de que esses artigos são baseados no Windows 10 Desktop e nem todas as informações são aplicadas ao HoloLens:</span><span class="sxs-lookup"><span data-stu-id="03b4c-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="03b4c-167">Windows Autopilot: problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="03b4c-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="03b4c-168">Solucionar problemas de registro de dispositivo Windows no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="03b4c-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="03b4c-169">Windows Autopilot: Conflitos de Política</span><span class="sxs-lookup"><span data-stu-id="03b4c-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="03b4c-170">Perguntas frequentes sobre dispositivos HoloLens gerenciados</span><span class="sxs-lookup"><span data-stu-id="03b4c-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="03b4c-171">Posso usar o SCCM (System Center Configuration Manager) para gerenciar dispositivos HoloLens?</span><span class="sxs-lookup"><span data-stu-id="03b4c-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="03b4c-172">Não.</span><span class="sxs-lookup"><span data-stu-id="03b4c-172">No.</span></span> <span data-ttu-id="03b4c-173">Você precisa usar um sistema MDM para gerenciar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="03b4c-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="03b4c-174">Posso usar o AD DS (Active Directory Domain Services) para gerenciar contas de usuário do HoloLens?</span><span class="sxs-lookup"><span data-stu-id="03b4c-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="03b4c-175">Não.</span><span class="sxs-lookup"><span data-stu-id="03b4c-175">No.</span></span> <span data-ttu-id="03b4c-176">Você precisa usar o Azure Active Directory para gerenciar contas de usuário para dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="03b4c-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="03b4c-177">O HoloLens consegue registrar automaticamente o ADCS (Sistemas de Captura de Dados Automatizados)?</span><span class="sxs-lookup"><span data-stu-id="03b4c-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="03b4c-178">Não.</span><span class="sxs-lookup"><span data-stu-id="03b4c-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="03b4c-179">O HoloLens pode participar da autenticação integrada do Windows?</span><span class="sxs-lookup"><span data-stu-id="03b4c-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="03b4c-180">Não.</span><span class="sxs-lookup"><span data-stu-id="03b4c-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="03b4c-181">O HoloLens permite identidade visual?</span><span class="sxs-lookup"><span data-stu-id="03b4c-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="03b4c-182">Não.</span><span class="sxs-lookup"><span data-stu-id="03b4c-182">No.</span></span> <span data-ttu-id="03b4c-183">No entanto, você pode contornar esse problema usando uma das seguintes abordagens:</span><span class="sxs-lookup"><span data-stu-id="03b4c-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="03b4c-184">Crie um aplicativo personalizado e, em seguida, [habilite o modo de quiosque](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="03b4c-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="03b4c-185">O aplicativo personalizado pode ter identidade visual e pode iniciar outros aplicativos (como o Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="03b4c-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="03b4c-186">Mude todas as imagens de perfil do usuário no Azure Active Directory para o logotipo da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="03b4c-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="03b4c-187">No entanto, isso pode não ser desejável para todos os cenários.</span><span class="sxs-lookup"><span data-stu-id="03b4c-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="03b4c-188">Quais recursos de registro em log o HoloLens 2 oferece?</span><span class="sxs-lookup"><span data-stu-id="03b4c-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="03b4c-189">O registro em log é limitado a rastreamentos que podem ser capturados em cenários de desenvolvimento ou solução de problemas ou telemetria que os dispositivos enviam aos servidores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03b4c-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="03b4c-190">Perguntas sobre como proteger dispositivos HoloLens</span><span class="sxs-lookup"><span data-stu-id="03b4c-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="03b4c-191">Confira [nossas informações de segurança do HoloLens 2](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="03b4c-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="03b4c-192">Para dispositivos HoloLens de primeira geração, confira [estas perguntas frequentes](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="03b4c-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="03b4c-193">Voltar para a lista</span><span class="sxs-lookup"><span data-stu-id="03b4c-193">Back to list</span></span>](#list)
