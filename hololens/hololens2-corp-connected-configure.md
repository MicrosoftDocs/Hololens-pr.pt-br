---
title: guia de implantação-corporativo conectado HoloLens 2 com guias do Dynamics 365 – configurar
description: saiba como configurar as configurações para implantar dispositivos HoloLens 2 em uma rede conectada corporativa com os guias do Dynamics 365.
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126031985"
---
# <a name="configure---corporate-connected-guide"></a>Configurar-guia conectado corporativo

## <a name="azure-users-and-groups"></a>Usuários e grupos do Azure

O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças. Para validar esse fluxo de implantação e ser capaz de verificar se você pode criar e operar um guia, você&#39;precisará de uma conta de usuário.

Podemos criar um único grupo de usuários especificamente para atribuir licenças.

Se você Don&#39;t já tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; Aqui estão os guias de início rápido para:

- [Como criar um usuário](/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar usuários a um grupo](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – adicionar usuários criados para criar grupo
- [Configurar o Azure ad para permitir que um grupo de usuários ingresse em dispositivos](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Verifique se o novo grupo de usuários tem permissão para registrar dispositivos no Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>registro automático no HoloLens 2

para ter uma experiência tranqüila e perfeita, configurar Azure Active Directory Join (AADJ) e o registro automático para o Intune para dispositivos HoloLens 2 é a melhor opção. Isso permite que os usuários insiram suas credenciais de logon da organização durante o OOBE e se registrem automaticamente com o Azure AD e registrem o dispositivo no MDM.

usando [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos selecionar serviços e navegar por algumas páginas até que possamos selecionar obter uma avaliação de Premium. você pode notar que há Azure Active Directory Premium 1 e 2-para o registro automático P1 é suficiente. Podemos selecionar o Intune e selecionar o escopo do usuário para registro automático e selecionar o grupo que foi criado anteriormente.

Para obter detalhes completos e etapas, leia o guia sobre [como habilitar o registro automático para o Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="corporate-wi-fi-connectivity"></a>Conectividade de Wi-Fi corporativa

as conexões corporativas Wi-Fi normalmente exigirão autenticação baseada em certificado para clientes que usam HoloLens 2. Você precisará implantar esses certificados usando uma infraestrutura de certificado de protocolo SCEP (SCEP) ou padrão de criptografia de chave pública (PKCS) integrada à sua solução de MDM. Usar o Intune para implantar perfis de Wi-Fi, certificados e configurações de proxy cria uma experiência direta para os usuários finais.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Implantar certificados e perfis de Wi-Fi

para implantar certificados e perfis por meio de Microsoft Endpoint Manager, siga estas etapas:

1. Crie um perfil para cada um dos certificados raiz e intermediários (consulte [criar perfis de certificado confiável](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Cada um desses perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/AAAA.

    > [!CAUTION]
    > Os **perfis de certificado sem uma data de expiração não serão implantados**.

2. Crie um perfil para cada certificado SCEP ou PKCS (confira [Criar um perfil de certificado SCEP ou Criar um perfil de certificado PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Cada um desses perfis deve ter uma descrição que inclua uma data de validade no formato DD/MM/AAAA.

    > [!CAUTION]
    > **Perfis de certificado sem uma data de validade não serão implantados.**

    > [!Note]
    > como o HoloLens 2 é considerado para muitos para ser um dispositivo compartilhado, ou seja, vários usuários por dispositivo, é recomendável implantar certificados de dispositivo em vez de certificados de usuário para autenticação Wi-Fi sempre que possível.

3. crie um perfil para sua rede de Wi-Fi corporativa (consulte [configurações de Wi-Fi para Windows 10 e dispositivos posteriores](/intune/wi-fi-settings-windows)). Em seu perfil de Wi-Fi, você pode optar por usar as configurações de proxy na sua organização.

    Suas opções:
    - **Nenhum**: Nenhuma configuração de proxy está definida.
    - **Configurar manualmente**: insira o **Endereço IP do servidor proxy** e seu **Número de porta**.
    - **Configurar automaticamente**: insira a URL que aponta para um script PAC (configuração automática de proxy). Por exemplo, insira *http://proxy.contoso.com/proxy.pac* .

    Para obter mais informações sobre os arquivos PAC, confira [Arquivo PAC (configuração automática de proxy)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (abre um site que não é da Microsoft).
 
    > [!Note]
    > É recomendável que o perfil de Wi-Fi seja atribuído a Grupos de dispositivos em vez de Grupos de usuários quando possível.
     
    > [!Tip]
    > Você também pode exportar um perfil de Wi-Fi em funcionamento em um computador com Windows 10 em sua rede corporativa. Essa exportação cria um arquivo XML com todas as configurações atuais. Em seguida, importe esse arquivo para o Intune e use-o como perfil de Wi-Fi para os dispositivos HoloLens 2. Confira [Exportar e importar configurações de Wi-Fi para dispositivos Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [atribua](/mem/intune/configuration/device-profile-assign) os perfis de dispositivo ao grupo de dispositivos HoloLens.

2.  [Monitore](/mem/intune/configuration/device-profile-monitor) os perfis de dispositivo no Intune.

Se houver problemas com perfis de Wi-Fi, consulte [solucionar problemas de Wi-Fi perfis de configuração de dispositivo no Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Solução de problemas de acesso externo à Internet quando Corp conectado
Quando os serviços tentam não passar por um proxy definido, eles podem tentar se conectar por meio do firewall. Você pode adicionar uma lista de especificações de ponto de extremidade às suas regras de firewall para solucionar esses problemas.

Se você estiver bloqueado em portas de firewall, habilite alguns [pontos de extremidade](/hololens/hololens-offline) comuns para HoloLens.

Você também pode habilitar as portas específicas dos guias: [URLs acessíveis à Internet necessárias para conectividade com Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Implantação de aplicativos

Implantar um aplicativo LOB via MDM é um método que é facilmente escalonável e pode ser implantado automaticamente em seus dispositivos após o registro em um grupo criado.

Se você ainda estiver desenvolvendo seus aplicativos ou ainda não tiver um, poderá usar um aplicativo de exemplo do hub de exemplos do MRTK. Este aplicativo de exemplo está pronto para uso e não exigirá o uso de Unity ou Visual Studio. [Baixe o aplicativo de exemplo MRTK exemplos](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Se você preferir usar seu próprio aplicativo ou estiver interessado no desenvolvimento de aplicativos para realidade misturada, sinta-se à vontade para revisar nossa [documentação de desenvolvedor de realidade misturada](/windows/mixed-reality/design/design).

> [!NOTE]
> Os requisitos do sistema para dispositivos HoloLens são baseados na arquitetura do build do aplicativo. HoloLens 2 dispositivos usam a arquitetura ARM. ao criar seus aplicativos no Visual Studio, verifique se você selecionou a arquitetura correta para o dispositivo e inclui todas as dependências necessárias.

> [!IMPORTANT]
> Ao implantar aplicativos LOB, é importante também carregar o certificado no Intune e atribuí-lo ao mesmo grupo que pretende usar o aplicativo ou ele não será instalado corretamente.

### <a name="upload-and-assign-the-app"></a>Upload e atribuir o aplicativo

1. Navegue até o [centro de administração do mem](https://endpoint.microsoft.com/#home).

2. Selecione **aplicativos**  ->  **todos os aplicativos** e selecione o botão **+ Adicionar** .

3. Abaixo de outro, selecione **aplicativo de linha de negócios**. Clique em **selecionar**.

4. Selecione o arquivo de pacote do aplicativo, este é o arquivo APPXBUNDLE ou, no nosso caso, o aplicativo é _MRTK examples Hub \_ 2.4.2.0 \_ ARM \_ Master. APPXBUNDLE_.

5. Você será notificado sobre dependências ausentes. Nesse caso, precisamos carregar _Microsoft. VCLibs. ARM. 14.00. Appx_. Pesquise por ele em **selecionar um arquivo**.

6. Selecione OK.

7. Na próxima tela, os campos obrigatórios serão preenchidos automaticamente. Selecione **Avançar**.

8. Em obrigatório, adicione nosso grupo criado anteriormente para tornar este aplicativo necessário para o grupo. Isso fará com que o aplicativo seja baixado automaticamente para dispositivos registrados no grupo. Selecione **Avançar**.

9. Selecione **Criar**.

Leia mais: [atribuir aplicativos a grupos no Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guias de instalação: licenças de aplicativo, dataverso e criação

Para usar os guias do Dynamics 365, você precisará fazer alguma preparação. Há três áreas nas quais precisaremos preparar; usuários, dataverso e os guias em si.

### <a name="users-and-application-licenses"></a>Usuários e licenças de aplicativos

Para que alguém use guias, será necessário usar uma conta do Azure AD, que configuramos anteriormente neste guia.

Você também precisará atribuir a licença de guias do Dynamics 365 ao usuário que você criou. você fará isso na [Centro de administração do Microsoft 365](https://admin.microsoft.com/AdminPortal/Home). Atribua também a licença à sua conta primária do Azure.

Siga [este breve guia](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) com imagens para obter instruções passo a passo sobre como aplicar licenças de aplicativo.

### <a name="set-up-the-dataverse"></a>Configurar o dataverso

Para [configurar um ambiente de produção](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) , você precisará atender a dois pré-requisitos. você deve ter a função [**administrador**](/power-platform/admin/database-security) do sistema **e** deve ter uma [**licença Power Apps**](/power-platform/admin/signup-question-and-answer) (ou uma [**licença de guias do Dynamics 365**](/dynamics365/mixed-reality/guides/setup-step-one) que inclui uma licença Power Apps). Se seguir este guia você criou o Azure AD, você atende aos requisitos de função para o administrador do sistema. Também atribuímos uma licença de guias na etapa anterior.

Neste guia para [criar um ambiente do Microsoft dataverso](/dynamics365/mixed-reality/guides/setup-step-two):

1. Comece usando o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/environments) e criando um novo ambiente.
2. Ao criar o **novo ambiente**, para o **tipo** que você&#39;está selecionando **produção**.
3. É importante que você alterne **para criar um banco de dados para este ambiente?**  opção como  **Sim**.
4. Na caixa de diálogo  **Adicionar Banco de dados**  , defina a opção  **habilitar aplicativos Dynamics 365**  como  **Sim.**

Você deseja aumentar o tamanho máximo de arquivo de itens no seu dataverso. Aumentar o tamanho máximo do arquivo permitirá carregar modelos 3D maiores ou arquivos de vídeo que você usará posteriormente em seus guias. Siga um guia curto para [alterar o tamanho máximo do arquivo de upload.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Por fim, você precisará instalar [e configurar a solução](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). No [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/environments), selecione **Recursos** \& gt;  **Aplicativos do Dynamics 365,** selecione Guias do **Dynamics 365** na lista e, em seguida, **selecione Instalar**.  

Você precisa [adicionar uma função de segurança guias](/dynamics365/mixed-reality/guides/assign-role) antes de poder usar os aplicativos.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Criar um guia de teste em seu computador por meio da criação

Ao criar Guias, você sempre iniciará em seu computador. Criando as etapas, selecionando modelos e como ancorar o guia. Isso será seguido pela colocação do conteúdo do guia posteriormente no modo de HoloLens dispositivo. Para os fins deste guia, sugerimos criar um guia de teste curto com etapas e modelos mínimos.

Se você quiser começar a aprender sobre a adoção de Guias, comece aqui com a visão [geral de autor.](/dynamics365/mixed-reality/guides/authoring-overview) Ou para obter uma visão geral do fast track, assista a este breve vídeo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Opcional: modo de quiosque

O modo de quiosque é um modo que permite que um administrador de IT configure a interface do usuário do menu Iniciar para mostrar apenas um único aplicativo ou seleção de aplicativos. Um quiosque também pode ser aplicado a usuários, grupos ou no nível do dispositivo específicos; e, em alguns casos, exclua determinados usuários do Quiosque ainda permitindo que eles acessem o menu iniciar normal.

O modo de quiosque tem muitas variáveis diferentes, tanto no escopo quanto nas configurações que podem ser definidas, bem como métodos de implantação do Quiosque no HoloLens. Devido a todas essas variáveis, o  modo de quiosque está sendo deixado como opcional para este guia e não será revisitado. Se você acredita que tem uma necessidade comercial de restringir aplicativos disponíveis aos usuários ou gostaria de saber mais, sinta-se à vontade para saber como configurar o HoloLens como um [quiosque](/hololens/hololens-kiosk).

## <a name="optional-wdac"></a>Opcional: WDAC

O WDAC permite que um administrador de IT configure seus dispositivos para bloquear o lançamento de aplicativos em dispositivos. Isso é diferente dos métodos de restrição de dispositivo, como o modo de quiosque, em que o usuário recebe uma interface do usuário que oculta os aplicativos no dispositivo, mas ainda pode ser lançado. Embora o WDAC seja implementado, os aplicativos ainda estão visíveis na lista Todos os Aplicativos, mas o WDAC impede que esses aplicativos e processos sejam lançados pelo usuário do dispositivo.

Para obter mais informações, consulte [Usar WDAC e Windows PowerShell para](/mem/intune/configuration/custom-profile-hololens)permitir ou bloquear aplicativos em HoloLens 2 dispositivos com Microsoft Intune .

[WDAC (Controle de Aplicativos do Windows Defender)](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Próxima etapa 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa – Implantar](hololens2-corp-connected-deploy.md)