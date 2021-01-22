---
title: Beiwirkende Anweisungen
description: Erfahren Sie, wie Sie mithilfe von GitHub-markdown auf der docs.microsoft.com A0 zu den HoloLens-Dokumenten beitragen.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283660"
---
# <span data-ttu-id="30439-103">Beitrag zur HoloLens-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="30439-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="30439-104">Willkommen bei der [HoloLens-Dokumentation!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="30439-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="30439-105">Alle Artikel, die Sie in diesem Repository erstellen oder **bearbeiten, sind für die Öffentlichkeit sichtbar.**</span><span class="sxs-lookup"><span data-stu-id="30439-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="30439-106">HoloLens-Dokumente werden auf der docs.microsoft.com angezeigt, die GitHub-markdown mit Markdig-Features verwendet.</span><span class="sxs-lookup"><span data-stu-id="30439-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="30439-107">Der Inhalt, den Sie in diesem Repository bearbeiten, wird in stilisierten Seiten formatiert, die unter angezeigt https://docs.microsoft.com/hololens werden.</span><span class="sxs-lookup"><span data-stu-id="30439-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="30439-108">Auf dieser Seite werden die grundlegenden Schritte und Richtlinien für die Mitwirkung sowie Links zu den Grundlagen von Markdown behandelt.</span><span class="sxs-lookup"><span data-stu-id="30439-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="30439-109">Vielen Dank für Ihren Beitrag!</span><span class="sxs-lookup"><span data-stu-id="30439-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="30439-110">Verfügbare Repositorys</span><span class="sxs-lookup"><span data-stu-id="30439-110">Available repos</span></span>

