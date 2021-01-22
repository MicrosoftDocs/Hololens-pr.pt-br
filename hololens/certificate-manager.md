---
title: Gerenciador de certificados
description: Saiba como instalar, gerenciar e remover certificados manualmente em dispositivos de realidade misturada do HoloLens 2.
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
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283682"
---
# Gerenciador de certificados

- Ferramentas aprimoradas de auditoria, diagnóstico e validação para segurança e conformidade de dispositivos por meio do novo Gerenciador de Certificados. Esse recurso permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows Holographic, versão 20H2, estamos adicionando um Gerenciador de Certificados no aplicativo Configurações do HoloLens 2. Vá para **Configurações > Atualizar & segurança > certificados.** Esse recurso fornece uma maneira simples e amigável de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de Certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar se um certificado foi implantado corretamente ou para confirmar se ele foi removido adequadamente. 
-   **Diagnóstico:** Quando surgirem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade pretendido e está funcional pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar um certificado específico na lista rapidamente, há opções para classificar por nome, armazenar ou expirar data. Os usuários também podem pesquisar diretamente por um certificado. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **Informações.** 

A instalação do certificado atualmente dá suporte a arquivos .cer e .crt. Os proprietários de dispositivos podem instalar certificados no Computador Local e no Usuário Atual;  todos os outros usuários só podem instalar no Usuário Atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário de Configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

## Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um computador.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.
1.  Navegue **até Configurações do Aplicativo > Atualizar & segurança > certificados**e selecione Instalar um certificado.
1.  Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione **Local do Armazenamento.**
1.  Selecione **o Armazenamento de Certificados.**
1.  Clique em **Instalar**.

O certificado agora deve ser instalado no dispositivo.

## Para remover um certificado: 
1. Navegue **até Configurações do Aplicativo > Atualização e Segurança > Certificados.**
1. Procure o certificado pelo nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique **em Remover**
1. Selecione **Sim** quando solicitado a confirmação.


![Visualizador de certificados no aplicativo Configurações em Ceritifcates](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado em Configurações.](images/certificate-device-install.jpg)
