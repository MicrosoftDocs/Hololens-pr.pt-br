---
title: Notas de versão do HoloLens 2
description: Mantenha-se atualizado com todas as atualizações em cada nova versão do HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 18b0d6b304e8de8c85caeec9f3e8ba190647aaec
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308231"
---
# <a name="hololens-2-release-notes"></a>Notas de versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus dispositivos de HoloLens, continuamos lançando recursos, bugs e atualizações de segurança. Nessa página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização mais recente do HoloLens 2, você pode [verificar se há atualizações e atualizar manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a atualização completa do flash (FFU) para atualizar [seu dispositivo usando o complemento de recuperação avançada](hololens-recovery.md#clean-reflash-the-device). O [Download](https://aka.ms/hololens2download) é mantido atualizado e fornece a compilação mais recente disponível ao público em geral.

>[!NOTE]
> Estamos empolgados para começar a comprovar novos recursos para os insideres do Windows novamente. Vamos passar para o canal de desenvolvimento para as atualizações mais recentes. Continuaremos para nossas [**notas internas do HoloLens**](hololens-insider.md) , à medida que adicionamos mais recursos e atualizações às nossas compilações do Windows Insider. Fique empolgado e pronto para misturar essas atualizações em sua realidade.

Confira as notas de versão relacionadas:

