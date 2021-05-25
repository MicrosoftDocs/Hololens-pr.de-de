---
title: HoloLens 2 Versionshinweise
description: Bleiben Sie mit allen Updates in jedem neuen Release auf dem HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397341"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 Versionshinweise

Um sicherzustellen, dass Sie mit Ihren HoloLens-Geräten produktiv arbeiten, veröffentlichen wir weiterhin Feature-, Fehler- und Sicherheitsupdates. Auf dieser Seite können Sie jeden Monat sehen, was für HoloLens neu ist. Um das neueste HoloLens 2-Update zu erhalten, können Sie entweder nach Updates suchen und manuell aktualisieren oder das vollständige Flashupdate (Full Flash Update, FFU) zum Flashen Ihres Geräts über [Advanced Recovery Companion erhalten.](hololens-recovery.md#clean-reflash-the-device) [](hololens-update-hololens.md#check-for-updates-and-manually-update) Der [Download](https://aka.ms/hololens2download) wird auf dem neuesten Stand gehalten und bietet den neuesten allgemein verfügbaren Build.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, Version 21H1
- Build 20346.1002

Dieses Update enthält Features für zwei Zielgruppen: -Funktionen, die von jedem Benutzer auf einem Gerät verwendet werden können, sowie neue Geräteverwaltungsoptionen, die von IT-Administratoren konfiguriert werden können. In der folgenden Tabelle sind die Features angegeben, die für die einzelnen Zielgruppen relevant sind. Wenn Sie IT-Administrator sind, sehen Sie sich unsere [Checkliste für IT-Administratoren – Update an.](#it-admin---update-checklist)
>[!IMPORTANT]
>Um auf diesen Build zu aktualisieren, müssen HoloLens 2-Geräte derzeit das Update vom Februar 2021 (Build 19041.1136) oder neuer ausführen. Wenn dieses Featureupdate nicht verfügbar ist, aktualisieren Sie zuerst Ihr Gerät, und versuchen Sie es erneut.

>[!NOTE]
>Heute unterstützt Microsoft HoloLens 2 monatliche Wartungsupdates (Fehler- und Sicherheitskorrekturen) für die folgenden Releases:
>- Windows Holographic, Version 20H2 (Build 19041.1128+)
>- Windows Holographic, Version 2004 (Build 19041.1103+)
>- Windows Holographic, Version 1903 (Build 18362+) 
>
> Mit der Einführung von Windows Holographic Version 21H1 werden monatliche Wartungsupdates für **Windows Holographic Version 1903 eingestellt.** Dies ermöglicht es uns, uns auf neuere Releases zu konzentrieren und weiterhin wertvolle Verbesserungen zu erzielen. 


| Funktionsname                                              | Kurze Beschreibung                                                                      | Zielgruppe | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Neue Microsoft Edge](#introducing-the-new-microsoft-edge)  | Die neue Chromium-basierte Microsoft Edge ist jetzt für HoloLens 2 verfügbar. | Endbenutzer | 
[WebXR und 360 Viewer](#webxr-and-360-viewer) | Probieren Sie immersive Weberfahrungen und die Wiedergabe von 360 Videos aus. | Endbenutzer | 
[Neue Einstellungs-App](#new-settings-app) | Die Legacy-Einstellungs-App wird durch eine aktualisierte Version mit neuen Features und Einstellungen ersetzt. | Endbenutzer |
[Farbkalibrierung anzeigen](#display-color-calibration) | Wählen Sie ein alternatives Farbprofil für Ihre HoloLens 2 Anzeigen aus. | Endbenutzer |
[Standard-App-Auswahl](#default-app-picker) | Wählen Sie aus, welche App für die einzelnen Datei- oder Linktypen gestartet werden soll. | Endbenutzer |
[Volumesteuerung pro App](#per-app-volume-control) | Steuern Sie das Volume auf App-Ebene unabhängig vom Systemvolume. | Endbenutzer |
[Installieren von Web-Apps](#install-web-apps) | Installieren Sie Web-Apps auf HoloLens 2, z. B. Microsoft Office, mit dem neuen Microsoft Edge Browser. | Endbenutzer |
[Wischen zum Typ](#swipe-to-type) | Verwenden Sie die Fingerspitze, um Wörter auf der holografischen Tastatur zu "wischen". | Endbenutzer |
[Power menu from Start](#power-menu-from-start) | Starten Sie im Startmenü das HoloLens-Gerät neu, und fahren Sie es herunter. | Endbenutzer |
[Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind](#multiple-users-listed-on-sign-in-screen) | Zeigen Sie mehrere Benutzerkonten auf dem Anmeldebildschirm an. | Endbenutzer |
[Unterstützung externer USB-C-Mikrofone](#usb-c-external-microphone-support) | Verwenden Sie USB-C-Mikrofone für Apps und/oder Remote Assist. | Endbenutzer |
[Automatische Anmeldung von Besucher für Kioske](#visitor-auto-logon-for-kiosks) | Aktiviert die automatische Anmeldung bei Besucherkonten, die für Kioskmodi verwendet werden sollen. | IT-Administrator |
[Neue AUMIDs für neue Apps im Kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs für neue Einstellungen und Edge-Apps. | IT-Administrator |
[Verbesserte Übergabe von Fehlern im Kioskmodus](#kiosk-mode-behavior-changes-for-handling-of-failures) | Im Kioskmodus wird vor dem leeren Startmenü nach Global Assigned Access (Globaler zugewiesener Zugriff) sucht. | IT-Administrator |
[Neue EinstellungenURIs für Sichtbarkeit von Seiteneinstellungen](#new-settings-uris-for-page-settings-visibility) | Über 20 neue EinstellungenURIs für Einstellungen/PageVisibilityList-Richtlinie. | IT-Administrator |
[Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app) | Festlegen des Fallbackdiagnoseverhaltens in der Einstellungs-App. | IT-Administrator |
[Freigeben von Geräten in der Nähe](#share-things-with-nearby-devices) | Freigeben von Dateien oder URLs von einer HoloLens für einen PC. | Alle |
[Neue Diagnoseverfolgungen für das Betriebssystem](#new-os-diagnostic-traces) | Neue Problembehandlung unter Einstellungen für Betriebssystemupdates. | IT-Administrator |
[Übermittlungsoptimierung Preview](#delivery-optimization-preview) | Reduzieren Sie den Bandbreitenverbrauch für Downloads von mehreren HoloLens-Geräten. | IT-Administrator |

Sehen Sie sich die zugehörigen Versionshinweise an:

- [Besuchen Sie das HoloLens-Emulatorarchiv.](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365-Leitfäden](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Einführung in die neue Microsoft Edge

![Animation des Legacy-Microsoft Edge-Logos zu einem neuen Microsoft Edge-Logo](images/new-edge.gif)

Die neue Microsoft Edge [übernimmt das Chromium-Open-Source-Projekt,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) um eine bessere Kompatibilität für Kunden und eine geringere Fragmentierung des Webs für Webentwickler zu schaffen.

> [!IMPORTANT]
> Diese neue Microsoft Edge ersetzt automatisch ältere Microsoft Edge, die in neuen Releases [nicht mehr unterstützt](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) werden.

![Screenshot der neuen Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Starten des neuen Microsoft Edge

Der neue Microsoft Edge ![Symbol für neue Microsoft Edge](images/new_edge_logo.png) (dargestellt durch ein blaues und grünes Wirlsymbol) wird an die Startmenü angeheftet und wird automatisch gestartet, wenn Sie einen Weblink aktivieren.

> [!NOTE]
> Wenn Sie die neue Microsoft Edge zum ersten Mal auf HoloLens 2 starten, werden Ihre Einstellungen und Daten aus legacy-Microsoft Edge importiert. Wenn Sie nach dem Start des neuen Microsoft Edge weiterhin Legacy-Microsoft Edge verwenden, werden diese neuen Daten nicht von Legacy-Microsoft Edge mit dem neuen Microsoft Edge synchronisiert.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurieren von Richtlinieneinstellungen für die neue Microsoft Edge

Die neue Microsoft Edge bietet IT-Administratoren einen viel umfassenderen Satz von Browserrichtlinien auf HoloLens 2 als bisher mit Legacy-Microsoft Edge verfügbar waren.

Hier finden Sie einige hilfreiche Ressourcen, um mehr über das Verwalten von Richtlinieneinstellungen für die neue Microsoft Edge zu erfahren:

- [Konfigurieren Microsoft Edge Richtlinieneinstellungen mit Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Vorgängerversion von Microsoft Edge zum Microsoft Edge der Richtlinienzuordnung](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Richtlinienzuordnung von Google Chrome zu Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Vollständige [dokumentation zu Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Aufgrund des Umfangs von Browserrichtlinien, die vom neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie auf HoloLens 2 funktioniert. Wir haben jedoch getestet und bestätigt, dass die neue Microsoft Edge Entsprechung jeder Legacyrichtlinie Microsoft Edge, die zuvor für HoloLens 2 unterstützt wurde, wie erwartet funktioniert. Unter [Vorgängerversion von Microsoft Edge Microsoft Edge Richtlinienzuordnung](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) finden Sie die neue Microsoft Edge Entsprechung jeder Legacy-Microsoft Edge Browserrichtlinie, die Sie mit HoloLens 2 verwendet haben.
>
> Es gibt mindestens zwei neue Microsoft Edge, von denen wir wissen, *dass sie nicht* mit den HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Was Sie von der neuen Microsoft Edge auf HoloLens 2

Da die neue Microsoft Edge eine native Win32-App mit einer neuen UWP-Adapterebene ist, die die Ausführung auf nur UWP-Geräten wie HoloLens 2 ermöglicht, sind einige Features möglicherweise nicht sofort verfügbar. Wir werden in den kommenden Monaten neue Szenarien und Features unterstützen. In diesem Bereich finden Sie aktuelle Informationen.

**Szenarien und Features, die voraussichtlich funktionieren:**
- Erste Ausführung, Anmeldung beim Profil und Synchronisierung
- Websites sollten wie erwartet gerendert werden und sich wie erwartet verhalten
- Die meisten Browserfunktionen (Favoriten, Verlauf usw.) sollten erwartungsgemäß funktionieren.
- Dunkler Modus
- Installieren von Web-Apps auf dem Gerät
- Installieren von Erweiterungen (bitte teilen Sie uns mit, wenn Sie Erweiterungen verwenden, die nicht ordnungsgemäß auf dem HoloLens 2)
- Anzeigen und Markieren einer PDF-Datei
- Raumklang aus einem einzelnen Browserfenster
- Automatische und manuelle Aktualisierung des Browsers
- Speichern einer PDF-Datei über das Menü Drucken (mit der Option "In PDF speichern")
- WebXR- und 360 Viewer-Erweiterung
- Inhaltswiederherstellung zum Korrigieren des Fensters beim Durchsuchen mehrerer Fenster in Ihrer Umgebung

**Szenarien und Features, die nicht funktionieren werden:**
- Raumklang aus mehreren Fenstern mit gleichzeitigen Audiostreams
- "See it, say it"
- Drucken

**Bekannte Probleme im Browser:**

- Die Bildschirmlupevorschau in der holografischen Tastatur wurde für die neue Microsoft Edge deaktiviert. Wir hoffen, dieses Feature in einem zukünftigen Update wieder zu ermöglichen, sobald die Vergrößerung ordnungsgemäß funktioniert.
- Audio wird möglicherweise im falschen Browserfenster wiedergegeben, wenn ein anderes Browserfenster geöffnet und aktiv ist. Sie können dieses Problem umgehen, indem Sie das andere aktive Fenster schließen, das keine Audiowiedergabe sein soll.
- Beim Wiedergeben von Audio aus einem Browserfenster im [Modus "Follow me"](hololens2-basic-usage.md#follow-me-stop-following)(Mir folgen) wird die Audiowiedergabe fortgesetzt, wenn Sie den Modus "Follow me" (Mir folgen) deaktivieren. Sie können dieses Problem umgehen, indem Sie die Audiowiedergabe beenden, bevor Sie den Modus "Follow me" deaktivieren, oder indem Sie das Fenster mit **der** X-Schaltfläche schließen.
- Die Interaktion mit aktiven Microsoft Edge Fenstern kann dazu führen, dass andere 2D-App-Fenster unerwartet inaktiv werden. Sie können diese Fenster reaktivieren, indem Sie erneut mit ihnen interagieren.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-Kanäle

Das Microsoft Edge-Team stellt der Edge Insider-Community drei Vorschaukanäle zur Verfügung: Beta, Dev und Canary. Beim Installieren eines Vorschaukanals wird die veröffentlichte Version von Microsoft Edge nicht auf Ihrem HoloLens 2 deinstalliert, und Sie können mehrere gleichzeitig installieren. 

Besuchen Sie die [Microsoft Edge Insider-Homepage,](https://www.microsoftedgeinsider.com) um mehr über die Edge Insider-Community zu erfahren. Weitere Informationen zu den verschiedenen Edge-Insider-Kanälen und den ersten Schritte finden Sie auf der [Edge Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)

Es gibt mehrere Methoden zum Installieren von Microsoft Edge Insider-Kanälen für HoloLens 2:

**Direkte Installation auf dem Gerät (derzeit nur für nicht verwaltete Geräte verfügbar)**
  1. Besuchen Sie auf Ihrer HoloLens 2 die [Edge Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie die Schaltfläche Download for HoloLens 2 (Herunterladen **für HoloLens 2)** für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Starten Sie die heruntergeladene MSIX-Datei aus der Edge-Downloadwarteschlange oder aus dem Ordner "Downloads" Ihres Geräts (mithilfe des Datei-Explorers).
  1. [Das App-Installationsprogramm](app-deploy-app-installer.md) wird gestartet.
  1. Wählen Sie die Schaltfläche **Installieren** aus.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der Alle Apps **liste** der Startmenü.

**Installation über PC mit Windows-Geräteportal (erfordert [die Aktivierung des](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) Entwicklermodus auf HoloLens 2)**
  1. Besuchen Sie auf Ihrem PC die [Edge Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie **die Dropdownpfeil-Schaltfläche** neben der Schaltfläche "Download for Windows 10" für den Edge Insider-Kanal aus, den Sie installieren möchten.
  1. Wählen **HoloLens 2** im Dropdownmenü die Option aus.
  1. Speichern Sie die MSIX-Datei im Ordner "Downloads" Ihres PCs (oder in einem anderen Ordner, den Sie leicht finden können).
  1. Verwenden [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC, um die heruntergeladene MSIX-Datei auf dem HoloLens 2.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der Alle Apps **liste** der Startmenü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Verwenden von WDAC zum Blockieren neuer Microsoft Edge

It-Administratoren, die ihre [WDAC-Richtlinie](windows-defender-application-control-wdac.md) aktualisieren möchten, um die neue Microsoft Edge-App zu blockieren, müssen Ihrer Richtlinie Folgendes hinzufügen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Verwalten von Endpunkten für die Microsoft Edge

In einigen Umgebungen müssen möglicherweise Netzwerkeinschränkungen berücksichtigt werden. Aktivieren Sie diese Microsoft-Endpunkte, um ein reibungsloses Erlebnis mit dem neuen [Edge zu gewährleisten.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Erfahren Sie mehr über die derzeit [verfügbaren Endpunkte für HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Installieren von Web-Apps
 > [!Note]
>Ab [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)ist die Office-Web-App nicht mehr vorinstalliert.

Sie können die neue Edge-Version verwenden, um Web-Apps zusammen mit Microsoft Store zu installieren. Sie können z. B. die Microsoft Office-Web-App installieren, um dateien, die auf SharePoint oder OneDrive gehostet werden, zu anzeigen und zu bearbeiten. Um die Office-Web-App zu installieren, besuchen Sie die Schaltfläche App verfügbar oder https://www.office.com **Office** installieren in der Adressleiste, und wählen Sie sie aus.  Wählen Sie **Installieren aus,** um dies zu bestätigen.

> [!IMPORTANT]
> Office-Web-App-Funktionen sind nur verfügbar, wenn Ihre HoloLens 2 über eine aktive Internetverbindung verfügt.

### <a name="webxr-and-360-viewer"></a>WebXR und 360 Viewer

Die neue Microsoft Edge enthält Unterstützung für WebXR. Dies ist der neue Standard zum Erstellen immersiver Weberfahrungen (ersetzen von WebVR). Viele immersive Weberfahrungen wurden unter Berücksichtigung von VR entworfen (sie ersetzen Ihr Sichtfeld durch eine virtuelle Umgebung), aber diese Erfahrungen werden auch von HoloLens 2 unterstützt. Der WebXR-Standard ermöglicht auch erweiterte und immersive Mixed Reality-Weberfahrungen, die Ihre physische Umgebung verwenden. Da Entwickler mehr Zeit mit WebXR verbringen, erwarten wir, dass neue immersive Augmented- und Mixed Reality-Erfahrungen für HoloLens 2 Kunden eingehen werden.

Die Erweiterung 360 Viewer basiert auf WebXR und wird automatisch zusammen mit dem neuen Microsoft Edge auf HoloLens 2 installiert. Diese Weberweiterung bietet Ihnen die Möglichkeit, sich selbst in 360-Grad-Videos zu präsentieren. YouTube bietet die größte Auswahl von 360 Videos, daher empfehlen wir Ihnen, dort zu beginnen.

#### <a name="how-to-use-webxr"></a>Verwenden von WebXR

1. Navigieren Sie zu einer Website mit WebXR-Unterstützung.
1. Wählen Sie auf der Website die Schaltfläche **VR eingeben** aus. Der Speicherort und die visuelle Darstellung dieser Schaltfläche können je nach Website variieren, aber sie kann in etwa wie die folgende aussehen:

    ![Beispiel für die Eingabe einer VR-Schaltfläche](images/75px-enter-vr.png)

1. Wenn Sie zum ersten Mal versuchen, eine WebXR-Benutzeroberfläche in einer bestimmten Domäne zu starten, fordert der Browser um Zustimmung für die Eingabe einer immersiven Ansicht auf. Wählen **Sie Zulassen** aus.
1. Verwenden Sie [HoloLens 2 Gesten,](hololens2-basic-usage.md#the-hand-tracking-frame) um die Benutzeroberfläche zu bearbeiten.
1. Wenn die Benutzeroberfläche nicht über die Schaltfläche **Beenden** verfügt, verwenden Sie die [Startgeste,](hololens2-basic-usage.md#start-gesture) um nach Hause zurückzukehren.

**Empfohlene WebXR-Beispiele**
- 360 Viewer (siehe nächster Abschnitt)
- [XR-Aussteller](https://www.xrdinosaurs.com/)
- [Barfan Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Verwenden von 360 Viewer

1. Navigieren Sie zu einem 360-Grad-Video auf YouTube.
1. Wählen Sie im Videoframe die Mixed Reality-Headset-Schaltfläche aus:

    ![Schaltfläche zum Aktivieren von 360 Viewer](images/enter-360-viewer.jpg)

1. Wenn Sie versuchen, 360 Viewer zum ersten Mal in einer bestimmten Domäne zu starten, wird der Browser um Zustimmung für die Eingabe einer immersiven Ansicht bitten. Wählen Sie **Zulassen aus.**
1. [Tippen Sie in](hololens2-basic-usage.md#select-using-air-tap) die Luft, um die Wiedergabesteuerelemente zu starten. Verwenden [Sie Handlichtlichter](hololens2-basic-usage.md#select-using-air-tap) und Tippen in die Luft, um zu spielen/anzuhalten, vorwärts/zurück zu springen, Untertitel zu aktivieren/deaktivieren oder die Erfahrung zu beenden (wodurch die immersive Ansicht beendet wird). Die Wiedergabesteuerelemente werden nach einigen Sekunden Inaktivität nicht mehr unterstützt.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Bekannte Probleme mit WebXR und 360 Viewer
- Je nach Komplexität der WebXR-Erfahrung kann die Framerate ab- oder versttern.
- Die Unterstützung für artikulierte Handgelenke in WebXR ist standardmäßig nicht aktiviert. Entwickler können die Unterstützung über `edge://flags` aktivieren, indem sie "WebXR Hand Input" aktivieren.
- 360 Videos von anderen Websites als YouTube funktionieren möglicherweise nicht wie erwartet.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Bereitstellen von Feedback zu WebXR und 360 Viewer

Teilen Sie feedback und bugs mit unserem Team über das **Feature Feedback** senden in der neuen Microsoft Edge.

### <a name="new-settings-app"></a>Neue Einstellungs-App

Mit diesem Release führen wir eine neue Version der Einstellungs-App ein. Die neue Einstellungs-App enthält neue Features und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Power & Standbymodus, Netzwerk & Internet, Apps, Konten, Erleichterte Bedienung und mehr.

> [!NOTE]
> Da sich die neue Einstellungs-App von der älteren Einstellungs-App unterscheidet, werden alle Einstellungenfenster, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Startseite der neuen App "Einstellungen"](images/new-settings-app.png)

**Neue Features und Einstellungen**
- Einstellungssuche: Suchen Sie auf der Startseite einstellungen nach Einstellungen, indem Sie Schlüsselwörter oder den Namen der Einstellung verwenden.
- System > Sound:
  - Eingabe- und Ausgabeaudiogeräte: Wählen Sie unabhängig Ihre Eingabe- und Ausgabeaudiogeräte aus (z. B. Audio über Bluetooth-Mikrofone lauschen oder ein USB-C-Mikrofon für die Audioeingabe verwenden).
    > [!NOTE]
    > Bluetooth-Mikrofone werden von HoloLens 2 nicht unterstützt.
  - App-Volume: Passen Sie das Volumen der einzelnen Apps unabhängig an. Weitere Informationen finden Sie [unter Volumesteuerelement pro App.](#per-app-volume-control)
- System > Power & Standbymodus: Wählen Sie aus, wann das Gerät nach einer Bestimmten Inaktivität in den Energiesparmodus versetzt werden soll.
- System > Akku: Aktivieren Sie manuell Stromsparmodus Modus, oder legen Sie einen Akkuschwellenwert fest, an dem Stromsparmodus Modus automatisch eingeschaltet wird.
- Geräte > USB: USB-Verbindungen können standardmäßig deaktiviert werden.
- Netzwerk & Internet:
  - USB-C-Ethernet-Adapter werden jetzt in Network & Internet angezeigt.
  - Usb-C Ethernet-Adaptereinstellungen sind jetzt verfügbar, einschließlich der IP-Adresse.
  - Sie können jetzt den Flugzeugmodus auf HoloLens 2 aktivieren.
- Apps: Sie können die Standard-Apps zurücksetzen, die für Datei- und Linktypen verwendet werden. Weitere Informationen finden Sie unter [Standard-App-Auswahl.](#default-app-picker)
- Konten > Andere Benutzer: Gerätebesitzer können Benutzer hinzufügen, Standardbenutzer auf Gerätebesitzer aktualisieren, Gerätebesitzer auf Standardbenutzer herabstufen und Benutzer entfernen.
- Erleichterte Bedienung: Ändern Sie die Textgröße und einige visuelle Effekte.

**Bekannte Probleme**
- Zuvor platzierte Einstellungsfenster werden entfernt (siehe Hinweis oben).
- Sie können Ihr Gerät nicht mehr mit der App Einstellungen umbenennen. IT-Administratoren können Geräte mithilfe der Vorlage [Windows Autopilot für HoloLens 2-Gerätenamen](https://docs.microsoft.com/hololens/hololens2-autopilot) oder des Knotens MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName umbenennen.
- Auf der Ethernet-Seite wird jederzeit ein virtuelles Ethernet-Gerät ("UsbNcm") angezeigt.
- Der Akkuverbrauch für das neue Microsoft Edge ist möglicherweise nicht genau, da es sich um eine Win32-Desktopanwendung mit Unterstützung durch eine UWP-Adapterebene (in Kürze keine Lösung) gibt.

#### <a name="display-color-calibration"></a>Anzeigen der Farb kalibrierung



Mit dieser neuen Einstellung können Sie ein alternatives Farbprofil für Ihre HoloLens 2 auswählen. Dies kann dazu beitragen, dass Farben genauer angezeigt werden, insbesondere bei niedrigeren Helligkeitsstufen der Anzeige. Die Kalibrierung der Anzeigefarbe finden Sie in der App Einstellungen auf der Seite System > Kalibrierung.

> [!NOTE]
> Da diese Einstellung ein neues Farbprofil in Ihrer Anzeigefirmware speichert, handelt es sich um eine Geräteeinstellung (und nicht für jedes Benutzerkonto eindeutig).

##### <a name="how-to-use-display-color-calibration"></a>Verwenden der Kalibrierung von Anzeigefarben

1. Starten Sie die **App Einstellungen,** und navigieren Sie zu **System > Kalibrierung.**
1. Wählen **Sie unter Farb kalibrierung anzeigen** die Schaltfläche Farb **kalibrierung der Anzeige** ausführen aus.
1. Die Kalibrierung der Anzeigefarbe wird gestartet, und Sie werden dazu ermutigen, sicherzustellen, dass sich Ihr Visor an der richtigen Position befindet.
1. Nachdem Sie die Anweisungsdialogfelder geöffnet haben, wird die Anzeige automatisch auf eine Helligkeit von 30 % abgeblendet.
    > [!TIP]
    > Wenn Sie Probleme haben, die abgeblendete Szene in Ihrer Umgebung zu sehen, können Sie die Helligkeitsstufe von HoloLens 2 mithilfe der Helligkeitsschaltflächen auf der linken Seite des Geräts manuell anpassen.
1. Wählen Sie die Schaltflächen 1 bis 6 aus, um jedes Farbprofil sofort auszuprobieren, und suchen Sie eins, das für Ihre Augen am besten aussieht (dies bedeutet in der Regel das Profil, das der Szene hilft, am neutralsten zu erscheinen, und das Graustufenmuster und die Skintons sehen wie erwartet aus.)

    ![Anzeigen der Farb kalibrierungsszene](images/color-cal-ui.png)
    
1. Wenn Sie mit dem ausgewählten Profil zufrieden sind, wählen Sie die Schaltfläche **Save & Exit (Speichern & Beenden)** aus.
1. Wenn Sie keine Änderungen vornehmen möchten, wählen Sie die Schaltfläche **Abbrechen & Beenden** aus, und Ihre Änderungen werden zurückgesetzt.

> [!TIP]
> Im Folgenden finden Sie einige hilfreiche Tipps, die Sie bei der Verwendung der Einstellung für die Kalibrierung der Anzeigefarbe beachten sollten:
> - Sie können die Farbkalibrierung der Anzeige unter Einstellungen nach Bedarf erneut ausführen.
> - Wenn jemand auf dem Gerät zuvor die Einstellung zum Ändern von Farbprofilen verwendet hat, wird das Datum/die Uhrzeit der letzten Änderung auf der Seite Einstellungen angezeigt.
> - Wenn Sie die Farbkalibrierung der Anzeige erneut ausführen, wird das zuvor gespeicherte Farbprofil hervorgehoben, und Profil 0 wird nicht angezeigt (da Profil 0 das ursprüngliche Farbprofil der Anzeige darstellt).
> - Wenn Sie zum ursprünglichen Farbprofil der Anzeige kehren möchten, können Sie dies auf der Seite Einstellungen durchführen (siehe [Zurücksetzen des Farbprofils).](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Zurücksetzen des Farbprofils 

Wenn Sie nicht mit dem benutzerdefinierten Farbprofil zufrieden sind, das in Ihrem HoloLens 2 gespeichert ist, können Sie das ursprüngliche Farbprofil des Geräts wiederherstellen:
1. Starten Sie die **App Einstellungen,** und navigieren Sie zu **System > Calibration**.
1. Wählen Sie unter **Farbkalibrierung anzeigen** die Schaltfläche **Auf Standardfarbprofil zurücksetzen** aus.
1. Wenn das Dialogfeld geöffnet wird, wählen Sie **Neu starten** aus, wenn Sie bereit sind, HoloLens 2 neu zu starten und Ihre Änderungen zu übernehmen.

#### <a name="top-display-color-calibration-known-issues"></a>Bekannte Probleme bei der Farbkalibrierung der obersten Anzeige

- Auf der Seite Einstellungen ist die Statuszeichenfolge, die Anzeigt, wann das Farbprofil zuletzt geändert wurde, veraltet, bis Sie diese Seite der Einstellungen erneut laden.
    - Problemumgehung: Wählen Sie eine andere Seite Einstellungen aus, und wählen Sie dann die Seite Kalibrierung erneut aus.

#### <a name="default-app-picker"></a>Standard-App-Auswahl

Wenn Sie einen Link aktivieren oder einen Dateityp mit mehreren installierten Apps öffnen, die dies unterstützen, wird ein neues Fenster geöffnet, in dem Sie aufgefordert werden, auszuwählen, welche installierte App die Datei oder den Linktyp verarbeiten soll. In diesem Fenster können Sie auch festlegen, dass die ausgewählte App die Datei oder den Linktyp "Once" oder "Always" verarbeitet.

Wenn Sie "Immer" auswählen, aber später ändern möchten, welche App eine bestimmte Datei oder einen bestimmten Linktyp verarbeitet, können Sie Ihre gespeicherten Standardwerte unter Einstellungen > **Apps zurücksetzen.** Scrollen Sie nach unten auf  der Seite, und wählen Sie unter "Standard-Apps für Dateitypen" und/oder "Standard-Apps für Linktypen" die Schaltfläche Löschen aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardeinstellungen einzelner Dateitypen nicht zurücksetzen.

#### <a name="per-app-volume-control"></a>Volumensteuerung pro App

In diesem Windows-Build können Benutzer nun die Volumeebene jeder App manuell anpassen. Dies ermöglicht es Benutzern, sich besser auf die Apps zu konzentrieren, die sie benötigen, oder besser zu hören, wenn sie mehrere Apps verwenden. Beispielsweise muss das Volumen einer App beim Aufrufen einer anderen Person zur Remoteunterstützung in einer anderen App heruntergefahren werden.

Navigieren Sie zum Festlegen der Lautstärke einer einzelnen App zu Systemsoundeinstellungen, und wählen Sie unter Erweiterte Soundoptionen die Option  ->    ->   **App-Lautstärke und Geräteeinstellungen aus.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Wischen zum Eingeben

Einige Kunden finden es schneller, auf virtuellen Tastaturen zu "tippen", indem sie die Form des Worts wischen, das sie eingeben möchten, und wir zeigen diese Funktion für die holografische Tastatur in der Vorschau an. Sie können ein Wort nach dem anderen wischen, indem Sie die Fingerspitze durch die Ebene der holografischen Tastatur übergeben, die Form des Worts wischen und dann die Fingerspitze von der Tastaturebene abziehen. Sie können Nach-oben-Wörter wischen, ohne die Abstandsleiste drücken zu müssen, indem Sie den Finger von der Tastatur zwischen Wörtern entfernen. Sie werden wissen, dass das Feature funktioniert, wenn Sie einen Wischpfad sehen, der der Bewegung Des Fingers auf der Tastatur folgt.

Beachten Sie, dass dieses Feature aufgrund der Natur einer holografischen Tastatur, bei der Sie keinen Widerstand gegen Ihren Finger haben (im Gegensatz zu einer Mobiltelefonanzeige), schwierig zu verwenden und zu mastern sein kann. 

### <a name="power-menu-from-start"></a>Menü "Energie" über "Start"

Ein neues Menü, mit dem sich der Benutzer abmelden, herunterfahren und das Gerät neu starten kann. Ein Indikator im HoloLens-Startbildschirm, der zeigt, wann ein Systemupdate verfügbar ist.

#### <a name="how-to-use"></a>Verwendung

1. Öffnen Sie die HoloLens-Startbildschirm, indem Sie die [Start-Geste](hololens2-basic-usage.md#start-gesture) verwenden oder "Gehe zu Start" sagen.

2. Beachten Sie das Auslassungszeichen (...) neben dem Benutzerprofilbild:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Wählen Sie das Benutzerprofilbild mit Ihren Händen oder dem Sprachbefehl "Power" aus.

4. Es wird ein Menü mit den Optionen Abmelden, Neustarten oder Herunterfahren des Geräts angezeigt:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Wählen Sie die Menüoptionen zum Abmelden, Neustarten oder Herunterfahren Ihrer HoloLens aus. Die Option Abmelden ist möglicherweise nicht verfügbar, wenn das Gerät für ein [einzelnes Microsoft-Konto (MSA) oder lokales Konto](hololens-identity.md)eingerichtet ist.

6. Schließen Sie das Menü, indem Sie eine andere Stelle berühren oder die Startmenü mit der Startgeste schließen.

#### <a name="update-indicator"></a>Updateindikator

Wenn ein Update verfügbar ist, wird das Symbol mit den Auslassungszeichen angezeigt, um anzugeben, dass das Update bei einem Neustart installiert wird. Die Menüoptionen ändern sich ebenfalls, um das Vorhandensein des Updates widerzuspiegeln.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind

Zuvor wurden auf dem Anmeldebildschirm nur der zuletzt angemeldete Benutzer sowie ein Einstiegspunkt "Anderer Benutzer" angezeigt. Wir haben Kundenfeedback erhalten, dass dies nicht ausreicht, wenn sich mehrere Benutzer am Gerät angemeldet haben. Sie mussten weiterhin ihren Benutzernamen usw. erneut eingeben.

In diesem Windows-Build eingeführt: Bei Auswahl von **Anderer Benutzer,** der sich rechts neben dem PIN-Eingabefeld befindet, zeigt der Anmeldebildschirm mehrere Benutzer an, die sich zuvor beim Gerät angemeldet haben. Dadurch können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Windows Hello Anmeldeinformationen anmelden. Ein neuer Benutzer kann dem Gerät auch auf dieser Seite Andere Benutzer über die Schaltfläche **Konto hinzufügen** hinzugefügt werden.

Im Menü Andere Benutzer zeigt die Schaltfläche Andere Benutzer den letzten Benutzer an, der sich am Gerät angemeldet hat. Wählen Sie diese Schaltfläche aus, um zum Anmeldebildschirm für diesen Benutzer zurückzukehren.

![Standardeinstellung des Anmeldebildschirms](./images/multiusers1.jpg)

<br>

![Anmeldebildschirm für andere Benutzer](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Unterstützung externer USB-C-Mikrofone

> [!IMPORTANT]
> Wenn Sie ein **USB-Mikrofon anschließen, wird** es nicht automatisch als Eingabegerät festgelegt. Beim Einstecken einer Reihe von USB-C-Anschlüssen werden Benutzer feststellen, dass die Audiodaten des Geräts automatisch an die Geräte umgeleitet werden, aber das HoloLens-Betriebssystem priorisiert das interne Mikrofonarray vor jedem anderen Eingabegerät. **Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**

Benutzer können externe Mikrofone mit USB-C-Verbindung über den **Bereich Soundeinstellungen** auswählen. USB-C-Mikrofone können zum Aufrufen, Aufzeichnen usw. verwendet werden.

Öffnen Sie die **App Einstellungen,** und wählen **Sie System sound**  >  **aus.**

![Soundeinstellungen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Um externe Mikrofone mit **Remote Assist** verwenden zu können, müssen Benutzer auf den Link "Soundgeräte verwalten" klicken.
>
> Verwenden Sie dann die Dropdownliste, um das externe Mikrofon entweder auf **Standard oder** Kommunikations **default (Kommunikationseinstellung) zu setzen.** Die Auswahl **von Standard** bedeutet, dass das externe Mikrofon überall verwendet wird.
>
> Die Auswahl **von Kommunikations standard** bedeutet, dass das externe Mikrofon in Remote Assist und anderen Kommunikations-Apps verwendet wird, aber das HoloLens-Mikrofonarray kann weiterhin für andere Aufgaben verwendet werden.

![Verwalten von Soundgeräten](images/usbc-mic-2.png)

<br>

![Festlegen der Mikrofon-Standardeinstellung](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Wie sieht es mit der Bluetooth-Mikrofonunterstützung aus?

Leider werden Bluetooth-Mikrofone auf dem Gerät derzeit HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Problembehandlung bei USB-C-Mikrofonen

Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als Mikrofon als auch als *Lautsprecher* melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone an HoloLens anschließen, kann der Sound verloren gehen. Glücklicherweise gibt es eine einfache Lösung.  

Legen Sie unter **Systemsound** für Einstellungen  ->    ->  die integrierten Lautsprecher **(Analog Feature Audio Driver)** explizit als **Standardgerät** fest. HoloLens sollte sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später erneut verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatische Besucheranmeldung für Kioske

Mit diesem neuen Feature kann die automatische Anmeldung für Besucherkonten für Kioskmodi verwendet werden.

Für eine Nicht-AAD-Konfiguration, um ein Gerät für die automatische Anmeldung von Besuchern zu konfigurieren:

1. Erstellen Sie ein Bereitstellungspaket, das:
    1. Konfiguriert **Laufzeiteinstellungen/AssignedAccess,** um Besucherkonten zuzulassen.
    1. Registriert das Gerät optional bei MDM **(Laufzeiteinstellungen/Arbeitsplatz/Registrierungen),** damit es später verwaltet werden kann.
    1. Erstellen Sie kein lokales Konto.
1. [Wenden Sie das Bereitstellungspaket an.](hololens-provisioning.md)

Bei einer AAD-Konfiguration können Benutzer heute ohne diese Änderung ähnliches erreichen. In AAD eingebundene Geräte, die für den Kioskmodus konfiguriert sind, können sich mit einer einzigen Schaltfläche vom Anmeldebildschirm aus bei einem Besucherkonto anmelden. Nach der Anmeldung beim Besucherkonto fordert das Gerät erst dann zur erneuten Anmeldung auf, wenn der Besucher explizit über das Startmenü abgemeldet oder das Gerät neu gestartet wurde.

Die automatische Anmeldung des Besuchers kann über [eine benutzerdefinierte OMA-URI-Richtlinie](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) verwaltet werden:

- URI-Wert: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Richtlinie  | BESCHREIBUNG   | Configurations  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Ermöglicht es einem Besucher, sich automatisch bei einem Kiosk zu anmelden.   | 1 (Ja), 0 (Nein, Standard)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Verwenden der neuen Einstellungen und Edge-Apps im Kioskmodus

Beim Hinzufügen von Apps in [Kiosks](hololens-kiosk.md)fügt ein IT-Administrator die App häufig dem Kiosk hinzu, verwendet aber die App-Benutzermodell-ID (AUMID). Da sowohl die Einstellungen-App als auch die Microsoft Edge-App als neue Apps betrachtet werden und sich von den älteren Apps unterscheiden, müssen Kiosks, die AUMIDs für diese Apps verwenden, aktualisiert werden, um die neue AUMID zu verwenden.

Wenn Sie einen Kiosk so ändern, dass er die neuen Apps enthält, empfiehlt es sich, die neue AUMID-Datei zu verwenden und die alte zu verlassen. Dies ermöglicht einen einfachen Übergang, wenn Benutzer das Betriebssystem aktualisieren und keine neuen Richtlinien erhalten müssen, um den Kiosk weiterhin wie vorgesehen zu verwenden.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Alte Einstellungs-App       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Neue Einstellungs-App       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Alte Microsoft Edge-App | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Neue Microsoft Edge-App | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern

Wenn ein Gerät in älteren Builds über eine Kioskkonfiguration (eine Kombination aus global zugewiesenem Zugriff und zugewiesenem Zugriff eines AAD-Gruppenmitglieds) verfehlt, wird dem Benutzer im Menü["Nichts](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)im Startmenü" angezeigt, wenn die AAD-Gruppenmitgliedschaft nicht bestimmt werden konnte.

Ab diesem Windows-Release wird die Kiosk-Begerung auf die globale Kioskkonfiguration (falls vorhanden) zurückfallen, falls während des Kioskmodus der AAD-Gruppe Fehler auftfallen.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Neue Einstellungs-URIs für die Sichtbarkeit von Seiteneinstellungen

In [Windows Holographic, Version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) haben wir die Richtlinie [Einstellungen/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) hinzugefügt, um die Seiten einzuschränken, die in der Einstellungs-App angezeigt werden. PageVisibilityList ist eine Richtlinie, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind, oder dies für alle Seiten mit Ausnahme der angegebenen Seiten zu tun.

Wenn Sie Die [Sichtbarkeit von Seiteneinstellungen besuchen,](settings-uri-list.md)finden Sie Anweisungen zur Verwendung dieses CSP und die Liste der URIs, die in früheren Versionen verfügbar waren.

Wir erweitern die Liste der verfügbaren Einstellungs-URIs, die IT-Administratoren verwalten können. Einige dieser URIs gelten für neu verfügbare Bereiche in der neuen Einstellungs-App. Wenn Sie die Richtlinie Settings/PageVisibilityList verwenden, überprüfen Sie die folgende Liste, und passen Sie Ihre zulässigen oder blockierten Seiten nach Bedarf an.

> [!NOTE]
> **Veraltet: ms-settings:network-proxy**
>
> Eine Einstellungsseite ist in diesen neueren Builds veraltet. Die alte Seite **Netzwerk-&**  >  **Internetproxy** ist nicht mehr als globale Einstellung verfügbar. Die neuen Proxyeinstellungen pro Verbindung finden Sie unter **Network & Internet**  >  **WI-Fi**  >  **Properties** oder Network **& Internet**  >  **Ethernet**  >  **Properties**.

<br>

| Seite "Einstellungen"                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps & Features                               | `ms-settings:appsfeatures`                         |
| Apps > Apps & Features > Erweiterte Optionen          | `ms-settings:appsfeatures-app`                     |
| Apps > Offlinezuordnungen                                  | `ms-settings:maps`                                 |
| Apps > Offlinezuordnungen > Karten herunterladen                  | `ms-settings:maps-downloadmaps`                    |
| Geräte > Maus                                      | `ms-settings:mouse`                                |
| Geräte > USB                                        | `ms-settings:usb`                                  |
| Netzwerk & Internet > Flugzeugmodus                   | `ms-settings:network-airplanemode`                 |
| Datenschutz > Allgemein                                    | `ms-settings:privacy-general`                      |
| Datenschutz > Ink-& Eingeben der Personalisierung             | `ms-settings:privacy-speechtyping`                 |
| Datenschutz > Motion                                     | `ms-settings:privacy-motion`                       |
| Datenschutz > Screenshot: Rahmen                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Datenschutz > Screenshots und Apps                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Battery                                     | `ms-settings:batterysaver`                         |
| System > Battery                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > App-Volume und Geräteeinstellungen | `ms-settings:apps-volume`                          |
| System > Sound > Verwalten von Soundgeräten              | `ms-settings:sound-devices`                        |
| System > Storage > Konfigurieren Speicheroptimierung         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & Time                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Update & Security > Reset & Recovery               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualisierte URIs

Zuvor haben die folgenden beiden URIs einen Benutzer nicht direkt zu den angegebenen Seiten gelangt, sondern nur die Hauptseite der Updates blockiert. Die folgenden Elemente wurden aktualisiert, um sie an ihre Seiten weiter zu leitet:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurieren der Fallbackdiagnose über die App "Einstellungen"

Jetzt kann ein Benutzer in der Einstellungs-App das Verhalten der [Fallbackdiagnose konfigurieren.](hololens-diagnostic-logs.md) Navigieren Sie in der App Einstellungen zur Seite  ->  **Problembehandlung beim** Datenschutz, um diese Einstellung zu konfigurieren.

> [!NOTE]
> Wenn eine MDM-Richtlinie für das Gerät konfiguriert ist, kann der Benutzer dieses Verhalten nicht außer Kraft setzen.  

### <a name="share-things-with-nearby-devices"></a>Freigeben von Geräten in der Nähe

Freigeben von Geräten in der Nähe Windows 10, einschließlich PCs und HoloLens 2 Geräten. Sie können es unter Freigegebene Systemerfahrungen für Einstellungen ausprobieren, um Dateien oder URLs von  ->    ->   einer HoloLens an einen PC zu teilen. Weitere Informationen finden Sie unter Freigeben von Geräten in der [Nähe in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Dieses Feature kann über [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)verwaltet werden.

### <a name="new-os-diagnostic-traces"></a>Neue Diagnoseablaufverfolgungen für das Betriebssystem

Zusätzlich zu den vorherigen Problembehandlungen in der Einstellungs-App wurde eine neue Problembehandlung mit der neuen App "Einstellungen" für Betriebssystemupdates hinzugefügt. Navigieren Sie zu **Windows Update** Problembehandlung bei der  ->  **&amp; Updatesicherheit** für  >    >   Einstellungen, und wählen Sie **Starten** aus. Dadurch können Sie Ablaufverfolgungen erfassen, während Sie Ihr Problem mit Betriebssystemupdates reproduzieren, um die Problembehandlung für Ihre IT oder Ihren Support zu verbessern.

### <a name="delivery-optimization-preview"></a>Übermittlungsoptimierung Preview

Mit diesem HoloLens-Update ermöglicht Windows Holographic for Business Übermittlungsoptimierungseinstellungen, um den Bandbreitenverbrauch für Downloads von mehreren HoloLens-Geräten zu reduzieren. Eine umfassendere Beschreibung dieser Funktionalität zusammen mit der empfohlenen Netzwerkkonfiguration finden Sie hier: [Übermittlungsoptimierung für Windows 10 Updates.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Die folgenden Einstellungen werden als Teil der Verwaltungsoberfläche aktiviert und [können über Intune konfiguriert werden:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Einige Einschränkungen zu diesem Vorschauangebot:

- Die HoloLens-Unterstützung ist in dieser Vorschauversion auf Betriebssystemupdates beschränkt.
- Windows Holographic for Business unterstützt nur HTTP-Downloadmodi und Downloads von einem [Microsoft Connected Cache-Endpunkt.](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Peer-zu-Peer-Downloadmodi und Gruppenzuweisungen werden für HoloLens-Geräte derzeit nicht unterstützt.
- HoloLens unterstützt keine Bereitstellungs- oder Übermittlungsoptimierung für Windows Server Update Services Endpunkte.
- Für die Problembehandlung ist entweder eine Diagnose auf dem Connected Cache-Server oder das Sammeln einer Ablaufverfolgung auf HoloLens auf HoloLens über das Einstellungsupdate &  >  **Security**  >   **Troubleshooting**  >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>IT-Administrator: Checkliste aktualisieren

Diese Prüfliste hilft Ihnen, die neuen Elemente zu kennen, die in diesem Featureupdate hinzugefügt werden und sich auf Ihre aktuellen Geräteverwaltungskonfigurationen oder neue Features auswirken können, die Sie möglicherweise verwenden möchten.

#### <a name="updates-to-kiosk-mode"></a>Updates für den Kioskmodus

✔️ Neue [**AUMIDs für neue Apps im Kioskmodus:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Wenn Sie zuvor entweder die Einstellungs-App oder Microsoft Edge-App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, neue [AUMIDs für neue](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Apps im Kioskmodus weiter unten zu lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin über die Einstellungs-App in Ihrem Kiosk verfügen oder die neue Microsoft Edge enthalten. Diese Änderungen können jetzt vorgenommen und auf allen Geräten bereitgestellt werden, um einen reibungsloseren Übergang beim Update zu ermöglichen.

✔️ automatische Anmeldung von Besucher [**für Kioske:**](#visitor-auto-logon-for-kiosks) 

Besucher können jetzt automatisch an einem Kiosk angemeldet werden. Dieses Verhalten ist standardmäßig aktiviert, kann aber verwaltet und deaktiviert werden.

✔️ [**fehlerbearbeitete Fehler im Kioskmodus:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Wenn die AAD-Gruppenmitgliedschaft eines angemeldeten AAD-Benutzers nicht erfolgreich bestimmt wurde, wird die globale Kioskkonfiguration für das Startmenü verwendet (sofern vorhanden). Andernfalls wird dem Benutzer ein leeres Startmenü angezeigt. Das leere Startmenü ist zwar keine Konfiguration, die Sie direkt festlegen können, aber diese neue Behandlung kann ihre Supportabteilung darüber informieren, wenn Sie Kiosks verwenden, da dies möglicherweise für Ihre Konfigurationen gilt oder Sie neue Anpassungen an Den zugewiesenen Zugriffskonfigurationen vornehmen möchten.

#### <a name="updates-to-page-settings-visibility"></a>Updates der Sichtbarkeit von Seiteneinstellungen

✔️ neue [**Einstellungs-URIs für Sichtbarkeit von Seiteneinstellungen**](#new-settings-uris-for-page-settings-visibility)

Wenn Sie derzeit Sichtbarkeit für [Seiteneinstellungen](settings-uri-list.md) verwenden, können Sie Anpassungen an Ihren vorhandenen URIs vornehmen, die Sie entweder zugelassen oder blockiert haben.

#### <a name="updates-for-your-wdac-policy"></a>Updates für Ihre WDAC-Richtlinie
✔️ Wenn Sie zuvor Microsoft Edge über WDAC blockiert haben, sollten Sie Ihre WDAC-Richtlinie aktualisieren. Überprüfen Sie Folgendes, und verwenden Sie den bereitgestellten Beispielcode.
#### <a name="enable-new-endpoints-for-edge"></a>Aktivieren neuer Endpunkte für Edge
✔️ Wenn Sie über eine Infrastruktur verfügen, die die Konfiguration von Netzwerkendpunkten wie Proxy oder Firewall umfasst, aktivieren Sie diese neuen Endpunkte für die neue Microsoft Edge-App.

#### <a name="newly-configurable-items"></a>Neu konfigurierbare Elemente

✔️ Konfigurieren [der Fallbackdiagnose:](#configuring-fallback-diagnostics-via-settings-app)Sie können konfigurieren, ob und wer die Fallbackdiagnose erfassen darf.

✔️ Freigeben von[Inhalten für Geräte in der Nähe:](#share-things-with-nearby-devices)Sie können das neue Feature zum Freigeben in der Nähe deaktivieren.

✔️ Konfigurieren [von Richtlinieneinstellungen für die neue Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Überprüfen Sie die neu für Microsoft Edge verfügbaren Konfigurationen.

#### <a name="new-diagnostic-tool"></a>Neues Diagnosetool

✔️[Neue Diagnoseablaufverfolgungen für das Betriebssystem:](#new-os-diagnostic-traces)Sammeln Sie Protokolle im Zusammenhang mit Betriebssystemupdates.

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:

- [Die Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics) enthält auch zusätzliche Geräteinformationen für Seriennummer und Betriebssystemversion.
- Behebt ein Problem im Zusammenhang mit der Bereitstellung von Branchenanwendungen über Laufzeitbereitstellungspakete.
- Behebt ein Problem im Zusammenhang mit der Berichterstellung zum Installationsstatus von Branchenanwendungen.
- Behebt ein Problem im Zusammenhang mit der Persistenz neuer App-Pakete über Geräterücksetzungen hinweg.
- Behebt ein Problem, das dazu führen kann, dass falsche Symbole in Edge für japanische Kunden typiert werden.
- Verbessert die Resilienz von Betriebssystemupdates für vorinstallierte Apps wie Edge. 
- Behandelt eine Updatezuverlässigkeit, die sich auf die Installation Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, Version 20H2 – Update mai 2021
- Build 19041.1146

Verbesserungen und Fehlerbehebungen im Update:
- Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, Version 1903 – Update mai 2021
- Build 18362.1110

Verbesserungen und Fehlerbehebungen im Update:
- Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. **Dieser Build empfängt keine monatlichen Dienstupdates mehr.** Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, Version 20H2 – Update april 2021
- Build 19041.1144

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem im Rahmen der Berichterstellung zum Installationsstatus von Line-of-Business-Anwendungen.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, Version 1903 – Update april 2021
- Build 18362.1108

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem, bei dem die Einstellungs-App abstürzt, wenn versucht wird, ein Kennwort für ein lokales Konto zu ändern.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, Version 20H2 – Update vom März 2021
- Build 19041.1140

Verbesserungen und Fehlerbehebungen im Update:

- Kunden, die AdvancedPhotoCapture oder LowLagPhotoCapture zum Erfassen von Fotos mit HoloLens 2 verwenden, können jetzt die Kamerapose bis zu 3 Sekunden nach der Aufnahme des Fotos abrufen.
- Behebung eines Speicherverlusts in Geräteportal-Dienst. Das Problem führte zu einer erhöhten Arbeitsspeicherauslastung durch den Dienst, die dazu führte, dass andere Anwendungen keinen Arbeitsspeicher belegen konnten.
- Es wurde ein Problem behoben, bei dem sich Benutzer, die für den gestufigen Rollout registriert sind, nicht beim Gerät anmelden konnten.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, Version 1903 – Update vom März 2021
- Build 18362.1102

Verbesserungen und Fehlerbehebungen im Update:

- Behebung eines Speicherverlusts in Geräteportal-Dienst. Das Problem führte zu einer erhöhten Arbeitsspeicherauslastung durch den Dienst, die dazu führte, dass andere Anwendungen keinen Arbeitsspeicher belegen konnten.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Februar 2021
- Build 19041.1136

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem im Zusammenhang mit der anfänglichen Geräteeinrichtung und dem Speichern von App-Updates.
- Behandelt ein Problem im Zusammenhang mit Upgrades und Flügen für spätere HoloLens-Releases.
- Nicht verwendete vorinstallierte Zertifikate wurden aus dem eSIM-Stammspeicher von HoloLens-Geräten entfernt.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, Version 1903 – Februar 2021 Update
- Build 18362.1098

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Januar 2021
- Build 19041.1134

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Leistung beim Starten, Fortsetzen und Wechseln von Benutzern, wenn viele Benutzer auf dem Gerät sind.
- Arm32-Unterstützung für den [Research-Modus wurde hinzugefügt.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, Version 1903 – Update januar 2021
- Build 18362.1091

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, Version 20H2 – Update vom Dezember 2020
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über App-Installer

Wir fügen **eine neue Funktion (App-Installer)** hinzu, mit der Sie Anwendungen nahtloser auf Ihren HoloLens 2 installieren können. Das Feature ist standardmäßig **für nicht verwaltete Geräte aktiviert.** Um Unterbrechungen für Unternehmen zu verhindern, ist das App-Installationsprogramm derzeit nicht für **verwaltete** Geräte verfügbar.  

Ein Gerät gilt als "verwaltet", **wenn** eine der folgenden Bedingungen zutrifft:
- MDM [registriert](hololens-enroll-mdm.md)
- Mit [Bereitstellungspaket konfiguriert](hololens-provisioning.md)
- Die [Benutzeridentität](hololens-identity.md) ist Azure AD

Sie können Apps jetzt installieren, ohne den Entwicklermodus zu aktivieren oder Geräteportal.  Laden Sie einfach (über USB oder über Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum Appx-Bundle, um zum Starten der Installation aufgefordert zu werden.  Alternativ können Sie [eine Installation über eine Webseite initiieren.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Genau wie Apps, die Sie über die Microsoft Store installieren oder mithilfe der BEREITSTELLUNGsfunktion für branchenspezifische Apps von MDM querladen, müssen Apps mit dem [Signierungstool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) digital signiert werden, und das zum Signieren verwendete Zertifikat muss vom HoloLens-Gerät [als vertrauenswürdig eingestuft werden,](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) bevor die App bereitgestellt werden kann.

**Anweisungen zur Anwendungsinstallation.**

1.  Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet angesehen wird.
1.  Stellen Sie sicher, dass Ihr HoloLens 2 Gerät eingeschaltet und mit Ihrem PC verbunden ist.
1.  Stellen Sie sicher, dass Sie beim HoloLens 2-Gerät angemeldet sind.
1.  Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie "app.appxbundle" in "IhrGerätename\Interner Speicher\Downloads".   Nachdem Sie das Kopieren Ihrer Datei abgeschlossen haben, können Sie ihr Gerät trennen.
1.  Wählen Sie auf Ihrem HoloLens 2 Gerät Startmenü öffnen aus, wählen Sie Alle Apps aus, und starten Sie die Datei-Explorer-App.
1.  Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie im linken Bereich der App zuerst Dieses Gerät auswählen und dann zu Downloads navigieren.
1.  Wählen Sie die Datei yourapp.appxbundle aus.
1.  Die App-Installer wird gestartet. Wählen Sie die Schaltfläche Installieren aus, um Ihre App zu installieren.
Die installierte App wird nach Abschluss der Installation automatisch gestartet.

Beispiel-Apps finden Sie auf GitHub für [universelle Windows-Beispiele,](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) um diesen Flow zu testen.

Erfahren Sie mehr über den [vollständigen](app-deploy-app-installer.md)Prozess der Installation von Apps auf HoloLens 2 mit dem App-Installer .  

![Installieren von MRTK-Beispielen über App-Installer](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:

- Die Handnachverfolgung verwaltet jetzt die Nachverfolgung in vielen neuen Fällen, in denen die Hand zuvor verloren gegangen wäre.  In einigen dieser neuen Fälle wird nur die Handflächenposition des Benutzers basierend auf der tatsächlichen Hand des Benutzers aktualisiert, während die anderen Fugen basierend auf einer vorherigen Pose abgeleitet werden.  Diese Änderung trägt zur Verbesserung der Nachverfolgungskonsistenz bei Bewegungen wie Slapping, Throwing, Scooping und Clapping bei.  Dies hilft auch in Fällen, in denen sich die Hand in der Nähe einer Oberfläche befindet oder ein Objekt hält.  Wenn Handgelenke abgeleitet werden, wird [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) der Genauigkeitswert pro Fugen auf "Approximate" anstatt auf "High" festgelegt.
- Es wurde ein Problem behoben, bei Azure AD pin reset for Azure AD accounts den Fehler "Something was wrong.
- Benutzer sollten beim Starten von ET, Iris über die Einstellungs-App, neuer Benutzer oder Popupbenachrichtigung deutlich weniger OoBE-Abstürze nach dem Start sehen.
- Benutzer sollten über die richtige Zeitzone verfügen, die aus der OOBE kommt.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2020
- Build 18362.1088

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unsere neueste Windows Holographic-Version 20H2 – Update vom Dezember 2020 und das neue App-Installer-Feature auszuprobieren, das im Build hinzugefügt wurde.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, Version 20H2
- Build 19041.1128

Windows Holographic, Version 20H2, ist jetzt verfügbar und bietet eine große Menge neuer Features für HoloLens 2 und IT-Experten. Von der automatischen Blickpositionierung über den Zertifikat-Manager in den Einstellungen bis hin zu verbesserten Kioskmodusfunktionen und neuen Autopilot-Setupfunktionen. Mit diesem neuen Update können IT-Teams eine präzisere Kontrolle über die Konfiguration und Verwaltung von HoloLens-Geräten übernehmen und den Benutzern noch nahtlosere holografische Erfahrungen bieten. 

Dieses neueste Release ist ein monatliches Update auf Version 2004, aber dieses Mal werden neue Features veröffentlicht. Die Hauptversionsnummer bleibt unverändert, und Windows Update gibt ein monatliches Release für Version 2004 (Build 19041) an. Sie können ihre Buildnummer auf dem Bildschirm Einstellungen > Informationen anzeigen, um zu bestätigen, dass Sie sich auf dem neuesten verfügbaren Build 19041.1128 und mehr befinden. Um auf das neueste Release zu aktualisieren, öffnen Sie die App Einstellungen, wechseln Sie zu Update & Sicherheit, und tippen Sie auf Nach Updates suchen. Weitere Informationen zum Verwalten von HoloLens-Updates finden Sie auf [dieser Seite.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Neuerungen in Windows Holographic, Version 20H2  

| Funktion                                              | Beschreibung                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Unterstützung der automatischen Augenposition](hololens-release-notes.md#auto-eye-position-support) | Berechnet aktiv Augenpositionen, ohne dass Benutzer die Eye Tracking-Kalibrierung durchlaufen.   |
| [Zertifikat-Manager](hololens-release-notes.md#certificate-manager)   | Ermöglicht neue einfachere Methoden zum Installieren und Entfernen von Zertifikaten aus der Einstellungs-App.     |
| [Automatisches Starten der Bereitstellung über USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Beim Bereitstellen von Paketen auf USB-Laufwerken wird automatisch die Bereitstellungsseite in OOBE angezeigt.                                                         |
| [Automatische Bestätigung von Bereitstellungspaketen in OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Bereitstellungspakete werden automatisch während der OOBE von der Bereitstellungsseite angewendet.                                                         |
| [Automatische Bereitstellung ohne Benutzeroberfläche](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Hier erfahren Sie, wie Sie den automatischen Start der Bereitstellung und die automatische Bestätigung kombinieren. |
| [Verwenden von Autopilot mit Wi-Fi Verbindung](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Verwenden Sie Autopilot vom Gerät Wi-Fi ohne Ethernet-Adapter. |
| [Tenantlockdown-CSP und Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Nachdem die Mandantenregistrierung und die Richtlinie angewendet wurden, kann das Gerät nur bei jedem Zurücksetzen oder erneuten Flashen des Geräts bei diesem Mandanten registriert werden. |
| [Global zugewiesener Zugriff](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Neue Konfigurationsmethode für den Kioskmodus für mehrere Apps, die den Kiosk auf Systemebene anwendet, sodass er für alle gilt.                  |
| [Automatisches Starten einer App im Kiosk mit mehreren Apps](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Legt fest, dass eine Anwendung automatisch gestartet wird, wenn sie sich bei einem Kioskmodus mit mehreren Apps anmeldet.                                                        |
| [Änderungen des Kioskmodusverhaltens bei der Behandlung von Fehlern](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Ein Fehler im Kioskmodus verfügt jetzt über ein restriktives Fallback.                                                                                                |
| [HoloLens-Richtlinien](hololens-release-notes.md#hololens-policies)                                    | Neue Richtlinien für HoloLens.     |
| [Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Mit der neuen Richtlinie können Benutzer den Gruppenmitgliedschaftscache verwenden, um den Kioskmodus offline für die festgelegte Anzahl von Tagen zu verwenden.                                        |
| [Neue Geräteeinschränkungsrichtlinien für HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Neu aktivierte Geräteverwaltungsrichtlinien für HoloLens 2.                                                                                |
| [Neue Energierichtlinien für HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Neu unterstützte Richtlinien für Energiezeitüberschreitungseinstellungen.  |
| [Aktualisieren von Richtlinien](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Neu aktivierte Richtlinien, die die Steuerung von Updates ermöglichen.           |
| [Sichtbarkeit der Seite "Einstellungen" für HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Richtlinie zum Auswählen der Seiten, die in der Einstellungs-App angezeigt werden.             |
| [Forschungsmodus](hololens-release-notes.md#research-mode) | Verwenden des Forschungsmodus auf HoloLens 2. |
| [Aufzeichnungslänge erhöht](hololens-release-notes.md#recording-length-increased) | MRC-Aufzeichnungen sind nicht mehr auf 5 Minuten begrenzt. |
| [Verbesserungen und Fehlerbehebungen im Update](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Zusätzliche Korrekturen im Update.   |

### <a name="auto-eye-position-support"></a>Automatische Unterstützung der Augenposition

In HoloLens 2 ermöglichen Augenpositionen eine genaue Hologrammpositionierung, eine komfortable Anzeige und eine verbesserte Anzeigequalität. Die Augenpositionen werden intern als Teil der Eyetrackingberechnung berechnet. Dies erfordert jedoch, dass jeder Benutzer die Kalibrierung des Eyetrackings durchgeht, auch wenn die Benutzeroberfläche möglicherweise keine Eingabe für das Anverfolgen der Augen erfordert.

**Auto Eye Position (AEP)** ermöglicht diese Szenarien mit einer interaktionsfreien Möglichkeit, Augenpositionen für den Benutzer zu berechnen. Die automatische Blickposition funktioniert im Hintergrund automatisch ab dem Moment, an dem der Benutzer das Gerät einschaltet. Wenn der Benutzer nicht über eine vorherige Kalibrierung der Blickverfolgung verfügt, beginnt die automatische Augenposition mit der Bereitstellung der Augenpositionen des Benutzers für das Anzeigesystem nach einer Verarbeitungszeit von 20 bis 30 Sekunden. Die Benutzerdaten werden nicht dauerhaft auf dem Gerät gespeichert. Daher wird dieser Vorgang wiederholt, wenn der Benutzer das Gerät startet und wieder einschaltet oder wenn das Gerät neu gestartet oder aus dem Standbymodus reaktiviert wird.

Es gibt einige Änderungen am Systemverhalten mit dem Feature "Auto Eye Position", wenn ein nicht behandelter Benutzer das Gerät einstellt. In diesem Kontext bezieht sich ein nicht überwachter Benutzer auf eine Person, die den Kalibrierungsprozess für die Eyetracking auf dem Gerät noch nicht durchlaufen hat.

| Aktive Anwendung | Vorheriges Verhalten | Verhalten von Windows Holographic, Version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Nicht anvaktivierte App oder Holographic Shell |Das Kalibrierungseingabeaufforderungsdialogfeld für die Eyetracking wird angezeigt. | Es wird keine Eingabeaufforderung angezeigt. |
| Anvaktivierte App | Das Kalibrierungseingabeaufforderungsdialogfeld für die Eyetracking wird angezeigt. | Die Kalibrierungsaufforderung für die Eyetracking wird nur angezeigt, wenn die Anwendung auf den Anverfolgungsstream der Augen zugreift. |

Wenn der Benutzer von einer Nicht-Anverweise-fähigen Anwendung zu einer Anwendung übergeht, die auf die Anviert-Daten zugreift, wird die Kalibrierungsaufforderung angezeigt. 

Alle anderen Systemverhalten ähneln, wenn der aktuelle Benutzer nicht über eine aktive Eyetracking-Kalibrierung verfügt. Beispielsweise wird die Einhändige Startgeste nicht aktiviert. Es gibt keine Änderung an der Vor-/Ausgangserfahrung für die erste Einrichtung.

Für Erfahrungen, die Anvingdaten mit den Augen oder eine sehr genaue Hologrammpositionierung erfordern, empfehlen wir Nicht-Veraltungsbenutzern, um die Eyetracking-Kalibrierung ausführen zu können. Sie können über die Eye Tracking-Kalibrierungsaufforderung oder durch Starten der App "Einstellungen" im Startmenü und anschließendes Auswählen von **System > Calibration > Eye Calibration > Run eye calibration**(Kalibrierung der Augen ausführen) verwenden.

Diese Informationen finden Sie später mit anderen [Kalibrierungsinformationen.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Überprüfungstools für Gerätesicherheit und -konformität über den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen im großen Stil bereitstellen, behandeln und überprüfen.

In Windows Holographic Version 20H2 fügen wir einen Zertifikat-Manager in der HoloLens 2-App hinzu. Wechseln Sie **zu Einstellungen > Update & Security > Certificates**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und konform bleiben. 

-   **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, spart die Validierung, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung. 
-   **Überprüfung:** Die Überprüfung, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionsfähig ist, kann insbesondere in kommerziellen Umgebungen viel Zeit sparen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um ein bestimmtes Zertifikat schnell in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Wählen Sie zum Anzeigen einzelner Zertifikateigenschaften das Zertifikat aus, und klicken Sie auf **Info**. 

Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in Current User installieren. Benutzer können nur Zertifikate entfernen, die direkt über die Benutzeroberfläche der Einstellungen installiert wurden. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.

#### <a name="to-install-a-certificate"></a>So installieren Sie ein Zertifikat: 

1.  Verbinden Sie Ihre HoloLens 2 mit einem PC.
1.  Platzieren Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2.
1.  Navigieren Sie zu **Einstellungen App > Update & Security > Certificates**, und wählen Sie Zertifikat installieren aus.
1.  Klicken Sie auf **Datei importieren,** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **Store Location (Speicherort) aus.**
1.  Wählen Sie **Zertifikatspeicher** aus.
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert sein.

#### <a name="to-remove-a-certificate"></a>So entfernen Sie ein Zertifikat: 
1. Navigieren Sie zu **Einstellungen App > Update- und Sicherheitszertifikate >**.
1. Suchen Sie im Suchfeld nach dem Zertifikat anhand des Namens.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen.**
1. Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.

![Zertifikatanzeige in der Einstellungs-App](images/certificate-viewer-device.jpg)

![Abbildung zur Verwendung der Zertifikat-Benutzeroberfläche zum Installieren eines Zertifikats](images/certificate-device-install.jpg)

Diese Informationen finden Sie später [auf einer neuen Seite des Zertifikat-Managers.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse, die eine geringere Benutzerinteraktion ermöglichen, wenn USB-Laufwerke mit Bereitstellungspaketen während der OOBE verwendet werden.

Vor diesem Release mussten Benutzer den Bereitstellungsbildschirm während der OOBE manuell starten, um die Bereitstellung mithilfe einer Schaltflächenkombination durchführen zu können. Jetzt können Benutzer die Schaltflächenkombination überspringen, indem sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Schließen Sie das USB-Laufwerk während des ersten Interaktionsmoments von OOBE mit dem Bereitstellungspaket an.
1. Wenn das Gerät bereit für die Bereitstellung ist, wird automatisch die Eingabeaufforderung mit der Bereitstellungsseite geöffnet. 

Hinweis: Wenn ein USB-Laufwerk angeschlossen bleibt, während das Gerät gestartet wird, werden vorhandene USB-Speichergeräte von OOBE enumeriert, und es wird darauf achten, dass zusätzliche USB-Speichergeräte angeschlossen werden.

Weitere Informationen zum Anwenden von Bereitstellungspaketen während der OOBE finden Sie in der [HoloLens-Bereitstellungsdokumentation.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Weitere Informationen zur [Automatischstartbereitstellung von](hololens-provisioning.md#auto-launch-provisioning-from-usb) einem USB-Gerät finden Sie in der HoloLens-Bereitstellungsdokumentation.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatisches Bestätigen von Bereitstellungspaketen in OOBE
- Automatisierter Prozess, der weniger Benutzerinteraktion ermöglicht, wenn die Seite Bereitstellungspaket angezeigt wird, werden automatisch alle aufgelisteten Pakete angewendet.

Wenn der Hauptbildschirm für die Bereitstellung angezeigt wird, wird oobe 10 Sekunden heruntergezählt, bevor automatisch mit dem Anwenden aller Bereitstellungspakete gestartet wird. Benutzer können die [Pakete innerhalb dieser](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 10 Sekunden bestätigen oder abbrechen, nachdem sie die erwarteten Pakete überprüft haben.

### <a name="automatic-provisioning-without-using-ui"></a>Automatische Bereitstellung ohne Benutzeroberfläche
- Kombinierte automatische Prozesse für reduzierte Geräteinteraktionen für die Bereitstellung. 

Durch die Kombination des automatischen Starts der Bereitstellung von USB-Geräten und der automatischen Bestätigung der Bereitstellung von Paketen kann ein Benutzer HoloLens 2-Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts zu verwenden oder das Gerät sogar zu verwenden. Sie können weiterhin dasselbe USB-Laufwerk und bereitstellungspaket für mehrere Geräte verwenden. Dies ist nützlich, um mehrere Geräte gleichzeitig in demselben Bereich bereitzustellen. 

1. [Erstellen Sie ein Bereitstellungspaket](hololens-provisioning.md) mithilfe des [Windows-Konfigurations-Designers.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flashen Sie Ihre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) auf [19041.1361 oder einen neueren Build.](https://aka.ms/hololens2previewdownload) 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken des Geräts abgeschlossen hat, trennen Sie das USB-C-Kabel. 
1. Schließen Sie Ihr USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2 Gerät in OOBE gestartet wird, erkennt es automatisch das Bereitstellungspaket auf dem USB-Laufwerk und startet die Bereitstellungsseite.
1. Nach 10 Sekunden wendet das Gerät automatisch das Bereitstellungspaket an. 

Ihr Gerät ist jetzt konfiguriert und [zeigt den Bildschirm Bereitstellung erfolgreich](hololens-provisioning.md#automatic-provisioning-without-using-ui)an.

### <a name="using-autopilot-with-wi-fi-connection"></a>Verwenden von Autopilot mit Wi-Fi Verbindung
- Usb-C-Adapter für Ethernet wurden nicht mehr benötigt, um den Hardwarebedarf zu reduzieren, da Autopilot auf Wi-Fi verbundenen Geräten funktionieren kann.

Sobald Sie während der OOBE eine Verbindung mit HoloLens 2 über WLAN herstellen, sucht OOBE nach einem Autopilot-Profil für das Gerät. Wenn eine gefunden wird, wird sie verwendet, um den restliche AAD-Join- und Registrierungsflow abzuschließen. Anders ausgedrückt: Die Verwendung von Ethernet zu USB-C oder Wi-Fi zu USB-C-Adaptern ist keine Anforderung mehr, sie funktionieren jedoch weiterhin, wenn sie zu Beginn der OOBE bereitgestellt werden. Erfahren Sie mehr über [Autopilot für HoloLens 2 Geräte.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown-CSP und Autopilot
- Behält Geräte auf dem Mandanten der Organisation bei, indem sie für den Mandanten gesperrt werden, auch wenn sie zurückgesetzt oder ein Reflash verwendet werden. Mit zusätzlicher Sicherheit, indem sie die Kontoerstellung in über die Bereitstellung nicht zulasst. 

HoloLens 2 Geräte unterstützen jetzt TenantLockdown CSP ab [Windows Holographic Version 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP ermöglicht es HoloLens 2, nur mit Autopilot an die MDM-Registrierung gebunden zu werden. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown-CSP auf HoloLens 2 entweder auf true oder false (anfänglich festgelegt) festgelegt ist, verbleibt dieser Wert auf dem Gerät, obwohl es neu blinkt, Betriebssystemupdates usw. 

Sobald der RequireNetworkInOOBE-Knoten der TenantLockdown-CSPs auf HoloLens 2 auf TRUE festgelegt ist, wartet OOBE unbegrenzt darauf, dass das Autopilot-Profil nach der Netzwerkkonnektivität erfolgreich heruntergeladen und angewendet wird. 

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown-CSPs auf "true" festgelegt ist, HoloLens 2 die folgenden Vorgänge in OOBE nicht mehr zutreffen: 
- Erstellen eines lokalen Benutzers mithilfe der Laufzeitbereitstellung 
- Ausführen Azure AD Join-Vorgangs per Laufzeitbereitstellung 
- Auswählen, wer das Gerät in der OOBE-Beerfahrung besitzt 

#### <a name="how-to-set-this-using-intune"></a>Wie wird dies mit Intune festgelegt? 
1. Erstellen Sie ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil, und geben Sie true für den RequireNetworkInOOBE-Knoten an, wie unten gezeigt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE sein.

   > [!div class="mx-imgBorder"]
   > ![Festlegen der tennant-Sperrung über OMA-URI](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe, und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie HoloLens 2 Gerätemitglied der Gruppe, die Sie im vorherigen Schritt erstellt haben, und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf dem HoloLens 2 angewendet wird, sind die Auswirkungen von TenantLockdown aktiv.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Wie kann ich requireNetworkInOOBE von TenantLockdown auf HoloLens 2 Intune absichern? 
1. Entfernen Sie HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde. 

1. Erstellen Sie ein benutzerdefiniertes OMA-URI-basiertes Gerätekonfigurationsprofil, und geben Sie false für RequireNetworkInOOBE an, wie unten gezeigt. Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE sein.

   > [!div class="mx-imgBorder"]
   > ![Screenshot: Festlegen von RequireNetworkInOOBE auf FALSE über den OMA-URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe, und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie HoloLens 2 Gerätemitglied der Gruppe, die Sie im vorherigen Schritt erstellt haben, und lösen Sie die Synchronisierung aus.

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2 Gerät angewendet wird, sind die Auswirkungen von TenantLockdown inaktiv. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Was geschieht während der OOBE, wenn das Autopilot-Profil auf einer HoloLens nicht zugewiesen wird, nachdem TenantLockdown auf TRUE festgelegt wurde? 
OOBE wartet unbegrenzt, bis das Autopilot-Profil heruntergeladen wurde, und das folgende Dialogfeld wird angezeigt. Um die Auswirkungen von TenantLockdown zu entfernen, muss das Gerät zunächst mit seinem ursprünglichen Mandanten registriert werden, wobei nur Autopilot verwendet wird, und RequireNetworkInOOBE muss wie im vorherigen Schritt beschrieben aufgehoben werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden. 

![Geräteseitige Ansicht für den Zeitpunkt, an dem die Richtlinie auf dem Gerät erzwungen wird.](images/hololens-autopilot-lockdown.png)

Diese Informationen finden Sie jetzt zusammen mit dem restliche Autopilot unter [Tenantlockdown CSP und Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Global zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene anwendet.

Mit diesem neuen Feature kann ein IT-Administrator ein HoloLens 2 Gerät für den Kioskmodus für mehrere Apps konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System aufwies und für alle Benutzer gilt, die sich beim Gerät anmelden. Weitere Informationen zu diesem neuen Feature finden Sie im [HoloLens-Kiosk mit global zugewiesenem Zugriff.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisches Starten einer Anwendung im Kioskmodus mit mehreren Apps 
- Fokussierte Erfahrung mit dem automatischen App-Start, wodurch die Benutzeroberflächen- und App-Auswahl weiter erhöht wird, die für Kioskmodus-Benutzeroberflächen ausgewählt wurde.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur eine App kann mithilfe des hervorgehobenen Attributs unten in der Konfiguration des zugewiesenen Zugriffs für den automatischen Start festgelegt werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Änderungen des Kioskmodusverhaltens bei der Behandlung von Fehlern
- Sichererer Kioskmodus, indem verfügbare Apps bei Kioskmodusfehlern beseitigt werden. 

Zuvor wurde holoLens verwendet, um alle Anwendungen im Startmenü anzuzeigen, wenn fehler beim Anwenden des Kioskmodus aufgetreten sind. In Windows Holographic Version 20H2 werden im Falle von Ausfällen keine Apps wie folgt im Startmenü angezeigt: 

![Abbildung des Kioskmodus, der jetzt aussieht, wenn ein Fehler auftritt.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens-Richtlinien
- Geräteverwaltungsoptionen speziell für HoloLens, die für die Verwaltung des Geräts erstellt wurden. 

Es wurden neue Mixed Reality-Richtlinien für HoloLens 2 Windows Holographic Version 20H2 erstellt. Zu den neuen steuerbaren Einstellungen gehören: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed Reality-Aufzeichnungen, Festlegen, wann Diagnosen erfasst werden können, und AAD-Gruppenmitgliedschaftscache.  

| Neue HoloLens-Richtlinie                                | Beschreibung                                                                               | Hinweise                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Ermöglicht das Deaktivieren von Helligkeitsschaltflächen, sodass durch Drücken der Schaltfläche die Helligkeit nicht geändert wird.       | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Ermöglicht das Deaktivieren von Lautstärkeschaltflächen, sodass durch drückende Tasten die Lautstärke nicht geändert wird.               | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\MicrophoneDisabled                    | Deaktiviert das Mikrofon, sodass keine Audioaufzeichnung auf dem HoloLens 2.                      | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\FallbackDiagnostics                   | Steuert das Verhalten, wann Diagnoseprotokolle gesammelt werden können.                               | 0 Deaktiviert, 1 Für Gerätebesitzer aktiviert, 2 Für alle aktiviert (Standard) |
| MixedReality\HeadTrackingMode                      | Für die zukünftige Verwendung reserviert.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheCacheInDays | Steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Kiosks für Azure AD Gruppen verwendet wird. | Siehe unten.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk
- Aktivierte Offlinekiosk für die Verwendung mit AAD-Gruppen für bis zu 60 Tage.

Diese Richtlinie steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Konfigurationen des zugewiesenen Zugriffs verwendet werden darf, die auf Azure AD Gruppen für angemeldete Benutzer ausgerichtet sind. Sobald dieser Richtlinienwert nur auf einen Wert größer als 0 festgelegt ist, wird der Cache verwendet, andernfalls nicht.  

Name: AADGroupMembershipCacheCacheInDays-URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCache UsernameInDays

Min. – 0 Tage  
Max. – 60 Tage 

Schritte zur ordnungsgemäßen Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für Kioskzielgruppen Azure AD, und weisen Sie es HoloLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) festlegt, und weisen Sie sie HoloLens-Geräten zu. 
    1. Der URI-Wert sollte in das Textfeld OMA-URI als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheOrporaInDays eingegeben werden.
    1. Der Wert kann zwischen min/max zulässig sein.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Azure AD Benutzer 1 anmelden, wenn das Internet verfügbar ist. Sobald sich der Benutzer anmeldet und Azure AD Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Azure AD Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Tage zulässt. 
1. Die Schritte 4 und 5 können für alle anderen Azure AD Benutzer N wiederholt werden. Der Wichtigste Punkt hierbei ist, dass sich jeder Azure AD Benutzer über das Internet beim Gerät anmelden muss, damit wir mindestens einmal feststellen können, dass er Mitglied Azure AD Gruppe ist, für die die Kioskkonfiguration vorgesehen ist. 
 
> [!NOTE]
> Bis Schritt 4 für einen Azure AD Benutzer das in "getrennten" Umgebungen beschriebene Fehlerverhalten auftritt. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Neue Geräteeinschränkungsrichtlinien für HoloLens 2
- Ermöglicht Benutzern das Verwalten bestimmter Geräteverwaltungsrichtlinien, z. B. das Blockieren des Hinzufügens oder Entfernens von Bereitstellungspaketen.

Neu aktivierte Richtlinien, die mehr Verwaltungsoptionen für HoloLens 2 ermöglichen. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Diese beiden neuen Policen für AllowAddProvisioningPackage und AllowRemoveProvisioningPackage werden unseren [allgemeinen Geräteeinschränkungen hinzugefügt.](hololens-common-device-restrictions.md)

> [!NOTE]
> In Bezug auf [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)unterstützt HoloLens nur die Konfiguration ./Vendor/MSFT/RemoteLock/Lock. Die Konfigurationen im Zusammenhang mit PIN wie Zurücksetzen und Wiederherstellen werden nicht unterstützt.

### <a name="new-power-policies-for-hololens-2"></a>Neue Energierichtlinien für HoloLens 2
- Weitere Optionen für den Ruhezustand oder sperren von HoloLens über Energierichtlinien. 

Mit diesen neu hinzugefügten Richtlinien können Administratoren Energiezustände steuern, z. B. Leerlaufzeitüberschreitungen. Klicken Sie auf den Link für diese Richtlinie, um weitere Informationen zu den einzelnen Richtlinien zu erhalten.

|     Link zur Richtliniendokumentation                |     Hinweise                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Beispielwert für die Verwendung im Windows-Konfigurations-Designer, d. h.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Beispielwert für die Verwendung im Windows-Konfigurations-Designer, d. h.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Beispielwert für die Verwendung im Windows-Konfigurations-Designer, d. h. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Beispielwert für die Verwendung im Windows-Konfigurations-Designer, d.h. 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, d. h.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, d. h.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Diese beiden neuen Richtlinien für DisplayOffTimeoutOnBattery und DisplayOffTimeoutPluggedIn werden unseren [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)hinzugefügt.

> [!NOTE]
> Stellen Sie sicher, dass die Werte für DisplayOffTimeoutOnBattery und StandbyTimeoutOnBattery auf den gleichen Wert festgelegt sind, um eine konsistente Benutzeroberfläche für HoloLens 2 zu gewährleisten. Dasselbe gilt für DisplayOffTimeoutPluggedIn und StandbyTimeoutPluggedIn. Weitere Informationen zum modernen Standbymodus finden Sie [unter Anzeigen, Standbymodus und Ruhezustand von Leerlauftimern.](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers)

### <a name="newly-enabled-update-policies-for-hololens"></a>Neu aktivierte Updaterichtlinien für HoloLens
- Weitere Optionen für die Installation von Updates oder das Deaktivieren der Schaltfläche Updates anhalten, um Updates sicherzustellen.

Diese Updaterichtlinien sind jetzt auf HoloLens 2 Geräten aktiviert:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Ausführliche Informationen zu diesen Updaterichtlinien und deren Verwendung für HoloLens-Geräte finden Sie hier unter [Verwalten von HoloLens-Updates.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Sichtbarkeit der Seite "Einstellungen" für HoloLens 2 aktiviert
- Erhöhte Benutzeroberflächensteuerung in der Einstellungs-App, die möglicherweise verwechselt wird, um eine begrenzte Auswahl von Seiten anzuzeigen.

Wir haben nun eine Richtlinie aktiviert, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind, oder dies für alle Seiten mit Ausnahme der angegebenen Seiten. Klicken Sie auf den folgenden Link, um zu erfahren, wie Sie dieses Feature vollständig anpassen.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Um zu erfahren, welche Seiteneinstellungen Sie auf HoloLens 2 anpassen können, besuchen Sie unsere Seite [Einstellungen-URIs](settings-uri-list.md). 
 
![Screenshot der aktiven Stunden, die in der App "Einstellungen" geändert werden](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Forschungsmodus
Im Forschungsmodus wird die HoloLens 2 zu einem wissenschaftlichen Tool für die Forschung für das sehende Sehen. Im Vergleich zu früheren Editionen hat der Forschungsmodus für HoloLens 2 die folgenden Vorteile:
-   Zusätzlich zu Sensoren, die im HoloLens-Forschungsmodus (1. Generation) verfügbar gemacht werden, bieten wir jetzt IMU-Sensorzugriff, einschließlich Beschleunigungsmesser, Gyroskop und Magnetometer.
-   HoloLens 2 bietet neue Funktionen, die zusammen mit dem Forschungsmodus verwendet werden können. Dies ist insbesondere der Zugriff auf artikulierte APIs für Handtracking und Eyetracking, die einen vielfältigeren Satz von Experimenten liefern können.

Forscher haben jetzt die Möglichkeit, den Forschungsmodus auf ihren HoloLens-Geräten zu aktivieren, um auf alle diese externen Unformatierungsbild-Sensorstreams zu zugreifen. Der Forschungsmodus für HoloLens 2 bietet auch Zugriff auf die Messwerte für Beschleunigungsmesser, Gyroskop und Magnetometer. Um die Privatsphäre der Benutzer zu schützen, sind Unformatieren von Kamerabildern mit Blickverfolgung nicht über den Forschungsmodus verfügbar, aber die Blickrichtung ist über vorhandene APIs verfügbar.

Weitere technische Details [finden Sie in](https://docs.microsoft.com/windows/mixed-reality/research-mode) der Dokumentation zum Forschungsmodus.

### <a name="recording-length-increased"></a>Aufzeichnungslänge erhöht
Aufgrund von Kundenfeedback haben wir die Aufzeichnungsdauer von [Mixed Reality-Erfassungen erhöht.](holographic-photos-and-videos.md) Mixed Reality-Erfassungen sind standardmäßig nicht mehr auf 5 Minuten beschränkt, sondern berechnen stattdessen die maximale Aufzeichnungslänge basierend auf dem verfügbaren Speicherplatz. Das Gerät schätzt die maximale Dauer der Videoaufzeichnung basierend auf dem verfügbaren Speicherplatz auf bis zu 80 % des gesamten Speicherplatzes auf dem Datenträger.

> [!NOTE]
> HoloLens verwendet die Standardlänge der Videoaufzeichnung (5 Minuten), wenn eine der folgenden Bedingungen eintritt:
> - Die geschätzte maximale Aufzeichnungsdauer ist kleiner als die standardmäßigen 5 Minuten.
> - Der verfügbare Speicherplatz beträgt weniger als 20 % des gesamten Speicherplatzes auf dem Datenträger.

Die vollständigen Anforderungen finden Sie in unserer [Dokumentation zu holografischen Fotos und](holographic-photos-and-videos.md#maximum-recording-length) Videos. 

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:
- Weitere Bildschirme in OOBE befinden sich jetzt im dunklen Modus.
- Weitere Informationen finden Sie in den aktuellen Onlinedatenschutzerklärungen.
- Es wurde ein Problem behoben, bei dem Benutzer VPN-Profile nicht über Bereitstellungspakete bereitstellen konnten.
- Proxykonfigurationsproblem für VPN-Verbindung behoben.
- Aktualisierte Richtlinie zum Deaktivieren der Enumeration von USB-Funktionen über MDM für NCM für AllowUsbConnection.
- Es wurde ein Problem behoben, das verhinderte, dass ein HoloLens-Gerät im [Datei-Explorer](hololens-kiosk.md)über das Media Transfer Protocol (MTP) angezeigt wurde, wenn das Gerät als Kiosk mit einer einzelnen App eingerichtet wurde. Beachten Sie, dass MTP (und usb-Verbindung im Allgemeinen) weiterhin mithilfe der [AllowUSBConnection-Richtlinie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) deaktiviert werden können.
- Ein Problem wurde behoben, bei dem Symbole im Startmenü im Kioskmodus ordnungsgemäß skaliert wurden.
- Ein Problem wurde behoben, das darauf zurückzuführen ist, dass die HTTP-Zwischenspeicherung den Kioskmodus für Azure AD Gruppen beeinträchtigt hat.
- Ein Problem wurde behoben, bei dem Benutzer die Schaltfläche Koppeln nicht verwenden konnten, nachdem sie den Entwicklermodus mit Bereitstellungspaketen aktiviert haben, es sei denn, sie haben den Entwicklermodus deaktiviert und wieder aktiviert.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, Version 1903 – November 2020 Update
- Build 18362.1085

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unser neuestes Feature release build Windows Holographic, Version 20H2, auszuprobieren.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, Version 2004 – Oktober 2020 Update
- Build 19041.1124
 
Verbesserungen und Fehlerbehebungen im Update:

- Eine unnötige Überprüfung, die einen Laufzeitsystemfehler verursacht hat, wurde entfernt.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, Version 1903 – Oktober 2020 Update
- Build 18362.1081

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, Version 2004 – Update vom September 2020
- Build 19041.1117

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem, das verhinderte, Visual Studio eine Anwendung debuggen konnte, wenn SupportsMultipleInstances="true" im appxmanifest vorhanden ist.
- Dieses Release enthält korrektur der NCSI-Proxyerkennung, um die fehlgeschlagene Interneterkennung über den Netzwerkproxy zu beheben. NCSI kann einen Computerproxy und profilspezifischen Proxy für die Erkennung der Internetverbindung verwenden. Benutzerspezifische Proxys werden von NCSI in zukünftigen Versionen unterstützt.
- Auf den Windows Mixed Reality Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet. Frühere Versionen von HoloLens 2 jedoch den Vektor so ausgerichtet, dass er stattdessen an den Anzeigepanels ausgerichtet wird, der im Verhältnis zur idealen Ausrichtung um einige Grad nach unten gekippt wird. Neuere Versionen von HoloLens 2 haben dies korrigiert, um semantische Konsistenz über Formfaktoren hinweg sicherzustellen.
- Verbesserte Stabilität der Handverfolgung, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.
- Dieses Release enthält eine Korrektur zur Verbesserung der Qualität des Audiozeitstempels, die möglicherweise zu Problemen bei der Videoaufzeichnung beigetragen hat.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, Version 1903 – Update vom September 2020
- Build 18362.1079

Verbesserungen und Fehlerbehebungen im Update:

- Auf den Windows Mixed Reality Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet. Frühere Versionen von HoloLens 2 jedoch den Vektor so ausgerichtet, dass er stattdessen an den Anzeigepanels ausgerichtet wird, der im Verhältnis zur idealen Ausrichtung um einige Grad nach unten gekippt wird. Neuere Versionen von HoloLens 2 haben dies korrigiert, um semantische Konsistenz über Formfaktoren hinweg sicherzustellen.
- Verbesserte Stabilität der Handverfolgung, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, Version 2004 – Update vom August 2020
- Build 19041.1113

Verbesserungen und Fehlerbehebungen im Update:

- Die Einstellungs-App folgt dem Benutzer nicht mehr in Iris Enrollment- oder Eye Tracking Calibration-Umgebungen.
- Es wurde ein Fehler behoben, bei dem beim Anwenden eines Bereitstellungspakets während der OoBE, das das Gerät umbenennt und andere Aktionen ausführt (z. B. das Herstellen einer Verbindung mit einem Netzwerk), die anderen Aktionen nach dem Neustart des Geräts aufgrund einer Umbenennung nicht ausgeführt werden.
- Geändertes Farbschema der anfänglichen Geräteeinrichtungsflows zur Verbesserung der visuellen Qualität.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, Version 1903 – Update vom August 2020
- Build 18362.1074

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, Version 2004 – Update vom Juli 2020
- Build 19041.1109

Verbesserungen und Fehlerbehebungen im Update:

- Entwickler können jetzt zwischen dem Aktivieren oder Deaktivieren von Geräteportal benötigen eine sichere Verbindung wählen.
- Die Zuverlässigkeit für Anwendungsstarts nach Betriebssystemupdates wurde verbessert.
- Standard-Eingangsbox-Helligkeit wurde in 100 Prozent geändert.
- Es wurde ein Problem mit der HTTPS-Weiterleitung für die Windows-Geräteportal auf HoloLens 2 behoben.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, Version 1903 – Update vom Juli 2020
- Build 18362.1071

Verbesserungen und Fehlerbehebungen im Update:

- Ein Problem wurde behoben, das dazu führen konnte, dass Hologramme in Unity-Anwendungen nicht mehr angezeigt werden, wenn die Nachverfolgung verloren geht oder wiedererlangt wird.
- Es wurde ein Problem behoben, das dazu führte, dass exklusive HoloLens-Apps bei Verwendung des HoloLens-Emulators mit Hardwarebeschleunigung auf bestimmten Geräten wieder auf die Shell abstürzten.
- Es wurde ein Problem in Bezug auf die HTTPS-Weiterleitung für die Windows-Geräteportal auf HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, Version 2004 – Update juni 2020
- Build 19041.1106

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen jetzt über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben werden.
  - Auf dem *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive Headset))
  - Auf dem *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle Wert für "App Audio Gain" auf der Mixed Reality-Aufnahme-Seite in Windows-Geräteportal)
    - MicrophoneGain (der aktuelle Wert "Mic Audio Gain" (Mikrofonaudiogewinn) auf Mixed Reality-Aufnahme-Seite in Windows-Geräteportal)
- Ein Fehler zur Verbesserung der Audioqualität in Mixed Reality-Erfassungsszenarien wurde behoben. Insbesondere sollte diese Korrektur audio glung in der Aufzeichnung beseitigen, wenn das **Startmenü** angezeigt wird.
- Verbesserte Hologrammstabilität in aufgezeichneten Videos.
- Es wurde ein Problem behoben, bei dem die Mixed Reality-Erfassung kein Video aufzeichnen konnte, nachdem das Gerät mehrere Tage lang im Standbyzustand war.
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, das dazu führte, dass einige Apps angehalten wurden, wenn das Visor gekippt wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert wurde. Die API ist jetzt für Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Wenn Sie Geräteportal über eine Wi-Fi zugreifen, kann ein Webbrowser den Zugriff auf aufgrund eines ungültigen Zertifikats verhindern. Der Browser meldet möglicherweise einen Fehler wie "ERR_SSL_PROTOCOL_ERROR", auch wenn das Gerätezertifikat zuvor vertrauenswürdig war. In diesem Fall können Sie nicht zu Geräteportal, da es keine Option zum Ignorieren von Sicherheitswarnungen gibt. Dieses Update hat das Problem behoben. Wenn das Gerätezertifikat zuvor heruntergeladen und auf einem PC als vertrauenswürdig eingestuft wurde, um Browsersicherheitswarnungen zu entfernen, und der SSL-Fehler auftritt, muss das neue Zertifikat heruntergeladen und als vertrauenswürdig eingestuft werden, um Sicherheitswarnungen des Browsers zu beheben.
- Ermöglicht das Erstellen eines Laufzeitbereitstellungspakets, das eine App mithilfe von MSIX-Paketen installieren kann.
- Unter **Einstellungen** System hologramme wurde eine Einstellung hinzugefügt, mit der  >    >   Benutzer beim Herunterfahren des Geräts automatisch alle Hologramme aus Mixed Reality Startseite entfernen können.
- Ein Problem wurde behoben, durch das HoloLens-Apps ihr Pixelformat so geändert haben, dass sie im HoloLens-Emulator schwarz gerendert werden.
- Ein Fehler wurde behoben, der während der Iris-Anmeldung einen Absturz verursacht hat.
- Ein Problem mit wiederholten Storedownloads für bereits aktuelle Apps wurde behoben.
- Ein Fehler wurde behoben, der verhinderte, dass immersive Apps Microsoft Edge wiederholt öffnen.
- Es wurde ein Problem mit dem Start der Photos-App beim ersten Start nach dem Update von Version 1903 behoben.
- Verbesserte Leistung und Zuverlässigkeit.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, Version 1903 – Update vom Juni 2020
- Build 18362.1064

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben sind.
  - Auf dem *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersives Headset))
  - Auf dem *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle Wert für "App Audio Gain" auf der Mixed Reality-Aufnahme-Seite in Windows-Geräteportal)
    - MicrophoneGain (der aktuelle Wert "Mic Audio Gain" (Mikrofonaudiogewinn) auf Mixed Reality-Aufnahme-Seite in Windows-Geräteportal)
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, das dazu führt, dass einige Apps angehalten werden, wenn das Visor gekippt wird, auch wenn die Einstellung für die Ausführung im Hintergrund aktiviert ist. Die API ist jetzt für Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Es wurde ein Problem behoben, durch das HoloLens-Apps, deren Pixelformat geändert wurde, im HoloLens-Emulator schwarz gerendert wurden.
- Es wurde ein Problem behoben, bei dem die Fotos-App nach dem Update von Release 1903 gestartet wurde.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, Version 2004  
- Build: 19041.1103

Das größere Softwareupdate für HoloLens 2, *Windows Holographic, Version 2004 vom Mai 2020,* enthält eine Vielzahl von interessanten neuen Funktionen, z.B. Unterstützung für Windows Autopilot, dunklen App-Modus, USB-Ethernet-Unterstützung für 5G/HOTSPOT-Hotspots und vieles mehr. Um auf das neueste Release zu aktualisieren, öffnen Sie die App Einstellungen, wechseln Sie zu Update & Security , und wählen Sie die Schaltfläche   Nach Updates **suchen** ****   aus. 

|             Funktion                              |          Beschreibung                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Vorkonfigurierung und nahtloses Einrichten neuer Geräte für die Produktion mitHilfe von Windows AutoPilot                 |
|       FIDO 2-Unterstützung                             |          Unterstützung für FIDO2-Sicherheitsschlüssel, um eine schnelle und sichere Authentifizierung für freigegebene Geräte zu ermöglichen            |
|       Verbesserte Bereitstellung                      |          Nahtloses Anwenden eines Bereitstellungspakets von einem USB-Laufwerk auf Ihre HoloLens                              |
|       Installationsstatus der Anwendung                 |          Überprüfen des Installationsstatus in der App "Einstellungen" für Apps, die per MDM HoloLens 2 wurden               |
|       Konfigurationsdienstanbieter (Configuration Service Providers, CSPs)   |          Neue Konfigurationsdienstanbieter zur Verbesserung der Verwaltungssteuerungsfunktionen hinzugefügt                 |
|       USB 5G/LTE-Unterstützung                       |          Erweiterte USB-Ethernet-Funktion ermöglicht Unterstützung für 5G/GIGABIT                                    |
|       Dunkler App-Modus                              |          Dunkler App-Modus für Apps verfügbar, die sowohl dunkle als auch helle Modi unterstützen, um die Anzeige zu verbessern        |
|       Sprachbefehle                             |          Unterstützung für zusätzliche Systemstimmenbefehle zum Steuern der HoloLens-Freihand                           |
|       Verbesserungen bei der Handnachverfolgung                 |          Verbesserungen bei der Handnachverfolgung verbessern die Genauigkeit von Schaltflächen und 2D-Slate-Interaktionen.                        |
|       Qualitätsverbesserungen und Fehlerbehebungen                 |          Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen des Systems auf der gesamten Plattform                            |

### <a name="support-for-windows-autopilot"></a>Unterstützung für Windows Autopilot

Windows Autopilot für HoloLens 2 ermöglicht es dem Geräteverkaufskanal, HoloLens vorab bei Ihrem Intune-Mandanten zu registrieren. Wenn Geräte eintreffen, können sie sich selbst als freigegebene Geräte unter Ihrem Mandanten bereitstellen. Um die Selbstbereitstellung nutzen zu können, muss das Gerät während des ersten Bildschirms des Setups eine Verbindung mit einem Netzwerk herstellen, indem ein USB-C-to-Ethernet verwendet wird.

Nachdem ein Benutzer den Autopilot-Selbstbereitstellungsprozess gestartet hat, führt der Prozess die folgenden Schritte aus:

1. Verbinden Sie das Gerät mit Azure Active Directory (Azure AD).
1. Verwenden Sie Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Laden Sie die geräteorientierten Richtlinien, Zertifikate und Netzwerkprofile herunter.
1. Bereitstellen des Geräts.
1. Zeigen Sie dem Benutzer den Anmeldebildschirm an.

Weitere Informationen finden Sie im leitfaden Windows Autopilot for HoloLens 2 evaluation (Leitfaden zur [HoloLens 2-Evaluierung).](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Wenden Sie sich an Ihren Konto-Manager, um jetzt an der AutoPilot-Vorschau teilzu nehmen. Für Autopilot bereite Geräte werden bald mit dem Versand beginnen.*

### <a name="fido2-security-key-support"></a>FIDO2-Sicherheitsschlüsselunterstützung

Einige Benutzer geben ein HoloLens-Gerät für andere Benutzer in einer Arbeits- oder Schulumgebung weiter. Daher ist es wichtig, dass Benutzer problemlos lange Benutzernamen und Kennwörter eingeben müssen. Mit Fast Identity Online (FIDO) können sich alle Benutzer in Ihrer Organisation (Azure AD-Mandant) nahtlos bei HoloLens anmelden, ohne einen Benutzernamen oder ein Kennwort eingeben zu müssen.

FIDO2-Sicherheitsschlüssel sind eine "unphishable" standardbasierte kennwortlose Authentifizierungsmethode, die in jedem Formfaktor verwendet werden kann. FIDO ist ein offener Standard für die kennwortlose Authentifizierung. Dadurch können sich Benutzer und Organisationen ohne Benutzernamen oder Kennwort bei ihren Ressourcen anmelden. Stattdessen verwenden sie einen externen Sicherheitsschlüssel oder einen in ein Gerät integrierten Plattformschlüssel.

Informationen zu den ersten Schritte finden Sie unter [Aktivieren der Anmeldung mit kennwortlosem Sicherheitsschlüssel.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Verbesserte MDM-Registrierung per Bereitstellungspaket

MitHilfe von Bereitstellungspaketen können Sie die HoloLens-Konfiguration über eine Konfigurationsdatei und nicht über die vorkonfigurierte HoloLens-Erfahrung festlegen. Zuvor mussten Bereitstellungspakete in den internen HoloLens-Speicher kopiert werden. Jetzt können sie sich auf einem USB-Laufwerk speichern, sodass sie leichter auf mehreren HoloLens-Geräten wiederverwendet werden können, und Sie können Geräte parallel bereitstellen. Bereitstellungspakete unterstützen jetzt auch ein Feld für die Registrierung bei der Geräteverwaltung, sodass nach der Bereitstellung keine manuelle Einrichtung mehr erforderlich ist.

So können Sie es ausprobieren:

1. Laden Sie die neueste Version des Windows-Konfigurations-Designers aus dem Windows Store auf Ihren PC herunter.
1. Wählen **Sie Provision HoloLens Devices** Provision HoloLens 2 devices  >  **(HoloLens-Geräte bereitstellen) aus.**
2. Erstellen Sie Ihr Konfigurationsprofil. Kopieren Sie dann alle Dateien, die auf ein USB-C-Speichergerät erstellt wurden.
3. Schließen Sie das USB-C-Gerät an alle neu blinkenden HoloLens an. Drücken Sie dann die Netzschalter für das **Volume,**  +   um Ihr Bereitstellungspaket anzuwenden.

### <a name="line-of-business-application-install-status"></a>Installationsstatus der Branchenanwendung

Die Bereitstellung und Verwaltung von MDM-Apps für Branchen-Apps ist für HoloLens von entscheidender Bedeutung. Administratoren und Benutzer müssen den App-Installationsstatus für die Überwachung und Diagnose anzeigen. In dieser Version haben wir weitere Details unter **Einstellungen**  >  **Konten**  >  **Zugriff auf Arbeits- oder Schulkonto**  >  **Klicken Sie auf Ihr Konto**  >  **Info** hinzugefügt.

### <a name="additional-csps-and-policies"></a>Zusätzliche CSPs und Richtlinien

Ein [Konfigurationsdienstanbieter (Configuration Service Provider, CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ist eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf einem Gerät. In dieser Version fügen wir Unterstützung für weitere Richtlinien hinzu, um die Kontrolle zu erhöhen, die Administratoren über bereitgestellte HoloLens-Geräte haben. Eine Liste der von HoloLens unterstützten CSPs finden Sie unter [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Neu in dieser Version:

**Policy CSP** 

Der Richtlinienkonfigurations-Dienstanbieter ermöglicht dem Unternehmen das Konfigurieren von Richtlinien auf Windows-Geräten. In dieser Version haben wir neue Richtlinien für HoloLens hinzugefügt, die hier aufgeführt sind. Weitere Informationen finden Sie unter [Richtlinien-CSPs,](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)die von HoloLens 2 unterstützt werden.  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy-CSP**

Der NetworkQoSPolicy-Konfigurationsdienstanbieter erstellt QoS-Richtlinien (Network Quality of Service). Eine QoS-Richtlinie führt eine Reihe von Aktionen für den Netzwerkdatenverkehr basierend auf einer Reihe von Abgleichsbedingungen aus. Weitere Informationen finden Sie unter [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Erweiterte USB-Ethernet-Unterstützung für 5G/ETHERNET-Tethergeräte

Es wurde Unterstützung hinzugefügt, um bestimmte mobile Breitbandgeräte zu aktivieren, z. B. 5G-/SPEED-Telefone und Wi-Fi-Hotspots, wenn sie über USB an die HoloLens 2 werden. Diese Geräte werden jetzt in den **Netzwerkeinstellungen als** eine andere Ethernet-Verbindung angezeigt. (Mobile Breitbandgeräte, die einen externen Treiber erfordern, werden nicht unterstützt.) Diese Funktion ermöglicht Verbindungen mit hoher Bandbreite, Wi-Fi nicht verfügbar ist und Wi-Fi Tethering nicht ausreichend leistungsfähigkeit auft. Weitere Informationen zu unterstützten USB-Geräten finden Sie unter [Verbinden mit Bluetooth- und USB-C-Geräten.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Verbesserungen bei der Handnachverfolgung

Dieses Release umfasst mehrere Verbesserungen der Handverfolgung:

- **Pointing-Pose-Stabilität:** Das System spricht sich jetzt dagegen aus, den Zeigefinger zu beugen, wenn er von der Handfläche verblendet wird. Diese Änderung verbessert die Genauigkeit beim Drücken von Schaltflächen, Eingeben, Scrollen von Inhalten und mehr! 
- **Reduziertes versehentliches Tippen in die Luft:** Wir haben die Erkennung der Tippbewegung in die Luft verbessert. Es gibt jetzt weniger versehentliche Aktivierungen in mehreren gängigen Szenarien, z. B. wenn Sie ihre Hände auf Ihre Seiten legen.
- **Zuverlässigkeit des Benutzerwechsels:** Das System ist jetzt schneller und zuverlässiger bei der Aktualisierung der Handgröße, wenn Sie ein Gerät freigeben.
- **Reduzierter Diebstahl von Hand:** Wir haben die Behandlung von Fällen verbessert, in denen mehr als zwei Hände im Blick auf die Sensoren sind. Wenn mehrere Personen eng zusammenarbeiten, ist die Wahrscheinlichkeit, dass die nachverfolgte Hand vom Benutzer zur Hand einer anderen Person in der Szene springt, wesentlich geringer.
- **Systemsicherheit:** Es wurde ein Problem behoben, das dazu führte, dass die Handverfolgung nicht mehr funktionierte, wenn das Gerät stark lastet.

### <a name="dark-mode"></a>Dunkler Modus

Viele Windows-Apps unterstützen jetzt sowohl dunkle als auch helle Modi. HoloLens 2 Benutzer können den Standardmodus für Apps auswählen, die beide unterstützen. Nach dem Update ist der Standard-App-Modus "dunkel", aber Sie können diese Einstellung einfach ändern: Navigieren Sie zu **Einstellungen**  >    >  **Systemfarben**  >  **Wählen Sie Ihren Standard-App-Modus** aus. 

Diese "in-box"-Apps unterstützen den dunklen Modus: 

- Einstellungen 
- Microsoft Store 
- E-Mail 
- Kalender 
- Datei-Explorer 
- Feedback-Hub 
- OneDrive 
- Fotos 
- 3D-Viewer 
- Filme & TV 

![Fenster im dunklen Modus gekachelt](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Sprachbefehle des Systems

Sie können jetzt Sprachbefehle mit jeder App auf dem Gerät verwenden. Weitere Informationen finden Sie unter [Verwenden Ihrer Stimme zum Betreiben von HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Weitere Informationen finden Sie auch unter [Unterstützte Sprachen für HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Cortana-Updates

Die aktualisierte App ist in Microsoft 365 integriert, damit Sie ihre Geräte besser nutzen können (derzeit nur in US-English). Auf HoloLens 2 unterstützt Cortana bestimmte gerätespezifische Befehle wie das Anpassen des Volumes oder das Neustarten nicht mehr. Diese Optionen werden jetzt von den neuen Sprachbefehlen des Systems unterstützt. Weitere Informationen zur neuen Cortana-App finden Sie in unserem [Blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Qualitätsverbesserungen und Fehlerbehebungen

Verbesserungen und Fehlerbehebungen auch im Update:  
- Ein aktives Kalibrierungssystem für die Anzeige wurde eingeführt. Dieses Feature verbessert die Stabilität und Ausrichtung von Hologrammen. Sie bleiben nun an Ort und Stelle, wenn Sie den Kopf von Seite zu Seite bewegen.
- Ein Fehler wurde behoben, Wi-Fi Streaming an HoloLens in regelmäßigen Abständen unterbrochen wurde. Wenn eine Anwendung angibt, dass streaming mit geringer Latenz benötigt wird, implementieren Sie die Korrektur, indem Sie die [SetSocketMediaStreamingMode-Funktion aufrufen.](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Ein Gerät, das während des Streamings im Forschungsmodus nicht mehr verfügbar war, wurde behoben.
- Es wurde ein Fehler behoben, bei dem in einigen Fällen der richtige Benutzer beim Fortsetzen einer Sitzung nicht auf dem Anmeldebildschirm angezeigt wurde.
- Es wurde ein Problem behoben, bei dem Benutzer MDM-Protokolle nicht über einstellungen **exportieren konnten.**
- Es wurde ein Problem behoben, bei dem die Genauigkeit der Blickverfolgung unmittelbar nach der vorgeschachtelten Einrichtung niedriger als erwartet sein konnte.
- Es wurde ein Problem behoben, bei dem das Eyetrackingsubsystem unter bestimmten Bedingungen nicht initialisiert oder kalibriert werden konnte.
- Es wurde ein Problem behoben, bei dem die Kalibrierung der Augen für einen bereits kalibrierten Benutzer angezeigt wurde.
- Ein Problem wurde behoben, bei dem ein Treiber während der Kalibrierung der Augen abstürzte.
- Es wurde ein Problem behoben, bei dem wiederholtes Drücken des Netzschalters zu einem Systemzeitüberschreitungs- und Shellabsturz von 60 Sekunden führen konnte.
- Verbesserte Stabilität für Tiefenpuffer.
- Im Bereich **wurde eine Schaltfläche** Freigeben hinzugefügt Feedback-Hub damit Benutzer leichter Feedback senden können.
- Es wurde ein Fehler behoben, bei dem RoboRaid wan nicht ordnungsgemäß installiert wurde.

### <a name="known-issues"></a>Bekannte Probleme

- Ein Problem mit der Zh-CN-Systemsprache verhindert, dass Sprachbefehle eine Mixed Reality-Erfassung ausführen oder die IP-Adresse des Geräts anzeigen.
- Ein Problem erfordert, dass Sie die Cortana-App starten, nachdem Sie das Gerät gestartet haben, um die "Hey Cortana" zu verwenden. Wenn Sie von einem Build 18362 aktualisiert haben, wird möglicherweise auch eine zweite App-Kachel für die vorherige Version der Cortana-App angezeigt, die in Starten nicht mehr **funktioniert.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, Version 1903 – Update mai 2020 
- Build 18362.1061

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen, da das Team wie zuvor beschrieben an der Windows Holographic-Version 2004 May Update gearbeitet hat.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, Version 1903 – April 2020 Update
- Build 18362.1059

**Dunkler Modus für unterstützte Apps** 

Viele Windows-Apps unterstützen sowohl den dunklen als auch den hellen Modus. HoloLens 2 Kunden können jetzt den Standardmodus für Apps auswählen, die beide Farbschemas unterstützen. Basierend auf Kundenfeedback legen wir den Standard-App-Modus auf "dunkel" fest. Sie können diese Einstellung jedoch jederzeit problemlos ändern: Navigieren Sie zu **Einstellungen > System > Colors,** um nach **"Choose your default app mode"** zu suchen.

Diese "in-box"-Apps unterstützen den dunklen Modus:
- Einstellungen
- Microsoft Store
- E-Mail
- Kalender
- Datei-Explorer
- Feedback-Hub
- OneDrive
- Fotos
- 3D-Viewer
- Filme & TV

**Verbesserungen und Fehlerbehebungen auch im Update:** 
- Es wurde sichergestellt, dass Shellüberlagerungen in Mixed Reality-Erfassungen enthalten sind.
- Unreal-Entwickler können jetzt die Seite 3D-Ansicht in Geräteportal verwenden, um ihre Anwendungen zu testen und zu debuggen.
- Verbesserte Hologrammstabilität in Mixed Reality-Erfassung, wenn der *HolographicDepthReprojectionMethod DepthReprojection-Algorithmus* verwendet wird.
- Der Fehler "WinRT IStreamSocketListener API Class not registered" (WinRT-IStreamSocketListener-API-Klasse nicht registriert) für 32-Bit-ARM-Apps wurde behoben.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, Version 1903 – Update vom März 2020 
- Build 18362.1056

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Hologrammstabilität in Mixed Reality-Erfassung, wenn der *HolographicDepthReprojectionMethod AutoPlanar-Algorithmus* verwendet wird.
- Es wurde sichergestellt, dass das Koordinatensystem, das an eine Tiefen-MF-Stichprobe angefügt ist, mit der öffentlichen Dokumentation konsistent ist.
- Die Produktivität von Entwicklern wurde verbessert, da Kunden große Mengen von Text über das Geräteportal einfügen können.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, Version 1903 – Update februar 2020 
- Build 18362.1053

Verbesserungen und Fehlerbehebungen im Update:

- Die HolographicSpace.UserPresence-API für Unity-Anwendungen wurde vorübergehend deaktiviert. Durch diese Änderung wird ein Problem vermieden, das dazu führte, dass einige Apps angehalten wurden, wenn das Visor gekippt wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert wurde.
- Es wurde ein zufälliger HUP-Absturz behoben, der durch die Handverfolgung verursacht wurde, bei dem der Benutzer bemerkte, dass die Benutzeroberfläche erst nach einigen Sekunden einfriert und dann wieder in die Shell zurückfing.
- Die Handnachverfolgung wurde verbessert, sodass der obere Teil dieses Fingers beim Pokeen mit dem Zeigefinger weniger wahrscheinlich unerwartet gelockt wird.
- Verbesserte Zuverlässigkeit von Head Tracking, räumlicher Zuordnung und anderen Laufzeiten.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, Version 1903 – Update januar 2020 
- Build 18362.1043
 
Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Stabilität für exklusive Apps bei der Arbeit mit dem HoloLens 2 Emulator.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2019 
- Build 18362.1042

Verbesserungen und Fehlerbehebungen im Update:

- LSR-Korrekturen (Last Stage Veröffentlichung) wurden eingeführt. Verbessertes visuelles Rendering von Hologrammen, um stabiler und präziser zu erscheinen, indem die Tiefe genauer abbucht. Dieses Symptom ist nach diesem Update deutlicher, wenn Apps die Tiefe der Hologramme nicht richtig festlegen.
- Die Stabilität exklusiver Apps und die Navigation zwischen exklusiven Apps wurden korrigiert.
- Ein Problem wurde behoben, bei dem die Mixed Reality-Erfassung das Video nicht aufzeichnen konnte, nachdem sich das Gerät mehrere Tage lang im Standbyzustand befand.
- Verbesserte Hologrammstabilität.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, Version 1903 – November 2019 Update 
- Build 18362.1039

Verbesserungen und Fehlerbehebungen im Update:

- Die Funktionalität von **Select** voice commands während der ersten Einrichtung für en-CA und en-AU wurde behoben.
- Verbesserte visuelle Qualität von Objekten, die weit entfernt in den neuesten Versionen von Unity und Mixed Reality Toolkit (MRTK) platziert wurden.
- Beheben von Problemen mit holografischen Anwendungen, die beim Start angehalten wurden, bis die Startmenü geöffnet und dann geschlossen wurde, wurde behoben.
- Fehlerbehebungen und Verbesserungen der OpenXR-Runtimekonformität für HoloLens 2 und den Emulator.
