---
title: Veröffentlichungshinweise für HoloLens 2
description: Informieren Sie sich über Updates in jeder neuen HoloLens-Version.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828253"
---
# Veröffentlichungshinweise für HoloLens 2

Um sicherzustellen, dass Sie mit ihren HoloLens-Geräten eine produktive Erfahrung haben, veröffentlichen wir weiterhin Funktions-, Fehler-und Sicherheitsupdates. Auf dieser Seite können Sie jeden Monat erfahren, was es Neues auf HoloLens gibt. Wenn Sie das neueste HoloLens 2-FFU herunterladen möchten, um Ihr Gerät über [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) zu blinken, können Sie es [hier](https://aka.ms/hololens2download)herunterladen. Diese wird auf dem neuesten Stand gehalten und entspricht dem neuesten allgemein verfügbaren Build. 

HoloLens-Emulator-Versionshinweise finden Sie [hier](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holographisch, Version 2004 – Update vom Juni 2020
- Build 19041,1106

Verbesserungen und Korrekturen im Update:

- Benutzerdefinierte MRC-Datenschreiber verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn Sie nicht angegeben werden.
  - Auf dem MRC-Video Effekt:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (immersives Headset))
  - Auf dem MRC-Audioeffekt:
    - LoopbackGain (der aktuelle Wert für "App-Audiogain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
    - MicrophoneGain (der aktuelle Wert "Mic Audio Gain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
- Dieses Update enthält eine Fehlerkorrektur, die die Audioqualität in Szenarien für Mixed-Reality-Aufnahmen verbessert. Insbesondere sollten alle Audiofehler in der Aufzeichnung beseitigt werden, wenn das Menü "Start" angezeigt wird.
- Verbesserte Hologramm-Stabilität in aufgezeichneten Videos.
- Behebt ein Problem, bei dem Mixed-Reality-Aufnahmen keine Videos aufzeichnen konnten, nachdem das Gerät mehrere Tage lang im Standby-Modus verbleibt.
- Die HolographicSpace. UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert, um ein Problem zu vermeiden, das dazu führt, dass einige apps angehalten werden, wenn das Visor nach oben geklappt wird, auch wenn die Einstellung für die Ausführung im Hintergrund aktiviert ist. Die API ist jetzt für Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Wenn Sie über eine WLAN-Verbindung auf Device Portal zugreifen, kann ein Webbrowser verhindern, dass der Zugriff auf ein ungültiges Zertifikat zurückzuführen ist, was einen Fehler wie "ERR_SSL_PROTOCOL_ERROR" meldet, auch wenn das Gerätezertifikat zuvor als vertrauenswürdig eingestuft wurde.  In diesem Fall können Sie nicht zu Device Portal Fortschreiten, da Optionen zum Ignorieren von Sicherheitswarnungen nicht verfügbar sind.  Dieses Update behebt das Problem.  Wenn das Gerätezertifikat zuvor heruntergeladen und auf einem PC als vertrauenswürdig eingestuft wurde, um Browser Sicherheitswarnungen zu entfernen, und der SSL-Fehler aufgetreten ist, muss das neue Zertifikat heruntergeladen und den Sicherheitswarnungen des Browsers als vertrauenswürdig eingestuft werden.
- Aktivierte Möglichkeit zum Erstellen eines Runtime-Bereitstellungspakets, das eine App mithilfe von MSIX-Paketen installieren kann.
- Neue Einstellung, die Benutzer unter Einstellungen > System > Hologramme finden können, die es Benutzern ermöglichen, alle Hologramme automatisch aus dem "Mixed Reality Home" zu entfernen, wenn das Gerät heruntergefahren wird.
- Ein Problem wurde behoben, durch das HoloLens-apps, die ihr Pixelformat ändern, im HoloLens-Emulator schwarz gerendert wurden.
- Fehler behoben, der während der Iris-Anmeldung einen Absturz verursacht hat.
- Behebt ein Problem mit wiederholten Store-Downloads für bereits aktuelle apps.
- Ein Fehler wurde behoben, um zu verhindern, dass immersive apps Edge mehrmals starten konnten.
- Behebt ein Problem bei der Einführung der Fotos-app in Initialen Stiefeln nach der Aktualisierung aus der 1903-Version.
- Verbesserte Leistung und Zuverlässigkeit.

## Windows holographisch, Version 1903 – Update vom Juni 2020
- Build 18362,1064

Verbesserungen und Korrekturen im Update:

- Benutzerdefinierte MRC-Datenschreiber verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn Sie nicht angegeben werden.
  - Auf dem MRC-Video Effekt:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (immersives Headset))
  - Auf dem MRC-Audioeffekt:
    - LoopbackGain (der aktuelle Wert für "App-Audiogain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
    - MicrophoneGain (der aktuelle Wert "Mic Audio Gain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
- Die HolographicSpace. UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert, um ein Problem zu vermeiden, das dazu führt, dass einige apps angehalten werden, wenn das Visor nach oben geklappt wird, auch wenn die Einstellung für die Ausführung im Hintergrund aktiviert ist. Die API ist jetzt für Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Ein Problem wurde behoben, durch das HoloLens-apps, die ihr Pixelformat ändern, im HoloLens-Emulator schwarz gerendert wurden.
- Behebt ein Problem bei der Einführung der Fotos-app in Initialen Stiefeln nach der Aktualisierung aus der 1903-Version.

## Windows holographisch, Version 2004  
Build-19041,1103

Wir freuen uns, Ihnen unser May 2020 Major-Software-Update für HoloLens 2, **Windows holographische, Version 2004,** bekannt zu geben. Diese Version enthält eine Reihe interessanter neuer Funktionen wie Unterstützung für Windows Autopilot, App Dark Mode, USB-Ethernet-Unterstützung für 5G/LTE-Hotspots und vieles mehr. Wenn Sie auf die neueste Version aktualisieren möchten, öffnen Sie die **Einstellungs-APP**, wechseln Sie zu **Update & Security**, und wählen Sie dann die Schaltfläche **auf Updates überprüfen**aus   . 

|             Feature                              |          Beschreibung                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Vorkonfigurieren und nahtloses Einrichten neuer Geräte für die Produktion mit Windows Autopilot                 |
|       Unterstützung für Fido 2                             |          Unterstützung für FIDO2-Sicherheitsschlüssel, um eine schnelle und sichere Authentifizierung für freigegebene Geräte zu ermöglichen            |
|       Verbesserte Bereitstellung                      |          Nahtloses Anwenden eines Bereitstellungspakets von einem USB-Laufwerk auf Ihr HoloLens                              |
|       Anwendungs Installationsstatus                 |          Überprüfen des Installationsstatus für apps, die über MDM in die HoloLens 2 übertragen wurden, in der Einstellungs-APP              |
|       Konfigurationsdienst Anbieter (LSP)   |          Neue Konfigurationsdienstanbieter (LSP), die die Administrator Steuerungsfunktionen erweitern, wurden hinzugefügt.                 |
|       USB 5G/LTE-Unterstützung                       |          Erweiterte USB-Ethernet-Funktion ermöglicht Unterstützung für 5G/LTE                                    |
|       Dunkler APP-Modus                              |          Dunkler APP-Modus für apps, die den dunklen und hellen Modus unterstützen, wodurch sich die Anzeige verbessert        |
|       Sprachbefehle                             |          Unterstützung für zusätzliche System Sprachbefehle zur Steuerung von HoloLens, Freisprechfunktion                           |
|       Verbesserungen bei der Hand Verfolgung                 |          Verbesserungen bei der Hand Verfolgung machen Tasten und 2D-Schiefer Interaktionen genauer                        |
|       Qualitätsverbesserungen und-Korrekturen                 |          Verschiedene Verbesserungen der Systemleistung und-Zuverlässigkeit auf der gesamten Plattform                            |

### Unterstützung für Windows Autopilot 

Mit Windows Autopilot für HoloLens 2 kann der Geräte Vertriebskanal HoloLens in Ihrem InTune-Mandanten vor der Registrierung registrieren.  Wenn Geräte eintreffen, können Sie als freigegebene Geräte unter Ihrem Mandanten selbst bereitgestellt werden. Um die Vorteile der Selbstbereitstellung zu nutzen, müssen Geräte während des ersten Bildschirms in Setup mit einem USB-c-zu-Ethernet-Dongle oder einem USB-c-zu-LTE-Dongle eine Verbindung mit einem Netzwerk herstellen. 

Wenn ein Benutzer den Self-Deployment-Prozess von Autopilot startet, werden folgende Schritte ausgeführt: 

1. Verknüpfen des Geräts mit Azure Active Directory (Azure AD). 
1. Verwenden von Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren. 
1. Herunterladen der gerätespezifischen Richtlinien, Zertifikate und Netzwerkprofile. 
1. Bereitstellen des Geräts. 
1. Präsentieren des Anmeldebildschirms für den Benutzer. 

Weitere Informationen finden Sie im [Evaluierungshandbuch für Windows Autopilot für HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

**Wenden Sie sich an Ihren Konto-Manager, um jetzt an der Autopilot Preview teilzunehmen. Autopilot-Ready-Geräte werden in Kürze ausgeliefert.**

### FIDO2-Sicherheitsschlüssel-Unterstützung 

Viele von Ihnen teilen ein HoloLens-Gerät mit vielen Personen in einem Arbeits-oder Schulumfeld. Unabhängig davon, ob Geräte von Kursteilnehmern in einem Schulungsraum freigegeben werden oder ob Sie aus einem Geräteschrank ausgecheckt sind, ist es wichtig, dass Sie die Benutzer schnell und einfach ändern können, ohne lange Benutzernamen und Kennwörter eingeben zu müssen. 

Mit Fido können sich alle Personen in Ihrer Organisation (AAD-Mandant) nahtlos bei HoloLens anmelden, ohne einen Benutzernamen oder ein Kennwort einzugeben. 

FIDO2-Sicherheitsschlüssel sind eine unphishing-basierte, auf Standards basierende, Kenn Wort sichere Authentifizierungsmethode, die in jedem Formfaktor enthalten sein kann. Fast Identity online (Fido) ist ein offener Standard für die Kenn Wort freie Authentifizierung. Fido ermöglicht es Benutzern und Organisationen, den Standard zur Anmeldung bei ihren Ressourcen zu nutzen, ohne einen Benutzernamen oder ein Kennwort mit einem externen Sicherheitsschlüssel oder einem in ein Gerät integrierten Plattformschlüssel zu verwenden. 

Lesen Sie die [kennwortgeschützten Sicherheitsdokumente](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) , um zu beginnen. 

### Verbesserte MDM-Registrierung über Bereitstellungspaket 

Mit Bereitstellungspaketen können Sie die HoloLens-Konfiguration über eine config-Datei einrichten, anstatt die HoloLens-Benutzeroberfläche zu durchlaufen. Zuvor mussten Bereitstellungspakete in den internen Speicher von HoloLens kopiert werden, jetzt können Sie sich auf einem USB-Laufwerk befinden, damit Sie auf mehreren HoloLens einfacher wieder verwendet werden können, sodass mehr Personen parallel HoloLens bereitstellen können.  Darüber hinaus unterstützen Bereitstellungspakete ein neues Feld für die Registrierung in der Geräteverwaltung, sodass keine manuelle Einrichtung nach der Bereitstellung erfolgt. 

1. Wenn Sie es ausprobieren möchten, laden Sie die neueste Version des Windows-Konfigurations-Designers aus dem Windows Store auf Ihren PC herunter. 
1. Wählen Sie **HoloLens-Geräte bereit** stellen > wählen Sie **HoloLens 2-Geräte bereit** stellen aus. 
1. Erstellen Sie Ihr Konfigurationsprofil, und kopieren Sie, wenn Sie fertig sind, alle Dateien, die auf einem USB-C-Speichergerät erstellt wurden. 
1. Schließen Sie es in einen neu aufgeblitzten HoloLens ein, und drücken Sie die **Lautstärke** Taste, um Ihr Bereitstellungspaket anzuwenden. 

### Installationsstatus der Branchenanwendung 

Die Bereitstellung und Verwaltung von MDM-Apps für Branchen-Apps ist für unsere Kunden entscheidend. Administratoren und Benutzer müssen in der Lage sein, den App-Installationsstatus zu Überwachungs-und Diagnosezwecken anzuzeigen. In dieser Version fügen wir weitere Informationen in **Einstellungen > Konten > Zugriff auf Arbeit oder Schule > klicken Sie auf Ihr Konto > Informationen.**

### Zusätzliche Kryptografiedienstanbieter und Richtlinien 

Ein [Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ist eine Schnittstelle zum Lesen, festlegen, ändern oder Löschen von Konfigurationseinstellungen auf einem Gerät. In dieser Version wird die Unterstützung für weitere Richtlinien hinzugefügt, und die Steuerelement Administratoren haben mehr als die bereitgestellten HoloLens-Geräte. Eine Liste der von HoloLens unterstützten LSP finden Sie auf diesem [Link](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Neu in dieser Version:

**Richtlinien-Konfigurationsdienstanbieter** 

Der Richtlinien Konfigurationsdienst Anbieter ermöglicht es dem Unternehmen, Richtlinien auf Windows-Geräten zu konfigurieren. In dieser Version fügen wir neue Richtlinien für HoloLens hinzu, die nachstehend aufgeführt sind. Weitere Informationen zu unterstützten Richtlinien finden Sie [hier](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

**NetworkQoSPolicy-CSP** Der NetworkQoSPolicy-Konfigurationsdienst Anbieter erstellt QoS-Richtlinien (Network Quality of Service). Eine QoS-Richtlinie führt eine Reihe von Aktionen für Netzwerkverkehr basierend auf einem Satz von übereinstimmenden Bedingungen aus. Weitere Informationen zu dieser Richtlinie finden Sie [hier](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). 

### Erweiterte USB-Ethernet-Unterstützung für 5G/LTE-angebundene Geräte

Unterstützung wurde hinzugefügt, um bestimmte mobile Breitbandgeräte wie 5G/LTE-Telefone und WLAN-Eintöpfen zu aktivieren, wenn Sie über einen USB-Anschluss an das HoloLens 2 angeschlossen sind. Diese Geräte werden unter Netzwerkeinstellungen als eine weitere Ethernet-Verbindung angezeigt. Mobile Breitbandgeräte, die einen externen Treiber erfordern, werden nicht unterstützt. Dies ermöglicht Verbindungen mit höherer Bandbreite in Szenarien, in denen WLAN nicht zur Verfügung steht und WLAN-Tethering nicht ausreicht. Weitere Informationen zu unterstützten USB-Geräten finden Sie [hier](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Verbesserungen bei der Hand Verfolgung

Hand Tracking hat in dieser Version mehrere Verbesserungen erhalten. 

- **Zeigen Sie Pose-Stabilität:** Das System widersteht nun dem Verbiegen des Zeigefingers, wenn es vom Palm verdeckt wird.  Dies verbessert die Genauigkeit beim Drücken von Schaltflächen, eingeben, Scrollen von Inhalten und vieles mehr! 
- **Reduzierte zufällige Wasserhähne:** Wir haben die Erkennung der AirTap-Geste verbessert.  Es gibt jetzt weniger zufällige Aktivierungen in einigen häufigen Fällen, wie etwa das Ablegen Ihrer Hände an Ihre Seite. 
- **Zuverlässigkeit des Benutzerwechsels:** Das System ist jetzt schneller und zuverlässiger beim Aktualisieren der Hand Größe, wenn ein Gerät hin-und hergeteilt wird. 
- **Reduzierter Hand Diebstahl:** Wir haben die Behandlung von Fällen verbessert, bei denen mehr als zwei Hände in Sicht der Sensoren vorhanden sind.  Wenn mehrere Personen eng zusammenarbeiten, gibt es jetzt eine viel geringere Wahrscheinlichkeit, dass die verfolgte Hand vom Benutzer zur Hand einer anderen Person in der Szene springt. 
- **System Zuverlässigkeit:** Ein Problem wurde behoben, bei dem die Hand Nachverfolgung für einen bestimmten Zeitraum nicht mehr funktionierte, wenn das Gerät stark ausgelastet ist. 

### Dunkler Modus

Viele Windows-apps unterstützen jetzt sowohl den dunklen als auch den hellen Modus, und HoloLens 2-Kunden können den Standardmodus für apps auswählen, die beide unterstützen. Nach der Aktualisierung ist der Standard-APP-Modus "dunkel", kann aber problemlos geändert werden. Navigieren Sie zu Einstellungen > System > Farben, um "Standard-APP-Modus auswählen" zu finden. Hier sind einige der in-Box-apps, die den dunklen Modus unterstützen: 

- Einstellungen 
- Microsoft Store 
- Mail 
- Kalender 
- Datei-Explorer 
- Feedback-Hub 
- OneDrive 
- Fotos 
- 3D-Viewer 
- Filme & TV 

![Fenster mit Kacheln im dunklen Modus](images/DarkMode.jpg)

### System Sprachbefehle

Sie können jetzt mithilfe einer beliebigen App auf dem Gerät schnell auf Befehle mit ihrer Stimme zugreifen und diese verwenden. Wenn Sie Ihr System mit einer anderen Sprache ausführen, versuchen Sie es mit den entsprechenden Befehlen in dieser Sprache. Weitere Informationen zu den Befehlen und deren Verwendung finden Sie in unserer Dokumentation [hier](https://docs.microsoft.com/hololens/hololens-cortana).  

### Cortana-Updates 

Die aktualisierte APP ist nur in Microsoft 365, derzeit nur in Englisch (USA), integriert, damit Sie mehr über Ihre Geräte hinweg erledigen können. Auf HoloLens 2 unterstützt Cortana nicht mehr bestimmte gerätespezifische Befehle wie das Anpassen der Lautstärke oder den Neustart des Geräts, die jetzt mit den oben genannten neuen System Sprachbefehlen unterstützt werden. Weitere Informationen zur neuen Cortana-APP und ihrer Richtung [finden Sie hier](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)in unserem Blog. 

### Qualitätsverbesserungen und-Korrekturen 

Verbesserungen und Korrekturen auch im Update:  
- Das Update führt ein aktives Display-Kalibriersystem ein. Dies verbessert die Stabilität und Ausrichtung von Hologrammen, wodurch Sie beim Bewegen des Kopfs von einer Seite zu Seite in Position bleiben können. 
- Ein Fehler wurde behoben, bei dem WLAN-Streaming zu HoloLens in regelmäßigen Abständen gestört wird. Wenn eine Anwendung angibt, dass Sie eine geringe Latenzzeit Streaming benötigt, kann dieser Fix durch Aufrufen [dieser Funktion](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)erreicht werden. 
- Ein Problem wurde behoben, bei dem das Gerät während des Streaming im Recherche Modus hängen konnte. 
- Fehler behoben, bei dem in einigen Fällen der richtige Benutzer beim Fortsetzen der Sitzung nicht auf dem Anmeldebildschirm angezeigt wird. 
- Ein Problem wurde behoben, bei dem Benutzer die MDM-Protokolle nicht über die Einstellungen exportieren konnten. 
- Ein Problem wurde behoben, bei dem die Genauigkeit der Augen Verfolgung unmittelbar nach der Out-of-Box-Einrichtung niedriger als die Spezifikation sein könnte. 
- Ein Problem wurde behoben, bei dem das Eye Tracking-Subsystem unter bestimmten Bedingungen nicht initialisiert und/oder kalibriert werden konnte. 
- Ein Problem wurde behoben, bei dem die Augen Kalibrierung für einen bereits kalibrierten Benutzer aufgefordert wurde. 
- Ein Problem wurde behoben, bei dem ein Treiber während der Augen Kalibrierung abstürzte. 
- Ein Problem wurde behoben, bei dem wiederholtes Drücken der Power-Taste zu einem 60 zweiten System Timeout und zum Absturz der Shell führen kann. 
- Verbesserte Stabilität für Tiefenpuffer. 
- Schaltfläche "freigeben" im Feedback-Hub, damit Benutzer Feedback leichter austauschen können. 
- Ein Fehler wurde behoben, bei dem RoboRaid nicht ordnungsgemäß installiert wurde. 

### Bekannte Probleme

- Wir untersuchen ein Problem im Zusammenhang mit der Verwendung der Systemsprache zh-cn, das verhindert, dass die Sprachbefehle für die Aufnahme einer Mixed-Reality-Aufnahme oder für die Anzeige der IP-Adresse des Geräts funktionieren.
- Wir untersuchen ein Problem, bei dem Sie nach dem Booten des Geräts die Cortana-app starten müssen, um die Sprachaktivierung "Hey Cortana" zu verwenden, und wenn Sie von einem 18362-Build aktualisiert haben, wird möglicherweise in Start eine zweite App-Kachel für die vorherige Version der Cortana-App angezeigt, die nicht mehr funktioniert. 

## Windows holographisch, Version 1903 – Update vom Mai 2020 
- Build 18362,1061

Dieses monatliche Qualitäts Update enthält keine Änderungen von Notizen, da das Team darauf ausgerichtet war, Ihnen das Update der höchsten Qualität zu bieten, das jetzt in der Windows-holographischen Version, Version 2004, oben beschrieben, verfügbar ist. Nutzen Sie diese Gelegenheit, um zum neuesten Funktions Update zu wechseln, um eine Menge interessanter neuer Änderungen zu erhalten.

## Windows holographisch, Version 1903 – Update vom April 2020
- Build 18362,1059

**Dunkler Modus für unterstützte apps** 

Viele Windows-apps unterstützen den dunklen und hellen Modus, und bald können HoloLens 2-Kunden den Standardmodus für apps auswählen, die beide Farbschemas unterstützen! Basierend auf überwiegend positivem Kundenfeedback setzen wir mit diesem Update den standardmäßigen APP-Modus auf "dunkel", aber Sie können diese Einstellung jederzeit problemlos ändern.
Navigieren Sie zu **Einstellungen > System > Farben** , um **"Standard-APP-Modus auswählen"** zu finden.

Hier sind einige der in-Box-apps, die den dunklen Modus unterstützen:
- Einstellungen
- Microsoft Store
- Mail
- Kalender
- Datei-Explorer
- Feedback-Hub
- OneDrive
- Fotos
- 3D-Viewer
- Filme & TV

**Verbesserungen und Korrekturen auch im Update:** 
- Stellen Sie sicher, dass Shell-Overlays in Mixed-Reality-Aufnahmen enthalten sind.
- Unechte Entwickler können nun die Seite 3D-Ansicht im Geräte Portal verwenden, um Ihre Anwendungen zu testen und zu debuggen.
- Verbessern Sie die Stabilität des Hologramms in Mixed-Reality-Aufnahmen, wenn der HolographicDepthReprojectionMethod DepthReprojection-Algorithmus verwendet wird.
- Fehler "WinRT-IStreamSocketListener-API-Klasse nicht registriert" auf 32-Bit-ARM-App behoben.

## Windows holographisch, Version 1903 – Update vom März 2020 
- Build 18362,1056

Verbesserungen und Korrekturen im Update:

- Verbessern Sie die Stabilität des Hologramms in Mixed-Reality-Aufnahmen, wenn der HolographicDepthReprojectionMethod autoplanner-Algorithmus verwendet wird.
- Stellt sicher, dass das an eine Tiefe MF-Beispiel angebrachte Koordinatensystem mit der öffentlichen Dokumentation konsistent ist.
- Produktivitätsverbesserungen von Entwicklern durch die Möglichkeit, dass Kunden große Textmenge über das Geräte Portal einfügen können.

## Windows holographisch, Version 1903 – Update vom Februar 2020 
- Build 18362,1053

Verbesserungen und Korrekturen im Update:

- Vorübergehende Deaktivierung der HolographicSpace. UserPresence-API für Unity-Anwendungen, um ein Problem zu vermeiden, das dazu führt, dass einige apps angehalten werden, wenn das Visor nach oben geklappt wird, auch wenn die im Hintergrund ausgeführte Einstellung aktiviert ist.
- Ein zufälliger HUP-Absturz, der von der Hand nachverfolgt wird, wurde behoben, bei dem der Benutzer nach einigen Sekunden eine Benutzeroberfläche Einfrieren und dann wieder in Shell feststellen kann.
- Wir haben eine Verbesserung bei der Hand Nachverfolgung vorgenommen, sodass der obere Teil des Fingers bei der Verwendung des Zeigefingers seltener unerwartet locken wird.
- Verbesserte Zuverlässigkeit der Kopf Nachverfolgung, räumlichen Zuordnung und anderer Laufzeiten.

## Windows holographisch, Version 1903 – Update vom Januar 2020 
- Build 18362,1043

Verbesserungen beim Update:

- Stabilitätsverbesserungen für exklusive apps beim Arbeiten mit dem HoloLens 2-Emulator.

## Windows holographisch, Version 1903 – Update vom Dezember 2019 
- Build 18362,1042

Verbesserungen und Korrekturen im Update:

- Einführung in LSR-Korrekturen (letzte Stufe). Verbessert die visuelle Darstellung von Hologrammen, sodass Sie stabiler und gestochen scharf erscheinen, indem Sie Ihre tiefe exakter darstellen. Dies wird sich bemerkbar machen, wenn apps nach diesem Update nicht die Tiefe der Hologramme richtig einstellen.
- Behebt die Stabilität exklusiver apps und die Navigation zwischen exklusiven apps.
- Behebt ein Problem, bei dem Mixed-Reality-Aufnahmen keine Videos aufzeichnen konnten, nachdem das Gerät mehrere Tage lang im Standby-Modus verbleibt.
- Verbessert die Stabilität des Hologramms.

## Windows holographisch, Version 1903 – Update vom November 2019 
- Build 18362,1039

Verbesserungen und Korrekturen im Update:

- Korrekturen für Sprachbefehle **"Select"** während der ersten Einrichtung für en-ca und en-au.
- Verbesserungen der visuellen Qualität von Objekten, die in der neuesten Einheits-und MRTK-Version weit entfernt sind.
- Behebt die Behebung von Problemen mit holographischen Anwendungen, die beim Start in einem angehalten Zustand hängen bleiben, bis der Stift Bereich wieder eingeblendet und geschlossen wird.
- Openxr Runtime-Konformitäts Korrekturen und Verbesserungen für HoloLens 2 und den Emulator.