- [Visite o arquivo de emulador do HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versão 20H2 – atualização de abril de 2021
- Build 19041,1144

Melhorias e correções na atualização:

- Corrige um problema em torno da linha de relatórios de status de instalação do aplicativo de negócios.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versão 1903 – atualização de abril de 2021
- Build 18362,1108

Melhorias e correções na atualização:

- Resolve um problema em que o aplicativo de configurações falha ao tentar alterar uma senha para uma conta local.

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versão 20H2-atualização de março de 2021
- Build 19041,1140

Melhorias e correções na atualização:

- Os clientes que usam AdvancedPhotoCapture ou LowLagPhotoCapture para capturar fotos com o HoloLens 2 agora podem recuperar a câmera até 3 segundos após a captura da foto.
- Correção para um vazamento de memória no serviço do portal do dispositivo, o problema causou um aumento no uso da memória pelo serviço que fazia com que outros aplicativos falhassem Alocando memória.
- Corrigido um problema em que os usuários registrados na distribuição em etapas não conseguem entrar no dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versão 1903-atualização de março de 2021
- Build 18362,1102

Melhorias e correções na atualização:

- Correção para um vazamento de memória no serviço do portal do dispositivo, o problema causou um aumento no uso da memória pelo serviço que fazia com que outros aplicativos falhassem Alocando memória.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versão 20H2-atualização de fevereiro de 2021
- Build 19041,1136

Melhorias e correções na atualização:

- Corrige um problema em relação à configuração inicial do dispositivo e à loja de atualizações do aplicativo.
- Resolve um problema em relação a atualizações e voos para versões posteriores do HoloLens.
- Removeu certificados pré-instalados não utilizados do armazenamento raiz do eSIM de dispositivos do HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versão 1903 – atualização de fevereiro de 2021
- Build 18362,1098

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas versões mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versão 20H2-atualização de janeiro de 2021
- Build 19041,1134

Melhorias e correções na atualização:

- Desempenho aprimorado durante a inicialização, retomada e troca de usuário quando há muitos usuários no dispositivo.
- Adicionado suporte arm32 para o [modo de pesquisa](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versão 1903 – atualização de janeiro de 2021
- Build 18362,1091

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas versões mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versão 20H2 – atualização de dezembro de 2020
- Build 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicativos no HoloLens 2 por meio do instalador de aplicativo

Estamos **adicionando um novo recurso (instalador do aplicativo) para permitir que você instale aplicativos com mais perfeição** em seus dispositivos de HoloLens 2. O recurso estará **ativado por padrão para dispositivos não gerenciados**. Para evitar a interrupção para as empresas, o instalador **de aplicativos não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:
- MDM [registrado](hololens-enroll-mdm.md)
- Configurado com [pacote de provisionamento](hololens-provisioning.md)
- A [identidade](hololens-identity.md) do usuário é Azure AD

Agora você pode instalar aplicativos sem a necessidade de habilitar o modo de desenvolvedor ou usar o portal do dispositivo.  Basta baixar (por USB ou por borda) o pacote Appx para seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.  Como alternativa, [inicie uma instalação de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos que você instala do Microsoft Store ou Sideload usando o recurso de implantação de aplicativo de LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiável](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo de HoloLens antes que o aplicativo possa ser implantado.

**Instruções de instalação do aplicativo.**

1.  Certifique-se de que seu dispositivo não seja considerado gerenciado
1.  Verifique se o dispositivo do seu HoloLens 2 está ligado e conectado ao seu PC
1.  Verifique se você está conectado ao dispositivo do HoloLens 2
1.  Em seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.   Depois de terminar de copiar o arquivo, você pode desconectar seu dispositivo
1.  Em seu dispositivo de HoloLens 2, abra o menu Iniciar, selecione todos os aplicativos e inicie o aplicativo explorador de arquivos.
1.  Navegue até a pasta downloads. Talvez seja necessário no painel esquerdo do aplicativo selecione primeiro este dispositivo e, em seguida, navegue até downloads.
1.  Selecione o arquivo yourapp. appxbundle.
1.  O instalador do aplicativo será iniciado. Selecione o botão instalar para instalar o aplicativo.
O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.

Você pode encontrar aplicativos de exemplo no [GitHub de exemplos do Windows universal](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar esse fluxo.

Leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o instalador do aplicativo](app-deploy-app-installer.md).  

![Instalando exemplos do MRTK por meio do instalador do aplicativo](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O rastreamento manual agora mantém o controle em vários novos casos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, apenas a posição Palm continua a ser atualizada com base na disponibilidade do usuário, enquanto as outras junções são inferidas com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência de rastreamento em movimentos como pregaria, lançando, scooping e Clapping.  Também ajuda nos casos em que a mão está perto de uma superfície ou segurando um objeto.  Quando as junções de mão estão sendo inferidas, o valor de [precisão por](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) conjunto será definido como "aproximado" em vez de "alto".
- Correção de um problema em que o PIN redefinido para contas do Azure AD mostraria um erro "algo deu errado.
- Os usuários devem ver muito menos falhas no OOBE após a inicialização de ET, íris no aplicativo de configurações, novo usuário ou notificação do sistema.
- Os usuários devem ter o fuso horário correto saindo do OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versão 1903 – atualização de dezembro de 2020
- Build 18362,1088

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa mais recente Holographic do Windows, versão 20H2 – atualização de dezembro de 2020 e o novo recurso instalador do aplicativo adicionado na compilação.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versão 20H2
- Build 19041,1128

O Windows Holographic, versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para usuários do HoloLens 2 e profissionais de ti. Do posicionamento de olho automático, para o Gerenciador de certificados em configurações, para aprimorar a funcionalidade do modo de quiosque e para novos recursos de instalação do AutoPilot. Essa nova atualização permite que as equipes de ti adotem um controle mais granular para configurar e gerenciar dispositivos HoloLens e oferece aos usuários experiências holographics ainda mais diretas. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. O número de Build principal permanecerá o mesmo e Windows Update indicará uma versão mensal para a versão 2004 (Build 19041). Você pode examinar o número da sua versão em suas configurações > tela para confirmar que está no Build mais recente disponível 19041.1128 +. Para atualizar para a versão mais recente, abra o aplicativo configurações, vá para atualizar & segurança e toque em verificar se há atualizações. Para obter mais informações sobre como gerenciar atualizações do HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>O que há de novo no Windows Holographic, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte de posição de olho automático](hololens-release-notes.md#auto-eye-position-support) | Computa ativamente posições de olho sem que os usuários passem pela calibragem de controle ocular.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que novos métodos mais simples instalem e removam certificados do aplicativo configurações.     |
| [Inicialização automática do provisionamento de USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | O provisionamento de pacotes em unidades USB solicita automaticamente a página de provisionamento no OOBE.                                                         |
| [Confirmar automaticamente os pacotes de provisionamento no OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante o OOBE da página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a inicialização automática de provisionamento e a confirmação automática em conjunto. |
| [Usando o piloto automático com conexão Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o AutoPilot do dispositivo Wi-Fi sem a necessidade do adaptador Ethernet. |
| [CSP Tenantlockdown e piloto automático](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após o registro do locatário e a política ser aplicada, o dispositivo só poderá ser registrado nesse locatário sempre que o dispositivo for redefinido ou atualizado novamente. |
| [Acesso global atribuído](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para vários modos de quiosque de aplicativo que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
| [Iniciar automaticamente um aplicativo no quiosque de vários aplicativos](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define um aplicativo para ser iniciado automaticamente ao entrar em um modo de quiosque de vários aplicativos.                                                        |
| [Alterações de comportamento do modo de quiosque para tratamento de falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Falha no modo de quiosque agora tem fallback restritivo.                                                                                                |
| [Políticas de HoloLens](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para o HoloLens.     |
| [Armazenar em cache a associação de grupo do Azure AD para quiosque offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os usuários usem o cache de associação de grupo para usar o modo de quiosque offline por um número de dias definido.                                        |
| [Novas políticas de restrição de dispositivo para o HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Políticas de gerenciamento de dispositivo habilitadas recentemente habilitadas para o HoloLens 2.                                                                                |
| [Novas políticas de energia para o HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recentemente suportadas para configurações de tempo limite de energia.  |
| [Atualizar políticas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas habilitadas recentemente, permitindo o controle de atualizações.           |
| [Visibilidade da página Configurações habilitadas para o HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Política para escolher quais páginas são vistas no aplicativo configurações.             |
| [Modo de pesquisa](hololens-release-notes.md#research-mode) | Usando o modo de pesquisa no HoloLens 2. |
| [Tamanho de gravação aumentado](hololens-release-notes.md#recording-length-increased) | Gravações da MRC não são mais limitadas a 5 minutos. |
| [Melhorias e correções na atualização](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correções adicionais na atualização.   |

### <a name="auto-eye-position-support"></a>Suporte de posição de olho automático

No HoloLens 2, as posições de olho permitem o posicionamento preciso do holograma, a experiência de exibição confortável e a qualidade de exibição aprimorada. As posições de olho são calculadas internamente como parte da computação de controle de olho. No entanto, isso requer que cada usuário passe pela calibragem de controle ocular, mesmo quando a experiência pode não exigir a entrada de olhar de olho.

A **AEP (posição de olho automático)** habilita esses cenários com uma maneira sem interação de computar posições de olho para o usuário. A posição de olho automático começa a trabalhar em segundo plano automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de acompanhamento de olho anterior, a posição de olho automático começará a fornecer as posições de olho do usuário para o sistema de vídeo após um tempo de processamento de 20-30 segundos. Os dados do usuário não são persistidos no dispositivo e, portanto, esse processo é repetido quando o usuário retira o botão de volta e coloca o dispositivo novamente ou se o dispositivo é reinicializado ou sai do modo de suspensão.

Há algumas alterações de comportamento do sistema com o recurso de posição de olho automático quando um usuário não calibrado coloca no dispositivo. Nesse contexto, um usuário não calibrado refere-se a alguém que não passou pelo processo de calibragem de controle ocular no dispositivo anteriormente.

| Aplicativo ativo | Comportamento anterior | Comportamento do Windows Holographic, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo não habilitado para olhar ou shell Holographic |A caixa de diálogo solicitação de calibragem de acompanhamento ocular é exibida. | Nenhum prompt é exibido. |
| Aplicativo habilitado para olhar | A caixa de diálogo solicitação de calibragem de acompanhamento ocular é exibida. | A solicitação de calibragem de controle de olho é exibida somente quando o aplicativo acessa o fluxo de olhar de olho. |

Se o usuário fizer a transição de um aplicativo não olhar habilitado para um que acesse os dados do olhar, o prompt de calibragem será exibido. 

Todo o outro comportamento do sistema será semelhante a quando o usuário atual não tiver uma calibragem de acompanhamento de olho ativo. Por exemplo, o gesto de início de uma mão não será habilitado. Não haverá nenhuma alteração na experiência de instalação inicial para a primeira.

Para experiências que exigem dados olhars de olho ou posicionamento muito preciso do holograma, recomendamos que usuários não calibrados executem a calibragem de controle ocular. Ele pode ser acessado no prompt de calibragem de controle ocular ou ao iniciar o aplicativo de configurações no menu iniciar e selecionar a calibragem de **> do sistema > calibragem de olho > executar a calibragem**

Essas informações podem ser encontradas posteriormente com [outras informações de calibragem](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança de dispositivo e conformidade por meio do novo Gerenciador de certificados. Essa funcionalidade permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows Holographic versão 20H2, estamos adicionando um Gerenciador de certificados no aplicativo de configurações do HoloLens 2. Vá para **configurações > atualização & segurança > certificados**. Esse recurso fornece uma maneira simples e amigável de usuário para exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar que um certificado foi implantado corretamente ou de confirmar que foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade desejada e está funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para localizar um certificado específico na lista rapidamente, há opções para classificar por nome, loja ou data de validade. Os usuários também podem procurar um certificado diretamente. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **informações**. 

A instalação do certificado atualmente dá suporte a arquivos. cer e. CRT. Os proprietários de dispositivo podem instalar certificados no computador local e no usuário atual;  todos os outros usuários só podem instalar no usuário atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário de configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um PC.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no seu HoloLens 2.
1.  Navegue até **configurações aplicativo > atualizar & segurança > certificados** e selecione instalar um certificado.
1.  Clique em **Importar arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione o **local do repositório**.
1.  Selecione **repositório de certificados**.
1.  Clique em **Instalar**.

O certificado agora deve estar instalado no dispositivo.

#### <a name="to-remove-a-certificate"></a>Para remover um certificado: 
1. Navegue até **configurações aplicativo > atualização e segurança > certificados**.
1. Procure o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **remover**
1. Selecione **Sim** quando solicitada a confirmação.

![Visualizador de certificados no aplicativo configurações](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado](images/certificate-device-install.jpg)

Essas informações podem ser encontradas posteriormente [em uma nova página do Gerenciador de certificados](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Inicialização automática do provisionamento de USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante o OOBE.

Antes desta versão, os usuários precisavam iniciar a tela de provisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora, os usuários podem ignorar a combinação de botões, usando um pacote de provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagindo do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB for deixada conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como observará que outros que estão sendo conectados.

Para obter mais informações sobre como aplicar pacotes de provisionamento durante o OOBE, visite a documentação de [provisionamento do HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) .

Informações adicionais sobre o [provisionamento automático de um USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) podem ser encontradas na documentação de provisionamento do HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmar automaticamente os pacotes de provisionamento no OOBE
- Processo automatizado permitindo menos interação do usuário, quando a página pacote de provisionamento for exibida, ele aplicará automaticamente todos os pacotes listados.

Quando a tela principal de provisionamento aparecer, o OOBE será reduzido 10 segundos antes de iniciar a aplicação de todos os pacotes de provisionamento automaticamente. Os usuários ainda podem [confirmar ou cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dentro desse 10 segundos depois de verificar os pacotes esperados.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para interações de dispositivo reduzidas para provisionamento. 

Ao combinar o lançamento automático do provisionamento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um usuário pode provisionar dispositivos de HoloLens 2 automaticamente sem usar a interface do usuário do dispositivo ou até mesmo utilizar o dispositivo. Você pode continuar a usar a mesma unidade USB e pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos de uma só vez na mesma área. 

1. [Crie um pacote de provisionamento](hololens-provisioning.md) usando o [Designer de configuração do Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie o pacote em uma unidade de armazenamento USB.
1. [Atualize seu HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) para [19041,1361 ou Build mais recente](https://aka.ms/hololens2previewdownload). 
1. Quando o [complemento de recuperação avançada](https://www.microsoft.com/store/productId/9P74Z35SFRS8) concluiu o seu dispositivo, desconecte seu cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. Quando o dispositivo HoloLens 2 for inicializado no OOBE, ele detectará automaticamente o pacote de provisionamento na unidade USB e iniciará a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Agora, seu dispositivo está configurado e [exibirá a tela de provisionamento bem-sucedido](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Usando o piloto automático com conexão Wi-Fi
- Necessidade de adaptadores USB-C para redução de Ethernet para reduzir as necessidades de hardware, permitindo que o AutoPilot funcione em dispositivos Wi-Fi conectados.

Agora, durante o OOBE, quando você conectar o HoloLens 2 com Wi-Fi, o OOBE verificará se há um perfil do AutoPilot para o dispositivo. Se um for encontrado, ele será usado para concluir o restante da União do AAD e do fluxo de registro. Em outras palavras, usar Ethernet para USB-C ou Wi-Fi para o adaptador USB-C não é mais um requisito, no entanto, ele continuará a funcionar se fornecido no início do OOBE. Saiba mais sobre o [piloto automático para dispositivos do HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP Tenantlockdown e piloto automático
- Mantém os dispositivos no locatário da organização bloqueando-os para o locatário mesmo por meio da redefinição do dispositivo ou do reflash. Com segurança adicional, desautorizando a criação de conta no por meio do provisionamento. 

Os dispositivos do HoloLens 2 agora dão suporte ao CSP TenantLockdown a partir do [Windows Holographic versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) O CSP permite que o HoloLens 2 seja vinculado ao registro do MDM usando somente o AutoPilot. Depois que o nó RequireNetworkInOOBE do CSP do TenantLockdown é definido como valor true ou false (inicialmente definido) no HoloLens 2, esse valor permanece no dispositivo, apesar da atualização, das atualizações do sistema operacional etc. 

Depois que o nó RequireNetworkInOOBE de CSPs do TenantLockdown for definido como true no HoloLens 2, o OOBE aguardará indefinidamente que o perfil do AutoPilot seja baixado e aplicado com êxito, após a conectividade de rede. 

Depois que o nó RequireNetworkInOOBE de CSPs do TenantLockdown for definido como true no HoloLens 2, as operações a seguir não serão permitidas no OOBE: 
- Criando usuário local usando provisionamento de tempo de execução 
- Executando a operação de ingresso do Azure AD por meio do provisionamento de tempo de execução 
- Selecionando quem possui o dispositivo na experiência do OOBE 

#### <a name="how-to-set-this-using-intune"></a>Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique true para o nó RequireNetworkInOOBE, conforme mostrado abaixo.
O valor de OMA-URI deve ser./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configurando o bloqueio locatário via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. Torne o membro do dispositivo do HoloLens 2 do grupo criado na etapa anterior e acione a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com êxito. Depois que essa configuração de dispositivo se aplicar com êxito no dispositivo de HoloLens 2, os efeitos de TenantLockdown estarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Como remover a definição de RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune? 
1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração de dispositivo criada acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em OMA URI personalizado e especifique false para RequireNetworkInOOBE, conforme mostrado abaixo. O valor de OMA-URI deve ser./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE como false por meio do URI OMA no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração do dispositivo a esse grupo de dispositivos. 

1. Torne o membro do dispositivo do HoloLens 2 do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com êxito. Depois que essa configuração de dispositivo se aplicar com êxito no dispositivo de HoloLens 2, os efeitos de TenantLockdown ficarão inativos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>O que aconteceria durante o OOBE, se o perfil do AutoPilot não for atribuído em um HoloLens depois que TenantLockdown for definido como true? 
O OOBE aguardará indefinidamente o perfil do AutoPilot para baixar e a caixa de diálogo a seguir será apresentada. Para remover efeitos de TenantLockdown, o dispositivo deve ser registrado primeiro com seu locatário original usando somente o AutoPilot e RequireNetworkInOOBE deve ser desmarcado, conforme descrito na etapa anterior, antes que as restrições apresentadas pelo CSP do TenantLockdown sejam removidas. 

![Exibição no dispositivo para quando a política é imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

Essas informações agora podem ser encontradas junto com o restante do piloto automático em [TENANTLOCKDOWN CSP e AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Acesso atribuído global – modo de quiosque
- Gerenciamento de identidades reduzido para quiosque, habilitando o novo método de quiosque que aplica o modo de quiosque no nível do sistema.

Esse novo recurso permite que um administrador de ti configure um dispositivo do HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem nenhuma afinidade com nenhuma identidade no sistema e se aplica a todos que se conectam ao dispositivo. Leia sobre esse novo recurso em detalhes no [quiosque de acesso global atribuído do HoloLens](hololens-global-assigned-access-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicialização automática de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada com a inicialização automática do aplicativo, aumentando ainda mais a interface do usuário e as seleções de aplicativo escolhidas para experiências de modo de quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e somente um aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração de acesso atribuída. 

O aplicativo é iniciado automaticamente quando o usuário entra. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações de comportamento do modo de quiosque para tratamento de falhas
- Modo de quiosque mais seguro ao eliminar aplicativos disponíveis em falhas do modo de quiosque. 

Antes de encontrar falhas na aplicação do modo de quiosque, o HoloLens costumava mostrar todos os aplicativos no menu iniciar. Agora no Windows Holographic versão 20H2 no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, como abaixo: 

![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Políticas de HoloLens
- Opções de gerenciamento de dispositivo especificamente para o HoloLens criado para gerenciar o dispositivo. 

Novas políticas de realidade misturada foram criadas para dispositivos do HoloLens 2 no Windows Holographic versão 20H2. As novas configurações controláveis incluem: definir o brilho, definir o volume, desabilitar a gravação de áudio em capturas de realidade misturada, definir quando o diagnóstico pode ser coletado e o cache de associação do grupo do AAD.  

| Nova política de HoloLens                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados e, portanto, pressioná-lo não altera o brilho.       | 1 Sim, 0 não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que os botões de volume sejam desabilitados e, portanto, pressionados não altera o volume.               | 1 Sim, 0 não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | Desabilita o microfone, portanto, não é possível gravar áudio no HoloLens 2.                      | 1 Sim, 0 não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os logs de diagnóstico podem ser coletados.                               | 0 desabilitado, 1 habilitado para proprietários de dispositivo, 2 habilitados para todos (padrão) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla quantos dias o cache de associação de grupo do Azure AD é usado para o quiosque de destino de grupos do Azure AD. | Veja abaixo.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Armazenar em cache a associação de grupo do Azure AD para quiosque offline
- Os quiosques offline habilitados serão usados com grupos do AAD por até 60 dias.

Essa política controla por quantos dias o cache de associação de grupo do Azure AD pode ser usado para configurações de acesso atribuídas direcionando grupos do Azure AD para o usuário conectado. Quando esse valor de política for definido como valor maior que 0 somente, o cache será usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays URI value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 dias  
Máx.-60 dias 

Etapas para usar esta política corretamente: 
1. Crie um perfil de configuração de dispositivo para o quiosque de destino de grupos do Azure AD e atribua-o a dispositivos do HoloLens. 
1. Crie uma configuração de dispositivo personalizada de OMA URI que defina esse valor de política para o número de dias desejado (> 0) e atribua-o aos dispositivos do HoloLens. 
    1. O valor do URI deve ser inserido na caixa de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre min/max permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário 1 do Azure AD entre quando a Internet estiver disponível, quando o usuário entrar e a associação de grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário 1 do Azure AD pode colocar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD. o ponto-chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que eles são membros do grupo do Azure AD ao qual a configuração de quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para um usuário do Azure AD passará por um comportamento de falha mencionado em ambientes "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Novas políticas de restrição de dispositivo para o HoloLens 2
- Permite que os usuários gerenciem políticas específicas de gerenciamento de dispositivos, como bloquear a adição ou remoção de pacotes de provisionamento.

Políticas habilitadas recentemente que permitem mais opções de gerenciamento de dispositivos do HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Essas duas novas políticas para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Em relação ao [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp), o HoloLens dará suporte apenas à configuração./Vendor/MSFT/RemoteLock/Lock. Não há suporte para as configurações que lidam com PIN como redefinição e recuperação.

### <a name="new-power-policies-for-hololens-2"></a>Novas políticas de energia para o HoloLens 2
- Mais opções para quando o HoloLens é suspenso ou trava por meio de políticas de energia. 

Essas políticas adicionadas recentemente permitem que os administradores controlem os Estados de energia, como tempo limite de ociosidade. Para ler mais sobre cada política individual, clique no link para essa política.

|     Link de documentação da política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas políticas para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Para uma experiência consistente no HoloLens 2, certifique-se de que os valores para DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery sejam definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Consulte os [temporizadores ociosos de exibição, suspensão e hibernação](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre o modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Políticas de atualização habilitadas recentemente para o HoloLens
- Mais opções para quando as atualizações são instaladas ou a desabilitação do botão Pausar atualizações para garantir as atualizações.

Essas políticas de atualização agora estão habilitadas em dispositivos do HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Atualizar/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Os detalhes completos sobre essas políticas de atualização e como usá-las para dispositivos do HoloLens podem ser lidos aqui em [gerenciar atualizações do hololens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilidade da página Configurações habilitadas para o HoloLens 2
- Controle de interface do usuário aumentado no aplicativo de configurações, que pode ser confundido para mostrar uma seleção limitada de páginas.

Agora habilitamos uma política que permite que os administradores de ti impeçam que páginas específicas no aplicativo Configurações do sistema sejam visíveis ou acessíveis, ou que façam isso para todas as páginas, exceto aquelas especificadas. Para saber como personalizar totalmente esse recurso, clique no link abaixo.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais configurações de página você pode personalizar no HoloLens 2, visite nossa [página URIs de configurações](settings-uri-list.md). 
 
![Captura de tela de horas ativas sendo modificadas no aplicativo de configurações](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de pesquisa
No modo de pesquisa, o HoloLens 2 se torna uma ferramenta potente para pesquisa Visual computacional. Em comparação com as edições anteriores, o modo de pesquisa para o HoloLens 2 tem as seguintes vantagens:
-   Além dos sensores expostos no modo de pesquisa do HoloLens (1º gen), agora fornecemos acesso do sensor IMU, incluindo um acelerômetro, giroscópio e magnetômetro.
-   O HoloLens 2 fornece novos recursos que podem ser usados juntamente com o modo de pesquisa. Especificamente, o acesso a APIs articuladas de acompanhamento de mão e acompanhamento de olho que podem oferecer um conjunto mais rico de experimentos.

Os pesquisadores agora têm a opção de habilitar o modo de pesquisa em seus dispositivos de HoloLens para acessar todos esses fluxos de sensores de imagem bruta externos. O modo de pesquisa para o HoloLens 2 também fornece acesso às leituras acelerômetro, giroscópio e magnetômetro. Para proteger a privacidade dos usuários, as imagens de câmera de controle de olho bruto não estão disponíveis por meio do modo de pesquisa, mas a direção olhar está disponível por meio de APIs existentes.

Confira a [documentação do modo de pesquisa](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

### <a name="recording-length-increased"></a>Tamanho de gravação aumentado
Devido aos comentários do cliente, aumentamos o tamanho da gravação de [capturas de realidade misturada](holographic-photos-and-videos.md). As capturas de realidade misturada não serão mais limitadas a 5 minutos por padrão, mas, em vez disso, calculará o tamanho máximo de gravação com base no espaço em disco disponível. O dispositivo irá estimar a duração máxima da gravação de vídeo com base no espaço em disco disponível até 80% do espaço total em disco.

> [!NOTE]
> O HoloLens usará o comprimento de gravação de vídeo padrão (5 minutos) se ocorrer uma das seguintes opções:
> - A duração de gravação máxima estimada é menor do que o padrão de 5 minutos.
> - O espaço em disco disponível é inferior a 20% do espaço total em disco.

Você pode encontrar os requisitos completos em nossa documentação de [fotos e vídeos do Holographic](holographic-photos-and-videos.md#maximum-recording-length) . 

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:
- Mais telas no OOBE agora estão no modo escuro.
- Saiba mais conteúdo deve apontar para a mais recente política de privacidade online.
- Foi resolvido um problema em que os usuários não podiam provisionar perfis VPN por meio de pacotes de provisionamento.
- Problema de configuração de proxy fixo para conexão VPN.
- Política atualizada para desabilitar a enumeração de funções USB por meio do MDM para NCM para AllowUsbConnection.
- Foi resolvido um problema que impedia um dispositivo HoloLens de aparecer no explorador de arquivos sobre o protocolo MTP quando o dispositivo estiver configurado como um [quiosque de aplicativo único](hololens-kiosk.md). Observe que o MTP (e a conexão USB em geral) ainda podem ser desabilitados usando a política [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- Corrigido um problema em que os ícones no menu iniciar foram dimensionados corretamente no modo de quiosque.
- Corrigido um problema devido ao cache HTTP interferir no modo de quiosque direcionado aos grupos do Azure AD.
- Corrigido um problema em que os usuários não conseguiram usar o botão emparelhar depois de habilitar o modo de desenvolvedor com pacotes de provisionamento, a menos que eles tenham desabilitado e habilitado o modo de desenvolvedor novamente.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versão 1903 – atualização de novembro de 2020
- Build 18362,1085

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossa versão mais recente de versão do recurso Build do Windows Holographic, Version 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versão 2004 – atualização de outubro de 2020
- Build 19041,1124
 
Melhorias e correções na atualização:

- Foi removida uma verificação desnecessária que causou a falha do sistema em tempo de execução.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versão 1903 – atualização de outubro de 2020
- Build 18362,1081

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas versões mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versão 2004 – atualização de setembro de 2020
- Build 19041,1117

Melhorias e correções na atualização:

- Aborda um problema que impediu o Visual Studio de depurar um aplicativo quando SupportsMultipleInstances = "true" estiver presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy do NCSI para tratar da detecção de Internet com falha no proxy de rede. O NCSI pode usar o proxy de computador e proxy por perfil para detecção de conectividade com a Internet. O proxy por usuário terá suporte do NCSI em versões futuras.
- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao chão quando o cabeçalho do usuário está em uma posição neutra, olhando para o futuro. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor a ser perpendicular aos painéis de exibição, o que é inclinado para baixo em alguns graus em relação à orientação ideal. As versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica em fatores forma.
- Maior robustez de rastreamento de mão que resultará em menos perdas de controle em cenários específicos.
- Esta versão contém uma correção para melhorar a qualidade do carimbo de data/hora de áudio que pode ter contribuído para problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versão 1903 – atualização de setembro de 2020
- Build 18362,1079

Melhorias e correções na atualização:

- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao chão quando o cabeçalho do usuário está em uma posição neutra, olhando para o futuro. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor a ser perpendicular aos painéis de exibição, o que é inclinado para baixo em alguns graus em relação à orientação ideal. As versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica em fatores forma.
- Maior robustez de rastreamento de mão que resultará em menos perdas de controle em cenários específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versão 2004-atualização de agosto de 2020
- Build 19041,1113

Melhorias e correções na atualização:

- O aplicativo de configurações não seguirá mais o usuário no registro da íris ou em experiências de calibragem de controle de olho.
- Corrigido um bug em que a aplicação de um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como a conexão a uma rede) falha ao executar as outras ações após a reinicialização do dispositivo devido à renomeação.
- Esquema de cores modificado de fluxos de configuração de dispositivo inicial para melhorar a qualidade visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versão 1903-atualização de agosto de 2020
- Build 18362,1074

Essa atualização de qualidade mensal não contém nenhuma alteração notável, incentivamos você a experimentar nossas versões mais recentes para o Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versão 2004 – atualização de julho de 2020
- Build 19041,1109

Melhorias e correções na atualização:

- Os desenvolvedores agora podem escolher entre habilitar ou desabilitar o portal do dispositivo exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Alterado o brilho da caixa de entrada padrão para 100 por cento.
- Foi resolvido um problema sobre o encaminhamento de HTTPS para o portal de dispositivo do Windows no HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versão 1903 – atualização de julho de 2020
- Build 18362,1071

Melhorias e correções na atualização:

- Correção de um problema que poderia fazer com que os hologramas desapareçam em aplicativos do Unity quando perderem ou reconhecerem o controle.
- Correção de um problema que fazia com que aplicativos HoloLens exclusivos falhassem no Shell ao usar o emulador do HoloLens com aceleração de hardware em determinados dispositivos.
- Foi resolvido um problema relacionado ao encaminhamento de HTTPS para o portal de dispositivo do Windows no HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versão 2004 – atualização de junho de 2020
- Build 19041,1106

Melhorias e correções na atualização:

- Os gravadores da MRC personalizados agora têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (Headset de imersão))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "obter o áudio do aplicativo" na página de captura da realidade misturada no portal de dispositivos do Windows)
    - MicrophoneGain (o valor atual de "lucro de áudio do MIC" na página de captura da realidade misturada no portal de dispositivos do Windows)
- Correção de um bug para melhorar a qualidade de áudio em cenários de captura de realidade misturada. Especificamente, essa correção deve eliminar a falha de áudio na gravação quando o menu **Iniciar** é exibido.
- Melhoria da estabilidade do holograma nos vídeos gravados.
- Foi resolvido um problema em que a captura de realidade misturada não pôde gravar vídeo depois que o dispositivo foi deixado no estado de espera por vários dias.
- A API HolographicSpace. userpresence geralmente é desabilitada para aplicativos do Unity. Esse comportamento evita um problema que fez com que alguns aplicativos pausarem quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" estivesse habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity e do 2019.3.4 e posterior.
- Quando você acessa o portal do dispositivo em uma conexão Wi-Fi, um navegador da Web pode impedir o acesso devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo que o certificado do dispositivo tenha sido confiável anteriormente. Nesse caso, não é possível progredir para o portal do dispositivo, pois não há nenhuma opção para ignorar os avisos de segurança. Essa atualização resolveu o problema. Se o certificado do dispositivo tiver sido baixado anteriormente e for confiável em um computador para remover avisos de segurança do navegador e o erro SSL ocorrer, o novo certificado precisará ser baixado e confiável para resolver os avisos de segurança do navegador.
- Habilitada a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
- Adicionada uma configuração em **configurações** de  >    >  **hologramas** do sistema que permite que os usuários removam automaticamente todos os hologramas de uma realidade misturada em casa quando o dispositivo é desligado.
- Corrigido um problema que fazia com que os aplicativos do HoloLens alterassem seu formato de pixel para renderizar o preto no emulador do HoloLens.
- Correção de um bug que causou uma falha durante o logon da íris.
- Correção de um problema sobre downloads de armazenamento repetidos para aplicativos já atuais.
- Correção de um bug para impedir que aplicativos de imersão Abram o Microsoft Edge repetidamente.
- Foi corrigido um problema com as inicializações do aplicativo fotos na inicialização inicial após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versão 1903 – atualização de junho de 2020
- Build 18362,1064

Melhorias e correções na atualização:

- Os gravadores da MRC personalizados têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (Headset de imersão))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "obter o áudio do aplicativo" na página de captura da realidade misturada no portal de dispositivos do Windows)
    - MicrophoneGain (o valor atual de "lucro de áudio do MIC" na página de captura da realidade misturada no portal de dispositivos do Windows)
- A API HolographicSpace. userpresence geralmente é desabilitada para aplicativos do Unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo que a configuração seja executada em segundo plano esteja habilitada. A API agora está habilitada para as versões 2018.4.18 e posteriores do Unity, e 2019.3.4 e posterior.
- Corrigido um problema que fazia com que os aplicativos do HoloLens alterassem seu formato de pixel para renderizar o preto no emulador do HoloLens.
- Corrigido um problema sobre as inicializações do aplicativo fotos na inicialização inicial após a atualização da versão 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versão 2004  
- Build-19041,1103

A principal atualização de software de maio de 2020 para o HoloLens 2, o *Windows Holographic, versão 2004* inclui uma série de novos recursos empolgantes, como suporte para o Windows AutoPilot, modo escuro do aplicativo, suporte a Ethernet USB para hotspots 5g/LTE e muito mais. Para atualizar para a versão mais recente, abra o aplicativo **configurações**   , vá para  **Atualizar & segurança** e selecione o botão  **verificar atualizações**   . 

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurar e configurar diretamente novos dispositivos para produção usando o Windows AutoPilot                 |
|       Suporte a FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar diretamente um pacote de provisionamento de uma unidade USB ao seu HoloLens                              |
|       Status de instalação do aplicativo                 |          Verifique se o status de instalação no aplicativo de configurações para aplicativos foi enviado por push para o HoloLens 2 por meio do MDM               |
|       Provedores de serviços de configuração (CSPs)   |          Novos provedores de serviços de configuração adicionados para aprimorar os recursos de controle de administrador                 |
|       Suporte a 5G/LTE USB                       |          O recurso Ethernet USB expandido habilita o suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que dão suporte aos modos escuro e claro, melhorando a experiência de exibição        |
|       Comandos de voz                             |          Suporte para comandos adicionais de voz do sistema para controlar as mãos gratuitas do HoloLens                           |
|       Aprimoramentos de acompanhamento de mão                 |          Melhorias de acompanhamento de mão tornam os botões e as interações de Slate 2D mais precisos                        |
|       Melhorias e correções de qualidade                 |          Vários aprimoramentos de desempenho e confiabilidade do sistema em toda a plataforma                            |

### <a name="support-for-windows-autopilot"></a>Suporte para Windows AutoPilot

O piloto automático do Windows para o HoloLens 2 permite que o canal de vendas do dispositivo Registre previamente o HoloLens em seu locatário do Intune. Quando os dispositivos chegam, eles estão prontos para serem implantados automaticamente como dispositivos compartilhados em seu locatário. Para tirar proveito da autoimplantação, o dispositivo deve se conectar a uma rede durante a primeira tela na instalação usando um USB-C-to-Ethernet.

Depois que um usuário inicia o processo de autoimplantação do AutoPilot, o processo conclui as seguintes etapas:

1. Ingresse o dispositivo no Azure Active Directory (Azure AD).
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe as políticas, os certificados e os perfis de rede direcionados ao dispositivo.
1. Provisionar o dispositivo.
1. Apresente a tela de entrada ao usuário.

Saiba mais no [Guia de avaliação do piloto automático do Windows para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Entre em contato com seu gerente de conta para participar da versão prévia do piloto automático agora. Os dispositivos prontos para o piloto automático começarão a enviar em breve.*

### <a name="fido2-security-key-support"></a>Suporte à chave de segurança do FIDO2

Alguns usuários compartilham um dispositivo HoloLens com outras pessoas em um ambiente corporativo ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. O Fast Identity online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre diretamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação com base em padrões "inphishável" que pode vir em qualquer fator forma. FIDO é um padrão aberto para autenticação com senha. Ele permite que usuários e organizações entrem em seus recursos sem um nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma embutida em um dispositivo.

Para começar, consulte [habilitar a entrada de chave de segurança sem senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Registro de MDM aprimorado por meio do pacote de provisionamento

Os pacotes de provisionamento permitem definir a configuração do HoloLens por meio de um arquivo de configuração, em vez de por meio da experiência inicial do HoloLens. Anteriormente, os pacotes de provisionamento tinham que ser copiados para a memória interna do HoloLens. Agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizar em vários dispositivos HoloLens e você pode provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também dão suporte a um campo para se registrar no gerenciamento de dispositivos, portanto, não há nenhuma configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do Windows Configuration designer da Windows Store no seu PC.
1. Selecione **provisionar dispositivos hololens**  >  **provisionar dispositivos do hololens 2**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C em qualquer HoloLens atualizado. Em seguida, pressione os botões de  +  **energia** volume para baixo para aplicar seu pacote de provisionamento.

### <a name="line-of-business-application-install-status"></a>Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento do aplicativo MDM para aplicativos de linha de negócios são essenciais para o HoloLens. Administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **configurações**  >  **contas**  >  **acesso corporativo ou de estudante**  >  **clique nas informações da sua conta**  >  .

### <a name="additional-csps-and-policies"></a>CSPs e políticas adicionais

Um [provedor de serviços de configuração (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou excluir definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores têm sobre dispositivos HoloLens implantados. Para obter a lista de CSPs com suporte do HoloLens, consulte [CSP do NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novo nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa Configure políticas em dispositivos Windows. Nesta versão, adicionamos novas políticas para o HoloLens, que estão listadas aqui. Para saber mais, confira [CSPs de política com suporte do HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

O provedor de serviços de configuração do NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, confira [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Suporte de Ethernet USB expandido para dispositivos 5G/LTE de compartilhamento de Internet

Foi adicionado suporte para habilitar determinados dispositivos de banda larga móvel, como telefones 5G/LTE e hotspots Wi-Fi, quando eles estão vinculados ao HoloLens 2 via USB. Esses dispositivos agora são exibidos nas **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos de banda larga móvel que exigem um driver externo.) Essa funcionalidade permite conexões de alta largura de banda quando Wi-Fi não está disponível e Wi-Fi compartilhamento de Internet não é um desempenho suficiente. Para saber mais sobre os dispositivos USB com suporte, confira [conectar-se a dispositivos Bluetooth e USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Aprimoramentos de acompanhamento de mão

Esta versão inclui vários aprimoramentos de acompanhamento:

- **Apontando para a estabilidade:** O sistema agora se resiste à curva do dedo do índice quando ele fica obstruído pelo Palm. Essa alteração melhora a exatidão ao enviar botões, digitar, rolar conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Melhoramos a detecção do gesto de toque do ar. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta suas mãos em seus lados.
- **Confiabilidade do comutador do usuário:** O sistema agora é mais rápido e mais confiável na atualização do tamanho da mão quando você compartilha um dispositivo.
- **Roubo reduzido:** Melhoramos o manuseio de casos em que há mais de duas mãos na exibição dos sensores. Se várias pessoas estiverem trabalhando juntas, agora há uma chance muito menor de que a mão controlada vai "saltar" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Corrigido um problema que fazia com que o rastreamento à mão deixasse de funcionar quando o dispositivo está sob carga alta.

### <a name="dark-mode"></a>Modo escuro

Muitos aplicativos do Windows agora dão suporte a modos escuros e leves. Os usuários do HoloLens 2 podem escolher o modo padrão para aplicativos que dão suporte a ambos. Após a atualização, o modo de aplicativo padrão é "escuro", mas você pode alterar facilmente essa configuração: Navegue até **configurações**  >  cores do **sistema**  >    >  **escolha seu modo de aplicativo padrão**. 

Esses aplicativos "integrados" suportam o modo escuro: 

- Configurações 
- Microsoft Store 
- Email 
- Calendário 
- Explorador de Arquivos 
- Hub de Feedback 
- OneDrive 
- Fotos 
- Visualizador 3D 
- Filmes e TV 

![Xadrez do modo escuro do Windows](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, consulte [usar sua voz para operar o HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulte também [idiomas com suporte para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Atualizações da Cortana

O aplicativo atualizado integra-se com o Microsoft 365 para ajudá-lo a fazer mais em seus dispositivos (atualmente em US-English apenas). No HoloLens 2, a Cortana não dá mais suporte a determinados comandos específicos do dispositivo, como ajustar o volume ou reiniciar. Agora, há suporte para essas opções nos novos comandos de voz do sistema. Saiba mais sobre o novo aplicativo Cortana em nosso [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibragem de vídeo ativo. Esse recurso melhora a estabilidade e o alinhamento de hologramas. Agora, eles permanecem em vigor quando você move sua cabeça do lado para o outro.
- Corrigido um bug em que Wi-Fi streaming para o HoloLens foi interrompido periodicamente. Se um aplicativo indicar que ele precisa de streaming de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Correção de um dispositivo suspenso que ocorreu durante o streaming no modo de pesquisa.
- Corrigido um bug em que, em alguns casos, o usuário certo não seria exibido na tela de entrada ao retomar uma sessão.
- Corrigido um problema em que os usuários não podiam exportar logs do MDM por meio de **configurações**.
- Correção de um problema em que a precisão do acompanhamento de olho imediatamente após a configuração pronta para uso pode ser menor do que o esperado.
- Corrigido um problema em que o subsistema de acompanhamento de olho falhou ao inicializar ou executar a calibragem sob determinadas condições.
- Corrigido um problema em que a calibragem de olhos seria solicitada por um usuário já calibrado.
- Corrigido um problema em que um driver falhava durante a calibragem de olho.
- Corrigido um problema em que os pressionamentos de botão de energia repetidos poderiam causar um tempo limite do sistema de 60 segundos e uma falha de Shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um botão de **compartilhamento** no Hub de comentários para que os usuários possam compartilhar com mais facilidade os comentários.
- Corrigido um bug em que RoboRaid wan't foi instalado corretamente.

### <a name="known-issues"></a>Problemas conhecidos

- Um problema com o idioma do sistema zh-CN impede que os comandos de voz executem uma captura de realidade misturada ou exiba o endereço IP do dispositivo.
- Um problema requer que você inicie o aplicativo Cortana depois de iniciar o dispositivo para usar a ativação de voz "Ei Cortana". Se você atualizou a partir de uma compilação 18362, também poderá ver um bloco do segundo aplicativo para a versão anterior do aplicativo Cortana que não funciona mais no **início**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versão 1903-maio 2020 atualização 
- Build 18362,1061

Essa atualização de qualidade mensal não contém nenhuma alteração notável porque a equipe estava trabalhando no Windows Holographic versão 2004 pode ser atualizada, conforme descrito anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versão 1903 – atualização de abril de 2020
- Build 18362,1059

**Modo escuro para aplicativos com suporte** 

Muitos aplicativos do Windows dão suporte ao modo escuro e leve. Os clientes do HoloLens 2 agora podem escolher o modo padrão para aplicativos que dão suporte a esquemas de cores. Com base nos comentários dos clientes, definimos o modo de aplicativo padrão como "escuro", mas você pode alterar facilmente essa configuração a qualquer momento: Navegue até **configurações > sistema > cores** para localizar **"escolher o modo de aplicativo padrão".**

Esses aplicativos "integrados" suportam o modo escuro:
- Configurações
- Microsoft Store
- Email
- Calendário
- Explorador de Arquivos
- Hub de Feedback
- OneDrive
- Fotos
- Visualizador 3D
- Filmes e TV

**Melhorias e correções também na atualização:** 
- Garantiu que as sobreposições de shell estão incluídas em capturas de realidade misturadas.
- Os desenvolvedores inreais agora podem usar a página exibição 3D no portal do dispositivo para testar e depurar seus aplicativos.
- Melhoria da estabilidade do holograma na captura de realidade misturada quando o algoritmo *HolographicDepthReprojectionMethod DepthReprojection* é usado.
- Corrigido o erro "classe de API IStreamSocketListener do WinRT não registrada" em aplicativos ARM de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versão 1903-atualização de março de 2020 
- Build 18362,1056

Melhorias e correções na atualização:

- Melhoria da estabilidade do holograma na captura de realidade misturada quando o algoritmo do *Autoplanar HolographicDepthReprojectionMethod* é usado.
- Garantiu que o sistema de coordenadas anexado a um exemplo de MF de profundidade é consistente com a documentação pública.
- Maior produtividade do desenvolvedor, permitindo que os clientes colem grandes quantidades de texto por meio do portal do dispositivo.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versão 1903 – atualização de fevereiro de 2020 
- Build 18362,1053

Melhorias e correções na atualização:

- Desabilitada temporariamente a API HolographicSpace. userpresence para aplicativos Unity. Essa alteração evita um problema que fez com que alguns aplicativos pausarem quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" estivesse habilitada.
- Correção de uma falha aleatória do HUP causada pelo acompanhamento manual, em que o usuário observou uma interface do usuário e, em seguida, de volta para o Shell após vários segundos.
- Acompanhamento de mão aprimorado para que, quando você se refaça com o dedo do seu índice, a parte superior do dedo tenha menos probabilidade de ser enrolada inesperadamente.
- Maior confiabilidade de rastreamento de cabeçalho, mapeamento espacial e outros tempos de execução.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versão 1903 – atualização de janeiro de 2020 
- Build 18362,1043
 
Melhorias e correções na atualização:

- Estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador do HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versão 1903-atualização de dezembro de 2019 
- Build 18362,1042

Melhorias e correções na atualização:

- Introduziu correções de LSR (última reprodução de estágio). Processamento visual aprimorado de hologramas para parecer mais estável e nítido por uma contabilidade mais precisa para sua profundidade. Esse sintoma será mais perceptível após essa atualização se os aplicativos não definirem a profundidade de holograma corretamente.
- Correção da estabilidade de aplicativos exclusivos e navegação entre aplicativos exclusivos.
- Foi resolvido um problema em que a captura de realidade misturada não pôde gravar vídeo depois que o dispositivo estava em estado de espera por vários dias.
- Melhoria da estabilidade do holograma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versão 1903 – atualização de novembro de 2019 
- Build 18362,1039

Melhorias e correções na atualização:

- Correção da funcionalidade de **selecionar** comandos de voz durante a configuração inicial para en-CA e en-au.
- Qualidade visual aprimorada de objetos foi colocada de longe nas versões mais recentes do Unity e do MRTK (Mixed Reality Toolkit).
- Correção de problemas de endereçamento com aplicativos Holographic que ficam presos em um estado de pausa na inicialização até que o menu iniciar seja aberto e fechado.
- Correções de conformidade do OpenXR Runtime e melhorias para o HoloLens 2 e o emulador.
