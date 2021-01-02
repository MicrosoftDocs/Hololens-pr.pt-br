---
title: Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito
description: Como o endereço MAC para a rede em dispositivos do HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253138"
---
# <span data-ttu-id="c8ae1-103">Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito</span><span class="sxs-lookup"><span data-stu-id="c8ae1-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="c8ae1-104">Este documento descreverá um cenário comum que identificamos em ambientes do cliente em que o Wi-Fi é restrito por endereços MAC, ou os certificados são necessários para se juntar a redes sem fio.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="c8ae1-105">Cenário de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8ae1-105">Example Scenario</span></span>

<span data-ttu-id="c8ae1-106">Muitos clientes em ambientes seguros têm restrições em suas redes Sem fio ou com fio, o que permitirá que apenas dispositivos aprovados (baseados em Endereços MAC) se conectem com êxito (com a filtragem de endereços MAC em um Ponto de Acesso Sem Fio ou em um servidor DHCP).</span><span class="sxs-lookup"><span data-stu-id="c8ae1-106">Many customers in secure environments have restrictions on their Wireless or wired networks, which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="c8ae1-107">Além disso, algumas redes Sem fio podem ser protegidas com PEAP, o que exige que um certificado seja aplicado ao dispositivo antes de poder autenticar a rede Sem fio com êxito.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate is applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="c8ae1-108">Dois problemas importantes podem surgir com dispositivos do HoloLens, o que pode fazer com que os atrasos e o trabalho manual se associem aos dispositivos do HoloLens à rede.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="c8ae1-109">O certificado PEAP sem fio deve ser aplicado ao dispositivo antes que o dispositivo ingresse na rede sem fio com êxito.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="c8ae1-110">O endereço MAC do adaptador de rede Wi-Fi do HoloLens deve ser registrado.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="c8ae1-111">Estes são os principais desafios para isso:</span><span class="sxs-lookup"><span data-stu-id="c8ae1-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="c8ae1-112">No momento, o endereço MAC só pode ser identificado no aplicativo configurações no dispositivo ou no Intune após um registro bem-sucedido do Intune.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="c8ae1-113">Sem o endereço MAC, o dispositivo não pode se conectar à rede Wi-Fi para iniciar o registro.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="c8ae1-114">As soluções manuais para esses desafios exigem o envolvimento do técnico com os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="c8ae1-115">Soluções</span><span class="sxs-lookup"><span data-stu-id="c8ae1-115">Solutions</span></span>

<span data-ttu-id="c8ae1-116">Há muitas maneiras de melhorar essa situação, dependendo da infraestrutura disponível no ambiente.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-116">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="c8ae1-117">Solução</span><span class="sxs-lookup"><span data-stu-id="c8ae1-117">Solution</span></span> | <span data-ttu-id="c8ae1-118">Benefícios</span><span class="sxs-lookup"><span data-stu-id="c8ae1-118">Benefits</span></span> | <span data-ttu-id="c8ae1-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8ae1-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="c8ae1-120">Pacote de provisionamento com o adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="c8ae1-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="c8ae1-121">Melhora a experiência do OOBE e permite uma experiência técnica mais rápida.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="c8ae1-122">HoloLens compatível com USB C HubTechnician ainda precisará interagir com o dispositivo para captura MAC e finalização OOBE</span><span class="sxs-lookup"><span data-stu-id="c8ae1-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalization</span></span> |
| <span data-ttu-id="c8ae1-123">Piloto automático com registro do Intune na Ethernet</span><span class="sxs-lookup"><span data-stu-id="c8ae1-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="c8ae1-124">A conexão de etapa única e o registro do dispositivo com o cliente a captura environmentMAC podem ser concluídas sem interagir com o dispositivo</span><span class="sxs-lookup"><span data-stu-id="c8ae1-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="c8ae1-125">Intune habilitado para o adaptador de rede USB-C Compatível com Microsoft Azure Active Directory TenantHoloLens do cliente</span><span class="sxs-lookup"><span data-stu-id="c8ae1-125">Intune enabled for the customer Azure AD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="c8ae1-126">Relatório automatizado de endereços MAC</span><span class="sxs-lookup"><span data-stu-id="c8ae1-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="c8ae1-127">Quando dispositivos forem registrados no locatário do Intune, script o relatório do endereço MAC para o técnico.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="c8ae1-128">Commandlets do Windows PowerShell do Intune</span><span class="sxs-lookup"><span data-stu-id="c8ae1-128">Intune PowerShell Commandlets</span></span> |

