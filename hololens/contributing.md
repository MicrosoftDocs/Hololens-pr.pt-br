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
# <span data-ttu-id="4db01-103">Contribuir para a documentação do HoloLens</span><span class="sxs-lookup"><span data-stu-id="4db01-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="4db01-104">Bem-vindo à [documentação do HoloLens](https://github.com/MicrosoftDocs/Hololens)!</span><span class="sxs-lookup"><span data-stu-id="4db01-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="4db01-105">Todos os artigos que você criar ou editar nesse repo **estarão visíveis ao público.**</span><span class="sxs-lookup"><span data-stu-id="4db01-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="4db01-106">Os documentos do HoloLens são exibidos na plataforma docs.microsoft.com, que usa Markdown do gitHub com recursos markdig.</span><span class="sxs-lookup"><span data-stu-id="4db01-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="4db01-107">O conteúdo editado nesse repo é formatado em páginas estilizadas que aparecem em https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="4db01-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="4db01-108">Esta página aborda as etapas básicas e as diretrizes para contribuir e links para noções básicas do Markdown.</span><span class="sxs-lookup"><span data-stu-id="4db01-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="4db01-109">Obrigado por sua contribuição!</span><span class="sxs-lookup"><span data-stu-id="4db01-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="4db01-110">Pos disponíveis</span><span class="sxs-lookup"><span data-stu-id="4db01-110">Available repos</span></span>

