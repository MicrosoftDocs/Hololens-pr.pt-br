---
title: implantar a nuvem conectada HoloLens 2 a clientes externos
description: guia de implantação para o HoloLens 2 para clientes externos (com o auxílio remoto como exemplo)
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190320"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>implantar a nuvem conectada HoloLens 2 a clientes externos

Este guia é um suplemento para o [Guia de implantação conectada na nuvem](hololens2-cloud-connected-overview.md). ele é usado em situações em que sua organização deseja enviar HoloLens dois dispositivos para uma instalação de cliente externo para uso curto ou longo prazo. o cliente externo fará logon no dispositivo HoloLens 2 usando as credenciais fornecidas pela sua organização e usará a [assistência remota](/dynamics365/mixed-reality/remote-assist/ra-overview) para entrar em contato com seus especialistas. este guia fornece [recomendações gerais de implantação de HoloLens 2](#general-deployment-recommendations) que são aplicáveis aos cenários de implantação mais externos HoloLens 2 e [preocupações comuns](#common-external-client-deployment-concerns) que os clientes têm ao implantar o auxílio remoto para uso externo. 

## <a name="prerequisites"></a>Pré-requisitos

a infraestrutura a seguir deve estar em vigor de acordo com o [guia de implantação conectada na nuvem](hololens2-cloud-connected-overview.md) para implantar o HoloLens 2 externamente.

- Ingresso no Azure AD com o registro automático do MDM — gerenciado pelo MDM (Intune)
- Os usuários entram com sua própria conta corporativa (Azure AD)
    - Há suporte para um ou vários usuários por dispositivo.

### <a name="remote-assist-licensing-and-requirements"></a>Requisitos e licenciamento da assistência remota

- Conta do Azure AD (necessária para comprar a assinatura e atribuir licenças)
- [Assinatura do Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (ou [avaliação do Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Consulte [saiba mais sobre o auxílio remoto](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Usuário do Dynamics 365 Remote Assist

- Licença do Remote Assist
- Conectividade de rede

### <a name="microsoft-teams-user"></a>Usuário do Microsoft Teams

- Microsoft Teams ou [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Conectividade de rede

## <a name="general-deployment-recommendations"></a>Recomendações gerais de implantação

recomendamos as seguintes etapas para a implantação externa do HoloLens 2:

1. Use a [versão mais recente do sistema operacional HoloLens](https://aka.ms/hololens2download) como sua compilação de linha de base.
1. Atribua licenças baseadas em usuário ou dispositivo seguindo as etapas abaixo:
    1. [crie um grupo no AAD e adicione membros](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) para HoloLens usuários do/RA.
    1. [Atribua licenças baseadas no dispositivo ou no usuário](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a esse grupo.
    1. Adicional Grupos de destino para políticas de [MDM (gerenciamento de dispositivo móvel)](hololens-enroll-mdm.md) .

1. Ingresse dispositivos do AAD em seu locatário, registre-se [automaticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configure por meio do [piloto](/hololens/hololens2-autopilot)automático. Para obter mais informações, consulte [proprietário do dispositivo](/hololens/security-adminless-os#device-owner).
    1. O primeiro usuário no dispositivo será o proprietário do dispositivo.
    1. Se o dispositivo for ingressado no AAD, o usuário que realizou a junção será tornado proprietário do dispositivo.
    
1. O [locatário bloqueia](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) o dispositivo para que ele só possa ser Unido pelo seu locatário.
    1. Consulte também [CSP de bloqueio de locatário](/windows/client-management/mdm/tenantlockdown-csp).

1. [Configure o modo de quiosque usando o acesso atribuído global](/hololens/hololens-global-assigned-access-kiosk).

1. Desabilite os seguintes recursos (opcionais):
    1. Capacidade de colocar o dispositivo no modo de desenvolvedor [aqui](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. capacidade de conectar o HoloLens a um PC para copiar a data, [desabilite o USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Se você não quiser desabilitar o USB, mas quiser a capacidade de aplicar um pacote de provisionamento ao dispositivo usando USB, siga as [instruções em como permitir a instalação do pacote de provisionamento](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. Use o [controle de aplicativo Windows Defender (WDAC)](/hololens/windows-defender-application-control-wdac) para permitir ou bloquear aplicativos no dispositivo HoloLens 2.
1. Atualize o assistência remota para a versão mais recente como parte da configuração. Considere as duas opções a seguir:
    1. vá para Windows **Microsoft Store--> assistência remota--> e atualize o aplicativo**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -que permite atualizações automáticas do aplicativo – está habilitado por padrão. Mantenha o dispositivo conectado para receber atualizações.
1. [Desabilite todas as páginas de configurações](/hololens/settings-uri-list) , exceto as configurações de rede, para permitir que os usuários se conectem a redes convidadas em sites cliente.
1. [Gerenciar atualizações do HoloLens](/hololens/hololens-updates)
    1. Opção para [controlar as atualizações do sistema operacional](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou permitir o fluxo livremente.
1. Defina as [restrições de dispositivo comuns](/hololens/hololens-common-device-restrictions).

agora, os clientes externos estão prontos para usar o HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Questões comuns de implantação de cliente externo

- [Garantindo que os clientes não possam se comunicar uns com os outros](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Garantindo que os clientes não possam acessar os recursos da empresa](#ensure-that-clients-wont-have-access-to-company-resources)
- [Ocultando ou restringindo aplicativos](#hidden-or-restricted-apps)
- [Gerenciando senhas para seus clientes](#password-management-for-your-clients) 
- [Garantindo que os clientes não acessem o histórico de chat](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Garantir que os clientes externos não possam se comunicar uns com os outros

não há suporte para HoloLens de assistência remota HoloLens chamadas. Os clientes podem pesquisar, mas não podem se comunicar entre si. [as barreiras de informações no Microsoft 365](/microsoft-365/compliance/information-barriers) podem restringir ainda mais com quem um cliente pode pesquisar e chamar. outra opção é usar [Microsoft Teams pesquisa de diretório no escopo](/MicrosoftTeams/teams-scoped-directory-search).

 > [!NOTE]
> como o logon único está habilitado, é importante desabilitar o navegador usando o [controle de aplicativo Windows Defender (WDAC)](/hololens/windows-defender-application-control-wdac). se um cliente externo abrir o navegador e usar a versão da web do Teams, o cliente terá acesso ao seu histórico de chat.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Garantir que os clientes não terão acesso aos recursos da empresa

Há duas opções a serem consideradas.

A primeira opção é uma abordagem de várias camadas:

1. Atribua apenas licenças que o usuário requer. se você não atribuir OneDrive, Outlook, SharePoint, Yammer, etc., o usuário não terá acesso a esses recursos. As únicas licenças que os usuários precisarão são as licenças de assistência remota, do Intune e do AAD para começar.
1. Bloquear aplicativos (como email) que você não deseja que os clientes acessem (consulte os [aplicativos estão ocultos ou restritos](#apps are hidden or restricted)).
1. Não compartilhe nomes de acessados nem senhas com clientes. para fazer logon no HoloLens 2, é necessário um email e um PIN numérico.

A segunda opção é criar um locatário separado que hospede clientes (consulte a imagem 1,1).

**Imagem 1,1**

![Imagem de locatário de serviço.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Aplicativos ocultos ou restritos

o [modo de quiosque](/hololens/hololens-kiosk) e/ou o [controle de aplicativo Windows Defender (WDAC)](/hololens/windows-efender-application-control-wdac) são opções para ocultar e/ou restringir aplicativos.

### <a name="password-management-for-your-clients"></a>Gerenciamento de senhas para seus clientes

1. Remover expiração de senha. No entanto, essa opção pode aumentar a chance de que uma conta seja comprometida. A recomendação de senha do NIST é alterar as senhas a cada 30-90 dias.
1. estenda a expiração da senha para que HoloLens 2 dispositivos ultrapassem 90 dias.
1. Os dispositivos devem ser retornados à sua organização para alterar as senhas. No entanto, essa opção pode causar problemas se os dispositivos estiverem na fábrica do cliente por mais de 90 dias.  
1. Para dispositivos que são enviados a vários clientes, redefina as senhas antes de enviar o dispositivo para os clientes.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Verifique se os clientes não terão acesso ao histórico de chat

A assistência remota limpa o histórico de chat após cada sessão. no entanto, o histórico de chat estará disponível para usuários Microsoft Teams.

> [!NOTE]
> como o logon único está habilitado, é importante desabilitar o navegador usando o [controle de aplicativo Windows Defender (WDAC)](/hololens/windows-defender-application-control-wdac).  se um cliente externo abrir o navegador e usar a versão da web do Teams, o cliente terá acesso ao histórico de chamadas/chat.
