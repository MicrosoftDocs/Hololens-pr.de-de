---
title: Insider Preview für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen, und geben Sie wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens.
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
ms.openlocfilehash: de5b8f052cfdd176f5b883661b2339764fd8ec24113e06b1286d9406acf3790f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664117"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, [zu](hololens-insider.md#start-receiving-insider-builds) beginnen und wertvolles Feedback für unser nächstes größeres Betriebssystemupdate für HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider-Versionshinweise

Wir freuen uns, mit der Entwicklung neuer Features für Windows Insider beginnen zu können. Neue Builds werden an die Entwicklungs- und Betakanäle übertragen, um die neuesten Updates zu erhalten. Wir werden diese Seite weiterhin aktualisieren, wenn wir unseren Insider-Builds weitere Features und Windows hinzufügen. Lassen Sie sich freuen und bereit sein, diese Updates in Ihre Realität zu mischen.

| Funktion                 | BESCHREIBUNG                | Benutzer oder Szenario | Build eingeführt |
|-------------------------|----------------------------|--------------|------------------|
| [CSP-Änderungen für die Berichterstellung HoloLens Details](#csp-changes-for-reporting-hololens-details) | Neue CSPs für zum Abfragen von Daten | IT-Administratoren    | 20348.1403                 |
| [Richtlinie für die automatische Anmeldung, die von CSP gesteuert wird](#auto-login-policy-controlled-by-csp) | Wird zum automatischen Anmelden eines Kontos verwendet. | IT-Administratoren | 20348.1405 |
| [PFX-Dateiunterstützung für den Zertifikat-Manager](#pfx-file-support-for-certificate-manager) | Hinzufügen von PFX-Zertifikaten über Einstellungen Benutzeroberfläche | Endbenutzer | 20348.1405 |
| [Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Anzeigen von MDM-Diagnoseprotokollen auf dem Gerät | Problembehandlung | 20348.1405 |
| [Offlinediagnosebenachrichtigungen](#offline-diagnostics-notifications) | Feedback zur Protokollsammlung | Problembehandlung | 20348.1405 |
| [Verwenden Sie nur private Store-Apps nur für Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurieren der Store-App, um nur Apps aus der Organisation anzeigen zu können | IT-Administrator | 20348.1408 |
| [Verbesserungen bei der Protokollsammlung mit geringem Speicher](#low-storage-log-collection-improvements) | Verbesserungen an Protokollsammlungsszenarien in Situationen mit geringem Speicher. | IT-Administrator | 20348.1412 |
| [Fehlerbehebungen und Verbesserungen](hololens-insider.md#fixes-and-improvements) | Korrekturen und Verbesserungen für HoloLens. | Alle | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-Änderungen für die Berichterstellung HoloLens Details

- Eingeführt in Windows Insider-Build, 20348.1403

Die folgenden CSPs wurden mit neuen Möglichkeiten zum Melden von Informationen von Ihren HoloLens aktualisiert.

#### <a name="devdetail-csp---free-storage"></a>DevDetail-CSP – kostenlose Storage

DevDetail-CSP meldet jetzt auch freien Speicherplatz auf HoloLens Gerät. Dies sollte ungefähr mit dem Wert übereinstimmen, der auf Einstellungen-Seite der App Storage wird. Im Folgenden finden Sie den spezifischen Knoten, der diese Informationen enthält.

- ./DevDetail/Ext/Microsoft/FreeStorage (nur GET-Vorgang)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus-CSP: SSID und BSSID

DeviceStatus-CSP meldet jetzt auch SSID und BSSID des Wi-Fi Netzwerks, mit dem HoloLens aktiv verbunden ist. Im Folgenden finden Sie die spezifischen Knoten, die diese Informationen enthalten.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

Beispiel für ein syncml-Blob (für MDM-Anbieter) zum Abfragen von NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Richtlinie für die automatische Anmeldung, die von CSP gesteuert wird

Diese neue AutoLogonUser-Richtlinie steuert, ob ein Benutzer automatisch angemeldet wird. Einige Kunden möchten Geräte einrichten, die an eine Identität gebunden sind, aber keine Anmeldeerfahrung wünschen. Imagine sofort ein Gerät aufnehmen und die Remoteunterstützung verwenden. Oder sie haben den Vorteil, dass sie schnell HoloLens verteilen und ihren Endbenutzern ermöglichen, die Anmeldung zu beschleunigt.

Wenn die Richtlinie auf einen nicht leeren Wert festgelegt ist, wird die E-Mail-Adresse des Benutzers mit automatischer Anmeldung angegeben. Der angegebene Benutzer muss sich mindestens einmal beim Gerät anmelden, um die automatische Anmeldung zu aktivieren.

Der OMA-URI des neuen `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` Richtlinienzeichenfolgenwerts

- Für Benutzer mit derselben E-Mail-Adresse ist die automatische Anmeldung aktiviert.

Auf einem Gerät, auf dem diese Richtlinie konfiguriert ist, muss sich der in der Richtlinie angegebene Benutzer mindestens einmal anmelden. Bei nachfolgenden Neustarts des Geräts nach der ersten Anmeldung wird der angegebene Benutzer automatisch angemeldet. Es wird nur ein einzelner Benutzer für die automatische Anmeldung unterstützt. Nach der Aktivierung kann sich der automatisch angemeldete Benutzer nicht mehr manuell abmelden. Um sich als anderer Benutzer zu anmelden, muss die Richtlinie zuerst deaktiviert werden.

> [!NOTE]
> - Für einige Ereignisse, z. B. wichtige Betriebssystemupdates, muss sich der angegebene Benutzer möglicherweise erneut beim Gerät anmelden, um das Verhalten der automatischen Anmeldung wieder aufzunehmen. 
> - Die automatische Anmeldung wird nur für MSA- und AAD-Benutzer unterstützt.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-Dateiunterstützung für den Zertifikat-Manager

Eingeführt in Windows Insider-Build 20348.1405. Wir haben dem [Zertifikat-Manager](certificate-manager.md) Unterstützung für die Verwendung von PFX-Zertifikaten hinzugefügt. Wenn Benutzer zu **Einstellungen** Update &-Sicherheitszertifikate navigieren und Zertifikat installieren auswählen, unterstützt die Benutzeroberfläche jetzt die  >    >  PFX-Zertifikatdatei. 
Benutzer können pfx-Zertifikate mit privatem Schlüssel in den Benutzer- oder Computerspeicher importieren.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens

Bei verwalteten Geräten bei der Problembehandlung ist die Bestätigung, dass eine erwartete Richtlinienkonfiguration angewendet wird, ein wichtiger Schritt. Zuvor musste dies auf dem Gerät über MDM oder in der Nähe des Geräts erfolgen, nachdem MDM-Diagnoseprotokolle exportiert wurden, die über **Einstellungen-Konten** gesammelt wurden, auf Arbeits- oder Schulkonto zugreifen, und wählen Sie Ihre Verwaltungsprotokolle exportieren und auf einem pc in der Nähe anzeigen  ->    >  aus. 

Die MDM-Diagnose kann nun mithilfe des Edge-Browsers auf dem Gerät angezeigt werden. Um den MDM-Diagnosebericht einfacher anzuzeigen, navigieren Sie zur Seite Auf Arbeits- oder Schularbeit zugreifen, und wählen **Sie Erweiterten Diagnosebericht anzeigen aus.** Dadurch wird der Bericht in einem neuen Edgefenster generiert und geöffnet.

![Zeigen Sie den erweiterten Diagnosebericht in Einstellungen an.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offlinediagnosebenachrichtigungen

Dies ist ein Update für ein vorhandenes Feature namens [Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics) Zuvor gab es keinen eindeutigen Hinweis für Benutzer, dass sie die Diagnosesammlung ausgelöst oder abgeschlossen hatten.
Jetzt in Windows Insider-Builds hinzugefügt, gibt es zwei Formen von Feedback zur Offlinediagnose. Das erste sind Popupbenachrichtigungen, die sowohl beim Start als auch beim Abschluss der Sammlung angezeigt werden. Diese werden angezeigt, wenn der Benutzer angemeldet ist und über Visuals verfügt.

![Popup zum Sammeln von Protokollen.](./images/logcollection1.jpg)

![Popup, wenn die Protokollsammlung abgeschlossen ist.](./images/logcollection2.jpg)
 
Da Benutzer die Offlinediagnose häufig als Fallbackprotokollerfassungsmechanismus verwenden, wenn sie keinen Zugriff auf eine Anzeige haben, sich nicht anmelden können oder sich noch in oobe befinden, wird beim Sammeln von Protokollen auch ein Audio-Hinweis abgespielt. Dieser Sound wird zusätzlich zur Popupbenachrichtigung abgespielt.

Dieses neue Feature wird aktiviert, wenn Ihr Gerät aktualisiert wird, und muss nicht aktiviert oder verwaltet werden. In jedem Fall, in dem dieses neue Feedback nicht angezeigt oder gehört werden kann, wird weiterhin die Offlinediagnose generiert.

Wir hoffen, dass es mit dieser neueren Hinzufügung von Feedback zur Resonanz einfacher ist, Diagnosedaten zu sammeln und Ihre Probleme schneller beheben zu können.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Nur private Store-Apps für Microsoft Store

Die RequirePrivateStoreOnly-Richtlinie wurde für HoloLens aktiviert. Mit dieser Richtlinie kann die Microsoft Store-App so konfiguriert werden, dass nur der private Speicher angezeigt wird, der für Ihre Organisation konfiguriert ist. Beschränken des Zugriffs auf die Apps, die Sie zur Verfügung gestellt haben.

Weitere Informationen zu [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Verbesserungen bei der Protokollsammlung mit geringem Speicher

In Szenarien, in denen ein Gerät bei der Erfassung von Diagnoseprotokollen wenig Speicherplatz auf dem Datenträger zu haben scheint, wird ein zusätzlicher Bericht mit dem Namen **StorageDiagnostics.zip** erstellt. Der Schwellenwert für niedrigen Speicher wird automatisch durch Windows [Speichers sense](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)bestimmt.

### <a name="fixes-and-improvements"></a>Fehlerbehebungen und Verbesserungen

- Es wurde ein [bekanntes Problem für Geräteportal behoben, bei dem keine Aufforderung zum Herunterladen gesperrter Dateien angezeigt wurde.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ein [bekanntes Problem für Geräteportal mit Dateiupload- und Downloadtime outs](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out) wurde behoben.
- Beheben von Problemen bei der Berichterstellung von Konformitätseigenschaften von HoloLens Geräten Möglicherweise ist ein Neustart erforderlich, damit die richtige Berichterstellung in Insider-Builds ausgelöst wird.  
- Die in der Box enthaltene Version von Remote Assist, die auf neuen Flashs installiert ist, wurde aktualisiert.

## <a name="start-receiving-insider-builds"></a>Starten des Empfangs von Insider-Builds

> [!NOTE]
> Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Zustand zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche "Neu starten" in Einstellungen/Windows Insider Program auswählen.
>
> Es ist ein Fehler auf dem Back-End aufgetreten, der möglicherweise aufgetreten ist, sodass Sie wieder auf kursierten Stand kommen.

Wechseln Sie auf einem HoloLens 2 Gerät zu **Einstellungen**  >  **Update & Security** Windows Insider  >  **Program,** und wählen Sie Erste Schritte **aus.** Verknüpfen Sie das Konto, das Sie zum Registrieren als Windows Insider verwendet haben.

Windows Insider wechselt jetzt zu Kanäle. Der **Fast-Ring** wird zum **Dev-Kanal,** der **langsame** Ring zum **Betakanal** und der **Release preview-Ring** zum **Releasevorschaukanal.** Diese Zuordnung sieht wie folgt aus:

![Windows Erklärung zu Insiderkanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Introducing Windows Insider Channels (Einführung Windows Insider Channels)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows Blogs.
Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie aus, ob Sie Dev **Channel** oder **Betakanal** Builds erhalten möchten, und überprüfen Sie die Programmbedingungen.
Wählen Sie **Confirm > Restart Now (Jetzt neu starten)** aus, um den Vorgang abzuschließen. Wechseln Sie nach dem Neustart Ihres Geräts zu **Einstellungen > Update & Security > Suchen nach Updates,** um den neuesten Build zu erhalten.

### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 Problembearbeitung

Wenn beim Aktualisieren im Dev- oder Betakanal ein Updatefehler 0x80070490 wird, versuchen Sie es mit der folgenden kurzfristigen Problemumgemeinung. Dies umfasst das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Verschieben Ihres Insider-Kanals zurück.

#### <a name="stage-one---release-preview"></a>Phase 1: Releasevorschau

1.  Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Release Preview Channel (Releasevorschaukanal)** aus.

2.  Einstellungen, Update & Security, Windows Update, Suchen **nach Updates.** Fahren Sie nach dem Update mit Phase 2 fort.

#### <a name="stage-two---dev-channel"></a>Phase 2: Entwicklungskanal

1. Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Dev Channel** aus.

2. Einstellungen, Update & Security, Windows Update, Suchen **nach Updates.**

## <a name="ffu-download-and-flash-directions"></a>Download- und Flash-Anweisungen für FFU

Zum Testen mit einer Flugsignierungs-FFU müssen Sie zunächst ihr Gerät entsperren, bevor Sie die flugsigniert-FFU blinken lassen.

1. Auf dem PC:
    1. Laden Sie FFU von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren Sie ARC (Advanced Recovery Companion) über die Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Bei HoloLens – Flight Unlock: Öffnen **Sie Einstellungen** Update  >  **& Security** Windows Insider  >  **Program,** und starten Sie das Gerät neu.

1. Flash-FFU: Jetzt können Sie die mit Flugsignieren signierte FFU mit ARC flashen.

### <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Melden von Problemen

Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrem HoloLens, um Feedback zu geben und Probleme zu melden. Die Verwendung von Feedback-Hub stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Achten Sie darauf, dass Sie die Eingabeaufforderung akzeptieren, in der Sie gefragt werden, ob sie Feedback-Hub möchten, auf Ihren Ordner Dokumente zuzugreifen (wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden).

## <a name="note-for-developers"></a>Hinweis für Entwickler

Sie sind willkommen und werden empfohlen, Ihre Anwendungen mit Insider-Builds von HoloLens zu entwickeln.  Sehen Sie sich die [HoloLens Developer-Dokumentation](https://developer.microsoft.com/windows/mixed-reality/development) an, um zu beginnen. Die gleichen Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für HoloLens Entwicklung verwenden.

## <a name="stop-receiving-insider-builds"></a>Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie sich abmelden, wenn Ihr HoloLens einen Produktionsbuild ausführt, oder Sie können Ihr Gerät mit dem Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic [wiederherzustellen.](hololens-recovery.md)

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die die Registrierung bei Insider Preview-Builds nach der manuellen Neuinstallation eines neuen Vorschaubuilds aufheben, einen Bluescreen erhalten. Anschließend müssen sie ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie in diesem [bekannten Problem.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

So überprüfen Sie, ob ihr HoloLens einen Produktionsbuild ausführt:

1. Wechseln Sie zu **Einstellungen > System > About**, und suchen Sie die Buildnummer.

1. [Informationen zu den Buildnummern für die Produktion finden Sie in den Versionshinweisen.](hololens-release-notes.md)

So deaktivieren Sie Insider-Builds:

1. Wechseln Sie auf einer HoloLens, die einen Produktionsbuild ausführt, zu **Einstellungen > Update & Security > Windows Insider Program,** und wählen Sie **Insider-Builds beenden** aus.

1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.
