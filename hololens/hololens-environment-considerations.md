---
title: Überlegungen zur HoloLens-Umgebung
description: Erzielen Sie die bestmögliche Erfahrung mit HoloLens, indem Sie das Gerät für Ihre Augen und Umgebung optimieren.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: Holografischer Rahmen, Sichtfeld, Kalibrierung, Räume, Umgebung, Hilfe und Anleitung, HoloLens, Mixed Reality, Mixed Reality-Headsets
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428615"
---
# <a name="hololens-environment-considerations"></a>Überlegungen zur HoloLens-Umgebung

HoloLens verbindet die holografische mit der „realen“ Welt und platziert Hologramme in Ihrer Umgebung. Das Fenster einer holografischen Anwendung „hängt“ an der Wand, eine holografische Ballerina dreht sich auf der Tischplatte oder Hasenohren befinden sich auf dem Kopf Ihres ahnungslosen Freunds. Wenn Sie ein immersives Spiel oder eine App nutzen, breitet sich die holografische Welt aus, um Ihre Umgebung zu füllen, aber Sie können den Raum immer noch sehen und sich darin bewegen.

Die von Ihnen platzierten Hologramme bleiben an der Stelle, an der Sie sie platziert haben, auch wenn Sie Ihr Gerät ausschalten.

## <a name="setting-up-an-environment"></a>Einrichten einer Umgebung

HoloLens-Geräte können stabile und genaue Hologramme platzieren, indem sie Benutzer in einem Raum *verfolgen*. Ohne entsprechende Verfolgung versteht das Gerät weder die Umgebung noch den Benutzer darin. Hologramme können an den falschen Stellen erscheinen, nicht immer an der gleichen Stelle erscheinen oder überhaupt nicht erscheinen. Die zum Verfolgen der Benutzer verwendeten Daten werden in der *räumlichen Karte* dargestellt.  

Die Leistung bei der Verfolgung ist stark von der Umgebung abhängig, in der sich der Benutzer befindet. Die Optimierung einer Umgebung für eine zuverlässige, konsistente Verfolgung ist eher eine Kunst als eine Wissenschaft. Viele verschiedene Umgebungsfaktoren werden miteinander verschmolzen, um die Verfolgung zu ermöglichen, aber als Mixed Reality-Entwickler gibt es einige Faktoren, die Sie im Auge behalten können, um einen Raum für eine bessere Verfolgung zu optimieren.

### <a name="lighting"></a>Beleuchtung

Windows Mixed Reality nutzt sichtbares Licht, um die Position des Benutzers zu verfolgen. Wenn eine Umgebung zu hell ist, können die Kameras gesättigt werden, sodass nichts zu sehen ist. Wenn die Umgebung zu dunkel ist, können die Kameras nicht genügend Informationen erfassen, sodass nichts zu sehen ist. Die Beleuchtung sollte gleichmäßig und ausreichend hell sein, sodass ein Mensch ohne Anstrengung sehen kann, aber nicht so hell, dass das Betrachten des Lichts schmerzhaft ist.  

Bereiche mit hellen Lichtpunkten in einem insgesamt dämmrigen Bereich sind ebenfalls problematisch, da die Kamera sich anpassen muss, wenn sie in helle Bereiche hinein- und wieder herausfährt. Dies kann dazu führen, dass das Gerät „sich verirrt“ und davon ausgeht, dass die Lichtänderung eine Standortänderung bedeutet. Stabile Beleuchtungspegel in einem Bereich führen zu einer besseren Verfolgung.  

Auch jegliche Außenbeleuchtung kann zu Instabilitäten bei der Verfolgung führen, da das Sonnenlicht im Lauf der Zeit stark variieren kann. Zum Beispiel kann die Nachverfolgung im gleichen Raum im Sommer gegenüber dem Winter zu drastisch unterschiedlichen Ergebnissen führen, da das passive Licht draußen zu verschiedenen Jahreszeiten stärker sein kann.  

Wenn Sie einen Beleuchtungsmesser haben, sind stabile 500 bis 1.000 Lux ein guter Ausgangspunkt.  

#### <a name="types-of-lighting"></a>Arten von Beleuchtung

