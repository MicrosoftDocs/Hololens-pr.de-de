---
title: Insider-Vorschau für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen, und geben Sie wertvolles Feedback für unser nächstes größeres Betriebssystemupdate für HoloLens.
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
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397821"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, [zu](hololens-insider.md#start-receiving-insider-builds) beginnen und wertvolles Feedback für unser nächstes größeres Betriebssystemupdate für HoloLens zu geben.

## <a name="windows-insider-release-notes"></a>Windows-Insider Versionshinweise

Wir freuen uns, neue Features erneut an Windows-Insider zu stellen. Neue Builds werden an die Entwicklungs- und Betakanäle übertragen, um die neuesten Updates zu erhalten. Wir werden diese Seite weiterhin aktualisieren, wenn wir weitere Features und Updates zu unseren Windows-Insider hinzufügen. Lassen Sie sich freuen und bereit sein, diese Updates in Ihre Realität zu mischen. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive for work or school Camera Roll upload (OneDrive for Work- oder School Camera Roll-Upload)

*Eingeführt in Build 20346.1402*

Wir haben der App "HoloLens 2 Settings" ein neues Feature hinzugefügt, mit dem Kunden automatisch Mixed Reality-Fotos und Videos aus dem Ordner Pictures > Camera Roll des Geräts in den entsprechenden OneDrive for Work- oder School-Ordner hochladen können. Dieses Feature behebt eine Featurelücke innerhalb der [OneDrive-App](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) auf HoloLens 2, die nur den automatischen Upload des Kamerarolls in die persönliche Microsoft-Konto eines Kunden (und nicht in dessen Arbeits-, Schul- oder Schulkonto) unterstützt.

**So funktioniert's**

- Besuchen **Sie einstellungen > System > Mixed Reality-Kamera,** um "Kameraupload" zu aktivieren.
- Wenn Sie dieses  Feature auf Die Position Ein festlegen, werden alle Mixed Reality-Fotos oder Videos, die auf Ihrem Gerät erfasst werden, automatisch in die Warteschlange eingereiht, um sie in den Ordner Pictures > Camera Roll Ihres OneDrive for Work- oder Schulkontos hochzuladen.
    >[!NOTE]
    >Fotos und Videos, die vor  der Aktivierung dieses Features erfasst wurden, werden nicht für den Upload in die Warteschlange eingereiht und müssen weiterhin manuell hochgeladen werden.
- In einer Statusmeldung auf der Seite Einstellungen wird die Anzahl der Dateien angezeigt, deren Upload aussteht (oder "OneDrive ist auf dem neuesten Stand", wenn alle ausstehenden Dateien hochgeladen wurden).
- Wenn Sie Bedenken hinsichtlich der Bandbreite haben oder den Upload aus irgendeinem Grund "anhalten" möchten, können Sie das Feature auf die Position **Aus** umstellen. Durch die vorübergehende Deaktivierung des Features wird sichergestellt, dass die Uploadwarteschlange weiter zunimmt, wenn Sie dem Ordner Camera Roll neue Dateien hinzufügen. Dateien werden jedoch erst hochgeladen, wenn Sie das Feature erneut aktivieren.
- Die neuesten Dateien werden zuerst hochgeladen (last in, first out).
- Wenn Bei Ihrem OneDrive-Konto Probleme auftreten (z. B. nach Kennwortänderungen), wird auf der Seite Einstellungen die Schaltfläche **Jetzt korrigieren** angezeigt.
- Es gibt keine maximale Dateigröße, aber beachten Sie, dass das Hochladen großer Dateien länger dauert (insbesondere, wenn die Uploadbandbreite eingeschränkt ist). Wenn Sie den Upload "anhalten" oder deaktivieren, während eine große Datei hochgeladen wird, wird der Upload sofort abgebrochen. Der Upload wird neu gestartet, wenn Sie das Feature erneut aktivieren. Sie verlieren keine Dateien, aber der Teilupload wird verworfen.

**Bekannte Probleme und Einschränkungen**

- Diese Einstellung verfügt über keine integrierte Drosselung basierend auf der aktuellen Bandbreitennutzung. Wenn Sie die Bandbreite für ein anderes Szenario maximieren müssen, deaktivieren Sie die Einstellung manuell. Der Upload wird angehalten, aber das Feature überwacht weiterhin neu hinzugefügte Dateien für Camera Roll. Aktivieren Sie den Upload erneut, wenn Sie bereit sind, den Upload fortzusetzen.
- Dieses Feature muss für jedes Benutzerkonto auf dem Gerät aktiviert sein und kann nur aktiv Dateien für den Benutzer hochladen, der derzeit auf dem Gerät angemeldet ist.
- Wenn Sie beim Ansehen der Uploadanzahl auf der Seite Einstellungen in Echtzeit Fotos oder Videos aufnehmen, beachten Sie, dass sich die Anzahl ausstehender Dateien möglicherweise erst ändert, wenn der Upload der aktuellen Datei abgeschlossen ist.
- Der Upload wird angehalten, wenn Ihr Gerät eingeschaltet oder ausgeschaltet ist. Um sicherzustellen, dass Ihre ausstehenden Uploads abgeschlossen sind, verwenden Sie das Gerät aktiv, bis die Seite Einstellungen "OneDrive ist auf dem neuesten Stand" lautet, oder passen Sie Ihre **Power & Standbyeinstellungen** an.

## <a name="start-receiving-insider-builds"></a>Starten des Empfangs von Insider-Builds
> [!NOTE]
> Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Zustand zu aktualisieren und den neuesten Build zu erhalten.
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut. 
> - Sie können auch die Schaltfläche "Neu starten" unter Einstellungen/Windows-Insider auswählen.
>
> Es ist ein Fehler auf dem Back-End aufgetreten, den Sie möglicherweise gefunden haben, damit Sie wieder auf Kurs sind.

