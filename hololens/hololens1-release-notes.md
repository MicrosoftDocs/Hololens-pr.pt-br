---
title: HoloLens 1ª (gen) notas de versão
description: Saiba mais sobre as atualizações em cada nova HoloLens versão.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032000"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1ª (gen) notas de versão

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens manutenção de longo prazo (1ª geração)
HoloLens (1ª geração) entrou no estado LTS (Manutenção de Longo Prazo). Atualizações futuras se concentrarão em problemas e correções de segurança, mantendo a paridade de recursos com o Windows 10 Holographic, versão 1809 para HoloLens (1ª geração).

Para desenvolvedores, isso significa que HoloLens (1ª geração) não darão suporte à API openXR.  Esses headsets permanecem com suporte no Unity 2019 LTS com o back-end da API do WinRT para o ciclo de vida completo do Unity 2019 LTS até meados de 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versão 1809

> **Aplica-se a:** HoloLens (1ª geração)

| Recurso | Detalhes |
|---|---|
| **Menu Ações rápidas** | Quando você estiver em um aplicativo, o gesto de Bloom agora abrirá um menu Ações rápidas para dar acesso rápido aos recursos do sistema comumente usados sem precisar sair do aplicativo. <br> Confira [Configurar o HoloLens no modo de quiosque para](hololens-kiosk.md) obter informações sobre o menu Ações rápidas no modo de quiosque.<br><br> |
| **Parar a captura de vídeo no menu Iniciar ou ações rápidas** | Se você iniciar a captura de vídeo no menu menu Iniciar ou ações rápidas, poderá interromper a gravação no mesmo local. (Não se esqueça, você sempre pode fazer isso com comandos de voz também.) |
| **Project a um Miracast habilitado para Miracast dispositivo habilitado** | Project seu conteúdo HoloLens para um dispositivo Surface ou TV/Monitor próximo se estiver usando o adaptador de Exibição da Microsoft.  Em **Iniciar**, **selecione Conexão** e, em seguida, selecione o dispositivo para o que você deseja projetar. **Observação:** Você pode implantar o HoloLens para usar a Miracast sem habilitá-lo. |
| **Novas notificações** | Veja e responda aos sistema de notificação HoloLens, assim como você faz em um computador. Aja com atenção para responder ou descartá-los (ou se você estiver em uma experiência imersiva, use o gesto de bloom). |
| **HoloLens sobreposições**<br>(selador de arquivo, teclado, caixas de diálogo, etc.) | Agora você verá sobreposições como o teclado, as caixas de diálogo, o selador de arquivos etc. ao usar aplicativos imersivos. |
| **Interface do usuário de sobreposição de comentários visuais para alteração de volume** | Ao usar os botões para cima/para baixo no HoloLens, você verá uma exibição visual do nível do volume. |
| **Nova interface do usuário para inicialização do dispositivo** | Um indicador de carregamento foi adicionado durante o processo de inicialização para fornecer comentários visuais que o sistema está carregando. Reinicialize o dispositivo para ver o novo indicador de carregamento– ele está entre a mensagem "Hello" e o logotipo Windows inicialização. |
| **Compartilhamento próximo** | Adição da experiência Windows Compartilhamento Próximo, permitindo que você compartilhe uma captura com um dispositivo Windows próximo. Ao capturar uma foto ou um vídeo no HoloLens (ou usar o botão compartilhar de um aplicativo, como Microsoft Edge), selecione um dispositivo Windows próximo com o que compartilhar. |
| **Compartilhar do Microsoft Edge** | O botão Compartilhar agora está disponível Microsoft Edge janelas no HoloLens. No Microsoft Edge, selecione **Compartilhar**. Use o se HoloLens de compartilhamento para compartilhar conteúdo da Web. |

#### <a name="for-international-customers"></a>Para clientes internacionais

| Recurso | Detalhes |
| --- | --- |
| Builds localizados em chinês e japonês | Use HoloLens interface do usuário localizada para chinês simplificado ou japonês, incluindo comandos de voz, ditado e teclado Pinyin localizados.<br>[Saiba como instalar as versões em chinês e japonês do HoloLens.](hololens1-install-localized.md) |
| Sintetizar fala (TTS) | O recurso de síntese de fala agora dá suporte a chinês, japonês e inglês. |

#### <a name="for-administrators"></a>Para administradores

