---
title: Guia de Implantação - HoloLens 2 conectado corporativo com Guias do Dynamics 365 - Configurar
description: Saiba como configurar configurações para implantar dispositivos do HoloLens 2 em uma rede conectada corporativa com guias do Dynamics 365.
keywords: HoloLens, gerenciamento, conectado corporativo, Guias do Dynamics 365, AAD, Azure AD, MDM, Gerenciamento de Dispositivo Móvel
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448502"
---
# <a name="configure---corporate-connected-guide"></a>Configurar - Guia Conectado Corporativo

## <a name="azure-users-and-groups"></a>Usuários e grupos do Azure

O Azure e o Intune por essa extensão usam usuários e grupos para ajudar a atribuir configurações e licenças. Para validar esse fluxo de implantação e verificar se você pode ser autor e operar um guia, você&#39;precisará de uma conta de usuário.

Podemos fazer um único grupo de usuários especificamente para atribuir licenças.

Se você não&#39;já tem acesso a duas contas do Azure AD em um grupo de usuários, você pode usar; aqui estão as guias de início rápido para:

- [Como criar um usuário](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Como criar um grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Adicionar usuários a um grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Adicionar usuários criados para criar grupo
- [Configurar o Azure AD](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) para permitir que um Grupo de Usuários inscreva dispositivos – Verifique se o novo grupo de usuários tem permissão para registrar dispositivos no Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Registro Automático no HoloLens 2

Para ter uma experiência suave e perfeita, configurar o AADJ (AADJ) e o Registro Automático no Intune para dispositivos HoloLens 2 é a melhor opção. Isso permite que os usuários inscrevem suas credenciais de login da organização durante o OOBE e registrem-se automaticamente no Azure AD e registrem o dispositivo no MDM.

Usando o [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos selecionar serviços e navegar por algumas páginas até que possamos selecionar Obter uma avaliação Premium. Você pode observar que há o Azure Active Directory Premium 1 e 2 - para o Registro Automático P1 é suficiente. Podemos selecionar o Intune e selecionar o escopo do usuário para registro automático e selecionar o grupo criado anteriormente.

Para obter detalhes completos e etapas, leia o guia [sobre como habilitar o registro automático para o Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="corporate-wi-fi-connectivity"></a>Conectividade Wi-Fi corporativa

Conexões Wi-Fi corporativas normalmente exigem autenticação baseada em certificado para clientes que usam o HoloLens 2. Você precisará implantar esses certificados usando uma infraestrutura de certificado SCEP (Simple Certificate Enrollment Protocol) ou PKCS (Public Key Cryptography Standard) integrada à sua solução MDM. Usar o Intune para implantar Wi-Fi perfis, certificados e configurações de proxy cria uma experiência perfeita para usuários finais.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Implantar certificados e Wi-Fi perfis

Para implantar certificados e perfis por meio do Microsoft Endpoint Manager, siga estas etapas:

1. Crie um perfil para cada um dos certificados Raiz e Intermediário (consulte [Criar perfis de certificado confiáveis](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Cada um desses perfis deve ter uma descrição que inclua uma data de expiração no formato DD/MM/YYYY. 

    > [!CAUTION]
    > **Os perfis de certificado sem uma data de expiração não serão implantados.**

2.  Crie um perfil para cada certificado SCEP ou PKCS (consulte [Criar um perfil de certificado SCEP ou Criar um perfil de certificado PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Cada um desses perfis deve ter uma descrição que inclui uma data de vencimento no formato DD/MM/AAAA. 

    > [!CAUTION]
    > **Os perfis de certificado sem uma data de vencimento não serão implantados.**

    > [!Note]
    > Como o HoloLens 2 é considerado para muitos como um dispositivo compartilhado, ou seja, vários usuários por dispositivo, é recomendável implantar certificados de dispositivo em vez de certificados de usuário para autenticação Wi-Fi quando possível.

3.  Crie um perfil para sua rede corporativa Wi-Fi (consulte [Configurações de Wi-Fi para Windows 10 e dispositivos posteriores](https://docs.microsoft.com/intune/wi-fi-settings-windows)). No seu Wi-Fi, você pode selecionar para usar as configurações de proxy em sua organização.
 
    Suas opções:
    - **Nenhum**: nenhuma configuração de proxy está configurada.
    - **Configurar manualmente**: insira o endereço IP do **servidor Proxy e** seu número de **porta**.
    - **Configurar automaticamente**: insira a URL apontando para um script pac (configuração automática de proxy). Por exemplo, digite *http://proxy.contoso.com/proxy.pac* .

    Para obter mais informações sobre arquivos PAC, consulte [Arquivo PAC (Configuração Automática de Proxy) (abre](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) um site que não seja da Microsoft).
 
    > [!Note]
    > É recomendável que o perfil Wi-Fi seja atribuído aos Grupos de dispositivos, em vez de Grupos de usuários, quando possível.
     
    > [!Tip]
    > Você também pode exportar um perfil de Wi-Fi de trabalho de um computador com Windows 10 em sua rede corporativa. Essa exportação cria um arquivo XML com todas as configurações atuais. Em seguida, importe esse arquivo para o Intune e o use como perfil de Wi-Fi para seus dispositivos do HoloLens 2. Consulte [Exportar e importar Wi-Fi configurações para dispositivos Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

1.  [Atribua](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) os perfis de dispositivo ao grupo de dispositivos HoloLens.

2.  [Monitore](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) os perfis de dispositivo no Intune.

Se houver problemas com perfis Wi-Fi, referência [Solucionar problemas Wi-Fi de configuração do dispositivo no Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Solução de problemas de acesso externo à Internet quando a Corp está conectada
Quando os serviços tentam não passar por um Proxy definido, eles podem tentar se conectar por meio do firewall. Você pode adicionar uma lista de detalhes do ponto de extremidade às regras de firewall para solucionar esses problemas.

Se você estiver bloqueado em portas de firewall, habilita alguns pontos de [extremidade comuns](https://docs.microsoft.com/hololens/hololens-offline) para o HoloLens.

Você também pode habilitar as portas específicas guias: [URLs](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)acessíveis à Internet necessárias para conectividade com Microsoft Dynamics CRM Online .

## <a name="app-deployment"></a>Implantação de aplicativo

Implantar um aplicativo LOB via MDM é um método facilmente escalonável e pode ser implantado automaticamente em seus dispositivos ao se inscrever em um grupo criado.

Se você ainda estiver desenvolvendo seus Aplicativos ou ainda não tiver um, poderá usar um aplicativo de exemplo do hub de exemplos MRTK. Este aplicativo de exemplo está pronto para uso e não exigirá o uso do Unity ou Visual Studio. [Baixe o aplicativo exemplo de exemplo mrtk](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Se você preferir usar seu próprio aplicativo ou estiver interessado no desenvolvimento de aplicativos para a Realidade Mista, esteja à vontade para revisar nossa documentação de desenvolvedor [de Realidade Mista.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> Os Requisitos do Sistema para dispositivos HoloLens são baseados na arquitetura da compilação do aplicativo. Os dispositivos HoloLens 2 usam ARM arquitetura. Ao criar seus aplicativos Visual Studio, verifique se você selecionou a arquitetura correta para o dispositivo e inclua as dependências necessárias.

> [!IMPORTANT]
> Ao implantar aplicativos LOB, é importante também carregar o certificado no Intune e atribuí-lo ao mesmo grupo que se destina a usar o aplicativo ou ele não será instalado corretamente.

### <a name="upload-and-assign-the-app"></a>Carregar e atribuir o aplicativo

1. Navegue até o [centro de administração do MEM.](https://endpoint.microsoft.com/#home)

2. Selecione ****  ->  **Aplicativos Todos os aplicativos** e selecione **o botão + Adicionar.**

3. Abaixo de Outro, selecione Aplicativo de Linha **de Negócios**. Clique **em selecionar**.

4. Selecione o arquivo de pacote do aplicativo, este é o arquivo APPXBUNDLE ou, no nosso caso deste exemplo, o aplicativo é Hub de _Exemplos MRTK\_2.4.2.0\_arm\_Master.appxbundle_.

5. Você será notificado sobre dependências ausentes. Nesse caso, precisamos carregar _Microsoft.VCLibs.ARM.14.00.appx_. Pesquise em **Selecionar um arquivo**.

6. Selecione OK.

7. Na próxima tela, os campos necessários serão preenchidos automaticamente. Selecione **Avançar**.

8. Em Obrigatório, adicione nosso grupo criado anteriormente para tornar esse aplicativo necessário para o grupo. Isso fará com que o aplicativo baixe automaticamente para dispositivos inscritos no grupo. Selecione **Avançar**.

9. Selecione **Criar**.

Leia mais: [Atribuir aplicativos a grupos no Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guias de Instalação: Licenças de aplicativo, dataverso e autoria

Para usar os Guias do Dynamics 365, você precisará se preparar. Há três áreas nas quais precisamos nos preparar; usuários, dadosversos e guias por conta própria.

### <a name="users-and-application-licenses"></a>Usuários e licenças de aplicativo

Para alguém usar Guias, ele precisará usar uma conta do Azure AD, que configuramos neste guia anteriormente.

Você também precisará atribuir a licença de Guias do Dynamics 365 ao usuário que você criou. Você fará isso no Centro de administração [do Microsoft 365.](https://admin.microsoft.com/AdminPortal/Home) Atribua também a licença à sua conta principal do Azure.

Siga [este guia curto](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) com imagens para obter instruções passo a passo sobre como aplicar licenças de aplicativo.

### <a name="set-up-the-dataverse"></a>Configurar o Dataverse

Para configurar [um ambiente de produção,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) você precisará atender a dois pré-requisitos. Você deve [****](https://docs.microsoft.com/power-platform/admin/database-security) ter a função Administrador do Sistema **e** ter uma licença do [**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (ou uma licença de Guias do [**Dynamics 365**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) que inclui uma licença do Power Apps). Se seguir este guia você criou o Azure AD, então atenderá aos requisitos de função para o Administrador do Sistema. Também atribuimos uma Licença de Guias na etapa anterior.

Neste guia para [criar um ambiente do Microsoft Dataverse](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two):

1. Comece usando o centro de administração [da Plataforma Power](https://admin.powerplatform.microsoft.com/environments) e criando um Novo Ambiente.
2. Ao criar o **Novo Ambiente**, para **o tipo** que você&#39;**selecionará Produção**.
3. É importante alternar Criar um banco de **dados para esse ambiente?**  para  **Sim**.
4. Na caixa  **de diálogo Adicionar banco**  de dados, de definir a opção Habilitar  **aplicativos do Dynamics 365**  como  **Sim.**

Você vai querer aumentar o tamanho máximo de arquivo de itens no seu dataverse. Aumentar o tamanho máximo do arquivo permitirá carregar modelos 3D maiores ou arquivos de vídeo que você usará posteriormente em suas guias. Siga um guia curto [para alterar o tamanho máximo do arquivo de carregamento.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Por fim, você precisará instalar [e configurar a solução](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). No Centro de administração [da Plataforma](https://admin.powerplatform.microsoft.com/environments)Power, selecione **Recursos**   \ &gt; **Aplicativos do Dynamics 365**, selecione Guias do **Dynamics 365** na lista e selecione **Instalar**.  

Você precisa [adicionar uma função de segurança guias](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) antes de poder usar os aplicativos.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Criar um guia de teste em seu computador por meio da criação

Ao criar Guias, você sempre iniciará em seu computador. Criando as etapas, selecionando modelos e como ancorar o guia. Isso será seguido pela colocação de conteúdo para seu guia posteriormente no modo de criação em seu dispositivo HoloLens. Para os fins deste guia, sugerimos fazer um guia de teste curto com etapas e modelos mínimos.

Se você quiser começar a aprender sobre a autoria de Guias, comece aqui com a visão [geral de autoria.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) Ou para obter uma visão geral de controle rápido, assista a este vídeo curto.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Opcional: modo quiosque

O modo de quiosque é um modo que permite que um administrador de IT configure a interface do usuário do menu inicial para mostrar apenas um único aplicativo ou seleção de aplicativos. Um quiosque também pode ser aplicado a usuários específicos, grupos ou no nível do dispositivo; e, em alguns casos, exclua determinados usuários do Quiosque ainda permitindo que eles acessem o menu inicial regular.

O modo quiosque tem muitas variáveis diferentes, tanto no escopo quanto em configurações que podem ser definidas, bem como métodos de implantação do Quiosque no HoloLens. Devido a todas essas variáveis, o __ modo Quiosque está sendo deixado como opcional para este guia e não será revisitado. Se você acredita que tem uma necessidade comercial de restringir aplicativos disponíveis aos usuários ou gostaria de saber mais, sinta-se à vontade para aprender a configurar [o HoloLens como um quiosque](https://docs.microsoft.com/hololens/hololens-kiosk).

## <a name="optional-wdac"></a>Opcional: WDAC

O WDAC permite que um administrador de IT configure seus dispositivos para bloquear o lançamento de aplicativos em dispositivos. Isso é diferente dos métodos de restrição de dispositivo, como o modo Quiosque, em que o usuário é apresentado a uma interface do usuário que oculta os aplicativos no dispositivo, mas eles ainda podem ser lançados. Embora o WDAC seja implementado, os aplicativos ainda estão visíveis na lista Todos os Aplicativos, mas o WDAC impede que esses aplicativos e processos sejam abertos pelo usuário do dispositivo.

Para obter mais informações, referência Use wdac e Windows PowerShell para permitir ou bloquear aplicativos em [dispositivos HoloLens 2 com o Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

[Controle de Aplicativos do Windows Defender - WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Próximas etapas 
> [!div class="nextstepaction"]
> [Implantação conectada corporativa - Implantar](hololens2-corp-connected-deploy.md)