---
title: Separação e isolamento de estado
description: Separação e isolamento de estado
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, separação de estado, separação e isolamento de estado, hololens 2, hololens2, segurança, visão geral de segurança, arquitetura de segurança, arquitetura, arquitetura do hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens 2
ms.openlocfilehash: e92e2fcbc13ad5c9e5748b1d619e387ae9a4d147
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865667"
---
# Separação e isolamento de estado

A separação e o isolamento de estado protegem partes críticas do sistema operacional do Hololens 2, como aquelas necessárias para que o sistema operacional seja inicializado em um estado confiável. Com a tecnologia de isolamento, os aplicativos não confiáveis são movidos para um ambiente de área restrita isolada, para garantir que eles não afetarão a segurança do sistema.

## Separação de estado

A separação de estado no HoloLens 2 melhora imensamente a segurança e a operacionalidade (atualização), e ajuda a proteger seus dados de aplicativo.  Separação de estado funciona da seguinte maneira:
  * O sistema operacional principal é armazenado no volume do sistema operacional principal (um SO da Microsoft confiável ou verificado atualizando o sistema operacional).
  * As partes do sistema operacional que podem ser alteradas no tempo de execução (como configurações e drivers para baixar), usam separação de estado adicional para particionar os dados e armazená-los em locais de armazenamento seguros e separados.
  * Cada local de armazenamento seguro tem políticas de segurança distintas associadas a eles, oferecendo diversas vantagens de segurança, conforme detalhado na seção a seguir.

## Benefícios da separação de estado

  * Segurança: A separação de estado em destaque no HoloLens 2 melhora significativamente a integridade da plataforma, a resistência contra malware e a proteção de dados do usuário. Ao separar a parte inalterável do sistema operacional e torná-la somente para leitura ou com integridade protegida, a separação de estado torna extremamente difícil para o malware persistir na reinicialização a frio. 
  * Atualizações: Com o HoloLens 2, uma vez que o sistema operacional principal não é modificável e foi corretamente separado do restante dos dados no dispositivo, as atualizações são simples e confiáveis.  Além disso, a separação de estado cria os alicerces vitais para atualizações muito mais rápidas, o que permite que o sistema operacional seja substituído em uma única etapa (unidade atômica).
  * Redefinição do dispositivo: A redefinição no HoloLens 2 limpa os dados gerados pelo usuário e os dados do aplicativo do usuário no dispositivo, incluindo locais de armazenamento internos e externos. Preserva os aplicativos do sistema operacional atual e os aplicativos essenciais de segurança, além dos aplicativos personalizados da Microsoft e do OEM (pré-instalado). Esses aplicativos pré-instalados podem ser reintegrados no dispositivo após a conclusão da redefinição.

### Etapas da separação de estado

A separação de estado assegura que o sistema operacional só possa ser alterado pelos componentes de dispositivos confiáveis da Microsoft e que somente o estado de alto valor tenha permissão para persistir entre reinicializações; outro estado de sistema existe somente durante a sessão de inicialização e é descartado após a reinicialização. A separação de estado retorna rapidamente o dispositivo de volta para o estado original de fabricação. Os estados do Windows Holographic for Business podem ser divididos nestas categorias distintas:
  * Sistema operacional principal – Estado inalterável
  * Dados do sistema operacional – Estado alterável 
  * Dados do usuário – Estado alterável

Cada um desses estados operacionais do HoloLens 2 estão descritos na seção a seguir.

#### Sistema operacional principal

Um estado imutável é formado por arquivos executáveis e dados inalteráveis e só podem ser alterados pela Microsoft durante a instalação das atualizações. Durante tal atualização do sistema operacional principal, uma nova imagem contendo o mais recente estado de operação desejado será habilitada.
O estado inalterável é marcado como somente leitura (ou é, caso contrário, com integridade protegida), evitando a persistência de qualquer malware com privilégios elevados. Os seguintes arquivos e dados executáveis estão protegidos no estado imutável:
  * Drivers originais do Windows Holographic
  * Binários do sistema operacional
  * Drivers originais do Windows
  * Configurações estáticas do Windows Holographic armazenadas no hive do registro do Windows (HKLM)
    * Exemplo: HKLM armazena as informações de configuração para os aplicativos instalados em um computador. Ele também armazena informações para detectar um hardware e os drivers correspondentes.
