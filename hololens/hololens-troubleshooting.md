---
title: Problembehandlung
description: Bleiben Sie über die häufigsten Lösungen für HoloLens-Geräteprobleme und Problembehandlungstechniken auf dem Laufenden.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: Issues, Bug, Troubleshoot, Fix, Help, Support, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308814"
---
# <a name="troubleshooting"></a>Problembehandlung

In diesem Artikel wird beschrieben, wie Sie verschiedene häufige HoloLens-Probleme beheben.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>Meine HoloLens reagiert nicht oder startet nicht.

Wenn Ihre HoloLens nicht gestartet wird:

- Wenn die LEDs neben dem Netzschalter nicht aufleuchten oder nur eine LED kurz blinkt, müssen Sie Möglicherweise müssen Sie [Ihre HoloLens aufladen.](hololens-recovery.md#charge-the-device)
- Wenn die LEDs beim Drücken des Netzschalters aufleuchten, aber auf den Bildschirmen nichts angezeigt wird, stellen Sie [eine harte Zurücksetzung des Geräts](hololens-recovery.md#hard-reset-procedure)vor.

Wenn Ihre HoloLens eingefroren wird oder nicht mehr reagiert:

- Schalten Sie Ihre HoloLens aus, indem Sie auf den Netzschalter klicken, bis sich alle fünf LEDs selbst ausschalten, oder 15 Sekunden lang, wenn die LEDs nicht reagieren. Um Ihre HoloLens zu starten, drücken Sie erneut den Netzschalter.

Wenn diese Schritte nicht funktionieren, können Sie versuchen, Ihr HoloLens 2 Gerät oder [HoloLens-Gerät (1. Generation)](hololens1-recovery.md) [wiederherzustellen.](hololens-recovery.md)

## <a name="holograms-dont-look-good"></a>Hologramme sehen nicht gut aus

Wenn Ihre Hologramme instabil, sprunghaft oder nicht richtig aussehen, versuchen Sie Es:

- Bereinigen des Gerätevisors und der Sensorleiste an der Front Ihrer HoloLens.
- Erhöhen des Lichts in Ihrem Raum.
- Gehen Sie durch Ihre Umgebung, und sehen Sie sich ihre Umgebung an, damit HoloLens sie vollständiger scannen kann.
- Kalibrieren Ihrer HoloLens für Ihre Augen. Wechseln Sie zu **Einstellungen** System utilities  >  **(Systemprogramme).**  >   Wählen Sie unter **Kalibrierung** die Option **Kalibrierung öffnen** aus.
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Melden von Problemen, bei denen Hologramme instabil sind oder nicht richtig aussehen
 
1. Zeichnen Sie das Problem [Mixed Reality-Aufnahme und ein](holographic-photos-and-videos.md#capture-a-mixed-reality-video) video des Problems auf. Dieses Video kann später über Feedback-Hub als angefügte Datei hochgeladen werden.  
1. Aktivieren Sie die  vollständige Telemetrie über die App "Einstellungen> Datenschutzdiagnose & Feedback, und stellen Sie unter Optionale Diagnosedaten sicher, dass die Umschaltung  ->   auf Ein **festgelegt ist.** 
1. Erhalten Sie die neuesten Fixes für Hologrammskala und Stabilität, indem Sie auf das neueste [Windows Holographic-Betriebssystem (20H2 oder höher) aktualisieren.](hololens-release-notes.md#windows-holographic-version-20h2) Führen Sie nach dem Aktualisieren Folgendes aus:
    1. Entfernen Sie alle Hologramme über settings **app** -> **System**  ->  **Holograms** -> wählen Sie dann Alle Hologramme entfernen aus, und beginnen Sie mit einer neuen Karte. 
    1. Erstellen Sie eine neue Karte Ihres Raumes, indem Sie die HoloLens begehen und Ihren Raum durchgehen und sich alle Bereiche und Oberflächen im Raum ansehen. Dies ist zwei bis drei Minuten lang der Fall.
    1. Führen Sie die IPD-Kalibrierung durch. Wechseln Sie zu **Einstellungen**  >    >  **Systemprogramme**. Wählen Sie **unter Kalibrierung** die Option **Kalibrierung öffnen aus.**
    1. Testen Sie das Szenario erneut, und prüfen Sie, ob es weiterhin besteht.
1. Wenn das Problem durch das Aktualisieren nicht behoben wird, melden Sie ein Feedback-Hub [Problem.](hololens-feedback.md) Nachdem Sie Feedback gesendet haben,  können Sie die Schaltfläche Freigeben verwenden, um einen einfach zu teilenden Link zu erstellen, der gesendet werden kann, wenn Sie sich an den Support wenden.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens reagiert nicht auf Handeingaben

Um sicherzustellen, dass HoloLens Ihre Hände sehen kann, müssen Sie sie im Gestenrahmen halten.  Das Mixed Reality Home bietet Feedback, das Sie darüber informiert, wann Ihre Hände nachverfolgt werden.  Das Feedback ist bei verschiedenen HoloLens-Versionen unterschiedlich:
- Auf HoloLens (1. Generation) ändert sich der Anvingcursor von einem Punkt in einen Ring.
- Auf HoloLens 2 wird ein Fingerspitzencursor angezeigt, wenn sich Ihre Hand in der Nähe einer Tafel befindet, und ein Handstrahl wird angezeigt, wenn Tafeln weiter entfernt sind.

Viele immersive Apps folgen Eingabemustern, die Mixed Reality Home ähneln.  Erfahren Sie mehr über die Verwendung von Handeingaben in [HoloLens (1. Generation)](hololens1-basic-usage.md#use-hololens-with-your-hands) und [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Beachten Sie, dass einige Handlangentypen bei der Handnachverfolgung nicht funktionieren, wenn Sie Hand tragen.  Ein häufiges Beispiel sind schwarze Handbänder, die dazu tendieren, Licht zu absorbieren und nicht von der Tiefenkamera aufgenommen werden.  Wenn Es bei Ihrer Arbeit um Handbänder geht, empfiehlt es sich, eine hellere Farbe wie Blau oder Grau zu versuchen.  Ein weiteres Beispiel sind große baggy-Handstücke, die dazu tendieren, die Form Ihrer Hand zu verbergen. Wir empfehlen die Verwendung von Handlangen, die so formanpassend wie möglich sind, um optimale Ergebnisse zu erzielen.

Wenn Ihr Visier Fingerabdrücke oder Smudges hat, verwenden Sie die Microfiber-Bereinigungsanlage, die mit der HoloLens stammt, um Ihr Visier sauber zu bereinigen.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens reagiert nicht auf meine Sprachbefehle

Wenn Cortana nicht auf Ihre Sprachbefehle reagiert, stellen Sie sicher, dass Cortana aktiviert ist. **Wählen** Sie in der Liste Alle Apps Cortana Menu Notebook Settings  >  **(Cortana-Menünotebookeinstellungen)**  >    >   aus, um Änderungen vorzunehmen. Weitere Informationen dazu, was Sie sagen können, finden Sie unter [Verwenden Ihrer Stimme mit HoloLens.](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Ich kann keine Hologramme platzieren oder Hologramme sehen, die ich zuvor platziert habe.

Wenn HoloLens Ihren Raum nicht zuordnen oder laden kann, wechselt er in den Eingeschränkten Modus, und Sie können keine Hologramme platzieren oder Hologramme sehen, die Sie platziert haben. Hier sind einige Dinge, die Sie ausprobieren können:

- Stellen Sie sicher, dass genügend Licht in Ihrer Umgebung vorhanden ist, damit HoloLens den Raum sehen und zuordnen kann.
- Stellen Sie sicher, dass Sie mit einem Wi-Fi Netzwerk verbunden sind. Wenn Sie nicht mit dem WLAN verbunden sind, kann HoloLens einen bekannten Bereich nicht identifizieren und laden.
- Wenn Sie einen neuen Bereich erstellen müssen, stellen Sie eine Wlan-Verbindung her, und starten Sie Dann Ihre HoloLens neu.
- Um festzustellen, ob der richtige Speicherplatz aktiv ist, oder um manuell ein Leerzeichen zu laden, wechseln Sie zu **Einstellungen**  >    >  **Systemräume**.
- Wenn der richtige Speicherplatz geladen wird und weiterhin Probleme auftreten, ist der Speicherplatz möglicherweise beschädigt. Um dieses Problem zu beheben, wählen Sie den Bereich und dann **Entfernen aus.** Nachdem Sie den Raum entfernt haben, beginnt HoloLens, Ihre Umgebung zu zuordnen und einen neuen Raum zu erstellen.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Meine HoloLens kann nicht erkennen, in welchem Raum ich bin.

Wenn Ihre HoloLens den Automatischen Speicherplatz nicht identifizieren und laden kann, überprüfen Sie die folgenden Faktoren:

- Stellen Sie sicher, dass Sie mit dem Wi-Fi
- Stellen Sie sicher, dass viel Licht im Raum zu sehen ist.
- Stellen Sie sicher, dass keine größeren Änderungen an der Umgebung vorgenommen wurden.

Sie können einen Bereich auch manuell laden oder Ihre Leerzeichen verwalten, indem Sie zu **Einstellungen**  >    >  **Systemräume .**

## <a name="im-getting-a-low-disk-space-error"></a>Ich habe den Fehler "Wenig Speicherplatz".

Sie müssen speicherplatzaufbewahren, indem Sie eine oder mehrere der folgenden Schritte tun:

- Löschen Sie einige nicht verwendete Leerzeichen. Wechseln Sie **zu Einstellungen**  >  **Systemräume,** wählen Sie ein Leerzeichen aus, das Sie nicht mehr  >  benötigen, und wählen Sie dann **Entfernen aus.**
- Entfernen Sie einige der Hologramme, die Sie platziert haben.
- Löschen Sie einige Bilder und Videos aus der Fotos-App.
- Deinstallieren Sie einige Apps von Ihrer HoloLens. Tippen **und Alle Apps** in der Liste Der Benutzer tippen und halten Sie die App, die Sie deinstallieren möchten, und wählen Sie dann Deinstallieren **aus.**

## <a name="my-hololens-cant-create-a-new-space"></a>Meine HoloLens kann keinen neuen Raum erstellen

Das wahrscheinlichste Problem ist, dass wenig Speicherplatz zur Verfügung steht. Probieren Sie einen der [vorherigen Tipps aus,](#im-getting-a-low-disk-space-error) um Speicherplatz frei zu geben.

## <a name="the-hololens-emulator-isnt-working"></a>Der HoloLens-Emulator funktioniert nicht

Informationen zum HoloLens-Emulator finden Sie in unserer Entwicklerdokumentation.  Erfahren Sie mehr über [die Problembehandlung für den HoloLens-Emulator.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
