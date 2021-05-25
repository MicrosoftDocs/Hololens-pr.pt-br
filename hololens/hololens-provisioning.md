---
title: Configurar o HoloLens usando um pacote de provisionamento (HoloLens)
description: O provisionamento do Windows torna fácil para os administradores de TI configurarem os dispositivos de usuário final sem geração de imagens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: cf2abe249e40e522b4d8993449b9f19033a64744
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397397"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Configurar o HoloLens usando um pacote de provisionamento

O [provisionamento do Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) facilita para os administradores de ti configurar dispositivos do usuário final sem geração de imagens. O designer de configuração do Windows é uma ferramenta para configurar imagens e configurações de tempo de execução que são criadas em pacotes de provisionamento.

Algumas das configurações do HoloLens que você pode aplicar em um pacote de provisionamento incluem o seguinte:

- Atualizar para o [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Configurar uma conta local
- Configurar uma conexão Wi-Fi
- Aplicar certificados ao dispositivo
- Habilitar o Modo de Desenvolvedor
- Configure o modo de quiosque seguindo nossas [instruções detalhadas](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

## <a name="provisioning-package-hololens-wizard"></a>Assistente para provisionamento de pacote do HoloLens

O assistente do HoloLens ajuda a definir as seguintes configurações em um pacote de provisionamento:

- Atualizar para o Enterprise Edition

    > [!NOTE]
    > Isso deve ser usado somente para dispositivos de 1º gen de HoloLens. As configurações em um pacote de provisionamento só serão aplicadas se o pacote de provisionamento incluir uma licença de atualização de edição para o Windows Holographic for Business ou se [o dispositivo já tiver sido atualizado para o Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- Configurar a primeira experiência do HoloLens (OOBE)
- Configurar a rede Wi-Fi
- Registrar o dispositivo no Azure Active Directory ou criar uma conta local
- Adicionar certificados
- Habilitar o Modo de Desenvolvedor
- Configure o modo de quiosque seguindo [instruções detalhadas](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

> [!WARNING]
> Você deve executar o Designer de Configuração do Windows no Windows 10 para configurar o Registro do Azure Active Directory usando qualquer um dos assistentes.

Os pacotes de provisionamento podem incluir instruções e políticas de gerenciamento, conexões de rede e políticas personalizadas e muito mais.

> [!TIP]
> Use o assistente da área de trabalho para criar um pacote com as configurações comuns e alterne para o editor avançado a fim de adicionar outras configurações, aplicativos, políticas etc.

## <a name="steps-for-creating-provisioning-packages"></a>Etapas para criar pacotes de provisionamento

1. **Opção 1:** [de Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Isso inclui recursos do HoloLens 2.
2. **Opção 2: do** Kit [de Avaliação e Implantação do Windows (ADK) para Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Se você instalar o Designer de Configuração do Windows no Windows ADK, selecione **Designer** de Configuração na caixa de diálogo Selecionar os recursos **que deseja** instalar. Essa opção não inclui recursos do HoloLens 2.

> [!NOTE]
> Se você sabe que está usando um computador offline que precisa de acesso ao Designer de Configuração do Windows, siga as [instalação de aplicativo offline( instruções para https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) o Advanced Recovery Companion. Faça do Designer de Configuração do Windows sua seleção. 

### <a name="2-create-the-provisioning-package"></a>2. Criar o pacote de provisionamento

Use a ferramenta Designer de Configuração do Windows para criar um pacote de provisionamento.

1. Abra o Designer de Configurações do Windows (por padrão, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Selecione **Provisionamento de dispositivos HoloLens.**

   ![Opções iniciais do ICD](images/icd-create-options-1703.png)

3. Nomeia seu projeto e selecione **Concluir**.

4. Leia as instruções na **página De início** e selecione **Próximo.** As páginas para provisionamento da área de trabalho explicam as etapas a seguir.
  
> [!IMPORTANT]
> Ao compilar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo do pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluí-los quando não forem mais necessários.

### <a name="configure-settings"></a>Definir configurações

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Navegue até e selecione o arquivo de licença empresarial para atualizar a edição do HoloLens.</br></br>Você também pode alternar <strong>Sim</strong> ou <strong>Não</strong> para ocultar partes da primeira experiência.</br></br>Para configurar o dispositivo sem a necessidade de se conectar a uma rede Wi-Fi, alterne Ignorar Wi-Fi <strong>configuração</strong> para <strong>On</strong>.</br></br>Selecione uma região e um timezone no qual o dispositivo será usado. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Nesta seção, você pode inserir os detalhes da rede Wi-Fi sem fio à que o dispositivo deve se conectar automaticamente. Para fazer isso, selecione <strong>Em</strong>, insira o SSID, o tipo de rede (<strong>Open</strong> ou <strong>WPA2-Personal</strong>) e (se <strong>WPA2-Personal</strong>) a senha da rede sem fio.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Você pode registrar o dispositivo no Azure Active Directory ou criar uma conta local no dispositivo</br></br>Antes de usar um assistente de Designer de Configuração do Windows para configurar o registro do Azure AD em massa, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configure a participação do Azure AD em sua organização</a>. A configuração <strong>número máximo de dispositivos por usuário</strong> em seu locatário do Azure AD determina quantas vezes o token em massa que você obtém do assistente pode ser usado. Para registrar o dispositivo no Azure AD, selecione essa opção e insira um nome amigável para o token em massa que você obterá usando o assistente. Defina uma data de expiração do token (máximo de 30 dias a partir da data de obtenção do token). Selecione <strong>Obter token em massa</strong>. Na janela <strong>&#39;,</strong> insira uma conta que tenha permissões para ingressar um dispositivo no Azure AD e, em seguida, a senha. Selecione <strong>aceitar</strong> para fornecer as permissões necessárias ao designer de configuração do Windows. </br></br>Para criar uma conta local, selecione essa opção e insira um nome de usuário e senha. </br></br><strong>Fundamental</strong> <br />(Somente para Windows 10, versão 1607) Se você criar uma conta local no pacote de provisionamento, deverá alterar a senha usando o aplicativo de <strong>configurações</strong> a cada 42 dias. Se a senha não for alterada durante esse período, a conta poderá estar bloqueada e não será possível entrar.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Para provisionar o dispositivo com um certificado, clique em <strong>Adicionar um certificado</strong>. Insira um nome para o certificado e, em seguida, procure e selecione o certificado a ser usado.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Alterne <strong>Sim</strong> ou <strong>não</strong> para habilitar o modo de desenvolvedor no HoloLens. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Saiba mais sobre o modo de desenvolvedor.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Não defina uma senha para proteger seu pacote de provisionamento. Se o pacote de provisionamento for protegido por uma senha, o provisionamento do dispositivo HoloLens falhará.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Quando terminar, selecione **Criar**. Leva apenas alguns segundos. Quando o pacote é criado, o local onde o pacote está armazenado é exibido como hiperlink na parte inferior da página.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. criar um pacote de provisionamento para o HoloLens usando o provisionamento avançado

> [!NOTE]
> Um pacote de provisionamento que você cria no **provisionamento avançado** não precisa incluir uma licença de atualização de edição para que o Windows Holographic for Business se aplique com êxito a um HoloLens (1º gen). [Veja mais no Windows Holographic for Business for HoloLens (1º gen)](hololens1-upgrade-enterprise.md).

1. Na página inicial do Designer de Configuração do Windows, selecione **Provisionamento avançado**.
2. Na janela **Digite os detalhes do projeto**, especifique um nome e o local para o projeto. Como alternativa, insira uma breve descrição para caracterizar seu projeto.

3. Selecione **Avançar**.

4. Na janela **escolha quais configurações exibir e configurar** , selecione **Windows 10 Holographic** e, em seguida, selecione **Avançar**.

5. Selecione **Concluir**.

6. Expanda **configurações de tempo de execução** e personalize o pacote usando qualquer uma das configurações [descritas posteriormente neste artigo](#what-you-can-configure).

    > [!IMPORTANT]
    > (Somente para Windows 10, versão 1607) Se você criar uma conta local no pacote de provisionamento, deverá alterar a senha usando o aplicativo de **configurações** a cada 42 dias. Se a senha não for alterada durante esse período, a conta poderá estar bloqueada e não será possível entrar. Se a conta do usuário estiver bloqueada, você deverá [realizar uma recuperação de dispositivo completo](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Selecione **arquivo**  >  **salvar**.

8. Leia o aviso de que os arquivos de projeto podem conter informações confidenciais e selecione **OK**.

    > [!IMPORTANT]
    > Ao compilar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo do pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluí-los quando não forem mais necessários.
    
9. Selecione **Exportar**  >  **pacote de provisionamento**.

10. Altere o **proprietário** para o **administrador de ti**. Isso define a precedência desse pacote de provisionamento superior ao provisionamento de pacotes aplicados a este dispositivo de outras fontes. Selecione **Avançar**.

11. Defina um valor para **Versão do Pacote**.

    > [!TIP]
    > Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes já aplicados.

12. Em **selecionar detalhes de segurança para o pacote de provisionamento**, selecione **Avançar**.

    > [!WARNING]
    > Se você criptografar o pacote de provisionamento, o provisionamento do dispositivo HoloLens falhará.  

13. Selecione **Próximo** para especificar o local de saída em que você deseja que o pacote de provisionamento vá quando ele for criado. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída.

    Opcionalmente, você pode selecionar **Procurar para** alterar o local de saída padrão.

14. Selecione **Avançar**.

15. Selecione **Build** para começar a criar o pacote. As informações do projeto são exibidas na página de compilação, e a barra de progresso indica o status da compilação.

16. Quando o build for concluído, selecione **Concluir**.

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Aplicar um pacote de provisionamento ao HoloLens durante a instalação

Dispositivos HoloLens 2 no Windows Holographic, versão 2004 ou build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) ou posterior, podem usar uma unidade USB para aplicar um pacote de provisionamento. Basta copiar o arquivo .ppkg para a raiz da unidade USB. Os pacotes de provisionamento só serão aplicados se eles estão na raiz da unidade USB. Vários pacotes de provisionamento presentes serão aplicados sequencialmente.

Os dispositivos HoloLens 2 no Windows Holographic versão [20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou posterior têm recursos mais novos para ajudar a simplificar e simplificar esse processo, tornando-o automático. Revise as seções a seguir:

- [Provisionamento de início automático de USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Confirmar automaticamente os pacotes de provisionamento no OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Provisionamento automático sem usar a interface do usuário](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Use o cabo USB para conectar o dispositivo a um computador (ou unidade USB para HoloLens 2, conforme mencionado acima) e, em seguida, inicie o dispositivo. Não continue após a **página Primeiro momento interativo** do OOBE.   
    - No HoloLens (1ª geração), essa página contém uma caixa azul. 
    - No HoloLens 2, esta página contém o colisão.

2. Pressione e solte rapidamente os botões de **Menos Volume** e **Ligar/Desligar** simultaneamente. 

3. O HoloLens aparece como um dispositivo Explorador de Arquivos no computador.

4. No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.

5. Pressione brevemente e solte os botões **Volume Down** e **Power** simultaneamente novamente enquanto estiver na página Primeiro momento **interativo** do OOBE.

6. O dispositivo pergunta se você confia no pacote e deseja aplicá-lo. Confirme que você confia no pacote.

7. Você verá se o pacote foi aplicado com êxito ou não. Se ele falhar, você poderá corrigir o pacote e tentar novamente. Se ele tiver bem-sucedido, continue OOBE.

> [!NOTE]
> Se o dispositivo tiver sido adquirido antes de agosto de 2016, você precisará entrar no dispositivo usando uma conta Microsoft, obter a atualização mais recente do sistema operacional e redefinir o sistema operacional para aplicar o pacote de provisionamento.

### <a name="auto-launch-provisioning-from-usb"></a>Inicialização automática do provisionamento de USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante o OOBE.

Antes desta versão, os usuários precisavam iniciar a tela de provisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora, os usuários podem ignorar a combinação de botões, usando um pacote de provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagindo do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB for deixada conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como observará que outros que estão sendo conectados.

Leia sobre como [aplicar pacotes de provisionamento durante o OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmar automaticamente os pacotes de provisionamento no OOBE
- Processo automatizado permitindo menos interação do usuário, quando a página pacote de provisionamento for exibida, ele aplicará automaticamente todos os pacotes listados.

Quando a tela principal de provisionamento aparecer, o OOBE será reduzido 10 segundos antes de iniciar a aplicação de todos os pacotes de provisionamento automaticamente. Os usuários ainda podem confirmar ou cancelar dentro desse 10 segundos depois de verificar os pacotes esperados.

### <a name="automatic-provisioning-without-using-ui"></a>Provisionamento automático sem usar a interface do usuário
- Processos automáticos combinados para interações de dispositivo reduzidas para provisionamento. 

Ao combinar o lançamento automático do provisionamento de dispositivos USB e a confirmação automática de pacotes de provisionamento, um usuário pode provisionar dispositivos de HoloLens 2 automaticamente sem usar a interface do usuário do dispositivo ou até mesmo utilizar o dispositivo. Você pode continuar a usar a mesma unidade USB e pacote de provisionamento para vários dispositivos. Isso é útil para implantar vários dispositivos ao mesmo tempo na mesma área. 

1. [Crie um pacote de provisionamento usando](hololens-provisioning.md) o [Designer de Configuração do Windows.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Copie o pacote para uma unidade de armazenamento USB.
1. [Flash do HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) para [19041.1361 ou build mais novo.](https://aka.ms/hololens2previewdownload) 
1. Quando [o Avançado Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) tiver concluído a exibição do dispositivo, desconectar o cabo USB-C. 
1. Conecte sua unidade USB ao dispositivo.
1. Quando o dispositivo HoloLens 2 for inicializado no OOBE, ele detectará automaticamente o pacote de provisionamento na unidade USB e iniciará a página de provisionamento.
1. Após 10 segundos, o dispositivo aplicará automaticamente o pacote de provisionamento. 

Seu dispositivo agora está configurado e exibirá a tela Provisionamento bem-sucedido.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Aplicar/remover um pacote de provisionamento no HoloLens após a instalação

> [!NOTE]
> Essas etapas se aplicam a todos os dispositivos HoloLens 2 e dispositivos HoloLens (1ª geração) no Windows Holographic, versão 1809 e superior.

No computador, siga estas etapas:
1. Crie um pacote de provisionamento, conforme descrito em Criar um pacote de provisionamento para [o HoloLens usando o assistente do HoloLens.](hololens-provisioning.md)
2. Conecte o dispositivo HoloLens a um computador usando um cabo USB. O HoloLens aparece como um dispositivo Explorador de Arquivos no computador.
3. Arraste e solte o pacote de provisionamento para a pasta Documentos no HoloLens.

No HoloLens, siga estas etapas:
1. Acesse **Configurações** > **Contas** > **Acessar conta corporativa ou de estudante**. 
2. Em **Configurações Relacionadas,** **selecione Adicionar ou remover um pacote de provisionamento**.
3. Na próxima página, selecione **Adicionar um pacote para** iniciar o seletor de arquivos e selecione o pacote de provisionamento. Se a pasta estiver vazia, selecione Este **Dispositivo** e selecione **Documentos**.

Depois que o pacote tiver sido aplicado, ele aparecerá na lista de **pacotes instalados**. Para exibir os detalhes do pacote ou remover o pacote do dispositivo, selecione o pacote listado.

## <a name="what-you-can-configure"></a>O que você pode configurar

Os pacotes de provisionamento usam CSPs (provedores de serviço de configuração). Se você não estiver familiarizado com os CSPs, consulte [Introdução aos CSPs para profissionais de TI](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

No Designer de Configuração do Windows, quando você cria um pacote de provisionamento para o Windows Holographic, as configurações em **Personalizações disponíveis** se baseiam em [CSPs compatíveis no Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). A tabela a seguir descreve as configurações que você deseja configurar para o HoloLens.

![Configurações de tempo de execução comuns para o HoloLens](images/icd-settings.png)

| Setting | Descrição |
| --- | --- |
| **Certificados** | Implante um certificado para o HoloLens.  |
| **ConnectivityProfiles** | Implante um perfil de Wi-Fi para o HoloLens.   |
| **EditionUpgrade** | [Atualize para o Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Políticas** | Permita ou evite o modo desenvolvedor no HoloLens. [Políticas compatíveis com o Windows Holographic for Business](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Instalação do aplicativo por meio do pacote de provisionamento

Os aplicativos podem ser instalados por meio de pacotes de provisionamento em dispositivos do HoloLens 2. Isso permite um pacote facilmente reutilizável que você pode usar para ajudá-lo a distribuir seus aplicativos. Leia as instruções completas para [implantar aplicativos por meio de pacotes de provisionamento](app-deploy-provisioning-package.md).  

> [!NOTE]
> O HoloLens (1º gen) tem suporte limitado para a instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento. Os dispositivos HoloLens (1º gen) só dão suporte à instalação de um aplicativo por meio de PPKG somente durante o OOBE e somente com instalações de contexto de usuário.
