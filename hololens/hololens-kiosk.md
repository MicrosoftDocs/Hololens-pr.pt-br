---
title: Configurar o HoloLens como um quiosque
description: Saiba como configurar e usar uma configuração de quiosque para bloquear os aplicativos em HoloLens dispositivos.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e8f269a3793a5e61eb3eb4b88084a5e4af375ffa
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351712"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurar o HoloLens como um quiosque

## <a name="what-is-kiosk-mode"></a>O que é o modo quiosque?

O modo de quiosque é um recurso em que você pode controlar quais aplicativos são mostrados no menu Iniciar quando um usuário faz a HoloLens. Há dois cenários com suporte:

1. **Modo de quiosque de aplicativo único** – nenhum menu iniciar é exibido e um único aplicativo é lançado automaticamente quando o usuário se ins signa. <br> *O exemplo usa*: um dispositivo que executa apenas o aplicativo Dynamics 365 Guides.
2. **Modo de quiosque de** vários aplicativos – menu Iniciar mostra apenas os aplicativos, que foram especificados na configuração de quiosque quando um usuário se ins signa. Um aplicativo pode ser escolhido para iniciar automaticamente, se desejado. <br> *O exemplo usa*: um dispositivo que mostra apenas o aplicativo da Store, o Hub de Comentários e Configurações aplicativo no menu Iniciar.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Descrição da experiência do modo de quiosque quando um usuário entrar

A tabela a seguir lista os recursos nos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu Ações Rápidas |Câmera e vídeo |Miracast |Cortana |Comandos de voz internos |
| --- | --- | --- | --- | --- | --- | --- |
|Quiosque de aplicativo único |Desabilitado |Desabilitado |Desabilitado |Desabilitado   |Desabilitado |Habilitado* |
|Quiosques de vários aplicativos |habilitado |Habilitado*  |Disponível*  |Disponível* |Disponível*   |Habilitado*  |

\*Para obter mais informações sobre como habilitar recursos desabilitados ou como os comandos de voz interagem com recursos desabilitados e Cortana consulte [HoloLens AUMIDs para aplicativos](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids).

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Principais considerações gerais antes de configurar o modo de quiosque

1. Determine o tipo de conta de usuário que entra no HoloLens em seu ambiente – o HoloLens dá suporte a contas Azure Active Directory (AAD), MSA (Contas da Microsoft) e Contas Locais. Além disso, também há suporte para contas criadas temporariamente chamadas convidados/visitantes (somente para dispositivos AAD de junção). Saiba mais em [Gerenciar a identidade do usuário e entrar no HoloLens](hololens-identity.md).
2. Determinar os destinos da experiência de modo de quiosque – seja todos, um único usuário, determinados usuários ou usuários que são membros de grupos de AAD, etc.
3. Para o modo de quiosque de vários aplicativos, determine os aplicativos a mostrar no menu Iniciar. Para cada aplicativo, sua [AUMID (ID](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) do Modelo de Usuário do Aplicativo) será necessária.
4. Determine se o modo de quiosque será aplicado ao HoloLens por meio de pacotes de provisionamento de runtime ou servidor MDM (mobile Gerenciamento de Dispositivos).

## <a name="security-considerations"></a>Considerações de segurança

O modo de quiosque não deve ser considerado como um método de segurança, mas como um meio de controlar a experiência de início na logon do usuário. Você pode combinar a experiência de modo de quiosque com as opções mencionadas abaixo se houver necessidades específicas relacionadas à segurança:

