---
title: Notas de versão do HoloLens 1ª (gen)
description: Saiba mais sobre as atualizações em cada nova versão do HoloLens.
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
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "108308284"
---
# <a name="hololens-1st-gen-release-notes"></a>Notas de versão do HoloLens 1ª (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>Serviço de longo prazo do HoloLens (1ª gen)
O HoloLens (1º gen) inseriu o estado de manutenção em longo prazo (LTS). As atualizações futuras se concentrarão em correções de problemas e de segurança, mantendo, ao mesmo tempo, a paridade de recursos com o Windows 10 Holographic, versão 1809 para o HoloLens (1º gen).

Para os desenvolvedores, isso significa que os aplicativos HoloLens (1º gen) não oferecerão suporte à API OpenXR.  Esses headsets permanecem com suporte no Unity 2019 LTS com o back-end da API do WinRT para o ciclo de vida completo do Unity 2019 LTS até o Mid-2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versão 1809

> **Aplica-se a:** HoloLens (1º gen)

| Recurso | Detalhes |
|---|---|
| **Menu de ações rápidas** | Quando você estiver em um aplicativo, o gesto de cair agora abrirá um menu de ações rápidas para dar a você acesso rápido aos recursos do sistema comumente usados sem precisar sair do aplicativo. <br> Consulte [Configurar o HoloLens no modo de quiosque](hololens-kiosk.md) para obter informações sobre o menu de ações rápidas no modo de quiosque.<br><br> |
| **Interromper captura de vídeo no menu iniciar ou ações rápidas** | Se você iniciar captura de vídeo no menu iniciar ou no menu ações rápidas, poderá parar a gravação do mesmo local. (Não se esqueça de que você sempre pode fazer isso com comandos de voz.) |
| **Projeto para um dispositivo habilitado para Miracast** | Projetar seu conteúdo do HoloLens para um dispositivo de superfície ou TV/monitor próximo se estiver usando o adaptador de vídeo da Microsoft.  Em **Iniciar**, selecione **conectar** e, em seguida, selecione o dispositivo para o qual deseja projetar. **Observação:** Você pode implantar o HoloLens para usar a projeção Miracast sem habilitar o modo de desenvolvedor. |
| **Novas notificações** | Exiba e responda a notificações de notificação no HoloLens, exatamente como você faz em um PC. Olhar para responder ou descartá-los (ou se você estiver em uma experiência de imersão, use o gesto de cair). |
| **Sobreposições de HoloLens**<br>(seletor de arquivos, teclado, caixas de diálogo, etc.) | Agora, você verá sobreposições como teclado, caixas de diálogo, seletor de arquivos, etc. ao usar aplicativos de imersão. |
| **Interface do usuário de sobreposição de comentários visuais para alteração de volume** | Ao usar os botões de volume para cima/para baixo no seu HoloLens, você verá uma exibição visual do nível de volume. |
| **Nova interface do usuário para inicialização do dispositivo** | Um indicador de carregamento foi adicionado durante o processo de inicialização para fornecer comentários visuais que o sistema está carregando. Reinicialize o dispositivo para ver o novo indicador de carregamento — ele está entre a mensagem "Olá" e o logotipo de inicialização do Windows. |
| **Compartilhamento próximo** | Adição da experiência de compartilhamento de proximidade do Windows, permitindo que você compartilhe uma captura com um dispositivo Windows próximo. Ao capturar uma foto ou vídeo no HoloLens (ou usar o botão compartilhar de um aplicativo, como o Microsoft Edge), selecione um dispositivo Windows próximo ao qual compartilhar. |
| **Compartilhar do Microsoft Edge** | O botão compartilhar agora está disponível nas janelas do Microsoft Edge no HoloLens. No Microsoft Edge, selecione **compartilhar**. Use o selecionador de compartilhamento do HoloLens para compartilhar conteúdo da Web. |

#### <a name="for-international-customers"></a>Para clientes internacionais

| Recurso | Detalhes |
| --- | --- |
| Compilações em chinês e japonês localizadas | Use o HoloLens com a interface do usuário localizada para chinês simplificado ou japonês, incluindo comandos de voz, de ditado e de teclados de Pinyin localizados.<br>[Saiba como instalar as versões em chinês e japonês do HoloLens.](hololens1-install-localized.md) |
| Síntese de fala (TTS) | O recurso de síntese de fala agora dá suporte a chinês, japonês e inglês. |

#### <a name="for-administrators"></a>Para administradores

