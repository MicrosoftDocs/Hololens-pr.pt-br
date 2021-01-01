---
title: Configurar o HoloLens em um ambiente comercial
description: Saiba mais sobre a implantação e o gerenciamento do HoloLens em ambientes empresariais.
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
ms.openlocfilehash: 082064acd075451e7a8d55352249a0776cd19d76
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253208"
---
# Implantação e gerenciamento corporativos do HoloLens 2

Esta visão geral tem como objetivo ajudar os profissionais de ti a entender as considerações para a implantação e o gerenciamento de dispositivos Microsoft HoloLens 2 na empresa.

O HoloLens 2 funciona no Windows 10 holográfico, que fornece às organizações com tecnologias de gerenciamento de aplicativos e dispositivos móveis robustos e flexíveis. O Windows 10 holográfico oferece suporte ao gerenciamento de ciclo de vida de dispositivo completo para dar às empresas o controle sobre seus dispositivos, dados e aplicativos. O HoloLens 2 pode ser facilmente incorporado às práticas do ciclo de vida padrão, do registro de dispositivos, da configuração e do gerenciamento de aplicativos, à manutenção e à aposentadoria usando uma solução abrangente de gerenciamento de dispositivos móveis.

## Preparar

Ao preparar-se para implantar o HoloLens 2 em seu ambiente corporativo corporativo, há várias considerações que devem ser revisadas e compreendidas ao começar a planejar as implantações de escala do HoloLens 2.

### Fundamentos da infraestrutura

Para o HoloLens 2 em um cenário de implantação corporativo corporativo, há alguns serviços essenciais de infraestrutura necessários para dar suporte ao conjunto completo de recursos. O HoloLens 2 foi desenvolvido com o [Gerenciamento moderno de dispositivos móveis](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) em mente para implantação e gerenciamento. Com o Azure AD Join + MDM como o principal meio de conseguir isso em uma equipe de força de celular sempre crescente. Os tópicos a seguir fornecem uma breve visão geral de cada componente de infraestrutura que deve ser considerado em seu planejamento de implantação para o HoloLens 2.

