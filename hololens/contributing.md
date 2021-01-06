---
title: Instruções de contribuição
description: Saiba como contribuir com os documentos do HoloLens na plataforma docs.microsoft.com usando a redução do GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 311da6bc52098d5ba16e4684f68fec9a01e7c23b
ms.sourcegitcommit: 8cea4c04c6d2e22225f4de43e10c05dab840736a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253805"
---
# <span data-ttu-id="34d74-103">Contribuindo para a documentação do HoloLens</span><span class="sxs-lookup"><span data-stu-id="34d74-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="34d74-104">Bem-vindo à [documentação do HoloLens](https://github.com/MicrosoftDocs/Hololens)!</span><span class="sxs-lookup"><span data-stu-id="34d74-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="34d74-105">Os artigos que você criar ou editar nesse repositório ficarão **visíveis para o público.**</span><span class="sxs-lookup"><span data-stu-id="34d74-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="34d74-106">Os documentos do HoloLens são exibidos na plataforma docs.microsoft.com, que usa a redução do intipo de GitHub com recursos do Markdig.</span><span class="sxs-lookup"><span data-stu-id="34d74-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="34d74-107">O conteúdo editado neste repositório é formatado em páginas estilizadas que aparecem em https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="34d74-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="34d74-108">Esta página aborda as etapas básicas e diretrizes para contribuição e links para noções básicas de redução.</span><span class="sxs-lookup"><span data-stu-id="34d74-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="34d74-109">Obrigado pela sua contribuição!</span><span class="sxs-lookup"><span data-stu-id="34d74-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="34d74-110">Disponível repositórios</span><span class="sxs-lookup"><span data-stu-id="34d74-110">Available repos</span></span>

