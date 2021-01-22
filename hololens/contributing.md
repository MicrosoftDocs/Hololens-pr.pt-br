---
title: Instruções de contribuição
description: Saiba como contribuir com os documentos do HoloLens na plataforma docs.microsoft.com usando o Markdown com o gitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283652"
---
# Contribuir para a documentação do HoloLens

Bem-vindo à [documentação do HoloLens](https://github.com/MicrosoftDocs/Hololens)! Todos os artigos que você criar ou editar nesse repo **estarão visíveis ao público.** 

Os documentos do HoloLens são exibidos na plataforma docs.microsoft.com, que usa Markdown do gitHub com recursos markdig. O conteúdo editado nesse repo é formatado em páginas estilizadas que aparecem em https://docs.microsoft.com/hololens . 

Esta página aborda as etapas básicas e as diretrizes para contribuir e links para noções básicas do Markdown. Obrigado por sua contribuição!

## Pos disponíveis

| Nome do repositório | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realidade Misturada | [MicrosoftDocs/realidade misturada](https://docs.microsoft.com/windows/mixed-reality) |
| Guia de entusiastas de VR | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Antes de começar

Se você ainda não tiver uma, precisará criar [uma conta do GitHub.](https://github.com/join)

>[!NOTE]
>Se você for um funcionário da Microsoft, vincule sua conta do GitHub ao alias da Microsoft no [portal do Microsoft Open Source.](https://repos.opensource.microsoft.com/) Participe das **organizações "Microsoft"** **e "MicrosoftDocs".**

Ao configurar sua conta do GitHub, também recomendamos estas precauções de segurança:
- Crie uma [senha forte para sua conta do GitHub.](https://github.com/settings/admin)
- [Habilitar a autenticação de dois fatores.](https://github.com/settings/two_factor_authentication/configure)
- Salve seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) em um local seguro.
- Atualize suas [configurações de perfil público.](https://github.com/settings/profile)
   - De definir seu nome e considere configurar seu *email público* para Não mostrar meu endereço *de email.*
   - Recomendamos que você carregue uma imagem de perfil porque uma miniatura é mostrada nas páginas de documentos para as as que você contribuiu.
- Se você planeja usar a linha de comando, considere configurar o [Gerenciador de Credenciais do Git para Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Dessa forma, você não terá que inserir sua senha sempre que fizer uma contribuição.

O sistema de publicação está vinculado ao GitHub, portanto, estas etapas são importantes. Você será listado como autor ou colaborador de cada artigo usando o alias do GitHub.

## Editando um artigo existente

Use o fluxo de trabalho a seguir para fazer atualizações *em um artigo existente* por meio do GitHub em um navegador da Web:

1. Navegue até o artigo que você deseja editar na pasta "mixed-reality-docs".

2. Selecione o botão de edição (ícone de lápis) no canto superior direito, que bifurca automaticamente uma ramificação ramificada ramificada do 'mestre'.

   ![Edite um artigo.](images/editpage.png)
   
3. Edite o conteúdo do artigo de acordo com [as "noções básicas do Markdown".](#markdown-basics)

4. Atualize os metadados na parte superior de cada artigo:

   * **título:** título da página que aparece na guia do navegador quando o artigo está sendo exibido. Títulos de página são usados para SEO e indexação, portanto, não altere o título, a menos que seja necessário (embora isso seja menos crítico antes que a documentação seja pública).
   * **description**: Escreva uma breve descrição do conteúdo do artigo, o que aumenta a SEO e a descoberta.
   * **author**: Se você for o proprietário principal da página, adicione seu alias do GitHub aqui.
   * **ms.author:** se você for o proprietário principal da página, adicione seu alias da Microsoft aqui (você não precisa de @microsoft.com, apenas o alias).
   * **ms.date:** atualize a data se você estiver adicionando conteúdo principal à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.
   * **palavras-chave:** as palavras-chave auxiliam no SEO (otimização do mecanismo de pesquisa). Adicione palavras-chave, separadas por uma vírgula e um espaço, que são específicas para seu artigo, mas sem pontuação após a última palavra-chave em sua lista. Você não precisa adicionar palavras-chave globais que se apliquem a todos os artigos, pois elas são gerenciadas em outro lugar. 
   
5. Quando você concluir as edições do artigo, role para baixo e selecione **Propor alteração de arquivo.**

6. Na próxima página, selecione **Criar solicitação pull** para mesclar sua ramificação criada automaticamente em 'mestre'.

7. Repita as etapas acima para o próximo artigo que você deseja editar.

## Renomeando ou excluindo um artigo existente

Se a alteração renomear ou excluir um artigo existente, certifique-se de adicionar um redirecionamento. Dessa forma, qualquer pessoa com um link para o artigo existente ainda acabará no lugar certo. Os redirecionamentos são gerenciados .openpublishing.redirection.jsarquivo on na raiz do repo.

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

- Este `source_path` é o caminho do repositório relativo para o artigo antigo que você está removendo. Certifique-se de que o caminho comece `mixed-reality-docs` com e termine com `.md` .

- Essa `redirect_url` é a URL pública relativa do artigo antigo para o novo artigo. Certifique-se de que essa URL **não contenha** ou , como ela se refere à URL pública `mixed-reality-docs` e não ao caminho do `.md` repositório. É permitido vincular a uma seção no novo artigo `#section` que usa. Você também pode usar um caminho absoluto para outro site aqui, se necessário.

- `redirect_document_id` indica se você gostaria de manter a ID do documento do arquivo anterior. O padrão é `false` . Use `true` se quiser preservar o valor do atributo do artigo `ms.documentid` redirecionado. Se você preservar a ID do documento, os dados, como exibições de página e classificações, serão transferidos para o artigo de destino. Faça isso se o redirecionamento for principalmente um renomeado, e não um ponteiro para um artigo diferente que abrange apenas parte do mesmo conteúdo.

Se você adicionar um redirecionamento, certifique-se de excluir o arquivo antigo também.

## Criando um novo artigo

Use o fluxo de trabalho a seguir *para criar novos artigos* no repositório de documentação por meio do GitHub em um navegador da Web:

1. Crie uma bifurcação na ramificação "mestre" do MicrosoftDocs/realidade misturada (usando o botão **Bifurcação** no canto superior direito).

   ![Bifurcar a ramificação mestra.](images/forkbranch.png)
   
2. Na pasta "mixed-reality-docs", selecione **Criar novo arquivo** no canto superior direito.

3. Crie um nome de página para o artigo (use hifens em vez de espaços e não use pontuação ou apóstrofos) e aend ".md"

   ![Nome da nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Certifique-se de criar o novo artigo na pasta "mixed-reality-docs". Você pode confirmar isso verificando "/mixed-reality-docs/" na nova linha de nome de arquivo.

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

6. Escrever conteúdo de artigo usando [noções básicas do Markdown.](#markdown-basics)

7. Adicione uma `## See also` seção na parte inferior do artigo com links para outros artigos relevantes.

8. Quando terminar, selecione **Commit new file**.

9. Selecione **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).

   ![Criar solicitação pull de sua bifurcação para o MicrosoftDocs/realidade misturada](images/pr-to-master.png)

## Noções básicas de Markdown

Os seguintes recursos o ajudarão a aprender a editar a documentação usando o idioma markdown:

- [Noções básicas de Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Recursos adicionais para escrever Markdown para docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Adicionando tabelas

Devido à maneira como docs.microsoft.com estilos de tabelas, elas não terão bordas ou estilos personalizados, mesmo que você tente css em linha. Ele parece funcionar por um curto período de tempo, mas eventualmente a plataforma retirará o estilo da tabela. Portanto, planeje com antecedência e mantenha suas tabelas simples. [Aqui está um site que facilita as tabelas de Markdown.](https://www.tablesgenerator.com/markdown_tables)

A [Extensão de Markdown](https://docs.microsoft.com/teamblog/docs-extension) de Documentos para Visual Studio Code também facilita a geração de tabela se você estiver usando o [Visual Studio Code (veja abaixo)](#using-visual-studio-code) para editar a documentação.

### Adicionando imagens

Você precisará carregar suas imagens na pasta "mixed-reality-docs/images" no repo e, em seguida, fazer referência a elas adequadamente no artigo. As imagens aparecerão automaticamente em tamanho total, o que significa que imagens grandes preencherão toda a largura do artigo. Recomendamos pré-reizing suas imagens antes de enviá-las. A largura recomendada é entre 600 e 700 pixels, embora você deva ser tamanho para cima ou para baixo se for uma captura de tela densa ou uma fração de uma captura de tela, respectivamente.

>[!IMPORTANT]
>Você só pode carregar imagens no seu repo bifurcado antes de mesclar. Portanto, se você planeja adicionar imagens a um artigo, precisará usar o [Visual Studio Code](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" da bifurcação primeiro ou certifique-se de ter feito o seguinte em um navegador da Web:
>
>1. Bifurcado o microsoftDocs/repo de realidade misturada.
>2. Editou o artigo em sua bifurcação.
>3. Carreguei as imagens que você está fazendo referência em seu artigo para a pasta "mixed-reality-docs/images" na bifurcação.
>4. Criou uma **solicitação pull** para mesclar sua bifurcação com o branch "mestre" do MicrosoftDocs/realidade misturada.
>
>Para saber como configurar seu próprio repo bifurcado, siga as instruções para [criar um novo artigo.](#creating-a-new-article)

## Visualizando seu trabalho

Durante a edição no GitHub por meio **** de um navegador da Web, você pode selecionar a guia Visualização na parte superior da página para visualizar seu trabalho antes de se comprometer. 

>[!NOTE]
>Visualizar suas alterações no review.docs.microsoft.com está disponível apenas para funcionários da Microsoft

Funcionários da Microsoft: depois que suas contribuições são mescladas na ramificação "mestre", você pode revisar o conteúdo antes que ele seja público em https://review.docs.microsoft.com/hololens?branch=master . Encontre seu artigo usando o índice na coluna esquerda.

## Edição no navegador versus edição com um cliente da área de trabalho

A edição no navegador é a maneira mais fácil de fazer alterações rápidas, no entanto, há algumas desvantagens:

- Você não obterá a verificação ort três ou mais.
- Você não tem nenhuma vinculação inteligente a outros artigos (você precisa digitar manualmente o nome de arquivo do artigo).
- Pode ser um problema carregar e referenciar imagens.

Se você preferir não lidar com esses problemas, use um cliente da área de trabalho como o [Visual Studio Code](https://code.visualstudio.com/) com algumas extensões úteis ao contribuir. [](#useful-extensions)

## Usando o Visual Studio Code

Pelos motivos listados [acima,](#editing-in-the-browser-vs-editing-with-a-desktop-client)você pode preferir usar um cliente da área de trabalho para editar a documentação em vez de um navegador da Web. Recomendamos usar [o Visual Studio Code.](https://code.visualstudio.com/)

### Configuração

Siga estas etapas para configurar o Visual Studio Code para trabalhar com esse repo:

1. Em um navegador da Web:
    1. Instale [o Git para seu computador.](https://git-scm.com/downloads)
    2. Instale [o Visual Studio Code.](https://code.visualstudio.com/)
    3. [Bifurcar MicrosoftDocs/realidade misturada,](#creating-a-new-article) se você ainda não o fez.
    4. Na bifurcação, selecione **Clone ou baixe** e copie a URL.
2. Crie um clone local da bifurcação no Visual Studio Code:
    1. No menu **Exibir,** selecione **Paleta de Comandos.**
    2. Digite "Git: Clone".
    3. Colar a URL que você copiou.
    4. Escolha onde salvar o clone em seu computador.
    5. Selecione **Abrir o repo** no pop-up.

### Documentação de edição

Use o fluxo de trabalho a seguir para fazer alterações na documentação com o Visual Studio Code:

>[!NOTE]
>Todas as diretrizes para [](#creating-a-new-article) [edição](#editing-an-existing-article) e criação de artigos e as noções básicas de edição do [Markdown](#markdown-basics)acima se aplica ao usar o Visual Studio Code também.

1. Certifique-se de que a bifurcação clonada esteja atualizada com o repo oficial.

   1. Em um navegador da Web, crie uma solicitação pull para sincronizar as alterações recentes de outros colaboradores no MicrosoftDocs/'mestre' de realidade misturada para sua bifurcação (certifique-se de que a seta está apontando para a direita).
      
      ![Sincronizar alterações do MicrosoftDocs/realidade misturada com sua bifurcação](images/sync-repos.png)
      
   2. No Visual Studio Code, selecione o botão de sincronização para sincronizar sua bifurcação atualizada para o clone local.
      
      ![Clique na imagem do botão de sincronização](images/sync-clone.png)
      
2. Crie ou edite artigos no seu repo clonado usando o Visual Studio Code.

   1. Edite um ou mais artigos (adicione imagens à pasta "imagens", se necessário).
   
   2. **Salvar** alterações no **Explorer**.
      
      ![Escolha "Salvar tudo" no Explorer](images/explorer-save.png)
      
   3. **Commit all** changes in **Source Control** (write commit message when prompted).
   
      ![Choose "Commit all" in Source Control](images/source-control-commit.png)
      
   4. Selecione o **botão de** sincronização para sincronizar suas alterações de volta à origem (sua bifurcação no GitHub).
      
      ![Clique no botão de sincronização](images/sync-back.png)
      
3. Em um navegador da Web, crie uma solicitação pull para sincronizar novas alterações em sua bifurcação de volta para MicrosoftDocs/'mestre' de realidade misturada (certifique-se de que a seta está apontando para a maneira correta).

   ![Criar solicitação pull de sua bifurcação para o MicrosoftDocs/realidade misturada](images/pr-to-master.png)

### Extensões úteis

As seguintes extensões do Visual Studio Code são úteis ao editar a documentação:

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:
   - Pesquisar e referenciar imagens que você carregou.
   - Adicionar formatação como listas, tabelas e explicações específicas de documentos, como `>[!NOTE]` .
   - Pesquisar e referenciar links internos e indicadores (links para seções específicas em uma página).
   - Os erros de formatação são realçados (passe o mouse sobre o erro para saber mais).
- [Verificador Ortônico de](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Código - as palavras com ortização inserida serão sublinhadas; clique com o botão direito do mouse em uma palavra com o botão direito do mouse para alterá-la ou salvá-la no dicionário.
