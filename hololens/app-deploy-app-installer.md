---
title: Como carregar e instalar aplicativos pelo instalador do aplicativo HoloLens 2
description: Carregar e instalar aplicativos por meio da interface do usuário
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135522"
---
# Instalar aplicativos no HoloLens 2 via instalador de aplicativos

No lançamento do Windows Insider, estamos **adicionando um novo recurso (instalador do aplicativo) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2.  Agora você pode instalar aplicativos sem precisar habilitar o modo de desenvolvedor ou usar o Device Portal.  Basta baixar (via USB ou pelo Edge) o pacote Appx para o seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.  Você também pode [iniciar uma instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos que você instala na Microsoft Store ou Sideload usando a funcionalidade de implantação do aplicativo LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiado](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de ser implantado.   

Esta atualização se alinha à área de trabalho em que o [Sideload está habilitado por padrão](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)

> [!IMPORTANT]
> No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +. [Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).

> [!NOTE]
> Para administradores de ti que desejam desabilitar esse recurso, use o nome da família de pacotes a seguir como parte da [política WDAC](windows-defender-application-control-wdac.md). Isso só bloqueará o aplicativo instalador de aplicativos, e não os aplicativos instalados de outras fontes, como a Microsoft Store ou da solução MDM.
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> É recomendável usar a [política WDAC](windows-defender-application-control-wdac.md) para controlar aplicativos, no entanto, se você quiser apenas permitir aplicativos da Microsoft Store, os dispositivos configurados para definir a política [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) explicitamente para "não permitir" só permitirão que os aplicativos sejam instalados na Microsoft Store. 

## Requisitos

### Para seus dispositivos: 
> [!NOTE]
> No momento, esse recurso só avalible no Windows Insider compilações do 19041.1377 +. [Saiba mais sobre como registrar-se nas compilações do Windows Insider](hololens-insider.md).

### Para seus aplicativos: 
A configuração da solução de seu aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja. Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Os aplicativos instalados por meio desse método devem ser assinados digitalmente. Você precisará usar um certificado para assinar o aplicativo. Você pode obter um certificado da lista de [CAS confiáveis da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), caso em que você não precisará executar nenhuma ação adicional. Ou você pode assinar seu próprio certificado, mas esse certificado precisará ser colocado no dispositivo. 
- Como assinar aplicativos [usando a ferramenta de assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opções de certificado:** 
- [Lista de CAS confiáveis da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Escolha um método de implantação de certificado.** 
- Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.
- O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Use o Gerenciador de [certificados](hololens-insider.md#certificate-manager)no dispositivo. 

## Método de instalação

1.  Verifique se o seu dispositivo do HoloLens 2 está ligado e se você está conectado.
1.  No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads. 
    Depois de concluir a cópia do seu arquivo, você pode desconectar seu dispositivo e concluir a instalação mais tarde.
1.  Em seu dispositivo do HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .
1.  Navegue até a pasta downloads. Talvez seja necessário no painel esquerdo do aplicativo selecione **este dispositivo** primeiro e, em seguida, navegue até downloads.
1.  Selecione o arquivo yourapp. appxbundle. 
1.  O instalador do aplicativo será iniciado. Selecione o botão **instalar** para instalar o aplicativo. 

O aplicativo instalado será iniciado automaticamente após a conclusão da instalação. 

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

### Solução de problemas de instalação
Se o aplicativo não tiver sido instalado, verifique o seguinte:
-   Seu aplicativo é uma compilação mestre ou de versão.
- Seu dispositivo é atualizado para uma compilação em que esse recurso está disponível. 
-   Você está [conectado à Internet](hololens-network.md).
-   Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.  

## Instalador da Web

Os usuários podem instalar um aplicativo diretamente de um servidor Web. Isso usa o instalador do aplicativo combinado com um método fácil de distribuição de download e instalação. 

### Como configurar a instalação da Web:
1.  Verifique se o aplicativo está configurado corretamente para a instalação.
1.  Siga estas [etapas para habilitar isso em uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage). 

### Experiência do usuário final:
1. O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima. 
1. O usuário visita a URL criada a partir da etapa acima.

O aplicativo agora será instalado no dispositivo. Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar seu aplicativo. 

-   Para ajudar a solucionar problemas com esse método de instalação, acesse [solucionar](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)problemas do instalador do aplicativo. 

> [!NOTE]
> Não há suporte para a interface do usuário durante o processo de atualização. Portanto, não há suporte para a opção não receber [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e opções relacionadas.

## Exemplos de aplicativos

Se quiser experimentar alguns exemplos de aplicativos, confira alguns dos exemplos disponíveis:
- [Hub de exemplos MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Produz](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Exemplos de aplicativos UWP que podem ser usados para teste](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
