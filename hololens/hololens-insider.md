---
title: Insider-Vorschau für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens bereitstellen.
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
ms.sourcegitcommit: ad725427c2c88e73df2e5753001a26502b2327de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474840"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, erste [Schritte zu machen](hololens-insider.md#start-receiving-insider-builds) und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens zu geben.

## <a name="windows-insider-release-notes"></a>Hinweise zur Windows-Insider-Version

Wir freuen uns darauf, neue Features für Windows-Insider zu starten. Neue Builds werden für die neuesten Updates in den Dev Channel geroutet. Wir werden diese Seite weiterhin aktualisieren, wenn wir weitere Features und Updates zu unseren Windows-Insider-Builds hinzufügen.  Freuen Sie sich und bereiten Sie sich darauf vor, diese Updates in Ihre Realität zu mischen.

Dieses Featureupdate enthält Features für zwei Zielgruppen. Features, die von jedem Benutzer auf einem Gerät verwendet werden können, und neue Geräteverwaltungsoptionen, die von IT-Administratoren konfiguriert werden können. Die folgende Featuretabelle gibt die Zielgruppen an, mit denen die einzelnen neuen Features verwendet werden können. Wenn Sie ein IT-Administrator sind, schauen Sie sich bitte unseren [IT-Administrator – Prüfliste zum Aktualisieren an.](#it-admin---update-checklist)

> [!IMPORTANT]
> Wenn Sie zuvor entweder die Einstellungs-App oder die Microsoft Edge-App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, [neue AUMIDs für neue Apps im Kioskmodus weiter unten zu](#use-the-new-settings-and-edge-apps-in-kiosk-modes) lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin die Einstellungs-App in Ihrem Kiosk haben oder die neue Microsoft Edge-App enthalten.

<br>

| Featurename                                              | Kurze Beschreibung                                                                      | Zielpublikum | Im Build verfügbar |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Neuer Microsoft Edge-Browser](#introducing-the-new-microsoft-edge) | Das neue, Chromium-basierte Microsoft Edge ist jetzt für HoloLens 2 verfügbar.                         | Endbenutzer | 20279.1006 |
| [WebXR und 360 Viewer](#webxr-and-360-viewer)             | Probieren Sie immersive Weberfahrungen und 360 Videowiedergabe aus                                           | Endbenutzer | 20289.1000 |
| [App "Neue Einstellungen"](#new-settings-app)                     | Die Ältere Einstellungen-App wird durch eine aktualisierte Version mit neuen Features und Einstellungen ersetzt. | Endbenutzer | 20279.1006 |
| [Anzeigen der Farbkalibrierung](#display-color-calibration)   | Auswählen eines alternativen Farbprofils für Ihre HoloLens 2-Anzeige                                | Endbenutzer | 20293.1000 |
| [Standardmäßige App-Auswahl](#default-app-picker)                 | Auswählen, welche App für jeden Datei- oder Linktyp gestartet werden soll                                      | Endbenutzer | 20279.1006 |
| [Volumensteuerung pro App](#per-app-volume-control) |  Steuern des Volumens auf App-Ebene unabhängig vom Systemvolume | Endbenutzer | 20293.1000 |
| [Office Web App](#office-web-app)                         | Eine Verknüpfung zur Office-Web-App ist jetzt unter "Alle Apps" aufgeführt.                                   | Endbenutzer | 20279.1006 |
| [Wischen zum Eingeben](#swipe-to-type)                           | Verwenden der Fingerspitze zum "Wischen" von Wörtern auf der holografischen Tastatur                        | Endbenutzer | 20279.1006 |
| [Hauptmenü vom Start](#power-menu-from-start) | Starten Sie das HoloLens-Gerät im Startmenü neu, und fahren Sie es herunter. | Endbenutzer | 20293.1000 |
| [Mehrere Benutzer auf dem Anmeldebildschirm aufgeführt](#multiple-users-listed-on-sign-in-screen) | Anzeigen mehrerer Benutzerkonten auf dem Anmeldebildschirm | Endbenutzer | 20293.1000 |
| [Unterstützung für externes USB-C-Mikrofon](#usb-c-external-microphone-support) | Verwenden Sie USB-C-Mikrofone für Apps und/oder Remote Assist.| Endbenutzer | 20279.1006 |
| [Automatische Besucheranmeldung für Kioske](#visitor-auto-logon-for-kiosks)                          | Ermöglicht die automatische Anmeldung für Besucherkonten für kiosk-Modi.                         | IT-Administrator | 20279.1006                 |
| [Neue AUMIDs für neue Apps im Kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs für neue Einstellungen und Edge-Apps | IT-Administrator | 20279.1006 |
| [Verbesserte Übergabe von Fehlern im Kioskmodus](#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Kioskmodus sucht vor dem leeren Startmenü nach global zugewiesenem Zugriff. | IT-Administrator | 20279.1006 |
| [Neue EinstellungenURIs für Sichtbarkeit von Seiteneinstellungen](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Mehr als 20 neue SettingsURIs für Einstellungen/PageVisibilityList-Richtlinie | IT-Administrator | 20289.1000 |
| [Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app) | Festlegen des Fallbackdiagnoseverhaltens in der App "Einstellungen" | IT-Administrator | 20279.1006 |
| [Teilen von Dingen mit Geräten in der Nähe](#share-things-with-nearby-devices) | Freigeben von Dateien oder URLs von einer HoloLens auf einem PC | Alle | 20279.1006 |
| [Problembehandlung für neues Betriebssystemupdate](#new-os-update-troubleshooter) | Neue Problembehandlung unter Einstellungen für Betriebssystemupdates | IT-Administrator | 20279.1006 |
| [Vorschau der Übermittlungsoptimierung](#delivery-optimization-preview) | Verringern des Bandbreitenverbrauchs für Downloads von mehreren HoloLens-Geräten | IT-Administrator | 20301.1000 |
| [Verbesserungen und Korrekturen im Update](#improvements-and-fixes-in-the-update) | Zusätzliche Korrekturen im Update. | Alle | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT-Administrator – Prüfliste für Updates

Diese Prüfliste hilft Ihnen, die neuen Elemente zu kennen, die in diesem Featureupdate hinzugefügt werden, die sich auf Ihre aktuellen Geräteverwaltungskonfigurationen auswirken können, oder neue Features, die Sie möglicherweise verwenden möchten.

#### <a name="updates-to-kiosk-mode"></a>Updates für den Kioskmodus

[**Neue AUMIDs für neue Apps im Kioskmodus**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Wenn Sie zuvor entweder die Einstellungs-App oder die Microsoft Edge-App in einem Kiosk verwendet haben, haben wir diese Apps durch neue Apps ersetzt, die eine andere App-ID verwenden. Wir empfehlen Ihnen dringend, [neue AUMIDs für neue Apps im Kioskmodus weiter unten zu](#use-the-new-settings-and-edge-apps-in-kiosk-modes) lesen. Dadurch wird sichergestellt, dass Sie entweder weiterhin die Einstellungs-App in Ihrem Kiosk haben oder die neue Microsoft Edge-App enthalten.

Diese Änderungen können jetzt vorgenommen und auf allen Geräten bereitgestellt werden und ermöglichen einen reibungslosen Übergang beim Update.

[**Automatische Besucheranmeldung für Kioske**](#visitor-auto-logon-for-kiosks)

Besucher können jetzt automatisch an einem Kiosk angemeldet werden. Dieses Verhalten ist standardmäßig aktiviert, kann jedoch verwaltet und deaktiviert werden.

[**Verbesserte Übergabe von Fehlern im Kioskmodus**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Wenn die AAD-Gruppenmitgliedschaft des angemeldeten AAD-Benutzers nicht erfolgreich ermittelt wird, wird die globale Kioskkonfiguration für das Startmenü verwendet (sofern vorhanden), andernfalls wird dem Benutzer ein leeres Startmenü angezeigt. Während das leere Startmenü keine Konfiguration ist, die Sie direkt festlegen können, kann diese neue Behandlung etwas sein, um Ihre Supportabteilung darüber zu informieren, ob Sie Kioske verwenden, da dies möglicherweise für Ihre Konfigurationen gilt oder Sie neue Anpassungen an Den zugewiesenen Zugriffskonfigurationen vornehmen möchten.

#### <a name="updates-to-page-settings-visibility"></a>Aktualisierungen der Sichtbarkeit von Seiteneinstellungen

[**Neue EinstellungenURIs für Sichtbarkeit von Seiteneinstellungen**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Wenn Sie derzeit die [Sichtbarkeit](settings-uri-list.md) von Seiteneinstellungen verwenden, können Sie Anpassungen an Ihren vorhandenen URIs vornehmen, die Sie entweder zugelassen oder blockiert haben.

#### <a name="updates-for-your-wdac-policy"></a>Updates für Ihre WDAC-Richtlinie

Wenn Sie Microsoft Edge zuvor über WDAC blockiert haben, sollten Sie Ihre WDAC-Richtlinie aktualisieren. Überprüfen [Sie Folgendes,](#using-wdac-to-block-new-microsoft-edge) und verwenden Sie den bereitgestellten Beispielcode.

#### <a name="enable-new-endpoints-for-edge"></a>Aktivieren neuer Endpunkte für Edge

Wenn Sie über eine Infrastruktur verfügen, die das Konfigurieren von Netzwerkendpunkten wie Proxy oder Firewall umfasst, aktivieren Sie diese neuen Endpunkte für [die neue Microsoft Edge-App.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>Neu konfigurierbare Elemente

- [Konfigurieren der Fallbackdiagnose](#configuring-fallback-diagnostics-via-settings-app)
  - Sie können konfigurieren, ob und wer Fallbackdiagnosen sammeln kann.
- [Teilen von Dingen mit Geräten in der Nähe](#share-things-with-nearby-devices)
  - Sie können das neue Freigabefeature in der Nähe deaktivieren.
- [Konfigurieren von Richtlinieneinstellungen für das neue Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Überprüfen Sie die neu für Microsoft Edge verfügbaren Konfigurationen.

#### <a name="new-diagnostic-tool"></a>Neues Diagnosetool

- [Problembehandlung für neues Betriebssystemupdate](#new-os-update-troubleshooter)
  - Sammeln von Protokollen im Zusammenhang mit Betriebssystemupdates

### <a name="introducing-the-new-microsoft-edge"></a>Einführung in das neue Microsoft Edge

![Animation des älteren Microsoft Edge-Logos zum neuen Microsoft Edge-Logo](images/new-edge.gif)

Das neue Microsoft Edge [übernimmt das Open -Source-Projekt Chromium,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) um eine bessere Kompatibilität für Kunden und eine geringere Fragmentierung des Webs für Webentwickler zu schaffen.

Mit dieser Insidervorschau ist das neue Microsoft Edge zum ersten Mal für HoloLens 2-Kunden verfügbar! Während das neue Microsoft Edge schließlich microsoft Edge auf HoloLens 2 ersetzt, stehen beide Browser derzeit Insidern zur Verfügung. Bitte teilen Sie Feedback und Fehler mit unserem Team über das **Feature** Feedback senden im neuen Microsoft Edge oder über [den FeedbackHub.](hololens-feedback.md)

![Neuer Microsoft Edge-Screenshot](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Starten des neuen Microsoft Edge

Insidern stehen zwei Versionen von Microsoft Edge zur Verfügung: das neue Microsoft Edge-Symbol (dargestellt durch ein blaues und grünes Wirbelsymbol) und das ältere Microsoft Edge (dargestellt durch das weiße ![ ](images/new_edge_logo.png) "e"-Symbol). Das neue Microsoft Edge ist an das Startmenü angeheftet und wird automatisch gestartet, wenn Sie einen Weblink aktivieren. Wenn Sie die Verwendung von Microsoft Edge als Standardwebbrowser wiederherstellen möchten, lesen Sie die Anweisungen unten zum Zurücksetzen [von Standard-Apps.](#default-app-picker)

> [!NOTE]
> Wenn Sie das neue Microsoft Edge auf HoloLens 2 zum ersten Mal starten, werden Ihre Einstellungen und Daten aus älteren Microsoft Edge importiert. Wenn Sie microsoft Edge nach dem Starten des neuen Microsoft Edge weiterhin verwenden, werden diese neuen Daten nicht von Microsoft Edge mit dem neuen Microsoft Edge synchronisiert.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurieren von Richtlinieneinstellungen für das neue Microsoft Edge

Das neue Microsoft Edge bietet IT-Administratoren einen wesentlich umfangreicheren Satz von Browserrichtlinien für HoloLens 2 als bisher mit Microsoft Edge verfügbar.

Hier sind einige hilfreiche Ressourcen, um mehr über die Verwaltung von Richtlinieneinstellungen für das neue Microsoft Edge zu erfahren:

- [Konfigurieren der Microsoft Edge-Richtlinieneinstellungen mit Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Zuordnung von Richtlinien von Microsoft Edge-Vorgängerversionen zu Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Zuordnung von Richtlinien von Google Chrome zu Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Vollständige [Microsoft Edge Enterprise-Dokumentation](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Aufgrund der Menge von Browserrichtlinien, die vom neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie auf HoloLens 2 funktioniert. Wir haben jedoch getestet und bestätigt, dass die neue Microsoft Edge-Entsprechung jeder früheren Microsoft Edge-Richtlinie, die zuvor für HoloLens 2 unterstützt wurde, wie erwartet funktioniert. Informationen zum neuen Microsoft Edge-Äquivalent jeder älteren Microsoft Edge-Browserrichtlinie, die Sie mit HoloLens 2 verwendet haben, finden Sie unter [Microsoft Edge Legacy to Microsoft Edge policy mapping.](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
>
> Es gibt mindestens zwei neue Microsoft ** Edge-Richtlinien, von deren Verwendung wir wissen, dass holoLens 2 nicht funktioniert:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Was Sie vom neuen Microsoft Edge auf HoloLens 2 erwarten können

Da es sich bei der neuen Microsoft Edge um eine systemeigene Win32-App mit einer neuen UWP-Adapterebene handelt, die die Ausführung auf nur UWP-Geräten wie HoloLens 2 ermöglicht, sind einige Features möglicherweise nicht sofort verfügbar. Wir unterstützen in den kommenden Monaten neue Szenarien und Features. Überprüfen Sie daher diesen Bereich, um aktuelle Informationen zu erhalten.

**Szenarien und Features, die voraussichtlich funktionieren:**
- Erste Ausführung, Anmelden beim Profil und Synchronisierung
- Websites sollten wie erwartet gerendert und verhalten
- Die meisten Browserfunktionen (Favoriten, Verlauf usw.) sollten wie erwartet funktionieren
- Dunkler Modus
- Installieren von Web-Apps auf dem Gerät
- Installieren von Erweiterungen (teilen Sie uns bitte mit, ob Sie Erweiterungen verwenden, die auf HoloLens 2 nicht ordnungsgemäß funktionieren)
- Anzeigen und Markieren einer PDF
- Räumlicher Sound aus einem einzelnen Browserfenster
- Automatische und manuelle Aktualisierung des Browsers
- Speichern einer PDF aus dem Menü Drucken (mit der Option "In PDF speichern")
- WebXR- und 360-Viewer-Erweiterung
- Inhaltswiederherstellung zum Korrigieren des Fensters beim Durchsuchen mehrerer Fenster in Ihrer Umgebung

**Szenarien und Features, die nicht funktionieren sollen:**
- Räumlicher Sound aus mehreren Fenstern mit gleichzeitigen Audiodatenströmen
- "See it, say it"
- Drucken

**Bekannte Probleme im Browser:**
- Wi-Fi Proxykonfigurationen, bei denen es sich um Proxyrichtlinien handelt, die auf einzelne Wi-Fi-Verbindungen zielen, funktionieren derzeit nicht mit dem neuen Microsoft Edge. Wir arbeiten aktiv daran, dieses Problem vor der öffentlichen Veröffentlichung des Betriebssystemupdates zu entsperren.
- Die Vergrößerungsvorschau in der holografischen Tastatur wurde für das neue Microsoft Edge deaktiviert. Wir hoffen, dieses Feature in einem zukünftigen Update wieder aktivieren zu können, sobald die Vergrößerung ordnungsgemäß funktioniert.
- Zwei Zeichen auf der japanischen Tastatur funktionieren im neuen Microsoft Edge nicht wie erwartet. Dieses Problem wurde stammverursachet und sollte bald behoben werden.
- Weblinks in der Microsoft Store-App starten den Browser möglicherweise nicht
- Die Audiowiedergabe kann im falschen Browserfenster angezeigt werden, wenn ein anderes Browserfenster geöffnet und aktiv ist. Sie können dieses Problem beheben, indem Sie das andere aktive Fenster schließen, das keine Audiowiedergabe sein soll.
- Bei der Wiedergabe von Audio aus einem Browserfenster im [Modus "Folgen Sie mir"](hololens2-basic-usage.md#follow-me-stop-following)wird die Audiowiedergabe fortgesetzt, wenn Sie den Modus "Folgen" deaktivieren. Sie können dieses Problem beheben, indem Sie die Audiowiedergabe beenden, bevor Sie den Modus "Folgen" deaktivieren oder das Fenster mit der **Schaltfläche X** schließen.
- Die Interaktion mit aktiven Microsoft Edge-Fenstern kann dazu führen, dass andere 2D-App-Fenster unerwartet inaktiv werden. Sie können diese Fenster reaktivieren, indem Sie erneut mit ihnen interagieren.
- Das Öffnen eines Weblinks von einer anderen App oder bestimmten Dokumententypen wie PDFs kann dazu führen, dass eine zweite leere Registerkarte im Browser geöffnet wird (zusätzlich zur neuen Registerkarte, die mit dem Inhalt des Weblinks oder dateilinks erstellt wurde). Sie können dieses Problem beheben, indem Sie die zusätzliche leere Registerkarte schließen.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge-Insider-Kanäle

Das Microsoft Edge-Team stellt der Edge-Insider-Community drei Vorschaukanäle zur Verfügung: Beta, Dev und Canary. Durch das Installieren eines Vorschaukanals wird die veröffentlichte Version von Microsoft Edge auf HoloLens 2 nicht deinstalliert, und Sie können mehrere gleichzeitig installieren. 

Besuchen Sie [die Microsoft Edge Insider-Homepage,](https://www.microsoftedgeinsider.com) um mehr über die Edge-Insider-Community zu erfahren. Weitere Informationen zu den verschiedenen Edge-Insider-Kanälen und erste Schritte finden Sie auf der [Edge-Insider-Downloadseite.](https://www.microsoftedgeinsider.com/download)

Es stehen mehrere Methoden zum Installieren von Microsoft Edge-Insider-Kanälen in HoloLens 2 zur Verfügung:

**Direkte Installation auf dem Gerät (derzeit nur für nicht verwaltete Geräte verfügbar)**
  1. Besuchen Sie auf Ihrer HoloLens 2 die [Edge-Insider-Downloadseite](https://www.microsoftedgeinsider.com/download).
  1. Wählen Sie **die Schaltfläche Herunterladen für HoloLens 2** für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Starten Sie die heruntergeladene MSIX-Datei aus der Edge-Downloadwarteschlange oder aus dem Ordner "Downloads" Ihres Geräts (mithilfe des Datei-Explorers).
  1. [Das App-Installationsprogramm](app-deploy-app-installer.md) wird gestartet.
  1. Wählen Sie die **Schaltfläche Installieren** aus.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der **Liste Alle** Apps im Startmenü.

**Installieren über PC mit dem [](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) Windows Device Portal (für HoloLens 2 muss der Entwicklermodus aktiviert sein)**
  1. Besuchen Sie auf Ihrem PC die [Edge-Insider-Downloadseite](https://www.microsoftedgeinsider.com/download).
  1. Wählen Sie **die Dropdownpfeilschaltfläche** neben der Schaltfläche "Für Windows 10 herunterladen" für den Edge-Insider-Kanal aus, den Sie installieren möchten.
  1. Wählen **Sie holoLens 2** im Dropdownmenü aus.
  1. Speichern Sie die MSIX-Datei im Ordner "Downloads" Ihres PCs (oder in einem anderen Ordner, den Sie leicht finden können).
  1. Verwenden [Sie das Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC, um die heruntergeladene .msix-Datei auf HoloLens 2 zu installieren.
  1. Nach der erfolgreichen Installation finden Sie Microsoft Edge Beta, Dev oder Canary als separaten Eintrag in der **Liste Alle** Apps im Startmenü.

> [!NOTE]
> Während dieser Windows-Insider-Vorschau für HoloLens 2 ist die Version von Microsoft Edge auf Ihrem Gerät möglicherweise höher als die version, die in einigen (oder allen) Microsoft Edge-Insider-Kanälen verfügbar ist. Dadurch soll sichergestellt werden, dass neue Features und Korrekturen, die speziell auf den Webbrowser in HoloLens 2 zielen, so schnell wie möglich zu unseren Windows-Insidern kommen. Kurz nach der öffentlichen Veröffentlichung des nächsten Windows-Updates werden die Microsoft Edge-Insider-Kanalbuilds die Version von Microsoft Edge auf HoloLens 2 übertreffen und vor ihnen bleiben.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Blockieren neuer Microsoft Edge mithilfe von WDAC

Für IT-Administratoren, die ihre [WDAC-Richtlinie](windows-defender-application-control-wdac.md) aktualisieren möchten, um die neue Microsoft Edge-App zu blockieren, müssen Sie Ihrer Richtlinie Folgendes hinzufügen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Verwalten von Endpunkten für das neue Microsoft Edge

In einigen Umgebungen müssen möglicherweise Netzwerkeinschränkungen berücksichtigt werden. Um eine reibungslose Oberfläche mit dem neuen Edge zu gewährleisten, aktivieren Sie [diese Microsoft-Endpunkte.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Lesen Sie mehr über die derzeit [verfügbaren Endpunkte für HoloLens](hololens-offline.md).

### <a name="webxr-and-360-viewer"></a>WebXR und 360 Viewer

*Hinzugefügt in Windows Insider Build 20289.1000*

Das neue Microsoft Edge umfasst Unterstützung für WebXR, der neue Standard für die Erstellung immersiver Weberfahrungen (ersetzt WebVR). Viele immersive Weberfahrungen wurden im Hinblick auf VR entworfen (sie ersetzen Ihr Sichtfeld durch eine virtuelle Umgebung), aber diese Erfahrungen werden auch von HoloLens 2 unterstützt. Der WebXR-Standard ermöglicht auch immersive Weberfahrungen mit erweiterter und gemischter Realität, die Ihre physische Umgebung verwenden. Da Entwickler mehr Zeit mit WebXR verbringen, erwarten wir, dass neue immersive Augmented- und Mixed Reality-Erfahrungen für HoloLens 2-Kunden verfügbar sein werden.

Die Erweiterung 360 Viewer baut auf WebXR auf und wird automatisch zusammen mit dem neuen Microsoft Edge auf HoloLens 2 installiert. Mit dieser Weberweiterung können Sie sich in 360-Grad-Videos eintauchen. YouTube bietet die größte Auswahl von 360 Videos, daher empfehlen wir Ihnen, dort zu beginnen.

#### <a name="how-to-use-webxr"></a>Verwenden von WebXR

1. Navigieren Sie zu einer Website mit WebXR-Unterstützung.
1. Wählen Sie **die Schaltfläche VR** eingeben auf der Website aus. Der Speicherort und die visuelle Darstellung dieser Schaltfläche können je nach Website variieren, sie sieht jedoch ähnlich aus wie:

    ![Beispiel für die Eingabe von VR-Schaltflächen](images/75px-enter-vr.png)

1. Wenn Sie das erste Mal versuchen, eine WebXR-Umgebung in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung, um eine immersive Ansicht einzuholen, und wählen Sie **Zulassen aus.**
1. Verwenden [Sie HoloLens 2-Gesten, um](hololens2-basic-usage.md#the-hand-tracking-frame) die Benutzererfahrung zu ändern.
1. Wenn die Benutzererfahrung nicht über eine **Exit-Schaltfläche** verfügt, verwenden Sie die [Startgeste,](hololens2-basic-usage.md#start-gesture) um nach Hause zurückzukehren.

**Empfohlene WebXR-Beispiele**
- 360 Viewer (siehe nächster Abschnitt)
- [XR-Dinosaurier](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Verwenden von 360 Viewer

1. Navigieren Sie zu einem 360-Grad-Video auf YouTube.
1. Wählen Sie im Videoframe die Mixed Reality-Headset-Schaltfläche aus:

    ![Schaltfläche zum Aktivieren von 360 Viewer](images/enter-360-viewer.jpg)

1. Wenn Sie versuchen, 360 Viewer zum ersten Mal in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung, um eine immersive Ansicht einzuholen. Wählen Sie **Zulassen**aus.
1. [Luft tippen,](hololens2-basic-usage.md#select-using-air-tap) um die Wiedergabesteuerelemente hoch zu bringen. Verwenden [Sie Handstrahlen](hololens2-basic-usage.md#select-using-air-tap) und Lufttippen, um zu spielen/zu pausieren, vorwärts/zurück zu überspringen, Beschriftungen ein-/auszuschalten oder die Erfahrung zu beenden (wodurch die immersive Ansicht beendet wird). Die Wiedergabesteuerelemente werden nach ein paar Sekunden Inaktivität ausgeblendet.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Bekannte Probleme mit WebXR und 360 Viewer
- Abhängig von der Komplexität der WebXR-Erfahrung kann die Framerate fallen oder stottern.
- Die Unterstützung für gelenkte Handgelenke in WebXR ist standardmäßig nicht aktiviert. Entwickler können die Unterstützung aktivieren, `edge://flags` indem sie "WebXR-Handeingabe" aktivieren.
- Wenn Sie eine WebXR- oder 360-Viewer-Erfahrung beenden, kann es 30 Sekunden oder mehr dauern, bis Hologramme im Mixed-Reality-Heim wieder angezeigt werden.
- 360 Videos von anderen Websites als YouTube funktionieren möglicherweise nicht wie erwartet.
- Captions are currently disabled in 360 Viewer on HoloLens 2. Wir planen, dieses Feature in einem zukünftigen Update zu aktivieren.
- Durch anhalten eines Videos in 360 Viewer wird das Rendern des Videos verhindert (das Auswählen der Wiedergabeschaltfläche setzt die Wiedergabe jedoch ordnungsgemäß fort).
- Die Schaltfläche "Nächstes Video" in 360 Viewer funktioniert derzeit nicht.
- Sie können 2D-Videos in einem immersiven "Theater"-Modus abspielen, die Framerate kann jedoch weniger als 30 fps sein.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Bereitstellen von Feedback zu WebXR und 360 Viewer

Teilen Sie feedback und Bugs mit unserem Team über das **Feature** Feedback senden im neuen Microsoft Edge.

### <a name="new-settings-app"></a>App "Neue Einstellungen"

Mit dieser Version stellen wir eine neue Version der Einstellungs-App vor. Die neue Einstellungs-App enthält neue Features und erweiterte Einstellungen für HoloLens 2 in den folgenden Bereichen: Sound, Power & Sleep, Network & Internet, Apps, Accounts, Ease of Access und vieles mehr.

> [!NOTE]
> Da sich die neue Einstellungs-App von der älteren Einstellungs-App unterscheidet, werden alle Einstellungen, die Sie zuvor in Ihrer Umgebung platziert haben, nach dem Update entfernt.

![Startseite der App "Neue Einstellungen"](images/new-settings-app.png)

**Neue Features und Einstellungen**
- Einstellungssuche: Suchen Sie auf der Startseite "Einstellungen" mithilfe von Schlüsselwörtern oder dem Namen der Einstellung nach Einstellungen.
- System > Sound:
  - Eingabe- und Ausgabeaudiogeräte: Wählen Sie unabhängig Ihre Ein- und Ausgabeaudiogeräte aus (z. B. Audio über Bluetooth-Kopfhörer abhören oder ein USB-C-Mikrofon für die Audioeingabe verwenden).
    > [!NOTE]
    > Bluetooth Mikrofone werden von HoloLens 2 nicht unterstützt.
  - App-Volume: Passen Sie das Volumen der einzelnen Apps unabhängig an. Weitere [Informationen finden Sie unter Volume Control pro App.](#per-app-volume-control)
- System > Power &: Wählen Sie aus, wann das Gerät nach einer Phase der Inaktivität in den Ruhezustand wechseln soll.
- System > Battery: Aktivieren Sie den Stromsparmodus manuell, oder legen Sie einen Akkuschwellenwert ein, an dem der Stromsparmodus automatisch aktiviert wird.
- Geräte > USB: Sie können USB-Verbindungen standardmäßig deaktivieren.
- Netzwerk & Internet:
  - USB-C-Ethernet-Adapter werden jetzt in Network & Internet angezeigt.
  - Usb-C-Ethernet-Adaptereinstellungen sind jetzt verfügbar, einschließlich der IP-Adresse.
  - Sie können jetzt den Flugzeugmodus auf HoloLens 2 aktivieren.
- Apps: Sie können die Standard-Apps zurücksetzen, die für Datei- und Linktypen verwendet werden. Weitere Informationen finden Sie unter [Standard-App-Auswahl](#default-app-picker).
- Konten > Andere Benutzer: Gerätebesitzer können Benutzer hinzufügen, Standardbenutzer auf Gerätebesitzer aktualisieren, Gerätebesitzer auf Standardbenutzer herabstufen und Benutzer entfernen.
- Einfache Bedienung: Ändern der Textgröße und einiger visueller Effekte.

**Bekannte Probleme**
- Zuvor platzierte Einstellungsfenster werden entfernt (siehe Hinweis oben).
- Sie können Ihr Gerät nicht mehr mit der Einstellungs-App umbenennen. #A0 können Geräte mithilfe der [Windows Autopilot für HoloLens 2-Gerätenamenvorlage](https://docs.microsoft.com/hololens/hololens2-autopilot) oder des Knotens MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName umbenennen.
- Die Seite "Ethernet" zeigt ein virtuelles Ethernet-Gerät ("UsbNcm") immer an.
- Der Akkuverbrauch für das neue Microsoft Edge ist aufgrund seiner Art als Win32-Desktopanwendung, die von einer UWP-Adapterschicht unterstützt wird, möglicherweise nicht genau (es wird keine Korrektur in Kürze erwartet).

### <a name="display-color-calibration"></a>Anzeigen der Farbkalibrierung

*Hinzugefügt in Windows Insider Build 20293.1000*

Mit dieser neuen Einstellung können Sie ein alternatives Farbprofil für Ihre HoloLens 2-Anzeige auswählen. Dies kann dazu beitragen, dass Farben genauer angezeigt werden, insbesondere bei niedrigeren Helligkeitsstufen. Die Anzeigefarbkalibrierung finden Sie in der App Einstellungen auf der Seite System > Kalibrierung.

> [!NOTE]
> Da mit dieser Einstellung ein neues Farbprofil in Ihrer Anzeigefirmware gespeichert wird, handelt es sich um eine Geräteeinstellung (und nicht für jedes Benutzerkonto eindeutig).

#### <a name="how-to-use-display-color-calibration"></a>Verwenden der Anzeigefarbkalibrierung

1. Starten **** Sie die Einstellungs-App, und navigieren Sie zu **System > Kalibrierung**.
1. Wählen **Sie unter Farbkalibrierung anzeigen**die Schaltfläche **Farbkalibrierung anzeigen** aus.
1. Die Anzeigefarbkalibrierung wird gestartet und Sie ermutigen, sicherzustellen, dass sich Ihr Visier an der richtigen Position befindet.
1. Nachdem Sie die Dialogfelder der Anweisung durchdunkelt haben, wird die Anzeige automatisch auf 30 % Helligkeit abgeblendet.
    > [!TIP]
    > Wenn Sie probleme haben, die abgeblendete Szene in Ihrer Umgebung zu sehen, können Sie die Helligkeit von HoloLens 2 manuell mithilfe der Helligkeitsschaltflächen auf der linken Seite des Geräts anpassen.
1. Wählen Sie die Schaltflächen 1 bis 6 aus, um jedes Farbprofil sofort auszuprobieren, und suchen Sie eins, das für Ihre Augen am besten aussieht (dies bedeutet in der Regel, dass das Profil, das die Szene am neutralsten erscheinen lässt, mit dem Graustufenmuster und den Skintönen wie erwartet aussieht).)

    ![Anzeigen der Farbkalibrierungsszene](images/color-cal-ui.png)
    
1. Wenn Sie mit dem ausgewählten Profil zufrieden sind, wählen Sie die Schaltfläche & **Beenden** speichern aus.
1. Wenn Sie keine Änderungen vornehmen möchten, wählen Sie die Schaltfläche Abbrechen **& Beenden** aus, und Ihre Änderungen werden zurückgesetzt.

> [!TIP]
> Im Folgenden finden Sie einige hilfreiche Tipps, die Sie bei der Verwendung der Einstellung für die Farbkalibrierung beachten sollten:
> - Sie können die Farbkalibrierung in den Einstellungen jederzeit erneut ausführen.
> - Wenn jemand auf dem Gerät zuvor die Einstellung zum Ändern von Farbprofilen verwendet hat, wird das Datum/die Uhrzeit der letzten Änderung auf der Seite Einstellungen angezeigt.
> - Wenn Sie die Farbkalibrierung erneut ausführen, wird das zuvor gespeicherte Farbprofil hervorgehoben, und Profil 0 wird nicht angezeigt (da Profil 0 das ursprüngliche Farbprofil der Anzeige darstellt)
> - Wenn Sie zum ursprünglichen Farbprofil der Anzeige zurückkehren möchten, können Sie dies über die Seite Einstellungen (siehe Zurücksetzen [des Farbprofils) tun.](#how-to-reset-color-profile)

#### <a name="how-to-reset-color-profile"></a>Zurücksetzen des Farbprofils

Wenn Sie mit dem in HoloLens 2 gespeicherten benutzerdefinierten Farbprofil nicht unzufrieden sind, können Sie das ursprüngliche Farbprofil des Geräts wiederherstellen:
1. Starten **** Sie die Einstellungs-App, und navigieren Sie zu **System > Kalibrierung**.
1. Wählen **Sie unter Farbkalibrierung anzeigen**die Schaltfläche Auf **Standardfarbprofil zurücksetzen** aus.
1. Wenn das Dialogfeld geöffnet wird, wählen Sie **Neustarten** aus, wenn Sie HoloLens 2 neu starten und Ihre Änderungen anwenden möchten.

#### <a name="top-display-color-calibration-known-issues"></a>Bekannte Probleme bei der Farbkalibrierung der obersten Anzeige

- Auf der Seite Einstellungen ist die Statuszeichenfolge, die Ihnen mitteilt, wann das Farbprofil zuletzt geändert wurde, veraltet, bis Sie diese Seite der Einstellungen neu laden.
    - Problemumgehung: Wählen Sie eine andere Einstellungsseite aus, und wählen Sie dann die Seite Kalibrierung erneut aus.

### <a name="default-app-picker"></a>Standardmäßige App-Auswahl

Wenn Sie einen Hyperlink aktivieren oder einen Dateityp mit mehr als einer installierten App öffnen, die ihn unterstützt, wird ein neues Fenster geöffnet, in dem Sie aufgefordert werden, auszuwählen, welche installierte App die Datei oder den Linktyp verarbeiten soll. In diesem Fenster können Sie auch festlegen, dass die ausgewählte App die Datei oder den Linktyp "Einmal" oder "Immer" verarbeiten soll.

![App-Auswahlfenster](images/default-app-picker.png)

Wenn Sie "Immer" auswählen, aber später ändern möchten, welche App eine bestimmte Datei oder einen bestimmten Linktyp verarbeitet, können Sie ihre gespeicherten Standardeinstellungen unter Einstellungen **> Apps zurücksetzen.** Scrollen Sie zum unteren Rand **** der Seite, und wählen Sie die Schaltfläche Löschen unter "Standard-Apps für Dateitypen" und/oder "Standard-Apps für Linktypen" aus. Im Gegensatz zur ähnlichen Einstellung auf Desktop-PCs können Sie die Standardeinstellungen für einzelne Dateitypen nicht zurücksetzen.

### <a name="per-app-volume-control"></a>Volumensteuerung pro App

In diesem Windows-Insider-Build können Benutzer nun die Lautstärke der einzelnen Apps manuell anpassen. Dies ermöglicht Benutzern, sich besser auf die Apps zu konzentrieren, die sie benötigen, oder besser zu hören, wenn sie mehrere Apps verwenden. Beispielsweise muss die Lautstärke einer App heruntergefahren werden, während eine andere Person zur Remoteunterstützung in einer anderen Person aufruft.

Zum Festlegen der Lautstärke einer einzelnen App navigieren Sie zu **Einstellungen**Systemsound , und wählen Sie unter Erweiterte Soundoptionen die Option  ->  ****  ->  **** **App-Volume- und Geräteeinstellungen aus.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office Web App

>[!NOTE]
>Ab Windows Insider Build 20325.1000 wird die Office-Web-App nicht mehr vorinstalliert (und nicht für die anstehende öffentliche Version des Betriebssystemupdates vorinstalliert). Um die Office-Web-App zu installieren, besuchen Sie die Schaltfläche App Verfügbar oder Installieren https://www.office.com von **Office** in der Adressleiste. **** Wählen **Sie Installieren aus,** um dies zu bestätigen.

Die Office-Web-App wurde der Liste "Alle Apps" im Startmenü hinzugefügt. Diese Web-App kann auch an Start angeheftet oder deinstalliert werden. Da es sich um eine Web-App handelt, entspricht ihre Funktionalität genau dem, was Sie beim Besuch erleben https://www.office.com würden. Office Web App-Funktionen sind nur verfügbar, wenn HoloLens 2 über eine aktive Internetverbindung verfügt.

**Bekanntes Problem**
- Durch zurücksetzen des Geräts wird die Office-Web-App entfernt.

### <a name="swipe-to-type"></a>Wischen zum Eingeben

Für einige Kunden ist es schneller, auf virtuellen Tastaturen "einzugeben", indem sie die Form des Worts, das sie eingeben möchten, schwenken, und wir sehen uns diese Funktion für die holografische Tastatur in der Vorschau an. Sie können ein Wort gleichzeitig wischen, indem Sie die Fingerspitze durch die Ebene der holografischen Tastatur übergeben, die Form des Worts wischen und dann die Fingerspitze aus der Tastaturebene ziehen. Sie können Nach-oben-Wörter wischnen, ohne die Leertaste drücken zu müssen, indem Sie den Finger von der Tastatur zwischen Wörtern entfernen. Sie wissen, dass das Feature funktioniert, wenn auf der Tastatur ein Wischpfad nach der Bewegung des Fingers angezeigt wird.

Bitte beachten Sie, dass diese Funktion aufgrund der Art einer holografischen Tastatur, bei der Sie keinen Widerstand gegen Ihren Finger spüren (im Gegensatz zu einem Mobiltelefondisplay), schwierig zu verwenden und zu mastern sein kann. Wir bewerten dieses Feature für die öffentliche Veröffentlichung, daher ist Ihr Feedback wichtig. Ob Sie das Feature nützlich finden oder ein positives Feedback haben, teilen Sie uns bitte über [den Feedback Hub mit.](hololens-feedback.md)

### <a name="power-menu-from-start"></a>Hauptmenü vom Start

Ein neues Menü, mit dem der Benutzer das Gerät abmelden, herunterfahren und neu starten kann. Ein Indikator auf dem HoloLens-Startbildschirm, der zeigt, wann ein Systemupdate verfügbar ist.

#### <a name="how-to-use"></a>Verwendung

1. Öffnen Sie den HoloLens-Startbildschirm mit der [Startgeste](hololens2-basic-usage.md#start-gesture) oder dem Spruch "Go to Start".

2. Beachten Sie das Auslassungssymbol (...) neben dem Benutzerprofilbild:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Wählen Sie das Benutzerprofilbild mit Ihren Händen oder dem Sprachbefehl "Power" aus.

4. Es wird ein Menü mit Optionen zum Abmelden, Neustarten oder Herunterfahren des Geräts angezeigt:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Wählen Sie die Menüoptionen zum Abmelden, Neustarten oder Herunterfahren Ihrer HoloLens aus. Die Option Abmelden ist möglicherweise nicht verfügbar, wenn das Gerät für ein einzelnes [Microsoft-Konto (MSA) oder ein lokales Konto eingerichtet ist.](hololens-identity.md)

6. Schließen Sie das Menü, indem Sie eine andere Stelle berühren oder das Startmenü mit der Startgeste schließen.

#### <a name="update-indicator"></a>Updateindikator

Wenn ein Update verfügbar ist, wird das Auslassungssymbol angezeigt, um anzugeben, dass ein Neustart das Update installiert. Die Menüoptionen ändern sich auch, um das Vorhandensein des Updates wider zuspiegeln.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Mehrere Benutzer auf dem Anmeldebildschirm aufgeführt

Zuvor wurde auf dem Anmeldebildschirm nur der zuletzt angemeldete Benutzer sowie ein Einstiegspunkt "Anderer Benutzer" angezeigt. Wir haben Kundenfeedback erhalten, dass dies nicht ausreicht, wenn sich mehrere Benutzer am Gerät angemeldet haben. Sie mussten ihren Benutzernamen usw. noch neu eingeben.

In diesem Windows-Insider-Build **** eingeführt, zeigt der Anmeldebildschirm beim Auswählen eines anderen Benutzers, der sich rechts neben dem PIN-Eintragsfeld befindet, mehrere Benutzer mit zuvor beim Gerät angemeldeten Benutzern an. Auf diese Weise können Benutzer ihr Benutzerprofil auswählen und sich dann mit ihren Windows Hello-Anmeldeinformationen anmelden. Ein neuer Benutzer kann dem Gerät auch über die Schaltfläche Konto hinzufügen auf dieser Seite Andere **Benutzer hinzugefügt** werden.

Wenn sie im Menü Andere Benutzer angezeigt werden, zeigt die Schaltfläche Andere Benutzer den letzten benutzer an, der am Gerät angemeldet ist. Wählen Sie diese Schaltfläche aus, um zum Anmeldebildschirm für diesen Benutzer zurückzukehren.

![Standardeinstellung des Anmeldebildschirms](./images/multiusers1.jpg)

<br>

![Anmeldebildschirm für andere Benutzer](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Unterstützung für externes USB-C-Mikrofon

> [!IMPORTANT]
> Wenn Sie ein **USB-Mikrofon anschließen,** wird es nicht automatisch als Eingabegerät festgelegt. Beim Anschließen einer Reihe von USB-C-Kopfhörern werden Benutzer feststellen, dass die Audiodaten des Kopfhörers automatisch an die Kopfhörer umgeleitet werden, aber das HoloLens-Betriebssystem priorisiert das interne Mikrofonarray über jedem anderen Eingabegerät. **Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**

Benutzer können externe USB-C-verbundene Mikrofone im Bereich **Soundeinstellungen** auswählen. USB-C-Mikrofone können für Anrufe, Aufzeichnungen usw. verwendet werden.

Öffnen Sie die **Einstellungs-App,** und wählen **Sie**  >  **Systemsound aus.**

![Soundeinstellungen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Um externe Mikrofone mit **Remoteunterstützung**zu verwenden, müssen Benutzer auf den Link "Soundgeräte verwalten" klicken.
>
> Verwenden Sie dann die Dropdownliste, um das externe Mikrofon entweder als **Standard** oder als **Kommunikations-Standard zu setzen.** Wenn Sie **Standard auswählen,** wird das externe Mikrofon überall verwendet.
>
> Die Auswahl **von Communications Default** bedeutet, dass das externe Mikrofon in remote assist und anderen Kommunikations-Apps verwendet wird, aber das HoloLens-Mikrofonarray kann weiterhin für andere Aufgaben verwendet werden.

![Verwalten von Soundgeräten](images/usbc-mic-2.png)

<br>

![Festlegen der Standardeinstellung des Mikrofons](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Wie sieht es mit Bluetooth Mikrofonunterstützung aus?

Leider Bluetooth Mikrofone derzeit noch nicht in HoloLens 2 unterstützt.

#### <a name="troubleshooting-usb-c-microphones"></a>Problembehandlung bei USB-C-Mikrofonen

Beachten Sie, dass einige USB-C-Mikrofone sich fälschlicherweise sowohl als Mikrofon als auch *als Lautsprecher* melden. Dies ist ein Problem mit dem Mikrofon und nicht mit HoloLens. Wenn Eines dieser Mikrofone in HoloLens angeschlossen wird, geht der Sound möglicherweise verloren. Glücklicherweise gibt es eine einfache Lösung.  

Legen **Sie**  ->  **unter Einstellungen Systemsound**die integrierten Lautsprecher  ->  **** **(Analog Feature Audio Driver)** explizit als **Standardgerät fest.** HoloLens sollte diese Einstellung auch dann beachten, wenn das Mikrofon entfernt und später wieder verbunden wird.

![Problembehandlung bei USB-C-Mikrofonen](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatische Besucheranmeldung für Kioske

Mit diesem neuen Feature kann die automatische Anmeldung für Besucherkonten für Kioskmodi verwendet werden.

Für eine Nicht-AAD-Konfiguration, um ein Gerät für die automatische Besucheranmeldung zu konfigurieren:

1. Erstellen Sie ein Bereitstellungspaket, das:
    1. Konfiguriert **Laufzeiteinstellungen/AssignedAccess so,** dass Besucherkonten zulässig sind.
    1. Registriert das Gerät optional in MDM **(Laufzeiteinstellungen/Workplace/Enrollments),** damit es später verwaltet werden kann.
    1. Kein lokales Konto erstellen
1. [Wenden Sie das Bereitstellungspaket an.](hololens-provisioning.md)

Bei einer AAD-Konfiguration können Benutzer heute ohne diese Änderung ähnliche Ergebnisse erzielen. AAD-angeschlossene Geräte, die für den Kioskmodus konfiguriert sind, können sich bei einem Besucherkonto anmelden, wenn sie mit einer einzelnen Schaltfläche auf dem Anmeldebildschirm tippen. Nach der Anmeldung beim Besucherkonto wird das Gerät erst dann zur erneuten Anmeldung aufgefordert, wenn der Besucher explizit aus dem Startmenü abmeldet oder das Gerät neu gestartet wird.

Die automatische Anmeldung von Besuchern kann über eine benutzerdefinierte [OMA-URI-Richtlinie verwaltet](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) werden:

- URI-Wert: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Richtlinie  | Beschreibung   | Konfigurationen  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Ermöglicht die automatische Anmeldung eines Besuchers bei einem Kiosk   | 1 (Ja), 0 (Nein, Standard).)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Verwenden der neuen Einstellungen und Edge-Apps im Kioskmodus

Beim Hinzufügen von Apps in [Kioske](hololens-kiosk.md)fügt ein IT-Administrator die App häufig zum Kiosk hinzu, verwendet jedoch die App User Model ID (AUMID). Da sowohl die Einstellungs-App als auch die Microsoft Edge-App als neue Apps gelten und sich von den älteren Apps unterscheiden, müssen Kioske, die AUMIDs für diese Apps verwenden, aktualisiert werden, um die neue AUMID zu verwenden.

Wenn Sie einen Kiosk so ändern, dass die neuen Apps hinzugefügt werden, wird empfohlen, die neue AUMID zu hinzufügen und die alte zu verlassen. Dadurch wird ein einfacher Übergang erstellt, wenn Benutzer das Betriebssystem aktualisieren und keine neuen Richtlinien erhalten müssen, um den Kiosk weiterhin wie beabsichtigt zu verwenden.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| App "Alte Einstellungen"       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| App "Neue Einstellungen"       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Alte Microsoft Edge-App | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Neue Microsoft Edge-App | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern

Wenn ein Gerät in älteren Builds eine Kioskkonfiguration hat, bei der es sich um eine Kombination aus dem globalen zugewiesenen[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)Zugriff und dem zugewiesenen Zugriff des AAD-Gruppenmitglieds handelt, wird dem Benutzer beim Ermitteln der AAD-Gruppenmitgliedschaft nichts im Startmenü angezeigt.

Ab Windows-Insider-Version wird die Kioskerfahrung bei Fehlern im Kioskmodus der AAD-Gruppe auf die globale Kioskkonfiguration (sofern vorhanden) zurückfallen.

### <a name="new-settingsuris-for-page-settings-visibility"></a>Neue EinstellungenURIs für Sichtbarkeit von Seiteneinstellungen

In [Windows Holographic, Version 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) haben wir die [Richtlinie Einstellungen/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) hinzugefügt, um die Seiten einzuschränken, die in der Einstellungs-App angezeigt werden. Die PageVisibilityList ist eine Richtlinie, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungs-App sichtbar oder zugänglich sind oder Sie können das für alle Seiten tun, außer den angegebenen.

Wenn Sie die [Sichtbarkeit von Seiteneinstellungen besuchen,](settings-uri-list.md)finden Sie Anweisungen zur Verwendung dieses CSP und die Liste der URIs, die in früheren Versionen verfügbar sind.

In Windows-Insider-Builds erweitern wir die Liste der verfügbaren UrIs für Einstellungen, die von IT-Administratoren verwaltet werden können. Einige dieser URIs sind für neu verfügbare Bereiche innerhalb der neuen Einstellungs-App. Wenn Sie Einstellungen/PageVisibilityList-Richtlinie verwenden, überprüfen Sie die folgende Liste, und passen Sie die zulässigen oder blockierten Seiten nach Bedarf an.

> [!NOTE]
> **Veraltet: ms-settings:network-proxy**
>
> Eine Einstellungsseite ist in diesen neueren Builds veraltet. Die alte **Seite & Internetproxy**  >  **** ist nicht mehr als globale Einstellung verfügbar. Die neuen Proxyeinstellungen pro Verbindung finden Sie unter **Network & Internet**  >  **Wi-Fi**  >  **Properties** oder Network **& Internet**  >  **Ethernet**  >  **Properties**.

<br>

| Einstellungsseite                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps & Features                               | `ms-settings:appsfeatures`                         |
| Apps > Apps & features > Advanced options          | `ms-settings:appsfeatures-app`                     |
| Apps > Offlinekarten                                  | `ms-settings:maps`                                 |
| Apps > Offlinekarten > Karten herunterladen                  | `ms-settings:maps-downloadmaps`                    |
| Geräte > Maus                                      | `ms-settings:mouse`                                |
| Geräte > USB                                        | `ms-settings:usb`                                  |
| Netzwerk & Internet > Flugzeugmodus                   | `ms-settings:network-airplanemode`                 |
| Datenschutz > Allgemein                                    | `ms-settings:privacy-general`                      |
| Datenschutz > Freihandeingabe & Personalisierung             | `ms-settings:privacy-speechtyping`                 |
| Datenschutz > Bewegung                                     | `ms-settings:privacy-motion`                       |
| Datenschutz > Screenshot-Rahmen                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Datenschutz > Screenshots und Apps                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Akku                                     | `ms-settings:batterysaver`                         |
| System > Akku                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound >-App-Volume- und Geräteeinstellungen | `ms-settings:apps-volume`                          |
| System > Sound > Verwalten von Soundgeräten              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Zeit & Sprache > Datum & Uhrzeit                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Zeit & Sprache > Sprache                           | `ms-settings:language`                             |
| Zeit & Sprache > Sprache                           | `ms-settings:regionlanguage-languageoptions`       |
| Update & Security > Reset & Recovery               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualisierte URIs

Zuvor haben die folgenden beiden URIs einen Benutzer nicht direkt zu den angegebenen Seiten weitergeleitet, sondern nur die Hauptaktualisierungsseite blockiert. Die folgenden Elemente wurden aktualisiert, um direkt auf ihre Seiten zu folgen:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurieren der Fallbackdiagnose über die Einstellungs-App

Jetzt kann ein Benutzer in der Einstellungs-App das Verhalten der [Fallbackdiagnose konfigurieren.](hololens-diagnostic-logs.md) Navigieren Sie auf **** der Seite Einstellungen-App zu  ->  **Datenschutzbehandlung,** um diese Einstellung zu konfigurieren.

> [!NOTE]
> Wenn für das Gerät eine MDM-Richtlinie konfiguriert ist, kann der Benutzer dieses Verhalten nicht außer Kraft setzen.  

### <a name="share-things-with-nearby-devices"></a>Teilen von Dingen mit Geräten in der Nähe

Teilen Sie Dinge mit Near von Windows 10-Geräten, einschließlich PCs und anderen HoloLens 2-Geräten, auf denen HoloLens Insider Builds 20279.1006+ ausgeführt wird. Sie können es unter **Einstellungen**System freigegebene Erfahrungen ausprobieren, um Dateien oder URLs von  ->  ****  ->  **** einer HoloLens auf einem PC zu teilen. Weitere Informationen finden Sie unter Teilen von Dingen mit Geräten in der Nähe [in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Dieses Feature kann über [Connectivity/AllowConnectedDevices verwaltet werden.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-update-troubleshooter"></a>Problembehandlung für neues Betriebssystemupdate

Zusätzlich zu den vorherigen Problembehandlungen in der Einstellungs-App wurde mit der neuen Einstellungs-App für Betriebssystemupdates eine neue Problembehandlung hinzugefügt. Navigieren Sie zu **Einstellungen**  ->  **Update &amp; Security**  >  **Troubleshoot**  >  **Windows Update,** und wählen Sie Start **aus.** Auf diese Weise können Sie Ablaufverfolgungen sammeln, während Sie Ihr Problem mit Betriebssystemupdates reprodukieren, um die Problembehandlung mit Ihrer IT oder Ihrem Support zu verbessern.

### <a name="delivery-optimization-preview"></a>Vorschau der Übermittlungsoptimierung

Mit diesem HoloLens-Insider-Update ermöglicht Windows Holographic for Business eine frühe Vorschau für Übermittlungsoptimierungseinstellungen, um den Bandbreitenverbrauch für Downloads von mehreren HoloLens-Geräten zu reduzieren. Eine vollständigere Beschreibung dieser Funktionalität zusammen mit der empfohlenen Netzwerkkonfiguration finden Sie hier: [Übermittlungsoptimierung für Windows 10-Updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Die folgenden Einstellungen sind als Teil der Verwaltungsoberfläche aktiviert und [können über Intune konfiguriert werden:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

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

Einige Vorbehalte zu diesem Vorschauangebot:

- Die HoloLens-Unterstützung ist in dieser Vorschau nur auf Betriebssystemupdates beschränkt.
- Windows Holographic for Business unterstützt nur #A0 und -Downloads von einem [Microsoft Connected Cache-Endpunkt;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Peer-zu-Peer-Downloadmodi und Gruppenzuweisungen werden derzeit für HoloLens-Geräte nicht unterstützt.
- HoloLens unterstützt keine Bereitstellungs- oder Übermittlungsoptimierung für Windows Server Update Services-Endpunkte.
- Für die Problembehandlung ist entweder eine Diagnose auf dem Verbundenen Cacheserver **** erforderlich, oder es ist eine Ablaufverfolgung für HoloLens auf HoloLens über Einstellungen  >  **update & Security**  >   **Troubleshooting**Windows  >   **Update erforderlich.**

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Korrekturen im Update:

- [Die Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics) enthält auch zusätzliche Geräteinformationen für Seriennummer und Betriebssystemversion.

### <a name="known-issues-and-work-around"></a>Bekannte Probleme und Problemumarbeitung

#### <a name="pairing-hololens-to-pc"></a>Koppeln von HoloLens mit DEM PC

Vor dem Windows-Insider-Build 20325.1000, als ein Benutzer Kopplungsanmeldeinformationen für [Windows Holographic, Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) oder [Windows Holographic, Version 2004,](hololens-release-notes.md#windows-holographic-version-2004) festgelegt und auf die Windows-Insider-Builds aktualisiert hatte, funktionierten ihre vorherigen Satzanmeldeinformationen zum Koppeln der HoloLens mit dem PC zum Bereitstellen und Debuggen von Apps wie über Visual Studio nicht mehr. Windows Insider Build 20325.1000 behebt dieses Problem und erfordert keine zusätzlichen Aktionen, um die Verwendung des Geräteportals fortsetzen zu können.

Benutzer, die ihr Gerät mit einem [Insider-Build](#ffu-download-and-flash-directions) aufblitzen lassen, müssen nun ihre Geräte (entweder auf 20325.1000+ oder einen GA-Build) umschalten, um ihre Geräte mit ihrem PC zu koppeln.

Benutzer, die sich nicht bei Windows-Insidern registriert haben und das Featureupdate verwenden, wenn es allgemein verfügbar ist, sind davon nicht betroffen.


## <a name="start-receiving-insider-builds"></a>Starten des Empfangens von Insiderbuilds

> [!NOTE]
> Wenn Sie vor kurzem noch nicht aktualisiert wurden, starten Sie ihr Gerät neu, um den Status zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche Neustart unter Einstellungen/Windows-Insider-Programm auswählen.
>
> Wir hatten einen Fehler im Back-End, auf den Sie möglicherweise gestoßen sind, und dies wird Sie wieder auf kurs bringen.

Wechseln Sie auf einem HoloLens 2-Gerät zu Einstellungen ****  >  **Update &**  >  **Windows-Insider-Sicherheitsprogramm,** und wählen Sie **Erste Schritte aus.** Verknüpfen Sie das Konto, mit dem Sie sich als Windows-Insider registriert haben.

Windows-Insider ziehen jetzt zu Kanäle. Der **Fast-Ring** wird zum **Dev Channel,** der **langsame** Ring zum **Betakanal**und der **Release Preview-Ring** wird zum Release **Preview Channel**. So sieht diese Zuordnung aus:

![Erläuterung von Windows-Insider-Kanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.

Wählen Sie dann **Aktive Entwicklung von Windows**aus, wählen Sie aus, ob Sie Dev **Channel-** oder **Betakanalbuilds** erhalten möchten, und überprüfen Sie die Programmbedingungen.

Wählen **Sie Bestätigen > Jetzt neu starten aus,** um fertig zu werden. Nachdem Ihr Gerät neu gestartet wurde, wechseln Sie zu Einstellungen **> Update & Security > Suchen** Sie nach Updates, um den neuesten Build zu erhalten.

### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 work-around
Wenn beim Aktualisieren auf dem Dev- oder Betakanal ein Updatefehler 0x80070490, versuchen Sie es mit der folgenden kurzfristigen Arbeit. Dazu gehört das Verschieben Ihres Insiderkanals, das Aufnehmen des Updates und das anschließende Verschieben des Insider-Kanals.

#### <a name="stage-one---release-preview"></a>Phase 1 – Release Preview
1.  Einstellungen, Update & Security, Windows Insider Program, wählen **Sie Release Preview Channel aus.**
2.  Einstellungen, Update & Security, Windows Update, **Check for updates**. Fahren Sie nach dem Update mit Phase 2 fort.

#### <a name="stage-two---dev-channel"></a>Phase 2 – Dev Channel
1. Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Dev Channel aus.**
2. Einstellungen, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU-Download- und Flash-Wegbeschreibungen
Zum Testen mit einem flight-signierten ffu müssen Sie zunächst ihr Gerät entsperren, bevor Sie die ffu mit Flight-Signierten blinken.
1. Auf dem PC:

    1. Laden Sie ffu von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren sie ARC (Advanced Recovery Companion) aus dem Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Auf HoloLens – Flight Unlock: **Öffnen**Sie Einstellungen  >  **Update & Windows**  >  **Insider-Sicherheitsprogramm,** registrieren Sie sich, starten Sie das Gerät neu.

1. Flash FFU – Jetzt können Sie die flight-signierte FFU mithilfe von ARC blitzen.

## <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Berichtsproblemen

Verwenden Sie [die FeedbackHub-App](hololens-feedback.md) auf Ihrer HoloLens, um Feedback zu geben und Probleme zu melden. Die Verwendung des Feedbackhubs stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Achten Sie darauf, die Eingabeaufforderung zu akzeptieren, in der **** Gefragt wird, ob Der Feedbackhub auf Ihren Ordner "Dokumente" zugreifen soll (wählen Sie Ja aus, wenn Sie dazu aufgefordert werden).

## <a name="note-for-developers"></a>Hinweis für Entwickler

Sie sind willkommen und ermutigt, Ihre Anwendungen mithilfe von Insider-Builds von HoloLens zu entwickeln.  Erste Schritte finden Sie in [der HoloLens Developer Documentation.](https://developer.microsoft.com/windows/mixed-reality/development) Diese Anweisungen funktionieren auch für Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für die HoloLens-Entwicklung verwenden.

## <a name="stop-receiving-insider-builds"></a>Beenden des Empfangs von Insiderbuilds

Wenn Sie keine Insiderbuilds von Windows Holographic mehr erhalten möchten, können Sie abmelden, [](hololens-recovery.md) wann Ihre HoloLens einen Produktionsbuild ausgeführt hat, oder Sie können Ihr Gerät mithilfe des Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic wiederhergestellt zu haben.

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die sich nicht bei Insider Preview-Builds registrieren, nach der manuellen Neuinstallation eines neuen Vorschaubuilds einen blauen Bildschirm erhalten würden. Anschließend müssen sie ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie unter diesem bekannten [Problem.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

So überprüfen Sie, ob Ihre HoloLens einen Produktions build ausgeführt:

1. Wechseln Sie **zu Einstellungen > System > Informationen**, und suchen Sie die Buildnummer.

1. [Weitere Informationen finden Sie in den Versionshinweisen zu Produktions build numbers](hololens-release-notes.md).

So melden Sie Insiderbuilds ab:

1. Wechseln Sie auf einer HoloLens, die einen Produktionsbuild ausgeführt, zu Einstellungen **> Update & Security > Windows Insider Program,** und wählen Sie Insiderbuilds beenden **aus.**

1. Befolgen Sie die Anweisungen, um Ihr Gerät abmelden.
