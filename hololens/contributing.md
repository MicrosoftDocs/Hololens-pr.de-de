---
title: Beizutragende Anweisungen
description: Hier erfahren Sie, wie Sie mithilfe von GitHub-aromatisiertem Abschlag zu den HoloLens-Dokumenten auf der docs.Microsoft.com-Plattform beitragen.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 311da6bc52098d5ba16e4684f68fec9a01e7c23b
ms.sourcegitcommit: 8cea4c04c6d2e22225f4de43e10c05dab840736a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253833"
---
# <span data-ttu-id="5a9d6-103">Beitrag zur HoloLens-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="5a9d6-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="5a9d6-104">Willkommen in der [HoloLens-Dokumentation](https://github.com/MicrosoftDocs/Hololens)!</span><span class="sxs-lookup"><span data-stu-id="5a9d6-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="5a9d6-105">Alle Artikel, die Sie in diesem Repo erstellen oder bearbeiten **, sind für die Öffentlichkeit sichtbar.**</span><span class="sxs-lookup"><span data-stu-id="5a9d6-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="5a9d6-106">HoloLens-Dokumente werden auf der docs.Microsoft.com-Plattform angezeigt, die mit GitHub-aromatisiertem Abschlägen mit Markdig-Features ausgestattet ist.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="5a9d6-107">Der Inhalt, den Sie in diesem Repo bearbeiten, wird in stilisierte Seiten formatiert, die sich bei befinden https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="5a9d6-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="5a9d6-108">Auf dieser Seite werden die grundlegenden Schritte und Richtlinien für den Beitrag und Links zu den Grundlagen von Abschriften behandelt.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="5a9d6-109">Vielen Dank für Ihren Beitrag!</span><span class="sxs-lookup"><span data-stu-id="5a9d6-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="5a9d6-110">Verfügbare Repos</span><span class="sxs-lookup"><span data-stu-id="5a9d6-110">Available repos</span></span>

