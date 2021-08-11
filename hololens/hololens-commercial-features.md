---
title: Funcionalidades e soluções do HoloLens 2
description: Saiba mais sobre os recursos do Microsoft HoloLens comercial que facilitam o gerenciamento de dispositivos HoloLens para as empresas.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2, commercial, features, mdm, mobile device management, kiosk mode, applications, identity, Bitlocker, iris, Windows Hello, Azure-powered, Autopilot, mixed reality, WDAC
ms.openlocfilehash: 5a68c4199cba20bba9d3aaa5183819975ea7b3f4
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635799"
---
# <a name="hololens-2-capabilities-and-solutions"></a>Funcionalidades e soluções do HoloLens 2

## <a name="what-can-hololens-2-do-for-you"></a>O que o HoloLens 2 pode fazer por você?

Colabore sem limites e tome decisões com precisão para aumentar a produtividade dos funcionários com os aplicativos de realidade misturada no HoloLens 2. Mantenha-se envolvido e alerta, com as mãos livres por mais tempo e com mais conforto usando os comandos de voz internos, o acompanhamento ocular e a ancoragem mundial para foco contínuo na conclusão segura de tarefas sem erros. Conecte-se com os colegas remotos em tempo real e trabalhe juntos com eles em uma ampla tela holográfica sobreposta no seu ambiente físico para resolver rapidamente os problemas no ponto de trabalho. Perceba o ROI imediatamente com um ecossistema robusto de aplicativos que têm o suporte da segurança, da confiabilidade e da escalabilidade da Microsoft.  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>Funcionalidades do HoloLens 2

O que torna o HoloLens 2 tão eficiente?

| Recurso | Descrição |
|---------|-------------|
| Ancoragem mundial | Os hologramas ancorados permanecem precisamente no local. O HoloLens 2 compreende seu workspace. Portanto, o conteúdo digital é mantido ao longo do tempo, ancorado nos objetos ou nas superfícies em que você trabalha. |
| Acompanhamento da mão | Toque, segure e mova os hologramas de maneiras naturais. O HoloLens 2 se adapta às suas mãos para uma satisfação nova em suas interações. |
| Acompanhamento ocular | Aproveite um novo nível de contexto e compreensão humana. O HoloLens 2 entende exatamente onde você está procurando. Portanto, ele pode entender sua intenção e adaptar os hologramas aos seus olhos em tempo real. |
| Habilitado para voz | Os comandos de voz internos permitem que você navegue pelo HoloLens 2 e opere-o rapidamente quando suas mãos estão ocupadas com uma tarefa. |
| Ergonômico | O HoloLens 2 é leve (3,28 kg) e inclui um sistema de ajuste de discagem para dar suporte ao uso estendido. |
| FoV grande | Expanda sua tela holográfica com telas de campo de visão grandes e de alta resolução. |
| Sem fio | Mova-se livremente, sem cabos nem pacotes externos para começar a trabalhar. |
| Habilitado para o Azure | Transmita um conteúdo 3D de alta fidelidade que pode ser ancorado em uma localização e/ou um objeto que é mantido entre os usuários com os serviços de Realidade Misturada do Azure.
| Captura de realidade mista | Documente uma experiência como uma foto ou um vídeo para compartilhar com outras pessoas em tempo real. |
| Windows Hello for Business | A autenticação biométrica baseada em íris leva você de maneira rápida e segura para o fluxo de trabalho. |
| Windows Autopilot | Configure e pré-configure serviços para o HoloLens 2 de modo que eles estejam prontos para uso em todos os locais de trabalho distribuídos. |
| Atualizações de SO | Mantenha a segurança com as atualizações de manutenção mensais e aproveite as novas funcionalidades de produtividade e capacidade de gerenciamento em versões bianuais. |
| Gerencie os dispositivos com facilidade | Gerencie vários dispositivos HoloLens 2 simultaneamente usando soluções como o Microsoft Intune, o VMware Workspace One, o MobileIron, entre outros. |
| Opere em ambientes regulamentados | O HoloLens 2 tem um amplo portfólio de dispositivos que dá suporte a ambientes altamente regulamentados, incluindo ambientes designados como Classe ISO 5.0 e Classe UL I, Divisão 2. |