Auch verschiedene Arten von Beleuchtung in einem Raum können die Verfolgung beeinflussen. Glühlampen pulsieren mit dem durch sie fließenden Wechselstrom. Wenn die Wechselstromfrequenz 50 Hz beträgt, dann pulsiert auch das Licht mit 50 Hz. Menschen nehmen dieses Pulsieren nicht wahr. Die 30-FPS-Kamera der HoloLens nimmt diese Änderungen jedoch wahr. Einige Einzelbilder werden gut, andere schlecht beleuchtet und wieder andere überbelichtet sein, da die Kamera versucht, die Lichtpulse auszugleichen.  

In den USA ist die Stromfrequenz standardmäßig 60 Hz, sodass die Glühlampenpulse auf die Bildfrequenz der HoloLens abgestimmt sind. 60-Hz-Pulse entsprechen der Bildfrequenz von 30 FPS der HoloLens. Viele Länder haben jedoch eine standardmäßige Wechselstromfrequenz von 50 Hz, was bedeutet, dass einige HoloLens-Bilder während der Pulse aufgenommen werden und andere nicht. Insbesondere fluoreszierende Beleuchtung in Europa verursacht Probleme.  

Es gibt einige Dinge, die Sie zum Beheben von Flackern ausprobieren können. Temperatur, Alter der Glühlampe und Aufwärmzyklen sind häufige Ursachen für fluoreszierendes Flackern. Daher kann es unter Umständen helfen, Glühlampen auszutauschen. Das Festziehen von Glühlampen und Sicherstellen einer konstanten Stromaufnahme können ebenfalls helfen.  

### <a name="items-in-a-space"></a>Objekte in einem Raum

HoloLens verwendet eindeutige Orientierungspunkte in der Umgebung, die auch als *Features* bezeichnet werden, um sich selbst in einem Raum zu lokalisieren.  

In einem Bereich, in dem es kaum Features gibt, ist einem Gerät die Verfolgung kaum möglich, da es keine Möglichkeit hat zu wissen, wo es sich im Raum befindet. Sie können die Verfolgung verbessern, indem Sie Features an den Wänden eines Raums anbringen. Poster, Symbole, die an die Wand geklebt werden, Pflanzen, ungewöhnliche Gegenstände oder ähnliches sind hilfreich. Ein unordentlicher Schreibtisch ist ein gutes Beispiel für eine Umgebung, die zu einer guten Verfolgung führt, da sich viele verschiedene Features in einem einzigen Bereich befinden.  

Verwenden Sie darüber hinaus zusätzlich unterschiedliche Features im gleichen Raum. Wenn z. B. an einer Wand mehrfach das gleiche Poster hängt, stiftet dies Verwirrung, da HoloLens nicht weiß, welches der sich wiederholenden Poster es gerade sieht. Eine gängige Methode zum Hinzufügen besonderer Features ist die Verwendung von Kreppband. Damit können Sie eindeutige, sich nicht wiederholende Muster entlang der Wände und des Bodens eines Raums anbringen.  

Sie sollten sich einfach folgende Frage stellen: Wenn Sie nur einen kleinen Teil einer Szenerie sehen würden, könnten Sie sich im Raum eindeutig lokalisieren? Falls nicht, wird das Gerät wahrscheinlich auch Probleme mit der Verfolgung haben.

#### <a name="wormholes"></a>Wurmlöcher

Wenn Sie zwei Bereiche haben, die gleich aussehen, denkt die Verfolgungsfunktion womöglich, dass sie identisch sind. Und dies führt dazu, dass das Gerät fälschlicherweise davon ausgeht, es wäre an einem anderen Ort. Wir nennen diese Arten sich wiederholender Bereiche *Wurmlöcher*.  

Um Wurmlöcher zu vermeiden, versuchen Sie, identische Bereiche im gleichen Raum zu vermeiden. Zu identischen Bereichen gehören mitunter Fabrikanlagen, Fenster an einem Gebäude, Serverracks oder Arbeitsstationen. Das Beschriften von Bereichen oder Hinzufügen eindeutiger Features zu jedem ähnlich aussehenden Bereich kann helfen, Wurmlöcher zu minimieren.

### <a name="movement-in-a-space"></a>Bewegung in einem Raum

Wenn sich Ihre Umgebung ständig bewegt und ändert, hat das Gerät keine stabilen Features, an denen es sich orientieren kann.  

Je mehr bewegliche Objekte sich in einem Raum befinden, einschließlich Personen, desto schneller verliert das Gerät die Orientierung. Sich bewegende Förderbänder, Objekte in verschiedenen Bauzuständen und viele Menschen in einem Raum haben allesamt bereits bekanntermaßen Probleme mit der Verfolgung verursacht.

