---
title: Diretrizes de infraestrutura para o HoloLens
description: Conheça as diretrizes de infraestrutura para dispositivos HoloLens, incluindo suporte de rede sem fio, assistência remota e gerenciamento de dispositivo móvel.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033978"
---
# <a name="configure-your-network-for-hololens"></a>Configurar sua rede para o HoloLens

Esta parte do documento exigirá as seguintes pessoas:

1. Administrador de rede com permissões para fazer alterações no proxy/no firewall
2. Administrador do Azure Active Directory
3. Administrador do Gerenciador de Dispositivo Móvel

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

Em essência, o HoloLens é um dispositivo móvel do Windows integrado ao Azure.  Ele funciona melhor em ambientes comerciais com disponibilidade de rede sem fio (Wi-Fi) e acesso aos serviços Microsoft.

Os serviços de nuvem críticos incluem:

- Azure AD (Azure Active Directory)
- WU (Windows Update)

Os clientes comerciais precisarão da infraestrutura do EMM (Enterprise Mobility Management) ou do MDM (gerenciamento de dispositivo móvel) para gerenciar os dispositivos HoloLens em escala.  Este guia usa o [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como exemplo, embora qualquer provedor com suporte completo à Política da Microsoft possa dar suporte ao HoloLens.  Pergunte ao seu provedor de gerenciamento de dispositivo móvel se ele dá suporte ao HoloLens 2.

O HoloLens dá suporte a um conjunto limitado de experiências desconectadas na nuvem.

### <a name="wireless-network-eap-support"></a>Suporte a EAP de rede sem fio

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- CHAP TTLS
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>Requisitos de rede específicos do HoloLens

Verifique se [esta lista](hololens-offline.md) de pontos de extremidade são permitidas no firewall da sua rede. Isso permitirá que o HoloLens funcione corretamente.

### <a name="remote-assist-specific-network-requirements"></a>Requisitos de rede específicos do Remote Assist

1. A largura de banda recomendada para obter o desempenho ideal do Remote Assist é de 1,5 Mbps. Confira os [requisitos de rede detalhados](/MicrosoftTeams/prepare-network) para obter mais informações.
**(Observe que, se você não tiver velocidades de rede de, no mínimo, 1,5 Mbps, o Remote Assist continuará funcionando. No entanto, poderá haver impacto na qualidade).**
1. Verifique se essas portas e as URLs são permitidas no firewall da rede para permitir que o Microsoft Teams funcione. Mantenha-se atualizado com a [lista mais recente de portas](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Saiba mais sobre os [requisitos de rede específicos do Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Saiba mais sobre como [preparar a rede da sua organização para o Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Guias dos requisitos de rede específicos

Os guias só exigem o acesso à rede para baixar e usar o aplicativo.

## <a name="azure-active-directory-guidance"></a>Diretrizes do Azure Active Directory

> [!NOTE]
> Essa etapa só é necessária se a sua empresa pretende gerenciar o HoloLens.

1. Verifique se você tem uma licença do Azure AD.
Confira [Requisitos de licença do HoloLens](hololens-licenses-requirements.md) para obter mais informações.

1. Se você pretender usar o registro automático, precisará [Configurar o registro do Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Verifique se os usuários da sua empresa estão no Azure AD (Azure Active Directory).
Confira as [instruções](/azure/active-directory/fundamentals/add-users-azure-active-directory) a seguir para adicionar usuários.

1. Sugerimos que os usuários que precisem de licenças similares sejam adicionados ao mesmo grupo.
    1. [Criar um grupo](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Adicionar usuários a grupos](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Verifique se os usuários da sua empresa (ou um grupo de usuários) receberam as licenças necessárias.
Se precisar atribuir licenças, siga estas [instruções](/azure/active-directory/fundamentals/license-users-groups).

1. Execute esta etapa apenas se você espera que os usuários registrem os respectivos dispositivos HoloLens/móveis (existem três opções). Essas etapas garantem que os usuários da sua empresa (ou um grupo de usuários) possam adicionar dispositivos.
    1. **Opção 1:** conceda a todos os usuários permissão para ingressar dispositivos no Azure AD.
**Entre no portal do Azure como administrador** > **Azure Active Directory** > **Dispositivos** > **Configurações do Dispositivo** >
**Defina a opção Os usuários podem ingressar no Azure AD com seus dispositivos como *Todos***

    1. **Opção 2:** conceda a permissão aos usuários/grupos selecionados para ingressar dispositivos no Azure AD **Entre no portal do Azure como administrador** > **Azure Active Directory** > **Dispositivos** > **Configurações do Dispositivo** >
**Defina Os usuários podem ingressar no Azure AD com seus dispositivos como *Selecionados***
![Imagem que mostra a configuração dos dispositivos ingressados no Azure AD.](images/azure-ad-image.png)

    1. **Opção 3:** você pode impedir que todos os usuários ingressem os respectivos dispositivos no domínio. Isso significa que todos os dispositivos precisarão ser registrados manualmente.

## <a name="mobile-device-manager-guidance"></a>Diretrizes do Gerenciador de Dispositivos Móveis

### <a name="ongoing-device-management"></a>Gerenciamento contínuo de dispositivos

> [!NOTE]
> Essa etapa só é necessária se a sua empresa pretende gerenciar o HoloLens.

O gerenciamento contínuo de dispositivos dependerá da sua infraestrutura de gerenciamento de dispositivo móvel.  A maioria tem a mesma funcionalidade geral, mas a interface do usuário pode variar muito.

1. Os [CSPs (provedores de serviço de configuração)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) permitem que você crie e implante configurações de gerenciamento para os dispositivos na sua rede. Confira a [lista de CSPs do HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) para obter uma referência.

1. As [políticas de conformidade](/intune/device-compliance-get-started) são regras e configurações às quais os dispositivos precisam atender para serem compatíveis com a sua infraestrutura corporativa. Use essas políticas com o acesso condicional para bloquear o acesso aos recursos da empresa em dispositivos que não estão em conformidade. Por exemplo, você pode criar uma política que exige que o BitLocker seja habilitado.

1. [Criar a política de conformidade](/intune/protect/compliance-policy-create-windows).

1. O acesso condicional permite/nega que aplicativos e dispositivos móveis acessem os recursos da empresa. Dois documentos que podem ser úteis são [Planejar sua implantação de AC](/azure/active-directory/conditional-access/plan-conditional-access) e [Melhores práticas](/azure/active-directory/conditional-access/best-practices).

1. [Este artigo](/intune/fundamentals/windows-holographic-for-business) descreve as ferramentas de gerenciamento do Intune para o HoloLens.

1. [Criar um perfil de dispositivo](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Gerenciar atualizações

O Intune inclui um recurso chamado Anéis de atualização para dispositivos Windows 10, incluindo o HoloLens 2 e o HoloLens v1 (com o Holographic for Business). Os Anéis de atualização incluem um grupo de configurações que determinam como e quando as atualizações serão instaladas.

Por exemplo, você pode criar uma janela de manutenção para instalar as atualizações ou optar por reiniciar depois que as atualizações forem instaladas.  Também é possível optar por pausar as atualizações por tempo indefinido até que você esteja pronto para fazer a atualização.

Leia mais sobre [como configurar anéis de atualização com o Intune](/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Gerenciamento de aplicativos

Gerencie os aplicativos do HoloLens por meio dos seguintes:

1. Microsoft Store  
  A Microsoft Store é a melhor maneira de distribuir e consumir aplicativos no HoloLens.  Já existe um ótimo conjunto de aplicativos básicos do HoloLens disponíveis na loja ou você pode [publicar os seus](/windows/uwp/publish/).  
  Todos os aplicativos da loja estão disponíveis publicamente para todos, mas se isso não for aceitável, confira a Microsoft Store para Empresas.  

1. [Microsoft Store para Empresas](/microsoft-store/)  
  A Microsoft Store para Empresas e Educação é um armazenamento personalizado para seu ambiente corporativo.  Ele permite que você use a Microsoft Store no Windows 10 e no HoloLens para encontrar, adquirir, distribuir e gerenciar aplicativos para sua organização.  Também permite implantar aplicativos específicos para seu ambiente comercial, mas não global.

1. Implantação e gerenciamento de aplicativos por meio do Intune ou de outra solução de gerenciamento de dispositivo móvel  
  A maioria das soluções de gerenciamento de dispositivo móvel, incluindo o Intune, oferece uma forma de implantar aplicativos de linha de negócios diretamente em um conjunto de dispositivos registrados.  Confira este artigo sobre a [instalação do aplicativo do Intune](/intune/apps-deploy).

1. _não recomendado_ Portal de Dispositivos  
  Os aplicativos também podem ser instalados no HoloLens diretamente por meio do Portal de Dispositivos do Windows.  Isso não é recomendado, pois o Modo de Desenvolvedor deve estar habilitado para uso do Portal de Dispositivos.

Leia mais sobre [como instalar aplicativos no HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certificados

Você pode distribuir certificados por meio do provedor de MDM. O Intune dá suporte ao PKCS, ao PFX e ao SCEP, caso sua empresa exija certificados. É importante entender qual certificado é ideal para sua empresa. Acesse a documentação de [configurações de certificado](/intune/protect/certificates-configure) para determinar qual certificado é melhor para você. Se você pretende usar certificados para Autenticação do HoloLens, o PFX ou o SCEP talvez seja adequado para você.

Confira as etapas a seguir de como usar o [SCEP](/intune/protect/certificates-profile-scep).

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Como fazer a atualização para o pacote comercial do Holographics for Business

> [!NOTE]
> O Windows Holographics for Business (pacote comercial) destina-se apenas aos dispositivos HoloLens da 1ª geração. O perfil não será aplicado aos dispositivos HoloLens 2.

Encontre instruções de atualização para o pacote comercial na documentação sobre a [atualização holográfica](/intune/configuration/holographic-upgrade).

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Como configurar o modo de quiosque usando o Microsoft Intune

1. Sincronize a Microsoft Store com o Intune (confira as [instruções](/intune/apps/windows-store-for-business) a seguir).

1. Verifique as configurações do aplicativo
    1. Entre na sua conta da Microsoft Store para Empresas
    1. **Gerenciar > Produtos e Serviços > Aplicativos e Software > Selecione o aplicativo que deseja sincronizar > Disponibilidade do Repositório Particular > Selecione "Todos" ou "Grupos Específicos"**
        >[!NOTE]
        >Se o aplicativo desejado não for exibido, você precisará "obter" o aplicativo pesquisando-o na loja. **Clique na barra "Pesquisar" no canto superior direito > digite o nome do aplicativo > clique no aplicativo > selecione "Obter"** .
    1. Caso os seus aplicativos não sejam exibidos em **Intune > Aplicativos Cliente > Aplicativos**, talvez seja necessário [sincronizar os aplicativos](/intune/apps/windows-store-for-business#synchronize-apps) novamente.

1. [Criar um perfil de dispositivo para o modo de quiosque](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Você pode configurar diferentes usuários para ter diferentes experiências do modo de quiosque usando o "Azure AD" como o "Tipo de logon do usuário". No entanto, esta opção só está disponível no modo de quiosque para Vários Aplicativos. O modo de quiosque para vários aplicativos funcionará com apenas um aplicativo, bem como com vários aplicativos.

![Imagem que mostra a configuração do Modo de Quiosque no Intune.](images/aad-kioskmode.png)

Para ver outros serviços de MDM, verifique a documentação do seu provedor para obter instruções. Veja as instruções do [quiosque do HoloLens](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) caso precise usar uma configuração personalizada e uma configuração XML completa para definir um quiosque no serviço de MDM.

## <a name="certificates-and-authentication"></a>Certificados e autenticação

Os certificados podem ser implantados por meio de MDM (confira "certificados" na [seção sobre o MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Eles também podem ser implantados no HoloLens por meio do provisionamento de pacotes. Confira [Provisionamento do HoloLens](hololens-provisioning.md) para obter mais informações.

### <a name="additional-intune-quick-links"></a>Links rápidos adicionais do Intune

1. [Criar perfis:](/intune/configuration/device-profile-create) os perfis permitem que você adicione e defina as configurações que serão enviadas por push para os dispositivos na sua organização.