## <a name="managing-hololens-2-in-your-organization"></a>Como gerenciar o HoloLens 2 na sua organização
O HoloLens 2 inclui recursos que facilitam o gerenciamento dos dispositivos HoloLens para as empresas. Alguns recursos estão incluídos no dispositivo, enquanto outros podem ser habilitados pelo [MDM (gerenciamento de dispositivo móvel)](hololens-mdm-configure.md) para o HoloLens ou por meio de [pacotes de provisionamento](hololens-provisioning.md) usando o [Designer de Configuração do Windows](app-deploy-provisioning-package.md#setup).

| Eu quero… | Solução | Descrição |  
|---------| ------------|------------|
Gerenciar a forma de entrada dos usuários finais | [**Identidade**](hololens-identity.md) | O HoloLens 2 dá suporte a vários tipos de identidades de usuário: AAD (Azure Active Directory), MSA (conta Microsoft) e contas locais.  |
| Criptografar os dados dos usuários | [**Segurança de dados**](security-encryption-data-protection.md) | A criptografia de dados do BitLocker está habilitada no HoloLens 2 para fornecer o mesmo nível de proteção de segurança que qualquer outro dispositivo Windows. | 
Gerenciar os dispositivos HoloLens em minha organização | [**Gerenciamento de dispositivo móvel**](hololens-mdm-configure.md) | Gerencie as configurações, selecione os aplicativos a serem instalados e defina configurações de segurança adaptadas à necessidade da sua organização em vários dispositivos HoloLens 2 em uma localização central. | 
|Minimizar o tempo de instalação para novos usuários e dispositivos | [**Autopilot**](hololens2-autopilot.md) | Configure o OOBE (configuração inicial pelo usuário) no Microsoft Endpoint Manager e habilite os usuários finais a prepararem os dispositivos para uso comercial com pouca ou nenhuma interação. |  
| Controlar as atualizações do sistema operacional para meus dispositivos | [**Windows Update para Empresas**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | O Windows Update para Empresas fornece atualizações do sistema operacional controladas para dispositivos e suporte para o canal de manutenção em longo prazo. |  
| Permitir o download de aplicativos específicos e LOB |[**Gerenciamento de aplicativos**](app-deploy-overview.md) | Escolha como distribuir e controlar os aplicativos para grupos selecionados dos usuários do HoloLens 2. | 
| Mostrar ou ocultar aplicativos específicos no menu Iniciar |[**Modo de quiosque**](hololens-kiosk.md) | Configure o HoloLens 2 para funcionar como um dispositivo de finalidade fixa para uso em demonstrações de aplicativos ou aplicativos de negócios dedicados. 
| Proteger meu ambiente com o bloqueio de aplicativos | [**WDAC**](windows-defender-application-control-wdac.md) | O WDAC (Controle de Aplicativos do Microsoft Defender) impede que aplicativos e processos sejam iniciados pelo usuário do dispositivo.
| Gerenciar a segurança do dispositivo com regras para aplicativos e processos | [**Políticas (CSPs)**](hololens-csp-policy-overview.md) | Os administradores de TI podem definir e implementar configurações de política usando uma lista existente de CSPs da Política compatíveis no HoloLens 2. |  
| Gerenciar a forma de conexão à Internet de um dispositivo | [**Rede e conectividade**](hololens-certificates-network.md) | Use a autenticação baseada em certificado para acessar Wi-Fi, VPNs ou recursos internos. | 
| Compartilhar o dispositivo com vários usuários | [**Telas personalizadas automaticamente**](hololens-calibration.md#auto-eye-position-support) | As telas do HoloLens 2 são ajustadas automaticamente com a AEP (Posição Automática dos Olhos), eliminando a necessidade de executar um processo de calibragem manual quando o dispositivo é [compartilhado entre usuários](hololens-multiple-users.md). |

Saiba mais sobre os [Requisitos de licenciamento](hololens-licenses-requirements.md) das soluções acima.

## <a name="next-steps"></a>Próximas etapas
> [!div class="nextstepaction"]
> [Explorar as opções do HoloLens 2](hololens2-options.md)

> [!div class="nextstepaction"]
>[Como planejar a implantação do HoloLens 2](hololens-requirements.md) 
