---
title: Configurar o HoloLens como um quiosque
description: saiba como configurar e usar uma configuração de quiosque para bloquear os aplicativos em dispositivos HoloLens.
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
ms.openlocfilehash: f717a0323d1b141423fab52e49a38407ba617d02
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189334"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configurar o HoloLens como um quiosque

## <a name="what-is-kiosk-mode"></a>O que é o modo de quiosque?

O modo de quiosque é um recurso no qual você pode controlar quais aplicativos são mostrados no menu iniciar quando um usuário entra no HoloLens. Há dois cenários com suporte:

1. **Modo de quiosque de aplicativo único** – nenhum menu iniciar é exibido e um único aplicativo é iniciado automaticamente quando o usuário faz logon. <br> O *exemplo usa*: um dispositivo que executa somente o aplicativo de guias do Dynamics 365.
2. **modo de quiosque de vários aplicativos** – menu Iniciar mostra apenas os aplicativos, que foram especificados na configuração de quiosque quando um usuário faz logon. Um aplicativo pode ser escolhido para ser iniciado automaticamente, se desejado. <br> o *exemplo usa*: um dispositivo que mostra apenas o aplicativo da loja, o Hub de comentários e o aplicativo Configurações no menu iniciar.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Descrição da experiência do modo de quiosque quando um usuário entra

A tabela a seguir lista os recursos de recurso nos diferentes modos de quiosque.

| &nbsp; |Menu Iniciar |Menu de ações rápidas |Câmera e vídeo |Miracast |Cortana |Comandos de voz internos |
| --- | --- | --- | --- | --- | --- | --- |
|Quiosque de aplicativo único |Desabilitado |Desabilitado |Desabilitado |Desabilitado   |Desabilitado |Habilitado |
|Quiosques de vários aplicativos |habilitado |Habilitado  |Há  |Há |Há   |Habilitado  |

\*para obter mais informações sobre como habilitar recursos desabilitados ou como os comandos de voz interagem com recursos desabilitados e Cortana consulte [HoloLens AUMIDs for apps](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids).

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Principais considerações gerais antes de configurar o modo de quiosque

1. Determine o tipo de conta de usuário que entra em HoloLens em seu ambiente-HoloLens dá suporte a contas de Azure Active Directory (AAD), contas da Microsoft (MSA) e contas locais. Além disso, também há suporte para contas criadas temporariamente chamadas convidados/visitantes (somente para dispositivos do AAD Join). Saiba mais em [gerenciar a identidade do usuário e entrar para HoloLens](hololens-identity.md).
2. Determine os destinos da experiência do modo de quiosque – seja todos, um único usuário, determinados usuários ou usuários que sejam membros de grupos do AAD, etc.
3. Para o modo de quiosque de vários aplicativos, determine os aplicativos a serem mostrados no menu iniciar. Para cada aplicativo, sua [AUMID (ID do modelo de usuário do aplicativo)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) será necessária.
4. Determine se o modo de quiosque será aplicado a HoloLens por meio de pacotes de provisionamento de tempo de execução ou do servidor de gerenciamento de dispositivo móvel (MDM).

## <a name="security-considerations"></a>Considerações de segurança

O modo de quiosque não deve ser considerado um método de segurança, mas como um meio de controlar a experiência de inicialização na entrada do usuário. Você pode combinar a experiência do modo de quiosque com as opções mencionadas abaixo se houver necessidades específicas relacionadas à segurança:

