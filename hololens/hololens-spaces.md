---
title: Abbilden von physischen Räumen mit HoloLens
description: HoloLens lernt im Lauf der Zeit, wie ein Raum aussieht. Benutzer können diesen Prozess unterstützen, indem sie die HoloLens auf bestimmte Weise durch den Raum bewegen.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: HoloLens, Windows Mixed Reality, Entwurf, räumliche Abbildung, HoloLens, Oberflächenrekonstruktion, Gitternetz, Kopfverfolgung, Zuordnung
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034369"
---
# <a name="map-physical-spaces-with-hololens"></a>Abbilden von physischen Räumen mit HoloLens

HoloLens kombiniert Hologramme mit Ihrer physischen Welt. Dazu muss HoloLens sich über die physische Welt informieren, die Sie umgibt, und sich merken, wo Sie Hologramme innerhalb dieses Raums platzieren.

Im Laufe der Zeit erstellt HoloLens eine *Raumzuordnungskarte* der Umgebung, die es gesehen hat.  HoloLens aktualisiert die Karte, wenn sich die Umgebung ändert. Solange Sie angemeldet sind und das Gerät eingeschaltet ist, erstellt und aktualisiert HoloLens Ihre Raumzuordnungskarten. Wenn Sie das Gerät so halten oder tragen, dass die Kameras in einen Raum zeigen, versucht HoloLens, das Gebiet abzubilden. Zwar lernt HoloLens einen Raum im Lauf der Zeit auf natürliche Weise, jedoch können Sie HoloLens dabei helfen, Ihren Raum schneller und effizienter abzubilden.  

> [!NOTE]
> Wenn Ihre HoloLens Ihren Raum nicht abbilden kann oder nicht kalibriert ist, wechselt HoloLens möglicherweise in den eingeschränkten Modus. Im eingeschränkten Modus können Sie keine Hologramme in Ihrer Umgebung platzieren.

In diesem Artikel wird erläutert, wie HoloLens Räume abbildet, wie Sie die räumliche Abbildung verbessern und wie Sie die Raumdaten verwalten können, die von HoloLens gesammelt werden.

## <a name="choosing-and-setting-up-and-your-space"></a>Auswahl und Einrichtung und Ihr Raum

Bestimmte Merkmale in Ihrer Umgebung können es für HoloLens schwierig machen, einen Raum zu interpretieren. Lichtpegel, Materialien im Raum, das Layout von Objekten und mehr können beeinflussen, wie HoloLens einen Bereich kartiert.

HoloLens funktioniert am besten in bestimmten Arten von Umgebungen. Zum Erzeugen einer möglichst guten räumlichen Abbildung wählen Sie einen Raum mit angemessener Beleuchtung und reichlich Platz. Meiden Sie dunkle Orte und Räume mit vielen dunklen, glänzenden oder transparenten Oberflächen (beispielsweise Spiegeln oder durchscheinenden Vorhängen).

HoloLens ist für die Verwendung im Innenbereich optimiert. Ferner funktioniert die räumliche Abbildung am besten, wenn WLAN aktiviert ist, allerdings muss keine Netzwerkverbindung bestehen. HoloLens kann WLAN-Zugriffspunkte abrufen, auch wenn es nicht verbunden oder authentifiziert ist. Die Funktionalität von HoloLens bleibt unverändert, wenn die Zugriffspunkte mit dem Internet oder nur mit einem Intranet/lokal verbunden sind.

