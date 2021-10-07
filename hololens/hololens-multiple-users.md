---
title: compartilhar seus HoloLens com várias pessoas
description: você pode configurar HoloLens para serem compartilhados por várias contas de Azure Active Directory ou por vários usuários que usam uma única conta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600722"
---
# <a name="share-your-hololens-with-multiple-people"></a>compartilhar seus HoloLens com várias pessoas

## <a name="overview"></a>Visão geral

as empresas geralmente investem em muitos dispositivos HoloLens compartilhados. a maneira como você usa HoloLens é flexível em todo o tabuleiro, dependendo de seus requisitos individuais. Aqui está um exemplo de algumas experiências de vários usuários:

- uma frota de dispositivos HoloLens 2 é configurada por meio do Windows autopilot para o HoloLens 2, com um portfólio consistente de aplicativos da empresa em cada dispositivo. Você configurou alguns perfis de quiosque diferentes, visando diferentes grupos do Azure AD. cada usuário faz logon no HoloLens usando chaves FIDO2 e entrando em sua própria conta do Azure AD e é apresentado a uma experiência personalizada.
- um ISV (fornecedor independente de software) aluga HoloLens 2 dispositivos com o auxílio remoto do D365 e seu aplicativo de linha de negócios (LOB) para a empresa de um cliente. Esses dispositivos são configurados para quiosques que incluem apenas seus aplicativos LOB e assistência remota e são compartilhados entre vários usuários finais. o WDAC é usado para manter o aplicativo Configurações e Microsoft Edge de iniciar. Incluído no aluguel está um pacote de bateria USB-C para manter os dispositivos em plena carga em vários turnos.
- um usuário final em uma empresa tenta fazer ajustes para Bluetooth no dispositivo para que eles possam conectar um novo dispositivo, mas a página Configurações política de visibilidade está habilitada para limitar a exibição da página de dispositivos. Eles ainda têm permissão de acesso a outras páginas, conforme necessário, como Wi-Fi para que possam usar o auxílio remoto em vários locais com o mesmo HoloLens.

## <a name="best-practices"></a>Práticas recomendadas

Ao planejar o compartilhamento de seus dispositivos, há várias considerações para otimizar seu ambiente de dispositivo com base nas suas necessidades de negócios.

