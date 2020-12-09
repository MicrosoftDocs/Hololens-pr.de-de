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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 260b195a18ecb7fe05d819fcd3e86d56fc2022bf
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201339"
---
# Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens! Es ist ganz einfach, die [ersten Schritte](hololens-insider.md#start-receiving-insider-builds) zu Unternehmen und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens zu liefern.

## Anmerkungen zu dieser Version von Windows Insider

Wir haben vor kurzem alle unsere Windows-Insider-Funktionen veröffentlicht. Da alle diese Funktionen jetzt allgemein verfügbar sind, empfehlen wir Ihnen, unsere [Versionshinweise](hololens-release-notes.md) zu lesen, um alle unsere neuesten Funktionen zu sehen. Schauen Sie immer wieder vorbei, um zu sehen, wann wir neue, spannende Funktionen testen können!

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