| <span data-ttu-id="5a9d6-111">Repository-Name</span><span class="sxs-lookup"><span data-stu-id="5a9d6-111">Repository name</span></span> | <span data-ttu-id="5a9d6-112">URL</span><span class="sxs-lookup"><span data-stu-id="5a9d6-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="5a9d6-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="5a9d6-113">HoloLens</span></span> | [<span data-ttu-id="5a9d6-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="5a9d6-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="5a9d6-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="5a9d6-115">Mixed Reality</span></span> | [<span data-ttu-id="5a9d6-116">MicrosoftDocs/Mixed-Reality</span><span class="sxs-lookup"><span data-stu-id="5a9d6-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="5a9d6-117">Leitfaden für VR-Enthusiasten</span><span class="sxs-lookup"><span data-stu-id="5a9d6-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="5a9d6-118">MicrosoftDocs/Mixed-Reality/Enthusiast-Leitfaden</span><span class="sxs-lookup"><span data-stu-id="5a9d6-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="5a9d6-119">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="5a9d6-119">Before you start</span></span>

<span data-ttu-id="5a9d6-120">Wenn Sie noch keinen haben, müssen Sie [ein GitHub-Konto erstellen](https://github.com/join).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="5a9d6-121">Wenn Sie ein Microsoft-Mitarbeiter sind, verknüpfen Sie Ihr GitHub-Konto mit Ihrem Microsoft-Alias auf dem [Microsoft Open-Source-Portal](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="5a9d6-122">Nehmen Sie an den Organisationen **"Microsoft"** und " **MicrosoftDocs"** Teil.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="5a9d6-123">Bei der Einrichtung Ihres GitHub-Kontos empfehlen wir auch diese Sicherheitsvorkehrungen:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="5a9d6-124">Erstellen [Sie ein sicheres Kennwort für Ihr GitHub-Konto](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="5a9d6-125">Aktivieren Sie die zweistufige [Authentifizierung](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="5a9d6-126">Speichern Sie Ihre [Wiederherstellungscodes](https://github.com/settings/auth/recovery-codes) an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="5a9d6-127">Aktualisieren Sie Ihre [Einstellungen für Öffentliches Profil](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="5a9d6-128">Geben Sie Ihren Namen ein, und setzen Sie Ihre *öffentliche e-Mail* so ein, dass *meine e-Mail-Adresse nicht angezeigt*wird.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="5a9d6-129">Wir empfehlen, dass Sie ein Profilbild hochladen, da eine Miniaturansicht auf den Dokumentenseiten angezeigt wird, zu denen Sie beitragen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="5a9d6-130">Wenn Sie beabsichtigen, die Befehlszeile zu verwenden, sollten Sie den [git Credential Manager für Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)einrichten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="5a9d6-131">Auf diese Weise müssen Sie nicht jedes Mal, wenn Sie einen Beitrag leisten, Ihr Kennwort eingeben.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="5a9d6-132">Da das Veröffentlichungssystem mit GitHub verbunden ist, sind diese Schritte wichtig.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="5a9d6-133">Sie werden als Autor oder Mitwirkender für jeden Artikel mit Ihrem GitHub-Alias aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="5a9d6-134">Bearbeiten eines vorhandenen Artikels</span><span class="sxs-lookup"><span data-stu-id="5a9d6-134">Editing an existing article</span></span>

<span data-ttu-id="5a9d6-135">Verwenden Sie den folgenden Workflow, um in einem Webbrowser Updates zu *einem vorhandenen Artikel* über GitHub zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="5a9d6-136">Navigieren Sie im Ordner "Mixed-Reality-docs" zu dem Artikel, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="5a9d6-137">Klicken Sie oben rechts auf die Schaltfläche "Bearbeiten" (Stiftsymbol), die automatisch eine Wegwerf Verzweigung vom "Master"-Zweig abzweigt.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Bearbeiten eines Artikels](images/editpage.png)
   
3. <span data-ttu-id="5a9d6-139">Bearbeiten Sie den Inhalt des Artikels gemäß den ["Grundlagen](#markdown-basics)der Abschriften".</span><span class="sxs-lookup"><span data-stu-id="5a9d6-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="5a9d6-140">Aktualisieren Sie die Metadaten oben in jedem Artikel:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="5a9d6-141">**Titel**: Seitentitel, der beim Anzeigen des Artikels auf der Registerkarte "Browser" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="5a9d6-142">Seitentitel werden für SEO und Indizierung verwendet, daher sollten Sie den Titel nur dann ändern, wenn dies erforderlich ist (Dies ist jedoch vor der öffentlichen Dokumentation eher unkritisch).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="5a9d6-143">**Beschreibung**: Schreiben Sie eine kurze Beschreibung des Inhalts des Artikels, die SEO und Discovery steigert.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="5a9d6-144">**Autor**: Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren GitHub-Alias hinzu.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="5a9d6-145">**ms. Author**: Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren Microsoft-Alias hinzu (Sie brauchen @Microsoft. com nicht, sondern nur den Alias).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="5a9d6-146">**ms. Date**: Aktualisieren Sie das Datum, wenn Sie der Seite Hauptinhalte hinzufügen, jedoch keine Korrekturen wie Klarstellung, Formatierung, Grammatik oder Rechtschreibung.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="5a9d6-147">**Schlüsselwörter**: Hilfe für Keywords in SEO (Suchmaschinenoptimierung).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="5a9d6-148">Fügen Sie Stichwörter hinzu, die durch ein Komma und ein Leerzeichengetrennt sind, die für Ihren Artikel spezifisch sind, aber keine Interpunktion nach dem letzten Schlüsselwort in der Liste.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="5a9d6-149">Sie müssen keine globalen Stichwörter hinzufügen, die für alle Artikel gelten, da diese an anderer Stelle verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="5a9d6-150">Wenn Sie Ihre Artikelbearbeitungen abgeschlossen haben, Scrollen Sie nach unten, und wählen Sie **Dateiänderung vorschlagen**aus.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="5a9d6-151">Wählen Sie auf der nächsten Seite **Pull Request erstellen** aus, um die automatisch erstellte Verzweigung in "Master" zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="5a9d6-152">Wiederholen Sie die obigen Schritte für den nächsten Artikel, den Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="5a9d6-153">Umbenennen oder Löschen eines vorhandenen Artikels</span><span class="sxs-lookup"><span data-stu-id="5a9d6-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="5a9d6-154">Wenn Ihre Änderung einen vorhandenen Artikel umbenennen oder löschen soll, stellen Sie sicher, dass Sie eine Umleitung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="5a9d6-155">Auf diese Weise wird jeder, der über einen Link zu dem vorhandenen Artikel verfügt, weiterhin an der richtigen Stelle platziert.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="5a9d6-156">Umleitungen werden von der .openpublishing.redirection.jsDatei im Stammverzeichnis des Repo verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="5a9d6-157">Wenn Sie eine Umleitung zu .openpublishing.redirection.jshinzufügen möchten, fügen Sie dem Array einen Eintrag hinzu `redirections` :</span><span class="sxs-lookup"><span data-stu-id="5a9d6-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="5a9d6-158">Hierbei `source_path` handelt es sich um den relativen Repository-Pfad zu dem alten Artikel, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="5a9d6-159">Achten Sie darauf, dass der Pfad mit beginnt `mixed-reality-docs` und endet `.md` .</span><span class="sxs-lookup"><span data-stu-id="5a9d6-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="5a9d6-160">Das `redirect_url` ist die relative öffentliche URL aus dem alten Artikel zum neuen Artikel.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="5a9d6-161">Stellen Sie sicher, dass diese **URL weder die** `mixed-reality-docs` `.md` öffentliche URL noch den Repository-Pfad enthält.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="5a9d6-162">Das Verknüpfen mit einem Abschnitt innerhalb des neuen Artikels `#section` ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="5a9d6-163">Sie können bei Bedarf auch hier einen absoluten Pfad zu einer anderen Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="5a9d6-164">Gibt an, ob Sie die Dokument-ID aus der vorherigen Datei beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="5a9d6-165">Der Standardwert ist `false` .</span><span class="sxs-lookup"><span data-stu-id="5a9d6-165">The default is `false`.</span></span> <span data-ttu-id="5a9d6-166">Verwenden `true` Sie diese Eigenschaft, wenn Sie den `ms.documentid` Attributwert aus dem umgeleiteten Artikel beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="5a9d6-167">Wenn Sie die Dokument-ID beibehalten, werden Daten wie Seitenaufrufe und Rankings an den Ziel Artikel übertragen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="5a9d6-168">Führen Sie diese Schritte aus, wenn die Umleitung in erster Linie ein umbenennen ist und kein Zeiger auf einen anderen Artikel, der nur einen Teil desselben Inhalts abdeckt.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="5a9d6-169">Wenn Sie eine Umleitung hinzufügen, müssen Sie auch die alte Datei löschen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="5a9d6-170">Erstellen eines neuen Artikels</span><span class="sxs-lookup"><span data-stu-id="5a9d6-170">Creating a new article</span></span>

<span data-ttu-id="5a9d6-171">Verwenden Sie den folgenden Workflow zum *Erstellen neuer Artikel* im Dokumentations-Repo über GitHub in einem Webbrowser:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="5a9d6-172">Erstellen Sie eine Abzweigung außerhalb des MicrosoftDocs/Mixed-Reality-"Master"-Zweigs (mithilfe der Schaltfläche " **Gabel** " oben rechts).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Gabeln Sie die Master Verzweigung.](images/forkbranch.png)
   
2. <span data-ttu-id="5a9d6-174">Wählen Sie im Ordner "Mixed-Reality-docs" oben rechts die Option **neue Datei erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="5a9d6-175">Erstellen Sie einen Seitennamen für den Artikel (verwenden Sie Bindestriche anstelle von Leerzeichen und verwenden Sie keine Interpunktions-oder Apostrophe), und fügen Sie ". MD" an.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Benennen Sie die neue Seite.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="5a9d6-177">Stellen Sie sicher, dass Sie den neuen Artikel im Ordner "Mixed-Reality-docs" erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="5a9d6-178">Sie können dies bestätigen, indem Sie in der neuen Zeile für Dateinamen auf "/Mixed-Reality-docs/" überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="5a9d6-179">Fügen Sie oben auf der neuen Seite den folgenden Metadaten-Block hinzu:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="5a9d6-180">Füllen Sie die relevanten Metadatenfelder gemäß den Anweisungen im [obigen Abschnitt](#editing-an-existing-article)aus.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="5a9d6-181">Schreiben Sie Artikel Inhalte mithilfe von [Grundlagen](#markdown-basics)zum Abgleichen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="5a9d6-182">Fügen Sie `## See also` am Ende des Artikels einen Abschnitt mit Links zu anderen relevanten Artikeln hinzu.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="5a9d6-183">Wenn Sie den Vorgang beenden, wählen Sie **neue Datei bestätigen**aus.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="5a9d6-184">Wählen Sie **neue Pull-Anforderung** aus, und führen Sie den "Master"-Zweig Ihrer Gabel in MicrosoftDocs/Mixed-Reality-Master ein (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Erstellen einer Pull-Anfrage von ihrer Gabelung in MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

## <span data-ttu-id="5a9d6-186">Grundlagen zu Abschriften</span><span class="sxs-lookup"><span data-stu-id="5a9d6-186">Markdown basics</span></span>

<span data-ttu-id="5a9d6-187">Mit den folgenden Ressourcen erfahren Sie, wie Sie die Dokumentation unter Verwendung der Abzugs Sprache bearbeiten können:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="5a9d6-188">Grundlagen zu Abschriften</span><span class="sxs-lookup"><span data-stu-id="5a9d6-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="5a9d6-189">Zusätzliche Ressourcen zum Schreiben von Abschlägen für docs.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5a9d6-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="5a9d6-190">Hinzufügen von Tabellen</span><span class="sxs-lookup"><span data-stu-id="5a9d6-190">Adding tables</span></span>

<span data-ttu-id="5a9d6-191">Aufgrund der Art und Weise, wie docs.Microsoft.com-Formatvorlagen Tabellen angezeigt werden, verfügen Sie nicht über Rahmen oder benutzerdefinierte Formatvorlagen, auch wenn Sie Inline-CSS versuchen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="5a9d6-192">Es scheint für einen kurzen Zeitraum zu funktionieren, doch schließlich wird die Plattform die Formatierung aus der Tabelle entfernen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="5a9d6-193">Planen Sie also weiter und halten Sie Ihre Tabellen einfach.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="5a9d6-194">[Hier finden Sie eine Website, die das](https://www.tablesgenerator.com/markdown_tables)Abspielen von Tabellen vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="5a9d6-195">Die doc-Abzugs [Erweiterung für Visual Studio-Code](https://docs.microsoft.com/teamblog/docs-extension) macht auch die Tabellengenerierung einfach, wenn Sie [Visual Studio-Code verwenden (siehe unten)](#using-visual-studio-code) , um die Dokumentation zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="5a9d6-196">Hinzufügen von Bildern</span><span class="sxs-lookup"><span data-stu-id="5a9d6-196">Adding images</span></span>

<span data-ttu-id="5a9d6-197">Sie müssen Ihre Bilder in den Ordner "Mixed-Reality-docs/Images" im Repo hochladen und im Artikel entsprechend verweisen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="5a9d6-198">Bilder werden automatisch in voller Größe angezeigt, was bedeutet, dass große Bilder die gesamte Breite des Artikels ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="5a9d6-199">Wir empfehlen, Ihre Bilder vor dem Hochladen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="5a9d6-200">Die empfohlene Breite liegt zwischen 600 und 700 Pixeln, wenn Sie die Größe nach oben oder unten ändern sollten, wenn es sich um einen dichten Screenshot oder einen Bruchteil eines Screenshots handelt.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="5a9d6-201">Sie können vor dem Zusammenführen nur Bilder in Ihr gegabelte Repo hochladen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="5a9d6-202">Wenn Sie also Bilder zu einem Artikel hinzufügen möchten, müssen Sie [Visual Studio-Code verwenden](#using-visual-studio-code) , um die Bilder zunächst dem Ordner "Images" ihrer Verzweigung hinzuzufügen, oder stellen Sie sicher, dass Sie die folgenden Schritte in einem Webbrowser ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="5a9d6-203">Hat das MicrosoftDocs/Mixed-Reality-Repo abgespalten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="5a9d6-204">Artikel in ihrer Verzweigung bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="5a9d6-205">Sie haben die Bilder, auf die Sie in Ihrem Artikel verweisen, in den Ordner "Mixed-Reality-docs/Images" in ihrer Verzweigung hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="5a9d6-206">Hat eine **Pull-Anforderung** erstellt, um Ihre Gabel in den MicrosoftDocs/Mixed-Reality-"Master"-Zweig zu verschmelzen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="5a9d6-207">Wenn Sie wissen möchten, wie Sie ein eigenes gegabelte Repo einrichten, folgen Sie den Anweisungen zum [Erstellen eines neuen Artikels](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="5a9d6-208">Anzeigen einer Vorschau Ihrer Arbeit</span><span class="sxs-lookup"><span data-stu-id="5a9d6-208">Previewing your work</span></span>

<span data-ttu-id="5a9d6-209">Wenn Sie in GitHub über einen Webbrowser bearbeiten, können Sie die Registerkarte **Vorschau** oben auf der Seite auswählen, um eine Vorschau Ihrer Arbeit anzuzeigen, bevor Sie einen Commit durchführen.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="5a9d6-210">Die Vorschau Ihrer Änderungen auf review.docs.Microsoft.com steht nur Microsoft-Mitarbeitern zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="5a9d6-211">Microsoft-Mitarbeiter: Nachdem Ihre Beiträge in den "Master"-Zweig verschmolzen sind, können Sie den Inhalt überprüfen, bevor er an die Öffentlichkeit geht https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="5a9d6-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="5a9d6-212">Suchen Sie Ihren Artikel mithilfe des Inhaltsverzeichnisses in der linken Spalte.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="5a9d6-213">Bearbeiten im Browser vs. Bearbeiten mit einem Desktop Client</span><span class="sxs-lookup"><span data-stu-id="5a9d6-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="5a9d6-214">Die Bearbeitung im Browser ist die einfachste Möglichkeit, schnelle Änderungen vorzunehmen, es gibt jedoch einige Nachteile:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="5a9d6-215">Sie erhalten keine Rechtschreibprüfung.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-215">You don't get spell-check.</span></span>
- <span data-ttu-id="5a9d6-216">Sie erhalten keine Smart-Links zu anderen Artikeln (Sie müssen den Dateinamen des Artikels manuell eingeben).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="5a9d6-217">Es kann mühsam sein, Bilder hochzuladen und zu referenzieren.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="5a9d6-218">Wenn Sie sich nicht mit diesen Problemen befassen möchten, verwenden Sie einen Desktop Client wie [Visual Studio-Code](https://code.visualstudio.com/) mit einigen [hilfreichen Erweiterungen](#useful-extensions) , wenn Sie einen Beitrag leisten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="5a9d6-219">Verwenden von Visual Studio-Code</span><span class="sxs-lookup"><span data-stu-id="5a9d6-219">Using Visual Studio Code</span></span>

<span data-ttu-id="5a9d6-220">Aus den [oben](#editing-in-the-browser-vs-editing-with-a-desktop-client)aufgelisteten Gründen empfiehlt es sich, einen Desktop-Client zu verwenden, um die Dokumentation anstelle eines Webbrowsers zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="5a9d6-221">Wir empfehlen die Verwendung von [Visual Studio-Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="5a9d6-222">Setup</span><span class="sxs-lookup"><span data-stu-id="5a9d6-222">Setup</span></span>

<span data-ttu-id="5a9d6-223">Führen Sie die folgenden Schritte aus, um Visual Studio-Code für die Arbeit mit diesem Repo zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="5a9d6-224">In einem Webbrowser:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-224">In a web browser:</span></span>
    1. <span data-ttu-id="5a9d6-225">Installieren [Sie git für Ihren PC](https://git-scm.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="5a9d6-226">Installieren Sie [Visual Studio-Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="5a9d6-227">[Gabel MicrosoftDocs/Mixed-Reality](#creating-a-new-article) , wenn Sie dies noch nicht getan haben.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="5a9d6-228">Wählen Sie in ihrer Verzweigung **Klonen aus, oder laden** Sie die URL herunter, und kopieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="5a9d6-229">Erstellen Sie einen lokalen Klon Ihrer Verzweigung in Visual Studio-Code:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="5a9d6-230">Wählen Sie im Menü **Ansicht** die Option **Befehls Palette**aus.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="5a9d6-231">Geben Sie "git: Clone" ein.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="5a9d6-232">Fügen Sie die kopierte URL ein.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="5a9d6-233">Wählen Sie aus, wo der Klon auf Ihrem PC gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="5a9d6-234">Wählen Sie im Popupfenster **Open Repo** aus.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="5a9d6-235">Bearbeiten von Dokumentation</span><span class="sxs-lookup"><span data-stu-id="5a9d6-235">Editing documentation</span></span>

<span data-ttu-id="5a9d6-236">Verwenden Sie den folgenden Workflow, um Änderungen an der Dokumentation mit Visual Studio-Code vorzunehmen:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="5a9d6-237">Alle Anleitungen für das [Bearbeiten](#editing-an-existing-article) und [Erstellen](#creating-a-new-article) von Artikeln und die [Grundlagen der Bearbeitung](#markdown-basics)von Abschlägen von oben gelten auch für die Verwendung von Visual Studio-Code.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="5a9d6-238">Stellen Sie sicher, dass Ihre geklonte Gabel mit dem offiziellen Repo auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="5a9d6-239">Erstellen Sie in einem Webbrowser eine Pull-Anforderung, um kürzlich vorgenommene Änderungen von anderen Mitwirkenden in MicrosoftDocs/Mixed-Reality-"Master" an Ihre Gabel zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchronisieren von Änderungen von MicrosoftDocs/Mixed-Reality auf Ihre Gabel](images/sync-repos.png)
      
   2. <span data-ttu-id="5a9d6-241">Wählen Sie in Visual Studio-Code die Schaltfläche synchronisieren aus, um den frisch aktualisierten Fork mit dem lokalen Klon zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Klicken Sie auf die Schaltfläche "synchronisieren".](images/sync-clone.png)
      
2. <span data-ttu-id="5a9d6-243">Erstellen oder bearbeiten Sie Artikel in Ihrem geklonten Repo mithilfe von Visual Studio-Code.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="5a9d6-244">Bearbeiten Sie einen oder mehrere Artikel (bei Bedarf Bilder in den Ordner "Bilder" hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="5a9d6-245">**Speichern** Sie die Änderungen im **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-245">**Save** changes in **Explorer**.</span></span>
      
      ![Wählen Sie im Explorer "Alle speichern" aus.](images/explorer-save.png)
      
   3. <span data-ttu-id="5a9d6-247">Übernehmen Sie **alle** Änderungen in der **Quellcodeverwaltung** (Commit-Nachricht schreiben, wenn Sie dazu aufgefordert werden).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
      
   4. <span data-ttu-id="5a9d6-248">Wählen Sie die Schaltfläche " **Synchronisieren** " aus, um Ihre Änderungen wieder in Origin zu synchronisieren (ihre Abzweigung auf GitHub).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-248">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Klicken Sie auf die Schaltfläche synchronisieren.](images/sync-back.png)
      
3. <span data-ttu-id="5a9d6-250">Erstellen Sie in einem Webbrowser eine Pull-Anforderung, um neue Änderungen in Ihrer Gabel wieder in MicrosoftDocs/Mixed-Reality-Master zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-250">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Erstellen einer Pull-Anfrage von ihrer Gabelung in MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

### <span data-ttu-id="5a9d6-252">Nützliche Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="5a9d6-252">Useful extensions</span></span>

<span data-ttu-id="5a9d6-253">Die folgenden Visual Studio-Code Erweiterungen sind beim Bearbeiten von Dokumentation hilfreich:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-253">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="5a9d6-254">Docs-Abzugs [Erweiterung für Visual Studio-Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – verwenden Sie **ALT + M** , um ein Menü mit Dokument Erstellungsoptionen wie folgenden zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="5a9d6-254">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="5a9d6-255">Suchen und referenzieren von Bildern, die Sie hochgeladen haben</span><span class="sxs-lookup"><span data-stu-id="5a9d6-255">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="5a9d6-256">Fügen Sie Formatierungen wie Listen, Tabellen und docs-spezifische Aufrufe wie `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="5a9d6-256">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="5a9d6-257">Suchen und verweisen auf interne Links und Lesezeichen (Links zu bestimmten Abschnitten innerhalb einer Seite).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-257">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="5a9d6-258">Formatierungsfehler sind hervorgehoben (zeigen Sie mit der Maus auf den Fehler, um weitere Informationen zu erhalten).</span><span class="sxs-lookup"><span data-stu-id="5a9d6-258">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="5a9d6-259">[Code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -Rechtschreibprüfung – falsch geschriebene Wörter werden unterstrichen; Klicken Sie mit der rechten Maustaste auf ein falsch geschriebenes Wort, um es zu ändern oder im Wörterbuch zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5a9d6-259">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
