---
title: Guia de implantação de clientes externos
description: guia de implantação para o HoloLens 2 para clientes externos (com o auxílio remoto como exemplo)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659896"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>implantando o HoloLens 2 para clientes externos com o auxílio remoto

este guia ajuda os profissionais de ti com os seguintes objetivos a implantar Microsoft HoloLens 2 dispositivos em sua organização:

1. conexão do Cloud HoloLens 2 dispositivos
1. empréstimo HoloLens 2 dispositivos a clientes externos para uso
1. Proteger dispositivos emprestados

este guia fornecerá [recomendações gerais de implantação de HoloLens 2](#general-deployment-recommendations-and-instructions) que se aplicam à maioria dos HoloLens 2 cenários de implantação e [preocupações comuns](#common-concerns) que os clientes têm ao implantar o auxílio remoto para uso externo.

## <a name="scenario-description"></a>Descrição do cenário

para fins deste documento, a empresa Contoso deseja enviar um dispositivo HoloLens 2 para uma planta de cliente externo para uso de curto ou longo prazo. quando o cliente precisar de assistência para manutenção de máquinas, o cliente fará logon no dispositivo HoloLens 2 usando as credenciais fornecidas pela empresa contoso e usará o auxílio remoto para contatar os especialistas da empresa contoso.

Saiba mais sobre o auxílio remoto [aqui](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="requirements-for-this-scenario"></a>Requisitos para este cenário

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Gerenciador de Dispositivos móveis – como o [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Licença de assistência remota
    1. [Comprar assistência remota](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Assistência remota de avaliação](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Preocupações comuns

- [Como garantir que os clientes externos não tenham a capacidade de se comunicar uns com os outros](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Como garantir que os clientes não tenham acesso aos recursos da empresa](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Como restringir aplicativos](#how-to-restrict-apps)
- [Como gerenciar senhas](#how-to-manage-passwords)
- [Como garantir que os clientes não tenham acesso ao histórico de chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Como garantir que os clientes externos não tenham a capacidade de se comunicar uns com os outros

como a assistência remota HoloLens HoloLens chamadas não são suportadas, os clientes podem procurar, mas não conseguem, se comunicarem entre si. Para restringir ainda mais quem os clientes podem pesquisar e chamar,  [as barreiras de informações](/microsoft-365/compliance/information-barriers) podem restringir a quem um cliente pode se comunicar. Outra opção a considerar é usar a [pesquisa de diretório no escopo](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Como o logon único está habilitado, é importante desabilitar o navegador usando o [**WDAC**](/hololens/windows-defender-application-control-wdac). se um cliente externo abrir o navegador e usar a versão da web do Teams, o cliente terá acesso ao histórico de chamadas/chat.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Como garantir que os clientes não tenham acesso aos recursos da empresa

Há duas opções a serem consideradas.

A primeira opção é uma abordagem de várias camadas:

1. Atribua apenas licenças que o usuário requer. se você não atribuir OneDrive, Outlook, SharePoint, Yammer, etc. ao usuário, ele não terá acesso a esses recursos. As únicas licenças que os usuários precisarão são as licenças de assistência remota, do Intune e do AAD para começar.
1. Bloquear aplicativos (como email) que você não deseja que os clientes acessem (consulte [como restringir aplicativos](#how-to-restrict-apps)).
1. Não compartilhe nomes de cliente nem senha com clientes. para fazer logon no HoloLens 2, é necessário um email e um PIN numérico.

A segunda opção é criar um locatário separado que hospede clientes (consulte a imagem 1,1).

**Imagem 1,1**

![Imagem de locatário de serviço](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Como restringir aplicativos

o [modo de quiosque](/hololens/hololens-kiosk) e/ou [WDAC (Windows Defender controle de aplicativo)](/hololens/windows-defender-application-control-wdac) são opções para restringir aplicativos.

### <a name="how-to-manage-passwords"></a>Como gerenciar senhas

1. Remover expiração de senha. No entanto, isso aumenta a chance de que uma conta seja comprometida. A recomendação de senha do NIST é alterar as senhas a cada 30-90 dias.
1. estenda a expiração da senha para que HoloLens 2 dispositivos ultrapassem 90 dias.
1. Os dispositivos devem ser retornados para contoso para alterar as senhas. No entanto, isso pode causar problemas se os dispositivos estiverem na fábrica do cliente por mais de 90 dias.  
1. Para dispositivos que são enviados a vários clientes, redefina as senhas antes de enviar o dispositivo para os clientes.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Como garantir que os clientes não tenham acesso ao histórico de chat

A assistência remota limpa o histórico de chat após cada sessão. no entanto, o histórico de chat estará disponível para o usuário Microsoft Teams.

> [!NOTE]
> Como o logon único está habilitado, é importante desabilitar o navegador usando o [**WDAC**](/hololens/windows-defender-application-control-wdac). se um cliente externo abrir o navegador e usar a versão da web do Teams, o cliente terá acesso ao histórico de chamadas/chat.

## <a name="general-deployment-recommendations-and-instructions"></a>Recomendações e instruções de implantação geral

recomendamos o seguinte para HoloLens 2 etapas de implantação:

1. Use a [versão mais recente do sistema operacional HoloLens](https://aka.ms/hololens2download) como sua compilação de linha de base.
1. Atribuir licenças baseadas em usuário ou dispositivo:
    1. As licenças baseadas no usuário e no dispositivo seguem as seguintes etapas:
        1. [crie um grupo no AAD e adicione membros](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) para HoloLens usuários do/RA.
        1. [Atribua licenças baseadas no dispositivo ou no usuário](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a esse grupo.
        1. Adicional Você pode direcionar grupos para políticas de MDM.

1. Os dispositivos devem ser ingressados no AAD ao seu locatário, [inscritos automaticamente](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)e configurados por meio do [piloto automático](/hololens/hololens2-autopilot).
    1. Observe que o primeiro usuário no dispositivo será o proprietário do dispositivo.
    1. Observe que, se o dispositivo for ingressado no AAD, o usuário que realizou a junção será tornado proprietário do dispositivo.
    1. Para obter mais informações, consulte [proprietário do dispositivo](/hololens/security-adminless-os#device-owner).
1. O [locatário bloqueia](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) o dispositivo para que ele só possa ingressar no seu locatário.
    1. **Link adicional:** [CSP de bloqueio de locatário](/windows/client-management/mdm/tenantlockdown-csp).
1. Configure o quiosque usando o acesso atribuído global a [aqui](/hololens/hololens-global-assigned-access-kiosk).
1. É recomendável desabilitar os seguintes recursos (opcionais):
    1. Capacidade de colocar o dispositivo no modo de desenvolvedor [aqui](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).
    1. capacidade de conectar o HoloLens a um PC para copiar a data, [desabilite o USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Se você não quiser desabilitar o USB, mas quiser a capacidade de aplicar um pacote de provisionamento ao dispositivo usando USB, siga as instruções listadas [**aqui**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. Use o [WDAC](/hololens/windows-defender-application-control-wdac) para permitir ou bloquear aplicativos no dispositivo HoloLens 2.
1. Atualize o assistência remota para a versão mais recente como parte da configuração. Há duas opções para fazer isso:
    1. isso pode ser feito acessando Windows **Microsoft Store--> Remote Assist--> e atualizar aplicativo**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -que permite atualizações automáticas do aplicativo – está habilitado por padrão. Mantenha o dispositivo conectado para receber atualizações.
1. [Desabilite todas as páginas de configurações](/hololens/settings-uri-list) , exceto as configurações de rede, para permitir que os usuários se conectem a redes convidadas em sites cliente.
1. [gerenciar atualizações de HoloLens](/hololens/hololens-updates)
    1. Opção para [controlar as atualizações do sistema operacional](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou permitir o fluxo livremente.
1. [Restrições comuns de dispositivo](/hololens/hololens-common-device-restrictions).