Verwenden Sie HoloLens nur an sicheren Orten ohne Stolpergefahr. [Weitere Informationen zur Sicherheit](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Abbilden Ihres Raums

Jetzt sind Sie bereit, mit der Abbildung Ihres Raums zu beginnen.  Wenn HoloLens mit der Abbildung Ihrer Umgebung beginnt, sehen Sie die Grafik eines Gittermodells, die sich über den Raum ausbreitet.  In der Mixed Reality-Startumgebung können Sie die Darstellung der Karte auslösen, indem Sie eine Auswahl auf einer bereits abgebildeten Fläche treffen.

Dies sind Richtlinien zum Erzeugen einer hervorragenden Raumabbildung.

### <a name="understand-the-scenarios-for-the-area"></a>Verstehen der Szenarien für den räumlichen Bereich

Es ist wichtig, die meiste Zeit dort zu verbringen, wo Sie die HoloLens verwenden, damit die Karte relevant und vollständig ist. Wenn ein Benutzerszenario für HoloLens z. B. die Bewegung von Punkt A zu Punkt B beinhaltet, gehen Sie diesen Pfad zwei- bis dreimal, und sehen Sie während des Gehens in alle Richtungen.  

### <a name="walk-slowly-around-the-space"></a>Langsames Gehen durch den Raum

Wenn Sie sich zu schnell im räumlichen Bereich bewegen, wird HoloLens wahrscheinlich die Abbildung von Bereichen versäumen. Gehen Sie langsam Raum umher, und halten Sie alle 1,5 bis 3 Meter an, um sich in Ihrer Umgebung umzusehen.  

Gleichmäßige Bewegungen unterstützen HoloLens ebenfalls bei der effizienteren Abbildung.

### <a name="look-in-all-directions"></a>In alle Richtungen blicken

Wenn Sie sich beim Abbilden des Raums umsehen, erhält HoloLens mehr Daten dazu, wo sich Punkte relativ zueinander befinden.  

Wenn Sie beispielsweise nicht nach oben blicken, weiß HoloLens möglicherweise nicht, wo sich die Decke eines Raums befindet.  

Vergessen Sie nicht, beim Abbilden des Raums nach unten auf den Fußboden zu blicken.

### <a name="cover-key-areas-multiple-times"></a>Mehrfaches Abdecken wichtiger Bereiche

Wenn Sie sich mehrmals durch einen Bereich bewegen, können Merkmale erfasst werden, die beim ersten Durchgang möglicherweise übersehen wurden. Zum Erstellen einer idealen Karte sollten Sie versuchen, einen Bereich zwei oder drei Mal zu durchqueren.

Verbringen Sie nach Möglichkeit beim Wiederholen dieser Bewegungen Zeit mit dem Gehen durch einen Bereich in einer Richtung, drehen Sie sich dann um, und gehen Sie auf dem gleichen Weg zurück.

### <a name="take-your-time-mapping-the-area"></a>Zeit für die Abbildung des Bereichs lassen

Es kann zwischen 15 und 20 Minuten dauern, bis HoloLens die Umgebung vollständig abgebildet und sich an sie angepasst hat. Wenn Sie über einen Bereich verfügen, in dem Sie HoloLens häufig verwenden möchten, können Sie sich spätere Probleme ersparen, wenn Sie sich vorab Zeit nehmen, den Bereich abzubilden.  

## <a name="possible-errors-in-the-spatial-map"></a>Mögliche Fehler in der räumlichen Abbildung

Fehler in Daten der räumlichen Abbildung lassen sich in einige Kategorien unterteilen:

- *Lücken*: Flächen der realen Welt fehlen in den räumlichen Abbildungsdaten.
- *Halluzinationen*: In den räumlichen Abbildungsdaten sind Flächen vorhanden, die es in der realen Welt nicht gibt.
- *Wurmlöcher*: HoloLens ‚verliert‘ einen Teil der räumlichen Abbildung, weil es glaubt, sich in einem anderen Teil der Abbildung zu befinden als es tatsächlich ist.
- *Verzerrung*: Flächen sind in den Daten der räumlichen Abbildung stimmen ungenau mit den Flächen der realen Welt überein, sie sind entweder vertieft oder herausgehoben.

Wenn bei Ihnen einer dieser Fehler auftritt, verwenden Sie den [FeedbackHub](hololens-feedback.md), um Feedback zu senden.

## <a name="security-and-storage-for-spatial-data"></a>Sicherheit und Speicherung räumlicher Daten

Im Update von Windows 10, Version 1803 und höher, für Microsoft HoloLens werden Abbildungsdaten in einer lokalen Datenbank (auf dem Gerät) gespeichert.

HoloLens-Benutzer können nicht direkt auf die Kartendatenbank zugreifen, selbst wenn das Gerät an einen PC angeschlossen ist oder die Datei-Explorer-App verwendet wird. Wenn BitLocker in HoloLens aktiviert ist, werden auch die gespeicherten Kartendaten zusammen mit dem gesamten Volume verschlüsselt.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Entfernen von Kartendaten und bekannten Orten aus HoloLens

Es gibt zwei Optionen zum Löschen von Kartendaten unter **Einstellungen > System > Hologramme**:

- Um Hologramme in der Nähe zu löschen, wählen **Remove nearby holograms** (In der Nähe befindliche Hologramme entfernen). Mit diesem Befehl werden die Kartendaten und verankerten Hologramme für den aktuellen Raum gelöscht. Wenn Sie das Gerät weiterhin im gleichen Raum verwenden, erstellt und speichert es einen von Grund auf neuen Kartenabschnitt, um die gelöschten Informationen zu ersetzen.

   > [!NOTE]
   > „In der Nähe befindliche“ Hologramme sind solche, die im aktuellen Raum im gleichen Kartenabschnitt verankert sind.

   Sie können diese Option beispielsweise verwenden, um arbeitsbezogene Kartendaten zu löschen, ohne auf den Ausgangspunkt bezogene Kartendaten zu beeinträchtigen.

- Wählen Sie zum Löschen aller Hologramme **Remove all holograms** (Alle Hologramme entfernen) aus. Mit diesem Befehl werden alle auf dem Gerät gespeicherten Kartendaten sowie alle verankerten Hologramme gelöscht. Sie müssen dann alle Hologramme explizit platzieren. Sie können die zuvor platzierten Hologramme nicht wiederentdecken.

> [!NOTE]
> Nachdem Sie die in der Nähe befindlichen oder alle Hologramme entfernt haben, beginnt HoloLens sofort, den aktuellen Raum zu scannen und abzubilden.

### <a name="wi-fi-data-in-spatial-maps"></a>WLAN-Daten in räumlichen Karten

HoloLens speichert WLAN-Merkmale, um die Korrelierung von Hologrammpositionen und Kartenabschnitten zu unterstützen, die in der HoloLens-Datenbank bekannter Orte gespeichert sind. Die Informationen über WLAN-Merkmale sind für Benutzer nicht zugänglich und werden nicht an Microsoft gesendet, weder per Cloud noch als Telemetriedaten.

Solange WLAN aktiviert ist, korreliert HoloLens Kartendaten mit WLAN-Zugangspunkten in der Nähe. Es gibt keinen Unterschied im Verhalten, ob die Zugriffspunkte mit dem Internet oder nur mit einem Intranet/lokal verbunden sind. Wenn WLAN deaktiviert ist, durchsucht HoloLens den Raum trotzdem. Allerdings muss HoloLens mehr Kartendaten in der Datenbank der Räume durchsuchen und benötigt möglicherweise mehr Zeit, um Hologramme zu finden. Ohne die WLAN-Informationen muss HoloLens aktive Scans mit allen Hologrammankern und Kartenabschnitten vergleichen, die auf dem Gerät gespeichert sind, um den richtigen Teil der Karte zu finden.

## <a name="related-topics"></a>Zugehörige Themen

- [Entwerfen einer räumlichen Kartierung](/windows/mixed-reality/spatial-mapping)
