---
title: Cenários comuns – Segurança offline HoloLens 2
description: Saiba como configurar uma implantação segura offline e um cenário de implantação de aplicativo com provisionamento para HoloLens dispositivos.
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
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031916"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Cenários comuns – Segurança offline HoloLens 2

## <a name="overview"></a>Visão geral

Este guia fornece diretrizes para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:

-   Desabilite o WiFi.
-   Desabilite BlueTooth.
-   Desabilitar Microfones.
-   Impede a adição ou remoção de pacotes de provisionamento.
-   Nenhum usuário pode habilitar nenhum dos componentes restritos acima.

[![Cenário de segurança offline. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Preparar

Windows 10 Instalação do PC
1. [Baixe o arquivo HoloLens sistema operacional 2 mais](https://aka.ms/hololens2download) recente diretamente em um computador. 
   1. O suporte para essa configuração está incluído no Build 19041.1117 e superior.
1. Baixe/instale a ferramenta ARC (Advanced Recovery Companion) [do Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) seu computador
1. Baixe/instale a ferramenta [Windows WCD (Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) de Configuração) mais recente do Microsoft Store seu computador.
1. [Baixe a OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.
1. Prepare seu aplicativo [offline de Linha de Negócios para implantação do PPKG.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configurar

Criar um pacote de provisionamento de configuração segura

1. Iniciar a ferramenta WCD em seu computador.
1. Selecione **Arquivo -> Abrir projeto**.
  1. Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve ser aberto e agora você deve ter uma lista de Personalizações Disponíveis:

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD.](images/offline-secure-sample-wcd.png)

   Configurações definidas neste pacote de provisionamento:
   
   |     Item                                                |     Configuração                       |     Descrição                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Contas/Usuários                                    |     Nome de usuário local & senha    |     Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.          |
   |     Primeira experiência/HoloLens/SkipCalibration       |     True                          |     Ignora a calibragem somente durante a configuração inicial do dispositivo                                                                             |
   |     Primeira experiência/HoloLens/SkipTraining          |     True                          |     Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo                                                                              |
   |     Primeira experiência/HoloLens/WiFi                  |     True                          |     Ignora a configuração Wi-Fi durante a configuração inicial do dispositivo                                                                                 |
   |     Políticas/Conectividade/AllowBluetooth                |     Não                            |     Desabilita Bluetooth                                                                                                             |
   |     Políticas/Experiência/AllowCortana                    |     Não                            |     Desabilita Cortana (para eliminar possíveis problemas, pois os microfones estão desabilitados)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Sim                           |     Desabilita o microfone                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     Forçar negação                    |     Impede que os Aplicativos tentarem acessar dados de Localização (para eliminar possíveis problemas, pois o rastreamento de localização está desabilitado)    |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     Forçar negação                    |     Impede que os aplicativos tentarem acessar microfones (para eliminar possíveis problemas, pois os microfones estão desabilitados)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     Não                            |     Impede que qualquer pessoa adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     Não                            |     Impede que qualquer pessoa remova esse pacote de provisionamento bloqueado.                                                           |
   |     Policies/System/AllowLocation                       |     Não                            |     Impede que o dispositivo tenta rastrear dados de localização.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     Não                            |     Desabilita Wi-Fi                                                                                                                 |

1. Em Runtime Configurações, selecione **Contas/Usuários/UserName: Holo/Password.**

   Anote a senha e redefinir se desejar.

1. Navegue até UniversalAppInstall/UserContextApp e configure o [aplicativo LOB](app-deploy-provisioning-package.md) que você implantará nesses dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo no WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Depois de concluir, selecione o botão "Exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote no WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implantar

1. Conexão o HL2 para seu computador Windows 10 via cabo USB.
1. Iniciar a ferramenta ARC e selecionar **HoloLens 2**

   ![Tela inicial da reinstalação de imagem limpa do HoloLens 2.](images/ARC2.png)

1. Na próxima tela, selecione **Seleção manual de pacote**.

   ![HoloLens de informações do ARC 2.](images/arc_device_info.png)

1. Navegue até o arquivo .ffu baixado anteriormente e selecione **Abrir**.
1. Na página Aviso, selecione **Continuar.**

   ![HoloLens tela de aviso do ARC 2.](images/arc_warning.png)

1. Aguarde até que a ferramenta ARC conclua a instalação HoloLens sistema operacional 2.
1. Depois que o dispositivo concluir a instalação e inicializar o back-up, no computador, navegue até Explorador de Arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Arquivo PPKG no PC Explorador de Arquivos janela.](images/offline-secure-file-explorer.png)

1. No HoloLens 2, pressione a seguinte combinação de botão para executar o Pacote de Provisionamento: Toque em **Volume Para** Baixo e **Botão** de Energia ao mesmo tempo.
1. Você será solicitado a aplicar o Pacote de Provisionamento, selecione **Confirmar**
1. Depois que o pacote de provisionamento é concluído, selecione **OK.**
1. Em seguida, você deverá ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.

## <a name="maintain"></a>Manter

Com essa configuração, é recomendável reiniciar o processo acima e reflash o dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer atualizações no sistema operacional e/ou aplicativos.
