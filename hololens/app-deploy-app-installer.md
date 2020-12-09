---
title: Como carregar e instalar aplicativos pelo instalador do aplicativo HoloLens 2
description: Carregar e instalar aplicativos por meio da interface do usuário
keywords: gerenciamento de aplicativos, app, hololens, instalador de aplicativos
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 53937881d6569e6aaa17d7e60083381b13502b87
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201365"
---
# Instalar aplicativos no HoloLens 2 via instalador de aplicativos


Estamos **adicionando uma nova funcionalidade (instalador de aplicativos) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2. O recurso estará **ativado por padrão para dispositivos não gerenciados**. Para evitar interrupções em empresas, o instalador do aplicativo **não estará disponível para dispositivos gerenciados** no momento.  

> [!NOTE]
> Esse recurso foi disponibilizado no [Windows holográfico, versão 20H2 – atualização de dezembro de 2020](hololens-release-notes.md). Verifique se o seu dispositivo está [atualizado](hololens-update-hololens.md) para usar este recurso.

**Adicionamos um novo recurso (instalador de aplicativos) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2. O recurso estará **ativado por padrão para dispositivos não gerenciados**. Para evitar interrupções em empresas, o instalador do aplicativo **não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:
- MDM [registrado](hololens-enroll-mdm.md)
- Configurado com o [pacote de provisionamento](hololens-provisioning.md)
- A [identidade](hololens-identity.md) do usuário é AAD

Agora você pode instalar aplicativos sem precisar habilitar o modo de desenvolvedor ou usar o Device Portal.  Basta baixar (via USB ou pelo Edge) o pacote Appx para o seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.  Você também pode [iniciar uma instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos que você instala na Microsoft Store ou Sideload usando a funcionalidade de implantação do aplicativo LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiado](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de ser implantado.   

## Requisitos

### Para seus dispositivos: 
No momento, isso é avalible em [compilações do Windows Insider](hololens-insider.md) para dispositivos do HoloLens 2. Certifique-se de que todos os dispositivos que usam esse método são [atualizados](hololens-update-hololens.md). 

### Para seus aplicativos: 
A configuração da solução de seu aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja. Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Os aplicativos instalados por meio desse método devem ser assinados digitalmente. Você precisará usar um certificado para assinar o aplicativo. Você pode obter um certificado da lista de [CAS confiáveis da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), caso em que você não precisará executar nenhuma ação adicional. Ou você pode assinar seu próprio certificado, mas esse certificado precisará ser colocado no dispositivo. 
- Como assinar aplicativos [usando a ferramenta de assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opções de certificado:** 
- [Lista de CAS confiáveis da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Escolha um método de implantação de certificado.** 
- Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.
- O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Use o Gerenciador de [certificados](certificate-manager.md)no dispositivo. 

## Método de instalação

1.  Certifique-se de que seu dispositivo não seja considerado gerenciado.
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
