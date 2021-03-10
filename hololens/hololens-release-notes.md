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
ms.openlocfilehash: 9ad1fd599605a82280fc3ce45a2b78fcd0be6f14
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400711"
---
# <a name="hololens-2-release-notes"></a>Notas de versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus dispositivos HoloLens, continuaremos a liberar atualizações de recursos, bugs e segurança. Nesta página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização mais recente do HoloLens 2, você pode verificar se há atualizações e atualizar [manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a Atualização Flash Completo (FFU) para piscar seu dispositivo por meio do [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). O [download](https://aka.ms/hololens2download) é mantido atualizado e fornece o build mais recente geralmente disponível.

>[!NOTE]
> Estamos animados para começar a iniciar a versão de novos recursos para o Windows Insiders novamente. Vamos voar para o Canal de Dev para as atualizações mais recentes. Continuaremos com nossas anotações do [**HoloLens Insider**](hololens-insider.md) à medida que adicionamos mais recursos e atualizações às nossas builds do Windows Insider. Fique animado e pronto para misturar essas atualizações em sua realidade.

Confira as notas de versão relacionadas:

- [Visite o arquivo morto do Emulador do HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Assistência Remota do Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Guias do Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versão 20H2 - Atualização de março de 2021
- Build 19041.1140

Melhorias e correções na atualização:

- Os clientes que usam AdvancedPhotoCapture ou LowLagPhotoCapture para capturar fotos com o HoloLens 2 agora podem recuperar a pose da câmera até 3 segundos após a captura da foto.
- Correção de um vazamento de memória no Device Portal Service, o problema causou o aumento do uso de memória pelo serviço que fez com que outros aplicativos falhassem ao alocar memória.
- Corrigido um problema em que os usuários inscritos na Rollout em Estágios não conseguem entrar no dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versão 1903 - Atualização de março de 2021
- Build 18362.1102

Melhorias e correções na atualização:

- Correção de um vazamento de memória no Device Portal Service, o problema causou o aumento do uso de memória pelo serviço que fez com que outros aplicativos falhassem ao alocar memória.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versão 20H2 - Atualização de fevereiro de 2021
- Build 19041.1136

Melhorias e correções na atualização:

- Corrige um problema em torno da configuração inicial do dispositivo e das atualizações de aplicativos de armazenamento.
- Resolve um problema em torno de atualizações e voos para versões posteriores do HoloLens.
- Foram removidos certificados pré-instalados não-instalados do armazenamento raiz do eSIM de dispositivos HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versão 1903 - Atualização de fevereiro de 2021
- Build 18362.1098

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente nossas versões mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versão 20H2 - Atualização de janeiro de 2021
- Build 19041.1134

Melhorias e correções na atualização:

- Desempenho aprimorado durante a inicialização, retomada e alternação do usuário quando há muitos usuários no dispositivo.
- Adicionado suporte ao arm32 para [o modo de pesquisa.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versão 1903 - Atualização de janeiro de 2021
- Build 18362.1091

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente nossas versões mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versão 20H2 – Atualização de dezembro de 2020
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicativos no HoloLens 2 por meio do Instalador de Aplicativos

Estamos **adicionando um novo recurso (Instalador de Aplicativos)** para permitir que você instale aplicativos de forma mais perfeita em seus dispositivos do HoloLens 2. O recurso estará **em uso por padrão para dispositivos nãomanageados.** Para evitar interrupções nas empresas, o instalador de aplicativos não estará **disponível para dispositivos** gerenciados no momento.  

Um dispositivo é considerado "gerenciado" **se qualquer** um dos seguintes são verdadeiros:
- MDM [Inscrito](hololens-enroll-mdm.md)
- Configurado com o [pacote de provisionamento](hololens-provisioning.md)
- Identidade [do usuário](hololens-identity.md) é o Azure AD

Agora você pode instalar Aplicativos sem precisar habilitar o Modo de Desenvolvedor ou usar o Device Portal.  Basta baixar (por USB ou por Borda) o Pacote appx para seu dispositivo e navegar até o Pacote appx no Explorador de Arquivos para ser solicitado a dar início à instalação.  Como alternativa, [inicie uma instalação de uma página da Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Assim como os aplicativos instalados na Microsoft Store ou sideload usando o recurso de implantação [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) do Aplicativo [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) LOB do MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Sinal e o certificado usado para assinar deve ser confiável pelo dispositivo HoloLens antes que o aplicativo possa ser implantado.

**Instruções de instalação do aplicativo.**

1.  Verifique se seu dispositivo não é considerado gerenciado
1.  Verifique se o dispositivo HoloLens 2 está ligado e conectado ao computador
1.  Verifique se você está conectado ao dispositivo HoloLens 2
1.  No computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para seudevicename\Armazenamento Interno\Downloads.   Depois de terminar de copiar seu arquivo, você pode desconectar seu dispositivo
1.  Em seu dispositivo HoloLens 2 Abra o Menu Iniciar, selecione Todos os aplicativos e inicie o aplicativo Explorador de Arquivos.
1.  Navegue até a pasta Downloads. Talvez seja necessário que, no painel esquerdo do aplicativo, selecione Este dispositivo primeiro e navegue até Downloads.
1.  Selecione o arquivo yourapp.appxbundle.
1.  O Instalador de Aplicativos será lançado. Selecione o botão Instalar para instalar seu aplicativo.
O aplicativo instalado será lançado automaticamente após a conclusão da instalação.

Você pode encontrar aplicativos de exemplo no [GitHub de Exemplos Universais do Windows](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar esse fluxo.

Leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o Instalador de Aplicativos](app-deploy-app-installer.md).  

![Instalando exemplos de MRTK por meio do Instalador de Aplicativos](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:

- O controle manual agora mantém o controle em muitos casos novos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, apenas a posição da palma da mão continua a ser atualizada com base na mão real do usuário, enquanto as outras juntas são inferidos com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência de controle em movimentos como bate-palmas, lançamentos, reações e bate-palmas.  Ele também ajuda em casos em que a mão está perto de uma superfície ou segurando um objeto.  Quando as juntas de mão estão sendo inferidos, [o](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) valor de precisão por conjunto será definido como "Aproximado" em vez de "Alto".
- Correção de um problema em que a redefinição de PIN para contas do Azure AD mostraria um erro "Algo deu errado.
- Os usuários devem ver muito menos falhas de OOBE pós-inicialização ao iniciar ET, Iris do aplicativo de configurações, novo usuário ou notificação do sistema.
- Os usuários devem ter o fuso horário correto saindo do OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versão 1903 – Atualização de dezembro de 2020
- Build 18362.1088

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente nosso Windows Holographic mais recente, versão 20H2 – Atualização de dezembro de 2020 e o novo recurso instalador de aplicativos adicionado à com build.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versão 20H2
- Build 19041.1128

Windows Holographic, versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para usuários do HoloLens 2 e profissionais de TI. Desde o Posicionamento Automático dos Olhos, até o Gerenciador de Certificados em Configurações, até a funcionalidade aprimorada do Modo de Quiosque e novos recursos de configuração do Autopilot. Essa nova atualização permite que as equipes de IT tomem controle mais granular para configurar e gerenciar dispositivos HoloLens e oferece aos usuários experiências holográficas ainda mais perfeitas. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. O número de com build principal permanecerá o mesmo e o Windows Update indicará uma versão mensal para a versão 2004 (build 19041). Você pode ver seu Número de Com build na tela Configurações > Sobre para confirmar se está na com build 19041.1128+. Para atualizar para a versão mais recente, abra o aplicativo Configurações, vá para Atualizar & Segurança e toque em Verificar atualizações. Para obter mais informações sobre como gerenciar atualizações do HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novidades no Windows Holographic, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte Automático de Posição Ocular](hololens-release-notes.md#auto-eye-position-support) | Calcula ativamente as posições dos olhos sem que os usuários façam a calibragem do Controle de Olhos.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que novos métodos mais simples instalem e removam certificados do aplicativo Configurações.     |
| [Provisionamento de início automático do USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Os pacotes de provisionamento em unidades USB solicitam automaticamente a página de provisionamento em OOBE.                                                         |
| [Confirmar automaticamente pacotes de provisionamento no OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante o OOBE na página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a iniciação automática de provisionamento e confirmar automaticamente. |
| [Usando o Autopilot com Wi-Fi conexão](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o piloto automático do dispositivo Wi-Fi sem a necessidade de adaptador ethernet. |
| [O Provedor de Soluções na Nuvem da Microsoft do Tenantlockdown e AutoPilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após o registro do locatário e a política ser aplicada, o dispositivo só poderá ser inscrito nesse locatário sempre que o dispositivo for redefinido ou reajustado. |
| [Acesso Global Atribuído](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para o modo de quiosque de vários aplicativos que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
| [Iniciar automaticamente um aplicativo em quiosque de vários aplicativos](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define um aplicativo para ser lançado automaticamente ao entrar em um modo de quiosque de vários aplicativos.                                                        |
| [Alterações no comportamento do modo quiosque para tratamento de falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | A falha no modo quiosque agora tem fallback restritivo.                                                                                                |
| [Políticas do HoloLens](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para o HoloLens.     |
| [Cache Azure AD Group membership for offline Kiosk](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os usuários usem o cache de associação de grupo para usar o modo Quiosque offline para o número definido de dias.                                        |
| [Novas políticas de restrição de dispositivo para o HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Políticas de gerenciamento de dispositivos habilitadas recentemente habilitadas para o HoloLens 2.                                                                                |
| [Novas políticas de energia para o HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recém-suportadas para configurações de tempo de tempo de energia.  |
| [Atualizar políticas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas recém-habilitadas permitindo o controle de atualizações.           |
| [Visibilidade da página Configurações Habilitadas para o HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Política para escolher quais páginas são vistas no aplicativo Configurações.             |
| [Modo de pesquisa](hololens-release-notes.md#research-mode) | Usando o modo de pesquisa no HoloLens 2. |
| [Comprimento da gravação aumentado](hololens-release-notes.md#recording-length-increased) | As gravações mrc não são mais limitados a 5 minutos. |
| [Melhorias e correções na atualização](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correções adicionais na atualização.   |

### <a name="auto-eye-position-support"></a>Suporte Automático de Posição Ocular

No HoloLens 2, as posições dos olhos habilitam o posicionamento preciso do holograma, experiência de visualização confortável e qualidade de exibição aprimorada. As posições do olho são calculadas internamente como parte da computação de rastreamento ocular. Entretanto, isso requer que cada usuário passe pela calibragem de rastreamento ocular, mesmo quando a experiência possa não requerer a entrada do olhar fixo.

A ** Posição Automática Ocular (AEP)** habilita esses cenários com uma forma livre de interação de calcular as posições dos olhos para o usuário. A Posição Automática Ocular começa a funcionar em tela de fundo automaticamente a partir do momento em que o usuário coloca o dispositivo. Se o usuário não tiver uma calibragem de rastreamento ocular anterior, a Posição Automática Ocular começará a fornecer as posições dos olhos do usuário para o sistema de exibição após um tempo de processamento de 20 a 30 segundos. Os dados do usuário não são persistentes no dispositivo e consequentemente esse processo é repetido se o usuário tirar e colocar o dispositivo novamente ou se o dispositivo for reinicializado ou acordar da suspensão.

Há algumas alterações de comportamento do sistema com o recurso Posição Automática Ocular quando um usuário não calibrado coloca o dispositivo. Nesse contexto, um usuário sem calibragem refere-se a alguém que não passou pelo processo de calibragem de rastreamento ocular no dispositivo anteriormente.

| Aplicativo Ativo | Comportamento Anterior | Comportamento do Windows Holográfico, versão 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicativo não habilitado para olhar ou o Shell Holográfico |A caixa de diálogo do sistema de gerenciamento de calibragem do rastreamento ocular é exibida. | Nenhum sistema de gerenciamento é exibido. |
| Aplicativo habilitado para olhar | A caixa de diálogo do sistema de gerenciamento de calibragem do rastreamento ocular é exibida. | O aviso de calibragem de rastreamento ocular é exibido apenas quando o aplicativo acessa o fluxo do olhar fixo. |

Se o usuário fizer a transição de um aplicativo não habilitado para olhar para um que acesse os dados do olhar, o sistema de gerenciamento de calibragem será exibido. 

Todos os outros comportamentos do sistema serão semelhantes quando o usuário atual não tiver uma calibragem de rastreamento ocular ativa. Por exemplo, o gesto de Partida com Uma mão não será habilitado. Não haverá nenhuma alteração na Experiência Inicial do programa de instalação inicial.

Para experiências que exigem dados do olhar do olho ou posicionamento muito preciso do holograma, recomendamos que os usuários não calibrados executem a calibragem de rastreamento ocular. Ele pode ser acessado do sistema de gerenciamento de calibragem de controle ocular ou iniciando o aplicativo Configurações no menu iniciar e, em seguida, selecionando **Sistema > Calibragem > Calibragem Ocular > Executar a calibragem ocular**.

Essas informações podem ser encontradas posteriormente com [outras informações de calibragem.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Gerenciador de certificados

- Ferramentas de auditoria, diagnóstico e validação aprimoradas para segurança e conformidade de dispositivos por meio do novo Gerenciador de Certificados. Essa funcionalidade permitirá implantar, solucionar problemas e validar seus certificados em escala em ambientes comerciais.

No Windows Holographic versão 20H2, estamos adicionando um Gerenciador de Certificados no aplicativo Configurações do HoloLens 2. Vá para **Configurações > Atualizar & Segurança > Certificados**. Esse recurso fornece uma maneira simples e fácil de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de Certificados, os administradores e os usuários agora têm ferramentas de auditoria, diagnóstico e validação aprimoradas para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar se um certificado foi implantado corretamente ou para confirmar se ele foi removido adequadamente. 
-   **Diagnóstico:** Quando surgem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade pretendido e está funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar um certificado específico na lista rapidamente, há opções para classificar por nome, armazenamento ou data de expiração. Os usuários também podem pesquisar diretamente por um certificado. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **Informações**. 

A instalação do certificado atualmente dá suporte a arquivos .cer e .crt. Os proprietários de dispositivos podem instalar certificados no Computador Local e no Usuário Atual;  todos os outros usuários só podem instalar no Usuário Atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um computador.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.
1.  Navegue **até Configurações Aplicativo > Atualizar & Certificados**> Segurança e selecione Instalar um certificado.
1.  Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione **Local do Armazenamento**.
1.  Selecione **Armazenamento de Certificados**.
1.  Clique em **Instalar**.

O certificado agora deve ser instalado no dispositivo.

#### <a name="to-remove-a-certificate"></a>Para remover um certificado: 
1. Navegue **até Configurações Aplicativo > Atualização e Segurança > Certificados**.
1. Pesquise o certificado pelo nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **Remover**
1. Selecione **Sim** quando solicitado a confirmar.

![Visualizador de certificados no aplicativo Configurações](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado](images/certificate-device-install.jpg)

Essas informações podem ser encontradas [posteriormente em uma nova página do Gerenciador de Certificados.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Provisionamento de início automático do USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com Pacotes de Provisionamento são usadas durante o OOBE.

Antes dessa versão, os usuários tinham que iniciar a tela de provisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora, os usuários podem ignorar a combinação de botões usando um Pacote de Provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB ao pacote de provisionamento durante o primeiro momento interagido do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB for deixada conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como observará se outros estão conectados.

Para obter mais informações sobre como aplicar pacotes de provisionamento durante o OOBE, visite a documentação de [provisionamento do HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Informações adicionais [sobre o provisionamento](hololens-provisioning.md#auto-launch-provisioning-from-usb) de início automático de uma USB podem ser encontradas na documentação de provisionamento do HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmar automaticamente pacotes de provisionamento no OOBE
- Processo automatizado que permite menos interação do usuário, quando a página Pacote de Provisionamento é exibida, ele aplicará automaticamente todos os pacotes listados.

Quando a tela principal de provisionamento aparecer, o OOBE contará 10 segundos antes de iniciar automaticamente a aplicação de todos os pacotes de provisionamento. Os usuários ainda podem [confirmar ou cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dentro de 10 segundos depois de verificar os pacotes esperados.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para interações de dispositivo reduzidas para provisionamento. 

Combinando a iniciação automática do provisionamento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um usuário pode provisionar dispositivos HoloLens 2 automaticamente sem usar a interface do usuário do dispositivo ou até mesmo usar o dispositivo. Você pode continuar a usar a mesma unidade USB e o pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos ao mesmo tempo na mesma área. 

1. [Criar um pacote de provisionamento](hololens-provisioning.md) usando [o Designer de Configuração do Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copie o pacote para uma unidade de armazenamento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Quando [o Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) tiver concluído o flash do dispositivo, desconectar o cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. Quando o dispositivo HoloLens 2 for inicializado no OOBE, ele detectará automaticamente o pacote de provisionamento na unidade USB e iniciará a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Seu dispositivo agora está configurado e [exibirá a tela Provisionamento Bem-sucedido.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Usando o Autopilot com Wi-Fi conexão
- Removeu a necessidade de adaptadores USB-C para ethernet reduzindo as necessidades de hardware, permitindo que o Autopilot funcione em Wi-Fi dispositivos conectados.

Agora, durante o OOBE, depois de conectar o HoloLens 2 com Wi-Fi, o OOBE verificará se há um perfil do Piloto Automático para o dispositivo. Se um for encontrado, ele será usado para concluir o restante do fluxo de inscrição e junção do AAD. Em outras palavras, usar ethernet para USB-C ou Wi-Fi adaptador USB-C não é mais um requisito, no entanto, eles continuam a funcionar se fornecidos no início do OOBE. Saiba mais sobre [o Autopilot para dispositivos HoloLens 2.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP do Tenantlockdown e AutoPilot
- Mantém os dispositivos no locatário da organização bloqueando-os para o locatário, mesmo através da reinicialização do dispositivo ou do reflash. Com mais segurança, desautorizando a criação da conta por meio do provisionamento. 

Os dispositivos HoloLens 2 agora suportam o CSP TenantLockdown a partir [do Windows Holographic versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

O Provedor de Soluções na Nuvem da Microsoft [TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) permite que o HoloLens 2 seja vinculado a inscrição do MDM usando apenas o Autopilot. Depois que o nó RequireNetworkInOOBE do CSP do TenantLockdown for definido com valor verdadeiro ou falso (definido inicialmente) no HoloLens 2, esse valor permanece no dispositivo, apesar de atualizar novamente, atualizações do sistema operacional, etc. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, o OOBE aguarda indefinidamente que o perfil do Autopilot seja baixado e aplicado com sucesso, após a conectividade de rede. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, as seguintes operações não serão permitidas no OOBE: 
- Criação de usuário local usando provisionamento do tempo de execução 
- Executando a operação de ingresso no Microsoft Azure Active Directory por meio de provisionamento em tempo de execução 
- Seleção de proprietários do dispositivo na experiência do OOBE 

#### <a name="how-to-set-this-using-intune"></a>Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique true para o nó RequireNetworkInOOBE, conforme mostrado a seguir.
O valor OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configurar o bloqueio de locatário via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Depois que esta configuração de dispositivo for aplicada com sucesso no dispositivo Hololens 2, os efeitos do TenantLockdown estarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Como desmarcar o RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune? 
1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração de dispositivos criada acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em OMA-URI personalizado e especifique falso para RequireNetworkInOOBE como mostrado a seguir. O valor OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE definida como falso via OMA-URI no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Assim que esta configuração de dispositivo for aplicada com sucesso no dispositivo Hololens 2, os efeitos do TenantLockdown ficarão inativos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>O que aconteceria durante o OOBE, se o perfil do Autopilot não fosse atribuído em um HoloLens depois que TenantLockdown fosse definido como verdadeiro? 
O OOBE aguardará indefinidamente o download do perfil do Autopilot e a caixa de diálogo a seguir será apresentada. Para remover os efeitos do TenantLockdown, o dispositivo deve ser registrado com seu locatário original primeiro usando apenas o Autopilot e o RequireNetworkInOOBE desmarcado, conforme descrito na etapa anterior antes que as restrições introduzidas pelo CSP do TenantLockdown sejam removidas. 

![Modo de exibição no dispositivo quando a política for imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

Essas informações agora podem ser encontradas juntamente com o restante do Autopilot em [Tenantlockdown CSP e Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Acesso Atribuído Global – Modo de Quiosque
- Gerenciamento de Identidade Reduzida para Quiosque, habilitando o novo método Kiosk que aplica o modo Quiosque no nível do sistema.

Esse novo recurso permite que um administrador de IT configure um dispositivo do HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com qualquer identidade no sistema e se aplica a todos que se insinuem no dispositivo. Leia sobre esse novo recurso em detalhes no quiosque de acesso atribuído [global do HoloLens.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Início automático de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada com o lançamento automático de aplicativos, aumentando ainda mais as seleções de interface do usuário e aplicativo escolhidas para experiências de modo Quiosque.

Aplica-se apenas ao modo de quiosque de vários aplicativos e apenas 1 aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração do Acesso Atribuído. 

O aplicativo é automaticamente lançado quando o usuário faz logor. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Alterações no comportamento do modo quiosque para tratamento de falhas
- Modo Quiosque mais seguro eliminando aplicativos disponíveis em falhas no modo Quiosque. 

Anteriormente, ao encontrar falhas na aplicação do modo quiosque, o HoloLens era usado para mostrar todos os aplicativos no menu iniciar. Agora, no Windows Holographic versão 20H2, no caso de falhas, nenhum aplicativo será mostrado no menu iniciar como abaixo: 

![Imagem da aparência do modo Quiosque agora quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Políticas do HoloLens
- Opções de gerenciamento de dispositivos especificamente para o HoloLens criadas para gerenciar o dispositivo. 

Novas políticas de realidade misturada foram criadas para dispositivos HoloLens 2 no Windows Holographic versão 20H2. As novas configurações controláveis incluem: definir brilho, definir volume, desabilitar a gravação de áudio em capturas de realidade misturada, definir quando os diagnósticos podem ser coletados e cache de associação de grupo do AAD.  

| Nova política do HoloLens                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados para que pressionar ele não altere o brilho.       | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que os botões de volume sejam desabilitados para que pressionar ele não altere o volume.               | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | Desabilita o microfone para que nenhuma gravação de áudio seja possível no HoloLens 2.                      | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os logs de diagnóstico podem ser coletados.                               | 0 Desabilitado, 1 Habilitado para Proprietários de Dispositivos, 2 Habilitado para todos (Padrão) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla quantos dias o cache de associação de grupo do Azure AD é usado para grupos de destino do Kiosk do Azure AD. | Confira abaixo.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cache Azure AD Group membership for offline Kiosk
- Quiosques offline habilitados para uso com grupos AAD por até 60 dias.

Essa política controla por quantos dias, o cache de associação de grupo do Azure AD tem permissão para ser usado para configurações de Acesso Atribuído destinados a grupos do Azure AD para usuários assinados. Depois que esse valor de política for definido como valor maior do que 0, o cache será usado caso contrário, não.  

Nome: AADGroupMembershipCacheValidityInDays Valor de URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 dias  
Max - 60 dias 

Etapas para usar essa política corretamente: 
1. Crie um perfil de configuração de dispositivo para grupos de quiosque destinados ao Azure AD e atribua-o aos dispositivos do HoloLens. 
1. Crie uma configuração de dispositivo baseado em URI OMA personalizada que define esse valor de política como o número desejado de dias (> 0) e atribua-o aos dispositivos HoloLens. 
    1. O valor de URI deve ser inserido na caixa de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre mín/máximo permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário do Azure AD 1 entre quando a Internet estiver disponível, quando o usuário entrar e a associação ao grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário do Azure AD 1 pode deixar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita o número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD N. O ponto chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet para que, pelo menos uma vez, possamos determinar que ele é membro do grupo do Azure AD para o qual a configuração do Quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para que um usuário do Azure AD experimente o comportamento de falha mencionado em ambientes "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Novas políticas de restrição de dispositivo para o HoloLens 2
- Permite que os usuários gerenciem políticas de gerenciamento de dispositivo específicas, como bloquear a adição ou a remoção de pacotes de provisionamento.

Políticas recém-habilitadas que permitem mais opções de gerenciamento de dispositivos HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Essas duas novas polícias para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas [Restrições comuns de dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Em relação ao [RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)o HoloLens só dará suporte à configuração ./Vendor/MSFT/RemoteLock/Lock. As configurações que lidam com PIN, como redefinição e recuperação, não são suportadas.

### <a name="new-power-policies-for-hololens-2"></a>Novas políticas de energia para o HoloLens 2
- Mais opções para quando o HoloLens dormir ou se bloqueia por meio de políticas de energia. 

Essas políticas recém-adicionadas permitem que os administradores controlem estados de energia, como o tempo de ocioso. Para ler mais sobre cada política individual, clique no link dessa política.

|     Link de documentação de política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas polícias para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas [Restrições comuns de dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Para uma experiência consistente no HoloLens 2, certifique-se de que os valores para DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery sejam definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Consulte [Display, sleep, and hibernate idle timers](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre o modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Políticas de atualização recém-habilitadas para o HoloLens
- Mais opções para quando as Atualizações são instaladas ou desabilitando o botão Pausar Atualizações para garantir atualizações.

Essas políticas de atualização agora estão habilitadas em dispositivos HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Detalhes completos sobre essas políticas de atualização e como usá-las para dispositivos HoloLens podem ser lidos aqui em [Gerenciar atualizações do HoloLens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilidade da página Configurações Habilitadas para o HoloLens 2
- Maior controle da interface do usuário no Aplicativo de Configurações, que pode ser confundido para mostrar uma seleção limitada de páginas.

Agora, habilitamos uma política que permite que os administradores de IT impeçam que páginas específicas no aplicativo Configurações do Sistema sejam visíveis ou acessíveis, ou para fazer isso para todas as páginas, exceto as especificadas. Para saber como personalizar totalmente esse recurso, clique no link abaixo.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais configurações de página você pode personalizar no HoloLens 2, visite nossa página [URIs de Configurações.](settings-uri-list.md) 
 
![Captura de tela do horário ativo sendo modificado no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de pesquisa
Enquanto estiver no Modo de Pesquisa, o HoloLens 2 se torna uma ferramenta potente para pesquisa de visão de computador. Em comparação com edições anteriores, o Modo de Pesquisa do HoloLens 2 tem as seguintes vantagens:
-   Além dos sensores expostos no Modo de Pesquisa do HoloLens (1ª geração), agora fornecemos acesso a sensor de IMU, incluindo acelerômetro, giroscópio e magnetômetro.
-   O HoloLens 2 fornece novos recursos que podem ser usados em conjunto com o Modo de Pesquisa. Especificamente, o acesso a APIs de controle de mãos e rastreamento de olhos articulados que podem fornecer um conjunto mais rico de experimentos.

Os pesquisadores agora têm a opção de habilenciar o Modo de Pesquisa em seus dispositivos HoloLens para acessar todos esses fluxos de sensores de imagem brutos voltados para externos. O Modo de Pesquisa do HoloLens 2 também fornece acesso às leituras de acelerômetro, giroscópio e magnetômetro. Para proteger a privacidade dos usuários, as imagens brutas da câmera de rastreamento de olhos não estão disponíveis por meio do Modo de Pesquisa, mas a direção de visão está disponível por meio de APIs existentes.

Confira a [documentação do Modo de Pesquisa](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

### <a name="recording-length-increased"></a>Comprimento da gravação aumentado
Devido aos comentários dos clientes, aumentamos o comprimento de gravação de [capturas de realidade misturada.](holographic-photos-and-videos.md) As capturas de realidade misturada não serão mais limitadas a 5 minutos por padrão, mas, em vez disso, calcularão o comprimento máximo de gravação com base no espaço em disco disponível. O dispositivo estima a duração máxima da gravação de vídeo com base no espaço em disco disponível até 80% do espaço total em disco.

> [!NOTE]
> O HoloLens usará o comprimento padrão de gravação de vídeo (5 minutos) se ocorrer um dos seguintes:
> - A duração máxima de gravação máxima estimada é menor do que os 5 minutos padrão.
> - O espaço em disco disponível é inferior a 20% do espaço total em disco.

Você pode encontrar os requisitos completos em [nossa documentação de](holographic-photos-and-videos.md#maximum-recording-length) fotos e vídeos holográficos. 

### <a name="improvements-and-fixes-in-the-update"></a>Melhorias e correções na atualização:
- Mais telas no OOBE agora estão no modo escuro.
- Saiba mais conteúdo deve apontar para a Declaração de Privacidade mais recente online.
- Resolvido um problema em que os usuários não podiam provisionar perfis VPN por meio de pacotes de provisionamento.
- Problema de configuração de proxy corrigido para conexão VPN.
- Política atualizada para desabilitar a enumeração de funções USB por meio do MDM para NCM para AllowUsbConnection.
- Resolvido um problema que impedia que um dispositivo HoloLens aparecendo no Explorador de Arquivos sobre o Protocolo de Transferência de Mídia (MTP) quando o dispositivo é definido como um [quiosque](hololens-kiosk.md)de aplicativo único. Observe que o MTP (e a conexão USB em geral) ainda podem ser desabilitados usando a [política AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Correção de um problema em que os ícones no menu Iniciar eram dimensionados corretamente no modo Quiosque.
- Corrigido um problema devido à interferência de cache HTTP no modo de quiosque direcionado para grupos do Azure AD.
- Corrigimos um problema em que os usuários não conseguiam usar o botão Par após habilitar o modo desenvolvedor com pacotes de provisionamento, a menos que eles desabilita e reabilitar o modo desenvolvedor.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versão 1903 - Atualização de novembro de 2020
- Build 18362.1085

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente nosso build de versão de recursos mais recente do Windows Holographic, versão 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versão 2004 - Atualização de outubro de 2020
- Build 19041.1124
 
Melhorias e correções na atualização:

- Foi removida uma verificação desnecessária que causou falha no sistema de tempo de execução.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versão 1903 - Atualização de outubro de 2020
- Build 18362.1081

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente nossas versões mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versão 2004 - Atualização de setembro de 2020
- Build 19041.1117

Melhorias e correções na atualização:

- Resolve um problema que impedia Visual Studio depurar um aplicativo quando SupportsMultipleInstances="true" está presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy NCSI para resolver falha na detecção da Internet por proxy de rede. NCSI pode usar proxy de máquina e proxy por perfil para detecção de conectividade com a Internet. O proxy por usuário terá suporte do NCSI na versão futura.
- Na maioria dos dispositivos de Realidade Mista do Windows, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, versões anteriores do HoloLens 2 alinharam o vetor para serem perpendiculares aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores de formulário.
- Robustez de controle de mão aprimorado que resultará em menos perdas de controle em cenários específicos.
- Esta versão contém uma correção para melhorar a qualidade do data/hora de áudio, o que pode ter contribuído para problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versão 1903 - Atualização de setembro de 2020
- Build 18362.1079

Melhorias e correções na atualização:

- Na maioria dos dispositivos de Realidade Mista do Windows, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, versões anteriores do HoloLens 2 alinharam o vetor para serem perpendiculares aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre os fatores de formulário.
- Robustez de controle de mão aprimorado que resultará em menos perdas de controle em cenários específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versão 2004 - Atualização de agosto de 2020
- Build 19041.1113

Melhorias e correções na atualização:

- O aplicativo de configurações não seguirá mais o usuário em Experiências de Calibragem de Registro de Íris ou Rastreamento de Olhos.
- Correção de um bug em que a aplicação de um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como conectar-se a uma rede) falharia ao executar as outras ações após a reinicialização do dispositivo devido ao renomeamento.
- Esquema de cores modificado dos fluxos iniciais de instalação do dispositivo para melhorar a qualidade visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versão 1903 - Atualização de agosto de 2020
- Build 18362.1074

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente nossas versões mais recentes para Windows Holographic, versão 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versão 2004 - Atualização de julho de 2020
- Build 19041.1109

Melhorias e correções na atualização:

- Os desenvolvedores agora podem escolher entre habilenciar ou desabilitar ter o Device Portal exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Alterou o brilho da caixa de entrada padrão para 100%.
- Resolvido um problema sobre o encaminhamento HTTPS para o Windows Device Portal no HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versão 1903 - Atualização de julho de 2020
- Build 18362.1071

Melhorias e correções na atualização:

- Corrigido um problema que poderia fazer com que os hologramas desaparecessem nos aplicativos Unity ao perder ou recuperar o controle.
- Corrigido um problema que causava a falha de aplicativos exclusivos do HoloLens no shell ao usar o Emulador do HoloLens com aceleração de hardware em determinados dispositivos.
- Resolvido um problema referente ao encaminhamento HTTPS para o Windows Device Portal no HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versão 2004 - Atualização de junho de 2020
- Build 19041.1106

Melhorias e correções na atualização:

- Os gravadores MRC personalizados agora têm novos valores padrão para determinadas propriedades se não são especificados.
  - No efeito *de vídeo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (headset imersivo))
  - No efeito *de áudio MRC*:
    - LoopbackGain (o valor atual "Ganho de áudio do aplicativo" na página Captura de Realidade Misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual "Ganho de áudio de microfone" na página Captura de Realidade Misturada no Portal de Dispositivos do Windows)
- Correção de um bug para melhorar a qualidade do áudio em cenários de captura de realidade misturada. Especificamente, essa correção deve eliminar a falha de áudio na gravação quando o menu **Iniciar** for exibido.
- Melhor estabilidade do holograma em vídeos gravados.
- Resolvido um problema em que a captura de realidade misturada não pôde gravar vídeo depois que o dispositivo foi deixado em estado de espera por vários dias.
- A API HolographicSpace.UserPresence geralmente é desabilitada para aplicativos Unity. Esse comportamento evita um problema que causava a pausa de alguns aplicativos quando o visor era invertido, mesmo se a configuração "executar em segundo plano" estivesse habilitada. A API agora está habilitada para as versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Quando você acessa o Device Portal Wi-Fi uma conexão de Wi-Fi, um navegador da Web pode impedir o acesso devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo que o certificado do dispositivo tenha sido anteriormente confiável. Nesse caso, você não pode progredir para o Device Portal, pois não há opção para ignorar avisos de segurança. Essa atualização resolveu o problema. Se o certificado de dispositivo tiver sido baixado anteriormente e confiável em um computador para remover avisos de segurança do navegador e ocorrer o erro SSL, o novo certificado deve ser baixado e confiável para lidar com os avisos de segurança do navegador.
- Habilitada a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
- Adicionada uma configuração em **Configurações**hologramas do sistema que permite que os usuários removam automaticamente todos os hologramas da casa da Realidade Misturada quando o dispositivo  >  ****  >  **** for desligado.
- Corrigido um problema que fez com que os aplicativos do HoloLens que alteram o formato de pixel para renderizar preto no emulador do HoloLens.
- Correção de um bug que causou uma falha durante o logon do Iris.
- Corrigido um problema sobre downloads repetidos do armazenamento para aplicativos já atuais.
- Correção de um bug para impedir que aplicativos imersivos abriam o Microsoft Edge repetidamente.
- Corrigido um problema com as inicializações do aplicativo Fotos nas inicializações iniciais após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versão 1903 - Atualização de junho de 2020
- Build 18362.1064

Melhorias e correções na atualização:

- Os gravadores MRC personalizados têm novos valores padrão para determinadas propriedades se não são especificados.
  - No efeito *de vídeo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (headset imersivo))
  - No efeito *de áudio MRC*:
    - LoopbackGain (o valor atual "Ganho de áudio do aplicativo" na página Captura de Realidade Misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual "Ganho de áudio de microfone" na página Captura de Realidade Misturada no Portal de Dispositivos do Windows)
- A API HolographicSpace.UserPresence geralmente é desabilitada para aplicativos Unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração para ser executado em segundo plano estiver habilitada. A API agora está habilitada para as versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Corrigido um problema que fez com que os aplicativos do HoloLens que alteram seu formato de pixel para renderizar em preto no Emulador do HoloLens.
- Corrigido um problema sobre as inicializações do aplicativo Fotos nas inicializações iniciais após a atualização da versão 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versão 2004  
- Build - 19041.1103

A atualização de software principal de maio de 2020 para HoloLens 2, *Windows Holographic, versão 2004* inclui uma série de novos recursos interessantes, como suporte para Windows Autopilot, modo escuro do aplicativo, suporte a Ethernet USB para hotspots 5G/LTE e muito mais. Para atualizar para a versão **** mais recente, abra o aplicativo Configurações, vá para Atualizar & Segurança e selecione o botão   Verificar **** **atualizações.**   

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Configurar e configurar previamente novos dispositivos para produção usando o Windows AutoPilot                 |
|       Suporte ao FIDO 2                             |          Suporte para Chaves de Segurança FIDO2 para habilitar autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar perfeitamente um pacote de provisionamento de uma unidade USB ao holoLens                              |
|       Status da instalação do aplicativo                 |          Verifique o status da instalação no aplicativo Configurações para que os aplicativos tenham sido pressionados para o HoloLens 2 via MDM               |
|       Provedores de serviços de configuração (CSPs)   |          Adicionados novos provedores de serviços de configuração para aprimorar os recursos de controle de administrador                 |
|       Suporte usb 5G/LTE                       |          A funcionalidade de Ethernet USB expandida habilita o suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que suportam modos escuro e claro, melhorando a experiência de exibição        |
|       Comandos de voz                             |          Suporte para comandos adicionais de voz do sistema para controlar o HoloLens de mãos livres                           |
|       Melhorias no controle de mãos                 |          As melhorias de controle de mão fazem com que os botões e as interações de ardósia 2D mais precisas                        |
|       Melhorias e correções de qualidade                 |          Várias melhorias de desempenho e confiabilidade do sistema em toda a plataforma                            |

### <a name="support-for-windows-autopilot"></a>Suporte para Windows Autopilot

O Windows Autopilot para HoloLens 2 permite ao canal de vendas de dispositivo pré-inscrever o HoloLens no locatário do Intune. Quando os dispositivos chegam, eles estão prontos para se auto-implantar como dispositivos compartilhados em seu locatário. Para aproveitar a auto-implantação, o dispositivo deve se conectar a uma rede durante a primeira tela na instalação usando um USB-C-para-Ethernet.

Depois que um usuário inicia o processo de auto-implantação do Autopilot, o processo conclui as seguintes etapas:

1. Ingresso do dispositivo no Azure Active Directory (Azure AD)
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe os perfis de rede, certificados e políticas direcionados aos dispositivos.
1. Provisione este dispositivo.
1. Apresente a tela de entrada ao usuário.

Saiba mais no guia de avaliação [do Windows Autopilot para HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Entre em contato com o Gerente de Conta para ingressar na visualização do AutoPilot agora. Os dispositivos prontos para piloto automático começarão a enviar em breve.*

### <a name="fido2-security-key-support"></a>Suporte a chave de segurança FIDO2

Alguns usuários compartilham um dispositivo HoloLens com outros em um ambiente de trabalho ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário longos e senhas. O Fast Identity Online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre perfeitamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação sem senha baseado em padrões "desfragrável" que pode vir em qualquer fator de formulário. FIDO é um padrão aberto para autenticação sem senha. Ele permite que os usuários e organizações entre em seus recursos sem um nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma interna em um dispositivo.

Para começar, consulte [Enable passwordless security key sign-in](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Registro MDM aprimorado por meio do pacote de provisionamento

Os pacotes de provisionamento permitem definir a configuração do HoloLens por meio de um arquivo de configuração, em vez de por meio da experiência inicial do HoloLens. Anteriormente, os pacotes de provisionamento tinham que ser copiados para a memória interna do HoloLens. Agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizar em vários dispositivos HoloLens e você pode provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também suportam um campo para se registrar no gerenciamento de dispositivos para que não haja configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do Designer de Configuração do Windows na Windows Store para o computador.
1. Selecione **Provisionr dispositivos HoloLens**  >  **Provisione dispositivos HoloLens 2**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C a qualquer HoloLens com flash recente. Em seguida, **pressione os botões de alimentação**de volume para baixo para aplicar seu pacote de  +  **** provisionamento.

### <a name="line-of-business-application-install-status"></a>Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento de aplicativos MDM para aplicativos de linha de negócios é fundamental para o HoloLens. Os administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **Configurações**Contas Acessar trabalho ou  >  ****  >  **escola**  >  **Clique em Informações da sua**  >  **conta**.

### <a name="additional-csps-and-policies"></a>CSPs e políticas adicionais

Um [provedor de serviços de configuração (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou excluir configurações em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar os administradores de controle sobre dispositivos HoloLens implantados. Para ver a lista de CSPs suportados pelo HoloLens, consulte [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novidade nesta versão:

**Política CSP** 

O provedor de serviços de configuração de política permite que a empresa configure políticas em dispositivos Windows. Nesta versão, adicionamos novas políticas para o HoloLens, que estão listadas aqui. Para saber mais, confira [CSPs de política com suporte do HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

O provedor de serviço de configuração networkQoSPolicy cria políticas de QoS (qualidade de serviço de rede). Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, confira [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Suporte usb ethernet expandido para dispositivos 5G/LTE conectados

O suporte foi adicionado para habilitar determinados dispositivos de banda larga móvel, como telefones 5G/LTE e hotspots Wi-Fi, quando eles são conectados ao HoloLens 2 via USB. Esses dispositivos agora são exibidos nas **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos de banda larga móveis que exigem um driver externo.) Essa funcionalidade habilita conexões de alta largura de banda quando Wi-Fi não está disponível e Wi-Fi a fixação não é suficiente. Para saber mais sobre dispositivos USB com suporte, consulte [Connect to Bluetooth e USB-C devices](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Melhorias no controle de mãos

Esta versão inclui várias melhorias de controle de mão:

- **Apontando estabilidade de pose:** O sistema agora resistem a inclinar o dedo de índice quando ele é ocluso pela palma da mão. Essa alteração melhora a precisão quando você pressiona botões, digita, rola conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Melhoramos a detecção do gesto de toque de ar. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta as mãos para os lados.
- **Confiabilidade da opção do usuário:** O sistema agora é mais rápido e confiável na atualização do tamanho da mão ao compartilhar um dispositivo.
- **Roubo de mão reduzido:** Melhoramos o tratamento de casos em que há mais de duas mãos à vista dos sensores. Se várias pessoas estão trabalhando juntas, agora há uma chance muito menor de que a mão controlada "pule" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Corrigido um problema que fez com que o controle de mão parasse de funcionar quando o dispositivo está sob alta carga.

### <a name="dark-mode"></a>Modo escuro

Muitos aplicativos do Windows agora suportam modos escuro e claro. Os usuários do HoloLens 2 podem escolher o modo padrão para aplicativos que suportam ambos. Após a atualização, o modo de aplicativo padrão é "escuro", **** mas você pode alterar facilmente essa configuração: Navegar até Configurações Cores do Sistema Escolha seu  >  ****  >  ****  >  **modo de aplicativo padrão**. 

Esses aplicativos "in-box" suportam o modo escuro: 

- Configurações 
- Microsoft Store 
- Mail 
- Calendário 
- Explorador de Arquivos 
- Hub de Feedback 
- OneDrive 
- Fotos 
- Visualizador 3D 
- Filmes e TV 

![Janelas de modo escuro em bloco](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, [consulte Use your voice to operate HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulte [Também idiomas com suporte para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Atualizações da Cortana

O aplicativo atualizado se integra ao Microsoft 365 para ajudá-lo a fazer mais em seus dispositivos (no momento, US-English apenas). No HoloLens 2, a Cortana não dá mais suporte a determinados comandos específicos do dispositivo, como ajustar volume ou reiniciar. Essas opções agora são suportadas pelos novos comandos de voz do sistema. Saiba mais sobre o novo aplicativo Cortana em nosso [blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduzido um sistema de calibragem de exibição ativo. Esse recurso melhora a estabilidade e o alinhamento dos hologramas. Eles agora permanecem no local quando você move sua cabeça de um lado para outro.
- Correção de um bug em que Wi-Fi streaming para o HoloLens foi interrompido periodicamente. Se um aplicativo indicar que ele precisa de baixa latência de streaming, implemente a correção chamando a [função SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Corrigido um dispositivo travado que ocorreu durante o streaming no modo de pesquisa.
- Correção de um bug em que, em alguns casos, o usuário certo não seria exibido na tela de logon ao retomar uma sessão.
- Corrigido um problema em que os usuários não podiam exportar logs MDM por **meio de Configurações**.
- Corrigido um problema em que a precisão do rastreamento de olhos imediatamente após a configuração imediata poderia ser menor do que o esperado.
- Corrigido um problema em que o subsistema de rastreamento de olhos falhou ao inicializar ou executar a calibragem em determinadas condições.
- Corrigido um problema em que a calibragem dos olhos seria solicitado para um usuário já calibrado.
- Corrigido um problema em que um driver falharia durante a calibragem dos olhos.
- Corrigido um problema em que pressões repetidas de botão de energia podem causar um tempo de tempo de 60 segundos do sistema e uma falha no shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um **botão Compartilhar** no Hub de Feedback para que os usuários possam compartilhar comentários com mais facilidade.
- Correção de um bug em que o RoboRaid não foi instalado corretamente.

### <a name="known-issues"></a>Problemas conhecidos

- Um problema com o idioma do sistema zh-CN impede que os comandos de voz capturem uma captura de realidade mista ou exibem o endereço IP do dispositivo.
- Um problema exige que você iniciar o aplicativo Cortana depois de iniciar o dispositivo para usar a ativação de voz "Ei Cortana". Se você tiver atualizado de uma com build 18362, também poderá ver um segundo telha de aplicativo para a versão anterior do aplicativo Cortana que não funciona mais em **Iniciar**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versão 1903 - Atualização de maio de 2020 
- Build 18362.1061

Esta atualização de qualidade mensal não contém alterações notáveis porque a equipe estava trabalhando na Versão 2004 do Windows Holographic, conforme descrito anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versão 1903 - Atualização de abril de 2020
- Build 18362.1059

**Modo escuro para aplicativos com suporte** 

Muitos aplicativos do Windows suportam o modo escuro e claro. Os clientes do HoloLens 2 agora podem escolher o modo padrão para aplicativos que suportam ambos os esquemas de cores. Com base nos comentários do cliente, **definimos** o modo de aplicativo padrão como "escuro", mas você pode alterar facilmente essa configuração a qualquer momento: Navegue até Configurações > System > Colors para encontrar "Escolher seu modo de aplicativo **padrão".**

Esses aplicativos "in-box" suportam o modo escuro:
- Configurações
- Microsoft Store
- Mail
- Calendário
- Explorador de Arquivos
- Hub de Feedback
- OneDrive
- Fotos
- Visualizador 3D
- Filmes e TV

**Melhorias e correções também na atualização:** 
- Certifique-se de que as sobreposições de shell sejam incluídas em capturas de realidade misturada.
- Os desenvolvedores irreais agora podem usar a página De exibição 3D no Device Portal para testar e depurar seus aplicativos.
- Melhor estabilidade do holograma na captura de realidade misturada quando o *algoritmo HolographicDepthReprojectionMethod DepthReprojection* é usado.
- Correção do erro "Classe de API WinRT IStreamSocketListener não registrada" em aplicativos ARM de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versão 1903 - Atualização de março de 2020 
- Build 18362.1056

Melhorias e correções na atualização:

- Melhor estabilidade do holograma na captura de realidade misturada quando o *algoritmo HolographicDepthReprojectionMethod AutoPlanar* é usado.
- Certifique-se de que o sistema de coordenadas anexado a um exemplo de MF de profundidade seja consistente com a documentação pública.
- Produtividade aprimorada do desenvolvedor permitindo que os clientes colem grandes quantidades de texto por meio do portal do dispositivo.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versão 1903 - Atualização de fevereiro de 2020 
- Build 18362.1053

Melhorias e correções na atualização:

- Desabilitada temporariamente a API HolographicSpace.UserPresence para aplicativos Unity. Essa alteração evita um problema que causava a pausa de alguns aplicativos quando o visor foi invertido, mesmo se a configuração "executar em segundo plano" estivesse habilitada.
- Corrigimos uma falha HUP aleatória causada pelo rastreamento de mãos, no qual o usuário reparou em um congelamento da interface do usuário e, em seguida, voltou ao shell após vários segundos.
- Controle de mão aprimorado para que, quando você cutuque com o dedo indicador, a parte superior desse dedo tem menos probabilidade de se curvar inesperadamente.
- Confiabilidade aprimorada do controle de cabeça, mapeamento espacial e outros tempos de execução.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versão 1903 - Atualização de janeiro de 2020 
- Build 18362.1043
 
Melhorias e correções na atualização:

- Estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador do HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versão 1903 - Atualização de dezembro de 2019 
- Build 18362.1042

Melhorias e correções na atualização:

- Introduzido correções de reprodução de último estágio (LSR). Renderização visual aprimorada de hologramas para parecer mais estável e nítido, explicando com mais precisão sua profundidade. Esse sintoma será mais perceptível após essa atualização se os aplicativos não definirem a profundidade dos hologramas corretamente.
- Estabilidade fixa de aplicativos exclusivos e navegação entre aplicativos exclusivos.
- Resolvido um problema em que a captura de realidade mista não pôde gravar vídeo depois que o dispositivo estava em estado de espera por vários dias.
- Estabilidade aprimorada do holograma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versão 1903 - Atualização de novembro de 2019 
- Build 18362.1039

Melhorias e correções na atualização:

- Funcionalidade fixa dos comandos **Selecionar** voz durante a configuração inicial para en-CA e en-AU.
- Qualidade visual aprimorada dos objetos colocados longe nas versões mais recentes do Unity e do Mixed Reality Toolkit (MRTK).
- Corrigimos problemas de endereçamento com aplicativos holográficos travados em um estado pausado na inicialização até que o menu Iniciar fosse aberto e fechado.
- Correções e melhorias de conformidade do tempo de execução do OpenXR para o HoloLens 2 e o emulador.
