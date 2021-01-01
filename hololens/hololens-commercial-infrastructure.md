---
title: Diretrizes de Infraestrutura para o HoloLens
description: Diretrizes de Infraestrutura para dispositivos HoloLens
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
ms.openlocfilehash: a67aaa5df4c74531b5bed88abaa266b00de5c406
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253158"
---
# Configurar Sua Rede para o HoloLens

Essa parte do documento exigirá as seguintes pessoas:

1. Administrador de Rede com permissões para fazer alterações no proxy/firewall
2. Administrador do Azure Active Directory
3. Administrador de Gerenciador de Dispositivos Móveis

## Requisitos de Infraestrutura

Em essência, o HoloLens é um dispositivo móvel do Windows integrado ao Azure.  Funciona melhor em ambientes comerciais com disponibilidade de rede sem fio (Wi-Fi) e acesso aos serviços da Microsoft.

Os serviços de nuvem essenciais incluem:

- Active Directory do Azure (Microsoft Azure Active Directory)
- Windows Update (WU)

Os clientes comerciais precisarão da infraestrutura de EMM (gerenciamento de mobilidade corporativa) ou de MDM (gerenciamento de dispositivo móvel) para gerenciar os dispositivos HoloLens em escala.  Este guia usa o [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como exemplo, embora qualquer provedor com suporte completo à Política da Microsoft dão suporte ao HoloLens.  Pergunte ao seu provedor de gerenciamento de dispositivo móvel se eles dão suporte ao HoloLens 2.

O HoloLens é compatível com um conjunto limitado de experiências desconectadas na nuvem.

### Suporte a redes sem fio EAP

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- CHAP TTLS
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### Requisitos de Rede Específicos do HoloLens

Certifique-se de que [essa lista](hololens-offline.md)de pontos de extremidade são permitidas no firewall da sua rede. Isso permitirá que o HoloLens funcione corretamente.

### Requisitos de Rede Específicos da Assistência Remota

1. A largura de banda recomendada para o desempenho ideal da Assistência Remota é de 1.5 Mbps. Os requisitos de rede detalhados e informações adicionais podem ser encontrados [aqui](https://docs.microsoft.com/MicrosoftTeams/prepare-network).
**(Observe que, caso não haja velocidades de rede de pelo menos 1.5 Mbps, a Assistência Remota continuará funcionando. No entanto, a qualidade pode ser afetada).**
1. Verifique se essas portas e URLs são permitidas no firewall da sua rede. Isso permitirá que o Microsoft Teams funcione. A lista mais recente pode ser encontrada [aqui](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Saiba mais, especificamente, sobre os [Requisitos de Rede para Assistência Remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Saiba mais sobre como [preparar a rede da sua organização para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### Guias dos Requisitos de Rede Específicos

As guias só exigem o acesso à rede para baixar e usar o aplicativo.

## Diretrizes do Azure Active Directory

> [!NOTE]
> Essa etapa só será necessária se a sua empresa planeja gerenciar os aplicativos do HoloLens.

1. Verifique se você tem uma licença do Azure AD.
Confira [Requisitos de Licenças do HoloLens](hololens-licenses-requirements.md) para obter mais informações.

1. Se planeja usar o Registro Automático, será necessário [Configurar o registro do Azure AD](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment).

1. Verifique se os usuários da sua empresa estão no Azure Active Directory (Azure AD).
Instruções para adicionar usuários podem ser encontradas [aqui](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).

1. Sugerimos que os usuários que precisarem de licenças similares sejam adicionados a um mesmo grupo.
    1. [Criar um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Adicionar usuários a grupos](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Verifique se os usuários da sua empresa (ou grupo de usuários) têm as licenças necessárias.
As instruções para atribuir licenças podem ser encontradas [aqui](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

1. Execute esta etapa apenas se espera que os usuários registrem seus dispositivos HoloLens/Dispositivo móvel (existem três opções). Estas etapas garantem que os usuários da empresa (ou um grupo de usuários) possam adicionar dispositivos.
    1. **Opção 1:** Conceda a todos os usuários permissão para adicionar dispositivos ao Azure AD.
Entrar no portal do Azure como um administradorAzure Active DirectoryDispositivosConfigurações de Dispositivo**Configurar Usuários para adicionar dispositivos ao Azure AD em Todos******

    1. **Opção 2:** Conceder permissão aos usuários/grupos selecionados para adicionar dispositivos ao Azure AD **Entrar no portal do Azure como administrador** > **Azure Active Directory** > **Dispositivos** > ** Configurações de Dispositivos** >
**Configurar usuários para adicionar dispositivos ao Azure AD para *Selecionar***
![ Imagem que mostra a Configuração dos Dispositivos Adicionados ao Azure AD](images/azure-ad-image.png)

    1. **Opção 3:** Você pode impedir que todos os usuários ingressem em seus dispositivos no domínio. Isso significa que todos os dispositivos precisarão ser registrados manualmente.

## Diretrizes do Administrador de Gerenciador de Dispositivos Móveis

### Gerenciamento contínuo de dispositivos 

> [!NOTE]
> Essa etapa só será necessária se a sua empresa planeja gerenciar o HoloLens.

O gerenciamento contínuo de dispositivos dependerá da infraestrutura de gerenciamento de dispositivo móvel.  A maioria tem a mesma funcionalidade geral, mas a interface do usuário pode variar muito.

1. Os [CSPs (Provedores de Serviços de Configuração)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) permitem criar e implantar as configurações de gerenciamento para os dispositivos em sua rede. É possível encontrar uma lista de CSPs para o HoloLens [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).

1. [Políticas de conformidade](https://docs.microsoft.com/intune/device-compliance-get-started) são regras e configurações que os dispositivos devem atender para serem compatíveis com a sua infraestrutura corporativa. Use essas políticas com Acesso Condicional para bloquear o acesso a recursos da empresa por dispositivos que não são compatíveis. Por exemplo, você pode criar uma política que requer que o Bitlocker esteja ativado.

1. [Criar Política de Conformidade](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).

1. O Acesso Condicional permite/nega que aplicativos e dispositivos móveis acessem recursos da empresa. Os dois documentos que você pode achar úteis são [Planejar a Implantação da AC](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) e [Práticas Recomendadas](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

1. [Este artigo](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) explicar sobre as ferramentas de gerenciamento do Intune para o HoloLens.

1. [Criar um perfil de dispositivo](https://docs.microsoft.com/intune/configuration/device-profile-create)

### Gerenciar atualizações

O Intune inclui um recurso chamado Anéis de atualização para dispositivos Windows 10, incluindo o HoloLens 2 e o HoloLens v1 (com o Holographic for Business). Os Anéis de atualização incluem um grupo de configurações que determinam como e quando as atualizações serão instaladas.

Por exemplo, você pode criar uma janela de manutenção para instalar atualizações ou optar por reiniciar após atualizar.  Também é possível optar por pausar atualizações indefinidamente até estar pronto para atualizar.

Leia mais sobre [configurar anéis de atualização com o Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### Gerenciamento de aplicativo

Gerenciar aplicativos do HoloLens através de:

1. Microsoft Store  
  A Microsoft Store é a melhor maneira de distribuir e usar aplicativos no HoloLens.  Já existe um ótimo conjunto de aplicativos principais do HoloLens disponíveis na loja ou você pode [publicar seus próprios](https://docs.microsoft.com/windows/uwp/publish/).  
  Todos os aplicativos na loja estão disponíveis publicamente, mas se não for aceitável, finalize a compra na Microsoft Store para Empresas.  

1. [Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/)  
  A Microsoft Store para Empresas e Educação é um armazenamento personalizado para ambiente corporativo.  Permite o uso da Microsoft Store no Windows 10 e no HoloLens para encontrar, adquirir, distribuir e gerenciar aplicativos para sua organização.  Também permite implantar aplicativos específicos para ambiente comercial, mas não global.

1. Implantação e gerenciamento de aplicativos via Intune ou outra solução de gerenciamento de dispositivo móvel  
  A maioria das soluções de gerenciamento de dispositivo móvel, incluindo o Intune, oferece uma maneira de implantar aplicativos de linha de negócios diretamente em um conjunto de dispositivos registrados.  Confira este artigo sobre [instalação de aplicativos do Intune](https://docs.microsoft.com/intune/apps-deploy).

1. Portal de Dispositivos _não recomendado_  
  Os aplicativos também podem ser instalados no HoloLens diretamente usando o Portal de Dispositivos do Windows.  Isso não é recomendado, pois o Modo de Desenvolvedor deve estar ativado para usar o portal do dispositivo.

Leia mais sobre [instalação de aplicativos no HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### Certificados

Você pode distribuir certificados através do provedor de MDM. O Intune dá suporte a PKCS, PFX e SCEP, caso sua empresa exija certificados. É importante entender qual certificado é adequado para sua empresa. Visite [aqui](https://docs.microsoft.com/intune/protect/certificates-configure) para determinar o certificado ideal para você. Se você planeja usar certificados para Autenticação do HoloLens, o PFX ou SCEP talvez sejam adequados para você.

As etapas para o SCEP podem ser encontradas [aqui](https://docs.microsoft.com/intune/protect/certificates-profile-scep).

### Como Atualizar para o Pacote Comercial do Holographics for Business

> [!NOTE]
> O Holographics for Business (pacote comercial) do Windows destina-se apenas a dispositivos da 1ª geração do HoloLens. O perfil não será aplicado a dispositivos do HoloLens 2.

As instruções de como atualizar para o pacote comercial podem ser encontradas [aqui](https://docs.microsoft.com/intune/configuration/holographic-upgrade).

### Como Configurar o Modo de Quiosque usando o Microsoft Intune.

1. Sincronizar a Microsoft Store com o Intune ([Aqui](https://docs.microsoft.com/intune/apps/windows-store-for-business)).

1. Verificar as configurações do aplicativo
    1. Entrar na sua conta da Microsoft Store para Empresas
    1. **Gerenciar > Produtos e Serviços> Aplicativos e Software > Select o aplicativo que você deseja sincronizar > Disponibilidade de Repositório Particular > Selecionar “Todos” ou “Grupos Específicos”**
        >[!NOTE]
        >Se você não vir o aplicativo desejado, será necessário "obter" o aplicativo pesquisando a loja do seu aplicativo. **clique na barra "Pesquisar" no canto superior direito > digite o nome do aplicativo > clique no aplicativo > selecione "Obter"**.
    1. Caso não veja seus aplicativos no **Intune > Aplicativos cliente > Aplicativos** , talvez seja preciso [sincronizar seus aplicativos](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) novamente.

1. [Criar um perfil de dispositivo para o Modo de quiosque](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Você pode configurar diferentes usuários para ter diferentes experiências de Modo de Quiosque usando o "Azure AD" como "Tipo de logon do usuário". No entanto, esta opção está disponível apenas no modo de quiosque para Vários Aplicativos. O modo de quiosque para vários aplicativos funcionará com apenas um aplicativo, bem como com vários aplicativos.

![Imagem que mostra a Configuração do Modo de Quiosque no Intune](images/aad-kioskmode.png)

Para outros serviços MDM, verifique a documentação do seu provedor para obter instruções. Caso precise usar uma configuração personalizada e uma configuração XML completa para instalar um quiosque no seu serviço MDM, instruções adicionais podem ser encontradas [aqui](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

## Certificados e Autenticação

Os certificados podem ser implantados via MDM (confira "certificados" na [Seção MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Os certificados também podem ser implantados no HoloLens por meio do provisionamento de pacotes. Confira [Provisionamento do HoloLens](hololens-provisioning.md) para obter mais informações.

### Links Rápidos Adicionais do Intune

1. [Criar perfis:](https://docs.microsoft.com/intune/configuration/device-profile-create) os perfis permitem que você adicione e defina as configurações que serão transferidas para os dispositivos em sua organização.

