---
title: Criptografia e proteção de dados
description: Criptografia e proteção de dados
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: segurança, hololens, criptografia, proteção de dados, dispositivo BitLocker, BitLocker, criptografia BitLocker, integração com o Azure
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: edf37e9e1461b69c1ae708f9c9e11985bb0480fd
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865657"
---
# Criptografia e proteção de dados

A criptografia e a proteção de dados protegem os dados quando o dispositivo for perdido ou roubado e impede que aplicativos não autorizados acessem informações confidenciais.

## Criptografia do Dispositivo BitLocker

O BitLocker é um recurso de criptografia de volume completo para a proteção da integridade da mídia somente leitura (RO) e da privacidade de mídias graváveis.  Desde o início, esse recurso tem sido uma blindagem efetiva contra o acesso não autorizado aos dados durante ataques offline. O HoloLens 2 permite a criptografia do dispositivo (BDE) do BitLocker por padrão para proteger os dados de qualquer acesso físico não autorizado ao dispositivo. Sempre evoluindo para atender às necessidades do futuro, a Microsoft continua investindo e aprimorando essa tecnologia.

O BDE é um recurso de proteção de dados que emprega a criptografia AES-XTS-256 em todos os volumes no layout do dispositivo separado. O BDE fornece criptografia no nível do dispositivo em um layout separado. A Criptografia de Dispositivo BitLocker é habilitada automaticamente no sistema operacional e nos volumes de dados fixos e não pode ser desativado, mesmo por administradores de TI, para que o dispositivo esteja sempre protegido.

As teclas de criptografia do BDE, em seguida, são usadas para descriptografar os binários com transparência e os dados necessários para a inicialização do dispositivo. Quando o volume do sistema operacional é desbloqueado e um sistema é inicializado, outros podem ser acessados usando uma versão de volume específica do protetor de desbloqueio automático. Nenhum outro protetor está disponível para manter a privacidade do usuário e o drive só pode ser desbloqueado no mesmo dispositivo. A imposição somente leitura (RO) em volumes necessários é aplicada e imposta imediatamente, começando pela primeira inicialização.

## Integração do Windows Azure 

O HoloLens 2 permite aos clientes de integrar seus dispositivos com o Azure Services. Comunicações entre dispositivos do HoloLens 2 e o Azure usam o protocolo TLS (Transport Layer Security) para proteger os dados viajando entre si e os serviços de nuvem que oferecem autenticação forte, privacidade da mensagem e integridade. Todos os serviços do Azure oferecem suporte completo a TLS 1.2 e em qualquer serviço em que os clientes estejam usando apenas o TLS 1.2 aceita apenas o tráfego TLS 1.2. Os padrões de criptografia do Azure para os dados em trânsito são detalhados no [visão geral da criptografia no Azure](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview). Visite a documentação do Azure para saber mais sobre [práticas recomendadas para a segurança e a criptografia de dados do Azure](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices). 

O OneDrive, um exemplo de integração em nuvem com o HoloLens 2, possui um recurso de carregamento automático, no qual seus arquivos e documentos podem ser carregados automaticamente para a nuvem quando você está conectado à Internet. Pausar a sincronização automática de arquivos não pode ser desabilitada por meio da política, mas é diretamente configurável pela UX. 
