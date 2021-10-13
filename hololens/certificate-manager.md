---
title: Gerenciador de certificados
description: saiba como instalar, gerenciar e remover manualmente certificados em HoloLens 2 dispositivos com realidade misturada.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: af9c6634ddbb40acace9a2abf8dd933ec05704de
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924391"
---
# <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança de dispositivo e conformidade por meio do novo Gerenciador de certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

no Windows Holographic, versão 20H2, estamos adicionando um gerenciador de certificados no aplicativo HoloLens 2 Configurações. vá para **Configurações > atualizar & segurança > certificados**. Esse recurso fornece uma maneira simples e amigável de usuário para exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade.

-   **Auditoria:** Capacidade de validar que um certificado foi implantado corretamente ou de confirmar que foi removido adequadamente.
-   **Diagnóstico:** Quando surgem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas.
-   **Validação:** Verificar se um certificado atende à finalidade desejada e está funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para localizar um certificado específico na lista rapidamente, há opções para classificar por nome, loja ou data de validade. Os usuários também podem procurar um certificado diretamente. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **informações**.

A instalação do certificado atualmente dá suporte a arquivos. cer e. CRT. Os proprietários de dispositivo podem instalar certificados no computador local e no usuário atual;  todos os outros usuários só podem instalar no usuário atual.

## <a name="to-install-a-certificate"></a>Para instalar um certificado:

1.  Conexão seu HoloLens 2 a um PC.
1.  coloque o arquivo de certificado que você deseja instalar em um local no seu HoloLens 2.
1.  navegue até **Configurações aplicativo > atualizar & segurança > certificados** e selecione instalar um certificado.
1.  Clique em **Importar arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione o **local do repositório**.
1.  Selecione **repositório de certificados**.
1.  Clique em **Instalar**.

O certificado agora deve estar instalado no dispositivo.

![visualizador de certificados no aplicativo Configurações em certificados.](images/certificate-viewer-device.jpg)

![imagem mostrando como usar a interface do usuário do certificado para instalar um certificado no Configurações.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Para remover um certificado:

> [!WARNING]
> usando o gerenciador de certificados, os usuários só podem remover certificados instalados diretamente da interface do usuário do Configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo e não poderá ser removido do Gerenciador de certificados. Embora você possa exibir certificados implantados no MDM no Gerenciador de Certificados, não é possível desinstalá-los lá. Você deve desinstalá-los por meio do MDM.

1. navegue até **Configurações aplicativo > atualização e segurança > certificados**.
1. Procure o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **remover**
1. Selecione **Sim** quando solicitada a confirmação.

## <a name="pfx-file-support-for-certificate-manager"></a>Suporte a arquivos PFX para o Gerenciador de certificados

- introduzido no [Windows Holographic, versão 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

 Adicionamos suporte ao Gerenciador de certificados para agora usar certificados. pfx. quando os usuários navegam para **Configurações**  >  **atualização &**  >  **certificados** de segurança e selecionam **instalar um certificado** , a interface do usuário agora dá suporte ao arquivo de certificado. pfx.
Os usuários podem importar o certificado. pfx, com a chave privada, para o repositório de usuários ou para o repositório de computadores.