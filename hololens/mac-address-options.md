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
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093216"
---
# <span data-ttu-id="b3998-103">Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito</span><span class="sxs-lookup"><span data-stu-id="b3998-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="b3998-104">Este documento descreverá um cenário comum que identificamos em ambientes do cliente em que o Wi-Fi é restrito por endereços MAC, ou os certificados são necessários para se juntar a redes sem fio.</span><span class="sxs-lookup"><span data-stu-id="b3998-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="b3998-105">Cenário de exemplo:</span><span class="sxs-lookup"><span data-stu-id="b3998-105">Example Scenario</span></span>

<span data-ttu-id="b3998-106">Muitos clientes em ambientes seguros têm restrições em relação a redes sem fio ou com fio, que só permitirão que os dispositivos aprovados (com base nos endereços MAC) sejam conectados com êxito (com a filtragem de endereços MAC em um ponto de acesso sem fio ou em um servidor DHCP).</span><span class="sxs-lookup"><span data-stu-id="b3998-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="b3998-107">Além disso, algumas redes sem fio podem ser protegidas com o PEAP, o que requer que um certificado seja aplicado ao dispositivo antes de poder autenticar com êxito a rede sem fio.</span><span class="sxs-lookup"><span data-stu-id="b3998-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="b3998-108">Dois problemas importantes podem surgir com dispositivos do HoloLens, o que pode fazer com que os atrasos e o trabalho manual se associem aos dispositivos do HoloLens à rede.</span><span class="sxs-lookup"><span data-stu-id="b3998-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="b3998-109">O certificado PEAP sem fio deve ser aplicado ao dispositivo antes que o dispositivo ingresse na rede sem fio com êxito.</span><span class="sxs-lookup"><span data-stu-id="b3998-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="b3998-110">O endereço MAC do adaptador de rede Wi-Fi do HoloLens deve ser registrado.</span><span class="sxs-lookup"><span data-stu-id="b3998-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="b3998-111">Estes são os principais desafios para isso:</span><span class="sxs-lookup"><span data-stu-id="b3998-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="b3998-112">No momento, o endereço MAC só pode ser identificado no aplicativo configurações no dispositivo ou no Intune após um registro bem-sucedido do Intune.</span><span class="sxs-lookup"><span data-stu-id="b3998-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="b3998-113">Sem o endereço MAC, o dispositivo não pode se conectar à rede Wi-Fi para iniciar o registro.</span><span class="sxs-lookup"><span data-stu-id="b3998-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="b3998-114">As soluções manuais para esses desafios exigem o envolvimento do técnico com os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b3998-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="b3998-115">Soluções</span><span class="sxs-lookup"><span data-stu-id="b3998-115">Solutions</span></span>

<span data-ttu-id="b3998-116">Há várias maneiras de melhorar essa situação, dependendo da infraestrutura disponível no ambiente.</span><span class="sxs-lookup"><span data-stu-id="b3998-116">There are a number of ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="b3998-117">Solução</span><span class="sxs-lookup"><span data-stu-id="b3998-117">Solution</span></span> | <span data-ttu-id="b3998-118">Benefícios</span><span class="sxs-lookup"><span data-stu-id="b3998-118">Benefits</span></span> | <span data-ttu-id="b3998-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3998-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b3998-120">Pacote de provisionamento com o adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="b3998-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="b3998-121">Melhora a experiência do OOBE e permite uma experiência técnica mais rápida.</span><span class="sxs-lookup"><span data-stu-id="b3998-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="b3998-122">A HubTechnician USB-C do HoloLens compatível ainda será necessária para interagir com o dispositivo para MAC Capture e a finalizar o OOBE</span><span class="sxs-lookup"><span data-stu-id="b3998-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalisation</span></span> |
| <span data-ttu-id="b3998-123">Piloto automático com registro do Intune na Ethernet</span><span class="sxs-lookup"><span data-stu-id="b3998-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="b3998-124">A conexão de etapa única e o registro do dispositivo com o cliente a captura environmentMAC podem ser concluídas sem interagir com o dispositivo</span><span class="sxs-lookup"><span data-stu-id="b3998-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="b3998-125">Intune habilitado para o cliente AAD TenantHoloLens adaptador de rede USB-C compatível com o cliente</span><span class="sxs-lookup"><span data-stu-id="b3998-125">Intune enabled for the customer AAD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="b3998-126">Relatório automatizado de endereços MAC</span><span class="sxs-lookup"><span data-stu-id="b3998-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="b3998-127">Quando dispositivos forem registrados no locatário do Intune, script o relatório do endereço MAC para o técnico.</span><span class="sxs-lookup"><span data-stu-id="b3998-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="b3998-128">Intune PowerShell commandlets</span><span class="sxs-lookup"><span data-stu-id="b3998-128">Intune Powershell Commandlets</span></span> |