HoloLens kann sich zwar schnell an diese Änderungen anpassen, allerdings nur, wenn dieser Bereich für das Gerät deutlich sichtbar ist. Bereiche, die nicht so häufig gesehen werden, können der Realität hinterherhinken, was zu Fehlern in der räumlichen Karte führen kann. Beispiel: Ein Benutzer scannt einen Freund und dreht sich dann um, während der Freund den Raum verlässt. Eine „Phantom“-Darstellung des Freunds verbleibt in den räumlichen Kartierungsdaten, bis der Benutzer den jetzt leeren Raum erneut scannt.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Nähe des Benutzers zu Objekten im Raum

Ähnlich wie Menschen nicht gut auf Objekte in Augennähe fokussieren können, hat die HoloLens Schwierigkeiten, wenn sich Objekte in der Nähe ihrer Kameras befinden. Wenn sich ein Objekt zu nahe im Sichtfeld der beiden Kameras befindet oder ein Objekt eine Kamera blockiert, hat das Gerät viel größere Probleme mit der Verfolgung des Objekts.  

Die Kameras können nicht näher als 15 cm an ein Objekt heransehen.

### <a name="surfaces-in-a-space"></a>Oberflächen in einem Raum

Stark verspiegelte Oberflächen sehen je nach Winkel unterschiedlich aus, was sich auf die Verfolgung auswirkt. Denken Sie an ein brandneues Auto – wenn Sie es bewegen, wird das Licht reflektiert, und es werden dabei unterschiedliche Dinge auf der Oberfläche gezeigt. Für die Verfolgungsfunktion stellen die unterschiedlichen Dinge, die auf der Oberfläche reflektiert werden, eine sich verändernde Umgebung dar, und das Gerät verliert die Orientierung.

Weniger glänzende Objekte können leichter verfolgt werden.

### <a name="wi-fi-fingerprint-considerations"></a>Überlegungen zum WLAN-Fingerabdruck

Solange WLAN aktiviert ist, werden Kartendaten mit einem WLAN-Fingerabdruck korreliert, auch wenn keine Verbindung mit einem tatsächlichen WLAN-Netzwerk oder -Router besteht. Ohne WLAN-Informationen sind Raum und Hologramme möglicherweise etwas langsamer zu erkennen. Wenn sich die WLAN-Signale erheblich ändern, denkt das Gerät unter Umständen, dass es sich in einem ganz anderen Bereich befindet.

Die Netzwerkkennung (z. B. SSID oder MAC-Adresse) wird nicht an Microsoft gesendet, und alle WLAN-Verweise werden lokal auf der HoloLens gespeichert.

## <a name="mapping-new-spaces"></a>Kartieren neuer Räume

Wenn Sie einen neuen Raum betreten (oder einen vorhandenen Raum laden), wird eine Gittergrafik über dem Raum verteilt angezeigt. Dies bedeutet, dass Ihr Gerät gerade Ihre Umgebung kartiert. Eine HoloLens erlernt einen Raum zwar im Laufe der Zeit, es gibt jedoch ein paar Tipps und Tricks für die Kartierung von Räumen.

## <a name="environment-management"></a>Umgebungsverwaltung

Es gibt zwei Einstellungen, mit denen Benutzer Hologramme „bereinigen“ können und die dazu führen, dass HoloLens einen Raum „vergisst“. Sie sind in **Holograms and environments** (Hologramme und Umgebungen) in der App „Einstellungen“ vorhanden. Die zweite Einstellung wird auch in der App „Einstellungen“ unter **Datenschutz** angezeigt.  

1. **Hologramme in der Nähe löschen.** Wenn Sie diese Einstellung auswählen, werden von HoloLens alle verankerten Hologramme und alle gespeicherten Kartierungsdaten für den „aktuellen Raum“ gelöscht, in dem sich das Gerät befindet. Ein neuer Kartenabschnitt würde erstellt und in der Datenbank für diesen Ort gespeichert, sobald die Hologramme wieder im gleichen Raum platziert werden.

1. **Alle Hologramme löschen.** Wenn Sie diese Einstellung wählen, löscht HoloLens alle Kartendaten und verankerten Hologramme in sämtlichen Datenbanken für Räume. Es werden keine Hologramme erneut ermittelt. Alle Hologramme müssen neu platziert werden, um wieder Kartenabschnitte in der Datenbank zu speichern.

