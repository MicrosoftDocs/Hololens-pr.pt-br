---
title: Arquitetura de segurança do HoloLens
description: Arquitetura de segurança
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, hololens 2, segurança do hololens2, visão geral da segurança, arquitetura de segurança, arquitetura, arquitetura do hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253248"
---
# <span data-ttu-id="9b426-104">Visão geral e arquitetura</span><span class="sxs-lookup"><span data-stu-id="9b426-104">Security overview and architecture</span></span>

<span data-ttu-id="9b426-105">A arquitetura de segurança do HoloLens 2 foi projetada e desenvolvida desde o início para ser isenta de problemas de segurança herdados, ao mesmo tempo em que cria uma superfície de ataque minimizada.</span><span class="sxs-lookup"><span data-stu-id="9b426-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="9b426-106">Esta nova arquitetura inovadora oferece locais de armazenamento seguros e elementos de segurança avançada, com mecanismos capazes de blindar sistemas operacionais contra possíveis ameaças e vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="9b426-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="9b426-107">O HoloLens 2 combina hardware, software, rede e serviços para oferecer segurança ponta a ponta, oferecendo ao usuário uma experiência ideal.</span><span class="sxs-lookup"><span data-stu-id="9b426-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="9b426-108">Com o HoloLens 2, a grande maioria dos recursos de segurança agora está ativada automaticamente, minimizando o esforço necessário para configurar corretamente o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9b426-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="9b426-109">O Windows HoloLens 2 e a arquitetura do sistema operacional oferecem esses recursos inovadores de segurança:</span><span class="sxs-lookup"><span data-stu-id="9b426-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="9b426-110">**Separação e isolamento de estado**:  Essa nova arquitetura protege partes críticas do sistema operacional do Hololens 2 contra mudanças, como as necessárias para que o sistema operacional central seja inicializado em um estado confiável.</span><span class="sxs-lookup"><span data-stu-id="9b426-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="9b426-111">A tecnologia de isolamento é usada para restringir aplicativos não confiáveis em uma área restrita, garantindo que eles não tenham impacto na segurança do sistema.</span><span class="sxs-lookup"><span data-stu-id="9b426-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="9b426-112">O sistema operacional inteiro é segmentado em seções seguras, com cada seção blindada por uma combinação de diferentes tecnologias de segurança.</span><span class="sxs-lookup"><span data-stu-id="9b426-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="9b426-113">**Proteção de Dados**: Se o dispositivo do usuário for perdido ou roubado, o HoloLens 2 impedirá que aplicativos não autorizados leiam informações confidenciais apoiado na criptografia de dados BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9b426-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="9b426-114">**Sistema operacional livre de senhas**:  Os sistemas operacionais mais antigos e baseados em senhas podem expor inadvertidamente os usuários a ameaças de phishing e eram frequentemente responsáveis por contas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="9b426-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="9b426-115">O Windows Holographic for Business elimina o uso de senhas para entrada MSA e Microsoft Azure Active Directory e fortalece a proteção da identidade do usuário com Windows Hello™ e entrada FIDO2.</span><span class="sxs-lookup"><span data-stu-id="9b426-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="9b426-116">Para ter o suporte do FIDO2, o dispositivo deve estar na Compilação 19041 ou superior.</span><span class="sxs-lookup"><span data-stu-id="9b426-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="9b426-117">**Segurança de rede**: O HoloLens 2 oferece ao usuário maior a segurança de rede por meio de protocolos e configurações padrão aprimorados.</span><span class="sxs-lookup"><span data-stu-id="9b426-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
