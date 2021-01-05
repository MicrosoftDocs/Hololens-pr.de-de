---
title: Beizutragende Anweisungen
description: Hier erfahren Sie, wie Sie mithilfe von GitHub-aromatisiertem Abschlag zu den HoloLens-Dokumenten auf der docs.Microsoft.com-Plattform beitragen.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.openlocfilehash: d17d9e30ca3699a7bd6c69b75043c6974a2bde1f
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253645"
---
# Beitrag zur HoloLens-Dokumentation

Willkommen in der [HoloLens-Dokumentation](https://github.com/MicrosoftDocs/Hololens)! Alle Artikel, die Sie in diesem Repo erstellen oder bearbeiten **, sind für die Öffentlichkeit sichtbar.** 

HoloLens-Dokumente werden auf der docs.Microsoft.com-Plattform angezeigt, die mit GitHub-aromatisiertem Abschlägen mit Markdig-Features ausgestattet ist. Der Inhalt, den Sie in diesem Repo bearbeiten, wird in stilisierte Seiten formatiert, die sich bei befinden https://docs.microsoft.com/hololens . 

Auf dieser Seite werden die grundlegenden Schritte und Richtlinien für den Beitrag und Links zu den Grundlagen von Abschriften behandelt. Vielen Dank für Ihren Beitrag!

## Verfügbare Repos

| Repository-Name | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/Mixed-Reality](https://docs.microsoft.com/windows/mixed-reality) |
| Leitfaden für VR-Enthusiasten | [MicrosoftDocs/Mixed-Reality/Enthusiast-Leitfaden](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Vorbereitung

Wenn Sie noch keinen haben, müssen Sie [ein GitHub-Konto erstellen](https://github.com/join).

>[!NOTE]
>Wenn Sie ein Microsoft-Mitarbeiter sind, verknüpfen Sie Ihr GitHub-Konto mit Ihrem Microsoft-Alias auf dem [Microsoft Open-Source-Portal](https://repos.opensource.microsoft.com/). Nehmen Sie an den Organisationen **"Microsoft"** und " **MicrosoftDocs"** Teil.

Bei der Einrichtung Ihres GitHub-Kontos empfehlen wir auch diese Sicherheitsvorkehrungen:
- Erstellen [Sie ein sicheres Kennwort für Ihr GitHub-Konto](https://github.com/settings/admin).
- Aktivieren Sie die zweistufige [Authentifizierung](https://github.com/settings/two_factor_authentication/configure).
- Speichern Sie Ihre [Wiederherstellungscodes](https://github.com/settings/auth/recovery-codes) an einem sicheren Ort.
- Aktualisieren Sie Ihre [Einstellungen für Öffentliches Profil](https://github.com/settings/profile).
   - Geben Sie Ihren Namen ein, und setzen Sie Ihre *öffentliche e-Mail* so ein, dass *meine e-Mail-Adresse nicht angezeigt*wird.
   - Wir empfehlen, dass Sie ein Profilbild hochladen, da eine Miniaturansicht auf den Dokumentenseiten angezeigt wird, zu denen Sie beitragen.
- Wenn Sie beabsichtigen, die Befehlszeile zu verwenden, sollten Sie den [git Credential Manager für Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)einrichten. Auf diese Weise müssen Sie nicht jedes Mal, wenn Sie einen Beitrag leisten, Ihr Kennwort eingeben.

Da das Veröffentlichungssystem mit GitHub verbunden ist, sind diese Schritte wichtig. Sie werden als Autor oder Mitwirkender für jeden Artikel mit Ihrem GitHub-Alias aufgeführt.

## Bearbeiten eines vorhandenen Artikels

Verwenden Sie den folgenden Workflow, um in einem Webbrowser Updates zu *einem vorhandenen Artikel* über GitHub zu erstellen:

1. Navigieren Sie im Ordner "Mixed-Reality-docs" zu dem Artikel, den Sie bearbeiten möchten.
2. Klicken Sie oben rechts auf die Schaltfläche "Bearbeiten" (Stiftsymbol), die automatisch eine Wegwerf Verzweigung vom "Master"-Zweig abzweigt.

   ![Bearbeiten eines Artikels](images/editpage.png)
3. Bearbeiten Sie den Inhalt des Artikels gemäß den ["Grundlagen](#markdown-basics)der Abschriften".
4. Aktualisieren Sie die Metadaten oben in jedem Artikel:
   * **Titel**: Seitentitel, der beim Anzeigen des Artikels auf der Registerkarte "Browser" angezeigt wird. Seitentitel werden für SEO und Indizierung verwendet, daher sollten Sie den Titel nur dann ändern, wenn dies erforderlich ist (Dies ist jedoch vor der öffentlichen Dokumentation eher unkritisch).
   * **Beschreibung**: Schreiben Sie eine kurze Beschreibung des Inhalts des Artikels, die SEO und Discovery steigert.
   * **Autor**: Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren GitHub-Alias hinzu.
   * **ms. Author**: Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren Microsoft-Alias hinzu (Sie brauchen @Microsoft. com nicht, sondern nur den Alias).
   * **ms. Date**: Aktualisieren Sie das Datum, wenn Sie der Seite Hauptinhalte hinzufügen, jedoch keine Korrekturen wie Klarstellung, Formatierung, Grammatik oder Rechtschreibung.
   * **Schlüsselwörter**: Hilfe für Keywords in SEO (Suchmaschinenoptimierung). Fügen Sie Stichwörter hinzu, die durch ein Komma und ein Leerzeichengetrennt sind, die für Ihren Artikel spezifisch sind, aber keine Interpunktion nach dem letzten Schlüsselwort in der Liste. Sie müssen keine globalen Stichwörter hinzufügen, die für alle Artikel gelten, da diese an anderer Stelle verwaltet werden. 
5. Wenn Sie Ihre Artikelbearbeitungen abgeschlossen haben, Scrollen Sie nach unten, und wählen Sie **Dateiänderung vorschlagen**aus.
6. Wählen Sie auf der nächsten Seite **Pull Request erstellen** aus, um die automatisch erstellte Verzweigung in "Master" zusammenzuführen.
7. Wiederholen Sie die obigen Schritte für den nächsten Artikel, den Sie bearbeiten möchten.

## Umbenennen oder Löschen eines vorhandenen Artikels

Wenn Ihre Änderung einen vorhandenen Artikel umbenennen oder löschen soll, stellen Sie sicher, dass Sie eine Umleitung hinzufügen. Auf diese Weise wird jeder, der über einen Link zu dem vorhandenen Artikel verfügt, weiterhin an der richtigen Stelle platziert. Umleitungen werden von der .openpublishing.redirection.jsDatei im Stammverzeichnis des Repo verwaltet.

Wenn Sie eine Umleitung zu .openpublishing.redirection.jshinzufügen möchten, fügen Sie dem Array einen Eintrag hinzu `redirections` :

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- Hierbei `source_path` handelt es sich um den relativen Repository-Pfad zu dem alten Artikel, der entfernt werden soll. Achten Sie darauf, dass der Pfad mit beginnt `mixed-reality-docs` und endet `.md` .
- Das `redirect_url` ist die relative öffentliche URL aus dem alten Artikel zum neuen Artikel. Stellen Sie sicher, dass diese **URL weder die** `mixed-reality-docs` `.md` öffentliche URL noch den Repository-Pfad enthält. Das Verknüpfen mit einem Abschnitt innerhalb des neuen Artikels `#section` ist zulässig. Sie können bei Bedarf auch hier einen absoluten Pfad zu einer anderen Website verwenden.
- `redirect_document_id` Gibt an, ob Sie die Dokument-ID aus der vorherigen Datei beibehalten möchten. Der Standardwert ist `false` . Verwenden `true` Sie diese Eigenschaft, wenn Sie den `ms.documentid` Attributwert aus dem umgeleiteten Artikel beibehalten möchten. Wenn Sie die Dokument-ID beibehalten, werden Daten wie Seitenaufrufe und Rankings an den Ziel Artikel übertragen. Führen Sie diese Schritte aus, wenn die Umleitung in erster Linie ein umbenennen ist und kein Zeiger auf einen anderen Artikel, der nur einen Teil desselben Inhalts abdeckt.

Wenn Sie eine Umleitung hinzufügen, müssen Sie auch die alte Datei löschen.

## Erstellen eines neuen Artikels

Verwenden Sie den folgenden Workflow zum *Erstellen neuer Artikel* im Dokumentations-Repo über GitHub in einem Webbrowser:

1. Erstellen Sie eine Abzweigung außerhalb des MicrosoftDocs/Mixed-Reality-"Master"-Zweigs (mithilfe der Schaltfläche " **Gabel** " oben rechts).

   ![Gabeln Sie die Master Verzweigung.](images/forkbranch.png)
2. Wählen Sie im Ordner "Mixed-Reality-docs" oben rechts die Option **neue Datei erstellen** aus.
3. Erstellen Sie einen Seitennamen für den Artikel (verwenden Sie Bindestriche anstelle von Leerzeichen und verwenden Sie keine Interpunktions-oder Apostrophe), und fügen Sie ". MD" an.

   ![Benennen Sie die neue Seite.](images/newpagetitle.PNG)
   
   >[!IMPORTANT]
   >Stellen Sie sicher, dass Sie den neuen Artikel im Ordner "Mixed-Reality-docs" erstellen. Sie können dies bestätigen, indem Sie in der neuen Zeile für Dateinamen auf "/Mixed-Reality-docs/" überprüfen.

4. Fügen Sie oben auf der neuen Seite den folgenden Metadaten-Block hinzu:

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

5. Füllen Sie die relevanten Metadatenfelder gemäß den Anweisungen im [obigen Abschnitt](#editing-an-existing-article)aus.
6. Schreiben Sie Artikel Inhalte mithilfe von [Grundlagen](#markdown-basics)zum Abgleichen.
7. Fügen Sie `## See also` am Ende des Artikels einen Abschnitt mit Links zu anderen relevanten Artikeln hinzu.
8. Wenn Sie den Vorgang beenden, wählen Sie **neue Datei bestätigen**aus.
9. Wählen Sie **neue Pull-Anforderung** aus, und führen Sie den "Master"-Zweig Ihrer Gabel in MicrosoftDocs/Mixed-Reality-Master ein (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).

   ![Erstellen einer Pull-Anfrage von ihrer Gabelung in MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

## Grundlagen zu Abschriften

Mit den folgenden Ressourcen erfahren Sie, wie Sie die Dokumentation unter Verwendung der Abzugs Sprache bearbeiten können:

- [Grundlagen zu Abschriften](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Referenz Poster zu Abschlägen auf einen Blick](images/MarkdownPoster.pdf)
- [Zusätzliche Ressourcen zum Schreiben von Abschlägen für docs.Microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Hinzufügen von Tabellen

Aufgrund der Art und Weise, wie docs.Microsoft.com-Formatvorlagen Tabellen angezeigt werden, verfügen Sie nicht über Rahmen oder benutzerdefinierte Formatvorlagen, auch wenn Sie Inline-CSS versuchen. Es scheint für einen kurzen Zeitraum zu funktionieren, doch schließlich wird die Plattform die Formatierung aus der Tabelle entfernen. Planen Sie also weiter und halten Sie Ihre Tabellen einfach. [Hier finden Sie eine Website, die das](https://www.tablesgenerator.com/markdown_tables)Abspielen von Tabellen vereinfacht.

Die doc-Abzugs [Erweiterung für Visual Studio-Code](https://docs.microsoft.com/teamblog/docs-extension) macht auch die Tabellengenerierung einfach, wenn Sie [Visual Studio-Code verwenden (siehe unten)](#using-visual-studio-code) , um die Dokumentation zu bearbeiten.

### Hinzufügen von Bildern

Sie müssen Ihre Bilder in den Ordner "Mixed-Reality-docs/Images" im Repo hochladen und im Artikel entsprechend verweisen. Bilder werden automatisch in voller Größe angezeigt, was bedeutet, dass große Bilder die gesamte Breite des Artikels ausfüllen. Wir empfehlen, Ihre Bilder vor dem Hochladen zu sortieren. Die empfohlene Breite liegt zwischen 600 und 700 Pixeln, wenn Sie die Größe nach oben oder unten ändern sollten, wenn es sich um einen dichten Screenshot oder einen Bruchteil eines Screenshots handelt.

>[!IMPORTANT]
>Sie können vor dem Zusammenführen nur Bilder in Ihr gegabelte Repo hochladen. Wenn Sie also Bilder zu einem Artikel hinzufügen möchten, müssen Sie [Visual Studio-Code verwenden](#using-visual-studio-code) , um die Bilder zunächst dem Ordner "Images" ihrer Verzweigung hinzuzufügen, oder stellen Sie sicher, dass Sie die folgenden Schritte in einem Webbrowser ausgeführt haben:
>
>1. Hat das MicrosoftDocs/Mixed-Reality-Repo abgespalten.
>2. Artikel in ihrer Verzweigung bearbeitet.
>3. Sie haben die Bilder, auf die Sie in Ihrem Artikel verweisen, in den Ordner "Mixed-Reality-docs/Images" in ihrer Verzweigung hochgeladen.
>4. Hat eine **Pull-Anforderung** erstellt, um Ihre Gabel in den MicrosoftDocs/Mixed-Reality-"Master"-Zweig zu verschmelzen.
>
>Wenn Sie wissen möchten, wie Sie ein eigenes gegabelte Repo einrichten, folgen Sie den Anweisungen zum [Erstellen eines neuen Artikels](#creating-a-new-article).

## Anzeigen einer Vorschau Ihrer Arbeit

Wenn Sie in GitHub über einen Webbrowser bearbeiten, können Sie die Registerkarte **Vorschau** oben auf der Seite auswählen, um eine Vorschau Ihrer Arbeit anzuzeigen, bevor Sie einen Commit durchführen. 

>[!NOTE]
>Die Vorschau Ihrer Änderungen auf review.docs.Microsoft.com steht nur Microsoft-Mitarbeitern zur Verfügung.

Microsoft-Mitarbeiter: Nachdem Ihre Beiträge in den "Master"-Zweig verschmolzen sind, können Sie den Inhalt überprüfen, bevor er an die Öffentlichkeit geht https://review.docs.microsoft.com/hololens?branch=master . Suchen Sie Ihren Artikel mithilfe des Inhaltsverzeichnisses in der linken Spalte.

## Bearbeiten im Browser vs. Bearbeiten mit einem Desktop Client

Die Bearbeitung im Browser ist die einfachste Möglichkeit, schnelle Änderungen vorzunehmen, es gibt jedoch einige Nachteile:

- Sie erhalten keine Rechtschreibprüfung.
- Sie erhalten keine Smart-Links zu anderen Artikeln (Sie müssen den Dateinamen des Artikels manuell eingeben).
- Es kann mühsam sein, Bilder hochzuladen und zu referenzieren.

Wenn Sie sich nicht mit diesen Problemen befassen möchten, verwenden Sie einen Desktop Client wie [Visual Studio-Code](https://code.visualstudio.com/) mit einigen [hilfreichen Erweiterungen](#useful-extensions) , wenn Sie einen Beitrag leisten.

## Verwenden von Visual Studio-Code

Aus den [oben](#editing-in-the-browser-vs-editing-with-a-desktop-client)aufgelisteten Gründen empfiehlt es sich, einen Desktop-Client zu verwenden, um die Dokumentation anstelle eines Webbrowsers zu bearbeiten. Wir empfehlen die Verwendung von [Visual Studio-Code](https://code.visualstudio.com/).

### Setup

Führen Sie die folgenden Schritte aus, um Visual Studio-Code für die Arbeit mit diesem Repo zu konfigurieren:

1. In einem Webbrowser:
    1. Installieren [Sie git für Ihren PC](https://git-scm.com/downloads).
    2. Installieren Sie [Visual Studio-Code](https://code.visualstudio.com/).
    3. [Gabel MicrosoftDocs/Mixed-Reality](#creating-a-new-article) , wenn Sie dies noch nicht getan haben.
    4. Wählen Sie in ihrer Verzweigung **Klonen aus, oder laden** Sie die URL herunter, und kopieren Sie Sie.
2. Erstellen Sie einen lokalen Klon Ihrer Verzweigung in Visual Studio-Code:
    1. Wählen Sie im Menü **Ansicht** die Option **Befehls Palette**aus.
    2. Geben Sie "git: Clone" ein.
    3. Fügen Sie die kopierte URL ein.
    4. Wählen Sie aus, wo der Klon auf Ihrem PC gespeichert werden soll.
    5. Wählen Sie im Popupfenster **Open Repo** aus.

### Bearbeiten von Dokumentation

Verwenden Sie den folgenden Workflow, um Änderungen an der Dokumentation mit Visual Studio-Code vorzunehmen:

>[!NOTE]
>Alle Anleitungen für das [Bearbeiten](#editing-an-existing-article) und [Erstellen](#creating-a-new-article) von Artikeln und die [Grundlagen der Bearbeitung](#markdown-basics)von Abschlägen von oben gelten auch für die Verwendung von Visual Studio-Code.

1. Stellen Sie sicher, dass Ihre geklonte Gabel mit dem offiziellen Repo auf dem neuesten Stand ist.
   1. Erstellen Sie in einem Webbrowser eine Pull-Anforderung, um kürzlich vorgenommene Änderungen von anderen Mitwirkenden in MicrosoftDocs/Mixed-Reality-"Master" an Ihre Gabel zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).
      
      ![Synchronisieren von Änderungen von MicrosoftDocs/Mixed-Reality auf Ihre Gabel](images/sync_repos.PNG)
   2. Wählen Sie in Visual Studio-Code die Schaltfläche synchronisieren aus, um den frisch aktualisierten Fork mit dem lokalen Klon zu synchronisieren.
      
      ![Klicken Sie auf die Schaltfläche "synchronisieren".](images/sync_clone.png)
2. Erstellen oder bearbeiten Sie Artikel in Ihrem geklonten Repo mithilfe von Visual Studio-Code.
   1. Bearbeiten Sie einen oder mehrere Artikel (bei Bedarf Bilder in den Ordner "Bilder" hinzufügen).
   2. **Speichern** Sie die Änderungen im **Explorer**.
      
      ![Wählen Sie im Explorer "Alle speichern" aus.](images/explorer_save.png)
   3. Übernehmen Sie **alle** Änderungen in der **Quellcodeverwaltung** (Commit-Nachricht schreiben, wenn Sie dazu aufgefordert werden).
      
      ![Wählen Sie "alle commiten" in der Quellcodeverwaltung aus.](images/source_control_commit.png)
   4. Wählen Sie die Schaltfläche " **Synchronisieren** " aus, um Ihre Änderungen wieder in Origin zu synchronisieren (ihre Abzweigung auf GitHub).
      
      ![Klicken Sie auf die Schaltfläche synchronisieren.](images/sync_back.png)
3. Erstellen Sie in einem Webbrowser eine Pull-Anforderung, um neue Änderungen in Ihrer Gabel wieder in MicrosoftDocs/Mixed-Reality-Master zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).

   ![Erstellen einer Pull-Anfrage von ihrer Gabelung in MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

### Nützliche Erweiterungen

Die folgenden Visual Studio-Code Erweiterungen sind beim Bearbeiten von Dokumentation hilfreich:

- Docs-Abzugs [Erweiterung für Visual Studio-Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – verwenden Sie **ALT + M** , um ein Menü mit Dokument Erstellungsoptionen wie folgenden zu öffnen:
   - Suchen und referenzieren von Bildern, die Sie hochgeladen haben
   - Fügen Sie Formatierungen wie Listen, Tabellen und docs-spezifische Aufrufe wie `>[!NOTE]` .
   - Suchen und verweisen auf interne Links und Lesezeichen (Links zu bestimmten Abschnitten innerhalb einer Seite).
   - Formatierungsfehler sind hervorgehoben (zeigen Sie mit der Maus auf den Fehler, um weitere Informationen zu erhalten).
- [Code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -Rechtschreibprüfung – falsch geschriebene Wörter werden unterstrichen; Klicken Sie mit der rechten Maustaste auf ein falsch geschriebenes Wort, um es zu ändern oder im Wörterbuch zu speichern.
