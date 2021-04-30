---
title: Anleitungen für Mitwirkende
description: Erfahren Sie, wie Sie mit gitHub-flavored Markdown zur HoloLens-Dokumentation auf der docs.microsoft.com-Plattform beitragen.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308612"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="20e03-103">Mitwirken an der HoloLens-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="20e03-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="20e03-104">Willkommen bei der [HoloLens-Dokumentation!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="20e03-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="20e03-105">Alle Artikel, die Sie in diesem Repository erstellen oder **bearbeiten, sind für die Öffentlichkeit sichtbar.**</span><span class="sxs-lookup"><span data-stu-id="20e03-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="20e03-106">HoloLens-Dokumente werden auf der docs.microsoft.com-Plattform angezeigt, die Markdown mit GitHub-Varianten mit Markdig-Features verwendet.</span><span class="sxs-lookup"><span data-stu-id="20e03-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="20e03-107">Der Inhalt, den Sie in diesem Repository bearbeiten, wird in stilisierte Seiten formatiert, die unter angezeigt https://docs.microsoft.com/hololens werden.</span><span class="sxs-lookup"><span data-stu-id="20e03-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="20e03-108">Auf dieser Seite werden die grundlegenden Schritte und Richtlinien für beiträge und Links zu Markdown-Grundlagen behandelt.</span><span class="sxs-lookup"><span data-stu-id="20e03-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="20e03-109">Vielen Dank für Ihren Beitrag!</span><span class="sxs-lookup"><span data-stu-id="20e03-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="20e03-110">Verfügbare Repositorys</span><span class="sxs-lookup"><span data-stu-id="20e03-110">Available repos</span></span>

| <span data-ttu-id="20e03-111">Name des Repositorys</span><span class="sxs-lookup"><span data-stu-id="20e03-111">Repository name</span></span> | <span data-ttu-id="20e03-112">URL</span><span class="sxs-lookup"><span data-stu-id="20e03-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="20e03-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="20e03-113">HoloLens</span></span> | [<span data-ttu-id="20e03-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="20e03-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="20e03-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="20e03-115">Mixed Reality</span></span> | [<span data-ttu-id="20e03-116">MicrosoftDocs/Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="20e03-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="20e03-117">VR-Handbuch für Fans</span><span class="sxs-lookup"><span data-stu-id="20e03-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="20e03-118">MicrosoftDocs/mixed-reality/fan-guide</span><span class="sxs-lookup"><span data-stu-id="20e03-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="20e03-119">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="20e03-119">Before you start</span></span>

<span data-ttu-id="20e03-120">Wenn Sie noch keins besitzen, müssen Sie [ein GitHub-Konto erstellen.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="20e03-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="20e03-121">Wenn Sie Microsoft-Mitarbeiter sind, verknüpfen Sie Ihr GitHub-Konto mit Ihrem Microsoft-Alias im [Microsoft Open Source-Portal.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="20e03-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="20e03-122">Treten Sie den Organisationen **"Microsoft"** und **"MicrosoftDocs"** bei.</span><span class="sxs-lookup"><span data-stu-id="20e03-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="20e03-123">Beim Einrichten Ihres GitHub-Kontos empfehlen wir auch die folgenden Sicherheitsvorkehrungen:</span><span class="sxs-lookup"><span data-stu-id="20e03-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="20e03-124">Erstellen Sie ein [sicheres Kennwort für Ihr GitHub-Konto.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="20e03-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="20e03-125">Aktivieren Sie [die zweistufige Authentifizierung.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="20e03-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="20e03-126">Speichern Sie [Ihre Wiederherstellungscodes](https://github.com/settings/auth/recovery-codes) an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="20e03-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="20e03-127">Aktualisieren Sie die [Einstellungen für Ihr öffentliches Profil.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="20e03-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="20e03-128">Legen Sie Ihren Namen fest, und legen Sie Ihre *öffentliche E-Mail-Adresse* *auf Don't show my email address (Meine E-Mail-Adresse nicht anzeigen) fest.*</span><span class="sxs-lookup"><span data-stu-id="20e03-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="20e03-129">Es wird empfohlen, ein Profilbild hochzuladen, da eine Miniaturansicht auf Dokumentationsseiten angezeigt wird, zu der Sie beitragen.</span><span class="sxs-lookup"><span data-stu-id="20e03-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="20e03-130">Wenn Sie die Befehlszeile verwenden möchten, sollten Sie git Anmeldeinformationsverwaltung [für Windows einrichten.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="20e03-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="20e03-131">Auf diese Weise müssen Sie ihr Kennwort nicht jedes Mal eingeben, wenn Sie einen Beitrag leisten.</span><span class="sxs-lookup"><span data-stu-id="20e03-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="20e03-132">Da das Veröffentlichungssystem an GitHub gebunden ist, sind diese Schritte wichtig.</span><span class="sxs-lookup"><span data-stu-id="20e03-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="20e03-133">Sie werden entweder als Autor oder Mitwirkender für jeden Artikel aufgeführt, indem Sie Ihren GitHub-Alias verwenden.</span><span class="sxs-lookup"><span data-stu-id="20e03-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="20e03-134">Bearbeiten eines vorhandenen Artikels</span><span class="sxs-lookup"><span data-stu-id="20e03-134">Editing an existing article</span></span>

<span data-ttu-id="20e03-135">Verwenden Sie den folgenden  Workflow, um über GitHub in einem Webbrowser Updates für einen vorhandenen Artikel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="20e03-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="20e03-136">Navigieren Sie zu dem Artikel, den Sie im Ordner "mixed-reality-docs" bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="20e03-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="20e03-137">Wählen Sie oben rechts die Bearbeitungsschaltfläche (Stiftsymbol) aus, die automatisch eine verwerfbar verzweigte Verzweigung aus der Verzweigung "master" verzweigt.</span><span class="sxs-lookup"><span data-stu-id="20e03-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Bearbeiten Sie einen Artikel.](images/editpage.png)
   
3. <span data-ttu-id="20e03-139">Bearbeiten Sie den Inhalt des Artikels gemäß den ["Markdowngrundkenntnissen".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="20e03-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="20e03-140">Aktualisieren Sie die Metadaten am Anfang jedes Artikels:</span><span class="sxs-lookup"><span data-stu-id="20e03-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="20e03-141">**title:** Seitentitel, der auf der Browserregisterkarte angezeigt wird, wenn der Artikel angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="20e03-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="20e03-142">Seitentitel werden für SEO und Indizierung verwendet. Ändern Sie daher den Titel nur, wenn dies erforderlich ist (obwohl dies weniger wichtig ist, bevor die Dokumentation öffentlich wird).</span><span class="sxs-lookup"><span data-stu-id="20e03-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="20e03-143">**description:** Schreiben Sie eine kurze Beschreibung des Artikels, wodurch SEO und Ermittlung verstärkt werden.</span><span class="sxs-lookup"><span data-stu-id="20e03-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="20e03-144">**author:** Wenn Sie der Hauptbesitzer der Seite sind, fügen Sie hier Ihren GitHub-Alias hinzu.</span><span class="sxs-lookup"><span data-stu-id="20e03-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="20e03-145">**ms.author:** Wenn Sie der Hauptbesitzer der Seite sind, fügen Sie hier Ihren Microsoft-Alias hinzu (Sie benötigen @microsoft.com nicht , sondern nur den Alias).</span><span class="sxs-lookup"><span data-stu-id="20e03-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="20e03-146">**ms.date:** Aktualisieren Sie das Datum, wenn Sie der Seite Hauptinhalte hinzufügen, aber nicht für Korrekturen wie Erläuterungen, Formatierung, Grammatik oder Rechtschreibung.</span><span class="sxs-lookup"><span data-stu-id="20e03-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="20e03-147">**keywords:** Schlüsselwörter helfen bei SEO (Suchmaschinenoptimierung).</span><span class="sxs-lookup"><span data-stu-id="20e03-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="20e03-148">Fügen Sie Schlüsselwörter hinzu, die durch ein Komma und ein Leerzeichen getrennt sind, die für Ihren Artikel spezifisch sind, aber keine Interpunktion nach dem letzten Schlüsselwort in Der Liste.</span><span class="sxs-lookup"><span data-stu-id="20e03-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="20e03-149">Sie müssen keine globalen Schlüsselwörter hinzufügen, die für alle Artikel gelten, da diese an anderer Stelle verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="20e03-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="20e03-150">Wenn Sie ihre Artikelbearbeitungen abgeschlossen haben, scrollen Sie nach unten, und wählen **Sie Dateiänderung vorschlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="20e03-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="20e03-151">Wählen Sie auf der nächsten Seite **Pull Request erstellen** aus, um ihren automatisch erstellten Branch in "master" zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="20e03-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="20e03-152">Wiederholen Sie die obigen Schritte für den nächsten Artikel, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="20e03-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="20e03-153">Umbenennen oder Löschen eines vorhandenen Artikels</span><span class="sxs-lookup"><span data-stu-id="20e03-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="20e03-154">Wenn Ihre Änderung einen vorhandenen Artikel umbenennen oder löschen wird, fügen Sie unbedingt eine Umleitung hinzu.</span><span class="sxs-lookup"><span data-stu-id="20e03-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="20e03-155">Auf diese Weise wird jeder Benutzer mit einem Link zum vorhandenen Artikel immer noch am richtigen Ort sein.</span><span class="sxs-lookup"><span data-stu-id="20e03-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="20e03-156">Umleitungen werden vom .openpublishing.redirection.jsin der Datei im Stammverzeichnis des Repositorys verwaltet.</span><span class="sxs-lookup"><span data-stu-id="20e03-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="20e03-157">Um eine Umleitung zu .openpublishing.redirection.jshinzuzufügen, fügen Sie dem Array einen Eintrag `redirections` hinzu:</span><span class="sxs-lookup"><span data-stu-id="20e03-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="20e03-158">`source_path`ist der relative Repositorypfad zum alten Artikel, den Sie entfernen.</span><span class="sxs-lookup"><span data-stu-id="20e03-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="20e03-159">Stellen Sie sicher, dass der Pfad mit beginnt `mixed-reality-docs` und mit `.md` endet.</span><span class="sxs-lookup"><span data-stu-id="20e03-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="20e03-160">ist `redirect_url` die relative öffentliche URL aus dem alten Artikel zum neuen Artikel.</span><span class="sxs-lookup"><span data-stu-id="20e03-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="20e03-161">Stellen Sie sicher, dass diese URL **nicht** `mixed-reality-docs` oder `.md` enthält, da sie auf die öffentliche URL und nicht auf den Repositorypfad verweist.</span><span class="sxs-lookup"><span data-stu-id="20e03-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="20e03-162">Das Verknüpfen mit einem Abschnitt innerhalb des neuen Artikels mit `#section` ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="20e03-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="20e03-163">Sie können hier bei Bedarf auch einen absoluten Pfad zu einer anderen Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="20e03-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="20e03-164">`redirect_document_id` gibt an, ob Sie die Dokument-ID aus der vorherigen Datei beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="20e03-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="20e03-165">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="20e03-165">The default is `false`.</span></span> <span data-ttu-id="20e03-166">Verwenden `true` Sie , wenn Sie den `ms.documentid` Attributwert aus dem umgeleiteten Artikel beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="20e03-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="20e03-167">Wenn Sie die Dokument-ID beibehalten, werden Daten wie Seitenaufrufe und Rangfolge an den Zielartikel übertragen.</span><span class="sxs-lookup"><span data-stu-id="20e03-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="20e03-168">Tun Sie dies, wenn die Umleitung in erster Linie eine Umbenennung und kein Zeiger auf einen anderen Artikel ist, der nur einen Teil desselben Inhalts abdeckt.</span><span class="sxs-lookup"><span data-stu-id="20e03-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="20e03-169">Wenn Sie eine Umleitung hinzufügen, müssen Sie auch die alte Datei löschen.</span><span class="sxs-lookup"><span data-stu-id="20e03-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="20e03-170">Erstellen eines neuen Artikels</span><span class="sxs-lookup"><span data-stu-id="20e03-170">Creating a new article</span></span>

<span data-ttu-id="20e03-171">Verwenden Sie den folgenden Workflow, *um neue Artikel im* Dokumentationsre repo über GitHub in einem Webbrowser zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="20e03-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="20e03-172">Erstellen Sie einen Fork aus dem Branch "Master" von  MicrosoftDocs/Mixed Reality (mithilfe der Verzweigungsschaltfläche oben rechts).</span><span class="sxs-lookup"><span data-stu-id="20e03-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Forken Sie den Masterzweig.](images/forkbranch.png)
   
2. <span data-ttu-id="20e03-174">Wählen Sie oben rechts im Ordner "mixed-reality-docs" die Option Neue Datei erstellen aus. </span><span class="sxs-lookup"><span data-stu-id="20e03-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="20e03-175">Erstellen Sie einen Seitennamen für den Artikel (verwenden Sie Bindestriche anstelle von Leerzeichen, und verwenden Sie keine Satzzeichen oder Apostrophe), und fügen Sie ".md" an.</span><span class="sxs-lookup"><span data-stu-id="20e03-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nennen Sie die neue Seite.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="20e03-177">Stellen Sie sicher, dass Sie den neuen Artikel im Ordner "mixed-reality-docs" erstellen.</span><span class="sxs-lookup"><span data-stu-id="20e03-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="20e03-178">Sie können dies bestätigen, indem Sie in der neuen Dateinamenszeile nach "/mixed-reality-docs/" überprüfen.</span><span class="sxs-lookup"><span data-stu-id="20e03-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="20e03-179">Fügen Sie oben auf der neuen Seite den folgenden Metadatenblock hinzu:</span><span class="sxs-lookup"><span data-stu-id="20e03-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="20e03-180">Füllen Sie die relevanten Metadatenfelder entsprechend den Anweisungen im [Abschnitt oben aus.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="20e03-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="20e03-181">Schreiben von Artikelinhalten [mithilfe der Markdown-Grundlagen.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="20e03-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="20e03-182">Fügen Sie am Ende des Artikels einen Abschnitt mit Links `## See also` zu anderen relevanten Artikeln hinzu.</span><span class="sxs-lookup"><span data-stu-id="20e03-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="20e03-183">Wählen Sie anschließend Commit **new file (Neue Datei commiten) aus.**</span><span class="sxs-lookup"><span data-stu-id="20e03-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="20e03-184">Wählen **Sie Neuer Pull Request** aus, und führen Sie den Branch "master" Ihres Forks in MicrosoftDocs/Mixed Reality "master" zusammen (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).</span><span class="sxs-lookup"><span data-stu-id="20e03-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Erstellen eines Pull Requests aus Ihrem Fork in MicrosoftDocs/Mixed Reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="20e03-186">Grundlegendes zu Markdown</span><span class="sxs-lookup"><span data-stu-id="20e03-186">Markdown basics</span></span>

<span data-ttu-id="20e03-187">Die folgenden Ressourcen helfen Ihnen, zu erfahren, wie Sie die Dokumentation mithilfe der Markdownsprache bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="20e03-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="20e03-188">Markdown-Grundlagen</span><span class="sxs-lookup"><span data-stu-id="20e03-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="20e03-189">Zusätzliche Ressourcen zum Schreiben von Markdown für docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="20e03-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="20e03-190">Hinzufügen von Tabellen</span><span class="sxs-lookup"><span data-stu-id="20e03-190">Adding tables</span></span>

<span data-ttu-id="20e03-191">Aufgrund der Art und Weise, wie Tabellen docs.microsoft.com, verfügen sie nicht über Rahmen oder benutzerdefinierte Stile, auch wenn Sie INLINE-CSS ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="20e03-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="20e03-192">Es scheint für einen kurzen Zeitraum zu funktionieren, aber schließlich entfernt die Plattform den Stil aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="20e03-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="20e03-193">Planen Sie also voraus, und halten Sie Ihre Tabellen einfach.</span><span class="sxs-lookup"><span data-stu-id="20e03-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="20e03-194">[Hier ist eine Website, die Markdowntabellen einfach macht.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="20e03-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="20e03-195">Die [Docs Markdown-Erweiterung für Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) vereinfacht auch die Tabellengenerierung, wenn Sie Visual Studio Code verwenden [(siehe unten),](#using-visual-studio-code) um die Dokumentation zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="20e03-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="20e03-196">Hinzufügen von Bildern</span><span class="sxs-lookup"><span data-stu-id="20e03-196">Adding images</span></span>

<span data-ttu-id="20e03-197">Sie müssen Ihre Bilder in den Ordner "mixed-reality-docs/images" im Repository hochladen und dann im Artikel entsprechend darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="20e03-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="20e03-198">Bilder werden automatisch in voller Größe angezeigt, was bedeutet, dass große Bilder die gesamte Breite des Artikels ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="20e03-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="20e03-199">Es wird empfohlen, die Größe Ihrer Bilder vorab zu dimensionieren, bevor Sie sie hochladen.</span><span class="sxs-lookup"><span data-stu-id="20e03-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="20e03-200">Die empfohlene Breite liegt zwischen 600 und 700 Pixel. Sie sollten die Größe jedoch nach oben oder unten anpassen, wenn es sich um einen dichten Screenshot bzw. einen Bruchteil eines Screenshots handelt.</span><span class="sxs-lookup"><span data-stu-id="20e03-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="20e03-201">Sie können Bilder nur vor dem Zusammenführen in Ihr gezweigtes Repository hochladen.</span><span class="sxs-lookup"><span data-stu-id="20e03-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="20e03-202">Wenn Sie also einem Artikel Bilder hinzufügen möchten, müssen Sie [Visual Studio Code verwenden,](#using-visual-studio-code) um die Bilder zuerst dem Ordner "images" Ihrer Verzweigung hinzuzufügen, oder stellen Sie sicher, dass Sie folgende Schritte in einem Webbrowser ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="20e03-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="20e03-203">Forked the MicrosoftDocs/mixed-reality repo.</span><span class="sxs-lookup"><span data-stu-id="20e03-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="20e03-204">Der Artikel in Ihrer Verzweigung wurde bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="20e03-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="20e03-205">Laden Sie die Bilder, auf die Sie in Ihrem Artikel verweisen, in den Ordner "mixed-reality-docs/images" in Ihrem Fork hoch.</span><span class="sxs-lookup"><span data-stu-id="20e03-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="20e03-206">Es wurde ein **Pull Request** erstellt, um Ihre Verzweigung mit dem MicrosoftDocs/Mixed Reality-Branch "master" zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="20e03-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="20e03-207">Um zu erfahren, wie Sie Ihr eigenes gezweigtes Repository einrichten, befolgen Sie die Anweisungen zum [Erstellen eines neuen Artikels](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="20e03-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="20e03-208">Anzeigen einer Vorschau Ihrer Arbeit</span><span class="sxs-lookup"><span data-stu-id="20e03-208">Previewing your work</span></span>

<span data-ttu-id="20e03-209">Beim Bearbeiten in GitHub über einen Webbrowser  können Sie oben auf der Seite die Registerkarte Vorschau auswählen, um eine Vorschau Ihrer Arbeit anzuzeigen, bevor Sie einen Commit committen.</span><span class="sxs-lookup"><span data-stu-id="20e03-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="20e03-210">Die Vorschau Ihrer Änderungen auf review.docs.microsoft.com ist nur für Microsoft-Mitarbeiter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="20e03-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="20e03-211">Microsoft-Mitarbeiter: Nachdem Ihre Beiträge mit dem Branch "master" zusammengeführt wurden, können Sie den Inhalt überprüfen, bevor er unter veröffentlicht https://review.docs.microsoft.com/hololens?branch=master wird.</span><span class="sxs-lookup"><span data-stu-id="20e03-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="20e03-212">Suchen Sie Ihren Artikel mithilfe des Inhaltsverzeichnis in der linken Spalte.</span><span class="sxs-lookup"><span data-stu-id="20e03-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="20e03-213">Bearbeiten im Browser im Vergleich zur Bearbeitung mit einem Desktopclient</span><span class="sxs-lookup"><span data-stu-id="20e03-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="20e03-214">Die Bearbeitung im Browser ist die einfachste Möglichkeit, um schnelle Änderungen vorzunehmen. Es gibt jedoch einige Nachteile:</span><span class="sxs-lookup"><span data-stu-id="20e03-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="20e03-215">Sie erhalten keine Rechtschreibprüfung.</span><span class="sxs-lookup"><span data-stu-id="20e03-215">You don't get spell-check.</span></span>
- <span data-ttu-id="20e03-216">Sie erhalten keine intelligente Verknüpfung mit anderen Artikeln (Sie müssen den Dateinamen des Artikels manuell eingeben).</span><span class="sxs-lookup"><span data-stu-id="20e03-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="20e03-217">Es kann mühsam sein, Bilder hochzuladen und darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="20e03-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="20e03-218">Wenn Sie diese Probleme nicht behandeln möchten, verwenden Sie einen Desktopclient [](#useful-extensions) wie [Visual Studio Code](https://code.visualstudio.com/) mit einigen hilfreichen Erweiterungen, wenn Sie mitwirken.</span><span class="sxs-lookup"><span data-stu-id="20e03-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="20e03-219">Verwendung von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="20e03-219">Using Visual Studio Code</span></span>

<span data-ttu-id="20e03-220">Aus den oben [genannten Gründen](#editing-in-the-browser-vs-editing-with-a-desktop-client)können Sie die Verwendung eines Desktopclients zum Bearbeiten der Dokumentation anstelle eines Webbrowsers bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="20e03-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="20e03-221">Wir empfehlen die Verwendung von [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="20e03-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="20e03-222">Setup</span><span class="sxs-lookup"><span data-stu-id="20e03-222">Setup</span></span>

<span data-ttu-id="20e03-223">Führen Sie die folgenden Schritte aus, um Visual Studio Code für die Arbeit mit diesem Repository zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="20e03-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="20e03-224">In einem Webbrowser:</span><span class="sxs-lookup"><span data-stu-id="20e03-224">In a web browser:</span></span>
    1. <span data-ttu-id="20e03-225">Installieren [Sie Git für Ihren PC.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="20e03-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="20e03-226">Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="20e03-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="20e03-227">[Forken Sie MicrosoftDocs/mixed-reality,](#creating-a-new-article) sofern noch nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="20e03-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="20e03-228">Wählen Sie in Ihrem Fork **Klonen oder herunterladen aus,** und kopieren Sie die URL.</span><span class="sxs-lookup"><span data-stu-id="20e03-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="20e03-229">Erstellen Sie einen lokalen Klon Ihrer Vererbung in Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="20e03-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="20e03-230">Wählen Sie **im Menü** Ansicht die Option **Befehlspalette aus.**</span><span class="sxs-lookup"><span data-stu-id="20e03-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="20e03-231">Geben Sie "Git: Clone" ein.</span><span class="sxs-lookup"><span data-stu-id="20e03-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="20e03-232">Fügen Sie die kopierte URL ein.</span><span class="sxs-lookup"><span data-stu-id="20e03-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="20e03-233">Wählen Sie aus, wo der Klon auf Ihrem PC gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20e03-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="20e03-234">Wählen Sie im Popupfenster **Repository öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="20e03-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="20e03-235">Bearbeiten der Dokumentation</span><span class="sxs-lookup"><span data-stu-id="20e03-235">Editing documentation</span></span>

<span data-ttu-id="20e03-236">Verwenden Sie den folgenden Workflow, um änderungen an der Dokumentation mit Visual Studio Code vorzunehmen:</span><span class="sxs-lookup"><span data-stu-id="20e03-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="20e03-237">Alle Anleitungen zum [Bearbeiten](#editing-an-existing-article) und [Erstellen von](#creating-a-new-article) Artikeln sowie die Grundlagen der Bearbeitung [von Markdown](#markdown-basics)von oben gelten auch bei Verwendung von Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="20e03-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="20e03-238">Stellen Sie sicher, dass Ihr geklonter Fork mit dem offiziellen Repository auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="20e03-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="20e03-239">Erstellen Sie in einem Webbrowser einen Pull Request, um aktuelle Änderungen anderer Mitwirkender in MicrosoftDocs/mixed-reality "master" mit Ihrer Verzweigung zu synchronisieren (stellen Sie sicher, dass der Pfeil den richtigen Weg zeigt).</span><span class="sxs-lookup"><span data-stu-id="20e03-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchronisieren von Änderungen von MicrosoftDocs/Mixed Reality mit Ihrer Verzweigung](images/sync-repos.png)
      
   2. <span data-ttu-id="20e03-241">Wählen Sie in Visual Studio Code die Schaltfläche sync aus, um Ihre neu aktualisierte Verzweigung mit dem lokalen Klon zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="20e03-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Klicken Sie auf das Bild der Synchronisierungsschaltfläche.](images/sync-clone.png)
      
2. <span data-ttu-id="20e03-243">Erstellen oder bearbeiten Sie Artikel in Ihrem geklonten Repository mithilfe Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="20e03-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="20e03-244">Bearbeiten Sie einen oder mehrere Artikel (fügen Sie bei Bedarf Bilder zum Ordner "images" hinzu).</span><span class="sxs-lookup"><span data-stu-id="20e03-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="20e03-245">**Speichern Sie** die Änderungen im **Explorer.**</span><span class="sxs-lookup"><span data-stu-id="20e03-245">**Save** changes in **Explorer**.</span></span>
      
      ![Auswählen von "Alle speichern" im Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="20e03-247">**Committen Sie alle** Änderungen in der **Quellcodeverwaltung** (schreiben Sie eine Commitnachricht, wenn Sie dazu aufgefordert werden).</span><span class="sxs-lookup"><span data-stu-id="20e03-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Auswählen von "Commit all" in der Quellcodeverwaltung](images/source-control-commit.png)
      
   4. <span data-ttu-id="20e03-249">Wählen Sie die Schaltfläche **"Synchronisieren"** aus, um Ihre Änderungen wieder mit dem Ursprung zu synchronisieren (Ihre Verzweigung auf GitHub).</span><span class="sxs-lookup"><span data-stu-id="20e03-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Klicken Sie auf die Schaltfläche "Synchronisieren".](images/sync-back.png)
      
3. <span data-ttu-id="20e03-251">Erstellen Sie in einem Webbrowser einen Pull Request, um neue Änderungen in Ihrer Verzweigung mit MicrosoftDocs/mixed-reality "master" zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).</span><span class="sxs-lookup"><span data-stu-id="20e03-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Erstellen eines Pull Requests aus Ihrer Verzweigung in MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="20e03-253">Nützliche Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="20e03-253">Useful extensions</span></span>

<span data-ttu-id="20e03-254">Die folgenden Visual Studio Code-Erweiterungen sind beim Bearbeiten der Dokumentation nützlich:</span><span class="sxs-lookup"><span data-stu-id="20e03-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="20e03-255">[Docs Markdown-Erweiterung für Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) Verwenden Sie **ALT+M,** um ein Menü mit Dokumenterstellungsoptionen wie den folgenden zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="20e03-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="20e03-256">Suchen Sie bilder, und verweisen Sie auf Bilder, die Sie hochgeladen haben.</span><span class="sxs-lookup"><span data-stu-id="20e03-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="20e03-257">Fügen Sie Formatierungen wie Listen, Tabellen und dokumentspezifische Aufrufe wie `>[!NOTE]` hinzu.</span><span class="sxs-lookup"><span data-stu-id="20e03-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="20e03-258">Suchen und Verweisen auf interne Links und Lesezeichen (Links zu bestimmten Abschnitten auf einer Seite).</span><span class="sxs-lookup"><span data-stu-id="20e03-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="20e03-259">Formatierungsfehler sind hervorgehoben (bewegen Sie den Mauszeiger über den Fehler, um mehr zu erfahren).</span><span class="sxs-lookup"><span data-stu-id="20e03-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="20e03-260">[Rechtschreibprüfung für Code:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Falsch geschriebene Wörter werden unterstrichen. Klicken Sie mit der rechten Maustaste auf ein falsch geschriebenes Wort, um es zu ändern oder im Wörterbuch zu speichern.</span><span class="sxs-lookup"><span data-stu-id="20e03-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
