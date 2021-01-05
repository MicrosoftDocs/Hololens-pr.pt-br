---
title: Windows Autopilot para HoloLens 2
description: Como configurar o AutoPilot em dispositivos do HoloLens 2.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 98f35c52091a2d477a2f0852f66ad706498ad026
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253587"
---
# Piloto automático do Windows para HoloLens 2

A partir da versão 2004 do Windows Holographic, o HoloLens 2 é compatível com o [Modo de Autoimplantação](https://docs.microsoft.com/mem/autopilot/self-deploying) do Windows Autopilot Deployment. Os administradores podem configurar aplicativo de configuração inicial pelo usuário (OOBE) no Microsoft Endpoint Manager e permite aos usuários finais preparem os dispositivos para uso comercial com pouca ou nenhuma interação. Isso reduz a sobrecarga de gerenciamento de estoque, o custo da preparação do dispositivo e das chamadas de suporte de funcionários durante a experiência de configuração. Para saber mais sobre o Windows Autopilot, clique [aqui](https://docs.microsoft.com/mem/autopilot/windows-autopilot).

Assim como os dispositivos Surface, é recomendável que os clientes trabalhem com o [Provedor de Soluções de Nuvem](https://partner.microsoft.com/cloud-solution-provider) da Microsoft Corporation (revendedor ou distribuidor) para obter dispositivos registrados com o serviço de piloto automático por meio do Partner Center. Outros métodos para o registro de dispositivos são descritos [aqui](https://docs.microsoft.com/mem/autopilot/add-devices), embora aproveitar os parceiros de canal da Microsoft garanta o caminho mais efetivo de ponta a ponta.

> [!NOTE]
> A partir de 20/11/2020 a configuração do Autopilot para HoloLens no Microsoft Endpoint Manager está em transição para a **Visualização Pública**. Os clientes não precisam mais se registrar na visualização particular e todos os locatários poderão configurar o AutoPilot no centro de administração do MEM.

Quando um usuário iniciar o processo de autoimplantação do AutoPilot, o AutoPilot concluirá as seguintes etapas:

1. Ingresso do dispositivo no Azure Active Directory (Azure AD) Observe que o AutoPilot para HoloLens não é compatível com o ingresso no Active Directory ou o ingresso do Azure AD Híbrido.

1. Use o Azure AD para registrar o dispositivo no Microsoft Endpoint Manager (ou em outro serviço de MDM).

1. Baixar e aplicar políticas direcionadas a dispositivos, certificados, perfis e aplicativos de rede.

1. Provisione este dispositivo.

1. Apresente a tela de entrada ao usuário.

## Configurando o AutoPilot para HoloLens 2

Siga as etapas abaixo para configurar o ambiente:

1. [Análise os requisitos do Windows Autopilot Deployment para o HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Habilitar a Inscrição Automática de MDM](#2-enable-automatic-mdm-enrollment)

1. [Registre os dispositivos no Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Crie um grupo de dispositivos.](#4-create-a-device-group)

1. [Crie um perfil de implantação.](#5-create-a-deployment-profile)

1. [Verifique a configuração da Página de Status de Inscrição (ESP).](#6-verify-the-esp-configuration)

1. [Verifique o status de perfil dos dispositivos do HoloLens.](#7-verify-the-profile-status-of-the-hololens-devices)

### 1. analisar os requisitos do Windows Autopilot Deployment para o HoloLens 2

#### Revise as seguintes seções do artigo de requisitos do Piloto automático do Windows:

- [Requisitos de rede](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Requisitos de licenciamento](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Requisitos de configuração](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Examine a seção ["Requisitos”](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements) do artigo do Artigo do modo Autoimplantação do piloto automático do Windows.** Seu ambiente precisa atender a esses requisitos, bem como aos requisitos padrão do Piloto automático do Windows. Você não precisa revisar as seções "Passo a passo" e "Validação" do artigo. Os procedimentos posteriores neste artigo fornecem as etapas correspondentes específicas do HoloLens.

Para obter informações sobre como registrar dispositivos e configurar perfis, confira [2. Registre os dispositivos no Windows AutoPilot e no](#3-register-devices-in-windows-autopilot) [4. Crie um perfil de implantação](#5-create-a-deployment-profile) neste artigo. Para configurar e gerenciar os perfis do modo Autoimplantação do Autopilot, certifique-se de que você possui acesso ao [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com).

#### Análise os requisitos do sistema operacional do HoloLens:

- Os dispositivos devem estar no [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) (Build 19041,1103) ou posterior. Para confirmar a versão de compilação em seu dispositivo ou atualizar para o sistema operacional mais recente, é possível usar o [Complemento Avançado de Recuperação (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab). É possível localizar as instruções [aqui](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). Observe que os dispositivos entregues até o final de setembro de 2020 têm a versão 1903 do Windows Holographic pré-instalada. Contato o revendedor para garantir que os dispositivos prontos para o AutoPilot sejam enviados para você.

- A versão 2004 do Windows Holographic, só é compatível com o Autopilot na conexão ethernet. Verifique se o HoloLens está conectado à ethernet usando um adaptador de "USB-C para Ethernet" **antes de ligá-lo**. Na inicialização do dispositivo, nenhuma interação do usuário é necessária. Se você estiver planejando uma implantação do AutoPilot para muitos dispositivos HoloLens, recomendamos que você planeje a infraestrutura do adaptador. Não recomendamos hubs USB, pois eles geralmente exigem que outros drivers de terceiros sejam instalados, os quais não são suportados no HoloLens.

- A [versão 20H2 do Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2) (Build 19041,1128) ou posterior suporta o AutoPilot pelo Wi-Fi, embora você ainda possa usar adaptadores ethernet. Para dispositivos conectados via Wi-Fi, o usuário só deve:

     - Percorrer a cena da hummingbird
     - Escolher o idioma e a localidade
     - Executar a calibragem do olho
     - Estabelecer a conexão de rede

- A versão 20H2 do Windows Holographic suporta o [Provedor de Soluções na Nuvem da Microsoft Tenantlockdown e o AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), que bloqueia um dispositivo para um locatário e garante que o dispositivo permaneça associado a esse locatário em caso de reinicialização acidental ou intencional de reinicialização ou apagamento.  

- Certifique-se de que os dispositivos ainda não sejam membros do Microsoft Azure Active Directory e não estejam registrados no Intune (ou outro sistema MDM). O processo de autoimplantação do Autopilot conclui essas etapas. Para garantir que todas as informações relacionadas ao dispositivo estejam limpas, verifique as páginas dos **Dispositivos** nos portais tanto do Azure AD quanto do Intune. Observe que o recurso "Converter todos os dispositivos de destino para AutoPilot" não é compatível com o HoloLens no momento.  

### 2. Habilitar a Inscrição Automática de MDM:

Para que o Autopilot tenha êxito, você precisará habilitar a Inscrição MDM Automática no portal do Azure. Isso permitirá que o dispositivo seja registrado sem um usuário.

No [portal do Azure](https://portal.azure.com/#home) selecione **Azure Active Directory** -> **Mobility (MDM e MAM)** -> **Microsoft Intune**. Em seguida, configure o **escopo do usuário MDM**, você precisará selecionar **Todos**.

Análise o seguinte [guia resumido sobre como ativar a Inscrição Automática de MDM](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) ou o [guia de início Rápido de Inscrição Automática](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) para obter ainda mais informações sobre como configurar.

### 3. Registre os dispositivos no Windows Autopilot

#### Obter hash de hardware

Os dispositivos devem ser registrados no Windows Autopilot Deployment antes da primeira configuração. Para obter a documentação do MEM no registro do dispositivo, confira [Adicionando os dispositivos ao AutoPilot](https://docs.microsoft.com/mem/autopilot/add-devices).  

Há duas maneiras principais de registrar dispositivos HoloLens:

 - **O revendedor pode registrar os dispositivos no Partner Center quando você fizer um pedido.**

   > [!NOTE]  
   > Esse é o caminho recomendado para adicionar os dispositivos ao serviço de Autopilot. [Saiba mais](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).  

 - **Recupere o hash de hardware (também conhecido como ID de hardware) e registre o dispositivo manualmente no centro de administração MEM**.

- **Recuperar o código hash de hardware**

O dispositivo registra o código hash de hardware em um arquivo CSV durante o processo OOBE, ou mais tarde, quando um proprietário do dispositivo inicia o processo de coleta do log de diagnóstico (descrito no procedimento a seguir). Geralmente, o proprietário do dispositivo é o primeiro usuário a entrar no dispositivo.

1. Inicie o dispositivo do HoloLens 2.

1. No dispositivo, pressione os botões **Ligar/Desligar** e **Volume para Baixo** ao mesmo tempo e, em seguida, libere-os. O dispositivo coleta os logs de diagnóstico e o código hash do hardware, e os armazena em um conjunto de arquivos .zip.

   1. Para obter detalhes completos e um vídeo de instrução sobre como realizar isso, leia sobre os [Diagnósticos Offline](hololens-diagnostic-logs.md#offline-diagnostics).

1. Use um cabo USB-C para conectar o dispositivo a um computador.

1. No computador, abra o Explorador de arquivos. Abra **Este compoutador\\\<*HoloLens device name*>\\Armazenamento interno\\Documentos**, e localize o arquivo AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Talvez o arquivo .zip não esteja disponível imediatamente. Se o arquivo ainda não estiver pronto, você poderá ver um arquivo HoloLensDiagnostics.temp na pasta Documentos. Para atualizar a lista de arquivos, atualize a janela.

1. Extraia o conteúdo do arquivo AutopilotDiagnostics.zip.

1. Nos arquivos extraídos, localize o arquivo CSV que tenha o prefixo do nome do arquivo "DeviceHash". Copie esse arquivo em uma unidade no computador no qual você poderá acessá-lo mais tarde.  

   > [!IMPORTANT]  
   > Os dados no arquivo CSV devem usar o seguinte formato de linha e cabeçalho:
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### Registrar dispositivo por meio do MEM

1. No [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecione **Dispositivos** > ** Windows** > **Inscrição do Windows** e, em seguida, selecione **Importar** > **Dispositivos** em **Programa Windows Autopilot Deployment**.

1. Em **Adicionar dispositivos do Windows Autopilot**, clique no arquivo CSV DeviceHash, clique em **Abrir**e em**Importar**.  

   > [!div class="mx-imgBorder"]
   > ![Use o comando Importar para importar o hash do hardware.](./images/hololens-ap-hash-import.png)

1. Assim que a importação estiver concluída, clique em DispositivosWindowsRegistro do WindowsDispositivos**Sincronização**. O processo pode levar alguns minutos para ser concluído, dependendo de quantos dispositivos estão sendo sincronizados. Para ver o dispositivo registrado, clique em **Atualização**.  

   > [!div class="mx-imgBorder"]
   > ![Use os comandos Sincronizar e Atualizar para exibir a lista de dispositivos.](./images/hololens-ap-devices-sync.png)  

### 4. Criar um grupo de dispositivos

1. No [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecione **Grupos**  >  **Novo grupo**.

1. Para **Tipo de grupo**, selecione **Segurança** e insira um nome e uma descrição do grupo.

1. Para Tipo de associação, clique em Atribuídos ou **Dispositivo dinâmico**.

1. Siga um destes procedimentos:  

   - Se você selecionou **Atribuído** para **Tipo de associação** na etapa anterior, clique em **Membros**e adicione os dispositivos do Piloto automático ao grupo. Os dispositivos do piloto automático que ainda não foram registrados são listados usando o número de série do dispositivo como o nome do dispositivo.
   - Se você clicou em **Dispositivos dinâmicos** para **Tipo de associação** na etapa anterior, clique em **Tipo de membros**e insira o código em **Regra avançada**, que se assemelha ao seguinte:
     - Se você quer criar um grupo que inclua todos os seus dispositivos de piloto automático, digite: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - O campo de marca de grupo do Intune é mapeado ao atributo **OrderID** nos dispositivos do Azure AD. Se você quer criar um grupo que inclua todos os seus dispositivos de piloto automático com um rótulo de grupo específico (a ID do pedido do dispositivo do Azure AD), digite: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se você quer criar um grupo que inclua todos os seus dispositivos de piloto automático que tenham uma ID do pedido de compra específico, digite: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Esses atributos de destino de regras são exclusivos dos dispositivos do Piloto automático.
1. Selecione **Salvar**, e em seguida, selecione **Criar**.

### 5. Criar um perfil de implantação

1. No [centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecione **Dispositivos** > ** Windows** > ** Inscrições do Windows** > ** Perfis de implantação do Windows Autopilot** > ** Criar perfil** > ** HoloLens**.
   ![Criar lista suspensa de perfis inclui um item do HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Insira um nome e uma descrição para o perfil e clique em **Próximo**.  
   Você deverá visualizar uma lista que inclui **HoloLens**. Se essa opção não estiver presente, use uma das opções de [Comentários](hololens2-autopilot.md#feedback-and-support-for-autopilot) para nos contatar.

   > [!div class="mx-imgBorder"]
   > ![Adicione um nome e descrição de perfil](./images/hololens-ap-profile-name.png)

1. Na página **Experiência pronta para uso (OOBE)**, a maioria das configurações são pré-configuradas para simplificar o OOBE para essa avaliação. Opcionalmente, você pode definir as seguintes configurações:  

   - **idioma (Região)**: selecione o idioma do OOBE. Recomendamos que você selecione um idioma na lista de [idiomas com suporte do HoloLens 2](hololens2-language-support.md).
   - **Configurar o teclado automaticamente**: para garantir que o teclado corresponda ao idioma selecionado, clique em **Sim**.
   - **Aplicar o modelo de nome do dispositivo**: para definir automaticamente o nome do dispositivo durante o OOBE, clique em **Sim** e insira a frase do modelo e os espaços reservados em **Digitar um nome**. Por exemplo, insira um prefixo e `%RAND:4%`&mdash;um espaço reservado para um número aleatório de quatro dígitos.
     > [!NOTE]  
     > Se você usar um modelo de nome de dispositivo, o processo OOBE reiniciará o dispositivo mais uma vez depois de aplicar o nome do dispositivo e antes de ingressar no Azure AD. Essa reinicialização permite que o novo nome tenha efeito.  

   > [!div class="mx-imgBorder"]
   > ![Defina as configurações do OOBE.](./images/hololens-ap-profile-oobe.png)

1. Depois de definir as configurações, clique em **Próximo**.
1. Na página **Rótulos do escopo**, opcionalmente, adicione os rótulos de escopo que você quer aplicar a esse perfil. Para obter mais informações sobre os rótulos de escopo, consulte [Usar o controle de acesso com base na função e nos rótulos de escopo da TI distribuída](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Quando terminar, clique em **Próximo**.
1. Na página **Atribuições**, clique em **Grupos selecionados** para **Atribuir a**.
1. Em **GROPOS SELECIONADOS**, clique em **+ Selecionar grupos para incluir**.
1. Na lista **Selecione grupos para incluir**, clique no grupo de dispositivos que você criou nos dispositivos de piloto automático do HoloLens e clique em **Próximo**.  
  
   Se você quiser excluir todos os grupos, clique em **Selecionar grupos para excluir**e clique nos grupos que você quer excluir.

   > [!div class="mx-imgBorder"]
   > ![Atribuir um grupo de dispositivos ao perfil.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na página **Revisar + Criar**, examine as configurações e clique em **Criar** para criar o perfil.  

   > [!div class="mx-imgBorder"]
   > ![Analisar + criar](./images/hololens-ap-profile-summ.png)

### 6. Verificar a configuração de ESP

A Página de status da inscrição (ESP) exibe o status do processo completo de configuração do dispositivo que é executado quando um usuário gerenciado pelo MDM entra em um dispositivo pela primeira vez. Verifique se a configuração do ESP é semelhante à seguinte e verifique se as atribuições estão corretas.  

> [!div class="mx-imgBorder"]
> ![Configuração ESP](./images/hololens-ap-profile-settings.png)

### 7. Verificar o status do perfil dos dispositivos HoloLens

1. No Centro de administração do Microsoft Endpoint Manager, selecione **Dispositivos** > **Windows** > **Inscrição do Windows** > **Dispositivos**.

1. Verifique se os dispositivos do HoloLens estão listados e se o status do perfil é **Atribuído**.  

   > [!NOTE]  
   > Pode levar alguns minutos para que o perfil seja atribuído ao dispositivo.  

   > [!div class="mx-imgBorder"]
   > ![Atribuições de dispositivo e de perfil.](./images/hololens-ap-devices-assignments.png)

## Piloto automático do Windows para a experiência do usuário do HoloLens 2

Depois que as instruções acima forem concluídas, os usuários do HoloLens 2 passarão pela seguinte experiência para provisionar seus dispositivos HoloLens:  

1. A experiência do AutoPilot requer acesso à Internet. Use uma das seguintes opções para fornecer acesso à Internet:

    - Conecte o dispositivo a uma rede Wi-Fi no OOBE e deixe-o detectar a experiência do Autopilot automaticamente. Este é o único momento em que você precisará interagir com o OOBE até que a experiência do AutoPilot seja concluída sozinha. Observe que, por padrão, o HoloLens 2 aguarda 10 segundos para detectar o Autopilot após detectar a Internet. Se nenhum perfil do AutoPilot for detectado em 10 segundos, o OOBE apresentará os Termos de Licença. Caso encontre esse cenário, reinicie o dispositivo para que seja feita outra tentativa de detectar o AutoPilot. Observe também que o OOBE só poderá esperar indefinidamente pelo Autopilot se a política TenantLockdown estiver definida no dispositivo.

    - Conecte o dispositivo com Ethernet usando adaptadores "USB-C para Ethernet" para conectividade com a Internet com fio e deixe o HoloLens 2 concluir a experiência do Autopilot automaticamente.

    - Conecte o dispositivo com adaptadores "USB-C para Wi-Fi" para conectividade com a Internet sem fio e deixe o HoloLens 2 concluir a experiência do Autopilot automaticamente.

        > [!IMPORTANT]  
       > Dispositivos que tentam usar redes Wi-Fi em OOBE para Autopilot devem estar no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Para dispositivos que usam adaptadores Ethernet, conecte o dispositivo à rede antes de iniciar o OOBE (Out-of-the-Box-Experience). O dispositivo determina se está sendo provisionado como um dispositivo Autopilot na primeira tela do OOBE. Se o dispositivo não puder se conectar à rede ou se você optar por não provisionar o dispositivo como um dispositivo de piloto automático, não poderá mudar para o provisionamento de piloto automático posteriormente. Em vez disso, você teria que iniciar esse procedimento novamente para provisionar o dispositivo como um dispositivo de piloto automático.

1. O dispositivo deve iniciar o OOBE automaticamente. Não interaja com o OOBE. Em vez disso, sente-se e relaxe! Deixe o HoloLens 2 detectar a conectividade de rede e permitir que ele complete o OOBE automaticamente. Talvez o dispositivo reinicie durante o OOBE. As telas OOBE devem ser assim.

   ![OOBE etapa 1](./images/autopilot-welcome.jpg)
   ![OOBE etapa 2](./images/autopilot-step-complete.jpg)
   ![OOBE etapa 3](./images/autopilot-device-setup.jpg)

1. No final do OOBE, é possível entrar no dispositivo usando seu nome de usuário e senha.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## O Provedor de Soluções na Nuvem da Microsoft do Tenantlockdown e AutoPilot

Os dispositivos do HoloLens 2 dão suporte ao Provedor de Soluções na Nuvem da Microsoft TenantLockdown para a versão 20H2 do Windows Holographic. O Provedor de Soluções na Nuvem da Microsoft mantém os dispositivos no locatário da organização bloqueando-os para esse locatário, mesmo através da reinicialização ou atualização do dispositivo.

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

1. Crie um perfil de configuração de dispositivo baseado em OMA-URI personalizado e especifique falso para RequireNetworkInOOBE como mostrado a seguir.
O valor OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE definida como falso via OMA-URI no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Assim que esta configuração de dispositivo for aplicada com sucesso no dispositivo Hololens 2, os efeitos do TenantLockdown ficarão inativos.

#### O que aconteceria durante o OOBE, se o perfil do Autopilot não fosse atribuído em um HoloLens depois que TenantLockdown fosse definido como verdadeiro? 
O OOBE aguardará indefinidamente o download do perfil do Autopilot e a caixa de diálogo a seguir será apresentada. Para remover os efeitos do TenantLockdown, o dispositivo deve ser registrado com seu locatário original primeiro usando apenas o Autopilot e o RequireNetworkInOOBE desmarcado, conforme descrito na etapa anterior antes que as restrições introduzidas pelo CSP do TenantLockdown sejam removidas.

![Modo de exibição no dispositivo quando a política for imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

## Problemas Conhecidos e limitações

- Estamos investigando um problema em que a instalação do aplicativo baseado em contexto de dispositivo configurada no MEM não se aplica ao HoloLens. [Saiba mais sobre as instalações de contexto de dispositivo e contexto de usuário.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Durante a configuração do AutoPilot pelo Wi-Fi, pode haver uma instância em que o perfil do AutoPilot não seja baixado quando a conexão com a Internet for estabelecida pela primeira vez. Nesse caso, o Contrato de Licença de Usuário Final (EULA) é apresentado e o usuário tem a opção de continuar com a experiência de configuração não-Autopilot. Para tentar configurar novamente com o Autopilot, coloque o dispositivo em suspensão e ligue-o novamente, ou reinicie o dispositivo e deixe-o tentar novamente.
- O recurso "converter todos os dispositivos de destino para AutoPilot" não é compatível com o HoloLens no momento.  

### Solução de problemas

Os artigos a seguir podem ser um recurso útil para obter mais informações e solucionar problemas do Autopilot. No entanto, esteja ciente de que esses artigos são baseados no Windows 10 Desktop e nem todas as informações são aplicadas ao HoloLens:

- [Windows Autopilot: problemas conhecidos](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Solução de problemas de registro de dispositivos Windows no Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: Conflitos de Política](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Comentários e suporte para o AutoPilot

Para fornecer comentários ou relatar problemas, use um dos seguintes métodos:

- Para obter suporte ao registro de dispositivos, entre em contato com seu revendedor ou distribuidor.
- Para obter consultas de suporte gerais sobre o Windows Autopilot, ou para problemas como atribuições de perfil, criação de grupo ou controles do portal MEM, [contate o suporte do Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/get-support)  
- Se o seu dispositivo estiver registrado no serviço de Autopilot e o perfil estiver atribuído no portal MEM, contate o [suporte](https://docs.microsoft.com/hololens/) do Microsoft HoloLens (confira o cartão "Suporte"). Abra um tíquete de suporte e, se aplicável, inclua capturas de tela e registros capturando [logs de diagnóstico offline](hololens-diagnostic-logs.md#offline-diagnostics) durante a experiência (OOBE).
- Para relatar um problema do dispositivo, use o aplicativo Hub de Comentários no HoloLens. No Hub de Comentários, clique na categoria **Gerenciamento de Empresa**  > **Dispositivo**.
- Para fornecer comentários gerais sobre o AutoPilot para HoloLens, você pode enviar esta [pesquisa](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
