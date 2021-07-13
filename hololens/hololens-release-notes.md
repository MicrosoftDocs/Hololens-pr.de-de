---
title: Versionshinweise für HoloLens 2
description: Bleiben Sie mit allen Updates in jedem neuen HoloLens 2-Release auf dem laufenden.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 73d89619498c61f2809702d788ffafc532afa67e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640031"
---
# <a name="hololens-2-release-notes"></a>Versionshinweise für HoloLens 2

Um sicherzustellen, dass Sie eine produktive Erfahrung mit Ihren HoloLens Geräten haben, werden weiterhin Feature-, Fehler- und Sicherheitsupdates veröffentlicht. Auf dieser Seite können Sie sehen, was für HoloLens jeden Monat neu ist. Um das neueste HoloLens 2 Update zu erhalten, können Sie entweder nach [Updates suchen und manuell aktualisieren](hololens-update-hololens.md#check-for-updates-and-manually-update) oder das Full Flash Update (FFU) abrufen, um Ihr Gerät über Advanced Recovery Companion zu [flashen.](hololens-recovery.md#clean-reflash-the-device) Der [Download](https://aka.ms/hololens2download) wird auf dem neuesten Stand gehalten und bietet den neuesten allgemein verfügbaren Build.

> [!NOTE]
> Die letzte Ankündigung Windows 11 konzentriert sich auf die PC-Version von Windows. Wir haben kürzlich im Mai 2021 ein [wichtiges Betriebssystemupdate](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) für HoloLens 2 veröffentlicht, und wir arbeiten an einem zukünftigen Release, das auf Kundenfeedback für diesen Fall basiert.

> [!IMPORTANT]
> Aufgrund eines nun behobenen [bekannten Problems in unserem 21H1-Build, das sich auf Remote Assist Benutzer auswirkte,](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)haben wir das Angebot von Windows Holographic- Version 21H1-Updates vorübergehend angehalten. Außerdem wurde der standardmäßige Arc-Build (Advanced Recovery Companion) in das [Windows Holographic, Version 20H2 – Update vom Juni 2021,](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)geändert. Der ARC-Build wird nun für den 21H1-Build fortgesetzt.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, Version 21H1 – Update vom Juni 2021
- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive für den Upload von Kamerarolls für Arbeits- oder Schul-

Wir haben der HoloLens 2 Einstellungen-App ein neues Feature hinzugefügt, mit dem Kunden automatisch Mixed Reality-Fotos und -Videos aus dem Ordner Pictures > Camera Roll des Geräts in den entsprechenden OneDrive für den Arbeits- oder Schulordner hochladen können. Dieses Feature behebt eine [Featurelücke innerhalb der OneDrive-App](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) auf HoloLens 2, die nur den automatischen Kamerarollup in die persönliche Microsoft-Konto eines Kunden (und nicht in sein Arbeits- oder Schulkonto) unterstützt.

**So funktioniert's**

- Besuchen Sie **Einstellungen > System > Mixed Reality-Kamera,** um "Kameraupload" zu aktivieren.
- Wenn Sie dieses Feature auf Die Position **Ein** festlegen, werden alle Mixed Reality-Fotos oder -Videos, die auf Ihrem Gerät erfasst werden, automatisch in die Warteschlange eingereiht, um sie in den Ordner Bilder > Kameraroll Ihres OneDrive für Ihr Arbeits- oder Schulkonto hochzuladen.
    >[!NOTE]
    >Fotos und Videos, die vor der Aktivierung dieses Features erfasst wurden, werden *nicht* für den Upload in die Warteschlange eingereiht und müssen weiterhin manuell hochgeladen werden.
- Eine Statusmeldung auf der seite Einstellungen zeigt die Anzahl der Dateien an, für die ein Upload aussteht (oder "OneDrive ist auf dem neuesten Stand", wenn alle ausstehenden Dateien hochgeladen wurden).
- Wenn Sie Bedenken hinsichtlich der Bandbreite haben oder den Upload aus irgendeinem Grund "anhalten" möchten, können Sie das Feature auf die Position **Aus** umstellen. Durch das vorübergehende Deaktivieren des Features wird sichergestellt, dass die Uploadwarteschlange weiter zunimmt, wenn Sie dem Ordner Camera Roll neue Dateien hinzufügen. Dateien werden jedoch erst hochgeladen, wenn Sie das Feature erneut aktivieren.
- Die neuesten Dateien werden zuerst hochgeladen (last in, first out).
- Wenn Ihr OneDrive-Konto Probleme hat (z. B. nach Kennwortänderungen), wird auf der Seite Einstellungen die Schaltfläche **Jetzt** korrigieren angezeigt.
- Es gibt keine maximale Dateigröße, aber beachten Sie, dass das Hochladen großer Dateien länger dauert (insbesondere, wenn die Uploadbandbreite eingeschränkt ist). Wenn Sie den Upload "anhalten" oder deaktivieren, während eine große Datei hochgeladen wird, wird der Teilupload beibehalten. Wenn der Upload innerhalb von mehreren Stunden nach dem Anhalten oder Deaktivieren wieder aktiviert wird, wird der Upload von dort fortgesetzt, wo er aufgehört hat. Wenn der Upload jedoch nach mehreren Stunden wieder aktiviert wird, wird der Upload der großen Datei von Anfang an neu gestartet.

**Bekannte Probleme und Einschränkungen**

- Diese Einstellung verfügt über keine integrierte Drosselung basierend auf der aktuellen Bandbreitennutzung. Wenn Sie die Bandbreite für ein anderes Szenario maximieren müssen, deaktivieren Sie die Einstellung manuell. Hochladen werden angehalten, aber das Feature überwacht weiterhin neu hinzugefügte Dateien für Camera Roll. Aktivieren Sie den Upload erneut, wenn Sie bereit sind, den Upload fortzusetzen.
- Dieses Feature muss für jedes Benutzerkonto auf dem Gerät aktiviert sein und kann nur aktiv Dateien für den Benutzer hochladen, der derzeit auf dem Gerät angemeldet ist.
- Wenn Sie beim Ansehen der Uploadanzahl auf der Einstellungen Seite in Echtzeit Fotos oder Videos aufnehmen, beachten Sie, dass sich die Anzahl ausstehender Dateien möglicherweise erst ändert, wenn der Upload der aktuellen Datei abgeschlossen ist.
- Hochladen wird angehalten, wenn Ihr Gerät in den Ruhefall fällt oder ausgeschaltet ist. Um sicherzustellen, dass Ihre ausstehenden Uploads abgeschlossen sind, verwenden Sie das Gerät aktiv, bis die Einstellungen Seite "OneDrive ist auf dem neuesten Stand" lautet, oder passen Sie Ihre **Power & Standbyeinstellungen** an.
### <a name="added-support-for-some-telemetry-policies"></a>Unterstützung für einige Telemetrierichtlinien hinzugefügt

Die folgenden Telemetrierichtlinien werden jetzt auf der HoloLens 2 unterstützt:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Sowohl System\AllowTelemetry als auch System\ConfigureTelemetryOptInSettingsUx sollten zusammen verwendet werden, um vollständige Kontrolle über die Telemetrie und das Verhalten in der Einstellungen-App zu haben.

Verbesserungen und Fehlerbehebungen im Update:
- Behebt größere Videobeschädigungen bei der Farbkalibrierung.
- Behebt ein Problem, bei dem Text im Power-Menü abgeschnitten werden kann.
- Aktiviert die Unterstützung für die RequirePrivateStoreOnly-Richtlinie.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Juni 2021
- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Unterstützung für einige Telemetrierichtlinien hinzugefügt

Die folgenden Telemetrierichtlinien werden jetzt auf der HoloLens 2 unterstützt:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Sowohl System\AllowTelemetry als auch System\ConfigureTelemetryOptInSettingsUx sollten zusammen verwendet werden, um vollständige Kontrolle über die Telemetrie und das Verhalten in der Einstellungen-App zu haben.

Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, Version 1903 – Update juni 2021
- Build 18362.1116

Verbesserungen und Fehlerbehebungen im Update:
- Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unseren neuesten Build Windows Holographic, Version 21H1, auszuprobieren.

>[!IMPORTANT]
> Dieser Build wird nicht mehr gewartet.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, Version 21H1
- Build 20346.1002

Dieses Update enthält Features für zwei Zielgruppen: Features, die von jedem Benutzer auf einem Gerät vom Endbenutzer verwendet werden können, sowie neue Optionen für die Geräteverwaltung, die von IT-Administratoren konfiguriert werden können. In der folgenden Tabelle sind die Features angegeben, die für jede Zielgruppe relevant sind. Wenn Sie IT-Administrator sind, sehen Sie sich unsere Checkliste für [IT-Administratoren – Update](#it-admin---update-checklist)an.
>[!IMPORTANT]
>Zum Aktualisieren auf diesen Build müssen HoloLens 2 Geräte derzeit das Update vom Februar 2021 (Build 19041.1136) oder neuer ausführen. Wenn dieses Featureupdate nicht verfügbar ist, aktualisieren Sie zuerst Ihr Gerät, und versuchen Sie es erneut.

>[!NOTE]
>Derzeit unterstützt Microsoft HoloLens 2 monatliche Wartungsupdates (Fehler- und Sicherheitskorrekturen) für die folgenden Releases:
>- Windows Holographic, Version 20H2 (Build 19041.1128+)
>- Windows Holographic, Version 2004 (Build 19041.1103 und höher)
>- Windows Holographic, Version 1903 (Build 18362 und höher) 
>
> Mit der Einführung von Windows Holographic Version 21H1 **stellen wir monatliche Wartungsupdates für Windows Holographic Version 1903 ein.** Dadurch können wir uns auf neuere Releases konzentrieren und weiterhin wertvolle Verbesserungen bereitstellen. 


| Funktionsname                                              | Kurze Beschreibung                                                                      | Zielgruppe | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Neue Microsoft Edge](#introducing-the-new-microsoft-edge)  | Die neue, Chromium-basierte Microsoft Edge ist jetzt für HoloLens 2 verfügbar. | Endbenutzer | 
[WebXR und 360 Viewer](#webxr-and-360-viewer) | Probieren Sie immersive Weberfahrungen und die Wiedergabe von 360 Videos aus. | Endbenutzer | 
[Neue Einstellungen-App](#new-settings-app) | Die Legacy-Einstellungen-App wird durch eine aktualisierte Version mit neuen Features und Einstellungen ersetzt. | Endbenutzer |
[Farbkalibrierung anzeigen](#display-color-calibration) | Wählen Sie ein alternatives Farbprofil für Ihre HoloLens 2 Anzeigen aus. | Endbenutzer |
[Standard-App-Auswahl](#default-app-picker) | Wählen Sie aus, welche App für die einzelnen Datei- oder Linktypen gestartet werden soll. | Endbenutzer |
[Volumesteuerung pro App](#per-app-volume-control) | Steuern Sie das Volume auf App-Ebene unabhängig vom Systemvolume. | Endbenutzer |
[Installieren von Web-Apps](#install-web-apps) | Installieren Sie Web-Apps auf HoloLens 2, z. B. Microsoft Office, mit dem neuen Microsoft Edge Browser. | Endbenutzer |
[Wischen zum Eingeben](#swipe-to-type) | Verwenden Sie die Fingerspitze, um Wörter auf der holografischen Tastatur zu "wischen". | Endbenutzer |
[Menü "Energie" über "Start"](#power-menu-from-start) | Starten Sie das Gerät im Startmenü neu, und fahren HoloLens herunter. | Endbenutzer |
[Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind](#multiple-users-listed-on-sign-in-screen) | Zeigen Sie mehrere Benutzerkonten auf dem Anmeldebildschirm an. | Endbenutzer |
[Unterstützung externer USB-C-Mikrofone](#usb-c-external-microphone-support) | Verwenden Sie USB-C-Mikrofone für Apps und/oder Remote Assist. | Endbenutzer |
[Automatische Anmeldung von Besucher für Kioske](#visitor-auto-logon-for-kiosks) | Aktiviert die automatische Anmeldung bei Besucherkonten, die für Kioskmodi verwendet werden sollen. | IT-Administrator |
[Neue AUMIDs für neue Apps im Kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs für neue Einstellungen und Edge-Apps. | IT-Administrator |
[Verbesserte Übergabe von Fehlern im Kioskmodus](#kiosk-mode-behavior-changes-for-handling-of-failures) | Im Kioskmodus wird vor dem leeren Startmenü nach Global Assigned Access (Globaler zugewiesener Zugriff) sucht. | IT-Administrator |
[New SettingsURIs for Page Einstellungen Visibility](#new-settings-uris-for-page-settings-visibility) | Über 20 neue SettingsURIs für Einstellungen/PageVisibilityList-Richtlinie. | IT-Administrator |
[Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app) | Festlegen des Fallbackdiagnoseverhaltens in Einstellungen App. | IT-Administrator |
[Freigeben von Geräten in der Nähe](#share-things-with-nearby-devices) | Freigeben von Dateien oder URLs von einem HoloLens auf einem PC. | Alle |
[Neue Diagnoseverfolgungen für das Betriebssystem](#new-os-diagnostic-traces) | Neue Problembehandlung in Einstellungen Betriebssystemupdates. | IT-Administrator |
[Übermittlungsoptimierung Preview](#delivery-optimization-preview) | Reduzieren Sie den Bandbreitenverbrauch für Downloads von HoloLens Geräten. | IT-Administrator |

Sehen Sie sich die zugehörigen Versionshinweise an:

- [Besuchen Sie das HoloLens Emulator Archiv.](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365-Leitfäden](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Einführung in die Microsoft Edge

![Animation des Legacy-Microsoft Edge-Logos zu einem neuen Microsoft Edge Logo](images/new-edge.gif)

Die neue Microsoft Edge übernimmt das open [source Chromium projekt,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) um eine bessere Kompatibilität für Kunden und eine geringere Fragmentierung des Webs für Webentwickler zu schaffen.

> [!IMPORTANT]
> Diese neue Microsoft Edge ersetzt automatisch legacy-Microsoft Edge, die in neuen Releases [nicht](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) mehr unterstützt wird.

![Screenshot Microsoft Edge neuen Version](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Starten des neuen Microsoft Edge

Der neue Microsoft Edge ![Symbol für Microsoft Edge-App](images/new_edge_logo.png) (dargestellt durch ein blaues und grünes Swirlsymbol) wird an den -Startmenü und wird automatisch gestartet, wenn Sie einen Weblink aktivieren.

> [!NOTE]
> Wenn Sie die neue Microsoft Edge auf HoloLens 2 starten, werden Ihre Einstellungen und Daten aus legacy-Microsoft Edge. Wenn Sie legacy-Microsoft Edge nach dem Start der neuen Microsoft Edge weiterhin verwenden, werden diese neuen Daten nicht von legacy Microsoft Edge mit dem neuen Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurieren von Richtlinieneinstellungen für die neue Microsoft Edge

Die neue Microsoft Edge bietet IT-Administratoren einen viel umfassenderen Satz von Browserrichtlinien für HoloLens 2, als zuvor mit Legacy-Microsoft Edge.

Im Folgenden finden Sie einige hilfreiche Ressourcen, um mehr über das Verwalten von Richtlinieneinstellungen für die neue Microsoft Edge:

- [Konfigurieren Microsoft Edge Richtlinieneinstellungen mit Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Vorgängerversion von Microsoft Edge zum Microsoft Edge der Richtlinienzuordnung](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome zum Microsoft Edge der Richtlinienzuordnung](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Vollständige [Microsoft Edge Enterprise dokumentation](/deployedge/)

> [!IMPORTANT]
> Aufgrund der Menge an Browserrichtlinien, die von der neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie auf HoloLens 2. Wir haben jedoch getestet und bestätigt, dass das neue Microsoft Edge-Äquivalent jeder Legacy-Microsoft Edge-Richtlinie, die zuvor für HoloLens 2 unterstützt wurde, wie erwartet funktioniert. Weitere [Vorgängerversion von Microsoft Edge sie Microsoft Edge,](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) um die neue Microsoft Edge-Entsprechung jeder legacy-Microsoft Edge-Browserrichtlinie zu finden, die Sie mit HoloLens 2.
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
- Installieren von Erweiterungen (teilen Sie uns dies mit, wenn Sie Erweiterungen verwenden, die nicht ordnungsgemäß auf dem HoloLens 2)
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

- Die Bildschirmlupevorschau in der holografischen Tastatur wurde für die neue Microsoft Edge. Wir hoffen, dieses Feature in einem zukünftigen Update wieder aktivieren zu können, sobald die Vergrößerung ordnungsgemäß funktioniert.
- Audiodaten werden möglicherweise aus dem falschen Browserfenster abspielt, wenn ein anderes Browserfenster geöffnet und aktiv ist. Sie können dieses Problem beheben, indem Sie das andere aktive Fenster schließen, das keine Audiowiedergabe verwenden soll.
- Wenn Sie Audiodaten aus einem Browserfenster im [Modus "Folge mir"](hololens2-basic-usage.md#follow-me-stop-following)wieder geben, wird die Audiowiedergabe fortgesetzt, wenn Sie den Modus "Follow me" deaktivieren. Sie können dieses Problem beheben, indem Sie die Audiowiedergabe beenden, bevor Sie den Modus "Follow me" deaktivieren, oder indem Sie das Fenster mit der **Schaltfläche X** schließen.
- Die Interaktion mit aktiven Microsoft Edge Fenstern kann dazu führen, dass andere 2D-App-Fenster unerwartet inaktiv werden. Sie können diese Fenster reaktivieren, indem Sie erneut mit ihnen interagieren.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-Kanäle

Das Microsoft Edge stellt der Edge Insider-Community drei Vorschaukanäle zur Verfügung: Beta, Dev und Canary. Durch die Installation eines Vorschaukanals wird die veröffentlichte Version von Microsoft Edge auf Ihrem HoloLens 2 nicht deinstalliert, und Sie können mehrere gleichzeitig installieren. 

Besuchen Sie [die Microsoft Edge Insider-Homepage,](https://www.microsoftedgeinsider.com) um mehr über die Edge Insider-Community zu erfahren. Weitere Informationen zu den verschiedenen Edge Insider-Kanälen und den ersten Schritte finden Sie auf der [Downloadseite von Edge Insider.](https://www.microsoftedgeinsider.com/download)

Es gibt mehrere Methoden zum Installieren von Microsoft Edge Insider-Kanälen für HoloLens 2:

**Direkte Installation auf dem Gerät (derzeit nur für nicht verwaltete Geräte verfügbar)**
  1. Besuchen Sie auf Ihrem HoloLens 2 die [Edge Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie die Schaltfläche Download for HoloLens 2 (Herunterladen **für HoloLens 2)** für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Starten Sie die heruntergeladene MSIX-Datei aus der Edge-Downloadwarteschlange oder aus dem Ordner "Downloads" Ihres Geräts (mithilfe des Datei-Explorers).
  1. [Das App-Installationsprogramm](app-deploy-app-installer.md) wird gestartet.
  1. Wählen Sie die Schaltfläche **Installieren** aus.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der **Alle Apps** Liste der Startmenü.

**Installation über PC mit Windows Geräteportal (erfordert, dass der [Entwicklermodus](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) auf HoloLens 2 aktiviert ist)**
  1. Besuchen Sie auf Ihrem PC die [Edge Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie die **Dropdownpfeilschaltfläche** neben der Schaltfläche "Download for Windows 10" für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Wählen Sie im Dropdownmenü **HoloLens 2** aus.
  1. Speichern Sie die MSIX-Datei im Ordner "Downloads" Ihres PCs (oder in einem anderen Ordner, den Sie leicht finden können).
  1. Verwenden Sie [Windows Geräteportal](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC, um die heruntergeladene MSIX-Datei auf HoloLens 2 zu installieren.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der **Alle Apps** Liste der Startmenü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Verwenden von WDAC zum Blockieren neuer Microsoft Edge

Für IT-Administratoren, die ihre [WDAC-Richtlinie](windows-defender-application-control-wdac.md) aktualisieren möchten, um die neue Microsoft Edge App zu blockieren, müssen Sie Ihrer Richtlinie Folgendes hinzufügen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Verwalten von Endpunkten für die neue Microsoft Edge

Für einige Umgebungen gelten möglicherweise Netzwerkeinschränkungen, die berücksichtigt werden müssen. Aktivieren Sie [diese Microsoft-Endpunkte,](/deployedge/microsoft-edge-security-endpoints) um eine reibungslose Benutzererfahrung mit dem neuen Edge sicherzustellen.

Erfahren Sie mehr über die derzeit [verfügbaren Endpunkte für HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Installieren von Web-Apps
 > [!Note]
>Ab [Windows Holographic, Version 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)ist die Office Web-App nicht mehr vorinstalliert.

Sie können den neuen Edge verwenden, um Web-Apps zusammen mit Microsoft Store Apps zu installieren. Beispielsweise können Sie die Microsoft Office Web-App installieren, um Dateien anzuzeigen und zu bearbeiten, die auf SharePoint oder OneDrive gehostet werden. Um die Office-Web-App zu installieren, besuchen https://www.office.com Sie die Schaltfläche App Available **(App verfügbar)** oder **Install Office (Office installieren)** in der Adressleiste. Wählen Sie **Installieren** aus, um dies zu bestätigen.

> [!IMPORTANT]
> Office Web-App-Funktionalität ist nur verfügbar, wenn Ihre HoloLens 2 über eine aktive Internetverbindung verfügt.

### <a name="webxr-and-360-viewer"></a>WebXR und 360 Viewer

Die neue Microsoft Edge enthält Unterstützung für WebXR. Dies ist der neue Standard für die Erstellung immersiver Weberfahrungen (wobei WebVR ersetzt wird). Viele immersive Weberfahrungen wurden im Hinblick auf VR entworfen (sie ersetzen Ihr Sichtfeld durch eine virtuelle Umgebung), aber diese Erfahrungen werden auch von HoloLens 2 unterstützt. Der WebXR-Standard ermöglicht auch erweiterte und immersive Mixed Reality-Weberfahrungen, die Ihre physische Umgebung verwenden. Da Entwickler mehr Zeit mit WebXR verbringen, gehen wir davon aus, dass neue immersive Augmented- und Mixed Reality-Erfahrungen für HoloLens 2 Kunden eintreffen werden!

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
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR-Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Verwenden von 360 Viewer

1. Navigieren Sie zu einem 360-Grad-Video auf YouTube.
1. Wählen Sie im Videoframe die Mixed Reality-Headset-Schaltfläche aus:

    ![Schaltfläche zum Aktivieren von 360 Viewer](images/enter-360-viewer.jpg)

1. Wenn Sie zum ersten Mal versuchen, 360 Viewer für eine bestimmte Domäne zu starten, fordert der Browser die Zustimmung zur Eingabe einer immersiven Ansicht an. Wählen Sie **Zulassen** aus.
1. [Tippen Sie](hololens2-basic-usage.md#select-using-air-tap) in die Luft, um die Wiedergabesteuerelemente aufzuführen. Verwenden Sie [Handlicht und Luftabzweigung,](hololens2-basic-usage.md#select-using-air-tap) um zu spielen/anzuhalten, Vorwärts/Zurück zu überspringen, Untertitel ein-/auszuschalten oder die Benutzeroberfläche zu beenden (wodurch die immersive Ansicht beendet wird). Die Wiedergabesteuerelemente werden nach einigen Sekunden Inaktivität nicht mehr angezeigt.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Top WebXR and 360 Viewer known issues (Top WebXR und 360 Viewer bekannte Probleme)
- Abhängig von der Komplexität der WebXR-Benutzeroberfläche kann die Framerate fallen oder stuttern.
- Die Unterstützung für artikulierte Handverbindungen in WebXR ist standardmäßig nicht aktiviert. Entwickler können die Unterstützung über aktivieren, `edge://flags` indem sie "WebXR Hand Input" aktivieren.
- 360 Videos von anderen Websites als YouTube funktionieren möglicherweise nicht wie erwartet.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Bereitstellen von Feedback zu WebXR und 360 Viewer

Teilen Sie feedback and bugs mit unserem Team über das Feature **Feedback senden** in der neuen Microsoft Edge.

### <a name="new-settings-app"></a>Neue Einstellungen-App

Mit diesem Release führen wir eine neue Version der Einstellungen-App ein. Die neue Einstellungen-App enthält neue Features und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Power & Standbymodus, Netzwerk & Internet, Apps, Konten, Erleichterte Bedienung und mehr.

> [!NOTE]
> Da sich die neue Einstellungen-App von der älteren Einstellungen-App unterscheidet, werden alle Einstellungen Fenster, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Homepage der neuen Einstellungen-App](images/new-settings-app.png)

**Neue Features und Einstellungen**
- Einstellungen Suchen: Suchen Sie auf der Startseite des Einstellungen nach Einstellungen, indem Sie Schlüsselwörter oder den Namen der Einstellung verwenden.
- System > Sound:
  - Eingabe- und Ausgabeaudiogeräte: Wählen Sie unabhängig Ihre Eingabe- und Ausgabeaudiogeräte aus (z. B. audio über Bluetooth Oder verwenden Sie ein USB-C-Mikrofon für die Audioeingabe).
    > [!NOTE]
    > Bluetooth Mikrofone werden von HoloLens 2 nicht unterstützt.
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
- Erleichterte Bedienung: Ändern der Textgröße und einiger visueller Effekte.

**Bekannte Probleme**
- Zuvor platzierte Einstellungen Fenster werden entfernt (siehe Hinweis oben).
- Sie können Ihr Gerät nicht mehr mit der Einstellungen App umbenennen. IT-Administratoren können Geräte mithilfe des [Windows Autopilot für HoloLens 2](hololens2-autopilot.md) Gerätenamenvorlage oder des Knotens MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName umbenennen.
- Auf der Seite Ethernet wird jederzeit ein virtuelles Ethernet-Gerät ("UsbNcm") angezeigt.
- Der Akkuverbrauch für die neue Microsoft Edge ist aufgrund ihrer Art als Win32-Desktopanwendung, die von einer UWP-Adapterebene unterstützt wird, möglicherweise nicht korrekt (es wird in Kürze keine Korrektur erwartet).

#### <a name="display-color-calibration"></a>Farbkalibrierung anzeigen



Mit dieser neuen Einstellung können Sie ein alternatives Farbprofil für Ihre HoloLens 2 Anzeigen auswählen. Dies kann dazu beitragen, dass Farben genauer angezeigt werden, insbesondere bei niedrigeren Helligkeitsstufen der Anzeige. Die Farbkalibrierung für die Anzeige finden Sie in der Einstellungen-App auf der Seite System > Kalibrierung.

> [!NOTE]
> Da diese Einstellung ein neues Farbprofil in Ihrer Anzeigefirmware speichert, handelt es sich um eine Geräteeinstellung (die nicht für jedes Benutzerkonto eindeutig ist).

##### <a name="how-to-use-display-color-calibration"></a>Verwenden der Kalibrierung von Anzeigefarben

1. Starten  Sie die Einstellungen-App, und navigieren Sie zu **System > Calibration**.
1. Wählen **Sie unter Farb kalibrierung anzeigen** die Schaltfläche Farb **kalibrierung der Anzeige** ausführen aus.
1. Die Kalibrierung der Anzeigefarbe wird gestartet, und Sie werden dazu ermutigen, sicherzustellen, dass sich Ihr Visor an der richtigen Position befindet.
1. Nachdem Sie die Anweisungsdialogfelder geöffnet haben, wird die Anzeige automatisch auf eine Helligkeit von 30 % abgeblendet.
    > [!TIP]
    > Wenn Sie Probleme haben, die abgeblendete Szene in Ihrer Umgebung zu sehen, können Sie die Helligkeitsstufe von HoloLens 2 mithilfe der Helligkeitsschaltflächen auf der linken Seite des Geräts manuell anpassen.
1. Wählen Sie die Schaltflächen 1 bis 6 aus, um jedes Farbprofil sofort auszuprobieren, und suchen Sie eins, das für Ihre Augen am besten aussieht (dies bedeutet in der Regel das Profil, das der Szene hilft, am neutralsten zu erscheinen, und das Graustufenmuster und die Skintons sehen wie erwartet aus.)

    ![Anzeigen der Farb kalibrierungsszene](images/color-cal-ui.png)
    
1. Wenn Sie mit dem ausgewählten Profil zufrieden sind, wählen Sie die Schaltfläche Save **& Exit (Beenden)** aus.
1. Wenn Sie keine Änderungen vornehmen möchten, wählen Sie die Schaltfläche Abbrechen **& Beenden** aus, und Ihre Änderungen werden zurückgewollt.

> [!TIP]
> Im Folgenden finden Sie einige hilfreiche Tipps, die Sie bei der Verwendung der Einstellung für die Kalibrierung der Anzeigefarbe beachten sollten:
> - Sie können die Farb kalibrierung der Anzeige immer dann Einstellungen, wenn Sie möchten.
> - Wenn jemand auf dem Gerät die Einstellung zuvor zum Ändern von Farbprofilen verwendet hat, wird das Datum bzw. die Uhrzeit der letzten Änderung auf der Einstellungen angezeigt.
> - Wenn Sie die Farb kalibrierung der Anzeige erneut ausführen, wird das zuvor gespeicherte Farbprofil hervorgehoben, und Profil 0 wird nicht angezeigt (da Profil 0 das ursprüngliche Farbprofil der Anzeige darstellt).
> - Wenn Sie auf das ursprüngliche Farbprofil der Anzeige zurückgesetzt werden möchten, können Sie dies auf der Einstellungen-Seite tun (siehe Zurücksetzen des [Farbprofils](#how-to-reset-color-profile)).

##### <a name="how-to-reset-color-profile"></a>Zurücksetzen des Farbprofils 

Wenn Sie nicht mit dem benutzerdefinierten Farbprofil in Ihrem HoloLens 2 sind, können Sie das ursprüngliche Farbprofil des Geräts wiederherstellen:
1. Starten  Sie die Einstellungen-App, und navigieren Sie zu **System > Calibration**.
1. Wählen **Sie unter Farb kalibrierung anzeigen** die Schaltfläche Auf **Standardfarbprofil zurücksetzen** aus.
1. Wenn das Dialogfeld geöffnet wird, wählen Sie **Neu starten** aus, wenn Sie bereit sind, HoloLens 2 und Ihre Änderungen anzuwenden.

#### <a name="top-display-color-calibration-known-issues"></a>Top display color calibration known issues (Bekannte Probleme bei der Farberb kalibrierung auf der Obersten Anzeige

- Auf der Einstellungen seite ist die Statuszeichenfolge, die Sie darüber informiert, wann das Farbprofil zuletzt geändert wurde, veraltet, bis Sie diese Seite erneut Einstellungen.
    - Problemumgehung: Wählen Einstellungen Seite aus, und wählen Sie dann erneut die Seite Kalibrierung aus.

#### <a name="default-app-picker"></a>Standard-App-Auswahl

Wenn Sie einen Link aktivieren oder einen Dateityp mit mehr als einer installierten App öffnen, die diesen unterstützt, wird ein neues Fenster geöffnet, in dem Sie aufgefordert werden, auszuwählen, welche installierte App den Datei- oder Linktyp verarbeiten soll. In diesem Fenster können Sie auch festlegen, dass die ausgewählte App die Datei oder den Linktyp "Once" oder "Always" behandelt.

Wenn Sie "Immer" auswählen, aber später ändern möchten, welche App eine bestimmte Datei oder einen bestimmten Linktyp verarbeitet, können Sie Ihre gespeicherten Standardwerte in Einstellungen > **Apps zurücksetzen.** Scrollen Sie nach unten auf  der Seite, und wählen Sie unter "Standard-Apps für Dateitypen" und/oder "Standard-Apps für Linktypen" die Schaltfläche Löschen aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardeinstellungen einzelner Dateitypen nicht zurücksetzen.

#### <a name="per-app-volume-control"></a>Volumensteuerung pro App

In diesem Windows können Benutzer nun die Volumeebene jeder App manuell anpassen. Dies ermöglicht es Benutzern, sich besser auf die Apps zu konzentrieren, die sie benötigen, oder besser zu hören, wenn sie mehrere Apps verwenden. Beispielsweise muss das Volumen einer App beim Aufrufen einer anderen Person zur Remoteunterstützung in einer anderen App heruntergefahren werden.

Navigieren Sie zum Festlegen der Lautstärke einer einzelnen App zu **Einstellungen**  ->  **System** Sound, und wählen Sie unter Erweiterte Soundoptionen die Option App-Volume und  ->   **Geräteeinstellungen aus.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Wischen zum Eingeben

Einige Kunden finden es schneller, auf virtuellen Tastaturen zu "tippen", indem sie die Form des Worts wischen, das sie eingeben möchten, und wir zeigen diese Funktion für die holografische Tastatur in der Vorschau an. Sie können ein Wort nach dem anderen wischen, indem Sie die Fingerspitze durch die Ebene der holografischen Tastatur übergeben, die Form des Worts wischen und dann die Fingerspitze von der Tastaturebene abziehen. Sie können Nach-oben-Wörter wischen, ohne die Abstandsleiste drücken zu müssen, indem Sie den Finger von der Tastatur zwischen Wörtern entfernen. Sie werden wissen, dass das Feature funktioniert, wenn Sie einen Wischpfad sehen, der der Bewegung Des Fingers auf der Tastatur folgt.

Beachten Sie, dass dieses Feature aufgrund der Natur einer holografischen Tastatur, bei der Sie keinen Widerstand gegen Ihren Finger haben (im Gegensatz zu einer Mobiltelefonanzeige), schwierig zu verwenden und zu mastern sein kann. 

### <a name="power-menu-from-start"></a>Menü "Energie" über "Start"

Ein neues Menü, mit dem sich der Benutzer abmelden, herunterfahren und das Gerät neu starten kann. Ein Indikator im HoloLens Startbildschirm, der zeigt, wann ein Systemupdate verfügbar ist.

#### <a name="how-to-use"></a>Verwendung

1. Öffnen Sie HoloLens Startbildschirm Startgeste, [oder](hololens2-basic-usage.md#start-gesture) sagen Sie "Gehe zu Start".

2. Beachten Sie das Auslassungszeichen (...) neben dem Benutzerprofilbild:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Wählen Sie das Benutzerprofilbild mit ihren Händen oder dem Sprachbefehl "Power" aus.

4. Ein Menü mit Optionen zum Abmelden, Neustarten oder Herunterfahren des Geräts wird angezeigt:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Wählen Sie die Menüoptionen zum Abmelden, Neustarten oder Herunterfahren Ihrer HoloLens. Die Option Abmelden ist möglicherweise nicht verfügbar, wenn das Gerät für ein einzelnes [Microsoft-Konto (MSA) oder ein lokales Konto eingerichtet ist.](hololens-identity.md)

6. Schließen Sie das Menü, indem Sie eine andere Stelle berühren oder die Startmenü mit der Startgeste schließen.

#### <a name="update-indicator"></a>Aktualisierungsindikator

Wenn ein Update verfügbar ist, wird das Symbol mit den Auslassungszeichen angezeigt, um anzugeben, dass bei einem Neustart das Update installiert wird. Die Menüoptionen ändern sich ebenfalls, um das Vorhandensein des Updates widerzubilden.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind

Zuvor wurde auf dem Bildschirm Anmelden nur der zuletzt angemeldete Benutzer sowie ein Einstiegspunkt "Anderer Benutzer" angezeigt. Wir haben Kundenfeedback erhalten, dass dies nicht ausreicht, wenn sich mehrere Benutzer beim Gerät angemeldet haben. Sie mussten weiterhin ihren Benutzernamen usw. erneut eingeben.

In diesem Windows-Build eingeführt:  Wenn Sie Auf der rechten Seite des PIN-Eingabefelds Anderer Benutzer auswählen, werden auf dem Bildschirm Anmelden mehrere Benutzer angezeigt, die sich zuvor beim Gerät angemeldet haben. Dadurch können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Anmeldeinformationen Windows Hello anmelden. Über die Schaltfläche Konto hinzufügen kann dem Gerät auch ein neuer Benutzer über die Seite Andere **Benutzer hinzugefügt** werden.

Im Menü Andere Benutzer zeigt die Schaltfläche Andere Benutzer den letzten Benutzer an, der sich am Gerät angemeldet hat. Wählen Sie diese Schaltfläche aus, um zum Anmeldebildschirm für diesen Benutzer zurückzukehren.

![Standardeinstellung des Anmeldebildschirms](./images/multiusers1.jpg)

<br>

![Anmeldebildschirm für andere Benutzer](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Unterstützung externer USB-C-Mikrofone

> [!IMPORTANT]
> Wenn Sie ein **USB-Mikrofon anschließen, wird** es nicht automatisch als Eingabegerät festgelegt. Beim Einstecken einer Reihe von USB-C-Anschlüssen werden Benutzer feststellen, dass die Audiodaten des Messgeräts automatisch an die Anschlüsse umgeleitet werden, aber das HoloLens-Betriebssystem priorisiert das interne Mikrofonarray über jedes andere Eingabegerät. **Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**

Benutzer können externe Mikrofone mit USB-C-Verbindung über den **Bereich Soundeinstellungen** auswählen. USB-C-Mikrofone können zum Aufrufen, Aufzeichnen usw. verwendet werden.

Öffnen  Sie die Einstellungen-App, und wählen Sie   >  **Systemsound aus.**

![Sound Einstellungen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Um externe Mikrofone mit **Remote Assist** verwenden zu können, müssen Benutzer auf den Link "Soundgeräte verwalten" klicken.
>
> Verwenden Sie dann die Dropdownliste, um das externe Mikrofon entweder auf **Standard oder** Kommunikations **default (Kommunikationseinstellung) zu setzen.** Die Auswahl **von Standard** bedeutet, dass das externe Mikrofon überall verwendet wird.
>
> Die Auswahl von **Kommunikations standard** bedeutet, dass das externe Mikrofon in Remote Assist und anderen Kommunikations-Apps verwendet wird, aber das HoloLens-Mikrofonarray kann weiterhin für andere Aufgaben verwendet werden.

![Verwalten von Soundgeräten](images/usbc-mic-2.png)

<br>

![Festlegen der Mikrofon-Standardeinstellung](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Was ist mit Bluetooth Mikrofonunterstützung?

Leider werden Bluetooth Mikrofone auf dem HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Problembehandlung bei USB-C-Mikrofonen

Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als Mikrofon als auch als *Lautsprecher* melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Sie eines dieser Mikrofone in HoloLens, kann der Sound verloren gehen. Glücklicherweise gibt es eine einfache Lösung.  

Legen **Einstellungen** Systemsound explizit die integrierten Lautsprecher  ->    ->   **(Analog Feature Audio Driver)** als **Standardgerät fest.** HoloLens sollten sich diese Einstellung auch dann merken, wenn das Mikrofon entfernt und später erneut verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatische Anmeldung von Besucher für Kioske

Mit diesem neuen Feature kann die automatische Anmeldung bei Besucherkonten für Kioskmodi verwendet werden.

Bei einer Nicht-AAD-Konfiguration, um ein Gerät für die automatische Anmeldung von Besucher zu konfigurieren:

1. Erstellen Sie ein Bereitstellungspaket, das:
    1. Konfiguriert **Laufzeiteinstellungen/AssignedAccess,** um Besucherkonten zu ermöglichen.
    1. Registriert das Gerät optional bei MDM **(Laufzeiteinstellungen/Arbeitsplatz/Registrierungen),** damit es später verwaltet werden kann.
    1. Erstellen Sie kein lokales Konto.
1. [Wenden Sie das Bereitstellungspaket an.](hololens-provisioning.md)

Bei einer AAD-Konfiguration können Benutzer ohne diese Änderung etwas ähnliches erreichen wie heute. Mit AAD verbundene Geräte, die für den Kioskmodus konfiguriert sind, können sich mit einer einzigen Schaltfläche vom Anmeldebildschirm aus bei einem Besucherkonto anmelden. Nach der Anmeldung beim Besucherkonto fordert das Gerät erst dann erneut zur Anmeldung auf, wenn der Besucher explizit über das Startmenü abmelden oder das Gerät neu gestartet wird.

Die automatische Anmeldung von Besucher kann über eine benutzerdefinierte [OMA-URI-Richtlinie verwaltet](/mem/intune/configuration/custom-settings-windows-10) werden:

- URI-Wert: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Richtlinie  | BESCHREIBUNG   | Configurations  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Ermöglicht es einem Besucher, sich automatisch bei einem Kiosk zu anmelden.   | 1 (Ja), 0 (Nein, Standard)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Verwenden der neuen Einstellungen- und Edge-Apps im Kioskmodus

Wenn Apps in [Kiosks](hololens-kiosk.md)eingeschlossen werden, fügt ein IT-Administrator die App häufig dem Kiosk hinzu, verwendet jedoch die App-Benutzermodell-ID (APP User Model ID, AUMID). Da sowohl die Einstellungen-App als auch Microsoft Edge App als neue Apps betrachtet werden und sich von den älteren Apps unterscheiden, müssen Kiosks, die AUMIDs für diese Apps verwenden, aktualisiert werden, um die neue AUMID zu verwenden.

Wenn Sie einen Kiosk ändern, um die neuen Apps einzuschließen, empfiehlt es sich, die neue AUMID hinzuzufügen und die alte zu belassen. Dies führt zu einem einfachen Übergang, wenn Benutzer das Betriebssystem aktualisieren und keine neuen Richtlinien erhalten müssen, um den Kiosk weiterhin wie vorgesehen zu verwenden.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Alte Einstellungen-App       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Neue Einstellungen-App       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Alte Microsoft Edge-App | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Neue Microsoft Edge-App | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Änderungen am Kioskmodusverhalten für die Behandlung von Fehlern

Wenn in älteren Builds ein Gerät über eine Kioskkonfiguration verfügt, bei der es sich um eine Kombination aus global zugewiesenem Zugriff und zugewiesenem Zugriff durch AAD-Gruppenmitglied handelt, wird dem Benutzer im Startmenü nichts[angezeigt,](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)wenn bei der Ermittlung der AAD-Gruppenmitgliedschaft ein Fehler aufgetreten ist.

Ab diesem Windows Release wird bei Ausfällen während des Kioskmodus der AAD-Gruppe ein Fallback auf die globale Kioskkonfiguration (falls vorhanden) ausgeführt.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Neue Einstellungen-URIs für Seiten-Einstellungen-Sichtbarkeit

In [Windows Holographic, Version 20H2 haben](hololens-release-notes.md#windows-holographic-version-20h2) wir die Richtlinie [Einstellungen/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) hinzugefügt, um die in der Einstellungen-App angezeigten Seiten einzuschränken. PageVisibilityList ist eine Richtlinie, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der System-Einstellungen-App sichtbar oder zugänglich sind, oder für alle Seiten mit Ausnahme der angegebenen Seiten.

Wenn Sie [Page Einstellungen Visibility](settings-uri-list.md)aufrufen, finden Sie Anweisungen zur Verwendung dieses CSP und die Liste der URIs, die in früheren Versionen verfügbar waren.

Wir erweitern die Liste der verfügbaren Einstellungen URIs, die IT-Administratoren verwalten können. Einige dieser URIs gelten für neu verfügbare Bereiche innerhalb der neuen Einstellungen-App. Wenn Sie Einstellungen/PageVisibilityList-Richtlinie verwenden, überprüfen Sie die folgende Liste, und passen Sie Ihre zulässigen oder blockierten Seiten nach Bedarf an.

> [!NOTE]
> **Veraltet: ms-settings:network-proxy**
>
> Eine Einstellungsseite ist in diesen neueren Builds veraltet. Die alte Seite **Netzwerk-&**  >  **Internetproxy** ist nicht mehr als globale Einstellung verfügbar. Die neuen Proxyeinstellungen pro Verbindung finden Sie unter **Netzwerk &**  >  **Internet-WLAN-Eigenschaften**  >   oder **Netzwerk-&**  >  **Internet-Ethernet-Eigenschaften.**  >  

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
| System > Sound > App-Lautstärke und Geräteeinstellungen | `ms-settings:apps-volume`                          |
| System > Sound > Verwalten von Soundgeräten              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Update & Security > Reset & Recovery               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualisierte URIs

Zuvor haben die folgenden beiden URIs einen Benutzer nicht direkt auf die angegebenen Seiten verwiesen, sondern nur die Hauptseite für Updates blockiert. Die folgenden Elemente wurden aktualisiert, um zu ihren Seiten zu leiten:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurieren der Fallbackdiagnose über Einstellungen App

In Einstellungen App kann ein Benutzer nun das Verhalten der [Fallbackdiagnose](hololens-diagnostic-logs.md)konfigurieren. Navigieren Sie auf der Einstellungen-App zur Seite   ->  **Datenschutzproblembehandlung,** um diese Einstellung zu konfigurieren.

> [!NOTE]
> Wenn eine MDM-Richtlinie für das Gerät konfiguriert ist, kann der Benutzer dieses Verhalten nicht außer Kraft setzen.  

### <a name="share-things-with-nearby-devices"></a>Freigeben von Dingen für Geräte in der Nähe

Teilen Sie Dinge mit nahezu Windows 10 Geräten, einschließlich PCs und anderen HoloLens 2 Geräten. Sie können es in **Einstellungen**  ->  **freigegebenen**  ->  **Systemerfahrungen** ausprobieren, um Dateien oder URLs von einem HoloLens auf einem PC freizugeben. Weitere Informationen zum Freigeben von [Geräten in der Nähe finden Sie in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Dieses Feature kann über [Connectivity/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)verwaltet werden.

### <a name="new-os-diagnostic-traces"></a>Neue Diagnoseablaufverfolgungen für das Betriebssystem

Zusätzlich zu den vorherigen Problembehandlungen in der Einstellungen-App wurde eine neue Problembehandlung hinzugefügt, und die neue Einstellungen-App für Betriebssystemupdates wurde hinzugefügt. Navigieren Sie zu **Einstellungen**  ->  **&amp; Updatesicherheitsproblembehandlung**  >    >  **Windows Update,** und wählen **Sie Starten** aus. Dadurch können Sie Ablaufverfolgungen erfassen, während Sie Ihr Problem mit Betriebssystemupdates reproduzieren, um die Problembehandlung für Ihre IT oder Ihren Support zu verbessern.

### <a name="delivery-optimization-preview"></a>Übermittlungsoptimierung Preview

Mit diesem HoloLens Update ermöglicht Windows Holographic for Business Übermittlungsoptimierungseinstellungen, um den Bandbreitenverbrauch für Downloads von mehreren HoloLens Geräten zu reduzieren. Eine umfassendere Beschreibung dieser Funktionalität zusammen mit der empfohlenen Netzwerkkonfiguration finden Sie hier: [Übermittlungsoptimierung für Windows 10 Updates.](/windows/deployment/update/waas-delivery-optimization)

Die folgenden Einstellungen werden als Teil der Verwaltungsoberfläche aktiviert und [können über Intune konfiguriert werden:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Einige Einschränkungen zu diesem Vorschauangebot:

- HoloLens Unterstützung ist in dieser Vorschauversion nur auf Betriebssystemupdates beschränkt.
- Windows Holographic for Business unterstützt nur HTTP-Downloadmodi und Downloads von einem [Microsoft Connected Cache-Endpunkt.](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Peer-zu-Peer-Downloadmodi und Gruppenzuweisungen werden derzeit für HoloLens Geräte nicht unterstützt.
- HoloLens unterstützt keine Bereitstellungs- oder Übermittlungsoptimierung für Windows Server Update Services Endpunkte.
- Für die Problembehandlung ist entweder eine Diagnose auf dem Connected Cache-Server oder das Sammeln einer Ablaufverfolgung auf HoloLens auf HoloLens über **Einstellungen**  >  **Update &**  >   **Sicherheitsproblembehandlung**  >   **Windows Update** erforderlich.

### <a name="it-admin---update-checklist"></a>IT-Administrator – Checkliste aktualisieren

Diese Prüfliste hilft Ihnen, die neuen Elemente zu kennen, die in diesem Featureupdate hinzugefügt werden und sich auf Ihre aktuellen Geräteverwaltungskonfigurationen auswirken können, oder neue Features, die Sie möglicherweise verwenden möchten.

#### <a name="updates-to-kiosk-mode"></a>Updates für den Kioskmodus

✔️ Neue [**AUMIDs für neue Apps im Kioskmodus:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Wenn Sie zuvor entweder die Einstellungen-App oder Microsoft Edge-App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, neue [AUMIDs für neue](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Apps im Kioskmodus weiter unten zu lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin die Einstellungen-App in Ihrem Kiosk haben oder die neue Microsoft Edge enthalten. Diese Änderungen können jetzt vorgenommen und auf allen Geräten bereitgestellt werden, um einen reibungsloseren Übergang beim Update zu ermöglichen.

✔️ automatische Anmeldung von Besucher [**für Kioske:**](#visitor-auto-logon-for-kiosks) 

Besucher können jetzt automatisch an einem Kiosk angemeldet werden. Dieses Verhalten ist standardmäßig aktiviert, kann aber verwaltet und deaktiviert werden.

✔️ [**fehlerbearbeitete Fehler im Kioskmodus:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Wenn die AAD-Gruppenmitgliedschaft eines angemeldeten AAD-Benutzers nicht erfolgreich bestimmt wurde, wird die globale Kioskkonfiguration für das Startmenü verwendet (sofern vorhanden). Andernfalls wird dem Benutzer ein leeres Startmenü angezeigt. Das leere Startmenü ist zwar keine Konfiguration, die Sie direkt festlegen können, aber diese neue Behandlung kann Ihre Supportabteilung darüber informieren, wenn Sie Kiosks verwenden, da dies möglicherweise für Ihre Konfigurationen gilt oder Sie neue Anpassungen an Ihren zugewiesenen Zugriffskonfigurationen vornehmen möchten.

#### <a name="updates-to-page-settings-visibility"></a>Aktualisierungen der Sichtbarkeit Einstellungen Seitenaufrufs

✔️ New [**Einstellungen URIs for Page Einstellungen Visibility**](#new-settings-uris-for-page-settings-visibility)

Wenn Sie derzeit [Page Einstellungen Visibility](settings-uri-list.md) verwenden, sollten Sie Anpassungen an Ihren vorhandenen URIs vornehmen, die Sie entweder zugelassen oder blockiert haben.

#### <a name="updates-for-your-wdac-policy"></a>Updates für Ihre WDAC-Richtlinie
✔️ Wenn Sie zuvor die Microsoft Edge WDAC blockiert haben, sollten Sie Ihre WDAC-Richtlinie aktualisieren. Sehen Sie sich die folgenden Informationen an, und verwenden Sie den bereitgestellten Beispielcode.
#### <a name="enable-new-endpoints-for-edge"></a>Aktivieren neuer Endpunkte für Edge
✔️ Wenn Sie über eine Infrastruktur verfügen, die das Konfigurieren von Netzwerkendpunkten wie Proxy oder Firewall umfasst, aktivieren Sie diese neuen Endpunkte für die neue Microsoft Edge App.

#### <a name="newly-configurable-items"></a>Neu konfigurierbare Elemente

✔️ [Fallbackdiagnose konfigurieren:](#configuring-fallback-diagnostics-via-settings-app)Sie können konfigurieren, ob und wer die Fallbackdiagnose erfassen darf.

✔️ Freigeben[von Inhalten mit Geräten in](#share-things-with-nearby-devices)der Nähe: Sie können die neue Funktion für die Gemeinsame Nutzung in der Nähe deaktivieren.

✔️ Konfigurieren [von Richtlinieneinstellungen für die](#configuring-policy-settings-for-the-new-microsoft-edge)neue Microsoft Edge: Überprüfen Sie die neu verfügbaren Konfigurationen für Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Neues Diagnosetool

✔️[Diagnoseverfolgungen für das neue Betriebssystem:](#new-os-diagnostic-traces)Sammeln Sie Protokolle im Zusammenhang mit Betriebssystemupdates.

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:

- [Die Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics) enthält auch zusätzliche Geräteinformationen für Seriennummer und Betriebssystemversion.
- Behebt ein Problem bei der Bereitstellung von Line-of-Business-Anwendungen über Laufzeitbereitstellungspakete.
- Behebt ein Problem im Rahmen der Berichterstellung zum Installationsstatus von Line-of-Business-Anwendungen.
- Behebt ein Problem im Umfall der Persistenz neuer App-Pakete bei Gerätezurücksetzungen.
- Behebt ein Problem, das dazu führen kann, dass falsche Symbole in Edge für japanische Kunden typiert werden.
- Verbessert die Resilienz von Betriebssystemupdates für vorinstallierte Apps wie Edge. 
- Behebt eine Updatezuverlässigkeit, die sich auf die Installation Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Mai 2021
- Build 19041.1146

Verbesserungen und Fehlerbehebungen im Update:
- Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, Version 1903 – Update mai 2021
- Build 18362.1110

Verbesserungen und Fehlerbehebungen im Update:
- Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. **Dieser Build empfängt keine monatlichen Dienstupdates mehr.** Wir empfehlen Ihnen, unseren neuesten Build, Windows Holographic, Version 21H1, auszuprobieren.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, Version 20H2 – Update vom April 2021
- Build 19041.1144

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem im Rahmen der Berichterstellung zum Installationsstatus von Line-of-Business-Anwendungen.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, Version 1903 – Update april 2021
- Build 18362.1108

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem, bei dem Einstellungen App abstürzt, wenn versucht wird, ein Kennwort für ein lokales Konto zu ändern.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, Version 20H2 – Update vom März 2021
- Build 19041.1140

Verbesserungen und Fehlerbehebungen im Update:

- Kunden, die AdvancedPhotoCapture oder LowLagPhotoCapture zum Erfassen von Fotos mit HoloLens 2 verwenden, können nun die Kamerapose bis zu 3 Sekunden nach der Aufnahme des Fotos abrufen.
- Behebung eines Arbeitsspeicherverlusts in Geräteportal Service, das zu einer erhöhten Speicherauslastung durch den Dienst führte, was dazu führte, dass andere Anwendungen nicht genügend Arbeitsspeicher zuordnen.
- Es wurde ein Problem behoben, bei dem sich Benutzer, die für den gestufigen Rollout registriert sind, nicht beim Gerät anmelden konnten.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, Version 1903 – Update vom März 2021
- Build 18362.1102

Verbesserungen und Fehlerbehebungen im Update:

- Behebung eines Arbeitsspeicherverlusts in Geräteportal Service, das zu einer erhöhten Speicherauslastung durch den Dienst führte, was dazu führte, dass andere Anwendungen nicht genügend Arbeitsspeicher zuordnen.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Februar 2021
- Build 19041.1136

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem bei der anfänglichen Geräteeinrichtung und beim Speichern von App-Updates.
- Behebt ein Problem mit Upgrades und Flügen für HoloLens Versionen.
- Nicht verwendete vorinstallierte Zertifikate wurden aus dem eSIM-Stammspeicher von HoloLens entfernt.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, Version 1903 – Update vom Februar 2021
- Build 18362.1098

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Januar 2021
- Build 19041.1134

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Leistung beim Starten, Fortsetzen und Wechseln von Benutzern, wenn viele Benutzer auf dem Gerät sind.
- Arm32-Unterstützung für den [Research-Modus wurde hinzugefügt.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, Version 1903 – Update vom Januar 2021
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

Sie können Apps jetzt installieren, ohne den Entwicklermodus zu aktivieren oder Geräteportal.  Laden Sie einfach (über USB oder über Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie im Datei-Explorer zum Appx-Bundle, um zum Starten der Installation aufgefordert zu werden.  Alternativ können Sie [eine Installation über eine Webseite initiieren.](/windows/msix/app-installer/installing-windows10-apps-web)  Genau wie Apps, die Sie über die Microsoft Store installieren oder mithilfe der BEREITSTELLUNGsfunktion für branchenseitige Apps [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) von MDM sideload verwenden, müssen Apps digital mit dem Signierungstool signiert werden, und das zertifikat, das zum Signieren verwendet wird, muss vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die App bereitgestellt werden kann. [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Installationsanweisungen für die Anwendung.**

1.  Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet gilt.
1.  Stellen Sie sicher, HoloLens 2 gerät eingeschaltet und mit Ihrem PC verbunden ist.
1.  Stellen Sie sicher, dass Sie beim HoloLens 2 angemeldet sind.
1.  Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie Yourapp.appxbundle in "IhrGerätename\Interner Storage\Downloads".   Nachdem Sie das Kopieren Ihrer Datei abgeschlossen haben, können Sie ihr Gerät trennen.
1.  Öffnen Sie HoloLens 2-Gerät das Startmenü, wählen Sie Alle Apps aus, und starten Sie die Datei-Explorer-App.
1.  Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie im linken Bereich der App zuerst Dieses Gerät auswählen und dann zu Downloads navigieren.
1.  Wählen Sie die Datei yourapp.appxbundle aus.
1.  Die App-Installer wird gestartet. Wählen Sie die Schaltfläche Installieren aus, um Ihre App zu installieren.
Die installierte App wird nach Abschluss der Installation automatisch gestartet.

Beispiel-Apps finden Sie [in Windows universellen Beispielen GitHub,](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) um diesen Flow zu testen.

Informieren Sie sich über den [vollständigen](app-deploy-app-installer.md)Prozess der Installation von Apps auf HoloLens 2 mit dem App-Installer .  

![Installieren von MRTK-Beispielen über App-Installer](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:

- Die Handnachverfolgung verwaltet jetzt die Nachverfolgung in vielen neuen Fällen, in denen die Hand zuvor verloren gegangen wäre.  In einigen dieser neuen Fälle wird nur die Handflächenposition basierend auf der realen Hand des Benutzers aktualisiert, während die anderen Fugen basierend auf einer früheren Pose abgeleitet werden.  Diese Änderung trägt zur Verbesserung der Nachverfolgungskonsistenz bei Bewegungen wie Slapping, Throwing, Scooping und Clapping bei.  Dies hilft auch in Fällen, in denen sich die Hand in der Nähe einer Oberfläche befindet oder ein Objekt hält.  Wenn Handverbindungen abgeleitet werden, wird der [Genauigkeitswert pro Joint](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) auf "Approximate" anstelle von "High" festgelegt.
- Ein Problem wurde behoben, bei dem die PIN-Zurücksetzung für Azure AD Konten den Fehler "Etwas ist schief gelaufen" angezeigt hat.
- Benutzer sollten deutlich weniger OOBE-Abstürze nach dem Start sehen, wenn ET, Iris aus der Einstellungs-App, neuer Benutzer oder Popupbenachrichtigung gestartet wird.
- Benutzer sollten über die richtige Zeitzone verfügen, die aus OOBE stammt.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2020
- Build 18362.1088

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unsere neueste Windows Holographic, Version 20H2 – Update von Dezember 2020 und das neue feature App-Installer, das im Build hinzugefügt wurde, auszuprobieren.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, Version 20H2
- Build 19041.1128

Windows Holographic, Version 20H2 ist jetzt verfügbar und bietet eine Vielzahl neuer Features für HoloLens 2 Benutzer und IT-Experten. Von der Automatischen Blickpositionierung über den Zertifikat-Manager in Einstellungen bis hin zu verbesserten Kioskmodusfunktionen und neuen Autopilot-Setupfunktionen. Dieses neue Update ermöglicht IT-Teams eine präzisere Steuerung der Konfiguration und Verwaltung HoloLens Geräten und bietet Benutzern noch nahtlosere holografische Funktionen. 

Dieses neueste Release ist ein monatliches Update auf Version 2004, aber dieses Mal enthalten wir neue Features. Die Hauptbuildnummer bleibt unverändert, und Windows Update gibt ein monatliches Release auf Version 2004 (Build 19041) an. Sie können ihre Buildnummer auf dem Bildschirm Einstellungen > About anzeigen, um zu bestätigen, dass Sie über den neuesten verfügbaren Build 19041.1128 und mehr informiert sind. Öffnen Sie zum Aktualisieren auf das neueste Release die Einstellungen-App, wechseln Sie zu Update & Security (& Sicherheit aktualisieren), und tippen Sie auf Nach Updates suchen. Weitere Informationen zum Verwalten HoloLens Updates finden Sie unter [Verwalten HoloLens Updates.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Neuerungen in Windows Holographic, Version 20H2  

| Feature                                              | Beschreibung                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Unterstützung der automatischen Augenposition](hololens-release-notes.md#auto-eye-position-support) | Berechnet aktiv Augenpositionen, ohne dass Benutzer die Eye Tracking-Kalibrierung durchlaufen.   |
| [Zertifikat-Manager](hololens-release-notes.md#certificate-manager)   | Ermöglicht neuen einfacheren Methoden das Installieren und Entfernen von Zertifikaten aus der Einstellungen-App.     |
| [Automatisches Starten der Bereitstellung über USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Bei Bereitstellungspaketen auf USB-Laufwerken wird automatisch die Bereitstellungsseite in OOBE angezeigt.                                                         |
| [Automatische Bestätigung von Bereitstellungspaketen in OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Bereitstellungspakete werden automatisch während der OOBE von der Bereitstellungsseite angewendet.                                                         |
| [Automatische Bereitstellung ohne Benutzeroberfläche](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Kombinieren des automatischen Starts und der automatischen Bestätigung der Bereitstellung. |
| [Verwenden von Autopilot mit Wi-Fi Verbindung](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Verwenden Sie Autopilot vom Gerät Wi-Fi ohne Ethernet-Adapter. |
| [Tenantlockdown-CSP und Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Nachdem die Mandantenregistrierung und die Richtlinie angewendet wurden, kann das Gerät nur bei jedem Zurücksetzen oder erneuten Flashen des Geräts bei diesem Mandanten registriert werden. |
| [Global zugewiesener Zugriff](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Neue Konfigurationsmethode für den Kioskmodus für mehrere Apps, die den Kiosk auf Systemebene anwendet, sodass er für alle gilt.                  |
| [Automatisches Starten einer App im Kiosk mit mehreren Apps](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Legt fest, dass eine Anwendung automatisch gestartet wird, wenn sie sich bei einem Kioskmodus mit mehreren Apps anmeldet.                                                        |
| [Änderungen am Kioskmodusverhalten für die Behandlung von Fehlern](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Kioskmodusfehler weist jetzt einen restriktiven Fallback auf.                                                                                                |
| [HoloLens Politik](hololens-release-notes.md#hololens-policies)                                    | Neue Richtlinien für HoloLens.     |
| [Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Mit der neuen Richtlinie können Benutzer den Gruppenmitgliedschaftscache verwenden, um den Kioskmodus für die festgelegte Anzahl von Tagen offline zu verwenden.                                        |
| [Neue Geräteeinschränkungsrichtlinien für HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Neu aktivierte Geräteverwaltungsrichtlinien für HoloLens 2.                                                                                |
| [Neue Energierichtlinien für HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Neu unterstützte Richtlinien für Energietimeouteinstellungen.  |
| [Aktualisieren von Richtlinien](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Neu aktivierte Richtlinien, die die Steuerung von Updates ermöglichen.           |
| [Einstellungen Seitensichtbarkeit für HoloLens 2 aktiviert](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Richtlinie zum Auswählen der Seiten, die in Einstellungen App angezeigt werden.             |
| [Forschungsmodus](hololens-release-notes.md#research-mode) | Verwenden des Forschungsmodus auf HoloLens 2. |
| [Aufzeichnungslänge erhöht](hololens-release-notes.md#recording-length-increased) | MRC-Aufzeichnungen sind nicht mehr auf 5 Minuten begrenzt. |
| [Verbesserungen und Fehlerbehebungen im Update](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Zusätzliche Fehlerbehebungen im Update.   |

### <a name="auto-eye-position-support"></a>Unterstützung der automatischen Augenposition

In HoloLens 2 ermöglichen Augenpositionen eine genaue Hologrammpositionierung, eine komfortable Anzeige und eine verbesserte Anzeigequalität. Die Augenpositionen werden intern als Teil der Eyetrackingberechnung berechnet. Dies erfordert jedoch, dass jeder Benutzer die Kalibrierung des Eyetrackings durchgeht, auch wenn die Benutzeroberfläche möglicherweise keine Eingabe für das Anverfolgen der Augen erfordert.

**Auto Eye Position (AEP)** ermöglicht diese Szenarien mit einer interaktionsfreien Möglichkeit, Augenpositionen für den Benutzer zu berechnen. Die automatische Blickposition funktioniert im Hintergrund automatisch ab dem Moment, an dem der Benutzer das Gerät einschaltet. Wenn der Benutzer nicht über eine vorherige Kalibrierung der Blickverfolgung verfügt, beginnt die automatische Augenposition mit der Bereitstellung der Augenpositionen des Benutzers für das Anzeigesystem nach einer Verarbeitungszeit von 20 bis 30 Sekunden. Die Benutzerdaten werden nicht dauerhaft auf dem Gerät gespeichert. Daher wird dieser Vorgang wiederholt, wenn der Benutzer das Gerät startet und wieder einschaltet oder wenn das Gerät neu gestartet oder aus dem Standbymodus reaktiviert wird.

Es gibt einige Änderungen am Systemverhalten mit dem Feature "Auto Eye Position", wenn ein nicht behandelter Benutzer das Gerät einstellt. In diesem Kontext bezieht sich ein nicht überwachter Benutzer auf eine Person, die den Kalibrierungsprozess für die Eyetracking auf dem Gerät noch nicht durchlaufen hat.

| Aktive Anwendung | Vorheriges Verhalten | Verhalten von Windows Holographic, Version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Nicht anvaktivierte App oder Holographic Shell |Das Kalibrierungseingabeaufforderungsdialogfeld für die Eyetracking wird angezeigt. | Es wird keine Eingabeaufforderung angezeigt. |
| Anvaktivierte App | Das Kalibrierungseingabeaufforderungsdialogfeld für die Eyetracking wird angezeigt. | Die Kalibrierungsaufforderung eye tracking wird nur angezeigt, wenn die Anwendung auf den Anverfolgungsstream der Augen zugreift. |

Wenn der Benutzer von einer Nicht-Anverweise-fähigen Anwendung zu einer Anwendung übergeht, die auf die Anviert-Daten zugreift, wird die Kalibrierungsaufforderung angezeigt. 

Alle anderen Systemverhalten ähneln, wenn der aktuelle Benutzer keine aktive Eyetracking-Kalibrierung hat. Beispielsweise wird die Einhändige Startgeste nicht aktiviert. Es gibt keine Änderungen an der Out-of-Box-Experience für die ersteinrichtung.

Für Benutzer, die Daten zum Anvisieren mit den Augen oder eine sehr genaue Hologrammpositionierung erfordern, empfehlen wir uncalibrierten Benutzern die Kalibrierung der Blickverfolgung. Sie ist über die Kalibrierungsaufforderung für die Eyetracking-Kalibrierung oder durch Starten der Einstellungen-App über das Startmenü zugänglich, und wählen Sie dann System > Calibration > Eye Calibration > Run eye calibration (Kalibrierung von **System > Kalibrierung > Augenkalibrierung > Kalibrierung** der Augen ausführen) aus.

Diese Informationen finden Sie später mit [anderen Kalibrierungsinformationen.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Validierungstools für Gerätesicherheit und -konformität über den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen im großen Stil bereitstellen, behandeln und überprüfen.

In Windows Holographic-Version 20H2 fügen wir einen Zertifikat-Manager in der HoloLens 2 Einstellungen-App hinzu. Wechseln Sie zu **Einstellungen > Update & Security > Certificates**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und konform bleiben. 

-   **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, spart die Überprüfung, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung. 
-   **Überprüfung:** Die Überprüfung, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionsfähig ist, kann insbesondere in kommerziellen Umgebungen erhebliche Zeit sparen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um schnell ein bestimmtes Zertifikat in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Um einzelne Zertifikateigenschaften anzuzeigen, wählen Sie das Zertifikat aus, und klicken Sie auf **Info**. 

Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur unter Aktueller Benutzer installieren. Benutzer können nur Zertifikate entfernen, die direkt von der Einstellungen Benutzeroberfläche installiert wurden. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.

#### <a name="to-install-a-certificate"></a>So installieren Sie ein Zertifikat: 

1.  Verbinden Ihre HoloLens 2 zu einem PC.
1.  Platzieren Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2.
1.  Navigieren Sie zu **Einstellungen App > Update & Security > Certificates**, und wählen Sie Zertifikat installieren aus.
1.  Klicken Sie auf **Datei importieren,** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **Store Standort aus.**
1.  Wählen Sie **Zertifikat Store** aus.
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert sein.

#### <a name="to-remove-a-certificate"></a>So entfernen Sie ein Zertifikat: 
1. Navigieren Sie zu **Einstellungen App > Update and Security > Certificates**.
1. Suchen Sie im Suchfeld nach dem Zertifikat anhand des Namens.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen.**
1. Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.

![Zertifikatanzeige in der Einstellungen-App](images/certificate-viewer-device.jpg)

![Abbildung zur Verwendung der Zertifikat-Benutzeroberfläche zum Installieren eines Zertifikats](images/certificate-device-install.jpg)

Diese Informationen finden Sie später [auf einer neuen Seite des Zertifikat-Managers.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse, die eine geringere Benutzerinteraktion ermöglichen, wenn USB-Laufwerke mit Bereitstellungspaketen während der OoBE verwendet werden.

Vor diesem Release mussten Benutzer den Bereitstellungsbildschirm während der OOBE manuell starten, um die Bereitstellung mithilfe einer Schaltflächenkombination zu ermöglichen. Jetzt können Benutzer die Schaltflächenkombination überspringen, indem sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Anschließen des USB-Laufwerks mit dem Bereitstellungspaket während des ersten interaktionsfähigen OoBE-Moments
1. Wenn das Gerät bereit für die Bereitstellung ist, öffnet es automatisch die Eingabeaufforderung mit der Bereitstellungsseite. 

Hinweis: Wenn ein USB-Laufwerk beim Starten des Geräts angeschlossen bleibt, zählt OOBE ein vorhandenes USB-Speichergerät auf und überwacht, ob weitere angeschlossen sind.

Weitere Informationen zum Anwenden von Bereitstellungspaketen während der Oobe finden Sie in der [Dokumentation zur HoloLens Bereitstellung.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Weitere Informationen zum [automatischen Starten](hololens-provisioning.md#auto-launch-provisioning-from-usb) der Bereitstellung über usb finden Sie in der Dokumentation zur HoloLens-Bereitstellung.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatische Bestätigung von Bereitstellungspaketen in OOBE
- Automatisierter Prozess, der eine geringere Benutzerinteraktion ermöglicht. Wenn die Seite Bereitstellungspaket angezeigt wird, werden automatisch alle aufgelisteten Pakete angewendet.

Wenn der Hauptbildschirm für die Bereitstellung angezeigt wird, zählt OOBE 10 Sekunden nach unten, bevor alle Bereitstellungspakete automatisch angewendet werden. Benutzer können die Pakete, die sie erwartet haben, innerhalb dieser 10 Sekunden bestätigen [oder abbrechen.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### <a name="automatic-provisioning-without-using-ui"></a>Automatische Bereitstellung ohne Benutzeroberfläche
- Kombinierte automatische Prozesse für reduzierte Geräteinteraktionen für die Bereitstellung. 

Durch die Kombination des automatischen Starts der Bereitstellung von USB-Geräten und der automatischen Bestätigung von Bereitstellungspaketen kann ein Benutzer HoloLens 2 Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts oder sogar das Gerät zu verwenden. Sie können weiterhin das gleiche USB-Laufwerk und Bereitstellungspaket für mehrere Geräte verwenden. Dies ist nützlich für die gleichzeitige Bereitstellung mehrerer Geräte im selben Bereich. 

1. Erstellen Sie mit [Windows Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) [ein Bereitstellungspaket.](hololens-provisioning.md) 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flashen Sie Ihre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) auf [19041.1361 oder einen neueren Build.](https://aka.ms/hololens2previewdownload) 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken des Geräts abgeschlossen hat, ziehen Sie das USB-C-Kabel aus. 
1. Schließen Sie Ihr USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2 Gerät in OOBE gestartet wird, erkennt es automatisch das Bereitstellungspaket auf dem USB-Laufwerk und startet die Bereitstellungsseite.
1. Nach 10 Sekunden wendet das Gerät automatisch das Bereitstellungspaket an. 

Ihr Gerät ist jetzt konfiguriert und [zeigt den Bildschirm Bereitstellung erfolgreich](hololens-provisioning.md#automatic-provisioning-without-using-ui)an.

### <a name="using-autopilot-with-wi-fi-connection"></a>Verwenden von Autopilot mit Wi-Fi Verbindung
- Usb-C-Adapter für Ethernet wurden nicht mehr benötigt, um den Hardwarebedarf zu reduzieren, da Autopilot auf Wi-Fi verbundenen Geräten funktionieren kann.

Sobald Sie während der OOBE eine Verbindung mit HoloLens 2 mit WLAN herstellen, sucht OOBE nach einem Autopilot-Profil für das Gerät. Wenn eine gefunden wird, wird sie verwendet, um den restliche AAD-Join- und Registrierungsflow abzuschließen. Anders ausgedrückt: Die Verwendung von Ethernet zu USB-C oder Wi-Fi zu USB-C-Adaptern ist keine Anforderung mehr, sie funktionieren jedoch weiterhin, wenn sie zu Beginn der OOBE bereitgestellt werden. Erfahren Sie mehr über [Autopilot für HoloLens 2 Geräte.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown-CSP und Autopilot
- Behält Geräte auf dem Mandanten der Organisation bei, indem sie für den Mandanten gesperrt werden, auch wenn sie zurückgesetzt oder ein Reflash verwendet werden. Mit zusätzlicher Sicherheit, indem sie die Kontoerstellung in über die Bereitstellung nicht zulasst. 

HoloLens 2 Geräte unterstützen ab [Windows Holographic-Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2)den TenantLockdown-CSP. 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP ermöglicht es HoloLens 2, nur mit Autopilot an die MDM-Registrierung gebunden zu werden. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown-CSP auf HoloLens 2 entweder auf true oder false (anfänglich festgelegt) festgelegt ist, verbleibt dieser Wert auf dem Gerät, obwohl es neu blinkt, Betriebssystemupdates usw. 

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown-CSPs auf HoloLens 2 auf TRUE festgelegt ist, wartet OOBE unbegrenzt darauf, dass das Autopilot-Profil nach der Netzwerkkonnektivität erfolgreich heruntergeladen und angewendet wird. 

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown-CSPs auf HoloLens 2 auf TRUE festgelegt ist, sind die folgenden Vorgänge in OOBE nicht zulässig: 
- Erstellen eines lokalen Benutzers mithilfe der Laufzeitbereitstellung 
- Ausführen Azure AD Joinvorgangs über die Laufzeitbereitstellung 
- Auswählen, wer das Gerät in der OOBE-Benutzeroberfläche besitzt 

#### <a name="how-to-set-this-using-intune"></a>Wie wird dies mit Intune festgelegt? 
1. Erstellen Sie ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil, und geben Sie true für den RequireNetworkInOOBE-Knoten an, wie unten dargestellt.
Der OMA-URI-Wert muss ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten.

   > [!div class="mx-imgBorder"]
   > ![Festlegen der tennant lockdown über OMA-URI](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe, und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2 Gerätemitglied der Gruppe, die sie im vorherigen Schritt erstellt haben, und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2 Gerät angewendet wird, sind die Auswirkungen von TenantLockdown aktiv.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Wie wird die RequireNetworkInOOBE-Version von TenantLockdown auf HoloLens 2 mit Intune nicht mehr ermittelt? 
1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der zuvor die oben erstellte Gerätekonfiguration zugewiesen wurde. 

1. Erstellen Sie ein benutzerdefiniertes OMA-URI-basiertes Gerätekonfigurationsprofil, und geben Sie false für RequireNetworkInOOBE an, wie unten dargestellt. Der OMA-URI-Wert muss ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten.

   > [!div class="mx-imgBorder"]
   > ![Screenshot: Festlegen von "RequireNetworkInOOBE" auf "false" über den OMA-URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe, und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2 Gerätemitglied der Gruppe, die sie im vorherigen Schritt erstellt haben, und lösen Sie die Synchronisierung aus.

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration auf dem HoloLens 2 Gerät erfolgreich angewendet wird, sind die Auswirkungen von TenantLockdown inaktiv. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Was geschieht während der OOBE, wenn das Autopilot-Profil auf einem HoloLens nicht zugewiesen wird, nachdem TenantLockdown auf TRUE festgelegt wurde? 
OOBE wartet unbegrenzt, bis das Autopilot-Profil heruntergeladen wurde, und das folgende Dialogfeld wird angezeigt. Um die Auswirkungen von TenantLockdown zu entfernen, muss das Gerät zunächst mit seinem ursprünglichen Mandanten registriert werden, wobei nur Autopilot verwendet wird, und RequireNetworkInOOBE muss wie im vorherigen Schritt beschrieben aufgehoben werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden. 

![Geräteseitige Ansicht für den Zeitpunkt, an dem die Richtlinie auf dem Gerät erzwungen wird.](images/hololens-autopilot-lockdown.png)

Diese Informationen finden Sie jetzt zusammen mit dem restliche Autopilot unter [Tenantlockdown CSP und Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Global zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene anwendet.

Mit diesem neuen Feature kann ein IT-Administrator ein HoloLens 2 Gerät für den Kioskmodus für mehrere Apps konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System aufwies und für alle Benutzer gilt, die sich beim Gerät anmelden. Weitere Informationen zu diesem neuen Feature finden Sie im HoloLens Kiosk mit [global zugewiesenem Zugriff.](hololens-global-assigned-access-kiosk.md)

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

Zuvor wurden Fehler beim Anwenden des Kioskmodus HoloLens verwendet, um alle Anwendungen im Startmenü anzuzeigen. In Windows Holographic-Version 20H2 werden im Fall von Ausfällen keine Apps wie folgt im Startmenü angezeigt: 

![Abbildung, wie der Kioskmodus jetzt aussieht, wenn ein Fehler auftritt.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Politik
- Geräteverwaltungsoptionen speziell für HoloLens, die für die Verwaltung des Geräts erstellt wurden. 

Neue Mixed Reality-Richtlinien wurden für HoloLens 2 Geräte auf Windows Holographic Version 20H2 erstellt. Neue steuerbare Einstellungen: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed Reality-Erfassungen, Festlegen, wann Diagnosedaten erfasst werden können, und AAD-Gruppenmitgliedschaftscache.  

| Neue HoloLens-Richtlinie                                | Beschreibung                                                                               | Hinweise                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Ermöglicht das Deaktivieren von Helligkeitsschaltflächen, sodass sich die Helligkeit nicht ändert, wenn Sie sie drücken.       | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Ermöglicht das Deaktivieren von Lautstärkereglern, sodass sich das Volumen durch drücken nicht ändert.               | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\MicrophoneDisabled                    | Deaktiviert das Mikrofon, sodass keine Audioaufzeichnung auf HoloLens 2 möglich ist.                      | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\FallbackDiagnostics                   | Steuert das Verhalten, wann Diagnoseprotokolle gesammelt werden können.                               | 0 Deaktiviert, 1 für Gerätebesitzer aktiviert, 2 für alle aktiviert (Standard) |
| MixedReality\HeadTrackingMode                      | Für die zukünftige Verwendung reserviert.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheCacheInDays | Steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Kiosks für Azure AD Gruppen verwendet wird. | Siehe unten.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Cache Azure AD Gruppenmitgliedschaft für Offlinekiosk
- Offlinekiosks können bis zu 60 Tage lang mit AAD-Gruppen verwendet werden.

Diese Richtlinie steuert, wie viele Tage Azure AD Gruppenmitgliedschaftscache für Konfigurationen des zugewiesenen Zugriffs verwendet werden darf, die auf Azure AD Gruppen für angemeldete Benutzer ausgerichtet sind. Sobald dieser Richtlinienwert nur auf einen Wert größer als 0 festgelegt ist, wird der Cache verwendet, andernfalls nicht.  

Name: AADGroupMembershipCacheCacheInDays-URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCache UsernameInDays

Min. – 0 Tage  
Max. – 60 Tage 

Schritte zur ordnungsgemäßen Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für Kioskzielgruppen Azure AD, und weisen Sie es HoloLens Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) festlegt, und weisen Sie ihn HoloLens Geräten zu. 
    1. Der URI-Wert sollte in das Textfeld OMA-URI als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheOrporaInDays eingegeben werden.
    1. Der Wert kann zwischen min/max zulässig sein.
1. Registrieren Sie HoloLens Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Azure AD Benutzer 1 anmelden, wenn das Internet verfügbar ist. Sobald sich der Benutzer anmeldet und Azure AD Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Azure AD Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Tage zulässt. 
1. Die Schritte 4 und 5 können für alle anderen Azure AD Benutzer N wiederholt werden. Der Wichtigste Punkt hierbei ist, dass sich jeder Azure AD Benutzer über das Internet beim Gerät anmelden muss, damit wir mindestens einmal feststellen können, dass er Mitglied Azure AD Gruppe ist, für die die Kioskkonfiguration vorgesehen ist. 
 
> [!NOTE]
> Bis Schritt 4 für einen Azure AD Benutzer das in "getrennten" Umgebungen beschriebene Fehlerverhalten auftritt. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Neue Geräteeinschränkungsrichtlinien für HoloLens 2
- Ermöglicht Benutzern das Verwalten bestimmter Geräteverwaltungsrichtlinien, z. B. das Blockieren des Hinzufügens oder Entfernens von Bereitstellungspaketen.

Neu aktivierte Richtlinien, die mehr Verwaltungsoptionen für HoloLens 2 Geräte ermöglichen. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Diese beiden neuen Richtlinien für AllowAddProvisioningPackage und AllowRemoveProvisioningPackage werden unseren [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)hinzugefügt.

> [!NOTE]
> In Bezug auf [RemoteLock](/windows/client-management/mdm/remotelock-csp)unterstützt HoloLens nur die Konfiguration ./Vendor/MSFT/RemoteLock/Lock. Die Konfigurationen für PIN wie Zurücksetzen und Wiederherstellen werden nicht unterstützt.

### <a name="new-power-policies-for-hololens-2"></a>Neue Energierichtlinien für HoloLens 2
- Weitere Optionen, wenn HoloLens über Energierichtlinien in den Energiesparmodus versetzt oder gesperrt wird. 

Mit diesen neu hinzugefügten Richtlinien können Administratoren Energiezustände steuern, z. B. Leerlauftimeout. Klicken Sie auf den Link für diese Richtlinie, um mehr über die einzelnen Richtlinien zu erfahren.

|     Link zur Richtliniendokumentation                |     Hinweise                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d.h. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d.h. 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Beispielwert, der in Windows Konfigurations-Designer verwendet werden soll, d. h.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Diese beiden neuen Richtlinien für DisplayOffTimeoutOnBattery und DisplayOffTimeoutPluggedIn werden unseren [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)hinzugefügt.

> [!NOTE]
> Stellen Sie für eine konsistente Benutzeroberfläche für HoloLens 2 sicher, dass die Werte für DisplayOffTimeoutOnBattery und StandbyTimeoutOnBattery auf den gleichen Wert festgelegt sind. Dasselbe gilt für DisplayOffTimeoutPluggedIn und StandbyTimeoutPluggedIn. Weitere Informationen zum modernen Standbymodus finden Sie [unter Anzeigen, Standbymodus und Ruhezustand von Leerlauftimern.](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers)

### <a name="newly-enabled-update-policies-for-hololens"></a>Neu aktivierte Updaterichtlinien für HoloLens
- Weitere Optionen für die Installation von Updates oder das Deaktivieren der Schaltfläche Updates anhalten, um Updates sicherzustellen.

Diese Updaterichtlinien sind jetzt auf HoloLens 2 Geräten aktiviert:
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Ausführliche Informationen zu diesen Updaterichtlinien und deren Verwendung für HoloLens Geräte finden Sie hier unter [Verwalten HoloLens Updates.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Einstellungen Seitensichtbarkeit für HoloLens 2 aktiviert
- Erhöhte Benutzeroberflächensteuerung in der Einstellungen-App, die möglicherweise verwechselt wird, um eine begrenzte Auswahl von Seiten anzuzeigen.

Wir haben nun eine Richtlinie aktiviert, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der System-Einstellungen-App sichtbar oder zugänglich sind, oder dies für alle Seiten mit Ausnahme der angegebenen Seiten zu tun. Klicken Sie auf den folgenden Link, um zu erfahren, wie Sie dieses Feature vollständig anpassen.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Um zu erfahren, welche Seiteneinstellungen Sie auf HoloLens 2 anpassen können, besuchen Sie unsere [Seite Einstellungen URIs](settings-uri-list.md). 
 
![Screenshot der aktiven Stunden, die in der Einstellungen-App geändert werden](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Forschungsmodus
Im Forschungsmodus wird die HoloLens 2 zu einem Tool für die Forschung im Bereich des computergestützten Sehens. Im Vergleich zu früheren Editionen hat der Forschungsmodus für HoloLens 2 die folgenden Vorteile:
-   Zusätzlich zu Sensoren, die im Forschungsmodus HoloLens (1. Generation) verfügbar gemacht werden, bieten wir jetzt IMU-Sensorzugriff, einschließlich Beschleunigungsmesser, Gyroskop und Magnetometer.
-   HoloLens 2 bietet neue Funktionen, die zusammen mit dem Forschungsmodus verwendet werden können. Insbesondere der Zugriff auf artikulierte APIs für Handtracking und Eyetracking, die eine umfangreichere Reihe von Experimenten bereitstellen können.

Forscher haben jetzt die Möglichkeit, den Forschungsmodus auf ihren HoloLens Geräten zu aktivieren, um auf alle diese externen Datenströme von Rohbildsensoren zuzugreifen. Der Forschungsmodus für HoloLens 2 bietet auch Zugriff auf die Messwerte für Beschleunigungsmesser, Gyroskop und Magnetometer. Um die Privatsphäre der Benutzer zu schützen, sind unformatierte Eyetrackingkamerabilder nicht über den Forschungsmodus verfügbar, aber die Blickrichtung ist über vorhandene APIs verfügbar.

Weitere technische Details finden Sie in der Dokumentation zum [Forschungsmodus.](/windows/mixed-reality/research-mode)

### <a name="recording-length-increased"></a>Aufzeichnungslänge erhöht
Aufgrund von Kundenfeedback haben wir die Aufzeichnungslänge von [Mixed Reality-Erfassungen](holographic-photos-and-videos.md)erhöht. Mixed Reality-Erfassungen sind standardmäßig nicht mehr auf 5 Minuten beschränkt, sondern berechnen die maximale Aufzeichnungslänge basierend auf dem verfügbaren Speicherplatz. Das Gerät schätzt die maximale Videoaufzeichnungsdauer basierend auf dem verfügbaren Speicherplatz auf bis zu 80 % des gesamten Speicherplatzes.

> [!NOTE]
> Die HoloLens verwendet die Standardlänge der Videoaufzeichnung (5 Minuten), wenn eine der folgenden Vorgänge auftritt:
> - Die geschätzte maximale Aufzeichnungsdauer ist kleiner als die Standarddauer von 5 Minuten.
> - Der verfügbare Speicherplatz beträgt weniger als 20 % des gesamten Speicherplatzes.

Die vollständigen Anforderungen finden Sie in unserer Dokumentation [zu holografischen Fotos und Videos.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:
- Weitere Bildschirme in OOBE befinden sich jetzt im dunklen Modus.
- Weitere Informationen finden Sie in den aktuellen Onlinedatenschutzerklärungen.
- Es wurde ein Problem behoben, bei dem Benutzer VPN-Profile nicht über Bereitstellungspakete bereitstellen konnten.
- Proxykonfigurationsproblem für VPN-Verbindung behoben.
- Aktualisierte Richtlinie zum Deaktivieren der Enumeration von USB-Funktionen über MDM für NCM für AllowUsbConnection.
- Es wurde ein Problem behoben, das verhinderte, dass ein HoloLens Gerät im [Datei-Explorer](hololens-kiosk.md)über das Media Transfer Protocol (MTP) angezeigt wurde, wenn das Gerät als Kiosk mit einer einzelnen App eingerichtet wurde. Beachten Sie, dass MTP (und usb-Verbindung im Allgemeinen) weiterhin mithilfe der [AllowUSBConnection-Richtlinie](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) deaktiviert werden können.
- Ein Problem wurde behoben, bei dem Symbole im Startmenü im Kioskmodus ordnungsgemäß skaliert wurden.
- Ein Problem wurde behoben, das darauf zurückzuführen ist, dass die HTTP-Zwischenspeicherung den Kioskmodus beeinträchtigt, der auf Azure AD Gruppen ausgerichtet ist.
- Ein Problem wurde behoben, bei dem Benutzer die Schaltfläche Koppeln nicht verwenden konnten, nachdem sie den Entwicklermodus mit Bereitstellungspaketen aktiviert haben, es sei denn, sie haben den Entwicklermodus deaktiviert und wieder aktiviert.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, Version 1903 – Update vom November 2020
- Build 18362.1085

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unseren neuesten Featureversionsbuild Windows Holographic, Version 20H2, auszuprobieren.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, Version 2004 – Oktober 2020 Update
- Build 19041.1124
 
Verbesserungen und Fehlerbehebungen im Update:

- Eine unnötige Überprüfung, die einen Laufzeitsystemfehler verursacht hat, wurde entfernt.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, Version 1903 – Oktober 2020 Update
- Build 18362.1081

Dieses monatliche Qualitätsupdate enthält keine wichtigen Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, Version 2004 – September 2020 Update
- Build 19041.1117

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem, das verhindert hat, dass Visual Studio eine Anwendung debuggt, wenn SupportsMultipleInstances="true" im appxmanifest vorhanden ist.
- Dieses Release enthält eine Korrektur der NCSI-Proxyerkennung, um die fehlerhafte Interneterkennung über den Netzwerkproxy zu beheben. NCSI kann einen Computerproxy und profilbasierten Proxy für die Erkennung von Internetkonnektivität verwenden. Der Pro-Benutzer-Proxy wird in der zukünftigen Version von NCSI unterstützt.
- Auf den meisten Windows Mixed Reality Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. Frühere Versionen von HoloLens 2 den Vektor jedoch so ausgerichtet, dass er stattdessen den Anzeigepanels entspricht, die relativ zur idealen Ausrichtung einige Grad nach unten geneigt sind. Neuere Versionen von HoloLens 2 haben dies korrigiert, um semantische Konsistenz zwischen Formfaktoren sicherzustellen.
- Verbesserte Handtrackingstabilität, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.
- Dieses Release enthält eine Korrektur zur Verbesserung der Qualität des Audiozeitstempels, die möglicherweise zu Problemen bei der Videoaufzeichnung beigetragen hat.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, Version 1903 – Update vom September 2020
- Build 18362.1079

Verbesserungen und Fehlerbehebungen im Update:

- Auf den meisten Windows Mixed Reality Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. Frühere Versionen von HoloLens 2 den Vektor jedoch so ausgerichtet, dass er stattdessen den Anzeigepanels entspricht, die relativ zur idealen Ausrichtung einige Grad nach unten geneigt sind. Neuere Versionen von HoloLens 2 haben dies korrigiert, um semantische Konsistenz zwischen Formfaktoren sicherzustellen.
- Verbesserte Handtrackingstabilität, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, Version 2004 – Update vom August 2020
- Build 19041.1113

Verbesserungen und Fehlerbehebungen im Update:

- Einstellungen App folgt dem Benutzer nicht mehr in iris-Registrierung oder Eye Tracking-Kalibrierungserfahrung.
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
- Es wurde ein Problem mit der HTTPS-Weiterleitung für die Windows Geräteportal auf HoloLens 2 behoben.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, Version 1903 – Update vom Juli 2020
- Build 18362.1071

Verbesserungen und Fehlerbehebungen im Update:

- Ein Problem wurde behoben, das dazu führen konnte, dass Hologramme in Unity-Anwendungen nicht mehr angezeigt werden, wenn die Nachverfolgung verloren geht oder wiedererlangt wird.
- Ein Problem wurde behoben, das dazu führte, dass exklusive HoloLens-Apps bei Verwendung des HoloLens Emulator mit Hardwarebeschleunigung auf bestimmten Geräten wieder auf die Shell abstürzten.
- Es wurde ein Problem mit der HTTPS-Weiterleitung für die Windows Geräteportal auf HoloLens 2 behoben.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, Version 2004 – Juni 2020 Update
- Build 19041.1106

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen jetzt über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben werden.
  - Auf dem *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersives Headset))
  - Auf dem *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle Wert "App-Audiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
    - MicrophoneGain (der aktuelle Wert "Mikrofonaudiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
- Ein Fehler zur Verbesserung der Audioqualität in Mixed Reality-Erfassungsszenarien wurde behoben. Durch diese Korrektur sollte insbesondere die Audiowiedergabe in der Aufzeichnung vermieden werden, wenn das **Startmenü** angezeigt wird.
- Verbesserte Hologrammstabilität in aufgezeichneten Videos.
- Ein Problem wurde behoben, bei dem die Mixed Reality-Erfassung das Video nicht aufzeichnen konnte, nachdem das Gerät mehrere Tage lang im Standbyzustand war.
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, das dazu geführt hat, dass einige Apps angehalten wurden, wenn das Visier nach oben gedreht wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert war. Die API ist jetzt für unity-Versionen 2018.4.18 und höher und 2019.3.4 und höher aktiviert.
- Wenn Sie über eine Wi-Fi Verbindung auf Geräteportal zugreifen, kann ein Webbrowser den Zugriff auf aufgrund eines ungültigen Zertifikats verhindern. Der Browser meldet möglicherweise einen Fehler wie "ERR_SSL_PROTOCOL_ERROR", auch wenn das Gerätezertifikat zuvor vertrauenswürdig war. In diesem Fall können Sie nicht zu Geräteportal, da es keine Option zum Ignorieren von Sicherheitswarnungen gibt. Dieses Update hat das Problem behoben. Wenn das Gerätezertifikat zuvor heruntergeladen und auf einem PC als vertrauenswürdig eingestuft wurde, um Browsersicherheitswarnungen zu entfernen, und der SSL-Fehler auftritt, muss das neue Zertifikat heruntergeladen und als vertrauenswürdig eingestuft werden, um Sicherheitswarnungen des Browsers zu beheben.
- Ermöglicht das Erstellen eines Laufzeitbereitstellungspakets, das eine App mithilfe von MSIX-Paketen installieren kann.
- In **Einstellungen** System Hologramme wurde eine Einstellung hinzugefügt, mit der  >    >   Benutzer automatisch alle Hologramme aus Mixed Reality Startseite entfernen können, wenn das Gerät heruntergefahren wird.
- Es wurde ein Problem behoben, das dazu führte, dass HoloLens Apps ihr Pixelformat so geändert haben, dass sie im HoloLens Emulator schwarz gerendert werden.
- Ein Fehler wurde behoben, der während der Iris-Anmeldung einen Absturz verursacht hat.
- Ein Problem mit wiederholten Storedownloads für bereits aktuelle Apps wurde behoben.
- Ein Fehler wurde behoben, der verhinderte, dass immersive Apps Microsoft Edge wiederholt öffnen.
- Es wurde ein Problem mit dem Starten der Fotos-App beim ersten Start nach dem Update vom Release 1903 behoben.
- Verbesserte Leistung und Zuverlässigkeit.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, Version 1903 – Juni 2020 Update
- Build 18362.1064

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben sind.
  - Auf dem *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersives Headset))
  - Für den *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle Wert "App-Audiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
    - MicrophoneGain (der aktuelle Wert "Mikrofonaudiogewinn" auf der Mixed Reality-Aufnahme Seite in Windows Geräteportal)
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, das dazu führt, dass einige Apps angehalten werden, wenn das Visier nach oben gedreht wird, auch wenn die Einstellung für die Ausführung im Hintergrund aktiviert ist. Die API ist jetzt für unity-Versionen 2018.4.18 und höher und 2019.3.4 und höher aktiviert.
- Es wurde ein Problem behoben, das dazu führte, dass HoloLens Apps ihr Pixelformat so geändert haben, dass sie im HoloLens Emulator schwarz gerendert werden.
- Es wurde ein Problem mit dem Starten der Fotos-App beim ersten Start nach dem Update von Version 1903 behoben.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, Version 2004  
- Build: 19041.1103

Das wichtige Softwareupdate von Mai 2020 für HoloLens 2, *Windows Holographic, Version 2004* enthält eine Vielzahl von interessanten neuen Funktionen, z.B. Unterstützung für Windows Autopilot, den dunklen App-Modus, USB Ethernet-Unterstützung für 5G/GIGABIT-Hotspots und vieles mehr. Öffnen Sie zum Aktualisieren auf das neueste Release die   Einstellungen-App, wechseln Sie zu **Update & Security**,und wählen Sie die Schaltfläche Nach Updates **suchen**   aus. 

|             Feature                              |          Beschreibung                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Vorkonfigurieren und nahtloses Einrichten neuer Geräte für die Produktion mithilfe von Windows AutoPilot                 |
|       FIDO 2-Unterstützung                             |          Unterstützung für FIDO2-Sicherheitsschlüssel, um eine schnelle und sichere Authentifizierung für freigegebene Geräte zu ermöglichen            |
|       Verbesserte Bereitstellung                      |          Nahtloses Anwenden eines Bereitstellungspakets von einem USB-Laufwerk auf Ihre HoloLens                              |
|       Anwendungsinstallationsstatus                 |          Überprüfen des Installationsstatus in der Einstellungen-App für Apps, die per Push an HoloLens 2 per MDM übertragen wurden               |
|       Konfigurationsdienstanbieter (Configuration Service Providers, CSPs)   |          Neue Konfigurationsdienstanbieter hinzugefügt, um die Verwaltungsfunktionen zu verbessern                 |
|       USB 5G/LTE-Unterstützung                       |          Erweiterte USB-Ethernet-Funktion ermöglicht Unterstützung für 5G/HEADSET                                    |
|       Dunkler App-Modus                              |          Dunkler App-Modus für Apps verfügbar, die sowohl dunkle als auch helle Modi unterstützen, um die Anzeige zu verbessern        |
|       Sprachbefehle                             |          Unterstützung für zusätzliche Sprachbefehle des Systems zum Steuern HoloLens freihändigen Befehlen                           |
|       Verbesserungen bei der Handnachverfolgung                 |          Verbesserungen bei der Handnachverfolgung verbessern die Genauigkeit von Schaltflächen und 2D-Slate-Interaktionen.                        |
|       Qualitätsverbesserungen und Fehlerbehebungen                 |          Verschiedene Leistungs- und Zuverlässigkeitsverbesserungen des Systems auf der gesamten Plattform                            |

### <a name="support-for-windows-autopilot"></a>Unterstützung für Windows Autopilot

Windows Autopilot für HoloLens 2 ermöglicht dem Vertriebskanal des Geräts die Vorab-Registrierung HoloLens bei Ihrem Intune-Mandanten. Wenn Geräte eintreffen, können sie sich selbst als freigegebene Geräte unter Ihrem Mandanten bereitstellen. Um die Selbstbereitstellung nutzen zu können, muss das Gerät während des ersten Bildschirms des Setups eine Verbindung mit einem Netzwerk herstellen, indem ein USB-C-to-Ethernet verwendet wird.

Nachdem ein Benutzer den Autopilot-Selbstbereitstellungsprozess gestartet hat, führt der Prozess die folgenden Schritte aus:

1. Verbinden Sie das Gerät mit Azure Active Directory (Azure AD).
1. Verwenden Sie Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Laden Sie die geräteorientierten Richtlinien, Zertifikate und Netzwerkprofile herunter.
1. Bereitstellen des Geräts.
1. Zeigen Sie dem Benutzer den Anmeldebildschirm an.

Weitere Informationen finden Sie im [Windows Autopilot für HoloLens 2 Evaluierungshandbuch.](hololens2-autopilot.md)

*Wenden Sie sich an Ihren Konto-Manager, um jetzt der AutoPilot-Vorschau beizutreten. Autopilot-fähige Geräte werden in Kürze ausgeliefert.*

### <a name="fido2-security-key-support"></a>FIDO2-Sicherheitsschlüsselunterstützung

Einige Benutzer teilen ein HoloLens Gerät für andere Benutzer in einer Arbeits- oder Schulumgebung. Daher ist es wichtig, dass Benutzer problemlos lange Benutzernamen und Kennwörter eingeben müssen. Mit Fast Identity Online (FIDO) können sich alle Benutzer in Ihrer Organisation (Azure AD Mandant) nahtlos bei HoloLens anmelden, ohne einen Benutzernamen oder ein Kennwort einzugeben.

FIDO2-Sicherheitsschlüssel sind eine "unverschlüsselbare" standardbasierte kennwortlose Authentifizierungsmethode, die in jedem Formfaktor verwendet werden kann. FIDO ist ein offener Standard für die kennwortlose Authentifizierung. Benutzer und Organisationen können sich ohne Benutzernamen oder Kennwort bei ihren Ressourcen anmelden. Stattdessen verwenden sie einen externen Sicherheitsschlüssel oder einen Plattformschlüssel, der in ein Gerät integriert ist.

Informationen zu den ersten Schritte finden Sie unter [Aktivieren der Kennwortlosen Anmeldung mit Sicherheitsschlüsseln.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Verbesserte MDM-Registrierung per Bereitstellungspaket

Mit Bereitstellungspaketen können Sie HoloLens Konfiguration über eine Konfigurationsdatei und nicht über die HoloLens-Standardkonfiguration festlegen. Zuvor mussten Bereitstellungspakete in den HoloLens internen Speicher kopiert werden. Jetzt können sie auf einem USB-Laufwerk gespeichert werden, sodass sie auf mehreren HoloLens Geräten einfacher wiederverwendet werden können und Sie Geräte parallel bereitstellen können. Bereitstellungspakete unterstützen jetzt auch ein Feld für die Registrierung bei der Geräteverwaltung, sodass nach der Bereitstellung keine manuelle Einrichtung mehr vorhanden ist.

So können Sie es ausprobieren:

1. Laden Sie die neueste Version des Windows-Konfigurations-Designers aus dem Windows-Speicher auf Ihren PC herunter.
1. Wählen Sie **Provision HoloLens Devices** Provision HoloLens 2 devices  >  **(HoloLens 2 Geräte bereitstellen)** aus.
2. Erstellen Sie Ihr Konfigurationsprofil. Kopieren Sie dann alle erstellten Dateien auf ein USB-C-Speichergerät.
3. Schließen Sie das USB-C-Gerät an alle neu blinkenden HoloLens an. Drücken Sie dann die Netzschalter für das **Volume,**  +   um Ihr Bereitstellungspaket anzuwenden.

### <a name="line-of-business-application-install-status"></a>Installationsstatus der Branchenanwendung

Die Bereitstellung und Verwaltung von MDM-Apps für Branchen-Apps ist für die HoloLens von entscheidender Bedeutung. Administratoren und Benutzer müssen den App-Installationsstatus für die Überwachung und Diagnose anzeigen. In dieser Version haben wir weitere Details unter **Einstellungen**  >  **Konten** Zugriff auf  >  **Arbeits- oder Schulkonto**  >  **Klicken Sie auf Ihre**  >  **Kontoinformationen** hinzugefügt.

### <a name="additional-csps-and-policies"></a>Zusätzliche CSPs und Richtlinien

Ein [Konfigurationsdienstanbieter (Configuration Service Provider, CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ist eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf einem Gerät. In dieser Version fügen wir Unterstützung für weitere Richtlinien hinzu, um die Kontrolle zu erhöhen, die Administratoren über bereitgestellte HoloLens Geräte haben. Eine Liste der von HoloLens unterstützten CSPs finden Sie unter [NetworkQoSPolicy-CSP.](/windows/client-management/mdm/networkqospolicy-csp)

Neu in dieser Version:

**Policy CSP** 

Der Richtlinienkonfigurations-Dienstanbieter ermöglicht dem Unternehmen das Konfigurieren von Richtlinien auf Windows Geräten. In dieser Version haben wir neue Richtlinien für HoloLens hinzugefügt, die hier aufgeführt sind. Weitere Informationen finden Sie unter [Richtlinien-CSPs,](/windows/client-management/mdm/policies-supported-by-hololens2)die von HoloLens 2 unterstützt werden.  

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

Der NetworkQoSPolicy-Konfigurationsdienstanbieter erstellt QoS-Richtlinien (Network Quality of Service). Eine QoS-Richtlinie führt eine Reihe von Aktionen für den Netzwerkdatenverkehr basierend auf einer Reihe von Abgleichsbedingungen aus. Weitere Informationen finden Sie unter [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Erweiterte USB-Ethernet-Unterstützung für 5G/ETHERNET-Tethergeräte

Unterstützung wurde hinzugefügt, um bestimmte mobile Breitbandgeräte wie 5G-/HOT-Telefone und Wi-Fi-Hotspots zu aktivieren, wenn sie über USB an die HoloLens 2 angeschlossen werden. Diese Geräte werden jetzt in den **Netzwerkeinstellungen als** eine andere Ethernet-Verbindung angezeigt. (Mobile Breitbandgeräte, die einen externen Treiber erfordern, werden nicht unterstützt.) Diese Funktion ermöglicht Verbindungen mit hoher Bandbreite, Wi-Fi nicht verfügbar ist und Wi-Fi Tethering nicht ausreichend leistungsfähigkeit auft. Weitere Informationen zu unterstützten USB-Geräten finden Sie unter [Verbinden zum Bluetooth und USB-C-Geräten.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>Verbesserungen bei der Handnachverfolgung

Dieses Release umfasst mehrere Verbesserungen der Handverfolgung:

- **Pointing-Pose-Stabilität:** Das System spricht sich jetzt dagegen aus, den Zeigefinger zu beugen, wenn er von der Handfläche verblendet wird. Diese Änderung verbessert die Genauigkeit beim Drücken von Schaltflächen, Eingeben, Scrollen von Inhalten und mehr! 
- **Reduziertes versehentliches Tippen in die Luft:** Wir haben die Erkennung der Tippbewegung in die Luft verbessert. Es gibt jetzt weniger versehentliche Aktivierungen in mehreren gängigen Szenarien, z. B. wenn Sie ihre Hände auf Ihre Seiten legen.
- **Zuverlässigkeit des Benutzerwechsels:** Das System ist jetzt schneller und zuverlässiger bei der Aktualisierung der Handgröße, wenn Sie ein Gerät freigeben.
- **Reduziertes Handdiebstahl:** Wir haben die Behandlung von Fällen verbessert, in denen die Sensoren mehr als zwei Hände im Blick haben. Wenn mehrere Personen nah beieinander arbeiten, ist die Wahrscheinlichkeit deutlich geringer, dass die nachverfolgte Hand vom Benutzer zur Hand einer anderen Person in der Szene "springt".
- **Systemzuverlässigkeit:** Es wurde ein Problem behoben, das dazu führte, dass die Handverfolgung nicht mehr funktionierte, wenn das Gerät unter hoher Auslastung steht.

### <a name="dark-mode"></a>Dunkler Modus

Viele Windows-Apps unterstützen jetzt sowohl den dunklen als auch den hellen Modus. HoloLens 2 Können Benutzer den Standardmodus für Apps auswählen, die beide unterstützen. Nach dem Update ist der Standard-App-Modus "dunkel", aber Sie können diese Einstellung leicht ändern: Navigieren Sie zu Einstellungen Systemfarben Wählen Sie Ihren Standard-App-Modus  >    >    >  **aus.** 

Diese "in-Box"-Apps unterstützen den dunklen Modus: 

- Einstellungen 
- Microsoft Store 
- E-Mail 
- Calendar 
- Datei-Explorer 
- Feedback-Hub 
- OneDrive 
- Fotos 
- 3D-Viewer 
- Filme & TV 

![Fenster im dunklen Modus, gekachelt](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systemstimmenbefehle

Sie können nun Sprachbefehle mit jeder App auf dem Gerät verwenden. Weitere Informationen finden Sie unter [Verwenden Ihrer Stimme zum Betreiben HoloLens](hololens-cortana.md). Siehe auch [Unterstützte Sprachen für HoloLens 2](hololens2-language-support.md).  

### <a name="cortana-updates"></a>Cortana Updates

Die aktualisierte App ist in Microsoft 365 integriert, damit Sie ihre Geräte besser nutzen können (derzeit nur in US-English verfügbar). Auf HoloLens 2 unterstützt Cortana gerätespezifische Befehle nicht mehr, z. B. das Anpassen des Volumes oder neustarten. Diese Optionen werden jetzt von den neuen Systemstimmenbefehlen unterstützt. Weitere Informationen zur neuen Cortana-App finden Sie in unserem [Blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Qualitätsverbesserungen und Fehlerbehebungen

Verbesserungen und Fehlerbehebungen auch im Update:  
- Ein aktives Kalibrierungssystem für die Anzeige wurde eingeführt. Dieses Feature verbessert die Stabilität und Ausrichtung von Hologrammen. Sie bleiben nun an Ort und Stelle, wenn Sie den Kopf von Seite zu Seite bewegen.
- Ein Fehler wurde behoben, Wi-Fi streaming to HoloLens in regelmäßigen Abständen unterbrochen wurde. Wenn eine Anwendung angibt, dass streaming mit geringer Latenz benötigt wird, implementieren Sie die Korrektur, indem Sie die [SetSocketMediaStreamingMode-Funktion aufrufen.](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Ein Gerät, das während des Streamings im Forschungsmodus nicht mehr verfügbar war, wurde behoben.
- Es wurde ein Fehler behoben, bei dem in einigen Fällen der richtige Benutzer beim Fortsetzen einer Sitzung nicht auf dem Anmeldebildschirm angezeigt wurde.
- Es wurde ein Problem behoben, bei dem Benutzer MDM-Protokolle nicht über **Einstellungen.**
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
- Ein Problem erfordert, dass Sie die Cortana-App starten, nachdem Sie das Gerät gestartet haben, um die Sprachaktivierung "Hey Cortana" zu verwenden. Wenn Sie ein Update von einem 18362-Build aus, wird möglicherweise auch eine zweite App-Kachel für die vorherige Version der Cortana-App angezeigt, die in Start nicht mehr **funktioniert.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, Version 1903 – Update vom Mai 2020 
- Build 18362.1061

Dieses monatliche Qualitätsupdate enthält keine wichtigsten Änderungen, da das Team an der holografischen Version Windows 2004 May Update arbeitet, wie zuvor beschrieben.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, Version 1903 – Update april 2020
- Build 18362.1059

**Dunkler Modus für unterstützte Apps** 

Viele Windows-Apps unterstützen sowohl den dunklen als auch den hellen Modus. HoloLens 2 Können Kunden jetzt den Standardmodus für Apps auswählen, die beide Farbschemas unterstützen. Basierend auf Kundenfeedback legen wir den Standard-App-Modus auf "dunkel" fest, aber Sie können diese Einstellung jederzeit problemlos ändern: Navigieren Sie zu **Einstellungen > System > Colors,** um **nach "Choose your default app mode"** (Standard-App-Modus auswählen) zu suchen.

Diese "in-Box"-Apps unterstützen den dunklen Modus:
- Einstellungen
- Microsoft Store
- E-Mail
- Calendar
- Datei-Explorer
- Feedback-Hub
- OneDrive
- Fotos
- 3D-Viewer
- Filme & TV

**Verbesserungen und Fehlerbehebungen auch im Update:** 
- Es wurde sichergestellt, dass Shellüberlagerungen in Mixed Reality-Erfassungen enthalten sind.
- Unreal-Entwickler können jetzt die 3D-Ansichtsseite in Geräteportal um ihre Anwendungen zu testen und zu debuggen.
- Verbesserte Hologrammstabilität bei der Mixed Reality-Erfassung, wenn der *HolographicDepthReprojectionMethod DepthReprojection-Algorithmus* verwendet wird.
- Der Fehler "WinRT IStreamSocketListener API Class not registered" (WinRT-IStreamSocketListener-API-Klasse nicht registriert) für 32-Bit-ARM-Apps wurde behoben.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, Version 1903 – Update vom März 2020 
- Build 18362.1056

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Hologrammstabilität bei der Mixed Reality-Erfassung, wenn der *AutoPlanar-Algorithmus HolographicDepthReprojectionMethod* verwendet wird.
- Es wurde sichergestellt, dass das Koordinatensystem, das an ein MF-Tiefenbeispiel angefügt ist, mit der öffentlichen Dokumentation konsistent ist.
- Die Produktivität von Entwicklern wurde verbessert, da Kunden große Mengen von Text über das Geräteportal einfügen können.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, Version 1903 – Update vom Februar 2020 
- Build 18362.1053

Verbesserungen und Fehlerbehebungen im Update:

- Die HolographicSpace.UserPresence-API für Unity-Anwendungen wurde vorübergehend deaktiviert. Durch diese Änderung wird ein Problem vermieden, das dazu führte, dass einige Apps angehalten wurden, wenn das Visor gekippt wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert wurde.
- Es wurde ein zufälliger HUP-Absturz behoben, der durch die Handverfolgung verursacht wurde, bei dem der Benutzer bemerkte, dass die Benutzeroberfläche erst nach einigen Sekunden einfriert und dann wieder in die Shell zurückfing.
- Die Handnachverfolgung wurde verbessert, sodass der obere Teil dieses Fingers beim Pokeen mit dem Zeigefinger weniger wahrscheinlich unerwartet gelockt wird.
- Verbesserte Zuverlässigkeit von Head Tracking, räumlicher Zuordnung und anderen Laufzeiten.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, Version 1903 – Update vom Januar 2020 
- Build 18362.1043
 
Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Stabilität für exklusive Apps bei der Arbeit mit dem HoloLens 2 Emulator.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2019 
- Build 18362.1042

Verbesserungen und Fehlerbehebungen im Update:

- LSR-Korrekturen (Last Stage Veröffentlichung) wurden eingeführt. Verbessertes visuelles Rendering von Hologrammen, um stabiler und präziser zu erscheinen, indem die Tiefe genauer abbucht. Dieses Symptom ist nach diesem Update deutlicher, wenn Apps die Tiefe der Hologramme nicht richtig festlegen.
- Die Stabilität exklusiver Apps und die Navigation zwischen exklusiven Apps wurden korrigiert.
- Es wurde ein Problem behoben, bei dem die Mixed Reality-Erfassung kein Video aufzeichnen konnte, nachdem sich das Gerät mehrere Tage lang im Standbyzustand befindet.
- Verbesserte Hologrammstabilität.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, Version 1903 – Update vom November 2019 
- Build 18362.1039

Verbesserungen und Fehlerbehebungen im Update:

- Die Funktionalität von **Select** voice commands during initial setup for en-CA and en-AU wurde behoben.
- Verbesserte visuelle Qualität von Objekten, die weit entfernt in den neuesten Versionen von Unity und Mixed Reality Toolkit (MRTK) platziert sind.
- Behoben: Probleme mit holografischen Anwendungen, die beim Start in einem angehaltenen Zustand hängen bleiben, bis die Startmenü geöffnet und dann geschlossen wurde.
- Korrekturen und Verbesserungen bei der Konformität mit openXR-Laufzeiten für HoloLens 2 und den Emulator.
