---
title: Guia de implantação – Guia de implantação HoloLens 2 com Guias do Dynamics 365 – Preparar
description: Saiba como se preparar para registrar HoloLens 2 dispositivos em uma rede conectada corporativa com guias do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Mobile Gerenciamento de Dispositivos
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
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190201"
---
# <a name="prepare---corporate-connected-guide"></a>Preparar – Guia conectado corporativo
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Para cenários de implantação pessoal e corporativa, um sistema MDM (Mobile Gerenciamento de Dispositivos) é a infraestrutura essencial necessária para implantar e gerenciar dispositivos Windows 10, especialmente o HoloLens 2. Uma [Azure AD Premium assinatura é](/azure/active-directory/fundamentals/active-directory-get-started-premium) recomendada como um provedor de identidade e **necessária** para dar suporte a determinadas funcionalidades.

> [!NOTE]
> Embora o HoloLens 2 seja implantado e gerenciado como um dispositivo móvel, ele geralmente é usado como um dispositivo compartilhado entre muitos usuários.

## <a name="azure-active-directory"></a>Azure Active Directory
O Azure AD é um serviço de diretório baseado em nuvem que fornece gerenciamento de identidade e acesso. As organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: Gratuita, Premium P1 e Premium P2 (consulte [Azure Active Directory edições](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Todas as edições são suportadas pelo registro de dispositivo do Azure AD, mas Premium P1 é necessário para habilitar o registro automático do MDM, que será usado neste guia posteriormente.
> [!Important]
> É essencial ter um Azure AD, pois HoloLens dispositivos não são compatíveis com a junção do AD local. Se você ainda não tiver uma configuração do Azure AD, siga as instruções para começar e Criar um novo locatário [no Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gerenciamento de Identidades
Neste guia, a [Identidade usada](/hololens/hololens-identity) será contas do Azure AD. Há vários benefícios para contas do Azure AD, como:

- Os funcionários usam sua conta do Azure AD para registrar o dispositivo no Azure AD e podem registrá-lo automaticamente na solução de MDM da organização (Azure AD+MDM – requer uma assinatura [Azure AD Premium](/azure/active-directory/fundamentals/active-directory-get-started-premium)).
- As contas do Azure AD têm opções de [autenticação adicionais](/hololens/hololens-identity) [por meio do Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Além do logoff do Iris, os usuários podem entrar de outro dispositivo ou usar chaves de segurança FIDO.

> [!WARNING] 
> Os funcionários podem usar apenas uma conta para inicializar um dispositivo, portanto, é imperativo que sua organização controle qual **conta está habilitada primeiro.** A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento.

## <a name="mobile-device-management"></a>Gerenciamento do Dispositivo Móvel
Microsoft Intune, parte do Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos conectados ao seu locatário. Assim como Office 365, o Intune usa o Azure AD para gerenciamento de identidades, portanto, os funcionários usam as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. O Intune também dá suporte a dispositivos que executem outros sistemas operacionais, como iOS e Android, para fornecer uma solução de MDM completa. Para os fins deste guia, nos concentraremos em usar o Intune para habilbilizar uma implantação em sua rede interna com HoloLens 2.
> [!Important] 
> É essencial ter dispositivos móveis Gerenciamento de Dispositivos. Se você ainda não o tiver definido, siga este guia e Começar a trabalhar com o Intune.

> [!Important]
> Para usar o Guides, uma conta do Azure AD é necessária.

> [!Note] 
> Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os provedores de MDM que Windows 10 Holographic incluem: AirWatch, MobileIron e outros. A maioria dos fornecedores de MDM líderes do setor já dão suporte à integração com o Azure AD. Você pode encontrar a lista mais atual de fornecedores de MDM que suportam o Azure AD [no Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Acesso de rede 
O Dynamics 365 Guides é um aplicativo baseado em nuvem. Se o administrador de rede tiver uma lista de aprovação, talvez seja necessário adicionar endereços IP e/ou pontos de extremidade necessários para se conectar aos servidores do Dynamics 365. [Saiba mais sobre como desbloquear endereços IP e URLs.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certificados
Os certificados ajudam a melhorar a segurança fornecendo autenticação de conta, Wi-Fi autenticação, criptografia VPN e criptografia SSL do conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento, é uma melhor prática usar seu sistema de MDM para gerenciar esses certificados em todo o ciclo de vida , desde o registro até a renovação e revogação. 

O sistema MDM pode implantar automaticamente esses certificados nos armazenamentos de certificados dos dispositivos depois que você os registra (desde que o sistema MDM seja compatível com o **SCEP (protocolo SCEP)** ou padrões de criptografia de chave **pública #12 (PKCS nº 12).** [Saiba mais sobre tipos de certificado e perfis que você usa com Microsoft Intune](/mem/intune/protect/certificates-configure). O MDM também pode consultar e excluir certificados de cliente inscritos ou disparar uma nova solicitação de registro antes que o certificado atual seja expirado.

Se os sistemas MDM já estão configurados para certificados, consulte Preparar certificados e perfis de rede para [o HoloLens 2 para](/hololens/hololens-certificates-network) começar a implantar certificados e perfis para seus dispositivos HoloLens 2.

## <a name="scep"></a>SCEP

Os serviços a seguir são necessários para a implantação do SCEP, com exceção do servidor de Proxy de Aplicativo Web.

- [Autoridade de Certificação](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Função de servidor NDES](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Conector](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Você também deve publicar a URL do NDES externa à sua rede corporativa usando o proxy de aplicativo do [Azure AD ou o proxy Acesso via Web .](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Você também pode usar outro proxy reverso que preferir.

![Fluxo de dados SCEP.](./images/hololens2-scep-info-flow.png)

Se sua rede ainda não dá suporte ao SCEP ou você não tem certeza se sua rede está configurada corretamente para SCEP com o Intune, consulte Configurar infraestrutura para dar suporte ao SCEP com [o Intune.](/mem/intune/protect/certificates-scep-configure)

Se sua infraestrutura já dá suporte [ao](/mem/intune/protect/certificates-profile-scep) [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) SCEP, você precisará criar um perfil para cada certificado SCEP que o HoloLens 2 usará. Se você estiver tendo problemas com o SCEP, use Solucionar problemas de uso de perfis de certificado SCEP para [provisionar certificados com Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
O Intune também dá suporte ao uso de certificados PKCS (par de chaves públicas e privadas). Referência [Use certificados de chave pública e privada Microsoft Intune](/mem/intune/protect/certificates-pfx-configure) para obter mais informações.

## <a name="proxy"></a>Proxy
A maioria das redes de intranet corporativas aproveita um proxy para gerenciar o tráfego externo. Com HoloLens 2, você pode configurar um servidor proxy para conexões ethernet, Wi-Fi VPN.

Há alguns tipos diferentes de proxy e maneiras de configurar o proxy. Para os fins deste guia, optamos por escolher o proxy Wi-Fi, definido por meio da URL do PAC e **implantado por meio do MDM.** Isso vem com as vantagens de ser implantado por meio do MDM automaticamente, poder atualizar o arquivo PAC em vez de usar uma configuração de servidor:porta e, por fim, usar o proxy do Wi-Fi para configurar o proxy para aplicar apenas a uma única conexão Wi-Fi, permitindo que os dispositivos sejam usados ainda se conectados em outro local.

Para obter mais detalhes sobre as configurações de proxy Windows 10, consulte Criar um perfil Wi-Fi para dispositivos [no Microsoft Intune – Azure](/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Aplicativos de linha de negócios 
Embora vários aplicativos possam ser instalados por meio do Microsoft Store, é provável que você tenha seu próprio aplicativo personalizado que você criou especificamente para usar na realidade misturada. Esses aplicativos personalizados distribuídos em toda a sua organização para seus negócios são chamados de aplicativos lob (linha de negócios).
  
Há várias maneiras de implantar aplicativos em HoloLens 2 dispositivos. Os aplicativos podem ser implantados diretamente por meio do MDM, Microsoft Store para Empresas (MSfB) ou sideload por meio de um pacote de provisionamento. Para este guia, implantaremos aplicativos por meio do MDM, por meio do uso da instalação necessária do aplicativo. Isso permitirá que seus aplicativos LOB sejam baixados automaticamente em seus dispositivos HoloLens depois que eles concluirem o registro.

Para aqueles que não têm seu próprio LOB, forneceremos um aplicativo de exemplo para testar esse fluxo de implantação. Esse aplicativo será o [aplicativo Exemplos do MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) e já foi pré-construído e empacotado para testar a prova de conceito.

Mais detalhes sobre a implantação do aplicativo podem ser encontrados em Gerenciamento [de Aplicativos: Visão geral.](/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 dá suporte apenas à execução de aplicativos ARM64 UWP.

## <a name="guides-playbook"></a>Guia de guias
Os guias usam um ambiente do Microsoft Dataverse como o armazenamento de dados para seus aplicativos guides. É importante entender o panorama geral de como seu ambiente do Dataverse interage com seus aplicativos Guides e seu locatário. Não vamos abranger como gerenciar seu dataverse neste guia, mas confira Conceitos básicos para implantar os Guias do [Dynamics 365 – Dynamics 365 Mixed Reality.](/dynamics365/mixed-reality/guides/admin-deployment-playbook)

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa – Configurar](hololens2-corp-connected-configure.md)