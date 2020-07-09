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
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b054b61b269522d673be104ffbda9abc1bc85415
ms.sourcegitcommit: 168a7659420525e5f3e3088d7ce0b5e03c969029
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "10860605"
---
# Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens!  Es ist ganz einfach, die ersten Schritte zu Unternehmen und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens zu liefern.

Windows Insider wird nun in Kanäle verschoben. Der **fast** -Ring wird zum **dev-Kanal**, **der Slow** -Ring wird zum **Beta-Kanal**, und der **Release Preview** -Ring wird zum **Release Preview-Kanal**. Diese Zuordnung sieht wie folgt aus:

![Erläuterung von Windows-Insider Kanälen](images/WindowsInsiderChannels.png)

Weitere Informationen: [Windows-Blog Eintrag](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## Beginnen Sie, Insider-Builds zu erhalten

Wechseln Sie auf einem HoloLens 2-Gerät zu **Einstellungen**  ->  **Aktualisieren & Security**  ->  **Windows-Insider-Programm** , und wählen Sie **Erste Schritte**aus. Verknüpfen Sie das Konto, das Sie für die Registrierung als Windows-Insider verwendet haben.

Wählen Sie dann **aktive Entwicklung von Windows**aus, wählen Sie aus, ob Sie **Entwickler Kanal** -oder **Beta Kanal** -Builds erhalten möchten, und überprüfen Sie die Programm Ausdrücke.

Wählen Sie **Confirm-> jetzt neu starten** aus, um den Vorgang abzuschließen. Nachdem das Gerät neu gestartet wurde, wechseln Sie zu **Einstellungen – > Update & Sicherheit – > auf Updates überprüfen** , um den neuesten Build zu erhalten.

## Beenden des Empfangs von Insider-Builds

Wenn Sie keine Insider-Builds von Windows holographischen mehr erhalten möchten, können Sie sich abmelden, wenn Ihr HoloLens einen Produktions-Build ausführt, oder Sie können Ihr Gerät mithilfe des erweiterten Wiederherstellungs-Assistenten [Wiederherstellen](hololens-recovery.md) , um Ihr Gerät auf eine nicht Insider-Version von Windows holographisch zu wiederherstellen.

> [!CAUTION]
> Es gibt ein bekanntes Problem, bei dem Benutzer, die sich von Insider Preview nicht registrieren, nach der manuellen Neuinstallation eines neuen Preview-Builds einen blauen Bildschirm erleben würden. Anschließend müssen Sie Ihr Gerät manuell wiederherstellen. Ausführliche Informationen dazu, ob Sie betroffen sind oder nicht, finden Sie unter diesem [bekannten Problem](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

So überprüfen Sie, ob Ihr HoloLens einen Produktions-Build ausführt:

1. Wechseln Sie zu **Einstellungen > System > Info**, und suchen Sie die Buildnummer.
1. [Sehen Sie sich die Versionshinweise für Production Build Numbers an.](hololens-release-notes.md)

So deaktivieren Sie Insider-Builds:

1. Wechseln Sie auf einem HoloLens, auf dem ein Produktions-Build ausgeführt wird, zu **Einstellungen > Update & Security > Windows-Insider-Programm**, und wählen Sie **Insider-Builds beenden**aus.
1. Befolgen Sie die Anweisungen, um Ihr Gerät zu deaktivieren.


## Bereitstellen von Feedback und melden von Problemen

Bitte verwenden Sie [die Feedback-Hub-App](hololens-feedback.md) auf Ihrem HoloLens, um Feedback zu geben und Probleme zu melden. Durch die Verwendung des Feedback-Hubs wird sichergestellt, dass alle erforderlichen Diagnoseinformationen enthalten sind, damit unsere Ingenieure das Problem schnell Debuggen und beheben können.  Probleme mit der chinesischen und japanischen Version von HoloLens sollten auf die gleiche Weise gemeldet werden.

> [!NOTE]
> Stellen Sie sicher, dass Sie die Aufforderung akzeptieren, in der Sie gefragt werden, ob Feedback-Hub auf Ihren Ordner "Dokumente" zugreifen soll (Wählen Sie **Ja** , wenn Sie dazu aufgefordert werden)

## Hinweis für Entwickler

Sie sind willkommen und ermutigt, Ihre Anwendungen mithilfe von Insider-Builds von HoloLens zu entwickeln.  Schauen Sie sich die [HoloLens-Entwicklerdokumentation](https://developer.microsoft.com/windows/mixed-reality/development) an, um zu beginnen. Diese Anweisungen funktionieren mit Insider-Builds von HoloLens.  Sie können die gleichen Builds von Unity und Visual Studio verwenden, die Sie bereits für die HoloLens-Entwicklung verwenden.


## Anmerkungen zu dieser Version von Windows Insider

Ab unserer [Windows holographischen 2020-Update](hololens-release-notes.md) Version sind alle unsere Funktionen zur Veröffentlichungs Vorschau jetzt in der Regel verfügbar! [Aktualisieren Sie Ihre HoloLens](hololens-update-hololens.md) , damit Sie die neuesten Funktionen nutzen können.

Wir werden diese Seite erneut mit neuen Features aktualisieren, während wir Sie für Windows-Insider-Builds freigeben.


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
1.  Wir untersuchen ein Problem, bei dem der Eye Tracker-Treiber Hostprozess bei starker Speicherauslastung abstürzt. Der Treiber Hostprozess für die Eye-Tracking-Funktion sollte automatisch wiederhergestellt werden.

## FFU herunterladen und Blitz Anleitungen
Um mit einem FFU-Flight-Test zu testen, müssen Sie zuerst das Gerät Entsperren, bevor Sie den Flug mit dem signierten FFU.
1. Auf dem PC
    1. Laden Sie FFU auf Ihren PC herunter:[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. Installieren von Arc (Advanced Recovery Companion) aus dem Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
1. Auf HoloLens-Flight Unlock: Öffnen Sie **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows-Insider-Programm** dann registrieren, Gerät neu starten
1. Flash-FFU-jetzt können Sie den Flight-signierten FFU mit ARC blinken
