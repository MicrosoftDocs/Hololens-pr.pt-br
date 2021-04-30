---
title: Como carregar e instalar aplicativos por meio do instalador de aplicativo do HoloLens 2
description: Saiba como instalar e solucionar problemas de aplicativos com o instalador do aplicativo e a carga do lado e instalar aplicativos por meio da interface do usuário.
keywords: gerenciamento de aplicativo, aplicativo, hololens, instalador de aplicativo
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308081"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicativos no HoloLens 2 por meio do instalador de aplicativo

> [!NOTE]
> Esse recurso foi disponibilizado no [Windows Holographic, versão 20H2 – atualização de dezembro de 2020](hololens-release-notes.md). Verifique se o dispositivo está [atualizado](hololens-update-hololens.md) para usar esse recurso.

**Adicionamos um novo recurso (instalador de aplicativo) para permitir que você instale aplicativos com mais perfeição** em seus dispositivos de HoloLens 2. O recurso estará **ativado por padrão para dispositivos não gerenciados**. Para evitar a interrupção para as empresas, o instalador **de aplicativos não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:

- MDM [registrado](hololens-enroll-mdm.md)
- Configurado com [pacote de provisionamento](hololens-provisioning.md)
- A [identidade](hololens-identity.md) do usuário é Azure AD

Agora você pode instalar aplicativos sem a necessidade de habilitar o modo de desenvolvedor ou usar o portal do dispositivo.  Baixe (via USB ou por meio do Microsoft Edge) o pacote Appx em seu dispositivo e navegue até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.  Como alternativa, [inicie uma instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos que você instala do Microsoft Store ou Sideload usando o recurso de implantação de aplicativo de LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiável](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo de HoloLens antes que o aplicativo possa ser implantado.

## <a name="requirements"></a>Requisitos

### <a name="for-your-devices"></a>Para seus dispositivos:

Esse recurso está disponível no momento no Windows Holographic 20H2 Builds para dispositivos do HoloLens 2. Certifique-se de que todos os dispositivos que usam esse método sejam [atualizados](hololens-update-hololens.md).

### <a name="for-your-apps"></a>Para seus aplicativos:

A configuração da solução do aplicativo deve ser **Master** ou **Release** , uma vez que o instalador do aplicativo usará dependências da loja. Veja mais sobre a [criação de pacotes de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Os aplicativos instalados por meio desse método devem ser assinados digitalmente. Você precisará usar um certificado para assinar o aplicativo. Você pode obter um certificado da lista de [AC confiável da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), caso em que você não precisará realizar nenhuma ação extra. Ou você pode assinar seu próprio certificado, no entanto, o certificado precisará ser enviado por push para o dispositivo.

- Como assinar aplicativos [usando a ferramenta de assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opções de certificado:**

- [Lista de AC confiável da MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Escolha um método de implantação de certificado.**

- Os [pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.
- O MDM pode ser usado para [aplicar certificados com configurações de dispositivo](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Use o no [Gerenciador de certificados](certificate-manager.md)do dispositivo.

## <a name="installation-method"></a>Método de instalação

1. Verifique se o dispositivo não é considerado gerenciado.
1. Verifique se o dispositivo do HoloLens 2 está ligado e se você está conectado.
1. Em seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.
    Depois de terminar de copiar o arquivo, você pode desconectar o dispositivo e concluir a instalação mais tarde.
1. Em seu dispositivo de HoloLens 2, abra o **menu iniciar**, selecione **todos os aplicativos** e inicie o aplicativo **Explorador de arquivos** .
1. Navegue até a pasta downloads. Talvez seja necessário no painel esquerdo do aplicativo selecione primeiro **este dispositivo** e, em seguida, navegue até downloads.
1. Selecione o arquivo yourapp. appxbundle.
1. O instalador do aplicativo será iniciado. Selecione o botão **instalar** para instalar o aplicativo.

O aplicativo instalado será iniciado automaticamente após a conclusão da instalação do.

![Instalando exemplos do MRTK por meio do instalador do aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Solução de problemas de instalações

Se o aplicativo não for instalado, verifique o seguinte para solucionar o problema:

- Seu aplicativo é um Build mestre ou de versão.
- Seu dispositivo é atualizado para uma compilação em que esse recurso está disponível.
- Você está [conectado à Internet](hololens-network.md).
- Seus [pontos de extremidade para o Microsoft Store](hololens-offline.md) estão configurados corretamente.  

## <a name="web-installer"></a>Instalador da Web

Os usuários podem instalar um aplicativo diretamente de um servidor Web. Esse fluxo usa o instalador do aplicativo combinado com um método de distribuição fácil de baixar e instalar.

### <a name="how-to-set-up-web-install"></a>Como configurar a instalação da Web:

1. Verifique se seu aplicativo está configurado corretamente para instalação.
1. Siga estas [etapas para habilitar a instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Experiência do usuário final:

1. O usuário recebe e instala o certificado no dispositivo usando um método anteriormente escolhido acima.
1. O usuário visita a URL criada na etapa acima.

O aplicativo agora será instalado no dispositivo. Para localizar o aplicativo, abra o **menu iniciar** e selecione o botão **todos os aplicativos** para localizar seu aplicativo.

- Para obter mais ajuda com a solução de problemas do método de instalação do instalador de aplicativos, visite [solucionar problemas do instalador de aplicativos](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).

> [!NOTE]
> Não há suporte para a interface do usuário durante o processo de atualização. Portanto, não há suporte para a opção de não-prompt nessa [página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) e nas opções relacionadas.

## <a name="sample-apps"></a>Aplicativos de exemplo

Para experimentar o instalador do aplicativo com alguns aplicativos de exemplo, confira alguns dos nossos exemplos disponíveis:

- [Hub de exemplos do MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Surfaces](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Aplicativos de exemplo UWP que podem ser usados para teste](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
