---
title: Visão geral-gerenciamento de aplicativos
description: gerenciamento de aplicativos, gerenciamento e aplicativos
keywords: HoloLens, usuário, conta, aplicativo, gerenciamento de aplicativos,
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857870"
---
# Gerenciamento de aplicativos: visão geral

Você pode implantar aplicativos em quatro caminhos diferentes: **Gerenciamento de dispositivos móveis (MDM)**, **Microsoft Store para empresas**, **Microsoft Store**ou instalando-os por meio do **provisionamento**. 

## Gerenciamento de Dispositivo Móvel (MDM)

Uma solução MDM permite que os responsáveis por decisões e administradores de ti sejam instalados de forma privada (push) em seus aplicativos internos, de linha de negócios ou comprar aplicativos por meio da loja para um grupo de usuários. Os dispositivos HoloLens funcionam melhor com o Microsoft Endpoint Manager (Intune) para [Gerenciamento de aplicativos](app-deploy-intune.md). O Intune também oferece aos usuários um controle mais refinado sobre aplicativos gerenciados por ti por meio da experiência que pode ser baixada do portal da empresa.

> [!NOTE] 
> As instruções a seguir são para os usuários que desejam gerenciar seus aplicativos com o Intune. A Microsoft recomenda usar o Intune para gerenciamento de aplicativos e dispositivos.
    
O MDM (gerenciamento de dispositivo móvel) é aplicável para: 
* MDM implantado + portal da empresa 
* Linha de aplicativos Business (não públicos)
* Instalação manual de aplicativos disponíveis por meio do portal da empresa
* Push de administrador por meio de política MDM
* Atualização automática por meio de MDM

## Microsoft Store para Empresas

A [Microsoft Store para empresas](app-deploy-store-business.md) fornece aos responsáveis por decisões e administradores de ti nas empresas para localizar, adquirir, gerenciar e distribuir aplicativos gratuitos e pagos. Os administradores de TI podem gerenciar os aplicativos da Microsoft Store e os aplicativos privados de linha de negócios em um único inventário, além de atribuir e reutilizar licenças conforme necessário. Para obter mais informações, acesse [pré-requisitos para usar a Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).
    
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

Os [pacotes de provisionamento](app-deploy-provisioning-package.md) permitem que você instale aplicativos personalizados ou de linha de negócios, permitindo que os profissionais de ti e administradores instalem rapidamente aplicativos em um ou mais dispositivos (s) locais via USB. Isso pode ser feito sem uma conexão à Internet e para qualquer tipo de identidade.
    
A instalação por meio de pacotes de provisionamento é aplicável para: 
* Linha de aplicativos Business (não públicos)
* Aplicativos públicos (se o instalador offline estiver disponível)
* Somente o carregamento do lado USB
* Sem atualização automática (exige atualizações manuais por meio do pacote de provisionamento)