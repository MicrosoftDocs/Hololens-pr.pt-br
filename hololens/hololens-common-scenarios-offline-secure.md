---
title: Cenários comuns – HoloLens Seguro Offline 2
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283411"
---
# Cenários comuns – HoloLens Seguro Offline 2

## Visão geral

Este guia fornece orientações para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:
-   Desabilitar WiFi.
-   Desabilitar BlueTooth.
-   Desabilitar microfones.
-   Impede a adição ou remoção de pacotes de provisionamento.
-   Nenhum usuário pode habilitar nenhum dos componentes restritos acima.

## Preparar

Configuração do computador Windows 10
1. Baixe o arquivo do sistema operacional mais recente do [HoloLens 2](https://aka.ms/hololens2download) diretamente para um computador. 
   1. O suporte para essa configuração está incluído no Build 19041.1117 e superior.
1. Baixar/instalar a ferramenta Advanced Recovery Companion (ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) em seu computador
1. Baixe/instale a ferramenta mais recente do Designer de Configuração [do Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store para seu computador.
1. [Baixe a OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.
1. Prepare seu aplicativo [offline de linha de negócios para implantação ppkg](app-deploy-provisioning-package.md). 


## Configurar

Criar um pacote de provisionamento de configuração segura

1. Iniciar a ferramenta WCD em seu computador.
1. Select **File -> Open project**.
  1. Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve ser aberto e agora você deve ter uma lista de Personalizações Disponíveis: 

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)

Configurações definidas neste pacote de provisionamento:

|     Item                                                |     Configuração                       |     Descrição                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Contas/usuários                                    |     Local User Name & Password    |     Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.          |
|     Primeira Experiência/ HoloLens/SkipCalibration       |     True                          |     Ignora a calibragem somente durante a configuração inicial do dispositivo                                                                             |
|     Primeira Experiência/ HoloLens/SkipTraining          |     True                          |     Ignora o treinamento de dispositivos durante a configuração inicial do dispositivo                                                                              |
|     Primeira Experiência/ HoloLens/WiFi                  |     True                          |     Ignora Wi-Fi configuração durante a configuração inicial do dispositivo                                                                                 |
|     Policies/Connectivity/AllowBluetooth                |     Não                            |     Desabilita o Bluetooth                                                                                                             |
|     Policies/Experience/AllowCortana                    |     Não                            |     Desabilita a Cortana (para eliminar possíveis problemas, pois os microfones estão desabilitados)                                          |
|     Policies/MixedReality/MicrophoneDisabled            |     Sim                           |     Desabilita o microfone                                                                                                            |
|     Policies/Privacy/LetAppsAccessLocation              |     Forçar negação                    |     Impede que os aplicativos tentam acessar dados de localização (para eliminar possíveis problemas, pois o rastreamento de localização está desabilitado)    |
|     Policies/Privacy/LetAppsAccessMicrophone            |     Forçar negação                    |     Impede que os aplicativos tentam acessar microfones (para eliminar possíveis problemas, pois os microfones estão desabilitados)           |
|     Policies/Security/AllowAddProvisioningPackage       |     Não                            |     Impede que qualquer pessoa adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.                         |
|     Policies/Security/AllowRemoveProvisioningPackage    |     Não                            |     Impede que qualquer pessoa remova esse pacote de provisionamento bloqueado.                                                           |
|     Policies/System/AllowLocation                       |     Não                            |     Impede que o dispositivo tentar rastrear dados de localização.                                                                        |
|     Policies/WiFi/AllowWiFi                             |     Não                            |     Desabilita Wi-Fi                                                                                                                 |

4. Em Configurações de Tempo de Execução, Selecione **Contas/Usuários / Nome de Usuário: Holo / Senha** 
    - Anote a senha e redefinir, se desejado.
5. Navegue até UniversalAppInstall / UserContextApp e configure o aplicativo [LOB](app-deploy-provisioning-package.md) que você implantará nesses dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo no WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Depois de concluir, selecione o botão "Exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote no WCD.](images/offline-secure-sample-wcd-export.png)


## Implantar

1. Conecte o HL2 ao seu computador Windows 10 por meio de cabo USB.
1. Iniciar a ferramenta ARC e selecionar **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. Na próxima tela, selecione **Seleção manual de pacote.**
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Navegue até o arquivo .ffu baixado anteriormente e selecione **Abrir**.
1. Na página Aviso, selecione **Continuar**.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.
1. Depois que o dispositivo concluir a instalação e inicializar o back-up, no computador, navegue até o Explorador de Arquivos e copie o arquivo PPKG salvo anteriormente na pasta do dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Arquivo PPKG no computador na janela do Explorador de Arquivos.](images/offline-secure-file-explorer.png)

1. No HoloLens 2, pressione a combinação do botão a seguir para **** executar o Pacote de Provisionamento: toque em **Aumentar o Volume** e no Botão Ligar/Desligar ao mesmo tempo.
1. You will be prompted to apply the Provisioning Package, select **Confirm**
1. Depois que o pacote de provisionamento é concluído, selecione **OK**.
1. Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.

## Manter

Com essa configuração, é recomendável reiniciar o processo acima e reflash o dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer quaisquer atualizações para o sistema operacional e/ou aplicativos. 

