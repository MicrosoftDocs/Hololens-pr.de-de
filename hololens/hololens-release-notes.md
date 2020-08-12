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
ms.openlocfilehash: deddd753c22095532c1a4e3f8e896e2e881a1ad5
ms.sourcegitcommit: 763896af822b247ee8ee981c2dec3b1abf61bf6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924257"
---
# Veröffentlichungshinweise für HoloLens 2

Um sicherzustellen, dass Sie mit ihren HoloLens-Geräten eine produktive Erfahrung haben, veröffentlichen wir weiterhin Funktions-, Fehler-und Sicherheitsupdates. Auf dieser Seite können Sie jeden Monat sehen, was es Neues für HoloLens gibt. Um das neueste HoloLens 2-vollständiges Flash-Update (FFU) zu erhalten, um [Ihr Gerät über Advanced Recovery Companion zu blinken](hololens-recovery.md#clean-reflash-the-device), [Laden Sie es hier herunter](https://aka.ms/hololens2download). Der Download wird auf dem neuesten Stand gehalten und bietet das neueste allgemein verfügbare Build.

>[!NOTE]
> Wenn Sie HoloLens-Emulator-Versionshinweise lesen möchten, [besuchen Sie das Archiv](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holographisch, Version 2004 – Update vom August 2020
- Build 19041,1113

Verbesserungen und Korrekturen im Update:

- Die app "Einstellungen" folgt dem Benutzer nicht mehr in die Iris-Registrierung oder die Kalibrierung von Augen Nachverfolgung.
- Ein Fehler wurde behoben, bei dem die Anwendung eines Bereitstellungspakets während OOBE, das das Gerät umbenennen und andere Aktionen ausführt (wie etwa das Herstellen einer Verbindung mit einem Netzwerk), die anderen Aktionen nach dem Neustart des Geräts aufgrund einer Umbenennung nicht durchführen kann.
- Geändertes Farbschema der anfänglichen Geräte Einrichtung, um die visuelle Qualität zu verbessern.

## Windows holographisch, Version 1903 – Update vom August 2020
- Build 18362,1074

Dieses monatliche Qualitäts Update enthält keine nennenswerten Änderungen, wir empfehlen Ihnen, unsere neuesten Builds für Windows holographisch, Version 2004, zu testen.

## Windows holographisch, Version 2004 – Update vom Juli 2020
- Build 19041,1109

Verbesserungen und Korrekturen im Update:

- Entwickler können nun auswählen, ob die Aktivierung oder Deaktivierung von Device Portal eine sichere Verbindung erfordert.
- Verbesserte Zuverlässigkeit für Anwendungsstarts nach Betriebssystemupdates.
- Die standardmäßige Posteingang-Helligkeit wurde auf 100 Prozent geändert.
- Es wurde ein Problem mit der HTTPS-Weiterleitung für das Windows Device Portal auf HoloLens 2 behoben.

## Windows holographisch, Version 1903 – Update vom Juli 2020
- Build 18362,1071

Verbesserungen und Korrekturen im Update:

- Ein Problem wurde behoben, das dazu führen kann, dass Hologramme in Einheits Anwendungen verschwinden, wenn Sie die Nachverfolgung verlieren oder wiedererlangen.
- Ein Problem wurde behoben, durch das exklusive HoloLens-Apps bei Verwendung des HoloLens-Emulators mit Hardwarebeschleunigung auf bestimmten Geräten wieder in die Shell zurück stürzten.
- Es wurde ein Problem im Zusammenhang mit der HTTPS-Weiterleitung für das Windows Device Portal auf HoloLens 2 behoben.

## Windows holographisch, Version 2004 – Update vom Juni 2020
- Build 19041,1106

Verbesserungen und Korrekturen im Update:

- Benutzerdefinierte MRC-Datenschreiber verfügen jetzt über neue Standardwerte für bestimmte Eigenschaften, wenn Sie nicht angegeben werden.
  - Auf dem *MRC-Video Effekt*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (immersives Headset))
  - Auf dem *MRC-Audioeffekt*:
    - LoopbackGain (der aktuelle Wert für "App-Audiogain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
    - MicrophoneGain (der aktuelle Wert "Mic Audio Gain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
- Ein Fehler wurde behoben, um die Audioqualität in Szenarien für Mixed-Reality-Aufnahmen zu verbessern. Insbesondere sollte dieser Fix die audioglitche in der Aufzeichnung beseitigen, wenn das **Startmenü** angezeigt wird.
- Verbesserte Hologramm-Stabilität in aufgezeichneten Videos.
- Ein Problem wurde behoben, bei dem "Mixed Reality Capture" kein Video aufzeichnen konnte, nachdem das Gerät mehrere Tage lang im Standby-Modus war.
- Die HolographicSpace. UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, bei dem einige apps angehalten wurden, als das Visor nach oben geklappt wurde, auch wenn die Einstellung "im Hintergrund ausführen" aktiviert war. Die API ist jetzt für Unity-Versionen 2018.4.18 und höher und 2019.3.4 und höher aktiviert.
- Wenn Sie über eine WLAN-Verbindung auf Device Portal zugreifen, kann ein Webbrowser den Zugriff auf die Ursache eines ungültigen Zertifikats verhindern. Der Browser meldet möglicherweise einen Fehler wie "ERR_SSL_PROTOCOL_ERROR", auch wenn das Gerätezertifikat zuvor als vertrauenswürdig eingestuft wurde. In diesem Fall können Sie nicht zu Device Portal Fortschreiten, da es keine Option zum Ignorieren von Sicherheitswarnungen gibt. Dieses Update hat das Problem behoben. Wenn das Gerätezertifikat zuvor heruntergeladen und auf einem PC als vertrauenswürdig eingestuft wurde, um die Sicherheitswarnungen des Browsers zu entfernen, und der SSL-Fehler auftritt, muss das neue Zertifikat heruntergeladen und den Sicherheitswarnungen des Browsers als vertrauenswürdig eingestuft werden.
- Die Möglichkeit zum Erstellen eines Runtime-Bereitstellungspakets, das eine App mithilfe von MSIX-Paketen installieren kann, wurde aktiviert.
- Eine Einstellung in Hologramme des **Einstellungen**-Systems wurde hinzugefügt  >  **System**  >  **Holograms** , mit der Benutzer alle Hologramme automatisch aus dem Mixed-Reality-Home entfernen können, wenn das Gerät heruntergefahren wird.
- Ein Problem wurde behoben, durch das HoloLens-apps, die ihr Pixelformat ändern, im HoloLens-Emulator schwarz gerendert wurden.
- Ein Fehler wurde behoben, der während der Iris-Anmeldung zu einem Absturz führte.
- Es wurde ein Problem mit wiederholten Store-Downloads für bereits aktuelle apps behoben.
- Ein Fehler wurde behoben, um zu verhindern, dass immersive Apps Microsoft Edge wiederholt öffnen.
- Es wurde ein Problem mit dem Start der Fotos-app in den anfänglichen Stiefeln nach der Aktualisierung aus der 1903-Version behoben.
- Verbesserte Leistung und Zuverlässigkeit.

## Windows holographisch, Version 1903 – Update vom Juni 2020
- Build 18362,1064

Verbesserungen und Korrekturen im Update:

- Benutzerdefinierte MRC-Datenschreiber verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn Sie nicht angegeben werden.
  - Auf dem *MRC-Video Effekt*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (immersives Headset))
  - Auf dem *MRC-Audioeffekt*:
    - LoopbackGain (der aktuelle Wert für "App-Audiogain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
    - MicrophoneGain (der aktuelle Wert "Mic Audio Gain" auf der Seite "Mixed Reality Capture" im Windows Device Portal)
- Die HolographicSpace. UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, bei dem einige apps angehalten werden, wenn das Visor nach oben geklappt wird, selbst wenn die Einstellung, die im Hintergrund ausgeführt werden soll, aktiviert ist. Die API ist jetzt für Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Ein Problem wurde behoben, durch das HoloLens-apps, die ihr Pixelformat ändern, im HoloLens-Emulator schwarz gerendert wurden.
- Es wurde ein Problem mit dem Start der Fotos-app in den anfänglichen Stiefeln nach der Aktualisierung aus der 1903-Version behoben.

## Windows holographisch, Version 2004  
- Build-19041,1103

Das 2020-Major-Software Update für HoloLens 2, *Windows holographisch, Version 2004* , bietet eine Reihe interessanter neuer Funktionen wie Unterstützung für Windows Autopilot, App-Dark-Modus, USB-Ethernet-Unterstützung für 5G/LTE-Hotspots und vieles mehr. Wenn Sie auf die neueste Version aktualisieren möchten, öffnen Sie die **Einstellungs**   -app, wechseln Sie zu **Update & Security**, und wählen Sie die Schaltfläche **auf Updates überprüfen**aus   . 

|             Feature                              |          Beschreibung                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Vorkonfigurieren und nahtloses Einrichten neuer Geräte für die Produktion mithilfe von Windows Autopilot                 |
|       Unterstützung für Fido 2                             |          Unterstützung für FIDO2-Sicherheitsschlüssel, um eine schnelle und sichere Authentifizierung für freigegebene Geräte zu ermöglichen            |
|       Verbesserte Bereitstellung                      |          Nahtloses Anwenden eines Bereitstellungspakets von einem USB-Laufwerk auf Ihr HoloLens                              |
|       Anwendungs Installationsstatus                 |          Überprüfen des Installationsstatus in der Einstellungs-APP für apps wurden über MDM zu HoloLens 2 verschoben               |
|       Konfigurationsdienst Anbieter (LSP)   |          Neue Konfigurationsdienstanbieter hinzugefügt, um die Funktionen der Administratorsteuerung zu verbessern                 |
|       USB 5G/LTE-Unterstützung                       |          Erweiterte USB-Ethernet-Funktion ermöglicht Unterstützung für 5G/LTE                                    |
|       Dunkler APP-Modus                              |          Dunkler APP-Modus für apps verfügbar, die sowohl die dunklen als auch die hellen Modi unterstützen, wodurch sich die Anzeige verbessert        |
|       Sprachbefehle                             |          Unterstützung für zusätzliche System Sprachbefehle zur Steuerung der HoloLens-Freisprechfunktion                           |
|       Verbesserungen bei der Hand Verfolgung                 |          Verbesserungen bei der Hand Verfolgung machen Tasten und 2D-Schiefer Interaktionen genauer                        |
|       Qualitätsverbesserungen und-Korrekturen                 |          Verschiedene Verbesserungen der Systemleistung und-Zuverlässigkeit auf der gesamten Plattform                            |

### Unterstützung für Windows Autopilot

Mit Windows Autopilot für HoloLens 2 kann der Geräte Vertriebskanal HoloLens in Ihrem InTune-Mandanten vor der Registrierung registrieren. Wenn Geräte eintreffen, können Sie als freigegebene Geräte unter Ihrem Mandanten selbst bereitgestellt werden. Um die Selbstbereitstellung zu nutzen, muss das Gerät während des ersten Bildschirms in Setup über einen USB-c-zu-Ethernet-oder USB-c-to-LTE-Dongle mit einem Netzwerk verbunden werden.

Nachdem ein Benutzer den selbst Bereitstellungsprozess von Autopilot gestartet hat, führt der Prozess die folgenden Schritte aus:

1. Verknüpfen des Geräts mit Azure Active Directory (Azure AD).
1. Verwenden von Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Herunterladen der gerätespezifischen Richtlinien, Zertifikate und Netzwerkprofile.
1. Bereitstellen des Geräts.
1. Präsentieren des Anmeldebildschirms für den Benutzer.

Weitere Informationen finden Sie im [Evaluierungshandbuch für Windows Autopilot für HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Wenden Sie sich an Ihren Konto-Manager, um jetzt an der Autopilot Preview teilzunehmen. Autopilot-Ready-Geräte werden in Kürze ausgeliefert.*

### FIDO2-Sicherheitsschlüssel-Unterstützung

Einige Benutzer teilen ein HoloLens-Gerät mit anderen Personen in einer geschäftlichen oder schulischen Umgebung. Daher ist es wichtig, dass Benutzer problemlos lange Benutzernamen und Kennwörter eingeben können. Mit der fast Identity online (Fido) können sich alle Personen in Ihrer Organisation (Azure AD Tenant) nahtlos bei HoloLens anmelden, ohne einen Benutzernamen oder ein Kennwort einzugeben.

FIDO2-Sicherheitsschlüssel sind eine auf Standards basierende, nicht Phishing-basierte, Kenn Wort sichere Authentifizierungsmethode, die in jedem Formfaktor enthalten sein kann. Fido ist ein offener Standard für die Kenn Wort freie Authentifizierung. Benutzer und Organisationen können sich ohne Benutzernamen oder Kennwort bei ihren Ressourcen anmelden. Stattdessen verwenden Sie einen externen Sicherheitsschlüssel oder einen Plattformschlüssel, der in ein Gerät integriert ist.

Informationen zu den ersten Schritten finden Sie unter [Aktivieren der Anmeldung für den Kennwortschutz](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### Verbesserte MDM-Registrierung über Bereitstellungspaket

Mit Bereitstellungspaketen können Sie die HoloLens-Konfiguration über eine config-Datei und nicht über die HoloLens-out-of-Box-Umgebung einrichten. Zuvor mussten Bereitstellungspakete in den HoloLens-internen Speicher kopiert werden. Nun können Sie sich auf einem USB-Laufwerk befinden, damit Sie auf mehreren HoloLens-Geräten einfacher wieder verwendet werden können, und Sie können Geräte parallel bereitstellen. Bereitstellungspakete unterstützen nun auch ein Feld für die Registrierung in der Geräteverwaltung, sodass nach der Bereitstellung keine manuellen Einstellungen durchgestellt werden.

Um dies auszuprobieren:

1. Laden Sie die neueste Version des Windows-Konfigurations-Designers aus dem Windows Store auf Ihren PC herunter.
1. Wählen Sie **HoloLens Devices**  >  **Provision HoloLens 2 Devices**.
2. Erstellen Sie Ihr Konfigurationsprofil. Kopieren Sie dann alle Dateien, die auf einem USB-C-Speichergerät erstellt wurden.
3. Schließen Sie das USB-C-Gerät an einen frisch geblitzten HoloLens an. Drücken Sie dann die Power-Taste **Lautstärke**  +  **power** , um Ihr Bereitstellungspaket anzuwenden.

### Installationsstatus der Branchenanwendung

Die Bereitstellung und Verwaltung von MDM-Apps für Branchen-Apps ist für HoloLens von entscheidender Bedeutung. Administratoren und Benutzer müssen den App-Installationsstatus für die Überwachung und Diagnoseanzeigen. In dieser Version haben wir weitere Details in den **Einstellungen**für  >  **Accounts**  >  den**Zugriff auf Arbeit oder Schule**hinzugefügt  >  .**Klicken Sie auf Ihre Konto**  >  **Informationen**.

### Zusätzliche Kryptografiedienstanbieter und Richtlinien

Ein [Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ist eine Schnittstelle zum Lesen, festlegen, ändern oder Löschen von Konfigurationseinstellungen auf einem Gerät. In dieser Version wird die Unterstützung für weitere Richtlinien hinzugefügt, um die Steuerelement Administratoren auf bereitgestellten HoloLens-Geräten zu erhöhen. Eine Liste der von HoloLens unterstützten Kryptografiedienstanbieter finden Sie unter [NetworkQoSPolicy-CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Neu in dieser Version:

**Richtlinien-Konfigurationsdienstanbieter** 

Der Richtlinien Konfigurationsdienst Anbieter ermöglicht es dem Unternehmen, Richtlinien auf Windows-Geräten zu konfigurieren. In dieser Version haben wir neue Richtlinien für HoloLens hinzugefügt, die hier aufgelistet sind. Weitere Informationen finden Sie unter [von HoloLens 2 unterstützte Richtlinien Kryptografiedienstanbieter](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

**NetworkQoSPolicy-Konfigurationsdienstanbieter**

Der NetworkQoSPolicy-Konfigurationsdienst Anbieter erstellt Netzwerk Quality-of-Service (QoS)-Richtlinien. Eine QoS-Richtlinie führt eine Reihe von Aktionen für Netzwerkverkehr basierend auf einem Satz von übereinstimmenden Bedingungen aus. Weitere Informationen finden Sie unter [NetworkQoSPolicy-CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Erweiterte USB-Ethernet-Unterstützung für 5G/LTE-angebundene Geräte

Unterstützung wurde hinzugefügt, um bestimmte mobile Breitbandgeräte wie 5G/LTE-Telefone und WLAN-Eintöpfen zu aktivieren, wenn Sie über einen USB-Anschluss an das HoloLens 2 angebunden sind. Diese Geräte werden nun in den **Netzwerkeinstellungen** als eine weitere Ethernet-Verbindung angezeigt. (Mobile Breitbandgeräte, die einen externen Treiber erfordern, werden nicht unterstützt.) Diese Funktion ermöglicht Verbindungen mit hoher Bandbreite, wenn WLAN nicht zur Verfügung steht und die WLAN-Anbindung nicht ausreicht. Weitere Informationen zu unterstützten USB-Geräten finden Sie unter [Herstellen einer Verbindung mit Bluetooth-und USB-C-Geräten](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Verbesserungen bei der Hand Verfolgung

Diese Version enthält mehrere Verbesserungen bei der Hand Nachverfolgung:

- **Zeigen Sie Pose-Stabilität:** Das System widersteht nun dem Biegen des Zeigefingers, wenn es vom Palm verdeckt wird. Diese Änderung verbessert die Genauigkeit beim Drücken von Schaltflächen, eingeben, Scrollen von Inhalten und mehr! 
- **Reduzierte zufällige Luft Hähne:** Wir haben die Erkennung der Luft Tap-Geste verbessert. Es gibt jetzt weniger zufällige Aktivierungen in mehreren gängigen Szenarien, beispielsweise wenn Sie Ihre Hände an Ihre Seiten ablegen.
- **Zuverlässigkeit des Benutzerwechsels:** Das System ist jetzt schneller und zuverlässiger beim Aktualisieren der Hand Größe, wenn Sie ein Gerät freigeben.
- **Reduzierter Hand Diebstahl:** Wir haben die Behandlung von Fällen verbessert, bei denen mehr als zwei Hände in Sicht der Sensoren vorhanden sind. Wenn mehrere Personen eng zusammenarbeiten, gibt es jetzt eine viel geringere Wahrscheinlichkeit, dass die nachverfolgte Hand vom Benutzer zur Hand einer anderen Person in der Szene springt.
- **System Zuverlässigkeit:** Ein Problem wurde behoben, das dazu führte, dass die Hand Nachverfolgung nicht mehr funktioniert, wenn das Gerät stark ausgelastet ist.

### Dunkler Modus

Viele Windows-apps unterstützen jetzt sowohl den dunklen als auch den hellen Modus. HoloLens 2-Benutzer können den Standardmodus für apps auswählen, die beide unterstützen. Nach dem Update ist der Standard-APP-Modus "dunkel", doch Sie können diese Einstellung einfach ändern: Navigieren Sie zu **Einstellungen**  >  **System**  >  **Farben**, und  >  **Wählen Sie den standardmäßigen APP-Modus aus**. 

Diese "in-Box"-Apps unterstützen den dunklen Modus: 

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

Sie können jetzt Sprachbefehle mit jeder beliebigen App auf dem Gerät verwenden. Weitere Informationen finden Sie unter [Verwenden Ihrer Stimme zum Betrieb von HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Siehe auch [Unterstützte Sprachen für HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Cortana-Updates

Die aktualisierte APP ist in Microsoft 365 integriert, damit Sie mehr über Ihre Geräte (derzeit nur in US-Englisch) erledigen können. Auf HoloLens 2 unterstützt Cortana nicht mehr bestimmte gerätespezifische Befehle, wie etwa das Anpassen der Lautstärke oder des Neustarts. Diese Optionen werden jetzt von den neuen System Sprachbefehlen unterstützt. Weitere Informationen zur neuen Cortana-App finden Sie in unserem [Blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Qualitätsverbesserungen und-Korrekturen

Verbesserungen und Korrekturen auch im Update:  
- Einführung eines aktiven Anzeige Kalibrier Systems Dieses Feature verbessert die Stabilität und Ausrichtung von Hologrammen. Sie bleiben nun in Kraft, wenn Sie den Kopf von einer Seite zur anderen bewegen.
- Ein Fehler wurde behoben, bei dem das WLAN-Streaming zu HoloLens in regelmäßigen Abständen gestört wurde. Wenn eine Anwendung angibt, dass Sie ein Streaming mit niedriger Latenz benötigt, implementieren Sie den Fix durch Aufrufen der [SetSocketMediaStreamingMode-Funktion](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Ein Geräte Absturz, der während des Streaming im Recherche Modus aufgetreten ist, wurde behoben.
- Ein Fehler wurde behoben, bei dem in einigen Fällen der richtige Benutzer beim Fortsetzen einer Sitzung nicht auf dem Anmeldebildschirm angezeigt wird.
- Ein Problem wurde behoben, bei dem Benutzer die MDM-Protokolle nicht über die **Einstellungen**exportieren konnten.
- Ein Problem wurde behoben, bei dem die Genauigkeit der Augen Verfolgung, die unmittelbar nach dem Setup erfolgt, niedriger als erwartet sein könnte.
- Ein Problem wurde behoben, bei dem das Eye-Tracking-Subsystem unter bestimmten Bedingungen nicht initialisiert oder kalibriert wurde.
- Ein Problem wurde behoben, bei dem die Augen Kalibrierung für einen bereits kalibrierten Benutzer aufgefordert wurde.
- Ein Problem wurde behoben, bei dem ein Treiber während der Augen Kalibrierung abstürzte.
- Ein Problem wurde behoben, bei dem wiederholtes Drücken der Power-Taste zu einem 60-Sekunden-System Timeout und einem Shell-Absturz führen kann.
- Verbesserte Stabilität für Tiefenpuffer.
- Die Schaltfläche " **Freigeben** " im Feedback-Hub wurde hinzugefügt, damit Benutzer Feedback leichter austauschen können.
- Ein Fehler wurde behoben, bei dem RoboRaid liebesapfels ordnungsgemäß installiert wurde.

### Bekannte Probleme

- Ein Problem mit der Systemsprache zh-cn verhindert, dass Sprachbefehle eine gemischte Realität aufnehmen oder die IP-Adresse des Geräts anzeigen.
- Ein Problem erfordert, dass Sie die Cortana-app starten, nachdem Sie das Gerät gestartet haben, um die Sprachaktivierung "Hey Cortana" zu verwenden. Wenn Sie von einem 18362-Build aktualisiert haben, wird möglicherweise auch eine zweite App-Kachel für die vorherige Version der Cortana-App angezeigt, die in **Start**nicht mehr funktioniert.

## Windows holographisch, Version 1903 – Update vom Mai 2020 
- Build 18362,1061

Dieses monatliche Qualitäts Update enthält keine nennenswerten Änderungen, da das Team an der Windows-holographischen Version 2004, die möglicherweise aktualisiert wurde, wie zuvor beschrieben, funktioniert.

## Windows holographisch, Version 1903 – Update vom April 2020
- Build 18362,1059

**Dunkler Modus für unterstützte apps** 

Viele Windows-apps unterstützen den dunklen und hellen Modus. HoloLens 2-Kunden können nun den Standardmodus für apps auswählen, die beide Farbschemas unterstützen. Auf der Grundlage des Kundenfeedbacks haben wir den standardmäßigen APP-Modus auf "dunkel" festgelegt, doch Sie können diese Einstellung jederzeit ganz einfach ändern: Navigieren Sie zu **Einstellungen > System > Farben** , um **"Standard-APP-Modus auswählen"** zu finden.

Diese "in-Box"-Apps unterstützen den dunklen Modus:
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
- Sichergestellt, dass Shell-Overlays in Mixed-Reality-Aufnahmen enthalten sind.
- Unwirkliche Entwickler können nun die Seite 3D-Ansicht im Geräte Portal verwenden, um Ihre Anwendungen zu testen und zu debuggen.
- Verbesserte Hologramm-Stabilität in Mixed-Reality-Aufnahmen, wenn der *HolographicDepthReprojectionMethod-DepthReprojection* -Algorithmus verwendet wird.
- Fehler "WinRT IStreamSocketListener-API-Klasse nicht registriert" auf 32-Bit-ARM-apps behoben.

## Windows holographisch, Version 1903 – Update vom März 2020 
- Build 18362,1056

Verbesserungen und Korrekturen im Update:

- Verbesserte Hologramm-Stabilität in Mixed-Reality-Aufnahmen, wenn der *HolographicDepthReprojectionMethod autoplanner* -Algorithmus verwendet wird.
- Sichergestellt, dass das an eine Tiefe MF-Beispiel angebrachte Koordinatensystem mit der öffentlichen Dokumentation vereinbar ist.
- Verbesserte Entwicklerproduktivität, da Kunden große Mengentext über das Geräte Portal einfügen können.

## Windows holographisch, Version 1903 – Update vom Februar 2020 
- Build 18362,1053

Verbesserungen und Korrekturen im Update:

- Vorübergehende Deaktivierung der HolographicSpace. UserPresence-API für Unity-Anwendungen. Diese Änderung vermeidet ein Problem, bei dem einige apps angehalten wurden, als das Visor nach oben geklappt wurde, auch wenn die Einstellung "im Hintergrund ausführen" aktiviert war.
- Ein zufälliger HUP-Absturz, der durch Hand Nachverfolgung verursacht wurde, wurde behoben, bei dem der Benutzer nach einigen Sekunden eine Benutzeroberfläche Einfrieren und dann wieder in Shell festgestellt hat.
- Verbesserte Hand Nachverfolgung, damit sich der obere Teil des Fingers, wenn Sie mit dem Zeigefinger stechen, unerwartet unerwartet anlockt.
- Verbesserte Zuverlässigkeit der Kopf Nachverfolgung, räumlichen Zuordnung und anderer Laufzeiten.

## Windows holographisch, Version 1903 – Update vom Januar 2020 
- Build 18362,1043
 
Verbesserungen und Korrekturen im Update:

- Verbesserte Stabilität für exklusive apps beim Arbeiten mit dem HoloLens 2-Emulator.

## Windows holographisch, Version 1903 – Update vom Dezember 2019 
- Build 18362,1042

Verbesserungen und Korrekturen im Update:

- Einführung der Updates für die letzte Stufe (LSR). Die visuelle Darstellung von Hologrammen wurde verbessert, um stabiler und gestochen scharfer zu wirken, indem die Tiefe genauer berechnet wird. Dieses Symptom wird nach diesem Update deutlicher, wenn Apps die Tiefe der Hologramme nicht richtig einstellen.
- Feste Stabilität exklusiver apps und Navigation zwischen exklusiven apps.
- Ein Problem wurde behoben, bei dem die Mixed-Reality-Aufnahme keine Videos aufzeichnen konnte, nachdem sich das Gerät mehrere Tage lang im Standby-Modus befand.
- Verbesserte Hologramm-Stabilität.

## Windows holographisch, Version 1903 – Update vom November 2019 
- Build 18362,1039

Verbesserungen und Korrekturen im Update:

- Die Funktionen von **Select** Voice Commands wurden bei der erstmaligen Einrichtung von en-ca und en-au behoben.
- Verbesserte visuelle Qualität von Objekten, die in den neuesten Versionen von Unity und Mixed Reality Toolkit (MRTK) weit entfernt sind.
- Beheben von Problemen mit holographischen Anwendungen, die beim Start in einem angehalten Zustand hängen bleiben, bis das Startmenü geöffnet und dann geschlossen wurde.
- Openxr Runtime-Konformitäts Korrekturen und Verbesserungen für HoloLens 2 und den Emulator.
