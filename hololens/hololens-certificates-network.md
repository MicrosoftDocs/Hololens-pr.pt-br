---
title: Preparar os certificados e os perfis de rede para o HoloLens 2
description: Como configurar e usar certificados para redes em dispositivos do HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 460b6f42de7413e77eaec041a5ab6141ed959cf4
ms.sourcegitcommit: 9944fd2040fc1267ace1da1bd62ef36b68c7f318
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015513"
---
# Preparar os certificados e os perfis de rede para o HoloLens 2

A autenticação baseada em certificado é um requisito comum para os clientes que usam o HoloLens 2. Você pode exigir que os certificados acessem o Wi-Fi, se conectar a soluções VPN ou acessar recursos internos da sua organização.

Como os dispositivos do HoloLens 2 geralmente são associados ao Azure Active Directory (Azure AD) e gerenciados pelo Intune ou outro provedor MDM, você precisará implantar esses certificados usando um SCEP (Protocolo de Registro de Certificado Simples) ou uma infraestrutura de certificado PKCS (Padrão de Criptografia por Chave Pública) integrada à sua solução MDM.

## Requisitos de certificado
Os certificados raiz são necessários para a implantação de certificados por meio de uma infraestrutura SCEP ou PKCS. Outros aplicativos e serviços em sua organização podem exigir que os certificados raiz sejam implantados em seus dispositivos do HoloLens 2 também. 

## Requisitos de conectividade Wi-Fi
Para permitir que um dispositivo seja fornecido automaticamente com a configuração de Wi-Fi necessária para sua rede corporativa, você precisará de um perfil de configuração de Wi-Fi. Você pode configurar o Intune ou outro provedor MDM para implantar esses perfis em seus dispositivos. Se a sua segurança de rede exigir que os dispositivos façam parte do domínio local, talvez você também precise avaliar a infraestrutura de rede Wi-Fi para verificar se é compatível com dispositivos do HoloLens 2 (os dispositivos do HoloLens 2 são ingressados somente no AD do Azure).

## Implantar a infraestrutura de certificado
Se não houver nenhuma infraestrutura de SCEP ou PKCS já existente, você precisará preparar uma. Para oferecer suporte ao uso de certificados do SCEP ou PKCS para autenticação, o Intune requer o uso de um [conector de certificado](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Ao usar o SCEP com uma autoridade de certificação da Microsoft, você também deve configurar o [Serviço de Registro de Dispositivo de Rede (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Para saber mais, confira [Configurar um perfil de certificado para seus dispositivos no Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## Implantar certificados e perfil Wi-Fi/VPN
Para implantar certificados e perfis, siga estas etapas:
1.  Crie um perfil para cada um dos certificados Raiz e Intermediários (consulte [Criar perfis de certificado confiáveis](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Cada um desses perfis deve ter uma descrição que inclui uma data de vencimento no formato DD/MM/AAAA. **Os perfis de certificado sem uma data de vencimento não serão implantados.**
1.  Crie um perfil para cada certificado SCEP ou PKCS (consulte [Criar um perfil de certificado SCEP ou Criar um perfil de certificado PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada um desses perfis deve ter uma descrição que inclui uma data de vencimento no formato DD/MM/AAAA. **Os perfis de certificado sem uma data de vencimento não serão implantados.**

> [!NOTE]
> À medida que o HoloLens 2 é considerado para muitos ser um dispositivo compartilhado, vários usuários por dispositivo, é recomendável implantar Certificados de dispositivo em vez de Certificados de usuário para autenticação Wi-Fi, quando possível

3.  Crie um perfil para cada rede Wi-Fi corporativa (consulte [Configurações de Wi-Fi para Windows 10 e dispositivos posteriores](https://docs.microsoft.com/intune/wi-fi-settings-windows)). 
> [!NOTE]
> É recomendável que o perfil Wi-Fi seja [atribuído](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) aos Grupos de dispositivos, em vez de Grupos de usuários, quando possível. 

> [!TIP]
> Você também pode exportar um perfil de Wi-Fi de trabalho de um computador com Windows 10 em sua rede corporativa. Essa exportação cria um arquivo XML com todas as configurações atuais. Em seguida, importe esse arquivo para o Intune e o use como perfil de Wi-Fi para seus dispositivos do HoloLens 2. Confira [Exportar e importar configurações de Wi-Fi para dispositivos Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Crie um perfil para cada VPN corporativa (consulte [Configurações de dispositivo do Windows 10 e Windows Holographic para adicionar conexões VPN usando o Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).




