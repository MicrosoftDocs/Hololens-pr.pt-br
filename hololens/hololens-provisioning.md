---
title: Configurar o HoloLens usando um pacote de provisionamento (HoloLens)
description: O provisionamento do Windows torna fácil para os administradores de TI configurar os dispositivos do usuário final sem geração de imagens.
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
ms.openlocfilehash: f6b715a6a43a403ec56119188db0121e0731af37
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162988"
---
# Configurar o HoloLens usando um pacote de provisionamento

O [provisionamento do Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) torna mais fácil para os administradores de ti configurar dispositivos de usuário final sem geração de imagens. O designer de configuração do Windows é uma ferramenta para configurar imagens e configurações de tempo de execução que, em seguida, são criadas em pacotes de provisionamento.

Algumas das configurações do HoloLens que você pode aplicar em um pacote de provisionamento incluem o seguinte:

- Atualize para o Windows holográfico for Business [aqui](hololens1-upgrade-enterprise.md)
- Configurar uma conta local
- Configurar uma conexão Wi-Fi
- Aplicar certificados ao dispositivo
- Habilitar o modo de desenvolvedor
- Configurar o modo de quiosque (instruções detalhadas para configurar o modo de quiosque podem ser encontradas [aqui](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

## Assistente de provisionamento do pacote do HoloLens

O assistente do HoloLens ajuda você a definir as seguintes configurações em um pacote de provisionamento:

- Atualizar para a edição Enterprise

    > [!NOTE]
    > Isso só deve ser usado para dispositivos do HoloLens 1ª Gen. As configurações em um pacote de provisionamento só serão aplicadas se o pacote de provisionamento incluir uma licença de atualização de edição para o Windows holográfico for Business ou se [o dispositivo já tiver sido atualizado para o Windows holográfico for Business](hololens1-upgrade-enterprise.md).

- Configurar a experiência inicial (OOBE) do HoloLens
- Configurar a rede Wi-Fi
- Registrar o dispositivo no Azure Active Directory ou criar uma conta local
- Adicionar certificados
- Habilitar o modo de desenvolvedor
- Configurar o modo de quiosque. (Instruções detalhadas para configurar o modo de quiosque podem ser encontradas [aqui](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)).

> [!WARNING]
> Você deve executar o Designer de Configuração do Windows no Windows 10 para configurar o Registro do Azure Active Directory usando qualquer um dos assistentes.

Os pacotes de provisionamento podem incluir instruções e políticas de gerenciamento, conexões de rede e políticas personalizadas e muito mais.

> [!TIP]
> Use o assistente da área de trabalho para criar um pacote com as configurações comuns e alterne para o editor avançado a fim de adicionar outras configurações, aplicativos, políticas etc.

## Etapas para criar pacotes de provisionamento

1. **Opção 1:** [na Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Isso inclui recursos do HoloLens 2.
2. **Opção 2:** [no ADK (Kit de avaliação e implantação do Windows) para Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Se você instalar o designer de configuração do Windows a partir do Windows ADK, selecione **Designer de configuração** na caixa de diálogo **selecionar os recursos que deseja instalar** . Essa opção não inclui recursos do HoloLens 2.

> [!NOTE]
> Se você souber que usará um computador offline que precisa de acesso ao designer de configuração do Windows, siga as instruções instalar o aplicativo offline [aqui](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) para obter o complemento de recuperação avançada, mas fazer com que o Windows Confiugration escolha a seleção em vez disso. 

### 2. Crie o pacote de provisionamento

Use a ferramenta Designer de Configuração do Windows para criar um pacote de provisionamento.

1. Abra o Designer de Configurações do Windows (por padrão, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Selecione **provisionar dispositivos HoloLens**.

   ![Opções iniciais do ICD](images/icd-create-options-1703.png)

3. Nomeie seu projeto e selecione **concluir**.

4. Leia as instruções na página de **introdução** e selecione **Avançar**. As páginas para provisionamento da área de trabalho orientam você pelas etapas a seguir.
  
> [!IMPORTANT]
> Ao compilar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluí-los quando não forem mais necessários.

### Definir configurações

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Procure e selecione o arquivo de licença para empresas para atualizar a edição do HoloLens.</br></br>Você também pode alternar <strong> Sim </strong> ou <strong> não </strong> para ocultar partes da primeira experiência.</br></br>Para configurar o dispositivo sem a necessidade de se conectar a uma rede Wi-Fi, alterne a opção <strong> ignorar Wi-Fi configuração </strong> para <strong> ativado </strong> .</br></br>Selecione uma região e um fuso horário em que o dispositivo será usado. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Nesta seção, você pode inserir os detalhes da rede sem fio Wi-Fi à qual o dispositivo deve se conectar automaticamente. Para fazer isso, selecione <strong> ativado </strong> , digite o SSID, o tipo de rede ( <strong> aberto </strong> ou <strong> WPA2-Pessoal </strong> ) e (se <strong> WPA2-Pessoal </strong> ) a senha da rede sem fio.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Você pode registrar o dispositivo no Azure Active Directory ou criar uma conta local no dispositivo</br></br>Antes de usar um assistente de Designer de Configuração do Windows para configurar o registro do Azure AD em massa, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configure a participação do Azure AD em sua organização</a>. A configuração <strong>número máximo de dispositivos por usuário</strong> em seu locatário do Azure AD determina quantas vezes o token em massa que você obtém do assistente pode ser usado. Para registrar o dispositivo no Azure AD, selecione essa opção e insira um nome amigável para o token em massa que você obterá usando o assistente. Defina uma data de expiração do token (máximo de 30 dias a partir da data de obtenção do token). Selecione <strong> obter token em massa </strong> . Na <strong> janela permitir que&#39;s você se conecta </strong> , insira uma conta que tenha permissões para ingressar em um dispositivo para o Azure AD e, em seguida, a senha. Selecione <strong> aceitar </strong> para dar ao Windows Configuration designer as permissões necessárias. </br></br>Para criar uma conta local, selecione essa opção e insira um nome de usuário e senha. </br></br><strong>Importante:</strong> <br />(Somente para Windows 10, versão 1607) Se você criar uma conta local no pacote de provisionamento, será necessário alterar a senha usando o <strong> aplicativo configurações a </strong> cada 42 dias. Se a senha não for alterada durante esse período, a conta poderá estar bloqueada e não será possível entrar.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Para provisionar o dispositivo com um certificado, clique em <strong>Adicionar um certificado</strong>. Insira um nome para o certificado e, em seguida, procure e selecione o certificado a ser usado.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Alternar <strong> Sim </strong> ou <strong> não </strong> para habilitar o modo de desenvolvedor no HoloLens. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Saiba mais sobre o Modo de desenvolvedor.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Não defina uma senha para proteger seu pacote de provisionamento. Se o pacote de provisionamento estiver protegido por uma senha, o provisionamento do dispositivo HoloLens falhará.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Quando terminar, selecione **criar**. Leva apenas alguns segundos. Quando o pacote é criado, o local onde o pacote está armazenado é exibido como hiperlink na parte inferior da página.

### 3. Crie um pacote de provisionamento para o HoloLens usando o provisionamento avançado

> [!NOTE]
> Um pacote de provisionamento que você cria no **provisionamento avançado** não precisa incluir uma licença de atualização de edição do Windows holográfico para empresas para se aplicar com sucesso a um HoloLens (1ª gen). [Veja mais no Windows holográfico for Business para HoloLens (1ª geração)](hololens1-upgrade-enterprise.md).

1. Na página inicial do Designer de Configuração do Windows, selecione **Provisionamento avançado**.
2. Na janela **Digite os detalhes do projeto**, especifique um nome e o local para o projeto. Como alternativa, insira uma breve descrição para caracterizar seu projeto.

3. Selecione **Avançar**.

4. Na janela **escolher quais configurações exibir e configurar** , selecione **Windows 10 holográfico**e, em seguida, selecione **Avançar**.

5. Selecione **concluir**.

6. Expanda **as configurações de tempo de execução** e personalize o pacote usando qualquer uma das configurações [descritas mais adiante neste artigo](#what-you-can-configure).

    > [!IMPORTANT]
    > (Somente para Windows 10, versão 1607) Se você criar uma conta local no pacote de provisionamento, será necessário alterar a senha usando o aplicativo **configurações** a cada 42 dias. Se a senha não for alterada durante esse período, a conta poderá estar bloqueada e não será possível entrar. Se a conta do usuário estiver bloqueada, você deverá [realizar uma recuperação de dispositivo completo](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Selecione **arquivo**  >  **salvar**.

8. Leia o aviso de que os arquivos do Project podem conter informações confidenciais e selecione **OK**.

    > [!IMPORTANT]
    > Ao compilar um pacote de provisionamento, você pode incluir informações confidenciais nos arquivos de projeto e no arquivo de pacote de provisionamento (.ppkg). Embora você tenha a opção de criptografar o arquivo. ppkg, arquivos de projeto não são criptografados. Você deve armazenar os arquivos de projeto em um local seguro e excluí-los quando não forem mais necessários.
    
9. Selecione **Exportar**  >  **pacote de provisionamento**.

10. Altere o **proprietário** para o **administrador de ti**. Isso define a precedência deste pacote de provisionamento mais alto do que os pacotes de provisionamento aplicados a este dispositivo de outras fontes. Selecione **Avançar**.

11. Defina um valor para **Versão do Pacote**.

    > [!TIP]
    > Você pode fazer alterações em pacotes existentes e alterar o número de versão para atualizar pacotes previamente aplicados.

12. Na guia **selecionar detalhes de segurança do pacote de provisionamento**, selecione **Avançar**.

    > [!WARNING]
    > Se você criptografar o pacote de provisionamento, o provisionamento do dispositivo HoloLens falhará.  

13. Selecione **Avançar** para especificar o local de saída onde você deseja que o pacote de provisionamento se torne depois de criado. Por padrão, o Designer de Configuração do Windows usa a pasta do projeto como o local de saída.

    Opcionalmente, você pode selecionar **procurar** para alterar o local de saída padrão.

14. Selecione **Avançar**.

15. Selecione **Compilar** para começar a criar o pacote. As informações do projeto são exibidas na página de compilação, e a barra de progresso indica o status da compilação.

16. Quando a compilação for concluída, selecione **concluir**.

<span id="apply" />

## Aplicar um pacote de provisionamento ao HoloLens durante a configuração

Dispositivos do HoloLens 2 no Windows holográfico, versão 2004 ou versão [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) ou posterior, podem usar uma unidade USB para aplicar um pacote de provisionamento. Basta copiar o arquivo. ppkg para a raiz da unidade USB. Os pacotes de provisionamento só serão aplicados se estiverem na raiz da unidade USB. O pacote de provisionamento presente será aplicado sequencialmente.

Os dispositivos do HoloLens 2 no [Windows holográfico versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou posterior têm recursos mais recentes para ajudar a simplificar e simplificar esse processo, tornando-o automático. Consulte as seguintes seções:

- [Fornecimento automático de inicialização de USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Confirmar automaticamente os pacotes de provisionamento em OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Provisionamento automático sem usar a interface do usuário](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Use o cabo USB para conectar o dispositivo a um PC (ou unidade USB para o HoloLens 2 conforme mencionado acima) e, em seguida, inicie o dispositivo. Não continue após a primeira página de **momento interagindo** do OOBE.   
    - No HoloLens (1ª gen), esta página contém uma caixa azul. 
    - No HoloLens 2, esta página contém o Hummingbird.

2. Pressione e solte rapidamente os botões de **Menos Volume** e **Ligar/Desligar** simultaneamente. 

3. O HoloLens aparece como um dispositivo no explorador de arquivos no computador.

4. No Explorador de Arquivos, arraste e solte o pacote de provisionamento (.ppkg) no armazenamento do dispositivo.

5. Pressione brevemente e solte os botões de **volume** e **energia** simultaneamente novamente enquanto estiver na **primeira página de momento interagindo** do OOBE.

6. O dispositivo pergunta se você confia no pacote e deseja aplicá-lo. Confirme que você confia no pacote.

7. Você verá se o pacote foi aplicado com êxito ou não. Se ele falhar, você poderá corrigir o pacote e tentar novamente. Se ele tiver bem-sucedido, continue OOBE.

> [!NOTE]
> Se o dispositivo foi comprado antes de agosto de 2016, você precisará entrar no dispositivo usando uma conta da Microsoft, obter a atualização do sistema operacional mais recente e, em seguida, redefinir o sistema operacional para aplicar o pacote de provisionamento.

### Fornecimento automático de inicialização de USB

- Processos automatizados que permitem menos interação do usuário, quando unidades USB com pacotes de provisionamento são usadas durante o OOBE.

Antes desta versão, os usuários precisavam iniciar a tela de aprovisionamento manualmente durante o OOBE para provisionar usando uma combinação de botões. Agora os usuários podem ignorar a combinação de botões usando um pacote de provisionamento em uma unidade de armazenamento USB. 

1. Conecte a unidade USB com o pacote de provisionamento durante o primeiro momento interagindo do OOBE
1. Quando o dispositivo estiver pronto para ser provisionado, ele abrirá automaticamente o prompt com a página de provisionamento. 

Observação: se uma unidade USB estiver conectada enquanto o dispositivo estiver sendo inicializado, o OOBE enumerará o dispositivo de armazenamento USB existente, bem como o relógio para a conexão de outros itens.

Para obter mais informações sobre como aplicar pacotes de provisionamento durante a OOBE, continue lendo [aqui](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### Confirmar automaticamente os pacotes de provisionamento em OOBE
- Processo automatizado que permite menos interação do usuário, quando a página do pacote de provisionamento é exibida, ele aplica automaticamente todos os pacotes listados.

Quando a tela principal do provisionamento surgir, o OOBE contará 10 segundos antes de iniciar automaticamente a aplicação de todos os pacotes de provisionamento. Os usuários ainda podem confirmar ou cancelar nestas 10 segundos após verificar os pacotes esperados.

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

## Aplicar um pacote de provisionamento ao HoloLens após a instalação

> [!NOTE]
> Estas etapas se aplicam somente ao Windows 10, versão 1809.

Em seu computador, siga estas etapas:
1. Crie um pacote de provisionamento, conforme descrito em [criar um pacote de provisionamento para HoloLens usando o assistente do hololens](hololens-provisioning.md).
2. Conecte o dispositivo HoloLens a um computador usando um cabo USB. O HoloLens aparece como um dispositivo no explorador de arquivos no computador.
3. Arraste e solte o pacote de provisionamento para a pasta documentos no HoloLens.

Em seu HoloLens, siga estas etapas:
1. Vá para **configurações**  >  **contas**  >  **acessar trabalho ou escola**. 
2. Em **configurações relacionadas**, selecione **Adicionar ou remover um pacote de provisionamento**.
3. Na próxima página, selecione **Adicionar um pacote** para iniciar o seletor de arquivos e selecione o pacote de provisionamento. Se a pasta estiver vazia, verifique se você selecionou **este dispositivo** e selecione **documentos**.

Após a aplicação do pacote, ele aparecerá na lista de **pacotes instalados**. Para exibir os detalhes do pacote ou remover o pacote do dispositivo, selecione o pacote listado.

## O que você pode configurar

Os pacotes de provisionamento usam CSPs (provedores de serviço de configuração). Se você não estiver familiarizado com os CSPs, consulte [Introdução aos CSPs para profissionais de TI](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

No Designer de Configuração do Windows, quando você cria um pacote de provisionamento para o Windows Holographic, as configurações em **Personalizações disponíveis** se baseiam em [CSPs compatíveis no Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). A tabela a seguir descreve as configurações que você deseja configurar para o HoloLens.

![Configurações de tempo de execução comuns para o HoloLens](images/icd-settings.png)

| Configuração | Descrição |
| --- | --- |
| **Certificados** | Implante um certificado para o HoloLens.  |
| **ConnectivityProfiles** | Implante um perfil de Wi-Fi para o HoloLens.   |
| **EditionUpgrade** | [Atualize para o Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Políticas** | Permita ou evite o modo desenvolvedor no HoloLens. [Políticas compatíveis com o Windows Holographic for Business](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## Instalação do aplicativo via pacote de provisionamento

Os aplicativos podem ser instalados por meio de pacotes de provisionamento em dispositivos do HoloLens 2. Isso permite um pacote facilmente reutilizável que você pode usar para ajudá-lo a distribuir seus aplicativos. Leia as instruções completas de [implantação de aplicativos por meio de pacotes de provisionamento](app-deploy-provisioning-package.md).  

> [!NOTE]
> O HoloLens (1ª gen) tem suporte limitado para a instalação de aplicativos (**UniversalAppInstall**) usando um pacote de provisionamento. Os dispositivos HoloLens (1ª gen) só dão suporte à instalação de um aplicativo via PPKG durante o OOBE e somente com instalações de contexto de usuário.
