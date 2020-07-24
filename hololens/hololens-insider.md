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
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 7eaa08b7d88cac1841573b08d492f6b66b599c37
ms.sourcegitcommit: bde0c2035638ba48f64ac05ed18595a907a05c6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894604"
---
# Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens!  Es ist ganz einfach, die ersten Schritte zu Unternehmen und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens zu liefern.

Windows Insider wird nun in Kanäle verschoben. Der **fast** -Ring wird zum **dev-Kanal**, **der Slow** -Ring wird zum **Beta-Kanal**, und der **Release Preview** -Ring wird zum **Release Preview-Kanal**. Diese Zuordnung sieht wie folgt aus:

![Erläuterung von Windows-Insider Kanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Einführung in Windows-Insider Kanäle](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-Blogs.

## Anmerkungen zu dieser Version von Windows Insider

Wenn Sie nach einem Feature suchen, das hier nicht mehr aufgeführt ist, ist es jetzt in der Regel verfügbar. Bitte lesen Sie die Anmerkungen zu dieser [Version](hololens-release-notes.md) , um zu erfahren, was Build die Funktion (en) hat, auf die Sie sich freuen. [Aktualisieren Sie Ihre HoloLens](hololens-update-hololens.md) , damit Sie die neuesten Funktionen nutzen können.

Wir werden diese Seite erneut mit neuen Features aktualisieren, während wir Sie für Windows-Insider-Builds freigeben.

|                     Feature                     |                                          Beschreibung                                          | Verfügbar in Insider-Builds |
|:-----------------------------------------------:|:---------------------------------------------------------------------------------------------:|:---------------------------:|
| Unterstützung der automatischen Augen Position                       | Sucht aktiv nach Augen Positionen und ermöglicht eine exakte Hologramm-Positionierung.                       | 19041.1339 +                 |
| Global zugewiesener Zugriff                          | Konfigurieren Sie das HoloLens 2-Gerät für den Multi-App-Kioskmodus, der auf Systemebene anwendbar ist.  | 19041.1346 +                 |
| Automatisches Starten einer APP im Multi-App-Kiosk           | Legt fest, dass eine Anwendung beim Anmelden in einem Kioskmodus mit mehreren Apps automatisch gestartet wird. | 19041.1346 +                 |
| Neue Energierichtlinien für Hololens 2               | Neu unterstützte Richtlinien für Energie Timeouteinstellungen.                                          | 19041.1349 +                 |
| Zertifikatanzeige                              | Zeigen Sie Benutzer-und Gerätezertifikate in der Einstellungs-APP an.                                        | 19041.1346 +                 |
| Neue Richtlinien für Geräteeinschränkungen für HoloLens 2  | Für HoloLens 2 aktivierte Geräteverwaltungsrichtlinien neu aktiviert.                              | 19041.1349 +                 |
| Sichtbarkeits Seite für aktivierte Einstellungen für HoloLens 2 | Richtlinie, um auszuwählen, welche Seiten in der Einstellungs-APP angezeigt werden.                                          | 19041.1349 +                 |
| HoloLens-Richtlinien                               | Neue Richtlinien für Mixed-Reality-Geräte.                                                       | 19041.1349 +                 |
| Update Richtlinien                                 | Neu aktivierte Richtlinien, die die Steuerung von Updates ermöglichen.                                           | 19041.1352 +                 |

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

### Global zugewiesener Zugriff – Kiosk Modus
Diese neue Funktion ermöglicht es einem IT-Administrator, ein HoloLens 2-Gerät für den Multi-App-Kioskmodus zu konfigurieren, das auf Systemebene anwendbar ist, keine Affinität zu einer beliebigen Identität im System hat und für alle Personen gilt, die sich beim Gerät anmelden. Informieren Sie sich [hier](hololens-global-assigned-access-kiosk.md)ausführlich über dieses neue Feature.

### Automatischer Start einer Anwendung im Kioskmodus mit mehreren apps 
Gilt nur für den Kioskmodus mit mehreren apps, und nur 1 App kann mithilfe des hervorgehobenen Attributs unten in zugewiesener Zugriffskonfiguration automatisch gestartet werden. 

Die Anwendung wird automatisch gestartet, wenn sich der Benutzer anmeldet. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

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

### Zertifikatanzeige

In Windows Insider Build 19041.1346 + fügen wir eine Zertifikatanzeige in der HoloLens 2-Einstellungs-APP hinzu. Dieses Feature bietet eine einfache und benutzerfreundliche Möglichkeit, Zertifikate auf Ihrem Gerät zu überprüfen. Um ein bestimmtes Zertifikat schnell zu finden, gibt es Optionen zum Sortieren nach Name, Store oder Ablaufdatum. Benutzer können auch direkt nach einem Zertifikat suchen. Mit der neuen Zertifikatanzeige haben Administratoren und Benutzer nun verbesserte Überwachungs-, Diagnose-und Validierungstools, um sicherzustellen, dass Geräte sicher und kompatibel bleiben.  Wenn Sie weitere Informationen zu einem einzelnen Zertifikat anzeigen möchten, wählen Sie das Zertifikat aus, und klicken Sie auf Info.

> [!NOTE]
> Es gibt eine bekannte Einschränkung für die Lokalisierung von nicht-US-Sprachen, die wir in nachfolgenden Windows-Insider-Versionen bearbeiten.

-   **Überwachung:** Fähigkeit, zu überprüfen, ob ein Zertifikat richtig bereitgestellt wurde, oder zu bestätigen, dass es ordnungsgemäß entfernt wurde. 
-   **Diagnose:** Wenn Probleme auftreten, können Sie überprüfen, ob die entsprechenden Zertifikate auf dem Gerät vorhanden sind, Zeit sparen und bei der Problembehandlung helfen. 
-   **Validierung:** Wenn Sie überprüfen, ob das Zertifikat den beabsichtigten Zweck erfüllt und funktionell ist, können Sie vor allem in kommerziellen Umgebungen beträchtliche Zeit sparen, bevor Sie Zertifikate im größeren Maßstab bereitstellen.

Wenn Sie Zertifikate anzeigen möchten, wechseln Sie zu **Einstellungen > Update & Security >-Zertifikate**.

![Zertifikatanzeige in der Einstellungs-APP](images/hololens-certificate-viewer.png)

### Neue Richtlinien für Geräteeinschränkungen für HoloLens 2
Neu aktivierte Richtlinien, die weitere Verwaltungsoptionen von HoloLens 2-Geräten ermöglichen. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone) 