## <span data-ttu-id="b3998-129">Pacote de provisionamento com o adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="b3998-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="b3998-130">Se a rede com fio também estiver sujeita a restrições de MAC, o endereço MAC do adaptador ou do hub Ethernet deve ser pré-impresso.</span><span class="sxs-lookup"><span data-stu-id="b3998-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="b3998-131">Tome cuidado com esse Hub, pois permite o acesso à rede de outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b3998-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="b3998-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3998-132">Requirements</span></span>

- <span data-ttu-id="b3998-133">Porta de rede com fio com acesso à rede do cliente</span><span class="sxs-lookup"><span data-stu-id="b3998-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="b3998-134">Hub USB-C compatível com o HoloLens, que contém um adaptador Ethernet, o Hub que não &#39; requer nenhum driver adicional ou instalações de aplicativos devem ser apropriados.</span><span class="sxs-lookup"><span data-stu-id="b3998-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="b3998-135">Pacote de provisionamento contendo:</span><span class="sxs-lookup"><span data-stu-id="b3998-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="b3998-136">Contendo certificados e informações de rede sem fio</span><span class="sxs-lookup"><span data-stu-id="b3998-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="b3998-137">Opcionalmente, que contém informações de registro para o &#39; Azure Active Directory da organização</span><span class="sxs-lookup"><span data-stu-id="b3998-137">Optionally containing enrollment information for the Organisation&#39;s Azure AD</span></span>
  - <span data-ttu-id="b3998-138">Contendo outras configurações de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="b3998-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="b3998-139">Processo</span><span class="sxs-lookup"><span data-stu-id="b3998-139">Process</span></span>

<span data-ttu-id="b3998-140">O processo pode variar dependendo do nível de software do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3998-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="b3998-141">Se o dispositivo tiver a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="b3998-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="b3998-142">Coloque o pacote de configuração na raiz de um pente USB e conecte-o ao Hub.</span><span class="sxs-lookup"><span data-stu-id="b3998-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="b3998-143">Conecte o cabo Ethernet ao Hub.</span><span class="sxs-lookup"><span data-stu-id="b3998-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="b3998-144">Conecte o hub USB-C ao dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3998-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="b3998-145">Ative o dispositivo do HoloLens e use o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3998-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="b3998-146">Pressione o **Botão Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="b3998-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="b3998-147">O técnico agora pode acompanhar o OOBE e, quando concluir, abrir o aplicativo de configurações e recuperar o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3998-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="b3998-148">Se o dispositivo tiver um build de sistema operacional antes de a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="b3998-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="b3998-149">Ative o dispositivo do HoloLens e conecte-o a um PC.</span><span class="sxs-lookup"><span data-stu-id="b3998-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="b3998-150">O dispositivo deve ser exibido no PC como um dispositivo de armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b3998-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="b3998-151">Copiar o pacote de provisionamento para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="b3998-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="b3998-152">Conecte o cabo Ethernet ao Hub.</span><span class="sxs-lookup"><span data-stu-id="b3998-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="b3998-153">Conecte o hub USB-C ao dispositivo do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3998-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="b3998-154">Use o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3998-154">Wear the device.</span></span>
7. <span data-ttu-id="b3998-155">Pressione o botão **Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="b3998-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="b3998-156">O técnico agora pode acompanhar o OOBE e, quando concluir, abrir o aplicativo de configurações e recuperar o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3998-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="b3998-157">Benefícios</span><span class="sxs-lookup"><span data-stu-id="b3998-157">Benefits</span></span>

<span data-ttu-id="b3998-158">Isso permitirá um &quot;toque único&quot; do dispositivo para aplicar o pacote de provisionamento correto e coletar o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3998-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="b3998-159">Os pacotes de provisionamento podem ser criados seguindo as orientações aqui.</span><span class="sxs-lookup"><span data-stu-id="b3998-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="b3998-160">Piloto automático com o Intune Enrolment</span><span class="sxs-lookup"><span data-stu-id="b3998-160">Autopilot with Intune Enrolment</span></span>

### <span data-ttu-id="b3998-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3998-161">Requirements</span></span>

