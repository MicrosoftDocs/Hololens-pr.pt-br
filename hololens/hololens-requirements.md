---
title: Configurar o HoloLens em um ambiente comercial
description: Saiba mais sobre como implantar e gerenciar o HoloLens em ambientes corporativos, incluindo infraestrutura, Azure Active Directory e gerenciamento de dispositivo móvel.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397217"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>Implantação e gerenciamento corporativos do HoloLens 2

Esta visão geral destina-se a ajudar os profissionais de ti a entender as considerações de implantação e gerenciamento de dispositivos Microsoft HoloLens 2 dentro da empresa.

O HoloLens 2 é executado no Windows 10 Holographic, que fornece às organizações tecnologias de gerenciamento de aplicativo e de dispositivo móvel robustas, flexíveis e integradas. O Windows 10 Holographic dá suporte ao gerenciamento de ciclo de vida de dispositivos de ponta a ponta para dar às empresas o controle sobre seus dispositivos, dados e aplicativos. O HoloLens 2 pode ser facilmente incorporado às práticas de ciclo de vida padrão, do registro de dispositivos, da configuração e do gerenciamento de aplicativos à manutenção e retirada usando uma solução abrangente de gerenciamento de dispositivos móveis.

## <a name="prepare"></a>Preparar

À medida que você se prepara para implantar o HoloLens 2 em seu ambiente corporativo corporativo, há várias considerações que devem ser examinadas e compreendidas à medida que você começar a planejar as implantações de escala do HoloLens 2.

### <a name="infrastructure-essentials"></a>Conceitos básicos de infraestrutura

