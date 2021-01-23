---
title: Configurar o HoloLens em um ambiente comercial
description: Saiba mais sobre como implantar e gerenciar o HoloLens em ambientes corporativos, incluindo infraestrutura, azure Active Directory e gerenciamento de dispositivos móveis.
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
ms.openlocfilehash: 9458a6fd02cf96dd265580cb099e39fa221d4206
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284042"
---
# Implantação e gerenciamento empresariais do HoloLens 2

Esta visão geral se destina a ajudar os profissionais de TI a entender as considerações para implantar e gerenciar dispositivos Microsoft HoloLens 2 dentro da empresa.

O HoloLens 2 é executado no Windows 10 Holographic, que fornece às organizações tecnologias robustas, flexíveis e de gerenciamento de aplicativos móveis. O Windows 10 Holographic dá suporte ao gerenciamento do ciclo de vida do dispositivo de ponta a ponta para dar às empresas o controle sobre seus dispositivos, dados e aplicativos. O HoloLens 2 pode ser incorporado facilmente às práticas padrão de ciclo de vida, desde o registro de dispositivos, a configuração e o gerenciamento de aplicativos até a manutenção e a baixa utilização de uma solução abrangente de gerenciamento de dispositivo móvel.

## Preparar

Conforme você se prepara para implantar o HoloLens 2 em seu ambiente corporativo corporativo, há várias considerações que devem ser revisadas e compreendidas à medida que você começa a planejar implantações em escala do HoloLens 2.

### Infrastructure Essentials

Para o HoloLens 2 em um cenário de implantação corporativa, existem determinados serviços de infraestrutura essenciais necessários para dar suporte ao conjunto completo de recursos. O HoloLens 2 foi criado com o [Gerenciamento](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) de Dispositivo Móvel Moderno em mente para implantação e gerenciamento. Com o Azure AD Join + MDM como o principal meio de conseguir isso em uma força de trabalho móvel cada vez maior. Os tópicos a seguir fornecem uma breve visão geral de cada componente de infraestrutura que deve ser considerado no planejamento de implantação do HoloLens 2.