- Quando Configurações aplicativo estiver configurado para ser mostrado no modo de quiosque e você quiser controlar quais páginas são mostradas no aplicativo Configurações, consulte Visibilidade de Configurações [página](settings-uri-list.md)
- Quando você quiser controlar o acesso a determinados recursos de hardware, por exemplo, câmera, Bluetooth etc. para determinados aplicativos etc., consulte Políticas no CSP de Política com suporte do [HoloLens 2 – Windows Gerenciamento](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)de Clientes do . Você pode revisar nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md) para ideias.
- O modo de quiosque não bloqueia um aplicativo (configurado como parte da experiência de quiosque) de iniciar outros aplicativos. Quando você quiser bloquear completamente a iniciação de determinados aplicativos/processos no HoloLens, consulte Usar o controle de aplicativo Windows Defender em dispositivos HoloLens 2 no [Microsoft Intune – Azure](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Principais considerações técnicas para o modo de quiosque para HoloLens

Aplica-se somente se você estiver planejando usar pacotes de provisionamento de runtime ou criar configurações de quiosque manualmente por conta própria. A configuração do modo de quiosque usa uma estrutura hierárquica baseada em XML:

- Um perfil de acesso atribuído define quais aplicativos são exibidos no menu Iniciar no modo de quiosque. Você pode definir vários perfis na mesma estrutura XML, que pode ser referenciada posteriormente.
- Uma configuração de acesso atribuído faz referência a um perfil e usuários de destino desse perfil, por exemplo, um usuário específico ou AAD grupo ou visitante etc. Você pode definir várias configurações na mesma estrutura XML dependendo da complexidade de seus cenários de uso (consulte a seção cenários com suporte abaixo).
- Para saber mais, consulte [AssignedAccess CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Cenários com suporte para o modo de quiosque com base no tipo de identidade

Consulte [links de referência](hololens-kiosk-reference.md#kiosk-xml-code-samples) para ver exemplos com base em seu cenário e atualize conforme necessário antes da cópia de colar.

> [!NOTE]
> Use XML somente se não estiver usando a interface do usuário do Intune para criar a configuração de quiosque.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Para usuários que se ins sign-in como conta local ou MSA

| **Experiência de quiosque desejada** | **Configuração de quiosque recomendada** | **Maneiras de configurar**  | **Comentários** |
| --- | --- | --- | --- |
| Cada usuário que entra obtém a experiência de quiosque. | [Configurar o perfil de acesso atribuído global a vários aplicativos](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento em runtime – Vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | O acesso atribuído global requer [builds 20H2 e mais novos](hololens-release-notes.md#windows-holographic-version-20h2) |
| Usuário específico que entra obtém a experiência de quiosque.  | [Configure o perfil de acesso atribuído a um ou vários aplicativos (conforme necessário) especificando o nome de um usuário específico.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Confira as opções com suporte abaixo.](#steps-in-configuring-kiosk-mode-for-hololens) | Para o modo de quiosque de aplicativo único, somente a conta de usuário local ou a conta MSA tem suporte HoloLens. <br> Para o modo de quiosque de vários aplicativos, somente a conta MSA ou AAD conta tem suporte no HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Para usuários que se ins sign-in como AAD conta

| **Experiência de quiosque desejada** | **Configuração de quiosque recomendada** | **Maneiras de configurar** | **Comentários** |
| --- | --- | --- | --- |
| Cada usuário que entra obtém a experiência de quiosque. | [Configurar o perfil de acesso atribuído global a vários aplicativos](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento em runtime – Vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | O acesso atribuído global requer [builds 20H2 e mais novos](hololens-release-notes.md#windows-holographic-version-20h2) |
| Cada usuário que entra obtém a experiência de quiosque, exceto determinados usuários. | [Configure o perfil de Acesso Atribuído Global de vários aplicativos excluindo determinados usuários (que devem ser proprietários do dispositivo).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento em runtime – Vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | O acesso atribuído global requer [builds 20H2 e mais novos](hololens-release-notes.md#windows-holographic-version-20h2) |
| Cada AAD usuário obtém uma experiência de quiosque separada específica para esse usuário. | [Configure a configuração de acesso atribuído para cada usuário especificando seu nome AAD conta.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento em runtime – Vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Os usuários em grupos AAD diferentes experimentam o modo de quiosque que é apenas para seu grupo. | [Configure a configuração de acesso atribuído para cada grupo AAD desejado.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento em runtime – Vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Quando um usuário entra e HoloLens está conectado com a Internet, se esse usuário for considerado um membro de um grupo de AAD para o qual a configuração de quiosque existe, o usuário poderá experimentar o quiosque para esse AAD grupo. <br> • Se não houver nenhuma Internet disponível quando o usuário entrar, o usuário terá HoloLens de [modo de falha.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Se a disponibilidade da Internet não for garantida quando o usuário entrar e AAD quiosque baseado em grupo precisar ser usado, considere usar [AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). <br> • Para obter uma experiência ideal com AAD grupos durante a login, a recomendação é usar [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| Os usuários que precisam usar o HoloLens para fins temporários têm experiência de quiosque. | [Configurar a configuração de acesso atribuído para visitantes](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento em runtime – aplicativo único](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • A conta de usuário temporária é criada automaticamente HoloLens ao entrar e é removida quando o usuário temporário sai. <br> • Considere [habilenciar a política de logon automático do visitante.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Etapas na configuração do modo de quiosque para HoloLens

As configurações de quiosque podem ser criadas e aplicadas das seguintes maneiras:

1. Com a interface do usuário do servidor MDM, por exemplo, os modelos de quiosque do Intune ou as configurações de OMA-URI personalizadas, que são aplicadas remotamente ao HoloLens.
2. Com pacotes de provisionamento de runtime, que são aplicados diretamente ao HoloLens.

Aqui estão as seguintes maneiras de configurar, selecione a guia correspondente ao processo que você gostaria de usar.

1. [Modelo de quiosque de aplicativo único do Microsoft Intune](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Modelo de quiosque de vários aplicativos do Microsoft Intune](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Modelo personalizado do Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Provisionamento de runtime – Vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Provisionamento de runtime – Aplicativo único](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Como as contas de visitante podem fazer logon automaticamente na experiência de quiosque?

Em builds [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante:

- AAD e configurações não ADD são suportadas por contas de visitante que estão habilitadas para o logon automático para modos de quiosque.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Há suporte para a experiência de quiosque HoloLens (1ª geração)?

O modo de quiosque só estará disponível se o dispositivo tiver Windows Holographic for Business. Todos HoloLens 2 dispositivos são Windows Holographic for Business e não há outras edições. Cada HoloLens 2 é capaz de executar o modo de quiosque de forma inocável.

HoloLens (1ª geração) precisam ser atualizados em termos de build do sistema operacional e edição do sistema operacional. Aqui estão mais informações sobre como atualizar um HoloLens (1ª geração) para [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edição. Para atualizar um HoloLens (1ª geração) para usar o modo de quiosque, primeiro você deve certificar-se de que o dispositivo seja executado Windows 10, versão 1803 ou uma versão posterior. Se você tiver usado Windows Ferramenta de Recuperação de Dispositivo do Windows para recuperar seu dispositivo HoloLens (1ª geração) para seu build padrão ou se tiver instalado as atualizações mais recentes, seu dispositivo estará pronto para configurar.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Como usar o portal do dispositivo para configurar o quiosque em ambientes de não produção?

Configurar o [dispositivo HoloLens para usar o Windows Portal de Dispositivos](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). O Device Portal é um servidor Web no HoloLens ao qual você pode se conectar usando um navegador da Web em seu computador.

 > [!CAUTION]
 > Ao configurar o HoloLens para usar o Portal de Dispositivos, você precisa habilitar o Modo de Desenvolvedor no dispositivo. O Modo de Desenvolvedor em um dispositivo que Windows Holographic for Business permite que você carregue aplicativos lado a lado. No entanto, essa configuração cria um risco de que um usuário possa instalar aplicativos que não foram certificados pelo Microsoft Store. Os administradores podem bloquear a capacidade de habilitar o Modo de Desenvolvedor usando a configuração **ApplicationManagement/AllowDeveloper Unlock** no [CSP de Política](/windows/client-management/mdm/policy-configuration-service-provider). [Saiba mais sobre o Modo de Desenvolvedor.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

O Modo de Quiosque pode ser definido por meio da API REST do Portal de Dispositivos fazendo um POST para /api/holographic/kioskmode/settings com um parâmetro de cadeia de caracteres de consulta necessário ("kioskModeEnabled" com um valor de "true" ou "false") e um parâmetro opcional ("startupApp" com um valor de um nome de pacote). Tenha em mente que o Portal de Dispositivos destina-se apenas aos desenvolvedores e não deve ser habilitado em dispositivos que não são desenvolvedores. A API REST está sujeita a alterações em atualizações/versões futuras.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problema – Nenhum aplicativo é mostrado no menu Iniciar no modo de quiosque

**Sintomas**

Ao encontrar falhas na aplicação do modo de quiosque, o seguinte comportamento será exibido:

- Antes de Windows Holographic, versão 20H2 – HoloLens mostrará todos os aplicativos no menu Iniciar.
- Windows Holographic, versão 20H2 – se um dispositivo tiver uma configuração de quiosque, que é uma combinação de acesso global atribuído e acesso atribuído ao membro do grupo AAD, se a determinação da associação ao grupo de AAD falhar, o usuário verá o menu "nada mostrado no início".

    ![Imagem da aparência do modo de quiosque agora quando ele falha.](images/hololens-kiosk-failure-behavior.png )

- Começando com [Windows Holographic, versão 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)o modo de quiosque procura Acesso Atribuído Global antes de mostrar um menu iniciar vazio. A experiência de quiosque retornará a uma configuração de quiosque global (se houver) se houver falhas durante o AAD de quiosque de grupo.

**Etapas para solucionar problemas**

- Verifique se a AUMID do aplicativo foi especificada corretamente e se ela não contém versões. Consulte a [HoloLens AUMIDs para aplicativos](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) de caixa de entrada para ver exemplos.
- Verifique se o aplicativo está instalado no dispositivo para esse usuário.
- Se a configuração de quiosque for baseada em AAD grupos, verifique se a conectividade com a Internet está presente quando o AAD usuário entrar. Se desejado, configure [a política MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) para que isso também funcione sem a Internet.

Se o XML foi usado para criar a configuração de acesso atribuído (por meio do provisionamento de runtime ou do URI de OMA personalizado do Intune), verifique se o XML está bem formado abrindo-o em qualquer navegador da Web ou editor XML. Consulte [Exemplos de código XML de quiosque](hololens-kiosk-reference.md#kiosk-xml-code-samples) para modelos bem formados e válidos.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problema – Falha ao criar um pacote com o modo de quiosque

**Sintomas**

Uma caixa de diálogo como abaixo é mostrada.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Etapas para solucionar problemas**

1. Clique no hiper link mostrado como na caixa de diálogo acima.
1. Abra ICD.log em um editor de texto e seu conteúdo deverá indicar o erro.

> [!NOTE]
> Se você tiver feito várias tentativas, verifique os carimbos de data/hora no log. Isso ajudará você a verificar apenas os problemas atuais.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problema – o pacote de provisionamento foi criado com êxito, mas não foi aplicado.

**Sintomas**

O erro é mostrado ao aplicar o pacote de provisionamento no Hololens

**Etapas para solucionar problemas**

1. Navegue até a pasta em que Windows projeto do Designer de Configuração para o pacote de provisionamento de runtime.
1. Abra ICD.log e verifique se não há erros no log durante a criação do pacote de provisionamento. Alguns erros não são exibidos durante o build, mas ainda são registrados em ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problema – o acesso atribuído a vários aplicativos AAD grupo não funciona

**Sintomas**

Ao AAD entrada do usuário, o dispositivo não entra no modo de quiosque esperado.

**Etapas para solucionar problemas**

- Confirme em XML de configuração de Acesso Atribuído que o GUID AAD grupo do qual o usuário associado é membro é usado e não o GUID do AAD usuário.
- Confirme se, no portal do Intune, AAD usuário é realmente mostrado como membro do grupo AAD direcionado.
- Somente para o Intune, confirme se o dispositivo está sendo exibido como compatível. Consulte a referência [de conformidade do dispositivo](/mem/intune/protect/device-compliance-get-started) para obter mais informações.
