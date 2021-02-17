---
title: Veröffentlichungshinweise für HoloLens 2
description: Bleiben Sie mit allen Updates in jeder neuen HoloLens 2-Version auf dem laufenden.
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
ms.openlocfilehash: 7ab8eede6e48ed1a6cb4584188a80adbd832c169
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340554"
---
# Veröffentlichungshinweise für HoloLens 2

Um sicherzustellen, dass Sie produktiv mit Ihren #A0 arbeiten, veröffentlichen wir weiterhin Feature-, Fehler- und Sicherheitsupdates. Auf dieser Seite können Sie jeden Monat sehen, was für HoloLens neu ist. To get the latest HoloLens 2 update, you can either [check for updates and manually update](hololens-update-hololens.md#check-for-updates-and-manually-update) or get the Full Flash Update (FFU) to flash your device via Advanced Recovery [Companion](hololens-recovery.md#clean-reflash-the-device). Der [Download](https://aka.ms/hololens2download) wird auf dem neuesten Stand gehalten und bietet den neuesten allgemein verfügbaren Build.

>[!NOTE]
> Wir freuen uns, neue Features erneut für Windows-Insider zu verwenden. Wir werden einen Flight zum Dev Channel für die neuesten Updates machen. We will continue to our [**HoloLens Insider notes**](hololens-insider.md) as we add more features and updates to our Windows Insider builds. Freuen Sie sich und bereiten Sie sich darauf, diese Updates in Ihre Realität zu mischen.

Lesen Sie verwandte Anmerkungen zur Version:

