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
ms.date: 4/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e00c043f7de1142e4d2e08e41ff0d91123d4a98b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828064"
---
# Insider-Vorschau für Microsoft HoloLens

Willkommen bei den neuesten Insider Preview-Builds für HoloLens!  Es ist ganz einfach, die ersten Schritte zu Unternehmen und wertvolles Feedback für unser nächstes wichtiges Betriebssystemupdate für HoloLens zu liefern.

## Beginnen Sie, Insider-Builds zu erhalten

Wechseln Sie auf einem HoloLens 2-Gerät zu **Einstellungen**  ->  **Aktualisieren & Security**  ->  **Windows-Insider-Programm** , und wählen Sie **Erste Schritte**aus. Verknüpfen Sie das Konto, das Sie für die Registrierung als Windows-Insider verwendet haben.

Wählen Sie dann **aktive Entwicklung von Windows**aus, wählen Sie aus, ob Sie **schnell** oder **langsam** Builds erhalten möchten, und überprüfen Sie die Programm Ausdrücke.

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

Ab unserem [Windows holographischen 2020-Update](hololens-release-notes.md) -Release können alle unsere Release Preview-feautres jetzt im allgemeinen avalible! [Aktualisieren Sie Ihre HoloLens](hololens-update-hololens.md) , damit Sie die neuesten Funktionen nutzen können.  

Wir werden diese Seite erneut mit neuen Features aktualisieren, während wir Sie für Windows-Insider-Builds freigeben. 

### FFU herunterladen und Blitz Anleitungen
Um mit einem FFU-Flight-Test zu testen, müssen Sie zuerst das Gerät Entsperren, bevor Sie den Flug mit dem signierten FFU.
1. Auf dem PC
    1. Laden Sie FFU auf Ihren PC herunter:[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. Installieren von Arc (Advanced Recovery Companion) aus dem Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 
1. Auf HoloLens-Flight Unlock: Öffnen Sie **Einstellungen**  >  **Aktualisieren & Security**  >  **Windows-Insider-Programm** dann registrieren, Gerät neu starten
1. Flash-FFU-jetzt können Sie den Flight-signierten FFU mit ARC blinken 
