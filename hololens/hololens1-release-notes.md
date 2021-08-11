---
title: notas de versão do HoloLens 1ª (gen)
description: saiba mais sobre as atualizações em cada nova versão de HoloLens.
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
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661839"
---
# <a name="hololens-1st-gen-release-notes"></a>notas de versão do HoloLens 1ª (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>manutenção de longo prazo do HoloLens (1ª gen)
HoloLens (1ª gen) inseriu o estado de manutenção em longo prazo (LTS). as atualizações futuras se concentrarão em correções de problemas e de segurança, mantendo, ao mesmo tempo, a paridade de recursos com o Windows 10 Holographic, versão 1809 para HoloLens (1ª gen).

para os desenvolvedores, isso significa que os aplicativos HoloLens (1ª gen) não oferecerão suporte à API OpenXR.  Esses headsets permanecem com suporte no Unity 2019 LTS com o back-end da API do WinRT para o ciclo de vida completo do Unity 2019 LTS até o Mid-2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versão 1809

> **aplica-se a:** HoloLens (1ª gen)

| Recurso | Detalhes |
|---|---|
| **Menu de ações rápidas** | Quando você estiver em um aplicativo, o gesto de cair agora abrirá um menu de ações rápidas para dar a você acesso rápido aos recursos do sistema comumente usados sem precisar sair do aplicativo. <br> consulte [configurar HoloLens no modo de quiosque](hololens-kiosk.md) para obter informações sobre o menu ações rápidas no modo de quiosque.<br><br> |
| **Interromper captura de vídeo no menu iniciar ou ações rápidas** | se você iniciar a captura de vídeo no menu menu Iniciar ou ações rápidas, poderá parar a gravação do mesmo local. (Não se esqueça de que você sempre pode fazer isso com comandos de voz.) |
| **Project a um dispositivo habilitado para Miracast** | Project seu conteúdo de HoloLens para um dispositivo de superfície ou TV/Monitor próximo, se estiver usando o adaptador de vídeo da Microsoft.  em **iniciar**, selecione **Conexão** e, em seguida, selecione o dispositivo para o qual deseja projetar. **Observação:** você pode implantar HoloLens para usar Miracast projeção sem habilitar o modo de desenvolvedor. |
| **Novas notificações** | exiba e responda a notificações de notificação em HoloLens, exatamente como você faz em um computador. Olhar para responder ou descartá-los (ou se você estiver em uma experiência de imersão, use o gesto de cair). |
| **sobreposições de HoloLens**<br>(seletor de arquivos, teclado, caixas de diálogo, etc.) | Agora, você verá sobreposições como teclado, caixas de diálogo, seletor de arquivos, etc. ao usar aplicativos de imersão. |
| **Interface do usuário de sobreposição de comentários visuais para alteração de volume** | quando você usar os botões de volume para cima/para baixo na HoloLens, verá uma exibição visual do nível de volume. |
| **Nova interface do usuário para inicialização do dispositivo** | Um indicador de carregamento foi adicionado durante o processo de inicialização para fornecer comentários visuais que o sistema está carregando. reinicialize o dispositivo para ver o novo indicador de carregamento — ele está entre a mensagem "olá" e o logotipo de inicialização do Windows. |
| **Compartilhamento próximo** | adição do Windows experiência de compartilhamento próxima, permitindo que você compartilhe uma captura com um dispositivo Windows próximo. ao capturar uma foto ou vídeo em HoloLens (ou usar o botão compartilhar de um aplicativo, como Microsoft Edge), selecione um dispositivo de Windows próximo ao qual compartilhar. |
| **Compartilhar de Microsoft Edge** | o botão compartilhar agora está disponível no windows Microsoft Edge no HoloLens. em Microsoft Edge, selecione **compartilhar**. Use o selecionador de compartilhamento de HoloLens para compartilhar conteúdo da web. |

#### <a name="for-international-customers"></a>Para clientes internacionais

| Recurso | Detalhes |
| --- | --- |
| Compilações em chinês e japonês localizadas | Use HoloLens com a interface do usuário localizada para chinês simplificado ou japonês, incluindo comandos de voz, de ditado e de teclados de Pinyin localizados.<br>[Saiba como instalar as versões em chinês e japonês do HoloLens.](hololens1-install-localized.md) |
| Síntese de fala (TTS) | O recurso de síntese de fala agora dá suporte a chinês, japonês e inglês. |

#### <a name="for-administrators"></a>Para administradores