- [Besuchen Sie das Archiv des HoloLens-Emulators.](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## Windows Holographic, Version 20H2 – Februar 2021 Update
- Build 19041.1136

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem bei der Ersteinrichtung von Geräten und beim Speichern von App-Updates.
- Behebt ein Problem mit Upgrades und Flights für spätere HoloLens-Versionen.
- Nicht verwendete vorinstallierte Zertifikate wurden aus dem eSIM-Stammspeicher von HoloLens-Geräten entfernt.

## Windows Holographic, Version 1903 – Februar 2021 Update
- Build 18362.1098

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## Windows Holographic, Version 20H2 – Update vom Januar 2021
- Build 19041.1134

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Leistung beim Starten, Fortsetzen und Wechseln von Benutzern, wenn viele Benutzer auf dem Gerät sind.
- Arm32-Unterstützung für den [Forschungsmodus wurde hinzugefügt.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## Windows Holographic, Version 1903 – Januar 2021 Update
- Build 18362.1091

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## Windows Holographic, Version 20H2 – Update vom Dezember 2020
- Build 19041.1131

### Installieren von Apps auf HoloLens 2 über den App-Installer

Wir fügen **eine neue Funktion (App-Installer)** hinzu, mit der Sie Anwendungen nahtloser auf Ihren HoloLens 2-Geräten installieren können. Das Feature ist **für nicht verwaltete Geräte standardmäßig aktiviert.** Um Unterbrechungen für Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit nicht für **verwaltete** Geräte zur Verfügung.  

Ein Gerät wird als "verwaltet" betrachtet, **wenn** eine der folgenden Bedingungen zutrifft:
- MDM [Enrolled](hololens-enroll-mdm.md)
- Mit [Bereitstellungspaket konfiguriert](hololens-provisioning.md)
- [Benutzeridentität](hololens-identity.md) ist Azure AD

Sie können jetzt Apps installieren, ohne den Entwicklermodus aktivieren oder das Geräteportal verwenden zu müssen.  Laden Sie einfach (über USB oder über Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie zum Appx Bundle im Datei-Explorer, um aufgefordert zu werden, die Installation zu starten.  Alternativ können [Sie eine Installation über eine Webseite initiieren.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Genau wie Apps, die Sie aus dem Microsoft Store installieren oder mithilfe der BRANCHEN-App-Bereitstellungsfunktion [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) von MDM querladen, müssen Apps digital mit dem Signierungstool signiert werden, und das zum Signieren verwendete Zertifikat muss vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die App bereitgestellt werden kann. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Anweisungen zur Anwendungsinstallation.**

1.  Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet betrachtet wird
1.  Stellen Sie sicher, dass Ihr HoloLens 2-Gerät eingeschaltet und mit Ihrem PC verbunden ist.
1.  Sicherstellen, dass Sie beim HoloLens 2-Gerät angemeldet sind
1.  Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie "yourapp.appxbundle" in "yourdevicename\Internal Storage\Downloads".   Nachdem Sie das Kopieren der Datei abgeschlossen haben, können Sie das Gerät trennen.
1.  Wählen Sie auf Ihrem HoloLens 2-Gerät das Startmenü aus, wählen Sie alle Apps aus, und starten Sie die Datei-Explorer-App.
1.  Navigieren Sie zum Ordner "Downloads". You may need to on the left panel of the app select This device first, then navigate to Downloads.
1.  Wählen Sie die Datei "yourapp.appxbundle" aus.
1.  Das App-Installationsprogramm wird gestartet. Wählen Sie die Schaltfläche "Installieren" aus, um Ihre App zu installieren.
Die installierte App wird nach Abschluss der Installation automatisch gestartet.

Sie finden Beispiel-Apps auf [GitHub für universelle Windows-Beispiele,](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) um diesen Fluss zu testen.

Erfahren Sie mehr über den vollständigen [Prozess der Installation von Apps auf HoloLens 2 mit dem App-Installer.](app-deploy-app-installer.md)  

![Installieren von MRTK-Beispielen über den App-Installer](images/hololens-app-installer-picture.jpg)

### Verbesserungen und Fehlerbehebungen im Update:

- Die Handverfolgung behält nun in vielen neuen Fällen, in denen die Hand zuvor verloren gegangen wäre, die Nachverfolgung bei.  In einigen dieser neuen Fälle wird nur die Handfläche basierend auf der tatsächlichen Hand des Benutzers aktualisiert, während die anderen Joints basierend auf einer vorherigen Pose abgeleitet werden.  Diese Änderung trägt zur Verbesserung der Verfolgungskonsistenz bei Bewegungen bei, z. B. Beim Slapen, Werfen, Wischen und Klammern.  Sie hilft auch in Fällen, in denen sich die Hand nah an einer Oberfläche befindet oder ein Objekt enthält.  Wenn Handgelenke abgeleitet werden, [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) wird der Wert pro gemeinsamer Genauigkeit auf "Ungefähr" statt auf "Hoch" festgelegt.
- Es wurde ein Problem behoben, bei dem beim Zurücksetzen der PIN für Azure AD-Konten der Fehler "Ein Fehler aufgetreten ist.
- Benutzer sollten beim Starten von ET, Iris aus der Einstellungs-App, einem neuen Benutzer oder einem Benachrichtigungs-Popup deutlich weniger Abstürze nach dem Start der OOBE sehen.
- Benutzer sollten über die richtige Zeitzone verfügen, die aus der OOBE kommt.

## Windows Holographic, Version 1903 – Update vom Dezember 2020
- Build 18362.1088

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unser neuestes Windows Holographic-Update, Version 20H2– Dezember 2020, und das neue App-Installer-Feature, das im Build hinzugefügt wurde, auszuprobieren.


## Windows Holographic, Version 20H2
- Build 19041.1128

Windows Holographic, Version 20H2, ist jetzt verfügbar und bietet Benutzern und IT-Experten von HoloLens 2 eine große Anzahl neuer Features. Von der automatischen Augenpositionierung über den Zertifikat-Manager in den Einstellungen bis hin zu verbesserten Funktionen für den Kioskmodus und neuen Autopilot-Setupfunktionen. Dieses neue Update ermöglicht es IT-Teams, die Konfiguration und Verwaltung von HoloLens-Geräten präziser zu steuern und bietet Benutzern noch mehr nahtlose holografische Erfahrungen. 

Dieses neueste Release ist ein monatliches Update auf Version 2004, aber dieses Mal werden wir neue Features verwenden. Die Hauptversionsnummer bleibt unverändert, und Windows Update gibt eine monatliche Version für Version 2004 (Build 19041) an. Sie können ihre Buildnummer auf dem Bildschirm "Einstellungen > Informationen" anzeigen, um zu bestätigen, dass Sie auf dem neuesten verfügbaren Build 19041.1128 oder höher sind. To update to the latest release, open the Settings app, go to Update & Security, and tap Check for Updates. Weitere Informationen zum Verwalten von HoloLens-Updates finden Sie auf [dieser Seite.](https://docs.microsoft.com/hololens/hololens-updates)

### Neues in Windows Holographic, Version 20H2  

| Feature                                              | Beschreibung                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Unterstützung der automatischen Augenstellung](hololens-release-notes.md#auto-eye-position-support) | Berechnet die Augenpositionen aktiv, ohne dass Benutzer die Eye Tracking-Kalibrierung verwenden.   |
| [Zertifikat-Manager](hololens-release-notes.md#certificate-manager)   | Ermöglicht neue einfachere Methoden zum Installieren und Entfernen von Zertifikaten aus der Einstellungs-App.     |
| [Automatisches Starten der Bereitstellung über USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Bereitstellungspakete auf USB-Laufwerken fordert automatisch die Bereitstellungsseite in der OOBE auf.                                                         |
| [Automatisches Bestätigen von Bereitstellungspaketen in der OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Bereitstellungspakete werden automatisch während der OOBE von der Bereitstellungsseite angewendet.                                                         |
| [Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Hier erfahren Sie, wie Sie den automatischen Start und die automatische Bestätigung der Bereitstellung kombinieren. |
| [Verwenden von Autopilot mit Wi-Fi Verbindung](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Verwenden Sie Autopilot von Wi-Fi, ohne dass ein Ethernetadapter erforderlich ist. |
| [TenantLockdown CSP und Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Nachdem die Mandantenregistrierung und die Richtlinie angewendet wurden, kann das Gerät nur bei jedem Zurücksetzen oder erneuten Flashen des Geräts in diesem Mandanten registriert werden. |
| [Global zugewiesener Zugriff](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Neue Konfigurationsmethode für den Kioskmodus mit mehreren Apps, bei dem der Kiosk auf Systemebene angewendet wird und für alle gilt.                  |
| [Automatisches Starten einer App im Kiosk mit mehreren Apps](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Legt fest, dass eine Anwendung automatisch gestartet wird, wenn sie sich bei einem Kioskmodus mit mehreren Apps anmeldet.                                                        |
| [Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Kioskmodusfehler hat jetzt ein restriktives Fallback.                                                                                                |
| [Richtlinien für HoloLens](hololens-release-notes.md#hololens-policies)                                    | Neue Richtlinien für HoloLens.     |
| [Azure AD-Gruppenmitgliedschaft für Offlinekiosk zwischenspeichern](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Mit der neuen Richtlinie können Benutzer den Gruppenmitgliedschaftscache verwenden, um den Kioskmodus für eine festgelegte Anzahl von Tagen offline zu verwenden.                                        |
| [Neue Geräteeinschränkungsrichtlinien für HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Geräteverwaltungsrichtlinien, die neu für HoloLens 2 aktiviert wurden.                                                                                |
| [Neue Energierichtlinien für HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Neu unterstützte Richtlinien für Energietimeouteinstellungen.  |
| [Aktualisieren von Richtlinien](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Neu aktivierte Richtlinien, die die Kontrolle über Updates ermöglichen.           |
| [Sichtbarkeit der Seite "Aktivierte Einstellungen" für HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Richtlinie zum Auswählen, welche Seiten in der Einstellungs-App angezeigt werden.             |
| [Recherchemodus](hololens-release-notes.md#research-mode) | Verwenden des Recherchemodus auf HoloLens 2. |
| [Aufzeichnungslänge erhöht](hololens-release-notes.md#recording-length-increased) | MrC-Aufzeichnungen wurden nicht mehr auf 5 Minuten begrenzt. |
| [Verbesserungen und Fehlerbehebungen im Update](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Zusätzliche Korrekturen im Update.   |

### Automatische Unterstützung der Augenposition

Bei HoloLens 2 wird durch die Augenstellungen eine genaue Hologramm-Positionierung, ein komfortables Seherlebnis und eine verbesserte Anzeigequalität ermöglicht. Die Augenstellungen werden intern im Rahmen der Eye-Tracking-Berechnung bestimmt. Dazu müssen alle Benutzer eine Eye Tracking-Kalibrierung durchführen, auch wenn keine Eingabe über Anvisieren erforderlich ist.

**Auto Eye Position (AEP, automatische Augenstellung)** ermöglicht diese Szenarien durch eine interaktionsfreie Methode zur Berechnung der Augenstellungen des Benutzers. Auto Eye Position beginnt automatisch im Hintergrund zu arbeiten, sobald der Benutzer das Gerät anlegt. Wenn ein Benutzer zuvor keine Eye Tracking-Kalibrierung durchgeführt hat, beginnt Auto Eye Position nach einer kurzen Verarbeitungszeit von 20-30 Sekunden, die Augenstellungen des Benutzers an das Anzeigesystem zu übermitteln. Die Benutzerdaten werden nicht auf dem Gerät beibehalten. Deshalb wird dieser Vorgang wiederholt, wenn das Gerät wieder eingesetzt, neu gestartet oder aus dem Ruhezustand reaktiviert wird.

Es gibt ein paar Änderungen hinsichtlich des Systemverhaltens bei der Funktion Auto Eye Position, wenn ein nicht kalibrierter Benutzer das Gerät anlegt. In diesem Zusammenhang bezieht sich der Begriff „nicht kalibrierter Benutzer“ auf eine Person, die den Eye-Tracking-Kalibrierungsprozess auf dem Gerät zuvor noch nicht durchlaufen hat.

| Aktive Anwendung | Früheres Verhalten | Verhalten ab Windows Holographic, Version 20H2-Update |
|:-------------------|:-----------------|:-----------------------------------|
| App oder Holographic Shell ohne Eingabe über Anvisieren |Dialogfeld zur Eye-Tracking-Kalibrierung wird angezeigt. | Es wird kein Dialogfeld angezeigt. |
| App mit Eingabe über Anvisieren | Dialogfeld zur Eye-Tracking-Kalibrierung wird angezeigt. | Das Dialogfeld zur Eye-Tracking-Kalibrierung wird nur angezeigt, wenn die Anwendung auf Blickdaten zugreift. |

Wenn Benutzer von einer Anwendung ohne Eingabe über Anvisieren zu einer Anwendung wechseln, die auf Blickdaten zugreift, wird das Kalibrierungsdialogfeld angezeigt. 

Alle anderen Systemverhalten sind jenem ähnlich, wenn keine aktive Eye Tracking-Kalibrierung für den aktuellen Benutzer vorliegt. Beispielsweise wird die einhändige Startgeste nicht aktiviert sein. Bei der Ersteinrichtung wird es keine Änderung an der Standardumgebung geben.

Bei Umgebungen, für die Blickdaten oder eine sehr präzise Hologramm-Positionierung erforderlich sind, empfehlen wir nicht kalibrierten Benutzern, die Eye Tracking-Kalibrierung durchzuführen. Sie kann über das Dialogfeld zur Eye-Tracking-Kalibrierung aufgerufen werden. Starten Sie alternativ die Einstellungs-App aus dem Startmenü, und wählen Sie dann **System > Kalibrierung > Augenkalibrierung > Augenkalibrierung auszuführen** aus.

Diese Informationen finden Sie später mit [anderen Kalibrierungsinformationen.](hololens-calibration.md#auto-eye-position-support) 

### Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Validierungstools für Gerätesicherheit und -kompatibilität durch den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen bereitstellen, Eine Problembehandlung und Validierung ihrer Zertifikate im großen Maßstab ermöglichen.

In Windows Holographic, Version 20H2, fügen wir einen Zertifikat-Manager in der HoloLens 2-Einstellungs-App hinzu. Wechseln Sie **zu "Einstellungen > update & Security > Certificates".** Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und kompatibel bleiben. 

-   **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, spart die Validierung, dass die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung. 
-   **Überprüfung:** Die Überprüfung, ob ein Zertifikat dem beabsichtigten Zweck dient und funktionsfähig ist, kann erhebliche Zeit sparen, insbesondere in kommerziellen Umgebungen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um ein bestimmtes Zertifikat schnell in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Um einzelne Zertifikateigenschaften anzeigen zu können, wählen Sie das Zertifikat aus, und klicken Sie auf **"Info".** 

Die Zertifikatinstallation unterstützt derzeit CER- und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  Alle anderen Benutzer können nur im aktuellen Benutzer installiert werden. Benutzer können nur Direkt installierte Zertifikate aus der Einstellungsbenutzeroberfläche entfernen. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.

#### So installieren Sie ein Zertifikat: 

1.  Verbinden Sie Ihre HoloLens 2 mit einem PC.
1.  Platzieren Sie die Zertifikatsdatei, die Sie installieren möchten, an einem Speicherort auf Ihrer HoloLens 2.
1.  Navigieren Sie **zu "Settings App > Update & Security > Certificates",** und wählen Sie "Zertifikat installieren" aus.
1.  Klicken **Sie auf "Datei importieren",** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **"Store-Speicherort" aus.**
1.  Wählen Sie **Zertifikatspeicher aus.**
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert werden.

#### So entfernen Sie ein Zertifikat: 
1. Navigieren Sie zu **"Settings App > Update and Security > Certificates".**
1. Suchen Sie im Suchfeld nach dem Namen des Zertifikats.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **"Entfernen".**
1. Wählen **Sie "Ja"** aus, wenn Sie zur Bestätigung aufgefordert werden.

![Zertifikatanzeige in der App "Einstellungen"](images/certificate-viewer-device.jpg)

![Abbildung der Verwendung der Zertifikatbenutzeroberfläche zum Installieren eines Zertifikats](images/certificate-device-install.jpg)

Diese Informationen finden Sie später [auf einer neuen Seite des Zertifikat-Managers.](certificate-manager.md)

### Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse, die eine geringere Benutzerinteraktion ermöglichen, wenn usb-Laufwerke mit Bereitstellungspaketen während der OOBE verwendet werden.

Vor dieser Version mussten Benutzer den Bereitstellungsbildschirm während der OOBE manuell starten, um die Bereitstellung mithilfe einer Tastenkombination zu ermöglichen. Jetzt können Benutzer die Tastenkombination überspringen, indem sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Schließen Sie das USB-Laufwerk während des ersten interagierbaren Moments der OOBE mit dem Bereitstellungspaket an.
1. Wenn das Gerät bereit für die Bereitstellung ist, wird die Eingabeaufforderung automatisch mit der Bereitstellungsseite geöffnet. 

Hinweis: Wenn ein USB-Laufwerk beim Starten des Geräts angeschlossen bleibt, wird von der OOBE ein vorhandenes USB-Speichergerät aufgezählt, und es wird darauf achten, dass weitere angeschlossen werden.

Weitere Informationen zum Anwenden von Bereitstellungspaketen während der OOBE finden Sie in der [HoloLens-Bereitstellungsdokumentation.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Weitere Informationen zur [Bereitstellung des automatischen Startes](hololens-provisioning.md#auto-launch-provisioning-from-usb) über einen USB finden Sie in der HoloLens-Bereitstellungsdokumentation.

### Automatisches Bestätigen von Bereitstellungspaketen in der OOBE
- Wenn die Seite "Bereitstellungspaket" angezeigt wird, werden automatisch alle aufgelisteten Pakete angewendet.

Wenn der Hauptbildschirm der Bereitstellung angezeigt wird, zählt die OOBE 10 Sekunden nach unten, bevor automatisch mit der Anwendung aller Bereitstellungspakete begonnen wird. Benutzer können [dies nach der](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) Überprüfung der erwarteten Pakete innerhalb von 10 Sekunden weiterhin bestätigen oder abbrechen.

### Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche
- Kombinierte automatische Prozesse für reduzierte Geräteinteraktionen für die Bereitstellung. 

Durch die Kombination des automatischen Starts der Bereitstellung über DIE USB-Geräte und der automatischen Bestätigung von Bereitstellungspaketen kann ein Benutzer HoloLens 2-Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts zu verwenden oder sogar das Gerät zu tragen. Sie können weiterhin das gleiche USB-Laufwerk und das gleiche Bereitstellungspaket für mehrere Geräte verwenden. Dies ist hilfreich, um mehrere Geräte gleichzeitig im selben Bereich bereitstellen zu können. 

1. [Erstellen Sie ein Bereitstellungspaket mit](hololens-provisioning.md) [dem Windows-Konfigurations-Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken des Geräts abgeschlossen hat, trennen Sie das USB-C-Kabel. 
1. Schließen Sie Das USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2-Gerät in die OOBE startet, erkennt es automatisch das Bereitstellungspaket auf dem USB-Laufwerk und startet die Bereitstellungsseite.
1. Nach 10 Sekunden wird das Bereitstellungspaket automatisch vom Gerät angewendet. 

Ihr Gerät ist jetzt konfiguriert und zeigt [den Bildschirm "Bereitstellung erfolgreich" an.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Verwenden von Autopilot mit Wi-Fi Verbindung
- Die Notwendigkeit von USB-C-Adaptern zur Reduzierung der Hardwareanforderungen durch Ethernet wurde entfernt, da Autopilot auf angeschlossenen Geräten Wi-Fi kann.

Sobald Sie HoloLens 2 mit WLAN verbinden, wird die OOBE nun während der OOBE nach einem Autopilotprofil für das Gerät suchen. Wenn eine gefunden wird, wird sie verwendet, um den Rest des AAD-Teilnahme- und Registrierungsflusses abzuschließen. Anders ausgedrückt: Die Verwendung von Ethernet auf USB-C oder Wi-Fi auf USB-C-Adapter ist keine Anforderung mehr, sie funktionieren jedoch weiterhin, wenn sie zu Beginn der Wi-Fi bereitgestellt werden. Erfahren Sie mehr über [Autopilot für HoloLens 2-Geräte.](hololens2-autopilot.md)

### TenantLockdown CSP und Autopilot
- Hält die Geräte am Mandanten der Organisation fest. Die Geräte werden an den Mandanten gebunden, selbst wenn sie zurückgesetzt werden oder erneut blinken. Mit zusätzlicher Sicherheit, indem die Einrichtung von Konten bei der Bereitstellung untersagt wird. 

HoloLens 2-Geräte unterstützen jetzt TenantLockdown CSP ab [Windows Holographic, Version 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) ermöglicht es, HoloLens 2 nur über Autopilot an die MDM-Registrierung zu binden. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf "true" oder "false" (anfänglich festgelegt) auf HoloLens 2 eingestellt ist, verbleibt dieser Wert auf dem Gerät, trotz erneutem Blinken, Betriebssystemupdates usw. 

Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt ist, wartet OOBE nach der Netzwerkverbindung unbegrenzt auf das erfolgreiche Herunterladen und Anwenden des Autopilot-Profils. 

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt wird, sind folgende Vorgänge in OOBE unzulässig: 
- Erstellen lokaler Benutzer mit Laufzeit-Bereitstellung 
- Durchführen einer Azure AD-Verknüpfungsoperation über Laufzeitbereitstellung 
- Auswählen, wem das Gerät in OOBE gehört 

#### Einrichtung mit Intune 
1. Erstellen Sie ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil und geben Sie „true“ für den RequireNetworkInOOBE-Knoten an, wie unten dargestellt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![TenantLockdown über OMA-URI einrichten](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown aktiv.

#### Aufhebung des RequireNetworkInOOBE von TenantLockdown auf HoloLens 2 mit Intune 
1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde. 

1. Erstellen Sie ein benutzerdefiniertes OMA URI-basiertes Gerätekonfigurationsprofil und geben Sie für RequireNetworkInOOBE den Wert „false“ an, wie unten dargestellt. Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Einstellung von RequireNetworkInOOBE auf „false“ über OMA-URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown inaktiv. 

#### Was würde in OOBE geschehen, wenn das Autopilot-Profil auf HoloLens deaktiviert wird, nachdem TenantLockdown auf „wahr“ festgelegt wurde? 
OOBE wartet unbestimmte Zeit auf den Autopilot-Profil-Download. Folgendes Dialogfeld wird angezeigt. Um die Auswirkungen von TenantLockdown zu entfernen, muss das Gerät zunächst bei seinem ursprünglichen Mandanten angemeldet werden, wobei nur Autopilot verwendet werden darf. RequireNetworkInOOBE muss wie im vorherigen Schritt beschrieben zurückgesetzt werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden. 

![Geräteinterne Ansicht für den Zeitpunkt, zu dem die Richtlinie auf dem Gerät durchgesetzt wird.](images/hololens-autopilot-lockdown.png)

Diese Informationen sind jetzt zusammen mit dem rest von Autopilot unter [Tenantlockdown CSP und Autopilot zu finden.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### Global zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene verwendet.

Dieses neue Feature ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Kioskmodus mit mehreren Apps zu konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System hat und für alle Benutzer gilt, die sich beim Gerät registrieren. Weitere Informationen zu diesem neuen Feature finden Sie im [HoloLens-Kiosk mit globalem zugewiesenem Zugriff.](hololens-global-assigned-access-kiosk.md)

### Automatisches Starten einer Anwendung im Kioskmodus mit mehreren Apps 
- Fokussierte Erfahrung mit dem automatischen Starten von Apps, um die Auswahl der Benutzeroberfläche und der App weiter zu erhöhen, die für die Benutzeroberfläche des Kioskmodus ausgewählt wurden.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur 1 App kann für den automatischen Start mit hervorgehobenen Attributen unten in der Konfiguration für zugewiesenen Zugriff festgelegt werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern
- Sichererer Kioskmodus durch Eliminieren verfügbarer Apps bei Kioskmodusfehlern. 

Vor dem Auftreten von Fehlern beim Anwenden des Kioskmodus hat HoloLens alle Anwendungen im Startmenü angezeigt. In Windows Holographic, Version 20H2, werden im Falle von Fehlern keine Apps wie unten im Startmenü angezeigt: 

![Abbildung des Kioskmodus, der jetzt aussieht, wenn er fehlschlägt.](images/hololens-kiosk-failure-behavior.png )

### Richtlinien für HoloLens
- Geräteverwaltungsoptionen speziell für HoloLens, die für die Verwaltung des Geräts erstellt wurden. 

Neue Mixed -Reality-Richtlinien wurden für HoloLens 2-Geräte unter Windows Holographic, Version 20H2, erstellt. Zu den neuen steuerbaren Einstellungen gehören: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed Reality-Aufzeichnungen, Festlegen, wann Diagnosen gesammelt werden können, und AAD-Gruppenmitgliedschaftscache.  

| Neue Richtlinie für HoloLens                                | Beschreibung                                                                               | Anmerkungen                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Ermöglicht das Deaktivieren von Helligkeitsschaltflächen, sodass das Drücken der Schaltfläche nicht die Helligkeit ändert.       | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Ermöglicht das Deaktivieren von Lautstärketasten, sodass durch drückende Tasten die Lautstärke nicht geändert wird.               | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\MicrophoneDisabled                    | Deaktiviert das Mikrofon, sodass keine Audioaufzeichnung auf HoloLens 2 möglich ist.                      | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\FallbackDiagnostics                   | Steuert das Verhalten, wann Diagnoseprotokolle erfasst werden können.                               | 0 Deaktiviert, 1 Aktiviert für Gerätebesitzer, 2 Aktiviert für alle (Standard) |
| MixedReality\HeadTrackingMode                      | Reserviert für die zukünftige Verwendung.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Steuert, wie viele Tage der Azure AD-Gruppenmitgliedschaftscache für Den Kiosk für Azure AD-Gruppen verwendet wird. | Siehe unten.                                                           |

### Azure AD-Gruppenmitgliedschaft für Offlinekiosk zwischenspeichern
- Aktivierte Offline kiosks für die Verwendung mit AAD-Gruppen für bis zu 60 Tage.

Diese Richtlinie steuert, wie viele Tage der Azure AD-Gruppenmitgliedschaftscache für Konfigurationen mit zugewiesenen Zugriffen für Azure AD-Gruppen für angemeldete Benutzer verwendet werden darf. Sobald dieser Richtlinienwert auf einen Wert größer als 0 festgelegt ist, wird der Cache andernfalls nicht verwendet.  

Name: AADGroupMembershipCacheValidityInDays URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min : 0 Tage  
Max : 60 Tage 

Schritte zur ordnungsgemäßen Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für den Kiosk für Azure AD-Gruppen, und weisen Sie es holoLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, mit der dieser Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) und holoLens-Geräten zugewiesen wird. 
    1. Der URI-Wert sollte im Textfeld "OMA-URI" als "./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays" eingegeben werden.
    1. Der Wert kann zwischen min/max allowed liegen.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Azure AD Benutzer 1 anmelden, wenn das Internet verfügbar ist, sobald sich der Benutzer anmeldet und die Azure AD-Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Azure AD Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Tage zulässt. 
1. Die Schritte 4 und 5 können für alle anderen Azure AD-Benutzer N wiederholt werden. Der wichtigste Punkt hier ist, dass sich jeder Azure AD-Benutzer über das Internet bei einem Gerät anmelden muss, damit wir mindestens einmal feststellen können, dass er Mitglied der Azure AD-Gruppe ist, für die die Kioskkonfiguration bestimmt ist. 
 
> [!NOTE]
> Bis Schritt 4 für einen Azure AD-Benutzer ausgeführt wird, tritt ein Fehlerverhalten auf, das in "getrennten" Umgebungen erwähnt wird. 

### Neue Geräteeinschränkungsrichtlinien für HoloLens 2
- Ermöglicht Benutzern das Verwalten bestimmter Geräteverwaltungsrichtlinien, z. B. das Blockieren des Hinzufügens oder Entfernens von Bereitstellungspaketen.

Neu aktivierte Richtlinien, die mehr Verwaltungsoptionen von HoloLens 2-Geräten ermöglichen. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Diese beiden neuen Policen für AllowAddProvisioningPackage und AllowRemoveProvisioningPackage werden unseren allgemeinen [Geräteeinschränkungen hinzugefügt.](hololens-common-device-restrictions.md)

> [!NOTE]
> In Bezug auf [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)unterstützt HoloLens nur die Konfiguration ./Vendor/MSFT/RemoteLock/Lock. Die Konfigurationen im Umgang mit PIN, z. B. Zurücksetzen und Wiederherstellen, werden nicht unterstützt.

### Neue Energierichtlinien für HoloLens 2
- Weitere Optionen, wenn HoloLens über Energierichtlinien in den Ruhezustand ein- oder aussperrt. 

Diese neu hinzugefügten Richtlinien ermöglichen Administratoren das Steuern von Energiezuständen, z. B. Leerlauftimeout. Um weitere Informationen zu den einzelnen Richtlinien zu erhalten, klicken Sie auf den Link für diese Richtlinie.

|     Link zur Richtliniendokumentation                |     Anmerkungen                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Beispielwert für die Verwendung in Windows-Konfigurations-Designer, z. B.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Beispielwert für die Verwendung in Windows-Konfigurations-Designer, z. B.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Beispielwert für die Verwendung in Windows-Konfigurations-Designer, d. h. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Beispielwert für die Verwendung in Windows-Konfigurations-Designer, d. h. 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Beispielwert für die Verwendung in Windows-Konfigurations-Designer, z. B.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Beispielwert für die Verwendung in Windows-Konfigurations-Designer, z. B.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Diese beiden neuen Policen für DisplayOffTimeoutOnBattery und DisplayOffTimeoutPluggedIn werden unseren allgemeinen [Geräteeinschränkungen hinzugefügt.](hololens-common-device-restrictions.md)

> [!NOTE]
> Um eine konsistente Erfahrung mit HoloLens 2 zu gewährleisten, stellen Sie sicher, dass Werte für DisplayOffTimeoutOnBattery und StandbyTimeoutOnBattery als derselbe Wert festgelegt sind. Gleiches gilt für DisplayOffTimeoutPluggedIn und StandbyTimeoutPluggedIn. Weitere Informationen zum modernen Standbymodus finden Sie unter "Anzeige-, Standby- und [Ruhezustandszeitgeber](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) im Ruhezustand".

### Neu aktivierte Updaterichtlinien für HoloLens
- Weitere Optionen zum Installieren von Updates oder Deaktivieren der Schaltfläche "Updates anhalten", um Updates sicherzustellen.

Diese Updaterichtlinien sind jetzt auf HoloLens 2-Geräten aktiviert:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Ausführliche Informationen zu diesen Updaterichtlinien und deren Verwendung für HoloLens-Geräte finden Sie hier unter [Verwalten von HoloLens-Updates.](hololens-updates.md)

### Sichtbarkeit der Seite "Aktivierte Einstellungen" für HoloLens 2
- Erhöhte Benutzeroberflächensteuerung in der Einstellungs-App, die verwechselt werden kann, um eine begrenzte Auswahl von Seiten zu zeigen.

Wir haben nun eine Richtlinie aktiviert, die es IT-Administratoren ermöglicht, entweder zu verhindern, dass bestimmte Seiten in der Systemeinstellungs-App sichtbar oder zugänglich sind, oder für alle Seiten mit Ausnahme der angegebenen Seiten. Klicken Sie auf den folgenden Link, um zu erfahren, wie Sie dieses Feature vollständig anpassen.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Um zu erfahren, welche Seiteneinstellungen Sie auf HoloLens 2 anpassen können, besuchen Sie unsere Seite ["UrIs für Einstellungen".](settings-uri-list.md) 
 
![Screenshot der Nutzungszeit, die in der Einstellungs-App geändert werden](images/hololens-page-visibility-list.jpg)

### Recherchemodus
Im Forschungsmodus wird HoloLens 2 zu einem Forschungstool für Computervisionen. Im Vergleich zu früheren Editionen hat der Forschungsmodus für HoloLens 2 die folgenden Vorteile:
-   Zusätzlich zu den Sensoren, die im HoloLens (1. Generation)-Forschungsmodus verfügbar gemacht werden, bieten wir jetzt im IMU-Sensor zugriff, einschließlich Beschleunigungsmesser, Gyroskop und Magnetometer.
-   HoloLens 2 bietet neue Funktionen, die zusammen mit dem Forschungsmodus verwendet werden können. Insbesondere zugriff auf artikulierte Hand-Tracking- und Eye-Tracking-APIs, die einen reichhaltigen Satz von Experimenten liefern können.

Forschende haben jetzt die Möglichkeit, den Forschungsmodus auf ihren HoloLens-Geräten zu aktivieren, um auf alle diese externen Datenströme von Rohdatensensoren zu zugreifen. Der Recherchemodus für HoloLens 2 bietet auch Zugriff auf die Beschleunigungsmesser-, Gyroskop- und Magnetometer-Messwerte. Um die Privatsphäre der Benutzer zu schützen, stehen unformatierte Kamerabilder für die Eye Tracking nicht über den Forschungsmodus zur Verfügung, die Blickrichtung ist jedoch über vorhandene APIs verfügbar.

Weitere technische Details finden Sie [in](https://docs.microsoft.com/windows/mixed-reality/research-mode) der Dokumentation zum Forschungsmodus.

### Aufzeichnungslänge erhöht
Aufgrund von Kundenfeedback haben wir die Aufzeichnungslänge von [Mixed -Reality-Aufzeichnungen erhöht.](holographic-photos-and-videos.md) Mixed Reality-Aufzeichnungen sind standardmäßig nicht mehr auf 5 Minuten beschränkt, sondern berechnen stattdessen die maximale Aufzeichnungslänge basierend auf dem verfügbaren Speicherplatz. Das Gerät schätzt die maximale Videoaufnahmedauer basierend auf dem verfügbaren Speicherplatz bis zu 80 % des gesamten Festplattenspeicherplatzes.

> [!NOTE]
> Die HoloLens verwendet die Standardmäßige Videoaufzeichnungsdauer (5 Minuten), wenn eine der folgenden Bedingungen auftritt:
> - Die geschätzte maximale Aufzeichnungsdauer ist kleiner als die standardmäßigen 5 Minuten.
> - Der verfügbare Speicherplatz beträgt weniger als 20 % des gesamten Speicherplatzes.

Die vollständigen Anforderungen finden Sie in unserer [Dokumentation zu holografischen Fotos und Videos.](holographic-photos-and-videos.md#maximum-recording-length) 

### Verbesserungen und Fehlerbehebungen im Update:
- Weitere Bildschirme in der OOBE befinden sich nun im dunklen Modus.
- Weitere Inhalte sollten auf die neuesten Online-Datenschutzbestimmungen verweisen.
- Es wurde ein Problem behoben, bei dem Benutzer keine VPN-Profile über Bereitstellungspakete bereitstellen konnten.
- Es wurde ein Problem mit der Proxykonfiguration für die VPN-Verbindung behoben.
- Aktualisierte Richtlinie zum Deaktivieren der Enumeration von USB-Funktionen über MDM für NCM für AllowUsbConnection.
- Es wurde ein Problem behoben, durch das verhindert wurde, dass ein Gerät von HoloLens im Datei-Explorer über das Medienübertragungsprotokoll (Media Transfer Protocol, MTP) angezeigt wird, wenn das Gerät als [Single-App-Kiosk](hololens-kiosk.md)eingerichtet ist. Beachten Sie, dass MTP (und die USB-Verbindung im Allgemeinen) weiterhin mithilfe der Richtlinie ["AllowUSBConnection" deaktiviert werden](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) kann.
- Es wurde ein Problem behoben, bei dem Symbole im Startmenü im Kioskmodus ordnungsgemäß skaliert wurden.
- Es wurde ein Problem behoben, aufgrund von HTTP-Zwischenspeicherung, das den Kioskmodus für Azure AD-Gruppen störte.
- Es wurde ein Problem behoben, bei dem Benutzer die Schaltfläche "Koppeln" nicht verwenden konnten, nachdem sie den Entwicklermodus mit Bereitstellungspaketen aktiviert hatten, es sei denn, sie deaktivierten und aktivierten den Entwicklermodus wieder.

## Windows Holographic, Version 1903 – November 2020 Update
- Build 18362.1085

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unseren neuesten Featureversions-Build Windows Holographic, Version 20H2, auszuprobieren.

## Windows Holographic, Version 2004 – Update vom Oktober 2020
- Build 19041.1124
 
Verbesserungen und Fehlerbehebungen im Update:

- Eine unnötige Überprüfung, die zu einem Laufzeitsystemfehler führte, wurde entfernt.

## Windows Holographic, Version 1903 – Update vom Oktober 2020
- Build 18362.1081

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## Windows Holographic, Version 2004 – September 2020 Update
- Build 19041.1117

Verbesserungen und Fehlerbehebungen im Update:

- Behebt ein Problem, das Visual Studio debuggen einer Anwendung verhinderte, wenn "SupportsMultipleInstances="true" im appxmanifest vorhanden ist.
- Diese Version enthält eine NCSI-Proxyerkennungskorrektur, um die fehlgeschlagene Interneterkennung über den Netzwerkproxy zu beheben. NCSI kann Computerproxy und pro Profilproxy für die Erkennung von Internetverbindungen verwenden. Der Benutzerproxy wird von NCSI in zukünftigen Veröffentlichungen unterstützt.
- Auf den meisten Windows Mixed Reality-Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. In früheren Versionen von HoloLens 2 wurde der Vektor jedoch stattdessen so ausgerichtet, dass er senkrecht zu den Anzeigepanels steht, was relativ zur idealen Ausrichtung um einige Grad nach unten gekippt wird. Neuere Versionen von HoloLens 2 haben dies korrigiert, um die semantische Konsistenz zwischen den Formfaktoren sicherzustellen.
- Verbesserte Robustheit der Handverfolgung, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.
- Diese Version enthält einen Fix zur Verbesserung der Qualität des Audiozeitstempel, der möglicherweise zu Problemen bei der Videoaufnahme beigetragen hat.

## Windows Holographic, Version 1903 – September 2020 Update
- Build 18362.1079

Verbesserungen und Fehlerbehebungen im Update:

- Auf den meisten Windows Mixed Reality-Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. In früheren Versionen von HoloLens 2 wurde der Vektor jedoch stattdessen so ausgerichtet, dass er senkrecht zu den Anzeigepanels steht, was relativ zur idealen Ausrichtung um einige Grad nach unten gekippt wird. Neuere Versionen von HoloLens 2 haben dies korrigiert, um die semantische Konsistenz zwischen den Formfaktoren sicherzustellen.
- Verbesserte Robustheit der Handverfolgung, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.

## Windows Holographic, Version 2004 – Update vom August 2020
- Build 19041.1113

Verbesserungen und Fehlerbehebungen im Update:

- Die App "Einstellungen" folgt dem Benutzer nicht mehr in die Irisregistrierungs- oder Eye Tracking-Kalibrierungserfahrungen.
- Behebung eines Fehlers, bei dem beim Anwenden eines Bereitstellungspakets während der #A0 das Gerät umbenannt und andere Aktionen ausgeführt werden (z. B. das Herstellen einer Verbindung mit einem Netzwerk), die anderen Aktionen nach dem Neustart des Geräts aufgrund der Umbenennung nicht ausgeführt werden.
- Geändertes Farbschema der ersten Geräteeinrichtungsflüsse zur Verbesserung der visuellen Qualität.

## Windows Holographic, Version 1903 – Update vom August 2020
- Build 18362.1074

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## Windows Holographic, Version 2004 – Juli 2020 Update
- Build 19041.1109

Verbesserungen und Fehlerbehebungen im Update:

- Entwickler können jetzt zwischen der Aktivierung oder Deaktivierung wählen, wenn für das Geräteportal eine sichere Verbindung erforderlich ist.
- Zuverlässigkeit für Anwendungsstarts nach Betriebssystemupdates verbessert.
- Standardhelligkeit des Posteingangs wurde auf 100 % geändert.
- Es wurde ein Problem mit der HTTPS-Weiterleitung für das Windows Device Portal auf HoloLens 2 behoben.

## Windows Holographic, Version 1903 – Juli 2020 Update
- Build 18362.1071

Verbesserungen und Fehlerbehebungen im Update:

- Es wurde ein Problem behoben, das dazu führen konnte, dass Hologramme in Unity-Anwendungen beim Verlust oder wiedererlangen der Nachverfolgung verloren gehen.
- Es wurde ein Problem behoben, das dazu führte, dass exklusive HoloLens-Apps während der Verwendung des HoloLens-Emulators mit Hardwarebeschleunigung auf bestimmten Geräten zurück auf die Shell stürzten.
- Es wurde ein Problem mit der HTTPS-Weiterleitung für das Windows Device Portal auf HoloLens 2 behoben.

## Windows Holographic, Version 2004 – Juni 2020 Update
- Build 19041.1106

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Recorder verfügen jetzt über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben sind.
  - Für den *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Immersive Headset))
  - Für den *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle "App Audio Gain"-Wert auf der Mixed Reality Capture-Seite im Windows Device Portal)
    - MicrophoneGain (der aktuelle "Mic Audio Gain"-Wert auf der Seite "Mixed Reality Capture" im Windows Device Portal)
- Behebung eines Fehlers zur Verbesserung der Audioqualität in Mixed Reality-Aufnahmeszenarien. Mit diesem Fix sollten insbesondere Audiobeschrungen in der Aufzeichnung beseitigt werden, wenn das **Startmenü** angezeigt wird.
- Verbesserte Hologrammstabilität in aufgezeichneten Videos.
- Es wurde ein Problem behoben, bei dem mixed reality capture video nicht aufzeichnen konnte, nachdem das Gerät mehrere Tage im Standbymodus war.
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Dieses Verhalten vermeidet ein Problem, das dazu führte, dass einige Apps beim Kippen des Visiers angehalten wurden, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert war. Die API ist jetzt für die Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Wenn Sie über eine Wi-Fi auf das Geräteportal zugreifen, kann ein Webbrowser den Zugriff aufgrund eines ungültigen Zertifikats verhindern. Der Browser kann einen Fehler wie "ERR_SSL_PROTOCOL_ERROR" melden, auch wenn das Gerätezertifikat zuvor als vertrauenswürdig eingestuft wurde. In diesem Fall können Sie nicht zum Geräteportal überkommen, da es keine Option gibt, Sicherheitswarnungen zu ignorieren. Mit diesem Update wurde das Problem behoben. Wenn das Gerätezertifikat zuvor heruntergeladen wurde und auf einem PC als vertrauenswürdig eingestuft wurde, um Browsersicherheitswarnungen zu entfernen, und der SSL-Fehler auftritt, muss das neue Zertifikat heruntergeladen und als vertrauenswürdig eingestuft werden, um Sicherheitswarnungen des Browsers zu beheben.
- Ermöglicht die Erstellung eines Laufzeitbereitstellungspakets, mit dem eine App mithilfe von MSIX-Paketen installiert werden kann.
- Unter "Hologramme des **** Einstellungssystems" wurde eine Einstellung hinzugefügt, mit der Benutzer automatisch alle Hologramme aus mixed Reality home entfernen können, wenn das Gerät  >  ****  >  **** heruntergefahren wird.
- Es wurde ein Problem behoben, das dazu führte, dass HoloLens-Apps, die ihr Pixelformat änderten, im HoloLens-Emulator schwarz gerendert wurden.
- Behebung eines Fehlers, der während der Irisanmeldung zu einem Absturz führte.
- Es wurde ein Problem mit wiederholten Storedownloads für bereits aktuelle Apps behoben.
- Ein Fehler wurde behoben, um zu verhindern, dass immersive Apps Microsoft Edge wiederholt öffnen.
- Es wurde ein Problem mit dem Starten der Fotos-App beim ersten Starten nach der Aktualisierung von version 1903 behoben.
- Verbesserte Leistung und Zuverlässigkeit.

## Windows Holographic, Version 1903 – Juni 2020 Update
- Build 18362.1064

Verbesserungen und Fehlerbehebungen im Update:

- Benutzerdefinierte MRC-Recorder verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben sind.
  - Für den *MRC-Videoeffekt:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Immersive Headset))
  - Für den *MRC-Audioeffekt:*
    - LoopbackGain (der aktuelle "App Audio Gain"-Wert auf der Mixed Reality Capture-Seite im Windows Device Portal)
    - MicrophoneGain (der aktuelle "Mic Audio Gain"-Wert auf der Seite "Mixed Reality Capture" im Windows Device Portal)
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Durch dieses Verhalten wird ein Problem vermieden, das dazu führt, dass einige Apps angehalten werden, wenn das Visier nach oben gekippt wird, auch wenn die Einstellung im Hintergrund aktiviert ist. Die API ist jetzt für die Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Es wurde ein Problem behoben, das dazu führte, dass HoloLens-Apps, die ihr Pixelformat änderten, im HoloLens-Emulator schwarz gerendert wurden.
- Es wurde ein Problem beim Starten der Fotos App beim ersten Starten nach der Aktualisierung von version 1903 behoben.

## Windows Holographic, Version 2004  
- Build - 19041.1103

Das wichtige Softwareupdate vom Mai 2020 für HoloLens 2, *Windows Holographic, Version 2004,* enthält eine Vielzahl von interessanten neuen Funktionen, z. B. Unterstützung für Windows Autopilot, dunklen App-Modus, USB-Ethernet-Unterstützung für 5G/LTE-Hotspots und vieles mehr. To update to the latest release, open the **Settings**   app, go to Update & **Security,** and select **the Check for Updates**   button. 

|             Feature                              |          Beschreibung                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Vorkonfigurierung und nahtloses Einrichten neuer Geräte für die Produktion mithilfe von Windows AutoPilot                 |
|       FIDO 2-Unterstützung                             |          Unterstützung für FIDO2-Sicherheitsschlüssel zum Aktivieren der schnellen und sicheren Authentifizierung für gemeinsam genutzte Geräte            |
|       Verbesserte Bereitstellung                      |          Nahtloses Anwenden eines Bereitstellungspakets von einem USB-Laufwerk auf Ihre HoloLens                              |
|       Anwendungsinstallationsstatus                 |          Überprüfen des Installationsstatus in der App "Einstellungen" für Apps, die über MDM an HoloLens 2 ge pusht wurden               |
|       Konfigurationsdienstanbieter (Configuration Service Providers, CSPs)   |          Neue Konfigurationsdienstanbieter zur Verbesserung der Administratorsteuerungsfunktionen hinzugefügt                 |
|       USB 5G/LTE-Unterstützung                       |          Erweiterte USB-Ethernet-Funktion ermöglicht Unterstützung für 5G/LTE                                    |
|       Dunkler App-Modus                              |          Dunkler App-Modus, verfügbar für Apps, die dunkle und helle Modi unterstützen, verbessert die Anzeige        |
|       Sprachbefehle                             |          Unterstützung für zusätzliche System-Sprachbefehle zum Steuern von HoloLens ohne Freisprechen                           |
|       Verbesserungen bei der Handverfolgung                 |          Verbesserungen bei der Handverfolgung sorgen dafür, dass Schaltflächen und 2D-Schieferinteraktionen präziser sind.                        |
|       Qualitätsverbesserungen und -korrekturen                 |          Verschiedene Verbesserungen der Systemleistung und Zuverlässigkeit auf der gesamten Plattform                            |

### Unterstützung für Windows Autopilot

Windows Autopilot für HoloLens 2 ermöglicht es dem Geräteumsatzkanal, HoloLens bei Ihrem Intune-Mandanten vorab zu registrieren. Wenn Geräte eintreffen, können sie sich selbst als freigegebene Geräte unter Ihrem Mandanten bereitstellen. Um die Vorteile der Selbstbereitstellung nutzen zu können, muss das Gerät während des ersten Bildschirms im Setup mithilfe eines USB-C-to-Ethernet eine Verbindung mit einem Netzwerk herstellen.

Nachdem ein Benutzer den Self-Deploying-Prozess von Autopilot gestartet hat, werden die folgenden Schritte abgeschlossen:

1. Verbinden des Geräts mit Azure Active Directory (Azure AD).
1. Verwenden von Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Herunterladen der gerätespezifischen Richtlinien, Zertifikate und Netzwerkprofile.
1. Bereitstellen des Geräts.
1. Präsentieren des Anmeldebildschirms für den Benutzer.

Weitere Informationen finden Sie im [Windows Autopilot für HoloLens 2-Evaluierungshandbuch.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Wenden Sie sich jetzt an Ihren Account Manager, um der AutoPilot Preview beizu treten. Autopilot-bereite Geräte beginnen in Kürze mit dem Versand.*

### Unterstützung von FIDO2-Sicherheitsschlüsseln

Einige Benutzer teilen ein HoloLens-Gerät mit anderen in einer Arbeits- oder Schulumgebung. Daher ist es wichtig, dass Benutzer problemlos lange Benutzernamen und Kennwörter eingeben müssen. Mit Fast Identity Online (FIDO) kann sich jeder in Ihrer Organisation (Azure AD-Mandant) nahtlos bei HoloLens anmelden, ohne einen Benutzernamen oder ein Kennwort einzugeben.

FIDO2-Sicherheitsschlüssel sind eine "unphishable" standardbasierte, kennwortlose Authentifizierungsmethode, die in jedem Formfaktor verwendet werden kann. FIDO ist ein offener Standard für die kennwortlose Authentifizierung. Benutzer und Organisationen können sich ohne Benutzernamen oder Kennwort bei ihren Ressourcen anmelden. Stattdessen verwenden sie einen externen Sicherheitsschlüssel oder einen Plattformschlüssel, der in ein Gerät integriert ist.

Informationen zu den ersten Schritte finden Sie unter [Aktivieren der Kennwort-Sicherheitsschlüssel-Anmeldung.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### Verbesserte MDM-Registrierung über Bereitstellungspaket

Mit Bereitstellungspaketen können Sie die Konfiguration von HoloLens über eine Konfigurationsdatei und nicht über die Out-of-Box-Erfahrung von HoloLens festlegen. Bisher mussten Bereitstellungspakete in den internen Speicher von HoloLens kopiert werden. Jetzt können sie auf einem USB-Laufwerk gespeichert werden, sodass sie einfacher auf mehreren HoloLens-Geräten wiederverwendet werden können, und Sie können Geräte parallel bereitstellen. Bereitstellungspakete unterstützen jetzt auch ein Feld für die Registrierung in der Geräteverwaltung, sodass es nach der Bereitstellung keine manuelle Einrichtung gibt.

Um dies auszuprobieren:

1. Laden Sie die neueste Version des Windows-Konfigurations-Designers aus dem Windows Store auf Ihren PC herunter.
1. Wählen **Sie "HoloLens-Geräte**  >  **bereitstellen" aus, um HoloLens 2-Geräte bereitstellen.**
2. Erstellen Sie Ihr Konfigurationsprofil. Kopieren Sie dann alle Dateien, die erstellt wurden, auf ein USB-C-Speichergerät.
3. Schließen Sie das USB-C-Gerät an eine beliebige flashende HoloLens an. Drücken Sie dann die **Ein/Aus-Taste,**  +  **** um Das Bereitstellungspaket anzuwenden.

### Installationsstatus der Line-of-Business-Anwendung

Die Bereitstellung und Verwaltung von MDM-Apps für Line-of-Business-Apps ist für HoloLens von entscheidender Bedeutung. Administratoren und Benutzer müssen den Installationsstatus der App für die Überwachung und Diagnose anzeigen. In dieser Version haben wir **** weitere Details unter "Einstellungen Kontenzugriff" auf Arbeits- oder Schulkonto hinzugefügt. Klicken  >  ****  >  ****  >  **Sie auf Ihre**  >  **Kontoinformationen.**

### Zusätzliche CSPs und Richtlinien

Ein [Konfigurationsdienstanbieter (Configuration Service Provider, CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ist eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf einem Gerät. In dieser Version fügen wir Unterstützung für weitere Richtlinien hinzu, um die Kontrolle zu erhöhen, die Administratoren gegenüber bereitgestellten HoloLens-Geräten haben. Eine Liste der von HoloLens unterstützten CSPs finden Sie unter [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Neu in dieser Version:

**Richtlinien-Konfigurationsdienstanbieter** 

Der Konfigurationsdienstanbieter für Richtlinien ermöglicht dem Unternehmen das Konfigurieren von Richtlinien auf Windows-Geräten. In dieser Version haben wir neue Richtlinien für HoloLens hinzugefügt, die hier aufgeführt sind. Weitere Informationen finden Sie unter [Richtlinien-CSPs, die von HoloLens 2 unterstützt werden.](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessAccesseInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy-Konfigurationsdienstanbieter**

Der Konfigurationsdienstanbieter "NetworkQoSPolicy" erstellt Richtlinien für die Netzwerkqualität (Quality of Service, QoS). Eine QoS-Richtlinie führt eine Reihe von Aktionen für Netzwerkverkehr basierend auf einem Satz von übereinstimmenden Bedingungen aus. Weitere Informationen finden Sie unter [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Erweiterte USB-Ethernet-Unterstützung für 5G/LTE-Kabelgeräte

Unterstützung wurde hinzugefügt, um bestimmte mobile Breitbandgeräte wie 5G/LTE-Telefone und Wi-Fi-Hotspots zu aktivieren, wenn sie per USB mit HoloLens 2 verbunden sind. Diese Geräte werden nun in den **Netzwerkeinstellungen als** eine andere Ethernetverbindung angezeigt. (Mobile Breitbandgeräte, die einen externen Treiber erfordern, werden nicht unterstützt.) Diese Funktion ermöglicht Verbindungen mit hoher Bandbreite, wenn Wi-Fi nicht verfügbar ist und Wi-Fi die Verbindungsfunktion nicht ausreichend ist. Weitere Informationen zu unterstützten #A0 finden Sie unter "Verbinden mit [Bluetooth und USB-C-Geräten.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### Verbesserungen bei der Handverfolgung

Diese Version enthält mehrere Verbesserungen bei der Handverfolgung:

- **Verweisen auf die Stabilität:** Das System wehrt sich jetzt gegen die Verunglierung des Zeigefingers, wenn er von der Handfläche übersäumt wird. Diese Änderung verbessert die Genauigkeit beim Drücken von Schaltflächen, Eingeben, Scrollen von Inhalten und vielem mehr! 
- **Reduzierte versehentliche Lufttipps:** Wir haben die Erkennung der Geste zum Tippen in die Luft verbessert. In mehreren gängigen Szenarien gibt es jetzt weniger versehentliche Aktivierungen, z. B. wenn Sie Ihre Hände an Ihre Seiten legen.
- **Zuverlässigkeit des Benutzerwechsels:** Das System ist jetzt schneller und zuverlässiger beim Aktualisieren der Handgröße, wenn Sie ein Gerät freigeben.
- **Reduzierter Handdiebstahl:** Wir haben die Behandlung von Fällen verbessert, in denen mehr als zwei Hände im Hinblick auf die Sensoren zur Hand sind. Wenn mehrere Personen eng zusammenarbeiten, ist die Wahrscheinlichkeit jetzt wesentlich geringer, dass die nachverfolgte Hand vom Benutzer zur Hand einer anderen Person in der Szene "springt".
- **Systemzuverlässigkeit:** Es wurde ein Problem behoben, das dazu führte, dass die Handverfolgung nicht mehr funktionierte, wenn das Gerät unter hoher Last war.

### Dunkler Modus

Viele Windows-Apps unterstützen jetzt sowohl dunkle als auch helle Modi. HoloLens 2-Benutzer können den Standardmodus für Apps auswählen, die beide unterstützen. Nach dem Update ist der Standardmäßige App-Modus "dunkel", Aber **** Sie können diese Einstellung ganz einfach ändern: Navigieren Sie zu Einstellungen Systemfarben Wählen Sie Ihren  >  ****  >  ****  >  **Standardmäßigen App-Modus.** 

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

![Fenster im dunklen Modus nebeneinander](images/DarkMode.jpg)

### Systemstimmenbefehle

Sie können jetzt Sprachbefehle mit jeder App auf dem Gerät verwenden. Weitere Informationen finden Sie unter ["Verwenden Sie Ihre Stimme, um HoloLens zu betreiben".](https://docs.microsoft.com/hololens/hololens-cortana) Siehe auch [unterstützte Sprachen für HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Updates für Cortana

Die aktualisierte App ist in Microsoft 365 integriert, damit Sie mehr auf Ihren Geräten erledigen können (derzeit nur in US-English). Auf HoloLens 2 unterstützt Cortana bestimmte gerätespezifische Befehle wie das Anpassen der Lautstärke oder das Neustarten nicht mehr. Diese Optionen werden jetzt von den neuen System-Sprachbefehlen unterstützt. Weitere Informationen zur neuen App Cortana finden Sie in unserem [Blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### Qualitätsverbesserungen und -korrekturen

Verbesserungen und Fehlerbehebungen auch im Update:  
- Ein aktives System zur Anzeigekalibrierung wurde eingeführt. Dieses Feature verbessert die Stabilität und Ausrichtung von Hologrammen. Sie bleiben nun erhalten, wenn Sie Ihren Kopf von einer Seite zur anderen bewegen.
- Behebung eines Fehlers, bei Wi-Fi Streaming auf HoloLens regelmäßig unterbrochen wurde. Wenn eine Anwendung angibt, dass Streaming mit geringer Latenz benötigt, implementieren Sie den Fix, indem Sie die [Funktion SetSocketMediaStreamingMode aufrufen.](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Es wurde ein Gerätehänger behoben, der während des Streamings im Recherchemodus aufgetreten ist.
- Ein Fehler wurde behoben, bei dem in einigen Fällen der richtige Benutzer beim Fortsetzen einer Sitzung nicht auf dem Anmeldebildschirm angezeigt wurde.
- Es wurde ein Problem behoben, bei dem Benutzer keine MDM-Protokolle über Einstellungen **exportieren konnten.**
- Es wurde ein Problem behoben, bei dem die Genauigkeit der Eye Tracking unmittelbar nach dem Out-of-Box-Setup niedriger als erwartet war.
- Es wurde ein Problem behoben, bei dem das Eye Tracking-Subsystem unter bestimmten Bedingungen keine Kalibrierung initialisieren oder durchführen konnte.
- Es wurde ein Problem behoben, bei dem die Augenkalibrierung zur Eingabe eines bereits kalibrierten Benutzers aufgefordert wurde.
- Es wurde ein Problem behoben, bei dem ein Treiber während der Augenkalibrierung abstürzte.
- Es wurde ein Problem behoben, bei dem wiederholte Drücken des Netzschalters zu einem Systemtimeout von 60 Sekunden und einem Absturz der Shell führen konnten.
- Verbesserte Stabilität für Tiefenpuffer.
- Es wurde eine **Schaltfläche "Freigeben"** im Feedbackhub hinzugefügt, damit Benutzer feedback einfacher teilen können.
- Behebung eines Fehlers, bei dem RoboRaid wan nicht ordnungsgemäß installiert wurde.

### Bekannte Probleme

- Ein Problem mit der zh-CN-Systemsprache verhindert, dass Sprachbefehle eine Mixed #A0 erstellen oder die #A1 des Geräts anzeigen.
- Ein Problem erfordert, dass Sie die Cortana-App starten, nachdem Sie das Gerät gestartet haben, um die Sprachaktivierung "Hey Cortana" zu verwenden. Wenn Sie von einem 18362-Build aktualisiert haben, wird möglicherweise auch eine zweite App-Kachel für die vorherige Version der Cortana-App angezeigt, die im Start nicht mehr **funktioniert.**

## Windows Holographic, Version 1903 – Mai 2020 Update 
- Build 18362.1061

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen, da das Team an dem Windows Holographic Version 2004 May Update wie zuvor beschrieben arbeitet.

## Windows Holographic, Version 1903 – April 2020 Update
- Build 18362.1059

**Dunkler Modus für unterstützte Apps** 

Viele Windows-Apps unterstützen sowohl den dunklen als auch den hellen Modus. HoloLens 2-Kunden können jetzt den Standardmodus für Apps auswählen, die beide Farbschemas unterstützen. Basierend auf Kundenfeedback haben wir den standardmäßigen App-Modus auf "dunkel" festgelegt, Aber Sie können diese Einstellung jederzeit einfach ändern: Navigieren Sie zu Einstellungen **> System > Farben,** um "Wählen Sie Ihren Standard-App-Modus" zu **suchen.**

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

**Verbesserungen und Fehlerbehebungen auch im Update:** 
- Sicherstellen, dass Shellüberlagerungen in Mixed -Reality-Erfassungen enthalten sind.
- Unreal entwickler can now use the 3D View page in Device Portal to test and debug their applications.
- Verbesserte Hologrammstabilität bei mixed Reality-Erfassung, wenn der *Algorithmus "HolographicDepthReprojectionMethod DepthReprojection"* verwendet wird.
- Fehler "WinRT IStreamSocketListener-API-Klasse nicht registriert" für 32-Bit-ARM behoben.

## Windows Holographic, Version 1903 – März 2020 Update 
- Build 18362.1056

Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Hologrammstabilität in Mixed Reality-Erfassung, wenn der *AutoPlanar-Algorithmus "HolographicDepthReprojectionMethod"* verwendet wird.
- Stellen Sie sicher, dass das Koordinatensystem, das einem Tiefen-MF-Beispiel zugeordnet ist, mit der öffentlichen Dokumentation konsistent ist.
- Verbesserte Produktivität von Entwicklern, indem Kunden große Textmengen über das Geräteportal einfügen können.

## Windows Holographic, Version 1903 – Februar 2020 Update 
- Build 18362.1053

Verbesserungen und Fehlerbehebungen im Update:

- Die HolographicSpace.UserPresence-API für Unity-Anwendungen wurde vorübergehend deaktiviert. Durch diese Änderung wird ein Problem vermieden, das dazu führte, dass einige Apps beim Kippen des Visiers angehalten wurden, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert war.
- Es wurde ein zufälliger HUP-Absturz behoben, der durch die Nachverfolgung der Hand verursacht wurde, bei dem der Benutzer bemerkte, dass die Benutzeroberfläche nach einigen Sekunden einfrierte und dann wieder in die Shell zurückfing.
- Verbesserte Nachverfolgung der Hand, sodass der obere Teil dieses Fingers beim Schießen mit dem Zeigefinger weniger wahrscheinlich unerwartet krümmt.
- Verbesserte Zuverlässigkeit von Head Tracking, räumlicher Zuordnung und anderer Laufzeiten.

## Windows Holographic, Version 1903 – Januar 2020 Update 
- Build 18362.1043
 
Verbesserungen und Fehlerbehebungen im Update:

- Verbesserte Stabilität für exklusive Apps beim Arbeiten mit dem HoloLens 2-Emulator.

## Windows Holographic, Version 1903 – Update vom Dezember 2019 
- Build 18362.1042

Verbesserungen und Fehlerbehebungen im Update:

- Fixes für die letzte Phase der Wiedergabe (Last Stage 2013, LSR) wurden eingeführt. Verbessertes visuelles Rendering von Hologrammen, um stabiler und präziser zu erscheinen, indem die Tiefe genauer erfasst wird. Dieses Symptom wird nach diesem Update deutlicher, wenn Apps die Tiefe von Hologrammen nicht richtig festlegen.
- Feste Stabilität exklusiver Apps und Navigation zwischen exklusiven Apps.
- Es wurde ein Problem behoben, bei dem mixed reality capture video nicht aufzeichnen konnte, nachdem das Gerät mehrere Tage im Standbymodus war.
- Verbesserte Hologrammstabilität.

## Windows Holographic, Version 1903 – Update vom November 2019 
- Build 18362.1039

Verbesserungen und Fehlerbehebungen im Update:

- Die Funktionalität von **"Sprachbefehle** auswählen" während der Ersteinrichtung für "en-CA" und "en-AU" wurde behoben.
- Verbesserte visuelle Qualität von Objekten, die weit entfernt in den neuesten Versionen von Unity und Mixed Reality Toolkit (MRTK) platziert sind.
- Behebung von Problemen mit holografischen Anwendungen, die beim Start angehalten wurden, bis das Startmenü geöffnet und dann geschlossen wurde.
- Korrekturen und Verbesserungen der OpenXR-Laufzeitkonformität für HoloLens 2 und den Emulator.
