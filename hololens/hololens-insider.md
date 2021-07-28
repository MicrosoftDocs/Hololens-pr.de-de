---
title: Insider Preview für Microsoft HoloLens
description: Erfahren Sie mehr über die ersten Schritte mit Insider-Builds, und geben Sie wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens.
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
ms.openlocfilehash: 52503c0e1ff8c937211500203b91a30806cd317d
ms.sourcegitcommit: 74f5b64c67026881c8ae46410f272b22862ff582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2021
ms.locfileid: "114696314"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, [zu beginnen](hololens-insider.md#start-receiving-insider-builds) und wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens zu geben.

## <a name="windows-insider-release-notes"></a>Windows Insider-Versionshinweise

Wir freuen uns, neue Features für Windows Insider zu starten. Neue Builds werden in den Entwicklungs- und Betakanälen bereitgestellt, um die neuesten Updates zu erhalten. Wir werden diese Seite weiterhin aktualisieren, wenn wir unseren Windows Insider-Builds weitere Features und Updates hinzufügen. Freuen Sie sich darauf, diese Updates in Ihre Realität zu integrieren.

| Funktion                 | BESCHREIBUNG                | Benutzer oder Szenario | Build eingeführt |
|-------------------------|----------------------------|--------------|------------------|
| [CSP-Änderungen für die Berichterstellung HoloLens Details](#csp-changes-for-reporting-hololens-details) | Neue CSPs für zum Abfragen von Daten | IT-Administratoren    | 20348.1403                 |
| [Richtlinie für die automatische Anmeldung, die von CSP gesteuert wird](#auto-login-policy-controlled-by-csp) | Wird verwendet, um sich automatisch bei einem Konto anzumelden. | IT-Administratoren | 20348.1405 |
| [PFX-Dateiunterstützung für den Zertifikat-Manager](#pfx-file-support-for-certificate-manager) | Hinzufügen von PFX-Zertifikaten über Einstellungen Benutzeroberfläche | Endbenutzer | 20348.1405 |
| [Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Anzeigen von MDM-Diagnoseprotokollen auf dem Gerät | Problembehandlung | 20348.1405 |
| [Offlinediagnosebenachrichtigungen](#offline-diagnostics-notifications) | Feedback zur Protokollsammlung | Problembehandlung | 20348.1405 |
| [Nur private Store-Apps für Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurieren der Store-App, um nur Apps aus der Organisation anzuzeigen | IT-Administrator | 20348.1408 |
| [Fehlerbehebungen und Verbesserungen](hololens-insider.md#fixes-and-improvements) | Fehlerbehebungen und Verbesserungen für HoloLens. | All | 20348.1408 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-Änderungen für die Berichterstellung HoloLens Details

- Eingeführt in Windows Insider-Build, 20348.1403

Die folgenden CSPs wurden mit neuen Möglichkeiten zum Melden von Informationen von Ihren HoloLens Geräten aktualisiert.

#### <a name="devdetail-csp---free-storage"></a>DevDetail-CSP : Kostenlose Storage

DevDetail CSP meldet jetzt auch freien Speicherplatz auf HoloLens Gerät. Dies sollte ungefähr mit dem Wert übereinstimmen, der auf der seite Storage Einstellungen App angezeigt wird. Im Folgenden finden Sie den spezifischen Knoten, der diese Informationen enthält.

- ./DevDetail/Ext/Microsoft/FreeStorage (nur GET-Vorgang)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus-CSP – SSID und BSSID

DeviceStatus CSP meldet jetzt auch SSID und BSSID Wi-Fi Netzwerks, mit dem HoloLens aktiv verbunden ist. Im Folgenden werden die spezifischen Knoten mit diesen Informationen angezeigt.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID

Syncml-Beispielblob (für MDM-Anbieter) zum Abfragen von NetworkIdentifiers

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

Diese neue AutoLogonUser-Richtlinie steuert, ob ein Benutzer automatisch angemeldet wird. Einige Kunden möchten Geräte einrichten, die an eine Identität gebunden sind, aber keine Anmeldeerfahrung haben möchten. Imagine sofort ein Gerät abzuholen und die Remoteunterstützung zu verwenden. Sie können auch schnell HoloLens Geräte verteilen und ihren Endbenutzern ermöglichen, die Anmeldung zu beschleunigen.

Wenn die Richtlinie auf einen nicht leeren Wert festgelegt ist, wird die E-Mail-Adresse des Benutzers für die automatische Anmeldung angegeben. Der angegebene Benutzer muss sich mindestens einmal beim Gerät anmelden, um die automatische Anmeldung zu aktivieren.

Der OMA-URI der neuen Richtlinie `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` Zeichenfolgenwert

- Für Benutzer mit derselben E-Mail-Adresse ist die automatische Anmeldung aktiviert.

Auf einem Gerät, auf dem diese Richtlinie konfiguriert ist, muss sich der in der Richtlinie angegebene Benutzer mindestens einmal anmelden. Bei nachfolgenden Neustarts des Geräts nach der ersten Anmeldung wird der angegebene Benutzer automatisch angemeldet. Es wird nur ein einzelner Benutzer für die automatische Anmeldung unterstützt. Nach der Aktivierung kann sich der automatisch angemeldete Benutzer nicht mehr manuell abmelden. Um sich als anderer Benutzer anmelden zu können, muss die Richtlinie zuerst deaktiviert werden.

> [!NOTE]
> - Einige Ereignisse, z. B. wichtige Betriebssystemupdates, erfordern möglicherweise, dass sich der angegebene Benutzer erneut beim Gerät anmeldet, um das Verhalten der automatischen Anmeldung fortzusetzen. 
> - Die automatische Anmeldung wird nur für MSA- und AAD-Benutzer unterstützt.

### <a name="pfx-file-support-for-certificate-manager"></a>PFX-Dateiunterstützung für den Zertifikat-Manager

Eingeführt in Windows Insider-Build 20348.1405. Wir haben dem [Zertifikat-Manager](certificate-manager.md) Unterstützung für die Verwendung von PFX-Zertifikaten hinzugefügt. Wenn Benutzer zu **Einstellungen** Update & Security Certificates navigieren und Zertifikat  >    >   **installieren** auswählen, unterstützt die Benutzeroberfläche jetzt PFX-Zertifikatsdateien.
Benutzer können ein PFX-Zertifikat mit privatem Schlüssel in den Benutzer- oder Computerspeicher importieren.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Anzeigen des erweiterten Diagnoseberichts in Einstellungen auf HoloLens

Bei verwalteten Geräten bei der Problembehandlung ist die Bestätigung, dass eine erwartete Richtlinienkonfiguration angewendet wird, ein wichtiger Schritt. Vor diesem neuen Feature musste dies über MDM oder in der Nähe des Geräts erfolgen, nachdem mdm-Diagnoseprotokolle exportiert wurden, die über **Einstellungen**  ->  **Konten**  >  **auf Arbeits- oder Schulkonto zugreifen** gesammelt wurden. Wählen Sie dann **Verwaltungsprotokolle exportieren** und auf einem PC in der Nähe anzeigen aus.

Jetzt kann die MDM-Diagnose über den Edge-Browser auf dem Gerät angezeigt werden. Um den MDM-Diagnosebericht einfacher anzuzeigen, navigieren Sie zur Seite Auf Arbeits- oder Schuleinrichtung zugreifen, und wählen **Sie Erweiterten Diagnosebericht anzeigen** aus. Dadurch wird der Bericht in einem neuen Edgefenster generiert und geöffnet.

![Zeigen Sie den erweiterten Diagnosebericht in Einstellungen App an.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offlinediagnosebenachrichtigungen

Dies ist ein Update für ein vorhandenes Feature namens [Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics) Bisher gab es für Benutzer keinen eindeutigen Hinweis, dass sie die Diagnosesammlung ausgelöst oder abgeschlossen hatten.
Jetzt in Windows Insider-Builds hinzugefügt, gibt es zwei Formen von feedback zur Offlinediagnose. Der erste , der popupt, zeigt Benachrichtigungen an, die sowohl beim Start als auch beim Abschluss der Sammlung angezeigt werden. Diese werden angezeigt, wenn der Benutzer angemeldet ist und über Visuals verfügt.

![Popup zum Sammeln von Protokollen.](./images/logcollection1.jpg)

![Popup, wenn die Protokollsammlung abgeschlossen ist.](./images/logcollection2.jpg)
 
Da Benutzer die Offlinediagnose häufig als Fallbackmechanismus für die Protokollsammlung verwenden, wenn sie keinen Zugriff auf eine Anzeige haben, sich nicht anmelden können oder sich noch in OOBE befinden, wird auch ein Audiohinweise wiedergegeben, wenn Protokolle gesammelt werden. Dieser Sound wird zusätzlich zur Popupbenachrichtigung wiedergegeben.

Dieses neue Feature wird aktiviert, wenn Ihr Gerät aktualisiert wird, und muss nicht aktiviert oder verwaltet werden. In jedem Fall, in dem dieses neue Feedback nicht angezeigt oder gehört werden kann, wird weiterhin die Offlinediagnose generiert.

Wir hoffen, dass es mit dieser neueren Hinzufügung von Feedback zur Freundlichkeit einfacher ist, Diagnosedaten zu sammeln und Ihre Probleme schneller beheben zu können.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Nur private Store-Apps für Microsoft Store verwenden

Die RequirePrivateStoreOnly-Richtlinie wurde für HoloLens aktiviert. Mit dieser Richtlinie kann die Microsoft Store-App so konfiguriert werden, dass nur der private Speicher angezeigt wird, der für Ihre Organisation konfiguriert ist. Beschränken des Zugriffs nur auf die Apps, die Sie zur Verfügung gestellt haben.

Weitere Informationen zu [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Fehlerbehebungen und Verbesserungen

- Es wurde ein [bekanntes Problem für Geräteportal, bei dem keine Aufforderung zum Herunterladen gesperrter Dateien angezeigt wurde.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Es wurde ein [bekanntes Problem bei Geräteportal dateiupload- und download-Time outs behoben.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Behandelt Probleme im Zusammenhang mit der Berichterstellung von Konformitätseigenschaften HoloLens Geräten. Möglicherweise ist ein Neustart erforderlich, damit die richtige Berichterstellung für Insider-Builds ausgelöst wird.  
- Die In-Box-Version von Remote Assist aktualisiert, die auf neuen Flashs installiert ist.


## <a name="start-receiving-insider-builds"></a>Starten des Empfangs von Insider-Builds

> [!NOTE]
> Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Status zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche "Neu starten" im Einstellungen/Windows Insider-Programm auswählen.
>
> Es ist ein Fehler auf dem Back-End aufgetreten, den Sie möglicherweise gefunden haben, damit Sie wieder auf Kurs sind.

Wechseln Sie HoloLens 2 gerät zu Einstellungen  >  **Update & Security** Windows Insider Program, und wählen Sie Erste Schritte  >   **aus.** Verknüpfen Sie das Konto, das Sie für die Registrierung als Windows Insider verwendet haben.

Windows Insider geht jetzt zu Kanälen. Der **Fast** Ring wird zum **Dev Channel,** der **Langsame** Ring wird zum **Betakanal,** und der **Release Preview** Ring wird zum Release **Preview Channel**. Diese Zuordnung sieht wie hier aus:

![Windows Erläuterungen zu Insiderkanälen](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter Introducing Windows Insider Channels (Einführung [Windows Insider-Kanälen)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows Blogs.
Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie aus, ob Sie Dev **Channel** oder Betakanal erhalten möchten, und überprüfen Sie die Programmbedingungen. 
Wählen **Sie Bestätigen > Jetzt neu starten aus,** um den Abschluss zu beenden. Nachdem Ihr Gerät neu gestartet wurde, wechseln Sie zu Einstellungen > **Update & Security > Suchen** nach Updates, um den neuesten Build zu erhalten.

### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 Der Arbeitsumgeher

Wenn beim Aktualisieren auf dem Dev- 0x80070490 Betakanal ein Updatefehler auftritt, probieren Sie die folgenden kurzfristigen Schritte aus. Dazu gehört das Verschieben Ihres Insiderkanals, das Aufnehmen des Updates und das anschließende Verschieben Des Insider-Kanals zurück.

#### <a name="stage-one---release-preview"></a>Phase 1: Releasevorschau

1.  Einstellungen Sie unter Update & Security (Windows Insider-Programm) **release preview channel (Releasevorschaukanal) aus.**

2.  Einstellungen, Update & Security, Windows Update, Check for updates (Nach **Updates suchen).** Fahren Sie nach dem Update mit Phase 2 fort.

#### <a name="stage-two---dev-channel"></a>Phase 2: Entwicklungskanal

1. Einstellungen Sie unter Update & Security (Windows Insider-Programm) die Option **Dev Channel (Entwicklungskanal) aus.**

2. Einstellungen, Update & Security, Windows Update, Check for updates (Nach **Updates suchen).**

## <a name="ffu-download-and-flash-directions"></a>FFU-Download und Flash-Anweisungen

Zum Testen mit einem FFU mit Flugsignierung müssen Sie ihr Gerät zunächst entsperren, bevor Sie den FFU-Test mit Flugsignierung blinken.

1. Auf dem PC:
    1. Laden Sie ffu von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren Sie ARC (Advanced Recovery Companion) über Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. On HoloLens – Flight Unlock :Öffnen **Sie Einstellungen** Update &  >  **Security** Windows  >  **Insider Program,** registrieren Sie sich, und starten Sie das Gerät neu.

1. Flash FFU: Jetzt können Sie die FFU mit Flugsignierung mit ARC flashen.

### <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Melden von Problemen

Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) in Ihrer HoloLens, um Feedback zu geben und Probleme zu melden. Durch Feedback-Hub wird sichergestellt, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Stellen Sie sicher, dass Sie die Eingabeaufforderung akzeptieren, in der  Sie gefragt werden, ob Sie Feedback-Hub Auf Ihren Ordner Dokumente zugreifen möchten (wählen Sie Ja aus, wenn Sie dazu aufgefordert werden).

## <a name="note-for-developers"></a>Hinweis für Entwickler

Sie sind willkommen und werden aufgefordert, Ihre Anwendungen mithilfe von Insider-Builds von HoloLens.  Sehen Sie sich die [HoloLens Entwicklerdokumentation an,](https://developer.microsoft.com/windows/mixed-reality/development) um zu beginnen. Diese Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio, die Sie bereits für die Entwicklung HoloLens verwenden.

## <a name="stop-receiving-insider-builds"></a>Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie dies deaktivieren, wenn [](hololens-recovery.md) Ihre HoloLens einen Produktions build ausgeführt, oder Sie können Ihr Gerät mit dem Advanced Recovery Companion wiederherstellen, um Ihr Gerät auf eine nicht-Insider-Version von Windows Holographic wiederhergestellt.

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die die Registrierung bei Insider Preview-Builds nach der manuellen Neuinstallation eines neuen Vorschauversions-Builds wieder auf einen blauen Bildschirm setzen. Anschließend muss das Gerät manuell wiederhergestellt werden. Ausführliche Informationen dazu, ob Sie davon in Kontakt sind, finden Sie unter Bekanntes [Problem.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

So überprüfen Sie, HoloLens ein Produktions-Build ausgeführt wird:

1. Wechseln Sie **zu Einstellungen > System > About (Informationen),** und suchen Sie die Buildnummer.

1. [Weitere Informationen finden Sie in den Versionshinweisen zu Produktions-Buildnummern.](hololens-release-notes.md)

So deaktivieren Sie Insider-Builds:

1. Wechseln Sie HoloLens Einem Produktions build ausgeführten Build zu Einstellungen > **Update & Security > Windows Insider Program,** und wählen Sie Stop Insider builds **(Insider-Builds beenden) aus.**

1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.
