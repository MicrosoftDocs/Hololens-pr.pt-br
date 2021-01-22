---
title: Visão geral - Gerenciamento de Aplicativos
description: Começar com uma visão geral do gerenciamento de aplicativos de realidade misturada com gerenciamento de dispositivo móvel, Microsoft Store para Empresas e pacotes de provisionamento.
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283702"
---
# Gerenciamento de aplicativos: Visão Geral

Você pode implantar aplicativos em quatro caminhos diferentes: Gerenciamento de Dispositivo **Móvel (MDM),** **Microsoft Store**para Empresas , **Microsoft Store**ou instalando-os por meio de **provisionamento.**

## Gerenciamento de Dispositivo Móvel (MDM)

Uma solução MDM permite que os tomadores de decisões de IT e os administradores instalem automaticamente (push) seus aplicativos de linha de negócios internamente ou comprem aplicativos por meio da loja para um grupo de usuários. Os dispositivos HoloLens funcionam melhor com o Microsoft Endpoint Manager (Intune) para gerenciamento [de aplicativos.](app-deploy-intune.md) O Intune também oferece aos usuários um controle mais fino sobre aplicativos gerenciados por IT por meio da experiência baixável do Portal da Empresa.

> [!NOTE]
> As instruções a seguir são para usuários que querem gerenciar seus aplicativos com o Intune. A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.

O Gerenciamento de Dispositivo Móvel (MDM) é aplicável para:

* MDM implantado + Portal da Empresa
* Aplicativos de linha de negócios (não públicos)
* Instalação manual de aplicativos disponíveis por meio do Portal da Empresa
* Admin push through MDM policy
* Atualização automática por meio do MDM

## Microsoft Store para Empresas

A [Microsoft Store para Empresas](app-deploy-store-business.md) fornece aos tomadores de decisões de IT e aos administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos. Os administradores de IT podem gerenciar aplicativos da Microsoft Store e aplicativos privados de linha de negócios em um único inventário, além de atribuir e reutilizar licenças conforme necessário. Para obter mais informações, visite [Pré-requisitos para usar a Microsoft Store para Empresas.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)

A Microsoft Store para Empresas se aplica a:

* Aplicativos públicos ou de linha de negócios
* Instalação automática de aplicativos necessários por meio da associação MDM
* O usuário baixa aplicativos manualmente
* Atualização Automática

## Aplicativos da Microsoft Store

A Microsoft Store fornece aos tomadores de decisões de IT e aos administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos públicos.

Esta Microsoft Store é aplicável para:

* Somente aplicativos públicos
* O usuário baixa aplicativos manualmente
* Atualização automática se conectado à Internet

Para obter mais informações, visite [Aplicativos da Loja Holográfica.](https://docs.microsoft.com/hololens/holographic-store-apps)

## Instalar por meio de pacotes de provisionamento

[Os Pacotes de Provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de Linha de Negócios, permitindo que profissionais de TI e administradores instalem rapidamente aplicativos em dispositivos locais via USB. Essa instalação pode ser feita sem uma conexão com a Internet e para qualquer tipo de identidade.

A instalação por meio de pacotes de provisionamento é aplicável para:

* Aplicativos de linha de negócios/auto-desenvolvidos (não públicos)
* Aplicativos públicos (se o instalador offline estiver disponível)
* Somente carregamento lateral USB
* Nenhuma atualização automática (requer atualizações manuais por meio do Pacote de Provisionamento)

## Instalar aplicativos no HoloLens 2 por meio do Instalador de Aplicativo

Usar os usuários do [Instalador](app-deploy-app-installer.md) de Aplicativo pode ter uma experiência simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não seja familiar com outros métodos de instalação de aplicativos no HoloLens. Isso pode ser feito sem a necessidade de habilitar o Modo de Desenvolvedor ou usar o Device Portal. Esse é um método simples de distribuir um aplicativo completamente criado. Independentemente de você simplesmente desejar demonstra seu aplicativo para outro usuário com um HoloLens ou se deseja implantar seu aplicativo, esse método funciona facilmente.

A instalação por meio do Instalador de Aplicativo é aplicável para:

* Aplicativos de linha de negócios/auto-desenvolvidos (não públicos)
* Somente side-load
* Não exige o modo desenvolvedor ou o portal de dispositivos
* Fácil para o usuário final instalar
