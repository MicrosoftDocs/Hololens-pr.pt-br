---
title: Visão geral-gerenciamento de aplicativos
description: gerenciamento de aplicativos, gerenciamento e aplicativos
keywords: HoloLens, usuário, conta, aplicativo, gerenciamento de aplicativos,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252662"
---
# Gerenciamento de aplicativos: Visão Geral

Você pode implantar aplicativos em quatro caminhos diferentes: **Gerenciamento de dispositivos móveis (MDM)**, **Microsoft Store para empresas**, **Microsoft Store**ou instalando-os por meio do **provisionamento**.

## Gerenciamento de Dispositivo Móvel (MDM)

Uma solução MDM permite que os responsáveis por decisões e administradores de ti sejam instalados de forma privada (push) em seus aplicativos internos, de linha de negócios ou comprar aplicativos por meio da loja para um grupo de usuários. Os dispositivos HoloLens funcionam melhor com o Microsoft Endpoint Manager (Intune) para [Gerenciamento de aplicativos](app-deploy-intune.md). O Intune também oferece aos usuários um controle mais refinado sobre aplicativos gerenciados por ti por meio da experiência que pode ser baixada do portal da empresa.

> [!NOTE]
> As instruções a seguir são para os usuários que desejam gerenciar seus aplicativos com o Intune. A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.

O MDM (gerenciamento de dispositivo móvel) é aplicável para:

* MDM implantado + portal da empresa
* Aplicativos de linha de negócios (não públicos)
* Instalação manual de aplicativos disponíveis por meio do portal da empresa
* Push de administrador por meio de política MDM
* Atualização automática por meio de MDM

## Microsoft Store para Empresas

A [Microsoft Store para empresas](app-deploy-store-business.md) fornece aos responsáveis por decisões e administradores de ti nas empresas para localizar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos. Os administradores de ti podem gerenciar aplicativos da Microsoft Store e aplicativos de linha de negócios particulares em um único inventário, além de atribuir licenças e reutilizar licenças conforme necessário. Para obter mais informações, acesse [pré-requisitos para usar a Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

A Microsoft Store para empresas se aplica a:

* Aplicativos públicos ou de linha de negócios
* Instalação automática de aplicativos necessários por meio da Associação MDM
* O usuário baixa os aplicativos manualmente
* Atualização automática

## Aplicativos da Microsoft Store

A Microsoft Store fornece aos responsáveis por decisões e administradores de ti nas empresas para localizar, adquirir, gerenciar e distribuir aplicativos públicos.

Esta Microsoft Store é aplicável para:

* Somente aplicativos públicos
* O usuário baixa os aplicativos manualmente
* Atualização automática se estiver conectada à Internet

Para obter mais informações, visite [holográfico Store apps](https://docs.microsoft.com/hololens/holographic-store-apps).

## Instalar via pacotes de provisionamento

Os [pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de linha de negócios, permitindo que os profissionais de ti e administradores instalem rapidamente aplicativos em um ou mais dispositivos (s) locais via USB. Essa instalação pode ser feita sem conexão à Internet e para qualquer tipo de identidade.

A instalação por meio de pacotes de provisionamento é aplicável para:

* Aplicativos de linha de negócios/autodesenvolvidos (não públicos)
* Aplicativos públicos (se o instalador offline estiver disponível)
* Somente para USB no carregamento do lado USB
* Sem atualização automática (exige atualizações manuais por meio do pacote de provisionamento)

## Instalar aplicativos no HoloLens 2 via instalador de aplicativos

Usar os usuários do [instalador de aplicativos](app-deploy-app-installer.md) pode ter uma experiência simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não esteja familiarizado com outros métodos de instalação do aplicativo no HoloLens. Isso pode ser feito sem a necessidade de habilitar o modo de desenvolvedor ou usar o Device Portal. Trata-se de um método simples de distribuir um aplicativo completamente compilado. Independentemente de se você simplesmente quer fazer uma demonstração do aplicativo para outro usuário com um HoloLens ou quiser implantar seu aplicativo, esse método funciona facilmente.

A instalação por meio do instalador do aplicativo é aplicável para:

* Aplicativos de linha de negócios/autônomos (não públicos)
* Somente carregar lado a lado
* Não requer modo de desenvolvedor ou Device Portal
* É fácil instalar o usuário final