| <span data-ttu-id="4db01-111">Nome do repositório</span><span class="sxs-lookup"><span data-stu-id="4db01-111">Repository name</span></span> | <span data-ttu-id="4db01-112">URL</span><span class="sxs-lookup"><span data-stu-id="4db01-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="4db01-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="4db01-113">HoloLens</span></span> | [<span data-ttu-id="4db01-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="4db01-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="4db01-115">Realidade Misturada</span><span class="sxs-lookup"><span data-stu-id="4db01-115">Mixed Reality</span></span> | [<span data-ttu-id="4db01-116">MicrosoftDocs/realidade misturada</span><span class="sxs-lookup"><span data-stu-id="4db01-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="4db01-117">Guia de entusiastas de VR</span><span class="sxs-lookup"><span data-stu-id="4db01-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="4db01-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="4db01-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="4db01-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4db01-119">Before you start</span></span>

<span data-ttu-id="4db01-120">Se você ainda não tiver uma, precisará criar [uma conta do GitHub.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="4db01-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="4db01-121">Se você for um funcionário da Microsoft, vincule sua conta do GitHub ao alias da Microsoft no [portal do Microsoft Open Source.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="4db01-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="4db01-122">Participe das **organizações "Microsoft"** **e "MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="4db01-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="4db01-123">Ao configurar sua conta do GitHub, também recomendamos estas precauções de segurança:</span><span class="sxs-lookup"><span data-stu-id="4db01-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="4db01-124">Crie uma [senha forte para sua conta do GitHub.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="4db01-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="4db01-125">[Habilitar a autenticação de dois fatores.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="4db01-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="4db01-126">Salve seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="4db01-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="4db01-127">Atualize suas [configurações de perfil público.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="4db01-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="4db01-128">De definir seu nome e considere configurar seu *email público* para Não mostrar meu endereço *de email.*</span><span class="sxs-lookup"><span data-stu-id="4db01-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="4db01-129">Recomendamos que você carregue uma imagem de perfil porque uma miniatura é mostrada nas páginas de documentos para as as que você contribuiu.</span><span class="sxs-lookup"><span data-stu-id="4db01-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="4db01-130">Se você planeja usar a linha de comando, considere configurar o [Gerenciador de Credenciais do Git para Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="4db01-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="4db01-131">Dessa forma, você não terá que inserir sua senha sempre que fizer uma contribuição.</span><span class="sxs-lookup"><span data-stu-id="4db01-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="4db01-132">O sistema de publicação está vinculado ao GitHub, portanto, estas etapas são importantes.</span><span class="sxs-lookup"><span data-stu-id="4db01-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="4db01-133">Você será listado como autor ou colaborador de cada artigo usando o alias do GitHub.</span><span class="sxs-lookup"><span data-stu-id="4db01-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="4db01-134">Editando um artigo existente</span><span class="sxs-lookup"><span data-stu-id="4db01-134">Editing an existing article</span></span>

<span data-ttu-id="4db01-135">Use o fluxo de trabalho a seguir para fazer atualizações *em um artigo existente* por meio do GitHub em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="4db01-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="4db01-136">Navegue até o artigo que você deseja editar na pasta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="4db01-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="4db01-137">Selecione o botão de edição (ícone de lápis) no canto superior direito, que bifurca automaticamente uma ramificação ramificada ramificada do 'mestre'.</span><span class="sxs-lookup"><span data-stu-id="4db01-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Edite um artigo.](images/editpage.png)
   
3. <span data-ttu-id="4db01-139">Edite o conteúdo do artigo de acordo com [as "noções básicas do Markdown".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="4db01-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="4db01-140">Atualize os metadados na parte superior de cada artigo:</span><span class="sxs-lookup"><span data-stu-id="4db01-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="4db01-141">**título:** título da página que aparece na guia do navegador quando o artigo está sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="4db01-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="4db01-142">Títulos de página são usados para SEO e indexação, portanto, não altere o título, a menos que seja necessário (embora isso seja menos crítico antes que a documentação seja pública).</span><span class="sxs-lookup"><span data-stu-id="4db01-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="4db01-143">**description**: Escreva uma breve descrição do conteúdo do artigo, o que aumenta a SEO e a descoberta.</span><span class="sxs-lookup"><span data-stu-id="4db01-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="4db01-144">**author**: Se você for o proprietário principal da página, adicione seu alias do GitHub aqui.</span><span class="sxs-lookup"><span data-stu-id="4db01-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="4db01-145">**ms.author:** se você for o proprietário principal da página, adicione seu alias da Microsoft aqui (você não precisa de @microsoft.com, apenas o alias).</span><span class="sxs-lookup"><span data-stu-id="4db01-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="4db01-146">**ms.date:** atualize a data se você estiver adicionando conteúdo principal à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.</span><span class="sxs-lookup"><span data-stu-id="4db01-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="4db01-147">**palavras-chave:** as palavras-chave auxiliam no SEO (otimização do mecanismo de pesquisa).</span><span class="sxs-lookup"><span data-stu-id="4db01-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="4db01-148">Adicione palavras-chave, separadas por uma vírgula e um espaço, que são específicas para seu artigo, mas sem pontuação após a última palavra-chave em sua lista.</span><span class="sxs-lookup"><span data-stu-id="4db01-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="4db01-149">Você não precisa adicionar palavras-chave globais que se apliquem a todos os artigos, pois elas são gerenciadas em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="4db01-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="4db01-150">Quando você concluir as edições do artigo, role para baixo e selecione **Propor alteração de arquivo.**</span><span class="sxs-lookup"><span data-stu-id="4db01-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="4db01-151">Na próxima página, selecione **Criar solicitação pull** para mesclar sua ramificação criada automaticamente em 'mestre'.</span><span class="sxs-lookup"><span data-stu-id="4db01-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="4db01-152">Repita as etapas acima para o próximo artigo que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="4db01-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="4db01-153">Renomeando ou excluindo um artigo existente</span><span class="sxs-lookup"><span data-stu-id="4db01-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="4db01-154">Se a alteração renomear ou excluir um artigo existente, certifique-se de adicionar um redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="4db01-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="4db01-155">Dessa forma, qualquer pessoa com um link para o artigo existente ainda acabará no lugar certo.</span><span class="sxs-lookup"><span data-stu-id="4db01-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="4db01-156">Os redirecionamentos são gerenciados .openpublishing.redirection.jsarquivo on na raiz do repo.</span><span class="sxs-lookup"><span data-stu-id="4db01-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="4db01-157">Para adicionar um redirecionamento .openpublishing.redirection.js, adicione uma entrada à `redirections` matriz:</span><span class="sxs-lookup"><span data-stu-id="4db01-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="4db01-158">Este `source_path` é o caminho do repositório relativo para o artigo antigo que você está removendo.</span><span class="sxs-lookup"><span data-stu-id="4db01-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="4db01-159">Certifique-se de que o caminho comece `mixed-reality-docs` com e termine com `.md` .</span><span class="sxs-lookup"><span data-stu-id="4db01-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="4db01-160">Essa `redirect_url` é a URL pública relativa do artigo antigo para o novo artigo.</span><span class="sxs-lookup"><span data-stu-id="4db01-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="4db01-161">Certifique-se de que essa URL **não contenha** ou , como ela se refere à URL pública `mixed-reality-docs` e não ao caminho do `.md` repositório.</span><span class="sxs-lookup"><span data-stu-id="4db01-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="4db01-162">É permitido vincular a uma seção no novo artigo `#section` que usa.</span><span class="sxs-lookup"><span data-stu-id="4db01-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="4db01-163">Você também pode usar um caminho absoluto para outro site aqui, se necessário.</span><span class="sxs-lookup"><span data-stu-id="4db01-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="4db01-164">indica se você gostaria de manter a ID do documento do arquivo anterior.</span><span class="sxs-lookup"><span data-stu-id="4db01-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="4db01-165">O padrão é `false` .</span><span class="sxs-lookup"><span data-stu-id="4db01-165">The default is `false`.</span></span> <span data-ttu-id="4db01-166">Use `true` se quiser preservar o valor do atributo do artigo `ms.documentid` redirecionado.</span><span class="sxs-lookup"><span data-stu-id="4db01-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="4db01-167">Se você preservar a ID do documento, os dados, como exibições de página e classificações, serão transferidos para o artigo de destino.</span><span class="sxs-lookup"><span data-stu-id="4db01-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="4db01-168">Faça isso se o redirecionamento for principalmente um renomeado, e não um ponteiro para um artigo diferente que abrange apenas parte do mesmo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4db01-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="4db01-169">Se você adicionar um redirecionamento, certifique-se de excluir o arquivo antigo também.</span><span class="sxs-lookup"><span data-stu-id="4db01-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="4db01-170">Criando um novo artigo</span><span class="sxs-lookup"><span data-stu-id="4db01-170">Creating a new article</span></span>

<span data-ttu-id="4db01-171">Use o fluxo de trabalho a seguir *para criar novos artigos* no repositório de documentação por meio do GitHub em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="4db01-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="4db01-172">Crie uma bifurcação na ramificação "mestre" do MicrosoftDocs/realidade misturada (usando o botão **Bifurcação** no canto superior direito).</span><span class="sxs-lookup"><span data-stu-id="4db01-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurcar a ramificação mestra.](images/forkbranch.png)
   
2. <span data-ttu-id="4db01-174">Na pasta "mixed-reality-docs", selecione **Criar novo arquivo** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="4db01-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="4db01-175">Crie um nome de página para o artigo (use hifens em vez de espaços e não use pontuação ou apóstrofos) e aend ".md"</span><span class="sxs-lookup"><span data-stu-id="4db01-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nome da nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="4db01-177">Certifique-se de criar o novo artigo na pasta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="4db01-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="4db01-178">Você pode confirmar isso verificando "/mixed-reality-docs/" na nova linha de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4db01-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="4db01-179">Na parte superior da nova página, adicione o seguinte bloco de metadados:</span><span class="sxs-lookup"><span data-stu-id="4db01-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="4db01-180">Preencha os campos de metadados relevantes de acordo com as instruções na [seção acima.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="4db01-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="4db01-181">Escrever conteúdo de artigo usando [noções básicas do Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="4db01-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="4db01-182">Adicione uma `## See also` seção na parte inferior do artigo com links para outros artigos relevantes.</span><span class="sxs-lookup"><span data-stu-id="4db01-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="4db01-183">Quando terminar, selecione **Commit new file**.</span><span class="sxs-lookup"><span data-stu-id="4db01-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="4db01-184">Selecione **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span><span class="sxs-lookup"><span data-stu-id="4db01-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Criar solicitação pull de sua bifurcação para o MicrosoftDocs/realidade misturada](images/pr-to-master.png)

## <span data-ttu-id="4db01-186">Noções básicas de Markdown</span><span class="sxs-lookup"><span data-stu-id="4db01-186">Markdown basics</span></span>

<span data-ttu-id="4db01-187">Os seguintes recursos o ajudarão a aprender a editar a documentação usando o idioma markdown:</span><span class="sxs-lookup"><span data-stu-id="4db01-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="4db01-188">Noções básicas de Markdown</span><span class="sxs-lookup"><span data-stu-id="4db01-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="4db01-189">Recursos adicionais para escrever Markdown para docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4db01-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="4db01-190">Adicionando tabelas</span><span class="sxs-lookup"><span data-stu-id="4db01-190">Adding tables</span></span>

<span data-ttu-id="4db01-191">Devido à maneira como docs.microsoft.com estilos de tabelas, elas não terão bordas ou estilos personalizados, mesmo que você tente css em linha.</span><span class="sxs-lookup"><span data-stu-id="4db01-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="4db01-192">Ele parece funcionar por um curto período de tempo, mas eventualmente a plataforma retirará o estilo da tabela.</span><span class="sxs-lookup"><span data-stu-id="4db01-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="4db01-193">Portanto, planeje com antecedência e mantenha suas tabelas simples.</span><span class="sxs-lookup"><span data-stu-id="4db01-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="4db01-194">[Aqui está um site que facilita as tabelas de Markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="4db01-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="4db01-195">A [Extensão de Markdown](https://docs.microsoft.com/teamblog/docs-extension) de Documentos para Visual Studio Code também facilita a geração de tabela se você estiver usando o [Visual Studio Code (veja abaixo)](#using-visual-studio-code) para editar a documentação.</span><span class="sxs-lookup"><span data-stu-id="4db01-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="4db01-196">Adicionando imagens</span><span class="sxs-lookup"><span data-stu-id="4db01-196">Adding images</span></span>

<span data-ttu-id="4db01-197">Você precisará carregar suas imagens na pasta "mixed-reality-docs/images" no repo e, em seguida, fazer referência a elas adequadamente no artigo.</span><span class="sxs-lookup"><span data-stu-id="4db01-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="4db01-198">As imagens aparecerão automaticamente em tamanho total, o que significa que imagens grandes preencherão toda a largura do artigo.</span><span class="sxs-lookup"><span data-stu-id="4db01-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="4db01-199">Recomendamos pré-reizing suas imagens antes de enviá-las.</span><span class="sxs-lookup"><span data-stu-id="4db01-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="4db01-200">A largura recomendada é entre 600 e 700 pixels, embora você deva ser tamanho para cima ou para baixo se for uma captura de tela densa ou uma fração de uma captura de tela, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4db01-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4db01-201">Você só pode carregar imagens no seu repo bifurcado antes de mesclar.</span><span class="sxs-lookup"><span data-stu-id="4db01-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="4db01-202">Portanto, se você planeja adicionar imagens a um artigo, precisará usar o [Visual Studio Code](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" da bifurcação primeiro ou certifique-se de ter feito o seguinte em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="4db01-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="4db01-203">Bifurcado o microsoftDocs/repo de realidade misturada.</span><span class="sxs-lookup"><span data-stu-id="4db01-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="4db01-204">Editou o artigo em sua bifurcação.</span><span class="sxs-lookup"><span data-stu-id="4db01-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="4db01-205">Carreguei as imagens que você está fazendo referência em seu artigo para a pasta "mixed-reality-docs/images" na bifurcação.</span><span class="sxs-lookup"><span data-stu-id="4db01-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="4db01-206">Criou uma **solicitação pull** para mesclar sua bifurcação com o branch "mestre" do MicrosoftDocs/realidade misturada.</span><span class="sxs-lookup"><span data-stu-id="4db01-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="4db01-207">Para saber como configurar seu próprio repo bifurcado, siga as instruções para [criar um novo artigo.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="4db01-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="4db01-208">Visualizando seu trabalho</span><span class="sxs-lookup"><span data-stu-id="4db01-208">Previewing your work</span></span>

<span data-ttu-id="4db01-209">Durante a edição no GitHub por meio \*\*\*\* de um navegador da Web, você pode selecionar a guia Visualização na parte superior da página para visualizar seu trabalho antes de se comprometer.</span><span class="sxs-lookup"><span data-stu-id="4db01-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="4db01-210">Visualizar suas alterações no review.docs.microsoft.com está disponível apenas para funcionários da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4db01-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="4db01-211">Funcionários da Microsoft: depois que suas contribuições são mescladas na ramificação "mestre", você pode revisar o conteúdo antes que ele seja público em https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="4db01-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="4db01-212">Encontre seu artigo usando o índice na coluna esquerda.</span><span class="sxs-lookup"><span data-stu-id="4db01-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="4db01-213">Edição no navegador versus edição com um cliente da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="4db01-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="4db01-214">A edição no navegador é a maneira mais fácil de fazer alterações rápidas, no entanto, há algumas desvantagens:</span><span class="sxs-lookup"><span data-stu-id="4db01-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="4db01-215">Você não obterá a verificação ort três ou mais.</span><span class="sxs-lookup"><span data-stu-id="4db01-215">You don't get spell-check.</span></span>
- <span data-ttu-id="4db01-216">Você não tem nenhuma vinculação inteligente a outros artigos (você precisa digitar manualmente o nome de arquivo do artigo).</span><span class="sxs-lookup"><span data-stu-id="4db01-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="4db01-217">Pode ser um problema carregar e referenciar imagens.</span><span class="sxs-lookup"><span data-stu-id="4db01-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="4db01-218">Se você preferir não lidar com esses problemas, use um cliente da área de trabalho como o [Visual Studio Code](https://code.visualstudio.com/) com algumas extensões úteis ao contribuir. [](#useful-extensions)</span><span class="sxs-lookup"><span data-stu-id="4db01-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="4db01-219">Usando o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4db01-219">Using Visual Studio Code</span></span>

<span data-ttu-id="4db01-220">Pelos motivos listados [acima,](#editing-in-the-browser-vs-editing-with-a-desktop-client)você pode preferir usar um cliente da área de trabalho para editar a documentação em vez de um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="4db01-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="4db01-221">Recomendamos usar [o Visual Studio Code.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="4db01-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="4db01-222">Configuração</span><span class="sxs-lookup"><span data-stu-id="4db01-222">Setup</span></span>

<span data-ttu-id="4db01-223">Siga estas etapas para configurar o Visual Studio Code para trabalhar com esse repo:</span><span class="sxs-lookup"><span data-stu-id="4db01-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="4db01-224">Em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="4db01-224">In a web browser:</span></span>
    1. <span data-ttu-id="4db01-225">Instale [o Git para seu computador.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="4db01-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="4db01-226">Instale [o Visual Studio Code.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="4db01-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="4db01-227">[Bifurcar MicrosoftDocs/realidade misturada,](#creating-a-new-article) se você ainda não o fez.</span><span class="sxs-lookup"><span data-stu-id="4db01-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="4db01-228">Na bifurcação, selecione **Clone ou baixe** e copie a URL.</span><span class="sxs-lookup"><span data-stu-id="4db01-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="4db01-229">Crie um clone local da bifurcação no Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="4db01-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="4db01-230">No menu **Exibir,** selecione **Paleta de Comandos.**</span><span class="sxs-lookup"><span data-stu-id="4db01-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="4db01-231">Digite "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="4db01-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="4db01-232">Colar a URL que você copiou.</span><span class="sxs-lookup"><span data-stu-id="4db01-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="4db01-233">Escolha onde salvar o clone em seu computador.</span><span class="sxs-lookup"><span data-stu-id="4db01-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="4db01-234">Selecione **Abrir o repo** no pop-up.</span><span class="sxs-lookup"><span data-stu-id="4db01-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="4db01-235">Documentação de edição</span><span class="sxs-lookup"><span data-stu-id="4db01-235">Editing documentation</span></span>

<span data-ttu-id="4db01-236">Use o fluxo de trabalho a seguir para fazer alterações na documentação com o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="4db01-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="4db01-237">Todas as diretrizes para [](#creating-a-new-article) [edição](#editing-an-existing-article) e criação de artigos e as noções básicas de edição do [Markdown](#markdown-basics)acima se aplica ao usar o Visual Studio Code também.</span><span class="sxs-lookup"><span data-stu-id="4db01-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="4db01-238">Certifique-se de que a bifurcação clonada esteja atualizada com o repo oficial.</span><span class="sxs-lookup"><span data-stu-id="4db01-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="4db01-239">Em um navegador da Web, crie uma solicitação pull para sincronizar as alterações recentes de outros colaboradores no MicrosoftDocs/'mestre' de realidade misturada para sua bifurcação (certifique-se de que a seta está apontando para a direita).</span><span class="sxs-lookup"><span data-stu-id="4db01-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronizar alterações do MicrosoftDocs/realidade misturada com sua bifurcação](images/sync-repos.png)
      
   2. <span data-ttu-id="4db01-241">No Visual Studio Code, selecione o botão de sincronização para sincronizar sua bifurcação atualizada para o clone local.</span><span class="sxs-lookup"><span data-stu-id="4db01-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Clique na imagem do botão de sincronização](images/sync-clone.png)
      
2. <span data-ttu-id="4db01-243">Crie ou edite artigos no seu repo clonado usando o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4db01-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="4db01-244">Edite um ou mais artigos (adicione imagens à pasta "imagens", se necessário).</span><span class="sxs-lookup"><span data-stu-id="4db01-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="4db01-245">**Salvar** alterações no **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="4db01-245">**Save** changes in **Explorer**.</span></span>
      
      ![Escolha "Salvar tudo" no Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="4db01-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span><span class="sxs-lookup"><span data-stu-id="4db01-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Choose "Commit all" in Source Control](images/source-control-commit.png)
      
   4. <span data-ttu-id="4db01-249">Selecione o **botão de** sincronização para sincronizar suas alterações de volta à origem (sua bifurcação no GitHub).</span><span class="sxs-lookup"><span data-stu-id="4db01-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Clique no botão de sincronização](images/sync-back.png)
      
3. <span data-ttu-id="4db01-251">Em um navegador da Web, crie uma solicitação pull para sincronizar novas alterações em sua bifurcação de volta para MicrosoftDocs/'mestre' de realidade misturada (certifique-se de que a seta está apontando para a maneira correta).</span><span class="sxs-lookup"><span data-stu-id="4db01-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Criar solicitação pull de sua bifurcação para o MicrosoftDocs/realidade misturada](images/pr-to-master.png)

### <span data-ttu-id="4db01-253">Extensões úteis</span><span class="sxs-lookup"><span data-stu-id="4db01-253">Useful extensions</span></span>

<span data-ttu-id="4db01-254">As seguintes extensões do Visual Studio Code são úteis ao editar a documentação:</span><span class="sxs-lookup"><span data-stu-id="4db01-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="4db01-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span><span class="sxs-lookup"><span data-stu-id="4db01-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="4db01-256">Pesquisar e referenciar imagens que você carregou.</span><span class="sxs-lookup"><span data-stu-id="4db01-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="4db01-257">Adicionar formatação como listas, tabelas e explicações específicas de documentos, como `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="4db01-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="4db01-258">Pesquisar e referenciar links internos e indicadores (links para seções específicas em uma página).</span><span class="sxs-lookup"><span data-stu-id="4db01-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="4db01-259">Os erros de formatação são realçados (passe o mouse sobre o erro para saber mais).</span><span class="sxs-lookup"><span data-stu-id="4db01-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="4db01-260">[Verificador Ortônico de](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Código - as palavras com ortização inserida serão sublinhadas; clique com o botão direito do mouse em uma palavra com o botão direito do mouse para alterá-la ou salvá-la no dicionário.</span><span class="sxs-lookup"><span data-stu-id="4db01-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
