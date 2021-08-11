---
title: Häufig gestellte Fragen zu HoloLens und Hologrammen
description: Haben Sie eine kurze Frage zu HoloLens interaktion mit Hologrammen?  Dieser Artikel bietet eine schnelle Antwort und weitere Ressourcen.
keywords: hololens, faq, bekanntes Problem, Hilfe
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
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664620"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramme und Interaktionen: Problembehandlung

In diesem Artikel werden Probleme beim Platzieren von Hologrammen, beim Arbeiten mit Leerzeichen und beim Melden von Problemen mit Hologrammen behandelt.

Stellen Sie bei jedem Auftreten von Problemen Sicher, dass:
- Versuchen [Sie, es neu zu](hololens-restart-recover.md) starten, um festzustellen, ob dies Probleme behebt.
- Stellen Sie vor der Problembehandlung sicher, dass HoloLens Ab [rechnung](hololens2-charging.md) gestellt wird (in Rechnung gestellt für mindestens eine Stunde). 


Verwenden Sie die Feedback-App, um uns Informationen zum Problem zu senden. Sie finden die Feedback-App im [ **Startmenü.**](holographic-home.md) 

Tipps zum Tragen Ihrer HoloLens finden Sie unter Anpassen der [Anpassung.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [Neue Leerzeichen können nicht erstellt werden](#new-spaces-cant-be-created)
- [Leerzeichen können nicht identifiziert oder geladen werden.](#spaces-cant-be-identified-or-loaded)
- [Gewusst wie alle Leerzeichen löschen?](#how-do-i-delete-all-spaces)
- [Hologramme nicht richtig aussehen oder sich bewegen](#holograms-dont-look-right-or-are-moving-around)
- [Meldung "Finding your space" (Suchen ihres Speicherplatzes)](#finding-your-space-message)
- [Erwartete Hologramme werden in meinem Raum nicht angezeigt](#expected-holograms-arent-showing-in-my-space)
- [Hologramme können nicht platziert oder zuvor platzierte Hologramme nicht zu sehen sein.](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramme oder werden in andere Hologramme oder Objekte umgehst](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramme auf der anderen Seite einer Wand angezeigt werden](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Nachdem ein Hologramm an einer Wand platziert wurde, scheint es zu gleiten.](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Apps werden nach dem Verschieben zu nah angezeigt](#apps-appear-too-close-after-moving-them)
- [Melden von Problemen mit instabilen oder unexact-Hologrammen](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Neue Leerzeichen können nicht erstellt werden

Das wahrscheinlichste Problem ist, dass wenig Speicherplatz zur Verfügung steht. [Geben Sie Speicherplatz auf dem Datenträger frei,](hololens-troubleshooting.md#low-disk-space-error) und wiederholen Sie den Vorgang.

[Zurück zur Liste](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Leerzeichen können nicht identifiziert oder geladen werden.

Wenn Ihr HoloLens den Automatischen Speicherplatz nicht identifizieren und laden kann, überprüfen Sie die folgenden Faktoren:

- Stellen Sie sicher, dass Sie mit dem Wi-Fi
- Stellen Sie sicher, dass viel Licht im Raum zu sehen ist.
- Stellen Sie sicher, dass keine größeren Änderungen an der Umgebung vorgenommen wurden.

Sie können einen Bereich auch manuell laden oder Ihre Leerzeichen verwalten, indem Sie Einstellungen System spaces  >  **(Systemplätze)**  >  **ausführen.**

[Zurück zur Liste](#list)

## <a name="how-do-i-delete-all-spaces"></a>Gewusst wie alle Leerzeichen löschen?

*Bald verfügbar*

[Zurück zur Liste](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramme nicht richtig aussehen oder sich bewegen

Wenn Ihre Hologramme nicht richtig aussehen (z. B. jittery oder shaky, oder Sie sehen schwarze Patches darauf), probieren Sie eine der folgenden Korrekturen aus:

- [Bereinigt das Gerätevisor](hololens1-hardware.md#care-and-cleaning) und vergewissert sich, dass die Sensoren nicht blockiert werden.
- Stellen Sie sicher, dass Sie sich in einem gut erlichteten Raum mit nicht vielen direkten Direktbeendingen befindet.
- Versuchen Sie, in Ihrer Umgebung zu laufen und zu nieren, HoloLens Sie sie vollständig überprüfen können.
- Wenn Sie viele Hologramme platziert haben, versuchen Sie, einige zu entfernen.

Wenn weiterhin Probleme auftreten, versuchen Sie, die Kalibrierungs-App zu verwenden. Diese App kalibriert Ihre HoloLens nur für Sie, damit Ihre Hologramme optimal aussehen. Um dies zu tun, wechseln Sie zu **Einstellungen**  >  **System**  >  **utilities**. Wählen Sie **unter Kalibrierung** die Option **Kalibrierung öffnen aus.**

[Zurück zur Liste](#list)

## <a name="finding-your-space-message"></a>Meldung "Finding your space" (Suchen ihres Speicherplatzes)

Wenn HoloLens ein Leerzeichen lernt oder lädt, wird möglicherweise eine kurze Meldung mit dem Text "Finding your space" (Suchen ihres Speicherplatzes) angezeigt. Wenn diese Meldung länger als ein paar Sekunden angezeigt wird, wird eine weitere Meldung unter dem Startmenü angezeigt, die besagt, dass noch nach Ihrem Speicherplatz gesucht wird.

Diese Meldungen bedeuten, dass HoloLens Probleme beim Zuordnen Ihres Speicherplatzes hat. In diesem Fall können Sie Apps öffnen, jedoch keine Hologramme in Ihrer Umgebung platzieren.

Wenn diese Meldungen häufig angezeigt werden, probieren Sie eine oder mehrere der folgenden Fehlerbehebungen aus:

- Stellen Sie sicher, dass Sie sich in einem gut erlichteten Raum mit nicht vielen direkten Direktbeendingen befindet.
- Stellen Sie sicher, dass Ihr Gerätevisor bereinigt ist. [Erfahren Sie, wie Sie Ihr Visor bereinigt.](hololens1-hardware.md#care-and-cleaning)
- Stellen Sie sicher, dass Sie über ein starkes Wi-Fi verfügen. Wenn Sie eine neue Umgebung ohne Wi-Fi oder ein schwaches signalisiertes Wi-Fi, kann HoloLens den Speicherplatz nicht finden. Überprüfen Sie Wi-Fi Verbindung, indem Sie **Einstellungen**  >  **&amp; Netzwerk-Internet-WLAN**  >  **verwenden.**
- Versuchen Sie, sich langsamer zu bewegen.

[Zurück zur Liste](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Erwartete Hologramme werden in meinem Raum nicht angezeigt

Wenn Die von Ihnen platzierten Hologramme nicht oder nicht zu erwartende Hologramme nicht zu sehen sind, probieren Sie eine oder mehrere der folgenden Korrekturen aus:

- Schalten Sie einige Lichtlichter ein. HoloLens funktioniert am besten in einem gut erlichteten Raum.
- Entfernen Sie Hologramme, die Sie nicht benötigen, indem Sie Einstellungen System Hologramme Entfernen von hologrammen in  >    >    >  **der Nähe.** Oder wählen Sie bei Bedarf **Alle Hologramme entfernen aus.**

  > [!NOTE]
  > Wenn sich das Layout oder die Beleuchtung in Ihrem Raum erheblich ändert, hat Ihr Gerät möglicherweise Probleme, Ihren Raum zu identifizieren und Ihre Hologramme zu zeigen.

[Zurück zur Liste](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Hologramme können nicht platziert oder zuvor platzierte Hologramme nicht zu sehen sein.

Wenn HoloLens Raum nicht zuordnen oder laden kann, wird er in den Eingeschränkten Modus wechseln, und Sie können keine Hologramme platzieren oder Hologramme sehen, die Sie platziert haben. Hier sind einige Dinge, die Sie ausprobieren sollten:

- Stellen Sie sicher, dass in Ihrer Umgebung genügend Licht vorhanden ist, damit HoloLens den Raum sehen und zuordnen können.
- Stehen Sie zwischen 1 und 3 Meter von dem Ort, an dem Sie versuchen, das Hologramm zu platzieren.
- Platzieren Sie Hologramme nicht auf schwarzen oder reflektierenden Oberflächen.
- Stellen Sie sicher, dass Sie mit einem Netzwerk Wi-Fi sind. Wenn Sie nicht mit dem WLAN verbunden sind, HoloLens einen bekannten Bereich nicht identifizieren und laden.
- Gehen Sie durch die Räume, HoloLens Sie Ihre Umgebung erneut einscannen können. Um zu sehen, was bereits gescannt wurde, tippen Sie in die Luft, um die Abbildung des Kartengitters zu zeigen.
- Wenn Sie einen neuen Bereich erstellen müssen, stellen Sie eine Verbindung mit dem WLAN-Gerät herstellen und dann Ihre HoloLens.
- Um zu sehen, ob der richtige Speicherplatz aktiv ist, oder um einen Bereich manuell zu laden, wechseln Sie zu **Einstellungen**  >  **System**  >  **Spaces**.
- Wenn der richtige Speicherplatz geladen wird und weiterhin Probleme auftreten, ist der Speicherplatz möglicherweise beschädigt. Um dieses Problem zu beheben, wählen Sie den Bereich und dann **Entfernen aus.** Nachdem Sie den Raum entfernt haben, beginnt HoloLens, Ihre Umgebung zu zuordnen und einen neuen Raum zu erstellen.

[Zurück zur Liste](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramme oder werden in andere Hologramme oder Objekte umgehst

Wenn Sie einem Hologramm zu nahe kommen, verschwindet es vorübergehend, um das &mdash; Hologramm wiederherzustellen, und entfernt es einfach. Wenn Sie mehrere Hologramme nah beieinander platziert haben, werden einige möglicherweise nicht mehr zusammenfallen. Versuchen Sie, einige zu entfernen.

Hologramme kann auch durch andere Hologramme oder Objekte wie Wände blockiert oder umhinget werden. Versuchen Sie in diesem Fall eine der folgenden Korrekturen:

- Wenn das Hologramm in ein anderes Hologramm umhinget ist, verschieben Sie das umhingierte Hologramm an eine andere Position. Wählen Sie hierzu Anpassen **aus,** tippen Sie dann auf , und halten Sie ihn an, um ihn zu positionieren.
- Wenn das Hologramm in einer Wand umhinget ist, wählen Sie Anpassen aus, und gehen Sie dann zur Wand, bis das Hologramm angezeigt wird.  Tippen und halten Sie es, und ziehen Sie dann das Hologramm nach vorn und von der Wand.
- Wenn Sie das Hologramm nicht mithilfe von Gesten verschieben können, verwenden Sie Ihre Stimme, um es zu entfernen. Sehen Sie sich das Hologramm an, und sagen Sie dann "Entfernen". Öffnen Sie dann das Hologramm erneut, und platzieren Sie es an einer neuen Position.

[Zurück zur Liste](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramme werden auf der anderen Seite einer Wand angezeigt.

Wenn Sie sich sehr nah an einer Wand befinden oder HoloLens die Wand noch nicht gescannt hat, können Sie Hologramme sehen, die sich im nächsten Raum befinden. Um die Wand zu scannen, stehen Sie zwischen einem und drei Meter von der Wand entfernt, und sehen Sie sie an.

Ein schwarzes oder reflektierendes Objekt (z. B. eine schwarze Couch oder ein Metallregen), das sich in der Nähe der Wand befindet, kann Probleme verursachen, wenn HoloLens versucht, die Wand zu scannen. Wenn ein solches Objekt vorhanden ist, überprüfen Sie die andere Seite der Wand.

[Zurück zur Liste](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Nachdem ein Hologramm an einer Wand platziert wurde, scheint es gleitend zu sein.

Ein Hologramm, das Sie an einer Wand platzieren, scheint in der Regel ein Zoll oder so weit von der Wand entfernt zu sein. Versuchen Sie es mit einem oder mehreren der folgenden Fehlerbehebungen, wenn sie weiter entfernt zu sein scheint:

- Wenn Sie ein Hologramm an einer Wand platzieren, stehen Sie zwischen einem und drei Meter von der Wand entfernt, und stellen Sie die Wand geradeaus.
- Tippen Sie in die Luft auf die Wand, um die Kartengitternetzgrafik zu zeigen. Stellen Sie sicher, dass das Gitternetz an der Wand ausgerichtet ist. Entfernen Sie andernfalls das Hologramm, scannen Sie die Wand erneut, und versuchen Sie es dann erneut.
- Wenn das Problem weiterhin besteht, führen Sie die Kalibrierungs-App aus. Sie finden es in **Einstellungen**  >  **System**  >  **Utilities**.

[Zurück zur Liste](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Apps werden nach dem Verschieben zu nah angezeigt

Versuchen Sie, den Bereich zu betrachten, in dem Sie die App platzieren, sodass HoloLens den Bereich aus verschiedenen Winkeln scannt. Das [Bereinigen des Gerätevisors](hololens1-hardware.md#care-and-cleaning) kann ebenfalls hilfreich sein.

[Zurück zur Liste](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Melden von Problemen mit instabilen oder ungenauen Hologrammen
 
1. Noten Sie sich das Problem und ein [Mixed Reality-Aufnahme Video.](holographic-photos-and-videos.md#capture-a-mixed-reality-video) Dieses Video kann später über Feedback-Hub als angefügte Datei hochgeladen werden.  
1. Aktivieren Sie vollständige Telemetriedaten über die **Einstellungen-App** >   ->  **Datenschutzdiagnose & Feedback,** und stellen Sie unter **Optionale Diagnosedaten** sicher, dass der Umschalter auf **Ein** festgelegt ist.
1. Erhalten Sie die neuesten Fehlerbehebungen für die Hologrammsskala und Stabilität, indem Sie auf die neueste [Windows Holographic OS (20H2 oder höher)](hololens-release-notes.md#windows-holographic-version-20h2)aktualisieren. Führen Sie nach dem Aktualisieren Folgendes aus:
    1. Entfernen Sie alle Hologramme über **Einstellungen** App -> **System**  ->  **Hologramme** -> wählen Sie dann **Alle Hologramme entfernen** aus, und beginnen Sie mit einer neuen Karte.
    1. Erstellen Sie eine neue Karte Ihres Raums, indem Sie die HoloLens verwenden, durch Ihren Raum gehen und alle Bereiche und Oberflächen im Raum betrachten. Tun Sie dies 2 bis 3 Minuten.
    1. Durchführen der IPD-Kalibrierung. Wechseln Sie zu **Einstellungen**  >  **System**  >  **Utilities**. Wählen Sie unter **Kalibrierung** die Option **Kalibrierung öffnen** aus.
    1. Testen Sie das Szenario erneut, und überprüfen Sie, ob es weiterhin besteht.
1. Wenn das Problem durch das Aktualisieren nicht behoben wird, melden Sie eine [Feedback-Hub Problem.](hololens-feedback.md) Nachdem Sie Feedback ausgefüllt haben, können Sie die Schaltfläche **Freigeben** verwenden, um einen einfach zu teilenden Link zu erstellen, der gesendet werden kann, wenn Sie sich an den Support wenden.

[Zurück zur Liste](#list)