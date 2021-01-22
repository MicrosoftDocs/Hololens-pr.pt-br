---
title: Gerenciador de certificados
description: Saiba como instalar, gerenciar e remover certificados manualmente em dispositivos de realidade misturada do HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283682"
---
# <span data-ttu-id="4cf0d-103">Gerenciador de certificados</span><span class="sxs-lookup"><span data-stu-id="4cf0d-103">Certificate Manager</span></span>

- <span data-ttu-id="4cf0d-104">Ferramentas aprimoradas de auditoria, diagnóstico e validação para segurança e conformidade de dispositivos por meio do novo Gerenciador de Certificados.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="4cf0d-105">Esse recurso permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="4cf0d-106">No Windows Holographic, versão 20H2, estamos adicionando um Gerenciador de Certificados no aplicativo Configurações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="4cf0d-107">Vá para **Configurações > Atualizar & segurança > certificados.**</span><span class="sxs-lookup"><span data-stu-id="4cf0d-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="4cf0d-108">Esse recurso fornece uma maneira simples e amigável de exibir, instalar e remover certificados em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="4cf0d-109">Com o novo Gerenciador de Certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="4cf0d-110">**Auditoria:** Capacidade de validar se um certificado foi implantado corretamente ou para confirmar se ele foi removido adequadamente.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="4cf0d-111">**Diagnóstico:** Quando surgirem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="4cf0d-112">**Validação:** Verificar se um certificado atende à finalidade pretendido e está funcional pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="4cf0d-113">Para encontrar um certificado específico na lista rapidamente, há opções para classificar por nome, armazenar ou expirar data.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="4cf0d-114">Os usuários também podem pesquisar diretamente por um certificado.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="4cf0d-115">Para exibir propriedades de certificado individuais, selecione o certificado e clique em **Informações.**</span><span class="sxs-lookup"><span data-stu-id="4cf0d-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="4cf0d-116">A instalação do certificado atualmente dá suporte a arquivos .cer e .crt.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="4cf0d-117">Os proprietários de dispositivos podem instalar certificados no Computador Local e no Usuário Atual;  todos os outros usuários só podem instalar no Usuário Atual.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="4cf0d-118">Os usuários só podem remover certificados instalados diretamente da interface do usuário de Configurações.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="4cf0d-119">Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="4cf0d-120">Para instalar um certificado:</span><span class="sxs-lookup"><span data-stu-id="4cf0d-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="4cf0d-121">Conecte seu HoloLens 2 a um computador.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="4cf0d-122">Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="4cf0d-123">Navegue **até Configurações do Aplicativo > Atualizar & segurança > certificados**e selecione Instalar um certificado.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="4cf0d-124">Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="4cf0d-125">Selecione **Local do Armazenamento.**</span><span class="sxs-lookup"><span data-stu-id="4cf0d-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="4cf0d-126">Selecione **o Armazenamento de Certificados.**</span><span class="sxs-lookup"><span data-stu-id="4cf0d-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="4cf0d-127">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-127">Click **Install**.</span></span>

<span data-ttu-id="4cf0d-128">O certificado agora deve ser instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="4cf0d-129">Para remover um certificado:</span><span class="sxs-lookup"><span data-stu-id="4cf0d-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="4cf0d-130">Navegue **até Configurações do Aplicativo > Atualização e Segurança > Certificados.**</span><span class="sxs-lookup"><span data-stu-id="4cf0d-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="4cf0d-131">Procure o certificado pelo nome na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="4cf0d-132">Selecione o certificado.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-132">Select the certificate.</span></span>
1. <span data-ttu-id="4cf0d-133">Clique **em Remover**</span><span class="sxs-lookup"><span data-stu-id="4cf0d-133">Click **Remove**</span></span>
1. <span data-ttu-id="4cf0d-134">Selecione **Sim** quando solicitado a confirmação.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-134">Select **Yes** when prompted for confirmation.</span></span>


![Visualizador de certificados no aplicativo Configurações em Ceritifcates](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado em Configurações.](images/certificate-device-install.jpg)
