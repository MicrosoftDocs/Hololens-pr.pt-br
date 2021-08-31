---
title: Windows Autopilot para HoloLens 2
description: Saiba como instalar, configurar e solucionar problemas do Autopilot em dispositivos HoloLens 2.
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
ms.openlocfilehash: 7dbe77c8c5999d5be1a61ca9deaa8071d152c87a
ms.sourcegitcommit: d0c7bf5b055fa1fa8ac5562eef904583a655da99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2021
ms.locfileid: "122782800"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot para HoloLens 2

> [!NOTE]
> A configuração do Autopilot para o HoloLens no Microsoft Endpoint Manager está em transição de **versão prévia pública** para **disponibilidade geral**. Todos os locatários poderão configurar o Autopilot na MEM do centro de administração.

Começando no Windows Holographic versão 2004, o HoloLens 2 dá suporte ao [Modo de Autoimplantação](/mem/autopilot/self-deploying) do Windows Autopilot com o Microsoft Intune (não há suporte para MDMs de terceiros). Os administradores podem configurar a OOBE (configuração inicial pelo usuário) no Microsoft Endpoint Manager e habilitar os usuários finais a prepararem os dispositivos para uso comercial com pouca ou nenhuma interação. Essa configuração reduz a sobrecarga de gerenciamento de estoque, o custo da preparação do dispositivo e as chamadas de suporte dos funcionários durante a experiência de instalação. Saiba mais na documentação do [Windows Autopilot](/mem/autopilot/windows-autopilot).