Ao protegê-los no estado imutável (integridade e proteção de somente leitura), garantimos que o sistema operacional principal sempre Inicializa num estado confiável. Além disso, quando um dispositivo é redefinido, podemos garantir que o dispositivo inicializará apenas nos componentes que estão nesta seção imutável. 

#### Dados do Sistema Operacional 

É importante observar que os arquivos e os dados executáveis que são alteráveis no tempo de execução (e que não são críticos para a função do sistema operacional), podem ser descartados e recriados quando os dados estiverem corrompidos ou comprometidos. O estado alterável de alto valor é necessário para persistir pelo sistema operacional ou é esperado que persista no desligamento do sistema operacional, e/ou entre reinicializações por cenários de dispositivos e de sistema operacional Windows com suporte. Exemplos de estado mutável de alto valor são:
  * O administrador de TI configurou as configurações do dispositivo global, como exemplo: desabilitar o local para todos os usuários.
  * Conexão de rede Wi-Fi e acesso a dispositivos de dados-lembrar de redes e senhas de conexão associadas.
  * Despejos de memória incluindo configurações e logs.
  * Drivers baixados por demanda para dispositivos recém descobertos.
Um estado alterável de alto valor no HoloLens 2 fica no local de segurança de dados do sistema operacional como um arquivo salvo no disco ou em um registro hive persistente.

#### Dados de usuários

A última categoria de estado representa os dados do usuário produzidos ou persistidos por aplicativos UWP ou do sistema operacional. Todas as pastas de usuário conhecidas, como Downloads, Documentos, Vídeos, perfis de usuários e HKEY_CURRENT_USER hive, também são armazenadas neste local. Esses dados não podem ser extraídos sem credenciais adequadas; para saber mais sobre como seus dados estão protegidos, confira [Criptografia e Proteção de Dados](security-encryption-data-protection.md).

##  Isolamento

Para alcançar esse equilíbrio, o HoloLens 2 tem um sistema operacional principal que é usado para as principais funções, como a inicialização, controle de hardware, fazer logon, etc. Há apenas dois conjuntos de aplicativos em execução no sistema operacional principal- aplicativos pré-instalados e aplicativos UWP.

## Assinatura de código

A assinatura de código digital permite a fundamentação que os executáveis e os scripts não foram modificados, já que eles foram assinados por uma fonte confiável, portanto fornecem autenticidade e integridade. As autoridades que o HoloLens 2 confia por padrão são a Microsoft e a Microsoft Store. Os administradores de TI podem adicionar novos certificados ao dispositivo por meio do [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) e [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) CSPs. Eles também podem usar a [política de AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) para confiar em sideload adicional ou [aplicativos de linha de negócios](https://docs.microsoft.com/intune/apps/lob-apps-windows). Os certificados residem no repositório de certificados do computador local, que é armazenado na HKLM/Root se estiverem usando "Dispositivo" ou em HKCU se estiverem usando "Usuário".

## Proteções do Defender
O HoloLens 2 usa os serviços Microsoft para conceder aos usuários um nível de segurança avançado:

* o [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) é habilitado automaticamente no Windows Holographic pelo SO e protege contra phishing e malware e também contra o download de arquivos potencialmente mal intencionados, no Microsoft Edge. Ele não pode ser desativado pelo usuário, mas pode ser desabilitado por meio da política de regras.

* O [Defender Firewall](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) bloqueia o tráfego de rede não autorizado de fluir de e para seu dispositivo. Ele está habilitado por padrão e não pode ser configurado pelo cliente por meio de uma política ou de ações locais. 

* [Controle de Aplicativo do Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): O HoloLens 2 oferece suporte WDAC que permite que o administrador de TI fazer o push de políticas de controle de aplicativo para o dispositivo. Mais informações podem ser encontradas no [Uso de WDAC em dispositivos do HoloLens 2 com o MSFT Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens). 

Os administradores de TI podem gerenciar o comportamento do SmartScreen por meio do [AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) e o comportamento do navegador por meio [dessas políticas](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