## <span data-ttu-id="c8ae1-129">Pacote de provisionamento com o adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="c8ae1-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="c8ae1-130">Se a rede com fio também estiver sujeita a restrições de MAC, o endereço MAC do adaptador ou do hub Ethernet deve ser pré-impresso.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="c8ae1-131">Tome cuidado com esse Hub, pois permite o acesso à rede de outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="c8ae1-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8ae1-132">Requirements</span></span>

- <span data-ttu-id="c8ae1-133">Porta de rede com fio com acesso à rede do cliente</span><span class="sxs-lookup"><span data-stu-id="c8ae1-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="c8ae1-134">Hub USB-C compatível com o HoloLens, que contém um adaptador Ethernet, o Hub que não &#39; requer nenhum driver adicional ou instalações de aplicativos devem ser apropriados.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="c8ae1-135">Pacote de provisionamento contendo:</span><span class="sxs-lookup"><span data-stu-id="c8ae1-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="c8ae1-136">Contendo certificados e informações de rede sem fio</span><span class="sxs-lookup"><span data-stu-id="c8ae1-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="c8ae1-137">Opcionalmente, contendo informações de inscrição para a Organização&#39;s do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c8ae1-137">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="c8ae1-138">Contendo outras configurações de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="c8ae1-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="c8ae1-139">Processo</span><span class="sxs-lookup"><span data-stu-id="c8ae1-139">Process</span></span>

<span data-ttu-id="c8ae1-140">O processo pode variar dependendo do nível de software do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="c8ae1-141">Se o dispositivo tiver a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="c8ae1-142">Coloque o pacote de configuração na raiz de um pente USB e conecte-o ao Hub.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="c8ae1-143">Conecte o cabo Ethernet ao Hub.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="c8ae1-144">Conecte o hub USB-C ao dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="c8ae1-145">Ative o dispositivo do HoloLens e use o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="c8ae1-146">Pressione o **Botão Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="c8ae1-147">O técnico agora pode acompanhar o OOBE e, quando concluir, abrir o aplicativo de configurações e recuperar o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="c8ae1-148">Se o dispositivo tiver um build de sistema operacional antes de a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="c8ae1-149">Ative o dispositivo do HoloLens e conecte-o a um PC.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="c8ae1-150">O dispositivo deve ser exibido no PC como um dispositivo de armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="c8ae1-151">Copiar o pacote de provisionamento para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="c8ae1-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="c8ae1-152">Conecte o cabo Ethernet ao Hub.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="c8ae1-153">Conecte o hub USB-C ao dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="c8ae1-154">Use o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-154">Wear the device.</span></span>
7. <span data-ttu-id="c8ae1-155">Pressione o botão **Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="c8ae1-156">O técnico agora pode acompanhar o OOBE e, quando concluir, abrir o aplicativo de configurações e recuperar o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="c8ae1-157">Benefícios</span><span class="sxs-lookup"><span data-stu-id="c8ae1-157">Benefits</span></span>

<span data-ttu-id="c8ae1-158">Isso permitirá um &quot;toque único&quot; do dispositivo para aplicar o pacote de provisionamento correto e coletar o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="c8ae1-159">Os pacotes de provisionamento podem ser criados seguindo as orientações aqui.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="c8ae1-160">AutoPilot com Inscrição do Intune</span><span class="sxs-lookup"><span data-stu-id="c8ae1-160">Autopilot with Intune Enrollment</span></span>

### <span data-ttu-id="c8ae1-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8ae1-161">Requirements</span></span>

