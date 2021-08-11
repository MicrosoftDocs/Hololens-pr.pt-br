---
title: Visão geral – gerenciamento de aplicativos
description: Comece com uma visão geral do gerenciamento de aplicativos de realidade misturada com gerenciamento de dispositivo móvel, Microsoft Store para empresas e pacotes de provisionamento.
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
ms.openlocfilehash: 019700c7e35f31c234c9fe69870cae54b3364b631253c37a17d8eaa0fe3053bd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665226"
---
# <a name="app-management-overview"></a>Gerenciamento de aplicativos: visão geral

você pode implantar aplicativos em quatro caminhos diferentes: **MDM (gerenciamento de dispositivo móvel)**, **Microsoft Store para Empresas**, **Microsoft Store** ou instalando-os por meio de **provisionamento**.

## <a name="mobile-device-management-mdm"></a>Gerenciamento de Dispositivos Móveis (MDM)

Uma solução de MDM permite que os administradores e tomadores de decisões de ti instalem de forma privada (push) seus aplicativos internos de linha de negócios ou comprem aplicativos por meio da loja para um grupo de usuários. HoloLens dispositivos funcionam melhor com o Microsoft Endpoint Manager (Intune) para [gerenciamento de aplicativos](app-deploy-intune.md). o Intune também oferece aos usuários um controle mais refinado sobre aplicativos gerenciados por ti por meio da experiência Portal da Empresa baixável.

> [!NOTE]
> As instruções a seguir são para os usuários que desejam gerenciar seus aplicativos com o Intune. A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.

O MDM (gerenciamento de dispositivo móvel) é aplicável para:

* MDM implantado + Portal da Empresa
* Aplicativos de linha de negócios (não públicos)
* instalação Manual de aplicativos disponíveis por meio do Portal da Empresa
* Push de administrador por meio da política de MDM
* Atualizar automaticamente por meio do MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

o [Microsoft Store para Empresas](app-deploy-store-business.md) fornece aos tomadores de decisão de ti e administradores em empresas para localizar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos. os administradores de ti podem gerenciar aplicativos Microsoft Store e aplicativos de linha de negócios privados em um único inventário, além de atribuir e reutilizar licenças conforme necessário. para obter mais informações, visite [pré-requisitos para usar o Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business).

o Microsoft Store para Empresas é aplicável para:

* Aplicativos públicos ou de linha de negócios
* Instalação automática de aplicativos necessários por meio da Associação de MDM
* O usuário baixa manualmente os aplicativos
* Atualização automática

## <a name="microsoft-store-apps"></a>Aplicativos da Microsoft Store

o Microsoft Store fornece aos tomadores de decisão de ti e administradores em empresas para localizar, adquirir, gerenciar e distribuir aplicativos públicos.

esse Microsoft Store é aplicável para:

* Somente aplicativos públicos
* O usuário baixa manualmente os aplicativos
* Atualização automática se estiver conectada à Internet

Para obter mais informações, visite [aplicativos da Holographic Store](/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Instalar por meio de pacotes de provisionamento

Os [pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de linha de negócios, permitindo que os profissionais de ti e os administradores instalem aplicativos rapidamente em um dispositivo local via USB. Essa instalação pode ser feita sem uma conexão com a Internet e para qualquer tipo de identidade.

A instalação por meio de pacotes de provisionamento é aplicável para:

* Aplicativos de linha de negócios/desenvolvidos automaticamente (não públicos)
* Aplicativos públicos (se o instalador offline estiver disponível)
* Somente carregamento USB
* Nenhuma atualização automática (requer atualizações manuais por meio do pacote de provisionamento)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>instalar aplicativos no HoloLens 2 por meio do instalador de aplicativo

Usar os usuários do [instalador do aplicativo](app-deploy-app-installer.md) pode ter uma experiência que seja simples para instalar aplicativos em dispositivos locais ou compartilhar um aplicativo com outra pessoa que não esteja familiarizado com outros métodos de instalação do aplicativo em HoloLens. Isso pode ser feito sem a necessidade de habilitar o modo de desenvolvedor nem usar o portal do dispositivo. Esse é um método simples de distribuir um aplicativo totalmente compilado. independentemente de se você simplesmente deseja demonstrar seu aplicativo para outro usuário com um HoloLens, ou você gostaria de implantar seu aplicativo, esse método funciona facilmente.

A instalação por meio do instalador do aplicativo é aplicável para:

* Aplicativos de linha de negócios/auto desenvolvidos (não públicos)
* Somente carregamento lateral
* Não requer o modo de desenvolvedor ou o portal do dispositivo
* Fácil de instalar o usuário final
