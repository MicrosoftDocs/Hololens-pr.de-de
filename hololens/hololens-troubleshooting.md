---
title: Problembehandlung
description: Bleiben Sie auf dem Laufenden über die gängigsten Lösungen für HoloLens-Geräteprobleme und -Problembehandlungstechniken.
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
keywords: Probleme, Fehler, Problembehandlung, Beheben, Hilfe, Support, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283046"
---
# Problembehandlung

In diesem Artikel wird beschrieben, wie Sie mehrere häufige Probleme mit HoloLens beheben.

## Meine HoloLens reagiert nicht oder wird nicht gestartet

Wenn Ihre HoloLens nicht gestartet wird:

- Wenn die LEDs neben dem Netzschalter nicht aufleuchten oder nur eine LED kurz blinkt, müssen Sie Ihre [HoloLens möglicherweise aufladen.](hololens-recovery.md#charge-the-device)
- Wenn die LEDs aufleuchten, wenn Sie den Netzschalter drücken, aber nichts auf den Displays angezeigt wird, setzen Sie das Gerät vorab fest [zurück.](hololens-recovery.md#hard-reset-procedure)

Wenn Ihre HoloLens eingefroren wird oder nicht mehr reagiert:

- Schalten Sie Ihre HoloLens aus, indem Sie den Netzschalter drücken, bis sich alle fünf LEDs selbst ausschalten, oder 15 Sekunden lang, wenn die LEDs nicht reagieren. Um Ihre HoloLens zu starten, drücken Sie erneut den Netzschalter.

Wenn diese Schritte nicht funktionieren, können Sie versuchen, Ihr [HoloLens 2-](hololens-recovery.md) oder [HoloLens -Gerät (1. Generation) wiederhergestellt.](hololens1-recovery.md)

## Hologramme sehen nicht gut aus

Wenn Ihre Hologramme instabil, sprunghaft oder nicht richtig aussehen, versuchen Sie es:

- Bereinigen des Visiers und der Sensorleiste des Geräts auf der Vorderseite Ihrer HoloLens.
- Erhöhen des Lichts in Ihrem Raum.
- Gehen Sie umher und schauen Sie sich Ihre Umgebung an, damit HoloLens sie vollständig scannen kann.
- Kalibrieren Ihrer HoloLens für Ihre Augen. Wechseln Sie zu **Settings**  >  **System**  >  **Utilities**. Wählen Sie unter **Kalibrierung** die Option **Kalibrierung öffnen** aus.
 
### Melden von Problemen, bei denen Hologramme instabil sind oder nicht richtig aussehen
 
1. Bitte zeichnen Sie das Problem mit einem [Mixed Reality Capture-Video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) auf. Dieses Video kann später über den Feedback Hub als angefügte Datei hochgeladen werden.  
1. Aktivieren Sie die **** vollständige Telemetrie über **** die App "Einstellungen> Datenschutzdiagnose & Feedback und stellen Sie unter "Optionale Diagnosedaten" sicher, dass die Umschalteinstellung auf  ->  **** "Ein" **festgelegt ist.** ****
1. Erhalten Sie die neuesten Korrekturen für Hologramme und Stabilität, indem Sie auf das neueste [Windows Holographic-Betriebssystem (20H2 oder höher) aktualisieren.](hololens-release-notes.md#windows-holographic-version-20h2) Führen Sie nach der Aktualisierung folgendes aus:
    1. Entfernen Sie alle **** Hologramme über die Einstellungs-App -> **System**  ->  **holograms** -> wählen Sie dann "Alle **Hologramme** entfernen" aus, und beginnen Sie mit einer neuen Karte.
    1. Erstellen Sie eine neue Karte Ihres Raums, indem Sie die HoloLens tragen und ihren Raum umgehen und alle Bereiche und Oberflächen im Raum ansehen. Tun Sie dies für 2 bis 3 Minuten.
    1. Durchführen der IPD-Kalibrierung. Wechseln Sie zu **Settings**  >  **System**  >  **Utilities**. Wählen Sie unter **Kalibrierung** die Option **Kalibrierung öffnen** aus.
    1. Testen Sie das Szenario erneut, und prüfen Sie, ob es weiterhin besteht.
1. Wenn das Problem durch das Aktualisieren nicht behoben wird, melden Sie bitte ein [Feedback-Hub-Problem an.](hololens-feedback.md) Nachdem Sie Feedback gegeben haben, **** können Sie die Schaltfläche "Freigeben" verwenden, um einen einfach zu teilenden Link zu erstellen, der beim Kontaktieren des Support gesendet werden kann.

## HoloLens reagiert nicht auf Handeingaben

Um sicherzustellen, dass HoloLens Ihre Hände sehen kann, müssen Sie sie im Gestenrahmen behalten.  Das Mixed Reality Home bietet Feedback, mit dem Sie wissen können, wann Ihre Hände nachverfolgt werden.  Das Feedback ist für verschiedene Versionen von HoloLens unterschiedlich:
- Auf HoloLens (1. Generation) ändert sich der Blickcursor von einem Punkt in einen Ring.
- Auf HoloLens 2 wird ein Fingerspitzencursor angezeigt, wenn sich Ihre Hand in der Nähe eines Schiefers befindet, und ein Handstrahl wird angezeigt, wenn schiefer weiter weg sind.

Viele immersive Apps folgen Eingabemustern, die Mixed Reality Home ähneln.  Erfahren Sie mehr über die Verwendung von Handeingaben auf [HoloLens (1. Generation)](hololens1-basic-usage.md#use-hololens-with-your-hands) und [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Beachten Sie, dass einige Arten von Brillen nicht mit der Handverfolgung verwendet werden können.  Ein gängiges Beispiel ist die Schwarze Dämpfung, die infrarotes Licht auffangen und nicht von der Tiefenkamera aufgenommen werden.  Wenn Ihre Arbeit eine Farbigung umfasst, empfehlen wir, eine hellere Farbe wie Blau oder Grau zu verwenden.  Ein weiteres Beispiel ist eine große Baggy-Brille, die in der Regel die Form Ihrer Hand verschleiert. Es wird empfohlen, möglichst gute Formanpassungen zu verwenden, um optimale Ergebnisse zu erzielen.

Wenn Ihr Visier Fingerabdrücke oder Wischen hat, verwenden Sie das Mikrofiber-Bereinigungstuch, das im HoloLens-Gerät zur Verfügung steht, um Ihr Visier vorsichtig zu reinigen.

## HoloLens reagiert nicht auf meine Sprachbefehle.

Wenn Cortana nicht auf Ihre Sprachbefehle reagiert, stellen Sie sicher, dass Cortana aktiviert ist. Wählen Sie in der Liste "Alle Apps" die **Einstellungen**des  >  ****  >  **Cortana-Menünotizbuchs**  >  **aus,** um Änderungen vorzunehmen. Weiter Informationen dazu, was Sie sagen können, finden Sie unter [Verwenden Sie Ihre Stimme mit HoloLens](hololens-cortana.md).

## Ich kann keine Hologramme platzieren oder Hologramme sehen, die ich zuvor platziert habe.

Wenn HoloLens Ihren Raum nicht karten oder laden kann, wechselt es in den eingeschränkten Modus, und Sie können keine Hologramme platzieren oder Hologramme sehen, die Sie platziert haben. Probieren Sie Folgendes aus:

- Stellen Sie sicher, dass in Ihrer Umgebung genügend Licht zur Verfügung ist, damit HoloLens den Raum sehen und zuordnungen kann.
- Stellen Sie sicher, dass Sie mit einem Wi-Fi verbunden sind. Wenn Sie nicht mit dem WLAN verbunden sind, kann HoloLens einen bekannten Raum nicht identifizieren und laden.
- Wenn Sie einen neuen Raum erstellen müssen, stellen Sie eine Verbindung mit dem WLAN auf, und starten Sie Ihre HoloLens neu.
- Wenn Sie sehen möchten, ob der richtige Speicherplatz aktiv **** ist, oder um ein Leerzeichen manuell zu laden, wechseln Sie zu  >  **"Systemplätze**für  >  **Einstellungen".**
- Wenn der richtige Speicherplatz geladen wird und weiterhin Probleme auftreten, ist der Speicherplatz möglicherweise beschädigt. Um dieses Problem zu beheben, wählen Sie das Leerzeichen aus, und wählen Sie dann **"Entfernen" aus.** Nachdem Sie den Raum entfernt haben, beginnt HoloLens, Ihre Umgebung zu mapn und einen neuen Raum zu erstellen.

## My HoloLens can't tell what space I'm in

Wenn Ihre HoloLens den Platz, in dem Sie sich automatisch ein- und laden können, nicht identifizieren und laden kann, überprüfen Sie die folgenden Faktoren:

- Stellen Sie sicher, dass Sie mit dem Wi-Fi
- Stellen Sie sicher, dass viel Licht im Raum vorhanden ist.
- Stellen Sie sicher, dass keine größeren Änderungen an der Umgebung vorgenommen wurden.

Sie können ein Leerzeichen auch manuell laden oder Ihre Leerzeichen verwalten, indem Sie **zu**Einstellungen  >  **"Systemplätze"**  >  **gehen.**

## I'm getting a "low disk space" error

Sie müssen Speicherplatz frei machen, indem Sie eine oder mehrere der folgenden Schritte tun:

- Löschen Sie einige nicht verwendete Leerzeichen. Wechseln Sie **zu "Systemplätze**für Einstellungen", wählen Sie ein nicht mehr benötigtes Leerzeichen aus, und wählen Sie  >  ****  >  **** dann **"Entfernen" aus.**
- Entfernen Sie einige der Hologramme, die Sie platziert haben.
- Löschen Sie einige Bilder und Videos aus der Fotos App.
- Deinstallieren Sie einige Apps von Ihrer HoloLens. Tippen und **halten Sie in** der Liste "Alle Apps" die App, die Sie deinstallieren möchten, und wählen Sie dann **"Deinstallieren" aus.**

## Meine HoloLens kann keinen neuen Raum erstellen

Das wahrscheinlichste Problem ist, dass der Speicherplatz knapp wird. Probieren Sie einen der [vorherigen Tipps aus,](#im-getting-a-low-disk-space-error) um Speicherplatz frei zu geben.

## Der HoloLens-Emulator funktioniert nicht

Informationen zum HoloLens-Emulator finden Sie in unserer Entwicklerdokumentation.  Erfahren Sie mehr über [die Problembehandlung für den HoloLens-Emulator.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
