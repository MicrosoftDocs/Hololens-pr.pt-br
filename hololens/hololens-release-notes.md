---
title: Notas de versão do HoloLens 2
description: Saiba mais sobre atualizações em cada nova versão do HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/10/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: e1bdc6292dc016dde78c781db79505e2b64b0d6d
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253058"
---
# Notas de versão do HoloLens 2

Para garantir que você tenha uma experiência produtiva com seus dispositivos de HoloLens, continuamos a liberar recursos, erros e atualizações de segurança. Nesta página, você pode ver as novidades do HoloLens a cada mês. Para obter a atualização mais recente do HoloLens 2, você pode [verificar se há atualizações e atualizar manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) ou obter a atualização Flash completa (FFU) para fazer o [flash do seu dispositivo por meio do complemento avançado de recuperação](hololens-recovery.md#clean-reflash-the-device), [Baixe-o aqui](https://aka.ms/hololens2download). O download é mantido atualizado e fornece a versão mais recente disponível no momento.

>[!NOTE]
> Para ler as notas de versão do emulador do HoloLens, [acesse o arquivo morto](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).


## Windows holográfico, versão 20H2 – atualização de dezembro de 2020
- Build 19041,1131

### Instalar aplicativos no HoloLens 2 via instalador de aplicativos

Estamos **adicionando uma nova funcionalidade (instalador de aplicativos) para permitir que você instale aplicativos com mais facilidade** em seus dispositivos do HoloLens 2. O recurso estará **ativado por padrão para dispositivos não gerenciados**. Para evitar interrupções em empresas, o instalador do aplicativo **não estará disponível para dispositivos gerenciados** no momento.  

Um dispositivo será considerado "gerenciado" se **qualquer** uma das seguintes opções for verdadeira:
- MDM [registrado](hololens-enroll-mdm.md)
- Configurado com o [pacote de provisionamento](hololens-provisioning.md)
- A [identidade](hololens-identity.md) do usuário é o Azure AD

Agora você pode instalar aplicativos sem precisar habilitar o modo de desenvolvedor ou usar o Device Portal.  Basta baixar (via USB ou pelo Edge) o pacote Appx para o seu dispositivo e navegar até o pacote Appx no explorador de arquivos para ser solicitado a iniciar a instalação.  Você também pode [iniciar uma instalação a partir de uma página da Web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Assim como os aplicativos que você instala na Microsoft Store ou Sideload usando a funcionalidade de implantação do aplicativo LOB do MDM, os aplicativos precisam ser assinados digitalmente com a [ferramenta de assinatura](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) e o [certificado usado para assinar deve ser confiado](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) pelo dispositivo HoloLens antes de ser implantado.

**Instruções de instalação do aplicativo.**

1.  Certifique-se de que seu dispositivo não seja considerado gerenciado
1.  Verifique se o seu dispositivo do HoloLens 2 está ligado e conectado ao computador
1.  Certifique-se de estar conectado ao dispositivo HoloLens 2
1.  No seu computador, navegue até seu aplicativo personalizado e copie yourapp. appxbundle para yourdevicename\Internal Storage\Downloads.   Depois de terminar de copiar seu arquivo, você pode desconectar seu dispositivo
1.  Em seu dispositivo do HoloLens 2, abra o menu Iniciar, selecione todos os aplicativos e inicie o aplicativo explorador de arquivos.
1.  Navegue até a pasta downloads. Talvez seja necessário no painel esquerdo do aplicativo Selecione este dispositivo primeiro e, em seguida, navegue até downloads.
1.  Selecione o arquivo yourapp. appxbundle.
1.  O instalador do aplicativo será iniciado. Selecione o botão instalar para instalar o aplicativo.
O aplicativo instalado será iniciado automaticamente após a conclusão da instalação.

Você pode encontrar aplicativos de exemplo no [GitHub de exemplos universais do Windows](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para testar esse fluxo.

Leia sobre o processo completo de [instalação de aplicativos no HoloLens 2 com o instalador do aplicativo](app-deploy-app-installer.md).  

![Instalando exemplos de MRTK via instalador de aplicativos](images/hololens-app-installer-picture.jpg)

### Melhorias e correções na atualização:

- Agora, o rastreamento de mão mantém o rastreamento em muitos casos novos em que a mão anteriormente teria sido perdida.  Em alguns desses novos casos, somente a posição de Palm continua a atualizar com base na disponibilidade do usuário, enquanto as outras juntas são inferidas com base em uma pose anterior.  Essa alteração ajuda a melhorar a consistência de rastreamento em movimentos, como Slapping, lançamento, scooping e aplausos.  Também ajuda nos casos em que a mão está perto de uma superfície ou que está segurando um objeto.  Quando as junções à mão estiverem sendo inferidas, o valor de [precisão](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) definido será definido como "aproximado" em vez de "alto".
- Correção de um problema em que o PIN reset para contas do Azure AD mostraria um erro "algo deu errado.
- Os usuários devem ver bem menos a postagem post-boot do OOBE falha ao iniciar ET, íris do aplicativo configurações, novo usuário ou notificação notificação do sistema.
- Os usuários devem ter o fuso horário correto que está saindo do OOBE.

## Windows holográfico, versão 1903 – atualização de dezembro de 2020
- Build 18362,1088

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente a atualização mais recente do Windows holográfico, versão 20H2 – dezembro de 2020 e o novo recurso instalador do aplicativo adicionado na compilação.


## Windows holográfico, versão 20H2
- Build 19041,1128

O Windows holográfico, versão 20H2 agora está disponível e traz um ótimo conjunto de novos recursos para usuários do HoloLens 2 e profissionais de ti. Do posicionamento de olho automático, para o Gerenciador de certificados em configurações, para melhorar a funcionalidade do modo de quiosque e os novos recursos de configuração do AutoPilot. Esta nova atualização permite que as equipes de ti tomem controle mais granular para configurar e gerenciar dispositivos HoloLens e oferece aos usuários experiências ainda mais holográficos. 

Esta versão mais recente é uma atualização mensal para a versão 2004, mas desta vez estamos incluindo novos recursos. O número da versão principal permanecerá igual e o Windows Update indicará uma versão mensal da versão 2004 (Build 19041). Você pode ver o seu número de Build em suas configurações > a tela para confirmar que está nas versões mais recentes do Build 19041.1128 +. Para atualizar para a versão mais recente, abra o aplicativo configurações, vá para atualizar & segurança e toque em verificar se há atualizações. Para obter mais informações sobre como gerenciar as atualizações do HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### O que há de novo no Windows holográfico, versão 20H2  

| Recurso                                              | Descrição                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Suporte Automático de Posição Ocular](hololens-release-notes.md#auto-eye-position-support) | Calcula ativamente as posições de olho sem que os usuários passem pela calibragem de rastreamento ocular.   |
| [Gerenciador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que novos métodos mais simples instalem e removam certificados do aplicativo configurações.     |
| [Fornecimento automático de inicialização de USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Os pacotes de provisionamento em unidades USB solicitam automaticamente a página de aprovisionamento em OOBE.                                                         |
| [Confirmar automaticamente os pacotes de provisionamento em OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Os pacotes de provisionamento são aplicados automaticamente durante o OOBE na página de provisionamento.                                                         |
| [Provisionamento automático sem usar a interface do usuário](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Como combinar a inicialização automática do provisionamento e a confirmação automática juntas. |
| [Usar o AutoPilot com conexão Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use o AutoPilot do dispositivo Wi-Fi sem necessidade de adaptador Ethernet. |
| [O Provedor de Soluções na Nuvem da Microsoft do Tenantlockdown e AutoPilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Após o registro do locatário e a política ser aplicada, o dispositivo só poderá ser registrado nesse locatário sempre que o dispositivo for redefinido ou atualizado novamente. |
| [Acesso Global Atribuído](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Novo método de configuração para o modo de quiosque de vários aplicativos que aplica o quiosque no nível do sistema, tornando-o aplicável a todos.                  |
| [Iniciar automaticamente um aplicativo no quiosque de vários aplicativos](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Define um aplicativo para ser iniciado automaticamente ao entrar em um modo de quiosque de vários aplicativos.                                                        |
| [Alterações de comportamento do modo de quiosque para manipulação de falhas](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Agora, a falha do modo de quiosque tem fallback restritivo.                                                                                                |
| [Políticas do HoloLens](hololens-release-notes.md#hololens-policies)                                    | Novas políticas para o HoloLens.     |
| [Armazenar membros do grupo do Azure AD para quiosque offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | A nova política permite que os usuários usem o cache de associação do grupo para usar o modo de quiosque offline para o número definido de dias.                                        |
| [Novas políticas de restrição de dispositivo para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Políticas de gerenciamento de dispositivos habilitadas recentemente para o HoloLens 2.                                                                                |
| [Novas políticas de energia para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Políticas recém aceitas para configurações de tempo limite de energia.  |
| [Atualizar políticas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Políticas habilitadas recentemente, permitindo o controle de atualizações.           |
| [Visibilidade da página Configurações habilitada para o HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Política para escolher quais páginas são vistas no aplicativo configurações.             |
| [Modo de pesquisa](hololens-release-notes.md#research-mode) | Usar o modo de pesquisa no HoloLens 2. |
| [Tamanho da gravação aumentado](hololens-release-notes.md#recording-length-increased) | As gravações da MRC não estão mais limitadas a 5 minutos. |
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

Essas informações podem ser encontradas mais tarde com [outras informações de calibragem](hololens-calibration.md#auto-eye-position-support). 

### Gerenciador de certificados

- Ferramentas aprimoradas de auditoria, diagnóstico e validação para segurança e conformidade de dispositivos por meio do novo Gerenciador de certificados. Esse recurso permitirá que você implante, solucione problemas e valide seus certificados em escala em ambientes comerciais.

No Windows holográfico versão 20H2, adicionamos um Gerenciador de certificados no aplicativo Configurações do HoloLens 2. Vá para **configurações > atualizar certificados & segurança >**. Esse recurso oferece uma maneira simples e fácil de exibir, instalar e remover certificados em seu dispositivo. Com o novo Gerenciador de certificados, administradores e usuários agora têm ferramentas aprimoradas de auditoria, diagnóstico e validação para garantir que os dispositivos permaneçam seguros e compatíveis. 

-   **Auditoria:** Capacidade de validar se um certificado está implantado corretamente ou para confirmar se foi removido apropriadamente. 
-   **Diagnóstico:** Quando surgem problemas, é possível validar se os certificados apropriados existem no dispositivo poupa tempo e ajuda na solução de problemas. 
-   **Validação:** Verificar se um certificado atende à finalidade e é funcional, pode economizar tempo significativo, especialmente em ambientes comerciais antes de implantar certificados em uma escala maior.

Para localizar um certificado específico na lista rapidamente, há opções para classificar por nome, loja ou data de expiração. Os usuários também podem procurar um certificado diretamente. Para exibir as propriedades de certificado individuais, selecione o certificado e clique em **informações**. 

A instalação do certificado atualmente oferece suporte a arquivos. cer e. CRT. Os proprietários de dispositivo podem instalar certificados na máquina local e no usuário atual;  todos os outros usuários podem instalar somente no usuário atual. Os usuários só podem remover certificados instalados diretamente da interface do usuário de configurações. Se um certificado tiver sido instalado por outros meios, ele também deverá ser removido pelo mesmo mecanismo.

#### Para instalar um certificado: 

1.  Conecte seu HoloLens 2 a um PC.
1.  Coloque o arquivo de certificado que você deseja instalar em um local no seu HoloLens 2.
1.  Navegue até **configurações aplicativo > atualização & segurança > certificados**e selecione instalar um certificado.
1.  Clique em **Importar arquivo** e navegue até o local onde você salvou o certificado.
1.  Selecione **local da loja**.
1.  Selecione **repositório de certificados**.
1.  Clique em **Instalar**.

Agora o certificado deve estar instalado no dispositivo.

#### Para remover um certificado: 
1. Navegue até **configurações aplicativo > atualização e segurança > certificados**.
1. Procure o certificado por nome na caixa de pesquisa.
1. Selecione o certificado.
1. Clique em **remover**
1. Selecione **Sim** quando for solicitada a confirmação.

![Visualizador de certificados no aplicativo configurações](images/certificate-viewer-device.jpg)

![Imagem mostrando como usar a interface do usuário do certificado para instalar um certificado](images/certificate-device-install.jpg)

Essas informações podem ser encontradas posteriormente [em uma nova página do Gerenciador de certificados](certificate-manager.md).

### Fornecimento automático de inicialização de USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante o OOBE.

Antes desta versão, os usuários precisavam iniciar a tela de aprovisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora os usuários podem ignorar a combinação de botões usando um pacote de provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagindo do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB estiver conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como o relógio para a conexão de outros itens.

Para obter mais informações sobre como aplicar pacotes de provisionamento durante a OOBE, continue lendo [aqui](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

Essas informações podem ser encontradas mais tarde [aqui.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### Confirmar automaticamente os pacotes de provisionamento em OOBE
- Processo automatizado que permite menos interação do usuário, quando a página do pacote de provisionamento é exibida, ele aplica automaticamente todos os pacotes listados.

Quando a tela principal do provisionamento surgir, o OOBE contará 10 segundos antes de iniciar automaticamente a aplicação de todos os pacotes de provisionamento. Os usuários ainda podem confirmar ou cancelar nestas 10 segundos após verificar os pacotes esperados.

Essas informações podem ser encontradas mais tarde [aqui.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para as interações reduzidas de dispositivos para provisionamento. 

Ao combinar o lançamento automático do provisionamento de dispositivos USB e a confirmação automática dos pacotes de provisionamento, um usuário pode provisionar dispositivos do HoloLens 2 automaticamente sem usar a interface do usuário do dispositivo ou mesmo usar o dispositivo. Você pode continuar a usar a mesma unidade USB e o pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos ao mesmo tempo na mesma área. 

1. [Crie um pacote de provisionamento](hololens-provisioning.md) usando o [Designer de configuração do Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie o pacote para uma unidade de armazenamento USB.
1. [Atualize seu HoloLens 2 para o](hololens-insider.md#ffu-download-and-flash-directions) [19041,1361 ou versão mais recente](https://aka.ms/hololens2previewdownload). 
1. Quando o [complemento de recuperação avançada](https://www.microsoft.com/store/productId/9P74Z35SFRS8) concluir a atualização do seu dispositivo, desconecte o cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. Quando o dispositivo HoloLens 2 for inicializado no OOBE, ele detectará automaticamente o pacote de provisionamento na unidade USB e iniciará a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Agora, seu dispositivo está configurado e exibirá a tela de provisionamento bem-sucedido.

Essas informações podem ser encontradas mais tarde [aqui.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Usar o AutoPilot com conexão Wi-Fi
- Removida a necessidade de adaptadores USB-C para a Ethernet reduzindo as necessidades de hardware, habilitando o AutoPilot para funcionar em Wi-Fi dispositivos conectados.

Agora, durante o OOBE, quando você conectar o HoloLens 2 com WiFi, o OOBE verificará se há um perfil do AutoPilot para o dispositivo. Se um for encontrado, ele será usado para concluir o restante do fluxo do AAD e do fluxo de registro. Em outras palavras, usar Ethernet para USB-C ou Wi-Fi para o adaptador USB-C não é mais necessário, mas continuará a funcionar, se fornecido no início do OOBE. Saiba mais sobre o [AutoPilot para dispositivos HoloLens 2](hololens2-autopilot.md).

### CSP do Tenantlockdown e AutoPilot
- Mantém os dispositivos no locatário da organização bloqueando-os para o locatário, mesmo através da reinicialização do dispositivo ou do reflash. Com mais segurança, desautorizando a criação da conta por meio do provisionamento. 

Os dispositivos do HoloLens 2 agora dão suporte ao CSP TenantLockdown da [versão 20H2 do Windows holográfico](hololens-release-notes.md#windows-holographic-version-20h2). 

O Provedor de Soluções na Nuvem da Microsoft [TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) permite que o HoloLens 2 seja vinculado a inscrição do MDM usando apenas o Autopilot. Depois que o nó RequireNetworkInOOBE do CSP do TenantLockdown for definido com valor verdadeiro ou falso (definido inicialmente) no HoloLens 2, esse valor permanece no dispositivo, apesar de atualizar novamente, atualizações do sistema operacional, etc. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, o OOBE aguarda indefinidamente que o perfil do Autopilot seja baixado e aplicado com sucesso, após a conectividade de rede. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, as seguintes operações não serão permitidas no OOBE: 
- Criação de usuário local usando provisionamento do tempo de execução 
- Executando a operação de junção do Azure AD por meio do provisionamento de tempo de execução 
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

Essas informações agora podem ser encontradas juntamente com o restante do piloto automático sob o [CSP Tenantlockdown e o AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### Acesso global atribuído – modo de quiosque
- Gerenciamento de identidades reduzido para o quiosque, habilitando o novo método quiosque que aplica o modo de quiosque no nível do sistema.

Este novo recurso permite que um administrador de ti configure um dispositivo HoloLens 2 para o modo de quiosque de vários aplicativos, que é aplicável no nível do sistema, não tem afinidade com qualquer identidade no sistema e se aplica a todos os participantes do dispositivo. Leia sobre esse novo recurso em detalhes [aqui](hololens-global-assigned-access-kiosk.md).

### Inicialização automática de um aplicativo no modo de quiosque de vários aplicativos 
- Experiência destaques com o lançamento automático do aplicativo, melhorando ainda mais a interface do usuário e as seleções de aplicativos escolhidas para experiências do modo de quiosque.

Aplica-se somente ao modo de quiosque de vários aplicativos e somente um aplicativo pode ser designado para inicialização automática usando o atributo realçado abaixo na configuração de acesso atribuído. 

O aplicativo é iniciado automaticamente quando o usuário entra. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Alterações de comportamento do modo de quiosque para manipulação de falhas
- Modo de quiosque mais seguro eliminando aplicativos disponíveis em falhas do modo de quiosque. 

Antes de encontrar falhas na aplicação do modo de quiosque, o HoloLens é usado para exibir todos os aplicativos no menu iniciar. Agora, no Windows holográfico Version 20H2, no caso de falhas, nenhum aplicativo será mostrado no menu Iniciar, como a seguir: 

![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

### Políticas do HoloLens
- Opções de gerenciamento de dispositivo especificamente para o HoloLens criado para o gerenciamento do dispositivo. 

Novas políticas de realidade mista foram criadas para dispositivos do HoloLens 2 na versão 20H2 do Windows holográfico. As novas configurações controláveis incluem: configuração do brilho, configuração do volume, desativação da gravação de áudio em capturas de realidade mista, configuração quando o diagnóstico pode ser coletado e o cache de associação do grupo AAD.  

| Nova política do HoloLens                                | Descrição                                                                               | Observações                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que os botões de brilho sejam desabilitados para que o pressionamento não altere o brilho.       | 1 Sim, 0 não (padrão)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que os botões de volume sejam desabilitados, portanto, ao pressioná-lo, não muda o volume.               | 1 Sim, 0 não (padrão)                                                |
| MixedReality\MicrophoneDisabled                    | Desabilita o microfone para que a gravação de áudio seja possível no HoloLens 2.                      | 1 Sim, 0 não (padrão)                                                |
| MixedReality\FallbackDiagnostics                   | Controla o comportamento de quando os logs de diagnóstico podem ser coletados.                               | 0 desativado, 1 habilitado para proprietários de dispositivo, 2 habilitado para todos (padrão) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla quantos dias o cache de membros do grupo do Azure AD é usado para os grupos de direcionamento do Azure AD. | Veja abaixo.                                                           |

### Armazenar membros do grupo do Azure AD para quiosque offline
- Foram habilitados quiosques offline para serem usados com grupos AAD por até 60 dias.

Essa política controla o número de dias, que o cache de associações do grupo do Azure AD pode ser usado para configurações de acesso atribuídas direcionadas a grupos do Azure AD para o usuário conectado. Quando esse valor de política é definido como valor maior que 0 somente, o cache é usado de outra forma não.  

Nome: AADGroupMembershipCacheValidityInDays URI value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín-0 dias  
Máx-60 dias 

Etapas para usar esta política corretamente: 
1. Crie um perfil de configuração de dispositivo para o quiosque que direciona os grupos do Azure AD e atribua-o a dispositivo (s) do HoloLens. 
1. Crie uma configuração de dispositivo baseada em OMA URI, que define esse valor de política como o número desejado de dias (> 0) e atribua-o a dispositivo (s) do HoloLens. 
    1. O valor de URI deve ser inserido na caixa de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. O valor pode estar entre min/max permitido.
1. Registrar dispositivos HoloLens e verificar se ambas as configurações são aplicadas ao dispositivo. 
1. Deixe que o usuário do Azure AD 1 entre quando a Internet estiver disponível, quando o usuário entrar e a assinatura do grupo do Azure AD for confirmada com êxito, o cache será criado. 
1. Agora, o usuário do Azure AD 1 pode colocar o HoloLens offline e usá-lo para o modo de quiosque, desde que o valor da política permita um número X de dias. 
1. As etapas 4 e 5 podem ser repetidas para qualquer outro usuário do Azure AD. o ponto da chave aqui é que qualquer usuário do Azure AD deve entrar no dispositivo usando a Internet, portanto, pelo menos uma vez podemos determinar que ele é membro do grupo do Azure AD para o qual a configuração do quiosque está direcionada. 
 
> [!NOTE]
> Até que a etapa 4 seja realizada para um usuário do Azure AD ter um comportamento de falha mencionado em ambientes "desconectados". 

### Novas políticas de restrição de dispositivo para HoloLens 2
- Permite que os usuários gerenciem políticas específicas de gerenciamento de dispositivos, como o bloqueio da adição ou da remoção de pacotes de provisionamento.

Políticas habilitadas recentemente que permitem mais opções de gerenciamento de dispositivos do HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Essas duas novas diretivas para AllowAddProvisioningPackage e AllowRemoveProvisioningPackage estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Em relação ao [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp), o HoloLens só dará suporte para a configuração./Vendor/MSFT/RemoteLock/Lock. Não há suporte para as configurações que lidam com o PIN, como redefinição e recuperação.

### Novas políticas de energia para HoloLens 2
- Mais opções para quando o HoloLens dorme ou trava via políticas de energia. 

Essas políticas adicionadas recentemente permitem que os administradores controlem os Estados de energia, como tempo limite ocioso. Para ler mais sobre cada política individual, clique no link para essa política.

|     Link de documentação da política                |     Observações                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de exemplo a ser usado no designer de configuração do Windows, ou seja,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Essas duas novas diretivas para DisplayOffTimeoutOnBattery e DisplayOffTimeoutPluggedIn estão sendo adicionadas às nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md).

> [!NOTE]
> Para uma experiência consistente com o HoloLens 2, certifique-se de que os valores de DisplayOffTimeoutOnBattery e StandbyTimeoutOnBattery sejam definidos como o mesmo valor. O mesmo se aplica a DisplayOffTimeoutPluggedIn e StandbyTimeoutPluggedIn. Confira os [temporizadores de exibição, suspensão e hibernação ociosa](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obter mais detalhes sobre o modo de espera moderno.

### Políticas de atualização habilitadas recentemente para HoloLens
- Mais opções de quando as atualizações são instaladas ou a desativação do botão Pausar atualizações para garantir as atualizações.

Essas políticas de atualização agora estão habilitadas em dispositivos HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Detalhes completos sobre essas políticas de atualização e sobre como usá-las para dispositivos HoloLens podem ser lidos aqui em [gerenciar atualizações do hololens](hololens-updates.md).

### Visibilidade da página Configurações habilitada para o HoloLens 2
- Controle de interface do usuário aumentado no aplicativo configurações, que pode ser confuso para mostrar uma seleção limitada de páginas.

Agora habilitamos uma política que permite que os administradores de ti impeçam que páginas específicas no aplicativo Configurações do sistema sejam visíveis ou acessíveis, ou que façam isso para todas as páginas, exceto aquelas especificadas. Para saber como personalizar completamente este recurso, clique no link abaixo.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber quais configurações de página você pode personalizar no HoloLens 2, acesse nossa [página URIs de configurações](settings-uri-list.md). 
 
![Captura de tela da modificação das horas ativas no aplicativo Configurações](images/hololens-page-visibility-list.jpg)

### Modo de pesquisa
Enquanto estiver no modo de pesquisa, o HoloLens 2 torna-se uma ferramenta potent para pesquisa de visão do computador. Em comparação com as edições anteriores, o modo de pesquisa para o HoloLens 2 tem as seguintes vantagens:
-   Além dos sensores expostos no modo de pesquisa do HoloLens (1ª gen), agora oferecemos acesso IMU sensor, incluindo acelerômetro, Gyroscope e magnetômetro.
-   O HoloLens 2 oferece novos recursos que podem ser usados em conjunto com o modo de pesquisa. Especificamente, o acesso a APIs articuladas de acompanhamento à mão e acompanhamento de olhos pode oferecer um conjunto mais rico de experimentos.

Os pesquisadores agora têm a opção de habilitar o modo de pesquisa em seus dispositivos HoloLens para acessar todos esses fluxos de sensores de imagens brutas externos. O modo de pesquisa para o HoloLens 2 também fornece acesso às leituras do acelerômetro, do Gyroscope e do magnetômetro. Para proteger a privacidade dos usuários, as imagens da câmera de controle de olhos brutos não estão disponíveis no modo de pesquisa, mas a direção olhar está disponível por meio de APIs existentes.

Confira a [documentação do modo de pesquisa](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obter mais detalhes técnicos.

### Tamanho da gravação aumentado
Devido aos comentários dos clientes, aumentamos o tamanho da gravação de [capturas de realidade misturadas](holographic-photos-and-videos.md). As capturas de realidade misturadas não ficarão mais limitadas a 5 minutos por padrão, mas, em vez disso, calcularão o tamanho máximo de gravação com base no espaço disponível em disco. O dispositivo estimará a duração máxima da gravação de vídeo com base no espaço em disco disponível até 80% do espaço total em disco.

> [!NOTE]
> O HoloLens usará o comprimento padrão de gravação de vídeo (5 minutos) se ocorrer um dos seguintes procedimentos:
> - A duração máxima de gravação estimada é menor do que o padrão de 5 minutos.
> - O espaço disponível em disco é inferior a 20% do espaço total em disco.

Essas informações podem ser encontradas novamente [aqui](holographic-photos-and-videos.md#maximum-recording-length). 

### Melhorias e correções na atualização:
- No momento, há mais telas em OOBE no modo escuro.
- Saiba mais o conteúdo deve apontar para a declaração de privacidade online mais recente.
- Corrigido um problema em que os usuários não puderam configurar perfis VPN por meio de pacotes de provisionamento.
- Problema de configuração de proxy fixo para conexão VPN.
- Política atualizada para desabilitar a enumeração de funções de USB por meio do MDM para NCM para AllowUsbConnection.
- Foi corrigido um problema que impedia a exibição de um dispositivo HoloLens no File Explorer over Media Transfer Protocol (MTP) quando o dispositivo é configurado como um [quiosque de aplicativo único](hololens-kiosk.md). Observe que a MTP (e a conexão USB em geral) ainda pode ser desabilitada usando a política [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- Correção de um problema em que os ícones no menu iniciar foram dimensionados corretamente no modo de quiosque.
- Correção de um problema devido ao cache HTTP interferindo no modo de quiosque direcionado para grupos do Azure AD.
- Correção de um problema em que os usuários não conseguiram usar o botão emparelhar após habilitar o modo de desenvolvedor com pacotes de provisionamento, a menos que eles sejam desabilitados e habilitados novamente para o modo de desenvolvedor.

## Windows holográfico, versão 1903 – atualização de novembro de 2020
- Build 18362,1085

Esta atualização de qualidade mensal não contém alterações notáveis, recomendamos que você experimente a versão mais recente do Build Windows holográfico, versão 20H2.

## Windows holográfico, versão 2004 – atualização de outubro de 2020
- Build 19041,1124
 
Melhorias e correções na atualização:

- Foi removida uma verificação desnecessária que causou a falha do sistema do tempo de execução.

## Windows holográfico, versão 1903 – atualização de outubro de 2020
- Build 18362,1081

Esta atualização de qualidade mensal não contém alterações notáveis, incentivamos você a experimentar nossas versões mais recentes para Windows holográfico, versão 2004.

## Windows holográfico, versão 2004 – atualização de setembro de 2020
- Build 19041,1117

Melhorias e correções na atualização:

- Trata de um problema que impedia o Visual Studio de depurar um aplicativo quando SupportsMultipleInstances = "true" está presente no appxmanifest.
- Esta versão inclui a correção de detecção de proxy do NCSI para resolver a falha na detecção pela Internet em um proxy de rede. O NCSI pode usar proxy de computador e proxy por perfil para detecção de conectividade à Internet. O proxy por usuário será compatível com o NCSI em lançamento futuro.
- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao terra quando a cabeça do usuário está em uma posição neutra, olhando para a frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ficar perpendicular aos painéis de exibição em vez disso, o que é inclinado para baixo alguns graus em relação à orientação ideal. As versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre fatores forma.
- Melhor controle da mão, o que resulta em menos perdas de controle em cenários específicos.
- Este lançamento contém uma correção para melhorar a qualidade do carimbo de data e hora que pode ter contribuído com problemas de captura de vídeo.

## Windows holográfico, versão 1903 – atualização de setembro de 2020
- Build 18362,1079

Melhorias e correções na atualização:

- Na maioria dos dispositivos Windows Mixed Reality, o vetor de direção de encaminhamento é paralelo ao terra quando a cabeça do usuário está em uma posição neutra, olhando para a frente. No entanto, as versões anteriores do HoloLens 2 alinharam o vetor para ficar perpendicular aos painéis de exibição em vez disso, o que é inclinado para baixo alguns graus em relação à orientação ideal. As versões mais recentes do HoloLens 2 corrigiram isso para garantir a consistência semântica entre fatores forma.
- Melhor controle da mão, o que resulta em menos perdas de controle em cenários específicos.

## Windows holográfico, versão 2004 – atualização de agosto de 2020
- Build 19041,1113

Melhorias e correções na atualização:

- O aplicativo configurações não acompanhará mais o usuário em experiências de calibragem de rastreamento de olho ou de acompanhamento da íris.
- Correção de um bug em que a aplicação de um pacote de provisionamento durante o OOBE que renomeia o dispositivo e executa outras ações (como conectar-se a uma rede) falhava ao executar as outras ações após a reinicialização do dispositivo devido ao renomeação.
- Esquema de cores modificado para fluxos iniciais de configuração de dispositivos para melhorar a qualidade visual.

## Windows holográfico, versão 1903 – atualização de agosto de 2020
- Build 18362,1074

Esta atualização de qualidade mensal não contém alterações notáveis, incentivamos você a experimentar nossas versões mais recentes para Windows holográfico, versão 2004.

## Windows holográfico, versão 2004-atualização de julho de 2020
- Build 19041,1109

Melhorias e correções na atualização:

- Os desenvolvedores agora podem escolher entre habilitar ou desabilitar o Device portal para exigir uma conexão segura.
- Confiabilidade aprimorada para lançamentos de aplicativos após atualizações do sistema operacional.
- Brilho da caixa de entrada padrão alterado para 100%.
- Foi corrigido um problema sobre o encaminhamento de HTTPS para o Windows Device portal no HoloLens 2.

## Windows holográfico, versão 1903-atualização de julho de 2020
- Build 18362,1071

Melhorias e correções na atualização:

- Correção de um problema que pode fazer com que os hologramas desapareçam em aplicativos do Unity ao perder ou recuperar o controle.
- Correção de um problema que causava o failback de aplicativos exclusivos do HoloLens para o Shell enquanto uso o emulador do HoloLens com aceleração de hardware em certos dispositivos.
- Foi corrigido um problema relacionado ao encaminhamento HTTPS para o Windows Device portal no HoloLens 2.

## Windows holográfico, versão 2004 – atualização de junho de 2020
- Build 19041,1106

Melhorias e correções na atualização:

- Registros da MRC personalizados agora têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (fone de ouvido com microfone))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "ganho de áudio do aplicativo" na página de captura da realidade misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual de "ganho de áudio do MIC" na página de captura da realidade misturada no Windows Device Portal)
- Correção de um bug para melhorar a qualidade de áudio em cenários de captura de realidade misturada. Especificamente, esta correção deve eliminar a falha de áudio na gravação quando o menu **Iniciar** é exibido.
- Estabilidade aprimorada de holograma em vídeos gravados.
- Corrigido um problema em que a captura de realidade misturada não pôde gravar vídeo após o dispositivo ter sido deixado em estado de espera por vários dias.
- A API HolographicSpace. userpresence geralmente está desabilitada para aplicativos Unity. Esse comportamento evita um problema que fez com que alguns aplicativos pausem quando o visor foi invertido, mesmo se a configuração "executar em segundo plano" estivesse habilitada. A API agora está habilitada para versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Quando você acessa o Device portal em uma conexão Wi-Fi, um navegador da Web pode impedir o acesso devido a um certificado inválido. O navegador pode relatar um erro como "ERR_SSL_PROTOCOL_ERROR", mesmo se o certificado do dispositivo era confiável anteriormente. Nesse caso, você não pode progredir para o Device portal, pois não há a opção de ignorar avisos de segurança. Esta atualização resolveu o problema. Se o certificado do dispositivo foi baixado anteriormente e confiável em um computador para remover avisos de segurança do navegador e o erro SSL ocorrer, o novo certificado precisará ser baixado e confiável para corrigir os avisos de segurança do navegador.
- Habilitou a capacidade de criar um pacote de provisionamento de tempo de execução que pode instalar um aplicativo usando pacotes MSIX.
- Foi adicionada uma configuração em **configurações**de  >  ****  >  **hologramas** do sistema que permite aos usuários remover automaticamente todos os hologramas de casa misturada da realidade quando o dispositivo é desligado.
- Correção de um problema que causava aplicativos HoloLens que alteravam o formato de pixel para renderização em preto no emulador do HoloLens.
- Correção de um bug que causou uma falha durante o logon íris.
- Correção de um problema sobre downloads de lojas repetidos para aplicativos já existentes.
- Correção de um bug para impedir que aplicativos imersivas Abram o Microsoft Edge repetidamente.
- Correção de um problema com as inicializações do aplicativo fotos em inicializações iniciais após a atualização da versão 1903.
- Desempenho e confiabilidade aprimorados.

## Windows holográfico, versão 1903 – atualização de junho de 2020
- Build 18362,1064

Melhorias e correções na atualização:

- Registros da MRC personalizados têm novos valores padrão para determinadas propriedades se não forem especificados.
  - No *efeito de vídeo da MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (fone de ouvido com microfone))
  - No *efeito de áudio da MRC*:
    - LoopbackGain (o valor atual de "ganho de áudio do aplicativo" na página de captura da realidade misturada no Windows Device Portal)
    - MicrophoneGain (o valor atual de "ganho de áudio do MIC" na página de captura da realidade misturada no Windows Device Portal)
- A API HolographicSpace. userpresence geralmente está desabilitada para aplicativos Unity. Esse comportamento evita um problema que faz com que alguns aplicativos pausem quando o visor é invertido, mesmo se a configuração para executar em segundo plano estiver habilitada. A API agora está habilitada para versões do Unity 2018.4.18 e posteriores e 2019.3.4 e posteriores.
- Correção de um problema que causava aplicativos HoloLens que alteravam o formato de pixel para renderização em preto no emulador do HoloLens.
- Correção de um problema sobre as inicializações do aplicativo fotos em inicializações iniciais após a atualização da versão 1903.

## Windows holográfico, versão 2004  
- Build-19041,1103

A atualização de software principal de maio de 2020 para o HoloLens 2, o *Windows holográfico, versão 2004* inclui um host de novos recursos incríveis, como suporte para o piloto automático do Windows, modo escuro do aplicativo, suporte para Ethernet USB para pontos de acesso 5g/LTE e muito mais. Para atualizar para a versão mais recente, abra o aplicativo **configurações**   , vá para **Atualizar & segurança**e selecione o botão verificar se há **atualizações**   . 

|             Recurso                              |          Descrição                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Pré-configurar e configurar tranqüilamente novos dispositivos para produção usando o piloto automático do Windows                 |
|       Suporte do FIDO 2                             |          Suporte para chaves de segurança FIDO2 para habilitar a autenticação rápida e segura para dispositivos compartilhados            |
|       Provisionamento aprimorado                      |          Aplicar integralmente um pacote de provisionamento de uma unidade USB ao seu HoloLens                              |
|       Status de instalação do aplicativo                 |          Verificar se o status de instalação no aplicativo configurações para aplicativos foi enviado por push para o HoloLens 2 via MDM               |
|       Provedores de serviços de configuração (CSPs)   |          Novos provedores de serviços de configuração adicionados para melhorar os recursos de controle de administração                 |
|       Suporte a USB 5G/LTE                       |          O recurso Ethernet USB expandida permite suporte para 5G/LTE                                    |
|       Modo de aplicativo escuro                              |          Modo de aplicativo escuro disponível para aplicativos que dão suporte a modos escuros e leves, melhorando a experiência de visualização        |
|       Comandos de voz                             |          Suporte para comandos de voz do sistema adicionais para controlar o HoloLens-sem viva-voz                           |
|       Melhorias no controle de mão                 |          Melhorias de rastreamento de mão tornam os botões e as interações de ardósia 2D mais precisos                        |
|       Melhorias e correções de qualidade                 |          Vários aprimoramentos de desempenho do sistema e confiabilidade em toda a plataforma                            |

### Suporte para o piloto automático do Windows

O piloto automático do Windows para o HoloLens 2 permite que o canal de vendas do dispositivo tenha cancelamento de registro do HoloLens em seu locatário do Intune. Quando os dispositivos chegam, eles estão prontos para serem implantados como dispositivos compartilhados em seu locatário. Para tirar proveito da autoimplantação, o dispositivo deve se conectar a uma rede durante a primeira tela no programa de instalação usando um USB-C-to-Ethernet.

Depois que um usuário iniciar o processo de implantação automática do AutoPilot, o processo concluirá as seguintes etapas:

1. Ingresso do dispositivo no Azure Active Directory (Azure AD)
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe os perfis de rede, certificados e políticas direcionados aos dispositivos.
1. Provisione este dispositivo.
1. Apresente a tela de entrada ao usuário.

Saiba mais no [Guia de avaliação do Windows AutoPilot para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Entre em contato com seu gerente de conta para participar da visualização do AutoPilot agora. Os dispositivos prontos para o AutoPilot começarão a ser entregues em breve.*

### Suporte a chave de segurança FIDO2

Alguns usuários compartilham um dispositivo HoloLens com outras pessoas em um ambiente de trabalho ou de estudante. Portanto, é importante que os usuários possam facilmente sem digitar nomes de usuário e senhas longos. A rápida identidade online (FIDO) permite que qualquer pessoa em sua organização (locatário do Azure AD) entre diretamente no HoloLens sem inserir um nome de usuário ou senha.

As chaves de segurança FIDO2 são um método de autenticação com senha baseada em padrões "não Phish" que pode ser inserido em qualquer fator forma. FIDO é um padrão aberto para autenticação com senha inexistente. Ele permite que usuários e organizações se conectem a seus recursos sem nome de usuário ou senha. Em vez disso, eles usam uma chave de segurança externa ou uma chave de plataforma integrada a um dispositivo.

Para começar, consulte [Habilitar entrada de chave de segurança sem senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### Registro de MDM aprimorado via pacote de provisionamento

Os pacotes de provisionamento permitem que você defina a configuração do HoloLens por meio de um arquivo de configuração, em vez de usar a experiência inicial pelo HoloLens. Anteriormente, os pacotes de provisionamento precisavam ser copiados para a memória interna do HoloLens. Agora eles podem estar em uma unidade USB para que sejam mais fáceis de reutilizá-los em vários dispositivos HoloLens e você possa provisionar dispositivos em paralelo. Os pacotes de provisionamento agora também dão suporte a um campo para inscrição no gerenciamento de dispositivos, portanto, não há configuração manual após o provisionamento.

Para experimentar:

1. Baixe a versão mais recente do designer de configuração do Windows na Windows Store em seu computador.
1. Selecione **provisionar dispositivos hololens**para  >  **configurar dispositivos hololens 2**.
2. Crie seu perfil de configuração. Em seguida, copie todos os arquivos que foram criados para um dispositivo de armazenamento USB-C.
3. Conecte o dispositivo USB-C em qualquer HoloLens atualizado. Em seguida, pressione os botões de energia para **baixo volume**  +  **** para aplicar seu pacote de provisionamento.

### Status de instalação do aplicativo de linha de negócios

A implantação e o gerenciamento de aplicativos MDM para aplicativos de linha de negócios são essenciais para o HoloLens. Administradores e usuários precisam exibir o status de instalação do aplicativo para auditoria e diagnóstico. Nesta versão, adicionamos mais detalhes em **configurações**  >  **contas**  >  **acessar trabalho ou escola**  >  **clique nas informações da sua conta**  >  ****.

### Provedores e políticas adicionais

Um [provedor de serviços de configuração (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) é uma interface que lê, define, modifica ou exclui definições de configuração em um dispositivo. Nesta versão, adicionamos suporte para mais políticas para aumentar o controle que os administradores têm sobre dispositivos HoloLens implantados. Para obter a lista de provedores compatíveis com o HoloLens, consulte [CSP do NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novo nesta versão:

**CSP Policy** 

O provedor de serviços de configuração de política permite que a empresa Configure políticas em dispositivos Windows. Nesta versão, adicionamos novas políticas para HoloLens, que estão listadas aqui. Para saber mais, consulte [CSPs de política com suporte pelo HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

O provedor de serviços de configuração do NetworkQoSPolicy cria políticas de QoS (qualidade de serviço) de rede. Uma política QoS executa um conjunto de ações no tráfego de rede com base em um conjunto de condições correspondentes. Para saber mais, consulte [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Suporte a Ethernet USB expandido para dispositivos 5G/LTE para compartilhamento de

O suporte foi adicionado para habilitar certos dispositivos de banda larga móvel, como telefones 5G/LTE e Wi-Fi hotpots, quando eles estiverem em compartilhamento de Internet para o HoloLens 2 via USB. Esses dispositivos agora são exibidos em **configurações de rede** como outra conexão Ethernet. (Não há suporte para dispositivos de banda larga móvel que exijam um driver externo). Essa funcionalidade permite conexões de alta largura de banda quando o Wi-Fi não está disponível e Wi-Fi o compartilhamento não é suficiente. Para saber mais sobre os dispositivos USB com suporte, consulte [conectar a dispositivos Bluetooth e USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Melhorias no controle de mão

Esta versão inclui vários aprimoramentos de controle de mão:

- **Ponteiro de pose:** O sistema agora se resiste à curva do dedo do índice quando ele é obstruídado pelo Palm. Essa alteração melhora a precisão ao enviar botões, digitar, rolar conteúdo e muito mais! 
- **Toques de ar acidentais reduzidos:** Aprimoramos a detecção do gesto de tocar no ar. Agora há menos ativações acidentais em vários cenários comuns, como quando você solta suas mãos em seus lados.
- **Confiabilidade da opção do usuário:** O sistema agora é mais rápido e mais confiável na atualização do tamanho da mão quando você compartilha um dispositivo.
- **Roubo reduzido:** Aprimoramos a manipulação de casos em que há mais de duas mãos em vista dos sensores. Se várias pessoas estiverem trabalhando juntas, há agora uma chance muito menor de que a mão rastreada vai "saltar" do usuário para a mão de outra pessoa na cena.
- **Confiabilidade do sistema:** Correção de um problema que causava o rastreamento da mão para parar de funcionar quando o dispositivo está sob carga elevada.

### Modo escuro

Muitos aplicativos do Windows agora dão suporte a modos escuros e leves. Usuários do HoloLens 2 podem escolher o modo padrão para aplicativos que dão suporte a ambos. Após a atualização, o modo de aplicativo padrão é "escuro", mas você pode facilmente alterar essa configuração: Navegue até **configurações**  >  cores do**sistema**  >  ****  >  **escolha o modo de aplicativo padrão**. 

Estes aplicativos "in-box" dão suporte ao modo escuro: 

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

![Lado a lado do Windows em modo escuro](images/DarkMode.jpg)

### Comandos de voz do sistema

Agora você pode usar comandos de voz com qualquer aplicativo no dispositivo. Para obter mais informações, consulte [usar sua voz para operar com o HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulte também [idiomas com suporte para o HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Atualizações da Cortana

O aplicativo atualizado integra-se com o Microsoft 365 para ajudá-lo a realizar mais em seus dispositivos (atualmente somente em US-English). No HoloLens 2, a Cortana não dá mais suporte a determinados comandos específicos do dispositivo, como o ajuste de volume ou a reinicialização. Essas opções agora são suportadas pelos novos comandos de voz do sistema. Saiba mais sobre o novo aplicativo da Cortana em nosso [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Melhorias e correções de qualidade

Melhorias e correções também na atualização:  
- Introduziu um sistema de calibragem de vídeo ativo. Esse recurso melhora a estabilidade e o alinhamento de hologramas. Agora, eles permanecem no lugar quando você move sua cabeça de um lado para outro.
- Correção de um bug em que Wi-Fi streaming para HoloLens foi interrompido periodicamente. Se um aplicativo indicar que precisa de transmissão de baixa latência, implemente a correção chamando a [função SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Foi corrigido um dispositivo que ocorreu durante o streaming no modo de pesquisa.
- Correção de um bug em alguns casos em que o usuário certo não será exibido na tela de entrada ao retomar uma sessão.
- Correção de um problema em que os usuários não puderam exportar logs do MDM por meio **das configurações**.
- Correção de um problema em que a precisão do controle de olho logo após a configuração imediata pode ser menor do que o esperado.
- Correção de um problema em que o subsistema de acompanhamento de olho falhou ao inicializar ou executar a calibragem em determinadas condições.
- Correção de um problema em que a calibragem de olho seria solicitada para um usuário já calibrado.
- Correção de um problema em que um driver falhava durante a calibragem de olho.
- Correção de um problema em que as prensas do botão de energia repetidas podem causar um tempo limite do sistema de 60 a um segundo e falha de Shell.
- Estabilidade aprimorada para buffers de profundidade.
- Adicionado um botão **compartilhar** no Hub de feedback para que os usuários possam compartilhar os comentários com mais facilidade.
- Correção de um bug em que o RoboRaid wan't instalado corretamente.

### Problemas conhecidos

- Um problema com o idioma do sistema zh-CN impede que os comandos de voz tenham uma captura de realidade mista ou exibam o endereço IP do dispositivo.
- Um problema exige que você inicie o aplicativo da Cortana após iniciar o dispositivo para usar a ativação de voz "Ei Cortana". Se você atualizou a partir de uma compilação do 18362, você também pode ver um segundo bloco do aplicativo para a versão anterior do aplicativo da Cortana que não funciona mais em **início**.

## Windows holográfico, versão 1903 – maio de 2020 Update 
- Build 18362,1061

Esta atualização de qualidade mensal não contém alterações notáveis porque a equipe estava trabalhando na versão 2004 do Windows holográfico pode ser atualizada, conforme descrito anteriormente.

## Windows holográfico, versão 1903 – atualização de abril de 2020
- Build 18362,1059

**Modo escuro para aplicativos com suporte** 

Muitos aplicativos do Windows dão suporte ao modo escuro e Light. Os clientes do HoloLens 2 agora podem escolher o modo padrão para aplicativos compatíveis com o esquema de cores. Com base nos comentários dos clientes, definimos o modo de aplicativo padrão como "escuro", mas você pode facilmente alterar essa configuração a qualquer momento: Navegue até **configurações > sistema > cores** para localizar **"escolher o modo de aplicativo padrão".**

Estes aplicativos "in-box" dão suporte ao modo escuro:
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
- Verificado se as sobreposições do Shell estão incluídas em capturas de realidade misturadas.
- Agora, os desenvolvedores não reais podem usar a página modo de exibição 3D no Device portal para testar e depurar seus aplicativos.
- Estabilidade aprimorada do holograma em captura de realidade mista quando o algoritmo *HolographicDepthReprojectionMethod DepthReprojection* é usado.
- Foi corrigido o erro "classe de API do WinRT IStreamSocketListener não registrada" em aplicativos ARM de 32 bits.

## Windows holográfico, versão 1903-atualização de março de 2020 
- Build 18362,1056

Melhorias e correções na atualização:

- Estabilidade aprimorada do holograma em captura de realidade mista quando o algoritmo de *autoplanar do HolographicDepthReprojectionMethod* é usado.
- Verificado se o sistema de coordenadas anexado a um exemplo de MF de profundidade é consistente com a documentação pública.
- Maior produtividade do desenvolvedor ao permitir que os clientes colem grandes quantidades de texto por meio do Device Portal.

## Windows holográfico, versão 1903 – atualização de fevereiro de 2020 
- Build 18362,1053

Melhorias e correções na atualização:

- Desativada temporariamente a API HolographicSpace. userpresence para aplicativos Unity. Essa alteração evita um problema que causava pausa em alguns aplicativos quando o visor foi invertido, mesmo se a configuração "executar em segundo plano" estivesse habilitada.
- Correção de uma falha aleatória HUP causada pelo acompanhamento à mão, em que o usuário observou um congelamento da interface do usuário e, em seguida, voltou para o Shell após vários segundos.
- Controle de mão aprimorado para que, quando você fizer a reportar com o seu índice, a parte superior do dedo seja menos provável de ser deondulado inesperadamente.
- Maior confiabilidade de controle de cabeçotes, associação espacial e outros tempos de execução.

## Windows holográfico, versão 1903 – atualização de janeiro de 2020 
- Build 18362,1043
 
Melhorias e correções na atualização:

- Estabilidade aprimorada para aplicativos exclusivos ao trabalhar com o emulador do HoloLens 2.

## Windows holográfico, versão 1903 – atualização de dezembro de 2019 
- Build 18362,1042

Melhorias e correções na atualização:

- Foram introduzidas correções de reprodução do último estágio (LSR). Renderização visual aprimorada de hologramas para parecer mais estável e mais nítido por uma contabilidade mais precisa de sua profundidade. Esse sintoma será mais perceptível após essa atualização se os aplicativos não definirem a profundidade dos hologramas corretamente.
- Correção da estabilidade de aplicativos exclusivos e navegação entre aplicativos exclusivos.
- Corrigido um problema em que a captura de realidade misturada não pôde gravar vídeo após o dispositivo estar em estado de espera por vários dias.
- Estabilidade aprimorada do holograma.

## Windows holográfico, versão 1903 – atualização de novembro de 2019 
- Build 18362,1039

Melhorias e correções na atualização:

- Funcionalidade corrigida de **selecionar** comandos de voz durante a configuração inicial para en-CA e en-au.
- Melhor qualidade visual dos objetos colocados na versão mais recente do Unity e do kit de ferramentas de realidade mista (MRTK).
- Problemas de endereçamento corrigidos com os aplicativos do holográfico ficam presos em um estado pausado na inicialização até que o menu iniciar tenha sido aberto e depois fechado.
- OpenXR correções e melhorias de conformidade do tempo de execução do HoloLens 2 e do emulador.
