---
title: Insider-Vorschau für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen und wertvolles Feedback für unser nächstes großes Betriebssystemupdate für HoloLens bereitstellen.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 1/21/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: c2d79c9cfbca263a507388227304f9d0dcecd9d0
ms.sourcegitcommit: f30add1d1eb07342e78a6baef87777c4d7123669
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297658"
---
# Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Die ersten Schritte sind einfach [und](hololens-insider.md#start-receiving-insider-builds) geben wertvolles Feedback für das nächste wichtige Betriebssystemupdate für HoloLens.

## Anmerkungen zur Windows-Insider-Version

Wir freuen uns, neue Features erneut für Windows-Insider zu verwenden. Wir werden einen Flight zum Dev Channel für die neuesten Updates machen. We will continue to update this page as we add more features and updates to our Windows Insider builds.  Freuen Sie sich, und bereiten Sie sich darauf vor, diese Updates in Ihre Realität zu mischen.

| Featurename                                              | Kurze Beschreibung                                                                      | Im Build verfügbar |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Neuer Microsoft Edge-Browser](#introducing-the-new-microsoft-edge) | Das neue Chromium-basierte Microsoft Edge ist jetzt für HoloLens 2 verfügbar.                         | 20279.1006 |
| [Neue Einstellungs-App](#new-settings-app)                     | Die ältere Einstellungs-App wird durch eine aktualisierte Version durch neue Features und Einstellungen ersetzt. | 20279.1006 |
| [Standardmäßige App-Auswahl](#default-app-picker)                 | Auswählen, welche App für jeden Datei- oder Linktyp gestartet werden soll                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Eine Verknüpfung zur Office Web App ist jetzt in "Alle Apps" aufgeführt.                                   | 20279.1006 |
| [Wischen zum Eingeben](#swipe-to-type)                           | Verwenden Sie die Fingerspitze, um Wörter auf der holografischen Tastatur zu "wischen".                        | 20279.1006 |
| [UNTERSTÜTZUNG für externes USB-C-Mikrofon](#usb-c-external-microphone-support) | Verwenden Sie USB-C-Mikrofone für Apps und/oder Remote Assist.| 20279.1006 |
| [Neue AUMIDs für neue Apps im Kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs für neue Einstellungen und Edge-Apps | 20279.1006 |
| [Verbesserte Fehlerbeweise im Kioskmodus](#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Kioskmodus sucht vor dem leeren Startmenü nach dem globalen zugewiesenen Zugriff. | 20279.1006 |
| [Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app) | Festlegen des Fallbackdiagnoseverhaltens in der App "Einstellungen" | 20279.1006 |

### Einführung in das neue Microsoft Edge

![Animation des älteren Microsoft Edge-Logos zum neuen Microsoft Edge-Logo](images/new-edge.gif)

Das neue Microsoft Edge [führt das Open -Source-Projekt Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ein, um eine bessere Kompatibilität für Kunden und eine geringere Fragmentierung des Webs für Webentwickler zu gewährleisten.

Mit dieser Insider Preview ist der neue Microsoft Edge zum ersten Mal für HoloLens 2-Kunden verfügbar! Während das neue Microsoft Edge in der Vergangenheit Microsoft Edge auf HoloLens 2 ersetzt, sind beide Browser derzeit für Insider verfügbar. Bitte teilen Sie Feedback und Fehler mit unserem Team über das Feature **"Feedback** senden" im neuen Microsoft Edge oder über den [Feedback-Hub.](hololens-feedback.md)

![Screenshot "Neuer Microsoft Edge"](images/new-edge-ui.png)

#### Starten des neuen Microsoft Edge

Insidern stehen zwei Versionen von Microsoft Edge zur Verfügung: das neue neue Microsoft Edge-Symbol (dargestellt durch ein blaues und grünes Kabelsymbol) und das ältere Microsoft Edge (dargestellt durch das weiße ![ ](images/new_edge_logo.png) "e"-Symbol). Das neue Microsoft Edge ist an das Startmenü angeheftet und wird automatisch gestartet, wenn Sie einen Weblink aktivieren. Wenn Sie zur Verwendung von älteren Microsoft Edge als Standardwebbrowser zurückkehren möchten, lesen Sie die anweisungen unten zum Zurücksetzen [von Standard-Apps.](#default-app-picker)

> [!NOTE]
> Wenn Sie das neue Microsoft Edge zum ersten Mal auf HoloLens 2 starten, werden Ihre Einstellungen und Daten aus der Vorgänger-Version von Microsoft Edge importiert. Wenn Sie nach dem Starten des neuen Microsoft Edge weiterhin Microsoft Edge der Vor-Vorgänger-Version verwenden, werden diese neuen Daten nicht von Microsoft Edge der Vor-Vorgänger-Version mit dem neuen Microsoft Edge synchronisiert.

#### Konfigurieren von Richtlinieneinstellungen für das neue Microsoft Edge

Das neue Microsoft Edge bietet IT-Administratoren einen viel umfassenderen Satz von Browserrichtlinien auf HoloLens 2 als bisher mit microsoft Edge der Vorgänger versionen verfügbar waren.

Hier sind einige hilfreiche Ressourcen, um mehr über das Verwalten von Richtlinieneinstellungen für das neue Microsoft Edge zu erfahren:

- [Konfigurieren der Microsoft Edge-Richtlinieneinstellungen mit Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Zuordnung von Richtlinien von Microsoft Edge-Vorgängerversionen zu Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Zuordnung von Richtlinien von Google Chrome zu Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Vollständige [Microsoft Edge Enterprise-Dokumentation](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Aufgrund der Anzahl von Browserrichtlinien, die vom neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie auf HoloLens 2 funktioniert. Wir haben jedoch getestet und bestätigt, dass das neue Microsoft Edge-Äquivalent jeder früher auf HoloLens 2 unterstützten Älteren Microsoft Edge-Richtlinie wie erwartet funktioniert. Informationen zur neuen Microsoft Edge-Entsprechung jeder älteren Microsoft Edge-Browserrichtlinie, die Sie mit HoloLens 2 verwendet haben, finden Sie unter ["Microsoft Edge Legacy-zu-Microsoft](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Edge-Richtlinienzuordnung".
>
> Es gibt mindestens zwei neue Microsoft Edge-Richtlinien, die wir *wissen, dass sie* nicht mit HoloLens 2 funktionieren:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### Was Sie von dem neuen Microsoft Edge auf HoloLens 2 erwarten können

Da es sich bei dem neuen Microsoft Edge um eine systemeigene Win32-App mit einer neuen UWP-Adapterebene handelt, die die Ausführung auf Nur-UWP-Geräten wie HoloLens 2 ermöglicht, sind einige Features möglicherweise nicht sofort verfügbar. We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.

**Szenarien und Features, die voraussichtlich funktionieren:**
- Erste Ausführung, Anmelden beim Profil und Synchronisierung
- Websites sollten wie erwartet gerendert und verhalten
- Die meisten Browserfunktionen (Favoriten, Verlauf usw.) sollten wie erwartet funktionieren.
- Dunkler Modus
- Installieren von Web Apps auf dem Gerät
- Installieren von Erweiterungen (teilen Sie uns bitte mit, wenn Sie Erweiterungen verwenden, die auf HoloLens 2 nicht ordnungsgemäß funktionieren)
- Anzeigen und Markieren einer PDF
- Räumlicher Sound aus einem einzelnen Browserfenster
- Automatische und manuelle Aktualisierung des Browsers
- Speichern einer PDF aus dem Menü "Drucken" (mit der Option "In PDF speichern")

**Szenarien und Features werden in Kürze folgen:**
- WebXR- und 360 -Viewer-Erweiterung
- Inhaltswiederherstellung zum Korrigieren des Fensters beim Durchsuchen mehrerer Fenster in Ihrer Umgebung
- Teilnahme an einem Microsoft Teams-Anruf über den Browser mit Video, Mixed Reality-Aufnahme oder Bildschirmfreigabe (das Beitreten von Anrufen mit Audio funktioniert gut)

**Szenarien und Features funktionieren nicht:**
- Räumlicher Sound aus mehreren Fenstern mit gleichzeitigen Audiodatenströmen
- "See it, say it"
- Drucken

**Die am besten bekannten Browserprobleme:**
- Durch zurücksetzen des Geräts wird das neue Microsoft Edge entfernt.
- Die Bildschirmlupevorschau auf der holografischen Tastatur zeigt falsche Inhalte an.

#### Microsoft Edge-Insider-Kanäle

Das Microsoft Edge-Team stellt der Edge-Insider-Community drei Vorschaukanäle zur Verfügung: Beta, Dev und Canary. Durch das Installieren eines Vorschaukanals wird die veröffentlichte Version von Microsoft Edge auf HoloLens 2 nicht deinstalliert, und Sie können mehrere gleichzeitig installieren. 

Besuchen Sie [die Microsoft Edge Insider-Homepage,](https://www.microsoftedgeinsider.com) um mehr über die Edge-Insider-Community zu erfahren. Weitere Informationen zu den verschiedenen Edge-Insider-Kanälen und den ersten Schritte finden Sie auf der [Edge-Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)

Es gibt mehrere Methoden zum Installieren von Microsoft Edge-Insider-Kanälen auf HoloLens 2:

**Direkte Installation auf dem Gerät (derzeit nur für nicht verwaltete Geräte verfügbar)**
  1. Besuchen Sie auf Ihrer HoloLens 2 die [Edge-Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie **die Schaltfläche "Download für HoloLens 2"** für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Starten Sie die heruntergeladene .msix-Datei aus der Edge-Downloadwarteschlange oder aus dem Ordner "Downloads" Ihres Geräts (mithilfe des Datei-Explorers).
  1. [Das App-Installationsprogramm](app-deploy-app-installer.md) wird gestartet.
  1. Wählen Sie die **Schaltfläche "Installieren"** aus.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev **** oder Canary als separaten Eintrag in der Liste "Alle Apps" im Startmenü.

**Installieren über PC mit dem Windows Device Portal [(entwicklermodus](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) muss auf HoloLens 2 aktiviert sein)**
  1. Besuchen Sie auf Ihrem PC die [Edge-Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie die Dropdownpfeilschaltfläche neben der Schaltfläche "Herunterladen für Windows 10" für den **Edge-Insider-Kanal** aus, den Sie installieren möchten.
  1. Auswählen **von HoloLens 2** im Dropdownmenü
  1. Speichern Sie die .msix-Datei im Ordner "Downloads" Ihres PCs (oder in einem anderen Ordner, den Sie leicht finden können).
  1. Verwenden [des Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC zum Installieren der heruntergeladenen .msix-Datei auf HoloLens 2
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev **** oder Canary als separaten Eintrag in der Liste "Alle Apps" im Startmenü.

> [!NOTE]
> Während dieser Windows-Insider-Vorschau für HoloLens 2 ist die Version von Microsoft Edge auf Ihrem Gerät möglicherweise höher als die, die in einigen (oder allen) Microsoft Edge-Insider-Kanälen verfügbar ist. Dadurch soll sichergestellt werden, dass neue Features und Fixes, die speziell auf den Webbrowser auf HoloLens 2 zielen, so schnell wie möglich an unsere Windows-Insider übermittelt werden. Kurz nach der öffentlichen Veröffentlichung des nächsten Windows-Updates werden die Microsoft Edge-Insider-Kanal-Builds die Version von Microsoft Edge auf Ihrer HoloLens 2 übertreffen und vor ihnen bleiben.

### Neue Einstellungs-App

In dieser Version wird eine neue Version der App "Einstellungen" eingeführt. Die neue Einstellungs-App umfasst neue Features und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Energie &-Ruhezustand, Netzwerk & Internet, Apps, Konten, Erleichterte Bedienung und vieles mehr.

> [!NOTE]
> Da sich die neue Einstellungs-App von der älteren Einstellungs-App unterscheidet, werden alle Einstellungsfenster, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Startseite der App "Neue Einstellungen"](images/new-settings-app.png)

**Neue Features und Einstellungen**
- Einstellungssuche: Suchen Nach Einstellungen auf der Startseite "Einstellungen" mithilfe von Schlüsselwörtern oder dem Namen der Einstellung
- System > Sound:
  - Ein- und Ausgabeaudiogeräte: Wählen Sie unabhängig Ihre Ein- und Ausgabeaudiogeräte aus (z. B. Audio über Bluetooth-Kopfhörer abhören oder ein USB-C-Mikrofon für die Audioeingabe verwenden). Hinweis: Bluetooth werden von HoloLens 2 nicht unterstützt.
  - App-Volume: Anpassen der Lautstärke der einzelnen Apps unabhängig
- System > Power &: Wählen Sie aus, wann das Gerät nach einer bestimmten Inaktivität in den Ruhezustand wechseln soll.
- System > Akku: Manuelles Aktivieren des Stromsparmodus oder Festlegen eines Akkuschwellenwerts, an dem der Stromsparmodus automatisch aktiviert wird
- Geräte > USB: Sie können standardmäßige USB-Verbindungen deaktivieren.
- Netzwerk & Internet:
  - USB-C-Ethernet-Adapter werden jetzt im Netzwerk & angezeigt
  - Usb-C-Ethernet-Adaptereinstellungen sind jetzt verfügbar, einschließlich der #A0
  - Sie können jetzt den Flugzeugmodus auf HoloLens 2 aktivieren
- Apps: Sie können die Für Datei- und Linktypen verwendeten Standard-Apps zurücksetzen. Weitere [Informationen finden Sie unter "Standardmäßige](#default-app-picker) App-Auswahl".
- Konten > andere Benutzer: Gerätebesitzer können Benutzer hinzufügen, Standardbenutzer auf Gerätebesitzer aktualisieren, Gerätebesitzer auf Standardbenutzer herabstufen und Benutzer entfernen.
- Erleichterte Bedienung: Ändern der Textgröße und einiger visueller Effekte

**Bekannte Probleme**
- Zuvor platzierte Einstellungsfenster werden entfernt (siehe Hinweis oben)
- Beim Besuch der Seite "Benachrichtigungen" kann die Einstellungs-App abstürzen (wird untersucht)
- Die Ethernetseite wird derzeit nicht angezeigt (in Kürze behoben)
- Der Akkuverbrauch für das neue Microsoft Edge ist aufgrund seiner Art als win32-Desktopanwendung, die von einer UWP-Adapterschicht unterstützt wird, möglicherweise nicht korrekt (bald keine Korrektur zu erwarten)

### Standardmäßige App-Auswahl

Wenn Sie einen Hyperlink aktivieren oder einen Dateityp mit mehr als einer installierten App öffnen, die ihn unterstützt, wird ein neues Fenster geöffnet, in dem Sie aufgefordert werden, auszuwählen, welche installierte App die Datei oder den Linktyp verarbeiten soll. In diesem Fenster können Sie auch auswählen, dass die ausgewählte App die Datei oder den Linktyp "Einmal" oder "Immer" behandeln soll.

![Fenster "App-Auswahl"](images/default-app-picker.png)

Wenn Sie "Immer" auswählen, aber später ändern möchten, welche App eine bestimmte Datei oder einen bestimmten Linktyp behandelt, können Sie ihre gespeicherten Standardeinstellungen unter "Einstellungen > **Apps" zurücksetzen.** Scrollen Sie zum unteren Rand **** der Seite, und wählen Sie die Schaltfläche "Löschen" unter "Standard-Apps für Dateitypen" und/oder "Standard-Apps für Linktypen" aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardeinstellungen für einzelne Dateitypen nicht zurücksetzen.

### Office Web App

Die Office Web App wurde der Liste "Alle Apps" im Startmenü hinzugefügt. Diese Web App kann auch an die Startseite angeheftet oder deinstalliert werden. Da es sich um eine Web-App handelt, entspricht ihre Funktionalität genau dem, was Sie beim Besuch erleben https://www.office.com würden. Die Office Web -App-Funktionalität ist nur verfügbar, wenn Ihre HoloLens 2 über eine aktive Internetverbindung verfügt.

### Wischen zum Eingeben

Einige Kunden finden es schneller, auf virtuellen Tastaturen "einzugeben", indem sie die Form des Worts swipsen, das sie eingeben möchten, und wir sehen uns diese Funktion für die holografische Tastatur in der Vorschau an. Sie können ein Wort nach dem anderen wischen, indem Sie die Fingerspitze durch die Fläche der holografischen Tastatur übergeben, die Form des Worts wischen und dann die Fingerspitze aus der Fläche der Tastatur ziehen. Sie können Nachworte wischen, ohne die LEERTASTE drücken zu müssen, indem Sie den Finger von der Tastatur zwischen Wörtern entfernen. Sie wissen, dass das Feature funktioniert, wenn eine Wischspur nach der Bewegung des Fingers auf der Tastatur angezeigt wird.

Bitte beachten Sie, dass diese Funktion aufgrund der Art einer holografischen Tastatur schwierig zu verwenden und zu mastern ist, bei der Sie (im Gegensatz zu einem Mobiltelefondisplay) keinen Widerstand gegen Ihren Finger verkraften. We are evaluating this feature for public release, so your feedback is important; Ob Sie das Feature hilfreich finden oder Feedback abgeben möchten, teilen Sie uns dies bitte über den [Feedback-Hub mit.](hololens-feedback.md)

### UNTERSTÜTZUNG für externes USB-C-Mikrofon

> [!IMPORTANT]
> Wenn Sie ein **USB-Mikrofon anschließen,** wird es nicht automatisch als Eingabegerät festgelegt. Beim Anschließen einer Gruppe von USB-C-Kopfhörern werden Benutzer feststellen, dass die Audiodaten des Kopfhörers automatisch an die Kopfhörer umgeleitet werden. Das #A0 priorisiert jedoch das interne Mikrofonarray über jedem anderen Eingabegerät. **Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**

Benutzer können externe USB-C-angeschlossene Mikrofone über den Bereich **"Soundeinstellungen"** auswählen. USB-C-Mikrofone können für Anrufe, Aufzeichnungen usw. verwendet werden.

Öffnen Sie die **Einstellungs-App,** und wählen **Sie**  ->  **Systemsound aus.**

![Soundeinstellungen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Um externe Mikrofone mit **Remote Assist**zu verwenden, müssen Benutzer auf den Link "Soundgeräte verwalten" klicken.
>
> Verwenden Sie dann die Dropdownliste, um das externe Mikrofon als Standard oder **Als** Standard **für Kommunikationen zu setzen.** Wenn Sie **"Standard"** auswählen, wird das externe Mikrofon überall verwendet.
>
> Wenn Sie **"Communications Default"** auswählen, wird das externe Mikrofon in Remote Assist und anderen Kommunikations-Apps verwendet, aber das HoloLens-Mikrofonarray kann weiterhin für andere Aufgaben verwendet werden.

![Verwalten von Soundgeräten](images/usbc-mic-2.png)

<br>

![Festlegen der Mikrofoneinstellung](images/usbc-mic-3.jpg)

#### Wie sieht es Bluetooth Mikrofonunterstützung aus?

Leider Bluetooth holoLens 2 derzeit noch keine Mikrofone unterstützt.

#### Problembehandlung bei USB-C-Mikrofonen

Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als Mikrofon *als auch als Lautsprecher* melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone an HoloLens anschließen, geht der Sound möglicherweise verloren. Glücklicherweise gibt es eine einfache Lösung.  

Legen Sie in **den**Einstellungen für Systemsound explizit die integrierten Lautsprecher  ->  ****  ->  **** **(Audiotreiber für analoge Features)** als **Standardgerät fest.** HoloLens sollte sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später wieder verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen](images/usbc-mic-4.png)

### Verwenden der neuen Einstellungen und Edge-Apps im Kioskmodus

Wenn Sie Apps in [Kiosks](hololens-kiosk.md)hinzufügen, fügt ein IT-Administrator die App häufig zum Kiosk hinzu, verwendet aber die App-Benutzermodell-ID (App User Model ID, AUMID). Da sowohl die Einstellungs-App als auch die Microsoft Edge-App als neue Apps gelten und sich von den älteren Apps unterscheiden, die AUMIDs für diese Apps verwenden, müssen sie aktualisiert werden, um die neue AUMID zu verwenden.

Wenn Sie einen Kiosk so ändern, dass er die neuen Apps enthält, empfehlen wir das Hinzufügen der neuen AUMID sowie das Verlassen der alten. Dies wird einen einfachen Übergang schaffen, wenn Benutzer das Betriebssystem aktualisieren und müssen keine neuen Richtlinien erhalten, um den Kiosk wie beabsichtigt weiter zu verwenden.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Alte Einstellungs-App       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Neue Einstellungs-App       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Alte Microsoft Edge-App | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Neue Microsoft Edge-App | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern

Wenn ein Gerät in älteren Builds eine Kioskkonfiguration hat, bei der es sich um eine Kombination aus globalem zugewiesenem[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)Zugriff und zugewiesenem Zugriff durch ein AAD-Gruppenmitglied handelt, wird dem Benutzer bei einem Fehler bei der Ermittlung der Mitgliedschaft in einer AAD-Gruppe nichts im Menü "Start" angezeigt.

Ab der Windows-Insider-Version wird die Kioskerfahrung bei Fehlern im Kioskmodus der AAD-Gruppe auf die globale Kioskkonfiguration (sofern vorhanden) zurückfallen.

### Konfigurieren der Fallbackdiagnose über die App "Einstellungen"

In der Einstellungs-App kann ein Benutzer nun das Verhalten der [Fallbackdiagnose konfigurieren.](hololens-diagnostic-logs.md) Navigieren Sie in **** der App "Einstellungen" zur Seite  ->  **"Datenschutzbehandlung",** um diese Einstellung zu konfigurieren.

> [!NOTE]
> Wenn für das Gerät eine MDM-Richtlinie konfiguriert ist, kann der Benutzer dieses Verhalten nicht außer Kraft setzen.  






## Start receiving Insider builds

> [!NOTE]
> Wenn Sie kürzlich noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Status zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche "Neustart" unter "Einstellungen/Windows-Insider-Programm" auswählen.
>
> Wir hatten einen Fehler auf dem Back-End, auf dem Sie möglicherweise aufgetreten sind, und dies wird Sie wieder auf kursverkn nen bringen.

On a HoloLens 2 device go to **Settings**  >  **Update & Security**Windows Insider  >  **Program** and select **Get started**. Verknüpfen Sie das Konto, mit dem Sie sich als Windows-Insider registriert haben.

Windows-Insider werden nun zu Kanälen um- Der **Schnelle** Ring wird der **** **Dev Channel,** der langsame Ring wird zum **Betakanal,** und der **Release** Preview Ring wird zum Release **Preview Channel.** So sieht diese Zuordnung aus:

![Erläuterung zu Windows-Insider-Kanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Einführung in Windows-Insider-Kanäle](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-Blogs.

Wählen Sie dann **"Aktive Entwicklung**von Windows" aus, wählen Sie aus, ob **Sie Dev Channel-** oder **Beta-Channel-Builds** erhalten möchten, und lesen Sie die Programmbedingungen.

Wählen **Sie "> Jetzt neu starten" aus,** um den Abschluss zu beenden. Nachdem Das Gerät neu gestartet wurde, wechseln Sie zu "Einstellungen **> Update & Sicherheit" > Suchen** Sie nach Updates, um den neuesten Build zu erhalten.

### Updatefehler 0x80070490– Fehlerumgearbeitung
Wenn beim Aktualisieren im Dev- oder Betakanal ein Updatefehler 0x80070490 auftritt, versuchen Sie es mit der folgenden kurzfristigen Lösung. Dazu gehört das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Zurück verschieben des Insider-Kanals.

#### Phase 1 – Release Preview
1.  Einstellungen, Update & Security, Windows-Insider-Programm, **Release Preview Channel auswählen.**
2.  Einstellungen, Update & Security, Windows Update, **Check for updates**. Fahren Sie nach dem Update mit Phase 2 fort.

#### Phase 2 : Dev Channel
1. Einstellungen, Update & Security, Windows-Insider-Programm, Dev **Channel auswählen.**
2. Einstellungen, Update & Security, Windows Update, **Check for updates**.

## FFU-Download- und Flash-Wegbeschreibungen
Um mit einer ffu zu testen, die mit einem Test-Flight signiert ist, müssen Sie zunächst ihr Gerät entsperren, bevor Sie die ffu mit Test-Flight-Signierten flashen.
1. Auf DEM PC:

    1. Laden Sie ffu auf Ihren PC von [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren sie ARC (Advanced Recovery Companion) aus dem Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. Auf HoloLens – Flight Unlock: Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up, reboot device.

1. Flash-FFU – Jetzt können Sie die FFU mit Flight-Signiert mit ARC flashen.

## Bereitstellen von Feedback und Melden von Problemen

Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrer HoloLens, um Feedback zu geben und Probleme zu melden. Die Verwendung des Feedbackhubs stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Achten Sie darauf, die Eingabeaufforderung zu akzeptieren, in der **** Sie gefragt werden, ob der Feedbackhub auf Ihren Ordner "Dokumente" zugreifen soll (wählen Sie "Ja" aus, wenn Sie dazu aufgefordert werden).

## Hinweis für Entwickler

Sie sind willkommen und möchten Versuchen, Ihre Anwendungen mit Insider-Builds von HoloLens zu entwickeln.  Sehen Sie sich die [Dokumentation für HoloLens-Entwickler an,](https://developer.microsoft.com/windows/mixed-reality/development) um zu beginnen. Diese Anweisungen funktionieren auch mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio, die Sie bereits für die Entwicklung von HoloLens verwenden.

## Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie abmelden, [](hololens-recovery.md) wann Ihre HoloLens einen Produktionsbuild ausgeführt, oder Sie können Ihr Gerät mithilfe des Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic wiederhergestellt.

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die sich nach der manuellen Neuinstallation eines neuen Vorschaubuilds von Insider -Preview-Builds nicht registrieren, einen Blauen Bildschirm erhalten würden. Danach müssen sie ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob sie betroffen sind oder nicht, finden Sie in diesem bekannten [Problem.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

So stellen Sie sicher, dass Ihre HoloLens einen Produktions build ausgeführt:

1. Wechseln Sie **zu Einstellungen > System > Informationen,** und suchen Sie die Buildnummer.

1. [Weitere Informationen finden Sie in den Versionshinweisen zu Produktions-Buildnummern.](hololens-release-notes.md)

So melden Sie Insider Builds ab:

1. On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program,** and select Stop Insider **builds**.

1. Befolgen Sie die Anweisungen, um Ihr Gerät abmelden.
