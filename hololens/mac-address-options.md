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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407616"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="f337f-103">Registro corporativo de dispositivos do HoloLens no endereço MAC, ambiente Wi-Fi restrito</span><span class="sxs-lookup"><span data-stu-id="f337f-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="f337f-104">Este documento descreverá um cenário comum que identificamos em ambientes do cliente em que o Wi-Fi é restrito por endereços MAC, ou os certificados são necessários para se juntar a redes sem fio.</span><span class="sxs-lookup"><span data-stu-id="f337f-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="f337f-105">Cenário de Exemplo</span><span class="sxs-lookup"><span data-stu-id="f337f-105">Example Scenario</span></span>

<span data-ttu-id="f337f-106">Muitos clientes em ambientes seguros têm restrições em suas redes sem fio ou com fio que só permitirão que dispositivos aprovados (com base em endereços MAC) se conectem com êxito.</span><span class="sxs-lookup"><span data-stu-id="f337f-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="f337f-107">Isso pode ser imposto por meio da filtragem de Endereço MAC em um Ponto de Acesso Sem Fio ou por meio de um servidor DHCP.</span><span class="sxs-lookup"><span data-stu-id="f337f-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="f337f-108">Além disso, algumas redes Sem Fio podem ser protegidas com PEAP, o que exige que um certificado seja aplicado ao dispositivo antes da autenticação na rede Sem Fio.</span><span class="sxs-lookup"><span data-stu-id="f337f-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="f337f-109">Neste cenário, dois requisitos principais podem introduzir atrasos ou exigir intervenção manual ao ingressar dispositivos HoloLens na rede:</span><span class="sxs-lookup"><span data-stu-id="f337f-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="f337f-110">O certificado PEAP sem fio deve ser aplicado ao dispositivo antes que o dispositivo ingresse na rede sem fio com êxito.</span><span class="sxs-lookup"><span data-stu-id="f337f-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="f337f-111">O endereço MAC do adaptador de rede Wi-Fi do HoloLens deve ser registrado.</span><span class="sxs-lookup"><span data-stu-id="f337f-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="f337f-112">Os principais desafios com os requisitos acima são:</span><span class="sxs-lookup"><span data-stu-id="f337f-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="f337f-113">No momento, o Endereço MAC só pode ser identificado no aplicativo Configurações no dispositivo ou no Intune após um registro bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="f337f-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="f337f-114">Sem o endereço MAC, o dispositivo não pode se conectar à rede Wi-Fi para iniciar o registro.</span><span class="sxs-lookup"><span data-stu-id="f337f-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="f337f-115">As soluções alternativas manuais para esses desafios exigem que um técnico interaja com o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f337f-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="f337f-116">Soluções</span><span class="sxs-lookup"><span data-stu-id="f337f-116">Solutions</span></span>

<span data-ttu-id="f337f-117">Há muitas maneiras de melhorar essa situação, dependendo da infraestrutura disponível no ambiente.</span><span class="sxs-lookup"><span data-stu-id="f337f-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="f337f-118">Solução</span><span class="sxs-lookup"><span data-stu-id="f337f-118">Solution</span></span> | <span data-ttu-id="f337f-119">Benefícios</span><span class="sxs-lookup"><span data-stu-id="f337f-119">Benefits</span></span> | <span data-ttu-id="f337f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f337f-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f337f-121">Pacote de provisionamento com o adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="f337f-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="f337f-122">Melhora a experiência do OOBE e permite uma experiência técnica mais rápida.</span><span class="sxs-lookup"><span data-stu-id="f337f-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="f337f-123">O Hub USB-C compatível com HoloLens + o adaptador técnico Ethernet ainda precisarão interagir com o dispositivo para a captura MAC e finalização do OOBE</span><span class="sxs-lookup"><span data-stu-id="f337f-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="f337f-124">Piloto automático com Registro do Intune na Ethernet</span><span class="sxs-lookup"><span data-stu-id="f337f-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="f337f-125">Esta é uma conexão de etapa única e o registro do dispositivo no ambiente do cliente.</span><span class="sxs-lookup"><span data-stu-id="f337f-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="f337f-126">A captura MAC pode ser concluída sem a necessidade de interagir com o dispositivo</span><span class="sxs-lookup"><span data-stu-id="f337f-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="f337f-127">Intune habilitado para o locatário AAD do cliente e um adaptador Ethernet USB-C compatível com o HoloLens</span><span class="sxs-lookup"><span data-stu-id="f337f-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="f337f-128">Relatório automatizado de endereços MAC</span><span class="sxs-lookup"><span data-stu-id="f337f-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="f337f-129">Quando os dispositivos são registrados com o locatário do Intune, um script pode relatar o endereço MAC ao técnico.</span><span class="sxs-lookup"><span data-stu-id="f337f-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="f337f-130">Cmdlets do PowerShell do Intune</span><span class="sxs-lookup"><span data-stu-id="f337f-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="f337f-131">Pacote de Provisionamento com o Adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="f337f-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="f337f-132">Se a rede com fio também estiver sujeita a restrições MAC, em seguida, o endereço MAC do adaptador USB-C Hub + Ethernet também precisará ser pré-aprovado.</span><span class="sxs-lookup"><span data-stu-id="f337f-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="f337f-133">O cuidado deve ser tomado com esse adaptador, pois ele permitirá o acesso à rede de outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f337f-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="f337f-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f337f-134">Requirements</span></span>

