---
title: Veröffentlichungshinweise für HoloLens 2
description: Bleiben Sie mit allen Updates in jeder neuen HoloLens 2-Version auf dem neuesten Stand.
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
ms.openlocfilehash: 9ad1fd599605a82280fc3ce45a2b78fcd0be6f14
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400715"
---
# <a name="hololens-2-release-notes"></a>Veröffentlichungshinweise für HoloLens 2

Um sicherzustellen, dass Sie eine produktive Erfahrung mit Ihren HoloLens-Geräten haben, veröffentlichen wir weiterhin Feature-, Bug- und Sicherheitsupdates. Auf dieser Seite können Sie sehen, was für HoloLens jeden Monat neu ist. Um das neueste HoloLens 2-Update [](hololens-update-hololens.md#check-for-updates-and-manually-update) zu erhalten, können Sie entweder nach Updates suchen und manuell aktualisieren oder das Vollblitzupdate (Full Flash Update, FFU) herunterladen, um Ihr Gerät über Advanced Recovery Companion zu [flashen.](hololens-recovery.md#clean-reflash-the-device) Der [Download](https://aka.ms/hololens2download) wird auf dem neuesten Stand gehalten und bietet den neuesten allgemein verfügbaren Build.

>[!NOTE]
> Wir freuen uns darauf, neue Features für Windows-Insider zu starten. Wir werden zum Dev Channel für die neuesten Updates flighting. Wir werden unsere [**HoloLens-Insider-Notizen**](hololens-insider.md) fortsetzen, wenn wir weitere Features und Updates zu unseren Windows-Insider-Builds hinzufügen. Freuen Sie sich und bereiten Sie sich darauf vor, diese Updates in Ihre Realität zu mischen.

Sehen Sie sich verwandte Versionshinweise an:

- [Besuchen Sie das Archiv des HoloLens-Emulators](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, Version 20H2 – März 2021 Update
- Build 19041.1140

Verbesserungen und Korrekturen im Update:

- Kunden, die AdvancedPhotoCapture oder LowLagPhotoCapture zum Erfassen von Fotos mit HoloLens 2 verwenden, können jetzt die Kamerapose bis zu 3 Sekunden nach der Aufnahme des Fotos abrufen.
- Behebung eines Speicherverlusts im Device Portal Service, das zu einer erhöhten Arbeitsspeicherauslastung durch den Dienst führte, die dazu führte, dass andere Anwendungen nicht genügend Arbeitsspeicher zuweisen.
- Es wurde ein Problem behoben, bei dem sich Benutzer, die beim mehrstufigen Rollout registriert sind, nicht beim Gerät anmelden können.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, Version 1903 – März 2021 Update
- Build 18362.1102

Verbesserungen und Korrekturen im Update:

- Behebung eines Speicherverlusts im Device Portal Service, das zu einer erhöhten Arbeitsspeicherauslastung durch den Dienst führte, die dazu führte, dass andere Anwendungen nicht genügend Arbeitsspeicher zuweisen.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Februar 2021
- Build 19041.1136

Verbesserungen und Korrekturen im Update:

- Behebt ein Problem beim Einrichten und Speichern von App-Updates für das erste Gerät.
- Behebt ein Problem mit Upgrades und Flügen für spätere HoloLens-Versionen.
- Nicht verwendete vorinstallierte Zertifikate wurden aus dem eSIM-Stammspeicher von HoloLens-Geräten entfernt.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, Version 1903 – Update vom Februar 2021
- Build 18362.1098

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, Version 20H2 – Update vom Januar 2021
- Build 19041.1134

Verbesserungen und Korrekturen im Update:

- Verbesserte Leistung beim Starten, Fortsetzen und Wechseln von Benutzern, wenn viele Benutzer auf dem Gerät sind.
- Arm32-Unterstützung für den [Forschungsmodus hinzugefügt.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, Version 1903 – Update vom Januar 2021
- Build 18362.1091

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, Version 20H2 – Update vom Dezember 2020
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Installieren von Apps auf HoloLens 2 über app Installer

Wir fügen **eine neue Funktion (App Installer)** hinzu, mit der Sie Anwendungen nahtloser auf Ihren HoloLens 2-Geräten installieren können. Das Feature ist **für nicht verwaltete**Geräte standardmäßig aktiviert. Um Unterbrechungen für Unternehmen zu verhindern, steht das App-Installationsprogramm derzeit nicht für **verwaltete** Geräte zur Verfügung.  

Ein Gerät wird als "verwaltet" betrachtet, **wenn** eines der folgenden Punkte zutrifft:
- MDM [Registriert](hololens-enroll-mdm.md)
- Mit [Bereitstellungspaket konfiguriert](hololens-provisioning.md)
- [Benutzeridentität](hololens-identity.md) ist Azure AD

Sie können jetzt Apps installieren, ohne den Entwicklermodus aktivieren oder das Geräteportal verwenden zu müssen.  Laden Sie einfach (über USB oder über Edge) das Appx Bundle auf Ihr Gerät herunter, und navigieren Sie zum Appx Bundle im Datei-Explorer, um zum Starten der Installation aufgefordert zu werden.  Alternativ können [Sie eine Installation über eine Webseite initiieren.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Genau wie Apps, die Sie aus dem Microsoft Store installieren oder querladen mithilfe der BRANCHEN-App-Bereitstellungsfunktion von MDM, müssen Apps digital mit dem Sign-Tool signiert werden, und das zum Signieren verwendete Zertifikat muss vom HoloLens-Gerät als vertrauenswürdig eingestuft werden, bevor die App bereitgestellt werden kann. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)

**Anweisungen zur Anwendungsinstallation.**

1.  Stellen Sie sicher, dass Ihr Gerät nicht als verwaltet betrachtet wird
1.  Stellen Sie sicher, dass Ihr HoloLens 2-Gerät eingeschaltet und mit Ihrem PC verbunden ist.
1.  Stellen Sie sicher, dass Sie beim HoloLens 2-Gerät angemeldet sind
1.  Navigieren Sie auf Ihrem PC zu Ihrer benutzerdefinierten App, und kopieren Sie yourapp.appxbundle in yourdevicename\Internal Storage\Downloads.   Nachdem Sie die Datei kopiert haben, können Sie das Gerät trennen.
1.  Öffnen Sie auf Ihrem HoloLens 2-Gerät das Startmenü, wählen Sie Alle Apps aus, und starten Sie die Datei-Explorer-App.
1.  Navigieren Sie zum Ordner Downloads. Möglicherweise müssen Sie im linken Bereich der App zuerst Dieses Gerät auswählen und dann zu Downloads navigieren.
1.  Wählen Sie die Datei yourapp.appxbundle aus.
1.  Das App-Installationsprogramm wird gestartet. Wählen Sie die Schaltfläche Installieren aus, um Ihre App zu installieren.
Die installierte App wird nach Abschluss der Installation automatisch gestartet.

Sie finden Beispiel-Apps unter [Windows Universal Samples GitHub,](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) um diesen Fluss zu testen.

Lesen Sie den vollständigen Prozess der [Installation von Apps auf HoloLens 2 mit dem App Installer.](app-deploy-app-installer.md)  

![Installieren von MRTK-Beispielen über das App-Installationsprogramm](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Korrekturen im Update:

- Die Handverfolgung verwaltet nun die Nachverfolgung in vielen neuen Fällen, in denen die Hand zuvor verloren gegangen wäre.  In einigen dieser neuen Fälle wird nur die Handfläche basierend auf der tatsächlichen Hand des Benutzers aktualisiert, während die anderen Verbindungen basierend auf einer vorherigen Pose abgeleitet werden.  Diese Änderung trägt zur Verbesserung der Nachverfolgungskonsistenz bei Bewegungen wie Slapping, Werfen, Schöpfen und Klatschen bei.  Es hilft auch in Fällen, in denen sich die Hand in der Nähe einer Oberfläche befindet oder ein Objekt hält.  Wenn Handgelenke abgeleitet werden, [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) wird der Wert für die Genauigkeit pro Verbindung auf "Ungefähr" anstelle von "Hoch" festgelegt.
- Es wurde ein Problem behoben, bei dem beim Zurücksetzen der PIN für Azure AD-Konten der Fehler "Ein Fehler aufgetreten ist.
- Benutzer sollten beim Starten von ET, Iris aus der Einstellungs-App, einem neuen Benutzer oder einem Benachrichtigungs-Popup deutlich weniger OOBE-Abstürze nach dem Start sehen.
- Benutzer sollten über die richtige Zeitzone verfügen, die aus OOBE kommt.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2020
- Build 18362.1088

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unser neuestes Windows Holographic,Version 20H2 – Dezember 2020 Update und das neue App Installer-Feature, das im Build hinzugefügt wurde, auszuprobieren.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, Version 20H2
- Build 19041.1128

Windows Holographic, Version 20H2, ist jetzt verfügbar und bietet HoloLens 2-Benutzern und IT-Experten eine große Reihe neuer Features. Von der Automatischen Augenpositionierung über den Zertifikat-Manager in den Einstellungen bis hin zu verbesserten Kioskmodusfunktionen und neuen Autopilot-Setupfunktionen. Mit diesem neuen Update können IT-Teams die Konfiguration und Verwaltung von HoloLens-Geräten präziser steuern und benutzern noch nahtlosere holografische Erfahrungen bieten. 

Diese neueste Version ist ein monatliches Update auf Version 2004, aber dieses Mal werden neue Features mit einschl. Die Haupt buildnummer bleibt unverändert, und Windows Update gibt eine monatliche Version für Version 2004 (Build 19041) an. Sie können ihre Buildnummer im Bildschirm Einstellungen > Informationen anzeigen, um zu bestätigen, dass Sie auf dem neuesten verfügbaren Build 19041.1128+ sind. Um auf die neueste Version zu aktualisieren, öffnen Sie die App Einstellungen, wechseln Sie zu Update & Security, und tippen Sie auf Auf Updates überprüfen. Weitere Informationen zum Verwalten von HoloLens-Updates finden Sie [auf dieser Seite.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Neues in Windows Holographic, Version 20H2  

| Feature                                              | Beschreibung                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Unterstützung der automatischen Augenstellung](hololens-release-notes.md#auto-eye-position-support) | Berechnet die Augenpositionen aktiv, ohne dass Benutzer die Eye Tracking-Kalibrierung durchf?chen.   |
| [Zertifikat-Manager](hololens-release-notes.md#certificate-manager)   | Ermöglicht neue einfachere Methoden zum Installieren und Entfernen von Zertifikaten aus der Einstellungs-App.     |
| [Automatisches Starten der Bereitstellung über USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Bereitstellungspakete auf USB-Laufwerken werden automatisch zur Bereitstellungsseite in OOBE aufgefordert.                                                         |
| [Automatische Bestätigung von Bereitstellungspaketen in OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Bereitstellungspakete werden automatisch während der OOBE von der Bereitstellungsseite angewendet.                                                         |
| [Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Kombinieren der automatischen Bereitstellungsstarts und automatischen Bestätigung. |
| [Verwenden von Autopilot mit Wi-Fi Verbindung](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Verwenden Sie Autopilot von Wi-Fi ohne Ethernetadapter. |
| [TenantLockdown CSP und Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Nachdem die Mandantenregistrierung und die Richtlinie angewendet wurden, kann das Gerät nur dann bei diesem Mandanten registriert werden, wenn das Gerät zurückgesetzt oder erneut geblitzt wird. |
| [Global zugewiesener Zugriff](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Neue Konfigurationsmethode für den Kioskmodus mit mehreren Apps, bei dem der Kiosk auf Systemebene angewendet wird, wodurch er für alle gilt.                  |
| [Automatisches Starten einer App im Multi-App-Kiosk](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Legt fest, dass eine Anwendung beim Anmelden an einem Kioskmodus mit mehreren Apps automatisch gestartet wird.                                                        |
| [Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Kioskmodusfehler hat jetzt ein restriktives Fallback.                                                                                                |
| [HoloLens-Richtlinien](hololens-release-notes.md#hololens-policies)                                    | Neue Richtlinien für HoloLens.     |
| [Azure AD-Gruppenmitgliedschaft für Offlinekiosk zwischenspeichern](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Mit der neuen Richtlinie können Benutzer den Gruppenmitgliedschaftscache verwenden, um den Kioskmodus offline für die festgelegte Anzahl von Tagen zu verwenden.                                        |
| [Neue Geräteeinschränkungsrichtlinien für HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Geräteverwaltungsrichtlinien, die neu für HoloLens 2 aktiviert wurden.                                                                                |
| [Neue Energierichtlinien für HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Neu unterstützte Richtlinien für Energietimeouteinstellungen.  |
| [Aktualisieren von Richtlinien](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Neu aktivierte Richtlinien, die die Kontrolle über Updates ermöglichen.           |
| [Sichtbarkeit der Seite "Aktivierte Einstellungen" für HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Richtlinie, um zu wählen, welche Seiten in der Einstellungs-App angezeigt werden.             |
| [Forschungsmodus](hololens-release-notes.md#research-mode) | Verwenden des Recherchemodus für HoloLens 2. |
| [Aufzeichnungslänge erhöht](hololens-release-notes.md#recording-length-increased) | MRC-Aufzeichnungen werden nicht mehr auf 5 Minuten begrenzt. |
| [Verbesserungen und Korrekturen im Update](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Zusätzliche Korrekturen im Update.   |

### <a name="auto-eye-position-support"></a>Automatische Unterstützung der Augenposition

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

Diese Informationen finden Sie später mit [anderen Kalibrierungsinformationen](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose- und Validierungstools für gerätesicherheit und -compliance durch den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerziellen Umgebungen bereitstellen, Probleme behandeln und überprüfen.

In Windows Holographic, Version 20H2, fügen wir einen Zertifikat-Manager in der HoloLens 2-Einstellungs-App hinzu. Wechseln Sie **zu Einstellungen > Update & Security > Certificates**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit zum Anzeigen, Installieren und Entfernen von Zertifikaten auf Ihrem Gerät. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer jetzt über verbesserte Überwachungs-, Diagnose- und Validierungstools, um sicherzustellen, dass Geräte sicher und kompatibel bleiben. 

-   **Überwachung:** Möglichkeit, zu überprüfen, ob ein Zertifikat ordnungsgemäß bereitgestellt wurde, oder um zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, spart die Validierung, dass die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit und hilft bei der Problembehandlung. 
-   **Überprüfung:** Die Überprüfung, ob ein Zertifikat dem beabsichtigten Zweck dient und funktionsfähig ist, kann erhebliche Zeit sparen, insbesondere in kommerziellen Umgebungen, bevor Zertifikate in größerem Umfang bereitgestellt werden.

Um ein bestimmtes Zertifikat schnell in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Speicher- oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Wählen Sie zum Anzeigen einzelner Zertifikateigenschaften das Zertifikat aus, und klicken Sie auf **Info**. 

Die Zertifikatinstallation unterstützt derzeit .cer- und .crt-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in Current User installiert werden. Benutzer können nur Direkt installierte Zertifikate aus der Benutzeroberfläche "Einstellungen" entfernen. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch mit demselben Mechanismus entfernt werden.

#### <a name="to-install-a-certificate"></a>So installieren Sie ein Zertifikat: 

1.  Verbinden Sie HoloLens 2 mit einem PC.
1.  Platzieren Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort in HoloLens 2.
1.  Navigieren Sie **zu Einstellungen App > Update & Security > Certificates**, und wählen Sie Installieren eines Zertifikats aus.
1.  Klicken **Sie auf Datei importieren,** und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen **Sie Speicherort speichern aus.**
1.  Wählen Sie **Zertifikatspeicher aus.**
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert werden.

#### <a name="to-remove-a-certificate"></a>So entfernen Sie ein Zertifikat: 
1. Navigieren Sie zu **Einstellungen App > Update and Security > Certificates**.
1. Suchen Sie im Suchfeld nach dem Namen des Zertifikats.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen**
1. Wählen **Sie Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.

![Zertifikatanzeige in der Einstellungs-App](images/certificate-viewer-device.jpg)

![Abbildung der Verwendung der Zertifikatbenutzeroberfläche zum Installieren eines Zertifikats](images/certificate-device-install.jpg)

Diese Informationen finden Sie später [auf einer neuen Seite des Zertifikat-Managers](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse, die eine geringere Benutzerinteraktion ermöglichen, wenn USB-Laufwerke mit Bereitstellungspaketen während der OOBE verwendet werden.

Vor dieser Version mussten Benutzer den Bereitstellungsbildschirm während der OOBE manuell starten, um die Bereitstellung mithilfe einer Tastenkombination zu ermöglichen. Jetzt können Benutzer die Tastenkombination überspringen, indem sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Schließen Sie das USB-Laufwerk mit dem Bereitstellungspaket während des ersten interagierbaren Moments von OOBE an.
1. Wenn das Gerät bereit ist, bereitgestellt zu werden, wird die Eingabeaufforderung automatisch mit der Bereitstellungsseite geöffnet. 

Hinweis: Wenn ein USB-Laufwerk während des Startens des Geräts angeschlossen bleibt, wird von OOBE das vorhandene USB-Speichergerät aufgezählt, und es wird darauf achten, dass weitere angeschlossen werden.

Weitere Informationen zum Anwenden von Bereitstellungspaketen während der OOBE finden Sie in der [HoloLens-Bereitstellungsdokumentation.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Weitere Informationen zur [Bereitstellung des automatischen Startes](hololens-provisioning.md#auto-launch-provisioning-from-usb) über einen USB finden Sie in der HoloLens-Bereitstellungsdokumentation.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatische Bestätigung von Bereitstellungspaketen in OOBE
- Wenn die Seite Bereitstellungspaket angezeigt wird, werden automatisch alle aufgeführten Pakete angewendet.

Wenn der Hauptbildschirm für die Bereitstellung angezeigt wird, zählt OOBE 10 Sekunden nach unten, bevor automatisch mit der Anwendung aller Bereitstellungspakete begonnen wird. Benutzer können die [Pakete, die](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) sie erwartet haben, innerhalb von 10 Sekunden bestätigen oder abbrechen.

### <a name="automatic-provisioning-without-using-ui"></a>Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche
- Kombinierte automatische Prozesse für reduzierte Geräteinteraktionen für die Bereitstellung. 

Durch die Kombination des automatischen Startens der Bereitstellung von USB-Geräten und der automatischen Bestätigung von Bereitstellungspaketen kann ein Benutzer HoloLens 2-Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts zu verwenden oder sogar das Gerät zu tragen. Sie können weiterhin dasselbe USB-Laufwerk und das gleiche Bereitstellungspaket für mehrere Geräte verwenden. Dies ist nützlich, um mehrere Geräte gleichzeitig in demselben Bereich bereitstellen zu können. 

1. [Erstellen eines Bereitstellungspakets](hololens-provisioning.md) mithilfe [von Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken des Geräts abgeschlossen hat, trennen Sie das USB-C-Kabel. 
1. Schließen Sie Ihr USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2-Gerät in OOBE startet, erkennt es automatisch das Bereitstellungspaket auf dem USB-Laufwerk und startet die Bereitstellungsseite.
1. Nach 10 Sekunden wird das Bereitstellungspaket automatisch vom Gerät angewendet. 

Ihr Gerät ist jetzt konfiguriert und zeigt [den Bildschirm Bereitstellung erfolgreich an.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Verwenden von Autopilot mit Wi-Fi Verbindung
- Die Notwendigkeit von USB-C-Adaptern wurde entfernt, um die Hardwareanforderungen zu reduzieren, da Autopilot auf verbundenen Geräten Wi-Fi kann.

Sobald Sie HoloLens 2 mit WLAN verbinden, überprüft OOBE nun während der OOBE nach einem Autopilotprofil für das Gerät. Wenn eine gefunden wird, wird sie zum Abschließen des restlichen AAD-Join- und Registrierungsflusses verwendet. Mit anderen Worten, die Verwendung von Ethernet zu USB-C oder Wi-Fi zu USB-C-Adapter ist keine Anforderung mehr, sie funktionieren jedoch weiterhin, wenn sie zu Beginn der Wi-Fi bereitgestellt werden. Erfahren Sie mehr [über Autopilot für HoloLens 2-Geräte.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>TenantLockdown CSP und Autopilot
- Hält die Geräte am Mandanten der Organisation fest. Die Geräte werden an den Mandanten gebunden, selbst wenn sie zurückgesetzt werden oder erneut blinken. Mit zusätzlicher Sicherheit, indem die Einrichtung von Konten bei der Bereitstellung untersagt wird. 

HoloLens 2-Geräte unterstützen jetzt TenantLockdown CSP ab [Windows Holographic Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) ermöglicht es, HoloLens 2 nur über Autopilot an die MDM-Registrierung zu binden. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf "true" oder "false" (anfänglich festgelegt) auf HoloLens 2 eingestellt ist, verbleibt dieser Wert auf dem Gerät, trotz erneutem Blinken, Betriebssystemupdates usw. 

Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt ist, wartet OOBE nach der Netzwerkverbindung unbegrenzt auf das erfolgreiche Herunterladen und Anwenden des Autopilot-Profils. 

Sobald der RequireNetworkInOOBE-Knoten von TenantLockdown CSP auf HoloLens 2 auf „true“ gesetzt wird, sind folgende Vorgänge in OOBE unzulässig: 
- Erstellen lokaler Benutzer mit Laufzeit-Bereitstellung 
- Durchführen einer Azure AD-Verknüpfungsoperation über Laufzeitbereitstellung 
- Auswählen, wem das Gerät in OOBE gehört 

#### <a name="how-to-set-this-using-intune"></a>Einrichtung mit Intune 
1. Erstellen Sie ein benutzerdefiniertes OMA-URI-Gerätekonfigurationsprofil und geben Sie „true“ für den RequireNetworkInOOBE-Knoten an, wie unten dargestellt.
Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![TenantLockdown über OMA-URI einrichten](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown aktiv.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Aufhebung des RequireNetworkInOOBE von TenantLockdown auf HoloLens 2 mit Intune 
1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde. 

1. Erstellen Sie ein benutzerdefiniertes OMA URI-basiertes Gerätekonfigurationsprofil und geben Sie für RequireNetworkInOOBE den Wert „false“ an, wie unten dargestellt. Der OMA-URI-Wert sollte ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE lauten

   > [!div class="mx-imgBorder"]
   > ![Screenshot der Einstellung von RequireNetworkInOOBE auf „false“ über OMA-URI in Intune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe und weisen Sie das Gerätekonfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Gerät zu einem Mitglied der im vorherigen Schritt erstellten Gruppe und lösen Sie die Synchronisierung aus.

Überprüfen Sie im Intune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf das HoloLens 2-Gerät angewendet wird, sind die Effekte von TenantLockdown inaktiv. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Was würde in OOBE geschehen, wenn das Autopilot-Profil auf HoloLens deaktiviert wird, nachdem TenantLockdown auf „wahr“ festgelegt wurde? 
OOBE wartet unbestimmte Zeit auf den Autopilot-Profil-Download. Folgendes Dialogfeld wird angezeigt. Um die Auswirkungen von TenantLockdown zu entfernen, muss das Gerät zunächst bei seinem ursprünglichen Mandanten angemeldet werden, wobei nur Autopilot verwendet werden darf. RequireNetworkInOOBE muss wie im vorherigen Schritt beschrieben zurückgesetzt werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden. 

![Geräteinterne Ansicht für den Zeitpunkt, zu dem die Richtlinie auf dem Gerät durchgesetzt wird.](images/hololens-autopilot-lockdown.png)

Diese Informationen finden Sie nun zusammen mit dem rest von Autopilot unter [Tenantlockdown CSP und Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Globaler zugewiesener Zugriff – Kioskmodus
- Reduzierte Identitätsverwaltung für Kiosk, indem die neue Kioskmethode aktiviert wird, die den Kioskmodus auf Systemebene verwendet.

Dieses neue Feature ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Kioskmodus mit mehreren Apps zu konfigurieren, der auf Systemebene anwendbar ist, keine Affinität mit einer Identität im System hat und für alle Benutzer gilt, die sich beim Gerät registrieren. Weitere Informationen zu diesem neuen Feature finden Sie im [globalen HoloLens-Kiosk](hololens-global-assigned-access-kiosk.md)für den zugewiesenen Zugriff.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisches Starten einer Anwendung im Kioskmodus mit mehreren Apps 
- Fokussierte Erfahrung mit der automatischen App-Start, eine weitere Erhöhung der Benutzeroberflächen- und App-Auswahl, die für die Kioskmoduserfahrung ausgewählt wurde.

Gilt nur für den Kioskmodus mit mehreren Apps, und nur 1 App kann für den automatischen Start mithilfe des hervorgehobenen Attributs unten unter Konfiguration mit zugewiesenen Zugriff festgelegt werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Verhaltensänderungen im Kioskmodus für die Behandlung von Fehlern
- Sichererer Kioskmodus durch Eliminieren verfügbarer Apps im Kioskmodus. 

Vor dem Auftreten von Fehlern beim Anwenden des Kioskmodus hat HoloLens alle Anwendungen im Startmenü angezeigt. In Windows Holographic, Version 20H2, werden im Falle von Fehlern keine Apps wie unten im Startmenü angezeigt: 

![Abbildung des Kioskmodus, der jetzt angezeigt wird, wenn er ausfällt.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens-Richtlinien
- Geräteverwaltungsoptionen speziell für HoloLens, die für die Verwaltung des Geräts erstellt wurden. 

Neue Mixed Reality-Richtlinien wurden für HoloLens 2-Geräte unter Windows Holographic, Version 20H2, erstellt. Zu den neuen kontrollierbaren Einstellungen gehören: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed Reality-Aufzeichnungen, Festlegen, wann Diagnosen erfasst werden können, und AAD-Gruppenmitgliedschaftscache.  

| Neue HoloLens-Richtlinie                                | Beschreibung                                                                               | Anmerkungen                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Ermöglicht das Deaktivieren von Helligkeitsschaltflächen, sodass durch drücken keine Helligkeit geändert wird.       | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Ermöglicht das Deaktivieren von Lautstärkeschaltflächen, sodass das Drücken der Lautstärke nicht geändert wird.               | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\MicrophoneDisabled                    | Deaktiviert das Mikrofon, damit keine Audioaufzeichnung in HoloLens 2 möglich ist.                      | 1 Ja, 0 Nein (Standard)                                                |
| MixedReality\FallbackDiagnostics                   | Steuert das Verhalten, wann Diagnoseprotokolle erfasst werden können.                               | 0 Deaktiviert, 1 Aktiviert für Gerätebesitzer, 2 Aktiviert für alle (Standard) |
| MixedReality\HeadTrackingMode                      | Reserviert für die zukünftige Verwendung.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Steuert, wie viele Tage der Azure AD-Gruppenmitgliedschaftscache für Kiosk für Azure AD-Gruppen verwendet wird. | Siehe unten.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-Gruppenmitgliedschaft für Offlinekiosk zwischenspeichern
- Aktivierte Offlinekiosk für die Verwendung mit AAD-Gruppen für bis zu 60 Tage.

Diese Richtlinie steuert, wie viele Tage der Azure AD-Gruppenmitgliedschaftscache für Konfigurationen mit zugewiesenen Zugriffen für Azure AD-Gruppen für angemeldete Benutzer verwendet werden darf. Sobald dieser Richtlinienwert auf einen Wert größer als 0 festgelegt ist, wird der Cache andernfalls nicht verwendet.  

Name: AADGroupMembershipCacheValidityInDays URI-Wert: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min. – 0 Tage  
Max. - 60 Tage 

Schritte zum ordnungsgemäßen Verwenden dieser Richtlinie: 
1. Erstellen Sie ein Gerätekonfigurationsprofil für Kiosk für Azure AD-Gruppen, und weisen Sie es HoloLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte OMA-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) legt, und weisen Sie ihn HoloLens-Geräten zu. 
    1. Der URI-Wert sollte im Textfeld OMA-URI als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays eingegeben werden.
    1. Der Wert kann zwischen min/max zulässig sein.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Azure AD User 1 anmelden, wenn das Internet verfügbar ist, sobald sich der Benutzer anmeldet und die Azure AD-Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Azure AD-Benutzer 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Anzahl von Tagen zulässt. 
1. Die Schritte 4 und 5 können für jeden anderen Azure AD-Benutzer N wiederholt werden. Der entscheidende Punkt hier ist, dass sich jeder Azure AD-Benutzer über das Internet bei einem Gerät anmelden muss, damit wir feststellen können, dass er Mitglied der Azure AD-Gruppe ist, auf die die Kioskkonfiguration ausgerichtet ist. 
 
> [!NOTE]
> Bis Schritt 4 für einen Azure AD-Benutzer ausgeführt wird, tritt ein Fehlerverhalten auf, das in "getrennten" Umgebungen erwähnt wird. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Neue Geräteeinschränkungsrichtlinien für HoloLens 2
- Ermöglicht Benutzern das Verwalten bestimmter Geräteverwaltungsrichtlinien, z. B. das Blockieren des Hinzufügens oder Entfernens von Bereitstellungspaketen.

Neu aktivierte Richtlinien, die mehr Verwaltungsoptionen für HoloLens 2-Geräte ermöglichen. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Diese beiden neuen Policen für AllowAddProvisioningPackage und AllowRemoveProvisioningPackage werden unseren allgemeinen [Geräteeinschränkungen hinzugefügt.](hololens-common-device-restrictions.md)

> [!NOTE]
> In Bezug auf [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)unterstützt HoloLens nur die Konfiguration ./Vendor/MSFT/RemoteLock/Lock. Die Konfigurationen im Umgang mit PIN wie Zurücksetzen und Wiederherstellen werden nicht unterstützt.

### <a name="new-power-policies-for-hololens-2"></a>Neue Energierichtlinien für HoloLens 2
- Weitere Optionen für den Ein- oder Ausruhen von HoloLens über Energierichtlinien. 

Diese neu hinzugefügten Richtlinien ermöglichen Administratoren die Steuerung von Energiezuständen, z. B. leerlauftimeout. Um mehr über jede einzelne Richtlinie zu erfahren, klicken Sie auf den Link für diese Richtlinie.

|     Link zur Richtliniendokumentation                |     Anmerkungen                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, d. h.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, d. h.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Beispielwert, der in Windows Configuration Designer verwendet werden soll, d. h. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Beispielwert, der in Windows Configuration Designer verwendet werden soll, d. h. 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, d. h.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, d. h.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Diese beiden neuen Policen für DisplayOffTimeoutOnBattery und DisplayOffTimeoutPluggedIn werden unseren allgemeinen [Geräteeinschränkungen hinzugefügt.](hololens-common-device-restrictions.md)

> [!NOTE]
> Stellen Sie sicher, dass werte für DisplayOffTimeoutOnBattery und StandbyTimeoutOnBattery als derselbe Wert festgelegt sind, um eine konsistente Erfahrung mit HoloLens 2 zu gewährleisten. Gleiches gilt für DisplayOffTimeoutPluggedIn und StandbyTimeoutPluggedIn. Weitere Informationen zum modernen Standbymodus finden Sie unter [Display, Sleep, and hibernate idle timers.](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers)

### <a name="newly-enabled-update-policies-for-hololens"></a>Neu aktivierte Updaterichtlinien für HoloLens
- Weitere Optionen für die Installation oder Deaktivierung der Schaltfläche Updates anhalten, um Updates sicherzustellen.

Diese Updaterichtlinien sind jetzt auf HoloLens 2-Geräten aktiviert:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Ausführliche Informationen zu diesen Updaterichtlinien und deren Verwendung für HoloLens-Geräte finden Sie hier [unter Manage HoloLens updates](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Sichtbarkeit der Seite "Aktivierte Einstellungen" für HoloLens 2
- Verbessertes Ui-Steuerelement in der Einstellungs-App, was verwechselt werden kann, um eine begrenzte Auswahl von Seiten zu zeigen.

Wir haben nun eine Richtlinie aktiviert, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der Systemeinstellungen-App sichtbar oder zugänglich sind, oder dass dies für alle Seiten mit Ausnahme der angegebenen Seiten möglich ist. Um zu erfahren, wie Sie dieses Feature vollständig anpassen, klicken Sie auf den folgenden Link.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Informationen zu den Seiteneinstellungen, die Sie in HoloLens 2 anpassen können, finden Sie auf der Seite [Einstellungen URIs](settings-uri-list.md). 
 
![Screenshot der Nutzungszeit, die in der Einstellungs-App geändert werden](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Forschungsmodus
Im Forschungsmodus wird HoloLens 2 zu einem leistungsstarken Tool für die Computervisionsforschung. Im Vergleich zu früheren Editionen bietet der Forschungsmodus für HoloLens 2 die folgenden Vorteile:
-   Zusätzlich zu Sensoren, die im HoloLens -Forschungsmodus (1. Generation) verfügbar gemacht werden, bieten wir jetzt imU-Sensor zugriff, einschließlich Beschleunigungsmesser, Gyroskop und Magnetometer.
-   HoloLens 2 bietet neue Funktionen, die zusammen mit dem Forschungsmodus verwendet werden können. Insbesondere der Zugriff auf artikulierte Handverfolgungs- und Eye-Tracking-APIs, die einen reichhaltigen Satz von Experimenten bieten können.

Forschende haben nun die Möglichkeit, den Forschungsmodus auf ihren HoloLens-Geräten zu aktivieren, um auf alle externen Datenströme mit unformatiertem Bild zu zugreifen. Der Forschungsmodus für HoloLens 2 bietet auch Zugriff auf beschleunigungsmesser-, Gyroskop- und Magnetometer-Messwerte. Um die Privatsphäre der Benutzer zu schützen, sind unformatierte Kamerabilder für die Augenverfolgung nicht über den Forschungsmodus verfügbar, die Blickrichtung ist jedoch über vorhandene APIs verfügbar.

Weitere technische Details [finden](https://docs.microsoft.com/windows/mixed-reality/research-mode) Sie in der Dokumentation zum Forschungsmodus.

### <a name="recording-length-increased"></a>Aufzeichnungslänge erhöht
Aufgrund von Kundenfeedback haben wir die Aufzeichnungsdauer von [Mixed Reality-Aufzeichnungen erhöht.](holographic-photos-and-videos.md) Mixed Reality-Aufzeichnungen sind standardmäßig nicht mehr auf 5 Minuten beschränkt, sondern berechnen stattdessen die maximale Aufzeichnungslänge basierend auf dem verfügbaren Speicherplatz. Das Gerät schätzt die maximale Videoaufnahmedauer basierend auf dem verfügbaren Speicherplatz bis zu 80 % des gesamten Speicherplatzes.

> [!NOTE]
> Die HoloLens verwendet die Standardmäßige Videoaufzeichnungslänge (5 Minuten), wenn eine der folgenden Schritte auftritt:
> - Die geschätzte maximale Aufzeichnungsdauer ist kleiner als die standardmäßigen 5 Minuten.
> - Der verfügbare Speicherplatz beträgt weniger als 20 % des gesamten Speicherplatzes.

Die vollständigen Anforderungen finden Sie in der [Dokumentation zu holografischen Fotos und Videos.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Verbesserungen und Korrekturen im Update:
- Weitere Bildschirme in OOBE befinden sich jetzt im dunklen Modus.
- Weitere Informationen zu Inhalten sollten online auf die neuesten Datenschutzbestimmungen verweisen.
- Es wurde ein Problem behoben, bei dem Benutzer keine VPN-Profile über Bereitstellungspakete bereitstellen konnten.
- Problem mit der Proxykonfiguration für die VPN-Verbindung wurde behoben.
- Die Richtlinie wurde aktualisiert, um die Aufzählung von USB-Funktionen über MDM für NCM für AllowUsbConnection zu deaktivieren.
- Es wurde ein Problem behoben, das verhinderte, dass ein HoloLens-Gerät im Datei-Explorer über das Medienübertragungsprotokoll (Media Transfer Protocol, MTP) angezeigt wurde, wenn das Gerät als [Ein-App-Kiosk eingerichtet wurde.](hololens-kiosk.md) Beachten Sie, dass MTP (und die USB-Verbindung im Allgemeinen) weiterhin mithilfe der [AllowUSBConnection-Richtlinie deaktiviert werden](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) kann.
- Es wurde ein Problem behoben, bei dem Symbole im Startmenü im Kioskmodus ordnungsgemäß skaliert wurden.
- Ein Problem wurde behoben, weil die HTTP-Zwischenspeicherung den Kioskmodus für Azure AD-Gruppen störte.
- Es wurde ein Problem behoben, bei dem Benutzer die Schaltfläche "Koppeln" nicht verwenden konnten, nachdem sie den Entwicklermodus mit Bereitstellungspaketen aktiviert hatten, es sei denn, sie deaktivierten und aktivierten den Entwicklermodus erneut.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, Version 1903 – Update vom November 2020
- Build 18362.1085

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unseren neuesten Feature release build Windows Holographic, Version 20H2, auszuprobieren.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, Version 2004 – Update vom Oktober 2020
- Build 19041.1124
 
Verbesserungen und Korrekturen im Update:

- Eine unnötige Überprüfung, die zu einem Laufzeitsystemfehler führte, wurde entfernt.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, Version 1903 – Update vom Oktober 2020
- Build 18362.1081

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, Version 2004 – Update vom September 2020
- Build 19041.1117

Verbesserungen und Korrekturen im Update:

- Behebt ein Problem, Visual Studio verhinderte, dass eine Anwendung debuggen konnte, wenn SupportsMultipleInstances="true" im appxmanifest vorhanden ist.
- Diese Version enthält eine Korrektur der NCSI-Proxyerkennung, um die fehlgeschlagene Interneterkennung über den Netzwerkproxy zu beheben. NCSI kann computerproxy und pro Profilproxy für die Erkennung von Internetverbindungen verwenden. Der Benutzerproxy wird in der zukünftigen Version von NCSI unterstützt.
- Auf den meisten Windows Mixed Reality-Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. In früheren Versionen von HoloLens 2 wurde der Vektor jedoch so ausgerichtet, dass er senkrecht zu den Anzeigepanels ausgerichtet wurde, der relativ zur idealen Ausrichtung um einige Grad nach unten gekippt wird. Neuere Versionen von HoloLens 2 haben dies korrigiert, um die semantische Konsistenz über alle Formfaktoren hinweg sicherzustellen.
- Verbesserte Robustheit der Handverfolgung, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.
- Diese Version enthält eine Korrektur zur Verbesserung der Audiozeitstempelqualität, die möglicherweise zu Problemen bei der Videoaufnahme beigetragen hat.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, Version 1903 – Update vom September 2020
- Build 18362.1079

Verbesserungen und Korrekturen im Update:

- Auf den meisten Windows Mixed Reality-Geräten ist der Vorwärtsrichtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet, die nach vorne blickt. In früheren Versionen von HoloLens 2 wurde der Vektor jedoch so ausgerichtet, dass er senkrecht zu den Anzeigepanels ausgerichtet wurde, der relativ zur idealen Ausrichtung um einige Grad nach unten gekippt wird. Neuere Versionen von HoloLens 2 haben dies korrigiert, um die semantische Konsistenz über alle Formfaktoren hinweg sicherzustellen.
- Verbesserte Robustheit der Handverfolgung, die in bestimmten Szenarien zu weniger Nachverfolgungsverlusten führt.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, Version 2004 – August 2020 Update
- Build 19041.1113

Verbesserungen und Korrekturen im Update:

- Die Einstellungs-App folgt dem Benutzer nicht mehr in iris enrollment or eye tracking calibration experiences.
- Es wurde ein Fehler behoben, bei dem das Anwenden eines Bereitstellungspakets während der OOBE, das das Gerät umnennt und andere Aktionen ausführt (z. B. das Herstellen einer Verbindung mit einem Netzwerk), die anderen Aktionen nach dem Neustart des Geräts aufgrund der Umbenennung nicht ausführen würde.
- Geändertes Farbschema der ersten Geräteeinrichtung fließt, um die visuelle Qualität zu verbessern.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, Version 1903 – August 2020 Update
- Build 18362.1074

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen. Wir empfehlen Ihnen, unsere neuesten Builds für Windows Holographic, Version 2004, auszuprobieren.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, Version 2004 – Update vom Juli 2020
- Build 19041.1109

Verbesserungen und Korrekturen im Update:

- Entwickler können jetzt zwischen dem Aktivieren oder Deaktivieren der Geräteportal erfordern eine sichere Verbindung auswählen.
- Zuverlässigkeit bei Anwendungsstarts nach Betriebssystemupdates verbessert.
- Die Standardhelligkeit des Posteingangs wurde auf 100 % geändert.
- Es wurde ein Problem mit der HTTPS-Weiterleitung für das Windows-Geräteportal auf HoloLens 2 behoben.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, Version 1903 – Update vom Juli 2020
- Build 18362.1071

Verbesserungen und Korrekturen im Update:

- Es wurde ein Problem behoben, das dazu führen konnte, dass Hologramme in Unity-Anwendungen beim Verlieren oder Zurückgewinnen der Nachverfolgung ausgeblendet wurden.
- Es wurde ein Problem behoben, das dazu führte, dass exklusive HoloLens-Apps während der Verwendung des HoloLens-Emulators mit Hardwarebeschleunigung auf bestimmten Geräten zurück zur Shell abstürzten.
- Es wurde ein Problem bezüglich der HTTPS-Weiterleitung für das Windows-Geräteportal auf HoloLens 2 behoben.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, Version 2004 – Update vom Juni 2020
- Build 19041.1106

Verbesserungen und Korrekturen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen jetzt über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben werden.
  - Im *MRC-Videoeffekt*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Immersive Headset))
  - Im *MRC-Audioeffekt*:
    - LoopbackGain (der aktuelle "App Audio Gain"-Wert auf der Seite Mixed Reality Capture im Windows Device Portal)
    - MicrophoneGain (der aktuelle "Mic Audio Gain"-Wert auf der Seite Mixed Reality Capture im Windows Device Portal)
- Behebung eines Fehlers zur Verbesserung der Audioqualität in Mixed Reality-Aufnahmeszenarien. Insbesondere sollte durch diese Korrektur bei der Anzeige **** des Startmenüs keine Audiofitchings in der Aufzeichnung mehr angezeigt werden.
- Verbesserte Hologrammstabilität in aufgezeichneten Videos.
- Es wurde ein Problem behoben, bei dem die Mixed Reality-Aufnahme kein Video aufzeichnen konnte, nachdem das Gerät mehrere Tage im Standbymodus war.
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Durch dieses Verhalten wird ein Problem vermieden, das dazu führte, dass einige Apps angehalten wurden, wenn das Visier nach oben gekippt wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert war. Die API ist jetzt für die Unity-Versionen 2018.4.18 und höher sowie 2019.3.4 und höher aktiviert.
- Wenn Sie über eine Wi-Fi auf das Geräteportal zugreifen, kann ein Webbrowser den Zugriff auf aufgrund eines ungültigen Zertifikats verhindern. Der Browser kann einen Fehler wie "ERR_SSL_PROTOCOL_ERROR" melden, auch wenn das Gerätezertifikat zuvor als vertrauenswürdig eingestuft wurde. In diesem Fall können Sie nicht zum Geräteportal überkommen, da es keine Möglichkeit gibt, Sicherheitswarnungen zu ignorieren. Mit diesem Update wurde das Problem behoben. Wenn das Gerätezertifikat zuvor heruntergeladen wurde und auf einem PC als vertrauenswürdig eingestuft wurde, um Browsersicherheitswarnungen zu entfernen, und der SSL-Fehler auftritt, muss das neue Zertifikat heruntergeladen und als vertrauenswürdig eingestuft werden, um Browsersicherheitswarnungen zu beheben.
- Ermöglicht die Erstellung eines Laufzeitbereitstellungspakets, mit dem eine App mithilfe von MSIX-Paketen installiert werden kann.
- Es wurde eine Einstellung unter **System**  >  ****  >  **hologramme** einstellungen hinzugefügt, mit der Benutzer beim Herunterfahren des Geräts automatisch alle Hologramme aus der Mixed Reality-Startseite entfernen können.
- Es wurde ein Problem behoben, durch das HoloLens-Apps, die ihr Pixelformat änderten, im HoloLens-Emulator schwarz gerendert wurden.
- Ein Fehler wurde behoben, der während der Iris-Anmeldung zu einem Absturz führte.
- Es wurde ein Problem mit wiederholten Storedownloads für bereits aktuelle Apps behoben.
- Ein Fehler wurde behoben, um zu verhindern, dass immersive Apps Microsoft Edge wiederholt öffnen.
- Es wurde ein Problem mit den Starts der Fotos-App in den ersten Startstarts nach der Aktualisierung von 1903 behoben.
- Verbesserte Leistung und Zuverlässigkeit.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, Version 1903 – Update vom Juni 2020
- Build 18362.1064

Verbesserungen und Korrekturen im Update:

- Benutzerdefinierte MRC-Aufzeichnungen verfügen über neue Standardwerte für bestimmte Eigenschaften, wenn sie nicht angegeben werden.
  - Im *MRC-Videoeffekt*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Immersive Headset))
  - Im *MRC-Audioeffekt*:
    - LoopbackGain (der aktuelle "App Audio Gain"-Wert auf der Seite Mixed Reality Capture im Windows Device Portal)
    - MicrophoneGain (der aktuelle "Mic Audio Gain"-Wert auf der Seite Mixed Reality Capture im Windows Device Portal)
- Die HolographicSpace.UserPresence-API ist in der Regel für Unity-Anwendungen deaktiviert. Durch dieses Verhalten wird ein Problem vermieden, das dazu führt, dass einige Apps angehalten werden, wenn das Visier nach oben gekippt wird, auch wenn die Einstellung für die Ausführung im Hintergrund aktiviert ist. Die API ist jetzt für die Unity-Versionen 2018.4.18 und höher sowie für 2019.3.4 und höher aktiviert.
- Es wurde ein Problem behoben, durch das HoloLens-Apps, die ihr Pixelformat änderten, im HoloLens-Emulator schwarz gerendert wurden.
- Es wurde ein Problem beim Starten der Fotos-App in ersten Startstarts nach der Aktualisierung von 1903 behoben.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, Version 2004  
- Build - 19041.1103

Das große Softwareupdate vom Mai 2020 für HoloLens 2, *Windows Holographic, Version 2004,* enthält eine Vielzahl von neuen Funktionen, z. B. Unterstützung für Windows Autopilot, dunkler App-Modus, USB-Ethernet-Unterstützung für 5G/LTE-Hotspots und vieles mehr. Um auf die neueste Version **** zu aktualisieren, öffnen Sie die App Einstellungen, wechseln Sie zu   Update & **Security,** und wählen Sie die Schaltfläche Nach **Updates**   suchen aus. 

|             Feature                              |          Beschreibung                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Vorkonfigurierung und nahtloses Einrichten neuer Geräte für die Produktion mithilfe von Windows AutoPilot                 |
|       FIDO 2-Unterstützung                             |          Unterstützung von FIDO2-Sicherheitsschlüsseln zum Aktivieren einer schnellen und sicheren Authentifizierung für freigegebene Geräte            |
|       Verbesserte Bereitstellung                      |          Nahtloses Anwenden eines Bereitstellungspakets von einem USB-Laufwerk auf Ihre HoloLens                              |
|       Anwendungsinstallationsstatus                 |          Überprüfen des Installationsstatus in der Einstellungs-App für Apps, die über MDM an HoloLens 2 geschubsert wurden               |
|       Konfigurationsdienstanbieter (Configuration Service Providers, CSPs)   |          Neue Konfigurationsdienstanbieter zur Verbesserung der Administratorsteuerungsfunktionen hinzugefügt                 |
|       USB 5G/LTE-Unterstützung                       |          Erweiterte USB-Ethernet-Funktion ermöglicht Unterstützung für 5G/LTE                                    |
|       Dunkler App-Modus                              |          Dunkler App-Modus für Apps verfügbar, die sowohl dunkle als auch helle Modi unterstützen, um die Anzeige zu verbessern        |
|       Sprachbefehle                             |          Unterstützung für zusätzliche System-Sprachbefehle zum Steuern von HoloLens freihändig                           |
|       Verbesserungen bei der Handverfolgung                 |          Verbesserungen bei der Handverfolgung machen Schaltflächen und 2D-Schieferinteraktionen präziser                        |
|       Qualitätsverbesserungen und -korrekturen                 |          Verschiedene Systemleistungs- und Zuverlässigkeitsverbesserungen auf der gesamten Plattform                            |

### <a name="support-for-windows-autopilot"></a>Unterstützung für Windows Autopilot

Mit Windows Autopilot für HoloLens 2 kann der Geräteverkaufskanal HoloLens vorab bei Ihrem Intune-Mandanten registrieren. Wenn Geräte eintreffen, sind sie bereit, sich selbst als freigegebene Geräte unter Ihrem Mandanten zu bereitstellen. Um die Vorteile der Selbstbereitstellung nutzen zu können, muss das Gerät während des ersten Bildschirms im Setup mithilfe eines USB-C-to-Ethernet eine Verbindung mit einem Netzwerk herstellen.

Nachdem ein Benutzer den Autopilot-Self-Deploying-Prozess gestartet hat, werden die folgenden Schritte abgeschlossen:

1. Verbinden des Geräts mit Azure Active Directory (Azure AD).
1. Verwenden von Azure AD, um das Gerät bei Microsoft Intune (oder einem anderen MDM-Dienst) zu registrieren.
1. Herunterladen der gerätespezifischen Richtlinien, Zertifikate und Netzwerkprofile.
1. Bereitstellen des Geräts.
1. Präsentieren des Anmeldebildschirms für den Benutzer.

Weitere Informationen finden Sie im [Evaluierungshandbuch für Windows Autopilot für HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Wenden Sie sich jetzt an Ihren Account Manager, um der AutoPilot-Vorschau beizuschließen. Autopilotbereite Geräte beginnen in Kürze mit dem Versand.*

### <a name="fido2-security-key-support"></a>Unterstützung von FIDO2-Sicherheitsschlüsseln

Einige Benutzer teilen ein HoloLens-Gerät mit anderen benutzern in einer Arbeits- oder Schulumgebung. Daher ist es wichtig, dass Benutzer problemlos lange Benutzernamen und Kennwörter eingeben müssen. Mit Fast Identity Online (FIDO) kann sich jeder in Ihrer Organisation (Azure AD-Mandant) nahtlos bei HoloLens anmelden, ohne einen Benutzernamen oder ein Kennwort einzugeben.

FIDO2-Sicherheitsschlüssel sind eine standardbasierte, auf Standards basierende, kennwortlose Authentifizierungsmethode, die in jedem Formfaktor verwendet werden kann. FIDO ist ein offener Standard für die kennwortlose Authentifizierung. Benutzer und Organisationen können sich ohne Benutzernamen oder Kennwort bei ihren Ressourcen anmelden. Stattdessen verwenden sie einen externen Sicherheitsschlüssel oder einen in ein Gerät integrierten Plattformschlüssel.

Informationen zu den ersten Schritte finden Sie unter [Aktivieren der Kennwortlosen Sicherheitsschlüssel-Anmeldung](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Verbesserte MDM-Registrierung über Bereitstellungspaket

Mithilfe von Bereitstellungspaketen können Sie die HoloLens-Konfiguration über eine Konfigurationsdatei und nicht über die out-of-box-Erfahrung von HoloLens festlegen. Zuvor mussten Bereitstellungspakete in den internen Speicher von HoloLens kopiert werden. Jetzt können sie auf einem USB-Laufwerk gespeichert werden, sodass sie auf mehreren HoloLens-Geräten leichter wiederverwendet werden können und Sie Geräte parallel bereitstellen können. Bereitstellungspakete unterstützen jetzt auch ein Feld zur Registrierung in der Geräteverwaltung, sodass nach der Bereitstellung keine manuelle Einrichtung mehr besteht.

Um dies auszuprobieren:

1. Laden Sie die neueste Version des Windows Configuration Designer aus dem Windows Store auf Ihren PC herunter.
1. Wählen **Sie Bereitstellen von HoloLens Devices**Provision  >  **HoloLens 2 devices aus.**
2. Erstellen Sie Ihr Konfigurationsprofil. Kopieren Sie dann alle Dateien, die erstellt wurden, auf ein USB-C-Speichergerät.
3. Schließen Sie das USB-C-Gerät an alle neu blinkenden HoloLens an. Drücken Sie dann die **Volume-Down-Power-Tasten,**  +  **** um Das Bereitstellungspaket anzuwenden.

### <a name="line-of-business-application-install-status"></a>Installationsstatus der Geschäftsanwendung

Die Bereitstellung und Verwaltung von MDM-Apps für Unternehmens-Apps ist für HoloLens von entscheidender Bedeutung. Administratoren und Benutzer müssen den Status der App-Installation für überwachung und Diagnose anzeigen. In dieser Version haben wir weitere Details unter **Einstellungen**Konten Zugriff auf Arbeit oder Schule  >  ****  >  ****  >  **Klicken Sie auf Ihr Konto**Info  >  **hinzugefügt.**

### <a name="additional-csps-and-policies"></a>Zusätzliche CSPs und Richtlinien

Ein [Konfigurationsdienstanbieter (Configuration Service Provider, CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) ist eine Schnittstelle zum Lesen, Festlegen, Ändern oder Löschen von Konfigurationseinstellungen auf einem Gerät. In dieser Version fügen wir Unterstützung für weitere Richtlinien hinzu, um die Kontrolle zu erhöhen, die Administratoren über bereitgestellte HoloLens-Geräte verfügen. Eine Liste der von HoloLens unterstützten CSPs finden Sie unter [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Neu in dieser Version:

**Richtlinien-Konfigurationsdienstanbieter** 

Der Richtlinienkonfigurationsdienstanbieter ermöglicht es dem Unternehmen, Richtlinien auf Windows-Geräten zu konfigurieren. In dieser Version haben wir neue Richtlinien für HoloLens hinzugefügt, die hier aufgeführt sind. Weitere Informationen finden Sie unter [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

Der NetzwerkQoSPolicy-Konfigurationsdienstanbieter erstellt QoS-Richtlinien (Network Quality-of-Service). Eine QoS-Richtlinie führt eine Reihe von Aktionen für Netzwerkverkehr basierend auf einem Satz von übereinstimmenden Bedingungen aus. Weitere Informationen finden Sie unter [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Erweiterte USB-Ethernet-Unterstützung für 5G/LTE-Tether-Geräte

Unterstützung wurde hinzugefügt, um bestimmte mobile Breitbandgeräte wie 5G/LTE-Telefone und Wi-Fi-Hotspots zu aktivieren, wenn sie per USB an holoLens 2 angeschlossen sind. Diese Geräte werden nun in den **Netzwerkeinstellungen als** eine weitere Ethernetverbindung angezeigt. (Mobile Breitbandgeräte, für die ein externer Treiber erforderlich ist, werden nicht unterstützt.) Diese Funktionalität ermöglicht Verbindungen mit hoher Bandbreite, Wi-Fi nicht verfügbar ist und Wi-Fi Nicht genügend Leistung bietet. Weitere Informationen zu unterstützten #A0 finden Sie unter [Connect to Bluetooth and USB-C devices](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Verbesserungen bei der Handverfolgung

Diese Version enthält mehrere Verbesserungen bei der Handverfolgung:

- **Zeigen der Posenstabilität:** Das System wehrt sich nun dagegen, den Zeigefinger zu verkrümmen, wenn er von der Handfläche übersäumt wird. Diese Änderung verbessert die Genauigkeit beim Drücken von Schaltflächen, Eingeben, Scrollen von Inhalten und vielem mehr! 
- **Reduzierte versehentliche Lufth taps:** Wir haben die Erkennung der Lufttippgeste verbessert. Es gibt jetzt weniger versehentliche Aktivierungen in mehreren gängigen Szenarien, z. B. wenn Sie Ihre Hände an Ihre Seiten legen.
- **Zuverlässigkeit des Benutzerwechsels:** Das System ist jetzt schneller und zuverlässiger bei der Aktualisierung der Handgröße, wenn Sie ein Gerät freigeben.
- **Reduzierter Handdiebstahl:** Wir haben die Behandlung von Fällen verbessert, in denen die Sensoren mehr als zwei Zeiger haben. Wenn mehrere Personen eng zusammenarbeiten, ist die Wahrscheinlichkeit sehr viel geringer, dass die nachverfolgte Hand vom Benutzer zur Hand einer anderen Person in der Szene "springt".
- **Systemzuverlässigkeit:** Es wurde ein Problem behoben, das dazu führte, dass die Handverfolgung nicht mehr funktionierte, wenn das Gerät unter hoher Last ist.

### <a name="dark-mode"></a>Dunkler Modus

Viele Windows-Apps unterstützen jetzt dunkle und helle Modi. HoloLens 2-Benutzer können den Standardmodus für Apps auswählen, die beides unterstützen. Nach dem Update ist der Standard-App-Modus "dunkel", aber Sie können diese Einstellung ganz einfach ändern: Navigieren Sie **zu**Einstellungen Systemfarben Wählen Sie  >  ****  >  ****  >  **Ihren Standard-App-Modus aus.** 

Diese "in-box"-Apps unterstützen den dunklen Modus: 

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

![Fenster im dunklen Modus mit Kacheln](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>System-Sprachbefehle

Sie können jetzt Sprachbefehle mit jeder Beliebigen App auf dem Gerät verwenden. Weitere Informationen finden Sie unter [Use your voice to operate HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Weitere Informationen finden [Sie unter Unterstützte Sprachen für HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Cortana-Updates

Die aktualisierte App ist in Microsoft 365 integriert, damit Sie mehr auf Ihren Geräten erledigen können (derzeit nur in US-English). In HoloLens 2 unterstützt Cortana bestimmte gerätespezifische Befehle nicht mehr, z. B. das Anpassen der Lautstärke oder den Neustart. Diese Optionen werden jetzt von den neuen System-Sprachbefehlen unterstützt. Weitere Informationen zur neuen Cortana-App finden Sie in unserem [Blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Qualitätsverbesserungen und -korrekturen

Verbesserungen und Korrekturen auch im Update:  
- Es wurde ein aktives Anzeigekalibrierungssystem eingeführt. Dieses Feature verbessert die Stabilität und Ausrichtung von Hologrammen. Sie bleiben nun erhalten, wenn Sie ihren Kopf von einer Seite zur anderen bewegen.
- Ein Fehler wurde behoben, Wi-Fi streaming to HoloLens regelmäßig unterbrochen wurde. Wenn eine Anwendung angibt, dass Streaming mit niedriger Latenz benötigt wird, implementieren Sie den Fix, indem Sie die [Funktion SetSocketMediaStreamingMode aufrufen.](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Es wurde ein Gerätehang behoben, der während des Streamings im Recherchemodus aufgetreten war.
- Ein Fehler wurde behoben, bei dem in einigen Fällen der richtige Benutzer beim Fortsetzen einer Sitzung nicht auf dem Anmeldebildschirm angezeigt wurde.
- Es wurde ein Problem behoben, bei dem Benutzer MDM-Protokolle nicht über Einstellungen **exportieren konnten.**
- Es wurde ein Problem behoben, bei dem die Genauigkeit der Augenverfolgung unmittelbar nach dem out-of-box-Setup niedriger als erwartet war.
- Es wurde ein Problem behoben, bei dem die Initialisierung oder Durchführung der Kalibrierung unter bestimmten Bedingungen durch das Eye-Tracking-Subsystem nicht möglich war.
- Es wurde ein Problem behoben, bei dem die Augenkalibrierung für einen bereits kalibrierten Benutzer aufgefordert wurde.
- Es wurde ein Problem behoben, bei dem ein Treiber während der Augenkalibrierung abstürzte.
- Es wurde ein Problem behoben, bei dem wiederholte Drücken von Netztasten zu einem Systemtimeout von 60 Sekunden und einem Shellabsturz führen konnten.
- Verbesserte Stabilität für Tiefenpuffer.
- Im **Feedbackhub wurde** eine Freigabeschaltfläche hinzugefügt, damit Benutzer feedback einfacher freigeben können.
- Ein Fehler wurde behoben, bei dem RoboRaid wan nicht ordnungsgemäß installiert wurde.

### <a name="known-issues"></a>Bekannte Probleme

- Ein Problem mit der zh-CN-Systemsprache verhindert, dass Sprachbefehle eine Mixed#A0 oder die Geräte-IP-Adresse anzeigen.
- Ein Problem erfordert, dass Sie die Cortana-App starten, nachdem Sie das Gerät gestartet haben, um die Sprachaktivierung "Hey Cortana" zu verwenden. Wenn Sie von einem 18362-Build aktualisiert wurden, wird möglicherweise auch eine zweite App-Kachel für die vorherige Version der Cortana-App angezeigt, die in Start nicht mehr **funktioniert.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, Version 1903 – Update vom Mai 2020 
- Build 18362.1061

Dieses monatliche Qualitätsupdate enthält keine nennenswerten Änderungen, da das Team wie zuvor beschrieben an der Windows Holographic Version 2004 May Update arbeitet.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, Version 1903 – April 2020 Update
- Build 18362.1059

**Dunkler Modus für unterstützte Apps** 

Viele Windows-Apps unterstützen sowohl den dunklen als auch den hellen Modus. HoloLens 2-Kunden können jetzt den Standardmodus für Apps auswählen, die beide Farbschemas unterstützen. Basierend auf Kundenfeedback legen wir den Standard-App-Modus auf "dunkel" festgelegt, aber Sie können diese Einstellung jederzeit leicht ändern: Navigieren Sie zu Einstellungen **> System > Farben,** um "Wählen Sie Ihren Standard-App-Modus" zu **finden.**

Diese "in-box"-Apps unterstützen den dunklen Modus:
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
- Sichergestellt, dass Shellüberlagerungen in Mixed Reality-Erfassungen enthalten sind.
- Unreale Entwickler können nun die Seite 3D-Ansicht im Geräteportal verwenden, um ihre Anwendungen zu testen und zu debuggen.
- Verbesserte Hologrammstabilität bei der Mixed Reality-Aufnahme, wenn der *HolographicDepthReprojectionMethod DepthReprojection-Algorithmus* verwendet wird.
- Der Fehler "WinRT IStreamSocketListener API Class not registered" für 32-Bit-ARM wurde behoben.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, Version 1903 – März 2020 Update 
- Build 18362.1056

Verbesserungen und Korrekturen im Update:

- Verbesserte Hologrammstabilität bei der Mixed Reality-Aufnahme, wenn der *HolographicDepthReprojectionMethod AutoPlanar-Algorithmus* verwendet wird.
- Stellen Sie sicher, dass das Koordinatensystem, das einem MF-Tiefenbeispiel zugeordnet ist, mit der öffentlichen Dokumentation konsistent ist.
- Verbesserte Produktivität von Entwicklern, da Kunden große Mengen an Text über das Geräteportal einfügen können.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, Version 1903 – Update vom Februar 2020 
- Build 18362.1053

Verbesserungen und Korrekturen im Update:

- Die HolographicSpace.UserPresence-API für Unity-Anwendungen wurde vorübergehend deaktiviert. Durch diese Änderung wird ein Problem vermieden, das dazu führte, dass einige Apps angehalten wurden, wenn das Visier nach oben gekippt wurde, auch wenn die Einstellung "Im Hintergrund ausführen" aktiviert war.
- Es wurde ein zufälliger HUP-Absturz behoben, der durch die Handverfolgung verursacht wurde, bei dem der Benutzer bemerkte, dass die Benutzeroberfläche einfrierte und nach einigen Sekunden wieder in die Shell zurückfing.
- Verbesserte Handverfolgung, sodass beim Pochen mit dem Zeigefinger der obere Teil dieses Fingers seltener unerwartet krümmt wird.
- Verbesserte Zuverlässigkeit der Kopfverfolgung, der räumlichen Zuordnung und anderer Laufzeiten.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, Version 1903 – Update vom Januar 2020 
- Build 18362.1043
 
Verbesserungen und Korrekturen im Update:

- Verbesserte Stabilität für exklusive Apps beim Arbeiten mit dem HoloLens 2-Emulator.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, Version 1903 – Update vom Dezember 2019 
- Build 18362.1042

Verbesserungen und Korrekturen im Update:

- Korrekturen für die letzte Phase der Vervielfältigung (Last Stage Reproduction, LSR) wurden eingeführt. Verbesserte visuelle Darstellung von Hologrammen, um stabiler und gestochen scharfer zu werden, indem ihre Tiefe genauer abrechend wird. Dieses Symptom wird nach diesem Update deutlicher, wenn Apps die Tiefe von Hologrammen nicht richtig festlegen.
- Stabilität von exklusiven Apps und Navigation zwischen exklusiven Apps behoben.
- Es wurde ein Problem behoben, bei dem die Mixed Reality-Aufnahme kein Video aufzeichnen konnte, nachdem das Gerät mehrere Tage im Standbymodus war.
- Verbesserte Hologrammstabilität.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, Version 1903 – Update vom November 2019 
- Build 18362.1039

Verbesserungen und Korrekturen im Update:

- Die Funktionalität **** der Select-Sprachbefehle wurde während der Ersteinrichtung für en-CA und en-AU behoben.
- Verbesserte visuelle Qualität von Objekten, die in den neuesten Versionen des Unity and Mixed Reality Toolkit (MRTK) weit entfernt platziert wurden.
- Behebung von Problemen mit holografischen Anwendungen, die beim Start angehalten wurden, bis das Startmenü geöffnet und dann geschlossen wurde.
- OpenXR-Laufzeitkonformitätskorrekturen und Verbesserungen für HoloLens 2 und den Emulator.