| Recurso |  Detalhes  |
|---|----|
| [Habilitar provisionamento pós-instalação](hololens-provisioning.md) | Agora você pode aplicar um pacote de provisionamento de tempo de execução a qualquer momento usando **configurações**. |
| Acesso atribuído com grupos do Azure AD | Agora você pode usar os grupos do Azure AD para configuração do acesso atribuído ao Windows para definir a configuração de quiosque único ou de vários aplicativos. |
| FIXAR entrada no perfil alternar da tela de entrada | O PIN de entrada agora está disponível para **outro usuário**. |
| Entrar com o provedor de credenciais da Web usando a senha | Agora você pode selecionar a opção de entrada do globo para iniciar a entrada na Web com sua senha. Na tela de entrada, selecione opções de **entrada** e selecione a opção de globo para iniciar a entrada na Web. Insira seu nome de usuário, se necessário, e sua senha. <br>**Observação:** Você pode optar por ignorar as opções de PIN/cartão inteligente quando solicitado durante a entrada na Web. |
| Ler informações de hardware do dispositivo por meio do MDM para que os dispositivos possam ser acompanhados pelo número de série | Os administradores de ti podem ver e acompanhar o HoloLens pelo número de série do dispositivo em seu console do MDM. Consulte a documentação do MDM para obter informações e disponibilidade de recursos. |
| Definir o nome do dispositivo do HoloLens por meio do MDM (renomear) | Os administradores de ti podem ver e renomear dispositivos HoloLens no console do MDM. Consulte a documentação do MDM para obter informações e disponibilidade de recursos. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, versão 1803 para Microsoft HoloLens

> **Aplica-se a:** HoloLens (1º gen)

O Windows 10, versão 1803, é a primeira atualização de recurso para o Windows Holographic for Business desde seu lançamento no Windows 10, versão 1607. Essa atualização apresenta as seguintes alterações:

- Anteriormente, você podia apenas verificar se a licença de atualização do pacote comercial foi aplicada ao seu dispositivo de HoloLens verificando se a VPN era uma opção disponível no dispositivo. Agora,   >  o **sistema** de configurações exibirá o **Windows Holographic for Business** depois que a licença de atualização for aplicada. [Saiba como desbloquear os recursos do Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- Você pode exibir o número de Build do sistema operacional nas propriedades do dispositivo no aplicativo explorador de arquivos e na [ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- O provisionamento de um dispositivo de HoloLens agora é mais fácil com o assistente de novo **provisionamento de dispositivos do hololens** na ferramenta de designer de configuração do Windows. No assistente, você pode configurar a experiência de instalação e as conexões de rede, definir o modo de desenvolvedor e obter tokens do Azure AD em massa. [Saiba como usar o assistente de provisionamento simples para o HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Quando você cria uma conta local em um pacote de provisionamento, a senha não expira mais a cada 42 dias.

- Você pode [Configurar o HoloLens como um quiosque de aplicativo único ou de vários aplicativos](hololens-kiosk.md). O modo de quiosque de vários aplicativos permite que você configure um HoloLens para executar apenas os aplicativos que você especificar e impede que os usuários façam alterações.

- O MTP (protocolo de transferência de mídia) está habilitado para que você possa conectar o dispositivo HoloLens a um PC por USB e transferir arquivos entre o HoloLens e o PC. Você também pode usar o aplicativo explorador de arquivos para mover e excluir arquivos de dentro do HoloLens.

- Anteriormente, depois de entrar no dispositivo com uma conta do Azure Active Directory (AD do Azure), você precisava **Adicionar acesso de trabalho** nas **configurações** para obter acesso aos recursos corporativos. Agora, você entra com uma conta do Azure AD e o registro ocorre automaticamente.

- Antes de entrar, você pode escolher o ícone de rede abaixo do campo senha para escolher uma rede Wi-Fi diferente à qual se conectar. Você também pode se conectar a uma rede de convidados, como em um hotel, na central de conferências ou em uma empresa.

- Agora você pode compartilhar facilmente o [HoloLens com várias pessoas](hololens-multiple-users.md) usando contas do Azure AD.

- Quando a instalação ou a entrada falhar, escolha a nova opção **coletar informações** para obter os logs de diagnóstico para solução de problemas.

- Os usuários individuais podem sincronizar seus emails corporativos sem registrar seu dispositivo no MDM (gerenciamento de dispositivo móvel). Você pode usar o dispositivo com uma conta da Microsoft, baixar e instalar o aplicativo de email e adicionar uma conta de email diretamente.

- Você pode verificar o status de sincronização do MDM de um dispositivo em **configurações**  >  **contas**  >  **acessar informações corporativas ou de estudante**  >  . Na seção **status de sincronização do dispositivo** , você pode iniciar uma sincronização, ver áreas gerenciadas pelo MDM e criar e exportar um relatório de diagnóstico avançado.
