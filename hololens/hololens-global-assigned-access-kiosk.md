---
title: Acesso Global Atribuído
description: Guia de como usar o OMA-URI para quiosques de Acesso Global Atribuído
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, acesso atribuído, quiosque
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882434"
---
# <span data-ttu-id="902da-104">Acesso Global Atribuído – Quiosque</span><span class="sxs-lookup"><span data-stu-id="902da-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="902da-105">Esse recurso configura o dispositivo Hololens 2 para o modo de quiosque para vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todas as pessoas que se inscrevem no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="902da-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="902da-106">No momento, esse recurso só é disponível na compilação do Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="902da-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="902da-107">Se você deseja testar esse recurso antes que ele seja geralmente disponível nas versões do HoloLens, leia mais sobre compilações do[Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="902da-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="902da-108">Como usar isso no Intune?</span><span class="sxs-lookup"><span data-stu-id="902da-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="902da-109">Lembre-se das áreas marcadas com "<!-".</span><span class="sxs-lookup"><span data-stu-id="902da-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="902da-110">Essas áreas exigem que você faça modificações baseadas nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="902da-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="902da-111">Crie um perfil de configuração de dispositivo OMA URI personalizado da seguinte maneira e aplique-o ao grupo de dispositivos do HoloLens: ![Acesso Global Atribuído ao OMA-URI no Intune</span><span class="sxs-lookup"><span data-stu-id="902da-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="902da-112">Para obter o valor, atualize e cole o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="902da-112">For value, update and paste following content:</span></span> 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## <span data-ttu-id="902da-113">Como usar esse suplemento no Designer de Configuração do Windows?</span><span class="sxs-lookup"><span data-stu-id="902da-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="902da-114">Atualize e salve o blob XML mencionado acima como arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="902da-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="902da-115">Siga as etapas em [Usar um pacote de provisionamento para configurar um quiosque de aplicativo único ou vários aplicativos](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), especificamente a seção “pacote</span><span class="sxs-lookup"><span data-stu-id="902da-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="902da-116">de provisionamento, etapa 2 – Adicionar o arquivo XML de configuração do Kiosk a um pacote de provisionamento” e consultar o arquivo XML que foi salvo na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="902da-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="902da-117">Posso criar uma configuração em que o acesso global se aplica a todos, exceto uma conta do AAD ou grupo AAD?</span><span class="sxs-lookup"><span data-stu-id="902da-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="902da-118">Sim, consulte o exemplo de blob XML abaixo.</span><span class="sxs-lookup"><span data-stu-id="902da-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="902da-119">Os perfis de Acesso Global Atribuídos são aplicados no Hololens quando um perfil determinado para o usuário conectado não é encontrado, portanto, é a configuração padrão de modo de quiosque para o usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="902da-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="902da-120">Aqui está um exemplo de blob XML a ser usado:</span><span class="sxs-lookup"><span data-stu-id="902da-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="902da-121">Lembre-se das áreas marcadas com <!- pois essas áreas exigem que você faça modificações com base nas suas preferências.</span><span class="sxs-lookup"><span data-stu-id="902da-121">Please be aware of the areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