| <span data-ttu-id="30439-111">Repositoryname</span><span class="sxs-lookup"><span data-stu-id="30439-111">Repository name</span></span> | <span data-ttu-id="30439-112">URL</span><span class="sxs-lookup"><span data-stu-id="30439-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="30439-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="30439-113">HoloLens</span></span> | [<span data-ttu-id="30439-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="30439-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="30439-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="30439-115">Mixed Reality</span></span> | [<span data-ttu-id="30439-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="30439-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="30439-117">Leitfaden für VR-Enthusiasten</span><span class="sxs-lookup"><span data-stu-id="30439-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="30439-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="30439-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="30439-119">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="30439-119">Before you start</span></span>

<span data-ttu-id="30439-120">Wenn Sie noch keins haben, müssen Sie ein [GitHub-Konto erstellen.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="30439-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="30439-121">Wenn Sie ein Microsoft-Mitarbeiter sind, verknüpfen Sie Ihr GitHub-Konto mit Ihrem Microsoft-Alias im [Microsoft Open Source-Portal.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="30439-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="30439-122">Treten Sie **den Organisationen "Microsoft"** und **"MicrosoftDocs"** bei.</span><span class="sxs-lookup"><span data-stu-id="30439-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="30439-123">Beim Einrichten Ihres GitHub-Kontos empfehlen wir auch die folgenden Sicherheitsvorkehrungen:</span><span class="sxs-lookup"><span data-stu-id="30439-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="30439-124">Erstellen Sie [ein starkes Kennwort für Ihr GitHub-Konto.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="30439-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="30439-125">Aktivieren [Sie die zweistufige Authentifizierung.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="30439-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="30439-126">Speichern Sie [Ihre Wiederherstellungscodes](https://github.com/settings/auth/recovery-codes) an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="30439-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="30439-127">Aktualisieren Sie [Ihre öffentlichen Profileinstellungen.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="30439-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="30439-128">Legen Sie Ihren Namen \*\* und ihre öffentliche E-Mail auf "Meine E-Mail-Adresse *nicht anzeigen" festlegen.*</span><span class="sxs-lookup"><span data-stu-id="30439-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="30439-129">Es wird empfohlen, ein Profilbild hochzuladen, da eine Miniaturansicht auf Dokumentseiten angezeigt wird, zu der Sie beitragen.</span><span class="sxs-lookup"><span data-stu-id="30439-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="30439-130">Wenn Sie die Befehlszeile verwenden möchten, erwägen Sie die Einrichtung von [Git Credential Manager für Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="30439-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="30439-131">Auf diese Weise müssen Sie Ihr Kennwort nicht jedes Mal eingeben, wenn Sie einen Beitrag leisten.</span><span class="sxs-lookup"><span data-stu-id="30439-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="30439-132">Das Veröffentlichungssystem ist an GitHub gebunden, daher sind diese Schritte wichtig.</span><span class="sxs-lookup"><span data-stu-id="30439-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="30439-133">Sie werden entweder als Autor oder Mitwirkender für jeden Artikel mit Ihrem GitHub-Alias aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="30439-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="30439-134">Bearbeiten eines vorhandenen Artikels</span><span class="sxs-lookup"><span data-stu-id="30439-134">Editing an existing article</span></span>

<span data-ttu-id="30439-135">Verwenden Sie den folgenden Workflow, um aktualisierungen an *einem vorhandenen Artikel* über GitHub in einem Webbrowser:</span><span class="sxs-lookup"><span data-stu-id="30439-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="30439-136">Navigieren Sie im Ordner "mixed-reality-docs" zu dem Artikel, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="30439-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="30439-137">Wählen Sie oben rechts die Bearbeitungsschaltfläche (Stiftsymbol) aus, die automatisch einen verzweigten Zweig von der Verzweigung "Master" verzweigt.</span><span class="sxs-lookup"><span data-stu-id="30439-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Bearbeiten eines Artikels.](images/editpage.png)
   
3. <span data-ttu-id="30439-139">Bearbeiten Sie den Inhalt des Artikels gemäß den ["Markdown-Grundlagen".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="30439-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="30439-140">Aktualisieren Von Metadaten am Anfang jedes Artikels:</span><span class="sxs-lookup"><span data-stu-id="30439-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="30439-141">**title:** Seitentitel, der auf der Browserregisterkarte angezeigt wird, wenn der Artikel angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="30439-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="30439-142">Seitentitel werden für SEO und Indizierung verwendet. Ändern Sie daher den Titel nur, wenn dies erforderlich ist (dies ist jedoch weniger wichtig, bevor die Dokumentation veröffentlicht wird).</span><span class="sxs-lookup"><span data-stu-id="30439-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="30439-143">**description**: Schreiben Sie eine kurze Beschreibung der Inhalte des Artikels, die SEO und Ermittlung fördert.</span><span class="sxs-lookup"><span data-stu-id="30439-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="30439-144">**author:** Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren GitHub-Alias hinzu.</span><span class="sxs-lookup"><span data-stu-id="30439-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="30439-145">**ms.author**: Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren Microsoft-Alias hinzu (Sie benötigen nicht @microsoft.com, sondern nur den Alias).</span><span class="sxs-lookup"><span data-stu-id="30439-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="30439-146">**ms.date**: Aktualisieren Sie das Datum, wenn Sie der Seite hauptinhalt hinzufügen, aber nicht für Korrekturen wie Klarstellung, Formatierung, Grammatik oder Rechtschreibung.</span><span class="sxs-lookup"><span data-stu-id="30439-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="30439-147">**keywords**: Keywords aid in SEO (search engine optimization).</span><span class="sxs-lookup"><span data-stu-id="30439-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="30439-148">Fügen Sie Schlüsselwörter, getrennt durch ein Komma und ein Leerzeichen, hinzu, die für Ihren Artikel spezifisch sind, aber keine Interpunktion nach dem letzten Schlüsselwort in der Liste.</span><span class="sxs-lookup"><span data-stu-id="30439-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="30439-149">Sie müssen keine globalen Schlüsselwörter hinzufügen, die für alle Artikel gelten, da diese an anderer Stelle verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="30439-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="30439-150">Wenn Sie ihre Artikelbearbeitungen abgeschlossen haben, scrollen Sie nach unten, und wählen **Sie "Dateiänderung vorschlagen" aus.**</span><span class="sxs-lookup"><span data-stu-id="30439-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="30439-151">Wählen Sie auf der nächsten Seite **"Pullanforderung erstellen"** aus, um die automatisch erstellte Verzweigung in "Master" zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="30439-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="30439-152">Wiederholen Sie die obigen Schritte für den nächsten Artikel, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="30439-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="30439-153">Umbenennen oder Löschen eines vorhandenen Artikels</span><span class="sxs-lookup"><span data-stu-id="30439-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="30439-154">Wenn Ihre Änderung einen vorhandenen Artikel umbenennen oder löschen wird, müssen Sie eine Umleitung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="30439-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="30439-155">Auf diese Weise wird jeder Benutzer mit einem Link zum vorhandenen Artikel immer noch an der richtigen Stelle landen.</span><span class="sxs-lookup"><span data-stu-id="30439-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="30439-156">Umleitungen werden vom .openpublishing.redirection.jsA0 im Stammverzeichnis des Repositorys verwaltet.</span><span class="sxs-lookup"><span data-stu-id="30439-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="30439-157">Um eine Umleitung zu .openpublishing.redirection.jshinzuzufügen, fügen Sie dem Array einen Eintrag `redirections` hinzu:</span><span class="sxs-lookup"><span data-stu-id="30439-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="30439-158">Dies `source_path` ist der relative Repositorypfad zu dem alten Artikel, den Sie entfernen.</span><span class="sxs-lookup"><span data-stu-id="30439-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="30439-159">Stellen Sie sicher, dass der Pfad `mixed-reality-docs` mit beginnt und mit `.md` .</span><span class="sxs-lookup"><span data-stu-id="30439-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="30439-160">Dies `redirect_url` ist die relative öffentliche URL aus dem alten Artikel zum neuen Artikel.</span><span class="sxs-lookup"><span data-stu-id="30439-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="30439-161">Stellen Sie sicher, dass **diese** URL nicht enthalten ist, da sie auf die öffentliche URL und nicht auf `mixed-reality-docs` den `.md` Repositorypfad verweist.</span><span class="sxs-lookup"><span data-stu-id="30439-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="30439-162">Das Verknüpfen mit einem Abschnitt innerhalb des neuen Artikels ist `#section` zulässig.</span><span class="sxs-lookup"><span data-stu-id="30439-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="30439-163">Sie können hier bei Bedarf auch einen absoluten Pfad zu einer anderen Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="30439-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="30439-164">gibt an, ob sie die Dokument-ID aus der vorherigen Datei behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="30439-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="30439-165">Der Standardwert ist `false` .</span><span class="sxs-lookup"><span data-stu-id="30439-165">The default is `false`.</span></span> <span data-ttu-id="30439-166">Verwenden `true` Sie diese Eigenschaft, wenn Sie den `ms.documentid` Attributwert aus dem umgeleiteten Artikel beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="30439-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="30439-167">Wenn Sie die Dokument-ID beibehalten, werden Daten, z. B. Seitenansichten und Rangfolge, an den Zielartikel übertragen.</span><span class="sxs-lookup"><span data-stu-id="30439-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="30439-168">Tun Sie dies, wenn es sich bei der Umleitung in erster Linie um eine Umbenennung und nicht um einen Zeiger auf andere Artikel handelt, die nur einen Teil desselben Inhalts enthalten.</span><span class="sxs-lookup"><span data-stu-id="30439-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="30439-169">Wenn Sie eine Umleitung hinzufügen, müssen Sie auch die alte Datei löschen.</span><span class="sxs-lookup"><span data-stu-id="30439-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="30439-170">Erstellen eines neuen Artikels</span><span class="sxs-lookup"><span data-stu-id="30439-170">Creating a new article</span></span>

<span data-ttu-id="30439-171">Verwenden Sie den folgenden Workflow, *um neue Artikel* im Dokumentationsreposi bericht über GitHub in einem Webbrowser zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="30439-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="30439-172">Erstellen Sie eine Verzweigung von der Verzweigung "MicrosoftDocs/mixed-reality" "Master" (mit der Schaltfläche **"Verzweigung"** oben rechts).</span><span class="sxs-lookup"><span data-stu-id="30439-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Verzweigung des Hauptzweigs.](images/forkbranch.png)
   
2. <span data-ttu-id="30439-174">Wählen Sie im Ordner "mixed-reality-docs" oben rechts "Neue Datei erstellen" aus. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="30439-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="30439-175">Erstellen Sie einen Seitennamen für den Artikel (verwenden Sie Bindestriche anstelle von Leerzeichen und verwenden Sie keine Interpunktion oder Apostrophen), und hängen Sie ".md" an.</span><span class="sxs-lookup"><span data-stu-id="30439-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Benennen Sie die neue Seite.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="30439-177">Stellen Sie sicher, dass Sie den neuen Artikel im Ordner "mixed-reality-docs" erstellen.</span><span class="sxs-lookup"><span data-stu-id="30439-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="30439-178">Sie können dies bestätigen, indem Sie in der neuen Dateinamenzeile nach "/mixed-reality-docs/" suchen.</span><span class="sxs-lookup"><span data-stu-id="30439-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="30439-179">Fügen Sie oben auf der neuen Seite den folgenden Metadatenblock hinzu:</span><span class="sxs-lookup"><span data-stu-id="30439-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="30439-180">Füllen Sie die relevanten Metadatenfelder nach den Anweisungen im [abschnitt oben aus.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="30439-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="30439-181">Schreiben von Artikelinhalten mithilfe [von Markdown-Grundlagen.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="30439-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="30439-182">Fügen Sie am Ende des Artikels einen Abschnitt mit Links `## See also` zu anderen relevanten Artikeln hinzu.</span><span class="sxs-lookup"><span data-stu-id="30439-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="30439-183">Wenn Sie fertig sind, wählen **Sie Commit für neue Datei aus.**</span><span class="sxs-lookup"><span data-stu-id="30439-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="30439-184">Wählen **Sie "Neue Pullanforderung"** aus, und führen Sie die Verzweigung "Master" Ihrer Verzweigung mit "MicrosoftDocs/mixed-reality"master" zusammen (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).</span><span class="sxs-lookup"><span data-stu-id="30439-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Erstellen einer Pullanforderung von Ihrer Vererbung in MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <span data-ttu-id="30439-186">Grundlegendes zu Markdown</span><span class="sxs-lookup"><span data-stu-id="30439-186">Markdown basics</span></span>

<span data-ttu-id="30439-187">In den folgenden Ressourcen erfahren Sie, wie Sie die Dokumentation mit der Sprache Markdown bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="30439-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="30439-188">Grundlegendes zu Markdown</span><span class="sxs-lookup"><span data-stu-id="30439-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="30439-189">Zusätzliche Ressourcen zum Schreiben von Markdown für docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="30439-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="30439-190">Hinzufügen von Tabellen</span><span class="sxs-lookup"><span data-stu-id="30439-190">Adding tables</span></span>

<span data-ttu-id="30439-191">Aufgrund der Art docs.microsoft.com Formatvorlagentabellen verfügen sie nicht über Rahmen oder benutzerdefinierte Formatvorlagen, auch wenn Sie Inline-CSS ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="30439-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="30439-192">Es scheint für einen kurzen Zeitraum zu funktionieren, aber schließlich wird die Plattform die Formatierung aus der Tabelle verdingen.</span><span class="sxs-lookup"><span data-stu-id="30439-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="30439-193">Planen Sie also voraus, und halten Sie Ihre Tabellen einfach.</span><span class="sxs-lookup"><span data-stu-id="30439-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="30439-194">[Hier ist eine Website, die Die Tabelle Markdown erleichtert.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="30439-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="30439-195">Die [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) erleichtert auch die Tabellengenerierung, wenn Sie Visual Studio Code [(siehe unten)](#using-visual-studio-code) zum Bearbeiten der Dokumentation verwenden.</span><span class="sxs-lookup"><span data-stu-id="30439-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="30439-196">Hinzufügen von Bildern</span><span class="sxs-lookup"><span data-stu-id="30439-196">Adding images</span></span>

<span data-ttu-id="30439-197">Sie müssen Ihre Bilder in den Ordner "mixed-reality-docs/images" im Repository hochladen und dann im Artikel entsprechend darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="30439-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="30439-198">Bilder werden automatisch in voller Größe angezeigt, was bedeutet, dass große Bilder die gesamte Breite des Artikels ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="30439-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="30439-199">Es wird empfohlen, die Größe Ihrer Bilder vor dem Hochladen vorzubeisieren.</span><span class="sxs-lookup"><span data-stu-id="30439-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="30439-200">Die empfohlene Breite liegt zwischen 600 und 700 Pixel. Sie sollten die Größe jedoch nach oben oder unten ändern, wenn es sich um einen dichten Screenshot bzw. einen Bruchteil eines Screenshot handelt.</span><span class="sxs-lookup"><span data-stu-id="30439-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="30439-201">Sie können Bilder nur vor dem Zusammenführen in Ihr ver forkiertes Repository hochladen.</span><span class="sxs-lookup"><span data-stu-id="30439-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="30439-202">Wenn Sie also planen, Bilder zu einem Artikel hinzuzufügen, müssen Sie [zunächst Visual Studio Code](#using-visual-studio-code) verwenden, um die Bilder dem Ordner "Bilder" Ihrer Vererbung hinzuzufügen, oder stellen Sie sicher, dass Sie folgendes in einem Webbrowser durchgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="30439-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="30439-203">Ver forked the MicrosoftDocs/mixed-reality repo.</span><span class="sxs-lookup"><span data-stu-id="30439-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="30439-204">Der Artikel wurde in Ihrer Ver fork bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="30439-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="30439-205">Die Bilder, auf die Sie in Ihrem Artikel verweisen, wurden in den Ordner "mixed-reality-docs/images" in Ihrer Vererbung hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="30439-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="30439-206">Es wurde **eine Pullanforderung erstellt,** um Ihre Verzweigung mit der Verzweigung "MicrosoftDocs/mixed-reality"-Master zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="30439-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="30439-207">Um zu erfahren, wie Sie Ihr eigenes ver forkiertes Repository einrichten, folgen Sie den Anweisungen zum [Erstellen eines neuen Artikels.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="30439-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="30439-208">Anzeigen einer Vorschau Ihrer Arbeit</span><span class="sxs-lookup"><span data-stu-id="30439-208">Previewing your work</span></span>

<span data-ttu-id="30439-209">Beim Bearbeiten in GitHub über einen Webbrowser \*\*\*\* können Sie die Registerkarte "Vorschau" am oberen Rand der Seite auswählen, um vor dem Commit eine Vorschau Ihrer Arbeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="30439-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="30439-210">Das Anzeigen einer Vorschau Ihrer Änderungen auf review.docs.microsoft.com ist nur für Mitarbeiter von Microsoft verfügbar</span><span class="sxs-lookup"><span data-stu-id="30439-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="30439-211">Microsoft-Mitarbeiter: Nachdem Ihre Beiträge mit dem Hauptzweig zusammengeführt wurden, können Sie die Inhalte überprüfen, bevor sie öffentlich https://review.docs.microsoft.com/hololens?branch=master werden.</span><span class="sxs-lookup"><span data-stu-id="30439-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="30439-212">Suchen Sie Ihren Artikel mithilfe des Inhaltsverzeichnisses in der linken Spalte.</span><span class="sxs-lookup"><span data-stu-id="30439-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="30439-213">Bearbeiten im Browser im Vergleich zur Bearbeitung mit einem Desktopclient</span><span class="sxs-lookup"><span data-stu-id="30439-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="30439-214">Die Bearbeitung im Browser ist die einfachste Möglichkeit, schnelle Änderungen vorzunehmen, es gibt jedoch einige Nachteile:</span><span class="sxs-lookup"><span data-stu-id="30439-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="30439-215">Sie erhalten keine Rechtschreibprüfung.</span><span class="sxs-lookup"><span data-stu-id="30439-215">You don't get spell-check.</span></span>
- <span data-ttu-id="30439-216">Sie erhalten keine intelligente Verknüpfung mit anderen Artikeln (Sie müssen den Dateinamen des Artikels manuell eingeben).</span><span class="sxs-lookup"><span data-stu-id="30439-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="30439-217">Das Hochladen und Verweisen auf Bilder kann sehr einfach sein.</span><span class="sxs-lookup"><span data-stu-id="30439-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="30439-218">Wenn Sie diese Probleme lieber nicht beheben möchten, verwenden Sie einen Desktopclient wie [Visual Studio Code](https://code.visualstudio.com/) mit einigen hilfreichen [Erweiterungen,](#useful-extensions) wenn Sie dazu beitragen.</span><span class="sxs-lookup"><span data-stu-id="30439-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="30439-219">Verwenden Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="30439-219">Using Visual Studio Code</span></span>

<span data-ttu-id="30439-220">Aus den oben [aufgeführten Gründen](#editing-in-the-browser-vs-editing-with-a-desktop-client)bevorzugen Sie möglicherweise die Verwendung eines Desktopclients zum Bearbeiten der Dokumentation anstelle eines Webbrowsers.</span><span class="sxs-lookup"><span data-stu-id="30439-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="30439-221">Es wird empfohlen, [Visual Studio Code zu verwenden.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="30439-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="30439-222">Setup</span><span class="sxs-lookup"><span data-stu-id="30439-222">Setup</span></span>

<span data-ttu-id="30439-223">Führen Sie die folgenden Schritte aus, um Visual Studio Code für die Arbeit mit diesem Repository zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="30439-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="30439-224">In einem Webbrowser:</span><span class="sxs-lookup"><span data-stu-id="30439-224">In a web browser:</span></span>
    1. <span data-ttu-id="30439-225">Installieren [Sie Git für Ihren PC.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="30439-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="30439-226">Installieren [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="30439-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="30439-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span><span class="sxs-lookup"><span data-stu-id="30439-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="30439-228">Wählen Sie in Ihrer Vererbung **Klonen oder Herunterladen und** Kopieren der URL aus.</span><span class="sxs-lookup"><span data-stu-id="30439-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="30439-229">Erstellen Sie einen lokalen Klon Ihrer Ver fork in Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="30439-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="30439-230">Wählen Sie **im Menü** "Ansicht" die **Befehlspalette aus.**</span><span class="sxs-lookup"><span data-stu-id="30439-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="30439-231">Geben Sie "Git: Klonen" ein.</span><span class="sxs-lookup"><span data-stu-id="30439-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="30439-232">Fügen Sie die kopierte URL ein.</span><span class="sxs-lookup"><span data-stu-id="30439-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="30439-233">Wählen Sie aus, wo der Klon auf Ihrem PC gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="30439-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="30439-234">Wählen **Sie im** Popup "Repository öffnen" aus.</span><span class="sxs-lookup"><span data-stu-id="30439-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="30439-235">Bearbeitungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="30439-235">Editing documentation</span></span>

<span data-ttu-id="30439-236">Verwenden Sie den folgenden Workflow, um Änderungen an der Dokumentation mit Visual Studio vorzunehmen:</span><span class="sxs-lookup"><span data-stu-id="30439-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="30439-237">Alle Anleitungen [zum](#editing-an-existing-article) Bearbeiten und Erstellen von Artikeln sowie die Grundlagen der Bearbeitung von [Markdown](#markdown-basics)von oben gelten auch bei verwendung von Visual Studio Code. [](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="30439-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="30439-238">Stellen Sie sicher, dass Die geklonte Ver fork mit dem offiziellen Repository auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="30439-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="30439-239">Erstellen Sie in einem Webbrowser eine Pullanforderung, um aktuelle Änderungen von anderen Mitwirkenden in MicrosoftDocs/Mixed-Reality-"Master" mit Ihrer Vererbung zu synchronisieren (stellen Sie sicher, dass der Pfeil auf den richtigen Weg zeigt).</span><span class="sxs-lookup"><span data-stu-id="30439-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchronisieren von Änderungen von MicrosoftDocs/mixed-reality mit Ihrer Vererbung](images/sync-repos.png)
      
   2. <span data-ttu-id="30439-241">Wählen Visual Studio Code die Synchronisierungsschaltfläche aus, um die aktualisierte Ver fork mit dem lokalen Klon zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="30439-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Klicken Sie auf das Bild der Synchronisierungsschaltfläche.](images/sync-clone.png)
      
2. <span data-ttu-id="30439-243">Erstellen oder bearbeiten Sie Artikel in Ihrem geklonten Repository mithilfe Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="30439-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="30439-244">Bearbeiten Sie einen oder mehrere Artikel (fügen Sie bei Bedarf Bilder zum Ordner "Bilder" hinzu).</span><span class="sxs-lookup"><span data-stu-id="30439-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="30439-245">**Änderungen** im **Explorer speichern.**</span><span class="sxs-lookup"><span data-stu-id="30439-245">**Save** changes in **Explorer**.</span></span>
      
      ![Choose "Save all" in Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="30439-247">**Commit aller** Änderungen in der **Quellcodeverwaltung** (Commitnachricht schreiben, wenn Sie dazu aufgefordert werden).</span><span class="sxs-lookup"><span data-stu-id="30439-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Wählen Sie in der Quellcodeverwaltung "Commit für alle" aus.](images/source-control-commit.png)
      
   4. <span data-ttu-id="30439-249">Wählen Sie die **Synchronisierungsschaltfläche** aus, um Ihre Änderungen wieder mit dem Ursprung zu synchronisieren (Ihre Vererbung auf GitHub).</span><span class="sxs-lookup"><span data-stu-id="30439-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Klicken Sie auf die Schaltfläche "Synchronisierung".](images/sync-back.png)
      
3. <span data-ttu-id="30439-251">Erstellen Sie in einem Webbrowser eine Pullanforderung, um neue Änderungen in Ihrer Ver fork zurück zu MicrosoftDocs/Mixed-Reality-Master zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).</span><span class="sxs-lookup"><span data-stu-id="30439-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Erstellen einer Pullanforderung von Ihrer Vererbung in MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <span data-ttu-id="30439-253">Nützliche Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="30439-253">Useful extensions</span></span>

<span data-ttu-id="30439-254">Die folgenden Visual Studio Codeerweiterungen sind beim Bearbeiten der Dokumentation hilfreich:</span><span class="sxs-lookup"><span data-stu-id="30439-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="30439-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **ALT+M** to bring up a menu of docs authoring options like:</span><span class="sxs-lookup"><span data-stu-id="30439-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="30439-256">Suchen und Referenzieren von Bildern, die Sie hochgeladen haben.</span><span class="sxs-lookup"><span data-stu-id="30439-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="30439-257">Fügen Sie Formatierungen wie Listen, Tabellen und dokumentspezifische Call-Outs hinzu, z. `>[!NOTE]` B. .</span><span class="sxs-lookup"><span data-stu-id="30439-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="30439-258">Suchen und Verweisen auf interne Links und Lesezeichen (Links zu bestimmten Abschnitten auf einer Seite).</span><span class="sxs-lookup"><span data-stu-id="30439-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="30439-259">Formatierungsfehler werden hervorgehoben (zeigen Sie mit der Maus auf den Fehler, um mehr zu erfahren).</span><span class="sxs-lookup"><span data-stu-id="30439-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="30439-260">[Code spell checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – falsch geschriebene Wörter werden unterstrichen; Klicken Sie mit der rechten Maustaste auf ein falsch geschriebenes Wort, um es zu ändern oder im Wörterbuch zu speichern.</span><span class="sxs-lookup"><span data-stu-id="30439-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
