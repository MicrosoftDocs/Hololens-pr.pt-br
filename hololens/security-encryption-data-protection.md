---
title: Criptografia e proteção de dados
description: Saiba mais sobre a criptografia e a proteção de dados em dispositivos HoloLens 2, incluindo a integração ao BitLocker e ao Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, Encryption, Data Protection, BitLocker Device, BitLocker, bitlocker, bitlocker encryption, azure integration,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427536"
---
# <a name="encryption-and-data-protection"></a>Criptografia e proteção de dados

A criptografia e a proteção de dados protegem os dados quando o dispositivo for perdido ou roubado e impede que os aplicativos não autorizados acessem informações confidenciais.

## <a name="bitlocker-device-encryption"></a>Criptografia do Dispositivo BitLocker

O BitLocker é um recurso de criptografia de volume completo para a proteção da integridade da mídia RO (somente leitura) e da privacidade de mídias graváveis.  Desde o início, esse recurso tem sido uma blindagem efetiva contra o acesso não autorizado aos dados durante ataques offline. O HoloLens 2 habilita a BDE (Criptografia do Dispositivo BitLocker) por padrão para proteger os dados contra qualquer acesso físico não autorizado ao dispositivo. Sempre evoluindo para atender às necessidades do futuro, a Microsoft continua investindo e aprimorando essa tecnologia.

A BDE é um recurso de proteção de dados que emprega a criptografia AES-XTS-256 em todos os volumes no layout do dispositivo separado por estado. Ela fornece criptografia no nível do dispositivo em um layout separado por estado. A Criptografia do Dispositivo BitLocker é habilitada automaticamente no sistema operacional e nos volumes de dados fixos e não pode ser desativada, mesmo por administradores de TI, para que o dispositivo esteja sempre protegido.

As chaves de criptografia da BDE são usadas para descriptografar os binários com transparência e os dados necessários para a inicialização do dispositivo. Quando o volume do sistema operacional é desbloqueado e um sistema é inicializado, outros volumes podem ser acessados por meio de uma versão específica do volume do protetor de desbloqueio automático. Nenhum outro protetor está disponível para manter a privacidade do usuário, e o drive só pode ser desbloqueado no mesmo dispositivo. A imposição RO (somente leitura) nos volumes necessários é aplicada e imposta imediatamente, começando na primeira inicialização. A chave de recuperação BitLocker não é necessária no ciclo de vida do HoloLens 2.

## <a name="azure-integration"></a>Integração do Azure 

O HoloLens 2 permite aos clientes integrar os dispositivos aos serviços do Azure. As comunicações entre os dispositivos HoloLens 2 e o Azure usam o protocolo TLS para proteger os dados no percurso entre eles mesmos e os serviços de nuvem, que oferecem autenticação forte, privacidade das mensagens e integridade. Todos os serviços do Azure dão suporte completo ao TLS 1.2 e qualquer serviço no qual os clientes estejam usando apenas o TLS 1.2 só aceita o tráfego TLS 1.2. Os padrões de criptografia do Azure para os dados em trânsito são detalhados na [Visão geral da criptografia do Azure](/azure/security/fundamentals/encryption-overview). Acesse a documentação do Azure para saber mais sobre as [melhores práticas de criptografia e segurança de dados do Azure](/azure/security/fundamentals/data-encryption-best-practices). 

O OneDrive, um exemplo de integração na nuvem ao HoloLens 2, conta com um recurso de upload automático, no qual os arquivos e os documentos podem ser carregados automaticamente na nuvem quando você está conectado à Internet. A pausa da sincronização automática de arquivos não pode ser desativada por meio da política, mas é diretamente configurável pela Experiência de Usuário. 