- <span data-ttu-id="c8ae1-162">Porta de rede com fio com acesso à rede do cliente</span><span class="sxs-lookup"><span data-stu-id="c8ae1-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="c8ae1-163">Dispositivos do HoloLens executando o Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="c8ae1-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="c8ae1-164">Hub USB-C compatível com HoloLens</span><span class="sxs-lookup"><span data-stu-id="c8ae1-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="c8ae1-165">Configurar e habilitar o Intune para o locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="c8ae1-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="c8ae1-166">Dispositivo registrado para o piloto automático e importado para o locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="c8ae1-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="c8ae1-167">Políticas do Intune definidas para o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c8ae1-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="c8ae1-168">Contendo certificados e informações de rede sem fio</span><span class="sxs-lookup"><span data-stu-id="c8ae1-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="c8ae1-169">Contendo outras configurações de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="c8ae1-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="c8ae1-170">Isso permitirá que um cliente com requisitos avançados de rede registre os dispositivos em uma abordagem adaptável e dimensionável</span><span class="sxs-lookup"><span data-stu-id="c8ae1-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="c8ae1-171">Os pré-requisitos adicionais serão necessários, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c8ae1-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="c8ae1-172">Habilitar o locatário da visualização AutoPilot</span><span class="sxs-lookup"><span data-stu-id="c8ae1-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="c8ae1-173">Crie as políticas do HoloLens para substituir o pacote de provisionamento no Intune.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="c8ae1-174">Criar as políticas do Intune do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="c8ae1-175">Atribua os dispositivos ao grupo correto.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="c8ae1-176">Processo</span><span class="sxs-lookup"><span data-stu-id="c8ae1-176">Process</span></span>

1. <span data-ttu-id="c8ae1-177">Conecte o Hub USB-C e o cabo ethernet no dispositivo do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="c8ae1-178">Ative o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="c8ae1-179">O dispositivo deve se conectar automaticamente à Internet no OOBE por meio do adaptador Ethernet, detectar a configuração piloto automático e se registrar automaticamente com o Microsoft Azure Active Directory e o Intune</span><span class="sxs-lookup"><span data-stu-id="c8ae1-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="c8ae1-180">O dispositivo aplica os certificados Wi-Fi necessários e outras configurações conforme necessário por meio do Intune</span><span class="sxs-lookup"><span data-stu-id="c8ae1-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="c8ae1-181">Quando for concluído, o técnico será capaz de carregar o portal do Intune (Gerenciador de pontos de extremidade) e detalhar na página de propriedades do dispositivo no **Home -> Dispositivos -> Nome do dispositivo -> Hardware**</span><span class="sxs-lookup"><span data-stu-id="c8ae1-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="c8ae1-182">O endereço Wi-Fi MAC estará visível no Portal do Intune</span><span class="sxs-lookup"><span data-stu-id="c8ae1-182">The Wi-Fi MAC address will be visible within the Intune Portal</span></span>

![Endereço MAC por meio do Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="c8ae1-184">O técnico adicionará esse endereço MAC como um dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="c8ae1-185">Benefícios</span><span class="sxs-lookup"><span data-stu-id="c8ae1-185">Benefits</span></span>

<span data-ttu-id="c8ae1-186">Isso permitirá que uma experiência de implantação &quot;Atalhada&quot; para o Técnico, com a capacidade de um dispositivo ser acessado no Microsoft Azure Active Directory e no Intune sem o técnico ter que usar o dispositivo ou interagir manualmente com o ambiente do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="c8ae1-187">Relatórios de endereços MAC para o técnico</span><span class="sxs-lookup"><span data-stu-id="c8ae1-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="c8ae1-188">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8ae1-188">Requirements</span></span>

- <span data-ttu-id="c8ae1-189">Autorização do &quot; PowerShell do Graph do Intune &quot; em relação ao Locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="c8ae1-189">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="c8ae1-190">Instalação do Windows PowerShell do Intune Graph na máquina de técnicos.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-190">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="c8ae1-191">Acesso de leitura para os elementos de &quot;Dispositivos gerenciados&quot; do Intune.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="c8ae1-192">(Operadora de suporte técnico ou acima, ou uma função personalizada)</span><span class="sxs-lookup"><span data-stu-id="c8ae1-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="c8ae1-193">No presente, não há uma maneira &quot;simples&quot; para acionar um comando de automação baseado na Enrolment de um novo dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="c8ae1-194">Portanto, esse comando fornecerá ao técnico uma maneira simples de recuperar o endereço MAC sem precisar fazer logon no portal e recuperá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="c8ae1-195">Isso retornará o nome e o endereço MAC de todos os dispositivos do HoloLens que tiverem sido inscritos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Endereço MAC por meio do PowerShell](images/mac-address-powershell.jpg)

### <span data-ttu-id="c8ae1-197">Processo</span><span class="sxs-lookup"><span data-stu-id="c8ae1-197">Process</span></span>

<span data-ttu-id="c8ae1-198">Depois que o Enrolment do Intune tiver sido concluído, o técnico executaria o script acima para recuperar o endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="c8ae1-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