- <span data-ttu-id="f337f-135">Porta de rede com fio com acesso à rede do cliente</span><span class="sxs-lookup"><span data-stu-id="f337f-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="f337f-136">Hub USB-C compatível do HoloLens com adaptador Ethernet – Qualquer adaptador que não exige drivers ou instalação de aplicativos adicionais deve ser adequado.</span><span class="sxs-lookup"><span data-stu-id="f337f-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="f337f-137">Pacote de provisionamento contendo:</span><span class="sxs-lookup"><span data-stu-id="f337f-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="f337f-138">Contendo certificados e informações de rede sem fio</span><span class="sxs-lookup"><span data-stu-id="f337f-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="f337f-139">Opcionalmente, contendo informações de registro do Azure AD da organização</span><span class="sxs-lookup"><span data-stu-id="f337f-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="f337f-140">Contendo outras configurações de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="f337f-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="f337f-141">Processo</span><span class="sxs-lookup"><span data-stu-id="f337f-141">Process</span></span>

<span data-ttu-id="f337f-142">O processo pode variar dependendo do nível de software do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f337f-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="f337f-143">Se o dispositivo tiver a [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="f337f-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="f337f-144">Coloque o pacote de provisionamento na raiz de um pen drive e conecte-o ao Hub.</span><span class="sxs-lookup"><span data-stu-id="f337f-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="f337f-145">Conecte o cabo Ethernet ao adaptador Hub + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f337f-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="f337f-146">Conecte o Hub USB-C ao dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f337f-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="f337f-147">Ligue o HoloLens e coloque o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f337f-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="f337f-148">Pressione o **Botão Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="f337f-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="f337f-149">O técnico agora pode seguir o OOBE e, quando concluído, abra o Aplicativo de Configurações para recuperar o Endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f337f-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="f337f-150">Se o dispositivo tiver um build do Sistema Operacional antes da [Atualização do maio do 2004](hololens-release-notes.md#windows-holographic-version-2004), siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="f337f-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="f337f-151">Ligue o HoloLens e conecte o dispositivo a um computador.</span><span class="sxs-lookup"><span data-stu-id="f337f-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="f337f-152">O dispositivo deve ser exibido no computador como um dispositivo de armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="f337f-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="f337f-153">Copiar o pacote de provisionamento para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="f337f-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="f337f-154">Conecte o cabo Ethernet ao Hub.</span><span class="sxs-lookup"><span data-stu-id="f337f-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="f337f-155">Conecte o Hub USB-C ao dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f337f-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="f337f-156">Colocar o HoloLens</span><span class="sxs-lookup"><span data-stu-id="f337f-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="f337f-157">Pressione o botão **Diminuir Volume e Ligar** para aplicar o Pacote de Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="f337f-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="f337f-158">O técnico agora pode seguir o OOBE e, quando concluído, abra o Aplicativo de Configurações para recuperar o Endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f337f-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="f337f-159">Benefícios</span><span class="sxs-lookup"><span data-stu-id="f337f-159">Benefits</span></span>

<span data-ttu-id="f337f-160">Isso permitirá um “Toque único” do dispositivo para aplicar o pacote de provisionamento correto e coletar o endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f337f-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="f337f-161">Os pacotes de provisionamento podem ser criados seguindo as orientações aqui.</span><span class="sxs-lookup"><span data-stu-id="f337f-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="f337f-162">AutoPilot com Inscrição do Intune</span><span class="sxs-lookup"><span data-stu-id="f337f-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="f337f-163">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f337f-163">Requirements</span></span>

- <span data-ttu-id="f337f-164">Porta de rede com fio com acesso à rede do cliente</span><span class="sxs-lookup"><span data-stu-id="f337f-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="f337f-165">Dispositivos do HoloLens executando o Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="f337f-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="f337f-166">Adaptador USB-C Compatível com HoloLens</span><span class="sxs-lookup"><span data-stu-id="f337f-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="f337f-167">Configurar e habilitar o Intune para o Locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="f337f-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="f337f-168">Dispositivo registrado para o piloto automático e importado para o locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="f337f-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="f337f-169">Políticas do Intune definidas para o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="f337f-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="f337f-170">Contendo certificados e informações de rede sem fio</span><span class="sxs-lookup"><span data-stu-id="f337f-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="f337f-171">Contendo outras configurações de provisionamento necessárias</span><span class="sxs-lookup"><span data-stu-id="f337f-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="f337f-172">Isso permitirá que um cliente com requisitos avançados de rede registre os dispositivos em uma abordagem adaptável e dimensionável</span><span class="sxs-lookup"><span data-stu-id="f337f-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="f337f-173">Os pré-requisitos adicionais serão necessários da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f337f-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="f337f-174">[Habilitar o Locatário da visualização AutoPilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span><span class="sxs-lookup"><span data-stu-id="f337f-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="f337f-175">Crie as políticas do HoloLens para substituir o Pacote de Provisionamento no Intune.</span><span class="sxs-lookup"><span data-stu-id="f337f-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="f337f-176">Criar as políticas do Intune do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f337f-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="f337f-177">Atribua os dispositivos ao grupo correto.</span><span class="sxs-lookup"><span data-stu-id="f337f-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="f337f-178">Processo</span><span class="sxs-lookup"><span data-stu-id="f337f-178">Process</span></span>

1. <span data-ttu-id="f337f-179">Conecte o cabo ethernet ao adaptador e conecte o adaptador à porta USB-C no dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f337f-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="f337f-180">Ligar o HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f337f-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="f337f-181">O dispositivo deve se conectar automaticamente à Internet durante o OOBE por meio do adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f337f-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="f337f-182">Ele deve detectar a configuração do Autopilot e registrar-se automaticamente no Azure AD e no Intune.</span><span class="sxs-lookup"><span data-stu-id="f337f-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="f337f-183">O Dispositivo aplicará os Certificados Wi-Fi necessários e outras configurações conforme necessário por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="f337f-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="f337f-184">Quando concluído, o técnico pode carregar o Portal do Intune (Endpoint Manager) e fazer uma pesquisa na página de propriedades do dispositivo em **Início-> Dispositivos-> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="f337f-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="f337f-185">O endereço MAC do Wi-Fi estará visível no Portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="f337f-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Endereço MAC por meio do Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="f337f-187">O técnico adicionará esse endereço MAC como um dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="f337f-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="f337f-188">Benefícios</span><span class="sxs-lookup"><span data-stu-id="f337f-188">Benefits</span></span>

<span data-ttu-id="f337f-189">Isso permitirá uma experiência de implantação "Preventiva" para o técnico, com o dispositivo podendo ir da caixa até o registro no Azure AD e no Intune sem que o técnico tenha que usar o dispositivo ou interagir manualmente com o ambiente do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f337f-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="f337f-190">Relatórios de endereços MAC para o técnico</span><span class="sxs-lookup"><span data-stu-id="f337f-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="f337f-191">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f337f-191">Requirements</span></span>

- <span data-ttu-id="f337f-192">Autorização do “PowerShell do Intune Graph” em relação ao Locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="f337f-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="f337f-193">Instalação do PowerShell do Intune Graph na máquina de técnicos.</span><span class="sxs-lookup"><span data-stu-id="f337f-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="f337f-194">Acesso de leitura para os elementos de “Dispositivos Gerenciados” do Intune.</span><span class="sxs-lookup"><span data-stu-id="f337f-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="f337f-195">(Operadora de Suporte Técnico ou acima, ou uma função personalizada)</span><span class="sxs-lookup"><span data-stu-id="f337f-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="f337f-196">No presente, não há uma maneira “simples” para acionar um comando de automação baseado na registro de um novo dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="f337f-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="f337f-197">Portanto, esse comando fornecerá ao técnico uma maneira simples de recuperar o endereço MAC sem precisar fazer logon no portal e recuperá-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="f337f-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="f337f-198">Isso retornará o nome e o endereço MAC de todos os dispositivos do HoloLens que tiverem sido registrados nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="f337f-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Endereço MAC por meio do PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="f337f-200">Processo</span><span class="sxs-lookup"><span data-stu-id="f337f-200">Process</span></span>

<span data-ttu-id="f337f-201">Depois que o registro do Intune tiver sido concluído, o técnico executaria o script acima para recuperar o endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="f337f-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
