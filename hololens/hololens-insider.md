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
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 3d7c4b5347019682896bb695690190e633c80677
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327399"
---
# Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider -Preview-Builds für HoloLens! Die ersten Schritte sind einfach [und](hololens-insider.md#start-receiving-insider-builds) geben wertvolles Feedback für das nächste wichtige Betriebssystemupdate für HoloLens.

## Anmerkungen zur Windows-Insider-Version

Wir freuen uns, neue Features erneut für Windows-Insider zu verwenden. Neue Builds werden für die neuesten Updates in den Dev Channel übertragen. We will continue to update this page as we add more features and updates to our Windows Insider builds.  Freuen Sie sich und bereiten Sie sich darauf, diese Updates in Ihre Realität zu mischen.

> [!IMPORTANT]
> Wenn Sie zuvor entweder die Einstellungs- oder die Microsoft Edge-App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, unten neue [AUMIDs für neue Apps im Kioskmodus zu](#use-the-new-settings-and-edge-apps-in-kiosk-modes) lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin die Einstellungs-App in Ihrem Kiosk haben oder die neue Microsoft Edge-App verwenden.

<br>

| Featurename                                              | Kurze Beschreibung                                                                      | Im Build verfügbar |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Neuer Microsoft Edge-Browser](#introducing-the-new-microsoft-edge) | Das neue Chromium-basierte Microsoft Edge ist jetzt für HoloLens 2 verfügbar.                         | 20279.1006 |
| [WebXR und 360 Viewer](#webxr-and-360-viewer)             | Probieren Sie immersive Weberfahrungen und die 360-Videowiedergabe aus                                           | 20289.1000 |
| [Neue Einstellungs-App](#new-settings-app)                     | Die ältere Einstellungs-App wird durch eine aktualisierte Version mit neuen Features und Einstellungen ersetzt. | 20279.1006 |
| [Standardmäßige App-Auswahl](#default-app-picker)                 | Auswählen, welche App für jeden Datei- oder Linktyp gestartet werden soll                                      | 20279.1006 |
| [Office Web App](#office-web-app)                         | Eine Verknüpfung zur Office Web App ist jetzt in "Alle Apps" aufgeführt.                                   | 20279.1006 |
| [Wischen zum Eingeben](#swipe-to-type)                           | Verwenden Sie die Fingerspitze, um Wörter auf der holografischen Tastatur zu "wischen".                        | 20279.1006 |
| [UNTERSTÜTZUNG für externes USB-C-Mikrofon](#usb-c-external-microphone-support) | Verwenden Sie USB-C-Mikrofone für Apps und/oder Remote Assist.| 20279.1006 |
| [Neue AUMIDs für neue Apps im Kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs für neue Einstellungen und Edge-Apps | 20279.1006 |
| [Neue SettingsURIs für Sichtbarkeit von Seiteneinstellungen](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Mehr als 20 neue SettingsURIs für Einstellungen/PageVisibilityList-Richtlinie | 20289.1000 |
| [Verbesserte Übergabe von Fehlern im Kioskmodus](#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Kioskmodus sucht vor dem leeren Startmenü nach dem globalen zugewiesenen Zugriff. | 20279.1006 |
| [Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app) | Festlegen des Fallbackdiagnoseverhaltens in der App "Einstellungen" | 20279.1006 |
| [Teilen von Dingen mit Geräten in der Nähe](#share-things-with-nearby-devices) | Freigeben von Dateien oder URLs von einer HoloLens auf einem PC | 20279.1006 |
| [Problembehandlung für neues Betriebssystemupdate](#new-os-update-troubleshooter) | Neue Problembehandlung in den Einstellungen für Betriebssystemupdates | 20279.1006 |
| [Verbesserungen und Fehlerbehebungen im Update](#improvements-and-fixes-in-the-update) | Zusätzliche Korrekturen im Update. | 20279.1006 |

### Einführung in das neue Microsoft Edge

![Animation des älteren Microsoft Edge-Logos zum neuen Microsoft Edge-Logo](images/new-edge.gif)

Das neue Microsoft Edge [führt das Open -Source-Projekt Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ein, um eine bessere Kompatibilität für Kunden und eine geringere Fragmentierung des Webs für Webentwickler zu gewährleisten.

Mit dieser Insider Preview ist das neue Microsoft Edge zum ersten Mal für HoloLens 2-Kunden verfügbar! Während das neue Microsoft Edge in der Vergangenheit Microsoft Edge auf HoloLens 2 ersetzt, sind beide Browser derzeit für Insider verfügbar. Bitte teilen Sie Feedback und Fehler mit unserem Team über das Feature **"Feedback** senden" im neuen Microsoft Edge oder über den [Feedback-Hub.](hololens-feedback.md)

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
> Aufgrund der Anzahl von Browserrichtlinien, die vom neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie auf HoloLens 2 funktioniert. Wir haben jedoch getestet und bestätigt, dass die neue Microsoft Edge-Entsprechung jeder früheren Microsoft Edge-Richtlinie, die zuvor auf HoloLens 2 unterstützt wurde, wie erwartet funktioniert. Informationen zur neuen Microsoft Edge-Entsprechung jeder älteren Microsoft Edge-Browserrichtlinie, die Sie mit HoloLens 2 verwendet haben, finden Sie unter ["Microsoft Edge Legacy-zu-Microsoft](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Edge-Richtlinienzuordnung".
>
> Es gibt mindestens zwei neue Microsoft Edge-Richtlinien, von der wir wissen, dass *sie nicht* mit HoloLens 2 funktionieren:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### Was Sie von dem neuen Microsoft Edge auf HoloLens 2 erwarten können

Da es sich bei dem neuen Microsoft Edge um eine systemeigene Win32-App mit einer neuen UWP-Adapterebene handelt, die die Ausführung auf Nur-UWP-Geräten wie HoloLens 2 ermöglicht, sind einige Features möglicherweise nicht sofort verfügbar. We'll be supporting new scenarios and features over the coming months, so check this space for up-to-date information.

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
  1. Wählen **Sie HoloLens 2** im Dropdownmenü aus.
  1. Speichern Sie die .msix-Datei im Ordner "Downloads" Ihres PCs (oder in einem anderen Ordner, den Sie leicht finden können).
  1. Verwenden [Sie das Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC, um die heruntergeladene .msix-Datei auf HoloLens 2 zu installieren.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev **** oder Canary als separaten Eintrag in der Liste "Alle Apps" im Startmenü.

> [!NOTE]
> Während dieser Windows-Insider-Vorschau für HoloLens 2 ist die Version von Microsoft Edge auf Ihrem Gerät möglicherweise höher als die version, die in einigen (oder allen) Microsoft Edge-Insider-Kanälen verfügbar ist. Dadurch soll sichergestellt werden, dass neue Features und Fixes, die speziell auf den Webbrowser auf HoloLens 2 zielen, so schnell wie möglich an unsere Windows-Insider übermittelt werden. Kurz nach der öffentlichen Version des nächsten Windows-Updates werden die Microsoft Edge-Insider-Kanal-Builds die Version von Microsoft Edge auf Ihrer HoloLens 2 übertreffen und vor ihnen bleiben.

### WebXR und 360 Viewer

*Hinzugefügt in Windows Insider Build 20289.1000*

Das neue Microsoft Edge bietet Unterstützung für WebXR. Dies ist der neue Standard zum Erstellen immersiver Weberfahrungen (ersetzt WebVR). Viele immersive Weberfahrungen wurden im Hinblick auf VR entworfen (sie ersetzen Ihr Sichtfeld durch eine virtuelle Umgebung), aber diese Erfahrungen werden auch von HoloLens 2 unterstützt. Der WebXR-Standard ermöglicht außerdem erweiterte und mixed Reality-immersive Weberfahrungen, die Ihre physische Umgebung verwenden. Da Entwickler mehr Zeit mit WebXR verbringen, erwarten wir, dass neue erweiterte und mixed Reality-immersive Erfahrungen für HoloLens 2-Kunden verfügbar sind.

Die Erweiterung 360 Viewer baut auf WebXR auf und wird automatisch zusammen mit dem neuen Microsoft Edge auf HoloLens 2 installiert. Mit dieser Weberweiterung können Sie sich in 360-Grad-Videos eintauchen. YouTube bietet die größte Auswahl von 360 Videos, daher empfehlen wir Ihnen, hier zu beginnen.

#### Verwenden von WebXR

1. Navigieren Sie zu einer Website mit WebXR-Unterstützung.
1. Wählen Sie auf der Website die Schaltfläche **"VR** eingeben" aus. Der Speicherort und die visuelle Darstellung dieser Schaltfläche können je nach Website variieren, sie sieht jedoch in etwa so aus:

    ![Beispiel für die Eingabe der SCHALTFLÄCHE "VR"](images/75px-enter-vr.png)

1. Wenn Sie zum ersten Mal versuchen, eine WebXR-Erfahrung in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung, um in eine immersive Ansicht eintauchen zu können. Wählen Sie **"Zulassen" aus.**
1. Verwenden [Sie HoloLens 2-Gesten, um](hololens2-basic-usage.md#the-hand-tracking-frame) die Erfahrung zu bearbeiten.
1. Wenn die Erfahrung nicht über eine Schaltfläche zum Beenden **verfügt,** verwenden Sie die [Startgeste,](hololens2-basic-usage.md#start-gesture) um nach Hause zurückzukehren.

**Empfohlene WebXR-Beispiele**
- 360 Viewer (siehe nächster Abschnitt)
- [XR-Dinosaurier](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### Verwenden von 360 Viewer

1. Navigieren Sie zu einem 360-Grad-Video auf YouTube.
1. Wählen Sie im Videoframe die Mixed Reality-Headset-Schaltfläche aus:

    ![Schaltfläche zum Aktivieren von 360 Viewer](images/enter-360-viewer.jpg)

1. Wenn Sie versuchen, 360 Viewer zum ersten Mal in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung, um in eine immersive Ansicht eintauchen zu können. Wählen Sie **"Zulassen"** aus.
1. [Tippen Sie in die](hololens2-basic-usage.md#select-using-air-tap) Luft, um die Wiedergabesteuerelemente zu starten. Verwenden [Sie Handstrahle und](hololens2-basic-usage.md#select-using-air-tap) Tippen in die Luft, um zu spielen/zu unterbrechen, vorwärts/zurück zu springen, Beschriftungen ein-/auszuschalten oder die Umgebung zu beenden (wodurch die immersive Ansicht beendet wird). Die Wiedergabesteuerelemente werden nach einigen Sekunden Inaktivität ausgeblendet.

#### Bekannte Probleme mit WebXR und 360 Viewer
- In WebXR-Umgebungen können Hologramme verschoben oder gekippt werden, wenn Sie Ihren Kopf neigen oder sich in Ihrer Umgebung bewegen.
- Je nach Komplexität der WebXR-Erfahrung kann die Framerate drop- oder stuttern.
- Handgelenke sind in WebXR noch nicht verfügbar.
- Beim Beenden einer WebXR- oder 360-Viewer-Erfahrung kann es 30 Sekunden oder mehr dauern, bis Hologramme in der Mixed -Reality-Startseite wieder angezeigt werden.
- 360 Videos von anderen Websites als YouTube funktionieren möglicherweise nicht wie erwartet.
- Wenn 360 Videos nicht in die immersive Ansicht gelangen (oder die Mixed Reality-Headset-Schaltfläche nicht angezeigt wird), versuchen Sie, die Seite zu aktualisieren.
- Beschriftungen sind im 360-Viewer auf HoloLens 2 noch nicht sichtbar.
- Durch anhalten eines Videos im 360-Viewer wird das Rendern des Videos beendet (aber durch Auswählen der Wiedergabeschaltfläche wird die Wiedergabe ordnungsgemäß fortgesetzt).
- Die Schaltfläche "Nächstes Video" in 360 Viewer funktioniert derzeit nicht.
- Sie können 2D-Videos in einem immersiven "Theater"-Modus abspielen, die Framerate ist jedoch weniger als 30 fps.

#### Bereitstellen von Feedback zu WebXR und 360 Viewer

Bitte teilen Sie Feedback und Fehler mit unserem Team über das Feature **"Feedback senden"** im neuen Microsoft Edge mit.

### Neue Einstellungs-App

In dieser Version wird eine neue Version der App "Einstellungen" eingeführt. Die neue Einstellungs-App umfasst neue Features und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Power &-Ruhezustand, Netzwerk & Internet, Apps, Konten, Erleichterte Bedienung und vieles mehr.

> [!NOTE]
> Da sich die neue Einstellungs-App von der älteren Einstellungs-App unterscheidet, werden alle Einstellungsfenster, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Startseite der App "Neue Einstellungen"](images/new-settings-app.png)

**Neue Features und Einstellungen**
- Einstellungssuche: Suchen Sie auf der Startseite "Einstellungen" mithilfe von Schlüsselwörtern oder dem Namen der Einstellung nach Einstellungen.
- System > Sound:
  - Ein- und Ausgabeaudiogeräte: Wählen Sie unabhängig Ihre Ein- und Ausgabeaudiogeräte aus (z. B. Audio über Bluetooth-Kopfhörer abhören oder ein USB-C-Mikrofon für die Audioeingabe verwenden). 
    > [!NOTE]
    > Bluetooth werden von HoloLens 2 nicht unterstützt.
  - App-Volume: Passen Sie die Lautstärke jeder App unabhängig an.
- System > Energie &: Wählen Sie aus, wann das Gerät nach einer bestimmten Inaktivität in den Ruhezustand wechseln soll.
- System > Akku: Aktivieren Sie den Stromsparmodus manuell, oder legen Sie einen Akkuschwellenwert ein, an dem der Stromsparmodus automatisch aktiviert wird.
- Geräte > USB: Sie können usb-Verbindungen standardmäßig deaktivieren.
- Netzwerk & Internet:
  - USB-C-Ethernet-Adapter werden jetzt im Netzwerk & angezeigt.
  - Usb-C-Ethernet-Adaptereinstellungen sind jetzt verfügbar, einschließlich der IP-Adresse.
  - Sie können jetzt den Flugzeugmodus auf HoloLens 2 aktivieren.
- Apps: Sie können die Für Datei- und Linktypen verwendeten Standard-Apps zurücksetzen. Weitere Informationen finden Sie unter ["Standardmäßige App-Auswahl".](#default-app-picker)
- Konten > andere Benutzer: Gerätebesitzer können Benutzer hinzufügen, Standardbenutzer auf Gerätebesitzer aktualisieren, Gerätebesitzer auf Standardbenutzer herabstufen und Benutzer entfernen.
- Erleichterte Bedienung: Ändern der Textgröße und einiger visueller Effekte.

**Bekannte Probleme**
- Zuvor platzierte Einstellungsfenster werden entfernt (siehe Hinweis oben).
- Beim Besuch der Seite "Benachrichtigungen" kann die Einstellungs-App abstürzen (wird untersucht).
- Die Ethernetseite wird derzeit nicht angezeigt (wird in Kürze behoben).
- Sie können Ihr Gerät nicht mehr mit der App "Einstellungen" umbenennen (IT-Administratoren können Bereitstellungspakete oder MDM verwenden, um Geräte umzubenennen).
- Der Akkuverbrauch für das neue Microsoft Edge ist aufgrund seiner Art als win32-Desktopanwendung, die von einer UWP-Adapterschicht unterstützt wird, möglicherweise nicht genau (bald wird keine Korrektur erwartet).

### Standardmäßige App-Auswahl

Wenn Sie einen Hyperlink aktivieren oder einen Dateityp mit mehr als einer installierten App öffnen, die dies unterstützt, wird ein neues Fenster geöffnet, in dem Sie aufgefordert werden, auszuwählen, welche installierte App den Datei- oder Linktyp verarbeiten soll. In diesem Fenster können Sie auch auswählen, dass die ausgewählte App die Datei oder den Linktyp "Einmal" oder "Immer" behandeln soll.

![Fenster "App-Auswahl"](images/default-app-picker.png)

Wenn Sie "Immer" auswählen, aber später ändern möchten, welche App eine bestimmte Datei oder einen bestimmten Linktyp behandelt, können Sie ihre gespeicherten Standardwerte in den Einstellungen > **Apps zurücksetzen.** Scrollen Sie zum unteren Rand **** der Seite, und wählen Sie die Schaltfläche "Löschen" unter "Standard-Apps für Dateitypen" und/oder "Standard-Apps für Linktypen" aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardeinstellungen für einzelne Dateitypen nicht zurücksetzen.

### Office Web App

Die Office Web App wurde der Liste "Alle Apps" im Startmenü hinzugefügt. Diese Web App kann auch an die Startseite angeheftet oder deinstalliert werden. Da es sich um eine Web-App handelt, entspricht ihre Funktionalität genau dem, was Sie beim Besuch erleben https://www.office.com würden. Die Office Web -App-Funktionalität ist nur verfügbar, wenn Ihre HoloLens 2 über eine aktive Internetverbindung verfügt.

### Wischen zum Eingeben

Einige Kunden finden es schneller, auf virtuellen Tastaturen "einzugeben", indem sie die Form des Worts swipsen, das sie eingeben möchten, und wir sehen uns diese Funktion für die holografische Tastatur in der Vorschau an. Sie können ein Wort nach dem anderen wischen, indem Sie die Fingerspitze durch die Fläche der holografischen Tastatur übergeben, die Form des Worts wischen und dann die Fingerspitze aus der Fläche der Tastatur ziehen. Sie können nach folgenden Wörtern wischen, ohne die LEERTASTE drücken zu müssen, indem Sie den Finger von der Tastatur zwischen Wörtern entfernen. Sie wissen, dass das Feature funktioniert, wenn eine Wischspur nach der Bewegung des Fingers auf der Tastatur angezeigt wird.

Bitte beachten Sie, dass es schwierig sein kann, diese Funktion zu verwenden und zu mastern, da sie eine holografische Tastatur ist, auf der Sie (im Gegensatz zu einem Mobiltelefondisplay) keinen Widerstand gegen Ihren Finger verkraften. We are evaluating this feature for public release, so your feedback is important; Ob Sie das Feature hilfreich finden oder Feedback abgeben möchten, teilen Sie uns dies bitte über den [Feedback-Hub mit.](hololens-feedback.md)

### UNTERSTÜTZUNG für externes USB-C-Mikrofon

> [!IMPORTANT]
> Wenn Sie ein **USB-Mikrofon anschließen,** wird es nicht automatisch als Eingabegerät festgelegt. Beim Anschließen einer Gruppe von USB-C-Kopfhörern beobachten Benutzer, dass die Audiodaten des Kopfhörers automatisch an die Kopfhörer umgeleitet werden. Das #A0 priorisiert jedoch das interne Mikrofonarray über jedem anderen Eingabegerät. **Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**

Benutzer können externe USB-C-angeschlossene Mikrofone über den Bereich **"Soundeinstellungen"** auswählen. USB-C-Mikrofone können für Anrufe, Aufzeichnungen usw. verwendet werden.

Öffnen Sie die **Einstellungs-App,** und wählen **Sie**  ->  **Systemsound aus.**

![Soundeinstellungen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Um externe Mikrofone mit **Remote Assist**zu verwenden, müssen Benutzer auf den Link "Soundgeräte verwalten" klicken.
>
> Verwenden Sie dann die Dropdownliste, um das externe Mikrofon entweder als **Standard** oder als Communications Default **zu setzen.** Wenn Sie **"Standard"** auswählen, wird das externe Mikrofon überall verwendet.
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

Wenn Sie Apps in [Kiosks](hololens-kiosk.md)hinzufügen, fügt ein IT-Administrator die App häufig zum Kiosk hinzu, verwendet aber die App-Benutzermodell-ID (App User Model ID, AUMID). Da sowohl die Einstellungs- als auch die Microsoft Edge-App als neue Apps gelten und sich von den älteren Apps unterscheiden, müssen Kioske, die AUMIDs für diese Apps verwenden, aktualisiert werden, um die neue AUMID zu verwenden.

Wenn Sie einen Kiosk so ändern, dass er die neuen Apps enthält, empfehlen wir, die neue AUMID zu hinzufügen und die alte zu verlassen. Dies wird einen einfachen Übergang schaffen, wenn Benutzer das Betriebssystem aktualisieren und müssen keine neuen Richtlinien erhalten, um den Kiosk wie beabsichtigt weiter zu verwenden.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Alte Einstellungs-App       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Neue Einstellungs-App       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Alte Microsoft Edge-App | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Neue Microsoft Edge-App | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### Neue SettingsURIs für Sichtbarkeit von Seiteneinstellungen

In [Windows Holographic, Version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) haben wir die Richtlinie ["Einstellungen/PageVisibilityList"](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) hinzugefügt, um die In der App "Einstellungen" angezeigten Seiten einzuschränken. Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungs-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, außer den angegebenen.

Wenn Sie die Sichtbarkeit der Seiteneinstellungen [besuchen,](settings-uri-list.md)finden Sie Anweisungen zur Verwendung dieses CSP und die Liste der URIs, die in früheren Versionen verfügbar waren.

In Windows-Insider-Builds erweitern wir die Liste der verfügbaren Einstellungs-URIs, die von IT-Administratoren verwaltet werden können. Einige dieser URIs sind für neu verfügbare Bereiche innerhalb der neuen Einstellungs-App. Wenn Sie die Einstellungs-/PageVisibilityList-Richtlinie verwenden, überprüfen Sie die folgende Liste, und passen Sie Ihre zulässigen oder blockierten Seiten nach Bedarf an.

> [!NOTE]
> **Veraltet: ms-settings:network-proxy**
>
> Eine Einstellungsseite ist in diesen neueren Builds veraltet. Die alte **Seite & Internetproxy**ist nicht mehr  >  **** als globale Einstellung verfügbar. Die neuen Proxyeinstellungen pro Verbindung finden Sie unter **"Netzwerk-&**  >  **Internet-WLAN-Eigenschaften"** oder "Network  >  **** **& Internet**  >  **Ethernet"-Eigenschaften.**  >  ****

<br>

| Einstellungsseite                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps & Features                               | `ms-settings:appsfeatures`                         |
| Features > Apps & Apps > erweiterte Optionen          | `ms-settings:appsfeatures-app`                     |
| Apps > Offlinekarten                                  | `ms-settings:maps`                                 |
| Apps > Offlinekarten > Karten herunterladen                  | `ms-settings:maps-downloadmaps`                    |
| Geräte > Maus                                      | `ms-settings:mouse`                                |
| Geräte > USB                                        | `ms-settings:usb`                                  |
| Netzwerk & Internet > Flugzeugmodus                   | `ms-settings:network-airplanemode`                 |
| Datenschutzrichtlinien > Allgemein                                    | `ms-settings:privacy-general`                      |
| Datenschutz > Freihandeingabe & Personalisierung             | `ms-settings:privacy-speechtyping`                 |
| Datenschutz > Bewegung                                     | `ms-settings:privacy-motion`                       |
| Rahmen des > A0                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Datenschutz-> Screenshots und Apps                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Akku                                     | `ms-settings:batterysaver`                         |
| System > Akku                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > -App- und Geräteeinstellungen | `ms-settings:apps-volume`                          |
| System > Sound > Verwalten von Soundgeräten              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Uhrzeit & Sprache > Datum & Uhrzeit                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Zeit & Sprache > Sprache                           | `ms-settings:language`                             |
| Zeit & Sprache > Sprache                           | `ms-settings:regionlanguage-languageoptions`       |
| Update & Security > Reset & Recovery               | `ms-settings:reset`                                |

#### Aktualisierte URIs

Die folgenden beiden URIs haben zuvor einen Benutzer nicht direkt zu den angegebenen Seiten weitergeleitet, sondern nur die Hauptaktualisierungsseite blockiert. Die folgenden Elemente wurden aktualisiert, um direkt zu ihren Seiten zu leitet:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern

Wenn ein Gerät in älteren Builds eine Kioskkonfiguration hat, bei der es sich um eine Kombination aus globalem zugewiesenem[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)Zugriff und zugewiesenem Zugriff durch ein AAD-Gruppenmitglied handelt, wird dem Benutzer bei einem Fehler bei der Ermittlung der Mitgliedschaft in einer AAD-Gruppe nichts im Menü "Start" angezeigt.

Ab der Windows-Insider-Version wird die Kioskerfahrung bei Fehlern im Kioskmodus der AAD-Gruppe auf die globale Kioskkonfiguration (sofern vorhanden) zurückfallen.

### Konfigurieren der Fallbackdiagnose über die App "Einstellungen"

In der Einstellungs-App kann ein Benutzer nun das Verhalten der [Fallbackdiagnose konfigurieren.](hololens-diagnostic-logs.md) Navigieren Sie in **** der App "Einstellungen" zur Seite  ->  **"Datenschutzbehandlung",** um diese Einstellung zu konfigurieren.

> [!NOTE]
> Wenn für das Gerät eine MDM-Richtlinie konfiguriert ist, kann der Benutzer dieses Verhalten nicht außer Kraft setzen.  

### Teilen von Dingen mit Geräten in der Nähe

Teilen Sie Dinge mit Geräten in der Nähe von Windows 10, einschließlich PCs und anderen HoloLens 2-Geräten, auf denen HoloLens Insider Builds 20279.1006 und höher ausgeführt werden. Sie können es **** in den gemeinsamen Erfahrungen des Einstellungssystems ausprobieren, um Dateien oder URLs von einer  ->  ****  ->  **** HoloLens auf einem PC zu teilen. Weitere Informationen zum Freigeben von Dingen mit Geräten in der Nähe finden Sie [unter Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Dieses Feature kann über [Connectivity/AllowConnectedDevices verwaltet werden.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### Problembehandlung für neues Betriebssystemupdate

Zusätzlich zu den vorherigen Problembehandlungen in der Einstellungs-App wurde eine neue Problembehandlung mit der neuen Einstellungs-App für Betriebssystemupdates hinzugefügt. Navigieren **** Sie zu  ->  **"Sicherheitsprobleme beim Aktualisieren &amp; **  ->  **von Einstellungen" bei**Windows  ->  **Update,** und wählen Sie **"Start" aus.** Auf diese Weise können Sie Ablaufverfolgungen sammeln und gleichzeitig Ihr Problem mit Betriebssystemupdates zur besseren Problembehandlung mit Ihrer IT oder Ihrem Support nachführen.

### Verbesserungen und Fehlerbehebungen im Update:

- [Die Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics) enthält auch zusätzliche Geräteinformationen für Seriennummer und Betriebssystemversion.






## Start receiving Insider builds

> [!NOTE]
> Wenn Sie kürzlich noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Status zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche "Neustart" unter "Einstellungen/Windows-Insider-Programm" auswählen.
>
> Wir hatten einen Fehler auf dem Back-End, auf dem Sie möglicherweise aufgetreten sind, und dadurch sind Sie wieder auf dem Weg.

On a HoloLens 2 device go to **Settings**  >  **Update & Security**Windows Insider  >  **Program** and select **Get started**. Verknüpfen Sie das Konto, mit dem Sie sich als Windows-Insider registriert haben.

Windows-Insider werden nun zu Kanälen um- Der **Schnelle** Ring wird der **** **Dev Channel,** der langsame Ring wird zum **Betakanal,** und der **Release** Preview Ring wird zum Release **Preview Channel.** So sieht diese Zuordnung aus:

![Erläuterung zu Windows-Insider-Kanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Einführung in Windows-Insider-Kanäle](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-Blogs.

Wählen Sie dann **"Aktive Entwicklung**von Windows" aus, wählen Sie aus, ob **Sie Dev Channel-** oder **Beta-Channel-Builds** erhalten möchten, und lesen Sie die Programmbedingungen.

Wählen **Sie "> Jetzt neu starten" aus,** um den Abschluss zu beenden. Nachdem Ihr Gerät neu gestartet wurde, wechseln Sie zu "Einstellungen **> Update & Sicherheit" > Suchen** Sie nach Updates, um den neuesten Build zu erhalten.

### Updatefehler 0x80070490 Fehlerumgearbeitung
Wenn beim Aktualisieren im Dev- oder 0x80070490 Betakanal ein Updatefehler auftritt, versuchen Sie es mit der folgenden kurzfristigen Problemumgearbeitung. Dazu gehört das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Zurück verschieben des Insider-Kanals.

#### Phase 1 – Release Preview
1.  Einstellungen, Update & Security, Windows-Insider-Programm, **Release Preview Channel auswählen.**
2.  Einstellungen, Update & Security, Windows Update, **Check for updates**. Fahren Sie nach dem Update mit Phase 2 fort.

#### Phase 2 : Dev Channel
1. Einstellungen, Update & Security, Windows-Insider-Programm, Dev **Channel auswählen.**
2. Einstellungen, Update & Security, Windows Update, **Check for updates**.

## FFU-Download- und Flash-Wegbeschreibungen
Zum Testen mit einer ffu mit Test-Flight-Vorlauf müssen Sie ihr Gerät zunächst entsperren, bevor Sie die ffu mit Test-Flight-Signierten flashen.
1. Auf DEM PC:

    1. Laden Sie ffu auf Ihren PC von [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren Sie ARC (Advanced Recovery Companion) aus dem Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Auf HoloLens – Flight Unlock: Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up, reboot device.

1. Flash-FFU – Jetzt können Sie die FFU mit Flight-Signiert mit ARC flashen.

## Bereitstellen von Feedback und Melden von Problemen

Bitte verwenden [Sie die Feedback-Hub-App](hololens-feedback.md) auf Ihrer HoloLens, um Feedback zu geben und Probleme zu melden. Die Verwendung des Feedbackhubs stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Achten Sie darauf, die Eingabeaufforderung zu akzeptieren, in der **** Sie gefragt werden, ob der Feedbackhub auf Ihren Ordner "Dokumente" zugreifen soll (wählen Sie "Ja" aus, wenn Sie dazu aufgefordert werden).

## Hinweis für Entwickler

Sie sind willkommen und möchten Versuchen, Ihre Anwendungen mit Insider-Builds von HoloLens zu entwickeln.  Sehen Sie sich die [Dokumentation für HoloLens-Entwickler an,](https://developer.microsoft.com/windows/mixed-reality/development) um zu beginnen. Diese Anweisungen funktionieren auch mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio, die Sie bereits für die Entwicklung von HoloLens verwenden.

## Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie abmelden, [](hololens-recovery.md) wann Ihre HoloLens einen Produktionsbuild ausgeführt, oder Sie können Ihr Gerät mithilfe des Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic wiederhergestellt.

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die sich nach der manuellen Neuinstallation eines neuen Vorschaubuilds von Insider -Preview-Builds nicht registrieren, einen blauen Bildschirm erhalten würden. Danach müssen sie ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob sie betroffen sind oder nicht, finden Sie unter diesem bekannten [Problem.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

So stellen Sie sicher, dass Ihre HoloLens einen Produktions build ausgeführt:

1. Wechseln Sie **zu Einstellungen > System > Informationen,** und suchen Sie die Buildnummer.

1. [Weitere Informationen finden Sie in den Versionshinweisen zu Produktions-Buildnummern.](hololens-release-notes.md)

So melden Sie Insider Builds ab:

1. On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program,** and select Stop Insider **builds**.

1. Befolgen Sie die Anweisungen, um Ihr Gerät abmelden.