### Azure Active Directory
O Azure AD é um serviço de diretório baseado na nuvem que fornece gerenciamento de acesso e identidade. Você pode integrá-lo com diretórios locais existentes para criar uma solução de identidade híbrida. As organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: Free, Premium P1 e Premium P2 (confira as edições do [Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Todas as edições são suportadas pelo registro de dispositivos do Azure AD, mas o Premium P1 é necessário para habilitar o registro automático no MDM. O HoloLens 2 requer o Azure Active Directory Join para habilitar a maioria dos recursos e funcionalidades de nível empresarial.

> [!NOTE]
> O Ingressar no Active Directory local não é suportado no HoloLens 2.

### Gerenciamento de Dispositivo Móvel
O HoloLens 2 foi projetado especificamente para ser gerenciado por sistemas de Gerenciamento de Dispositivo Móvel (MDM) em um ambiente corporativo. O Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), parte do Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos na empresa. Assim como o Office 365, o Intune usa o Azure AD para gerenciamento de identidades, para que os funcionários usem as mesmas credenciais para registrar dispositivos no Intune que usam para entrar no Office 365. Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os sistemas MDM também podem gerenciar implantações e atualizações de aplicativos para o HoloLens 2. Outros provedores de MDM que suportam o HoloLens 2 atualmente incluem: AirWatch, MobileIron e outros. Todos os fornecedores de sistema MDM têm acesso igual aos CSP (provedores de serviços de configuração) de gerenciamento de dispositivos (CSP) do Windows 10, dando às organizações de TI a liberdade de selecionar o sistema que melhor se adéque aos seus requisitos de gerenciamento, seja o Microsoft Intune ou um produto MDM de terceiros.

> [!NOTE]
> Sistemas de gerenciamento de computadores locais tradicionais, como o System Center Configuration Manager, não são suportados no HoloLens 2.

### Windows Update para Empresas
A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações. Consulte a [documentação de atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates) para obter detalhes sobre como gerenciar as atualizações do HoloLens 2.

### Certificados
O HoloLens 2 oferece suporte à implantação de certificados por meio do MDM se seu ambiente exigir certificados para autenticação de rede Corp Wi-Fi ou acesso a outros recursos. Algumas configurações de infraestrutura MDM podem ser necessárias para habilitar implantações de certificado no HoloLens 2. Leia sobre como preparar [certificados e perfis de rede para o HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network) Se você estiver usando o Intune, confira os detalhes de [configuração de certificação.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## Configurar

Os administradores de MDM podem definir e implementar configurações de política em qualquer dispositivo corporativo inscrito em um sistema MDM. As definições de configuração usadas serão diferentes com base no cenário de implantação. No Windows 10, os Provedores de Serviços de Configuração (CSP) são uma interface para ler, definir, modificar ou excluir definições de configuração no dispositivo. Essas configurações mapeiam para arquivos ou chaves do Registro. Para obter mais informações sobre CSPs de gerenciamento de dispositivos Windows 10 para HoloLens 2, consulte a lista completa de CSPs com suporte em [dispositivos HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

O HoloLens 2 também dá suporte à definição de um conjunto limitado de configurações CSP por meio de pacotes de provisionamento personalizados. Os pacotes de provisionamento são geralmente aproveitados para dispositivos gerenciados não MDM e precisam ser aplicados manualmente a cada dispositivo. Consulte a [documentação de provisionamento do HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) para obter detalhes sobre como criar pacotes de provisionamento personalizados.

> [!NOTE]
> O HoloLens 2 dá suporte ao [Windows Autopilot,](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)fornecendo um processo fácil e simples para gerenciar suas configurações de dispositivos Windows 10 corporativas.

### Gerenciamento de Identidades

Os funcionários podem usar apenas uma conta para inicializar um dispositivo para que&#39;imperativo que sua organização controle qual conta é habilitada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento. O HoloLens 2 oferece suporte a três tipos de conta: conta de usuário local, conta pessoal da Microsoft e contas do Azure Active Directory. É altamente recomendável aproveitar o Azure Active Directory para sua solução de gerenciamento de identidade corporativa, pois ele habilita todos os recursos em seus dispositivos HoloLens 2. Confira a [identidade do HoloLens](https://docs.microsoft.com/hololens/hololens-identity) para obter mais detalhes sobre identidades do HoloLens 2.

### Rede e Conectividade

Como o HoloLens 2 é um primeiro dispositivo na nuvem, o acesso de rede aos recursos online é necessário para que funcionalidades e funcionalidades completas sejam disponibilizadas. Se você estiver implantando dispositivos HoloLens 2 com conectividade com sua rede de intranet corporativa, talvez seja necessário atualizar suas regras de proxy/firewall para permitir o acesso aos serviços de nuvem do HoloLens 2. Para obter mais informações, dê uma olhada na lista de pontos de extremidade comuns para o sistema [operacional HoloLens 2.](https://docs.microsoft.com/hololens/hololens-offline) O acesso a pontos de extremidade adicionais pode ser necessário para que aplicativos ou outros serviços de nuvem sejam executados no HoloLens 2 com êxito.

Alguns serviços comuns do HoloLens 2 que exigem acesso adicional ao ponto de extremidade são:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guias do D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Assistência Remota do D365 (infraestrutura do O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Implantação de certificado

Se os certificados são necessários para acesso a redes Wi-Fi corporativas ou outros serviços em sua organização, o HoloLens 2 oferece suporte à implantação de certificados de usuário e dispositivo por meio do MDM. Observação: sua solução MDM pode exigir configuração de infraestrutura adicional para implantar certificados em dispositivos Windows 10.

### Revisão de Segurança

A maioria dos departamentos de IT corporativos exigirá avaliação e revisão de novos dispositivos que estão sendo implantados em uma rede corporativa. Se sua organização precisar de uma revisão de segurança do HoloLens 2, você poderá encontrar mais detalhes para ajudar na obtenção de [aprovações de segurança.](https://docs.microsoft.com/hololens/security-overview)

### Configurações comuns do dispositivo do HoloLens 2

Ao implantar dispositivos HoloLens 2 em um ambiente corporativo corporativo, há várias configurações de dispositivo comuns que podem ser consideradas ao planejar sua implantação do HoloLens 2. Esta lista destaca as configurações e as configurações que são encontradas como muito comuns e não consistem em uma lista completa de opções disponíveis:

| Configuração do dispositivo | Breve descrição.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrições de hardware](hololens-requirements.md#hardware-restrictions)               | As restrições de hardware reduzem a conectividade e auxiliam na proteção de dados.                        |
| [Perfis de Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configure Wi-Fi perfis sem intervenção ou interação do usuário.                              |
| [Certificados](hololens-requirements.md#certificates-1)               | Fornecer autenticação de conta e/ou Wi-Fi, criptografia VPN e criptografia SSL do conteúdo da Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gerencie o tráfego interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controlar o acesso a aplicativos e recursos na intranet da empresa.                               |
| [Modo de quiosque](hololens-requirements.md#kiosk-mode) | Limita os aplicativos apresentados aos usuários por meio da interface do usuário. |

#### Restrições de hardware

O HoloLens 2 usa tecnologia de última geração que inclui recursos de hardware populares, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.

A lista a seguir lista as configurações MDM mais usadas que o HoloLens 2 suporta para configurar restrições de hardware. Algumas dessas restrições de hardware fornecem conectividade e auxiliam na proteção de dados.

- [**Permitir WiFi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar o rádio Wi-Fi em seus dispositivos
- [**Permitir Conexão USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (&#39;afeta o carregamento USB)
- [**Permitir Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o rádio Bluetooth em seus dispositivos

Leia mais sobre outras [restrições comuns de dispositivo.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Perfis de Wi-Fi

A maioria das redes Wi-Fi corporativas exigem certificados e outras informações complexas para restringir e proteger o acesso de usuário. Essas informações Wi-Fi avançadas são difíceis para os usuários comuns configurarem, mas os sistemas MDM podem configurar totalmente esses perfis de Wi-Fi sem intervenção do usuário. Você pode criar vários perfis de Wi-Fi em seu sistema MDM.

Para obter mais detalhes sobre Wi-Fi configurações para o Windows 10, consulte configurações de WiFi de perfil [empresarial.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### Certificados

Os certificados ajudam a melhorar a segurança, fornecendo autenticação de conta, Wi-Fi autenticação, criptografia VPN e criptografia SSL de conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento, é uma prática&#39;usar seu sistema MDM para gerenciar esses certificados durante todo o ciclo de vida, desde o registro até a renovação e revogação. Seu sistema MDM pode implantar automaticamente esses certificados nos dispositivos que&#39; armazenam certificados depois de registrar o dispositivo (desde que o sistema MDM suporte o protocolo SCEP ou os padrões de criptografia de chave pública #12 (PKCS#12)). O MDM também pode consultar e excluir certificados de cliente inscritos ou disparar uma nova solicitação de registro antes que o certificado atual seja expirado.

Leia mais sobre como preparar [certificados e perfis de rede para o HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

A maioria das redes de intranet corporativas utiliza um proxy para gerenciar o tráfego interno. Com o HoloLens 2, você pode configurar um servidor proxy para conexões ethernet e Wi-Fi rede. Essas configurações não se aplicam a conexões VPN.

Para obter mais detalhes sobre as configurações de proxy para o Windows 10, consulte [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

As organizações geralmente usam uma VPN para controlar o acesso a aplicativos e recursos na&#39;da empresa. O HoloLens 2 dá suporte a conexões VPN SSL, que exigem um plug-in baixável da Microsoft Store e são específicas para o fornecedor de VPN de sua escolha.

Para obter mais detalhes sobre perfis de VPN, consulte o [CSP de VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### Modo de quiosque

Você pode configurar um dispositivo HoloLens 2 para funcionar como um dispositivo de finalidade fixa, também chamado de quiosque, configurando o dispositivo para ser executado no modo de quiosque. O modo de quiosque limita os aplicativos (ou usuários) disponíveis no dispositivo. O modo de quiosque é um recurso conveniente que você pode usar para dedicar um dispositivo HoloLens 2 a aplicativos de negócios ou para usar o dispositivo HoloLens 2 em uma demonstração de aplicativo.

Para obter mais detalhes sobre como configurar um HoloLens 2 no Modo de Quiosque, consulte Configurar o [HoloLens como um Quiosque](https://docs.microsoft.com/hololens/hololens-kiosk)

## Implantar

### Registro de dispositivos MDM

Para implantações corporativas, [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) é recomendável registrar dispositivos no MDM como dispositivos corporativos somente com o Azure AD e o registro automático no MDM (Azure AD+MDM). Isso requer o Azure AD Premium e dá suporte ao registro automático para vários provedores de MDM, incluindo o Intune.

Saiba mais sobre o método de registro auto-implantação [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### Implantação de aplicativos

A produtividade do usuário em dispositivos móveis geralmente depende dos aplicativos.

O Windows 10 permite desenvolver aplicativos que funcionem perfeitamente em vários dispositivos usando a Plataforma Universal do Windows (UWP) para aplicativos do Windows.

Há várias maneiras de implantar aplicativos em dispositivos HoloLens 2. Os aplicativos podem ser implantados diretamente por meio do MDM, da Microsoft Store para Empresas ou por meio de um pacote de provisionamento. Confira a [documentação de implantação do](https://docs.microsoft.com/hololens/app-deploy-overview) aplicativo para obter mais detalhes.

> [!NOTE]
> O HoloLens 2 dá suporte somente à execução de aplicativos ARM64 UWP.

## Manter

Em ambientes de TI corporativos, a necessidade de controle de custo e segurança precisa ser balanceada com o desejo de fornecer aos usuários as tecnologias mais recentes. Como os ataques cibernéticos se tornaram uma ocorrência diária, é importante manter corretamente o estado dos seus dispositivos Windows 10. A TI precisa controlar as configurações, impedindo-as de se desviar da conformidade, bem como impor quais dispositivos podem acessar aplicativos internos. O HoloLens 2 oferece os recursos de gerenciamento de operações móveis necessários para garantir que os dispositivos estão em conformidade com a política corporativa.

### Opções de manutenção do sistema operacional

**Um processo de atualização simplificado**

A Microsoft simplificou o ciclo de engenharia e o ciclo de versão do produto Windows para que os novos recursos, as experiências e as funcionalidades que o mercado exigem possam ser fornecidos de forma muito mais rápida. A Microsoft planeja oferecer duas Atualizações de Recursos por ano (período de 12 meses). **As Atualizações de** Recursos estabelecem um Branch Atual ou CB e têm uma versão associada.

A Microsoft também fornecerá e instalará atualizações de segurança e estabilidade diretamente para dispositivos HoloLens 2. Essas **Atualizações de Qualidade, lançadas** sob o controle da Microsoft por meio do Windows Update, estão disponíveis mensalmente. O HoloLens 2 consome Atualizações de Recursos e Atualizações de Qualidade como parte do mesmo processo de atualização padrão.

Os clientes corporativos podem gerenciar a experiência e o processo de atualização no HoloLens 2s usando um sistema MDM. Na maioria dos casos, as políticas para gerenciar o processo de atualização serão aplicadas às atualizações de recursos e qualidade. Mais detalhes na [configuração do MDM para atualizações do HoloLens.](https://docs.microsoft.com/hololens/hololens-updates)

### Gerenciando aplicativos

Os administradores de IT podem controlar quais aplicativos têm permissão para serem instalados no HoloLens 2 e como eles devem ser mantidos atualizados.

O HoloLens 2 dá suporte ao [Windows Defender Application Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)que permite aos administradores criar, permitir ou não listas de aplicativos da Microsoft Store. Essa funcionalidade também se estende a aplicativos nativos. A capacidade de permitir ou negar aplicativos ajuda a garantir que as pessoas usem seus dispositivos para os fins pretendido. No entanto, nem sempre é uma abordagem simples encontrar um equilíbrio entre o que os funcionários precisam ou solicitam e as preocupações com a segurança. Criar listas de permissão ou proibição também exige o acompanhamento das mudanças do cenário de aplicativos na Microsoft Store.

Para obter mais detalhes, consulte [CSP de Controle de Aplicativo.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### Desativar

A baixa do dispositivo é a última fase do ciclo de vida do dispositivo. É&#39;&#39;importante que os dispositivos que estão sendo substituídos por modelos mais recentes sejam retirados com segurança, pois você não quer que os dados da empresa permaneçam em dispositivos descartados que poderiam comprometer a confidencialidade dos seus dados. A TI também precisa de uma forma de oferecer suporte adequado a usuários que precisam apagar dispositivos perdidos ou roubados.

O HoloLens 2 dá suporte a três métodos de apagar o dispositivo

**Limpeza de fábrica do MDM:** Redefine o HoloLens 2 de volta à imagem de fábrica por meio do comando MDM iniciado pelo administrador. Apaga todos os dados armazenados no dispositivo.

**Redefinição do dispositivo em Configurações:** Os usuários finais podem redefinir manualmente o HoloLens 2 dentro do aplicativo Configurações no dispositivo. Apaga todos os dados armazenados no dispositivo.

**Advanced Recovery Companion (ARC):** Em um computador que executa a ferramenta ARC, um usuário ou administrador pode piscar um HoloLens 2 conectado ao computador por meio de cabo USB. Apaga todos os dados armazenados no dispositivo.

> [!div class="nextstepaction"]
> [Cenários de Implantação Comuns](common-scenarios.md)
