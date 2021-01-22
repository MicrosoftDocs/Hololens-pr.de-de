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
# Beitrag zur HoloLens-Dokumentation

Willkommen bei der [HoloLens-Dokumentation!](https://github.com/MicrosoftDocs/Hololens) Alle Artikel, die Sie in diesem Repository erstellen oder **bearbeiten, sind für die Öffentlichkeit sichtbar.** 

HoloLens-Dokumente werden auf der docs.microsoft.com angezeigt, die GitHub-markdown mit Markdig-Features verwendet. Der Inhalt, den Sie in diesem Repository bearbeiten, wird in stilisierten Seiten formatiert, die unter angezeigt https://docs.microsoft.com/hololens werden. 

Auf dieser Seite werden die grundlegenden Schritte und Richtlinien für die Mitwirkung sowie Links zu den Grundlagen von Markdown behandelt. Vielen Dank für Ihren Beitrag!

## Verfügbare Repositorys

| Repositoryname | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-reality](https://docs.microsoft.com/windows/mixed-reality) |
| Leitfaden für VR-Enthusiasten | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Vorbereitung

Wenn Sie noch keins haben, müssen Sie ein [GitHub-Konto erstellen.](https://github.com/join)

>[!NOTE]
>Wenn Sie ein Microsoft-Mitarbeiter sind, verknüpfen Sie Ihr GitHub-Konto mit Ihrem Microsoft-Alias im [Microsoft Open Source-Portal.](https://repos.opensource.microsoft.com/) Treten Sie **den Organisationen "Microsoft"** und **"MicrosoftDocs"** bei.

Beim Einrichten Ihres GitHub-Kontos empfehlen wir auch die folgenden Sicherheitsvorkehrungen:
- Erstellen Sie [ein starkes Kennwort für Ihr GitHub-Konto.](https://github.com/settings/admin)
- Aktivieren [Sie die zweistufige Authentifizierung.](https://github.com/settings/two_factor_authentication/configure)
- Speichern Sie [Ihre Wiederherstellungscodes](https://github.com/settings/auth/recovery-codes) an einem sicheren Ort.
- Aktualisieren Sie [Ihre öffentlichen Profileinstellungen.](https://github.com/settings/profile)
   - Legen Sie Ihren Namen ** und ihre öffentliche E-Mail auf "Meine E-Mail-Adresse *nicht anzeigen" festlegen.*
   - Es wird empfohlen, ein Profilbild hochzuladen, da eine Miniaturansicht auf Dokumentseiten angezeigt wird, zu der Sie beitragen.
- Wenn Sie die Befehlszeile verwenden möchten, erwägen Sie die Einrichtung von [Git Credential Manager für Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Auf diese Weise müssen Sie Ihr Kennwort nicht jedes Mal eingeben, wenn Sie einen Beitrag leisten.

Das Veröffentlichungssystem ist an GitHub gebunden, daher sind diese Schritte wichtig. Sie werden entweder als Autor oder Mitwirkender für jeden Artikel mit Ihrem GitHub-Alias aufgeführt.

## Bearbeiten eines vorhandenen Artikels

Verwenden Sie den folgenden Workflow, um aktualisierungen an *einem vorhandenen Artikel* über GitHub in einem Webbrowser:

1. Navigieren Sie im Ordner "mixed-reality-docs" zu dem Artikel, den Sie bearbeiten möchten.

2. Wählen Sie oben rechts die Bearbeitungsschaltfläche (Stiftsymbol) aus, die automatisch einen verzweigten Zweig von der Verzweigung "Master" verzweigt.

   ![Bearbeiten eines Artikels.](images/editpage.png)
   
3. Bearbeiten Sie den Inhalt des Artikels gemäß den ["Markdown-Grundlagen".](#markdown-basics)

4. Aktualisieren Von Metadaten am Anfang jedes Artikels:

   * **title:** Seitentitel, der auf der Browserregisterkarte angezeigt wird, wenn der Artikel angezeigt wird. Seitentitel werden für SEO und Indizierung verwendet. Ändern Sie daher den Titel nur, wenn dies erforderlich ist (dies ist jedoch weniger wichtig, bevor die Dokumentation veröffentlicht wird).
   * **description**: Schreiben Sie eine kurze Beschreibung der Inhalte des Artikels, die SEO und Ermittlung fördert.
   * **author:** Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren GitHub-Alias hinzu.
   * **ms.author**: Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren Microsoft-Alias hinzu (Sie benötigen nicht @microsoft.com, sondern nur den Alias).
   * **ms.date**: Aktualisieren Sie das Datum, wenn Sie der Seite hauptinhalt hinzufügen, aber nicht für Korrekturen wie Klarstellung, Formatierung, Grammatik oder Rechtschreibung.
   * **keywords**: Keywords aid in SEO (search engine optimization). Fügen Sie Schlüsselwörter, getrennt durch ein Komma und ein Leerzeichen, hinzu, die für Ihren Artikel spezifisch sind, aber keine Interpunktion nach dem letzten Schlüsselwort in der Liste. Sie müssen keine globalen Schlüsselwörter hinzufügen, die für alle Artikel gelten, da diese an anderer Stelle verwaltet werden. 
   
5. Wenn Sie ihre Artikelbearbeitungen abgeschlossen haben, scrollen Sie nach unten, und wählen **Sie "Dateiänderung vorschlagen" aus.**

6. Wählen Sie auf der nächsten Seite **"Pullanforderung erstellen"** aus, um die automatisch erstellte Verzweigung in "Master" zusammenführen.

7. Wiederholen Sie die obigen Schritte für den nächsten Artikel, den Sie bearbeiten möchten.

## Umbenennen oder Löschen eines vorhandenen Artikels

Wenn Ihre Änderung einen vorhandenen Artikel umbenennen oder löschen wird, müssen Sie eine Umleitung hinzufügen. Auf diese Weise wird jeder Benutzer mit einem Link zum vorhandenen Artikel immer noch an der richtigen Stelle landen. Umleitungen werden vom .openpublishing.redirection.jsA0 im Stammverzeichnis des Repositorys verwaltet.

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

- Dies `source_path` ist der relative Repositorypfad zu dem alten Artikel, den Sie entfernen. Stellen Sie sicher, dass der Pfad `mixed-reality-docs` mit beginnt und mit `.md` .

- Dies `redirect_url` ist die relative öffentliche URL aus dem alten Artikel zum neuen Artikel. Stellen Sie sicher, dass **diese** URL nicht enthalten ist, da sie auf die öffentliche URL und nicht auf `mixed-reality-docs` den `.md` Repositorypfad verweist. Das Verknüpfen mit einem Abschnitt innerhalb des neuen Artikels ist `#section` zulässig. Sie können hier bei Bedarf auch einen absoluten Pfad zu einer anderen Website verwenden.

- `redirect_document_id` gibt an, ob sie die Dokument-ID aus der vorherigen Datei behalten möchten. Der Standardwert ist `false` . Verwenden `true` Sie diese Eigenschaft, wenn Sie den `ms.documentid` Attributwert aus dem umgeleiteten Artikel beibehalten möchten. Wenn Sie die Dokument-ID beibehalten, werden Daten, z. B. Seitenansichten und Rangfolge, an den Zielartikel übertragen. Tun Sie dies, wenn es sich bei der Umleitung in erster Linie um eine Umbenennung und nicht um einen Zeiger auf andere Artikel handelt, die nur einen Teil desselben Inhalts enthalten.

Wenn Sie eine Umleitung hinzufügen, müssen Sie auch die alte Datei löschen.

## Erstellen eines neuen Artikels

Verwenden Sie den folgenden Workflow, *um neue Artikel* im Dokumentationsreposi bericht über GitHub in einem Webbrowser zu erstellen:

1. Erstellen Sie eine Verzweigung von der Verzweigung "MicrosoftDocs/mixed-reality" "Master" (mit der Schaltfläche **"Verzweigung"** oben rechts).

   ![Verzweigung des Hauptzweigs.](images/forkbranch.png)
   
2. Wählen Sie im Ordner "mixed-reality-docs" oben rechts "Neue Datei erstellen" aus. ****

3. Erstellen Sie einen Seitennamen für den Artikel (verwenden Sie Bindestriche anstelle von Leerzeichen und verwenden Sie keine Interpunktion oder Apostrophen), und hängen Sie ".md" an.

   ![Benennen Sie die neue Seite.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Stellen Sie sicher, dass Sie den neuen Artikel im Ordner "mixed-reality-docs" erstellen. Sie können dies bestätigen, indem Sie in der neuen Dateinamenzeile nach "/mixed-reality-docs/" suchen.

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

5. Füllen Sie die relevanten Metadatenfelder nach den Anweisungen im [abschnitt oben aus.](#editing-an-existing-article)

6. Schreiben von Artikelinhalten mithilfe [von Markdown-Grundlagen.](#markdown-basics)

7. Fügen Sie am Ende des Artikels einen Abschnitt mit Links `## See also` zu anderen relevanten Artikeln hinzu.

8. Wenn Sie fertig sind, wählen **Sie Commit für neue Datei aus.**

9. Wählen **Sie "Neue Pullanforderung"** aus, und führen Sie die Verzweigung "Master" Ihrer Verzweigung mit "MicrosoftDocs/mixed-reality"master" zusammen (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).

   ![Erstellen einer Pullanforderung von Ihrer Vererbung in MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## Grundlegendes zu Markdown

In den folgenden Ressourcen erfahren Sie, wie Sie die Dokumentation mit der Sprache Markdown bearbeiten:

- [Grundlegendes zu Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Zusätzliche Ressourcen zum Schreiben von Markdown für docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Hinzufügen von Tabellen

Aufgrund der Art docs.microsoft.com Formatvorlagentabellen verfügen sie nicht über Rahmen oder benutzerdefinierte Formatvorlagen, auch wenn Sie Inline-CSS ausprobieren. Es scheint für einen kurzen Zeitraum zu funktionieren, aber schließlich wird die Plattform die Formatierung aus der Tabelle verdingen. Planen Sie also voraus, und halten Sie Ihre Tabellen einfach. [Hier ist eine Website, die Die Tabelle Markdown erleichtert.](https://www.tablesgenerator.com/markdown_tables)

Die [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) erleichtert auch die Tabellengenerierung, wenn Sie Visual Studio Code [(siehe unten)](#using-visual-studio-code) zum Bearbeiten der Dokumentation verwenden.

### Hinzufügen von Bildern

Sie müssen Ihre Bilder in den Ordner "mixed-reality-docs/images" im Repository hochladen und dann im Artikel entsprechend darauf verweisen. Bilder werden automatisch in voller Größe angezeigt, was bedeutet, dass große Bilder die gesamte Breite des Artikels ausfüllen. Es wird empfohlen, die Größe Ihrer Bilder vor dem Hochladen vorzubeisieren. Die empfohlene Breite liegt zwischen 600 und 700 Pixel. Sie sollten die Größe jedoch nach oben oder unten ändern, wenn es sich um einen dichten Screenshot bzw. einen Bruchteil eines Screenshot handelt.

>[!IMPORTANT]
>Sie können Bilder nur vor dem Zusammenführen in Ihr ver forkiertes Repository hochladen. Wenn Sie also planen, Bilder zu einem Artikel hinzuzufügen, müssen Sie [zunächst Visual Studio Code](#using-visual-studio-code) verwenden, um die Bilder dem Ordner "Bilder" Ihrer Vererbung hinzuzufügen, oder stellen Sie sicher, dass Sie folgendes in einem Webbrowser durchgeführt haben:
>
>1. Ver forked the MicrosoftDocs/mixed-reality repo.
>2. Der Artikel wurde in Ihrer Ver fork bearbeitet.
>3. Die Bilder, auf die Sie in Ihrem Artikel verweisen, wurden in den Ordner "mixed-reality-docs/images" in Ihrer Vererbung hochgeladen.
>4. Es wurde **eine Pullanforderung erstellt,** um Ihre Verzweigung mit der Verzweigung "MicrosoftDocs/mixed-reality"-Master zusammenführen.
>
>Um zu erfahren, wie Sie Ihr eigenes ver forkiertes Repository einrichten, folgen Sie den Anweisungen zum [Erstellen eines neuen Artikels.](#creating-a-new-article)

## Anzeigen einer Vorschau Ihrer Arbeit

Beim Bearbeiten in GitHub über einen Webbrowser **** können Sie die Registerkarte "Vorschau" am oberen Rand der Seite auswählen, um vor dem Commit eine Vorschau Ihrer Arbeit anzuzeigen. 

>[!NOTE]
>Das Anzeigen einer Vorschau Ihrer Änderungen auf review.docs.microsoft.com ist nur für Mitarbeiter von Microsoft verfügbar

Microsoft-Mitarbeiter: Nachdem Ihre Beiträge mit dem Hauptzweig zusammengeführt wurden, können Sie die Inhalte überprüfen, bevor sie öffentlich https://review.docs.microsoft.com/hololens?branch=master werden. Suchen Sie Ihren Artikel mithilfe des Inhaltsverzeichnisses in der linken Spalte.

## Bearbeiten im Browser im Vergleich zur Bearbeitung mit einem Desktopclient

Die Bearbeitung im Browser ist die einfachste Möglichkeit, schnelle Änderungen vorzunehmen, es gibt jedoch einige Nachteile:

- Sie erhalten keine Rechtschreibprüfung.
- Sie erhalten keine intelligente Verknüpfung mit anderen Artikeln (Sie müssen den Dateinamen des Artikels manuell eingeben).
- Das Hochladen und Verweisen auf Bilder kann sehr einfach sein.

Wenn Sie diese Probleme lieber nicht beheben möchten, verwenden Sie einen Desktopclient wie [Visual Studio Code](https://code.visualstudio.com/) mit einigen hilfreichen [Erweiterungen,](#useful-extensions) wenn Sie dazu beitragen.

## Verwenden Visual Studio Code

Aus den oben [aufgeführten Gründen](#editing-in-the-browser-vs-editing-with-a-desktop-client)bevorzugen Sie möglicherweise die Verwendung eines Desktopclients zum Bearbeiten der Dokumentation anstelle eines Webbrowsers. Es wird empfohlen, [Visual Studio Code zu verwenden.](https://code.visualstudio.com/)

### Setup

Führen Sie die folgenden Schritte aus, um Visual Studio Code für die Arbeit mit diesem Repository zu konfigurieren:

1. In einem Webbrowser:
    1. Installieren [Sie Git für Ihren PC.](https://git-scm.com/downloads)
    2. Installieren [Visual Studio Code](https://code.visualstudio.com/).
    3. [Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.
    4. Wählen Sie in Ihrer Vererbung **Klonen oder Herunterladen und** Kopieren der URL aus.
2. Erstellen Sie einen lokalen Klon Ihrer Ver fork in Visual Studio Code:
    1. Wählen Sie **im Menü** "Ansicht" die **Befehlspalette aus.**
    2. Geben Sie "Git: Klonen" ein.
    3. Fügen Sie die kopierte URL ein.
    4. Wählen Sie aus, wo der Klon auf Ihrem PC gespeichert werden soll.
    5. Wählen **Sie im** Popup "Repository öffnen" aus.

### Bearbeitungsdokumentation

Verwenden Sie den folgenden Workflow, um Änderungen an der Dokumentation mit Visual Studio vorzunehmen:

>[!NOTE]
>Alle Anleitungen [zum](#editing-an-existing-article) Bearbeiten und Erstellen von Artikeln sowie die Grundlagen der Bearbeitung von [Markdown](#markdown-basics)von oben gelten auch bei verwendung von Visual Studio Code. [](#creating-a-new-article)

1. Stellen Sie sicher, dass Die geklonte Ver fork mit dem offiziellen Repository auf dem neuesten Stand ist.

   1. Erstellen Sie in einem Webbrowser eine Pullanforderung, um aktuelle Änderungen von anderen Mitwirkenden in MicrosoftDocs/Mixed-Reality-"Master" mit Ihrer Vererbung zu synchronisieren (stellen Sie sicher, dass der Pfeil auf den richtigen Weg zeigt).
      
      ![Synchronisieren von Änderungen von MicrosoftDocs/mixed-reality mit Ihrer Vererbung](images/sync-repos.png)
      
   2. Wählen Visual Studio Code die Synchronisierungsschaltfläche aus, um die aktualisierte Ver fork mit dem lokalen Klon zu synchronisieren.
      
      ![Klicken Sie auf das Bild der Synchronisierungsschaltfläche.](images/sync-clone.png)
      
2. Erstellen oder bearbeiten Sie Artikel in Ihrem geklonten Repository mithilfe Visual Studio Code.

   1. Bearbeiten Sie einen oder mehrere Artikel (fügen Sie bei Bedarf Bilder zum Ordner "Bilder" hinzu).
   
   2. **Änderungen** im **Explorer speichern.**
      
      ![Choose "Save all" in Explorer](images/explorer-save.png)
      
   3. **Commit aller** Änderungen in der **Quellcodeverwaltung** (Commitnachricht schreiben, wenn Sie dazu aufgefordert werden).
   
      ![Wählen Sie in der Quellcodeverwaltung "Commit für alle" aus.](images/source-control-commit.png)
      
   4. Wählen Sie die **Synchronisierungsschaltfläche** aus, um Ihre Änderungen wieder mit dem Ursprung zu synchronisieren (Ihre Vererbung auf GitHub).
      
      ![Klicken Sie auf die Schaltfläche "Synchronisierung".](images/sync-back.png)
      
3. Erstellen Sie in einem Webbrowser eine Pullanforderung, um neue Änderungen in Ihrer Ver fork zurück zu MicrosoftDocs/Mixed-Reality-Master zu synchronisieren (stellen Sie sicher, dass der Pfeil auf die richtige Weise zeigt).

   ![Erstellen einer Pullanforderung von Ihrer Vererbung in MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### Nützliche Erweiterungen

Die folgenden Visual Studio Codeerweiterungen sind beim Bearbeiten der Dokumentation hilfreich:

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **ALT+M** to bring up a menu of docs authoring options like:
   - Suchen und Referenzieren von Bildern, die Sie hochgeladen haben.
   - Fügen Sie Formatierungen wie Listen, Tabellen und dokumentspezifische Call-Outs hinzu, z. `>[!NOTE]` B. .
   - Suchen und Verweisen auf interne Links und Lesezeichen (Links zu bestimmten Abschnitten auf einer Seite).
   - Formatierungsfehler werden hervorgehoben (zeigen Sie mit der Maus auf den Fehler, um mehr zu erfahren).
- [Code spell checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – falsch geschriebene Wörter werden unterstrichen; Klicken Sie mit der rechten Maustaste auf ein falsch geschriebenes Wort, um es zu ändern oder im Wörterbuch zu speichern.
