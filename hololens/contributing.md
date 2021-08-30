---
title: Instruções de contribuição
description: saiba como contribuir com os HoloLens documentos na plataforma docs.microsoft.com usando uma redução GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188977"
---
# <a name="contributing-to-the-hololens-documentation"></a>contribuindo para a documentação de HoloLens

bem-vindo à [documentação do HoloLens](https://github.com/MicrosoftDocs/Hololens)! Todos os artigos que você criar ou editar neste repositório **estarão visíveis para o público.** 

HoloLens docs são exibidos na plataforma docs.microsoft.com, que usa a redução GitHub com recursos do Markdig. O conteúdo editado neste repositório é formatado em páginas estilizadas que aparecem em/hololens.

Esta página aborda as etapas e diretrizes básicas de contribuição e links para noções básicas de redução. Obrigado pela sua contribuição!

## <a name="available-repos"></a>Repositórios disponíveis

| Nome do repositório | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realidade Misturada | [MicrosoftDocs/misto – realidade](/windows/mixed-reality) |
| Guia dos entusiastas do VR | [MicrosoftDocs/misto-realidade/entusiasta-guia](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Antes de começar

se você ainda não tiver uma, precisará [criar uma conta de GitHub](https://github.com/join).

>[!NOTE]
>se você for um funcionário da microsoft, vincule sua conta de GitHub ao seu alias da microsoft no [portal do microsoft Open Source](https://repos.opensource.microsoft.com/). Junte-se às organizações **"Microsoft"** e **"MicrosoftDocs"** .

ao configurar sua conta de GitHub, também recomendamos estas precauções de segurança:
- crie uma [senha forte para sua conta de GitHub](https://github.com/settings/admin).
- Habilite [a autenticação de dois fatores](https://github.com/settings/two_factor_authentication/configure).
- Salve seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) em um local seguro.
- Atualize suas [configurações de perfil público](https://github.com/settings/profile).
   - Defina seu nome e considere definir seu *email público* para *não mostrar meu endereço de email*.
   - Recomendamos que você carregue uma imagem de perfil porque uma miniatura é mostrada nas páginas de docs para as quais você contribui.
- Se você planeja usar a linha de comando, considere configurar o [Gerenciador de credenciais git para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Dessa forma, você não precisará inserir sua senha toda vez que fizer uma contribuição.

o sistema de publicação está vinculado a GitHub, portanto, essas etapas são importantes. você será listado como autor ou colaborador para cada artigo usando seu alias de GitHub.

## <a name="editing-an-existing-article"></a>Editando um artigo existente

Use o fluxo de trabalho a seguir para fazer atualizações em *um artigo existente* por meio de GitHub em um navegador da web:

1. Navegue até o artigo que você deseja editar na pasta "Mixed-realde docs".

2. Selecione o botão Editar (ícone de lápis) no canto superior direito.

   ![Edite um artigo.](images/editpage.png)

   Isso irá bifurcar automaticamente uma ramificação descartável do Branch padrão, _mestre_.

   > [!NOTE]
   > Este artigo contém referências ao _mestre_, um termo que a Microsoft não usa mais. Quando o termo for removido do software, também o removeremos deste artigo.
   
3. Edite o conteúdo do artigo de acordo com as [noções básicas de redução](#markdown-basics).

4. Atualize os metadados na parte superior de cada artigo:

   * **título**: título da página que aparece na guia do navegador quando o artigo está sendo exibido. Os títulos de página são usados para SEO e indexação, portanto, não altere o título, a menos que seja necessário (embora isso seja menos crítico antes que a documentação fique pública).
   * **Descrição**: escreva uma breve descrição do conteúdo do artigo, que aumenta a SEO e a descoberta.
   * **autor**: se você for o proprietário principal da página, adicione seu alias de GitHub aqui.
   * **MS. Author**: se você for o proprietário principal da página, adicione seu alias da Microsoft aqui (você não precisa @microsoft.com , apenas o alias).
   * **MS. Date**: Atualize a data se você estiver adicionando conteúdo principal à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.
   * **palavras-** chave: o Word ajuda na SEO (otimização do mecanismo de pesquisa). Adicione palavras-chave, separadas por uma vírgula e um espaço, que são específicos do seu artigo, mas sem pontuação após a última palavra-chave em sua lista. Você não precisa adicionar palavras-chave globais que se aplicam a todos os artigos, pois elas são gerenciadas em outro lugar. 
   
5. Depois de concluir as edições do artigo, role para baixo e selecione **propor alteração de arquivo**.

6. Na página seguinte, selecione **criar solicitação de pull** para mesclar seu Branch criado automaticamente no Branch padrão, _mestre_.

7. Repita as etapas acima para o próximo artigo que você deseja editar.

## <a name="renaming-or-deleting-an-existing-article"></a>Renomeando ou excluindo um artigo existente

Se sua alteração for renomear ou excluir um artigo existente, certifique-se de adicionar um redirecionamento. Dessa forma, qualquer pessoa com um link para o artigo existente ainda será encerrada no lugar certo. Os redirecionamentos são gerenciados pelo .openpublishing.redirection.jsno arquivo na raiz do repositório.

Para adicionar um redirecionamento para .openpublishing.redirection.jsem, adicione uma entrada à `redirections` matriz:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- O `source_path` é o caminho relativo do repositório para o artigo antigo que você está removendo. Verifique se o caminho começa com `mixed-reality-docs` e termina com `.md` .

- O `redirect_url` é a URL pública relativa do artigo antigo para o novo artigo. Certifique-se de que essa URL **não** contenha `mixed-reality-docs` ou `.md` , como se refere à URL pública e não ao caminho do repositório. É permitido vincular a uma seção dentro do novo artigo usando `#section` . Você também pode usar um caminho absoluto para outro site aqui, se necessário.

- `redirect_document_id` indica se você deseja manter a ID do documento do arquivo anterior. O padrão é `false`. Use `true` se você quiser preservar o `ms.documentid` valor do atributo do artigo Redirecionado. Se você preservar a ID do documento, os dados, como exibições de página e classificações, serão transferidos para o artigo de destino. Faça isso se o redirecionamento for principalmente renomeado e não um ponteiro para um artigo diferente que abrange apenas parte do mesmo conteúdo.

Se você adicionar um redirecionamento, certifique-se de excluir o arquivo antigo também.

## <a name="creating-a-new-article"></a>Criando um novo artigo

Use o fluxo de trabalho a seguir para *criar novos artigos* no repositório de documentação via GitHub em um navegador da web:

1. Crie uma bifurcação do Branch padrão, _mestre_, de MicrosoftDocs/Mixed-Realm usando o botão **bifurcar** no canto superior direito.

   ![Bifurcar o Branch padrão, atualmente denominado "Master".](images/forkbranch.png)

   > [!NOTE]
   > Este artigo contém referências ao _mestre_, um termo que a Microsoft não usa mais. Quando o termo for removido do software, também o removeremos deste artigo.
   
2. Na pasta "Mixed-Reality-docs", selecione **criar novo arquivo** no canto superior direito.

3. Crie um nome de página para o artigo (use hifens em vez de espaços e não use pontuação ou apóstrofos) e acrescente ". MD"

   ![Nomeie sua nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Certifique-se de criar o novo artigo de dentro da pasta "Mixed-Realm docs". Você pode confirmar isso verificando "/Mixed-Reality-docs/" na nova linha de nome de arquivo.

4. Na parte superior da sua nova página, adicione o seguinte bloco de metadados:

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. Preencha os campos de metadados relevantes, conforme descrito anteriormente, em [editando um artigo existente](#editing-an-existing-article).

6. Escreva o conteúdo do artigo usando [noções básicas de redução](#markdown-basics).

7. Adicione uma `## See also` seção na parte inferior do artigo com links para outros artigos relevantes.

8. Quando terminar, selecione **confirmar novo arquivo**.

9. Selecione **nova solicitação de pull** e mescle o Branch _mestre_ da bifurcação no _mestre_ MicrosoftDocs/Mixed-Realm (verifique se a seta está apontando para o destino correto).

   ![Crie uma solicitação de pull de sua bifurcação em MicrosoftDocs/Mixed-Reality.](images/pr-to-master.png)

## <a name="markdown-basics"></a>Noções básicas de markdown

Os recursos a seguir ajudarão você a aprender a editar a documentação usando a linguagem de redução:

- [Noções básicas de Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Recursos adicionais para a redução do texto para docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Adicionando tabelas

Por causa da maneira como as tabelas de estilos docs.microsoft.com, elas não terão bordas ou estilos personalizados, mesmo que você experimente o CSS embutido. Parecerá funcionar por um curto período de tempo, mas eventualmente a plataforma removerá o estilo da tabela. Então, planeje com antecedência e mantenha suas tabelas simples. Aqui está um site que torna as tabelas de redução fáceis: [gerador de tabelas]] ( https://www.tablesgenerator.com/markdown_tables) .

a [extensão de redução de documentos para Visual Studio Code](/teamblog/docs-extension) também facilitará a geração de tabelas se você estiver usando [Visual Studio Code (veja abaixo)](#using-visual-studio-code) para editar a documentação.

### <a name="adding-images"></a>Adição de imagens

Você precisará carregar suas imagens na pasta "mixed-reality-docs/images" no repo e, em seguida, fazer referência a elas adequadamente no artigo. As imagens aparecerão automaticamente em tamanho total, o que significa que imagens grandes preencherão toda a largura do artigo. É recomendável pré-fazer o pré-uso de suas imagens antes de enviá-las. A largura recomendada está entre 600 e 700 pixels, embora você deva ter um tamanho para cima ou para baixo se for uma captura de tela densa ou uma fração de uma captura de tela, respectivamente.

>[!IMPORTANT]
>Você só pode carregar imagens no seu repo bifurcado antes de mesclar. Portanto, se você planeja adicionar imagens a um artigo, precisará usar o [Visual Studio Code](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" do fork primeiro ou fazer o seguinte em um navegador da Web:
>
>1. Forked the MicrosoftDocs/mixed-reality repo( Forked the MicrosoftDocs/mixed-reality repo).
>2. Editou o artigo em sua bifurcação.
>3. Carregou as imagens que você está referenciando em seu artigo para a pasta "mixed-reality-docs/images" em sua bifurcação.
>4. Criou uma **solicitação de pull** para mesclar seu fork no branch mestre MicrosoftDocs/mixed-reality. 
>
>Para saber como configurar seu próprio repo bifurcado, siga as instruções para [criar um novo artigo](#creating-a-new-article).

## <a name="previewing-your-work"></a>Visualizando seu trabalho

Durante a edição no GitHub por meio de  um navegador da Web, você pode selecionar a guia Visualização na parte superior da página para visualizar seu trabalho antes de se comprometer. 

>[!NOTE]
>Visualizar as alterações no review.docs.microsoft.com está disponível apenas para os funcionários da Microsoft

Funcionários da Microsoft: quando suas contribuições foram mescladas no branch _padrão,_ mestre , você pode revisar o conteúdo antes que ele seja público em </hololens?branch=master>. Encontre seu artigo usando o tabela de conteúdo na coluna à esquerda.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Edição no navegador versus edição com um cliente da área de trabalho

A edição no navegador é a maneira mais fácil de fazer alterações rápidas, no entanto, há algumas desvantagens:

- Você não obterá a verificação ort ort só.
- Você não tem nenhuma vinculação inteligente a outros artigos (você precisa digitar manualmente o nome do arquivo do artigo).
- Pode ser um problema carregar e referenciar imagens.

Se você preferir não lidar com esses problemas, use um cliente da área de trabalho [como Visual Studio Code](https://code.visualstudio.com/) com algumas extensões úteis [ao](#useful-extensions) contribuir.

## <a name="using-visual-studio-code"></a>Usar o Visual Studio Code

Pelos motivos listados [acima,](#editing-in-the-browser-vs-editing-with-a-desktop-client)você pode preferir usar um cliente da área de trabalho para editar a documentação em vez de um navegador da Web. O uso do [Visual Studio Code](https://code.visualstudio.com/) é recomendado.

### <a name="setup"></a>Instalação

Siga estas etapas para configurar Visual Studio Code para trabalhar com este repo:

1. Em um navegador da Web:
    1. Instale [o Git para seu computador.](https://git-scm.com/downloads)
    2. Instale o [Visual Studio Code](https://code.visualstudio.com/).
    3. [Bifurcar MicrosoftDocs/realidade misturada](#creating-a-new-article) se você ainda não fez isso.
    4. Na bifurcação, selecione **Clonar ou baixar** e copie a URL.
2. Crie um clone local da bifurcação Visual Studio Code:
    1. No menu **Exibir,** selecione **Paleta de Comandos**.
    2. Digite "Git: Clone".
    3. Colar a URL que você copiou.
    4. Escolha onde salvar o clone em seu computador.
    5. Selecione **Abrir o repo** no pop-up.

### <a name="editing-documentation"></a>Documentação de edição

Use o seguinte fluxo de trabalho para fazer alterações na documentação com Visual Studio Code:

>[!NOTE]
>Todas as diretrizes para [](#creating-a-new-article) [edição](#editing-an-existing-article) e criação de artigos e as noções básicas de edição de [Markdown,](#markdown-basics)acima, se aplica ao usar Visual Studio Code também.

1. Certifique-se de que o fork clonado esteja atualizado com o repo oficial.

   1. Em um navegador da Web, crie uma solicitação de pull para sincronizar alterações recentes de outros colaboradores no branch padrão do MicrosoftDocs/mixed-reality, mestre , para a bifurcação (certifique-se de que a seta está apontando para o destino correto).
      
      ![Sincronizar alterações do MicrosoftDocs/realidade misturada para seu fork.](images/sync-repos.png)
      
   2. No Visual Studio Code, selecione o botão de sincronização para sincronizar sua bifurcação atualizada recentemente com o clone local.
      
      ![Clique na imagem do botão de sincronização.](images/sync-clone.png)
      
2. Crie ou edite artigos em seu repo clonado usando Visual Studio Code.

   1. Edite um ou mais artigos (adicione imagens à pasta "imagens", se necessário).
   
   2. **Salve** as alterações no **Explorer.**
      
      ![Escolha "Salvar tudo" no Explorer](images/explorer-save.png)
      
   3. **Faça commit de** todas as alterações **no Controle do Código-Fonte** (escreva a mensagem de commit quando solicitado).
   
      ![Escolha "Commit all" no controle do código-fonte](images/source-control-commit.png)
      
   4. Selecione o botão **de sincronização** para sincronizar suas alterações de volta à origem (seu fork GitHub).
      
      ![Clique no botão sincronizar.](images/sync-back.png)
      
3. Em um navegador da Web, crie uma solicitação de pull para sincronizar novas alterações em seu fork de volta para MicrosoftDocs/mestre de _realidade_ misturada (certifique-se de que a seta está apontando para o destino correto).

   ![Crie uma solicitação de pull de seu fork para MicrosoftDocs/realidade misturada.](images/pr-to-master.png)

### <a name="useful-extensions"></a>Extensões úteis

As seguintes Visual Studio Code extensões são úteis ao editar a documentação:

- [Extensão Markdown do Docs para Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – use **Alt+M** para abrir um menu de opções de autor de documentos, como:
   - Pesquisar e referenciar imagens que você carregou.
   - Adicione formatação como listas, tabelas e saídas específicas de documentos, como `>[!NOTE]` .
   - Pesquisar e referenciar links internos e indicadores (links para seções específicas em uma página).
   - Erros de formatação são realçadas (passe o mouse sobre o erro para saber mais).
- [Verificador Ortônico de](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Código – palavras com ortagem inoclinada serão sublinhadas; Clique com o botão direito do mouse em uma palavra com o botão direito do mouse para alterá-la ou salvá-la no dicionário.