### Sichtbarkeits Seite für aktivierte Einstellungen für HoloLens 2
Wir haben jetzt eine Richtlinie aktiviert, mit der IT-Administratoren entweder verhindern können, dass bestimmte Seiten in der System Einstellungen-App sichtbar oder barrierefrei sind, oder dies für alle Seiten mit Ausnahme der angegebenen Aktionen. Klicken Sie auf den Link unten, um zu erfahren, wie Sie diese Funktion vollständig anpassen können.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![Screenshot der in der Einstellungs-APP geänderten aktiven Stunden](images/hololens-page-visibility-list.jpg)

### HoloLens-Richtlinien
Neue Mixed-Reality-Richtlinien wurden für HoloLens 2-Geräte auf Builds 19041.1349 + erstellt. Zu den neuen steuerbaren Einstellungen gehören: Festlegen der Helligkeit, Festlegen der Lautstärke, Deaktivieren der Audioaufzeichnung in Mixed-Reality-Aufnahmen, festlegen, wann Diagnosen erfasst werden können.  

|     Neue HoloLens-Richtlinie                   |     Beschreibung                                                                            |     Anmerkungen                                                                |
|-------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
|     MixedReality\BrightnessButtonDisabled |     Ermöglicht die Deaktivierung der Helligkeits Schaltflächen, damit die Helligkeit nicht geändert wird.    |     1 ja, 0 Nein (Standard)                                                |
|     MixedReality\VolumeButtonDisabled     |     Ermöglicht das Deaktivieren von Lautstärketasten, damit die Lautstärke nicht geändert wird.            |     1 ja, 0 Nein (Standard)                                                |
|     MixedReality\MicrophoneDisabled       |     Deaktiviert das Mikrofon, damit auf HoloLens 2 keine Audioaufnahme möglich ist.                   |     1 ja, 0 Nein (Standard)                                                |
|     MixedReality\FallbackDiagnostics      |     Steuert das Verhalten, wenn Diagnoseprotokolle erfasst werden können.                            |     0 deaktiviert, 1 für Gerätebesitzer aktiviert, 2 für alle aktiviert (Standard) |
|     MixedReality\HeadTrackingMode         |     Für die spätere Verwendung reserviert.                                                               |                                                                          |
### Neu aktivierte Update Richtlinien für HoloLens
Diese Update Richtlinien sind jetzt auf HoloLens 2-Geräten aktiviert:
-   [Update-ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update-ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update-ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update-SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

## Beginnen Sie, Insider-Builds zu erhalten

Wechseln Sie auf einem HoloLens 2-Gerät zu **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows-Insider-Programm** , und wählen Sie **Erste Schritte**aus. Verknüpfen Sie das Konto, das Sie für die Registrierung als Windows-Insider verwendet haben.

Wählen Sie dann **aktive Entwicklung von Windows**aus, wählen Sie aus, ob Sie **Entwickler Kanal** -oder **Beta Kanal** -Builds erhalten möchten, und überprüfen Sie die Programm Ausdrücke.

Wählen Sie **> jetzt neu starten** aus, um den Vorgang abzuschließen. Nachdem das Gerät neu gestartet wurde, wechseln Sie zu **Einstellungen > Update & Sicherheit > auf Updates überprüfen** , um den neuesten Build zu erhalten.

## FFU herunterladen und Blitz Anleitungen
Um mit einem FFU-Flight-Test zu testen, müssen Sie zuerst das Gerät Entsperren, bevor Sie den Flug mit dem signierten FFU.
1. Auf dem PC:

    1. Laden Sie FFU von auf Ihren PC herunter [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installieren von Arc (Advanced Recovery Companion) aus dem Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
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
