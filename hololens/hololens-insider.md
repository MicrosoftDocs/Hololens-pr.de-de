---
title: Insider Preview für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen und wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens geben.
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924365"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, [zu beginnen](hololens-insider.md#start-receiving-insider-builds) und wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens zu geben.

## <a name="windows-insider-release-notes"></a>Windows-Insider Anmerkungen zu dieser Version

Wir freuen uns, wieder neue Features für Windows-Insider nutzen zu können. Neue Builds werden in den Entwicklungs- und Betakanälen bereitgestellt, um die neuesten Updates zu erhalten. Wir werden diese Seite weiterhin aktualisieren, wenn wir unseren Windows-Insider Builds weitere Features und Updates hinzufügen. Freuen Sie sich darauf, diese Updates in Ihre Realität zu integrieren. 

### <a name="csp-changes-on-hololens"></a>CSP-Änderungen auf HoloLens
 
- Eingeführt in Windows-Insider Build, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP meldet jetzt auch freien Speicherplatz auf HoloLens-Geräten. Dies sollte ungefähr mit dem Wert übereinstimmen, der auf der Seite Speicher der Einstellungs-App angezeigt wird. Im Folgenden finden Sie den spezifischen Knoten, der diese Informationen enthält.

- ./DevDetail/Ext/Microsoft/FreeStorage (nur GET-Vorgang)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP meldet jetzt auch SSID und BSSID des Wlan-Netzwerks, mit dem HoloLens aktiv verbunden ist. Im Folgenden werden die spezifischen Knoten mit diesen Informationen angezeigt.

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

### <a name="fixes-and-improvements"></a>Fehlerbehebungen und Verbesserungen:

- Es wurde ein [bekanntes Problem für Geräteportal behoben, bei dem keine Aufforderung zum Herunterladen gesperrter Dateien angezeigt wurde.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Ein [bekanntes Problem für Geräteportal mit Dateiupload- und Downloadtime outs](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out) wurde behoben.

## <a name="start-receiving-insider-builds"></a>Starten des Empfangs von Insider-Builds
> [!NOTE]
> Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Zustand zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche "Neu starten" unter Einstellungen/Windows-Insider Programm auswählen.
>
> Es ist ein Fehler auf dem Back-End aufgetreten, der möglicherweise aufgetreten ist, sodass Sie wieder auf kursierten Stand kommen.

Wechseln Sie auf einem HoloLens 2 Gerät zu **Einstellungen**  >  **aktualisieren & Security** Windows-Insider  >  **Program,** und wählen Sie Erste Schritte **aus.** Verknüpfen Sie das Konto, das Sie zum Registrieren als Windows-Insider verwendet haben.
Windows-Insider wechselt jetzt zu Channels. Der **Fast-Ring** wird zum **Dev-Kanal,** der **langsame** Ring zum **Betakanal** und der **Release preview-Ring** zum **Releasevorschaukanal.** Diese Zuordnung sieht wie folgt aus: ![ Windows-Insider Erläuterung zu Kanälen Weitere Informationen finden ](images/WindowsInsiderChannels.png) Sie unter Introducing Windows-Insider Channels on Windows Blogs [(Einführung in Windows-Insider Kanäle](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-Blogs).
Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie aus, ob Sie Dev **Channel** oder **Betakanal** Builds erhalten möchten, und überprüfen Sie die Programmbedingungen.
Wählen Sie **Confirm > Restart Now (Jetzt neu starten)** aus, um den Vorgang abzuschließen. Wechseln Sie nach dem Neustart Ihres Geräts zu **Einstellungen > Update & Security > Suchen nach Updates,** um den neuesten Build zu erhalten.
### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 Problembearbeitung
Wenn beim Aktualisieren im Dev- oder Betakanal ein Updatefehler 0x80070490 wird, versuchen Sie es mit der folgenden kurzfristigen Problemumgemeinung. Dies umfasst das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Verschieben Ihres Insider-Kanals zurück.
#### <a name="stage-one---release-preview"></a>Phase 1: Releasevorschau
1.  Einstellungen, Update & Security, Windows-Insider Program, wählen Release **Preview Channel** aus.
2.  Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.** Fahren Sie nach dem Update mit Phase 2 fort.
#### <a name="stage-two---dev-channel"></a>Phase 2: Entwicklungskanal
1. Einstellungen, Update & Security, Windows-Insider Program, wählen **Sie Dev Channel** aus.
2. Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.**
## <a name="ffu-download-and-flash-directions"></a>FFU-Download und Flash-Anweisungen
Zum Testen mit einer Flugsignierungs-FFU müssen Sie zunächst ihr Gerät entsperren, bevor Sie die flugsigniert-FFU blinken lassen.
1. Auf dem PC:
    1. Laden Sie FFU von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren Sie ARC (Advanced Recovery Companion) über die Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Auf HoloLens – Flight Unlock: Open **Settings** Update & Security Windows-Insider Program (Auf HoloLens – Flight Unlock: Open Settings  >  **Update & Security** Windows-Insider  >  **Program)** registrieren Sie sich, und starten Sie das Gerät neu.
1. Flash-FFU: Jetzt können Sie die flugsignieren FFU mit ARC flashen.
### <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Melden von Problemen
Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrer HoloLens, um Feedback zu geben und Probleme zu melden. Die Verwendung von Feedback-Hub stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.
> [!NOTE]
> Achten Sie darauf, dass Sie die Eingabeaufforderung akzeptieren, in der Sie gefragt werden, ob sie Feedback-Hub möchten, auf Ihren Ordner Dokumente zuzugreifen (wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden).
## <a name="note-for-developers"></a>Hinweis für Entwickler
Sie sind willkommen und werden empfohlen, Ihre Anwendungen mit Insider-Builds von HoloLens zu entwickeln.  Sehen Sie sich die [HoloLens-Entwicklerdokumentation](https://developer.microsoft.com/windows/mixed-reality/development) an, um zu beginnen. Die gleichen Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für die HoloLens-Entwicklung verwenden.
## <a name="stop-receiving-insider-builds"></a>Beenden des Empfangs von Insider-Builds
Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie sich abmelden, wenn Ihre HoloLens einen Produktionsbuild ausführt, oder Sie können Ihr Gerät mit dem Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic [wiederherzustellen.](hololens-recovery.md)
> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die die Registrierung bei Insider Preview-Builds nach der manuellen Neuinstallation eines neuen Vorschaubuilds aufheben, einen Bluescreen erhalten. Anschließend müssen sie ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie in diesem [bekannten Problem.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
So überprüfen Sie, ob HoloLens einen Produktionsbuild ausführt:
1. Wechseln Sie zu **Einstellungen > System > Informationen**, und suchen Sie die Buildnummer.
1. [Informationen zu den Buildnummern für die Produktion finden Sie in den Versionshinweisen.](hololens-release-notes.md)
So deaktivieren Sie Insider-Builds:
1. Wechseln Sie auf einer HoloLens, die einen Produktionsbuild ausführt, zu **Einstellungen > Update & Security > Windows-Insider Program**, und wählen Sie **Insider-Builds beenden** aus.
1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.
