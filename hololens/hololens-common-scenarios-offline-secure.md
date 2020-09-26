---
title: Cenários comuns – HoloLens offline seguro 2
description: Uma implantação segura offline e implantação de aplicativo por meio do provisionamento.
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080457"
---
# Cenários comuns – HoloLens offline seguro 2

## Visão geral
Este guia fornece orientação para aplicar um pacote de provisionamento de exemplo que bloqueará um HoloLens 2 para ser usado em ambientes seguros com as seguintes restrições:
-   Desative o WiFi.
-   Desative o BlueTooth.
-   Desative os microfones.
-   Impede a adição ou a remoção de pacotes de provisionamento.
-   Nenhum usuário pode habilitar qualquer um dos componentes restritos acima.

## Preparar 
Configuração do Windows 10 para PC
1. [Baixe o arquivo mais recente do sistema operacional do HoloLens 2](https://aka.ms/hololens2download) diretamente em um PC. 
   1. O suporte para essa configuração está incluído no Build 19041,1117 e versões mais recentes.
1. Baixar/instalar a ferramenta avançado de recuperação (ARC) [da Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) para seu PC
1. Baixe/instale a ferramenta de configuração mais recente do [Windows Configuration designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) da Microsoft Store para seu PC.
1. [Baixe a pasta OfflineSecureHL2_Sample com os arquivos do projeto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para criar o PPKG.
1. Prepare seu [aplicativo de linha de negócios offline para a implantação do PPKG](app-deploy-provisioning-package.md). 


## Configurar
Criar um pacote de provisionamento de configuração segura

1. Inicie a ferramenta WCD em seu computador.
1. Selecione **arquivo – > Abrir projeto**.
  1. Navegue até o local da pasta OfflineSecureHL2_Sample salva anteriormente e selecione: OfflineSecureHL2_Sample.icdproj.xml
1. O projeto deve abrir e agora você deve ter uma lista de personalizações disponíveis: 

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do pacote de configuração aberto em WCD](images/offline-secure-sample-wcd.png)

Configurações definidas neste pacote de provisionamento:

|     Item                                                |     Configuração                       |     Descrição                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Contas/usuários                                    |     Nome de usuário local & senha    |     Para esses dispositivos offline, um único nome de usuário e senha precisarão ser definidos e compartilhados por todos os usuários do dispositivo.          |
|     Primeira experiência/HoloLens/SkipCalibration       |     True                          |     Ignora a calibragem durante a configuração inicial do dispositivo apenas                                                                             |
|     Primeira experiência/HoloLens/SkipTraining          |     True                          |     Ignora o treinamento do dispositivo durante a configuração inicial do dispositivo                                                                              |
|     Primeira experiência/HoloLens/WiFi                  |     True                          |     Ignora a configuração de Wi-Fi durante a configuração inicial do dispositivo                                                                                 |
|     Políticas/conectividade/AllowBluetooth                |     Não                            |     Desabilita o Bluetooth                                                                                                             |
|     Políticas/experiência/AllowCortana                    |     Não                            |     Desabilita a Cortana (para eliminar problemas em potencial, pois os microfones estão desativados)                                          |
|     Policies/MixedReality/MicrophoneDisabled            |     Sim                           |     Desabilita o microfone                                                                                                            |
|     Políticas/privacidade/LetAppsAccessLocation              |     Forçar negação                    |     Impede que os aplicativos tentem acessar dados de localização (para eliminar problemas em potencial porque o rastreamento de localização está desabilitado)    |
|     Políticas/privacidade/LetAppsAccessMicrophone            |     Forçar negação                    |     Impede que os aplicativos tentem acessar microfones (para eliminar problemas potenciais, já que os microfones estão desativados)           |
|     Políticas/segurança/AllowAddProvisioningPackage       |     Não                            |     Impede que qualquer pessoa Adicione pacotes de provisionamento que podem tentar substituir políticas bloqueadas.                         |
|     Políticas/segurança/AllowRemoveProvisioningPackage    |     Não                            |     Impede que qualquer pessoa Remova esse pacote de provisionamento bloqueado.                                                           |
|     Políticas/sistema/AllowLocation                       |     Não                            |     Impede que o dispositivo tente acompanhar os dados de localização.                                                                        |
|     Políticas/WiFi/AllowWiFi                             |     Não                            |     Desabilita Wi-Fi                                                                                                                 |

4. Em configurações de tempo de execução, selecione **contas/usuários/nome de usuário: holo/senha** 
    - Anote a senha e redefina se desejado.
5. Navegue até UniversalAppInstall/UserContextApp e [Configure o aplicativo LOB](app-deploy-provisioning-package.md) que você vai implantar nesses dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela de onde adicionar seu aplicativo em WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Depois de concluir, selecione o botão "exportar" e siga todos os avisos até que o pacote de provisionamento seja criado.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do botão Exportar deste pacote em WCD.](images/offline-secure-sample-wcd-export.png)


## Implantar
1. Conecte o HL2 ao seu PC Windows 10 via cabo USB.
1. Iniciar a ferramenta ARC e selecionar **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. Na tela seguinte, selecione **seleção manual do pacote**.
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Navegue até o arquivo. FFU baixado anteriormente e selecione **abrir**.
1. Na página de aviso, selecione **continuar**.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Aguarde até que a ferramenta ARC conclua a instalação do sistema operacional do HoloLens 2.
1. Depois que o dispositivo concluir o backup da instalação e inicialização, no seu computador, navegue até explorador de arquivos e copie o arquivo PPKG salvo anteriormente para a pasta do dispositivo.

   > [!div class="mx-imgBorder"]
   > ![PPKG arquivo no PC na janela do explorador de arquivos.](images/offline-secure-file-explorer.png)

1. No HoloLens 2, pressione a combinação de botões a seguir para executar o pacote de provisionamento: toque em **volume para baixo** e **botão de energia** ao mesmo tempo.
1. Você será solicitado a aplicar o pacote de provisionamento, selecionar **confirmar**
1. Depois que o pacote de provisionamento terminar, selecione **OK**.
1. Em seguida, você deve ser solicitado a conectar-se ao dispositivo com a conta local e a senha compartilhadas.

## Manter
Com essa configuração, é recomendável reiniciar o processo acima e reativar o dispositivo com a ferramenta ARC e aplicar um novo PPKG para fazer atualizações para o sistema operacional e/ou aplicativo (s). 

