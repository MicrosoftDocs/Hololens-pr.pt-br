---
title: Notas da versão do HoloLens 1ª (gen)
description: Saiba mais sobre atualizações em cada nova versão do HoloLens.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/12/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: ab67962efdafe3f39097210d60589dc6db715837
ms.sourcegitcommit: c870802ea75a9dd602319c59fedb124f80c19b71
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136166"
---
# Notas da versão do HoloLens 1ª (gen)

## Serviço de longo prazo do HoloLens (1ª gen)
O HoloLens (1ª gen) entrou em estado de serviço de longo prazo (LTS). As futuras atualizações se concentrarão nas correções de problemas e segurança, enquanto mantêm a paridade do recurso com o Windows 10 holográfico, versão 1809 para o HoloLens (1ª gen).

Para os desenvolvedores, isso significa que os aplicativos HoloLens (1ª gen) não suportam a API OpenXR.  Esses fones de ouvido com microfone permanecem com suporte no Unity 2019 LTS com o back-end da API do WinRT para o ciclo de vida total do Unity 2019 LTS a Mid-2022.

### Windows 10 holográfico, versão 1809

> **Aplica-se a:** HoloLens (1ª gen)

| Recurso | Detalhes |
|---|---|
| **Menu ações rápidas** | Quando você estiver em um aplicativo, o gesto de flor agora abrirá um menu de ações rápidas para dar a você acesso rápido aos recursos do sistema comumente usados, sem precisar sair do aplicativo. <br> Consulte [Configurar o HoloLens no modo de quiosque](hololens-kiosk.md) para obter informações sobre o menu de ações rápidas no modo de quiosque.<br><br> |
| **Parar captura de vídeo no menu iniciar ou ações rápidas** | Se você iniciar a captura de vídeo no menu iniciar ou no menu ações rápidas, você poderá parar a gravação do mesmo lugar. (Não se esqueça de que você sempre pode fazer isso com comandos de voz também.) |
| **Projeto em um dispositivo habilitado para Miracast** | Projetar o conteúdo do HoloLens para um dispositivo de superfície próxima ou TV/monitor, caso esteja usando o adaptador de vídeo da Microsoft.  Em **Iniciar**, selecione **conectar**e, em seguida, selecione o dispositivo que você deseja projetar. **Observação:** Você pode implantar o HoloLens para usar a projeção Miracast sem habilitar o modo de desenvolvedor. |
| **Novas notificações** | Exiba e responda a notificações de notificação no HoloLens, da mesma forma que no computador. Olhar para responder ou descartá-las (ou se você estiver em uma experiência de imersão, use o gesto de flor). |
| **Sobreposições do HoloLens**<br>(seletor de arquivos, teclado, caixas de diálogo etc.) | Agora você verá sobreposições, como teclado, caixas de diálogo, seletor de arquivos, etc. ao usar aplicativos imersivas. |
| **Interface do usuário de sobreposição de comentário visual para alteração de volume** | Ao usar os botões de cima/para baixo do volume do seu HoloLens, você verá uma exibição visual do nível do volume. |
| **Nova interface do usuário para inicialização do dispositivo** | Um indicador de carregamento foi adicionado durante o processo de inicialização para fornecer um comentário visual que o sistema está carregando. Reinicie o dispositivo para ver o novo indicador de carregamento: ele está entre a mensagem "Olá" e o logotipo de inicialização do Windows. |
| **Compartilhamento por proximidade** | Adição da experiência de compartilhamento por proximidade do Windows, permitindo que você compartilhe uma captura com um dispositivo Windows próximo. Ao capturar uma foto ou vídeo no HoloLens (ou usar o botão compartilhar de um aplicativo como o Microsoft Edge), selecione um dispositivo do Windows ao qual você deseja compartilhar. |
| **Compartilhar do Microsoft Edge** | O botão compartilhar agora está disponível no Microsoft Edge Windows no HoloLens. No Microsoft Edge, selecione **compartilhar**. Use o seletor de compartilhamento do HoloLens para compartilhar conteúdo da Web. |

#### Para clientes internacionais

| Recurso | Detalhes |
| --- | --- |
| Compilações em chinês e japonês localizadas | Use o HoloLens com a interface do usuário localizada para chinês simplificado ou japonês, incluindo teclado de Pinyin localizado, ditado e comandos de voz.<br>[Saiba como instalar as versões em chinês e em Japonês do HoloLens.](hololens1-install-localized.md) |
| Sintetização de fala (TTS) | O recurso de sintetização de fala agora é compatível com chinês, japonês e inglês. |

#### Para administradores