| <span data-ttu-id="34d74-111">Nome do repositório</span><span class="sxs-lookup"><span data-stu-id="34d74-111">Repository name</span></span> | <span data-ttu-id="34d74-112">URL</span><span class="sxs-lookup"><span data-stu-id="34d74-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="34d74-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="34d74-113">HoloLens</span></span> | [<span data-ttu-id="34d74-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="34d74-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="34d74-115">Realidade Misturada</span><span class="sxs-lookup"><span data-stu-id="34d74-115">Mixed Reality</span></span> | [<span data-ttu-id="34d74-116">MicrosoftDocs/Mixed-realidade</span><span class="sxs-lookup"><span data-stu-id="34d74-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="34d74-117">Guia de entusiastas da VR</span><span class="sxs-lookup"><span data-stu-id="34d74-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="34d74-118">MicrosoftDocs/misto-guia de realidade/entusiasta</span><span class="sxs-lookup"><span data-stu-id="34d74-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="34d74-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="34d74-119">Before you start</span></span>

<span data-ttu-id="34d74-120">Se ainda não tiver uma, você precisará [criar uma conta do GitHub](https://github.com/join).</span><span class="sxs-lookup"><span data-stu-id="34d74-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="34d74-121">Se você for um funcionário da Microsoft, vincule sua conta do GitHub ao seu alias da Microsoft no [portal de código-fonte Microsoft aberto](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="34d74-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="34d74-122">Junte-se às organizações **"Microsoft"** e **"MicrosoftDocs"** .</span><span class="sxs-lookup"><span data-stu-id="34d74-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="34d74-123">Ao configurar sua conta do GitHub, também recomendamos estas precauções de segurança:</span><span class="sxs-lookup"><span data-stu-id="34d74-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="34d74-124">Crie uma [senha forte para a sua conta do GitHub](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="34d74-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="34d74-125">Habilite [a autenticação de dois fatores](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="34d74-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="34d74-126">Salve seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="34d74-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="34d74-127">Atualize [as configurações do seu perfil público](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="34d74-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="34d74-128">Defina seu nome e considere configurar seu *email público* para *não mostrar meu endereço de email*.</span><span class="sxs-lookup"><span data-stu-id="34d74-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="34d74-129">Recomendamos carregar uma imagem de perfil porque uma miniatura é mostrada em páginas de docs às quais você contribui.</span><span class="sxs-lookup"><span data-stu-id="34d74-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="34d74-130">Se você planeja usar a linha de comando, considere configurar o [Gerenciador de credenciais git para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="34d74-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="34d74-131">Dessa forma, você não precisará inserir a senha toda vez que fizer uma contribuição.</span><span class="sxs-lookup"><span data-stu-id="34d74-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="34d74-132">O sistema de publicação está vinculado ao GitHub, portanto, essas etapas são importantes.</span><span class="sxs-lookup"><span data-stu-id="34d74-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="34d74-133">Você será listado como autor ou colaborador de cada artigo usando seu alias do GitHub.</span><span class="sxs-lookup"><span data-stu-id="34d74-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="34d74-134">Editando um artigo existente</span><span class="sxs-lookup"><span data-stu-id="34d74-134">Editing an existing article</span></span>

<span data-ttu-id="34d74-135">Use o fluxo de trabalho a seguir para fazer atualizações em *um artigo existente* por meio do GitHub em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="34d74-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="34d74-136">Navegue até o artigo que você deseja editar na pasta "Mixed-Reality-docs".</span><span class="sxs-lookup"><span data-stu-id="34d74-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="34d74-137">Selecione o botão Editar (ícone de lápis) no canto superior direito, que bifurcará automaticamente uma ramificação descartável da ramificação ' mestre '.</span><span class="sxs-lookup"><span data-stu-id="34d74-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Editar um artigo.](images/editpage.png)
   
3. <span data-ttu-id="34d74-139">Edite o conteúdo do artigo de acordo com o ["básico de redução"](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="34d74-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="34d74-140">Atualize os metadados na parte superior de cada artigo:</span><span class="sxs-lookup"><span data-stu-id="34d74-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="34d74-141">**título**: o título da página que aparece na guia do navegador quando o artigo está sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="34d74-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="34d74-142">Os títulos de página são usados para SEO e indexação, portanto, não altere o título, a menos que seja necessário (embora isso seja menos crítico antes que a documentação fique pública).</span><span class="sxs-lookup"><span data-stu-id="34d74-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="34d74-143">**Descrição**: escreva uma breve descrição do conteúdo do artigo, que aumenta a SEO e a descoberta.</span><span class="sxs-lookup"><span data-stu-id="34d74-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="34d74-144">**autor**: se você for o proprietário principal da página, adicione o alias do GitHub aqui.</span><span class="sxs-lookup"><span data-stu-id="34d74-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="34d74-145">**MS. Author**: se você for o proprietário principal da página, adicione seu alias da Microsoft aqui (você não precisa de @microsoft. com, apenas o alias).</span><span class="sxs-lookup"><span data-stu-id="34d74-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="34d74-146">**Data MS. Date**: Atualize a data se estiver adicionando conteúdo principal à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.</span><span class="sxs-lookup"><span data-stu-id="34d74-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="34d74-147">**palavras-** chave: as palavras-chave ajudam na SEO (otimização do mecanismo de pesquisa).</span><span class="sxs-lookup"><span data-stu-id="34d74-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="34d74-148">Adicione palavras-chave, separadas por uma vírgula e um espaço, que são específicas do seu artigo, mas sem pontuação após a última palavra-chave na lista.</span><span class="sxs-lookup"><span data-stu-id="34d74-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="34d74-149">Você não precisa adicionar palavras-chave globais que se aplicam a todos os artigos, pois elas são gerenciadas em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="34d74-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="34d74-150">Quando concluir as edições do artigo, role para baixo e selecione **propor alteração de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="34d74-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="34d74-151">Na próxima página, selecione **criar solicitação pull** para mesclar sua ramificação criada automaticamente em "Master".</span><span class="sxs-lookup"><span data-stu-id="34d74-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="34d74-152">Repita as etapas acima para o próximo artigo que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="34d74-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="34d74-153">Renomear ou excluir um artigo existente</span><span class="sxs-lookup"><span data-stu-id="34d74-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="34d74-154">Se a alteração for renomear ou excluir um artigo existente, certifique-se de adicionar um redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="34d74-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="34d74-155">Dessa forma, qualquer pessoa que tenha um link para o artigo existente ainda será encerrada no lugar certo.</span><span class="sxs-lookup"><span data-stu-id="34d74-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="34d74-156">Os redirecionamentos são gerenciados pelo .openpublishing.redirection.jsem arquivo na raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="34d74-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="34d74-157">Para adicionar um redirecionamento para .openpublishing.redirection.jsem, adicione uma entrada à `redirections` matriz:</span><span class="sxs-lookup"><span data-stu-id="34d74-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="34d74-158">O `source_path` caminho do repositório relativo para o artigo antigo que você está removendo.</span><span class="sxs-lookup"><span data-stu-id="34d74-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="34d74-159">Certifique-se de que o caminho comece com `mixed-reality-docs` e termina com `.md` .</span><span class="sxs-lookup"><span data-stu-id="34d74-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="34d74-160">A `redirect_url` URL pública relativa do artigo antigo para o novo artigo.</span><span class="sxs-lookup"><span data-stu-id="34d74-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="34d74-161">Certifique-se de que esta URL **não** contém `mixed-reality-docs` ou `.md` , como se refere à URL pública e não ao caminho do repositório.</span><span class="sxs-lookup"><span data-stu-id="34d74-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="34d74-162">É permitido vincular a uma seção no novo artigo usando `#section` .</span><span class="sxs-lookup"><span data-stu-id="34d74-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="34d74-163">Você também pode usar um caminho absoluto para outro site aqui, se necessário.</span><span class="sxs-lookup"><span data-stu-id="34d74-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="34d74-164">indica se você deseja manter a ID do documento do arquivo anterior.</span><span class="sxs-lookup"><span data-stu-id="34d74-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="34d74-165">O padrão é `false` .</span><span class="sxs-lookup"><span data-stu-id="34d74-165">The default is `false`.</span></span> <span data-ttu-id="34d74-166">Use `true` se desejar preservar o valor de `ms.documentid` atributo do artigo Redirecionado.</span><span class="sxs-lookup"><span data-stu-id="34d74-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="34d74-167">Se você preservar a ID do documento, os dados, como modos de exibição de página e classificações, serão transferidos para o artigo de destino.</span><span class="sxs-lookup"><span data-stu-id="34d74-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="34d74-168">Faça isso se o redirecionamento for basicamente uma renomeação, e não um ponteiro para um artigo diferente que cobre apenas alguns dos mesmos conteúdos.</span><span class="sxs-lookup"><span data-stu-id="34d74-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="34d74-169">Se você adicionar um redirecionamento, certifique-se de excluir o arquivo antigo também.</span><span class="sxs-lookup"><span data-stu-id="34d74-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="34d74-170">Criando um novo artigo</span><span class="sxs-lookup"><span data-stu-id="34d74-170">Creating a new article</span></span>

<span data-ttu-id="34d74-171">Use o fluxo de trabalho a seguir para *criar novos artigos* no repositório de documentação via GitHub em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="34d74-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="34d74-172">Crie uma bifurcação para fora da ramificação ' mestre ' de realidade MicrosoftDocs/mista (usando o botão de **bifurcação** no canto superior direito).</span><span class="sxs-lookup"><span data-stu-id="34d74-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurcar a ramificação mestre.](images/forkbranch.png)
   
2. <span data-ttu-id="34d74-174">Na pasta "Mixed-Reality-docs", selecione **criar novo arquivo** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="34d74-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="34d74-175">Crie um nome de página para o artigo (use hifens em vez de espaços e não use pontuação ou apóstrofo) e acrescente ". MD"</span><span class="sxs-lookup"><span data-stu-id="34d74-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nomeie sua nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="34d74-177">Certifique-se de criar o novo artigo na pasta "Mixed-Reality-docs".</span><span class="sxs-lookup"><span data-stu-id="34d74-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="34d74-178">Você pode confirmar isso verificando "/Mixed-Reality-docs/" na nova linha de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="34d74-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="34d74-179">Na parte superior da nova página, adicione o seguinte bloco de metadados:</span><span class="sxs-lookup"><span data-stu-id="34d74-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="34d74-180">Preencha os campos de metadados relevantes, conforme as instruções na [seção acima](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="34d74-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="34d74-181">Escreva o conteúdo do artigo usando [noções básicas de redução](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="34d74-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="34d74-182">Adicione uma `## See also` seção na parte inferior do artigo com links para outros artigos relevantes.</span><span class="sxs-lookup"><span data-stu-id="34d74-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="34d74-183">Quando terminar, selecione **confirmar novo arquivo**.</span><span class="sxs-lookup"><span data-stu-id="34d74-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="34d74-184">Selecione **nova solicitação de recebimento** e mescle a ramificação ' mestre ' da sua bifurcação em MicrosoftDocs/misto-realidade ' mestra ' (certifique-se de que a seta esteja apontando da maneira correta).</span><span class="sxs-lookup"><span data-stu-id="34d74-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crie uma solicitação de recebimento da sua bifurcação para o MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

## <span data-ttu-id="34d74-186">Noções básicas sobre redução</span><span class="sxs-lookup"><span data-stu-id="34d74-186">Markdown basics</span></span>

<span data-ttu-id="34d74-187">Os recursos a seguir ajudarão você a aprender a editar a documentação usando o idioma de redução:</span><span class="sxs-lookup"><span data-stu-id="34d74-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="34d74-188">Noções básicas sobre redução</span><span class="sxs-lookup"><span data-stu-id="34d74-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="34d74-189">Recursos adicionais para a redução da redação de docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="34d74-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="34d74-190">Adicionando tabelas</span><span class="sxs-lookup"><span data-stu-id="34d74-190">Adding tables</span></span>

<span data-ttu-id="34d74-191">Devido à maneira como as tabelas de estilos docs.microsoft.com, elas não terão bordas ou estilos personalizados, mesmo se você tentar CSS embutido.</span><span class="sxs-lookup"><span data-stu-id="34d74-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="34d74-192">Parecerá funcionar por um curto período de tempo, mas eventualmente a plataforma irá remover o estilo da tabela.</span><span class="sxs-lookup"><span data-stu-id="34d74-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="34d74-193">Então planeje e mantenha suas tabelas simples.</span><span class="sxs-lookup"><span data-stu-id="34d74-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="34d74-194">[Aqui está um site que torna as tabelas de redução fáceis](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="34d74-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="34d74-195">A [extensão de redução de docs para o código do Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) também torna fácil a geração de tabelas se você estiver usando o [código do Visual Studio (veja abaixo)](#using-visual-studio-code) para editar a documentação.</span><span class="sxs-lookup"><span data-stu-id="34d74-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="34d74-196">Adicionando imagens</span><span class="sxs-lookup"><span data-stu-id="34d74-196">Adding images</span></span>

<span data-ttu-id="34d74-197">Você precisará carregar suas imagens na pasta "Mixed-real-docs/images" no repositório e, em seguida, fazer referência a elas apropriadamente no artigo.</span><span class="sxs-lookup"><span data-stu-id="34d74-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="34d74-198">As imagens serão automaticamente exibidas em tamanho máximo, o que significa que as imagens grandes preencherão toda a largura do artigo.</span><span class="sxs-lookup"><span data-stu-id="34d74-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="34d74-199">Recomendamos que você tenha dimensionado previamente as imagens antes de carregá-las.</span><span class="sxs-lookup"><span data-stu-id="34d74-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="34d74-200">A largura recomendada é entre 600 e 700 pixels, mas você deve dimensionar para cima ou para baixo se for uma captura de tela denso ou uma fração de uma captura de tela, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="34d74-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="34d74-201">Você só pode carregar imagens no repositório bifurcado antes de mesclá-las.</span><span class="sxs-lookup"><span data-stu-id="34d74-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="34d74-202">Portanto, se você planeja adicionar imagens a um artigo, precisará [usar o código do Visual Studio](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" da sua bifurcação primeiro ou garantir que você tenha feito o seguinte em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="34d74-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="34d74-203">Repositório MicrosoftDocs/misto da realidade em bifurcação.</span><span class="sxs-lookup"><span data-stu-id="34d74-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="34d74-204">Editou o artigo na sua bifurcação.</span><span class="sxs-lookup"><span data-stu-id="34d74-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="34d74-205">Carregou as imagens que você está fazendo referência ao seu artigo à pasta "Mixed Reality-docs/images" na sua bifurcação.</span><span class="sxs-lookup"><span data-stu-id="34d74-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="34d74-206">Criou uma **solicitação pull** para mesclar sua bifurcação com o Branch ' Master ' de realidade MicrosoftDocs/mista.</span><span class="sxs-lookup"><span data-stu-id="34d74-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="34d74-207">Para saber como configurar seu próprio repositório bifurcado, siga as instruções para [criar um novo artigo](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="34d74-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="34d74-208">Visualizando seu trabalho</span><span class="sxs-lookup"><span data-stu-id="34d74-208">Previewing your work</span></span>

<span data-ttu-id="34d74-209">Durante a edição no GitHub por meio de um navegador da Web, você pode selecionar a guia **Visualização** na parte superior da página para visualizar o trabalho antes de confirmá-lo.</span><span class="sxs-lookup"><span data-stu-id="34d74-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="34d74-210">Visualizar as alterações em review.docs.microsoft.com só está disponível para funcionários da Microsoft</span><span class="sxs-lookup"><span data-stu-id="34d74-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="34d74-211">Funcionários da Microsoft: quando suas contribuições forem mescladas ao Branch ' mestre ', você poderá revisar o conteúdo antes de ele ficar público https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="34d74-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="34d74-212">Encontre o artigo usando o Sumário na coluna à esquerda.</span><span class="sxs-lookup"><span data-stu-id="34d74-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="34d74-213">Editando no navegador versus editando com um cliente de desktop</span><span class="sxs-lookup"><span data-stu-id="34d74-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="34d74-214">A edição no navegador é a maneira mais fácil de fazer alterações rápidas, no entanto, há algumas desvantagens:</span><span class="sxs-lookup"><span data-stu-id="34d74-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="34d74-215">Você não recebe a verificação ortográfica.</span><span class="sxs-lookup"><span data-stu-id="34d74-215">You don't get spell-check.</span></span>
- <span data-ttu-id="34d74-216">Você não tem links inteligentes para outros artigos (você precisa digitar manualmente o nome do arquivo do artigo).</span><span class="sxs-lookup"><span data-stu-id="34d74-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="34d74-217">Pode ser um trabalho para carregar e fazer referência a imagens.</span><span class="sxs-lookup"><span data-stu-id="34d74-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="34d74-218">Se você preferir não lidar com esses problemas, use um cliente de desktop como [código do Visual Studio](https://code.visualstudio.com/) com algumas [extensões úteis](#useful-extensions) ao contribuir.</span><span class="sxs-lookup"><span data-stu-id="34d74-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="34d74-219">Usando o código do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="34d74-219">Using Visual Studio Code</span></span>

<span data-ttu-id="34d74-220">Pelos motivos listados [acima](#editing-in-the-browser-vs-editing-with-a-desktop-client), você pode preferir usar um cliente de área de trabalho para editar a documentação em vez de um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="34d74-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="34d74-221">Recomendamos o uso do [código do Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="34d74-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="34d74-222">Configuração</span><span class="sxs-lookup"><span data-stu-id="34d74-222">Setup</span></span>

<span data-ttu-id="34d74-223">Siga estas etapas para configurar o código do Visual Studio para trabalhar com esse repositório:</span><span class="sxs-lookup"><span data-stu-id="34d74-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="34d74-224">Em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="34d74-224">In a web browser:</span></span>
    1. <span data-ttu-id="34d74-225">Instale [o Git para seu PC](https://git-scm.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="34d74-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="34d74-226">Instale o [código do Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="34d74-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="34d74-227">[MicrosoftDocs de bifurcação/mistura-realidade](#creating-a-new-article) se ainda não fez isso.</span><span class="sxs-lookup"><span data-stu-id="34d74-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="34d74-228">Na sua bifurcação, selecione **clonar ou baixar** e copie a URL.</span><span class="sxs-lookup"><span data-stu-id="34d74-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="34d74-229">Crie um clone local da sua bifurcação no código do Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="34d74-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="34d74-230">No menu **Exibir** , selecione **paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="34d74-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="34d74-231">Digite "Git: clone".</span><span class="sxs-lookup"><span data-stu-id="34d74-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="34d74-232">Cole a URL que você copiou.</span><span class="sxs-lookup"><span data-stu-id="34d74-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="34d74-233">Escolha onde deseja salvar o clone em seu computador.</span><span class="sxs-lookup"><span data-stu-id="34d74-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="34d74-234">Selecione **abrir repositório** no menu pop-up.</span><span class="sxs-lookup"><span data-stu-id="34d74-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="34d74-235">Editando a documentação</span><span class="sxs-lookup"><span data-stu-id="34d74-235">Editing documentation</span></span>

<span data-ttu-id="34d74-236">Use o fluxo de trabalho a seguir para fazer alterações na documentação com o código do Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="34d74-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="34d74-237">Todas as orientações para [edição](#editing-an-existing-article) e [criação](#creating-a-new-article) de artigos, e [noções básicas de redução da edição](#markdown-basics), de cima aplicam-se ao uso do código do Visual Studio também.</span><span class="sxs-lookup"><span data-stu-id="34d74-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="34d74-238">Verifique se a bifurcação clonada está atualizada com o repositório oficial.</span><span class="sxs-lookup"><span data-stu-id="34d74-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="34d74-239">Em um navegador da Web, crie uma solicitação pull para sincronizar alterações recentes de outros colaboradores no MicrosoftDocs/real-realidade ' mestra ' em sua bifurcação (verifique se a seta está apontando da maneira correta).</span><span class="sxs-lookup"><span data-stu-id="34d74-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronizar alterações de MicrosoftDocs/Mixed-realidade para sua bifurcação](images/sync-repos.png)
      
   2. <span data-ttu-id="34d74-241">No código do Visual Studio, selecione o botão Sincronizar para sincronizar sua bifurcação atualizada recentemente para o clone local.</span><span class="sxs-lookup"><span data-stu-id="34d74-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Clique na imagem do botão Sincronizar](images/sync-clone.png)
      
2. <span data-ttu-id="34d74-243">Crie ou edite artigos no repositório clonado usando o código do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34d74-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="34d74-244">Editar um ou mais artigos (adicionar imagens à pasta "imagens", se necessário).</span><span class="sxs-lookup"><span data-stu-id="34d74-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="34d74-245">**Salvar** alterações no **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="34d74-245">**Save** changes in **Explorer**.</span></span>
      
      ![Escolha "salvar tudo" no Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="34d74-247">**Confirmar todas** as alterações no **controle do código-fonte** (gravar mensagem de confirmação quando solicitado).</span><span class="sxs-lookup"><span data-stu-id="34d74-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
      
   4. <span data-ttu-id="34d74-248">Selecione o botão **sincronizar** para sincronizar as alterações de volta à origem (sua bifurcação no GitHub).</span><span class="sxs-lookup"><span data-stu-id="34d74-248">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Clique no botão Sincronizar](images/sync-back.png)
      
3. <span data-ttu-id="34d74-250">Em um navegador da Web, crie uma solicitação pull para sincronizar novas alterações na sua bifurcação para MicrosoftDocs/Mixed-Reality ' Master ' (certifique-se de que a seta esteja apontando para a maneira correta).</span><span class="sxs-lookup"><span data-stu-id="34d74-250">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crie uma solicitação de recebimento da sua bifurcação para o MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

### <span data-ttu-id="34d74-252">Extensões úteis</span><span class="sxs-lookup"><span data-stu-id="34d74-252">Useful extensions</span></span>

<span data-ttu-id="34d74-253">As seguintes extensões de código do Visual Studio são úteis ao editar a documentação:</span><span class="sxs-lookup"><span data-stu-id="34d74-253">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="34d74-254">[Extensão de redução de docs para o código do Visual Studio](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) -use **ALT + M** para exibir um menu de opções de criação de documentos, como:</span><span class="sxs-lookup"><span data-stu-id="34d74-254">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="34d74-255">Pesquisar e fazer referência a imagens carregadas.</span><span class="sxs-lookup"><span data-stu-id="34d74-255">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="34d74-256">Adicione formatação, como listas, tabelas e chamadas específicas de documentos, como `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="34d74-256">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="34d74-257">Pesquisar e referenciar links internos e indicadores (links para seções específicas dentro de uma página).</span><span class="sxs-lookup"><span data-stu-id="34d74-257">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="34d74-258">Erros de formatação são realçados (passe o mouse sobre o erro para saber mais).</span><span class="sxs-lookup"><span data-stu-id="34d74-258">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="34d74-259">[Verificador ortográfico de código](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -as palavras incorretas serão sublinhadas; Clique com o botão direito do mouse em uma palavra incorreta para alterá-la ou salvá-la no dicionário.</span><span class="sxs-lookup"><span data-stu-id="34d74-259">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
