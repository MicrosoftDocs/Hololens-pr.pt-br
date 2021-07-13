---
title: Recursos comerciais
description: Saiba mais sobre os recursos do Microsoft HoloLens Commercial Suite que tornam mais fácil para as empresas gerenciar dispositivos HoloLens.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, comercial, recursos, MDM, gerenciamento de dispositivo móvel, modo de quiosque
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397857"
---
# <a name="commercial-features"></a>Recursos comerciais

O HoloLens inclui recursos que tornam mais fácil para as empresas gerenciarem os dispositivos HoloLens.

Cada dispositivo HoloLens 2 tem recursos comerciais disponíveis.

O HoloLens (1ª geração) veio com duas opções de licenciamento: a licença de desenvolvedor e uma licença comercial. Para desbloquear os recursos comerciais do HoloLens, atualize a licença de desenvolvedor para uma licença comercial. Para comprar o Microsoft HoloLens Commercial Suite, entre em contato com seu gerente de conta Microsoft local.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Principais recursos comerciais

- **Modo de quiosque.** Você pode usar o HoloLens em experiências de demonstração usando o modo de quiosque, para limitar quais aplicativos podem ser executados.

  ![Usando o modo de quiosque, o HoloLens é iniciado diretamente no aplicativo de sua escolha.](images/201608-kioskmode-400px.png)

- **MDM (Gerenciamento de Dispositivo Móvel) para HoloLens.** Seu departamento de TI pode gerenciar vários dispositivos HoloLens simultaneamente usando soluções como o Microsoft Intune. Você pode gerenciar as configurações, selecionar aplicativos para instalar e definir as configurações de segurança adaptadas às necessidades da sua organização.

  ![O Gerenciamento de Dispositivo Móvel no HoloLens fornece gerenciamento de dispositivos de nível empresarial em vários dispositivos.](images/201608-enterprisemanagement-400px.png)

- **Windows Update para Empresas.** O Windows Update para Empresas fornece atualizações do sistema operacional controladas para dispositivos e suporte para o canal de manutenção em longo prazo.
- **Segurança de dados.** A criptografia de dados do BitLocker está habilitada no HoloLens para fornecer o mesmo nível de proteção de segurança que qualquer outro dispositivo Windows.
- **Acesso corporativo.** Qualquer pessoa em sua organização pode se conectar remotamente à rede corporativa por meio de uma rede virtual privada (VPN) em um HoloLens. O HoloLens também pode acessar redes Wi-Fi que exigem credenciais.
- **Microsoft Store para Empresas.** Seu departamento de TI também pode configurar um repositório particular corporativo, contendo somente os aplicativos da empresa para uso específico do HoloLens. Distribua os softwares corporativos com segurança ao grupo selecionado de usuários corporativos.

## <a name="feature-comparison-between-editions"></a>Comparação de recursos entre edições

|Recursos |HoloLens (1ª geração) Development Edition |HoloLens (1ª geração) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Criptografia de Dispositivo (BitLocker) | |✔️ |✔️ |
|VPN (Rede Privada Virtual) | |✔️ |✔️ |
|[Modo de quiosque](hololens-kiosk.md) | |✔️ |✔️ |
|**Gerenciamento e implantação** | | | |
|Gerenciamento de Dispositivos Móveis (MDM) | |✔️ |✔️ |
|Capacidade de bloquear o cancelamento de registro | |✔️ |✔️ |
|Acesso Wi-Fi corporativo com base em certificado | |✔️ |✔️ |
|Microsoft Store (Consumidor) |Consumidor |Filtrar usando MDM |Filtrar usando MDM |
|[Portal Comercial da Store](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Segurança e identidade** | | | |
|Entrar usando a conta do Azure AD (Azure Active Directory) |✔️ |✔️ |✔️ |
|Entrar usando a conta Microsoft (MSA) |✔️ |✔️ |✔️ |
|Credenciais da Próxima Geração com desbloqueio de PIN |✔️ |✔️ |✔️ |
|[Inicialização segura](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Manutenção e suporte** | | | |
|Atualizações automáticas do sistema ao chegarem |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|LTSC (Canal de Manutenção em Longo Prazo) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Habilitar recursos comerciais

O administrador de TI da sua organização pode configurar recursos comerciais, como Microsoft Store para Empresas, modo de quiosque e acesso Wi-Fi corporativo. A documentação do [Microsoft HoloLens](index.yml) fornece instruções passo a passo para registrar dispositivos e instalar aplicativos da Microsoft Store para Empresas.

## <a name="see-also"></a>Confira também

- [Microsoft HoloLens](index.yml)
- [Modo de quiosque](hololens-kiosk.md)
- [CSPs com suporte em dispositivos HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store para Empresas e aplicativos de linha de negócios](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Trabalhando com aplicativos de linha de negócios](/microsoft-store/working-with-line-of-business-apps)
