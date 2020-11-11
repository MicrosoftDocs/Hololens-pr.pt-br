---
title: Gerenciador de certificados
description: Saiba como gerenciar certificados manualmente no HoloLens 2.
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
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163212"
---
# <span data-ttu-id="a844c-103">Gerenciador de certificados</span><span class="sxs-lookup"><span data-stu-id="a844c-103">Certificate Manager</span></span>

- <span data-ttu-id="a844c-104">Ferramentas aprimoradas de auditoria, diagnóstico e validação para segurança e conformidade de dispositivos por meio do novo Gerenciador de certificados.</span><span class="sxs-lookup"><span data-stu-id="a844c-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="a844c-105">Esse recurso permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.</span><span class="sxs-lookup"><span data-stu-id="a844c-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="a844c-106">No Windows holográfico, versão 20H2, adicionamos um Gerenciador de certificados no aplicativo Configurações do HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a844c-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="a844c-107">Vá para **configurações > atualizar certificados & segurança >**.</span><span class="sxs-lookup"><span data-stu-id="a844c-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="a844c-108">Esse recurso oferece uma maneira simples e fácil de exibir, instalar e remover certificados em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a844c-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="a844c-109">Com o novo Gerenciador de certificados, administradores e usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e compatíveis.</span><span class="sxs-lookup"><span data-stu-id="a844c-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="a844c-110">**Auditoria:** Capacidade de validar se um certificado está implantado corretamente ou para confirmar se foi removido apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="a844c-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="a844c-111">**Diagnóstico:** Quando surgem problemas, é possível validar se os certificados apropriados existem no dispositivo poupa tempo e ajuda na solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="a844c-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="a844c-112">**Validação:** Verificar se um certificado atende à finalidade e é funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em uma escala maior.</span><span class="sxs-lookup"><span data-stu-id="a844c-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="a844c-113">Para localizar um certificado específico na lista rapidamente, há opções para classificar por nome, loja ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="a844c-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="a844c-114">Os usuários também podem procurar um certificado diretamente.</span><span class="sxs-lookup"><span data-stu-id="a844c-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="a844c-115">Para exibir as propriedades de certificado individuais, selecione o certificado e clique em **informações**.</span><span class="sxs-lookup"><span data-stu-id="a844c-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="a844c-116">A instalação do certificado atualmente oferece suporte a arquivos. cer e. CRT.</span><span class="sxs-lookup"><span data-stu-id="a844c-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="a844c-117">Os proprietários de dispositivo podem instalar certificados na máquina local e no usuário atual;  todos os outros usuários podem instalar somente no usuário atual.</span><span class="sxs-lookup"><span data-stu-id="a844c-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="a844c-118">Os usuários só podem remover certificados instalados diretamente da interface do usuário de configurações.</span><span class="sxs-lookup"><span data-stu-id="a844c-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="a844c-119">Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.</span><span class="sxs-lookup"><span data-stu-id="a844c-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="a844c-120">Para instalar um certificado:</span><span class="sxs-lookup"><span data-stu-id="a844c-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="a844c-121">Conecte seu HoloLens 2 a um PC.</span><span class="sxs-lookup"><span data-stu-id="a844c-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="a844c-122">Coloque o arquivo de certificado que você deseja instalar em um local no seu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a844c-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="a844c-123">Navegue até **configurações aplicativo > atualização & segurança > certificados**e selecione instalar um certificado.</span><span class="sxs-lookup"><span data-stu-id="a844c-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="a844c-124">Clique em **Importar arquivo** e navegue até o local onde você salvou o certificado.</span><span class="sxs-lookup"><span data-stu-id="a844c-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="a844c-125">Selecione **local da loja**.</span><span class="sxs-lookup"><span data-stu-id="a844c-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="a844c-126">Selecione **repositório de certificados**.</span><span class="sxs-lookup"><span data-stu-id="a844c-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="a844c-127">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="a844c-127">Click **Install**.</span></span>

<span data-ttu-id="a844c-128">Agora o certificado deve estar instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a844c-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="a844c-129">Para remover um certificado:</span><span class="sxs-lookup"><span data-stu-id="a844c-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="a844c-130">Navegue até **configurações aplicativo > atualização e segurança > certificados**.</span><span class="sxs-lookup"><span data-stu-id="a844c-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="a844c-131">Procure o certificado por nome na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a844c-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="a844c-132">Selecione o certificado.</span><span class="sxs-lookup"><span data-stu-id="a844c-132">Select the certificate.</span></span>
1. <span data-ttu-id="a844c-133">Clique em **remover**</span><span class="sxs-lookup"><span data-stu-id="a844c-133">Click **Remove**</span></span>
1. <span data-ttu-id="a844c-134">Selecione **Sim** quando for solicitada a confirmação.</span><span class="sxs-lookup"><span data-stu-id="a844c-134">Select **Yes** when prompted for confirmation.</span></span>


![Visualizador de certificados no aplicativo configurações em CERITIFCATES](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado em configurações.](images/certificate-device-install.jpg)
