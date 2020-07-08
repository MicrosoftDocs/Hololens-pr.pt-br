---
title: Piloto automático do Windows para HoloLens 2
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: piloto automático
manager: jarrettr
ms.openlocfilehash: 9f7306e1e2f190634df7b25833e22b27089d19de
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857779"
---
# Piloto automático do Windows para HoloLens 2

Quando você configura dispositivos do HoloLens 2 para o programa piloto automático do Windows, seus usuários podem seguir um processo simples para provisionar os dispositivos na nuvem.

Esse programa de piloto automático suporta o modo de autoimplantação do piloto automático para provisionar dispositivos HoloLens 2 como dispositivos compartilhados no seu locatário. O modo de autoimplantação aproveita a imagem e os drivers OEM pré-instalados do dispositivo durante o processo de provisionamento. Um usuário pode provisionar o dispositivo sem colocá-lo e passar pela experiência pronta para uso (OOBE).  

![O processo de autoimplantação do piloto automático configura dispositivos compartilhados no modo "sem cabeça" usando uma conexão de rede.](./images/hololens-ap-intro.png)

Quando um usuário iniciar o processo de autoimplantação do piloto automático, o processo concluirá as etapas a seguir:

1. Ingresso do dispositivo no Azure Active Directory (Azure AD)
   > [!NOTE]  
   > O piloto automático do HoloLens não é compatível com o ingresso no Active Directory ou o Azure AD join.
1. Use o Azure AD para registrar o dispositivo no Microsoft Intune (ou outro serviço MDM).
1. Baixe perfis de rede, certificados e aplicativos e políticas direcionados aos dispositivos.
1. Provisione este dispositivo.
1. Apresente a tela de entrada ao usuário.

## Piloto automático do Windows para HoloLens 2: Introdução

As etapas a seguir resumem o processo de configuração do seu ambiente do Piloto automático do Windows para HoloLens 2. O restante desta seção fornece os detalhes dessas etapas.

1. Certifique-se de atender aos requisitos do Piloto automático Windows para HoloLens.
1. Inscreva-se no programa Piloto automático do Windows para o HoloLens 2.
1. Verifique se o seu locatário está em voo (inscrito para participar do programa).
1. Registre dispositivos no Piloto automático do Windows.
1. Crie um grupo de dispositivos.
1. Crie um perfil de implantação.
1. Verifique a configuração ESP.
1. Configure um perfil de configuração personalizado dos dispositivos HoloLens (problema conhecido).
1. Verifique o status do perfil dos dispositivos do HoloLens.