Para o HoloLens 2 em um cenário de implantação empresarial corporativa, há alguns serviços de infraestrutura essenciais necessários para dar suporte ao conjunto completo de recursos. O HoloLens 2 foi criado com o [Gerenciamento moderno de dispositivos móveis](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) em mente para implantação e gerenciamento. Com o Azure AD Join + MDM como o principal meio de obter isso em uma força de mercado móvel cada vez maior. Os tópicos a seguir fornecem uma breve visão geral de cada componente de infraestrutura que deve ser considerado em seu planejamento de implantação para o HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
O Azure AD é um serviço de diretório baseado em nuvem que fornece gerenciamento de identidade e acesso. Você pode integrá-lo com diretórios locais existentes para criar uma solução de identidade híbrida. As organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: gratuita, Premium P1 e Premium P2 (consulte [Azure Active Directory Editions](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Todas as edições são suportadas pelo registro de dispositivo do Azure AD, mas o Premium P1 é necessário para habilitar o registro automático do MDM. O HoloLens 2 requer Azure Active Directory para habilitar a maioria dos recursos e funcionalidades de nível empresarial.

> [!NOTE]
> Não há suporte para Junção do Active Directory local no HoloLens 2.

### <a name="mobile-device-management"></a>Gerenciamento do Dispositivo Móvel
O HoloLens 2 foi projetado especificamente para ser gerenciado por sistemas MDM (mobile Gerenciamento de Dispositivos) em um ambiente empresarial. O Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), parte do Enterprise Mobility + Security, é um sistema de MDM baseado em nuvem que gerencia dispositivos na empresa. Assim como o Office 365, o Intune usa o Azure AD para gerenciamento de identidades, portanto, os funcionários usam as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os sistemas MDM também podem gerenciar implantações e atualizações de aplicativos para o HoloLens 2. Outros provedores de MDM que suportam o HoloLens 2 atualmente incluem: AirWatch, MobileIron e outros. Todos os fornecedores do sistema MDM têm acesso igual a CSP (provedores de serviços de configuração de gerenciamento de dispositivos) do Windows 10, dando às organizações de TI a liberdade de selecionar o sistema que melhor atende aos seus requisitos de gerenciamento, seja Microsoft Intune ou um produto MDM de terceiros.

> [!NOTE]
> Sistemas tradicionais de gerenciamento de computadores locais, como System Center Gerenciador de Configurações, não têm suporte no HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update for Business
A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações. Confira a [documentação de atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates) para obter detalhes sobre como gerenciar atualizações do HoloLens 2.

### <a name="certificates"></a>Certificados
O HoloLens 2 dá suporte à implantação de certificados por meio do MDM se seu ambiente exigir certificados para autenticação de rede Wi-Fi Corp ou acesso a outros recursos. Algumas configurações de infraestrutura de MDM podem ser necessárias para habilitar implantações de certificado no HoloLens 2. Leia sobre como preparar [certificados e perfis de rede para o HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network) Se você estiver usando o Intune, confira os detalhes de [configuração de certificação.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## <a name="configure"></a>Configurar

Os administradores de MDM podem definir e implementar configurações de política em qualquer dispositivo corporativo inscrito em um sistema MDM. As definições de configuração que você usar serão diferentes com base no cenário de implantação. No Windows 10, os provedores de serviços de configuração (CSP) são uma interface para ler, definir, modificar ou excluir definições de configuração no dispositivo. Essas configurações são mapeadas para arquivos ou chaves do registro. Para obter mais informações sobre os CSPs de gerenciamento de dispositivo do Windows 10 para o HoloLens 2, consulte a lista completa de [CSPs com suporte em dispositivos do hololens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

O HoloLens 2 também dá suporte à definição de um conjunto limitado de configurações do CSP por meio de pacotes de provisionamento personalizados. Os pacotes de provisionamento normalmente são utilizados para dispositivos não gerenciados por MDM e precisam ser aplicados manualmente a cada dispositivo. Consulte a documentação de [provisionamento do HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) para obter detalhes sobre a criação de pacotes de provisionamento personalizados.

> [!NOTE]
> O HoloLens 2 dá suporte ao [Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), fornecendo um processo fácil e simples para gerenciar suas configurações corporativas de dispositivo do Windows 10.

### <a name="identity-management"></a>Gerenciamento de Identidades

Os funcionários podem usar apenas uma conta para inicializar um dispositivo de modo que&#39;é imperativo que sua organização controla qual conta está habilitada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento. O HoloLens 2 dá suporte a três tipos de conta: conta de usuário local, conta pessoal da Microsoft e contas de Azure Active Directory. É altamente recomendável aproveitar Azure Active Directory para sua solução de gerenciamento de identidades corporativas, pois ela permitirá os recursos completos em seus dispositivos de HoloLens 2. Confira a [identidade do hololens](https://docs.microsoft.com/hololens/hololens-identity) para obter mais detalhes sobre as identidades do HoloLens 2.

### <a name="network-and-connectivity"></a>Rede e conectividade

Como o HoloLens 2 é um primeiro dispositivo de nuvem, o acesso à rede para recursos online é necessário para que a funcionalidade completa e os recursos sejam disponibilizados. Se você estiver implantando dispositivos do HoloLens 2 com conectividade à sua rede de intranet corporativa, talvez seja necessário atualizar suas regras de proxy/firewall para permitir o acesso aos serviços de nuvem do HoloLens 2. Para obter mais informações, veja a lista de pontos de [extremidade comuns para o sistema operacional do HoloLens 2](https://docs.microsoft.com/hololens/hololens-offline). O acesso a pontos de extremidade adicionais pode ser necessário para que aplicativos ou outros serviços de nuvem sejam executados no HoloLens 2 com êxito.

Alguns serviços comuns do HoloLens 2 que exigem acesso adicional ao ponto de extremidade são os seguinte:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guias D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Assistência Remota do D365 (infraestrutura do O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Implantação de certificado

Se os certificados são necessários para acesso a redes Wi-Fi corporativas ou outros serviços em sua organização, o HoloLens 2 dá suporte à implantação de certificado de usuário e dispositivo por meio do MDM. Observação: sua solução de MDM pode exigir configuração de infraestrutura adicional para implantar certificados em Windows 10 dispositivos.

### <a name="security-review"></a>Revisão de segurança

A maioria dos departamentos de IT empresariais exigirá a avaliação e a revisão de novos dispositivos que estão sendo implantados em uma rede corporativa. Se sua organização precisar de uma revisão de segurança do HoloLens 2, você poderá encontrar mais detalhes para ajudar na obtenção de [aprovações de segurança.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Configurações comuns de dispositivo do HoloLens 2

Ao implantar dispositivos HoloLens 2 em um ambiente corporativo corporativo, há várias configurações de dispositivo comuns que podem ser consideradas ao planejar sua implantação do HoloLens 2. Esta lista realça as configurações e as configurações que são encontradas como bastante comuns e não consistem em uma lista completa de opções disponíveis:

| Configuração do dispositivo | Breve descrição.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrições de hardware](hololens-requirements.md#hardware-restrictions)               | As restrições de hardware reduzem a conectividade e auxiliam na proteção de dados.                        |
| [Perfis de Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configure Wi-Fi perfis sem intervenção ou interação do usuário.                              |
| [Certificados](hololens-requirements.md#certificates-1)               | Forneça autenticação de conta e/ou Wi-Fi, criptografia VPN e criptografia SSL do conteúdo da Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gerenciar o tráfego interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controlar o acesso a aplicativos e recursos na intranet da empresa.                               |
| [Modo de quiosque](hololens-requirements.md#kiosk-mode) | Limita os aplicativos que são apresentados aos usuários por meio da interface do usuário. |

#### <a name="hardware-restrictions"></a>Restrições de hardware

O HoloLens 2 usa tecnologia de ponta que inclui recursos de hardware populares, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.

O a seguir lista as configurações de MDM mais usadas que o HoloLens 2 dá suporte para configurar restrições de hardware. Algumas dessas restrições de hardware fornecem conectividade e ajuda na proteção de dados.

- [**Permitir WiFi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar o Wi-Fi rádio em seus dispositivos
- [**Permitir conexão USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não&#39;não afeta o carregamento de USB)
- [**Permitir Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o rádio Bluetooth em seus dispositivos

Leia mais sobre outras [restrições comuns de dispositivo.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Perfis de Wi-Fi

A maioria das redes Wi-Fi corporativas exige certificados e outras informações complexas para restringir e proteger o acesso do usuário. Essas informações de Wi-Fi avançadas são difíceis para os usuários típicos configurarem, mas os sistemas MDM podem configurar esses perfis de Wi-Fi sem intervenção do usuário. Você pode criar vários perfis de Wi-Fi em seu sistema MDM.

Para obter mais detalhes sobre as configurações de Wi-Fi para o Windows 10, consulte [configurações do Enterprise Profile WiFi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### <a name="certificates"></a>Certificados

Os certificados ajudam a melhorar a segurança fornecendo autenticação de conta, Wi-Fi autenticação, criptografia de VPN e criptografia SSL do conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento,&#39;uma prática recomendada usar seu sistema MDM para gerenciar esses certificados em todo o ciclo de vida, desde o registro até a renovação e a revogação. O sistema MDM pode implantar automaticamente esses certificados nos dispositivos&#39; repositórios de certificados depois de registrar o dispositivo (desde que o sistema MDM dê suporte aos padrões de protocolo SCEP (SCEP) ou criptografia de chave pública #12 (PKCS # 12)). O MDM também pode consultar e excluir certificados de cliente registrados ou disparar uma nova solicitação de registro antes que o certificado atual expire.

Leia mais sobre como preparar [certificados e perfis de rede para o HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

A maioria das redes de intranet corporativas aproveita um proxy para gerenciar o tráfego interno. Com o HoloLens 2, você pode configurar um servidor proxy para ethernet e Wi-Fi conexões. Essas configurações não se aplicam a conexões VPN.

Para obter mais detalhes sobre as configurações de proxy Windows 10, consulte [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>VPN

As organizações geralmente usam uma VPN para controlar o acesso a aplicativos e recursos na intranet&#39;empresa. O HoloLens 2 dá suporte a conexões VPN SSL, que exigem um plug-in para download do Microsoft Store e são específicos para o fornecedor de VPN de sua escolha.

Para obter mais detalhes sobre perfis de VPN, consulte o [CSP de VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Modo de quiosque

Você pode configurar um dispositivo HoloLens 2 para funcionar como um dispositivo de finalidade fixa, também chamado de quiosque, configurando o dispositivo para ser executado no modo de quiosque. O modo de quiosque limita os aplicativos (ou usuários) que estão disponíveis no dispositivo. O modo de quiosque é um recurso conveniente que você pode usar para dedicar um dispositivo HoloLens 2 a aplicativos de negócios ou usar o dispositivo HoloLens 2 em uma demonstração de aplicativo.

Para obter mais detalhes sobre como configurar um HoloLens 2 no modo de quiosque, consulte [Configurar o HoloLens como um quiosque](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Implantar

### <a name="mdm-device-enrollment"></a>Registro de dispositivo MDM

Para implantações corporativas, [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) é recomendável registrar dispositivos no MDM como dispositivos corporativos somente com o junção do Azure AD e o registro automático de MDM (Azure AD+MDM). Isso requer Azure AD Premium e dá suporte ao registro automático para vários provedores de MDM, incluindo o Intune.

Saiba mais sobre o método de registro auto-implantação [Autopilot.](https://docs.microsoft.com/hololens/hololens2-autopilot)

### <a name="application-deployment"></a>Implantação do aplicativo

A produtividade do usuário em dispositivos móveis geralmente depende dos aplicativos.

O Windows 10 permite desenvolver aplicativos que funcionem perfeitamente em vários dispositivos usando a Plataforma Universal do Windows (UWP) para aplicativos do Windows.

Há várias maneiras de implantar aplicativos em dispositivos HoloLens 2. Os aplicativos podem ser implantados diretamente por meio do MDM, Microsoft Store para Empresas ou sideload por meio de um pacote de provisionamento. Confira a [documentação de implantação do](https://docs.microsoft.com/hololens/app-deploy-overview) aplicativo para obter mais detalhes.

> [!NOTE]
> O HoloLens 2 dá suporte apenas à execução de aplicativos ARM64 UWP.

## <a name="maintain"></a>Manter

Em ambientes de TI corporativos, a necessidade de controle de custo e segurança precisa ser balanceada com o desejo de fornecer aos usuários as tecnologias mais recentes. Como os ataques cibernéticos se tornaram uma ocorrência diária, é importante manter corretamente o estado de seus Windows 10 dispositivos. A TI precisa controlar as configurações, impedindo-as de se desviar da conformidade, bem como impor quais dispositivos podem acessar aplicativos internos. O HoloLens 2 fornece os recursos de gerenciamento de operações móveis necessários para garantir que os dispositivos estejam em conformidade com a política corporativa.

### <a name="os-servicing-options"></a>Opções de serviço do so

**Um processo de atualização simplificado**

A Microsoft simplificou o ciclo de engenharia e o ciclo de versão do produto Windows para que os novos recursos, as experiências e as funcionalidades que o mercado exigem possam ser fornecidos de forma muito mais rápida. A Microsoft planeja oferecer duas Atualizações de Recursos por ano (período de 12 meses). **As atualizações de recurso** estabelecem um Branch atual ou CB e têm uma versão associada.

A Microsoft também fornecerá e instalará atualizações de segurança e estabilidade diretamente para dispositivos de HoloLens 2. Essas **atualizações de qualidade** , liberadas sob o controle da Microsoft via Windows Update, estão disponíveis mensalmente. O HoloLens 2 consome atualizações de recursos e atualizações de qualidade como parte do mesmo processo de atualização padrão.

Os clientes corporativos podem gerenciar a experiência de atualização e o processo no HoloLens 2s usando um sistema MDM. Na maioria dos casos, as políticas para gerenciar o processo de atualização serão aplicadas às atualizações de recursos e qualidade. Mais detalhes sobre [como configurar o MDM para atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="managing-applications"></a>Gerenciar aplicativos

Os administradores de ti podem controlar quais aplicativos têm permissão para serem instalados no HoloLens 2 e como eles devem ser mantidos atualizados.

O HoloLens 2 dá suporte ao [controle de aplicativos do Windows Defender (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), que permite aos administradores criar, permitir ou não permitir listas de aplicativos do Microsoft Store. Esse recurso se estende a aplicativos internos também. A capacidade de permitir ou negar aplicativos ajuda a garantir que as pessoas usem seus dispositivos para suas finalidades pretendidas. No entanto, nem sempre é uma abordagem simples encontrar um equilíbrio entre o que os funcionários precisam ou solicitam e as preocupações com a segurança. Criar listas de permissão ou proibição também exige o acompanhamento das mudanças do cenário de aplicativos na Microsoft Store.

Para obter mais detalhes, consulte [CSP do controle de aplicativo](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Desativar

Desativação do dispositivo é a última fase do ciclo de vida do dispositivo. &#39;é importante que os dispositivos que estão sendo substituídos por modelos mais recentes sejam desativados com segurança, pois você não&#39;deseja que os dados da empresa permaneçam em dispositivos descartados que possam comprometer a confidencialidade dos seus dados. A TI também precisa de uma forma de oferecer suporte adequado a usuários que precisam apagar dispositivos perdidos ou roubados.

O HoloLens 2 dá suporte a três métodos de apagamento do dispositivo

**Apagamento de fábrica de MDM:** Redefine o HoloLens 2 de volta para a imagem de fábrica por meio do comando MDM iniciado pelo administrador. Apaga todos os dados armazenados no dispositivo.

**Redefinição de dispositivo de dentro das configurações:** Os usuários finais podem redefinir manualmente o HoloLens 2 dentro do aplicativo de configurações no dispositivo. Apaga todos os dados armazenados no dispositivo.

**ARC (Advanced Recovery Companion):** Em um computador que executa a ferramenta ARC, um usuário ou administrador pode piscar um HoloLens 2 conectado ao computador por meio de cabo USB. Apaga todos os dados armazenados no dispositivo.

> [!div class="nextstepaction"]
> [Cenários comuns de implantação](common-scenarios.md)
