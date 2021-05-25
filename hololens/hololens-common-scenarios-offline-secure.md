---
title: Cenários comuns – HoloLens 2 seguro offline
description: Saiba como configurar uma implantação segura offline e um cenário de implantação de aplicativo com provisionamento para dispositivos HoloLens.
keywords: HoloLens, gerenciamento, offline, seguro offline
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397877"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Cenários comuns – HoloLens 2 seguro offline

## <a name="overview"></a>Visão geral

Este guia fornece diretrizes para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:

-   Desabilite o WiFi.
-   Desabilite BlueTooth.
-   Desabilitar Microfones.
-   Impede a adição ou remoção de pacotes de provisionamento.
-   Nenhum usuário pode habilitar nenhum dos componentes restritos acima.

[![Cenário de segurança offline ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Preparar

Windows 10 configuração do computador
1. Baixe o arquivo mais recente do sistema operacional [do HoloLens 2](https://aka.ms/hololens2download) diretamente em um computador. 
   1. O suporte para essa configuração está incluído no Build 19041.1117 e superior.
1. Baixe/instale a ferramenta ARC (Advanced Recovery Companion) [do Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) seu computador
1. Baixe/instale a ferramenta [WCD (Designer de Configuração do Windows)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) mais recente do Microsoft Store seu computador.
1. [Baixe a OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.
1. Prepare seu aplicativo [offline de Linha de Negócios para implantação do PPKG.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configurar

Criar um pacote de provisionamento de configuração segura

1. Iniciar a ferramenta WCD em seu computador.
1. Selecione **Arquivo -> Abrir projeto**.
  1. Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve ser aberto e agora você deve ter uma lista de Personalizações Disponíveis:

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)

   Configurações definidas neste pacote de provisionamento:
   
   |     Item                                                |     Setting                       |     Descrição                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Contas/Usuários                                    |     Nome de usuário local & senha    |     Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.          |
   |     Primeira experiência/HoloLens/SkipCalibration       |     Verdadeiro                          |     Ignora a calibragem somente durante a configuração inicial do dispositivo                                                                             |
   |     Primeira experiência/HoloLens/SkipTraining          |     Verdadeiro                          |     Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo                                                                              |
   |     Primeira experiência/HoloLens/WiFi                  |     Verdadeiro                          |     Ignora a configuração Wi-Fi durante a configuração inicial do dispositivo                                                                                 |
   |     Políticas/Conectividade/AllowBluetooth                |     No                            |     Desabilita o Bluetooth                                                                                                             |
   |     Políticas/Experiência/AllowCortana                    |     No                            |     Desabilita a Cortana (para eliminar possíveis problemas, pois os microfones estão desabilitados)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Yes                           |     Desabilita o microfone                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     Forçar negação                    |     Impede que os Aplicativos tentarem acessar dados de Localização (para eliminar possíveis problemas, pois o rastreamento de localização está desabilitado)    |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     Forçar negação                    |     Impede que os aplicativos tentarem acessar microfones (para eliminar possíveis problemas, pois os microfones estão desabilitados)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     Impede que qualquer pessoa adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Impede que qualquer pessoa remova esse pacote de provisionamento bloqueado.                                                           |
   |     Policies/System/AllowLocation                       |     No                            |     Impede que o dispositivo tenta rastrear dados de localização.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     No                            |     Desabilita Wi-Fi                                                                                                                 |

1. Em Configurações de Runtime, selecione **Contas/Usuários/UserName: Holo /Password**.

   Anote a senha e redefinir se desejar.

1. Navegue até UniversalAppInstall/UserContextApp e configure o [aplicativo LOB](app-deploy-provisioning-package.md) que você implantará nesses dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo no WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Depois de concluir, selecione o botão "Exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote no WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implantar

1. Conecte o HL2 ao seu PC com Windows 10 via cabo USB.
1. Inicie a ferramenta ARC e selecione **HoloLens 2**

   ![Tela inicial do HoloLens 2 limpar reflash](images/ARC2.png)

1. Na próxima tela, selecione **seleção de pacote manual**.

   ![Tela de informações sobre ARC 2 do HoloLens](images/arc_device_info.png)

1. Navegue até o arquivo. FFU baixado anteriormente e selecione **abrir**.
1. Na página de aviso, selecione **continuar**.

   ![Tela de aviso de arco 2 do HoloLens](images/arc_warning.png)

1. Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.
1. Depois que o dispositivo concluir a instalação e inicializar o backup, em seu PC, navegue até o explorador de arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Arquivo PPKG no PC na janela Explorador de arquivos.](images/offline-secure-file-explorer.png)

1. No HoloLens 2, pressione a combinação de botão a seguir para executar o pacote de provisionamento: toque em **volume baixo** e **botão de energia** ao mesmo tempo.
1. Você será solicitado a aplicar o pacote de provisionamento, selecionar **confirmar**
1. Depois que o pacote de provisionamento for concluído, selecione **OK**.
1. Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.

## <a name="maintain"></a>Manter

Com essa configuração, é recomendável reiniciar o processo acima e refazer o flash do dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer atualizações no sistema operacional e/ou aplicativos.