- quando Configurações aplicativo é configurado para ser mostrado no modo de quiosque e você deseja controlar quais páginas são mostradas no aplicativo Configurações, consulte [visibilidade de Configurações de página](settings-uri-list.md)
- quando você deseja controlar o acesso a determinados recursos de hardware, por exemplo, câmera, Bluetooth, etc. para determinados aplicativos, etc. consulte [políticas no CSP de política com suporte do gerenciamento de cliente HoloLens 2 Windows](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2). Você pode revisar nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md) para ideias.
- O modo de quiosque não bloqueia um aplicativo (configurado como parte da experiência de quiosque) de iniciar outros aplicativos. quando quiser bloquear completamente o início de determinados aplicativos/processos em HoloLens, consulte usar o [controle de aplicativo Windows Defender em dispositivos HoloLens 2 no Microsoft Intune-Azure](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Principais considerações técnicas para o modo de quiosque para HoloLens

Aplica-se somente se você estiver planejando usar pacotes de provisionamento de tempo de execução ou criar configurações de quiosque manualmente. A configuração do modo de quiosque usa uma estrutura hierárquica baseada em XML:

- Um perfil de acesso atribuído define quais aplicativos são exibidos no menu iniciar no modo de quiosque. Você pode definir vários perfis na mesma estrutura XML, que pode ser referenciada mais tarde.
- Uma configuração de acesso atribuída faz referência a um perfil e a usuários de destino desse perfil, por exemplo, um usuário específico, ou grupo ou visitante do AAD, etc. Você pode definir várias configurações na mesma estrutura XML, dependendo da complexidade dos seus cenários de uso (consulte a seção cenários com suporte abaixo).
- Para saber mais, consulte [ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Cenários com suporte para o modo de quiosque com base no tipo de identidade

Consulte [links de referência](hololens-kiosk-reference.md#kiosk-xml-code-samples) para obter exemplos com base em seu cenário e atualizar conforme necessário antes de copiar e colar.

> [!NOTE]
> Use XML somente se não estiver usando a interface do usuário do Intune para criar a configuração de quiosque.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Para usuários que se conectam como uma conta local ou MSA

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. pacote, etapa 2 &ndash; Adicionar o arquivo XML de configuração do quiosque a um pacote de provisionamento

1. abra [Windows Designer de configuração](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Selecione **provisionamento avançado**, insira um nome para o seu projeto e, em seguida, selecione **Avançar**.
1. selecione **Windows 10 Holographic** e, em seguida, selecione **avançar**.
1. Selecione **Concluir**. O espaço de trabalho para seu pacote é aberto.
1. Selecione **configurações de tempo de execução**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. No painel central, selecione **procurar** para localizar e selecionar o arquivo XML de configuração de quiosque que você criou.

   ![captura de tela do campo MultiAppAssignedAccessSettings no Designer de configuração Windows.](./images/multiappassignedaccesssettings.png)
| **Experiência de quiosque desejada** | **Configuração de quiosque recomendada** | **Maneiras de configurar**  | **Comentários** |
| --- | --- | --- | --- |
| Todos os usuários que entraram têm experiência de quiosque. | [Configurar o perfil de acesso atribuído global de vários aplicativos](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução-vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | O acesso atribuído global requer [20H2 e compilações mais recentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Usuário específico que entra no obtém experiência de quiosque.  | [Configure um perfil de acesso atribuído a um ou vários aplicativos (conforme necessário) especificando o nome de um usuário específico.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Consulte as opções com suporte abaixo.](#steps-in-configuring-kiosk-mode-for-hololens) | Para o modo de quiosque de aplicativo único, somente a conta de usuário local ou a conta MSA tem suporte em HoloLens. <br> Para o modo de quiosque de vários aplicativos, somente a conta MSA ou conta AAD tem suporte em HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Para usuários que entram como conta do AAD

| **Experiência de quiosque desejada** | **Configuração de quiosque recomendada** | **Maneiras de configurar** | **Comentários** |
| --- | --- | --- | --- |
| Todos os usuários que entraram têm experiência de quiosque. | [Configurar o perfil de acesso atribuído global de vários aplicativos](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução-vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | O acesso atribuído global requer [20H2 e compilações mais recentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Cada usuário que entra no obtém experiência de quiosque, exceto determinados usuários. | [Configurar o perfil de acesso global atribuído a vários aplicativos, excluindo determinados usuários (que devem ser proprietários do dispositivo)](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners). | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução-vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | O acesso atribuído global requer [20H2 e compilações mais recentes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Cada usuário do AAD Obtém uma experiência de quiosque separada específica para esse usuário. | [Configure a configuração de acesso atribuída para cada usuário especificando seu nome de conta do AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução-vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Os usuários em diferentes grupos do AAD experimentam o modo de quiosque que é apenas para seu grupo. | [Configure a configuração de acesso atribuída para cada grupo do AAD desejado.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução-vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • quando um usuário entrar e HoloLens estiver conectado à Internet, se esse usuário for considerado membro do grupo do aad para o qual a configuração de quiosque existe, o usuário terá que experimentar o quiosque para esse grupo do aad. <br> • [se não houver internet disponível quando o usuário entrar, o usuário terá HoloLens comportamento do modo de falha.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Se a disponibilidade da Internet não for garantida quando o usuário entrar e o quiosque baseado em grupo do AAD precisar ser usado, [Considere o uso de AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). |
| os usuários que precisam usar HoloLens para fins temporários obtêm experiência de quiosque. | [Configurar a configuração de acesso atribuída para visitantes](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Provisionamento de tempo de execução-aplicativo único](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • a conta de usuário temporário é criada automaticamente pelo HoloLens na entrada e é removida quando o usuário temporário sai. <br> • Considere habilitar [a política de logon automático do visitante](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience). |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Etapas na configuração do modo de quiosque para HoloLens

As configurações de quiosque podem ser criadas e aplicadas das seguintes maneiras:

1. Com a interface do usuário do servidor MDM, por exemplo, modelos de quiosque do Intune ou configurações de OMA-URI personalizadas, que são aplicadas remotamente a HoloLens.
2. Com pacotes de provisionamento de tempo de execução, que são aplicados diretamente a HoloLens.

Aqui estão as seguintes maneiras de configurar o, selecione a guia que corresponde ao processo que você deseja usar.

1. [Microsoft Intune modelo de quiosque de aplicativo único](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune modelo de quiosque de vários aplicativos](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune modelo personalizado](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Provisionamento de tempo de execução-vários aplicativos](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Provisionamento de tempo de execução-aplicativo único](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Como as contas de visitantes podem fazer logon automaticamente na experiência de quiosque?

em builds [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1) e em diante:

- As configurações do AAD e de não-adição dão suporte a contas de visitantes que estão com o logon automático habilitado para modos de quiosque.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>há suporte para a experiência de quiosque em HoloLens (1ª gen)?

O modo de quiosque só estará disponível se o dispositivo tiver Windows Holographic for Business. todos os dispositivos HoloLens 2 são fornecidos com Windows Holographic for Business e não há outras edições. cada dispositivo HoloLens 2 é capaz de executar o modo de quiosque pronto.

os dispositivos HoloLens (1ª gen) precisam ser atualizados em termos de build do sistema operacional e edição do sistema operacional. aqui estão mais informações sobre como atualizar uma HoloLens (1ª gen) para [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition. para atualizar um dispositivo HoloLens (1ª gen) para usar o modo de quiosque, você deve primeiro verificar se o dispositivo é executado Windows 10, versão 1803 ou uma versão posterior. se você tiver usado a ferramenta de recuperação de dispositivo Windows para recuperar seu dispositivo HoloLens (1ª gen) para sua compilação padrão ou se tiver instalado as atualizações mais recentes, o dispositivo estará pronto para ser configurado.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Como usar o portal do dispositivo para configurar o quiosque em ambientes de não produção?

configure o [dispositivo de HoloLens para usar o Portal do dispositivo Windows](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). O Device Portal é um servidor Web no HoloLens ao qual você pode se conectar usando um navegador da Web em seu computador.

 > [!CAUTION]
 > ao configurar HoloLens para usar o Portal do dispositivo, você precisa habilitar o modo de desenvolvedor no dispositivo. o modo de desenvolvedor em um dispositivo que tem Windows Holographic for Business permite que você carregue aplicativos. No entanto, essa configuração cria um risco de que um usuário possa instalar aplicativos que não foram certificados pelo Microsoft Store. Os administradores podem bloquear a capacidade de habilitar o modo de desenvolvedor usando a configuração de **desbloqueio ApplicationManagement/AllowDeveloper** no [CSP de política](/windows/client-management/mdm/policy-configuration-service-provider). [Saiba mais sobre o modo de desenvolvedor.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

O modo de quiosque pode ser definido por meio da API REST do portal do dispositivo fazendo um POST para/API/Holographic/KioskMode/Settings com um parâmetro de cadeia de caracteres de consulta necessário ("kioskModeEnabled" com um valor de "true" ou "false") e um parâmetro opcional ("startupApp" com um valor de um nome de pacote). Tenha em mente que o portal do dispositivo destina-se apenas a desenvolvedores e não deve ser habilitado em dispositivos sem desenvolvedores. A API REST está sujeita a alterações em atualizações/versões futuras.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problema-nenhum aplicativo é mostrado no menu iniciar no modo de quiosque

**Sintomas**

Ao encontrar falhas na aplicação do modo de quiosque, o seguinte comportamento é exibido:

- antes do Windows Holographic, a versão 20H2-HoloLens mostrará todos os aplicativos no menu Iniciar.
- Windows Holographic, versão 20H2-se um dispositivo tiver uma configuração de quiosque, que é uma combinação de acesso global atribuído e acesso atribuído ao membro do grupo do AAD, se determinar a associação do grupo do AAD falhar, o usuário verá o menu "nada mostrado no início".

    ![Imagem do que o modo de quiosque agora parece quando ele falha.](images/hololens-kiosk-failure-behavior.png )

- a partir do [Windows Holographic, versão 21H1](hololens-release-notes.md#windows-holographic-version-21h1), o modo de quiosque procura acesso Global atribuído antes de mostrar um menu iniciar vazio. A experiência de quiosque voltará a uma configuração de quiosque global (se presente), se houver falhas durante o modo de quiosque do grupo do AAD.

**Etapas para solucionar problemas**

- Verifique se o AUMID do aplicativo está especificado corretamente e se ele não contém versões. consulte [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) para aplicativos da caixa de entrada para obter exemplos.
- Verifique se o aplicativo está instalado no dispositivo para esse usuário.
- Se a configuração do quiosque for baseada em grupos do AAD, verifique se a conectividade com a Internet está presente quando o usuário do AAD entra. Se desejar, configure a política [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) para que isso possa funcionar sem a Internet também.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problema-falha ao criar um pacote com o modo de quiosque

**Sintomas**

É exibida uma caixa de diálogo como A seguir.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Etapas para solucionar problemas**

1. Clique no hiperlink mostrado como na caixa de diálogo acima.
1. Abra o ICD. log em um editor de texto e seu conteúdo deve indicar o erro.

> [!NOTE]
> Se você tiver feito várias tentativas, verifique os carimbos de data/hora no log. Isso irá ajudá-lo a verificar apenas os problemas atuais.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problema – pacote de provisionamento criado com êxito, mas com falha ao aplicar.

**Sintomas**

O erro é mostrado ao aplicar o pacote de provisionamento no Hololens

**Etapas para solucionar problemas**

1. navegue até a pasta onde Windows projeto do Designer de configuração para o pacote de provisionamento de tempo de execução existe.
1. Abra ICD. log e verifique se não há erros no log ao compilar o pacote de provisionamento. Alguns erros não são mostrados durante a compilação, mas ainda estão conectados no ICD. log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problema – o acesso atribuído a vários aplicativos ao grupo do AAD não funciona

**Sintomas**

Na entrada do usuário do AAD, o dispositivo não entra no modo de quiosque

**Etapas para solucionar problemas**

- Confirme no XML de configuração de acesso atribuído que o GUID do grupo do AAD do qual o usuário conectado é um membro é usado e não o GUID do usuário do AAD.
- Confirme que no portal do Intune que o usuário do AAD é realmente mostrado como membro do grupo do AAD de destino.
