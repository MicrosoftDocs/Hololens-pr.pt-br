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
ms.date: 1/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8dd5f4c50ebdab202d24d4a52d393b8bee086c7a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284092"
---
# Notas de versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus dispositivos HoloLens, continuaremos a lançar atualizações de recursos, bugs e segurança. Nesta página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização mais recente do HoloLens 2, você pode verificar se há atualizações e atualizar [manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter o FFU (Full Flash Update) para piscar seu dispositivo por meio do [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). O [download](https://aka.ms/hololens2download) é mantido atualizado e fornece o build mais recente disponível para o público em geral.

Estamos animados em iniciar a versão de versões We will be flighting to the Dev Channel for the latest updates. Continuaremos com nossas [notas do HoloLens Insider](hololens-insider.md) à medida que adicionarmos mais recursos e atualizações às nossas versões do Windows Insider. Fique animado e pronto para misturar essas atualizações à sua realidade. 

>[!NOTE]
> Para ler as notas de versão do Emulador do HoloLens, [visite o arquivo morto.](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)

## Windows Holographic, versão 20H2 - Atualização de janeiro de 2021
- Build 19041.1134

Melhorias e correções na atualização:

- Desempenho aprimorado durante a inicialização, retomada e troca de usuário quando há muitos usuários no dispositivo.
- Adicionado suporte arm32 para [o Modo de Pesquisa](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## Windows Holographic, versão 1903 - Atualização de janeiro de 2021
- Build 18362.1091

Esta atualização de qualidade mensal não contém alterações notáveis. Recomendamos que você experimente nossas versões mais recentes para o Windows Holographic, versão 2004.

## Windows Holographic, versão 20H2 – Atualização de dezembro de 2020
- Build 19041.1131

### Instalar aplicativos no HoloLens 2 por meio do Instalador de Aplicativo

Estamos **adicionando um novo recurso (Instalador** de Aplicativo) para permitir que você instale aplicativos mais facilmente em seus dispositivos HoloLens 2. O recurso estará **conectado por padrão para dispositivos não-manageados.** Para evitar a interrupção nas empresas, o instalador de aplicativo **não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo é considerado "gerenciado" **se qualquer** um dos seguintes for verdadeiro:
- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado com o [pacote de provisionamento](hololens-provisioning.md)
- A [identidade do](hololens-identity.md) usuário é o Azure AD

Agora você pode instalar aplicativos sem precisar habilitar o Modo de Desenvolvedor ou usar o Device Portal.  Basta baixar (por USB ou por meio do Edge) o Appx Bundle para seu dispositivo e navegar até o Pacote Appx no Explorador de Arquivos para ser solicitado a dar início à instalação.  Como alternativa, [inicie uma instalação a partir de uma página da Web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Assim como os aplicativos instalados da Microsoft Store ou sideload usando o recurso de implantação [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) do aplicativo [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) LOB do MDM, os aplicativos precisam ser assinados digitalmente com a Ferramenta de Assinatura e o certificado usado para assinar deve ser confiável para o dispositivo HoloLens antes que o aplicativo possa ser implantado.

**Instruções de instalação do aplicativo.**

1.  Certifique-se de que seu dispositivo não seja considerado gerenciado
1.  Verifique se o dispositivo HoloLens 2 está ligado e conectado ao computador
1.  Verifique se você está conectado ao dispositivo do HoloLens 2
1.  Em seu computador, navegue até seu aplicativo personalizado e copie yourapp.appxbundle para yourdevicename\Internal Storage\Downloads.   Depois de terminar de copiar o arquivo, você poderá desconectar seu dispositivo
1.  No dispositivo HoloLens 2, abra o Menu Iniciar, selecione Todos os aplicativos e inicie o aplicativo Explorador de Arquivos.
1.  Navegue até a pasta Downloads. Talvez seja necessário que, no painel esquerdo do aplicativo, selecione Este dispositivo primeiro e, em seguida, navegue até Downloads.
1.  Selecione o arquivo yourapp.appxbundle.
1.  O Instalador de Aplicativo será lançado. Selecione o botão Instalar para instalar seu aplicativo.
O aplicativo instalado será automaticamente lançado após a conclusão da instalação.

Você pode encontrar exemplos de [aplicativos no GitHub de exemplos](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) universais do Windows para testar esse fluxo.

Leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o Instalador de Aplicativo.](app-deploy-app-installer.md)  

![Instalando exemplos de MRTK por meio do Instalador de Aplicativo](images/hololens-app-installer-picture.jpg)

### Melhorias e correções na atualização:

- O rastreamento de mãos agora mantém o rastreamento em muitos casos novos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, apenas a posição da palma continua a ser atualizada com base na mão real do usuário, enquanto as outras conjuntas são inferidos com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência do rastreamento em movimentos como desespetivo, lançamento, lançamento e bate-cabeça.  Ele também ajuda em casos em que a mão está perto de uma superfície ou segurando um objeto.  Quando as junções de mão [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) estão sendo inferidos, o valor de precisão por conjunto será definido como "Aproximado" em vez de "Alto".
- Correção de um problema em que a redefinição de PIN para contas do Azure AD mostrava um erro "Algo deu errado.
- Os usuários devem ver muito menos falhas de OOBE pós-inicialização ao iniciar ET, Íris do aplicativo configurações, novo usuário ou notificação do sistema.
- Os usuários devem ter o fuso horário correto saindo da OOBE.

## Windows Holographic, versão 1903 – Atualização de dezembro de 2020
- Build 18362.1088

Essa atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente nossa versão mais recente do Windows Holographic, versão 20H2 – Atualização de dezembro de 2020, e o novo recurso instalador de aplicativo adicionado na complicação.


## Windows Holographic, versão 20H2
- Build 19041.1128

O Windows Holographic, versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para usuários do HoloLens 2 e profissionais de TI. Do Posicionamento Automático aos Olhos, ao Gerenciador de Certificados em Configurações, à funcionalidade aprimorada do Modo de Quiosque e aos novos recursos de configuração do Autopilot. Essa nova atualização permite que as equipes de IT tomem um controle mais granular para configurar e gerenciar dispositivos HoloLens e oferece aos usuários experiências holográficas ainda mais perfeitas. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. O número do build principal permanecerá o mesmo, e o Windows Update indicará uma versão mensal para a versão 2004 (build 19041). Você pode ver o número de com build na tela Configurações > Sobre para confirmar se está no build 19041.1128 mais recente disponível. Para atualizar para a versão mais recente, abra o aplicativo Configurações, vá para Atualizar & Segurança e toque em Verificar Atualizações. Para obter mais informações sobre como gerenciar as atualizações do HoloLens, visite [esta página.](https://docs.microsoft.com/hololens/hololens-updates)

### Novidades no Windows Holographic, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte Automático de Posição Ocular](hololens-release-notes.md#auto-eye-position-support) | Calcula ativamente as posições dos olhos sem que os usuários façam a calibragem do Rastreamento de Olhos.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que novos métodos mais simples instalem e removam certificados do aplicativo Configurações.     |
| [Provisionamento de início automático via USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Os pacotes de provisionamento em unidades USB solicitam automaticamente a página de provisionamento na OOBE.                                                         |
| [Confirmar automaticamente pacotes de provisionamento na OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante a OOBE na página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a iniciação automática de provisionamento e a confirmação automática juntos. |
| [Usando o Autopilot com Wi-Fi conexão](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o autopilot do dispositivo Wi-Fi sem a necessidade de adaptador ethernet. |
| [O Provedor de Soluções na Nuvem da Microsoft do Tenantlockdown e AutoPilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Depois que o registro do locatário e a política for aplicada, o dispositivo só poderá ser inscrito nesse locatário sempre que o dispositivo for redefinido ou piscado novamente. |
| [Acesso Global Atribuído](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para o modo de quiosque de vários aplicativos que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
| [Iniciar automaticamente um aplicativo no quiosque de vários aplicativos](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define um aplicativo para ser lançado automaticamente ao entrar em um modo de quiosque de vários aplicativos.                                                        |
| [Alterações no comportamento do modo de quiosque para o tratamento de falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Falha no modo de quiosque agora tem fallback restritivo.                                                                                                |
| [Políticas do HoloLens](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para o HoloLens.     |
| [Cache da associação do Grupo do Azure AD para Quiosque offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os usuários usem o cache de associação de grupo para usar o modo de quiosque offline por um número definido de dias.                                        |
| [Novas políticas de restrição de dispositivo para o HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Políticas de gerenciamento de dispositivo habilitadas recentemente para o HoloLens 2.                                                                                |
| [Novas políticas de energia para o HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recém-suportadas para configurações de tempo de energia.  |
| [Políticas de atualização](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas recém-habilitadas permitindo o controle de atualizações.           |
| [Visibilidade da página Configurações Habilitadas para o HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Política para escolher quais páginas são vistas no aplicativo Configurações.             |
| [Modo de pesquisa](hololens-release-notes.md#research-mode) | Usando o modo pesquisa no HoloLens 2. |
| [Comprimento de gravação aumentado](hololens-release-notes.md#recording-length-increased) | As gravações MRC não são mais a 5 minutos. |
| [Melhorias e correções na atualização](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correções adicionais na atualização.   |

### Suporte Automático de Posição Ocular

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

Essas informações podem ser encontradas posteriormente com outras [informações de calibragem.](hololens-calibration.md#auto-eye-position-support) 

### Gerenciador de certificados

- Ferramentas aprimoradas de auditoria, diagnóstico e validação para segurança e conformidade de dispositivos por meio do novo Gerenciador de Certificados. Esse recurso permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows Holographic versão 20H2, estamos adicionando um Gerenciador de Certificados no aplicativo Configurações do HoloLens 2. Vá para **Configurações > Atualizar & segurança > certificados.** Esse recurso fornece uma maneira simples e amigável de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de Certificados, os administradores e os usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e em conformidade. 

-   **Auditoria:** Capacidade de validar se um certificado foi implantado corretamente ou para confirmar se ele foi removido adequadamente. 
-   **Diagnóstico:** Quando surgirem problemas, a validação de que os certificados apropriados existem no dispositivo economiza tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade pretendido e está funcional pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em maior escala.

Para encontrar um certificado específico na lista rapidamente, há opções para classificar por nome, armazenar ou expirar data. Os usuários também podem pesquisar diretamente por um certificado. Para exibir propriedades de certificado individuais, selecione o certificado e clique em **Informações.** 

A instalação do certificado atualmente dá suporte a arquivos .cer e .crt. Os proprietários de dispositivos podem instalar certificados no Computador Local e no Usuário Atual;  todos os outros usuários só podem instalar no Usuário Atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário de Configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

#### Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um computador.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no HoloLens 2.
1.  Navegue **até Configurações do Aplicativo > Atualizar & segurança > certificados**e selecione Instalar um certificado.
1.  Clique **em Importar Arquivo** e navegue até o local em que você salvou o certificado.
1.  Selecione **Local do Armazenamento.**
1.  Selecione **o Armazenamento de Certificados.**
1.  Clique em **Instalar**.

O certificado agora deve ser instalado no dispositivo.

#### Para remover um certificado: 
1. Navegue **até Configurações do Aplicativo > Atualização e Segurança > Certificados.**
1. Procure o certificado pelo nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique **em Remover**
1. Selecione **Sim** quando solicitado a confirmação.

![Visualizador de certificados no aplicativo Configurações](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado](images/certificate-device-install.jpg)

Essas informações podem ser encontradas [posteriormente em uma nova página do Gerenciador de Certificados.](certificate-manager.md)

### Provisionamento de início automático via USB

- Processos automatizados permitindo menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante OOBE.

Antes desta versão, os usuários tinham que iniciar a tela de provisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora os usuários podem ignorar a combinação de botões usando um Pacote de Provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagido da OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB for deixada conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como observará outros que estão conectados.

Para obter mais informações sobre como aplicar pacotes de provisionamento durante a OOBE, visite a documentação de [provisionamento do HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Informações adicionais [sobre o provisionamento](hololens-provisioning.md#auto-launch-provisioning-from-usb) de início automático de um USB podem ser encontradas na documentação de provisionamento do HoloLens.

### Confirmar automaticamente pacotes de provisionamento na OOBE
- Processo automatizado permitindo menos interação do usuário, quando a página Pacote de Provisionamento é exibida, ela aplicará automaticamente todos os pacotes listados.

Quando a tela principal de provisionamento aparece, o OOBE conta 10 segundos antes de começar automaticamente a aplicar todos os pacotes de provisionamento. Os usuários ainda podem [confirmar ou cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) dentro de 10 segundos depois de verificar os pacotes esperados.

### Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para interações reduzidas do dispositivo para provisionamento. 

Combinando a iniciação automática do provisionamento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um usuário pode provisionar dispositivos HoloLens 2 automaticamente sem usar a interface do usuário do dispositivo ou até mesmo usar o dispositivo. Você pode continuar a usar a mesma unidade USB e o pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos ao mesmo tempo na mesma área. 

1. [Crie um pacote de provisionamento usando](hololens-provisioning.md) o [Designer de Configuração do Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copie o pacote para uma unidade de armazenamento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Quando [o Advanced Recovery Companion tiver](https://www.microsoft.com/store/productId/9P74Z35SFRS8) concluído a flash do dispositivo, desconectar o cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. Quando o dispositivo HoloLens 2 é inicializado na configuração inicial pelo usuário, ele detecta automaticamente o pacote de provisionamento na unidade USB e inicia a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Seu dispositivo agora está configurado e [exibirá a tela Provisionamento bem-sucedido.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Usando o Autopilot com Wi-Fi conexão
- Removida a necessidade de adaptadores USB-C para ethernet reduzir as necessidades de hardware, habilitando o Autopilot para funcionar Wi-Fi dispositivos conectados.

Agora, durante a OOBE, depois de conectar o HoloLens 2 com Wifi, o OOBE verificará se há um perfil do Autopilot para o dispositivo. Se uma for encontrada, ela será usada para concluir o restante do fluxo de inscrição e junção do AAD. Em outras palavras, usar ethernet para USB-C ou Wi-Fi para adaptador USB-C não é mais um requisito, no entanto, eles continuam a funcionar se fornecidos no início da OOBE. Saiba mais sobre [o Autopilot para dispositivos HoloLens 2.](hololens2-autopilot.md)

### CSP do Tenantlockdown e AutoPilot
- Mantém os dispositivos no locatário da organização bloqueando-os para o locatário, mesmo através da reinicialização do dispositivo ou do reflash. Com mais segurança, desautorizando a criação da conta por meio do provisionamento. 

Os dispositivos HoloLens 2 agora são compatíveis com CSP TenantLockdown a partir [do Windows Holographic versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

O Provedor de Soluções na Nuvem da Microsoft [TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) permite que o HoloLens 2 seja vinculado a inscrição do MDM usando apenas o Autopilot. Depois que o nó RequireNetworkInOOBE do CSP do TenantLockdown for definido com valor verdadeiro ou falso (definido inicialmente) no HoloLens 2, esse valor permanece no dispositivo, apesar de atualizar novamente, atualizações do sistema operacional, etc. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, o OOBE aguarda indefinidamente que o perfil do Autopilot seja baixado e aplicado com sucesso, após a conectividade de rede. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, as seguintes operações não serão permitidas no OOBE: 
- Criação de usuário local usando provisionamento do tempo de execução 
- Executando a operação de ingresso no Microsoft Azure Active Directory por meio de provisionamento em tempo de execução 
- Seleção de proprietários do dispositivo na experiência do OOBE 

#### Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique true para o nó RequireNetworkInOOBE, conforme mostrado a seguir.
O valor OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configurar o bloqueio de locatário via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Depois que esta configuração de dispositivo for aplicada com sucesso no dispositivo Hololens 2, os efeitos do TenantLockdown estarão ativos.

#### Como desmarcar o RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune? 
1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração de dispositivos criada acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em OMA-URI personalizado e especifique falso para RequireNetworkInOOBE como mostrado a seguir. O valor OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE definida como falso via OMA-URI no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Assim que esta configuração de dispositivo for aplicada com sucesso no dispositivo Hololens 2, os efeitos do TenantLockdown ficarão inativos. 

#### O que aconteceria durante o OOBE, se o perfil do Autopilot não fosse atribuído em um HoloLens depois que TenantLockdown fosse definido como verdadeiro? 
O OOBE aguardará indefinidamente o download do perfil do Autopilot e a caixa de diálogo a seguir será apresentada. Para remover os efeitos do TenantLockdown, o dispositivo deve ser registrado com seu locatário original primeiro usando apenas o Autopilot e o RequireNetworkInOOBE desmarcado, conforme descrito na etapa anterior antes que as restrições introduzidas pelo CSP do TenantLockdown sejam removidas. 

![Modo de exibição no dispositivo quando a política for imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

Essas informações agora podem ser encontradas junto com o restante do Autopilot em [Tenantlockdown CSP e Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### Acesso Global Atribuído – Modo de Quiosque
- Gerenciamento de identidade reduzido para Quiosque, habilitando o novo método kiosk que aplica o modo de quiosque no nível do sistema.

Esse novo recurso permite que um administrador de IT configure um dispositivo do HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com nenhuma identidade no sistema e se aplica a todos que entrarem no dispositivo. Leia sobre esse novo recurso em detalhes no quiosque de acesso atribuído [global do HoloLens.](hololens-global-assigned-access-kiosk.md)

### Início automático de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência focada na abertura automática de aplicativos, aumentando ainda mais as seleções de interface do usuário e aplicativo escolhidas para experiências do modo quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e apenas 1 aplicativo pode ser designado para iniciar automaticamente usando o atributo realçado abaixo na configuração de Acesso Atribuído. 

O aplicativo é automaticamente lançado quando o usuário se insiciona. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Alterações no comportamento do modo de quiosque para o tratamento de falhas
- Modo de Quiosque mais seguro eliminando os aplicativos disponíveis em falhas no modo de quiosque. 

Anteriormente, ao encontrar falhas na aplicação do modo de quiosque, o HoloLens usava para exibir todos os aplicativos no menu Iniciar. Agora, no Windows Holographic versão 20H2 no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, como abaixo: 

![Imagem da aparência do modo de quiosque agora quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### Políticas do HoloLens
- Opções de gerenciamento de dispositivos especificamente para o HoloLens criadas para gerenciar o dispositivo. 

Novas políticas de realidade misturada foram criadas para dispositivos HoloLens 2 no Windows Holographic versão 20H2. As novas configurações controláveis incluem: definição de brilho, definição de volume, desabilitação de gravação de áudio em capturas de realidade misturada, definição de quando o diagnóstico pode ser coletado e cache de associação de grupo do AAD.  

| Nova política do HoloLens                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados para que o pressionamento não altere o brilho.       | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que botões de volume sejam desabilitados para que o pressionando não altere o volume.               | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | Desabilita o microfone para que nenhuma gravação de áudio seja possível no HoloLens 2.                      | 1 Sim, 0 Não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os logs de diagnóstico podem ser coletados.                               | 0 Desabilitado, 1 Habilitado para Proprietários de Dispositivos, 2 Habilitado para todos (Padrão) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla por quantos dias o cache de associação de grupo do Azure AD é usado para grupos do Azure AD destinados a quiosque. | Veja abaixo.                                                           |

### Cache da associação do Grupo do Azure AD para Quiosque offline
- Habilitar o uso de Quiosques Offline com grupos do AAD por até 60 dias.

Essa política controla por quantos dias o cache de associação de grupo do Azure AD tem permissão para ser usado para configurações de Acesso Atribuído destinados a grupos do Azure AD para o usuário associado. Depois que esse valor de política for definido para um valor maior do que 0, o cache será usado caso contrário, não.  

Nome: AADGroupMembershipCacheValidityInDays Valor do URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min - 0 dias  
Máx . 60 dias 

Etapas para usar essa política corretamente: 
1. Crie um perfil de configuração de dispositivo para quiosque voltado para grupos do Azure AD e atribua-o a dispositivos do HoloLens. 
1. Crie uma configuração de dispositivo baseada em OMA URI personalizada que define esse valor de política para o número desejado de dias (> 0) e o atribui aos dispositivos do HoloLens. 
    1. O valor do URI deve ser inserido na caixa de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre mín/ máximo permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Permitir que o usuário 1 do Azure AD entre quando a Internet estiver disponível, quando o usuário entrar e a associação ao grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário 1 do Azure AD pode deixar o HoloLens offline e usá-lo no modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD N. O ponto chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que ele é membro do grupo do Azure AD para o qual a configuração de Quiosque é direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja executada para um usuário do Azure AD, o comportamento de falha será mencionado em ambientes "desconectados". 

### Novas políticas de restrição de dispositivo para o HoloLens 2
- Permite que os usuários gerenciem políticas de gerenciamento de dispositivo específicas, como bloquear a adição ou remoção de pacotes de provisionamento.

Políticas recém-habilitadas que permitem mais opções de gerenciamento de dispositivos HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Essas duas novas polícias para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas restrições [comuns de dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Em relação ao [RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)o HoloLens dará suporte apenas à configuração ./Vendor/MSFT/RemoteLock/Lock. As configurações que lidam com PIN, como redefinição e recuperação, não são suportadas.

### Novas políticas de energia para o HoloLens 2
- Mais opções para quando o HoloLens trava ou trava por meio de políticas de energia. 

Essas políticas recém-adicionadas permitem que os administradores controlem estados de energia, como o tempo de ociosidade. Para ler mais sobre cada política individual, clique no link dessa política.

|     Link de documentação de política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado no Designer de Configuração do Windows, ou seja,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas polícias para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas restrições [comuns de dispositivo.](hololens-common-device-restrictions.md)

> [!NOTE]
> Para uma experiência consistente no HoloLens 2, certifique-se de que os valores de DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery sejam definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Consulte [Exibir, sleep e hibernar temporizadores ociosos](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre o modo de espera moderno.

### Políticas de atualização recém-habilitadas para o HoloLens
- Mais opções para quando as Atualizações são instaladas ou desabilitar o botão Pausar Atualizações para garantir atualizações.

Essas políticas de atualização agora estão habilitadas em dispositivos HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Detalhes completos sobre as políticas de atualização e como usá-las para dispositivos HoloLens podem ser lidos aqui em Gerenciar atualizações [do HoloLens.](hololens-updates.md)

### Visibilidade da página Configurações Habilitadas para o HoloLens 2
- Maior controle de interface do usuário no aplicativo Configurações, que pode ser confundido ao mostrar uma seleção limitada de páginas.

Agora, habilitamos uma política que permite que os administradores de IT impeçam que páginas específicas do aplicativo Configurações do Sistema sejam visíveis ou acessíveis, ou para fazer isso para todas as páginas, exceto as especificadas. Para saber como personalizar totalmente esse recurso, clique no link abaixo.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais configurações de página você pode personalizar no HoloLens 2, visite nossa página [de URIs de Configurações.](settings-uri-list.md) 
 
![Captura de tela da modificação das horas ativas no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

### Modo de pesquisa
Enquanto estiver no Modo de Pesquisa, o HoloLens 2 se torna uma ferramenta poderosa para pesquisa de visão do computador. Em comparação com as edições anteriores, o Modo de Pesquisa para HoloLens 2 tem as seguintes vantagens:
-   Além dos sensores expostos no Modo de Pesquisa do HoloLens (1ª geração), agora fornecemos acesso ao sensor de IMU, incluindo um acelerômetro, um giroscope e um magnetômetro.
-   O HoloLens 2 fornece novos recursos que podem ser usados em conjunto com o Modo de Pesquisa. Especificamente, o acesso a APIs de rastreamento manual e rastreamento de olhos articuladas que podem oferecer um conjunto mais rico de experimentos.

Os pesquisadores agora têm a opção de habilenciar o Modo de Pesquisa em seus dispositivos HoloLens para acessar todos esses fluxos de sensores de imagem bruta voltados para o lado externo. O Modo de Pesquisa para HoloLens 2 também fornece acesso às leituras do acelerômetro, do gyroscope e do magnetômetro. Para proteger a privacidade dos usuários, as imagens brutas da câmera de rastreamento ocular não estão disponíveis por meio do Modo de Pesquisa, mas a direção do olhar está disponível por meio de APIs existentes.

Confira a [documentação do Modo de Pesquisa](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

### Comprimento de gravação aumentado
Devido aos comentários dos clientes, aumentamos o comprimento de gravação de [capturas de realidade misturada.](holographic-photos-and-videos.md) As capturas de realidade misturada não serão mais limitadas a 5 minutos por padrão, mas calcularão o comprimento máximo de gravação com base no espaço em disco disponível. O dispositivo estima a duração máxima de gravação de vídeo com base no espaço em disco disponível em até 80% do espaço total em disco.

> [!NOTE]
> O HoloLens usará o comprimento padrão de gravação de vídeo (5 minutos) se ocorrer um dos seguintes:
> - A duração máxima estimada de gravação é menor do que os 5 minutos padrão.
> - O espaço em disco disponível é inferior a 20% do espaço total em disco.

Você pode encontrar os requisitos completos em nossa [documentação de fotos e vídeos](holographic-photos-and-videos.md#maximum-recording-length) holográficos. 

### Melhorias e correções na atualização:
- Agora, mais telas na tela OOBE estão no modo escuro.
- Saiba mais sobre o conteúdo que deve apontar para a Declaração de Privacidade online mais recente.
- Resolvido um problema em que os usuários não podiam provisionar perfis VPN por meio de pacotes de provisionamento.
- Problema de configuração de proxy corrigido para conexão VPN.
- Política atualizada para desabilitar a enumeração de funções USB por meio do MDM para NCM para AllowUsbConnection.
- Solucionado um problema que impedia que um dispositivo HoloLens aparecendo no Explorador de Arquivos sobre Protocolo de Transferência de Mídia (MTP) quando o dispositivo é definido como um [quiosque](hololens-kiosk.md)de aplicativo único. Observe que o MTP (e a conexão USB em geral) ainda podem ser desabilitados usando [a política AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Correção de um problema em que os ícones no menu Iniciar eram dimensionados corretamente no modo quiosque.
- Corrigido um problema devido ao armazenamento em cache HTTP interferir no modo de quiosque direcionado para grupos do Azure AD.
- Corrigido um problema em que os usuários não conseguiam usar o botão Emparelhar depois de habilitar o modo Desenvolvedor com pacotes de provisionamento, a menos que desabilita e reabilitaram o modo desenvolvedor.

## Windows Holographic, versão 1903 - Atualização de novembro de 2020
- Build 18362.1085

Esta atualização de qualidade mensal não contém alterações notáveis. Recomendamos que você experimente nossa versão mais recente do recurso com build do Windows Holographic, versão 20H2.

## Windows Holographic, versão 2004 - Atualização de outubro de 2020
- Build 19041.1124
 
Melhorias e correções na atualização:

- Removida uma verificação desnecessária que causou falha no sistema de tempo de execução.

## Windows Holographic, versão 1903 - Atualização de outubro de 2020
- Build 18362.1081

Esta atualização de qualidade mensal não contém alterações notáveis. Recomendamos que você experimente nossas versões mais recentes para o Windows Holographic, versão 2004.

## Windows Holographic, versão 2004 - Atualização de setembro de 2020
- Build 19041.1117

Melhorias e correções na atualização:

- Resolve um problema que impedia o Visual Studio de depurar um aplicativo quando SupportsMultipleInstances="true" está presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy NCSI para resolver falha na detecção de Internet por proxy de rede. NCSI pode usar proxy de máquina e proxy por perfil para detecção de conectividade com a Internet. O proxy por usuário será suportado pelo NCSI na versão futura.
- Na maioria dos dispositivos do Windows Mixed Reality, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ser perpendicular aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre fatores forma.
- Robustez aprimorada do rastreamento de mãos que resultará em menos perdas de rastreamento em cenários específicos.
- Esta versão contém uma correção para melhorar a qualidade do registro de data/hora de áudio que pode ter contribuído para problemas de captura de vídeo.

## Windows Holographic, versão 1903 - Atualização de setembro de 2020
- Build 18362.1079

Melhorias e correções na atualização:

- Na maioria dos dispositivos do Windows Mixed Reality, o vetor de direção para frente é paralelo ao chão quando a cabeça do usuário está em uma posição neutra olhando para frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ser perpendicular aos painéis de exibição, que é inclinado para baixo alguns graus em relação à orientação ideal. Versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre fatores forma.
- Robustez aprimorada do rastreamento de mãos que resultará em menos perdas de rastreamento em cenários específicos.

## Windows Holographic, versão 2004 - Atualização de agosto de 2020
- Build 19041.1113

Melhorias e correções na atualização:

- O aplicativo Configurações não acompanhará mais o usuário nas experiências de Registro de Íris ou Calibragem de Rastreamento de Olhos.
- Corrigido um bug em que a aplicação de um pacote de provisionamento durante OOBE que renomeia o dispositivo e executa outras ações (como conectar-se a uma rede) não executaria as outras ações após a reinicialização do dispositivo devido a uma renomeação.
- Esquema de cores modificado dos fluxos iniciais de configuração do dispositivo para melhorar a qualidade visual.

## Windows Holographic, versão 1903 - Atualização de agosto de 2020
- Build 18362.1074

Esta atualização de qualidade mensal não contém alterações notáveis. Recomendamos que você experimente nossas versões mais recentes para o Windows Holographic, versão 2004.

## Windows Holographic, versão 2004 - Atualização de julho de 2020
- Build 19041.1109

Melhorias e correções na atualização:

- Agora, os desenvolvedores podem escolher entre habilger ou desabilitar o Device Portal para exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Alterou o brilho da caixa de entrada padrão para 100%.
- Resolvido um problema sobre o encaminhamento HTTPS para o Windows Device Portal no HoloLens 2.

## Windows Holographic, versão 1903 - Atualização de julho de 2020
- Build 18362.1071

Melhorias e correções na atualização:

- Corrigido um problema que poderia fazer com que os hologramas desaparecessem nos aplicativos Unity ao perder ou recuperar o rastreamento.
- Corrigido um problema que causava falha de aplicativos exclusivos do HoloLens no shell enquanto usava o Emulador do HoloLens com aceleração de hardware em determinados dispositivos.
- Resolvido um problema referente ao encaminhamento HTTPS para o Windows Device Portal no HoloLens 2.

## Windows Holographic, versão 2004 - Atualização de junho de 2020
- Build 19041.1106

Melhorias e correções na atualização:

- Gravadores MRC personalizados agora têm novos valores padrão para determinadas propriedades se eles não são especificados.
  - Sobre o efeito *de vídeo MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (headset imersivo))
  - Sobre o *efeito de áudio MRC:*
    - LoopbackGain (o valor atual "Ganho de Áudio de Aplicativo" na página Captura de Realidade Misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual "Mic Audio Gain" na página Captura de Realidade Misturada no Windows Device Portal)
- Correção de um bug para melhorar a qualidade do áudio em cenários de captura de realidade misturada. Especificamente, essa correção deve eliminar falhas de áudio na gravação quando **o** menu Iniciar é exibido.
- Melhoria da estabilidade do holograma em vídeos gravados.
- Resolvemos um problema em que a captura de realidade misturada não podia gravar vídeo depois que o dispositivo era deixado em estado de espera por vários dias.
- A API HolographicSpace.UserPresence geralmente é desabilitada para aplicativos Unity. Esse comportamento evita um problema que causava a pausa de alguns aplicativos quando o visor estava invertido, mesmo se a configuração "executar em segundo plano" estivesse habilitada. A API agora está habilitada para as versões Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Quando você acessa o Device Portal através de uma Wi-Fi, um navegador da Web pode impedir o acesso devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo que o certificado do dispositivo seja confiável anteriormente. Nesse caso, você não pode avançar para o Device Portal, pois não há opção para ignorar avisos de segurança. Essa atualização resolveu o problema. Se o certificado do dispositivo tiver sido baixado anteriormente e confiável em um computador para remover avisos de segurança do navegador, e o erro SSL ocorrer, o novo certificado terá que ser baixado e confiável para lidar com os avisos de segurança do navegador.
- Habilitada a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
- Adicionada uma configuração **nos**  >  ****  >  **Hologramas** do Sistema de Configurações que permite aos usuários remover automaticamente todos os hologramas da página de realidade misturada quando o dispositivo é desligado.
- Corrigido um problema que causava aplicativos do HoloLens que alteram seu formato de pixel para renderizar preto no emulador do HoloLens.
- Corrigido um bug que causava uma falha durante o logon da íris.
- Corrigido um problema sobre downloads repetidos da loja para aplicativos já atuais.
- Correção de um bug para impedir que aplicativos imersivos abriam o Microsoft Edge repetidamente.
- Corrigido um problema com inicializações do aplicativo Fotos na inicialização inicial após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## Windows Holographic, versão 1903 - Atualização de junho de 2020
- Build 18362.1064

Melhorias e correções na atualização:

- Gravadores MRC personalizados têm novos valores padrão para determinadas propriedades se não são especificados.
  - Sobre o efeito *de vídeo MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (headset imersivo))
  - Sobre o *efeito de áudio MRC:*
    - LoopbackGain (o valor atual "Ganho de Áudio de Aplicativo" na página Captura de Realidade Misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual "Mic Audio Gain" na página Captura de Realidade Misturada no Windows Device Portal)
- A API HolographicSpace.UserPresence geralmente é desabilitada para aplicativos Unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração para executar em segundo plano estiver habilitada. A API agora está habilitada para as versões Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Corrigido um problema que causava aplicativos do HoloLens que alteram seu formato de pixel para renderizar preto no Emulador do HoloLens.
- Corrigido um problema sobre inicializações do aplicativo Fotos na inicialização inicial após a atualização da versão 1903.

## Windows Holographic, versão 2004  
- Build - 19041.1103

A atualização de software principal de maio de 2020 para o HoloLens 2, *Windows Holographic, versão 2004* inclui uma série de novos recursos interessantes, como suporte para o Windows Autopilot, modo escuro do aplicativo, suporte a Ethernet USB para hotspots 5G/LTE e muito mais. Para atualizar para a versão **** mais recente, abra o aplicativo Configurações, vá para Atualizar & Segurança e selecione o botão Verificar    **** **Atualizações.**   

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurar e configurar perfeitamente novos dispositivos para produção usando o Windows AutoPilot                 |
|       Suporte para FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar perfeitamente um pacote de provisionamento de uma unidade USB ao seu HoloLens                              |
|       Status de instalação do aplicativo                 |          Verificar o status de instalação no aplicativo Configurações para aplicativos foram por meio do HoloLens 2 via MDM               |
|       Provedores de serviços de configuração (CSPs)   |          Adicionados novos provedores de serviços de configuração para aprimorar os recursos de controle de administração                 |
|       Suporte a USB 5G/LTE                       |          A funcionalidade Ethernet USB expandida habilita o suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que suportam os modos escuro e claro, melhorando a experiência de visualização        |
|       Comandos de voz                             |          Suporte para comandos adicionais de voz do sistema para controlar as mãos livres do HoloLens                           |
|       Melhorias no controle de mãos                 |          As melhorias no controle de mãos fazem com que os botões e as interações 2D slate mais precisas                        |
|       Melhorias e correções de qualidade                 |          Várias melhorias de desempenho e confiabilidade do sistema em toda a plataforma                            |

### Suporte para o Windows Autopilot

O Windows Autopilot para HoloLens 2 permite que o canal de vendas do dispositivo pré-inscreva o HoloLens em seu locatário do Intune. Quando os dispositivos chegam, eles estão prontos para auto-implantar como dispositivos compartilhados em seu locatário. Para aproveitar a auto-implantação, o dispositivo deve se conectar a uma rede durante a primeira tela na instalação usando um USB-C para Ethernet.

Depois que um usuário inicia o processo de auto-implantação do Autopilot, o processo conclui as seguintes etapas:

1. Ingresso do dispositivo no Azure Active Directory (Azure AD)
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe os perfis de rede, certificados e políticas direcionados aos dispositivos.
1. Provisione este dispositivo.
1. Apresente a tela de entrada ao usuário.

Saiba mais no guia [de avaliação do Windows Autopilot para HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Entre em contato com seu Gerente de Contas para ingressar na visualização do AutoPilot agora. Os dispositivos prontos para o Autopilot começarão a ser entregados em breve.*

### Suporte à chave de segurança FIDO2

Alguns usuários compartilham um dispositivo HoloLens com outros em um ambiente de trabalho ou de escola. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. O Fast Identity Online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre perfeitamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação sem senha baseada em padrões "inphishable" que pode vir em qualquer fator forma. FIDO é um padrão aberto para autenticação sem senha. Ele permite que usuários e organizações se inscrevam em seus recursos sem um nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma interna em um dispositivo.

Para começar, consulte [Habilitar o logo](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)in de chave de segurança sem senha.

### Registro no MDM aprimorado por meio do pacote de provisionamento

Os pacotes de provisionamento permitem definir a configuração do HoloLens por meio de um arquivo de configuração em vez de por meio da experiência inicial pelo HoloLens. Anteriormente, os pacotes de provisionamento tinham que ser copiados para a memória interna do HoloLens. Agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizar em vários dispositivos HoloLens e você pode provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também suportam um campo para registro no gerenciamento de dispositivos, portanto, não há configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do Designer de Configuração do Windows da Windows Store para o computador.
1. Selecione **Provisionamento de Dispositivos HoloLens**  >  **Provisionamento dispositivos HoloLens 2**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C a qualquer HoloLens recentemente piscado. Em seguida, pressione **os botões**de energia de volume para baixo para aplicar seu pacote de  +  **** provisionamento.

### Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento de aplicativos de MDM para aplicativos de linha de negócios são fundamentais para o HoloLens. Administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **Configurações**  >  **contas do**Access trabalho ou  >  **escola**Clique em  >  **suas informações de**  >  **conta.**

### CSPs e políticas adicionais

Um [provedor de serviços de configuração (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface para ler, definir, modificar ou excluir definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores implantaram em dispositivos HoloLens. Para ver a lista de CSPs suportados pelo HoloLens, consulte [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

Novidade nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa configure políticas em dispositivos Windows. Nesta versão, adicionamos novas políticas para o HoloLens, que estão listadas aqui. Para saber mais, consulte [CSPs de política com suporte pelo HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

O provedor de serviços de configuração NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, consulte [CSP NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### Suporte de Ethernet USB expandida para dispositivos conectados 5G/LTE

O suporte foi adicionado para habilitar determinados dispositivos de banda larga móvel, como telefones 5G/LTE e hotpots Wi-Fi, quando eles são conectados ao HoloLens 2 via USB. Esses dispositivos agora são exibidos nas **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos de banda larga móveis que exigem um driver externo.) Essa funcionalidade permite conexões de largura de banda alta quando Wi-Fi não está disponível e Wi-Fi o conexões não tem desempenho suficiente. Para saber mais sobre dispositivos USB compatíveis, consulte Conectar-se a [dispositivos Bluetooth e USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### Melhorias no controle de mãos

Esta versão inclui várias melhorias de controle de mãos:

- **Apontar apresenta estabilidade:** O sistema agora resistindo à inclinação do dedo indicador quando ele é omitido pela palma. Essa alteração melhora a precisão quando você pressiona botões, digita, rola o conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Melhoramos a detecção do gesto de air tap. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta as mãos em seus lados.
- **Confiabilidade da opção do usuário:** O sistema agora é mais rápido e confiável na atualização do tamanho da mão quando você compartilha um dispositivo.
- **Roubo de mão reduzido:** Melhoramos o tratamento dos casos em que há mais de duas mãos à vista dos sensores. Se várias pessoas trabalham juntas, agora há uma chance muito menor de que a mão controlada "pule" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Corrigido um problema que fez com que o rastreamento de mão parasse de funcionar quando o dispositivo estava com carga alta.

### Modo escuro

Muitos aplicativos do Windows agora são suportados nos modos escuro e claro. Os usuários do HoloLens 2 podem escolher o modo padrão para aplicativos que suportam ambos. Após a atualização, o modo de aplicativo padrão é "escuro", **** mas você pode alterar facilmente essa configuração: Navegue até Configurações cores do sistema Escolha o modo  >  ****  >  ****  >  **de aplicativo padrão.** 

Esses aplicativos "nativos" suportam o modo escuro: 

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

![Janelas lado a lado do modo escuro lado a lado](images/DarkMode.jpg)

### Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, [consulte Usar sua voz para operar o HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Consulte também [idiomas com suporte para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Atualizações da Cortana

O aplicativo atualizado se integra ao Microsoft 365 para ajudá-lo a fazer mais em seus dispositivos (atualmente US-English apenas). No HoloLens 2, a Cortana não dá mais suporte a determinados comandos específicos do dispositivo, como ajustar o volume ou reiniciar. Essas opções agora são suportadas pelos novos comandos de voz do sistema. Saiba mais sobre o novo aplicativo Cortana em nosso [blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduzido um sistema de calibragem de exibição ativo. Esse recurso melhora a estabilidade e o alinhamento dos hologramas. Eles agora permanecem no lugar quando você move sua cabeça de um lado para outro.
- Correção de um bug em Wi-Fi streaming para o HoloLens foi interrompido periodicamente. Se um aplicativo indicar que ele precisa de streaming de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Corrigido um trava de dispositivo que ocorreu durante o streaming no modo de pesquisa.
- Correção de um bug em que, em alguns casos, o usuário correto não era exibido na tela de logon ao retomar uma sessão.
- Corrigido um problema em que os usuários não podiam exportar logs MDM por meio **de Configurações.**
- Corrigido um problema em que a precisão do rastreamento de olhos imediatamente após a configuração inicial pelo usuário poderia ser menor do que o esperado.
- Corrigido um problema em que o subsistema de rastreamento de olhos falhava ao inicializar ou executar a calibragem em determinadas condições.
- Corrigido um problema em que a calibragem dos olhos era solicitada para um usuário já calibrado.
- Corrigido um problema em que um driver travava durante a calibragem dos olhos.
- Corrigido um problema em que pressionamentos repetidos do botão de energia poderiam causar um tempo de 60 segundos no sistema e uma falha no shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um **botão Compartilhar** no Hub de Feedback para que os usuários possam compartilhar comentários com mais facilidade.
- Corrigido um bug em que o RoboRaid wan não estava instalado corretamente.

### Problemas conhecidos

- Um problema com o idioma do sistema zh-CN impede que comandos de voz capturem ou exibem o endereço IP do dispositivo.
- Um problema exige que você iniciar o aplicativo Cortana depois de iniciar o dispositivo para usar a ativação de voz "Ei Cortana". Se você atualizou de um build 18362, também poderá ver um segundo tile de aplicativo para a versão anterior do aplicativo Cortana que não funciona mais em **Iniciar.**

## Windows Holographic, versão 1903 - Atualização de maio de 2020 
- Build 18362.1061

Essa atualização de qualidade mensal não contém alterações notáveis porque a equipe estava trabalhando na versão 2004 do Windows Holographic, conforme descrito anteriormente.

## Windows Holographic, versão 1903 - Atualização de abril de 2020
- Build 18362.1059

**Modo escuro para aplicativos com suporte** 

Muitos aplicativos do Windows suportam os modos escuro e claro. Os clientes do HoloLens 2 agora podem escolher o modo padrão para aplicativos que suportam os dois esquemas de cores. Com base nos comentários dos clientes, definimos o modo de aplicativo padrão como "escuro", mas você pode facilmente alterar essa configuração a qualquer momento: Navegue até Configurações > **Sistema >** Cores para encontrar "Escolha seu modo de aplicativo **padrão".**

Esses aplicativos "nativos" suportam o modo escuro:
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
- Garante que as sobreposições de shell sejam incluídas em capturas de realidade misturada.
- Os desenvolvedores do Unreal agora podem usar a página De exibição 3D no Device Portal para testar e depurar seus aplicativos.
- Melhoria da estabilidade do holograma na captura de realidade misturada quando o algoritmo *HolographicDepthReprojectionMethod DepthReprojection* é usado.
- Correção do erro "Classe de API IStreamSocketListener do WinRT não registrada" em aplicativos ARM de 32 bits.

## Windows Holographic, versão 1903 - Atualização de março de 2020 
- Build 18362.1056

Melhorias e correções na atualização:

- Melhoria da estabilidade do holograma na captura de realidade misturada quando o algoritmo *HolographicDepthReprojectionMethod AutoPlanar* é usado.
- Certifique-se de que o sistema de coordenadas anexado a um exemplo de MF de profundidade seja consistente com a documentação pública.
- Produtividade do desenvolvedor aprimorada, permitindo que os clientes colem grandes quantidades de texto por meio do device portal.

## Windows Holographic, versão 1903 - Atualização de fevereiro de 2020 
- Build 18362.1053

Melhorias e correções na atualização:

- Desabilitada temporariamente a API HolographicSpace.UserPresence para aplicativos Unity. Essa alteração evita um problema que faz com que alguns aplicativos pausem quando o visor foi invertido, mesmo que a configuração "executar em segundo plano" tenha sido habilitada.
- Corrigimos uma falha de HUP aleatória causada pelo rastreamento de mãos, em que o usuário notava que uma interface do usuário congelava e volta ao shell após vários segundos.
- Rastreamento de mão aprimorado para que, quando você se desdoque com o dedo indicador, a parte superior do dedo tenha menos probabilidade de ficar incorretamente.
- Confiabilidade aprimorada do rastreamento de cabeça, mapeamento espacial e outros tempos de execução.

## Windows Holographic, versão 1903 - Atualização de janeiro de 2020 
- Build 18362.1043
 
Melhorias e correções na atualização:

- Estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador do HoloLens 2.

## Windows Holographic, versão 1903 - Atualização de dezembro de 2019 
- Build 18362.1042

Melhorias e correções na atualização:

- Apresentamos correções de reprodução em último estágio (LSR). Renderização visual aprimorada de hologramas para parecer mais estável e nítido, contando com mais precisão sua profundidade. Esse sintoma será mais perceptível após essa atualização se os aplicativos não definirem a profundidade dos hologramas corretamente.
- Estabilidade fixa de aplicativos exclusivos e navegação entre aplicativos exclusivos.
- Resolvemos um problema em que a captura de realidade misturada não podia gravar vídeo depois que o dispositivo estava em estado de espera por vários dias.
- Melhoria da estabilidade do holograma.

## Windows Holographic, versão 1903 - Atualização de novembro de 2019 
- Build 18362.1039

Melhorias e correções na atualização:

- Foi corrigida a funcionalidade **dos comandos Selecionar** voz durante a configuração inicial para en-CA e en-AU.
- Melhor qualidade visual dos objetos colocados longe das versões mais recentes do Unity e do Kit de Ferramentas de Realidade Misturada (MRTK).
- Corrigimos problemas de endereçamento com aplicativos holográficos travados em um estado pausado na inicialização até que o menu Iniciar fosse aberto e fechado.
- Correções e melhorias de conformidade do tempo de execução do OpenXR para o HoloLens 2 e o emulador.