Wechseln Sie auf HoloLens 2 Gerät zu **Settings** Update & Security Windows-Insider Program (Sicherheits-Windows-Insider Programm), und  >    >   wählen Sie **Get started (Erste Schritte) aus.** Verknüpfen Sie das Konto, das Sie zum Registrieren als Windows-Insider.
Windows-Insider geht jetzt zu Kanälen über. Der **Fast** Ring wird zum **Dev Channel,** der **Langsame** Ring wird zum **Betakanal,** und der **Release Preview** Ring wird zum Release **Preview Channel**. So sieht diese Zuordnung aus: Windows-Insider Erläuterungen zu Kanälen. Weitere Informationen finden Sie unter Introducing Windows-Insider Channels on Windows Blogs (Einführung in ![ ](images/WindowsInsiderChannels.png) [Windows-Insider-Kanäle](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-Blogs).
Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie  aus, ob Sie Dev **Channel** oder Betakanal erhalten möchten, und sehen Sie sich die Programmbedingungen an.
Wählen **Sie Bestätigen > Jetzt neu starten aus,** um den Abschluss zu beenden. Nachdem Ihr Gerät neu gestartet wurde, wechseln Sie zu Einstellungen > Update & **Security > Suchen** nach Updates, um den neuesten Build zu erhalten.
### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 Der Arbeitsumgeher
Wenn beim Aktualisieren auf dem Dev- 0x80070490 Betakanal ein Updatefehler auftritt, probieren Sie die folgenden kurzfristigen Schritte aus. Dazu gehört das Verschieben Ihres Insiderkanals, das Aufnehmen des Updates und das anschließende Verschieben Des Insider-Kanals zurück.
#### <a name="stage-one---release-preview"></a>Phase 1: Releasevorschau
1.  Einstellungen, Update & Security, Windows-Insider Program, wählen **Sie Release Preview Channel (Vorschaukanal für Release) aus.**
2.  Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.** Fahren Sie nach dem Update mit Phase 2 fort.
#### <a name="stage-two---dev-channel"></a>Phase 2: Entwicklungskanal
1. Einstellungen, Update & Security, Windows-Insider Program, wählen **Sie Dev Channel aus.**
2. Einstellungen, Update & Security, Windows Update, **Suchen nach Updates.**
## <a name="ffu-download-and-flash-directions"></a>Download- und Flash-Anweisungen für FFU
Zum Testen mit einer Flugsignierungs-FFU müssen Sie zunächst ihr Gerät entsperren, bevor Sie die flugsigniert-FFU blinken lassen.
1. Auf dem PC:
    1. Laden Sie FFU von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.
    
    1. Installieren Sie ARC (Advanced Recovery Companion) über die Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Auf HoloLens – Flight Unlock: Open **Settings** Update & Security Windows-Insider Program (Auf HoloLens – Flight Unlock: Open Settings  >  **Update & Security** Windows-Insider  >  **Program)** registrieren Sie sich, und starten Sie das Gerät neu.
1. Flash-FFU: Jetzt können Sie die flugsignieren FFU mit ARC flashen.
### <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Melden von Problemen
Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrer HoloLens, um Feedback zu geben und Probleme zu melden. Mit Feedback-Hub wird sichergestellt, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.
> [!NOTE]
> Achten Sie darauf, dass Sie die Eingabeaufforderung akzeptieren, in der Sie gefragt werden, ob sie Feedback-Hub möchten, auf Ihren Ordner Dokumente zuzugreifen (wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden).
## <a name="note-for-developers"></a>Hinweis für Entwickler
Sie sind willkommen und werden empfohlen, Ihre Anwendungen mit Insider-Builds von HoloLens zu entwickeln.  Sehen Sie sich die [HoloLens-Entwicklerdokumentation](https://developer.microsoft.com/windows/mixed-reality/development) an, um zu beginnen. Die gleichen Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für die HoloLens-Entwicklung verwenden.
## <a name="stop-receiving-insider-builds"></a>Beenden des Empfangs von Insider-Builds
Wenn Sie keine Insider-Builds von Windows Holographic mehr erhalten möchten, können Sie sich abmelden, wenn Ihre HoloLens einen Produktionsbuild ausführt, oder Sie können Ihr Gerät mit dem Advanced Recovery Companion wiederherstellen, um Ihr Gerät in einer Nicht-Insider-Version von Windows Holographic [wiederherzustellen.](hololens-recovery.md)
> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die die Registrierung bei Insider Preview-Builds nach der manuellen Neuinstallation eines neuen Vorschaubuilds aufheben, einen Bluescreen erhalten. Anschließend muss das Gerät manuell wiederhergestellt werden. Ausführliche Informationen dazu, ob Sie davon in Kontakt sind, finden Sie unter Bekanntes [Problem.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
So überprüfen Sie, ob Ihre HoloLens einen Produktions-Build ausgeführt:
1. Wechseln Sie **zu Einstellungen > System > About (Informationen),** und suchen Sie die Buildnummer.
1. [Weitere Informationen finden Sie in den Versionshinweisen zu Produktions-Buildnummern.](hololens-release-notes.md)
So deaktivieren Sie Insider-Builds:
1. Wechseln Sie auf einem HoloLens-Computer, auf dem ein Produktions-Build ausgeführt wird, zu Einstellungen > Update & **Security > Windows-Insider Program,** und wählen Sie **Stop Insider builds (Insider-Builds beenden) aus.**
1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.
