---
title: Instruções de contribuição
description: Saiba como contribuir com os documentos HoloLens na plataforma docs.microsoft.com usando GitHub Markdown.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635663"
---
# <a name="contributing-to-the-hololens-documentation"></a>Contribuir com a documentação HoloLens dados

Bem-vindo à [documentação do HoloLens!](https://github.com/MicrosoftDocs/Hololens) Todos os artigos que você criar ou editar neste repo **estarão visíveis para o público.** 

HoloLens documentos são exibidos na plataforma docs.microsoft.com, que usa GitHub Markdown com recursos markdig. O conteúdo editado neste repo é formatado em páginas estilizadas que aparecem em /hololens.

Esta página aborda as etapas básicas e as diretrizes para contribuir e links para noções básicas de Markdown. Obrigado por sua contribuição!

## <a name="available-repos"></a>Repos disponíveis

| Nome do repositório | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realidade Misturada | [MicrosoftDocs/realidade misturada](/windows/mixed-reality) |
| Guia de entusiados de VR | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Antes de começar

Se você ainda não tiver uma, precisará criar uma conta [GitHub .](https://github.com/join)

>[!NOTE]
>Se você for um funcionário da Microsoft, vincule sua GitHub ao alias da Microsoft no portal de Código Aberto [da Microsoft.](https://repos.opensource.microsoft.com/) Participe das **organizações "Microsoft"** **e "MicrosoftDocs".**

Ao configurar sua conta GitHub, também recomendamos estas precauções de segurança:
- Crie uma [senha forte para sua conta GitHub .](https://github.com/settings/admin)
- [Habilita a autenticação de dois fatores.](https://github.com/settings/two_factor_authentication/configure)
- Salve seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) em um local seguro.
- Atualize [suas configurações de perfil público](https://github.com/settings/profile).
   - De definir seu nome e considere definir seu *email público* como Não mostrar meu endereço *de email*.
   - Recomendamos que você carregue uma imagem de perfil porque uma miniatura é mostrada nas páginas de documentos com as que você contribui.
- Se você planeja usar a linha de comando, considere configurar o [Git Gerenciador de Credenciais para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Dessa forma, você não precisa inserir sua senha sempre que fizer uma contribuição.

O sistema de publicação está vinculado GitHub, portanto, essas etapas são importantes. Você será listado como autor ou colaborador de cada artigo usando seu alias GitHub dados.

## <a name="editing-an-existing-article"></a>Editando um artigo existente

Use o seguinte fluxo de trabalho para fazer atualizações *em um artigo existente* por meio GitHub em um navegador da Web:

1. Navegue até o artigo que você deseja editar na pasta "mixed-reality-docs".

2. Selecione o botão Editar (ícone de lápis) no canto superior direito, que bifurca automaticamente um branch descartável do branch 'mestre'.

   ![Edite um artigo.](images/editpage.png)
   
3. Edite o conteúdo do artigo de acordo com [as "Noções básicas de Markdown".](#markdown-basics)

4. Atualize os metadados na parte superior de cada artigo:

   * **título:** título da página que aparece na guia do navegador quando o artigo está sendo exibido. Os títulos de página são usados para SEO e indexação, portanto, não altere o título, a menos que necessário (embora isso seja menos crítico antes que a documentação seja pública).
   * **description**: escreva uma breve descrição do conteúdo do artigo, o que aumenta o SEO e a descoberta.
   * **author**: se você for o proprietário principal da página, adicione seu alias GitHub aqui.
   * **ms.author:** se você for o proprietário principal da página, adicione o alias da Microsoft aqui (você não precisa @microsoft.com apenas do alias).
   * **ms.date:** atualize a data se você estiver adicionando conteúdo principal à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.
   * **palavras-chave:** as palavras-chave auxiliam no SEO (otimização do mecanismo de pesquisa). Adicione palavras-chave, separadas por uma vírgula e um espaço, que são específicas para seu artigo, mas nenhuma pontuação após a última palavra-chave em sua lista. Você não precisa adicionar palavras-chave globais que se aplicam a todos os artigos, pois eles são gerenciados em outro lugar. 
   
5. Quando você concluir as edições do artigo, role para baixo e selecione **Propor alteração de arquivo.**

6. Na próxima página, selecione Criar **solicitação de pull** para mesclar o branch criado automaticamente em 'mestre'.

7. Repita as etapas acima para o próximo artigo que você deseja editar.

## <a name="renaming-or-deleting-an-existing-article"></a>Renomeando ou excluindo um artigo existente

Se a alteração renomear ou excluir um artigo existente, adicione um redirecionamento. Dessa forma, qualquer pessoa com um link para o artigo existente ainda acabará no lugar certo. Os redirecionamentos são gerenciados pelo .openpublishing.redirection.jsno arquivo na raiz do repo.

Para adicionar um redirecionamento .openpublishing.redirection.js, adicione uma entrada à `redirections` matriz:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- O `source_path` é o caminho do repositório relativo para o artigo antigo que você está removendo. Certifique-se de que o caminho comece `mixed-reality-docs` com e termine com `.md` .

- O `redirect_url` é a URL pública relativa do artigo antigo para o novo artigo. Certifique-se de que essa URL **não contenha** ou , pois ela se refere à `mixed-reality-docs` URL pública e não ao caminho do `.md` repositório. A vinculação a uma seção dentro do novo artigo usando `#section` é permitida. Você também pode usar um caminho absoluto para outro site aqui, se necessário.

- `redirect_document_id` indica se você gostaria de manter a ID do documento do arquivo anterior. O padrão é `false`. Use `true` se você quiser preservar o valor do atributo do artigo `ms.documentid` redirecionado. Se você preservar a ID do documento, os dados, como exibições de página e classificações, serão transferidos para o artigo de destino. Faça isso se o redirecionamento for principalmente um renomeado e não um ponteiro para um artigo diferente que abrange apenas parte do mesmo conteúdo.

Se você adicionar um redirecionamento, exclua o arquivo antigo também.

## <a name="creating-a-new-article"></a>Criando um novo artigo

Use o fluxo de trabalho a *seguir para criar novos artigos* no GitHub documentação em um navegador da Web:

1. Crie um fork do branch 'mestre' MicrosoftDocs/mixed-reality (usando o **botão Bifurcar** no canto superior direito).

   ![Bifurcar o branch mestre.](images/forkbranch.png)
   
2. Na pasta "mixed-reality-docs", selecione **Criar arquivo** no canto superior direito.

3. Crie um nome de página para o artigo (use hifens em vez de espaços e não use pontuação ou apóstrofos) e anexar ".md"

   ![Nomeia sua nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Certifique-se de criar o novo artigo de dentro da pasta "mixed-reality-docs". Você pode confirmar isso verificando "/mixed-reality-docs/" na nova linha de nome de arquivo.

4. Na parte superior da nova página, adicione o seguinte bloco de metadados:

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

5. Preencha os campos de metadados relevantes de acordo com as instruções na [seção acima.](#editing-an-existing-article)

6. Escreva o conteúdo do artigo [usando noções básicas de Markdown.](#markdown-basics)

7. Adicione uma `## See also` seção na parte inferior do artigo com links para outros artigos relevantes.

8. Quando terminar, selecione **Commit new file**.

9. Selecione **Nova solicitação de pull** e mesclar o branch 'mestre' do fork em MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está apontando para o caminho correto).

   ![Criar solicitação de pull de seu fork para MicrosoftDocs/realidade misturada](images/pr-to-master.png)

## <a name="markdown-basics"></a>Noções básicas de markdown

Os recursos a seguir ajudarão você a aprender a editar a documentação usando a linguagem Markdown:

- [Noções básicas de Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Recursos adicionais para escrever Markdown para docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Adicionando tabelas

Devido à maneira como docs.microsoft.com tabelas de estilos, elas não terão bordas nem estilos personalizados, mesmo se você tentar CSS em linha. Ele parece funcionará por um curto período de tempo, mas, eventualmente, a plataforma retirará o estilo da tabela. Portanto, planeje com antecedência e mantenha as tabelas simples. [Aqui está um site que facilita as tabelas de Markdown.](https://www.tablesgenerator.com/markdown_tables)

A Extensão Markdown do [Docs para Visual Studio Code](/teamblog/docs-extension) também facilita a geração de tabelas se você estiver usando Visual Studio Code [(veja abaixo)](#using-visual-studio-code) para editar a documentação.

### <a name="adding-images"></a>Adição de imagens

Você precisará carregar suas imagens na pasta "mixed-reality-docs/images" no repo e, em seguida, fazer referência a elas adequadamente no artigo. As imagens aparecerão automaticamente em tamanho total, o que significa que imagens grandes preencherão toda a largura do artigo. É recomendável pré-fazer o pré-sizing das imagens antes de enviá-las. A largura recomendada está entre 600 e 700 pixels, embora você deva ter um tamanho para cima ou para baixo se for uma captura de tela densa ou uma fração de uma captura de tela, respectivamente.

>[!IMPORTANT]
>Você só pode carregar imagens no seu repo bifurcado antes de mesclar. Portanto, se você planeja adicionar imagens a um artigo, precisará usar o [Visual Studio Code](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" do fork primeiro ou fazer o seguinte em um navegador da Web:
>
>1. Forked the MicrosoftDocs/mixed-reality repo( Forked the MicrosoftDocs/mixed-reality repo).
>2. Editou o artigo em sua bifurcação.
>3. Carregou as imagens que você está referenciando em seu artigo para a pasta "mixed-reality-docs/images" em sua bifurcação.
>4. Criou uma **solicitação de pull** para mesclar seu fork no branch 'mestre' MicrosoftDocs/mixed-reality.
>
>Para saber como configurar seu próprio repo bifurcado, siga as instruções para [criar um novo artigo](#creating-a-new-article).

## <a name="previewing-your-work"></a>Visualizando seu trabalho

Durante a edição no GitHub por meio de um  navegador da Web, você pode selecionar a guia Visualização na parte superior da página para visualizar seu trabalho antes de se comprometer. 

>[!NOTE]
>Visualizar suas alterações no review.docs.microsoft.com está disponível apenas para funcionários da Microsoft

Funcionários da Microsoft: depois que suas contribuições foram mescladas no branch "mestre", você pode revisar o conteúdo antes que ele seja público em </hololens?branch=master>. Encontre seu artigo usando o tabela de conteúdo na coluna à esquerda.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Edição no navegador versus edição com um cliente da área de trabalho

A edição no navegador é a maneira mais fácil de fazer alterações rápidas, no entanto, há algumas desvantagens:

- Você não obterá a verificação ort ort só.
- Você não tem nenhuma vinculação inteligente a outros artigos (você precisa digitar manualmente o nome do arquivo do artigo).
- Pode ser um problema carregar e referenciar imagens.

Se você preferir não lidar com esses problemas, use um cliente da área de trabalho [como Visual Studio Code](https://code.visualstudio.com/) com algumas extensões úteis [ao](#useful-extensions) contribuir.

## <a name="using-visual-studio-code"></a>Usar o Visual Studio Code

Pelos motivos listados [acima,](#editing-in-the-browser-vs-editing-with-a-desktop-client)você pode preferir usar um cliente da área de trabalho para editar a documentação em vez de um navegador da Web. É recomendável usar [Visual Studio Code](https://code.visualstudio.com/).

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

   1. Em um navegador da Web, crie uma solicitação de pull para sincronizar alterações recentes de outros colaboradores no MicrosoftDocs/mixed-reality 'master' para sua bifurcação (certifique-se de que a seta está apontando para a direita).
      
      ![Sincronizar alterações do MicrosoftDocs/realidade misturada para sua bifurcação](images/sync-repos.png)
      
   2. No Visual Studio Code, selecione o botão de sincronização para sincronizar sua bifurcação atualizada recentemente com o clone local.
      
      ![Clique na imagem do botão de sincronização](images/sync-clone.png)
      
2. Crie ou edite artigos em seu repo clonado usando Visual Studio Code.

   1. Edite um ou mais artigos (adicione imagens à pasta "imagens", se necessário).
   
   2. **Salve** as alterações no **Explorer.**
      
      ![Escolha "Salvar tudo" no Explorer](images/explorer-save.png)
      
   3. **Faça commit de** todas as alterações **no Controle do Código-Fonte** (escreva a mensagem de commit quando solicitado).
   
      ![Escolha "Commit all" no controle do código-fonte](images/source-control-commit.png)
      
   4. Selecione o botão **de sincronização** para sincronizar suas alterações de volta à origem (seu fork GitHub).
      
      ![Clique no botão de sincronização](images/sync-back.png)
      
3. Em um navegador da Web, crie uma solicitação de pull para sincronizar novas alterações em seu fork de volta para MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está apontando para o caminho correto).

   ![Criar solicitação de pull de seu fork para MicrosoftDocs/realidade misturada](images/pr-to-master.png)

### <a name="useful-extensions"></a>Extensões úteis

As seguintes Visual Studio Code extensões são úteis ao editar a documentação:

- [Extensão Markdown do Docs para Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – use **Alt+M** para abrir um menu de opções de autor de documentos, como:
   - Pesquisar e referenciar imagens que você carregou.
   - Adicione formatação como listas, tabelas e saídas específicas de documentos, como `>[!NOTE]` .
   - Pesquisar e referenciar links internos e indicadores (links para seções específicas em uma página).
   - Erros de formatação são realçadas (passe o mouse sobre o erro para saber mais).
- [Verificador Ortônico de](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Código – palavras com ortagem inoclinada serão sublinhadas; Clique com o botão direito do mouse em uma palavra com o botão direito do mouse para alterá-la ou salvá-la no dicionário.
