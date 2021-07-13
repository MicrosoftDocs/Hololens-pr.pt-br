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
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="06c7b-103">Contribuir com a documentação HoloLens dados</span><span class="sxs-lookup"><span data-stu-id="06c7b-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="06c7b-104">Bem-vindo à [documentação do HoloLens!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="06c7b-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="06c7b-105">Todos os artigos que você criar ou editar neste repo **estarão visíveis para o público.**</span><span class="sxs-lookup"><span data-stu-id="06c7b-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="06c7b-106">HoloLens documentos são exibidos na plataforma docs.microsoft.com, que usa GitHub Markdown com recursos markdig.</span><span class="sxs-lookup"><span data-stu-id="06c7b-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="06c7b-107">O conteúdo editado neste repo é formatado em páginas estilizadas que aparecem em /hololens.</span><span class="sxs-lookup"><span data-stu-id="06c7b-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="06c7b-108">Esta página aborda as etapas básicas e as diretrizes para contribuir e links para noções básicas de Markdown.</span><span class="sxs-lookup"><span data-stu-id="06c7b-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="06c7b-109">Obrigado por sua contribuição!</span><span class="sxs-lookup"><span data-stu-id="06c7b-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="06c7b-110">Repos disponíveis</span><span class="sxs-lookup"><span data-stu-id="06c7b-110">Available repos</span></span>

