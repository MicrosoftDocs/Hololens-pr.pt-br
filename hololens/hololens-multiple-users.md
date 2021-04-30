---
title: Compartilhe seu HoloLens com várias pessoas
description: Você pode configurar o HoloLens para ser compartilhado por várias contas de Azure Active Directory ou por vários usuários que usam uma única conta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308150"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="8b119-103">Compartilhe seu HoloLens com várias pessoas</span><span class="sxs-lookup"><span data-stu-id="8b119-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="8b119-104">É comum compartilhar um HoloLens com muitas pessoas ou fazer com que muitas pessoas compartilhem um conjunto de dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8b119-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="8b119-105">Este artigo descreve as diferentes maneiras em que você pode compartilhar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b119-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="8b119-106">Compartilhar com várias pessoas, cada uma usando sua própria conta</span><span class="sxs-lookup"><span data-stu-id="8b119-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="8b119-107">**Pré-requisito**: o dispositivo HoloLens deve estar executando o Windows 10, versão 1803 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="8b119-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="8b119-108">O HoloLens (1º gen) também precisa ser [atualizado para o Windows Holographic for Business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8b119-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="8b119-109">Quando eles usam suas próprias contas do Azure Active Directory (AD do Azure), vários usuários podem manter suas próprias configurações de usuário e dados de usuário no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b119-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="8b119-110">Para garantir que várias pessoas possam usar suas próprias contas em seu HoloLens, siga estas etapas para configurá-lo:</span><span class="sxs-lookup"><span data-stu-id="8b119-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="8b119-111">Verifique se o dispositivo está executando o Windows 10, versão 1803 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="8b119-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="8b119-112">Se você estiver usando um dispositivo HoloLens (1º gen), [atualize o dispositivo para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8b119-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="8b119-113">Quando você configurar o dispositivo, selecione **meu trabalho ou escola que o possui** e entre usando uma conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8b119-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="8b119-114">Depois de concluir a instalação, verifique se as configurações da conta (contas de **configurações**  >  ) incluem **outros usuários**.</span><span class="sxs-lookup"><span data-stu-id="8b119-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="8b119-115">Para usar o HoloLens, cada usuário segue estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8b119-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="8b119-116">Se outro usuário estiver usando o dispositivo, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8b119-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="8b119-117">Pressione o botão de energia uma vez para ir para o modo de espera e pressione o botão de energia novamente para retornar à tela de bloqueio</span><span class="sxs-lookup"><span data-stu-id="8b119-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="8b119-118">Os usuários do HoloLens 2 podem selecionar o bloco do usuário no menu Iniciar para sair do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="8b119-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="8b119-119">Use suas credenciais de conta do Azure AD para entrar no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b119-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="8b119-120">Se esta for a primeira vez que você usou o dispositivo, você precisará [calibrar](hololens-calibration.md) o HoloLens para seus próprios olhos.</span><span class="sxs-lookup"><span data-stu-id="8b119-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="8b119-121">Para ver uma lista dos usuários do dispositivo ou remover um usuário do dispositivo, vá para **configurações**  >  **contas**  >  **outros usuários**.</span><span class="sxs-lookup"><span data-stu-id="8b119-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="8b119-122">Compartilhar com várias pessoas, tudo usando a mesma conta</span><span class="sxs-lookup"><span data-stu-id="8b119-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="8b119-123">Vários usuários também podem compartilhar um dispositivo HoloLens ao usar uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="8b119-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="8b119-124">**No HoloLens 2**, quando um novo usuário coloca o dispositivo na cabeça pela primeira vez (enquanto mantém a mesma conta conectada), o dispositivo solicita que o novo usuário calibre rapidamente e personalize a experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="8b119-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="8b119-125">O dispositivo pode armazenar as informações de calibragem para que, no futuro, o dispositivo possa otimizar automaticamente a qualidade e o conforto da experiência de exibição de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="8b119-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="8b119-126">Os usuários não precisam calibrar o dispositivo novamente.</span><span class="sxs-lookup"><span data-stu-id="8b119-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="8b119-127">**Em usuários do HoloLens (1ª gen)** , o compartilhamento de uma conta precisará solicitar a recalibração no aplicativo configurações.</span><span class="sxs-lookup"><span data-stu-id="8b119-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="8b119-128">Leia mais sobre [calibragem](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="8b119-128">Read more about [calibration](hololens-calibration.md).</span></span>
