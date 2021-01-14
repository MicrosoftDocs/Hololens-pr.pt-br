---
title: Guia de implantação de clientes externos
description: Guia de implantação do HoloLens 2 para clientes externos (com assistência remota como exemplo)
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
ms.openlocfilehash: c0ea468df2188700af408803ae1c55b9d0e4c763
ms.sourcegitcommit: ea5fa6c970756025b77c00b4ea600d60ce033106
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "11267997"
---
# Implantando o HoloLens 2 para clientes externos com Assistência Remota

Este documento ajuda profissionais de IT a planejar e implantar dispositivos HoloLens 2 com foco na Assistência Remota. [Saiba mais sobre a Assistência Remota.](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

## Descrição do cenário

Para a finalidade deste documento, a Contoso Company deseja enviar um dispositivo holoLens 2 para a fábrica de um cliente externo para uso de curto ou longo prazo. Quando o cliente precisar de assistência no computador de manutenção, o cliente fará logon no dispositivo do HoloLens 2 usando credenciais fornecidas pela Contoso Company e usará a Assistência Remota para entrar em contato com os especialistas da Empresa Contoso.

### Requisitos para este cenário

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Gerenciador de Dispositivos Móveis – como [o Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licença de Assistência Remota
    1. [Comprar Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Assistência Remota de Avaliação](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## Preocupações comuns

- [Como garantir que os clientes externos não tenham a capacidade de se comunicar entre si](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Como garantir que os clientes não tenham acesso aos recursos da empresa](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Como restringir aplicativos](#how-to-restrict-apps)
- [Como gerenciar senhas](#how-to-manage-passwords)
- [Como garantir que os clientes não tenham acesso ao histórico de chat](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### Como garantir que os clientes externos não tenham a capacidade de se comunicar entre si

Como as chamadas do HoloLens de Assistência Remota para HoloLens não são suportadas, os clientes podem pesquisar, mas não podem, se comunicar entre si. Para restringir ainda mais quem os clientes podem pesquisar e chamar, as  [barreiras de informações](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) podem restringir com quem um cliente pode se comunicar. Outra opção a considerar é usar a [Pesquisa de Diretório com Escopo](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Como o single sign on está habilitado, é importante desabilitar o navegador usando [**o WDAC.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Se um cliente externo abrir o navegador e usar a versão da Web do Teams, o cliente terá acesso ao histórico de chamada/chat.

### Como garantir que os clientes não tenham acesso aos recursos da empresa

Há duas opções a considerar.

A primeira opção é uma abordagem de várias camadas:

1. Atribua apenas licenças que o usuário requer. Se você não atribuir o OneDrive, o Outlook, o SharePoint, o Yammer etc. ao usuário, ele/ela não terá acesso a esses recursos. As únicas licenças de que os usuários precisarão são licenças de Assistência Remota, Intune e AAD para começar.
1. Bloquear aplicativos (como emails) que você não deseja que os clientes acessem (veja [como restringir aplicativos).](#how-to-restrict-apps)
1. NÃO compartilhe nomes de usuário nem senha com clientes. Para fazer logon no HoloLens 2, é necessário um email e um PIN numérico.

A segunda opção é criar um locatário separado que hospeda clientes (consulte a Imagem 1.1).

**Imagem 1.1**

![Imagem do locatário do serviço](./images/hololens-service-tenant-image.png)

### Como restringir aplicativos

[O Modo de Quiosque](https://docs.microsoft.com/hololens/hololens-kiosk) e/ou [o WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) são opções para restringir aplicativos.

### Como gerenciar senhas

1. Remova a expiração da senha. No entanto, isso aumenta a chance de que uma conta seja comprometida. A recomendação de senha NIST é alterar senhas a cada 30 a 90 dias.
1. Estender a expiração de senha para dispositivos HoloLens 2 para exceder 90 dias.
1. Os dispositivos devem ser retornados à Contoso para alterar as senhas. No entanto, isso poderá causar problemas se os dispositivos devem ficar na fábrica do cliente por mais de 90 dias.  
1. Para dispositivos que são enviados para vários clientes, redefina senhas antes de enviar o dispositivo aos clientes.

### Como garantir que os clientes não tenham acesso ao histórico de chat

A Assistência Remota limpa o histórico do chat após cada sessão. No entanto, o histórico de chat estará disponível para o usuário do Microsoft Teams.

> [!NOTE]
> Como o single sign on está habilitado, é importante desabilitar o navegador usando [**o WDAC.**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) Se um cliente externo abrir o navegador e usar a versão da Web do Teams, o cliente terá acesso ao histórico de chamada/chat.

## Recomendações e instruções gerais de implantação

Recomendamos o seguinte para as etapas de implantação do HoloLens 2:

1. Use a versão [mais recente do sistema operacional HoloLens como](https://aka.ms/hololens2download) a com build de linha de base.
1. Atribua licenças baseadas no usuário ou em dispositivos:
    1. As licenças baseadas no usuário e no dispositivo seguem as seguintes etapas:
        1. [Crie um grupo no AAD e adicione membros para](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) usuários do HoloLens/RA.
        1. [Atribua licenças baseadas em dispositivos ou usuários](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) a esse grupo.
        1. (Opcional) Você pode direcionar grupos para políticas MDM.

1. Os dispositivos devem ser ingressados no AAD em seu locatário, [automaticamente](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)inscritos e configurados por meio [do piloto automático.](https://docs.microsoft.com/hololens/hololens2-autopilot)
    1. Observe que o primeiro usuário no dispositivo será o proprietário do dispositivo.
    1. Observe que, se o dispositivo for ingressado no AAD, o usuário que realizou a junção se tornou proprietário do dispositivo.
    1. Para obter mais informações, consulte [Proprietário do Dispositivo.](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)
1. [O locatário](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) bloqueará o dispositivo para que ele só possa ingressar no locatário.
    1. **Link adicional:** [CSP de bloqueio de locatário.](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)
1. Configure o quiosque usando o acesso global atribuído a [aqui.](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)
1. Recomendamos desabilitar os recursos a seguir (opcionais) :
    1. Capacidade de colocar o dispositivo no modo de desenvolvedor [aqui.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Capacidade de conectar o HoloLens a um computador para copiar a data [desabilitar USB.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Se você não quiser desabilitar USB, mas quiser a capacidade de aplicar um pacote de provisionamento ao dispositivo usando USB, siga as instruções [**listadas aqui.**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Use [o WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) para permitir ou preto aplicativos no dispositivo HoloLens 2.
1. Atualize a Assistência Remota para a versão mais recente como parte da configuração. Há duas opções para fazer isso:
    1. Isso pode ser feito indo para a **Windows Microsoft Store --> Assistência**Remota --> e Atualizar aplicativo .
    1. Outro método é deixar o HoloLens 2 conectado durante a noite para atualização automática.
1. [Desabilite todas as páginas de configurações,](https://docs.microsoft.com/hololens/settings-uri-list) exceto as configurações de rede, para permitir que os usuários se conectem a redes convidadas em sites cliente.
1. [Gerenciar Atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Opção para [controlar as atualizações do sistema operacional](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) ou permitir o fluxo livre.
1. [Restrições comuns de dispositivo.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)