## <a name="hologram-quality"></a>Hologrammqualität

Hologramme können in Ihrer gesamten Umgebung platziert werden – hoch, niedrig und ganz um Sie herum. Sie sehen sie aber durch einen [holografischen Rahmen](/windows/mixed-reality/holographic-frame), der sich vor Ihren Augen befindet. Um die beste Sicht zu erhalten, stellen Sie sicher, dass Sie das Gerät so anpassen, dass Sie den gesamten Rahmen sehen können. Und zögern Sie nicht, durch den Raum zu gehen und ihn zu erkunden!

Damit Ihre [Hologramme](/windows/mixed-reality/hologram) gestochen scharf und stabil aussehen, sollte Ihre HoloLens nur für Sie kalibriert werden. Wenn Sie Ihre HoloLens zum ersten Mal einrichten, werden Sie durch diesen Prozess geführt. Später, wenn die Hologramme nicht richtig aussehen oder Sie zahlreiche Fehler erkennen, können Sie Anpassungen vornehmen.

Wenn Sie Probleme beim Kartieren von Räumen haben, versuchen Sie, Hologramme in der Nähe zu löschen und den Raum erneut zu kartieren.

### <a name="calibration"></a>Kalibrierung

Wenn Ihre Hologramme zittrig oder wackelig aussehen oder Sie Probleme beim Platzieren von Hologrammen haben, sollten Sie zunächst die App [Kalibrierung](hololens-calibration.md) ausprobieren. Diese App kann auch helfen, wenn Sie bei der Nutzung Ihrer HoloLens Unbehagen empfinden.

Die App „Kalibrierung“ finden Sie unter **Einstellungen** > **System** > **Dienstprogramme**. Wählen Sie **Kalibrierung öffnen** aus, und befolgen Sie die Anweisungen.

Wenn ein anderer Benutzer Ihre HoloLens verwendet, sollte er zuerst die App „Kalibrierung“ ausführen, damit das Gerät ordnungsgemäß für Ihn eingerichtet wird.

## <a name="temperature-and-regulatory-information"></a>Temperatur- und rechtliche Informationen

[Rechtliche Informationen zu HoloLens](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): Enthält Informationen zu Temperaturbereich, Entsorgung, Funk- und TV-Störungen und mehr.

Ausführliche Informationen zu HoloLens finden Sie unter [Materials and substances](https://www.microsoft.com/legal/compliance/materials-substances) unter „Download our REACH Article 33 Disclosure on Environmental Compliance (PDF)“.

Hier einige Richtlinien, die bei der Nutzung Ihres Geräts zu beachten sind:

1. Lagern Sie das Gerät eine Stunde lang in einer Umgebung innerhalb des Temperaturbereichs (entweder im Standbymodus oder ausgeschaltet), bevor Sie das Gerät verwenden.
1. Nutzen Sie das Gerät in einer Umgebung innerhalb des Temperaturbereichs.
1. Verwenden Sie das Gerät in Innenräumen.
1. Nutzen Sie das Gerät im Schatten. Vermeiden Sie auch in Innenräumen direkte Sonneneinstrahlung durch Fenster oder Oberlichter.
1. Wenn Sie die oben genannten Richtlinien befolgen, aber unerwartete Überhitzungsprobleme auftreten, führen Sie die folgenden Schritte aus, um [Feedback](hololens-feedback.md) einzureichen. 
    1. Stellen Sie sicher, dass für Telemetrie auf Ihrem Gerät **Vollständig** oder **Optional** aktiviert ist. Falls nicht, aktivieren Sie eine der Einstellungen. 
    >[!CAUTION]
    > Die Telemetrie ist bei thermischen Ereignissen nicht rückwirkend. Sie muss während der Überhitzung aktiviert sein, da sonst die erforderlichen Daten nicht erfasst werden.
    
    2. Reproduzieren Sie das Überhitzungsproblem.
    3. Schließen Sie das Datum und die Uhrzeit der Überhitzung ein.
    4. Senden Sie [Feedback](hololens-feedback.md).

## <a name="see-also"></a>Siehe auch

- [Entwerfen einer räumlichen Kartierung](/windows/mixed-reality/spatial-mapping)
- [Hologramme](/windows/mixed-reality/hologram)
