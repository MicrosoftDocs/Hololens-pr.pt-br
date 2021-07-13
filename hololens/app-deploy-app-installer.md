---
title: Como carregar e instalar aplicativos por meio HoloLens 2 Instalador de Aplicativo
description: Saiba como instalar e solucionar problemas de aplicativos com o instalador de aplicativo e o side load e instalar aplicativos por meio da interface do usuário.
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635578"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicativos no HoloLens 2 por meio Instalador de Aplicativo

> [!NOTE]
> Esse recurso foi disponibilizado no Windows [Holographic, versão 20H2 – Atualização de dezembro de 2020.](hololens-release-notes.md) Verifique se o dispositivo [está atualizado](hololens-update-hololens.md) para usar esse recurso.

Adicionamos **uma nova funcionalidade (Instalador de Aplicativo)** para permitir que você instale aplicativos de forma mais direta em seus HoloLens 2. O recurso estará em **por padrão para dispositivos não planejados.** Para evitar interrupções nas empresas, o instalador de aplicativo não **estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" **se qualquer** um dos seguintes for verdadeiro:

- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado com o [pacote de provisionamento](hololens-provisioning.md)
- A [Identidade do](hololens-identity.md) Usuário é o Azure AD

Agora você pode instalar aplicativos sem a necessidade de habilitar o Modo de Desenvolvedor ou usar Portal de Dispositivos.  Baixe (por USB ou por Microsoft Edge) o Pacote Appx para seu dispositivo e navegue até o Pacote Appx no Explorador de Arquivos para ser solicitado a dar início à instalação.  Como alternativa, [inicie uma instalação de uma página da Web](/windows/msix/app-installer/installing-windows10-apps-web). Assim como os aplicativos instalados do Microsoft Store ou sideload usando a funcionalidade de implantação de Aplicativo [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB do [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Assinatura e o certificado usado para assinar deve ser confiável para o dispositivo HoloLens antes que o aplicativo possa ser implantado.

## <a name="requirements"></a>Requisitos

### <a name="for-your-devices"></a>Para seus dispositivos:

Esse recurso está disponível atualmente em builds Windows Holographic 20H2 para HoloLens 2 dispositivos. Certifique-se de que todos os dispositivos que usam esse método sejam [atualizados.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Para seus aplicativos:

A Configuração da Solução do  aplicativo deve ser **Mestre** ou Versão, pois o Instalador de Aplicativo usará dependências do armazenamento. Confira mais sobre como [criar pacotes de aplicativos](/windows/msix/app-installer/create-appinstallerfile-vs).

Os aplicativos instalados por meio desse método devem ser assinados digitalmente. Você precisará usar um certificado para assinar o aplicativo. Você pode obter um certificado da Lista de AC Confiáveis da [MS;](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)nesse caso, você não precisará tomar nenhuma ação extra. Ou você pode assinar seu próprio certificado, no entanto, esse certificado precisará ser esvasado para o dispositivo.

- Como assinar aplicativos [usando a Ferramenta de Assinatura.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opções de certificado:**

- [Lista de AC confiáveis do MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Escolha um método de implantação de certificado.**

- [Os pacotes de provisionamento](hololens-provisioning.md) podem ser aplicados a dispositivos locais.
- O MDM pode ser usado para [aplicar certificados com configurações de dispositivo.](/mem/intune/protect/certificates-configure)
- Use o no Gerenciador [de Certificados do dispositivo.](certificate-manager.md)

## <a name="installation-method"></a>Método de instalação

1. Verifique se o dispositivo não é considerado gerenciado.
1. Verifique se o HoloLens 2 está ligado e se você está conectado.
1. No computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para yourdevicename\Internal Armazenamento\Downloads.
    Depois de concluir a cópia do arquivo, você poderá desconectar seu dispositivo e concluir a instalação mais tarde.
1. Em seu HoloLens 2, abra o **Menu Iniciar,** **selecione** Todos os apps e inicie o **Explorador de Arquivos** aplicativo.
1. Navegue até a pasta Downloads. Talvez seja necessário que, no painel esquerdo do aplicativo, selecione Este dispositivo **primeiro** e, em seguida, navegue até Downloads.
1. Selecione o arquivo yourapp.appxbundle.
1. O Instalador de Aplicativo será lançado. Selecione o **botão** Instalar para instalar seu aplicativo.

O aplicativo instalado será automaticamente lançado após a conclusão da instalação.

![Instalando exemplos do MRTK por meio Instalador de Aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Solução de problemas de instalação

Se o aplicativo não for instalado, verifique o seguinte para solucionar problemas:

- Seu aplicativo é um build Mestre ou Versão.
- Seu dispositivo é atualizado para um build no qual esse recurso está disponível.
- Você está [conectado à Internet.](hololens-network.md)
- Os [pontos de extremidade para o Microsoft Store](hololens-offline.md) estão configurados corretamente.  

## <a name="web-installer"></a>Instalador da Web

Os usuários podem instalar um aplicativo diretamente de um servidor Web. Esse fluxo usa o Instalador de Aplicativo combinado com um método de distribuição fácil de baixar e instalar.

### <a name="how-to-set-up-web-install"></a>Como configurar a instalação da Web:

1. Verifique se o aplicativo está configurado corretamente para instalação.
1. Siga estas [etapas para habilitar a instalação de uma página da Web](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Experiência do usuário final:

1. O usuário recebe e instala o certificado no dispositivo usando um método escolhido anteriormente acima.
1. O usuário visita a URL criada na etapa acima.

O aplicativo agora será instalado no dispositivo. Para encontrar o aplicativo, abra o **menu Iniciar** e selecione o **Todos os apps** para encontrar seu aplicativo.

- Para obter mais ajuda com a solução de problemas do método de instalação do instalador de aplicativo, visite [solucionar problemas do instalador de aplicativo.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Não há suporte para a interface do usuário durante o processo de atualização. Portanto, não há suporte para a opção ShowPrompt [nesta página](/windows/msix/app-installer/update-settings) e as opções relacionadas.

## <a name="sample-apps"></a>Aplicativos de exemplo

Experimente o Instalador de Aplicativo com um de nossos aplicativos de exemplo disponíveis. 
> [!div class="nextstepaction"]
> [Aplicativos de exemplo](/windows/mixed-reality/develop/features-and-samples)
