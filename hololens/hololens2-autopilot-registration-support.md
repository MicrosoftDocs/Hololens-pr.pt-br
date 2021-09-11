---
title: Suporte para registro do Windows Autopilot no HoloLens 2
description: Saiba como obter suporte com o registro do Autopilot em dispositivos HoloLens 2.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427983"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Suporte de registro do HoloLens 2 para o Autopilot

Agora, clientes e CSPs (Provedores de Soluções na Nuvem) da Microsoft podem registrar dispositivos HoloLens 2 enviando solicitações diretamente para o Suporte da Microsoft. Esta página descreve os requisitos para os seguintes cenários de registro do Autopilot com suporte:

- **Registro do Autopilot em dispositivo HoloLens 2**. Envia uma solicitação para registrar dispositivos HoloLens 2 no Windows Autopilot.
- **Solicitação de hash de hardware para dispositivo HoloLens 2**. Envia uma solicitação para o Suporte da Microsoft para fornecer a você hashes de hardware que os clientes ou os CSPs podem usar para registrar dispositivos por conta própria usando o Microsoft Intune ou o Microsoft Partner Center.
- **Cancelamento do registro do Autopilot em dispositivo HoloLens 2**. Envia uma solicitação para excluir dispositivos do Windows Autopilot, normalmente usada em cenários de fim de vida do dispositivo.

A tabela a seguir detalha as informações que você precisará coletar *antes* de enviar solicitações de registro para o Suporte da Microsoft.

| Informações necessárias | Descrição | Registro do Autopilot  | Solicitação de hash de hardware | Cancelamento do registro do Autopilot |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  ID do locatário do Azure Active Directory    |    Sua ID de locatário do Azure Active Directory é um GUID (identificador global exclusivo) diferente do nome e do domínio de sua organização.    Para encontrar sua ID de locatário, entre no [Portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).    |     ✔️                         |                              |                         ✔️                        |
|  Nome de domínio do Azure Active Directory    |   Seu nome de domínio de nível superior, por exemplo, contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Prova de propriedade    |   Verifique a prova de propriedade carregando o recibo de compra ou a fatura original no formato PDF. Capturas de tela não são aceitas. O recibo de compra ou a fatura deve incluir o seguinte: números de série do dispositivo. Nome da empresa.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Números de série do dispositivo    |   Carregue um arquivo do Excel no formato CSV com cada número de série de dispositivo em uma nova linha.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Enviar solicitação de suporte

> [!div class="nextstepaction"]
> [Enviar solicitação de suporte para registro do Autopilot no HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