Assim como ocorre com os dispositivos Surface, é recomendável que os clientes trabalhem com o [Provedor de Soluções na Nuvem](https://partner.microsoft.com/cloud-solution-provider) (revendedor ou distribuidor) da Microsoft para registrar os dispositivos no serviço do Autopilot por meio do Partner Center. Outros métodos de registro de dispositivos são descritos na documentação [adicionar dispositivo](/mem/autopilot/add-devices), mas usar os parceiros de canal da Microsoft garante o caminho de ponta a ponta mais eficaz.



Quando um usuário iniciar o processo de autoimplantação do Autopilot, o Autopilot concluirá as seguintes etapas:

1. Adicionar o dispositivo ao Azure AD (Azure Active Directory). Observe que o Autopilot para HoloLens não dá suporte ao ingresso no Active Directory nem ao ingresso no Azure AD Híbrido.

1. Usar o Azure AD para registrar o dispositivo no Microsoft Endpoint Manager (ou em outro serviço de MDM).

1. Baixar e aplicar políticas, certificados, perfis de rede e aplicativos voltados ao dispositivo.

1. Provisionar o dispositivo.

1. Apresentar a tela de conexão ao usuário.

## <a name="configuring-autopilot-for-hololens-2"></a>Configurando o Autopilot para o HoloLens 2

Siga estas etapas para configurar seu ambiente:

1. [Examinar os requisitos do Windows Autopilot para o HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Habilitar o Registro de MDM Automático](#2-enable-automatic-mdm-enrollment)

1. (Somente para o Intune) [Verifique se o registro de MDM não está bloqueado para dispositivos do Windows.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Registrar dispositivos no Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Criar um grupo de dispositivos.](#5-create-a-device-group)

1. [Criar um perfil de implantação.](#6-create-a-deployment-profile)

1. [Verificar a configuração da EP (Página de Status do Registro).](#7-verify-the-esp-configuration)

1. [Verificar o status do perfil dos dispositivos HoloLens.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Examinar os requisitos do Windows Autopilot para o HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Examine as seguintes seções do artigo sobre requisitos do Windows Autopilot:

- [Requisitos de rede](/mem/autopilot/networking-requirements)  
- [Requisitos de licenciamento](/mem/autopilot/licensing-requirements)  
- [Requisitos de configuração](/mem/autopilot/configuration-requirements)

**Examine a seção "[Requisitos](/windows/deployment/windows-autopilot/self-deploying#requirements)" do artigo sobre o modo de Autoimplantação do Windows Autopilot.** Seu ambiente precisa atender a esses requisitos e aos requisitos do Windows Autopilot padrão. Não é necessário examinar as seções "Passo a passo" e "Validação" do artigo. Os procedimentos descritos mais adiante neste artigo fornecem as etapas correspondentes que são específicas do HoloLens.

Para saber como registrar dispositivos e configurar perfis, confira [4. Registrar dispositivos no Windows Autopilot](#4-register-devices-in-windows-autopilot) e [6. Criar um perfil de implantação](#6-create-a-deployment-profile) neste artigo. Para configurar e gerenciar os perfis do modo de autoimplantação do Autopilot, verifique se você tem acesso ao [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com).

#### <a name="review-hololens-os-requirements"></a>Examinar os requisitos do sistema operacional do HoloLens:

- Os dispositivos devem estar na [versão 2004 do Windows Holographic](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) ou posterior. Para confirmar a versão do build em seu dispositivo ou reinstalar a imagem do sistema operacional mais recente, use o [ARC (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) e nossas [instruções para reinstalar a imagem do dispositivo](/hololens/hololens-recovery#clean-reflash-the-device). Observe que os dispositivos fornecidos até o final de setembro de 2020 têm a versão 1903 do Windows Holographic pré-instalada. Entre em contato com o revendedor para garantir que dispositivos prontos para o Autopilot sejam enviados para você.

- A versão 2004 do Windows Holographic dá suporte apenas à conexão com o Autopilot via ethernet. Verifique se o HoloLens está conectado à ethernet usando um adaptador "USB-C para Ethernet" **antes de ligá-lo**. Na inicialização do dispositivo, não é necessária nenhuma interação do usuário. Se você está planejando uma implantação do Autopilot para muitos dispositivos HoloLens, recomendamos que planeje a infraestrutura de adaptadores. Não recomendamos o uso de hubs USB, pois geralmente eles exigem que outros drivers de terceiros sejam instalados, o que não tem suporte no HoloLens.

- A [versão 20H2 do Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) ou posterior dá suporte ao Autopilot por Wi-Fi, embora você ainda possa usar adaptadores ethernet. Para dispositivos conectados via Wi-Fi, o usuário precisa somente:

     - Percorrer a cena do beija-flor
     - Escolher o idioma e a localidade
     - Executar a calibragem dos olhos
     - Estabelecer a conexão de rede

- A versão 20H2 do Windows Holographic dá suporte ao [CSP TenantLockdown e ao Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), o que bloqueia um dispositivo para um locatário e garante que o dispositivo permaneça associado a esse locatário em caso de reinicialização ou limpeza acidental ou intencional.  

- Verifique se os dispositivos ainda não são membros do Azure AD e não estão registrados no Intune (ou outro sistema de MDM). O processo de autoimplantação do Autopilot realiza essas etapas. Para garantir que todas as informações relacionadas ao dispositivo sejam limpas, verifique as páginas dos **Dispositivos** nos portais do Azure AD e do Intune. Observe que no momento o recurso "Converter todos os dispositivos de destino ao Autopilot" não tem suporte no HoloLens.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Habilitar o Registro de MDM Automático:

Para que o Autopilot tenha êxito, você precisará habilitar o Registro de MDM Automático no portal do Azure. Isso permitirá que o dispositivo seja registrado sem um usuário.

No [portal do Azure](https://portal.azure.com/#home), selecione **Azure Active Directory** -> **Mobilidade (MDM e MAM)**  -> **Microsoft Intune**. Configure o **Escopo do usuário do MDM**. Você precisará selecionar **Tudo**.

Analise o breve [guia sobre como habilitar o registro automático de MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) ou o [guia de início rápido de registro automático](/mem/intune/enrollment/quickstart-setup-auto-enrollment) para obter ainda mais informações sobre a configuração.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Verifique se o registro de MDM não está bloqueado para dispositivos do Windows.

Para que o Autopilot seja bem-sucedido, você precisará verificar se seus dispositivos HoloLens podem ser inscritos. Como o HoloLens é considerado um dispositivo do Windows, será necessário não haver restrições de registro que possam bloquear sua implantação. [Analise essa lista de restrições](/mem/intune/enrollment/enrollment-restrictions-set) e verifique se você poderá registrar seus dispositivos.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Registrar dispositivos no Windows Autopilot

Os dispositivos devem ser registrados no Windows Autopilot antes da primeira configuração. Para obter a documentação do MEM sobre registro de dispositivos, confira [Adição de dispositivos ao Autopilot](/mem/autopilot/add-devices).  

Há três maneiras principais de registrar dispositivos HoloLens:

 - **O revendedor pode registrar dispositivos no Partner Center quando você faz um pedido.**

   > [!NOTE]  
   > Esse é o caminho recomendado para adicionar dispositivos ao serviço do Autopilot. [Saiba mais](/mem/autopilot/partner-registration).  

 - **Você pode [enviar uma solicitação de suporte](hololens2-autopilot-registration-support.md) diretamente à Microsoft.**
 - **Recuperar o hash do hardware (também conhecido como a ID do hardware) e registrar o dispositivo manualmente no centro de administração do MEM**.

#### <a name="obtain-hardware-hash"></a>Obter o hash de hardware
Há duas maneiras de recuperar o hash de hardware.
1. Você pode [enviar uma solicitação de suporte](hololens2-autopilot-registration-support.md) diretamente à Microsoft.
2. Você pode recuperá-lo no dispositivo. O dispositivo registra o hash de hardware em um arquivo CSV durante o processo de OOBE ou mais tarde, quando um proprietário do dispositivo inicia o processo de coleta do log de diagnóstico (descrito no procedimento a seguir). Normalmente, o proprietário do dispositivo é o primeiro usuário a entrar nele.
     > [!WARNING]
     > Em builds anteriores ao 20H2, se você tiver percorrido o processo de OOBE e a telemetria tiver sido definida como Obrigatória, você não poderá coletar o hash de hardware para o Autopilot usando esse método. Para coletar o hash de hardware com esse método, defina sua opção de telemetria como Completa por meio do aplicativo Configurações e selecione Privacidade –> Diagnóstico.

    1. Inicie o dispositivo HoloLens 2.

    1. No dispositivo, pressione os botões **Ligar/Desligar** e **Diminuir o volume** ao mesmo tempo e solte-os. O dispositivo coleta os logs de diagnóstico e o hash de hardware e os armazena em um conjunto de arquivos .zip.

   1. Para ver todos os detalhes e um vídeo de instruções sobre como fazer isso, leia sobre o [Diagnóstico offline](hololens-diagnostic-logs.md#offline-diagnostics).

    1. Use um cabo USB-C para conectar o dispositivo a um computador.

    1. No computador, abra o Explorador de Arquivos. Abra **Este Computador\\\<*HoloLens device name*>\\Armazenamento Interno\\Documentos** e localize o arquivo AutopilotDiagnostics.zip.  

       > [!NOTE]  
       > Talvez o arquivo .zip não fique disponível imediatamente. Se ele ainda não estiver pronto, você poderá ver um arquivo HoloLensDiagnostics.temp na pasta Documentos. Para atualizar a lista de arquivos, atualize a janela.
    
    1. Extraia o conteúdo do arquivo AutopilotDiagnostics.zip.

    1. Nos arquivos extraídos, localize o arquivo CSV que tem o prefixo de nome de arquivo "DeviceHash". Copie esse arquivo para uma unidade no computador na qual você possa acessá-lo mais tarde.  

       > [!IMPORTANT]  
       > Os dados no arquivo CSV devem usar o seguinte formato de linha e cabeçalho:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Registrar dispositivo usando o MEM

1. No [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecione **Dispositivos** > **Windows** > **Registro do Windows** e escolha **Dispositivos** > **Importar** em **Programa Windows Autopilot Deployment**.

1. Em **Adicionar dispositivos Windows Autopilot**, selecione o arquivo CSV DeviceHash, escolha **Abrir** e selecione **Importar**.  

   > [!div class="mx-imgBorder"]
   > ![Usar o comando Importar para importar o hash de hardware.](./images/hololens-ap-hash-import.png)

1. Após a conclusão da importação, selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos** > **Sincronização**. O processo poderá levar alguns minutos para ser concluído dependendo de quantos dispositivos estiverem sendo sincronizados. Para ver o dispositivo registrado, selecione **Atualizar**.  

   > [!div class="mx-imgBorder"]
   > ![Usar os comandos Sincronizar e Atualizar para exibir a lista de dispositivos.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Criar um grupo de dispositivos

1. No [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecione **Grupos** > **Novo grupo**.

1. Em **Tipo de grupo**, selecione **Segurança** e insira um nome do grupo e uma descrição.

1. Em **Tipo de associação**, selecione **Atribuída** ou **Dispositivo Dinâmico**.

1. Realize um dos seguintes procedimentos:  

   - Se você selecionou **Atribuída** para **Tipo de associação** na etapa anterior, selecione **Membros** e adicione dispositivos Autopilot ao grupo. Os dispositivos Autopilot que ainda não foram registrados são listados usando o número de série do dispositivo como nome do dispositivo.
   - Se você selecionou **Dispositivos Dinâmicos** para **Tipo de associação** na etapa anterior, selecione **Membros do dispositivo dinâmico** e insira o código em **Regra avançada** semelhante ao seguinte:
     - Se você pretende criar um grupo que inclua todos os dispositivos do Autopilot, digite: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - O campo de marcação do grupo do Intune é mapeado para o atributo **OrderID** em dispositivos do Azure AD. Se você quer criar um grupo que inclua todos os seus dispositivos Autopilot com uma marcação de grupo específica (a OrderID do dispositivo do Azure AD), digite: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Se você quer criar um grupo que inclui todos os seus dispositivos Autopilot com uma ID de ordem de compra específica, digite: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Essas regras são destinadas a atributos que são exclusivos de dispositivos Autopilot.
1. Selecione **Salvar** e **Criar**.

### <a name="6-create-a-deployment-profile"></a>6. Criar um perfil de implantação

1. No [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Perfis de implantação do Windows Autopilot** > **Criar perfil** > **HoloLens**.
   ![A lista suspensa Criar perfil inclui um item do HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Insira um nome e uma descrição para o perfil e selecione **Avançar**.  
   Você verá uma lista que inclui o **HoloLens**. Se essa opção não estiver presente, use uma das opções de [Comentários](hololens2-autopilot.md#feedback-and-support-for-autopilot) para entrar em contato conosco.

   > [!div class="mx-imgBorder"]
   > ![Adicionar um nome e uma descrição do perfil](./images/hololens-ap-profile-name.png)

1. Na página do **OOBE (aplicativo de configuração inicial pelo usuário)** , a maioria das definições são pré-configuradas para simplificar o OOBE para essa avaliação. Opcionalmente, você pode definir estas configurações:  

   - **Idioma (Região)** : selecione o idioma para o OOBE. Recomendamos selecionar um idioma na lista de [idiomas com suporte para o HoloLens 2](hololens2-language-support.md).
   - **Configurar o teclado automaticamente**: para garantir que o teclado corresponda ao idioma selecionado, selecione **Sim**.
   - **Aplicar modelo de nome de dispositivo**: para definir automaticamente o nome do dispositivo durante o OOBE, selecione **Sim** e insira a frase do modelo e os espaços reservados em **Inserir um nome**. Por exemplo, insira um prefixo e `%RAND:4%`&mdash;um espaço reservado para um número aleatório de quatro dígitos.
     > [!NOTE]  
     > Se você usar um modelo de nome de dispositivo, o processo de OOBE reiniciará o dispositivo mais uma vez após aplicar o nome do dispositivo e antes de adicionar o dispositivo ao Azure AD. Essa reinicialização permite que o novo nome entre em vigor.  

   > [!div class="mx-imgBorder"]
   > ![Definir as configurações do OOBE](./images/hololens-ap-profile-oobe.png)

1. Depois de definir as configurações, selecione **Avançar**.
1. Na página **Marcações de escopo**, você tem a opção de adicionar as marcações de escopo que deseja aplicar ao perfil. Saiba mais sobre marcas de escopo em [Usar controle de acesso baseado em função e marcas de escopo para TI distribuída](/mem/intune/fundamentals/scope-tags.md). Quando terminar, selecione **Avançar**.
1. Na página **Atribuições**, selecione **Grupos selecionados** em **Atribuir a**.
1. Em **GRUPOS SELECIONADOS**, selecione **+ Selecionar grupos para incluir**.
1. Na lista **Selecionar grupos para incluir**, selecione o grupo de dispositivos que você criou nos dispositivos Autopilot do HoloLens e selecione **Avançar**.  
  
   Se quiser excluir algum grupo, escolha **Selecionar grupos para excluir** e escolha os grupos que deseja excluir.

   > [!div class="mx-imgBorder"]
   > ![Atribuindo um grupo de dispositivos ao perfil.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na página **Examinar + Criar**, examine as configurações e selecione **Criar** para criar o perfil.  

   > [!div class="mx-imgBorder"]
   > ![Examinar + criar](./images/hololens-ap-profile-summ.png)

### <a name="7-verify-the-esp-configuration"></a>7. Verificar a configuração do ESP

A ESP (Página de Status de Registro) exibe o status do processo completo de configuração do dispositivo que é executado quando um usuário gerenciado pelo MDM entra em um dispositivo pela primeira vez. Verifique se a configuração da ESP é semelhante à seguinte e verifique se as atribuições estão corretas.  

> [!div class="mx-imgBorder"]
> ![Configuração da ESP](./images/hololens-ap-profile-settings.png)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Verificar o status do perfil dos dispositivos HoloLens

1. No Centro de Administração do Microsoft Endpoint Manager, selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Dispositivos**.

1. Verifique se os dispositivos HoloLens estão listados e se o status do perfil deles é **Atribuído**.  

   > [!NOTE]  
   > Poderão ser necessários alguns minutos para que o perfil seja atribuído ao dispositivo.  

   > [!div class="mx-imgBorder"]
   > ![Atribuições de dispositivo e de perfil.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Experiência do usuário do Windows Autopilot para o HoloLens 2

Após as instruções acima serem concluídas, os usuários do HoloLens 2 passarão pela seguinte experiência para provisionar os dispositivos HoloLens deles:  

1. A experiência do Autopilot requer acesso à Internet. Use uma das seguintes opções para fornecer acesso à Internet:

    - Conecte o dispositivo a uma rede Wi-Fi no OOBE e deixe-o detectar a experiência do Autopilot automaticamente. Este é o único momento em que você precisará interagir com o OOBE até que a experiência do Autopilot seja concluída por conta própria. Observe que, por padrão, o HoloLens 2 aguarda 10 segundos para detectar o Autopilot após detectar a Internet. Se nenhum perfil do Autopilot for detectado em 10 segundos, o OOBE apresentará os Termos de Licença para Software Microsoft. Se isso acontecer com você, reinicie o dispositivo para que ele tente detectar o Autopilot novamente. Observe também que a OOBE só poderá esperar indefinidamente pelo Autopilot se a política de TenantLockdown estiver definida no dispositivo.

    - Conecte o dispositivo à Ethernet usando um adaptador "USB-C para Ethernet" para ter conectividade com a Internet com fio e deixe o HoloLens 2 concluir a experiência do Autopilot automaticamente.

    - Conecte o dispositivo usando um adaptador "USB-C para Wi-Fi" para ter conectividade com a Internet sem fio e deixe o HoloLens 2 concluir a experiência do Autopilot automaticamente.

        > [!IMPORTANT]  
       > Os dispositivos que tentam usar redes Wi-Fi no OOBE para o Autopilot devem estar no [Windows Holographic, versão 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Para dispositivos que usam adaptadores Ethernet, conecte o dispositivo à rede antes de iniciar o OOBE (aplicativo de configuração inicial pelo usuário). O dispositivo determina se está sendo provisionado como um dispositivo Autopilot na primeira tela do OOBE. Se o dispositivo não puder se conectar à rede ou se você optar por não o provisionar como um dispositivo Autopilot, você não poderá mudar para o provisionamento com Autopilot posteriormente. Você teria que iniciar esse procedimento novamente para provisionar o dispositivo como Autopilot.

1. O dispositivo deve iniciar o OOBE automaticamente. Não interaja com o OOBE.

    > [!IMPORTANT]
    > Não interaja com a OOBE nem pressione o botão de energia para colocar o sistema em espera/desligamento enquanto o Autopilot está em andamento. Isso pode fazer com que o fluxo do Autopilot não seja concluído.

   Aguarde o HoloLens 2 detectar a conectividade de rede e deixe que ele complete o OOBE automaticamente. O dispositivo poderá ser reiniciado durante o OOBE. As telas do OOBE devem ser semelhantes às ilustradas a seguir.

   ![Etapa 1 do OOBE](./images/autopilot-welcome.jpg)
   ![Etapa 2 do OOBE](./images/autopilot-step-complete.jpg)
   ![Etapa 3 do OOBE](./images/autopilot-device-setup.jpg)

1. No final do OOBE, você poderá entrar no dispositivo usando seu nome de usuário e senha.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>CSP TenantLockdown e Autopilot

Os dispositivos HoloLens 2 dão suporte ao CSP TenantLockdown como parte da versão 20H2 do Windows Holographic. Esse CSP mantém os dispositivos no locatário da organização bloqueando-os no locatário por redefinição ou atualização do dispositivo.

O CSP [TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) permite que o HoloLens 2 seja vinculado ao registro do MDM usando apenas o Autopilot. Após o nó RequireNetworkInOOBE do CSP TenantLockdown ser definido com um valor de verdadeiro ou falso (definido inicialmente) no HoloLens 2, esse valor permanecerá no dispositivo mesmo que haja reinstalações da imagem, atualizações do sistema operacional etc.

Após o nó RequireNetworkInOOBE do CSP TenantLockdown ser definido como verdadeiro no HoloLens 2, o OOBE aguarda indefinidamente que o perfil do Autopilot seja baixado e aplicado com sucesso após a conexão com a rede.

Após o nó RequireNetworkInOOBE do CSP TenantLockdown ser definido como verdadeiro no HoloLens 2, as seguintes operações deixam de ser permitidas no OOBE:

- Criação de usuário local usando provisionamento no runtime 
- Execução de uma operação de adição no Azure AD por meio de provisionamento no runtime 
- Seleção de proprietários do dispositivo na experiência do OOBE 

#### <a name="how-to-set-this-using-intune"></a>Como definir isso usando o Intune? 
1. Crie um perfil de configuração de dispositivo OMA URI personalizado e especifique verdadeiro para o nó RequireNetworkInOOBE, conforme mostrado a seguir.
O valor do OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuração do bloqueio de locatário via OMA-URI](images/hololens-tenant-lockdown.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos.

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.  

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Depois que essa configuração de dispositivo for aplicada com sucesso ao dispositivo HoloLens 2, os efeitos do TenantLockdown ficarão ativos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Como remover definição de RequireNetworkInOOBE do TenantLockdown no HoloLens 2 usando o Intune?

1. Remova o HoloLens 2 do grupo de dispositivos ao qual a configuração de dispositivos criada acima foi atribuída anteriormente.

1. Crie um perfil de configuração de dispositivo baseado em OMA-URI personalizado e especifique falso para RequireNetworkInOOBE, como mostrado a seguir.
O valor do OMA-URI deve ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de tela da configuração de RequireNetworkInOOBE como falso via OMA-URI no Intune](images/hololens-tenant-lockdown-false.png)

1. Crie um grupo e atribua o perfil de configuração de dispositivo a esse grupo de dispositivos. 

1. Torne o dispositivo HoloLens 2 um membro do grupo criado na etapa anterior e acione a sincronização.

Verifique no portal do Intune se a configuração do dispositivo foi aplicada com sucesso. Depois que essa configuração de dispositivo for aplicada com sucesso ao dispositivo HoloLens 2, os efeitos do TenantLockdown ficarão inativos.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>O que aconteceria durante o OOBE se o perfil do Autopilot não estivesse atribuído em um HoloLens após TenantLockdown ter sido definido como verdadeiro? 
O OOBE aguardaria indefinidamente o download do perfil do Autopilot e a caixa de diálogo a seguir seria apresentada. Para remover os efeitos do TenantLockdown, o dispositivo precisa ser registrado com seu locatário original usando apenas o Autopilot e RequireNetworkInOOBE precisa ter a definição removida, conforme descrito na etapa anterior, antes que as restrições introduzidas pelo CSP TenantLockdown sejam removidas.

![Exibição no dispositivo de quando a política é imposta no dispositivo.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Limitações e problemas conhecidos

- Estamos investigando um problema em que a instalação do aplicativo baseada no contexto do dispositivo configurado no MEM não se aplica ao HoloLens. [Saiba mais sobre as instalações no contexto do dispositivo e no contexto do usuário.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Durante a configuração do Autopilot por Wi-Fi, pode haver uma situação em que o perfil do Autopilot não é baixado quando a conexão com a Internet é estabelecida pela primeira vez. Nesse caso, os Termos de Licença para Software Microsoft são apresentados e o usuário tem a opção de continuar com a experiência de configuração sem o Autopilot. Para tentar configurar com o Autopilot mais uma vez, coloque o dispositivo em suspensão e ligue-o novamente ou reinicie o dispositivo e deixe-o tentar novamente.
- O recurso "Converter todos os dispositivos de destino para o Autopilot" não é compatível com o HoloLens no momento.  

### <a name="troubleshooting"></a>Solução de problemas

Os artigos a seguir podem ser um recurso útil para obter mais informações e solucionar problemas do Autopilot. No entanto, esteja ciente de que esses artigos são baseados no Windows 10 Desktop e nem todas as informações são aplicadas ao HoloLens:

- [Windows Autopilot: problemas conhecidos](/mem/autopilot/known-issues)
- [Solucionar problemas de registro de dispositivo Windows no Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: Conflitos de Política](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Comentários e suporte para o Autopilot

Para fornecer comentários ou relatar problemas, use um dos seguintes métodos:

- Para obter suporte com o registro de dispositivos, entre em contato com seu revendedor ou distribuidor.
- Para consultas gerais de suporte sobre o Windows Autopilot ou para problemas relacionados a atribuições de perfil, criação de grupos ou controles do portal do MEM, entre em contato com o [suporte do Microsoft Endpoint Manager](/mem/get-support)  
- Se o seu dispositivo está registrado no serviço do Autopilot e o perfil está atribuído no portal do MEM, entre em contato com o [suporte](/hololens/) do HoloLens (confira o cartão "Suporte"). Abra um tíquete de suporte e, se aplicável, inclua capturas de tela e logs capturando [logs de diagnóstico offline](hololens-diagnostic-logs.md#offline-diagnostics) durante o OOBE (aplicativo de configuração inicial pelo usuário).
- Para relatar um problema do dispositivo, use o aplicativo Hub de Comentários no HoloLens. No Hub de Comentários, selecione a categoria **Gerenciamento Corporativo** > **Dispositivo**.
- Para fornecer comentários gerais sobre o Autopilot para o HoloLens, envie esta [pesquisa](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Excluir dispositivos Autopilot

Talvez você não queira mais usar um dispositivo para o Autopilot ou queira registrar seus dispositivos em um locatário diferente. Se você quiser fazer isso, leia C[omo excluir dispositivos Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)