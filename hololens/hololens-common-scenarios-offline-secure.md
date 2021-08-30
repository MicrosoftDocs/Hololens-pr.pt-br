---
title: cenários comuns – seguro Offline HoloLens 2
description: saiba como configurar uma implantação segura offline e um cenário de implantação de aplicativo com o provisionamento para dispositivos HoloLens.
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189113"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>cenários comuns – seguro Offline HoloLens 2

## <a name="overview"></a>Visão geral

este guia fornece diretrizes para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:

-   Desabilite o WiFi.
-   Desabilite o BlueTooth.
-   Desabilite os microfones.
-   Impede a adição ou remoção de pacotes de provisionamento.
-   Nenhum usuário pode habilitar qualquer um dos componentes restritos acima.

[![Cenário seguro offline. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Preparar

Windows 10 Configuração do computador
1. [baixe o arquivo do sistema operacional mais recente HoloLens 2](https://aka.ms/hololens2download) diretamente em um PC. 
   1. O suporte para essa configuração está incluído no Build 19041,1117 e superior.
1. baixe/instale a ferramenta complementar de recuperação avançada (ARC) [do Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para seu PC
1. baixe/instale a mais recente ferramenta de [Windows do Designer de configuração (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) do Microsoft Store para o seu PC.
1. [Baixe a pasta OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.
1. Prepare seu [aplicativo de linha de negócios offline para a implantação do PPKG](app-deploy-provisioning-package.md). 


## <a name="configure"></a>Configurar

Criar um pacote de provisionamento de configuração segura

1. Inicie a ferramenta WCD em seu computador.
1. Selecione **arquivo-> projeto aberto**.
  1. Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve ser aberto e agora você deve ter uma lista de personalizações disponíveis:

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD.](images/offline-secure-sample-wcd.png)

   Configurações definidas neste pacote de provisionamento:
   
   |     Item                                                |     Configuração                       |     Descrição                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Contas/usuários                                    |     Nome de usuário local & senha    |     Para esses dispositivos offline, um único nome de usuário e uma senha deverão ser definidos e compartilhados por todos os usuários do dispositivo.          |
   |     primeira experiência/HoloLens/SkipCalibration       |     Verdadeiro                          |     Ignora a calibragem durante somente a configuração inicial do dispositivo                                                                             |
   |     primeira experiência/HoloLens/SkipTraining          |     True                          |     Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo                                                                              |
   |     primeira experiência/HoloLens/WiFi                  |     True                          |     Ignora Wi-Fi config durante a configuração inicial do dispositivo                                                                                 |
   |     Políticas/conectividade/AllowBluetooth                |     Não                            |     Desabilita Bluetooth                                                                                                             |
   |     Políticas/experiência/AllowCortana                    |     Não                            |     desabilita Cortana (para eliminar problemas potenciais, pois os microfones estão desabilitados)                                          |
   |     Políticas/MixedReality/MicrophoneDisabled            |     Sim                           |     Desabilita o microfone                                                                                                            |
   |     Políticas/privacidade/LetAppsAccessLocation              |     Forçar negação                    |     Impede que os aplicativos tentem acessar os dados do local (para eliminar problemas potenciais, já que o rastreamento de local está desabilitado)    |
   |     Políticas/privacidade/LetAppsAccessMicrophone            |     Forçar negação                    |     Impede que os aplicativos tentem acessar microfones (para eliminar problemas potenciais, pois os microfones estão desabilitados)           |
   |     Políticas/segurança/AllowAddProvisioningPackage       |     Não                            |     Impede que qualquer pessoa Adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.                         |
   |     Políticas/segurança/AllowRemoveProvisioningPackage    |     Não                            |     Impede que qualquer pessoa Remova esse pacote de provisionamento bloqueado.                                                           |
   |     Políticas/sistema/AllowLocation                       |     Não                            |     Impede que o dispositivo tente controlar os dados de localização.                                                                        |
   |     Políticas/WiFi/AllowWiFi                             |     Não                            |     Desabilita Wi-Fi                                                                                                                 |

1. em tempo de execução Configurações, selecione **contas/usuários/nome de usuário: Holo/senha**.

   Anote a senha e redefina, se desejado.

1. Navegue até UniversalAppInstall/UserContextApp e [Configure o aplicativo LOB](app-deploy-provisioning-package.md) que você estará implantando nesses dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo em WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Depois de concluído, selecione o botão "exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote em WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implantar

1. Conexão o HL2 ao seu PC Windows 10 via cabo USB.
1. inicie a ferramenta ARC e selecione **HoloLens 2**

   ![tela inicial do HoloLens 2 limpar reflash.](images/ARC2.png)

1. Na próxima tela, selecione **seleção de pacote manual**.

   ![tela de informações do HoloLens 2 ARC.](images/arc_device_info.png)

1. Navegue até o arquivo. FFU baixado anteriormente e selecione **abrir**.
1. Na página de aviso, selecione **continuar**.

   ![tela de aviso do HoloLens 2 de dois arcos.](images/arc_warning.png)

1. aguarde até que a ferramenta ARC conclua a instalação do sistema operacional HoloLens 2.
1. Depois que o dispositivo concluir a instalação e inicializar o backup, em seu PC, navegue até o explorador de arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Arquivo PPKG no PC na janela Explorador de arquivos.](images/offline-secure-file-explorer.png)

1. no HoloLens 2, pressione a combinação de botão a seguir para executar o pacote de provisionamento: toque em **Volume baixo** e **botão de energia** ao mesmo tempo.
1. Você será solicitado a aplicar o pacote de provisionamento, selecionar **confirmar**
1. Depois que o pacote de provisionamento for concluído, selecione **OK**.
1. Em seguida, você deve ser solicitado a entrar no dispositivo com a conta local compartilhada e a senha.

## <a name="maintain"></a>Manter

Com essa configuração, é recomendável reiniciar o processo acima e refazer o flash do dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer atualizações no sistema operacional e/ou aplicativos.
