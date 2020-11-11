---
title: Gerenciador de certificados
description: Saiba como gerenciar certificados manualmente no HoloLens 2.
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
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163212"
---
# Gerenciador de certificados

- Ferramentas aprimoradas de auditoria, diagnóstico e validação para segurança e conformidade de dispositivos por meio do novo Gerenciador de certificados. Esse recurso permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows holográfico, versão 20H2, adicionamos um Gerenciador de certificados no aplicativo Configurações do HoloLens 2. Vá para **configurações > atualizar certificados & segurança >**. Esse recurso oferece uma maneira simples e fácil de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de certificados, administradores e usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e compatíveis. 

-   **Auditoria:** Capacidade de validar se um certificado está implantado corretamente ou para confirmar se foi removido apropriadamente. 
-   **Diagnóstico:** Quando surgem problemas, é possível validar se os certificados apropriados existem no dispositivo poupa tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade e é funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em uma escala maior.

Para localizar um certificado específico na lista rapidamente, há opções para classificar por nome, loja ou data de expiração. Os usuários também podem procurar um certificado diretamente. Para exibir as propriedades de certificado individuais, selecione o certificado e clique em **informações**. 

A instalação do certificado atualmente oferece suporte a arquivos. cer e. CRT. Os proprietários de dispositivo podem instalar certificados na máquina local e no usuário atual;  todos os outros usuários podem instalar somente no usuário atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário de configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

## Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um PC.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no seu HoloLens 2.
1.  Navegue até **configurações aplicativo > atualização & segurança > certificados**e selecione instalar um certificado.
1.  Clique em **Importar arquivo** e navegue até o local onde você salvou o certificado.
1.  Selecione **local da loja**.
1.  Selecione **repositório de certificados**.
1.  Clique em **Instalar**.

Agora o certificado deve estar instalado no dispositivo.

## Para remover um certificado: 
1. Navegue até **configurações aplicativo > atualização e segurança > certificados**.
1. Procure o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **remover**
1. Selecione **Sim** quando for solicitada a confirmação.


![Visualizador de certificados no aplicativo configurações em CERITIFCATES](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado em configurações.](images/certificate-device-install.jpg)