- [Identidade e autenticação](#identity-and-authentication)
- [Gerenciamento de dispositivo](#device-management)
- [Gerenciamento avançado de dispositivos – quiosque e WDAC](#advanced-device-management---kiosk-and-wdac)
- [Gerenciamento físico](#physical-management)

### <a name="identity-and-authentication"></a>[Identidade e autenticação](hololens-identity.md)

Se você estiver planejando ter várias contas em um dispositivo, terá contas do Azure AD com todos os modos de autenticação. esses métodos de autenticação serão baseados em [Windows Hello](/windows-hardware/design/device-experiences/windows-hello), incluindo as chaves íris e FIDO2.

- As chaves de segurança FIDO 2 serão excelentes se você tiver vários dispositivos, muitos usuários ou estiver constantemente usando novos dispositivos.
- Se você tiver 10 ou menos usuários, a íris é uma solução rápida para conectar usuários que entraram anteriormente no mesmo dispositivo.

### <a name="device-management"></a>[Gerenciamento de dispositivo](hololens-csp-policy-overview.md)

Se os dispositivos estiverem sendo compartilhados entre os usuários, você provavelmente desejará usar restrições de dispositivo. Usando o gerenciamento de dispositivos, você pode definir algumas políticas para habilitar melhor os usuários a usar o dispositivo, gerenciar atualizações ou limitar o que o dispositivo pode fazer. É recomendável que você examine nossas [restrições comuns de dispositivo](hololens-common-device-restrictions.md)e veja se essas recomendações parecem se ajustar à sua organização. depois de saber quais políticas você deseja usar, você pode aplicá-las por meio [do Microsoft MDM (Endpoint Manager)](hololens-mdm-configure.md) ou pacotes de provisionamento.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Gerenciamento avançado de dispositivos – [quiosque](hololens-kiosk.md) e [WDAC](windows-defender-application-control-wdac.md)

Em alguns casos, talvez você queira limitar quais aplicativos podem ser acessados pelos usuários finais. Você pode estar limitando a quais aplicativos os usuários são apresentados no menu iniciar usando o [modo de quiosque](hololens-kiosk.md). O quiosque pode ser configurado para apresentar diferentes menus de início com base em usuários, grupos do Azure ou tipos de usuário especiais; esse visitante ou excluindo os proprietários do dispositivo. Você pode escolher vários aplicativos ou apenas um único aplicativo. Um quiosque de vários aplicativos não impede que um aplicativo inicie outro, portanto, se a loja ou outro aplicativo estiver disponível, os usuários ainda poderão iniciar outro aplicativo.

talvez você também queira interromper completamente a inicialização de aplicativos ou serviços usando o [controle de aplicativo Windows Defender (WDAC)](windows-defender-application-control-wdac.md) para restringir os aplicativos. o WDAC é diferente daquele quiosque, porque ele não altera a interface do usuário do HoloLens, mas não permite que um aplicativo bloqueado seja iniciado.

a [visibilidade da Configurações de página](settings-uri-list.md) é outra maneira de adicionar restrições a um dispositivo. no evento, você precisa conceder aos usuários acesso a algumas páginas no aplicativo Configurações, mas nem todos você pode usar a página Configurações visibilidade para limitar o acesso. Isso é útil, por exemplo, se os usuários precisarem alterar o Wi-Fi, mas você não quiser que eles acessem a página contas.

### <a name="physical-management"></a>Gerenciamento físico

Ao compartilhar o dispositivo entre vários usuários, há algumas considerações físicas.

- Verifique se os dispositivos estão carregando entre os turnos.
- Se um dispositivo for necessário para um turno e precisar dos últimos vários turnos, considere o uso de uma bateria externa no início de uma mudança, enquanto o dispositivo ainda tem um encargo significativo de acordo com as [direções de calor de gerenciamento](hololens2-charging.md#managing-heat).
- Ao armazenar dispositivos, mantenha-os conectados e conectados a uma rede. Essa é a melhor maneira de garantir atualizações do sistema operacional e do aplicativo.
- Considere como você planeja [limpar o dispositivo](hololens2-maintenance.md) entre os usuários.
- Para um dispositivo com um único usuário compartilhado, se estiver usando um PIN compartilhado/senha para um único usuário, não coloque o PIN/senha no lado do dispositivo.
- Para vários dispositivos com um único usuário compartilhado, use vários PINs/senhas.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Compartilhar com várias pessoas, cada uma usando sua própria conta

as contas individuais do Azure Active Directory (AD do Azure) são o caso de uso preferencial e mais seguro de identidade para HoloLens 2 usuários. Ao usar suas próprias contas do Azure AD, vários usuários podem manter suas próprias configurações de usuário e dados de usuário no dispositivo. Somente um usuário pode ser conectado por vez. quando um usuário entra, HoloLens desconecta o usuário anterior.

para garantir que várias pessoas possam usar suas próprias contas na sua HoloLens, siga estas etapas para configurá-las:

1. Quando você [Configurar o dispositivo](hololens2-start.md), selecione **meu trabalho ou escola que o possui** e entre usando uma conta do Azure AD.
1. depois de concluir a instalação, verifique se as configurações da conta (Configurações > contas) incluem **outros usuários**.

> [!NOTE]
> Se o dispositivo não tiver sido configurado com uma conta do Azure AD, ele precisará ser [redefinido ou reatualizado](hololens-recovery.md) e configurado corretamente.

para usar HoloLens, cada usuário segue estas etapas:

1. Se outro usuário estiver usando o dispositivo, escolha uma das seguintes opções:
   - Pressione o botão de energia uma vez para ir para o modo de espera e pressione o botão de energia novamente para retornar à tela de bloqueio
   - selecione o bloco usuário no **menu Iniciar** ou escolha sair no **menu de energia** para sair do usuário atual.

1. Use suas credenciais de conta do Azure AD para entrar no dispositivo.  
    - se for a primeira vez que você usou o dispositivo, ele solicitará que você [calibre](hololens-calibration.md) os HoloLens para seus próprios olhos.
    - Se você usou anteriormente o dispositivo:
        - [Windows Holographic, versão 20H2, build 19041,1128](hololens-release-notes.md#windows-holographic-version-20h2) ou superior, a exibição ajusta-se diretamente para qualidade e uma experiência de exibição confortável.
        - As compilações anteriores precisarão de calibragem manual para se ajustar aos seus olhos.

> [!TIP]
> Se um usuário não tiver entrado em um dispositivo ainda, tente um desses dois métodos para um logon mais rápido:
>
> - **Chave de segurança do Fido 2** : sua chave de segurança do FIDO2 será reconhecida automaticamente e o usuário não precisará digitar suas credenciais de usuário ou usar MFA. Esse é o método mais rápido para entrar em um novo dispositivo.
> - **Autenticação na Web** : quando você entra em um novo dispositivo, pode selecionar a **entrada de link de outro dispositivo** que gerará um código de 9 caracteres que você pode usar em [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) para entrar como o usuário no dispositivo ou digitar seu nome de usuário e senha usando um teclado para sua conveniência.

para ver uma lista dos usuários do dispositivo ou remover um usuário do dispositivo, acesse **Configurações**  >  **contas**  >  **outros usuários**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Compartilhar com várias pessoas, tudo usando a mesma conta

vários usuários também podem compartilhar um dispositivo HoloLens ao usar uma única conta de usuário. embora seja preferível que os usuários HoloLens façam logon no dispositivo com suas identidades individuais (contas do Azure AD), isso não é uma opção em algumas organizações.

Há dois métodos de dispositivo compartilhado disponíveis:

- **vários usuários finais compartilhando 1 dispositivo** -um dispositivo HoloLens é alocado para um espaço designado onde qualquer funcionário pode usar o dispositivo. Os exemplos seriam uma sala limpa ou um pacote Surgical.

- **vários usuários finais que compartilham vários dispositivos** – HoloLens dispositivos estão em um espaço de armazenamento compartilhado onde os funcionários podem usar qualquer dispositivo. Os exemplos seriam um Rig óleo ou um revendedor/garagem automático.

Quando um novo usuário coloca o dispositivo pela primeira vez enquanto mantém a mesma conta conectada, o dispositivo solicita que o usuário calibre rapidamente e personalize a experiência de exibição. O dispositivo armazenará as informações de calibragem para otimizar automaticamente a qualidade e o conforto da experiência de exibição de cada usuário. Os usuários não precisarão calibrar o dispositivo novamente.
