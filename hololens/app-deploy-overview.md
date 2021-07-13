---
title: Visão geral – Gerenciamento de Aplicativos
description: Começar com uma visão geral do gerenciamento de aplicativos de realidade misturada com gerenciamento de dispositivo móvel, Microsoft Store para empresas e pacotes de provisionamento.
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635544"
---
# <a name="app-management-overview"></a>Gerenciamento de Aplicativos: Visão geral

Você pode implantar aplicativos em quatro caminhos diferentes: **MDM (Mobile Gerenciamento de Dispositivos),** **Microsoft Store para Empresas**, **Microsoft Store** ou instalando-os por meio **do Provisionamento**.

## <a name="mobile-device-management-mdm"></a>Gerenciamento de Dispositivos Móveis (MDM)

Uma solução de MDM permite que os tomadores de decisões e administradores de IT instalem (push) seus aplicativos de linha de negócios internamente ou comprem aplicativos por meio da loja para um grupo de usuários. HoloLens dispositivos funcionam melhor com o Microsoft Endpoint Manager (Intune) para gerenciamento [de aplicativos.](app-deploy-intune.md) O Intune também oferece aos usuários um controle mais fino sobre aplicativos gerenciados por IT por meio da Portal da Empresa baixável.

> [!NOTE]
> As instruções a seguir são para usuários que querem gerenciar seus aplicativos com o Intune. A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.

O MDM (mobile Gerenciamento de Dispositivos) é aplicável a:

* MDM implantado + Portal da Empresa
* Aplicativos de linha de negócios (não públicos)
* Instalação manual de aplicativos disponíveis por meio Portal da Empresa
* Push do administrador por meio da política de MDM
* Atualização automática por meio do MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

A [Microsoft Store para Empresas](app-deploy-store-business.md) fornece tomadores de decisões de IT e administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos. Os administradores de gerenciar Microsoft Store aplicativos de linha de negócios privados em um inventário, além de atribuir e reutilizar licenças conforme necessário. Para obter mais informações, [visite Pré-requisitos para usar o Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business).

O Microsoft Store para Empresas é aplicável a:

* Aplicativos públicos ou de linha de negócios
* Instalação automática de aplicativos necessários por meio da associação de MDM
* O usuário baixa manualmente aplicativos
* Atualização automática

## <a name="microsoft-store-apps"></a>Aplicativos da Microsoft Store

O Microsoft Store fornece tomadores de decisões de IT e administradores em empresas para encontrar, adquirir, gerenciar e distribuir aplicativos públicos.

Este Microsoft Store é aplicável a:

* Somente aplicativos públicos
* O usuário baixa manualmente aplicativos
* Atualização automática se conectado à Internet

Para obter mais informações, visite [Aplicativos da Holographic Store.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Instalar por meio de pacotes de provisionamento

[Os pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de Linha de Negócios, permitindo que profissionais de TI e administradores instalem rapidamente aplicativos em um(s) dispositivo(s) local via USB. Essa instalação pode ser feita sem uma conexão com a Internet e com qualquer tipo de identidade.

A instalação por meio de pacotes de provisionamento é aplicável a:

* Aplicativos de linha de negócios/autodepro desenvolvidos (não públicos)
* Aplicativos públicos (se o instalador offline estiver disponível)
* Somente carregamento lateral USB
* Nenhuma atualização automática (requer atualizações manuais por meio do Pacote de Provisionamento)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicativos no HoloLens 2 por meio Instalador de Aplicativo

Usar o [Instalador de Aplicativo](app-deploy-app-installer.md) usuários pode ter uma experiência simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não está familiarizado com outros métodos de instalação de aplicativo no HoloLens. Isso pode ser feito sem a necessidade de habilitar o Modo de Desenvolvedor ou usar Portal de Dispositivos. Esse é um método simples de distribuir um aplicativo completamente criado. Independentemente de se você simplesmente deseja demonstração de seu aplicativo para outro usuário com um HoloLens ou se deseja implantar seu aplicativo, esse método funciona facilmente.

A instalação por Instalador de Aplicativo é aplicável a:

* Aplicativos de linha de negócios/autodepro desenvolvidos (não públicos)
* Somente side-load
* Não requer o modo de desenvolvedor ou o portal de dispositivos
* Fácil para o usuário final instalar