- <span data-ttu-id="b3998-162">Porta de rede com fio com acesso à rede do cliente</span><span class="sxs-lookup"><span data-stu-id="b3998-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="b3998-163">Dispositivos do HoloLens executando o Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="b3998-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="b3998-164">Hub USB-C compatível com HoloLens</span><span class="sxs-lookup"><span data-stu-id="b3998-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="b3998-165">Configurar e habilitar o Intune para o locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="b3998-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="b3998-166">Dispositivo registrado para o piloto automático e importado para o locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="b3998-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="b3998-167">Políticas do Intune definidas para o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b3998-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="b3998-168">Contendo certificados e informações de rede sem fio</span><span class="sxs-lookup"><span data-stu-id="b3998-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="b3998-169">Contendo outras configurações de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="b3998-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="b3998-170">Isso permitirá que um cliente com requisitos avançados de rede registre os dispositivos em uma abordagem adaptável e dimensionável</span><span class="sxs-lookup"><span data-stu-id="b3998-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="b3998-171">Os pré-requisitos adicionais serão necessários, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b3998-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="b3998-172">Habilitar o locatário da visualização AutoPilot</span><span class="sxs-lookup"><span data-stu-id="b3998-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="b3998-173">Crie as políticas do HoloLens para substituir o pacote de provisionamento no Intune.</span><span class="sxs-lookup"><span data-stu-id="b3998-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="b3998-174">Criar as políticas do Intune do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3998-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="b3998-175">Atribua os dispositivos ao grupo correto.</span><span class="sxs-lookup"><span data-stu-id="b3998-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="b3998-176">Processo</span><span class="sxs-lookup"><span data-stu-id="b3998-176">Process</span></span>

1. <span data-ttu-id="b3998-177">Conecte o Hub USB-C e o cabo ethernet no dispositivo do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b3998-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="b3998-178">Ative o HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b3998-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="b3998-179">O dispositivo deve se conectar automaticamente à Internet no OOBE por meio do adaptador Ethernet, detectar a configuração piloto automático e se registrar automaticamente com o Microsoft Azure Active Directory e o Intune</span><span class="sxs-lookup"><span data-stu-id="b3998-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="b3998-180">O dispositivo aplica os certificados Wi-Fi necessários e outras configurações conforme necessário por meio do Intune</span><span class="sxs-lookup"><span data-stu-id="b3998-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="b3998-181">Quando for concluído, o técnico será capaz de carregar o portal do Intune (Gerenciador de pontos de extremidade) e detalhar na página de propriedades do dispositivo no **Home -> Dispositivos -> Nome do dispositivo -> Hardware**</span><span class="sxs-lookup"><span data-stu-id="b3998-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="b3998-182">O endereço MAC WiFi ficará visível no portal do Intune</span><span class="sxs-lookup"><span data-stu-id="b3998-182">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Endereço MAC por meio do Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="b3998-184">O técnico adicionará esse endereço MAC como um dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="b3998-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="b3998-185">Benefícios</span><span class="sxs-lookup"><span data-stu-id="b3998-185">Benefits</span></span>

<span data-ttu-id="b3998-186">Isso permitirá que uma experiência de implantação &quot;atalhada&quot; para o técnico, com a capacidade de um dispositivo ser acessado no AAD e no Intune sem o técnico ter que usar o dispositivo ou interagir manualmente com o ambiente do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3998-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in AAD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="b3998-187">Relatórios de endereços MAC para o técnico</span><span class="sxs-lookup"><span data-stu-id="b3998-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="b3998-188">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3998-188">Requirements</span></span>

- <span data-ttu-id="b3998-189">Autorização do &quot;Powershell do Intune Graph&quot; contra o locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="b3998-189">Authorisation of the &quot;Intune Graph Powershell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="b3998-190">Instalação do PowerShell do Intune Graph na máquina dos técnicos.</span><span class="sxs-lookup"><span data-stu-id="b3998-190">Installation of the Intune Graph Powershell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="b3998-191">Acesso de leitura para os elementos de &quot;Dispositivos gerenciados&quot; do Intune.</span><span class="sxs-lookup"><span data-stu-id="b3998-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="b3998-192">(Operadora de suporte técnico ou acima, ou uma função personalizada)</span><span class="sxs-lookup"><span data-stu-id="b3998-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="b3998-193">No presente, não há uma maneira &quot;simples&quot; para acionar um comando de automação baseado na Enrolment de um novo dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="b3998-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="b3998-194">Portanto, esse comando fornecerá ao técnico uma maneira simples de recuperar o endereço MAC sem precisar fazer logon no portal e recuperá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="b3998-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="b3998-195">Isso retornará o nome e o endereço MAC de todos os dispositivos do HoloLens que tiverem sido inscritos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b3998-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Endereço MAC por meio do PowerShell](images/mac-address-powershell.jpg)

### <span data-ttu-id="b3998-197">Processo</span><span class="sxs-lookup"><span data-stu-id="b3998-197">Process</span></span>

<span data-ttu-id="b3998-198">Depois que o Enrolment do Intune tiver sido concluído, o técnico executaria o script acima para recuperar o endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="b3998-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
