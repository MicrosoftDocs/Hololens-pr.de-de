---
title: Häufig gestellte Fragen zu HoloLens Geräten und Hologrammen
description: Haben Sie eine kurze Frage zur HoloLens oder Interaktion mit Hologrammen?  Dieser Artikel bietet eine schnelle Antwort und weitere Ressourcen.
keywords: HoloLens, faq, bekanntes Problem, Hilfe
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032501"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Problembehandlung bei Hologramme und Interaktionen

In diesem Artikel werden Probleme beim Platzieren von Hologrammen, beim Arbeiten mit Leerzeichen und beim Melden von Problemen mit Hologrammen behandelt.

Stellen Sie immer dann sicher, dass Sie Probleme haben:
- Versuchen [Sie, ihn neu](hololens-restart-recover.md) zu starten, um zu sehen, ob dadurch Probleme behoben werden.
- Stellen Sie vor der Problembehandlung sicher, dass die HoloLens [in Rechnung gestellt](hololens2-charging.md) wird (mindestens eine Stunde). 


Verwenden Sie die Feedback-App, um uns Informationen zum Problem zu senden. Sie finden die Feedback-App im [ **Startmenü**](holographic-home.md). 

Tipps zum Tragen Ihrer HoloLens finden Sie unter [Anpassen der Anpassung von](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Neue Leerzeichen können nicht erstellt werden](#new-spaces-cant-be-created)
- [Leerzeichen können nicht identifiziert oder geladen werden.](#spaces-cant-be-identified-or-loaded)
- [Gewusst wie alle Leerzeichen löschen?](#how-do-i-delete-all-spaces)
- [Hologramme nicht richtig aussehen oder sich bewegen](#holograms-dont-look-right-or-are-moving-around)
- [Meldung "Finding your space" (Speicherplatz suchen)](#finding-your-space-message)
- [Erwartete Hologramme werden in meinem Raum nicht angezeigt](#expected-holograms-arent-showing-in-my-space)
- [Hologramme können nicht platziert oder zuvor platzierte Hologramme angezeigt werden](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramme verschwinden oder werden in andere Hologramme oder Objekte umschlossen.](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramme werden auf der anderen Seite einer Wand angezeigt.](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Nachdem ein Hologramm an einer Wand platziert wurde, scheint es gleitend zu sein.](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Apps werden nach dem Verschieben zu nah angezeigt](#apps-appear-too-close-after-moving-them)
- [Melden von Problemen mit instabilen oder ungenauen Hologrammen](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Neue Leerzeichen können nicht erstellt werden

Das wahrscheinlichste Problem ist, dass der Speicherplatz knapp wird. [Freigeben sie Speicherplatz,](hololens-troubleshooting.md#low-disk-space-error) und wiederholen Sie den Vorgang.

[Zurück zur Liste](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Leerzeichen können nicht identifiziert oder geladen werden.

Wenn Ihr HoloLens den Speicherplatz nicht automatisch identifizieren und laden kann, überprüfen Sie die folgenden Faktoren:

- Stellen Sie sicher, dass Sie mit Wi-Fi
- Stellen Sie sicher, dass im Raum ausreichend Licht vorhanden ist.
- Stellen Sie sicher, dass keine größeren Änderungen an der Umgebung vorgenommen wurden.

Sie können einen Bereich auch manuell laden oder Ihre Leerzeichen verwalten, indem Sie **zu Einstellungen** System spaces  >  **(Systemräume)**  >  gehen.

[Zurück zur Liste](#list)

## <a name="how-do-i-delete-all-spaces"></a>Gewusst wie alle Leerzeichen löschen?

*In Kürze verfügbar*

[Zurück zur Liste](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramme nicht richtig aussehen oder sich bewegen

Wenn Ihre Hologramme nicht richtig aussehen (z. B. sind sie jitterig oder unsicher, oder es werden schwarze Patches darüber angezeigt), probieren Sie eine der folgenden Fehlerbehebungen aus:

- [Bereinigen Sie ihr Gerätevisor,](hololens1-hardware.md#care-and-cleaning) und stellen Sie sicher, dass die Sensoren nicht blockiert werden.
- Stellen Sie sicher, dass Sie sich in einem gut beleuchteten Raum befinden, der nicht über viele direkte Würfe verfügt.
- Versuchen Sie, ihre Umgebung zu durchsuchen und zu durchsuchen, damit HoloLens sie vollständiger scannen können.
- Wenn Sie viele Hologramme platziert haben, entfernen Sie einige.

Wenn weiterhin Probleme auftreten, versuchen Sie, die Kalibrierungs-App auszuführen. Diese App kalibriert Ihre HoloLens nur für Sie, damit Ihre Hologramme optimal aussehen. Wechseln Sie hierzu zu **Einstellungen**  >  **System**  >  **Utilities**. Wählen Sie unter **Kalibrierung** die Option **Kalibrierung öffnen** aus.

[Zurück zur Liste](#list)

## <a name="finding-your-space-message"></a>Meldung "Finding your space" (Speicherplatz suchen)

Wenn HoloLens ein Leerzeichen lernt oder lädt, wird möglicherweise eine kurze Meldung mit der Meldung "Finding your space" angezeigt. Wenn diese Meldung mehr als einige Sekunden lang angezeigt wird, wird unter dem Startmenü eine weitere Meldung mit der Meldung "Still looking for your space" (Noch suchen nach Ihrem Platz) angezeigt.

Diese Nachrichten bedeuten, dass HoloLens Probleme beim Zuordnen Ihres Speicherplatzes haben. In diesem Fall können Sie Apps öffnen, aber keine Hologramme in Ihrer Umgebung platzieren.

Wenn diese Meldungen häufig angezeigt werden, versuchen Sie es mit einer oder mehreren der folgenden Fehlerbehebungen:

- Stellen Sie sicher, dass Sie sich in einem gut beleuchteten Raum befinden, der nicht über viele direkte Würfe verfügt.
- Stellen Sie sicher, dass Ihr Gerätevisier sauber ist. [Erfahren Sie, wie Sie Ihr Visor bereinigen.](hololens1-hardware.md#care-and-cleaning)
- Stellen Sie sicher, dass Sie über ein sicheres Wi-Fi Signal verfügen. Wenn Sie eine neue Umgebung ohne Wi-Fi oder ein schwaches Wi-Fi Signal eingeben, können HoloLens Ihren Speicherplatz nicht finden. Überprüfen Sie Ihre Wi-Fi Verbindung, indem **Sie zu Einstellungen** Network  >  **&amp; Internet**  >  **WI-Fi (Netzwerkinternet-WLAN)** gehen.
- Versuchen Sie, sich langsamer zu bewegen.

[Zurück zur Liste](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Erwartete Hologramme werden in meinem Raum nicht angezeigt

Wenn die von Ihnen platzierten Hologramme nicht angezeigt werden oder wenn Sie einige sehen, die Sie nicht erwarten, probieren Sie mindestens eine der folgenden Korrekturen aus:

- Aktivieren Sie einige Beleuchtungslichter. HoloLens funktioniert am besten in einem gut beleuchteten Raum.
- Entfernen Sie Hologramme, die Sie nicht benötigen, indem Sie **zu Einstellungen**  >  **System**  >  **Hologramme**  >  **Entfernen von Hologrammen in der Nähe** gehen. Oder wählen Sie bei Bedarf **Alle Hologramme entfernen aus.**

  > [!NOTE]
  > Wenn sich das Layout oder die Beleuchtung in Ihrem Raum erheblich ändert, kann es sein, dass Ihr Gerät Probleme beim Identifizieren Ihres Raums und beim Anzeigen ihrer Hologramme hat.

[Zurück zur Liste](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Hologramme können nicht platziert oder zuvor platzierte Hologramme angezeigt werden

Wenn HoloLens Ihren Raum nicht zuordnen oder laden können, wechselt er in den Eingeschränkten Modus, und Sie können keine Hologramme platzieren oder Hologramme sehen, die Sie platziert haben. Hier sind einige Dinge, die Sie ausprobieren können:

- Stellen Sie sicher, dass genügend Licht in Ihrer Umgebung vorhanden ist, damit HoloLens den Raum sehen und zuordnen können.
- Stellen Sie sich zwischen einem und drei Metern vom Ort ab, an dem Sie versuchen, das Hologramm zu platzieren.
- Platzieren Sie Hologramme nicht auf schwarzen oder reflektierenden Oberflächen.
- Stellen Sie sicher, dass Sie mit einem Wi-Fi Netzwerk verbunden sind. Wenn Sie nicht mit dem WLAN verbunden sind, können HoloLens einen bekannten Bereich nicht identifizieren und laden.
- Gehen Sie durch die Räume, damit HoloLens Ihre Umgebung erneut scannen können. Um zu sehen, was bereits gescannt wurde, tippen Sie in die Luft, um die Abbildung des Zuordnungsgitternetzes anzuzeigen.
- Wenn Sie einen neuen Bereich erstellen müssen, stellen Sie eine Verbindung mit dem WLAN her, und starten Sie ihre HoloLens neu.
- Um festzustellen, ob der richtige Speicherplatz aktiv ist, oder um manuell ein Leerzeichen zu laden, wechseln Sie zu **Einstellungen**  >    >  **Systemräume**.
- Wenn der richtige Speicherplatz geladen ist und weiterhin Probleme auftreten, ist der Speicherplatz möglicherweise beschädigt. Um dieses Problem zu beheben, wählen Sie den Bereich und dann **Entfernen aus.** Nachdem Sie den Bereich entfernt haben, beginnt HoloLens, Ihre Umgebung zuzuordnen und ein neues Leerzeichen zu erstellen.

[Zurück zur Liste](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramme verschwinden oder werden in andere Hologramme oder Objekte umschlossen.

Wenn Sie einem Hologramm zu nahe kommen, wird es vorübergehend nicht mehr angezeigt, &mdash; um das Hologramm wiederherzustellen. Verschieben Sie es einfach weg. Wenn Sie mehrere Hologramme nahe beieinander platziert haben, werden einige möglicherweise nicht mehr angezeigt. Versuchen Sie, einige zu entfernen.

Hologramme können auch durch andere Hologramme oder Objekte wie Wände blockiert oder umschlossen werden. Versuchen Sie in diesem Fall eine der folgenden Fehlerbehebungen:

- Wenn das Hologramm in einem anderen Hologramm umschlossen ist, verschieben Sie das umschlossene Hologramm an einen anderen Ort. Wählen Sie hierzu **Anpassen** aus, tippen Und halten Sie dann fest, um es zu positionieren.
- Wenn das Hologramm in einer Wand umschlossen ist, wählen **Sie Anpassen** aus, und gehen Sie dann zur Wand, bis das Hologramm angezeigt wird. Tippen Und halten Sie es, und ziehen Sie dann das Hologramm nach vorn und aus der Wand.
- Wenn Sie das Hologramm nicht mithilfe von Gesten verschieben können, verwenden Sie Ihre Stimme, um es zu entfernen. Sehen Sie sich das Hologramm an, und sagen Sie dann "Entfernen". Öffnen Sie dann das Hologramm erneut, und platzieren Sie es an einem neuen Speicherort.

[Zurück zur Liste](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramme auf der anderen Seite einer Wand angezeigt werden

Wenn Sie sich in der Nähe einer Wand befinden oder wenn HoloLens die Wand noch nicht gescannt hat, können Sie Hologramme sehen, die sich im nächsten Raum befinden. Um die Wand zu scannen, stehen Sie zwischen ein und drei Meter von der Wand und sehen sie an.

Ein schwarzes oder reflektierendes Objekt (z. B. eine schwarze Couch oder ein Tafelband) in der Nähe der Wand kann Probleme verursachen, wenn HoloLens versucht, die Wand zu scannen. Wenn ein solches Objekt vor liegt, scannen Sie die andere Seite der Wand.

[Zurück zur Liste](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Nachdem ein Hologramm an einer Wand platziert wurde, scheint es zu gleiten.

Ein Hologramm, das Sie an einer Wand platzieren, scheint in der Regel ein Zoll von der Wand entfernt zu sein. Wenn es weiter entfernt zu sein scheint, versuchen Sie mindestens eine der folgenden Korrekturen:

- Wenn Sie ein Hologramm an einer Wand platzieren, stehen Sie zwischen 1 und 3 Meter von der Wand, und zeigen Sie die Wand direkt an.
- Tippen Sie in der Luft auf die Wand, um die Abbildung des Kartengitters zu zeigen. Stellen Sie sicher, dass das Gitternetz an der Wand ausgerichtet ist. Wenn dies nicht der Wert ist, entfernen Sie das Hologramm, scannen Sie die Wand erneut, und versuchen Sie es dann erneut.
- Wenn das Problem weiterhin besteht, führen Sie die Kalibrierungs-App aus. Sie finden es in **Einstellungen**  >  **System**  >  **Utilities**.

[Zurück zur Liste](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Apps werden nach dem Verschieben zu nah angezeigt

Versuchen Sie, den Bereich zu durchsuchen, in dem Sie die App platzieren, damit HoloLens den Bereich aus unterschiedlichen Winkeln durchsucht. [Das Bereinigen des Gerätevisors](hololens1-hardware.md#care-and-cleaning) kann ebenfalls helfen.

[Zurück zur Liste](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Melden von Problemen mit instabilen oder unexact-Hologrammen
 
1. Bitte zeichnen Sie ein Mixed Reality-Aufnahme [video des](holographic-photos-and-videos.md#capture-a-mixed-reality-video) Problems auf. Dieses Video kann später über Feedback-Hub als angefügte Datei hochgeladen werden.  
1. Aktivieren Sie vollständige Telemetriedaten über die **Einstellungen-App** –> **Privacy** Diagnostics & Feedback, und stellen Sie unter Optionale Diagnosedaten sicher, dass die Umschaltung  ->   auf Ein **festgelegt ist.** 
1. Erhalten Sie die neuesten Fixes für Hologrammskala und Stabilität, indem Sie auf das neueste Windows [Holographic OS (20H2 oder höher) aktualisieren.](hololens-release-notes.md#windows-holographic-version-20h2) Führen Sie nach dem Aktualisieren Folgendes aus:
    1. Entfernen Sie alle Hologramme über **Einstellungen-App** -> **System** Hologramme -> und wählen Sie dann  ->   **Alle Hologramme** entfernen aus, und beginnen Sie mit einer neuen Karte.
    1. Erstellen Sie eine neue Karte Ihres Raumes, indem Sie die HoloLens, ihren Raum durchgehen und sich alle Bereiche und Oberflächen im Raum ansehen. Dies ist zwei bis drei Minuten lang der Fall.
    1. Führen Sie die IPD-Kalibrierung durch. Wechseln Sie **zu Einstellungen**  >    >  **Systemprogramme**. Wählen Sie **unter Kalibrierung** die Option **Kalibrierung öffnen aus.**
    1. Testen Sie das Szenario erneut, und prüfen Sie, ob es weiterhin besteht.
1. Wenn das Problem durch das Aktualisieren nicht behoben wird, melden Sie ein Feedback-Hub [Problem.](hololens-feedback.md) Nachdem Sie Feedback gesendet haben,  können Sie die Schaltfläche Freigeben verwenden, um einen einfach zu teilenden Link zu erstellen, der gesendet werden kann, wenn Sie sich an den Support wenden.

[Zurück zur Liste](#list)