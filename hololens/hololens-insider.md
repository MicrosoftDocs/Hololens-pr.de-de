---
title: Insider Preview für Microsoft HoloLens
description: Erfahren Sie, wie Sie mit Insider-Builds beginnen und wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens geben.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351651"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist einfach, [zu beginnen](hololens-insider.md#start-receiving-insider-builds) und wertvolles Feedback zu unserem nächsten wichtigen Betriebssystemupdate für HoloLens zu geben.

## <a name="windows-insider-release-notes"></a>Windows Insider-Versionshinweise

Neuerungen und Neuerungen bei HoloLens Sehen Sie sich diese neuen Updates an, die HoloLens!

### <a name="colorblind-mode"></a>Farbblindmodus

Hinzugefügt im Insider-Build 20348.1463

Der Farbblindmodus ist ein nützliches Feature, das HoloLens zugänglicher macht. Den neuen Farbblindmodus finden Sie in der Einstellungen-App unter **Einstellungen**  ->  **Erleichterte Bedienung**  ->  **Farbfilter.** Es sind mehrere neue Filter verfügbar. Hier sehen Sie ein visuelles Beispiel für einige der verfügbaren Filter.

| Aus | Graustufen | Tritantropie |
|-----|-----------|------------|
| ![Farbfilter aus](images/colorblind-off.png)   | ![Farbfilter graustufen](images/colorblind-greyscale.png)         | ![Farbfilter-Tritantropie](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>Fehlerbehebungen und Verbesserungen

- Ein bekanntes Problem wurde behoben, bei [dem das Gerät bei jedem Stromstrom von 18 Prozent plötzlich automatisch heruntergefahren wurde.](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- Verbesserungen beim Verschieben des Plattformmodus beim Erkennen der Abwärtsrichtung.
- Ein Problem mit Updatedialogen wurde behoben.
- Der Posteingang Microsoft Edge Browserversion wurde aktualisiert.
- Ein Problem wurde behoben, bei dem das Umstellen optionaler Diagnosedaten die ausgewählte Einstellung nach einem Neustart auf der Seite mit den Telemetrieeinstellungen nicht beibehalten hat.
- Es wurde ein Problem behoben, bei dem QR-Codes nicht erkannt wurden, wenn sie relativ zum Gerät in einem Winkel von 45 Grad gedreht wurden.

## <a name="start-receiving-insider-builds"></a>Starten des Empfangs von Insider-Builds

> [!NOTE]
> Wenn Sie vor Kurzem noch nicht aktualisiert haben, starten Sie Ihr Gerät neu, um den Zustand zu aktualisieren und den neuesten Build zu erhalten.
>
> - Der Sprachbefehl "Gerät neu starten" funktioniert gut.
> - Sie können auch die Schaltfläche "Neu starten" in Einstellungen/Windows Insider Program auswählen.
>
> Es ist ein Fehler auf dem Back-End aufgetreten, der möglicherweise aufgetreten ist, sodass Sie wieder auf kursierten Stand kommen.

Wechseln Sie auf einem HoloLens 2 Gerät zu **Einstellungen**  >  **Update & Security** Windows Insider  >  **Program,** und wählen Sie Erste Schritte **aus.** Verknüpfen Sie das Konto, das Sie zum Registrieren als Windows Insider verwendet haben.

> [!NOTE]
> Um Ihr Gerät bei Insider-Builds zu registrieren, müssen Sie optionale Telemetriedaten aktivieren. Wenn Sie dies noch nicht getan haben, öffnen Sie die Einstellungen-App, wählen Sie  ->  **Datenschutzdiagnose & Feedback** und dann Optionale **Diagnosedaten** aus.

Windows Insider wechselt jetzt zu Kanäle. Der **schnelle** Ring wird zum **Entwicklungskanal,** der **langsame** Ring zum **Betakanal** und der **Releasevorschauring** zum **Releasevorschaukanal.** Diese Zuordnung sieht wie folgt aus:

![Windows Erklärung der Insiderkanäle.](images/WindowsInsiderChannels.png)

Weitere Informationen finden Sie unter [Introducing Windows Insider Channels (Einführung in Windows Insider Channels)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) auf Windows Blogs.
Wählen Sie dann **Aktive Entwicklung von Windows** aus, wählen Sie aus, ob Sie Dev **Channel** oder **Betakanal** Builds erhalten möchten, und überprüfen Sie die Programmbedingungen.
Wählen Sie **Confirm > Restart Now (Jetzt neu starten)** aus, um den Vorgang abzuschließen. Wechseln Sie nach dem Neustart Ihres Geräts zu **Einstellungen > Update & Security > Suchen nach Updates,** um den neuesten Build zu erhalten.

### <a name="update-error-0x80070490-work-around"></a>Updatefehler 0x80070490 Problembearbeitung

Wenn beim Aktualisieren im Dev- oder Betakanal ein Updatefehler 0x80070490 auftritt, versuchen Sie es mit der folgenden kurzfristigen Problemumgemeinung. Dies umfasst das Verschieben Ihres Insider-Kanals, das Aufnehmen des Updates und das anschließende Verschieben Ihres Insider-Kanals zurück.

#### <a name="stage-one---release-preview"></a>Phase 1: Releasevorschau

1. Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Release Preview Channel (Releasevorschaukanal)** aus.

2. Einstellungen, Update & Security, Windows Update, Suchen **nach Updates.** Fahren Sie nach dem Update mit Phase 2 fort.

#### <a name="stage-two---dev-channel"></a>Phase 2: Entwicklungskanal

1. Einstellungen, Update & Security, Windows Insider Program, wählen Sie **Dev Channel** aus.

2. Einstellungen, Update & Security, Windows Update, Suchen **nach Updates.**

## <a name="ffu-download-and-flash-directions"></a>Download- und Flash-Anweisungen für FFU

Zum Testen mit einer Flugsignierungs-FFU müssen Sie zunächst ihr Gerät entsperren, bevor Sie die flugsigniert-FFU blinken lassen.

1. Auf dem PC:
    1. Laden Sie FFU von auf Ihren PC [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) herunter.

    1. Installieren Sie ARC (Advanced Recovery Companion) über die Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Bei HoloLens – Flight Unlock: Öffnen **Sie Einstellungen** Update  >  **& Security** Windows Insider  >  **Program,** registrieren Sie sich, und starten Sie das Gerät neu.

1. Flash-FFU: Jetzt können Sie die mit Flugsignieren signierte FFU mit ARC flashen.

### <a name="provide-feedback-and-report-issues"></a>Bereitstellen von Feedback und Melden von Problemen

Verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrem HoloLens, um Feedback zu geben und Probleme zu melden. Die Verwendung von Feedback-Hub stellt sicher, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Techniker das Problem schnell debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Achten Sie darauf, dass Sie die Eingabeaufforderung akzeptieren, in der Sie gefragt werden, ob sie Feedback-Hub möchten, um auf Ihren Ordner Dokumente zuzugreifen (wählen Sie **Ja** aus, wenn Sie dazu aufgefordert werden).

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
