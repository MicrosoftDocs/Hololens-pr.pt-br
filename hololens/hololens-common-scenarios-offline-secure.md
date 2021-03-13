---
title: Cenários Comuns - Offline Secure HoloLens 2
description: Saiba como configurar um cenário de implantação de aplicativo e implantação de aplicativo seguro offline com provisionamento para dispositivos HoloLens.
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407566"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Cenários Comuns - Offline Secure HoloLens 2

## <a name="overview"></a>Visão geral

Este guia fornece orientações para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:

-   Desabilitar WiFi.
-   Desabilitar BlueTooth.
-   Desabilitar microfones.
-   Impede a adição ou remoção de pacotes de provisionamento.
-   Nenhum usuário pode habilitar nenhum dos componentes restritos acima.

## <a name="prepare"></a>Preparar

Instalação do computador windows 10
1. Baixe o arquivo operacional mais recente do [HoloLens 2](https://aka.ms/hololens2download) diretamente para um computador. 
   1. O suporte para essa configuração está incluído no Build 19041.1117 e acima.
1. Baixar/instalar a ferramenta Arc (Advanced Recovery Companion) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para o computador
1. Baixe/instale a ferramenta mais recente do Designer de Configuração do [Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store para seu computador.
1. [Baixe a OfflineSecureHL2_Sample com os arquivos do projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.
1. Prepare seu aplicativo [de Linha de Negócios offline para implantação do PPKG.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configurar

Criar um pacote de provisionamento de configuração segura

1. Iniciar a ferramenta WCD em seu computador.
1. Selecione **Arquivo -> Abrir projeto**.
  1. Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve ser aberto e agora você deve ter uma lista de Personalizações Disponíveis:

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)

   Configurações definidas neste pacote de provisionamento:
   
   |     Item                                                |     Configuração                       |     Descrição                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Contas/Usuários                                    |     Nome de usuário local & Senha    |     Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.          |
   |     Primeira Experiência / HoloLens / SkipCalibration       |     True                          |     Ignora a calibragem somente durante a configuração inicial do dispositivo                                                                             |
   |     Primeira Experiência / HoloLens / SkipTraining          |     True                          |     Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo                                                                              |
   |     Primeira Experiência / HoloLens / WiFi                  |     True                          |     Ignora Wi-Fi configuração inicial do dispositivo                                                                                 |
   |     Políticas/Conectividade/AllowBluetooth                |     Não                            |     Desabilita Bluetooth                                                                                                             |
   |     Políticas/Experiência/AllowCortana                    |     Não                            |     Desabilita a Cortana (para eliminar possíveis problemas, já que os microfones estão desabilitados)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Sim                           |     Desabilita o microfone                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     Negar força                    |     Impede que os aplicativos acessem dados de localização (para eliminar possíveis problemas, já que o rastreamento de local está desabilitado)    |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     Negar força                    |     Impede que os aplicativos acessem microfones (para eliminar possíveis problemas, já que os Microfones estão desabilitados)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     Não                            |     Impede que qualquer pessoa adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     Não                            |     Impede que qualquer pessoa remova esse pacote de provisionamento bloqueado.                                                           |
   |     Policies/System/AllowLocation                       |     Não                            |     Impede que o dispositivo tenta rastrear dados de localização.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     Não                            |     Desabilita Wi-Fi                                                                                                                 |

1. Em Configurações de Tempo de Execução, Selecione **Contas / Usuários / UserName: Holo / Password**.

   Observe a senha e redefinir se desejado.

1. Navegue até UniversalAppInstall /UserContextApp e configure o [aplicativo LOB](app-deploy-provisioning-package.md) que você implantará nesses dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo no WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Depois de concluir, selecione o botão "Exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote no WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implantar

1. Conecte o HL2 ao computador windows 10 por meio de cabo USB.
1. Iniciar a ferramenta ARC e selecionar **HoloLens 2**

   ![Tela inicial da limpeza da flash do HoloLens 2](images/ARC2.png)

1. Na próxima tela, selecione **Seleção manual de pacote**.

   ![Tela de informações do HoloLens 2 ARC](images/arc_device_info.png)

1. Navegue até o arquivo .ffu baixado anteriormente e selecione **Abrir**.
1. Na página Aviso, selecione **Continuar**.

   ![Tela de aviso do HoloLens 2 ARC](images/arc_warning.png)

1. Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.
1. Depois que o dispositivo concluir a instalação e inicializar o back-up, do computador navegue até o Explorador de Arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Arquivo PPKG no computador na janela Explorador de Arquivos.](images/offline-secure-file-explorer.png)

1. No HoloLens 2, pressione a combinação de botão a seguir para executar o Pacote de Provisionamento: Toque em **Volume** Para Baixo e **Botão** Desligar ao mesmo tempo.
1. Você será solicitado a aplicar o Pacote de Provisionamento, selecione **Confirmar**
1. Depois que o pacote de provisionamento é concluído, selecione **OK**.
1. Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.

## <a name="maintain"></a>Manter

Com essa configuração, é recomendável reiniciar o processo acima e reaflar o dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer qualquer atualização no sistema operacional e/ou aplicativos.
