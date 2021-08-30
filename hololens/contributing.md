---
title: Anleitungen für Mitwirkende
description: Erfahren Sie, wie Sie mit GitHub-Flavored Markdown zur HoloLens-Dokumentation auf der docs.microsoft.com-Plattform beitragen.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188983"
---
# <a name="contributing-to-the-hololens-documentation"></a>Mitwirken an der HoloLens-Dokumentation

Willkommen bei der dokumentation zu [HoloLens](https://github.com/MicrosoftDocs/Hololens)! Alle Artikel, die Sie in diesem Repository erstellen oder **bearbeiten, sind für die Öffentlichkeit sichtbar.** 

HoloLens-Dokumentation wird auf der docs.microsoft.com-Plattform angezeigt, die GitHub-flavored Markdown mit Markdig-Features verwendet. Der Inhalt, den Sie in diesem Repository bearbeiten, wird in stilisierte Seiten formatiert, die unter /hololens angezeigt werden.

Auf dieser Seite werden die grundlegenden Schritte und Richtlinien für beiträge und Links zu Markdown-Grundlagen behandelt. Vielen Dank für Ihren Beitrag!

## <a name="available-repos"></a>Verfügbare Repositorys

| Name des Repositorys | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/Mixed Reality](/windows/mixed-reality) |
| VR-Handbuch für Fans | [MicrosoftDocs/mixed-reality/fan-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Vorbereitung

Wenn Sie noch nicht über ein Konto verfügen, müssen Sie [ein GitHub Konto erstellen.](https://github.com/join)

>[!NOTE]
>Wenn Sie Microsoft-Mitarbeiter sind, verknüpfen Sie Ihr GitHub-Konto mit Ihrem Microsoft-Alias im [Microsoft Open Source-Portal.](https://repos.opensource.microsoft.com/) Treten Sie den Organisationen **"Microsoft"** und **"MicrosoftDocs"** bei.

Beim Einrichten Ihres GitHub-Kontos empfehlen wir auch die folgenden Sicherheitsvorkehrungen:
- Erstellen Sie ein [sicheres Kennwort für Ihr GitHub-Konto.](https://github.com/settings/admin)
- Aktivieren Sie [die zweistufige Authentifizierung.](https://github.com/settings/two_factor_authentication/configure)
- Speichern Sie Ihre [Wiederherstellungscodes](https://github.com/settings/auth/recovery-codes) an einem sicheren Ort.
- Aktualisieren Sie die Einstellungen ihres [öffentlichen Profils.](https://github.com/settings/profile)
   - Legen Sie Ihren Namen fest, und legen Sie ihre *öffentliche E-Mail-Adresse* auf *Meine E-Mail-Adresse nicht anzeigen* fest.
   - Es wird empfohlen, ein Profilbild hochzuladen, da eine Miniaturansicht auf Dokumentationsseiten angezeigt wird, zu der sie beitragen.
- Wenn Sie die Befehlszeile verwenden möchten, sollten Sie [git Anmeldeinformationsverwaltung für Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)einrichten. Auf diese Weise müssen Sie nicht jedes Mal, wenn Sie einen Beitrag leisten, Ihr Kennwort eingeben.

Das Veröffentlichungssystem ist an GitHub gebunden, daher sind diese Schritte wichtig. Sie werden entweder als Autor oder Mitwirkender für jeden Artikel mit Ihrem GitHub-Alias aufgeführt.

## <a name="editing-an-existing-article"></a>Bearbeiten eines vorhandenen Artikels

Verwenden Sie den folgenden Workflow, um über GitHub in einem Webbrowser Aktualisierungen an einem *vorhandenen Artikel* vorzunehmen:

1. Navigieren Sie zu dem Artikel, den Sie bearbeiten möchten, im Ordner "mixed-reality-docs".

2. Wählen Sie oben rechts die Schaltfläche Bearbeiten (Stiftsymbol) aus.

   ![Bearbeiten sie einen Artikel.](images/editpage.png)

   Dadurch wird automatisch eine verwerfbare Verzweigung aus der Standardverzweigung _master_ gezweigt.

   > [!NOTE]
   > Dieser Artikel enthält Verweise auf _master_, einen Begriff, den Microsoft nicht mehr verwendet. Sobald der Begriff aus der Software entfernt wurde, wird er auch aus diesem Artikel entfernt.
   
3. Bearbeiten Sie den Inhalt des Artikels gemäß den [Markdown-Grundlagen.](#markdown-basics)

4. Aktualisieren Sie die Metadaten am Anfang jedes Artikels:

   * **title:** Seitentitel, der auf der Browserregisterkarte angezeigt wird, wenn der Artikel angezeigt wird. Seitentitel werden für SEO und Indizierung verwendet. Ändern Sie den Titel daher nur, wenn dies erforderlich ist (obwohl dies weniger wichtig ist, bevor die Dokumentation veröffentlicht wird).
   * **description:** Schreiben Sie eine kurze Beschreibung des Inhalts des Artikels, die SEO und Discovery steigert.
   * **author:** Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren GitHub Alias hinzu.
   * **ms.author:** Wenn Sie der primäre Besitzer der Seite sind, fügen Sie hier Ihren Microsoft-Alias hinzu (Sie benötigen nicht @microsoft.com , nur den Alias).
   * **ms.date:** Aktualisieren Sie das Datum, wenn Sie der Seite Hauptinhalte hinzufügen, aber nicht für Korrekturen wie Erläuterungen, Formatierung, Grammatik oder Rechtschreibung.
   * **keywords:** Schlüsselwörter helfen bei der SUCHMASCHINENOPTIMIERUNG (Suchmaschinenoptimierung). Fügen Sie Schlüsselwörter hinzu, die durch ein Komma und ein Leerzeichen getrennt sind, die für Ihren Artikel spezifisch sind, aber keine Interpunktion nach dem letzten Schlüsselwort in Der Liste. Sie müssen keine globalen Schlüsselwörter hinzufügen, die für alle Artikel gelten, da diese an anderer Stelle verwaltet werden. 
   
5. Scrollen Sie nach Abschluss der Bearbeitung Ihres Artikels nach unten, und wählen Sie **Dateiänderung vorschlagen** aus.

6. Wählen Sie auf der nächsten Seite **Pull Request erstellen** aus, um ihren automatisch erstellten Branch mit dem Standardverzweigung _master_ zusammenzuführen.

7. Wiederholen Sie die obigen Schritte für den nächsten Artikel, den Sie bearbeiten möchten.

## <a name="renaming-or-deleting-an-existing-article"></a>Umbenennen oder Löschen eines vorhandenen Artikels

Wenn Ihre Änderung einen vorhandenen Artikel umbenennen oder löschen wird, fügen Sie unbedingt eine Umleitung hinzu. Auf diese Weise werden alle Benutzer, die einen Link zum vorhandenen Artikel haben, immer noch am richtigen Ort sein. Umleitungen werden vom .openpublishing.redirection.jsin der Datei im Stammverzeichnis des Repositorys verwaltet.

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

- `redirect_document_id` gibt an, ob Sie die Dokument-ID aus der vorherigen Datei beibehalten möchten. Der Standardwert ist `false`. Verwenden `true` Sie , wenn Sie den `ms.documentid` Attributwert aus dem umgeleiteten Artikel beibehalten möchten. Wenn Sie die Dokument-ID beibehalten, werden Daten wie Seitenaufrufe und Rangfolgen an den Zielartikel übertragen. Legen Sie das so fest, wenn die Umleitung in erster Linie eine Umbenennung und kein Zeiger auf einen anderen Artikel ist, der nur einen Teil desselben Inhalts abdeckt.

Wenn Sie eine Umleitung hinzufügen, löschen Sie auch die alte Datei.

## <a name="creating-a-new-article"></a>Erstellen eines neuen Artikels

Verwenden Sie den folgenden Workflow, um neue Artikel im Dokumentations-Repository über GitHub in einem Webbrowser zu *erstellen:*

1. Erstellen Sie mithilfe der Verzweigungsschaltfläche rechts oben eine  Verzweigung des Standardzweigs _master_ von MicrosoftDocs/Mixed Reality.

   ![Verzweigen Sie den Standardverzweigung, der derzeit den Namen "master" hat.](images/forkbranch.png)

   > [!NOTE]
   > Dieser Artikel enthält Verweise auf _master_, einen Begriff, den Microsoft nicht mehr verwendet. Sobald der Begriff aus der Software entfernt wurde, wird er auch aus diesem Artikel entfernt.
   
2. Wählen Sie im Ordner "mixed-reality-docs" oben rechts die Option **Neue Datei erstellen** aus.

3. Erstellen Sie einen Seitennamen für den Artikel (verwenden Sie Bindestriche anstelle von Leerzeichen, und verwenden Sie keine Interpunktion oder Apostrophe), und fügen Sie ".md" an.

   ![Benennen Sie Ihre neue Seite.](images/newpagetitle.png)
   
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

5. Füllen Sie die relevanten Metadatenfelder aus, wie weiter oben in [Bearbeiten eines vorhandenen Artikels](#editing-an-existing-article)beschrieben.

6. Schreiben von Artikelinhalten mit [markdown basics](#markdown-basics).

7. Fügen Sie am Ende des Artikels einen `## See also` Abschnitt mit Links zu anderen relevanten Artikeln hinzu.

8. Wenn Sie fertig sind, wählen Sie **Commit new file (Neue Datei committen)** aus.

9. Wählen Sie **Neuer Pull Request** aus, und führen Sie den _Master-Branch_ Ihres Forks in MicrosoftDocs/Mixed Reality _Master_ zusammen (stellen Sie sicher, dass der Pfeil auf das richtige Ziel zeigt).

   ![Erstellen Sie pull request aus Ihrer Verzweigung in MicrosoftDocs/Mixed-Reality.](images/pr-to-master.png)

## <a name="markdown-basics"></a>Grundlegendes zu Markdown

In den folgenden Ressourcen erfahren Sie, wie Sie die Dokumentation mithilfe der Markdownsprache bearbeiten:

- [Markdown-Grundlagen](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Zusätzliche Ressourcen zum Schreiben von Markdown für docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Hinzufügen von Tabellen

Aufgrund der Art und Weise, wie Tabellen formatiert docs.microsoft.com, haben sie keine Rahmen oder benutzerdefinierten Stile, auch wenn Sie INLINE-CSS ausprobieren. Es scheint für einen kurzen Zeitraum zu funktionieren, aber schließlich entfernt die Plattform die Formatierung aus der Tabelle. Planen Sie also voraus, und halten Sie Ihre Tabellen einfach. Hier ist eine Website, die Markdowntabellen einfach macht: [Tabellengenerator]]( https://www.tablesgenerator.com/markdown_tables) .

Die [Docs Markdown-Erweiterung für Visual Studio Code](/teamblog/docs-extension) vereinfacht auch die Tabellengenerierung, wenn Sie Visual Studio Code verwenden [(siehe unten),](#using-visual-studio-code) um die Dokumentation zu bearbeiten.

### <a name="adding-images"></a>Hinzufügen von Bildern

Sie müssen Ihre Bilder in den Ordner "mixed-reality-docs/images" im Repository hochladen und dann im Artikel entsprechend darauf verweisen. Bilder werden automatisch in voller Größe gezeigt, was bedeutet, dass große Bilder die gesamte Breite des Artikels ausfüllen. Es wird empfohlen, ihre Bilder vorab zu sizingen, bevor Sie sie hochladen. Die empfohlene Breite liegt zwischen 600 und 700 Pixeln, aber Sie sollten die Größe nach oben oder unten ändern, wenn es sich um einen dichten Screenshot oder einen Bruchteil eines Screenshots handelt.

>[!IMPORTANT]
>Sie können Bilder nur vor dem Zusammenführen in Ihr ge forktete Repository hochladen. Wenn Sie also einem Artikel Bilder hinzufügen möchten, müssen Sie [Visual Studio Code](#using-visual-studio-code) verwenden, um die Bilder zuerst dem Ordner "images" Ihres Forks hinzuzufügen, oder stellen Sie sicher, dass Sie folgende Schritte in einem Webbrowser durchgeführt haben:
>
>1. Forked the MicrosoftDocs/mixed-reality repo.
>2. Der Artikel wurde in Ihrem Fork bearbeitet.
>3. Sie haben die Bilder, auf die Sie in Ihrem Artikel verweisen, in den Ordner "mixed-reality-docs/images" in Ihrem Fork hochgeladen.
>4. Es wurde ein **Pull Request erstellt,** um Ihren Fork mit dem Master-Branch MicrosoftDocs/Mixed Reality _zusammen_ zu führen.
>
>Um zu erfahren, wie Sie Ihr eigenes ge forkiertes Repository einrichten, befolgen Sie die Anweisungen zum [Erstellen eines neuen Artikels.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Anzeigen einer Vorschau Ihrer Arbeit

Beim Bearbeiten in GitHub über einen Webbrowser können  Sie oben auf der Seite die Registerkarte Vorschau auswählen, um eine Vorschau Ihrer Arbeit anzuzeigen, bevor Sie einen Commit committen. 

>[!NOTE]
>Die Vorschau Ihrer Änderungen auf review.docs.microsoft.com ist nur für Microsoft-Mitarbeiter verfügbar.

Microsoft-Mitarbeiter: Wenn Ihre Beiträge in der Standardverzweigung _master_ zusammengeführt wurden, können Sie den Inhalt überprüfen, bevor er unter </hololens?branch=master>. Suchen Sie Ihren Artikel mithilfe des Inhaltsverzeichnis in der linken Spalte.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Bearbeiten im Browser im Vergleich zur Bearbeitung mit einem Desktopclient

Die Bearbeitung im Browser ist die einfachste Möglichkeit, um schnelle Änderungen vorzunehmen, es gibt jedoch einige Nachteile:

- Sie erhalten keine Rechtschreibprüfung.
- Sie erhalten keine intelligente Verknüpfung mit anderen Artikeln (Sie müssen den Dateinamen des Artikels manuell eingeben).
- Es kann mühsam sein, Bilder hochzuladen und darauf zu verweisen.

Wenn Sie sich nicht mit diesen Problemen befassen möchten, verwenden Sie [](#useful-extensions) einen Desktopclient wie [Visual Studio Code](https://code.visualstudio.com/) mit einigen hilfreichen Erweiterungen, wenn Sie mitwirken.

## <a name="using-visual-studio-code"></a>Verwendung von Visual Studio Code

Aus den oben [genannten Gründen](#editing-in-the-browser-vs-editing-with-a-desktop-client)können Sie die Verwendung eines Desktopclients zum Bearbeiten der Dokumentation anstelle eines Webbrowsers bevorzugen. Wir empfehlen die Verwendung von [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Einrichten

Führen Sie die folgenden Schritte aus, um Visual Studio Code für die Arbeit mit diesem Repository zu konfigurieren:

1. In einem Webbrowser:
    1. Installieren [Sie Git für Ihren PC.](https://git-scm.com/downloads)
    2. Installieren Sie [Visual Studio Code](https://code.visualstudio.com/).
    3. [Forken Sie MicrosoftDocs/mixed-reality,](#creating-a-new-article) sofern noch nicht vorhanden.
    4. Wählen Sie in Ihrem Fork **Klonen oder herunterladen aus,** und kopieren Sie die URL.
2. Erstellen Sie einen lokalen Klon Ihres Forks in Visual Studio Code:
    1. Wählen Sie **im Menü** Ansicht die Option **Befehlspalette aus.**
    2. Geben Sie "Git: Clone" ein.
    3. Fügen Sie die kopierte URL ein.
    4. Wählen Sie aus, wo der Klon auf Ihrem PC gespeichert werden soll.
    5. Wählen **Sie im Popupfenster** Open repo (Repository öffnen) aus.

### <a name="editing-documentation"></a>Bearbeiten der Dokumentation

Verwenden Sie den folgenden Workflow, um Änderungen an der Dokumentation mit Visual Studio Code:

>[!NOTE]
>Alle Oben [genannten](#editing-an-existing-article) Anleitungen zum [Bearbeiten](#creating-a-new-article) und Erstellen von Artikeln sowie die Grundlagen der Bearbeitung von [Markdown](#markdown-basics)gelten auch, wenn sie Visual Studio Code verwenden.

1. Stellen Sie sicher, dass Ihr geklonter Fork mit dem offiziellen Repository auf dem neuesten Stand ist.

   1. Erstellen Sie in einem Webbrowser einen Pull Request, um aktuelle Änderungen von anderen Mitwirkenden im Standardzweig von MicrosoftDocs/mixed-reality, _master,_ mit Ihrer Verzweigung zu synchronisieren (stellen Sie sicher, dass der Pfeil auf das richtige Ziel zeigt).
      
      ![Synchronisieren Sie Änderungen von MicrosoftDocs/Mixed Reality mit Ihrem Fork.](images/sync-repos.png)
      
   2. Wählen Visual Studio Code Synchronisierungsschaltfläche aus, um Den neu aktualisierten Fork mit dem lokalen Klon zu synchronisieren.
      
      ![Klicken Sie auf das Bild der Synchronisierungsschaltfläche.](images/sync-clone.png)
      
2. Erstellen oder bearbeiten Sie Artikel in Ihrem geklonten Repository mithilfe Visual Studio Code.

   1. Bearbeiten Sie einen oder mehrere Artikel (fügen Sie bei Bedarf Bilder zum Ordner "images" hinzu).
   
   2. **Speichern Sie** die Änderungen im **Explorer.**
      
      ![Auswählen von "Alle speichern" im Explorer](images/explorer-save.png)
      
   3. **Commit für alle** Änderungen in **der Quellcodeverwaltung** ausführen (Commitnachricht schreiben, wenn sie dazu aufgefordert wird).
   
      ![Auswählen von "Commit all" in der Quellcodeverwaltung](images/source-control-commit.png)
      
   4. Wählen Sie die **Synchronisierungsschaltfläche** aus, um Ihre Änderungen wieder mit dem Ursprung zu synchronisieren (Ihr Fork auf GitHub).
      
      ![Klicken Sie auf die Synchronisierungsschaltfläche.](images/sync-back.png)
      
3. Erstellen Sie in einem Webbrowser einen Pull Request, um neue Änderungen in Ihrem Fork mit microsoftdocs/mixed-reality _master_ zu synchronisieren (stellen Sie sicher, dass der Pfeil auf das richtige Ziel zeigt).

   ![Erstellen Sie einen Pull Request aus Ihrem Fork in MicrosoftDocs/Mixed Reality.](images/pr-to-master.png)

### <a name="useful-extensions"></a>Nützliche Erweiterungen

Die folgenden Visual Studio Code-Erweiterungen sind beim Bearbeiten der Dokumentation nützlich:

- [Docs Markdown-Erweiterung für Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) Verwenden Sie **ALT+M,** um ein Menü mit Dokumenterstellungsoptionen wie den folgenden zu öffnen:
   - Suchen Sie bilder, und verweisen Sie auf Bilder, die Sie hochgeladen haben.
   - Fügen Sie Formatierungen wie Listen, Tabellen und dokumentspezifische Aufrufe wie `>[!NOTE]` hinzu.
   - Suchen und Verweisen auf interne Links und Lesezeichen (Links zu bestimmten Abschnitten auf einer Seite).
   - Formatierungsfehler sind hervorgehoben (bewegen Sie den Mauszeiger über den Fehler, um mehr zu erfahren).
- [Rechtschreibprüfung für Code:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) Falsch geschriebene Wörter werden unterstrichen. Klicken Sie mit der rechten Maustaste auf ein falsch geschriebenes Wort, um es zu ändern oder im Wörterbuch zu speichern.