| Recurso |  Detalhes  |
|---|----|
| [Habilitar o provisionamento após a instalação](hololens-provisioning.md) | Agora você pode aplicar um pacote de provisionamento de tempo de execução a qualquer momento usando **as configurações**. |
| Acesso atribuído a grupos do Azure AD | Agora você pode usar grupos do Azure AD para configuração do acesso atribuído ao Windows para configurar o quiosque único ou múltiplo aplicativo de configuração. |
| Entrada fixar no perfil alternar da tela de entrada | O recurso de entrada de PIN agora está disponível para **outro usuário**. |
| Entrar com o provedor de credenciais Web usando a senha | Agora você pode selecionar a opção de entrada de globo para iniciar a entrada na Web com sua senha. Na tela de entrada, selecione opções de **entrada** e selecione a opção globo para iniciar a entrada na Web. Insira seu nome de usuário, se necessário, a senha. <br>**Observação:** Você pode optar por ignorar qualquer opção de pino/cartão inteligente quando solicitado durante a entrada na Web. |
| Ler informações de hardware do dispositivo por meio de MDM para que os dispositivos possam ser rastreados por número de série | Os administradores de ti podem ver e acompanhar o HoloLens pelo número de série do dispositivo no console de MDM. Consulte a documentação do MDM para obter informações e informações sobre a disponibilidade de recursos. |
| Definir o nome do dispositivo do HoloLens por meio de MDM (Rename) | Os administradores de ti podem ver e renomear dispositivos do HoloLens no console de MDM. Consulte a documentação do MDM para obter informações e informações sobre a disponibilidade de recursos. |

### Windows 10, versão 1803 para Microsoft HoloLens

> **Aplica-se a:** HoloLens (1ª gen)

O Windows 10, versão 1803, é a primeira atualização de recursos do Windows holográfico para empresas desde o lançamento no Windows 10, versão 1607. Esta atualização introduz as seguintes alterações:

- Antes, você só podia verificar se a licença de atualização do pacote comercial foi aplicada ao seu dispositivo HoloLens verificando se a VPN era uma opção disponível no dispositivo. Agora, **Settings**o  >  **sistema** de configurações mostrará o **Windows holográfico for Business** após a aplicação da licença de atualização. [Saiba como desbloquear os recursos do Windows holográfico para empresas](hololens1-upgrade-enterprise.md).

- Você pode visualizar o número da compilação do sistema operacional nas propriedades do dispositivo no aplicativo explorador de arquivos e na [ferramenta de recuperação de dispositivo do Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- O provisionamento de um dispositivo HoloLens agora ficou mais fácil com o assistente de novo **fornecimento de dispositivos hololens** na ferramenta do designer de configuração do Windows. No assistente, você pode configurar a experiência de configuração e as conexões de rede, definir o modo de desenvolvedor e obter tokens do Azure AD em massa. [Saiba como usar o assistente de provisionamento simples para o HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Quando você cria uma conta local em um pacote de provisionamento, a senha não expira mais a cada 42 dias.

- Você pode [Configurar o HoloLens como um quiosque de aplicativo único ou de vários aplicativos](hololens-kiosk.md). O modo de quiosque de vários aplicativos permite que você configure um HoloLens para executar somente os aplicativos que você especificar e impede que os usuários façam alterações.

- O MTP (protocolo de transferência de mídia) está habilitado para que você possa conectar o dispositivo HoloLens a um computador por USB e transferir arquivos entre o HoloLens e o computador. Você também pode usar o aplicativo explorador de arquivos para mover e excluir arquivos no HoloLens.

- Antes de entrar no dispositivo com uma conta do Azure Active Directory (Azure AD), você teve que **Adicionar acesso de trabalho** em **configurações** para obter acesso aos recursos corporativos. Agora, você entra com uma conta do Azure AD e a inscrição ocorre automaticamente.

- Antes de entrar, você pode escolher o ícone de rede abaixo do campo de senha para escolher uma rede diferente Wi-Fi para se conectar. Você também pode se conectar a uma rede de convidados, como em um hotel, um centro de conferências ou um negócio.

- Agora você pode compartilhar facilmente o [HoloLens com várias pessoas](hololens-multiple-users.md) usando contas do Azure AD.

- Quando a instalação ou a entrada falhar, escolha a nova opção **coletar informações** para obter os logs de diagnóstico para a solução de problemas.

- Usuários individuais podem sincronizar seus emails corporativos sem registrar o dispositivo no gerenciamento de dispositivo móvel (MDM). Você pode usar o dispositivo com uma conta da Microsoft, baixar e instalar o aplicativo de email e adicionar uma conta de email diretamente.

- Você pode verificar o status de sincronização do MDM para um dispositivo em **configurações**  >  **Accounts**  >  **acessando as informações de trabalho ou escola**  >  **Info**. Na seção **status de sincronização do dispositivo** , você pode iniciar uma sincronização, ver áreas gerenciadas pelo MDM e criar e exportar um relatório de diagnóstico avançado.
