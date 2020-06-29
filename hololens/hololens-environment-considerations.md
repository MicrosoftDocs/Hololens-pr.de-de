---
title: Umgebungsaspekte für HoloLens
description: Sie haben mit HoloLens das bestmögliche Erlebnis, wenn Sie das Gerät für Ihre Augen und Ihre Umgebung optimieren. Es gibt viele verschiedene Umgebungsfaktoren, die die Verfolgung ermöglichen. Als Entwickler von Mixed Reality gibt es jedoch mehrere Faktoren, die Sie berücksichtigen können, um einen Raum für bessere Hologramme zu optimieren.
keywords: Holografischer Rahmen, Sichtfeld, Kalibrierung, Räume, Umgebung, Vorgehensweise
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d2bec32e118ee1c9307b56fad99b7e8859e2a94d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828092"
---
# Umgebungsaspekte für HoloLens

HoloLens mischt Holografie mit der „realen“ Welt und bringt Hologramme in Ihre unmittelbare Umgebung. Das Fenster einer holografischen Anwendung „hängt“ an der Wand, eine holografische Ballerina dreht sich auf der Tischplatte, oder Hasenohren befinden sich auf dem Kopf Ihres ahnungslosen Freundes. Wenn Sie ein spannendes Spiel oder eine immersive App verwenden, breitet sich die holografische Welt aus und füllt Ihre gesamte Umgebung. Sie können den Raum aber trotzdem noch sehen und sich darin bewegen.

Die von Ihnen platzierten Hologramme bleiben an der Stelle, an der Sie sie platziert haben, auch wenn Sie Ihr Gerät ausschalten.

## Einrichten einer Umgebung

HoloLens-Geräte wissen, wie sie stabile und genaue Hologramme platzieren, indem sie Benutzer in einem Raum *verfolgen*. Ohne ordnungsgemäße Verfolgung kann das Gerät die Umgebung oder den Benutzer in dieser Umgebung nicht erfassen, sodass Hologramme eventuell an falschen Stellen angezeigt werden, nicht jedes Mal an derselben Stelle erscheinen oder überhaupt nicht angezeigt werden. Die zum Verfolgen der Benutzer verwendeten Daten werden in der *räumlichen Zuordnung* dargestellt.  

Die Leistung bei der Verfolgung ist stark von der Umgebung abhängig, in der sich der Benutzer befindet, und die Optimierung einer Umgebung für eine zuverlässige, konsistente Verfolgung ist eher eine Kunst als eine Wissenschaft. Es gibt viele verschiedene Umgebungsfaktoren, die die Verfolgung ermöglichen. Als Entwickler von Mixed Reality gibt es jedoch mehrere Faktoren, die Sie berücksichtigen können, um einen Raum für eine bessere Verfolgung zu optimieren.

### Beleuchtung

Windows Mixed Reality nutzt sichtbares Licht, um die Position des Benutzers zu verfolgen. Wenn eine Umgebung zu hell ist, könnte eine Sättigung der Kameras auftreten, und es wird nichts gesehen. Wenn die Umgebung zu dunkel ist, können die Kameras nicht genügend Informationen erfassen, und es wird nichts gesehen. Die Beleuchtung sollte gleichmäßig und ausreichend hell sein, damit ein Mensch ohne Anstrengung sehen kann, allerdings nicht so hell, dass es wehtut, in das Licht zu schauen.  

Bereiche mit hellen Lichtpunkten in einem insgesamt schummrigen Raum sind ebenfalls problematisch, da sich die Kamera beim Bewegen in und aus hellen Bereichen anpassen muss. Dies kann dazu führen, dass das Gerät „verloren geht“ und davon ausgeht, dass die Lichtänderung eine Standortänderung bedeutet. Ein stabiles Beleuchtungsniveau in einem Bereich führt zu einer besseren Verfolgung.  

Auch jegliche Außenbeleuchtung kann auch zu Instabilitäten bei der Verfolgung führen, da die Sonne im Laufe der Zeit stark variieren kann. Beispielsweise kann die Verfolgung im gleichen Raum im Sommer im Vergleich zum Winter zu sehr unterschiedlichen Ergebnissen führen, da das passive Licht draußen zu unterschiedlichen Jahreszeiten eventuell heller ist.  

Wenn Sie einen Beleuchtungsmesser haben, sind stabile 500 bis 1.000 Lux ein guter Ausgangspunkt.  

#### Arten von Beleuchtung

Auch verschiedene Arten von Beleuchtung in einem Raum können die Verfolgung beeinflussen. Glühbirnen liefern Impulse mit dem Wechselstrom, der durch sie hindurch läuft. Wenn die Wechselstromfrequenz 50Hz beträgt, liegt der Lichtimpuls bei 50Hz. Für einen Menschen ist dieser Impuls nicht sichtbar. Aber die 30fps-Kamera von HoloLens sieht diese Änderungen. So sind einige Bilder gut beleuchtet, einige schlecht beleuchtet, und einige werden überbelichtet, da die Kamera versucht, die Lichtimpulse zu kompensieren.  

