---
title: Vorstellung des neuen Microsoft Edge
description: Informationen zur neuen Edge-App
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, Edge, Internet, Browser
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 35d3b38cd442198aec8aaabf46ff7d842c1bf599dbada68718c1d0fa548b2030
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663238"
---
# <a name="introducing-the-new-microsoft-edge"></a>Vorstellung des neuen Microsoft Edge

![Animation vom Logo der Vorgängerversion von Microsoft Edge zum neuen Microsoft Edge-Logo](images/new-edge.gif)

Der neue Microsoft Edge [greift auf das Open-Source-Projekt Chromium zurück](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/), um für Kunden mehr Kompatibilität und für Webentwickler weniger Fragmentierung des Webs zu ermöglichen.

Mit der [Windows Holographic-Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ist der neue Microsoft Edge erstmals auch für HoloLens 2-Kunden verfügbar! Teilen Sie Feedback und Fehler über das Feature **Feedback senden** im neuen Microsoft Edge oder über [Feedback-Hub](hololens-feedback.md) mit unserem Team.

> [!IMPORTANT]
> Diese neue Microsoft Edge-Version ersetzt automatisch die Vorgängerversion von Microsoft Edge, die in neuen Releases [nicht mehr unterstützt](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) wird.

![Screenshot des neuen Microsoft Edge](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Einführung des neuen Microsoft Edge

Der neue Microsoft Edge ![Symbol des neuen Microsoft Edge](images/new_edge_logo.png) (dargestellt durch ein blaugrünes Wirbelsymbol) wird an das Startmenü angeheftet und automatisch gestartet, wenn Sie einen Weblink aktivieren.

> [!NOTE]
> Wenn Sie den neuen Microsoft Edge erstmals auf der HoloLens 2 starten, werden Ihre Einstellungen und Daten aus der Vorgängerversion von Microsoft Edge importiert.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurieren von Richtlinieneinstellungen für den neuen Microsoft Edge

Der neue Microsoft Edge bietet IT-Administratoren auf der HoloLens 2 eine wesentlich breitere Palette an Richtlinien für den Browser als in der Vorgängerversion möglich war.

Hier finden Sie einige hilfreiche Ressourcen, um mehr über die Verwaltung von Richtlinieneinstellungen für den neuen Microsoft Edge zu erfahren:

- [Konfigurieren von Microsoft Edge-Richtlinieneinstellungen mit Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Richtlinienzuordnung zwischen Vorgänger- und neuer Version von Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Richtlinienzuordnung zwischen Google Chrome und Microsoft Edge](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Vollständige [Microsoft Edge Enterprise-Dokumentation](/deployedge/)

> [!IMPORTANT]
> Aufgrund des Umfangs der Browserrichtlinien, die vom neuen Microsoft Edge unterstützt werden, kann unser Team nicht garantieren, dass jede neue Richtlinie auf der HoloLens 2 funktioniert. Wir haben jedoch getestet und bestätigt, dass die neue Microsoft Edge-Entsprechung jeder Richtlinie in der Vorgängerversion von Microsoft Edge, die zuvor auf HoloLens 2 unterstützt wurde, wie erwartet funktioniert. Unter [Richtlinienzuordnung zwischen Vorgänger- und neuer Version von Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) finden Sie die neue Microsoft Edge-Entsprechung jeder Browserrichtlinie in der Vorgängerversion, die Sie mit HoloLens 2 verwendet haben.
>
> Es gibt mindestens zwei neue Microsoft Edge-Richtlinien, von denen wir wissen, dass sie *nicht* mit HoloLens 2 funktionieren:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Was Sie vom neuen Microsoft Edge auf der HoloLens 2 erwarten können

Da es sich beim neuen Microsoft Edge um eine native Win32-App mit neuer UWP-Adapterschicht handelt, die es ermöglicht, auf reinen UWP-Geräten wie der HoloLens 2 ausgeführt zu werden, sind einige Features möglicherweise nicht sofort verfügbar. In den kommenden Monaten werden wir neue Szenarien und Features unterstützen, weshalb Sie an dieser Stelle stets aktuelle Informationen finden.

**Szenarien und Features, die voraussichtlich nicht funktionieren:**
- Erfahrung bei der ersten Inbetriebnahme, Anmeldung am Profil und Synchronisierung
- Das Rendering und Verhalten von Websites sollte wie erwartet sein
- Die meisten Browserfunktionen (Favoriten, Verlauf usw.) sollten wie erwartet funktionieren
- Dunkler Modus
- Installieren von Web-Apps auf dem Gerät
- Installieren von Erweiterungen (teilen Sie uns mit, wenn Sie Erweiterungen verwenden, die auf der HoloLens 2 nicht ordnungsgemäß funktionieren)
- Anzeige und Markup einer PDF-Datei
- Raumklang aus einem einzelnen Browserfenster
- Automatische und manuelle Aktualisierung des Browsers
- Speichern einer PDF-Datei im Menü „Drucken“ (mit der Option „In PDF-Datei speichern“)
- WebXR- und 360 Viewer-Erweiterung
- Inhaltswiederherstellung in richtigem Fenster beim Durchsuchen mehrerer in Ihrer Umgebung platzierter Fenster

**Szenarien und Features, die voraussichtlich nicht funktionieren:**
- Raumklang aus mehreren Fenstern mit gleichzeitigen Audiostreams
- „Sehen, sagen“
- Drucken

**Bekannte Browserprobleme:**
- Die Bildschirmlupenvorschau auf der holografischen Tastatur wurde für den neuen Microsoft Edge deaktiviert. Wir hoffen, dieses Feature in einem künftigen Update wieder aktivieren zu können, sobald die Vergrößerung ordnungsgemäß funktioniert.
- Audio wird möglicherweise im falschen Browserfenster wiedergegeben, wenn ein anderes Browserfenster geöffnet und aktiv ist. Sie können dieses Problem umgehen, indem Sie das andere aktive Fenster schließen, das kein Audio wiedergeben soll.
- Bei der Wiedergabe von Audio über ein Browserfenster im Modus „Mir folgen“ wird das Audio weiter wiedergegeben, wenn Sie den Modus „Mir folgen“ deaktivieren. Sie können dieses Problem umgehen, indem Sie die Audiowiedergabe beenden, bevor Sie den Modus „Mir folgen“ deaktivieren, oder indem Sie das Fenster über die Schaltfläche X schließen.
- Die Interaktion mit aktiven Microsoft Edge-Fenstern kann dazu führen, dass andere 2D-App-Fenster unerwartet inaktiv werden. Sie können diese Fenster reaktivieren, indem Sie erneut mit ihnen interagieren.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-Kanäle

Das Microsoft Edge-Team stellt der Edge Insider-Community drei Vorschaukanäle zur Verfügung: Beta, Dev und Canary. Wenn Sie einen Vorschaukanal installieren, wird die veröffentlichte Version von Microsoft Edge nicht von Ihrer HoloLens 2 deinstalliert. Zudem können Sie mehrere gleichzeitig installieren. 

Besuchen Sie die [Homepage von Microsoft Edge Insider](https://www.microsoftedgeinsider.com), um mehr über die Edge Insider-Community zu erfahren. Weitere Informationen zu den verschiedenen Edge Insider-Kanälen und den ersten Schritte finden Sie auf der [Downloadseite für Edge Insider](https://www.microsoftedgeinsider.com/download).

Es gibt mehrere Methoden zum Installieren von Microsoft Edge Insider-Kanälen für HoloLens 2:

**Direkte Installation auf dem Gerät (derzeit nur für nicht verwaltete Geräte möglich)**
  1. Besuchen Sie auf Ihrer HoloLens 2 die [Downloadseite von Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Wählen Sie die Schaltfläche **Download for HoloLens 2** für den Edge Insider-Kanal aus, den Sie installieren möchten.
  1. Rufen Sie die heruntergeladene MSIX-Datei in der Edge-Downloadwarteschlange oder im Ordner „Downloads“ Ihres Geräts (mithilfe von Datei-Explorer) auf.
  1. Das [App-Installationsprogramm](app-deploy-app-installer.md) wird gestartet.
  1. Wählen Sie die Schaltfläche **Installieren** aus.
  1. Nach erfolgreicher Installation finden Sie im Startmenü in der Liste **Alle Apps** Microsoft Edge Beta, Dev oder Canary als separaten Eintrag.

**Installation über PC mit Windows-Geräteportal (erfordert, dass der [Entwicklermodus](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) auf der HoloLens 2 aktiviert ist)**
  1. Besuchen Sie auf Ihrem PC die [Downloadseite von Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Wählen Sie die **Dropdownpfeilschaltfläche** neben der Schaltfläche „Download for Windows 10“ für den Edge Insider-Kanal aus, den Sie installieren möchten.
  1. Wählen Sie im Dropdownmenü **HoloLens 2** aus.
  1. Speichern Sie die MSIX-Datei im Ordner „Downloads“ Ihres PCs (oder in einem anderen einfach zugänglichen Ordner).
  1. Verwenden Sie das [Windows-Geräteportal](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) auf Ihrem PC, um die heruntergeladene MSIX-Datei auf HoloLens 2 zu installieren.
  1. Nach erfolgreicher Installation finden Sie im Startmenü in der Liste **Alle Apps** Microsoft Edge Beta, Dev oder Canary als separaten Eintrag.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Blockieren des neuen Microsoft Edge mit WDAC

IT-Administratoren, die ihre [WDAC-Richtlinie](windows-defender-application-control-wdac.md) so aktualisieren möchten, dass die neue Microsoft Edge-App blockiert wird, müssen ihrer Richtlinie Folgendes hinzufügen.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Verwalten von Endpunkten für den neuen Microsoft Edge

In einigen Umgebungen gelten möglicherweise Netzwerkeinschränkungen, die berücksichtigt werden müssen. Um eine reibungslose Erfahrung mit dem neuen Edge zu gewährleisten, [aktivieren Sie diese Microsoft-Endpunkte](/deployedge/microsoft-edge-security-endpoints).

Erfahren Sie mehr über die derzeit [verfügbaren Endpunkte für HoloLens](hololens-offline.md).

## <a name="install-web-apps"></a>Installieren von Web-Apps
 > [!Note]
> Ab der [Windows Holographic-Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ist die Web-App „Microsoft Office“ nicht mehr vorinstalliert. 

Sie können den neuen Edge verwenden, um Web-Apps neben Microsoft Store-Apps zu installieren. Beispielsweise können Sie die Microsoft Office-Web-App installieren, um Dateien anzuzeigen und zu bearbeiten, die in SharePoint oder auf OneDrive gehostet werden. Um die Office-Web-App zu installieren, besuchen Sie https://www.office.com. Wählen Sie auf der Adressleiste die Schaltfläche **App verfügbar** oder **Office installieren** aus. Wählen Sie zum Bestätigen **Installieren** aus.
> [!IMPORTANT]
> Office-Web-App-Funktionalität ist nur verfügbar, wenn Ihre HoloLens 2 über eine aktive Internetverbindung verfügt.

## <a name="webxr-and-360-viewer"></a>WebXR und 360 Viewer


Der neue Microsoft Edge unterstützt WebXR, den neuen Standard zum Schaffen immersiver Weberfahrungen (der WebVR ersetzt). Viele immersive Weberfahrungen wurden unter Berücksichtigung von VR entworfen (sie ersetzen Ihr Sichtfeld durch eine virtuelle Umgebung), aber diese Erfahrungen werden auch von der HoloLens 2 unterstützt. Der WebXR-Standard ermöglicht auch immersive Weberfahrungen mittels Augmented und Mixed Reality, die Ihre physische Umgebung nutzen. Je mehr Zeit Entwickler für WebXR aufwenden, desto mehr erwarten wir neue Augmented und Mixed-Reality-Erfahrungen, die HoloLens 2-Kunden ausprobieren können!

Die 360 Viewer-Erweiterung basiert auf WebXR und wird automatisch zusammen mit dem neuen Microsoft Edge auf der HoloLens 2 installiert. Diese Weberweiterung gibt Ihnen die Möglichkeit, in 360-Grad-Videos einzutauchen. YouTube bietet die größte Auswahl an 360-Grad-Videos, weshalb wir Ihnen empfehlen, dort zu beginnen.

### <a name="how-to-use-webxr"></a>Verwendung von WebXR

1. Navigieren Sie zu einer Website mit WebXR-Unterstützung.
1. Wählen Sie auf der Website die Schaltfläche **In VR ansehen** aus. Die Position und visuelle Darstellung dieser Schaltfläche kann je nach Website variieren, sieht aber in etwa so aus:

    ![Beispiel der Schaltfläche „In VR ansehen“](images/75px-enter-vr.png)

1. Wenn Sie zum ersten Mal versuchen, eine WebXR-Umgebung in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung zum Aufrufen einer immersiven Ansicht. Wählen Sie **Zulassen** aus.
1. Verwenden Sie [HoloLens 2-Gesten](hololens2-basic-usage.md#the-hand-tracking-frame), um sich in der Umgebung zu bewegen.
1. Wenn die Umgebung nicht über die Schaltfläche **Beenden** verfügt, kehren Sie mit der [Startgeste](hololens2-basic-usage.md#start-gesture) zur Startseite zurück.

**Empfohlene WebXR-Beispiele**
- 360 Viewer (siehe den nächsten Abschnitt)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Verwenden von 360 Viewer

1. Navigieren Sie auf YouTube zu einem 360-Grad-Video.
1. Wählen Sie im Videoframe die Schaltfläche mit dem Mixed Reality-Headset aus:

    ![Schaltfläche zum Aktivieren von 360 Viewer](images/enter-360-viewer.jpg)

1. Wenn Sie zum ersten Mal versuchen, 360 Viewer in einer bestimmten Domäne zu starten, bittet der Browser um Zustimmung zum Aufrufen einer immersiven Ansicht. Wählen Sie **Zulassen** aus.
1. [Tippen Sie in die Luft](hololens2-basic-usage.md#select-using-air-tap), um die Wiedergabesteuerelemente zu aktivieren. Per [Handstrahl und Tippen in die Luft](hololens2-basic-usage.md#select-using-air-tap) können Sie die Wiedergabe starten/anhalten, vor- und zurückspringen, Untertitel ein-/ausschalten oder die Umgebung beenden (wodurch die immersive Ansicht beendet wird). Die Wiedergabesteuerelemente werden nach einigen Sekunden Inaktivität nicht mehr angezeigt.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Bekannte Probleme mit WebXR und 360 Viewer
- Je nach Komplexität des WebXR-Erlebnisses kann die Framerate abfallen oder ruckeln.
- Die Unterstützung beweglicher Handgelenke in WebXR ist standardmäßig nicht aktiviert. Entwickler können Unterstützung über „edge://flags“ aktivieren, indem sie „WebXR Hand Input“ aktivieren.
- 360-Grad-Videos von anderen Websites als YouTube funktionieren möglicherweise nicht wie erwartet.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Senden von Feedback zu WebXR und 360 Viewer

Teilen Sie Feedback und Fehler über das Feature **Feedback senden** im neuen Microsoft Edge mit unserem Team.