| Recurso |  Detalhes  |
|---|----|
| [Habilitar o provisionamento pós-instalação](hololens-provisioning.md) | Agora você pode aplicar um pacote de provisionamento de runtime a qualquer momento usando **Configurações**. |
| Acesso atribuído com grupos do Azure AD | Agora você pode usar grupos do Azure AD para a configuração Windows acesso atribuído para configurar a configuração de quiosque de aplicativo único ou de vários aplicativos. |
| Entrada de PIN na opção de perfil da tela de entrada | A login do PIN agora está disponível para **Outro Usuário.** |
| Entrar com o Web Provedor de Credenciais usando senha | Agora você pode selecionar a opção de login do Globe para iniciar a login na Web com sua senha. Na tela de login, selecione **Opções de** login e selecione a opção Globe para iniciar a login na Web. Insira seu nome de usuário, se necessário, em seguida, sua senha. <br>**Observação:** Você pode optar por ignorar qualquer opção de PIN/Cartão inteligente quando solicitado durante a logon na Web. |
| Ler informações de hardware do dispositivo por meio do MDM para que os dispositivos possam ser rastreados pelo número de série | Os administradores de IT podem ver e acompanhar HoloLens pelo número de série do dispositivo no console do MDM. Consulte a documentação do MDM para obter instruções e disponibilidade de recursos. |
| Definir HoloLens do dispositivo por meio do MDM (renomear) | Os administradores de IT podem ver e renomear HoloLens dispositivos no console do MDM. Consulte a documentação do MDM para obter instruções e disponibilidade de recursos. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, versão 1803 para Microsoft HoloLens

> **Aplica-se a:** HoloLens (1ª geração)

Windows 10, versão 1803, é a primeira atualização de recursos para Windows Holographic for Business desde sua versão Windows 10, versão 1607. Essa atualização apresenta as seguintes alterações:

- Anteriormente, você só podia verificar se a licença de atualização do Commercial Suite havia sido aplicada ao seu dispositivo HoloLens verificando se a VPN era uma opção disponível no dispositivo. Agora, **Configurações**  >  **System** exibirá **Windows Holographic for Business** depois que a licença de atualização for aplicada. [Saiba como desbloquear recursos Windows Holographic for Business .](hololens1-upgrade-enterprise.md)

- Você pode exibir o número de build do sistema operacional nas propriedades do dispositivo no aplicativo Explorador de Arquivos e no [WDRT (Ferramenta Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)Recuperação de Dispositivo).
- O provisionamento de um HoloLens agora é mais fácil com o novo assistente **provisionar HoloLens dispositivos** na ferramenta Windows Designer de Configuração. No assistente, você pode configurar a experiência de instalação e as conexões de rede, definir o modo de desenvolvedor e obter tokens do Azure AD em massa. [Saiba como usar o assistente de provisionamento simples para HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Quando você cria uma conta local em um pacote de provisionamento, a senha não expira mais a cada 42 dias.

- Você pode [configurar HoloLens como um quiosque](hololens-kiosk.md)de aplicativo único ou de vários aplicativos. O modo de quiosque de vários aplicativos permite configurar um HoloLens para executar apenas os aplicativos especificados e impede que os usuários façam alterações.

- O protocolo MTP está habilitado para que você possa conectar o dispositivo HoloLens a um computador por USB e transferir arquivos entre o HoloLens e o computador. Você também pode usar o aplicativo Explorador de Arquivos para mover e excluir arquivos de dentro HoloLens.

- Anteriormente, depois de entrar no dispositivo com uma conta do Azure Active Directory (Azure AD), você precisava adicionar acesso de trabalho no **Configurações** para obter acesso aos recursos corporativos.  Agora, você pode entrar com uma conta do Azure AD e o registro ocorre automaticamente.

- Antes de entrar, você pode escolher o ícone de rede abaixo do campo de senha para escolher uma rede Wi-Fi rede à qual se conectar. Você também pode se conectar a uma rede de convidado, como em um hotel, centro de conferência ou negócios.

- Agora você pode compartilhar [facilmente HoloLens com várias pessoas usando](hololens-multiple-users.md) contas do Azure AD.

- Quando a instalação ou a conexão falhar, escolha a nova opção Coletar **informações** para obter logs de diagnóstico para solução de problemas.

- Usuários individuais podem sincronizar seus emails corporativos sem registrar seu dispositivo no MDM (gerenciamento de dispositivo móvel). Você pode usar o dispositivo com uma Conta da Microsoft, baixar e instalar o aplicativo Mail e adicionar uma conta de email diretamente.

- Você pode verificar o status de sincronização do MDM para um **dispositivo Configurações** Informações de Trabalho ou De Estudante de Acesso a  >    >    >  **Contas.** Na seção **Status da sincronização** do dispositivo, você pode iniciar uma sincronização, ver áreas gerenciadas pelo MDM e criar e exportar um relatório de diagnóstico avançado.
