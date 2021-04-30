---
title: Insider-Vorschau für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen, und geben Sie wertvolles Feedback für unser nächstes größeres Betriebssystemupdate für HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309607"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, [zu](hololens-insider.md#start-receiving-insider-builds) beginnen und wertvolles Feedback für unser nächstes größeres Betriebssystemupdate für HoloLens zu geben.

## <a name="windows-insider-release-notes"></a>Windows-Insider Versionshinweise

Wir freuen uns, neue Features erneut an Windows-Insider zu stellen. Neue Builds werden an den Entwicklungskanal übertragen, um die neuesten Updates zu erhalten. Wir werden diese Seite weiterhin aktualisieren, wenn wir weitere Features und Updates zu unseren Windows-Insider hinzufügen.  Lassen Sie sich freuen und bereit sein, diese Updates in Ihre Realität zu mischen.

Dieses Featureupdate enthält Features für zwei Zielgruppen. Features, die von jedem Benutzer auf einem Gerät verwendet werden können, sowie neue Geräteverwaltungsoptionen, die von IT-Administratoren konfiguriert werden können. In der folgenden Featuretabelle werden die Zielgruppen angegeben, die die einzelnen neuen Features verwenden können. Wenn Sie IT-Administrator sind, sehen Sie sich unsere [Checkliste für IT-Administratoren – Update an.](#it-admin---update-checklist)

> [!IMPORTANT]
> Wenn Sie zuvor entweder die Einstellungs-App oder Microsoft Edge-App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, neue [AUMIDs für neue](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Apps im Kioskmodus weiter unten zu lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin über die Einstellungs-App in Ihrem Kiosk verfügen oder die neue Microsoft Edge enthalten.

<br>

| Funktionsname                                              | Kurze Beschreibung                                                                      | Zielgruppe | Im Build verfügbar |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Neue Microsoft Edge](#introducing-the-new-microsoft-edge) | Die neue Chromium-basierte Microsoft Edge jetzt für HoloLens 2                         | Endbenutzer | 20279.1006 |
| [WebXR und 360 Viewer](#webxr-and-360-viewer)             | Immersive Weberfahrungen und 360 Videowiedergabe ausprobieren                                           | Endbenutzer | 20289.1000 |
| [Neue Einstellungs-App](#new-settings-app)                     | Die Legacy-Einstellungs-App wird durch eine aktualisierte Version mit neuen Features und Einstellungen ersetzt. | Endbenutzer | 20279.1006 |
| [Farbkalibrierung anzeigen](#display-color-calibration)   | Wählen Sie ein alternatives Farbprofil für Ihre HoloLens 2 Anzeige aus.                                | Endbenutzer | 20293.1000 |
| [Standard-App-Auswahl](#default-app-picker)                 | Wählen Sie aus, welche App für die einzelnen Datei- oder Linktypen gestartet werden soll.                                      | Endbenutzer | 20279.1006 |
| [Volumesteuerung pro App](#per-app-volume-control) |  Steuern des Volumes auf App-Ebene unabhängig vom Systemvolume | Endbenutzer | 20293.1000 |
| [Office-Web-App](#office-web-app)                         | Eine Verknüpfung mit der Office-Web-App ist jetzt unter "Alle Apps" aufgeführt.                                   | Endbenutzer | 20279.1006 |
| [Wischen zum Typ](#swipe-to-type)                           | Verwenden Sie die Fingerspitze, um Wörter auf der holografischen Tastatur zu "wischen".                        | Endbenutzer | 20279.1006 |
| [Menü "Energie" über "Start"](#power-menu-from-start) | Starten Sie das HoloLens-Gerät im Startmenü neu, und fahren Sie es herunter. | Endbenutzer | 20293.1000 |
| [Mehrere Benutzer, die auf dem Anmeldebildschirm aufgeführt sind](#multiple-users-listed-on-sign-in-screen) | Anzeigen mehrerer Benutzerkonten auf dem Anmeldebildschirm | Endbenutzer | 20293.1000 |
| [Unterstützung externer USB-C-Mikrofone](#usb-c-external-microphone-support) | Verwenden Sie USB-C-Mikrofone für Apps und/oder Remote Assist.| Endbenutzer | 20279.1006 |
| [Automatische Anmeldung von Besucher für Kioske](#visitor-auto-logon-for-kiosks)                          | Aktiviert die automatische Anmeldung bei Besucherkonten, die für Kioskmodi verwendet werden sollen.                         | IT-Administrator | 20279.1006                 |
| [Neue AUMIDs für neue Apps im Kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs für neue Einstellungen und Edge-Apps | IT-Administrator | 20279.1006 |
| [Verbesserte Übergabe von Fehlern im Kioskmodus](#kiosk-mode-behavior-changes-for-handling-of-failures) | Im Kioskmodus wird vor dem leeren Startmenü nach Global Assigned Access (Globaler zugewiesener Zugriff) sucht. | IT-Administrator | 20279.1006 |
| [Neue EinstellungenURIs für Sichtbarkeit von Seiteneinstellungen](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20+ neue EinstellungenURIs für Einstellungen/PageVisibilityList-Richtlinie | IT-Administrator | 20289.1000 |
| [Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app) | Festlegen des Fallbackdiagnoseverhaltens in der Einstellungs-App | IT-Administrator | 20279.1006 |
| [Freigeben von Dingen für Geräte in der Nähe](#share-things-with-nearby-devices) | Freigeben von Dateien oder URLs aus einer HoloLens für einen PC | Alle | 20279.1006 |
| [Neue Problembehandlung für Betriebssystemupdates](#new-os-update-troubleshooter) | Neue Problembehandlung unter Einstellungen für Betriebssystemupdates | IT-Administrator | 20279.1006 |
| [Übermittlungsoptimierung Preview](#delivery-optimization-preview) | Reduzieren des Bandbreitenverbrauchs für Downloads von mehreren HoloLens-Geräten | IT-Administrator | 20301.1000 |
| [Verbesserungen und Fehlerbehebungen im Update](#improvements-and-fixes-in-the-update) | Zusätzliche Fehlerbehebungen im Update. | Alle | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT-Administrator – Checkliste aktualisieren

Diese Prüfliste hilft Ihnen, die neuen Elemente zu kennen, die in diesem Featureupdate hinzugefügt werden und sich auf Ihre aktuellen Geräteverwaltungskonfigurationen auswirken können, oder neue Features, die Sie möglicherweise verwenden möchten.

#### <a name="updates-to-kiosk-mode"></a>Updates für den Kioskmodus

[**Neue AUMIDs für neue Apps im Kioskmodus**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Wenn Sie zuvor entweder die Einstellungs-App oder Microsoft Edge-App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, neue [AUMIDs für neue](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Apps im Kioskmodus weiter unten zu lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin über die Einstellungs-App in Ihrem Kiosk verfügen oder die neue Microsoft Edge enthalten.

Diese Änderungen können jetzt vorgenommen und auf allen Geräten bereitgestellt werden, um einen reibungsloseren Übergang beim Update zu ermöglichen.

[**Automatische Anmeldung von Besucher für Kioske**](#visitor-auto-logon-for-kiosks)

Besucher können jetzt automatisch an einem Kiosk angemeldet werden. Dieses Verhalten ist standardmäßig aktiviert, kann aber verwaltet und deaktiviert werden.

[**Verbesserte Übergabe von Fehlern im Kioskmodus**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Wenn die AAD-Gruppenmitgliedschaft eines angemeldeten AAD-Benutzers nicht erfolgreich bestimmt wurde, wird die globale Kioskkonfiguration für das Startmenü verwendet (sofern vorhanden). Andernfalls wird dem Benutzer ein leeres Startmenü angezeigt. Das leere Startmenü ist zwar keine Konfiguration, die Sie direkt festlegen können, aber diese neue Behandlung kann Ihre Supportabteilung darüber informieren, wenn Sie Kiosks verwenden, da dies möglicherweise für Ihre Konfigurationen gilt oder Sie neue Anpassungen an Ihren zugewiesenen Zugriffskonfigurationen vornehmen möchten.

#### <a name="updates-to-page-settings-visibility"></a>Aktualisierungen der Sichtbarkeit von Seiteneinstellungen

[**Neue EinstellungenURIs für Sichtbarkeit von Seiteneinstellungen**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Wenn Sie derzeit die [Sichtbarkeit](settings-uri-list.md) von Seiteneinstellungen verwenden, sollten Sie Anpassungen an Ihren vorhandenen URIs vornehmen, die Sie entweder zugelassen oder blockiert haben.

#### <a name="updates-for-your-wdac-policy"></a>Updates für Ihre WDAC-Richtlinie

Wenn Sie zuvor die Microsoft Edge WDAC blockiert haben, sollten Sie Ihre WDAC-Richtlinie aktualisieren. Sehen [Sie sich die folgenden Informationen an,](#using-wdac-to-block-new-microsoft-edge) und verwenden Sie den bereitgestellten Beispielcode.

#### <a name="enable-new-endpoints-for-edge"></a>Aktivieren neuer Endpunkte für Edge

Wenn Sie über eine Infrastruktur verfügen, die die Konfiguration von Netzwerkendpunkten wie Proxy oder Firewall umfasst, aktivieren Sie diese neuen Endpunkte für die neue Microsoft Edge [App.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>Neu konfigurierbare Elemente

- [Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app)
  - Sie können konfigurieren, ob und wer die Fallbackdiagnose erfassen darf.
- [Freigeben von Dingen für Geräte in der Nähe](#share-things-with-nearby-devices)
  - Sie können das neue Feature für die Freigabe in der Nähe deaktivieren.
- [Konfigurieren von Richtlinieneinstellungen für die neue Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Überprüfen Sie die neu verfügbaren Konfigurationen für Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Neues Diagnosetool

- [Neue Problembehandlung für Betriebssystemupdates](#new-os-update-troubleshooter)
  - Sammeln von Protokollen im Zusammenhang mit Betriebssystemupdates

### <a name="introducing-the-new-microsoft-edge"></a>Einführung in die neue Microsoft Edge

![Animation des Legacy-Microsoft Edge-Logos zu einem neuen Microsoft Edge-Logo](images/new-edge.gif)

Die neue Microsoft Edge [übernimmt das Chromium-Open-Source-Projekt,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) um eine bessere Kompatibilität für Kunden und eine geringere Fragmentierung des Webs für Webentwickler zu schaffen.

Mit dieser Insider-Vorschau ist die neue Microsoft Edge zum ersten Mal für HoloLens 2 Kunden verfügbar! Während die neue Microsoft Edge ältere Microsoft Edge auf HoloLens 2 ersetzen wird, sind beide Browser derzeit für Insider verfügbar. Teilen Sie Feedback und Fehler mit unserem Team über das Feature **Feedback senden** im neuen Microsoft Edge oder über [Feedback-Hub](hololens-feedback.md).

![Screenshot der neuen Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Starten des neuen Microsoft Edge

Insidern stehen zwei Versionen von Microsoft Edge zur Verfügung: die neue Microsoft Edge ![ neue Microsoft Edge ](images/new_edge_logo.png) (dargestellt durch ein blaues und grünes Verwirlsymbol) und legacy Microsoft Edge (dargestellt durch das weiße Symbol "e"). Die neue Microsoft Edge wird an die Startmenü angeheftet und automatisch gestartet, wenn Sie einen Weblink aktivieren. Wenn Sie die Verwendung von Legacy-Apps Microsoft Edge Standardwebbrowser zurücksetzen möchten, lesen Sie die anweisungen unten zum Zurücksetzen [von Standard-Apps.](#default-app-picker)

> [!NOTE]
> Wenn Sie die neue Microsoft Edge auf HoloLens 2 starten, werden Ihre Einstellungen und Daten aus legacy-Microsoft Edge. Wenn Sie legacy-Microsoft Edge nach dem Start des neuen Microsoft Edge weiterhin verwenden, werden diese neuen Daten nicht von legacy Microsoft Edge mit dem neuen Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurieren von Richtlinieneinstellungen für die neue Microsoft Edge

Die neue Microsoft Edge bietet IT-Administratoren einen viel umfassenderen Satz von Browserrichtlinien für HoloLens 2, als zuvor bei Legacy-Microsoft Edge.

Im Folgenden finden Sie einige hilfreiche Ressourcen, um mehr über das Verwalten von Richtlinieneinstellungen für die neue Microsoft Edge:

- [Konfigurieren Microsoft Edge Richtlinieneinstellungen mit Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Vorgängerversion von Microsoft Edge, um Microsoft Edge richtlinienzuordnung zu erstellen](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome zum Microsoft Edge der Richtlinienzuordnung](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Vollständige [Microsoft Edge Enterprise-Dokumentation](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Aufgrund des Umfangs der Browserrichtlinien, die von der neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie HoloLens 2. Wir haben jedoch getestet und bestätigt, dass das neue Microsoft Edge-Äquivalent jeder Legacy-Microsoft Edge-Richtlinie, die zuvor für HoloLens 2 unterstützt wurde, wie erwartet funktioniert. Unter [Vorgängerversion von Microsoft Edge sie](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge, wie Sie die neue Microsoft Edge-Entsprechung jeder älteren Microsoft Edge-Browserrichtlinie finden, die Sie mit HoloLens 2.
>
> Es gibt mindestens zwei neue Microsoft Edge, von denen wir wissen, *dass sie nicht* mit den HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Was Sie von der neuen Microsoft Edge auf HoloLens 2

Da die neue Microsoft Edge eine native Win32-App mit einer neuen UWP-Adapterebene ist, die die Ausführung auf nur UWP-Geräten wie HoloLens 2 ermöglicht, sind einige Features möglicherweise nicht sofort verfügbar. Wir werden in den kommenden Monaten neue Szenarien und Features unterstützen. In diesem Bereich finden Sie aktuelle Informationen.

**Szenarien und Features, die funktionieren sollen:**
- Erste Ausführung, Anmeldung beim Profil und Synchronisierung
- Websites sollten wie erwartet gerendert werden und sich verhalten.
- Die meisten Browserfunktionen (Favoriten, Verlauf usw.) sollten wie erwartet funktionieren.
- Dunkler Modus
- Installieren von Web-Apps auf dem Gerät
- Installieren von Erweiterungen (bitte teilen Sie uns mit, wenn Sie Erweiterungen verwenden, die auf HoloLens 2 nicht ordnungsgemäß funktionieren)
- Anzeigen und Markieren einer PDF-Datei
- Räumlicher Sound aus einem einzelnen Browserfenster
- Automatische und manuelle Aktualisierung des Browsers
- Speichern einer PDF-Datei aus dem Menü Drucken (mit der Option "In PDF speichern")
- WebXR- und 360 Viewer-Erweiterung
- Inhaltswiederherstellung im richtigen Fenster beim Durchsuchen mehrerer Fenster in Ihrer Umgebung

**Szenarien und Features funktionieren voraussichtlich nicht:**
- Räumlicher Sound aus mehreren Fenstern mit gleichzeitigen Audiostreams
- "Sehen Sie es, sagen Sie es".
- Drucken

**Bekannte Probleme im Browser:**
- Wi-Fi Proxykonfigurationen, bei denen es sich um Proxyrichtlinien handelt, die auf einzelne Wi-Fi Verbindungen ausgerichtet sind, funktionieren derzeit nicht mit dem neuen Microsoft Edge. Wir arbeiten aktiv daran, dieses Problem vor der öffentlichen Veröffentlichung des Betriebssystemupdates aufzuheben.
- Die Bildschirmlupevorschau in der holografischen Tastatur wurde für die neue Microsoft Edge deaktiviert. Wir hoffen, dieses Feature in einem zukünftigen Update wieder zu ermöglichen, sobald die Vergrößerung ordnungsgemäß funktioniert.
- Zwei Zeichen auf der japanischen Tastatur funktionieren in der neuen Version nicht wie erwartet Microsoft Edge. Dieses Problem wurde grundverursachet und sollte bald behoben werden.
- Weblinks in der Microsoft Store-App starten den Browser möglicherweise nicht
- Audiodaten werden möglicherweise aus dem falschen Browserfenster abspielt, wenn ein anderes Browserfenster geöffnet und aktiv ist. Sie können dieses Problem beheben, indem Sie das andere aktive Fenster schließen, das keine Audiowiedergabe verwenden soll.
- Wenn Sie Audiodaten aus einem Browserfenster im [Modus "Folge mir"](hololens2-basic-usage.md#follow-me-stop-following)wieder geben, wird die Audiowiedergabe fortgesetzt, wenn Sie den Modus "Follow me" deaktivieren. Sie können dieses Problem beheben, indem Sie die Audiowiedergabe beenden, bevor Sie den Modus "Follow me" deaktivieren, oder indem Sie das Fenster mit der **Schaltfläche X** schließen.
- Die Interaktion mit aktiven Microsoft Edge fenstern kann dazu führen, dass andere 2D-App-Fenster unerwartet inaktiv werden. Sie können diese Fenster reaktivieren, indem Sie erneut mit ihnen interagieren.
- Das Öffnen eines Weblinks über eine andere App oder bestimmte Arten von Dokumenten wie PDFs kann dazu führen, dass eine zweite leere Registerkarte im Browser geöffnet wird (zusätzlich zur neuen Registerkarte, die mit dem Inhalt des Weblinks oder Dateilinks erstellt wurde). Sie können dieses Problem beheben, indem Sie die zusätzliche leere Registerkarte schließen.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-Kanäle

Das Microsoft Edge stellt der Edge Insider-Community drei Vorschaukanäle zur Verfügung: Beta, Dev und Canary. Durch die Installation eines Vorschaukanals wird die veröffentlichte Version von Microsoft Edge auf Ihrem HoloLens 2 nicht deinstalliert, und Sie können mehrere gleichzeitig installieren. 

Besuchen Sie [die Microsoft Edge Insider-Homepage,](https://www.microsoftedgeinsider.com) um mehr über die Edge Insider-Community zu erfahren. Weitere Informationen zu den verschiedenen Edge Insider-Kanälen und den ersten Schritte finden Sie auf der [Downloadseite von Edge Insider.](https://www.microsoftedgeinsider.com/download)

Es gibt mehrere Methoden zum Installieren von Insider Microsoft Edge kanälen für HoloLens 2:

**Direkte Installation auf dem Gerät (derzeit nur für nicht verwaltete Geräte verfügbar)**
  1. Besuchen Sie HoloLens 2 Edge [Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie die Schaltfläche Download for HoloLens 2 (Herunterladen **für HoloLens 2)** für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Starten Sie die heruntergeladene MSIX-Datei aus der Edge-Downloadwarteschlange oder aus dem Ordner "Downloads" Ihres Geräts (mithilfe des Datei-Explorers).
  1. [Das App-Installationsprogramm](app-deploy-app-installer.md) wird gestartet.
  1. Wählen Sie die Schaltfläche **Installieren** aus.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der **Alle Apps** Liste der Startmenü.

**Installation über PC mit Windows-Geräteportal (erfordert, dass der [Entwicklermodus](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) auf HoloLens 2 aktiviert ist)**
  1. Besuchen Sie auf Ihrem PC die [Edge Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)
  1. Wählen Sie die **Dropdownpfeilschaltfläche** neben der Schaltfläche "Download for Windows 10" (Herunterladen für Windows 10) für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Wählen Sie im Dropdownmenü **HoloLens 2** aus.
  1. Speichern Sie die MSIX-Datei im Ordner "Downloads" Ihres PCs (oder in einem anderen Ordner, den Sie leicht finden können).
  1. Verwenden Sie [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC, um die heruntergeladene MSIX-Datei auf HoloLens 2 zu installieren.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der **Alle Apps** Liste der Startmenü.

> [!NOTE]
> Während dieser Windows-Insider Vorschauversion für HoloLens 2 ist die Version von Microsoft Edge auf Ihrem Gerät möglicherweise höher als die Version, die in einigen (oder allen) Microsoft Edge Insider-Kanälen verfügbar ist. Dadurch wird sichergestellt, dass neue Features und Fehlerbehebungen speziell für den Webbrowser auf HoloLens 2 so schnell wie möglich zu unseren Windows-Insidern gelangen. Kurz nach der Veröffentlichung des nächsten Windows-Updates werden die Builds des Microsoft Edge Insider-Kanals die Version von Microsoft Edge auf Ihrem HoloLens 2 über- und voraus halten.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Verwenden von WDAC zum Blockieren neuer Microsoft Edge

Für IT-Administratoren, die ihre [WDAC-Richtlinie](windows-defender-application-control-wdac.md) aktualisieren möchten, um die neue Microsoft Edge App zu blockieren, müssen Sie Ihrer Richtlinie Folgendes hinzufügen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Verwalten von Endpunkten für die neue Microsoft Edge

Für einige Umgebungen gelten möglicherweise Netzwerkeinschränkungen, die berücksichtigt werden müssen. Aktivieren Sie diese Microsoft-Endpunkte, um ein reibungsloses Erlebnis mit dem neuen [Edge zu gewährleisten.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Erfahren Sie mehr über die derzeit [verfügbaren Endpunkte für HoloLens](hololens-offline.md).

### <a name="webxr-and-360-viewer"></a>WebXR und 360 Viewer

*Hinzugefügt in Windows-Insider Build 20289.1000*

Die neue Microsoft Edge bietet Unterstützung für WebXR. Dies ist der neue Standard zum Erstellen immersiver Weberfahrungen (ersetzen von WebVR). Viele immersive Webumgebungen wurden im Hinblick auf VR entworfen (sie ersetzen Ihr Sichtfeld durch eine virtuelle Umgebung), aber diese Erfahrungen werden auch von HoloLens 2. Der WebXR-Standard ermöglicht auch immersive Webumgebungen mit Augmented und Mixed Reality, die Ihre physische Umgebung verwenden. Da Entwickler mehr Zeit mit WebXR verbringen, gehen wir davon aus, dass neue immersive Mixed Reality-Umgebungen für HoloLens 2 Kunden eintreffen werden!

Die 360 Viewer-Erweiterung basiert auf WebXR und wird automatisch zusammen mit dem neuen Microsoft Edge auf HoloLens 2. Diese Weberweiterung bietet Ihnen die Möglichkeit, sich in 360-Grad-Videos zu vertiefen. YouTube bietet die größte Auswahl von 360 Videos, daher empfehlen wir Ihnen, dort zu beginnen.

#### <a name="how-to-use-webxr"></a>Verwenden von WebXR

1. Navigieren Sie zu einer Website mit WebXR-Unterstützung.
1. Wählen Sie auf **der Website die Schaltfläche VR** eingeben aus. Der Speicherort und die visuelle Darstellung dieser Schaltfläche können je nach Website variieren, aber sie kann in etwa wie die folgenden aussehen:

    ![Beispiel für VR-Schaltfläche eingeben](images/75px-enter-vr.png)

1. Wenn Sie zum ersten Mal versuchen, eine WebXR-Umgebung in einer bestimmten Domäne zu starten, wird der Browser um Zustimmung für die Eingabe einer immersiven Ansicht bitten. Wählen Sie **Zulassen aus.**
1. Verwenden [HoloLens 2 Gesten,](hololens2-basic-usage.md#the-hand-tracking-frame) um die Benutzererfahrung zu bearbeiten.
1. Wenn die Beerfahrung nicht über die Schaltfläche **Beenden verfügen,** verwenden Sie die [Startgeste,](hololens2-basic-usage.md#start-gesture) um nach Hause zurückzukehren.

**Empfohlene WebXR-Beispiele**
- 360 Viewer (siehe nächster Abschnitt)
- [XR-Aussteller](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Verwenden von 360 Viewer

1. Navigieren Sie zu einem 360-Grad-Video auf YouTube.
1. Wählen Sie im Videoframe die Mixed Reality-Headset-Schaltfläche aus:

    ![Schaltfläche zum Aktivieren von 360 Viewer](images/enter-360-viewer.jpg)

1. Wenn Sie zum ersten Mal versuchen, 360 Viewer für eine bestimmte Domäne zu starten, fordert der Browser um Zustimmung für die Eingabe einer immersiven Ansicht auf. Wählen Sie **Zulassen** aus.
1. [Tippen Sie](hololens2-basic-usage.md#select-using-air-tap) in die Luft, um die Wiedergabesteuerelemente aufzuführen. Verwenden Sie [Handlicht und Luftabzweigung,](hololens2-basic-usage.md#select-using-air-tap) um zu spielen/anzuhalten, Vorwärts/Zurück zu überspringen, Untertitel ein-/auszuschalten oder die Benutzeroberfläche zu beenden (wodurch die immersive Ansicht beendet wird). Die Wiedergabesteuerelemente werden nach einigen Sekunden Inaktivität nicht mehr angezeigt.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Top WebXR and 360 Viewer known issues (Top WebXR und 360 Viewer bekannte Probleme)
- Abhängig von der Komplexität der WebXR-Benutzeroberfläche kann die Framerate fallen oder stuttern.
- Die Unterstützung für artikulierte Handverbindungen in WebXR ist standardmäßig nicht aktiviert. Entwickler können die Unterstützung über `edge://flags` aktivieren, indem sie "WebXR Hand Input" aktivieren.
- Beim Beenden einer WebXR- oder 360 Viewer-Benutzeroberfläche kann es 30 Sekunden oder mehr dauern, bis Hologramme im Mixed Reality Startumgebung erneut angezeigt werden.
- 360 Videos von anderen Websites als YouTube funktionieren möglicherweise nicht wie erwartet.
- Untertitel sind derzeit in 360 Viewer auf HoloLens 2 deaktiviert. Wir planen, dieses Feature in einem zukünftigen Update zu aktivieren.
- Das Anhalten eines Videos in 360 Viewer verhindert, dass das Video gerendert wird (durch Auswählen der Wiedergabeschaltfläche wird die Wiedergabe jedoch ordnungsgemäß fortgesetzt).
- Die Schaltfläche "Nächstes Video" in 360 Viewer funktioniert derzeit nicht.
- Sie können 2D-Videos in einem immersiven "Ungsmodus" wieder geben, aber die Framerate kann kleiner als 30 Fps sein.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Bereitstellen von Feedback zu WebXR und 360 Viewer

Teilen Sie feedback und bugs mit unserem Team über das **Feature Feedback** senden in der neuen Microsoft Edge.

### <a name="new-settings-app"></a>Neue Einstellungs-App

Mit diesem Release führen wir eine neue Version der Einstellungs-App ein. Die neue Einstellungs-App enthält neue Features und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Power & sleep, Network & Internet, Apps, Accounts, Erleichterte Bedienung und mehr.

> [!NOTE]
> Da sich die neue Einstellungs-App von der älteren Einstellungs-App ab unterscheiden, werden alle Einstellungsfenster, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Neue Startseite der Einstellungs-App](images/new-settings-app.png)

**Neue Features und Einstellungen**
- Einstellungssuche: Suchen Sie auf der Startseite einstellungen nach Einstellungen, indem Sie Schlüsselwörter oder den Namen der Einstellung verwenden.
- System > Sound:
  - Eingabe- und Ausgabeaudiogeräte: Wählen Sie Ihre Eingabe- und Ausgabeaudiogeräte unabhängig aus (z. B. audio über Bluetooth-Anschlüsse lauschen oder ein USB-C-Mikrofon für die Audioeingabe verwenden).
    > [!NOTE]
    > Bluetooth-Mikrofone werden von der HoloLens 2.
  - App-Volume: Passen Sie das Volumen jeder App unabhängig an. Siehe [pro App-Volumesteuerung.](#per-app-volume-control)
- System > Power &: Wählen Sie aus, wann das Gerät nach einer Bestimmten Inaktivität in den Ruhezustand wechseln soll.
- System > Akku: Aktivieren Sie den Stromsparmodus manuell, oder legen Sie einen Akkuschwellenwert fest, an dem der Stromsparmodus automatisch eingeschaltet wird.
- Geräte > USB: USB-Verbindungen können standardmäßig deaktiviert werden.
- Netzwerk & Internet:
  - USB-C-Ethernet-Adapter werden jetzt in Network & Internet angezeigt.
  - Die Usb-C-Ethernet-Adaptereinstellungen sind jetzt verfügbar, einschließlich der IP-Adresse.
  - Sie können jetzt den Flugzeugmodus auf HoloLens 2 aktivieren.
- Apps: Sie können die Standard-Apps zurücksetzen, die für Datei- und Linktypen verwendet werden. Weitere Informationen finden Sie unter [Standard-App-Auswahl.](#default-app-picker)
- Konten > Andere Benutzer: Gerätebesitzer können Benutzer hinzufügen, Standardbenutzer auf Gerätebesitzer aktualisieren, Gerätebesitzer auf Standardbenutzer herabstufen und Benutzer entfernen.
- Erleichterte Bedienung: Ändern der Textgröße und einiger visueller Effekte.

**Bekannte Probleme**
- Zuvor platzierte Einstellungsfenster werden entfernt (siehe Hinweis oben).
- Sie können Ihr Gerät nicht mehr mit der App Einstellungen umbenennen. IT-Administratoren können Geräte umbenennen, indem sie die [Windows Autopilot für HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) Gerätenamenvorlage oder den Knoten MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName verwenden.
- Auf der Seite Ethernet wird jederzeit ein virtuelles Ethernet-Gerät ("UsbNcm") angezeigt.
- Der Akkuverbrauch für die neue Microsoft Edge ist aufgrund ihrer Art als Win32-Desktopanwendung, die von einer UWP-Adapterebene unterstützt wird, möglicherweise nicht korrekt (es wird keine Korrektur in Kürze erwartet).

### <a name="display-color-calibration"></a>Farbkalibrierung anzeigen

*Hinzugefügt in Windows-Insider Build 20293.1000*

Mit dieser neuen Einstellung können Sie ein alternatives Farbprofil für Ihre HoloLens 2 Anzeigen auswählen. Dies kann dazu beitragen, dass Farben genauer angezeigt werden, insbesondere bei niedrigeren Helligkeitsstufen der Anzeige. Die Farbkalibrierung für die Anzeige finden Sie in der App Einstellungen auf der Seite System > Kalibrierung.

> [!NOTE]
> Da diese Einstellung ein neues Farbprofil in Ihrer Anzeigefirmware speichert, handelt es sich um eine Geräteeinstellung (die nicht für jedes Benutzerkonto eindeutig ist).

#### <a name="how-to-use-display-color-calibration"></a>Verwenden der Kalibrierung von Anzeigefarben

1. Starten Sie die **App Einstellungen,** und navigieren Sie zu **System > Kalibrierung.**
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
> - Sie können die Kalibrierung der Anzeigefarbe in den Einstellungen jederzeit erneut ausführen.
> - Wenn jemand auf dem Gerät die Einstellung zuvor zum Ändern von Farbprofilen verwendet hat, wird das Datum bzw. die Uhrzeit der letzten Änderung auf der Seite Einstellungen angezeigt.
> - Wenn Sie die Farb kalibrierung der Anzeige erneut ausführen, wird das zuvor gespeicherte Farbprofil hervorgehoben, und Profil 0 wird nicht angezeigt (da Profil 0 das ursprüngliche Farbprofil der Anzeige darstellt).
> - Wenn Sie zum ursprünglichen Farbprofil der Anzeige zurückgesetzt werden möchten, können Sie dies auf der Seite Einstellungen tun (siehe Zurücksetzen [des Farbprofils](#how-to-reset-color-profile)).

#### <a name="how-to-reset-color-profile"></a>Zurücksetzen des Farbprofils

Wenn Sie nicht mit dem benutzerdefinierten Farbprofil in Ihrem HoloLens 2 sind, können Sie das ursprüngliche Farbprofil des Geräts wiederherstellen:
1. Starten Sie die **App Einstellungen,** und navigieren Sie zu **System > Calibration**.
1. Wählen Sie unter **Farbkalibrierung anzeigen** die Schaltfläche **Auf Standardfarbprofil zurücksetzen** aus.
1. Wenn das Dialogfeld geöffnet wird, wählen Sie **Neu starten** aus, wenn Sie bereit sind, HoloLens 2 neu zu starten und Ihre Änderungen zu übernehmen.

#### <a name="top-display-color-calibration-known-issues"></a>Bekannte Probleme bei der Farbkalibrierung der obersten Anzeige

- Auf der Seite Einstellungen ist die Statuszeichenfolge, die Anzeigt, wann das Farbprofil zuletzt geändert wurde, veraltet, bis Sie diese Seite der Einstellungen erneut laden.
    - Problemumgehung: Wählen Sie eine andere Seite Einstellungen aus, und wählen Sie dann die Seite Kalibrierung erneut aus.

### <a name="default-app-picker"></a>Standard-App-Auswahl

Wenn Sie einen Link aktivieren oder einen Dateityp mit mehreren installierten Apps öffnen, die dies unterstützen, wird ein neues Fenster geöffnet, in dem Sie aufgefordert werden, auszuwählen, welche installierte App die Datei oder den Linktyp verarbeiten soll. In diesem Fenster können Sie auch festlegen, dass die ausgewählte App die Datei oder den Linktyp "Einmal" oder "Immer" verarbeitet.

![Fenster "App-Auswahl"](images/default-app-picker.png)

Wenn Sie "Immer" auswählen, aber später ändern möchten, welche App eine bestimmte Datei oder einen bestimmten Linktyp verarbeitet, können Sie Die gespeicherten Standardwerte unter **Einstellungen > Apps** zurücksetzen. Scrollen Sie zum unteren Rand der Seite, und wählen Sie die Schaltfläche **Löschen** unter "Standard-Apps für Dateitypen" und/oder "Standard-Apps für Linktypen" aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardwerte einzelner Dateitypen nicht zurücksetzen.

### <a name="per-app-volume-control"></a>Volumesteuerung pro App

In diesem Windows-Insider können Buildbenutzer die Volumeebene jeder App manuell anpassen. Dies ermöglicht Benutzern, sich besser auf die Apps zu konzentrieren, die sie benötigen, oder besser zu hören, wenn sie mehrere Apps verwenden. Beispielsweise muss das Volumen einer App beim Aufrufen einer anderen Person für Remoteunterstützung in einer anderen App heruntergesetzt werden.

Navigieren Sie zum Festlegen der Lautstärke einer einzelnen App zu **Einstellungen**  ->    ->  **Systemsound,** und wählen Sie unter Erweiterte Soundoptionen **die Option App-Lautstärke und Geräteeinstellungen aus.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office-Web-App

>[!NOTE]
>Ab Windows-Insider Build 20325.1000 wird die Office-Web-App nicht mehr vorinstalliert (und nicht für die bevorstehende öffentliche Version des Betriebssystemupdates vorinstalliert). Um die Office-Web-App zu installieren, besuchen Sie die Schaltfläche App verfügbar oder https://www.office.com **Office** installieren in der Adressleiste, und wählen Sie sie aus.  Wählen Sie **Installieren aus,** um dies zu bestätigen.

Die Office-Web-App wurde der Liste "Alle Apps" im Startmenü. Diese Web-App kann auch an Start oder Deinstallation angeheftet werden. Da es sich um eine Web-App handelt, entspricht ihre Funktionalität genau der Funktionalität, die Sie beim Besuchen von erleben https://www.office.com würden. Die Office-Web-App-Funktionalität ist nur verfügbar, wenn HoloLens 2 eine aktive Internetverbindung hat.

**Bekanntes Problem**
- Durch zurücksetzen Ihres Geräts wird die Office-Web-App entfernt.

### <a name="swipe-to-type"></a>Wischen zum Eingeben

Einige Kunden finden es schneller, auf virtuellen Tastaturen zu "tippen", indem sie die Form des Worts wischen, das sie eingeben möchten, und wir zeigen diese Funktion für die holografische Tastatur in der Vorschau an. Sie können ein Wort nach dem anderen wischen, indem Sie die Fingerspitze durch die Ebene der holografischen Tastatur übergeben, die Form des Worts wischen und dann die Fingerspitze von der Tastaturebene abziehen. Sie können Nach-oben-Wörter wischen, ohne die Abstandsleiste drücken zu müssen, indem Sie den Finger von der Tastatur zwischen Wörtern entfernen. Sie werden wissen, dass das Feature funktioniert, wenn Sie einen Wischpfad sehen, der der Bewegung Des Fingers auf der Tastatur folgt.

Beachten Sie, dass dieses Feature aufgrund der Natur einer holografischen Tastatur, bei der Sie keinen Widerstand gegen Ihren Finger haben (im Gegensatz zu einer Mobiltelefonanzeige), schwierig zu verwenden und zu mastern sein kann. Wir bewerten dieses Feature für die öffentliche Veröffentlichung, daher ist Ihr Feedback wichtig. Unabhängig davon, ob Sie das Feature nützlich finden oder feedbacken möchten, teilen Sie uns dies über [Feedback-Hub.](hololens-feedback.md)

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

In diesem Windows-Insider Build eingeführt: Wenn Sie **Anderer Benutzer** auswählen, der sich rechts neben dem PIN-Eingabefeld befindet, zeigt der Anmeldebildschirm mehrere Benutzer an, die sich zuvor beim Gerät angemeldet haben. Dadurch können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Windows Hello Anmeldeinformationen anmelden. Ein neuer Benutzer kann dem Gerät auch auf dieser Seite Andere Benutzer über die Schaltfläche **Konto hinzufügen** hinzugefügt werden.

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

Für eine Nicht-AAD-Konfiguration, um ein Gerät für die automatische Anmeldung durch Besucher zu konfigurieren:

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

Ab dem Windows-Insider fallt die Kioskerfahrung auf die globale Kioskkonfiguration (falls vorhanden) zurück, falls es während des Kioskmodus der AAD-Gruppe zu Fehlern kommt.

### <a name="new-settingsuris-for-page-settings-visibility"></a>Neue EinstellungenURIs für Sichtbarkeit von Seiteneinstellungen

In [Windows Holographic, Version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) haben wir die Richtlinie [Einstellungen/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) hinzugefügt, um die Seiten einzuschränken, die in der Einstellungs-App angezeigt werden. PageVisibilityList ist eine Richtlinie, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind, oder dies für alle Seiten mit Ausnahme der angegebenen Seiten zu tun.

Wenn Sie Die [Sichtbarkeit von Seiteneinstellungen besuchen,](settings-uri-list.md)finden Sie Anweisungen zur Verwendung dieses CSP und die Liste der URIs, die in früheren Versionen verfügbar waren.

In Windows-Insider builds erweitern wir die Liste der verfügbaren Einstellungs-URIs, die IT-Administratoren verwalten können. Einige dieser URIs gelten für neu verfügbare Bereiche in der neuen Einstellungs-App. Wenn Sie die Richtlinie Settings/PageVisibilityList verwenden, überprüfen Sie die folgende Liste, und passen Sie Ihre zulässigen oder blockierten Seiten nach Bedarf an.

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

Teilen Sie Dinge mit geräten in der Nähe von Windows 10, einschließlich PCs und anderen HoloLens 2-Geräten, auf denen HoloLens Insider-Builds ab 20279.1006 ausgeführt werden. Sie können es unter Freigegebene Systemerfahrungen für Einstellungen ausprobieren, um Dateien oder URLs von  ->    ->   einer HoloLens an einen PC zu teilen. Weitere Informationen finden Sie unter Freigeben von Geräten in der [Nähe in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Dieses Feature kann über [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)verwaltet werden.

### <a name="new-os-update-troubleshooter"></a>Neue Problembehandlung für Betriebssystemupdates

Zusätzlich zu den vorherigen Problembehandlungen in der Einstellungs-App wurde eine neue Problembehandlung mit der neuen App "Einstellungen" für Betriebssystemupdates hinzugefügt. Navigieren Sie zu  ->  **&amp; Sicherheitsupdate** für Einstellungen  >  **problembehandlung**  >  **Windows Update,** und wählen Sie **Starten** aus. Dadurch können Sie Ablaufverfolgungen erfassen, während Sie Ihr Problem mit Betriebssystemupdates reproduzieren, um die Problembehandlung für Ihre IT oder Ihren Support zu verbessern.

### <a name="delivery-optimization-preview"></a>Übermittlungsoptimierung Preview

Mit diesem HoloLens Insider-Update ermöglicht Windows Holographic for Business eine frühe Vorschau für Einstellungen zur Übermittlungsoptimierung, um den Bandbreitenverbrauch für Downloads von mehreren HoloLens-Geräten zu reduzieren. Eine umfassendere Beschreibung dieser Funktionalität zusammen mit der empfohlenen Netzwerkkonfiguration finden Sie hier: [Übermittlungsoptimierung für Windows 10 Updates.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

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

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Fehlerbehebungen im Update:

- [Die Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics) enthält auch zusätzliche Geräteinformationen für Seriennummer und Betriebssystemversion.

### <a name="known-issues-and-work-around"></a>Bekannte Probleme und Problemumknung

#### <a name="pairing-hololens-to-pc"></a>Koppeln von HoloLens mit dem PC

Vor dem Windows-Insider-Build 20325.1000 funktionierten die zuvor festgelegten Anmeldeinformationen zum Koppeln der HoloLens mit dem PC zum Bereitstellen und Debuggen von Apps wie über Visual Studio nicht mehr, als ein Benutzer Anmeldeinformationen für die Kopplung von Anmeldeinformationen unter [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder [Windows Holographic, Version 2004](hololens-release-notes.md#windows-holographic-version-2004) festgelegt und auf die Windows-Insider-Builds aktualisiert hatte. Windows-Insider Build 20325.1000 behebt dieses Problem und erfordert keine zusätzlichen Aktionen, die über das Geräteportal fortgesetzt werden müssen.

Benutzer, die ihr Gerät mit einem [Insider-Build](#ffu-download-and-flash-directions) flasht haben, müssen nun ihre Geräte (auf 20325.1000 oder einen ga-Build) umschalten, um ihre Geräte mit ihrem PC zu koppeln.

Benutzer, die sich nicht bei Windows-Insidern registriert haben und das Featureupdate nutzen, wenn es allgemein verfügbar ist, sind davon nicht betroffen.


## <a name="start-receiving-insider-builds"></a>Starten des Empfangs von Insider-Builds

> [!NOTE]
> Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Status zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche "Neu starten" unter Einstellungen/Windows-Insider auswählen.
>
> Es ist ein Fehler auf dem Back-End aufgetreten, der möglicherweise aufgetreten ist, sodass Sie wieder auf kursierten Stand kommen.

Wechseln Sie auf einem HoloLens 2 Gerät zu **Einstellungen**  >  **aktualisieren & Security** Windows-Insider  >  **Program,** und wählen Sie Erste Schritte **aus.** Verknüpfen Sie das Konto, das Sie zum Registrieren als Windows-Insider verwendet haben.

Windows-Insider wechselt jetzt zu Channels. Der **Fast-Ring** wird zum **Dev-Kanal,** der **langsame** Ring zum **Betakanal** und der **Release preview-Ring** zum **Releasevorschaukanal.** Diese Zuordnung sieht wie folgt aus:

![Erläuterung zu Windows-Insider Kanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter Introducing Windows-Insider Channels on Windows Blogs [(Einführung in Windows-Insider Kanäle](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-Blogs).

Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie aus, ob Sie Dev **Channel** oder **Betakanal** Builds erhalten möchten, und überprüfen Sie die Programmbedingungen.

Wählen Sie **Confirm > Restart Now (Jetzt neu starten)** aus, um den Vorgang abzuschließen. Wechseln Sie nach dem Neustart Ihres Geräts zu **Einstellungen > Update & Security > Suchen nach Updates,** um den neuesten Build zu erhalten.

### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 Problembearbeitung
Wenn beim Aktualisieren im Dev- oder Betakanal ein Updatefehler 0x80070490 wird, versuchen Sie es mit der folgenden kurzfristigen Problemumgemeinung. Dies umfasst das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Verschieben Ihres Insider-Kanals zurück.

#### <a name="stage-one---release-preview"></a>Phase 1: Releasevorschau
1.  Einstellungen, Update & Security, Windows-Insider Program, wählen Release **Preview Channel** aus.
2.  Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.** Fahren Sie nach dem Update mit Phase 2 fort.

#### <a name="stage-two---dev-channel"></a>Phase 2: Entwicklungskanal
1. Einstellungen, Update & Security, Windows-Insider Program, wählen **Sie Dev Channel** aus.
2. Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.**

## <a name="ffu-download-and-flash-directions"></a>FFU-Download und Flash-Anweisungen
Zum Testen mit einem FFU mit Flugsignierung müssen Sie ihr Gerät zunächst entsperren, bevor Sie den FFU-Test mit Flugsignierung blinken.
1. Auf dem PC:

    1. Laden Sie ffu von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren Sie ARC (Advanced Recovery Companion) über Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Auf HoloLens – Flight Unlock: Öffnen Sie das Einstellungsupdate &  >  **Security**  >  **Windows-Insider Program,** registrieren Sie sich, starten Sie das Gerät neu.

1. Flash FFU: Jetzt können Sie die FFU mit Flugsignierung mit ARC flashen.

## <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Melden von Problemen

Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrer HoloLens, um Feedback zu geben und Probleme zu melden. Durch Feedback-Hub wird sichergestellt, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Stellen Sie sicher, dass Sie die Eingabeaufforderung akzeptieren, in der  Sie gefragt werden, ob Sie Feedback-Hub Auf Ihren Ordner Dokumente zugreifen möchten (wählen Sie Ja aus, wenn Sie dazu aufgefordert werden).

## <a name="note-for-developers"></a>Hinweis für Entwickler

Sie sind willkommen und werden aufgefordert, Ihre Anwendungen mitHilfe von Insider-Builds von HoloLens zu entwickeln.  Sehen Sie sich die [HoloLens-Entwicklerdokumentation an,](https://developer.microsoft.com/windows/mixed-reality/development) um zu beginnen. Diese Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio, die Sie bereits für die HoloLens-Entwicklung verwenden.

## <a name="stop-receiving-insider-builds"></a>Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie dies deaktivieren, wenn Ihre HoloLens einen Produktions build ausgeführt, oder Sie können Ihr Gerät mit dem Advanced Recovery Companion wiederherstellen, um Ihr Gerät auf eine Nicht-Insider-Version von Windows Holographic wiederhergestellt zu haben. [](hololens-recovery.md)

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die die Registrierung bei Insider Preview-Builds nach der manuellen Neuinstallation eines neuen Vorschaubuilds aufheben, einen Bluescreen erhalten. Anschließend müssen sie ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie in diesem [bekannten Problem.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

So überprüfen Sie, ob HoloLens einen Produktionsbuild ausführt:

1. Wechseln Sie zu **Einstellungen > System > Informationen**, und suchen Sie die Buildnummer.

1. [Informationen zu den Buildnummern für die Produktion finden Sie in den Versionshinweisen.](hololens-release-notes.md)

So deaktivieren Sie Insider-Builds:

1. Wechseln Sie auf einer HoloLens, die einen Produktionsbuild ausführt, zu **Einstellungen > Update & Security > Windows-Insider Program**, und wählen Sie **Insider-Builds beenden** aus.

1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.
