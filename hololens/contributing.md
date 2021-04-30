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
# <a name="contributing-to-the-hololens-documentation"></a>Mitwirken an der HoloLens-Dokumentation

Willkommen bei der [HoloLens-Dokumentation!](https://github.com/MicrosoftDocs/Hololens) Alle Artikel, die Sie in diesem Repository erstellen oder **bearbeiten, sind für die Öffentlichkeit sichtbar.** 

HoloLens-Dokumente werden auf der docs.microsoft.com-Plattform angezeigt, die Markdown mit GitHub-Varianten mit Markdig-Features verwendet. Der Inhalt, den Sie in diesem Repository bearbeiten, wird in stilisierte Seiten formatiert, die unter angezeigt https://docs.microsoft.com/hololens werden. 

Auf dieser Seite werden die grundlegenden Schritte und Richtlinien für beiträge und Links zu Markdown-Grundlagen behandelt. Vielen Dank für Ihren Beitrag!

## <a name="available-repos"></a>Verfügbare Repositorys

| Name des Repositorys | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/Mixed Reality](https://docs.microsoft.com/windows/mixed-reality) |
| VR-Handbuch für Fans | [MicrosoftDocs/mixed-reality/fan-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Vorbereitung

Wenn Sie noch keins besitzen, müssen Sie [ein GitHub-Konto erstellen.](https://github.com/join)

>[!NOTE]
>Wenn Sie Microsoft-Mitarbeiter sind, verknüpfen Sie Ihr GitHub-Konto mit Ihrem Microsoft-Alias im [Microsoft Open Source-Portal.](https://repos.opensource.microsoft.com/) Treten Sie den Organisationen **"Microsoft"** und **"MicrosoftDocs"** bei.

Beim Einrichten Ihres GitHub-Kontos empfehlen wir auch die folgenden Sicherheitsvorkehrungen:
- Erstellen Sie ein [sicheres Kennwort für Ihr GitHub-Konto.](https://github.com/settings/admin)
- Aktivieren Sie [die zweistufige Authentifizierung.](https://github.com/settings/two_factor_authentication/configure)
- Speichern Sie [Ihre Wiederherstellungscodes](https://github.com/settings/auth/recovery-codes) an einem sicheren Ort.
- Aktualisieren Sie die [Einstellungen für Ihr öffentliches Profil.](https://github.com/settings/profile)
   - Legen Sie Ihren Namen fest, und legen Sie Ihre *öffentliche E-Mail-Adresse* *auf Don't show my email address (Meine E-Mail-Adresse nicht anzeigen) fest.*
   - Es wird empfohlen, ein Profilbild hochzuladen, da eine Miniaturansicht auf Dokumentationsseiten angezeigt wird, zu der Sie beitragen.
- Wenn Sie die Befehlszeile verwenden möchten, sollten Sie git Anmeldeinformationsverwaltung [für Windows einrichten.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Auf diese Weise müssen Sie ihr Kennwort nicht jedes Mal eingeben, wenn Sie einen Beitrag leisten.

Da das Veröffentlichungssystem an GitHub gebunden ist, sind diese Schritte wichtig. Sie werden entweder als Autor oder Mitwirkender für jeden Artikel aufgeführt, indem Sie Ihren GitHub-Alias verwenden.

## <a name="editing-an-existing-article"></a>Bearbeiten eines vorhandenen Artikels

Verwenden Sie den folgenden  Workflow, um über GitHub in einem Webbrowser Updates für einen vorhandenen Artikel zu erstellen:

1. Navigieren Sie zu dem Artikel, den Sie im Ordner "mixed-reality-docs" bearbeiten möchten.

2. Wählen Sie oben rechts die Bearbeitungsschaltfläche (Stiftsymbol) aus, die automatisch eine verwerfbar verzweigte Verzweigung aus der Verzweigung "master" verzweigt.

   ![Bearbeiten Sie einen Artikel.](images/editpage.png)
   
3. Bearbeiten Sie den Inhalt des Artikels gemäß den ["Markdowngrundkenntnissen".](#markdown-basics)

4. Aktualisieren Sie die Metadaten am Anfang jedes Artikels:

   * **title:** Seitentitel, der auf der Browserregisterkarte angezeigt wird, wenn der Artikel angezeigt wird. Seitentitel werden für SEO und Indizierung verwendet. Ändern Sie daher den Titel nur, wenn dies erforderlich ist (obwohl dies weniger wichtig ist, bevor die Dokumentation öffentlich wird).
   * **description:** Schreiben Sie eine kurze Beschreibung des Artikels, wodurch SEO und Ermittlung verstärkt werden.
   * **author:** Wenn Sie der Hauptbesitzer der Seite sind, fügen Sie hier Ihren GitHub-Alias hinzu.
   * **ms.author:** Wenn Sie der Hauptbesitzer der Seite sind, fügen Sie hier Ihren Microsoft-Alias hinzu (Sie benötigen @microsoft.com nicht , sondern nur den Alias).
   * **ms.date:** Aktualisieren Sie das Datum, wenn Sie der Seite Hauptinhalte hinzufügen, aber nicht für Korrekturen wie Erläuterungen, Formatierung, Grammatik oder Rechtschreibung.
   * **keywords:** Schlüsselwörter helfen bei SEO (Suchmaschinenoptimierung). Fügen Sie Schlüsselwörter hinzu, die durch ein Komma und ein Leerzeichen getrennt sind, die für Ihren Artikel spezifisch sind, aber keine Interpunktion nach dem letzten Schlüsselwort in Der Liste. Sie müssen keine globalen Schlüsselwörter hinzufügen, die für alle Artikel gelten, da diese an anderer Stelle verwaltet werden. 
   
5. Wenn Sie ihre Artikelbearbeitungen abgeschlossen haben, scrollen Sie nach unten, und wählen **Sie Dateiänderung vorschlagen** aus.

6. Wählen Sie auf der nächsten Seite **Pull Request erstellen** aus, um ihren automatisch erstellten Branch in "master" zusammenzuführen.

7. Wiederholen Sie die obigen Schritte für den nächsten Artikel, den Sie bearbeiten möchten.

## <a name="renaming-or-deleting-an-existing-article"></a>Umbenennen oder Löschen eines vorhandenen Artikels

Wenn Ihre Änderung einen vorhandenen Artikel umbenennen oder löschen wird, fügen Sie unbedingt eine Umleitung hinzu. Auf diese Weise wird jeder Benutzer mit einem Link zum vorhandenen Artikel immer noch am richtigen Ort sein. Umleitungen werden vom .openpublishing.redirection.jsin der Datei im Stammverzeichnis des Repositorys verwaltet.

Um eine Umleitung zu .openpublishing.redirection.jshinzuzufügen, fügen Sie dem Array einen Eintrag `redirections` hinzu:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`ist der relative Repositorypfad zum alten Artikel, den Sie entfernen. Stellen Sie sicher, dass der Pfad mit beginnt `mixed-reality-docs` und mit `.md` endet.

- ist `redirect_url` die relative öffentliche URL aus dem alten Artikel zum neuen Artikel. Stellen Sie sicher, dass diese URL **nicht** `mixed-reality-docs` oder `.md` enthält, da sie auf die öffentliche URL und nicht auf den Repositorypfad verweist. Das Verknüpfen mit einem Abschnitt innerhalb des neuen Artikels mit `#section` ist zulässig. Sie können hier bei Bedarf auch einen absoluten Pfad zu einer anderen Website verwenden.

- `redirect_document_id` gibt an, ob Sie die Dokument-ID aus der vorherigen Datei beibehalten möchten. Der Standardwert lautet `false`. Verwenden `true` Sie , wenn Sie den `ms.documentid` Attributwert aus dem umgeleiteten Artikel beibehalten möchten. Wenn Sie die Dokument-ID beibehalten, werden Daten wie Seitenaufrufe und Rangfolge an den Zielartikel übertragen. Tun Sie dies, wenn die Umleitung in erster Linie eine Umbenennung und kein Zeiger auf einen anderen Artikel ist, der nur einen Teil desselben Inhalts abdeckt.

Wenn Sie eine Umleitung hinzufügen, müssen Sie auch die alte Datei löschen.

## <a name="creating-a-new-article"></a>Erstellen eines neuen Artikels

Verwenden Sie den folgenden Workflow, *um neue Artikel im* Dokumentationsre repo über GitHub in einem Webbrowser zu erstellen:

1. Erstellen Sie einen Fork aus dem Branch "Master" von  MicrosoftDocs/Mixed Reality (mithilfe der Verzweigungsschaltfläche oben rechts).

   ![Forken Sie den Masterzweig.](images/forkbranch.png)
   
2. Wählen Sie oben rechts im Ordner "mixed-reality-docs" die Option Neue Datei erstellen aus. 

3. Erstellen Sie einen Seitennamen für den Artikel (verwenden Sie Bindestriche anstelle von Leerzeichen, und verwenden Sie keine Satzzeichen oder Apostrophe), und fügen Sie ".md" an.

   ![Nennen Sie die neue Seite.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Stellen Sie sicher, dass Sie den neuen Artikel im Ordner "mixed-reality-docs" erstellen. Sie können dies bestätigen, indem Sie in der neuen Dateinamenszeile nach "/mixed-reality-docs/" überprüfen.

4. Fügen Sie oben auf der neuen Seite den folgenden Metadatenblock hinzu:

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

5. Füllen Sie die relevanten Metadatenfelder entsprechend den Anweisungen im [Abschnitt oben aus.](#editing-an-existing-article)

6. Schreiben von Artikelinhalten [mithilfe der Markdown-Grundlagen.](#markdown-basics)

7. Fügen Sie am Ende des Artikels einen Abschnitt mit Links `## See also` zu anderen relevanten Artikeln hinzu.

8. Wählen Sie anschließend Commit **new file (Neue Datei commiten) aus.**

9. Wählen **Sie Neuer Pull Request** aus, und führen Sie den Branch "master" Ihres Forks in MicrosoftDocs/Mixed Reality "master" zusammen (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).

   ![Erstellen eines Pull Requests aus Ihrem Fork in MicrosoftDocs/Mixed Reality](images/pr-to-master.png)

## <a name="markdown-basics"></a>Grundlegendes zu Markdown

Die folgenden Ressourcen helfen Ihnen, zu erfahren, wie Sie die Dokumentation mithilfe der Markdownsprache bearbeiten:

- [Markdown-Grundlagen](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Zusätzliche Ressourcen zum Schreiben von Markdown für docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Hinzufügen von Tabellen

Aufgrund der Art und Weise, wie Tabellen docs.microsoft.com, verfügen sie nicht über Rahmen oder benutzerdefinierte Stile, auch wenn Sie INLINE-CSS ausprobieren. Es scheint für einen kurzen Zeitraum zu funktionieren, aber schließlich entfernt die Plattform den Stil aus der Tabelle. Planen Sie also voraus, und halten Sie Ihre Tabellen einfach. [Hier ist eine Website, die Markdowntabellen einfach macht.](https://www.tablesgenerator.com/markdown_tables)

Die [Docs Markdown-Erweiterung für Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) vereinfacht auch die Tabellengenerierung, wenn Sie Visual Studio Code verwenden [(siehe unten),](#using-visual-studio-code) um die Dokumentation zu bearbeiten.

### <a name="adding-images"></a>Hinzufügen von Bildern

Sie müssen Ihre Bilder in den Ordner "mixed-reality-docs/images" im Repository hochladen und dann im Artikel entsprechend darauf verweisen. Bilder werden automatisch in voller Größe angezeigt, was bedeutet, dass große Bilder die gesamte Breite des Artikels ausfüllen. Es wird empfohlen, die Größe Ihrer Bilder vorab zu dimensionieren, bevor Sie sie hochladen. Die empfohlene Breite liegt zwischen 600 und 700 Pixel. Sie sollten die Größe jedoch nach oben oder unten anpassen, wenn es sich um einen dichten Screenshot bzw. einen Bruchteil eines Screenshots handelt.

>[!IMPORTANT]
>Sie können Bilder nur vor dem Zusammenführen in Ihr gezweigtes Repository hochladen. Wenn Sie also einem Artikel Bilder hinzufügen möchten, müssen Sie [Visual Studio Code verwenden,](#using-visual-studio-code) um die Bilder zuerst dem Ordner "images" Ihrer Verzweigung hinzuzufügen, oder stellen Sie sicher, dass Sie folgende Schritte in einem Webbrowser ausgeführt haben:
>
>1. Forked the MicrosoftDocs/mixed-reality repo.
>2. Der Artikel in Ihrer Verzweigung wurde bearbeitet.
>3. Laden Sie die Bilder, auf die Sie in Ihrem Artikel verweisen, in den Ordner "mixed-reality-docs/images" in Ihrem Fork hoch.
>4. Es wurde ein **Pull Request** erstellt, um Ihre Verzweigung mit dem MicrosoftDocs/Mixed Reality-Branch "master" zusammenzuführen.
>
>Um zu erfahren, wie Sie Ihr eigenes gezweigtes Repository einrichten, befolgen Sie die Anweisungen zum [Erstellen eines neuen Artikels](#creating-a-new-article).

## <a name="previewing-your-work"></a>Anzeigen einer Vorschau Ihrer Arbeit

Beim Bearbeiten in GitHub über einen Webbrowser  können Sie oben auf der Seite die Registerkarte Vorschau auswählen, um eine Vorschau Ihrer Arbeit anzuzeigen, bevor Sie einen Commit committen. 

>[!NOTE]
>Die Vorschau Ihrer Änderungen auf review.docs.microsoft.com ist nur für Microsoft-Mitarbeiter verfügbar.

Microsoft-Mitarbeiter: Nachdem Ihre Beiträge mit dem Branch "master" zusammengeführt wurden, können Sie den Inhalt überprüfen, bevor er unter veröffentlicht https://review.docs.microsoft.com/hololens?branch=master wird. Suchen Sie Ihren Artikel mithilfe des Inhaltsverzeichnis in der linken Spalte.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Bearbeiten im Browser im Vergleich zur Bearbeitung mit einem Desktopclient

Die Bearbeitung im Browser ist die einfachste Möglichkeit, um schnelle Änderungen vorzunehmen. Es gibt jedoch einige Nachteile:

- Sie erhalten keine Rechtschreibprüfung.
- Sie erhalten keine intelligente Verknüpfung mit anderen Artikeln (Sie müssen den Dateinamen des Artikels manuell eingeben).
- Es kann mühsam sein, Bilder hochzuladen und darauf zu verweisen.

Wenn Sie diese Probleme nicht behandeln möchten, verwenden Sie einen Desktopclient [](#useful-extensions) wie [Visual Studio Code](https://code.visualstudio.com/) mit einigen hilfreichen Erweiterungen, wenn Sie mitwirken.

## <a name="using-visual-studio-code"></a>Verwendung von Visual Studio Code

Aus den oben [genannten Gründen](#editing-in-the-browser-vs-editing-with-a-desktop-client)können Sie die Verwendung eines Desktopclients zum Bearbeiten der Dokumentation anstelle eines Webbrowsers bevorzugen. Wir empfehlen die Verwendung von [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Setup

Führen Sie die folgenden Schritte aus, um Visual Studio Code für die Arbeit mit diesem Repository zu konfigurieren:

1. In einem Webbrowser:
    1. Installieren [Sie Git für Ihren PC.](https://git-scm.com/downloads)
    2. Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
    3. [Forken Sie MicrosoftDocs/mixed-reality,](#creating-a-new-article) sofern noch nicht vorhanden.
    4. Wählen Sie in Ihrem Fork **Klonen oder herunterladen aus,** und kopieren Sie die URL.
2. Erstellen Sie einen lokalen Klon Ihrer Vererbung in Visual Studio Code:
    1. Wählen Sie **im Menü** Ansicht die Option **Befehlspalette aus.**
    2. Geben Sie "Git: Clone" ein.
    3. Fügen Sie die kopierte URL ein.
    4. Wählen Sie aus, wo der Klon auf Ihrem PC gespeichert werden soll.
    5. Wählen Sie im Popupfenster **Repository öffnen** aus.

### <a name="editing-documentation"></a>Bearbeiten der Dokumentation

Verwenden Sie den folgenden Workflow, um änderungen an der Dokumentation mit Visual Studio Code vorzunehmen:

>[!NOTE]
>Alle Anleitungen zum [Bearbeiten](#editing-an-existing-article) und [Erstellen von](#creating-a-new-article) Artikeln sowie die Grundlagen der Bearbeitung [von Markdown](#markdown-basics)von oben gelten auch bei Verwendung von Visual Studio Code.

1. Stellen Sie sicher, dass Ihr geklonter Fork mit dem offiziellen Repository auf dem neuesten Stand ist.

   1. Erstellen Sie in einem Webbrowser einen Pull Request, um aktuelle Änderungen anderer Mitwirkender in MicrosoftDocs/mixed-reality "master" mit Ihrer Verzweigung zu synchronisieren (stellen Sie sicher, dass der Pfeil den richtigen Weg zeigt).
      
      ![Synchronisieren von Änderungen von MicrosoftDocs/Mixed Reality mit Ihrer Verzweigung](images/sync-repos.png)
      
   2. Wählen Sie in Visual Studio Code die Schaltfläche sync aus, um Ihre neu aktualisierte Verzweigung mit dem lokalen Klon zu synchronisieren.
      
      ![Klicken Sie auf das Bild der Synchronisierungsschaltfläche.](images/sync-clone.png)
      
2. Erstellen oder bearbeiten Sie Artikel in Ihrem geklonten Repository mithilfe Visual Studio Code.

   1. Bearbeiten Sie einen oder mehrere Artikel (fügen Sie bei Bedarf Bilder zum Ordner "images" hinzu).
   
   2. **Speichern Sie** die Änderungen im **Explorer.**
      
      ![Auswählen von "Alle speichern" im Explorer](images/explorer-save.png)
      
   3. **Committen Sie alle** Änderungen in der **Quellcodeverwaltung** (schreiben Sie eine Commitnachricht, wenn Sie dazu aufgefordert werden).
   
      ![Auswählen von "Commit all" in der Quellcodeverwaltung](images/source-control-commit.png)
      
   4. Wählen Sie die Schaltfläche **"Synchronisieren"** aus, um Ihre Änderungen wieder mit dem Ursprung zu synchronisieren (Ihre Verzweigung auf GitHub).
      
      ![Klicken Sie auf die Schaltfläche "Synchronisieren".](images/sync-back.png)
      
3. Erstellen Sie in einem Webbrowser einen Pull Request, um neue Änderungen in Ihrer Verzweigung mit MicrosoftDocs/mixed-reality "master" zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).

   ![Erstellen eines Pull Requests aus Ihrer Verzweigung in MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

### <a name="useful-extensions"></a>Nützliche Erweiterungen

Die folgenden Visual Studio Code-Erweiterungen sind beim Bearbeiten der Dokumentation nützlich:

- [Docs Markdown-Erweiterung für Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) Verwenden Sie **ALT+M,** um ein Menü mit Dokumenterstellungsoptionen wie den folgenden zu öffnen:
   - Suchen Sie bilder, und verweisen Sie auf Bilder, die Sie hochgeladen haben.
   - Fügen Sie Formatierungen wie Listen, Tabellen und dokumentspezifische Aufrufe wie `>[!NOTE]` hinzu.
   - Suchen und Verweisen auf interne Links und Lesezeichen (Links zu bestimmten Abschnitten auf einer Seite).
   - Formatierungsfehler sind hervorgehoben (bewegen Sie den Mauszeiger über den Fehler, um mehr zu erfahren).
- [Rechtschreibprüfung für Code:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Falsch geschriebene Wörter werden unterstrichen. Klicken Sie mit der rechten Maustaste auf ein falsch geschriebenes Wort, um es zu ändern oder im Wörterbuch zu speichern.
