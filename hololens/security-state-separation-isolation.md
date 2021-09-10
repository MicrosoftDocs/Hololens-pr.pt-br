---
title: Separação e isolamento de estado
description: Saiba mais sobre separação de estado, isolamento, assinatura de código e aplicativos do Defender no dispositivo de realidade misturada do HoloLens 2.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, State separation, State separation and isolation, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428426"
---
# <a name="state-separation-and-isolation"></a>Separação e isolamento de estado

A separação e o isolamento de estado protegem partes críticas do sistema operacional do HoloLens 2 contra alterações, como aquelas necessárias para que o sistema operacional seja inicializado em um estado confiável. Com a tecnologia de isolamento, os aplicativos não confiáveis são movidos para um ambiente de área restrita isolada, para garantir que eles não afetarão a segurança do sistema.

## <a name="state-separation"></a>Separação de estado

A separação de estado no HoloLens 2 aprimora imensamente a segurança e a capacidade de manutenção (atualização) e ajuda a proteger seus dados de aplicativo.  A separação de estado funciona da seguinte maneira:
  * O sistema operacional principal é armazenado no volume do sistema operacional principal (um SO confiável ou verificado da Microsoft que atualiza o sistema operacional).
  * As partes do sistema operacional que podem ser alteradas em runtime (como drivers e configurações para download) usam a separação de estado adicional para particionar os dados e armazená-los em locais de armazenamento seguros e separados.
  * Cada localização de armazenamento seguro tem políticas de segurança distintas associadas, oferecendo diversas vantagens de segurança, conforme detalhado na seção a seguir.

## <a name="state-separation-benefits"></a>Benefícios da separação de estado

  * Segurança: a separação de estado apresentada no HoloLens 2 aprimora significativamente a integridade da plataforma, a resistência contra malware e a proteção de dados do usuário. Ao separar a parte inalterável do sistema operacional e torná-la somente leitura ou com integridade protegida, a separação de estado torna extremamente difícil para o malware persistir na reinicialização a frio. 
  * Atualizações: com o HoloLens 2, como o sistema operacional principal não é modificável e foi corretamente separado do restante dos dados no dispositivo, as atualizações se tornam simples e confiáveis.  Além disso, a separação de estado cria os alicerces vitais para atualizações muito mais rápidas, o que permite que o sistema operacional seja substituído em uma só etapa (unidade atômica).
  * Redefinição do dispositivo: a redefinição no HoloLens 2 limpa os dados gerados pelo usuário e os dados do aplicativo do usuário no dispositivo, incluindo locais de armazenamento internos e externos. Ela preserva os aplicativos do sistema operacional atual e os aplicativos críticos de segurança, além dos aplicativos personalizados da Microsoft e do OEM (pré-instalados). Esses aplicativos pré-instalados podem ser reidratados no dispositivo após a conclusão da redefinição

### <a name="state-separation-states"></a>Estados da separação de estado

A separação de estado assegura que o sistema operacional só possa ser alterado por componentes de dispositivos confiáveis da Microsoft e que somente o estado de alto valor tenha permissão para ser persistido entre as reinicializações; outros estados do sistema só existem durante a sessão de inicialização e são descartados após a reinicialização. A separação de estado retorna rapidamente o dispositivo novamente para o estado de fábrica. Os estados do Windows Holographic for Business podem ser divididos nestas categorias distintas:
  * Sistema operacional principal – Estado inalterável
  * Dados do sistema operacional – Estado alterável 
  * Dados do usuário – Estado alterável

Cada um desses estados operacionais do HoloLens 2 são descritos na seção a seguir.

#### <a name="core-operating-system"></a>Sistema operacional principal

Um estado imutável é formado por arquivos executáveis e dados inalteráveis e que só podem ser alterados pela Microsoft durante a instalação das atualizações. Durante essa atualização do sistema operacional principal, uma nova imagem contendo o mais recente estado operacional desejado é habilitada.
O estado inalterável é marcado como somente leitura (ou, de outro modo, tem a integridade protegida), evitando a persistência de qualquer malware com privilégios elevados. Os seguintes arquivos e dados executáveis estão protegidos no estado imutável:
  * Drivers originais do Windows Holographic
  * Binários do sistema operacional
  * Drivers originais do Windows
  * Configurações estáticas do Windows Holographic armazenadas no hive do Registro do Windows (HKLM)
    * Exemplo: o HKLM armazena as informações de configuração dos aplicativos instalados em um computador. Ele também armazena informações para detectar um hardware e os drivers correspondentes.
