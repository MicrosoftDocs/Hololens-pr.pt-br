---
title: Cenários comuns – HoloLens seguro offline 2
description: Saiba como configurar uma implantação segura offline e um cenário de implantação de aplicativo com o provisionamento para dispositivos HoloLens.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308046"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Cenários comuns – HoloLens seguro offline 2

## <a name="overview"></a>Visão geral

Este guia fornece diretrizes para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para uso em ambientes seguros com as seguintes restrições:

-   Desabilite o WiFi.
-   Desabilite o BlueTooth.
-   Desabilite os microfones.
-   Impede a adição ou remoção de pacotes de provisionamento.
-   Nenhum usuário pode habilitar qualquer um dos componentes restritos acima.

## <a name="prepare"></a>Preparar

Instalação do PC com Windows 10
1. [Baixe o mais recente arquivo do sistema operacional do HoloLens 2](https://aka.ms/hololens2download) diretamente em um PC. 
   1. O suporte para essa configuração está incluído no Build 19041,1117 e superior.
1. Baixe/instale a ferramenta complementar de recuperação avançada (ARC) [do Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para seu PC
1. Baixe/instale a mais recente ferramenta do [Windows Configuration designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) do Microsoft Store para seu PC.
1. [Baixe a pasta OfflineSecureHL2_Sample com os arquivos de projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.
1. Prepare seu [aplicativo de linha de negócios offline para a implantação do PPKG](app-deploy-provisioning-package.md). 


## <a name="configure"></a>Configurar

Criar um pacote de provisionamento de configuração segura

1. Inicie a ferramenta WCD em seu computador.
1. Selecione **arquivo-> projeto aberto**.
  1. Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve ser aberto e agora você deve ter uma lista de personalizações disponíveis:

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto no WCD](images/offline-secure-sample-wcd.png)

   Configurações definidas neste pacote de provisionamento:
   
   |     Item                                                |     Configuração                       |     Descrição                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Contas/usuários                                    |     Nome de usuário local & senha    |     Para esses dispositivos offline, um único nome de usuário e uma senha deverão ser definidos e compartilhados por todos os usuários do dispositivo.          |
   |     Primeira experiência/HoloLens/SkipCalibration       |     True                          |     Ignora a calibragem durante somente a configuração inicial do dispositivo                                                                             |
   |     Primeira experiência/HoloLens/SkipTraining          |     True                          |     Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo                                                                              |
   |     Primeira experiência/HoloLens/WiFi                  |     True                          |     Ignora Wi-Fi config durante a configuração inicial do dispositivo                                                                                 |
   |     Políticas/conectividade/AllowBluetooth                |     No                            |     Desabilita o Bluetooth                                                                                                             |
   |     Políticas/experiência/AllowCortana                    |     No                            |     Desabilita a Cortana (para eliminar problemas potenciais, pois os microfones estão desabilitados)                                          |
   |     Políticas/MixedReality/MicrophoneDisabled            |     Yes                           |     Desabilita o microfone                                                                                                            |
   |     Políticas/privacidade/LetAppsAccessLocation              |     Forçar negação                    |     Impede que os aplicativos tentem acessar os dados do local (para eliminar problemas potenciais, já que o rastreamento de local está desabilitado)    |
   |     Políticas/privacidade/LetAppsAccessMicrophone            |     Forçar negação                    |     Impede que os aplicativos tentem acessar microfones (para eliminar problemas potenciais, pois os microfones estão desabilitados)           |
   |     Políticas/segurança/AllowAddProvisioningPackage       |     No                            |     Impede que qualquer pessoa Adicione pacotes de provisionamento que possam tentar substituir políticas bloqueadas.                         |
   |     Políticas/segurança/AllowRemoveProvisioningPackage    |     No                            |     Impede que qualquer pessoa Remova esse pacote de provisionamento bloqueado.                                                           |
   |     Políticas/sistema/AllowLocation                       |     No                            |     Impede que o dispositivo tente controlar os dados de localização.                                                                        |
   |     Políticas/WiFi/AllowWiFi                             |     No                            |     Desabilita Wi-Fi                                                                                                                 |

1. Em configurações de tempo de execução, selecione **contas/usuários/nome de usuário: holo/senha**.

   Anote a senha e redefina, se desejado.

1. Navegue até UniversalAppInstall/UserContextApp e [Configure o aplicativo LOB](app-deploy-provisioning-package.md) que você estará implantando nesses dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo em WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Depois de concluído, selecione o botão "exportar" e siga todos os prompts até que o pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar para este pacote em WCD.](images/offline-secure-sample-wcd-export.png)

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
