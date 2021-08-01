---
title: Gerenciador de certificados
description: Saiba como instalar, gerenciar e remover certificados manualmente em HoloLens 2 dispositivos de realidade misturada.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b1869e786e3f3324494cecbfd596f61811e1893
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009316"
---
# <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança e conformidade do dispositivo por meio do novo Gerenciador de Certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows Holographic, versão 20H2, estamos adicionando um Gerenciador de Certificados no HoloLens 2 Configurações aplicativo. Vá para **Configurações > atualizar & certificados > segurança.** Esse recurso fornece uma maneira simples e amigável de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de Certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar se um certificado foi implantado corretamente ou para confirmar que ele foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, validar que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade pretendido e é funcional pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar um certificado específico na lista rapidamente, há opções para classificar por nome, armazenamento ou data de validade. Os usuários também podem pesquisar diretamente um certificado. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **Informações.** 

Atualmente, a instalação do certificado dá suporte a arquivos .cer e .crt. Os proprietários do dispositivo podem instalar certificados no Computador Local e no Usuário Atual;  todos os outros usuários só podem instalar no Usuário Atual.

## <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Conexão seu HoloLens 2 em um computador.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.
1.  Navegue até Configurações Aplicativo > Atualizar **& Certificados**> Segurança e selecione Instalar um certificado.
1.  Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione **Local do Armazenamento**.
1.  Selecione **Armazenamento de Certificados**.
1.  Clique em **Instalar**.

O certificado agora deve ser instalado no dispositivo.

![Visualizador de certificados no Configurações em Certificados.](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado Configurações.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Para remover um certificado:

> [!WARNING]
> Usando o Gerenciador de Certificados, os usuários só podem remover certificados instalados diretamente da Configurações interface do usuário. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo e não poderá ser removido do Gerenciador de Certificados. Embora você possa exibir certificados implantados no MDM no Gerenciador de Certificados, não é possível desinstalá-los lá. Você deve desinstalá-los por meio do MDM.

1. Navegue **até Configurações aplicativo > certificados de atualização e > segurança.**
1. Pesquise o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **Remover**
1. Selecione **Sim** quando solicitada a confirmação.