In den USA ist die Standardfrequenz 60Hz. Also werden die Impulse von Glühbirnen mit der Bildrate von HoloLens harmonisiert– Impulse mit 60Hz werden an die 30BpS von HoloLens angeglichen. In vielen Ländern gibt es jedoch eine standardmäßige Wechselstromfrequenz von 50Hz. Dies bedeutet, dass einige HoloLens-Bilder während der Impulse erfasst werden, andere hingegen nicht. Insbesondere die fluoreszierende Beleuchtung in Europa verursacht Probleme.  

Es gibt einige Dinge, die Sie zum Beheben von Flackern ausprobieren können. Temperatur, Alter der Glühbirne und Aufwärmzyklen sind häufige Ursachen für fluoreszierendes Flackern. Daher kann es unter Umständen helfen, die Glühbirnen auszutauschen. Die Glühbirnen festzuschrauben und sicherzustellen, dass die Stromentnahme konstant sind, kann ebenfalls hilfreich sein.  

### Objekte in einem Raum

HoloLens verwendet einzigartige Umgebungsmarker, die auch als *Features* bezeichnet werden, um sich in einem Raum zu lokalisieren.  

In einem Bereich, in dem es kaum Features gibt, ist einem Gerät die Verfolgung kaum möglich, da es keine Möglichkeit hat zu wissen, wo es sich im Raum befindet. Sie können die Verfolgung verbessern, wenn Sie Features an den Wänden eines Raums anbringen. Poster, an die Wand geklebte Symbole, Pflanzen, eindeutige Gegenstände oder ähnliche Elemente sind hier hilfreich. Ein unordentlicher Schreibtisch ist ein gutes Beispiel für eine Umgebung, die eine einwandfreie Verfolgung ermöglicht, denn hier gibt es viele verschiedene Features in einem einzigen Bereich.  

Sie sollten im gleichen Raum außerdem eindeutige Features verwenden. Wenn z.B. an einer Wand mehrfach das gleiche Poster hängt, stiftet dies Verwirrung, da HoloLens nicht weiß, welches der sich wiederholenden Poster es gerade sieht. Eine gängige Methode zum Hinzufügen von eindeutigen Features ist die Verwendung von Kreppband. Damit können Sie eindeutige, sich nicht wiederholende Muster entlang der Wände und des Bodens eines Raums anbringen.  

Sie sollten sich einfach folgende Frage stellen: Wenn Sie nur einen kleinen Teil einer Szenerie sehen würden, könnten Sie sich im Raum eindeutig lokalisieren? Ist dies nicht der Fall, wird das Gerät wahrscheinlich auch Probleme mit der Verfolgung haben.

#### Wurmlöcher

Wenn Sie zwei Bereiche haben, die gleich aussehen, denkt der Tracker womöglich, dass sie identisch sind. Und dies führt dazu, dass das Gerät fälschlicherweise davon ausgeht, es wäre an einem anderen Ort. Wir nennen diese Arten von sich wiederholenden Bereichen *Wurmlöcher*.  

Um Wurmlöcher zu vermeiden, versuchen Sie, identische Bereiche im gleichen Raum zu vermeiden. Zu identischen Bereichen können Werkstationen, Fenster in einem Gebäude, Server-Racks oder Arbeitsstationen gehören. Sie können Wurmlöcher verringern, indem Sie Bereiche etikettieren oder eindeutige Objekte zu Bereichen hinzufügen, die ähnlich aussehen.

### Bewegung in einem Raum

Wenn sich Ihre Umgebung ständig verschiebt und verändert, verfügt das Gerät über keine stabilen Features, anhand derer es sich lokalisieren könnte.  

Je mehr bewegliche Objekte sich in einem Raum befinden, einschließlich Personen, desto leichter verliert das Gerät die Orientierung. Das Bewegen von Förderbändern, Objekte in verschiedenen Bauzuständen und viele Menschen in einem Raum haben alle bereits bekanntermaßen Probleme mit der Verfolgung verursacht.

HoloLens kann sich zwar schnell an diese Änderungen anpassen, allerdings nur, wenn dieser Bereich für das Gerät deutlich sichtbar ist. Bereiche, die nicht so häufig gesehen werden, können hinter der Realität zurückbleiben, was zu Fehlern in der räumlichen Zuordnung führen kann. Beispiel: Ein Benutzer scannt einen Freund und dreht sich dann um, während der Freund den Raum verlässt. Eine „Phantom“-Darstellung des Freundes verbleibt in den Raumzuordnungsdaten, bis der Benutzer den jetzt leeren Raum erneut scannt.

### Nähe des Benutzers zu Objekten im Raum

Ähnlich wie Menschen Objekte nicht gut fokussieren können, die sich in der Nähe des Auges befinden, hat auch HoloLens Probleme, wenn Objekte in der Nähe der Kameras sind. Wenn sich ein Objekt zu nahe im Sichtfeld der beiden Kameras befindet oder ein Objekt eine Kamera blockiert, hat das Gerät viel mehr Probleme mit der Verfolgung des Objekts.  

Die Kameras können nicht näher als 15cm von einem Objekt sehen.

### Oberflächen in einem Raum