| Recurso |  Detalhes  |
|---|----|
| [Habilitar provisionamento pós-instalação](hololens-provisioning.md) | agora você pode aplicar um pacote de provisionamento de tempo de execução a qualquer momento usando **Configurações**. |
| Acesso atribuído com grupos do Azure AD | agora você pode usar grupos do Azure AD para configuração de Windows acesso atribuído para configurar a configuração de quiosque único ou de vários aplicativos. |
| FIXAR entrada no perfil alternar da tela de entrada | O PIN de entrada agora está disponível para **outro usuário**. |
| Entrar com o provedor de credenciais da Web usando a senha | Agora você pode selecionar a opção de entrada do globo para iniciar a entrada na Web com sua senha. Na tela de entrada, selecione opções de **entrada** e selecione a opção de globo para iniciar a entrada na Web. Insira seu nome de usuário, se necessário, e sua senha. <br>**Observação:** Você pode optar por ignorar as opções de PIN/cartão inteligente quando solicitado durante a entrada na Web. |
| Ler informações de hardware do dispositivo por meio do MDM para que os dispositivos possam ser acompanhados pelo número de série | os administradores de ti podem ver e controlar HoloLens pelo número de série do dispositivo em seu console do MDM. Consulte a documentação do MDM para obter informações e disponibilidade de recursos. |
| definir HoloLens nome do dispositivo por meio de MDM (renomear) | os administradores de ti podem ver e renomear HoloLens dispositivos em seu console do MDM. Consulte a documentação do MDM para obter informações e disponibilidade de recursos. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, versão 1803 para Microsoft HoloLens

> **aplica-se a:** HoloLens (1ª gen)

Windows 10, versão 1803, é a primeira atualização de recurso a Windows Holographic for Business desde sua versão no Windows 10, versão 1607. Essa atualização apresenta as seguintes alterações:

- anteriormente, você podia apenas verificar se a licença de atualização do pacote comercial foi aplicada ao dispositivo HoloLens verificando se a VPN era uma opção disponível no dispositivo. agora, **Configurações**  >  **sistema** exibirá **Windows Holographic for Business** depois que a licença de atualização for aplicada. [saiba como desbloquear recursos de Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- você pode exibir o número de build do sistema operacional nas propriedades do dispositivo no aplicativo explorador de arquivos e na [ferramenta de recuperação de dispositivo Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- o provisionamento de um dispositivo de HoloLens agora é mais fácil com o novo assistente para **provisionar HoloLens dispositivos** na ferramenta Windows Configuration Designer. No assistente, você pode configurar a experiência de instalação e as conexões de rede, definir o modo de desenvolvedor e obter tokens do Azure AD em massa. [Saiba como usar o assistente de provisionamento simples para HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Quando você cria uma conta local em um pacote de provisionamento, a senha não expira mais a cada 42 dias.

- você pode [configurar HoloLens como um quiosque de aplicativo único ou de vários aplicativos](hololens-kiosk.md). o modo de quiosque de vários aplicativos permite que você configure um HoloLens para executar apenas os aplicativos que você especificar e impede que os usuários façam alterações.

- o MTP (protocolo de transferência de mídia) está habilitado para que você possa conectar o dispositivo de HoloLens a um PC por USB e transferir arquivos entre HoloLens e o PC. Você também pode usar o aplicativo explorador de arquivos para mover e excluir arquivos de dentro HoloLens.

- anteriormente, depois de entrar no dispositivo com uma conta do Azure Active Directory (AD do Azure), você precisava **adicionar acesso de trabalho** no **Configurações** para obter acesso aos recursos corporativos. Agora, você entra com uma conta do Azure AD e o registro ocorre automaticamente.

- Antes de entrar, você pode escolher o ícone de rede abaixo do campo senha para escolher uma rede Wi-Fi diferente à qual se conectar. Você também pode se conectar a uma rede de convidados, como em um hotel, na central de conferências ou em uma empresa.

- agora você pode [compartilhar facilmente HoloLens com várias pessoas](hololens-multiple-users.md) usando contas do Azure AD.

- Quando a instalação ou a entrada falhar, escolha a nova opção **coletar informações** para obter os logs de diagnóstico para solução de problemas.

- Os usuários individuais podem sincronizar seus emails corporativos sem registrar seu dispositivo no MDM (gerenciamento de dispositivo móvel). Você pode usar o dispositivo com uma conta da Microsoft, baixar e instalar o aplicativo de email e adicionar uma conta de email diretamente.

- você pode verificar o status de sincronização do MDM de um dispositivo no **Configurações**  >  **contas**  >  **acessar informações corporativas ou de estudante**  >  . Na seção **status de sincronização do dispositivo** , você pode iniciar uma sincronização, ver áreas gerenciadas pelo MDM e criar e exportar um relatório de diagnóstico avançado.
