---
title: Guia de implantação-instalação corporativa do HoloLens 2 com guias do Dynamics 365 – configurar
description: Saiba como configurar as configurações para implantar dispositivos do HoloLens 2 em uma rede conectada corporativa com os guias do Dynamics 365.
keywords: HoloLens, gerenciamento, corporativo conectado, guias do Dynamics 365, AAD, Azure AD, MDM, gerenciamento de dispositivo móvel
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308041"
---
# <a name="configure---corporate-connected-guide"></a>Configurar-guia conectado corporativo

## <a name="azure-users-and-groups"></a>Usuários e grupos do Azure

O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças. Para validar esse fluxo de implantação e ser capaz de verificar se você pode criar e operar um guia, você&#39;precisará de uma conta de usuário.

Podemos criar um único grupo de usuários especificamente para atribuir licenças.

Se você Don&#39;t já tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; Aqui estão os guias de início rápido para:

- [Como criar um usuário](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar usuários a um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – adicionar usuários criados para criar grupo
- [Configurar o Azure ad para permitir que um grupo de usuários ingresse em dispositivos](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Verifique se o novo grupo de usuários tem permissão para registrar dispositivos no Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Registro automático no HoloLens 2

Para ter uma experiência tranqüila e perfeita, configurar Azure Active Directory Join (AADJ) e o registro automático para o Intune para dispositivos do HoloLens 2 é a melhor opção. Isso permite que os usuários insiram suas credenciais de logon da organização durante o OOBE e se registrem automaticamente com o Azure AD e registrem o dispositivo no MDM.

Usando [o Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos selecionar serviços e navegar por algumas páginas até que possamos selecionar obter uma avaliação Premium. Você pode notar que há Azure Active Directory Premium 1 e 2-para o registro automático P1 é suficiente. Podemos selecionar o Intune e selecionar o escopo do usuário para registro automático e selecionar o grupo que foi criado anteriormente.

Para obter detalhes completos e etapas, leia o guia sobre [como habilitar o registro automático para o Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="corporate-wi-fi-connectivity"></a>Conectividade de Wi-Fi corporativa

As conexões corporativas Wi-Fi normalmente exigirão autenticação baseada em certificado para clientes que usam o HoloLens 2. Você precisará implantar esses certificados usando uma infraestrutura de certificado de protocolo SCEP (SCEP) ou padrão de criptografia de chave pública (PKCS) integrada à sua solução de MDM. Usar o Intune para implantar perfis de Wi-Fi, certificados e configurações de proxy cria uma experiência direta para os usuários finais.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Implantar certificados e perfis de Wi-Fi

Para implantar certificados e perfis por meio do Microsoft Endpoint Manager, siga estas etapas:

1. Crie um perfil para cada um dos certificados raiz e intermediários (consulte [criar perfis de certificado confiável](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Cada um desses perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/AAAA. 

    > [!CAUTION]
    > Os **perfis de certificado sem uma data de expiração não serão implantados**.

2.  Criar um perfil para cada certificado SCEP ou PKCS (consulte [criar um perfil de certificado SCEP ou criar um perfil de certificado PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) cada um desses perfis deve ter uma descrição que inclua uma data de expiração no formato dd/mm/aaaa. 

    > [!CAUTION]
    > **Os perfis de certificado sem uma data de expiração não serão implantados.**

    > [!Note]
    > Como o HoloLens 2 é considerado para muitos para ser um dispositivo compartilhado, ou seja, vários usuários por dispositivo, é recomendável implantar certificados de dispositivo em vez de certificados de usuário para autenticação Wi-Fi sempre que possível.

3.  Crie um perfil para sua rede de Wi-Fi corporativa (consulte [configurações de Wi-Fi para dispositivos Windows 10 e posteriores](https://docs.microsoft.com/intune/wi-fi-settings-windows)). Em seu perfil de Wi-Fi, você pode optar por usar as configurações de proxy na sua organização.
 
    Suas opções:
    - **Nenhum**: Nenhuma configuração de proxy está definida.
    - **Configurar manualmente**: insira o **Endereço IP do servidor proxy** e seu **Número de porta**.
    - **Configurar automaticamente**: insira a URL que aponta para um script PAC (configuração automática de proxy). Por exemplo, insira *http://proxy.contoso.com/proxy.pac* .

    Para obter mais informações sobre os arquivos PAC, confira [Arquivo PAC (configuração automática de proxy)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (abre um site que não é da Microsoft).
 
    > [!Note]
    > É recomendável que o perfil de Wi-Fi seja atribuído a grupos de dispositivos em vez de grupos de usuários sempre que possível.
     
    > [!Tip]
    > Você também pode exportar um perfil de Wi-Fi de trabalho de um PC com Windows 10 em sua rede corporativa. Essa exportação cria um arquivo XML com todas as configurações atuais. Em seguida, importe esse arquivo para o Intune e use-o como o perfil de Wi-Fi para seus dispositivos de HoloLens 2. Confira [Exportar e importar configurações de Wi-Fi para dispositivos Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Atribua](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) os perfis de dispositivo ao grupo de dispositivos do HoloLens.

2.  [Monitore](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) os perfis de dispositivo no Intune.

Se houver problemas com perfis de Wi-Fi, consulte [solucionar problemas de Wi-Fi perfis de configuração de dispositivo no Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Solução de problemas de acesso externo à Internet quando Corp conectado
Quando os serviços tentam não passar por um proxy definido, eles podem tentar se conectar por meio do firewall. Você pode adicionar uma lista de especificações de ponto de extremidade às suas regras de firewall para solucionar esses problemas.

Se você estiver bloqueado em portas de firewall, habilite alguns [pontos de extremidade](https://docs.microsoft.com/hololens/hololens-offline) comuns para o HoloLens.

Você também pode habilitar as portas específicas de guias: [URLs acessíveis à Internet necessárias para a conectividade com o Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Implantação de aplicativos

Implantar um aplicativo LOB via MDM é um método que é facilmente escalonável e pode ser implantado automaticamente em seus dispositivos após o registro em um grupo criado.

Se você ainda estiver desenvolvendo seus aplicativos ou ainda não tiver um, poderá usar um aplicativo de exemplo do hub de exemplos do MRTK. Este aplicativo de exemplo está pronto para uso e não exigirá o uso do Unity ou do Visual Studio. [Baixe o aplicativo de exemplo MRTK exemplos](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Se você preferir usar seu próprio aplicativo ou estiver interessado no desenvolvimento de aplicativos para realidade misturada, sinta-se à vontade para revisar nossa [documentação de desenvolvedor de realidade misturada](https://docs.microsoft.com/windows/mixed-reality/design/design).

> [!NOTE]
> Os requisitos de sistema para dispositivos do HoloLens são baseados na arquitetura da compilação do aplicativo. Os dispositivos HoloLens 2 usam a arquitetura ARM. Ao criar seus aplicativos no Visual Studio, verifique se você selecionou a arquitetura correta para o dispositivo e inclui todas as dependências necessárias.

> [!IMPORTANT]
> Ao implantar aplicativos LOB, é importante também carregar o certificado no Intune e atribuí-lo ao mesmo grupo que pretende usar o aplicativo ou ele não será instalado corretamente.

### <a name="upload-and-assign-the-app"></a>Carregar e atribuir o aplicativo

1. Navegue até o [centro de administração do mem](https://endpoint.microsoft.com/#home).

2. Selecione **aplicativos**  ->  **todos os aplicativos** e selecione o botão **+ Adicionar** .

3. Abaixo de outro, selecione **aplicativo de linha de negócios**. Clique em **selecionar**.

4. Selecione o arquivo de pacote do aplicativo, este é o arquivo APPXBUNDLE ou, no nosso caso, o aplicativo é _MRTK examples Hub \_ 2.4.2.0 \_ ARM \_ Master. APPXBUNDLE_.

5. Você será notificado sobre dependências ausentes. Nesse caso, precisamos carregar _Microsoft. VCLibs. ARM. 14.00. Appx_. Pesquise por ele em **selecionar um arquivo**.

6. Selecione OK.

7. Na próxima tela, os campos obrigatórios serão preenchidos automaticamente. Selecione **Avançar**.

8. Em obrigatório, adicione nosso grupo criado anteriormente para tornar este aplicativo necessário para o grupo. Isso fará com que o aplicativo seja baixado automaticamente para dispositivos registrados no grupo. Selecione **Avançar**.

9. Selecione **Criar**.

Leia mais: [atribuir aplicativos a grupos no Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guias de instalação: licenças de aplicativo, dataverso e criação

Para usar os guias do Dynamics 365, você precisará fazer alguma preparação. Há três áreas nas quais precisaremos preparar; usuários, dataverso e os guias em si.

### <a name="users-and-application-licenses"></a>Usuários e licenças de aplicativos

Para que alguém use guias, será necessário usar uma conta do Azure AD, que configuramos anteriormente neste guia.

Você também precisará atribuir a licença de guias do Dynamics 365 ao usuário que você criou. Você fará isso no centro de [Administração do Microsoft 365](https://admin.microsoft.com/AdminPortal/Home). Atribua também a licença à sua conta primária do Azure.

Siga [este breve guia](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) com imagens para obter instruções passo a passo sobre como aplicar licenças de aplicativo.

### <a name="set-up-the-dataverse"></a>Configurar o dataverso

Para [configurar um ambiente de produção](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) , você precisará atender a dois pré-requisitos. Você deve ter a função [**administrador**](https://docs.microsoft.com/power-platform/admin/database-security) do sistema  **e**  deve ter uma [**licença do Power apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (ou uma [**licença de guias do Dynamics 365**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) que inclui uma licença de aplicativos de energia). Se seguir este guia você criou o Azure AD, você atende aos requisitos de função para o administrador do sistema. Também atribuímos uma licença de guias na etapa anterior.

Neste guia para [criar um ambiente do Microsoft dataverso](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two):

1. Comece usando o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/environments) e criando um novo ambiente.
2. Ao criar o **novo ambiente**, para o **tipo** que você&#39;está selecionando **produção**.
3. É importante que você alterne **para criar um banco de dados para este ambiente?**  opção como  **Sim**.
4. Na caixa de diálogo  **Adicionar Banco de dados**  , defina a opção  **habilitar aplicativos Dynamics 365**  como  **Sim.**

Você desejará aumentar o tamanho máximo do arquivo de itens em seu dataverso. Aumentar o tamanho máximo do arquivo permitirá que você carregue modelos 3D maiores ou arquivos de vídeo que serão usados posteriormente em seus guias. Siga um breve guia [para alterar o tamanho máximo do arquivo de carregamento](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).

Por fim, você precisará [instalar e configurar a solução](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). No [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/environments), selecione **recursos** \& gt;  **Aplicativos do dynamics 365**, selecione **guias do Dynamics 365** na lista e, em seguida, selecione **instalar**.  

Você precisa [Adicionar uma função de segurança de guias](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) antes de poder usar os aplicativos.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Criar um guia de teste em seu computador por meio de criação

Ao criar guias, você sempre iniciará em seu computador. Criando as etapas, selecionando modelos e como ancorar o guia. Isso será seguido colocando o conteúdo para seu guia posteriormente no modo de criação em seu dispositivo de HoloLens. Para os fins deste guia, sugerimos fazer um breve guia de teste com as etapas e os modelos mínimos.

Se você quiser começar a aprender sobre a criação de guias, comece aqui com a [visão geral de criação](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview). Ou, para obter uma visão geral de faixa rápida, Assista a este breve vídeo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Opcional: modo de quiosque

O modo de quiosque é um modo que permite que um administrador de ti configure a interface do usuário do menu Iniciar para mostrar apenas um único aplicativo ou seleção de aplicativos. Um quiosque também pode ser aplicado a usuários específicos, grupos ou no nível do dispositivo; e, em alguns casos, excluir determinados usuários do quiosque ainda permitindo o acesso ao menu iniciar normal.

O modo de quiosque tem muitas variáveis diferentes, no escopo e nas configurações que podem ser definidas, bem como métodos de implantação do quiosque no HoloLens. Por causa de todas essas variáveis, o modo de quiosque está sendo deixado como _opcional_ para este guia e não será revisitado. Se você acreditar que tem uma necessidade comercial de restringir os aplicativos disponíveis aos usuários ou gostaria de saber mais, fique à vontade para saber como [Configurar o HoloLens como um quiosque](https://docs.microsoft.com/hololens/hololens-kiosk).

## <a name="optional-wdac"></a>Opcional: WDAC

O WDAC permite que um administrador de ti Configure seus dispositivos para bloquear a inicialização de aplicativos em dispositivos. Isso é diferente dos métodos de restrição de dispositivo, como o modo de quiosque, em que o usuário recebe uma interface de usuário que oculta os aplicativos no dispositivo, mas eles ainda podem ser iniciados. Embora o WDAC seja implementado, os aplicativos ainda estão visíveis na lista todos os aplicativos, mas o WDAC interrompe esses aplicativos e processos de poder ser iniciado pelo usuário do dispositivo.

Para obter mais informações, referência [use WDAC e Windows PowerShell para permitir ou bloquear aplicativos em dispositivos de HoloLens 2 com Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

[Controle de aplicativos do Windows Defender – WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa-implantação](hololens2-corp-connected-deploy.md)