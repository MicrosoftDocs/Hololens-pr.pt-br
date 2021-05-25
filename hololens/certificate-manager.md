---
title: Gerenciador de certificados
description: Saiba como instalar, gerenciar e remover manualmente certificados em dispositivos de realidade misturados do HoloLens 2.
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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397447"
---
# <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança de dispositivo e conformidade por meio do novo Gerenciador de certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows Holographic, versão 20H2, estamos adicionando um Gerenciador de certificados no aplicativo de configurações do HoloLens 2. Vá para **configurações > atualização & segurança > certificados**. Esse recurso fornece uma maneira simples e amigável de usuário para exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar que um certificado foi implantado corretamente ou de confirmar que foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade desejada e está funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para localizar um certificado específico na lista rapidamente, há opções para classificar por nome, loja ou data de validade. Os usuários também podem procurar um certificado diretamente. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **informações**. 

A instalação do certificado atualmente dá suporte a arquivos. cer e. CRT. Os proprietários de dispositivo podem instalar certificados no computador local e no usuário atual;  todos os outros usuários só podem instalar no usuário atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário de configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

## <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um PC.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.
1.  Navegue **até Configurações Aplicativo > Atualizar & Certificados**> Segurança e selecione Instalar um certificado.
1.  Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione **Local do Armazenamento**.
1.  Selecione **Armazenamento de Certificados**.
1.  Clique em **Instalar**.

O certificado agora deve ser instalado no dispositivo.

## <a name="to-remove-a-certificate"></a>Para remover um certificado: 
>[!WARNING]
> Embora você possa exibir certificados implantados no MDM no Gerenciador de Certificados, não é possível desinstalá-los no Gerenciador de Certificados. Você deve desinstalá-los por meio do MDM.
1. Navegue **até Configurações Aplicativo > Atualização e Segurança > Certificados**.
1. Pesquise o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **Remover**
1. Selecione **Sim** quando solicitada a confirmação.



![Visualizador de certificados no aplicativo Configurações em Certificados](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado em Configurações.](images/certificate-device-install.jpg)
