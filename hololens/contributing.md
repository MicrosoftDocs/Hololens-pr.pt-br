---
title: Instruções de contribuição
description: Saiba como contribuir com os documentos do HoloLens na plataforma docs.microsoft.com usando a redução do GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.openlocfilehash: d17d9e30ca3699a7bd6c69b75043c6974a2bde1f
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253605"
---
# Contribuindo para a documentação do HoloLens

Bem-vindo à [documentação do HoloLens](https://github.com/MicrosoftDocs/Hololens)! Os artigos que você criar ou editar nesse repositório ficarão **visíveis para o público.** 

Os documentos do HoloLens são exibidos na plataforma docs.microsoft.com, que usa a redução do intipo de GitHub com recursos do Markdig. O conteúdo editado neste repositório é formatado em páginas estilizadas que aparecem em https://docs.microsoft.com/hololens . 

Esta página aborda as etapas básicas e diretrizes para contribuição e links para noções básicas de redução. Obrigado pela sua contribuição!

## Disponível repositórios

| Nome do repositório | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realidade Misturada | [MicrosoftDocs/Mixed-realidade](https://docs.microsoft.com/windows/mixed-reality) |
| Guia de entusiastas da VR | [MicrosoftDocs/misto-guia de realidade/entusiasta](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Antes de começar

Se ainda não tiver uma, você precisará [criar uma conta do GitHub](https://github.com/join).

>[!NOTE]
>Se você for um funcionário da Microsoft, vincule sua conta do GitHub ao seu alias da Microsoft no [portal de código-fonte Microsoft aberto](https://repos.opensource.microsoft.com/). Junte-se às organizações **"Microsoft"** e **"MicrosoftDocs"** .

Ao configurar sua conta do GitHub, também recomendamos estas precauções de segurança:
- Crie uma [senha forte para a sua conta do GitHub](https://github.com/settings/admin).
- Habilite [a autenticação de dois fatores](https://github.com/settings/two_factor_authentication/configure).
- Salve seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) em um local seguro.
- Atualize [as configurações do seu perfil público](https://github.com/settings/profile).
   - Defina seu nome e considere configurar seu *email público* para *não mostrar meu endereço de email*.
   - Recomendamos carregar uma imagem de perfil porque uma miniatura é mostrada em páginas de docs às quais você contribui.
- Se você planeja usar a linha de comando, considere configurar o [Gerenciador de credenciais git para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Dessa forma, você não precisará inserir a senha toda vez que fizer uma contribuição.

O sistema de publicação está vinculado ao GitHub, portanto, essas etapas são importantes. Você será listado como autor ou colaborador de cada artigo usando seu alias do GitHub.

## Editando um artigo existente

Use o fluxo de trabalho a seguir para fazer atualizações em *um artigo existente* por meio do GitHub em um navegador da Web:

1. Navegue até o artigo que você deseja editar na pasta "Mixed-Reality-docs".
2. Selecione o botão Editar (ícone de lápis) no canto superior direito, que bifurcará automaticamente uma ramificação descartável da ramificação ' mestre '.

   ![Editar um artigo.](images/editpage.png)
3. Edite o conteúdo do artigo de acordo com o ["básico de redução"](#markdown-basics).
4. Atualize os metadados na parte superior de cada artigo:
   * **título**: o título da página que aparece na guia do navegador quando o artigo está sendo exibido. Os títulos de página são usados para SEO e indexação, portanto, não altere o título, a menos que seja necessário (embora isso seja menos crítico antes que a documentação fique pública).
   * **Descrição**: escreva uma breve descrição do conteúdo do artigo, que aumenta a SEO e a descoberta.
   * **autor**: se você for o proprietário principal da página, adicione o alias do GitHub aqui.
   * **MS. Author**: se você for o proprietário principal da página, adicione seu alias da Microsoft aqui (você não precisa de @microsoft. com, apenas o alias).
   * **Data MS. Date**: Atualize a data se estiver adicionando conteúdo principal à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.
   * **palavras-** chave: as palavras-chave ajudam na SEO (otimização do mecanismo de pesquisa). Adicione palavras-chave, separadas por uma vírgula e um espaço, que são específicas do seu artigo, mas sem pontuação após a última palavra-chave na lista. Você não precisa adicionar palavras-chave globais que se aplicam a todos os artigos, pois elas são gerenciadas em outro lugar. 
5. Quando concluir as edições do artigo, role para baixo e selecione **propor alteração de arquivo**.
6. Na próxima página, selecione **criar solicitação pull** para mesclar sua ramificação criada automaticamente em "Master".
7. Repita as etapas acima para o próximo artigo que você deseja editar.

## Renomear ou excluir um artigo existente

Se a alteração for renomear ou excluir um artigo existente, certifique-se de adicionar um redirecionamento. Dessa forma, qualquer pessoa que tenha um link para o artigo existente ainda será encerrada no lugar certo. Os redirecionamentos são gerenciados pelo .openpublishing.redirection.jsem arquivo na raiz do repositório.

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

- O `source_path` caminho do repositório relativo para o artigo antigo que você está removendo. Certifique-se de que o caminho comece com `mixed-reality-docs` e termina com `.md` .
- A `redirect_url` URL pública relativa do artigo antigo para o novo artigo. Certifique-se de que esta URL **não** contém `mixed-reality-docs` ou `.md` , como se refere à URL pública e não ao caminho do repositório. É permitido vincular a uma seção no novo artigo usando `#section` . Você também pode usar um caminho absoluto para outro site aqui, se necessário.
- `redirect_document_id` indica se você deseja manter a ID do documento do arquivo anterior. O padrão é `false` . Use `true` se desejar preservar o valor de `ms.documentid` atributo do artigo Redirecionado. Se você preservar a ID do documento, os dados, como modos de exibição de página e classificações, serão transferidos para o artigo de destino. Faça isso se o redirecionamento for basicamente uma renomeação, e não um ponteiro para um artigo diferente que cobre apenas alguns dos mesmos conteúdos.

Se você adicionar um redirecionamento, certifique-se de excluir o arquivo antigo também.

## Criando um novo artigo

Use o fluxo de trabalho a seguir para *criar novos artigos* no repositório de documentação via GitHub em um navegador da Web:

1. Crie uma bifurcação para fora da ramificação ' mestre ' de realidade MicrosoftDocs/mista (usando o botão de **bifurcação** no canto superior direito).

   ![Bifurcar a ramificação mestre.](images/forkbranch.png)
2. Na pasta "Mixed-Reality-docs", selecione **criar novo arquivo** no canto superior direito.
3. Crie um nome de página para o artigo (use hifens em vez de espaços e não use pontuação ou apóstrofo) e acrescente ". MD"

   ![Nomeie sua nova página.](images/newpagetitle.PNG)
   
   >[!IMPORTANT]
   >Certifique-se de criar o novo artigo na pasta "Mixed-Reality-docs". Você pode confirmar isso verificando "/Mixed-Reality-docs/" na nova linha de nome de arquivo.

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

5. Preencha os campos de metadados relevantes, conforme as instruções na [seção acima](#editing-an-existing-article).
6. Escreva o conteúdo do artigo usando [noções básicas de redução](#markdown-basics).
7. Adicione uma `## See also` seção na parte inferior do artigo com links para outros artigos relevantes.
8. Quando terminar, selecione **confirmar novo arquivo**.
9. Selecione **nova solicitação de recebimento** e mescle a ramificação ' mestre ' da sua bifurcação em MicrosoftDocs/misto-realidade ' mestra ' (certifique-se de que a seta esteja apontando da maneira correta).

   ![Crie uma solicitação de recebimento da sua bifurcação para o MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

## Noções básicas sobre redução

Os recursos a seguir ajudarão você a aprender a editar a documentação usando o idioma de redução:

- [Noções básicas sobre redução](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Cartaz de referência de redução de visão geral](images/MarkdownPoster.pdf)
- [Recursos adicionais para a redução da redação de docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Adicionando tabelas

Devido à maneira como as tabelas de estilos docs.microsoft.com, elas não terão bordas ou estilos personalizados, mesmo se você tentar CSS embutido. Parecerá funcionar por um curto período de tempo, mas eventualmente a plataforma irá remover o estilo da tabela. Então planeje e mantenha suas tabelas simples. [Aqui está um site que torna as tabelas de redução fáceis](https://www.tablesgenerator.com/markdown_tables).

A [extensão de redução de docs para o código do Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) também torna fácil a geração de tabelas se você estiver usando o [código do Visual Studio (veja abaixo)](#using-visual-studio-code) para editar a documentação.

### Adicionando imagens

Você precisará carregar suas imagens na pasta "Mixed-real-docs/images" no repositório e, em seguida, fazer referência a elas apropriadamente no artigo. As imagens serão automaticamente exibidas em tamanho máximo, o que significa que as imagens grandes preencherão toda a largura do artigo. Recomendamos que você tenha dimensionado previamente as imagens antes de carregá-las. A largura recomendada é entre 600 e 700 pixels, mas você deve dimensionar para cima ou para baixo se for uma captura de tela denso ou uma fração de uma captura de tela, respectivamente.

>[!IMPORTANT]
>Você só pode carregar imagens no repositório bifurcado antes de mesclá-las. Portanto, se você planeja adicionar imagens a um artigo, precisará [usar o código do Visual Studio](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" da sua bifurcação primeiro ou garantir que você tenha feito o seguinte em um navegador da Web:
>
>1. Repositório MicrosoftDocs/misto da realidade em bifurcação.
>2. Editou o artigo na sua bifurcação.
>3. Carregou as imagens que você está fazendo referência ao seu artigo à pasta "Mixed Reality-docs/images" na sua bifurcação.
>4. Criou uma **solicitação pull** para mesclar sua bifurcação com o Branch ' Master ' de realidade MicrosoftDocs/mista.
>
>Para saber como configurar seu próprio repositório bifurcado, siga as instruções para [criar um novo artigo](#creating-a-new-article).

## Visualizando seu trabalho

Durante a edição no GitHub por meio de um navegador da Web, você pode selecionar a guia **Visualização** na parte superior da página para visualizar o trabalho antes de confirmá-lo. 

>[!NOTE]
>Visualizar as alterações em review.docs.microsoft.com só está disponível para funcionários da Microsoft

Funcionários da Microsoft: quando suas contribuições forem mescladas ao Branch ' mestre ', você poderá revisar o conteúdo antes de ele ficar público https://review.docs.microsoft.com/hololens?branch=master . Encontre o artigo usando o Sumário na coluna à esquerda.

## Editando no navegador versus editando com um cliente de desktop

A edição no navegador é a maneira mais fácil de fazer alterações rápidas, no entanto, há algumas desvantagens:

- Você não recebe a verificação ortográfica.
- Você não tem links inteligentes para outros artigos (você precisa digitar manualmente o nome do arquivo do artigo).
- Pode ser um trabalho para carregar e fazer referência a imagens.

Se você preferir não lidar com esses problemas, use um cliente de desktop como [código do Visual Studio](https://code.visualstudio.com/) com algumas [extensões úteis](#useful-extensions) ao contribuir.

## Usando o código do Visual Studio

Pelos motivos listados [acima](#editing-in-the-browser-vs-editing-with-a-desktop-client), você pode preferir usar um cliente de área de trabalho para editar a documentação em vez de um navegador da Web. Recomendamos o uso do [código do Visual Studio](https://code.visualstudio.com/).

### Configuração

Siga estas etapas para configurar o código do Visual Studio para trabalhar com esse repositório:

1. Em um navegador da Web:
    1. Instale [o Git para seu PC](https://git-scm.com/downloads).
    2. Instale o [código do Visual Studio](https://code.visualstudio.com/).
    3. [MicrosoftDocs de bifurcação/mistura-realidade](#creating-a-new-article) se ainda não fez isso.
    4. Na sua bifurcação, selecione **clonar ou baixar** e copie a URL.
2. Crie um clone local da sua bifurcação no código do Visual Studio:
    1. No menu **Exibir** , selecione **paleta de comandos**.
    2. Digite "Git: clone".
    3. Cole a URL que você copiou.
    4. Escolha onde deseja salvar o clone em seu computador.
    5. Selecione **abrir repositório** no menu pop-up.

### Editando a documentação

Use o fluxo de trabalho a seguir para fazer alterações na documentação com o código do Visual Studio:

>[!NOTE]
>Todas as orientações para [edição](#editing-an-existing-article) e [criação](#creating-a-new-article) de artigos, e [noções básicas de redução da edição](#markdown-basics), de cima aplicam-se ao uso do código do Visual Studio também.

1. Verifique se a bifurcação clonada está atualizada com o repositório oficial.
   1. Em um navegador da Web, crie uma solicitação pull para sincronizar alterações recentes de outros colaboradores no MicrosoftDocs/real-realidade ' mestra ' em sua bifurcação (verifique se a seta está apontando da maneira correta).
      
      ![Sincronizar alterações de MicrosoftDocs/Mixed-realidade para sua bifurcação](images/sync_repos.PNG)
   2. No código do Visual Studio, selecione o botão Sincronizar para sincronizar sua bifurcação atualizada recentemente para o clone local.
      
      ![Clique na imagem do botão Sincronizar](images/sync_clone.png)
2. Crie ou edite artigos no repositório clonado usando o código do Visual Studio.
   1. Editar um ou mais artigos (adicionar imagens à pasta "imagens", se necessário).
   2. **Salvar** alterações no **Explorer**.
      
      ![Escolha "salvar tudo" no Explorer](images/explorer_save.png)
   3. **Confirmar todas** as alterações no **controle do código-fonte** (gravar mensagem de confirmação quando solicitado).
      
      ![Escolha "confirmar tudo" no controle do código-fonte](images/source_control_commit.png)
   4. Selecione o botão **sincronizar** para sincronizar as alterações de volta à origem (sua bifurcação no GitHub).
      
      ![Clique no botão Sincronizar](images/sync_back.png)
3. Em um navegador da Web, crie uma solicitação pull para sincronizar novas alterações na sua bifurcação para MicrosoftDocs/Mixed-Reality ' Master ' (certifique-se de que a seta esteja apontando para a maneira correta).

   ![Crie uma solicitação de recebimento da sua bifurcação para o MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

### Extensões úteis

As seguintes extensões de código do Visual Studio são úteis ao editar a documentação:

- [Extensão de redução de docs para o código do Visual Studio](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) -use **ALT + M** para exibir um menu de opções de criação de documentos, como:
   - Pesquisar e fazer referência a imagens carregadas.
   - Adicione formatação, como listas, tabelas e chamadas específicas de documentos, como `>[!NOTE]` .
   - Pesquisar e referenciar links internos e indicadores (links para seções específicas dentro de uma página).
   - Erros de formatação são realçados (passe o mouse sobre o erro para saber mais).
- [Verificador ortográfico de código](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -as palavras incorretas serão sublinhadas; Clique com o botão direito do mouse em uma palavra incorreta para alterá-la ou salvá-la no dicionário.
