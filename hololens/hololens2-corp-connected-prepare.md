---
title: Guia de Implantação – HoloLens 2 conectado corporativo com Guias do Dynamics 365 - Preparar
description: Saiba como se preparar para registrar dispositivos do HoloLens 2 em uma rede conectada corporativa com guias do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448499"
---
# <a name="prepare---corporate-connected-guide"></a>Preparar - Guia conectado corporativo
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Para cenários de implantação pessoal e corporativa, um sistema de Gerenciamento de Dispositivo Móvel (MDM) é a infraestrutura essencial necessária para implantar e gerenciar dispositivos Windows 10, especialmente o HoloLens 2. Uma [assinatura do Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) é recomendada como um provedor de identidade e necessária para dar suporte a determinados recursos. ****

> [!NOTE]
> Embora o HoloLens 2 seja implantado e gerenciado como um dispositivo móvel, ele geralmente é usado como um dispositivo compartilhado entre muitos usuários.

## <a name="azure-active-directory"></a>Azure Active Directory
O Azure AD é um serviço de diretório baseado na nuvem que fornece gerenciamento de acesso e identidade. As organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: Free, Premium P1 e Premium P2 (consulte edições do [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Todas as edições suportam o registro de dispositivos do Azure AD, mas o Premium P1 é necessário para habilitar o registro automático do MDM que vamos usar neste guia posteriormente.
> [!Important]
> É essencial ter um Azure AD, pois os dispositivos do HoloLens não suportam a entrada no AD local. Se você ainda não tiver uma configuração do Azure AD, siga as instruções para começar e Crie um novo locatário [no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Gerenciamento de identidade
Neste guia, a [Identidade](https://docs.microsoft.com/hololens/hololens-identity) usada será contas do Azure AD. Há vários benefícios para contas do Azure AD, como:
- Os funcionários usam sua conta do Azure AD para registrar o dispositivo no Azure AD e podem registrá-lo automaticamente na solução MDM da organização (Azure AD+MDM – exige uma assinatura [do Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)).
- As contas do Azure AD têm opções de [autenticação adicionais](https://docs.microsoft.com/hololens/hololens-identity) por meio [do Windows Hello para Empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Além do logo-in Iris, os usuários podem entrar de outro dispositivo ou usar chaves de segurança FIDO.

> [!WARNING] 
> Os funcionários podem usar apenas uma conta para inicializar um dispositivo, portanto, é imperativo que sua organização controle qual conta **está habilitada primeiro**. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento.

## <a name="mobile-device-management"></a>Gerenciamento de Dispositivo Móvel
O Microsoft Intune, parte do Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos conectados ao locatário. Assim como o Office 365, o Intune usa o Azure AD para gerenciamento de identidade, para que os funcionários usem as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. O Intune também oferece suporte a dispositivos que executem outros sistemas operacionais, como iOS e Android, para fornecer uma solução MDM completa. Para os fins deste guia, vamos nos concentrar em usar o Intune para habilbilizar uma implantação para sua rede interna com o HoloLens 2.
> [!Important] 
> É essencial ter o Gerenciamento de Dispositivo Móvel. Se você ainda não tiver a configuração, siga este guia e Começar com o Intune.

> [!Important]
> Para usar Guias, uma conta do Azure AD é necessária.

> [!Note] 
> Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os provedores MDM que suportam o Windows 10 Holographic incluem: AirWatch, MobileIron e outros. A maioria dos fornecedores de MDM líderes do setor já dão suporte à integração com o Azure AD. Você pode encontrar a lista mais atual de fornecedores MDM que suportam o Azure AD no [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Acesso à Rede 
Guias do Dynamics 365 é um aplicativo baseado em nuvem. Se o administrador de rede tiver uma lista de aprovação, talvez seja necessário adicionar endereços IP e/ou pontos de extremidade necessários para se conectar aos servidores do Dynamics 365. [Saiba mais sobre como desbloquear endereços IP e URLs](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>Certificados
Os certificados ajudam a melhorar a segurança fornecendo autenticação de conta, Wi-Fi autenticação, criptografia VPN e criptografia SSL do conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento, é uma prática prática usar seu sistema MDM para gerenciar esses certificados durante todo o ciclo de vida , desde o registro até a renovação e revogação. 

Seu sistema MDM pode implantar automaticamente esses certificados nos armazenamentos de certificados dos dispositivos depois que você os registra (contanto que seu sistema MDM suporte o **ScEP (Simple Certificate Enrollment Protocol)** ou **Public Key Cryptography Standards #12 (PKCS#12)**). [Saiba mais sobre tipos de certificados e perfis que você usa com o Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure). O MDM também pode consultar e excluir certificados de cliente inscritos ou disparar uma nova solicitação de registro antes que o certificado atual seja expirado.
 
Se seus sistemas MDM já estão configurados para certificados, consulte Preparar certificados e perfis de rede para [o HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) para começar a implantar certificados e perfis para seus dispositivos HoloLens 2.

## <a name="scep"></a>SCEP

Os seguintes serviços são necessários para a implantação do SCEP, com exceção do Servidor Proxy de Aplicativo Web.
- [Autoridade de Certificação](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Função de servidor NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Connector](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Você também deve publicar sua URL do NDES externa à sua rede corporativa usando o proxy de aplicativo [do Azure AD ou](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)o Proxy de Acesso à Web. Você também pode usar outro proxy reverso de sua escolha.

![Fluxo de dados SCEP](./images/hololens2-scep-info-flow.png)

Se sua rede ainda não tiver suporte para SCEP ou você não tiver certeza se sua rede está configurada corretamente para SCEP com o Intune, faça referência Configurar infraestrutura para dar suporte ao SCEP com  [o Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure).

Se sua infraestrutura já for compatível [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) com [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) SCEP, você precisará criar um perfil para cada certificado SCEP que o HoloLens 2 usará. Se você estiver tendo problemas com SCEP, use Solucionar problemas de uso de perfis de certificado SCEP para provisionar [certificados com o Microsoft Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
O Intune também dá suporte ao uso de certificados PKCS (par de chaves públicas e privadas). Referência [Use certificados de chave pública e privada no Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) para obter mais informações.

## <a name="proxy"></a>Proxy
A maioria das redes de intranet corporativas utiliza um proxy para gerenciar o tráfego externo. Com o HoloLens 2, você pode configurar um servidor proxy para conexões ethernet, Wi-Fi VPN e ethernet.

Há alguns tipos diferentes de proxy e maneiras de configurar o proxy. Para os fins deste guia, estamos optando por escolher **proxy Wi-Fi,** definido por meio de URL do PAC e implantado por meio do MDM . Isso vem com as vantagens de ser implantado automaticamente por meio do MDM, poder atualizar o arquivo PAC em vez de usar uma configuração de servidor:porta e, finalmente, usar o proxy do Wi-Fi para configurar o proxy para aplicar somente a uma única conexão Wi-Fi permitindo que os dispositivos sejam usados ainda se conectados em outro local. 


Para obter mais detalhes sobre configurações de proxy para Windows 10, consulte [Create a Wi-Fi profile for devices in Microsoft Intune - Azure](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Aplicativos de Linha de Negócios 
Embora vários aplicativos possam ser instalados por meio da Microsoft Store, é provável que você tenha seu próprio aplicativo personalizado criado especificamente para usar na realidade misturada. Esses aplicativos personalizados distribuídos por toda a sua organização para sua empresa são chamados de aplicativos de Linha de Negócios (LOB).
  
Há várias maneiras de implantar aplicativos em dispositivos HoloLens 2. Os aplicativos podem ser implantados diretamente por meio do MDM, da Microsoft Store para Empresas(MSfB) ou sideload por meio de um Pacote de Provisionamento. Para o bem deste guia, vamos implantar aplicativos por meio do MDM, por meio do uso da instalação necessária do aplicativo. Isso permitirá que seus aplicativos LOB sejam baixados automaticamente para seus dispositivos HoloLens quando terminarem o registro.

Para aqueles que não têm seu próprio LOB, forneceremos um aplicativo de exemplo para testar esse fluxo de implantação. Este aplicativo será o [aplicativo Exemplos MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) e já foi pré-construído e empacotado para testar a prova de conceito.
 
Mais detalhes sobre a implantação do aplicativo podem ser encontrados em [Gerenciamento de Aplicativos: Visão geral](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> O HoloLens 2 dá suporte à execução apenas de aplicativos ARM64 UWP.

## <a name="guides-playbook"></a>Manual de Guias
Os guias usam um ambiente do Microsoft Dataverse como o datastore para seus aplicativos Guias. É importante entender a imagem maior de como seu ambiente dataverso interage com seus aplicativos guias e seu locatário. Não vamos abranger como gerenciar seu dataverse neste guia, mas revise conceitos básicos para implantar guias do [Dynamics 365 - Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Próximas etapas 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa - Configurar](hololens2-corp-connected-configure.md)