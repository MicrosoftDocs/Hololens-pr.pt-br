---
title: Guia de implantação – o HoloLens conectado corporativo 2 com guias do Dynamics 365-preparar
description: Saiba como se preparar para registrar dispositivos do HoloLens 2 em uma rede conectada corporativa com os guias do Dynamics 365.
keywords: HoloLens, gerenciamento, corporativo conectado, guias do Dynamics 365, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308136"
---
# <a name="prepare---corporate-connected-guide"></a>Preparar – guia conectado corporativo
## <a name="infrastructure-essentials"></a>Conceitos básicos de infraestrutura
Para cenários de implantação pessoal e corporativo, um sistema de MDM (gerenciamento de dispositivo móvel) é a infraestrutura essencial necessária para implantar e gerenciar dispositivos Windows 10, especialmente o HoloLens 2. Uma [assinatura Azure ad Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) é recomendada como um provedor de identidade e **necessária** para dar suporte a determinados recursos.

> [!NOTE]
> Embora o HoloLens 2 seja implantado e gerenciado como um dispositivo móvel, ele geralmente é usado como um dispositivo compartilhado entre muitos usuários.

## <a name="azure-active-directory"></a>Azure Active Directory
O Azure AD é um serviço de diretório baseado em nuvem que fornece gerenciamento de identidade e acesso. As organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: gratuita, Premium P1 e Premium P2 (consulte [Azure Active Directory Editions](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Todas as edições dão suporte ao registro de dispositivos do Azure AD, mas o Premium P1 é necessário para habilitar o registro automático de MDM que usaremos neste guia posteriormente.
> [!Important]
> É essencial ter um Azure AD como dispositivos HoloLens não dão suporte a ingresso no AD local. Se você ainda não tiver uma configuração do Azure AD, siga as instruções para começar e [criar um novo locatário no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gerenciamento de Identidades
Neste guia, a [identidade](https://docs.microsoft.com/hololens/hololens-identity) usada será contas do Azure AD. Há vários benefícios para as contas do Azure AD, como:
- Os funcionários usam sua conta do Azure AD para registrar o dispositivo no Azure AD e podem registrá-lo automaticamente com a solução de MDM da organização (Azure AD + MDM – requer uma [assinatura Azure ad Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)).
- As contas do Azure AD têm [Opções de autenticação](https://docs.microsoft.com/hololens/hololens-identity) adicionais por meio [do Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Além do logon de íris, os usuários podem entrar de outro dispositivo ou usar chaves de segurança FIDO.

> [!WARNING] 
> Os funcionários podem usar apenas uma conta para inicializar um dispositivo para que seja **imperativo que sua organização controle qual conta está habilitada primeiro**. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento.

## <a name="mobile-device-management"></a>Gerenciamento do Dispositivo Móvel
Microsoft Intune, parte do Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos conectados ao seu locatário. Como o Office 365, o Intune usa o Azure AD para gerenciamento de identidades, de modo que os funcionários usam as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. O Intune também dá suporte a dispositivos que executam outros sistemas operacionais, como iOS e Android, para fornecer uma solução completa de MDM. Para os fins deste guia, vamos nos concentrar em usar o Intune para habilitar uma implantação em sua rede interna com o HoloLens 2.
> [!Important] 
> É essencial ter o gerenciamento de dispositivos móveis. Se você ainda não tiver configurado, siga este guia e comece a usar o Intune.

> [!Important]
> Para usar guias, é necessária uma conta do Azure AD.

> [!Note] 
> Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os provedores de MDM que dão suporte ao Windows 10 Holographic incluem: monitor de relógio, MobileIron e outros. A maioria dos fornecedores de MDM líderes do setor já dão suporte à integração com o Azure AD. Você pode encontrar a lista mais atual de fornecedores de MDM que dão suporte ao Azure AD no [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Acesso de rede 
Os guias do Dynamics 365 são um aplicativo baseado em nuvem. Se o administrador de rede tiver uma lista de aprovados, talvez seja necessário adicionar endereços IP e/ou pontos de extremidade que são necessários para se conectar aos servidores Dynamics 365. [Saiba mais sobre o desbloqueio de URLs e endereços IP](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>Certificados
Os certificados ajudam a melhorar a segurança fornecendo autenticação de conta, Wi-Fi autenticação, criptografia de VPN e criptografia SSL do conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento, é uma prática recomendada usar seu sistema MDM para gerenciar esses certificados em todo o ciclo de vida – do registro por meio de renovação e revogação. 

O sistema MDM pode implantar automaticamente esses certificados nos repositórios de certificados dos dispositivos depois de registrá-los (desde que o seu sistema MDM ofereça suporte a **protocolo SCEP (SCEP)** ou **padrões de criptografia de chave pública #12 (PKCS # 12)**). [Saiba mais sobre os tipos de certificado e perfis que você usa com o Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure). O MDM também pode consultar e excluir certificados de cliente registrados ou disparar uma nova solicitação de registro antes que o certificado atual expire.
 
Se os sistemas MDM já estiverem configurados para certificados, referência [preparar certificados e perfis de rede para o HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) para iniciar a implantação de certificados e perfis para seus dispositivos de HoloLens 2.

## <a name="scep"></a>SCEP

Os serviços a seguir são necessários para a implantação do SCEP, com exceção do servidor proxy de aplicativo Web.
- [Autoridade de certificação](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Função de servidor de NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Conector do Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Você também deve publicar a URL de NDES externamente em sua rede corporativa usando o [proxy de aplicativo do Azure ad ou o proxy de acesso via Web](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application). Você também pode usar outro proxy reverso que preferir.

![Fluxo de dados SCEP](./images/hololens2-scep-info-flow.png)

Se sua rede ainda não oferecer suporte a SCEP ou se você não tiver certeza se sua rede está configurada corretamente para o SCEP com o Intune, consulte  [Configurar a infraestrutura para dar suporte ao SCEP com o Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure).

Se sua infraestrutura já oferece suporte a SCEP, você precisará [criar](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) um [perfil](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) para cada certificado SCEP que o HoloLens 2 usará. Se você estiver tendo problemas com o SCEP, use [a solução de problemas de uso de perfis de certificado SCEP para provisionar certificados com Microsoft Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
O Intune também dá suporte ao uso de certificados PKCS e privados (par de chaves públicas). Referência [Use certificados de chave pública e privada no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) para obter mais informações.

## <a name="proxy"></a>Proxy
A maioria das redes de intranet corporativas aproveita um proxy para gerenciar o tráfego externo. Com o HoloLens 2, você pode configurar um servidor proxy para conexões Ethernet, Wi-Fi e VPN.

Há alguns tipos diferentes de proxy e maneiras de configurar o proxy. Para os fins deste guia, estamos optando por escolher o **proxy Wi-Fi, definir por meio da URL de PAC e implantado por meio do MDM**. Isso vem com as vantagens de ser implantado via MDM automaticamente, sendo capaz de atualizar o arquivo PAC em vez de usar uma configuração de servidor: porta e, por fim, usar Wi-Fi proxy para configurar o proxy para se aplicar somente a uma única conexão de Wi-Fi, permitindo que os dispositivos sejam usados ainda se estiverem conectados em outro local. 


Para obter mais detalhes sobre as configurações de proxy para o Windows 10, consulte [criar um perfil de Wi-Fi para dispositivos no Microsoft Intune-Azure](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Aplicativos de linha de negócios 
Embora vários aplicativos possam ser instalados por meio do Microsoft Store, é provável que você tenha seu próprio aplicativo personalizado criado especificamente para uso em realidade misturada. Esses aplicativos personalizados distribuídos em toda a sua empresa para sua empresa são chamados de aplicativos LOB (linha de negócios).
  
Há várias maneiras de implantar aplicativos em dispositivos do HoloLens 2. Os aplicativos podem ser implantados diretamente por meio do MDM, o Microsoft Store for Business (MSfB) ou o Sideload por meio de um pacote de provisionamento. Para este guia, implantaremos aplicativos por meio do MDM, por meio do uso da instalação do aplicativo necessário. Isso permitirá que seus aplicativos LOB sejam baixados automaticamente para seus dispositivos de HoloLens quando o registro for concluído.

Para aqueles que não têm seu próprio LOB, forneceremos um aplicativo de exemplo para testar esse fluxo de implantação. Este aplicativo será o aplicativo de [exemplos MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) e já foi predefinido e empacotado para testar a prova de conceito.
 
Mais detalhes sobre a implantação de aplicativo podem ser encontrados em [Gerenciamento de aplicativos: visão geral](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> O HoloLens 2 dá suporte somente à execução de aplicativos UWP ARM64.

## <a name="guides-playbook"></a>Guia estratégico
Os guias usam um ambiente do Microsoft dataverso como o repositório de armazenamento para seus aplicativos de guias. É importante entender a visão mais ampla de como seu ambiente de dataverso interage com seus aplicativos de guias e seu locatário. Não abordaremos como gerenciar seu dataverso neste guia, mas examine os [conceitos básicos para implantar guias do dynamics 365-realidade misturada do dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa-configurar](hololens2-corp-connected-configure.md)