---
title: Veröffentlichungshinweise für HoloLens 2
description: Informieren Sie sich über Updates in jeder neuen Version von HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/10/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: df8d6e2c00bd8ff8507be4a2fd58c773d8833c11
ms.sourcegitcommit: 20ff249e3570c74f62cdf6339c8be76c401d9f4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "11165973"
---
# Veröffentlichungshinweise für HoloLens 2

Um sicherzustellen, dass Sie mit ihren HoloLens-Geräten eine produktive Erfahrung haben, veröffentlichen wir weiterhin Funktions-, Fehler-und Sicherheitsupdates. Auf dieser Seite können Sie jeden Monat sehen, was es Neues für HoloLens gibt. Um das neueste HoloLens 2-Update zu erhalten, können Sie entweder [nach Updates suchen und](hololens-update-hololens.md#check-for-updates-and-manually-update) das vollständige Flash-Update (FFU) manuell aktualisieren, um [Ihr Gerät über Advanced Recovery Companion zu blinken](hololens-recovery.md#clean-reflash-the-device), [hier herunterladen](https://aka.ms/hololens2download). Der Download wird auf dem neuesten Stand gehalten und bietet das neueste allgemein verfügbare Build.

>[!NOTE]
> Wenn Sie HoloLens-Emulator-Versionshinweise lesen möchten, [besuchen Sie das Archiv](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows holographisch, Version 20H2
- Build 19041,1128

Windows holographisch, Version 20H2 ist jetzt verfügbar und bietet einen tollen Satz neuer Funktionen für HoloLens 2-Benutzer und IT-Experten. Von der automatischen Augen Positionierung über den Zertifikat-Manager in den Einstellungen, um die Funktionalität des Kiosk Modus zu verbessern und um neue Autopilot-Setup Funktionen zu nutzen. Dieses neue Update ermöglicht es Teams, eine genauere Kontrolle über die Konfiguration und Verwaltung von HoloLens-Geräten zu erhalten, und bietet Benutzern noch nahtlosere holographische Erfahrungen. 

Diese neueste Version ist ein monatliches Update auf Version 2004, aber dieses Mal sind wir mit neuen Features ausgestattet. Die Haupt Buildnummer bleibt unverändert, und Windows Update zeigt eine monatliche Version von Version 2004 (Build 19041) an. Sie können Ihre Buildnummer in Ihren Einstellungen > Bildschirm überprüfen, um zu bestätigen, dass Sie sich auf dem neuesten verfügbaren Build 19041.1128 + befinden. Wenn Sie auf die neueste Version aktualisieren möchten, öffnen Sie die Einstellungs-APP, wechseln Sie zu Update & Security, und tippen Sie auf auf Updates überprüfen. Weitere Informationen zum Verwalten von HoloLens-Updates finden Sie auf [dieser Seite](https://docs.microsoft.com/hololens/hololens-updates).

### Neuerungen in Windows holographisch, Version 20H2  

| Feature                                              | Beschreibung                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Automatische Unterstützung der Augenposition](hololens-release-notes.md#auto-eye-position-support) | Berechnet aktive Augen Positionen, ohne dass die Benutzer die Kalibrierung der Augen Verfolgung durchlaufen.   |
| [Zertifikat-Manager](hololens-release-notes.md#certificate-manager)   | Ermöglicht neue einfachere Methoden zum Installieren und Entfernen von Zertifikaten aus der Einstellungs-APP.     |
| [Automatisches Starten der Bereitstellung über USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Bereitstellungspakete auf USB-Laufwerken fordern die Bereitstellungsseite in OOBE automatisch an.                                                         |
| [Automatisches bestätigen von Bereitstellungspaketen in Oobe](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Bereitstellungspakete werden während OOBE automatisch von der Bereitstellungsseite übernommen.                                                         |
| [Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Kombinieren Sie den automatischen Start der Bereitstellung und die automatische Bestätigung zusammen. |
| [Verwenden von Autopilot mit Wi-Fi-Verbindung](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Verwenden Sie Autopilot von Device Wi-Fi ohne Ethernet-Adapter. |
| [Tenantlockdown-CSP und Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Nachdem die mandantenregistrierung und die Richtlinie angewendet wurden, kann das Gerät immer nur für diesen Mandanten registriert werden, wenn das Gerät zurückgesetzt oder erneut geflasht wird. |
| [Global zugewiesener Zugriff](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Neue Konfigurationsmethode für den Multi-App-Kioskmodus, der den Kiosk auf Systemebene anwendet, wodurch er für alle anwendbar ist.                  |
| [Automatisches Starten einer APP im Multi-App-Kiosk](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Legt fest, dass eine Anwendung beim Anmelden bei einem Kioskmodus mit mehreren Apps automatisch gestartet wird.                                                        |
| [Verhaltensänderungen im Kiosk Modus zur Behandlung von Fehlern](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Der Fehler im Kiosk Modus hat nun einschränkende Fallbacks.                                                                                                |
| [HoloLens-Richtlinien](hololens-release-notes.md#hololens-policies)                                    | Neue Richtlinien für HoloLens.     |
| [Cache-Aad-Gruppenmitgliedschaft für Offline-Kiosk](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | Mit der neuen Richtlinie können Benutzer den Gruppen Mitgliedschafts Cache verwenden, um den Kiosk Modus für eine bestimmte Anzahl von Tagen offline zu verwenden.                                        |
| [Neue Richtlinien für Geräteeinschränkungen für HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Für HoloLens 2 aktivierte Geräteverwaltungsrichtlinien neu aktiviert.                                                                                |
| [Neue Energierichtlinien für HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Neu unterstützte Richtlinien für Energie Timeouteinstellungen.  |
| [Update Richtlinien](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Neu aktivierte Richtlinien, die die Steuerung von Updates ermöglichen.           |
| [Sichtbarkeits Seite für aktivierte Einstellungen für HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Richtlinie, um auszuwählen, welche Seiten in der Einstellungs-APP angezeigt werden.             |
| [Recherche Modus](hololens-release-notes.md#research-mode) | Verwenden des Recherche Modus auf HoloLens 2. |
| [Aufnahmedauer erhöht](hololens-release-notes.md#recording-length-increased) | MRC-Aufnahmen sind nicht mehr auf 5 Minuten begrenzt. |
| [Verbesserungen und Korrekturen im Update](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Weitere Korrekturen im Update.   |

### Automatische Unterstützung der Augenposition

Bei HoloLens 2 ermöglichen die Augenpositionen eine genaue Hologramm-Positionierung, ein komfortables Seherlebnis und eine verbesserte Anzeigequalität. Augen Positionen werden intern als Teil der Eye Tracking-Berechnung berechnet. Dies erfordert allerdings, dass jeder Benutzer die Kalibrierung der Eye-Tracking-Anwendung durchlaufen muss, selbst wenn die Erfahrung möglicherweise keine Augenblicke benötigt.

**Auto Eye Position (AEP)** ermöglicht diese Szenarien mit einer interaktionsfreien Methode zur Berechnung der Augenpositionen für Benutzer. Auto Eye Position beginnt automatisch im Hintergrund zu arbeiten, sobald Benutzer das Gerät anlegen. Wenn der Benutzer nicht über eine vorherige Kalibrierung der Augen verfügt, beginnt die automatische augenposition mit der Bereitstellung der Augen Positionen des Benutzers nach einer Verarbeitungszeit von 20-30 Sekunden für das Anzeigesystem. Die Benutzerdaten werden nicht auf dem Gerät beibehalten. Deshalb wird dieser Vorgang wiederholt, wenn das Gerät wieder eingesetzt, neu gestartet oder aus dem Ruhezustand reaktiviert wird.

Änderungen des Systemverhaltens mit der Funktion Auto Eye Position, wenn ein unkalibrierter Benutzer das Gerät anlegt. In diesem Zusammenhang bezieht sich ein nicht kalibrierter Benutzer auf eine Person, die den Kalibrierungsprozess der Augen Verfolgung auf dem Gerät zuvor nicht durchlaufen hat.

| Aktive Anwendung | Vorheriges Verhalten | Verhalten von Windows holographisch, Version 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App oder Holographic Shell ohne Blickkontakt |Das Dialogfeld zur Kalibrierung der Augen Verfolgung wird angezeigt. | Es wird keine Aufforderung angezeigt. |
| App mit Blickeingabe | Das Dialogfeld zur Kalibrierung der Augen Verfolgung wird angezeigt. | Die Eingabeaufforderung zur Kalibrierung der Augen wird nur angezeigt, wenn die Anwendung auf Eye-Gaze-Datenstrom zugreift. |

Wenn Benutzer von einer Anwendung ohne Blickeingabe zu einer Anwendung wechseln, die auf Blickdaten zugreift, wird die Kalibrierungsaufforderung angezeigt. 

Alle anderen Systemverhalten sind ähnlich, wenn der aktuelle Benutzer nicht über eine aktive Eye Tracking-Kalibrierung verfügt. Beispielsweise wird die einhändige anfangs Geste nicht aktiviert. Bei der Ersteinrichtung wird es keine Änderung an der Out-of-Box-Erfahrung geben.

Für Erfahrungen, bei denen Augenblick Daten oder eine sehr präzise Hologramm-Positionierung erforderlich sind, empfehlen wir unkalibrierten Benutzern, die Augen Tracking-Kalibrierung durchzuführen. Sie können über die Eingabeaufforderung zur Augen Verfolgung oder durch Starten der Einstellungs-APP aus dem Startmenü aufgerufen werden, und wählen Sie dann **System > Kalibrierung > Augen Kalibrierung**aus, > die Augen Kalibrierung auszuführen.

Diese Informationen sind später mit [anderen Kalibrierinformationen](hololens-calibration.md#auto-eye-position-support)zu finden. 

### Zertifikat-Manager

- Verbesserte Überwachungs-, Diagnose-und Validierungstools für Gerätesicherheit und-Compliance durch den neuen Zertifikat-Manager. Mit dieser Funktion können Sie Ihre Zertifikate in kommerzieller Umgebung bereitstellen, beheben und überprüfen.

In der Windows holographischen Version 20H2 fügen wir in der HoloLens 2-Einstellungs-APP einen Zertifikat-Manager hinzu. Wechseln Sie zu **Einstellungen > Update & Security >-Zertifikate**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit, Zertifikate auf Ihrem Gerät anzuzeigen, zu installieren und zu entfernen. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer nun über verbesserte Überwachungs-, Diagnose-und Validierungstools, um sicherzustellen, dass die Geräte sicher und kompatibel sind. 

-   **Überwachung:** Fähigkeit, zu überprüfen, ob ein Zertifikat richtig bereitgestellt wurde, oder zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, können Sie überprüfen, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit sparen und bei der Problembehandlung helfen. 
-   **Validierung:** Wenn Sie überprüfen, ob ein Zertifikat den beabsichtigten Zweck erfüllt und funktionell ist, können Sie vor allem in kommerziellen Umgebungen beträchtliche Zeit sparen, bevor Sie Zertifikate im größeren Maßstab bereitstellen.

Um schnell ein bestimmtes Zertifikat in der Liste zu finden, gibt es Optionen zum Sortieren nach Name, Store oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Wenn Sie einzelne Zertifikateigenschaften anzeigen möchten, wählen Sie das Zertifikat aus, und klicken Sie auf **Info**. 

Die Zertifikatinstallation unterstützt derzeit CER-und CRT-Dateien. Gerätebesitzer können Zertifikate auf dem lokalen Computer und dem aktuellen Benutzer installieren.  alle anderen Benutzer können nur in den aktuellen Benutzer installieren. Benutzer können nur Zertifikate entfernen, die direkt von der UI für Einstellungen installiert wurden. Wenn ein Zertifikat auf andere Weise installiert wurde, muss es auch vom gleichen Mechanismus entfernt werden.

#### So installieren Sie ein Zertifikat: 

1.  Verbinden Sie Ihr HoloLens 2 mit einem PC.
1.  Legen Sie die Zertifikatdatei, die Sie installieren möchten, an einem Speicherort auf Ihrem HoloLens 2 ab.
1.  Navigieren Sie zu **Einstellungen-app > aktualisieren Sie & Security >-Zertifikate**, und wählen Sie Zertifikat installieren aus.
1.  Klicken Sie auf **Datei importieren** , und navigieren Sie zu dem Speicherort, an dem Sie das Zertifikat gespeichert haben.
1.  Wählen Sie **Store Location**aus.
1.  Wählen Sie **Zertifikatspeicher**aus.
1.  Klicken Sie auf **Installieren**.

Das Zertifikat sollte nun auf dem Gerät installiert sein.

#### So entfernen Sie ein Zertifikat: 
1. Navigieren Sie zu **Einstellungen-app > Update-und Sicherheits > Zertifikate**.
1. Suchen Sie im Suchfeld nach dem Namen des Zertifikats.
1. Wählen Sie das Zertifikat aus.
1. Klicken Sie auf **Entfernen** .
1. Wählen Sie **Ja** aus, wenn Sie zur Bestätigung aufgefordert werden.

![Zertifikatanzeige in der Einstellungs-APP](images/certificate-viewer-device.jpg)

![Abbildung der Verwendung der Zertifikat-UI zum Installieren eines Zertifikats](images/certificate-device-install.jpg)

Diese Informationen finden Sie später [auf einer neuen Seite des Zertifikats-Managers](certificate-manager.md).

### Automatisches Starten der Bereitstellung über USB

- Automatisierte Prozesse ermöglichen eine geringere Benutzerinteraktion, wenn USB-Laufwerke mit Bereitstellungspaketen während OOBE verwendet werden.

Vor dieser Version mussten die Benutzer den Bereitstellungs Bildschirm während der OOBE manuell starten, um die Bereitstellung mithilfe einer Tastenkombination durchführen zu können. Jetzt können Benutzer die Tastenkombination überspringen, indem Sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Anschließen des USB-Laufwerks mit dem Bereitstellungspaket während des ersten interagierenden Moments von Oobe
1. Wenn das Gerät bereitgestellt wird, wird die Eingabeaufforderung automatisch mit der Bereitstellungsseite geöffnet. 

Hinweis: Wenn ein USB-Laufwerk angeschlossen ist, während das Gerät bootet, listet OOBE vorhandenes USB-Speichergerät auf und überwacht, ob weitere angeschlossen sind.

Weitere Informationen zum Anwenden von Bereitstellungspaketen während OOBE finden Sie [hier](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

Diese Informationen finden Sie später [hier.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### Automatisches bestätigen von Bereitstellungspaketen in Oobe
- Automatisierter Prozess, der eine geringere Benutzerinteraktion ermöglicht, wenn die Seite Bereitstellungspaket angezeigt wird, werden automatisch alle aufgelisteten Pakete übernommen.

Wenn der Hauptbildschirm Bereitstellung angezeigt wird, zählt OOBE 10 Sekunden, bevor automatisch alle Bereitstellungspakete angewendet werden. Benutzer können nach der Überprüfung der erwarteten Pakete innerhalb dieser 10 Sekunden weiterhin bestätigen oder stornieren.

Diese Informationen finden Sie später [hier.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche
- Kombinierte automatische Prozesse für reduzierte Geräte Interaktionen für die Bereitstellung. 

Durch die Kombination des automatischen Starts der Bereitstellung von USB-Geräten und der automatischen Bestätigung von Bereitstellungspaketen kann ein Benutzer HoloLens 2-Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts zu verwenden oder das Gerät sogar zu tragen. Sie können weiterhin dasselbe USB-Laufwerk und Bereitstellungspaket für mehrere Geräte verwenden. Dies ist hilfreich, wenn Sie mehrere Geräte gleichzeitig im gleichen Bereich bereitstellen. 

1. [Erstellen eines Bereitstellungspakets](hololens-provisioning.md) mit dem [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flashen Sie Ihre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) bis [19041,1361 oder neuere Version](https://aka.ms/hololens2previewdownload). 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken Ihres Geräts beendet hat, ziehen Sie das USB-C-Kabel ab. 
1. Schließen Sie das USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2-Gerät in OOBE bootet, wird das Bereitstellungspaket auf dem USB-Laufwerk automatisch erkannt und die Bereitstellungsseite gestartet.
1. Nach 10 Sekunden wendet das Gerät automatisch das Bereitstellungspaket an. 

Ihr Gerät ist jetzt konfiguriert, und der Bildschirm Bereitstellung erfolgreich wird angezeigt.

Diese Informationen finden Sie später [hier.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Verwenden von Autopilot mit Wi-Fi-Verbindung
- Der Bedarf an USB-C-Adaptern für Ethernet, die Hardwareanforderungen reduzieren, wurde entfernt, da Autopilot auf Wi-Fi verbundenen Geräten funktioniert.

Wenn Sie jetzt während OOBE eine Verbindung zwischen HoloLens 2 und WLAN herstellen, überprüft OOBE, ob das Gerät ein Autopilot-Profil hat. Wenn einer gefunden wird, wird er verwendet, um den restlichen Teil des Aad-Joins und-Registrierungs Flusses abzuschließen. Mit anderen Worten: die Verwendung von Ethernet zu USB-c oder Wi-Fi zu USB-c-Adapter ist nicht mehr erforderlich, Sie funktionieren jedoch weiterhin, wenn Sie am Anfang von OOBE bereitgestellt werden. Weitere Informationen zu [Autopilot für HoloLens 2-Geräte](hololens2-autopilot.md).

### Tenantlockdown-CSP und Autopilot
- Hält Geräte auf dem Mandanten des Unternehmens, indem Sie diese auch über das Zurücksetzen oder wieder Blitzen des Geräts an den Mandanten sperren. Mit weiterer Sicherheit, indem Sie die Kontoerstellung über die Bereitstellung nicht zulassen. 

HoloLens 2-Geräte unterstützen jetzt TenantLockdown CSP ab [Windows holographischer Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP ermöglicht es HoloLens 2, nur mit Autopilot an die MDM-Registrierung gebunden zu sein. Sobald der RequireNetworkInOOBE-Knoten des TenantLockdown-CSP auf "true" oder "false" (anfänglich festgelegt) auf HoloLens 2 festgelegt ist, verbleibt dieser Wert trotz erneuter blinken, Betriebssystemupdates usw. auf dem Gerät. 

Sobald der TenantLockdown-Kryptografiedienstanbieter-RequireNetworkInOOBE-Knoten auf HoloLens 2 auf true festgelegt ist, wartet OOBE auf unbestimmte Zeit, bis das Autopilot-Profil nach der Netzwerkkonnektivität erfolgreich heruntergeladen und angewendet wurde. 

Sobald der TenantLockdown-Kryptografiedienstanbieter-RequireNetworkInOOBE-Knoten auf HoloLens 2 auf true festgelegt ist, werden die folgenden Vorgänge in OOBE nicht zugelassen: 
- Erstellen eines lokalen Benutzers mithilfe der Laufzeitbereitstellung 
- Durchführen einer Aad-Join-Operation über die Bereitstellung von Laufzeiten 
- Auswählen des Besitzers des Geräts in der OOBE-Benutzeroberfläche 

#### Wie kann ich diese Verwendung von InTune einrichten? 
1. Erstellen Sie ein benutzerdefiniertes Konfigurationsprofil für ein Oma-URI-Gerät, und geben Sie true für den RequireNetworkInOOBE-Knoten an.
Oma-URI-Wert sollte./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Festlegen der Tennant-Sperrung über OMA-URI](images/hololens-tenant-lockdown.png)

1. Erstellen Sie eine Gruppe, und weisen Sie das Geräte Konfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Geräte Mitglied der im vorherigen Schritt erstellten Gruppe, und lösen Sie die Synchronisierung aus.  

Überprüfen Sie im InTune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf dem HoloLens 2-Gerät angewendet wurde, sind die Effekte von TenantLockdown aktiv.

#### Wie kann ich TenantLockdown-RequireNetworkInOOBE auf HoloLens 2 mithilfe von InTune löschen? 
1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde. 

1. Erstellen Sie ein benutzerdefiniertes Oma-URI-basiertes Geräte Konfigurationsprofil, und geben Sie für RequireNetworkInOOBE false an, wie unten dargestellt. Oma-URI-Wert sollte./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot: Festlegen von RequireNetworkInOOBE auf "false" über OMA-URI in InTune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe, und weisen Sie das Geräte Konfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Geräte Mitglied der im vorherigen Schritt erstellten Gruppe, und lösen Sie die Synchronisierung aus.

Überprüfen Sie im InTune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf dem HoloLens 2-Gerät angewendet wurde, sind die Effekte von TenantLockdown inaktiv. 

#### Was passiert während OOBE, wenn das Autopilot-Profil auf einem HoloLens nicht zugewiesen wurde, nachdem TenantLockdown auf "true" festgelegt wurde? 
OOBE wartet unbegrenzt auf das Autopilot-Profil, um es herunterzuladen, und das folgende Dialogfeld wird angezeigt. Um die Effekte von TenantLockdown zu entfernen, muss das Gerät zunächst nur mit Autopilot für seinen ursprünglichen Mandanten registriert werden, und RequireNetworkInOOBE muss wie in vorheriger Schritt beschrieben nicht festgelegt werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden. 

![In-Device-Ansicht für wenn Richtlinie auf dem Gerät erzwungen wird.](images/hololens-autopilot-lockdown.png)

Diese Informationen sind nun neben dem restlichen Autopilot unter [Tenantlockdown CSP und Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)zu finden.

### Global zugewiesener Zugriff – Kiosk Modus
- Reduzierte Identitätsverwaltung für Kiosk durch Aktivieren der neuen Kiosk Methode, die den Kioskmodus auf Systemebene anwendet.

Diese neue Funktion ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Multi-App-Kioskmodus zu konfigurieren, das auf Systemebene anwendbar ist, keine Affinität zu einer beliebigen Identität im System hat und für alle Personen gilt, die sich beim Gerät anmelden. Informieren Sie sich [hier](hololens-global-assigned-access-kiosk.md)ausführlich über dieses neue Feature.

### Automatischer Start einer Anwendung im Kioskmodus mit mehreren apps 
- Mit der automatischen App-Einführung wird die Benutzeroberfläche und die APP-Auswahl für die Erfahrungen im Kiosk Modus weiter verbessert.

Gilt nur für den Kioskmodus mit mehreren apps, und nur 1 App kann mithilfe des hervorgehobenen Attributs unten in zugewiesener Zugriffskonfiguration automatisch gestartet werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Verhaltensänderungen im Kiosk Modus zur Behandlung von Fehlern
- Sicherer Kioskmodus durch Eliminierung verfügbarer apps im Kioskmodus-Fehler. 

Zu einem früheren Zeitpunkt, zu dem Fehler bei der Anwendung des Kioskmodus aufgetreten sind, wurden im Startmenü alle Anwendungen HoloLens angezeigt. Jetzt in Windows holographische Version 20H2 im Fall von Fehlern werden keine apps im Startmenü wie folgt angezeigt: 

![Abbildung dessen, was der Kiosk Modus jetzt sieht, wenn er fehlschlägt.](images/hololens-kiosk-failure-behavior.png )

### HoloLens-Richtlinien
- Geräte Verwaltungsoptionen speziell für HoloLens, die für die Verwaltung des Geräts erstellt wurden. 

Neue Mixed-Reality-Richtlinien wurden für HoloLens 2-Geräte unter Windows holographischer Version 20H2 erstellt. Zu den neuen steuerbaren Einstellungen gehören: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed-Reality-Aufnahmen, festlegen, wann die Diagnose erfasst werden kann, und Aad-Gruppenmitgliedschaft Zwischenspeicher.  

| Neue HoloLens-Richtlinie                                | Beschreibung                                                                               | Anmerkungen                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Ermöglicht die Deaktivierung der Helligkeits Schaltflächen, damit die Helligkeit nicht geändert wird.       | 1 ja, 0 Nein (Standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Ermöglicht das Deaktivieren von Lautstärketasten, damit die Lautstärke nicht geändert wird.               | 1 ja, 0 Nein (Standard)                                                |
| MixedReality\MicrophoneDisabled                    | Deaktiviert das Mikrofon, damit auf HoloLens 2 keine Audioaufnahme möglich ist.                      | 1 ja, 0 Nein (Standard)                                                |
| MixedReality\FallbackDiagnostics                   | Steuert das Verhalten, wenn Diagnoseprotokolle erfasst werden können.                               | 0 deaktiviert, 1 für Gerätebesitzer aktiviert, 2 für alle aktiviert (Standard) |
| MixedReality\HeadTrackingMode                      | Für die spätere Verwendung reserviert.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Steuert, wie viele Tage der Aad-Gruppen Mitgliedschafts Cache für Kiosk-Targeting-Aad-Gruppen verwendet wird. | Siehe unten.                                                           |

### Cache-Aad-Gruppenmitgliedschaft für Offline-Kiosk
- Ermöglicht das Verwenden von Offline-Kiosken für Aad-Gruppen für bis zu 60 Tage.

Diese Richtlinie steuert, wie viele Tage der Aad-Gruppen Mitgliedschafts Cache für zugewiesene Zugriffs Konfigurationen verwendet werden kann, die für Aad-Gruppen für signierten Benutzer vorgesehen sind. Sobald dieser Richtlinienwert auf den Wert größer als 0 gesetzt ist, wird der Cache andernfalls verwendet.  

Name: AADGroupMembershipCacheValidityInDays URI-Wert:./Vendor/MSFT/Policy/config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 Tage  
Max-60 Tage 

Schritte zur korrekten Verwendung dieser Richtlinie: 
1. Erstellen Sie ein Device-Konfigurationsprofil für Kiosk-Targeting-Aad-Gruppen, und weisen Sie es HoloLens-Geräten zu. 
1. Erstellen Sie eine benutzerdefinierte Oma-URI-basierte Gerätekonfiguration, die diesen Richtlinienwert auf die gewünschte Anzahl von Tagen (> 0) festlegt und HoloLens-Device (s) zuweist. 
    1. Der URI-Wert sollte in Oma-URI-Textfeld als./Vendor/MSFT/Policy/config/MixedReality/AADGroupMembershipCacheValidityInDays eingegeben werden.
    1. Der Wert kann zwischen min/max zulässig sein.
1. Registrieren Sie HoloLens-Geräte, und überprüfen Sie, ob beide Konfigurationen auf das Gerät angewendet werden. 
1. Lassen Sie Aad Benutzer 1 anmelden, wenn Internet verfügbar ist, sobald die Benutzeranmeldung und die Aad-Gruppenmitgliedschaft erfolgreich bestätigt wurde, wird der Cache erstellt. 
1. Jetzt kann Aad User 1 HoloLens offline schalten und für den Kioskmodus verwenden, solange der Richtlinienwert X Anzahl von Tagen zulässt. 
1. Die Schritte 4 und 5 können für jeden anderen Aad-Benutzer N. entscheidend ist hier, dass sich jeder Aad-Benutzer bei einem Gerät mit Internet anmelden muss, damit mindestens einmal festgestellt werden kann, dass Sie Mitglied der Aad-Gruppe sind, auf die die Kiosk Konfiguration ausgerichtet ist. 
 
> [!NOTE]
> Bis zum Ausführen von Schritt 4 für einen Aad-Benutzer tritt ein Fehler Verhalten auf, das in "getrennte" Umgebungen erwähnt wird. 

### Neue Richtlinien für Geräteeinschränkungen für HoloLens 2
- Ermöglicht Benutzern das Verwalten bestimmter Geräteverwaltungsrichtlinien, beispielsweise das Blockieren des Hinzufügens oder Entfernens von Bereitstellungspaketen.

Neu aktivierte Richtlinien, die weitere Verwaltungsoptionen von HoloLens 2-Geräten ermöglichen. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Diese zwei neuen Policen für AllowAddProvisioningPackage und AllowRemoveProvisioningPackage werden unseren [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)hinzugefügt.

### Neue Energierichtlinien für HoloLens 2
- Weitere Optionen für den Fall, dass HoloLens über Energierichtlinien schläft oder sperrt. 

Diese neu hinzugefügten Richtlinien ermöglichen Administratoren, Energiezustände wie Leerlauftimeout zu steuern. Wenn Sie mehr über die einzelnen Richtlinien erfahren möchten, klicken Sie auf den Link für diese Richtlinie.

|     Link zur Richtlinien Dokumentation                |     Anmerkungen                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Beispielwert für die Verwendung im Windows-Konfigurations-Designer, also 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Beispielwert für die Verwendung im Windows-Konfigurations-Designer, also 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Diese zwei neuen Policen für DisplayOffTimeoutOnBattery und DisplayOffTimeoutPluggedIn werden unseren [allgemeinen Geräteeinschränkungen](hololens-common-device-restrictions.md)hinzugefügt.

> [!NOTE]
> Um eine konsistente Nutzung von HoloLens 2 zu gewährleisten, stellen Sie bitte sicher, dass die Werte für DisplayOffTimeoutOnBattery und StandbyTimeoutOnBattery mit dem gleichen Wert festgesetzt werden. Das gleiche gilt für DisplayOffTimeoutPluggedIn und StandbyTimeoutPluggedIn. Weitere Informationen zum modernen Standby finden Sie unter [Leerlaufzeiten für Anzeige, Ruhezustand und Ruhezustand](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### Neu aktivierte Update Richtlinien für HoloLens
- Weitere Optionen für die Installation von Updates oder Deaktivieren der Schaltfläche "Updates anhalten", um Updates zu gewährleisten.

Diese Update Richtlinien sind jetzt auf HoloLens 2-Geräten aktiviert:
-   [Update-ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update-ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update-ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update-SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Ausführliche Informationen zu diesen Update Richtlinien und deren Verwendung für HoloLens-Geräte finden Sie hier unter [Verwalten von HoloLens-Updates](hololens-updates.md).

### Sichtbarkeits Seite für aktivierte Einstellungen für HoloLens 2
- Erweitertes UI-Steuerelement in der Einstellungs-APP, das möglicherweise verwirrt ist, um eine begrenzte Auswahl von Seiten anzuzeigen.

Wir haben jetzt eine Richtlinie aktiviert, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der System Einstellungen-App sichtbar oder barrierefrei sind, oder dies für alle Seiten mit Ausnahme der angegebenen Aktionen. Klicken Sie auf den Link unten, um zu erfahren, wie Sie diese Funktion vollständig anpassen können.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Informationen zu den Seiteneinstellungen, die Sie auf HoloLens 2 anpassen können, finden Sie auf unserer Seite mit den [Einstellungen-URIs](settings-uri-list.md). 
 
![Screenshot der Nutzungszeit, die in der Einstellungs-App geändert werden](images/hololens-page-visibility-list.jpg)

### Recherche Modus
Im forschungsmodus wird das HoloLens 2 zu einem potenten Tool für die Computer Vision-Forschung. Im Vergleich zu früheren Versionen bietet der Recherche Modus für HoloLens 2 die folgenden Vorteile:
-   Neben Sensoren, die im HoloLens (1st Gen)-Recherche Modus verfügbar gemacht werden, bieten wir jetzt den IMU-Sensorzugriff einschließlich eines Beschleunigungsmessers, Kreisels und Magnetometer.
-   HoloLens 2 bietet neue Funktionen, die zusammen mit dem Recherche Modus verwendet werden können. Insbesondere Zugriff auf artikulierte Hand-Tracking-und Eye-Tracking-APIs, die eine umfangreichere Reihe von Experimenten bereitstellen können.

Forscher haben nun die Möglichkeit, den forschungsmodus auf Ihren HoloLens-Geräten zu aktivieren, um auf alle diese externen, unformatierten Bildsensor Ströme zuzugreifen. Der Recherche Modus für HoloLens 2 bietet ebenfalls Zugriff auf die Beschleunigungsmesser-, Kreisel-und Magnetometer-Werte. Um die Privatsphäre der Nutzer zu schützen, sind unformatierte Augen Tracking-Kamera Bilder im Recherche Modus nicht verfügbar, aber Blick Richtung ist über vorhandene APIs verfügbar.

Weitere technische Details finden Sie in der [Dokumentation zum Recherche Modus](https://docs.microsoft.com/windows/mixed-reality/research-mode) .

### Aufnahmedauer erhöht
Aufgrund des Kundenfeedbacks haben wir die Aufnahmedauer von [Mixed-Reality-Aufnahmen](holographic-photos-and-videos.md)erhöht. Mixed-Reality-Aufnahmen sind standardmäßig nicht mehr auf 5 Minuten limitiert, sondern berechnen die maximale Aufnahmedauer basierend auf dem verfügbaren Speicherplatz. Das Gerät schätzt die maximale Videoaufnahmedauer basierend auf dem verfügbaren Speicherplatz bis zu 80% des gesamten Speicherplatzes.

> [!NOTE]
> Die HoloLens verwendet die standardmäßige Videoaufnahme Länge (5 Minuten), wenn eine der folgenden Vorgehensweise Eintritt:
> - Die geschätzte maximale Aufnahmedauer ist kleiner als die standardmäßigen 5 Minuten.
> - Der verfügbare Speicherplatz beträgt weniger als 20% des gesamten Speicherplatzes.

Diese Informationen finden Sie [hier](holographic-photos-and-videos.md#maximum-recording-length). 

### Verbesserungen und Korrekturen im Update:
- Weitere Bildschirme in OOBE sind jetzt im dunklen Modus.
- Weitere Informationen sollten auf die neueste Datenschutzerklärung Online verweisen.
- Ein Problem wurde behoben, bei dem Benutzer VPN-Profile nicht über Bereitstellungspakete bereitstellen konnten.
- Problem bei der Proxykonfiguration für die VPN-Verbindung behoben.
- Aktualisierte Richtlinie zum Deaktivieren der Enumeration von USB-Funktionen über MDM für NCM für AllowUsbConnection.
- Ein Problem wurde behoben, das verhinderte, dass ein HoloLens-Gerät im Datei-Explorer über das Media Transfer Protocol (MTP) angezeigt wird, wenn das Gerät als [Single-App-Kiosk](hololens-kiosk.md)eingerichtet wurde. Beachten Sie, dass MTP (und eine USB-Verbindung im allgemeinen) weiterhin mithilfe der [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) -Richtlinie deaktiviert werden können.
- Ein Problem wurde behoben, bei dem Symbole im Startmenü im Kiosk Modus richtig skaliert wurden.
- Ein Problem wurde behoben, aufgrund des http-Cachings, das den Kioskmodus für Aad-Gruppen gezielt stört.
- Ein Problem wurde behoben, bei dem Benutzer die Schaltfläche "paar" nicht verwenden konnten, nachdem Sie den Entwicklermodus mit Bereitstellungspaketen aktiviert haben, es sei denn, Sie haben den Entwicklermodus deaktiviert und wieder aktiviert.

## Windows holographisch, Version 1903 – Update vom November 2020
- Build 18362,1085

Dieses monatliche Qualitäts Update enthält keine nennenswerten Änderungen, wir empfehlen Ihnen, unser neuestes Feature Release Build Windows holographische Version 20H2 zu testen.

## Windows holographisch, Version 2004 – Update vom Oktober 2020
- Build 19041,1124
 
Verbesserungen und Korrekturen im Update:

- Eine unnötige Überprüfung wurde entfernt, die einen Laufzeitsystem Fehler verursacht hat.

## Windows holographisch, Version 1903 – Update vom Oktober 2020
- Build 18362,1081

Dieses monatliche Qualitäts Update enthält keine nennenswerten Änderungen, wir empfehlen Ihnen, unsere neuesten Builds für Windows holographisch, Version 2004, zu testen.

## Windows holographisch, Version 2004 – Update vom September 2020
- Build 19041,1117

Verbesserungen und Korrekturen im Update:

- Behebt ein Problem, durch das Visual Studio das Debuggen einer Anwendung verhindert, wenn SupportsMultipleInstances = "true" im appxmanifest vorhanden ist.
- Diese Version enthält die Netzwerkverbindungs-Proxy Erkennungs Korrektur zum Beheben einer fehlgeschlagenen Internet Erkennung über einen Netzwerkproxy. Netzwerkverbindungs kann den Computer Proxy und den pro-Profil-Proxy für die Erkennung von Internet Verbindungen verwenden. Pro-Benutzer-Proxy wird von Netzwerkverbindungs in der zukünftigen Version unterstützt.
- Bei den meisten Windows-Mixed-Reality-Geräten befindet sich der aufwärts Richtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet. In früheren Versionen von HoloLens 2 wurde der Vektor jedoch so ausgerichtet, dass er senkrecht zu den Anzeigebereichen verläuft, was relativ zur idealen Ausrichtung um einige Grad nach unten geneigt ist. Neuere Versionen von HoloLens 2 haben dies korrigiert, um die semantische Konsistenz in Formfaktoren zu gewährleisten.
- Verbesserte Robustheit der Hand Nachverfolgung, die zu weniger nach Verfolgungs Verlusten in bestimmten Szenarien führt.
- Diese Version enthält eine Lösung zur Verbesserung der Qualität des Audio-Zeitstempels, die möglicherweise zu Problemen bei der Videoaufnahme beigetragen hat.

## Windows holographisch, Version 1903 – Update vom September 2020
- Build 18362,1079

Verbesserungen und Korrekturen im Update:

- Bei den meisten Windows-Mixed-Reality-Geräten befindet sich der aufwärts Richtungsvektor parallel zum Boden, wenn sich der Kopf des Benutzers in einer neutralen Position befindet. In früheren Versionen von HoloLens 2 wurde der Vektor jedoch so ausgerichtet, dass er senkrecht zu den Anzeigebereichen verläuft, was relativ zur idealen Ausrichtung um einige Grad nach unten geneigt ist. Neuere Versionen von HoloLens 2 haben dies korrigiert, um die semantische Konsistenz in Formfaktoren zu gewährleisten.
- Verbesserte Robustheit der Hand Nachverfolgung, die zu weniger nach Verfolgungs Verlusten in bestimmten Szenarien führt.

## Windows holographisch, Version 2004 – Update vom August 2020
- Build 19041,1113

Verbesserungen und Korrekturen im Update:

- Die app "Einstellungen" folgt dem Benutzer nicht mehr in die Iris-Registrierung oder die Kalibrierung von Augen Nachverfolgung.
- Ein Fehler wurde behoben, bei dem die Anwendung eines Bereitstellungspakets während OOBE, das das Gerät umbenennen und andere Aktionen ausführt (wie etwa das Herstellen einer Verbindung mit einem Netzwerk), die anderen Aktionen nach dem Neustart des Geräts aufgrund einer Umbenennung nicht durchführen würde.
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
- Wenn Sie über eine Wi-Fi Verbindung auf Device Portal zugreifen, kann ein Webbrowser möglicherweise verhindern, dass der Zugriff auf ein ungültiges Zertifikat zurückzuführen ist. Der Browser meldet möglicherweise einen Fehler wie "ERR_SSL_PROTOCOL_ERROR", auch wenn das Gerätezertifikat zuvor als vertrauenswürdig eingestuft wurde. In diesem Fall können Sie nicht zu Device Portal Fortschreiten, da es keine Option zum Ignorieren von Sicherheitswarnungen gibt. Dieses Update hat das Problem behoben. Wenn das Gerätezertifikat zuvor heruntergeladen und auf einem PC als vertrauenswürdig eingestuft wurde, um die Sicherheitswarnungen des Browsers zu entfernen, und der SSL-Fehler auftritt, muss das neue Zertifikat heruntergeladen und den Sicherheitswarnungen des Browsers als vertrauenswürdig eingestuft werden.
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

Mit Windows Autopilot für HoloLens 2 kann der Geräte Vertriebskanal HoloLens in Ihrem InTune-Mandanten vor der Registrierung registrieren. Wenn Geräte eintreffen, können Sie als freigegebene Geräte unter Ihrem Mandanten selbst bereitgestellt werden. Um die Vorteile der Selbstbereitstellung zu nutzen, muss das Gerät während des ersten Bildschirms in Setup mithilfe eines USB-C-zu-Ethernet-Geräts eine Verbindung mit einem Netzwerk herstellen.

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

Unterstützung wurde hinzugefügt, um bestimmte mobile Breitbandgeräte wie 5G/LTE-Telefone und Wi-Fi Eintöpfen zu aktivieren, wenn Sie über einen USB-Anschluss an das HoloLens 2 angebunden sind. Diese Geräte werden nun in den **Netzwerkeinstellungen** als eine weitere Ethernet-Verbindung angezeigt. (Mobile Breitbandgeräte, die einen externen Treiber erfordern, werden nicht unterstützt.) Diese Funktion ermöglicht Verbindungen mit hoher Bandbreite, wenn Wi-Fi nicht verfügbar ist und Wi-Fi Tethering nicht ausreicht. Weitere Informationen zu unterstützten USB-Geräten finden Sie unter [Herstellen einer Verbindung mit Bluetooth-und USB-C-Geräten](https://docs.microsoft.com/hololens/hololens-connect-devices).  

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
- Calendar 
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

Die aktualisierte APP ist in Microsoft 365 integriert, damit Sie mehr über Ihre Geräte hinweg erledigen können (derzeit nur in US-English). Auf HoloLens 2 unterstützt Cortana nicht mehr bestimmte gerätespezifische Befehle, wie etwa das Anpassen der Lautstärke oder des Neustarts. Diese Optionen werden jetzt von den neuen System Sprachbefehlen unterstützt. Weitere Informationen zur neuen Cortana-App finden Sie in unserem [Blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Qualitätsverbesserungen und-Korrekturen

Verbesserungen und Korrekturen auch im Update:  
- Einführung eines aktiven Anzeige Kalibrier Systems Dieses Feature verbessert die Stabilität und Ausrichtung von Hologrammen. Sie bleiben nun in Kraft, wenn Sie den Kopf von einer Seite zur anderen bewegen.
- Ein Fehler wurde behoben, bei dem Wi-Fi Streaming zu HoloLens in regelmäßigen Abständen gestört wurde. Wenn eine Anwendung angibt, dass Sie ein Streaming mit niedriger Latenz benötigt, implementieren Sie den Fix durch Aufrufen der [SetSocketMediaStreamingMode-Funktion](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
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
- Calendar
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