Ao protegê-los no estado imutável (com proteção de integridade e somente leitura), garantimos que o sistema operacional principal sempre seja inicializado em um estado confiável. Além disso, quando um dispositivo é redefinido, podemos garantir que o dispositivo será inicializado apenas nos componentes que estão nesta seção imutável. 

#### <a name="operating-system-data"></a>Dados do sistema operacional 

É importante observar que os arquivos e os dados executáveis que são alteráveis em runtime (e que não são críticos para a função do sistema operacional) poderão ser descartados e recriados quando os dados estiverem corrompidos ou comprometidos. É necessário que o estado alterável de alto valor seja persistido pelo sistema operacional ou é esperado que ele seja persistido no desligamento do sistema operacional e/ou entre reinicializações por cenários de dispositivos e de sistema operacional Windows compatíveis. Entre os exemplos de estado mutável de alto valor estão:
  * Configurações de dispositivo globais definidas pelo administrador de TI, como a desabilitação da localização para todos os usuários.
  * Redes lembradas nos dispositivos de dados de acesso à conexão de rede Wi-Fi e senhas de conexão associadas.
  * Despejos de memória, incluindo configurações e logs.
  * Drivers baixados sob demanda para dispositivos recém-descobertos.
Um estado alterável de alto valor no HoloLens 2 reside na localização de segurança de dados do sistema operacional como um arquivo salvo em disco ou em um hive do Registro persistente.

#### <a name="user-data"></a>Dados do usuário

A última categoria de estado representa os dados do usuário produzidos ou persistidos por aplicativos UWP ou do sistema operacional. Todas as pastas de usuário conhecidas, como Downloads, Documentos, Vídeos, perfis de usuários e o hive HKEY_CURRENT_USER, também são armazenadas nessa localização. Esses dados não podem ser extraídos sem as credenciais adequadas; para saber mais sobre como seus dados são protegidos, confira [Criptografia e proteção de dados](security-encryption-data-protection.md).

##  <a name="isolation"></a>Isolamento

Para alcançar esse equilíbrio, o HoloLens 2 tem um sistema operacional principal que é usado para as funções primárias, como inicialização, controle de hardware, logon etc. Há apenas dois conjuntos de aplicativos em execução no sistema operacional principal: aplicativos pré-instalados e aplicativos UWP.

## <a name="code-signing"></a>Assinatura de código

A assinatura de código digital permite a comprovação de que os executáveis e os scripts não foram modificados, pois foram assinados por uma fonte confiável, fornecendo, portanto, autenticidade e integridade. As autoridades nas quais o HoloLens 2 confia por padrão são a Microsoft e a Microsoft Store. Os administradores de TI podem adicionar novos certificados ao dispositivo por meio dos CSPs [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) e [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp). Eles também podem usar a [política AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) para confiar em aplicativos adicionais de sideload ou de [linha de negócios](/intune/apps/lob-apps-windows). Os certificados residem no repositório de certificados do computador local, que é armazenado em HKLM/Raiz se o “Dispositivo” estiver sendo usado ou em HKCU se o “Usuário” estiver sendo usado.

## <a name="defender-protections"></a>Proteções do Defender
O HoloLens 2 usa serviços Microsoft para proporcionar aos usuários um nível de segurança avançado:

* O [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) é habilitado automaticamente no Windows Holographic pelo sistema operacional e fornece proteção contra phishing e malware e contra o download de arquivos potencialmente mal-intencionados no Microsoft Edge. Ele não pode ser desativado pelo usuário, mas pode ser desabilitado por meio da política.

* O [Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) bloqueia o fluxo de tráfego de rede não autorizado no dispositivo. Ele está habilitado por padrão e não pode ser configurado pelo cliente por meio de uma política ou de ações locais. 

* [Controle de Aplicativos do Windows Defender](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): o HoloLens 2 dá suporte ao WDAC, que permite que o administrador de TI envie por push as políticas de controle de aplicativo para o dispositivo. Encontre mais informações em [Usar o WDAC em dispositivos HoloLens 2 com o MSFT Intune](/mem/intune/configuration/custom-profile-hololens). 

Os administradores de TI podem gerenciar o comportamento do SmartScreen por meio de [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) e o comportamento do navegador por meio [destas políticas](/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