### Azure Active Directory
O Azure AD é um serviço de diretório baseado na nuvem que fornece gerenciamento de acesso e identidade. Você pode integrá-lo com diretórios locais existentes para criar uma solução de identidade híbrida. Organizações que usam o Microsoft Office 365 ou o Intune já estão usando o Azure AD, que tem três edições: grátis, Premium P1 e Premium P2 (consulte [edições do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Todas as edições dão suporte ao registro de dispositivos do Azure AD, mas o Premium P1 é necessário para habilitar o registro automático do MDM. O HoloLens 2 requer o Azure Active Directory Join para habilitar a maioria dos recursos e funcionalidades de nível empresarial.

> [!NOTE]
> Não há suporte para o ingresso no Active Directory local no HoloLens 2.

### Gerenciamento de Dispositivo Móvel
O HoloLens 2 foi projetado especificamente para ser gerenciado por sistemas de gerenciamento de dispositivos móveis (MDM) em um ambiente corporativo. O Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), parte da Enterprise Mobility + Security, é um sistema MDM baseado em nuvem que gerencia dispositivos na empresa. Assim como o Office 365, o Intune usa o Azure AD para gerenciamento de identidades, portanto, os funcionários usam as mesmas credenciais para registrar dispositivos no Intune que eles usam para entrar no Office 365. Vários sistemas MDM dão suporte ao Windows 10, e a maioria dão suporte a cenários de implantação de dispositivos pessoais e corporativos. Os sistemas de MDM também podem gerenciar implantações e atualizações de aplicativos para o HoloLens 2 também. No momento, outros provedores de MDM que dão suporte ao HoloLens 2 são: Watch Watch, MobileIron e outros. Todos os fornecedores de sistema do MDM têm acesso igual aos provedores de serviços de configuração de gerenciamento de dispositivos (CSP) do Windows 10, dando às organizações de ti a liberdade de selecionar o sistema mais adequado para seus requisitos de gerenciamento, se o Microsoft Intune ou um produto de MDM de terceiros.

> [!NOTE]
> Não há suporte para sistemas de gerenciamento de PC tradicionais, como o System Center Configuration Manager, no HoloLens 2.

### Windows Update para Empresas
A Microsoft projetou o Windows Update para Empresas para fornecer aos administradores de TI recursos de gerenciamento adicionais centrados no Windows Update, como a habilidade de implantar atualizações em grupos de dispositivos e de definir janelas de manutenção para a instalação de atualizações. Os detalhes de gerenciamento de atualizações do HoloLens 2 podem ser encontrados [aqui](https://docs.microsoft.com/hololens/hololens-updates).

### Certificados
O HoloLens 2 dá suporte à implantação de certificados por meio do MDM se seu ambiente exigir certificados para autenticação de rede Wi-Fi Corp ou acesso a outros recursos. Algumas configurações de infraestrutura do MDM podem ser necessárias para habilitar implantações de certificados para o HoloLens 2. Leia sobre como [preparar certificados e perfis de rede para o HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Os detalhes do Intune podem ser encontrados [aqui](https://docs.microsoft.com/mem/intune/protect/certificates-configure).

## Configurar

Os administradores do MDM podem definir e implementar configurações de política em qualquer dispositivo corporativo registrado em um sistema MDM. As configurações que você usa serão diferentes com base no cenário de implantação. No Windows 10, os provedores de serviços de configuração (CSP) são uma interface para ler, definir, modificar ou excluir definições de configuração no dispositivo. Essas configurações mapeiam para arquivos ou chaves do Registro. Para obter mais informações sobre CSPs de gerenciamento de dispositivos do Windows 10 para o HoloLens 2, consulte a lista completa de [CSPs com suporte em dispositivos do hololens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

O HoloLens 2 também oferece suporte à configuração de um conjunto limitado de configurações de CSP por meio de pacotes de provisionamento personalizados. Os pacotes de provisionamento geralmente são aproveitados para dispositivos gerenciados não MDM e exigem que sejam aplicados manualmente a cada dispositivo. Mais informações sobre a criação de pacotes de provisionamento personalizados podem ser encontradas [aqui](https://docs.microsoft.com/hololens/hololens-provisioning).

> [!NOTE]
> O HoloLens 2 é compatível com o [piloto automático do Windows](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), fornecendo um processo simples e fácil de gerenciar as configurações de dispositivos corporativos do Windows 10.

### Gerenciamento de identidades

Os funcionários podem usar apenas uma conta para inicializar um dispositivo para que&#39;s obrigações de que a sua organização controla qual conta está ativada primeiro. A conta escolhida determinará quem controla o dispositivo e influencia seus recursos de gerenciamento. O HoloLens 2 tem suporte para três tipos de conta: conta de usuário local, conta pessoal da Microsoft e contas do Azure Active Directory. É altamente recomendável aproveitar o Azure Active Directory para sua solução de gerenciamento de identidades corporativos, pois isso permitirá que todos os recursos de seus dispositivos do HoloLens 2 sejam habilitados. Mais detalhes sobre identidades no HoloLens 2 podem ser encontrados [aqui](https://docs.microsoft.com/hololens/hololens-identity).

### Rede e conectividade

Como o HoloLens 2 é um primeiro dispositivo na nuvem, o acesso à rede aos recursos online é necessário para funcionalidade completa e recursos a serem disponibilizados. Se você estiver implantando dispositivos do HoloLens 2 com conectividade com sua rede de intranet corporativa, talvez seja necessário atualizar suas regras de proxy/firewall para permitir o acesso a serviços de nuvem do HoloLens 2. Uma lista de pontos de extremidade comuns necessária para o sistema operacional do HoloLens 2 pode ser encontrada [aqui](https://docs.microsoft.com/hololens/hololens-offline). O acesso a pontos de extremidade adicionais pode ser necessário para que aplicativos ou outros serviços de nuvem sejam executados no HoloLens 2 com êxito.

Alguns serviços comuns do HoloLens 2 que exigem o Endpoint Access adicional são os seguintes:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guias do D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Assistência remota do D365 (infraestrutura de equipes do O365)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Implantação de certificado

Se os certificados forem necessários para acessar redes Wi-Fi corporativas ou outros serviços em sua organização, o HoloLens 2 dá suporte à implantação de certificado de usuário e dispositivo por meio do MDM. Observação: sua solução MDM pode exigir configuração de infraestrutura adicional para implantar certificados em dispositivos Windows 10.

### Revisão de segurança

A maioria dos departamentos de ti da empresa exigirá avaliação e revisão de novos dispositivos sendo implantados em uma rede corporativa corporativa. Se a sua organização exigir uma revisão de segurança do HoloLens 2, você [encontrará mais detalhes aqui para ajudar a obter aprovações de segurança](https://docs.microsoft.com/hololens/security-overview).

### Configurações de dispositivo comuns do HoloLens 2

Ao implantar dispositivos do HoloLens 2 em um ambiente corporativo corporativo, há várias configurações de dispositivos comuns que podem ser consideradas ao planejar sua implantação do HoloLens 2. Esta lista realça as configurações e as configurações que são comuns e não compõem uma lista completa de opções disponíveis:

| Configuração do dispositivo | Breve descrição.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restrições de hardware](hololens-requirements.md#hardware-restrictions)               | Restrições de hardware reduza a conectividade e auxilie na proteção de dados.                        |
| [Perfis de Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurar perfis do Wi-Fi sem intervenção do usuário ou interação.                              |
| [Certificados](hololens-requirements.md#certificates-1)               | Fornecer autenticação de conta e/ou Wi-Fi, criptografia VPN e criptografia SSL do conteúdo da Web. |
| [Proxy](hololens-requirements.md#proxy)              | Gerenciar o tráfego interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controlar o acesso a aplicativos e recursos na intranet da empresa.                               |
| [Modo de quiosque](hololens-requirements.md#kiosk-mode) | Limita os aplicativos que são apresentados aos usuários por meio da interface do usuário. |

#### Restrições de hardware

O HoloLens 2 usa tecnologia de última geração que inclui recursos populares de hardware, como câmeras, microfones, alto-falantes, interfaces USB, interfaces Bluetooth e Wi-Fi. Você pode usar restrições de hardware para controlar a disponibilidade desses recursos.

Veja a seguir as configurações de MDM mais comumente usadas que o HoloLens 2 suporta para configurar restrições de hardware. Algumas dessas restrições de hardware fornecem conectividade e auxiliam na proteção de dados.

- [**Permitir WiFi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Se os usuários podem habilitar e usar o rádio Wi-Fi em seus dispositivos
- [**Permitir conexão USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Se a conexão USB está habilitada (não&#39;t afetar o carregamento USB)
- [**Permitir Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Se os usuários podem habilitar e usar o rádio Bluetooth em seus dispositivos

Leia mais sobre outras [restrições comuns de dispositivo.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Perfis de Wi-Fi

A maioria das redes Wi-Fi corporativas exigem certificados e outras informações complexas para restringir e proteger o acesso de usuário. Essas informações de Wi-Fi avançadas são difíceis de serem configuradas pelos usuários típicos, mas os sistemas MDM podem configurar completamente esses perfis de Wi-Fi sem a intervenção do usuário. Você pode criar vários perfis de Wi-Fi em seu sistema MDM.

Para obter mais detalhes sobre as configurações do Wi-Fi para Windows 10, consulte [configurações do perfil do empreendimento WiFi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### Certificados

Os certificados ajudam a aprimorar a segurança fornecendo autenticação de conta, Wi-Fi autenticação, criptografia VPN e criptografia SSL do conteúdo da Web. Embora os administradores possam gerenciar certificados em dispositivos manualmente por meio de pacotes de provisionamento,&#39;a prática recomendada usar seu sistema de MDM para gerenciar esses certificados durante todo o ciclo de vida deles, desde a inscrição até a renovação e a revogação. Seu sistema MDM pode implantar automaticamente esses certificados nos dispositivos&#39; repositórios de certificados após a inscrição do dispositivo (desde que o sistema MDM dê suporte ao protocolo de registro de certificado simples (SCEP) ou aos padrões de criptografia de chave pública #12 (PKCS # 12)). O MDM também pode consultar e excluir certificados de cliente registrados ou disparar uma nova solicitação de inscrição antes que o certificado atual expire.

Leia mais sobre como [preparar certificados e perfis de rede para o HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

A maioria das redes de intranet corporativas aproveita um proxy para gerenciar o tráfego interno. Com o HoloLens 2, você pode configurar um servidor proxy para conexões Ethernet e Wi-Fi. Essas configurações não se aplicam a conexões VPN.

Para obter mais detalhes sobre as configurações de proxy para o Windows 10, consulte [CSP do NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

Geralmente, as organizações usam uma VPN para controlar o acesso a aplicativos e recursos na empresa&#39;s intranet. O HoloLens 2 dá suporte a conexões VPN SSL, que exigem um plug-in para download da Microsoft Store e são específicas do fornecedor de VPN de sua preferência.

Para obter mais detalhes sobre perfis de VPN, consulte o [CSP de VPNv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### Modo de quiosque

Você pode configurar um dispositivo HoloLens 2 para funcionar como um dispositivo de finalidade fixa, também chamado de quiosque, configurando o dispositivo para ser executado no modo de quiosque. O modo de quiosque limita os aplicativos (ou usuários) que estão disponíveis no dispositivo. O modo de quiosque é um recurso conveniente que você pode usar para dedicar um dispositivo HoloLens 2 a aplicativos comerciais ou usar o dispositivo HoloLens 2 em uma demonstração do aplicativo.

Para obter mais detalhes sobre como configurar um HoloLens 2 no modo de quiosque, consulte [Configurar o hololens como um quiosque](https://docs.microsoft.com/hololens/hololens-kiosk)

## Implantar

### Registro de dispositivo MDM

Para implantações empresariais, é recomendável [registrar dispositivos](https://docs.microsoft.com/hololens/hololens-enroll-mdm) em MDM como dispositivos corporativos somente com o Azure ad Join e o registro automático de MDM (Azure ad + MDM). Isso requer o Azure AD Premium e dá suporte à inscrição automática para vários provedores de MDM, incluindo o Intune.

Saiba mais sobre o auto-Deploying do método de inscrição [AutoPilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### Implantação de aplicativos

A produtividade do usuário em dispositivos móveis geralmente depende dos aplicativos.

O Windows 10 permite desenvolver aplicativos que funcionem perfeitamente em vários dispositivos usando a Plataforma Universal do Windows (UWP) para aplicativos do Windows.

Há várias maneiras de implantar aplicativos em dispositivos do HoloLens 2. Os aplicativos podem ser implantados diretamente por meio do MDM, da Microsoft Store para empresas ou do Sideload por meio de um pacote de provisionamento. Mais [detalhes sobre a implantação de aplicativos podem ser encontrados aqui](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> O HoloLens 2 só permite a execução de aplicativos UWP ARM64.

## Manter

Em ambientes de TI corporativos, a necessidade de controle de custo e segurança precisa ser balanceada com o desejo de fornecer aos usuários as tecnologias mais recentes. Como o cyberattacks tornou-se uma ocorrência diária, é importante manter o estado de seus dispositivos Windows 10 corretamente. A TI precisa controlar as configurações, impedindo-as de se desviar da conformidade, bem como impor quais dispositivos podem acessar aplicativos internos. O HoloLens 2 oferece as funcionalidades de gerenciamento de operações para dispositivos móveis necessárias para garantir que os dispositivos estejam em conformidade com a política corporativa.

### Opções de serviço do so

**Um processo de atualização simplificado**

A Microsoft simplificou o ciclo de engenharia e o ciclo de versão do produto Windows para que os novos recursos, as experiências e as funcionalidades que o mercado exigem possam ser fornecidos de forma muito mais rápida. A Microsoft planeja oferecer duas Atualizações de Recursos por ano (período de 12 meses). **As atualizações de recursos** estabelecem um Branch ou CB atual e têm uma versão associada.

A Microsoft também fornecerá e instalará atualizações de segurança e estabilidade diretamente para dispositivos do HoloLens 2. Essas **atualizações de qualidade** , lançadas em controle da Microsoft via Windows Update, estão disponíveis mensalmente. O HoloLens 2 consome atualizações de recursos e atualizações de qualidade como parte do mesmo processo de atualização padrão.

Os clientes empresariais podem gerenciar a experiência de atualização e processar o HoloLens 2s usando um sistema MDM. Na maioria dos casos, as políticas para gerenciar o processo de atualização serão aplicadas às atualizações de recursos e qualidade. Mais detalhes em [Configurando o MDM para atualizações do HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### Gerenciando aplicativos

Os administradores de ti podem controlar quais aplicativos podem ser instalados no HoloLens 2 e como eles devem ser mantidos em dia.

O HoloLens 2 tem suporte para o [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), que permite aos administradores criar, permitir ou proibir listas de aplicativos da Microsoft Store. Esse recurso também se estende a aplicativos internos. A capacidade de permitir ou recusar aplicativos ajuda a garantir que as pessoas usem seus dispositivos para fins pretendidos. No entanto, nem sempre é uma abordagem simples encontrar um equilíbrio entre o que os funcionários precisam ou solicitam e as preocupações com a segurança. Criar listas de permissão ou proibição também exige o acompanhamento das mudanças do cenário de aplicativos na Microsoft Store.

Para obter mais detalhes, consulte [CSP de controle de aplicativo](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### Desativar

Descontinuação de dispositivo é a última fase do ciclo de vida do dispositivo. É&#39;certeza de que os dispositivos que estão sendo substituídos por modelos mais recentes são desativados com segurança, pois você não&#39;deseja que os dados da empresa permaneçam em dispositivos descartados que podem comprometer a confidencialidade dos seus dados. A TI também precisa de uma forma de oferecer suporte adequado a usuários que precisam apagar dispositivos perdidos ou roubados.

O HoloLens 2 tem suporte para três métodos de limpar o dispositivo

**Apagamento de fábrica do MDM:** Redefine o HoloLens 2 de volta para a imagem de fábrica via comando MDM iniciado pelo administrador. Apaga todos os dados armazenados no dispositivo.

**Reinicialização do dispositivo nas configurações:** Os usuários finais podem redefinir manualmente o HoloLens 2 dentro do aplicativo configurações no dispositivo. Apaga todos os dados armazenados no dispositivo.

**Complemento avançado de recuperação (ARC):** Em um PC com a ferramenta ARC, um usuário ou administrador pode fazer flash de um HoloLens 2 conectado ao PC via cabo USB. Apaga todos os dados armazenados no dispositivo.

> [!div class="nextstepaction"]
> [Cenários de Implantação Comuns](common-scenarios.md)