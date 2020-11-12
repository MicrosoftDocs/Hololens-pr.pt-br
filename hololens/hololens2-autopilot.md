---
title: Windows Autopilot para o HoloLens 2 (Visualização Privada)
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
ms.openlocfilehash: 5f887d7321c391ea9d67833373b39b3c9feeaf2c
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163095"
---
# Piloto automático do Windows para HoloLens 2

Quando você configura dispositivos do HoloLens 2 para o programa piloto automático do Windows, seus usuários podem seguir um processo simples para provisionar os dispositivos na nuvem.

Esse programa de piloto automático suporta o modo de autoimplantação do piloto automático para provisionar dispositivos HoloLens 2 como dispositivos compartilhados no seu locatário. O modo de autoimplantação aproveita a imagem e os drivers OEM pré-instalados do dispositivo durante o processo de provisionamento. Um usuário pode provisionar o dispositivo sem colocá-lo e passar pela experiência pronta para uso (OOBE). Para saber mais sobre o Windows Autopilot para Windows 10 clique [aqui](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

Quando um usuário iniciar o processo de autoimplantação do piloto automático, o processo concluirá as etapas a seguir:

1. Ingresso do dispositivo no Azure Active Directory (Azure AD)
   > [!NOTE]  
   > O piloto automático do HoloLens não é compatível com o ingresso no Active Directory ou o Azure AD join.
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe perfis de rede, certificados e aplicativos e políticas direcionados aos dispositivos.
1. Provisione este dispositivo.
1. Apresente a tela de entrada ao usuário.

## Windows Autopilot para o HoloLens 2 Visualização Privada

Siga as etapas abaixo para configurar a Visualização Privada do seu ambiente:

1. Certifique-se de atender aos requisitos do Windows Autopilot para o HoloLens 2
1. Inscreva-se no programa de visualização privada do Windows Autopilot para o HoloLens 2
1. Verifique se o seu locatário está limitado (inscrito para participar do programa)
1. Registre seus dispositivos no Windows Autopilot
1. Crie um grupo de dispositivos
1. Crie um perfil de implementação
1. Verifique a configuração do ESP
1. Configurar um perfil de configuração personalizada para os dispositivos do HoloLens (problema conhecido)
1. Verifique o status do perfil dos dispositivos do HoloLens


### 1. Verifique se você atende aos requisitos do Windows Autopilot para o HoloLens 2

**Revise as seguintes seções do artigo de requisitos do Piloto automático do Windows:**

- [Requisitos de rede](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Requisitos de licenciamento](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Requisitos de configuração](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**Examine a seção ["Requisitos”](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements) do artigo do Artigo do modo Autoimplantação do piloto automático do Windows.** Seu ambiente precisa atender a esses requisitos, bem como aos requisitos padrão do Piloto automático do Windows. Você não precisa revisar as seções "Passo a passo" e "Validação" do artigo. Os procedimentos posteriores neste artigo fornecem as etapas correspondentes específicas do HoloLens. Para obter mais informações sobre como registrar dispositivos e configurar perfis, consulte [4. Registrar dispositivos no Piloto automático do Windows](#4-register-devices-in-windows-autopilot) e [6. Crie um perfil de implantação](#6-create-a-deployment-profile) neste artigo. Estas seções fornecem as etapas específicas para o HoloLens.

> [!IMPORTANT]  
> O Windows Autopilot para HoloLens 2 possui requisitos específicos de sistema operacional. O Autopilot conta com o Windows Holographic, versão 2004 (build 19041.1103 ou posterior) sendo pré-instalado em dispositivos HoloLens. Os dispositivos entregues até o final de setembro de 2020 têm o Windows Holographic, versão 1903 pré-instalado. Entre em contato com o seu distribuidor para saber quando os dispositivos prontos para o Autopilot podem ser enviados a você. Se você deseja participar da versão prévia privada, confira as instruções e requisitos abaixo.

Informações específicas do Autopilot por versões do sistema operacional do HoloLens.
- Para usar o AutoPilot, um dispositivo deve ter o [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004) ou mais recente.
- Para usar o AutoPilot usando Wi-Fi, um dispositivo deve ter o [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ou mais recente. No entanto, essas compilações ainda podem usar adaptadores Ethernet. 
- Em compilações do [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2), foi habilitada uma nova opção de gerenciamento de dispositivo de [CSP do Tenantlockdown e Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).  

Se quiser confirmar a versão de compilação do dispositivo ou atualizá-la, conecte-o ao um computador com Windows 10 e inicie o [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8). 

**Se você deseja experimentar a visualização do Autopilot, antes de iniciar o processo OOBE e provisionamento, verifique se os dispositivos do HoloLens atendem aos seguintes requisitos:**

- Certifique-se de que o dispositivo esteja no Windows Holográfico, versão 2004 (compilação 19041.1103 ou posterior). Se o Sistema Operacional mais recente não estiver pré-instalado, você deve atualizar manualmente usando o [Complemento de Recuperação Avançado (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab). Você pode encontrar as instruções [aqui](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). 
- Seus dispositivos devem estar registrados no Windows Autopilot. Para obter informações sobre como registrar os dispositivos, consulte [4. Registre os dispositivos no Windows Autopilot](#4-register-devices-in-windows-autopilot). É recomendável que o revendedor ou distribuidor registre os dispositivos para você.  
- No [Windows Holographic, versão 2004](hololens-release-notes.md#windows-holographic-version-2004), os dispositivos precisam estar conectados à Internet antes de ativar o HoloLens e iniciar o processo de provisionamento do AutoPilot. Conecte o dispositivo à Ethernet usando um adaptador "USB-C para Ethernet" para conectividade com a Internet com fio.
- No [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2), os dispositivos podem se conectar a Wi-Fi no OOBE para detectar o AutoPilot. 
- Os dispositivos ainda não são membros do Azure AD e não estão registrados no Intune (ou em outro sistema MDM). O processo de autoimplantação do Piloto automático conclui essas etapas. Para garantir que todas as informações relacionadas ao dispositivo estejam limpas, verifique as páginas dos **Dispositivos** nos portais do Azure AD e do Intune.
- Para configurar e gerenciar os perfis do modo Autoimplantação do Piloto automático, certifique-se de que você possui acesso ao [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com).


### 2. Inscreva-se no programa Piloto Automático do Windows para o HoloLens 2.

**Para participar do programa, você deve ter seu locatário inscrito no Programa de Visualização Privada. Isso habilita os controles da interface do usuário específicos do HoloLens Intune (também conhecido como MEM) para o Autopilot.** Para fazer isso, vá para a [Solicitação de Piloto automático do Windows para a Visualização privada do HoloLens](https://aka.ms/APHoloLensTAP) ou use o seguinte código QR para enviar uma solicitação.  

![Código QR do piloto automático](./images/hololens-ap-qrcode.png)  

A Microsoft faz voos com os locatários uma vez por semana. Você receberá uma notificação por e-mail assim que o período de veiculação for concluído. 

Na solicitação, forneça as seguintes informações:

- Domínio do locatário
- ID do locatário
- Número de dispositivos HoloLens 2 que estão participando desta avaliação
- Número de dispositivos HoloLens 2 que você planeja implantar usando o modo autoimplantação do piloto automático

### 3. verifique se o locatário foi comprovado

Para verificar se seu locatário é transportado ao programa Piloto automático depois de enviar sua solicitação, siga estas etapas:

1. Entre no [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com).
1. Clique em DispositivosWindowsRegistro do Windows**Perfis de implantação do Piloto automático do Windows** > **Criar perfil**.  
   
   ![Criar lista suspensa de perfis inclui um item do HoloLens.](./images/hololens-ap-enrollment-profiles.png)
  Você deverá visualizar uma lista que inclui **HoloLens**. Se essa opção não estiver presente, use uma das opções de [Comentários](hololens2-autopilot.md#feedback-for-autopilot) para entrar em contato conosco.

### 4. Registre dispositivos no Piloto automático do Windows.

Na fase de preparação, existem duas maneiras principais de registrar os dispositivos no Windows Autopilot: 

1. **Entrar em contato com seu distribuidor ou revendedor quando fizer um pedido para registrar os seus dispositivos** ou
2. **Recuperar o hash do hardware (também conhecido como ID do hardware) e registre o dispositivo manualmente.** 

Para mais informações sobre o registro de dispositivos, consulte a documentação [Adicionando dispositivos ao Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices).  

**Recupere um hash de hardware de dispositivo**

O dispositivo pode registrar seu hash de hardware em um arquivo CSV durante o processo OOBE, ou mais tarde, quando o proprietário do dispositivo iniciar o processo de coleta de logs de diagnóstico (descrito no procedimento a seguir). Geralmente, o proprietário do dispositivo é o primeiro usuário a entrar no dispositivo.

1. Inicie o dispositivo do HoloLens 2.
1. No dispositivo, pressione os botões Ligar e Baixar volume e solte-os solte-os. O dispositivo coleta os logs de diagnóstico e o hash do hardware, e os armazena em um conjunto de arquivos. zip. 
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

**Registre os dispositivos no Piloto automático do Windows.**

1. No Centro de administração do Microsoft Endpoint Manager, clique em DispositivosWindowsRegistro do Windows e clique em dispositivos > **Importar** em **Programa de implantação do piloto automático do Windows**.

1. Em **Adicionar dispositivos do piloto automático do Windows**, clique no arquivo CSV DeviceHash, clique em **Abrir**e em **Importar**.  
   
   ![Use o comando Importar para importar o hash do hardware.](./images/hololens-ap-hash-import.png)
1. Assim que a importação estiver concluída, clique em DispositivosWindowsRegistro do WindowsDispositivos**Sincronização**. O processo pode levar alguns minutos para ser concluído, dependendo de quantos dispositivos estão sendo sincronizados. Para ver o dispositivo registrado, clique em **Atualização**.  
   
   ![Use os comandos Sincronizar e Atualizar para exibir a lista de dispositivos.](./images/hololens-ap-devices-sync.png)  

### 5. Crie um grupo de dispositivos

1. No Centro de administração do Microsoft Endpoint Manager, clique em **Grupos** > **Grupo novo**.
1. Para **Tipo de grupo**, clique em **Segurança** e insira um nome e uma descrição do grupo.
1. Para Tipo de associação, clique em Atribuídos ou **Dispositivo dinâmico**.
1. Siga um destes procedimentos:  
   
   - Se você selecionou **Atribuído** para **Tipo de associação** na etapa anterior, clique em **Membros**e adicione os dispositivos do Piloto automático ao grupo. Os dispositivos do piloto automático que ainda não foram registrados são listados usando o número de série do dispositivo como o nome do dispositivo.
   - Se você clicou em **Dispositivos dinâmicos** para **Tipo de associação** na etapa anterior, clique em **Tipo de membros**e insira o código em **Regra avançada**, que se assemelha ao seguinte:
     - Se você quer criar um grupo que inclua todos os seus dispositivos de piloto automático, digite: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - O campo de marca de grupo do Intune é mapeado ao atributo **OrderID** nos dispositivos do Azure AD. Se você quer criar um grupo que inclua todos os seus dispositivos de piloto automático com um rótulo de grupo específico (a ID do pedido do dispositivo do Azure AD), digite: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se você quer criar um grupo que inclua todos os seus dispositivos de piloto automático que tenham uma ID do pedido de compra específico, digite: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Esses atributos de destino de regras são exclusivos dos dispositivos do Piloto automático.
1. Clique em **OK** e em **Criar**.

### 6. Crie um perfil de implantação

1. No Centro de administração do Microsoft Endpoint Manager, clique em **Dispositivos** > **Windows** > **Registro do Windows** > **Perfis de implantação do Piloto automático do Windows** > **Criar perfil** > **HoloLens**.
1. Insira um nome e uma descrição para o perfil e clique em **Próximo**.  
   
   ![Adicione um nome e descrição de perfil](./images/hololens-ap-profile-name.png)
1. Na página **Experiência pronta para uso (OOBE)**, a maioria das configurações são pré-configuradas para simplificar o OOBE para essa avaliação. Opcionalmente, você pode definir as seguintes configurações:  

   - **idioma (Região)**: selecione o idioma do OOBE. Recomendamos que você selecione um idioma na lista de [idiomas com suporte do HoloLens 2](hololens2-language-support.md).
   - **Configurar o teclado automaticamente**: para garantir que o teclado corresponda ao idioma selecionado, clique em **Sim**.
   - **Aplicar o modelo de nome do dispositivo**: para definir automaticamente o nome do dispositivo durante o OOBE, clique em **Sim** e insira a frase do modelo e os espaços reservados em **Digitar um nome**. Por exemplo, insira um prefixo e `%RAND:4%`&mdash;um espaço reservado para um número aleatório de quatro dígitos.
     > [!NOTE]  
     > Se você usar um modelo de nome de dispositivo, o processo OOBE reiniciará o dispositivo mais uma vez depois de aplicar o nome do dispositivo e antes de ingressar no Azure AD. Essa reinicialização permite que o novo nome tenha efeito.  

   ![Defina as configurações do OOBE.](./images/hololens-ap-profile-oobe.png)
1. Depois de definir as configurações, clique em **Próximo**.
1. Na página **Rótulos do escopo**, opcionalmente, adicione os rótulos de escopo que você quer aplicar a esse perfil. Para obter mais informações sobre os rótulos de escopo, consulte [Usar o controle de acesso com base na função e nos rótulos de escopo da TI distribuída](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Quando terminar, clique em **Próximo**.
1. Na página **Atribuições**, clique em **Grupos selecionados** para **Atribuir a**.
1. Em **GROPOS SELECIONADOS**, clique em **+ Selecionar grupos para incluir**.
1. Na lista **Selecione grupos para incluir**, clique no grupo de dispositivos que você criou nos dispositivos de piloto automático do HoloLens e clique em **Próximo**.  
  
   Se você quiser excluir todos os grupos, clique em **Selecionar grupos para excluir**e clique nos grupos que você quer excluir.

   ![Atribuir um grupo de dispositivos ao perfil.](./images/hololens-ap-profile-assign-devicegroup.png)
1. Na página **Revisar + Criar**, examine as configurações e clique em **Criar** para criar o perfil.  
   
   ![Revisar + Criar](./images/hololens-ap-profile-summ.png)

### 7. Verifique a configuração ESP

A Página de status da inscrição (ESP) exibe o status do processo completo de configuração do dispositivo que é executado quando um usuário gerenciado pelo MDM entra em um dispositivo pela primeira vez. Verifique se a configuração do ESP é semelhante à seguinte e verifique se as atribuições estão corretas.  

![Configuração ESP](./images/hololens-ap-profile-settings.png)

### 8. Verifique o status do perfil dos dispositivos HoloLens

1. No Centro de administração do Microsoft Endpoint manager, clique em DispositivosWindows > **Registro do Windows** > **Dispositivos**.
1. Verifique se os dispositivos do HoloLens estão listados e se o status do perfil é **Atribuído**.  
   > [!NOTE]  
   > Pode levar alguns minutos para que o perfil seja atribuído ao dispositivo.  
   
   ![Atribuições de dispositivo e de perfil.](./images/hololens-ap-devices-assignments.png)

## Piloto automático do Windows para a experiência do usuário do HoloLens 2

Depois que as instruções acima forem concluídas, os usuários do HoloLens 2 passarão pela seguinte experiência para provisionar seus dispositivos HoloLens:  

1. A experiência do AutoPilot requer acesso à Internet. Use uma das seguintes opções para fornecer acesso à Internet:
    - Conecte o dispositivo a uma rede Wi-Fi no OOBE e deixe-o detectar a experiência do Autopilot automaticamente. Este é o único momento em que você precisará interagir com o OOBE até que a experiência do AutoPilot seja concluída sozinha. Observe que, por padrão, o HoloLens 2 aguarda 10 segundos para detectar o Autopilot após detectar a Internet. Se nenhum perfil do AutoPilot for detectado em 10 segundos, o OOBE apresentará os Termos de Licença. Caso encontre esse cenário, reinicie o dispositivo para que seja feita outra tentativa de detectar o AutoPilot. Observe também que o OOBE só poderá esperar indefinidamente pelo Autopilot se a política TenantLockdown estiver definida no dispositivo.
    - Conecte o dispositivo com Ethernet usando adaptadores "USB-C para Ethernet" para conectividade com a Internet com fio e deixe o HoloLens 2 concluir a experiência do Autopilot automaticamente.
    - Conecte o dispositivo com adaptadores "USB-C para Wi-Fi" para conectividade com a Internet sem fio e deixe o HoloLens 2 concluir a experiência do Autopilot automaticamente.

       > [!NOTE]
       > O uso do Autopilot terá um efeito no [proprietário do dispositivo](security-adminless-os.md#device-owner).
   
       > [!IMPORTANT]  
       > Os dispositivos que querem usar redes Wi-Fi no OOBE para Autopilot devem ser [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Para dispositivos que usam adaptadores Ethernet, conecte o dispositivo à rede antes de iniciar o OOBE (Out-of-the-Box-Experience). O dispositivo determina se está sendo provisionado como um dispositivo Autopilot na primeira tela do OOBE. Se o dispositivo não puder se conectar à rede ou se você optar por não provisionar o dispositivo como um dispositivo de piloto automático, não poderá mudar para o provisionamento de piloto automático posteriormente. Em vez disso, você teria que iniciar esse procedimento novamente para provisionar o dispositivo como um dispositivo de piloto automático.

1. O dispositivo deve iniciar o OOBE automaticamente. Não interaja com o OOBE. Em vez disso, sente-se e relaxe! Deixe o HoloLens 2 detectar a conectividade de rede e permitir que ele complete o OOBE automaticamente. Talvez o dispositivo reinicie durante o OOBE. As telas OOBE devem ser assim.
   
   ![Etapa 1 do OOBE](./images/hololens-ap-uex-1.png)
   ![Etapa 2 do OOBE](./images/hololens-ap-uex-2.png)
   ![Etapa 3 do OOBE](./images/hololens-ap-uex-3.png)
   ![Etapa 4 do OOBE](./images/hololens-ap-uex-4.png)

1. No final do OOBE, você pode entrar no dispositivo usando seu nome de usuário e senha.

   ![Etapa 5 do OOBE](./images/hololens-ap-uex-5.png)

## Problemas conhecidos

- Não é possível instalar aplicativos que usam o contexto de segurança do dispositivo.

## CSP do Tenantlockdown e AutoPilot
- Mantém os dispositivos no locatário da organização bloqueando-os para o locatário, mesmo através da reinicialização do dispositivo ou do reflash. Com mais segurança, desautorizando a criação da conta por meio do provisionamento. 

Os dispositivos HoloLens 2 agora são compatíveis com o CSP do TenantLockdown a partir da versão 20H2 do Windows Holographic. 

O CSP do [TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) permite que o HoloLens 2 seja vinculado ao registro do MDM usando apenas o Autopilot. Depois que o nó RequireNetworkInOOBE do CSP do TenantLockdown for definido com valor verdadeiro ou falso (definido inicialmente) no HoloLens 2, esse valor permanece no dispositivo, apesar de atualizar novamente, atualizações do sistema operacional, etc. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, o OOBE aguarda indefinidamente que o perfil do Autopilot seja baixado e aplicado com sucesso, após a conectividade de rede. 

Depois que o nó RequireNetworkInOOBE dos CSPs do TenantLockdown for definido como verdadeiro no HoloLens 2, as seguintes operações não serão permitidas no OOBE: 
- Criação de usuário local usando provisionamento do tempo de execução 
- Execução da operação de ingresso no AAD através de provisionamento do tempo de execução 
- Seleção de proprietários do dispositivo na experiência do OOBE 

### Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique true para o nó RequireNetworkInOOBE, conforme mostrado a seguir.
O valor OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configurar o bloqueio de locatário via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Depois que esta configuração de dispositivo for aplicada com sucesso no dispositivo Hololens 2, os efeitos do TenantLockdown estarão ativos.

### Como desmarcar o RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune? 
1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração de dispositivos criada acima foi atribuída anteriormente. 

1. Crie um perfil de configuração de dispositivo baseado em OMA-URI personalizado e especifique falso para RequireNetworkInOOBE como mostrado a seguir. O valor OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE definida como falso via OMA-URI no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Assim que esta configuração de dispositivo for aplicada com sucesso no dispositivo Hololens 2, os efeitos do TenantLockdown ficarão inativos. 

### O que aconteceria durante o OOBE, se o perfil do Autopilot não fosse atribuído em um HoloLens depois que TenantLockdown fosse definido como verdadeiro? 
O OOBE aguardará indefinidamente o download do perfil do Autopilot e a caixa de diálogo a seguir será apresentada. Para remover os efeitos do TenantLockdown, o dispositivo deve ser registrado com seu locatário original primeiro usando apenas o Autopilot e o RequireNetworkInOOBE desmarcado, conforme descrito na etapa anterior antes que as restrições introduzidas pelo CSP do TenantLockdown sejam removidas. 

![Modo de exibição no dispositivo quando a política for imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

## Comentários para o AutoPilot

Para fornecer comentários ou relatar problemas, use um dos seguintes métodos:

- Use o aplicativo Feedback Hub. Você pode encontrar esse aplicativo em um computador conectado ao HoloLens. No Feedback Hub, clique em **Gerenciamento de empresa**  > **Dispositivo**.  

  Ao enviar comentários ou relatar um problema, forneça uma descrição detalhada. Se aplicável, inclua capturas de tela e logs.
- Envie um e-mail para [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com). Para o assunto do e-mail, insira o **\<*Tenant*> comentário da avaliação do Piloto automático do HoloLens 2** (onde \<*Tenant*>é o nome do seu locatário do Intune).

  Forneça uma descrição detalhada na sua mensagem. No entanto, a menos que a Equipe de suporte solicite especificamente, não inclua dados como capturas de tela ou logs. Esses dados podem incluir informações privadas ou de identificação pessoal (PII).