### 1. Certifique-se de que você atende aos requisitos do Piloto Windows para HoloLens
Para obter as informações mais recentes sobre como participar do programa, consulte as [Notas de versão do Windows Insider](hololens-insider.md#windows-insider-release-notes).

Revise as seguintes seções do artigo de requisitos do Piloto automático do Windows:

- [Requisitos de rede](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Requisitos de licenciamento](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Requisitos de configuração](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)
> [!IMPORTANT]  
> Ao contrário de outros programas piloto automático do Windows, o Piloto automático do Windows para o HoloLens 2 possui requisitos específicos do sistema operacional.

Examine a seção ["Requisitos”](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements) do artigo do Artigo do modo Autoimplantação do piloto automático do Windows. Seu ambiente precisa atender a esses requisitos, bem como aos requisitos padrão do Piloto automático do Windows.

> [!NOTE]  
> Você não precisa revisar as seções "Passo a passo" e "Validação" do artigo. Os procedimentos posteriores neste artigo fornecem as etapas correspondentes específicas do HoloLens.

> [!IMPORTANT]  
> Para obter mais informações sobre como registrar dispositivos e configurar perfis, consulte [4. Registrar dispositivos no Piloto automático do Windows](#4-register-devices-in-windows-autopilot) e [6. Crie um perfil de implantação](#6-create-a-deployment-profile) neste artigo. Estas seções fornecem as etapas específicas para o HoloLens.

Antes de iniciar o OOBE e o processo de provisionamento, verifique se os dispositivos HoloLens atendem aos seguintes requisitos:

- Os dispositivos ainda não são membros do Azure AD e não estão registrados no Intune (ou outro sistema MDM). O processo de autoimplantação do Piloto automático conclui essas etapas. Para garantir que todas as informações relacionadas aos dispositivos sejam limpas, verifique as páginas **Dispositivos** no Azure AD e no Intune.
- Todos os dispositivos podem se conectar à Internet. Você pode usar adaptadores "USB C para Ethernet" para conectividade à Internet com fio ou adaptadores "USB C para Wi-Fi" para conectividade à Internet sem fio. 
- Cada dispositivo pode se conectar a um computador usando um cabo USB-C, e esse computador possui o [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) instalado
- Cada dispositivo possui a atualização mais recente do Windows: Windows 10, versão 19041.1002.200107-0909 ou uma versão posterior.

Para configurar e gerenciar os perfis do modo Autoimplantação do Piloto automático, certifique-se de que você possui acesso ao [Centro de administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com).

### 2. Inscreva-se no programa Piloto Automático do Windows para o HoloLens 2.

Para participar do programa, você precisa usar um locatário que seja transportado para o HoloLens. Para fazer isso, vá para a [Solicitação de Piloto automático do Windows para a Visualização privada do HoloLens](https://aka.ms/APHoloLensTAP) ou use o seguinte código QR para enviar uma solicitação.  

![Código QR do piloto automático](./images/hololens-ap-qrcode.png)  

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
  Você deverá visualizar uma lista que inclui **HoloLens**. Se essa opção não estiver presente, use uma das opções de [Comentários](#feedback) para entrar em contato conosco.

### 4. Registre dispositivos no Piloto automático do Windows.

Para registrar um dispositivo HoloLens no programa Piloto automático do Windows, é necessário obter o hash de hardware do dispositivo (também conhecido como ID do hardware). O dispositivo pode registrar seu hash de hardware em um arquivo CSV durante o processo OOBE, ou mais tarde, quando o proprietário do dispositivo iniciar o processo de coleta de logs de diagnóstico (descrito no procedimento a seguir). Geralmente, o proprietário do dispositivo é o primeiro usuário a entrar no dispositivo.

**Recupere um hash de hardware de dispositivo**

1. Inicie o dispositivo do HoloLens 2.
1. No dispositivo, pressione os botões Ligar e Baixar volume e solte-os solte-os. O dispositivo coleta os logs de diagnóstico e o hash do hardware e os armazena em um conjunto de arquivos. zip.
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

Seus usuários HoloLens podem seguir estas etapas para provisionar dispositivos HoloLens.  

1. Use o cabo USB-C para conectar o dispositivo HoloLens a um computador com o Advanced Recovery Companion (ARC) instalado e com a atualização apropriada do Windows baixada.
1. Use o ARC para atualizar a versão apropriada do Windows no dispositivo.
1. Conecte o dispositivo à rede e reinicie o dispositivo.  
   > [!IMPORTANT]  
   > Você deve conectar o dispositivo à rede antes de iniciar a experiência pronta para uso (OOBE). O dispositivo determina se está provisionando como um dispositivo de piloto automático enquanto estiver na primeira telado OOBE. Se o dispositivo não puder se conectar à rede ou se você optar por não provisionar o dispositivo como um dispositivo de piloto automático, não poderá mudar para o provisionamento de piloto automático posteriormente. Em vez disso, você teria que iniciar esse procedimento novamente para provisionar o dispositivo como um dispositivo de piloto automático.

   O dispositivo deve iniciar o OOBE automaticamente. Não interaja com o OOBE. Em vez disso, sente-se e relaxe! Deixe o HoloLens 2 detectar a conectividade de rede e permitir que ele complete o OOBE automaticamente. Talvez o dispositivo reinicie durante o OOBE. As telas OOBE devem ser assim.
   
   ![Etapa 1 do OOBE](./images/hololens-ap-uex-1.png)
   ![Etapa 2 do OOBE](./images/hololens-ap-uex-2.png)
   ![Etapa 3 do OOBE](./images/hololens-ap-uex-3.png)
   ![Etapa 4 do OOBE](./images/hololens-ap-uex-4.png)

No final do OOBE, você pode entrar no dispositivo usando seu nome de usuário e senha.

  ![Etapa 5 do OOBE](./images/hololens-ap-uex-5.png)

## Problemas conhecidos

- Você não pode instalar aplicativos que usam o contexto de segurança do dispositivo.

## Privacidade Jurídica

Para fornecer comentários ou relatar problemas, use um dos seguintes métodos:

- Use o aplicativo Feedback Hub. Você pode encontrar esse aplicativo em um computador conectado ao HoloLens. No Feedback Hub, clique em **Gerenciamento de empresa**  > **Dispositivo**.  

  Ao enviar comentários ou relatar um problema, forneça uma descrição detalhada. Se aplicável, inclua capturas de tela e logs.
- Envie um e-mail para [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com). Para o assunto do e-mail, insira o **\<*Tenant*> comentário da avaliação do Piloto automático do HoloLens 2** (onde \<*Tenant*>é o nome do seu locatário do Intune).

  Forneça uma descrição detalhada na sua mensagem. No entanto, a menos que a Equipe de suporte solicite especificamente, não inclua dados como capturas de tela ou logs. Esses dados podem incluir informações privadas ou de identificação pessoal (PII).
