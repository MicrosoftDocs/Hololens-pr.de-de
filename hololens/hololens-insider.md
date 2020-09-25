---
title: Insider-Vorschau für Microsoft HoloLens
description: Es ist ganz einfach, mit Insider-Builds zu beginnen und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens zu liefern.
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
ms.date: 9/23/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: caf860ad5926c03d1e87e829f04838531510df51
ms.sourcegitcommit: 44de31c6d3534b6e0b73ddc2a9336147daf7a41d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078383"
---
# Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist ganz einfach, die [ersten Schritte](hololens-insider.md#start-receiving-insider-builds) zu Unternehmen und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens zu liefern.

## Anmerkungen zu dieser Version von Windows Insider

Hier finden Sie eine Liste der anstehenden Features, die Sie heute in unserem Windows-Insider-Build ausprobieren können.

| Feature                                                | Beschreibung                                                                                    | Verfügbar in Insider-Builds |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [Unterstützung der automatischen Augen Position](hololens-insider.md#auto-eye-position-support)                              | Sucht aktiv nach Augen Positionen und ermöglicht eine exakte Hologramm-Positionierung.                        | 19041.1339 +                 |
| [Zertifikat-Manager](hololens-insider.md#certificate-manager)                                     | Benutzer können Zertifikate der aktuellen Benutzer-und lokalen Computerzertifikate in der Einstellungs-APP anzeigen, installieren und entfernen.                                         | 19041.1361 +                 |
| [Automatisches Starten der Bereitstellung über USB](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE erkennt automatisch Bereitstellungspakete auf USB-Laufwerken.                                | 19041.1361 +                 |
| [Automatisches bestätigen von Bereitstellungspaketen in Oobe](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | Automatisches Anwenden von Bereitstellungspaketen in Oobe                                             | 19041.1361 +                 |
| [Verwenden von Autopilot mit Wi-Fi-Verbindung](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | Verwenden Sie Autopilot vom Gerät Wi-Fi ohne Ethernet-Adapter.                             | 19041.1364 +                 |
|[Tenantlockdown-CSP und Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | Nachdem die mandantenregistrierung und die Richtlinie angewendet wurden, kann das Gerät immer nur für diesen Mandanten registriert werden, wenn das Gerät zurückgesetzt oder erneut geflasht wird. | 19041.1366 +|
| [Global zugewiesener Zugriff](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | Konfigurieren Sie das HoloLens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist. | 19041.1356 +                 |
| [Automatisches Starten einer APP im Multi-App-Kiosk](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | Legt fest, dass eine Anwendung beim Anmelden bei einem Kioskmodus mit mehreren Apps automatisch gestartet wird.     | 19041.1346 +                 |
| [Verhaltensänderungen im Kiosk Modus zur Behandlung von Fehlern](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Änderungen beim Ausfall des Kiosk Modus werden nun verarbeitet.                                              | 19041.1356 +                 |
| [HoloLens-Richtlinien](hololens-insider.md#hololens-policies)                                      | Neue Richtlinien für Mixed-Reality-Geräte.                                                        | 19041.1349 +                 |
| [Cache-Aad-Gruppenmitgliedschaft für Offline-Kiosk](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | Richtlinie für die Anzahl der Tage, an denen der Aad-Gruppen Mitgliedschafts Cache für den Kiosk Modus verwendet werden darf.    | 19041.1356 +                 |
| [Neue Richtlinien für Geräteeinschränkungen für HoloLens 2](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | Für HoloLens 2 aktivierte Geräteverwaltungsrichtlinien neu aktiviert.                               | 19041.1349 +                 |
| [Neue Energierichtlinien für HoloLens 2](hololens-insider.md#new-power-policies-for-hololens-2)                      | Neu unterstützte Richtlinien für Energie Timeouteinstellungen.                                           | 19041.1349 +                 |
| [Update Richtlinien](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | Neu aktivierte Richtlinien, die die Steuerung von Updates ermöglichen.                                            | 19041.1352 +                 |
| [Sichtbarkeits Seite für aktivierte Einstellungen für HoloLens 2](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | Richtlinie, um auszuwählen, welche Seiten in der Einstellungs-APP angezeigt werden.                                           | 19041.1349 +                 |
|  [Recherche Modus](hololens-insider.md#research-mode) | Verwenden des Recherche Modus auf HoloLens 2 | 19041.1375 + |
| [Verbesserungen und Korrekturen im Update](hololens-insider.md#improvements-and-fixes-in-the-update)                   | Weitere Korrekturen im Update.                                                                | 19041.1361 +                 |


### Unterstützung der automatischen Augen Position

In HoloLens 2 ermöglichen Augen Positionen eine exakte Hologramm-Positionierung, ein komfortables Anzeigeerlebnis und eine verbesserte Anzeigequalität. Augen Positionen werden als Teil des Eye Tracking-Ergebnisses berechnet. Dies erfordert allerdings, dass jeder Benutzer die Kalibrierung der Eye-Tracking-Anwendung durchlaufen muss, selbst wenn die Erfahrung keine Augenblicke erfordert.

Die **Automatische Augen Position (AEP)** ermöglicht diese Szenarien mit einer Interaktions freien Möglichkeit zum Berechnen von Augen Positionen für den Benutzer.  Die automatische Augen Position beginnt automatisch ab dem Moment, in dem der Benutzer das Gerät anlegt, im Hintergrund zu arbeiten. Wenn der Benutzer nicht über eine vorherige Kalibrierung der Augen verfügt, beginnt die automatische augenposition, um die Augen Positionen des Benutzers nach einer kleinen Verarbeitungszeit dem Anzeigesystem zur Verfügung zu stellen. Diese Verarbeitungszeit liegt in der Regel zwischen 20-60 Sekunden. Die Benutzerdaten werden nicht auf dem Gerät gespeichert, und daher wird dieser Vorgang wiederholt, wenn der Benutzer das Gerät wieder annimmt, oder wenn das Gerät neu gestartet oder aus dem Ruhezustand reaktiviert wird.  

Wenn ein nicht kalibrierter Benutzer das Gerät anlegt, gibt es einige Änderungen des Systemverhaltens mit der Funktion "Automatische Augen Position". Ein nicht kalibrierter Benutzer bezieht sich auf eine Person, die den Kalibrierungsprozess für die Augen Verfolgung auf dem Gerät zuvor nicht durchlaufen hat.

|     Aktive Anwendung                           |     Aktuelles Verhalten                                   |     Verhalten von Windows Insider Build 19041.1339 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     APP oder holographische Shell ohne Blick    |     Aufforderung zur Kalibrierung der Augen Verfolgung wird angezeigt.    |     Es wird keine Eingabeaufforderung angezeigt.                                                                                |
|     App "Blick aktiviert"                             |     Aufforderung zur Kalibrierung der Augen Verfolgung wird angezeigt.    |     Die Eingabeaufforderung zur Kalibrierung der Augen wird nur angezeigt, wenn die Anwendung auf Eye-Gaze-Datenstrom zugreift.     |

 Wenn der Benutzer von einer nicht auf den Blick aktivierten Anwendung zu einer wechselt, die auf die Blickdaten zugreift, wird die Kalibrierungs Aufforderung angezeigt. Der Erfahrungs Fluss "außerhalb des Felds" wird nicht geändert. 
 
Für Erfahrungen, bei denen Augenblick Daten oder eine sehr präzise Hologramm-Positionierung erforderlich sind, empfehlen wir unkalibrierten Benutzern, die Eye Tracking-Kalibrierung über die Kalibrierungs Aufforderung zur Augen Verfolgung auszuführen, oder indem Sie die Einstellungs-APP aus dem Startmenü starten, und dann **System > Kalibrierung > Augen Kalibrierung auswählen > die Augen**Kalibrierung durchführen.

**Bekannte Probleme**
 - Wir untersuchen ein Problem, bei dem der Eye Tracker-Treiber Hostprozess bei starker Speicherauslastung abstürzt. Der Treiber Hostprozess für die Eye-Tracking-Funktion sollte automatisch wiederhergestellt werden.

### Zertifikat-Manager

In Windows Insider Build 19041.1361 + fügen wir eine Zertifikatverwaltung in die HoloLens 2-Einstellungs-APP ein. Wechseln Sie zu **Einstellungen > Update & Security >-Zertifikate**. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit, Zertifikate auf Ihrem Gerät anzuzeigen, zu installieren und zu entfernen. Mit dem neuen Zertifikat-Manager verfügen Administratoren und Benutzer nun über verbesserte Überwachungs-, Diagnose-und Validierungstools, um sicherzustellen, dass die Geräte sicher und kompatibel sind. 

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

### Automatisches Starten der Bereitstellung über USB
Vor diesem Build mussten Benutzer den Bereitstellungs Bildschirm während der OOBE manuell starten, um die Bereitstellung über eine Tastenkombination durchführen zu können. Jetzt können Benutzer die Tastenkombination überspringen, indem Sie ein Bereitstellungspaket auf einem USB-Speicherlaufwerk verwenden. 

1. Anschließen des USB-Laufwerks mit dem Bereitstellungspaket während des ersten interagierenden Moments von Oobe
1. Wenn das Gerät bereitgestellt wird, wird die Eingabeaufforderung automatisch mit der Bereitstellungsseite geöffnet. 

> [!NOTE]
> Wenn ein USB-Laufwerk angeschlossen ist, während das Gerät gestartet wird, listet OOBE vorhandenes USB-Speichergerät auf und überwacht, ob weitere angeschlossen sind.

Weitere Informationen zum Anwenden von Bereitstellungspaketen während OOBE finden Sie [hier](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### Automatisches bestätigen von Bereitstellungspaketen in Oobe
Wenn der Hauptbildschirm Bereitstellung angezeigt wird, zählt OOBE 10 Sekunden, bevor automatisch alle Bereitstellungspakete angewendet werden. Benutzer können nach der Überprüfung der erwarteten Pakete innerhalb dieser 10 Sekunden weiterhin bestätigen oder stornieren.

### Automatische Bereitstellung ohne Verwendung der Benutzeroberfläche
Durch die Kombination des automatischen Starts der Bereitstellung von USB-Geräten und der automatischen Bestätigung von Bereitstellungspaketen kann ein Benutzer HoloLens 2-Geräte automatisch bereitstellen, ohne die Benutzeroberfläche des Geräts zu verwenden oder das Gerät sogar zu tragen. Sie können weiterhin dasselbe USB-Laufwerk und Bereitstellungspaket für mehrere Geräte verwenden. Dies ist hilfreich, wenn Sie mehrere Geräte gleichzeitig im gleichen Bereich bereitstellen. 

1. [Erstellen eines Bereitstellungspakets](hololens-provisioning.md) mit dem [Windows-Konfigurations-Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopieren Sie das Paket auf ein USB-Speicherlaufwerk.
1. [Flashen Sie Ihre HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) bis [19041,1361 oder neuere Version](https://aka.ms/hololens2previewdownload). 
1. Wenn [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) das Blinken Ihres Geräts beendet hat, ziehen Sie das USB-C-Kabel ab. 
1. Schließen Sie das USB-Laufwerk an das Gerät an.
1. Wenn das HoloLens 2-Gerät in OOBE bootet, wird das Bereitstellungspaket auf dem USB-Laufwerk automatisch erkannt und die Bereitstellungsseite gestartet.
1. Nach 10 Sekunden wendet das Gerät automatisch das Bereitstellungspaket an. 

Ihr Gerät ist jetzt konfiguriert, und der Bildschirm Bereitstellung erfolgreich wird angezeigt.

### Verwenden von Autopilot mit Wi-Fi-Verbindung
Wenn Sie jetzt während OOBE eine Verbindung zwischen HoloLens 2 und WLAN herstellen, überprüft OOBE, ob das Gerät ein Autopilot-Profil hat. Wenn einer gefunden wird, wird er verwendet, um den restlichen Teil des Aad-Joins und-Registrierungs Flusses abzuschließen. Mit anderen Worten: die Verwendung von Ethernet-zu-USB-c-oder WiFi-zu-USB-c-Adaptern ist nicht mehr erforderlich, Sie funktionieren jedoch weiterhin, wenn Sie am Anfang von OOBE bereitgestellt werden. Weitere Informationen zu [Autopilot für HoloLens 2-Geräte](hololens2-autopilot.md).

### Tenantlockdown-CSP und Autopilot
HoloLens 2-Geräte unterstützen jetzt TenantLockdown CSP ab Windows Insider Build 19041.1366 +. 

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

Überprüfen Sie im InTune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf dem Hololens 2-Gerät angewendet wurde, sind die Effekte von TenantLockdown aktiv.

#### Wie kann ich TenantLockdown-RequireNetworkInOOBE auf HoloLens 2 mithilfe von InTune löschen? 
1. Entfernen Sie die HoloLens 2 aus der Gerätegruppe, der die oben erstellte Gerätekonfiguration zuvor zugewiesen wurde. 

1. Erstellen Sie ein benutzerdefiniertes Oma-URI-basiertes Geräte Konfigurationsprofil, und geben Sie für RequireNetworkInOOBE false an, wie unten dargestellt. Oma-URI-Wert sollte./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Screenshot: Festlegen von RequireNetworkInOOBE auf "false" über OMA-URI in InTune](images/hololens-tenant-lockdown-false.png)

1. Erstellen Sie eine Gruppe, und weisen Sie das Geräte Konfigurationsprofil dieser Gerätegruppe zu. 

1. Machen Sie das HoloLens 2-Geräte Mitglied der im vorherigen Schritt erstellten Gruppe, und lösen Sie die Synchronisierung aus.

Überprüfen Sie im InTune-Portal, ob die Gerätekonfiguration erfolgreich angewendet wurde. Sobald diese Gerätekonfiguration erfolgreich auf dem Hololens 2-Gerät angewendet wurde, sind die Effekte von TenantLockdown inaktiv. 

#### Was passiert während OOBE, wenn das Autopilot-Profil auf einem HoloLens nicht zugewiesen wurde, nachdem TenantLockdown auf "true" festgelegt wurde? 
OOBE wartet unbegrenzt auf das Autopilot-Profil, um es herunterzuladen, und das folgende Dialogfeld wird angezeigt. Um die Effekte von TenantLockdown zu entfernen, muss das Gerät zunächst nur mit Autopilot für seinen ursprünglichen Mandanten registriert werden, und RequireNetworkInOOBE muss wie in vorheriger Schritt beschrieben nicht festgelegt werden, bevor die von TenantLockdown CSP eingeführten Einschränkungen entfernt werden. 

![In-Device-Ansicht für wenn Richtlinie auf dem Gerät erzwungen wird.](images/hololens-autopilot-lockdown.png)

### Global zugewiesener Zugriff – Kiosk Modus
Diese neue Funktion ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Multi-App-Kioskmodus zu konfigurieren, das auf Systemebene anwendbar ist, keine Affinität zu einer beliebigen Identität im System hat und für alle Personen gilt, die sich beim Gerät anmelden. Informieren Sie sich [hier](hololens-global-assigned-access-kiosk.md)ausführlich über dieses neue Feature.

### Automatischer Start einer Anwendung im Kioskmodus mit mehreren apps 
Gilt nur für den Kioskmodus mit mehreren apps, und nur 1 App kann mithilfe des hervorgehobenen Attributs unten in zugewiesener Zugriffskonfiguration automatisch gestartet werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Verhaltensänderungen im Kiosk Modus zur Behandlung von Fehlern

Zu einem früheren Zeitpunkt, zu dem Fehler bei der Anwendung des Kioskmodus aufgetreten sind, wurden im Startmenü alle Anwendungen HoloLens angezeigt. Ab diesem Windows-Insider-Build werden im Fall von Fehlern keine apps im Startmenü wie folgt angezeigt: 

![Abbildung dessen, was der Kiosk Modus jetzt sieht, wenn er fehlschlägt.](images/hololens-kiosk-failure-behavior.png )

#### Updates
Updates können auch für diese Methode konfiguriert werden, auch wenn der Benutzer nicht über den Microsoft Store installiert wird, kann er dennoch Updates erhalten. Updates können so konfiguriert werden, dass Sie auf app-starten oder geplant basieren. Weitere Informationen zum Einrichten dieser [Website finden Sie auf dieser Seite](https://docs.microsoft.com/windows/msix/app-installer/update-settings). 

### HoloLens-Richtlinien
Neue Mixed-Reality-Richtlinien wurden für HoloLens 2-Geräte auf Builds 19041.1349 + erstellt. Zu den neuen steuerbaren Einstellungen gehören: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed-Reality-Aufnahmen, festlegen, wann die Diagnose erfasst werden kann, und Aad-Gruppenmitgliedschaft Zwischenspeicher.  

| Neue HoloLens-Richtlinie                                | Beschreibung                                                                               | Anmerkungen                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Ermöglicht die Deaktivierung der Helligkeits Schaltflächen, damit die Helligkeit nicht geändert wird.       | 1 ja, 0 Nein (Standard)                                                |
| MixedReality\VolumeButtonDisabled                  | Ermöglicht das Deaktivieren von Lautstärketasten, damit die Lautstärke nicht geändert wird.               | 1 ja, 0 Nein (Standard)                                                |
| MixedReality\MicrophoneDisabled                    | Deaktiviert das Mikrofon, damit auf HoloLens 2 keine Audioaufnahme möglich ist.                      | 1 ja, 0 Nein (Standard)                                                |
| MixedReality\FallbackDiagnostics                   | Steuert das Verhalten, wenn Diagnoseprotokolle erfasst werden können.                               | 0 deaktiviert, 1 für Gerätebesitzer aktiviert, 2 für alle aktiviert (Standard) |
| MixedReality\HeadTrackingMode                      | Für die spätere Verwendung reserviert.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Steuert, wie viele Tage der Aad-Gruppen Mitgliedschafts Cache für Kiosk-Targeting-Aad-Gruppen verwendet wird. | Siehe unten.                                                           |

### Cache-Aad-Gruppenmitgliedschaft für Offline-Kiosk

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
> Bis Schritt 4 für einen Aad-Benutzer durchgeführt wird, tritt das nachstehend beschriebene Fehler Verhalten in "getrennte" Umgebungen auf. 

### Neue Richtlinien für Geräteeinschränkungen für HoloLens 2
Neu aktivierte Richtlinien, die weitere Verwaltungsoptionen von HoloLens 2-Geräten ermöglichen. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp) *

>[!NOTE]
> In Bezug auf [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)unterstützt HoloLens nur die./Vendor/MSFT/RemoteLock/Lock-Konfiguration. Die Konfigurationen, die sich mit PIN wie Reset und Recover befassen, werden nicht unterstützt.

### Neue Energierichtlinien für Hololens 2
Diese neu hinzugefügten Richtlinien ermöglichen Administratoren, Energiezustände wie Leerlauftimeout zu steuern. Wenn Sie mehr über die einzelnen Richtlinien erfahren möchten, klicken Sie auf den Link für diese Richtlinie.

|     Link zur Richtlinien Dokumentation                |     Anmerkungen                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Beispielwert für die Verwendung im Windows-Konfigurations-Designer, also 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Beispielwert für die Verwendung im Windows-Konfigurations-Designer, also 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Beispielwert, der im Windows-Konfigurations-Designer verwendet werden soll, also  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

> [!NOTE]
> Um eine konsistente Nutzung von HoloLens 2 zu gewährleisten, stellen Sie bitte sicher, dass die Werte für DisplayOffTimeoutOnBattery und StandbyTimeoutOnBattery mit dem gleichen Wert festgesetzt werden. Das gleiche gilt für DisplayOffTimeoutPluggedIn und StandbyTimeoutPluggedIn. Weitere Informationen zum modernen Standby finden Sie unter [Leerlaufzeiten für Anzeige, Ruhezustand und Ruhezustand](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### Neu aktivierte Update Richtlinien für HoloLens
Diese Update Richtlinien sind jetzt auf HoloLens 2-Geräten aktiviert:
-   [Update-ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update-ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update-ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update-SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### Sichtbarkeits Seite für aktivierte Einstellungen für HoloLens 2
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

### Verbesserungen und Korrekturen im Update:
- Aktualisierte Richtlinie zum Deaktivieren der Enumeration von USB-Funktionen über MDM für NCM für AllowUsbConnection.
- Weitere Bildschirme in OOBE sind jetzt im dunklen Modus.
- Weitere Informationen sollten auf die neueste Datenschutzerklärung Online verweisen.
- Ein Problem wurde behoben, bei dem Benutzer VPN-Profile nicht über Bereitstellungspakete bereitstellen konnten.
- Ein Problem wurde behoben, das verhinderte, dass ein HoloLens-Gerät im Datei-Explorer über das Media Transfer Protocol (MTP) angezeigt wird, wenn das Gerät als [Single-App-Kiosk](hololens-kiosk.md)eingerichtet wurde. Beachten Sie, dass MTP (und eine USB-Verbindung im allgemeinen) weiterhin mithilfe der [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) -Richtlinie deaktiviert werden können.

## Beginnen Sie, Insider-Builds zu erhalten

> [!NOTE]
> Wenn Sie nicht kürzlich aktualisiert haben, starten Sie Ihr Gerät neu, um den Zustand zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche Neustart in Einstellungen/Windows-Insider-Programm auswählen.
>
> Wir hatten einen Bug auf dem Back-End, auf den Sie möglicherweise gestoßen sind, sodass Sie wieder auf dem richtigen Weg sind.

Wechseln Sie auf einem HoloLens 2-Gerät zu **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows-Insider-Programm** , und wählen Sie **Erste Schritte**aus. Verknüpfen Sie das Konto, das Sie für die Registrierung als Windows-Insider verwendet haben.

Windows Insider wird nun in Kanäle verschoben. Der **fast** -Ring wird zum **dev-Kanal**, **der Slow** -Ring wird zum **Beta-Kanal**, und der **Release Preview** -Ring wird zum **Release Preview-Kanal**. Diese Zuordnung sieht wie folgt aus:

![Erläuterung von Windows-Insider Kanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Einführung in Windows-Insider Kanäle](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-Blogs.

Wählen Sie dann **aktive Entwicklung von Windows**aus, wählen Sie aus, ob Sie **Entwickler Kanal** -oder **Beta Kanal** -Builds erhalten möchten, und überprüfen Sie die Programm Ausdrücke.

Wählen Sie **> jetzt neu starten** aus, um den Vorgang abzuschließen. Nachdem das Gerät neu gestartet wurde, wechseln Sie zu **Einstellungen > Update & Sicherheit > auf Updates überprüfen** , um den neuesten Build zu erhalten.

## FFU herunterladen und Blitz Anleitungen
Um mit einem FFU-Flight-Test zu testen, müssen Sie zuerst das Gerät Entsperren, bevor Sie den Flug mit dem signierten FFU.
1. Auf dem PC:

    1. Laden Sie FFU von auf Ihren PC herunter [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installieren von Arc (Advanced Recovery Companion) aus dem Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. Auf HoloLens-Flight Unlock: Öffnen Sie **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows-Insider-Programm** und registrieren Sie sich, und starten Sie das Gerät neu.

1. Flash-FFU-jetzt können Sie den Flight signierten FFU mithilfe von Arc blinken.

## Bereitstellen von Feedback und melden von Problemen

Bitte verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrem HoloLens, um Feedback zu geben und Probleme zu melden. Durch die Verwendung des Feedback-Hubs wird sichergestellt, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Ingenieure das Problem schnell Debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Stellen Sie sicher, dass Sie die Aufforderung akzeptieren, in der Sie gefragt werden, ob Feedback-Hub auf Ihren Ordner "Dokumente" zugreifen soll (Wählen Sie **Ja** , wenn Sie dazu aufgefordert werden)

## Hinweis für Entwickler

Sie sind willkommen und ermutigt, Ihre Anwendungen mithilfe von Insider-Builds von HoloLens zu entwickeln.  Schauen Sie sich die [HoloLens-Entwicklerdokumentation](https://developer.microsoft.com/windows/mixed-reality/development) an, um zu beginnen. Diese Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für die HoloLens-Entwicklung verwenden.

## Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows holographischen mehr erhalten möchten, können Sie sich abmelden, wenn Ihr HoloLens einen Produktions-Build ausführt, oder Sie können Ihr Gerät mithilfe des erweiterten Wiederherstellungs-Assistenten [Wiederherstellen](hololens-recovery.md) , um Ihr Gerät auf eine nicht Insider-Version von Windows holographisch zu wiederherstellen.

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die sich von Insider Preview nicht registrieren, nach der manuellen Neuinstallation eines neuen Preview-Builds einen blauen Bildschirm erleben würden. Anschließend müssen Sie Ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie unter diesem [bekannten Problem](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

So überprüfen Sie, ob Ihr HoloLens einen Produktions-Build ausführt:

1. Wechseln Sie zu **Einstellungen > System > Info**, und suchen Sie die Buildnummer.

1. [Sehen Sie sich die Versionshinweise für Production Build Numbers an](hololens-release-notes.md).

So deaktivieren Sie Insider-Builds:

1. Wechseln Sie auf einem HoloLens, auf dem ein Produktions-Build ausgeführt wird, zu **Einstellungen > Update & Security > Windows-Insider-Programm**, und wählen Sie **Insider-Builds beenden**aus.

1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.