Stark verspiegelte Oberflächen sehen je nach Winkel unterschiedlich aus, was sich auf die Verfolgung auswirkt. Denken Sie an ein brandneues Auto – wenn Sie es bewegen, wird das Licht reflektiert, und es werden dabei unterschiedliche Dinge auf der Oberfläche angezeigt. Für den Tracker stellen die unterschiedlichen Dinge, die auf der Oberfläche reflektiert werden, eine sich verändernde Umgebung dar, und das Gerät verliert die Orientierung.

Weniger glänzende Objekte können leichter nachverfolgt werden.

### Überlegungen zum WLAN-Fingerabdruck

Solange WLAN aktiviert ist, werden Kartendaten mit einem WLAN-Fingerabdruck korreliert, auch wenn sie nicht mit einem tatsächlichen WLAN-Netzwerk/-Router verbunden sind. Ohne WLAN-Informationen sind Raum und Hologramme möglicherweise etwas langsamer zu erkennen. Wenn sich die WLAN-Signale erheblich ändern, denkt das Gerät unter Umständen, dass es sich in einem ganz anderen Bereich befindet.

Die Netzwerkkennung (z.B. SSID oder MAC-Adresse) wird nicht an Microsoft gesendet, und alle WLAN-Verweise werden lokal auf dem HoloLens gespeichert.

## Abbildung neuer Räume

Wenn Sie einen neuen Raum betreten (oder einen vorhandenen Raum laden), wird eine Gittergrafik über dem Raum verteilt angezeigt. Dies bedeutet, dass Ihr Gerät gerade Ihre Umgebung abbildet. Eine HoloLens erlernt einen Raum zwar im Laufe der Zeit, es gibt jedoch ein paar Tipps und Tricks für die Raumzuordnung.

## Umgebungsverwaltung

Es gibt zwei Einstellungen, mit denen Benutzer Hologramme „bereinigen“ können und die dazu führen, dass HoloLens einen Raum „vergisst“. Sie befinden sich unter **Hologramme und Umgebungen** in der Einstellungs-App, wobei die zweite Einstellung auch unter **Datenschutz** in der Einstellungs-App angezeigt wird.  

1. **Hologramme in der Nähe entfernen** Wenn Sie diese Einstellung auswählen, werden von HoloLens alle verankerten Hologramme und alle gespeicherten Zuordnungsdaten für den „aktuellen Raum“ gelöscht, in dem sich das Gerät befindet. Ein neuer Zuordnungsabschnitt würde erstellt und in der Datenbank für diesen Ort gespeichert, sobald die Hologramme wieder im gleichen Raum platziert werden.

1. **Alle Hologramme löschen**: Wenn Sie diese Einstellung auswählen, werden von HoloLens ALLE Zuordnungsdaten und verankerten Hologramme in den gesamten Raumdatenbanken gelöscht. Es werden keine Hologramme erneut ermittelt. Alle Hologramme müssen neu platziert werden, um wieder Zuordnungsabschnitte in der Datenbank zu speichern.

## Hologrammqualität

Hologramme können in Ihrer gesamten Umgebung platziert werden – hoch, niedrig und ganz um Sie herum. Sie sehen sie aber durch einen [holografischen Rahmen](https://docs.microsoft.com/windows/mixed-reality/holographic-frame), der sich vor Ihren Augen befindet. Um die beste Ansicht zu erhalten, stellen Sie sicher, dass Sie das Gerät so anpassen, dass Sie den gesamten Rahmen sehen können. Und zögern Sie nicht, durch den Raum zu gehen und Ihre Umgebung zu erkunden!

Damit Ihre [Hologramme](https://docs.microsoft.com/windows/mixed-reality/hologram) gestochen scharf und stabil aussehen, sollte Ihre HoloLens nur für Sie kalibriert werden. Wenn Sie Ihre HoloLens zum ersten Mal einrichten, werden Sie durch diesen Prozess geführt. Wenn Hologramme später nicht richtig angezeigt werden oder viele Fehler auftreten, können Sie Anpassungen vornehmen.

Wenn Sie Probleme beim Abbilden von Räumen haben, versuchen Sie, Hologramme in der Nähe zu löschen und den Raum erneut abzubilden.

### Kalibrierung

Wenn Ihre Hologramme zittrig oder wackelig aussehen oder Sie Probleme beim Platzieren von Hologrammen haben, sollten Sie zunächst die [Kalibrierungs-App](hololens-calibration.md) ausprobieren. Diese App kann auch hilfreich sein, wenn Sie bei der Verwendung Ihrer HoloLens Beschwerden haben.

Um die Kalibrierungs-App aufzurufen, wechseln Sie zu **Einstellungen** > **System** > **Dienstprogramme**. Wählen Sie **Kalibrierung öffnen** aus, und folgen Sie den Anweisungen.

Wenn ein anderer Benutzer Ihre HoloLens verwendet, sollte er zuerst die Kalibrierungs-App ausführen, damit das Gerät ordnungsgemäß eingerichtet ist.

## Weitere Informationen:

- [Entwurf der Raumabbildung](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
- [Hologramme](https://docs.microsoft.com/windows/mixed-reality/hologram)