| <span data-ttu-id="06c7b-111">Nome do repositório</span><span class="sxs-lookup"><span data-stu-id="06c7b-111">Repository name</span></span> | <span data-ttu-id="06c7b-112">URL</span><span class="sxs-lookup"><span data-stu-id="06c7b-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="06c7b-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="06c7b-113">HoloLens</span></span> | [<span data-ttu-id="06c7b-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="06c7b-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="06c7b-115">Realidade Misturada</span><span class="sxs-lookup"><span data-stu-id="06c7b-115">Mixed Reality</span></span> | [<span data-ttu-id="06c7b-116">MicrosoftDocs/realidade misturada</span><span class="sxs-lookup"><span data-stu-id="06c7b-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="06c7b-117">Guia de entusiados de VR</span><span class="sxs-lookup"><span data-stu-id="06c7b-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="06c7b-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="06c7b-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="06c7b-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="06c7b-119">Before you start</span></span>

<span data-ttu-id="06c7b-120">Se você ainda não tiver uma, precisará criar uma conta [GitHub .](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="06c7b-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="06c7b-121">Se você for um funcionário da Microsoft, vincule sua GitHub ao alias da Microsoft no portal de Código Aberto [da Microsoft.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="06c7b-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="06c7b-122">Participe das **organizações "Microsoft"** **e "MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="06c7b-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="06c7b-123">Ao configurar sua conta GitHub, também recomendamos estas precauções de segurança:</span><span class="sxs-lookup"><span data-stu-id="06c7b-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="06c7b-124">Crie uma [senha forte para sua conta GitHub .](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="06c7b-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="06c7b-125">[Habilita a autenticação de dois fatores.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="06c7b-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="06c7b-126">Salve seus [códigos de recuperação](https://github.com/settings/auth/recovery-codes) em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="06c7b-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="06c7b-127">Atualize [suas configurações de perfil público](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="06c7b-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="06c7b-128">De definir seu nome e considere definir seu *email público* como Não mostrar meu endereço *de email*.</span><span class="sxs-lookup"><span data-stu-id="06c7b-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="06c7b-129">Recomendamos que você carregue uma imagem de perfil porque uma miniatura é mostrada nas páginas de documentos com as que você contribui.</span><span class="sxs-lookup"><span data-stu-id="06c7b-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="06c7b-130">Se você planeja usar a linha de comando, considere configurar o [Git Gerenciador de Credenciais para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="06c7b-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="06c7b-131">Dessa forma, você não precisa inserir sua senha sempre que fizer uma contribuição.</span><span class="sxs-lookup"><span data-stu-id="06c7b-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="06c7b-132">O sistema de publicação está vinculado GitHub, portanto, essas etapas são importantes.</span><span class="sxs-lookup"><span data-stu-id="06c7b-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="06c7b-133">Você será listado como autor ou colaborador de cada artigo usando seu alias GitHub dados.</span><span class="sxs-lookup"><span data-stu-id="06c7b-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="06c7b-134">Editando um artigo existente</span><span class="sxs-lookup"><span data-stu-id="06c7b-134">Editing an existing article</span></span>

<span data-ttu-id="06c7b-135">Use o seguinte fluxo de trabalho para fazer atualizações *em um artigo existente* por meio GitHub em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="06c7b-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="06c7b-136">Navegue até o artigo que você deseja editar na pasta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="06c7b-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="06c7b-137">Selecione o botão Editar (ícone de lápis) no canto superior direito, que bifurca automaticamente um branch descartável do branch 'mestre'.</span><span class="sxs-lookup"><span data-stu-id="06c7b-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Edite um artigo.](images/editpage.png)
   
3. <span data-ttu-id="06c7b-139">Edite o conteúdo do artigo de acordo com [as "Noções básicas de Markdown".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="06c7b-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="06c7b-140">Atualize os metadados na parte superior de cada artigo:</span><span class="sxs-lookup"><span data-stu-id="06c7b-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="06c7b-141">**título:** título da página que aparece na guia do navegador quando o artigo está sendo exibido.</span><span class="sxs-lookup"><span data-stu-id="06c7b-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="06c7b-142">Os títulos de página são usados para SEO e indexação, portanto, não altere o título, a menos que necessário (embora isso seja menos crítico antes que a documentação seja pública).</span><span class="sxs-lookup"><span data-stu-id="06c7b-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="06c7b-143">**description**: escreva uma breve descrição do conteúdo do artigo, o que aumenta o SEO e a descoberta.</span><span class="sxs-lookup"><span data-stu-id="06c7b-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="06c7b-144">**author**: se você for o proprietário principal da página, adicione seu alias GitHub aqui.</span><span class="sxs-lookup"><span data-stu-id="06c7b-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="06c7b-145">**ms.author:** se você for o proprietário principal da página, adicione o alias da Microsoft aqui (você não precisa @microsoft.com apenas do alias).</span><span class="sxs-lookup"><span data-stu-id="06c7b-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="06c7b-146">**ms.date:** atualize a data se você estiver adicionando conteúdo principal à página, mas não para correções como esclarecimento, formatação, gramática ou ortografia.</span><span class="sxs-lookup"><span data-stu-id="06c7b-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="06c7b-147">**palavras-chave:** as palavras-chave auxiliam no SEO (otimização do mecanismo de pesquisa).</span><span class="sxs-lookup"><span data-stu-id="06c7b-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="06c7b-148">Adicione palavras-chave, separadas por uma vírgula e um espaço, que são específicas para seu artigo, mas nenhuma pontuação após a última palavra-chave em sua lista.</span><span class="sxs-lookup"><span data-stu-id="06c7b-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="06c7b-149">Você não precisa adicionar palavras-chave globais que se aplicam a todos os artigos, pois eles são gerenciados em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="06c7b-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="06c7b-150">Quando você concluir as edições do artigo, role para baixo e selecione **Propor alteração de arquivo.**</span><span class="sxs-lookup"><span data-stu-id="06c7b-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="06c7b-151">Na próxima página, selecione Criar **solicitação de pull** para mesclar o branch criado automaticamente em 'mestre'.</span><span class="sxs-lookup"><span data-stu-id="06c7b-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="06c7b-152">Repita as etapas acima para o próximo artigo que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="06c7b-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="06c7b-153">Renomeando ou excluindo um artigo existente</span><span class="sxs-lookup"><span data-stu-id="06c7b-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="06c7b-154">Se a alteração renomear ou excluir um artigo existente, adicione um redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="06c7b-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="06c7b-155">Dessa forma, qualquer pessoa com um link para o artigo existente ainda acabará no lugar certo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="06c7b-156">Os redirecionamentos são gerenciados pelo .openpublishing.redirection.jsno arquivo na raiz do repo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="06c7b-157">Para adicionar um redirecionamento .openpublishing.redirection.js, adicione uma entrada à `redirections` matriz:</span><span class="sxs-lookup"><span data-stu-id="06c7b-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="06c7b-158">O `source_path` é o caminho do repositório relativo para o artigo antigo que você está removendo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="06c7b-159">Certifique-se de que o caminho comece `mixed-reality-docs` com e termine com `.md` .</span><span class="sxs-lookup"><span data-stu-id="06c7b-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="06c7b-160">O `redirect_url` é a URL pública relativa do artigo antigo para o novo artigo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="06c7b-161">Certifique-se de que essa URL **não contenha** ou , pois ela se refere à `mixed-reality-docs` URL pública e não ao caminho do `.md` repositório.</span><span class="sxs-lookup"><span data-stu-id="06c7b-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="06c7b-162">A vinculação a uma seção dentro do novo artigo usando `#section` é permitida.</span><span class="sxs-lookup"><span data-stu-id="06c7b-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="06c7b-163">Você também pode usar um caminho absoluto para outro site aqui, se necessário.</span><span class="sxs-lookup"><span data-stu-id="06c7b-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="06c7b-164">`redirect_document_id` indica se você gostaria de manter a ID do documento do arquivo anterior.</span><span class="sxs-lookup"><span data-stu-id="06c7b-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="06c7b-165">O padrão é `false`.</span><span class="sxs-lookup"><span data-stu-id="06c7b-165">The default is `false`.</span></span> <span data-ttu-id="06c7b-166">Use `true` se você quiser preservar o valor do atributo do artigo `ms.documentid` redirecionado.</span><span class="sxs-lookup"><span data-stu-id="06c7b-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="06c7b-167">Se você preservar a ID do documento, os dados, como exibições de página e classificações, serão transferidos para o artigo de destino.</span><span class="sxs-lookup"><span data-stu-id="06c7b-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="06c7b-168">Faça isso se o redirecionamento for principalmente um renomeado e não um ponteiro para um artigo diferente que abrange apenas parte do mesmo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="06c7b-169">Se você adicionar um redirecionamento, exclua o arquivo antigo também.</span><span class="sxs-lookup"><span data-stu-id="06c7b-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="06c7b-170">Criando um novo artigo</span><span class="sxs-lookup"><span data-stu-id="06c7b-170">Creating a new article</span></span>

<span data-ttu-id="06c7b-171">Use o fluxo de trabalho a *seguir para criar novos artigos* no GitHub documentação em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="06c7b-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="06c7b-172">Crie um fork do branch 'mestre' MicrosoftDocs/mixed-reality (usando o **botão Bifurcar** no canto superior direito).</span><span class="sxs-lookup"><span data-stu-id="06c7b-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurcar o branch mestre.](images/forkbranch.png)
   
2. <span data-ttu-id="06c7b-174">Na pasta "mixed-reality-docs", selecione **Criar arquivo** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="06c7b-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="06c7b-175">Crie um nome de página para o artigo (use hifens em vez de espaços e não use pontuação ou apóstrofos) e anexar ".md"</span><span class="sxs-lookup"><span data-stu-id="06c7b-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nomeia sua nova página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="06c7b-177">Certifique-se de criar o novo artigo de dentro da pasta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="06c7b-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="06c7b-178">Você pode confirmar isso verificando "/mixed-reality-docs/" na nova linha de nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="06c7b-179">Na parte superior da nova página, adicione o seguinte bloco de metadados:</span><span class="sxs-lookup"><span data-stu-id="06c7b-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="06c7b-180">Preencha os campos de metadados relevantes de acordo com as instruções na [seção acima.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="06c7b-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="06c7b-181">Escreva o conteúdo do artigo [usando noções básicas de Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="06c7b-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="06c7b-182">Adicione uma `## See also` seção na parte inferior do artigo com links para outros artigos relevantes.</span><span class="sxs-lookup"><span data-stu-id="06c7b-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="06c7b-183">Quando terminar, selecione **Commit new file**.</span><span class="sxs-lookup"><span data-stu-id="06c7b-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="06c7b-184">Selecione **Nova solicitação de pull** e mesclar o branch 'mestre' do fork em MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está apontando para o caminho correto).</span><span class="sxs-lookup"><span data-stu-id="06c7b-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Criar solicitação de pull de seu fork para MicrosoftDocs/realidade misturada](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="06c7b-186">Noções básicas de markdown</span><span class="sxs-lookup"><span data-stu-id="06c7b-186">Markdown basics</span></span>

<span data-ttu-id="06c7b-187">Os recursos a seguir ajudarão você a aprender a editar a documentação usando a linguagem Markdown:</span><span class="sxs-lookup"><span data-stu-id="06c7b-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="06c7b-188">Noções básicas de Markdown</span><span class="sxs-lookup"><span data-stu-id="06c7b-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="06c7b-189">Recursos adicionais para escrever Markdown para docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="06c7b-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="06c7b-190">Adicionando tabelas</span><span class="sxs-lookup"><span data-stu-id="06c7b-190">Adding tables</span></span>

<span data-ttu-id="06c7b-191">Devido à maneira como docs.microsoft.com tabelas de estilos, elas não terão bordas nem estilos personalizados, mesmo se você tentar CSS em linha.</span><span class="sxs-lookup"><span data-stu-id="06c7b-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="06c7b-192">Ele parece funcionará por um curto período de tempo, mas, eventualmente, a plataforma retirará o estilo da tabela.</span><span class="sxs-lookup"><span data-stu-id="06c7b-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="06c7b-193">Portanto, planeje com antecedência e mantenha as tabelas simples.</span><span class="sxs-lookup"><span data-stu-id="06c7b-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="06c7b-194">[Aqui está um site que facilita as tabelas de Markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="06c7b-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="06c7b-195">A Extensão Markdown do [Docs para Visual Studio Code](/teamblog/docs-extension) também facilita a geração de tabelas se você estiver usando Visual Studio Code [(veja abaixo)](#using-visual-studio-code) para editar a documentação.</span><span class="sxs-lookup"><span data-stu-id="06c7b-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="06c7b-196">Adição de imagens</span><span class="sxs-lookup"><span data-stu-id="06c7b-196">Adding images</span></span>

<span data-ttu-id="06c7b-197">Você precisará carregar suas imagens na pasta "mixed-reality-docs/images" no repo e, em seguida, fazer referência a elas adequadamente no artigo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="06c7b-198">As imagens aparecerão automaticamente em tamanho total, o que significa que imagens grandes preencherão toda a largura do artigo.</span><span class="sxs-lookup"><span data-stu-id="06c7b-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="06c7b-199">É recomendável pré-fazer o pré-sizing das imagens antes de enviá-las.</span><span class="sxs-lookup"><span data-stu-id="06c7b-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="06c7b-200">A largura recomendada está entre 600 e 700 pixels, embora você deva ter um tamanho para cima ou para baixo se for uma captura de tela densa ou uma fração de uma captura de tela, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="06c7b-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="06c7b-201">Você só pode carregar imagens no seu repo bifurcado antes de mesclar.</span><span class="sxs-lookup"><span data-stu-id="06c7b-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="06c7b-202">Portanto, se você planeja adicionar imagens a um artigo, precisará usar o [Visual Studio Code](#using-visual-studio-code) para adicionar as imagens à pasta "imagens" do fork primeiro ou fazer o seguinte em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="06c7b-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="06c7b-203">Forked the MicrosoftDocs/mixed-reality repo( Forked the MicrosoftDocs/mixed-reality repo).</span><span class="sxs-lookup"><span data-stu-id="06c7b-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="06c7b-204">Editou o artigo em sua bifurcação.</span><span class="sxs-lookup"><span data-stu-id="06c7b-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="06c7b-205">Carregou as imagens que você está referenciando em seu artigo para a pasta "mixed-reality-docs/images" em sua bifurcação.</span><span class="sxs-lookup"><span data-stu-id="06c7b-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="06c7b-206">Criou uma **solicitação de pull** para mesclar seu fork no branch 'mestre' MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="06c7b-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="06c7b-207">Para saber como configurar seu próprio repo bifurcado, siga as instruções para [criar um novo artigo](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="06c7b-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="06c7b-208">Visualizando seu trabalho</span><span class="sxs-lookup"><span data-stu-id="06c7b-208">Previewing your work</span></span>

<span data-ttu-id="06c7b-209">Durante a edição no GitHub por meio de um  navegador da Web, você pode selecionar a guia Visualização na parte superior da página para visualizar seu trabalho antes de se comprometer.</span><span class="sxs-lookup"><span data-stu-id="06c7b-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="06c7b-210">Visualizar suas alterações no review.docs.microsoft.com está disponível apenas para funcionários da Microsoft</span><span class="sxs-lookup"><span data-stu-id="06c7b-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="06c7b-211">Funcionários da Microsoft: depois que suas contribuições foram mescladas no branch "mestre", você pode revisar o conteúdo antes que ele seja público em </hololens?branch=master>.</span><span class="sxs-lookup"><span data-stu-id="06c7b-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="06c7b-212">Encontre seu artigo usando o tabela de conteúdo na coluna à esquerda.</span><span class="sxs-lookup"><span data-stu-id="06c7b-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="06c7b-213">Edição no navegador versus edição com um cliente da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="06c7b-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="06c7b-214">A edição no navegador é a maneira mais fácil de fazer alterações rápidas, no entanto, há algumas desvantagens:</span><span class="sxs-lookup"><span data-stu-id="06c7b-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="06c7b-215">Você não obterá a verificação ort ort só.</span><span class="sxs-lookup"><span data-stu-id="06c7b-215">You don't get spell-check.</span></span>
- <span data-ttu-id="06c7b-216">Você não tem nenhuma vinculação inteligente a outros artigos (você precisa digitar manualmente o nome do arquivo do artigo).</span><span class="sxs-lookup"><span data-stu-id="06c7b-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="06c7b-217">Pode ser um problema carregar e referenciar imagens.</span><span class="sxs-lookup"><span data-stu-id="06c7b-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="06c7b-218">Se você preferir não lidar com esses problemas, use um cliente da área de trabalho [como Visual Studio Code](https://code.visualstudio.com/) com algumas extensões úteis [ao](#useful-extensions) contribuir.</span><span class="sxs-lookup"><span data-stu-id="06c7b-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="06c7b-219">Usar o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="06c7b-219">Using Visual Studio Code</span></span>

<span data-ttu-id="06c7b-220">Pelos motivos listados [acima,](#editing-in-the-browser-vs-editing-with-a-desktop-client)você pode preferir usar um cliente da área de trabalho para editar a documentação em vez de um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="06c7b-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="06c7b-221">É recomendável usar [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="06c7b-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="06c7b-222">Instalação</span><span class="sxs-lookup"><span data-stu-id="06c7b-222">Setup</span></span>

<span data-ttu-id="06c7b-223">Siga estas etapas para configurar Visual Studio Code para trabalhar com este repo:</span><span class="sxs-lookup"><span data-stu-id="06c7b-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="06c7b-224">Em um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="06c7b-224">In a web browser:</span></span>
    1. <span data-ttu-id="06c7b-225">Instale [o Git para seu computador.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="06c7b-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="06c7b-226">Instale o [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="06c7b-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="06c7b-227">[Bifurcar MicrosoftDocs/realidade misturada](#creating-a-new-article) se você ainda não fez isso.</span><span class="sxs-lookup"><span data-stu-id="06c7b-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="06c7b-228">Na bifurcação, selecione **Clonar ou baixar** e copie a URL.</span><span class="sxs-lookup"><span data-stu-id="06c7b-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="06c7b-229">Crie um clone local da bifurcação Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="06c7b-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="06c7b-230">No menu **Exibir,** selecione **Paleta de Comandos**.</span><span class="sxs-lookup"><span data-stu-id="06c7b-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="06c7b-231">Digite "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="06c7b-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="06c7b-232">Colar a URL que você copiou.</span><span class="sxs-lookup"><span data-stu-id="06c7b-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="06c7b-233">Escolha onde salvar o clone em seu computador.</span><span class="sxs-lookup"><span data-stu-id="06c7b-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="06c7b-234">Selecione **Abrir o repo** no pop-up.</span><span class="sxs-lookup"><span data-stu-id="06c7b-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="06c7b-235">Documentação de edição</span><span class="sxs-lookup"><span data-stu-id="06c7b-235">Editing documentation</span></span>

<span data-ttu-id="06c7b-236">Use o seguinte fluxo de trabalho para fazer alterações na documentação com Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="06c7b-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="06c7b-237">Todas as diretrizes para [](#creating-a-new-article) [edição](#editing-an-existing-article) e criação de artigos e as noções básicas de edição de [Markdown,](#markdown-basics)acima, se aplica ao usar Visual Studio Code também.</span><span class="sxs-lookup"><span data-stu-id="06c7b-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="06c7b-238">Certifique-se de que o fork clonado esteja atualizado com o repo oficial.</span><span class="sxs-lookup"><span data-stu-id="06c7b-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="06c7b-239">Em um navegador da Web, crie uma solicitação de pull para sincronizar alterações recentes de outros colaboradores no MicrosoftDocs/mixed-reality 'master' para sua bifurcação (certifique-se de que a seta está apontando para a direita).</span><span class="sxs-lookup"><span data-stu-id="06c7b-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronizar alterações do MicrosoftDocs/realidade misturada para sua bifurcação](images/sync-repos.png)
      
   2. <span data-ttu-id="06c7b-241">No Visual Studio Code, selecione o botão de sincronização para sincronizar sua bifurcação atualizada recentemente com o clone local.</span><span class="sxs-lookup"><span data-stu-id="06c7b-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Clique na imagem do botão de sincronização](images/sync-clone.png)
      
2. <span data-ttu-id="06c7b-243">Crie ou edite artigos em seu repo clonado usando Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="06c7b-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="06c7b-244">Edite um ou mais artigos (adicione imagens à pasta "imagens", se necessário).</span><span class="sxs-lookup"><span data-stu-id="06c7b-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="06c7b-245">**Salve** as alterações no **Explorer.**</span><span class="sxs-lookup"><span data-stu-id="06c7b-245">**Save** changes in **Explorer**.</span></span>
      
      ![Escolha "Salvar tudo" no Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="06c7b-247">**Faça commit de** todas as alterações **no Controle do Código-Fonte** (escreva a mensagem de commit quando solicitado).</span><span class="sxs-lookup"><span data-stu-id="06c7b-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Escolha "Commit all" no controle do código-fonte](images/source-control-commit.png)
      
   4. <span data-ttu-id="06c7b-249">Selecione o botão **de sincronização** para sincronizar suas alterações de volta à origem (seu fork GitHub).</span><span class="sxs-lookup"><span data-stu-id="06c7b-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Clique no botão de sincronização](images/sync-back.png)
      
3. <span data-ttu-id="06c7b-251">Em um navegador da Web, crie uma solicitação de pull para sincronizar novas alterações em seu fork de volta para MicrosoftDocs/mixed-reality 'master' (certifique-se de que a seta está apontando para o caminho correto).</span><span class="sxs-lookup"><span data-stu-id="06c7b-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Criar solicitação de pull de seu fork para MicrosoftDocs/realidade misturada](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="06c7b-253">Extensões úteis</span><span class="sxs-lookup"><span data-stu-id="06c7b-253">Useful extensions</span></span>

<span data-ttu-id="06c7b-254">As seguintes Visual Studio Code extensões são úteis ao editar a documentação:</span><span class="sxs-lookup"><span data-stu-id="06c7b-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="06c7b-255">[Extensão Markdown do Docs para Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – use **Alt+M** para abrir um menu de opções de autor de documentos, como:</span><span class="sxs-lookup"><span data-stu-id="06c7b-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="06c7b-256">Pesquisar e referenciar imagens que você carregou.</span><span class="sxs-lookup"><span data-stu-id="06c7b-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="06c7b-257">Adicione formatação como listas, tabelas e saídas específicas de documentos, como `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="06c7b-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="06c7b-258">Pesquisar e referenciar links internos e indicadores (links para seções específicas em uma página).</span><span class="sxs-lookup"><span data-stu-id="06c7b-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="06c7b-259">Erros de formatação são realçadas (passe o mouse sobre o erro para saber mais).</span><span class="sxs-lookup"><span data-stu-id="06c7b-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="06c7b-260">[Verificador Ortônico de](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Código – palavras com ortagem inoclinada serão sublinhadas; Clique com o botão direito do mouse em uma palavra com o botão direito do mouse para alterá-la ou salvá-la no dicionário.</span><span class="sxs-lookup"><span data-stu-id="06c7b-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
