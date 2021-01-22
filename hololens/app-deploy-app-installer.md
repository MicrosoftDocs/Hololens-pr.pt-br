---
title: Como fazer side load e instalar aplicativos por meio do Instalador de Aplicativos do HoloLens 2
description: Saiba como instalar e solucionar problemas de aplicativos com o instalador do aplicativo e a carga lateral e instalar aplicativos por meio da interface do usuário.
keywords: gerenciamento de aplicativos, aplicativo, hololens, instalador de aplicativo
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
ms.openlocfilehash: 89f48fab236fdaf58fb0bf8b29e5a3aacb3bdee3
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283732"
---
# Instalar aplicativos no HoloLens 2 por meio do Instalador de Aplicativo

> [!NOTE]
> Esse recurso foi disponibilizado no [Windows Holographic, versão 20H2 – atualização de dezembro de 2020.](hololens-release-notes.md) Certifique-se de que [seu dispositivo seja](hololens-update-hololens.md) atualizado para usar esse recurso.

Adicionamos **um novo recurso (Instalador** de Aplicativo) para permitir que você instale aplicativos mais facilmente em seus dispositivos HoloLens 2. O recurso estará **conectado por padrão para dispositivos não-manageados.** Para evitar a interrupção nas empresas, o instalador de aplicativo **não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo é considerado "gerenciado" **se qualquer** um dos seguintes for verdadeiro:

- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado com o [pacote de provisionamento](hololens-provisioning.md)
- A [identidade do](hololens-identity.md) usuário é o Azure AD

Agora você pode instalar aplicativos sem precisar habilitar o Modo de Desenvolvedor ou usar o Device Portal.  Baixe (por USB ou por meio do Microsoft Edge) o Appx Bundle para seu dispositivo e navegue até o Pacote Appx no Explorador de Arquivos para ser solicitado a dar início à instalação.  Como alternativa, [inicie uma instalação a partir de uma página da Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Assim como os aplicativos instalados da Microsoft Store ou sideload usando o recurso de implantação [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) do aplicativo [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) LOB do MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Assinatura e o certificado usado para assinar deve ser confiável para o dispositivo HoloLens antes que o aplicativo possa ser implantado.

## Requisitos

### Para seus dispositivos:

 está atualmente disponível em builds do Windows Holographic 20H2 para dispositivos HoloLens 2. Certifique-se de que todos os dispositivos que usam esse método sejam [atualizados.](hololens-update-hololens.md)

### Para seus aplicativos: 
A Configuração da Solução do **** aplicativo deve ser **Mestre** ou Versão, pois o Instalador de Aplicativo usará dependências da loja. Veja mais sobre [como criar pacotes de aplicativos.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)

Os aplicativos instalados por meio desse método devem ser assinados digitalmente. Você precisará usar um certificado para assinar o aplicativo. Você pode obter um certificado da lista de CA confiáveis do [MS.](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)Nesse caso, não será necessário tomar nenhuma ação extra. Ou você pode assinar seu próprio certificado, no entanto, esse certificado precisará ser emitido para o dispositivo.

- Como assinar [aplicativos usando a Ferramenta de Assinatura.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opções de certificado:**

- [Lista de CA confiáveis do MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Escolha um método de implantação de certificado.**

- [Os Pacotes de Provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.
- O MDM pode ser usado para [aplicar certificados com configurações de dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- Use o Gerenciador de [Certificados no dispositivo.](certificate-manager.md)

## Método de instalação

1. Verifique se o dispositivo não é considerado gerenciado.
1. Verifique se o dispositivo HoloLens 2 está ligado e se você está conectado.
1. Em seu computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para yourdevicename\Internal Storage\Downloads.
    Depois de terminar de copiar o arquivo, você poderá desconectar o dispositivo e concluir a instalação mais tarde.
1. No dispositivo HoloLens 2, abra o **Menu Iniciar,** selecione **Todos os** aplicativos e inicie o aplicativo **Explorador de** Arquivos.
1. Navegue até a pasta Downloads. Talvez seja necessário que, no painel esquerdo do aplicativo, selecione **Este** dispositivo primeiro e, em seguida, navegue até Downloads.
1. Selecione o arquivo yourapp.appxbundle.
1. O Instalador de Aplicativo será lançado. Selecione o **botão Instalar** para instalar seu aplicativo.

O aplicativo instalado será automaticamente lançado após a conclusão da instalação.

![Instalando exemplos de MRTK por meio do Instalador de Aplicativo](images/hololens-app-installer-picture.jpg)

### Solução de problemas de instalação

Se o aplicativo não tiver êxito na instalação, verifique o seguinte para solucionar problemas:

- Seu aplicativo é uma complicação Master ou Release.
- Seu dispositivo é atualizado para um build no qual esse recurso está disponível.
- Você está [conectado à Internet.](hololens-network.md)
- Seus [pontos de extremidade para a Microsoft Store](hololens-offline.md) estão configurados corretamente.  

## Instalador da Web

Os usuários podem instalar um aplicativo diretamente de um servidor Web. Esse fluxo usa o Instalador de Aplicativo combinado com um método de distribuição fácil de baixar e instalar.

### Como configurar a instalação da Web:

1. Certifique-se de que seu aplicativo está configurado corretamente para instalação.
1. Siga estas [etapas para habilitar a instalação a partir de uma página da Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### Experiência do usuário final:

1. O usuário recebe e instala o certificado no dispositivo usando um método escolhido anteriormente acima.
1. O usuário visita a URL criada na etapa acima.

O aplicativo agora será instalado no dispositivo. Para encontrar o aplicativo, abra o **menu Iniciar** e selecione o botão Todos os **aplicativos** para encontrar seu aplicativo.

- Para obter mais ajuda com a solução de problemas do método de instalação do instalador de aplicativo, visite [solucionar problemas do instalador de aplicativo.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> A interface do usuário durante o processo de atualização não é suportada. Portanto, a opção ShowPrompt [nesta página e](https://docs.microsoft.com/windows/msix/app-installer/update-settings) as opções relacionadas não são suportadas.

## Aplicativos de exemplo

Para testar o Instalador de Aplicativo com alguns aplicativos de exemplo, confira alguns dos nossos exemplos disponíveis:

- [Hub de Exemplos de MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Superfícies](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Aplicativos de exemplo UWP que podem ser usados para teste](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
