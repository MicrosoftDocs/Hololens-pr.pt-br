---
title: Implantar o cloud connected HoloLens 2 em clientes externos
description: Guia de implantação HoloLens 2 para clientes externos (com Assistência remota como exemplo)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031968"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Implantar o cloud connected HoloLens 2 em clientes externos

Este guia é um suplemento para o Guia [de Implantação Conectada à Nuvem](hololens2-cloud-connected-overview.md). Ele é usado em situações em que sua organização deseja enviar HoloLens 2 dispositivos para o recurso de um cliente externo para uso de curto ou longo prazo. O cliente externo fará logoff no dispositivo HoloLens 2 usando as credenciais fornecidas pela sua organização e usará o [Remote Assist](/dynamics365/mixed-reality/remote-assist/ra-overview) para entrar em contato com seus especialistas. Este guia fornece recomendações gerais HoloLens [implantação do](#general-deployment-recommendations) HoloLens 2 que são aplicáveis [](#common-external-client-deployment-concerns) à maioria dos cenários externos de implantação do HoloLens 2 e preocupações comuns que os clientes têm ao implantar o Remote Assist para uso externo. 

## <a name="prerequisites"></a>Pré-requisitos

A infraestrutura a seguir deve estar em uso de acordo com [o](hololens2-cloud-connected-overview.md) Guia de Implantação Conectada à Nuvem para implantar o HoloLens 2 externamente.

- Ingressar no Azure AD com o registro automático do MDM — gerenciado por MDM (Intune)
- Os usuários entrarão com sua própria conta corporativa (Azure AD)
    - Há suporte para usuários individuais ou múltiplos por dispositivo.

### <a name="remote-assist-licensing-and-requirements"></a>Licenciamento e requisitos do Remote Assist

- Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)
- [Assinatura do Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [avaliação do Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Consulte [Saiba mais sobre o Remote Assist.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="dynamics-365-remote-assist-user"></a>Usuário do Dynamics 365 Remote Assist

- Licença do Remote Assist
- Conectividade de rede

### <a name="microsoft-teams-user"></a>Usuário do Microsoft Teams

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Conectividade de rede

## <a name="general-deployment-recommendations"></a>Recomendações gerais de implantação

Recomendamos as seguintes etapas para implantação HoloLens 2 externa:

1. Use a versão [mais recente HoloLens sistema operacional como](https://aka.ms/hololens2download) o build de linha de base.
1. Atribua licenças baseadas no usuário ou no dispositivo seguindo as etapas abaixo:
    1. [Crie um grupo no AAD e adicione membros para](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) usuários HoloLens/RA.
    1. [Atribua licenças baseadas em](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) dispositivo ou de usuário a esse grupo.
    1. (Opcional) Grupos de destino [para políticas de MDM (gerenciamento de dispositivo](hololens-enroll-mdm.md) móvel).

1. Ingressar dispositivos do AAD em seu locatário, [registrar automaticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurar por meio do [Autopilot.](/hololens/hololens2-autopilot) Para obter mais informações, consulte [proprietário do dispositivo.](/hololens/security-adminless-os#device-owner)
    1. O primeiro usuário no dispositivo será o proprietário do dispositivo.
    1. Se o dispositivo estiver ingressado no AAD, o usuário que realizou a junção se tornou proprietário do dispositivo.
    
1. [O locatário](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) bloqueará o dispositivo para que ele só possa ser unido pelo seu locatário.
    1. Consulte também [CSP de bloqueio de locatário.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Configure o modo de quiosque usando o acesso atribuído global](/hololens/hololens-global-assigned-access-kiosk).

1. Desabilite os seguintes recursos (opcionais) :
    1. Capacidade de colocar o dispositivo no modo de desenvolvedor [aqui.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. A capacidade de conectar o HoloLens a um computador para copiar a data [desabilita o USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Se você não quiser desabilitar o USB, mas quiser a capacidade de aplicar um pacote de provisionamento ao dispositivo usando USB, siga as instruções sobre como permitir a instalação [do pacote de provisionamento](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. Use [Windows Defender WDAC (Controle](/hololens/windows-defender-application-control-wdac) de Aplicativo) para permitir ou bloquear aplicativos no HoloLens 2.
1. Atualize o Remote Assist para a versão mais recente como parte da instalação. Considere as duas opções a seguir:
    1. Vá para Windows **Microsoft Store --> Remote Assist --> e Atualizar Aplicativo**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) , que permite atualizações automáticas de aplicativos, está habilitado por padrão. Mantenha o dispositivo conectado para receber atualizações.
1. [Desabilite todas as páginas de configurações,](/hololens/settings-uri-list) exceto as configurações de rede, para permitir que os usuários se conectem a redes convidadas em sites cliente.
1. [Gerenciar atualizações do HoloLens](/hololens/hololens-updates)
    1. Opção para [controlar atualizações do sistema operacional](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou permitir que fluam livremente.
1. Definir [restrições comuns de dispositivo](/hololens/hololens-common-device-restrictions).

Agora, seus clientes externos estão prontos para usar seus HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Preocupações comuns de implantação de cliente externo

- [Garantir que os clientes não possam se comunicar entre si](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Garantir que os clientes não possam acessar os recursos da empresa](#ensure-that-clients-wont-have-access-to-company-resources)
- [Ocultando ou restringindo aplicativos](#hidden-or-restricted-apps)
- [Gerenciando senhas para seus clientes](#password-management-for-your-clients) 
- [Garantir que os clientes não possam acessar o histórico de chat](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Verifique se os clientes externos não podem se comunicar entre si

Não há suporte HoloLens assistência remota HoloLens chamadas remotas. Os clientes podem pesquisar, mas não podem se comunicar entre si. [As barreiras de informações Microsoft 365](/microsoft-365/compliance/information-barriers) podem restringir ainda mais com quem um cliente pode pesquisar e chamar. Outra opção é usar Microsoft Teams [pesquisa de diretório com escopo](/MicrosoftTeams/teams-scoped-directory-search).

 > [!NOTE]
> Como o login único está habilitado, é importante desabilitar o navegador usando [Windows Defender WDAC (Application Control).](/hololens/windows-defender-application-control-wdac) Se um cliente externo abrir o navegador e usar a versão da Web do Teams, o cliente terá acesso ao seu histórico de chat.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Verifique se os clientes não terão acesso aos recursos da empresa

Há duas opções a considerar.

A primeira opção é uma abordagem de várias camadas:

1. Atribua apenas licenças que o usuário requer. Se você não atribuir OneDrive, Outlook, SharePoint, Yammer etc., o usuário não terá acesso a esses recursos. As únicas licenças que os usuários precisarão são licenças do Remote Assist, do Intune e do AAD para começar.
1. Bloquear aplicativos (como email) que você não deseja que os clientes acessem (consulte Aplicativos [ocultos ou restritos).](#apps are hidden or restricted)
1. Não compartilhe nomes de usuário nem senha com clientes. Para fazer logoff no HoloLens 2, é necessário um email e um PIN numérico.

A segunda opção é criar um locatário separado que hospeda clientes (consulte Imagem 1.1).

**Imagem 1.1**

![Imagem do locatário do serviço.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Aplicativos ocultos ou restritos

[O modo de quiosque](/hololens/hololens-kiosk) e/ou [Windows Defender WDAC (Controle](/hololens/windows-efender-application-control-wdac) de Aplicativo) são opções para ocultar e/ou restringir aplicativos.

### <a name="password-management-for-your-clients"></a>Gerenciamento de senhas para seus clientes

1. Remova a expiração da senha. No entanto, essa opção pode aumentar a chance de uma conta ser comprometida. A recomendação de senha NIST é alterar senhas a cada 30 a 90 dias.
1. Estenda a expiração da senha HoloLens dois dispositivos excederem 90 dias.
1. Os dispositivos devem ser retornados à sua organização para alterar as senhas. No entanto, essa opção poderá causar problemas se os dispositivos devem estar na fábrica do cliente por mais de 90 dias.  
1. Para dispositivos que são enviados a vários clientes, redefina as senhas antes de enviar o dispositivo aos clientes.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Verifique se os clientes não terão acesso ao histórico de chat

O Remote Assist limpa o histórico de chat após cada sessão. No entanto, o histórico de chat estará disponível para Microsoft Teams usuários.

> [!NOTE]
> Como o login único está habilitado, é importante desabilitar o navegador usando [Windows Defender WDAC (Application Control).](/hololens/windows-defender-application-control-wdac)  Se um cliente externo abrir o navegador e usar a versão da Web do Teams, o cliente terá acesso ao histórico de chamada/chat.
