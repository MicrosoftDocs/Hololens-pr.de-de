---
title: Abbilden von physischen Räumen mit HoloLens
description: HoloLens lernt im Laufe der Zeit, wie ein Raum aussieht. Benutzer können diesen Prozess vereinfachen, indem sie die HoloLens auf bestimmte Weise durch den Raum bewegen.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: Hololens, Windows Mixed Reality, Design, räumliche Zuordnung, HoloLens, Surface Rekonstruktion, Gittermodell, Head Tracking, Mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 992b17160eb6ba6ca2f6c8b12e112b98ab154774
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828242"
---
# Abbilden von physischen Räumen mit HoloLens

HoloLens verbindet Hologramme mit Ihrer physischen Welt. Dazu muss HoloLens die Ihre physische Umgebung kennen lernen und sich merken, wo Sie Hologramme in diesem Raum platzieren.

Nach und nach baut HoloLens eine *räumliche Karte* der Umgebung, die HoloLens gesehen hat.  HoloLens aktualisiert die Karte, wenn sich die Umgebung ändert. Solange Sie angemeldet sind und das Gerät aktiviert ist, erstellt HoloLens räumliche Karten Ihrer Umgebung. Wenn Sie das Gerät mit den Kameras in einen Raum halten oder tragen, versucht HoloLens die Umgebung zu kartieren. Während HoloLens mit der Zeit einen Raum kennenlernt, können Sie HoloLens helfen, Ihre Umgebung schneller und effizienter zu kartieren.  

> [!NOTE]
> Wenn HoloLens Ihre Umgebung nicht kartieren kann oder nicht mehr kalibriert ist, kann HoloLens in den eingeschränkten Modus wechseln. Im eingeschränkten Modus können Sie keine Hologramme in Ihrer Umgebung platzieren.

In diesem Artikel wird erläutert, wie HoloLens Räume erfasst, wie die räumliche Zuordnung verbessert werden kann und wie die von HoloLens gesammelten räumlichen Daten zu verwalten sind.

## Ihre räumliche Umgebung auswählen und einrichten

Bestimmte Merkmale in Ihrer Umgebung erschweren es HoloLens, einen Raum zu erfassen. Belichtungsstufen, Materialien im Raum, die Anordnung von Objekten und vieles mehr, können sich auf die Art und Weise auswirken, wie HoloLens einen Bereich kartiert.

HoloLens funktioniert am besten in bestimmten Umgebungen. Um die beste räumliche Karte zu erstellen, wählen Sie einen Raum mit ausreichend Licht und viel Platz. Vermeiden Sie dunkle Räume und Räume mit vielen dunklen, glänzenden oder durchscheinenden Oberflächen (z. B. Spiegel oder lichtdurchlässige Gardinen).

HoloLens ist für den Inneneinsatz optimiert. Die räumliche Zuordnung funktioniert am besten bei aktiviertem WLAN, auch wenn es nicht mit einem Netzwerk verbunden ist. HoloLens kann WLAN-Zugriffspunkte abrufen, auch wenn es nicht verbunden oder authentifiziert ist. Die HoloLens-Funktionalität ändert sich nicht, wenn die Zugriffspunkte mit dem Internet, Intranet oder lokal verbunden sind.

Verwenden Sie HoloLens nur an sicheren Orten ohne Stolperfallen. [Mehr zur Sicherheit](https://support.microsoft.com/help/4023454/safety-information).

## Kartieren Ihres Raumes

Jetzt können Sie mit der Zuordnung Ihres Raumes beginnen.  Wenn HoloLens die Zuordnung Ihrer Umgebung beginnt, wird ein Gittermodell angezeigt, das sich über dem Raum ausbreitet.  In der Mixed Reality Startumgebung können Sie die Anzeige der Karte auslösen, indem Sie eine zugeordnete Oberfläche auswählen.

Hier finden Sie Anleitungen zum Erstellen einer großartigen räumlichen Karte.

### Grundlegende Informationen zu den Szenarien der Umgebung

Es ist wichtig, dass Sie die meiste Zeit dort verbringen, wo HoloLens verwendet wird, damit die Karte relevant und vollständig ist. Wenn z. B. ein Benutzerszenario für HoloLens die Bewegung von Punkt A nach Punkt B erfordert, gehen Sie diesen Pfad zwei bis dreimal und sehen Sie sich dabei in alle Richtungen um.  

### Gehen Sie langsam im Raum herum

Wenn Sie sich zu schnell bewegen, fehlen HoloLens möglicherweise einige Zuordnungsbereiche. Gehen Sie langsam durch den Raum, halten Sie alle 1,5–2,5 m an und sehen Sie sich in Ihrer Umgebung um.  

Mit weichen Bewegungen wird Ihre HoloLens-Karte genauer.

### Sehen Sie sich in alle Richtungen um.

Wenn Sie sich beim Kartieren des Raums umschauen, erhält die HoloLens mehr Daten darüber, wo Punkte relativ zueinander sind.  

Wenn Sie beispielsweise nicht nach oben sehen, weiß HoloLens möglicherweise nicht, wo sich die Decke befindet.  

Vergessen Sie nicht, beim Kartieren auf den Boden zu sehen.

### Schlüsselbereiche mehrfach abdecken

Wenn Sie mehrere Male durch einen Bereich gehen, werden möglicherweise Einzelheiten erfasst, die beim ersten Durchgang übersehen wurden. Wenn Sie eine ideale Karte erstellen möchten, versuchen Sie, einen Bereich zwei bis dreimal zu durchlaufen.

Wenn möglich, durchgehen Sie einen Bereich in eine Richtung, drehen sich dann um und gehen den gleichen Weg zurück.

### Nehmen Sie sich Zeit, um den Bereich zu kartieren

Es kann 15 bis 20 Minuten dauern, bis sich HoloLens vollständig an die Umgebung angepasst und sie kartiert hat. Wenn Sie HoloLens in einem bestimmten Raum häufig verwenden möchten, können Sie im Vorfeld die Zeit nutzen und den Raum kartieren, um spätere Probleme zu vermeiden.  

## Mögliche Fehler in der räumlichen Zuordnung

Die Fehler in den Kartierungsdaten lassen sich in einige Kategorien unterteilen:

- *Löcher*: Reale Oberflächen fehlen in den Kartierungsdaten.
- *Halluzinationen*: Flächen in den Kartierungsdaten sind in der Realität nicht vorhanden.
- *Wurmlöcher*: HoloLens „verliert“ einen Teil der räumlichen Karte, indem sie sich woanders verortet als sie sich tatsächlich befindet.
- *Bias*: Flächen in den Kartierungsdaten werden nicht perfekt an realen Oberflächen ausgerichtet, entweder nach hinten oder nach vorne verschoben.

Wenn einer dieser Fehler angezeigt wird, senden Sie Ihr Feedback an [FeedbackHub](hololens-feedback.md).

## Sicherheit und Speicherplatz für räumliche Daten

Das Windows 10-Update für Version 1803 für Microsoft HoloLens und höher speichert Zuordnungsdaten in einer lokalen Datenbank (auf dem Gerät).

HoloLens-Benutzer können nicht direkt auf die Kartendatenbank zugreifen, selbst wenn das Gerät an einen PC oder die Datei-Explorer-App angeschlossen ist. Wenn BitLocker auf HoloLens aktiviert ist, werden die gespeicherten Kartendaten auch zusammen mit dem gesamten Volume verschlüsselt.

### Kartendaten und bekannte Räume aus HoloLens entfernen

Es gibt zwei Optionen zum Löschen von Kartendaten in **Einstellungen > System > Hologramme**:

- Wenn Sie Hologramme in der Nähe löschen möchten, wählen Sie **Hologramme in der Nähe entfernen**aus. Mit diesem Befehl werden die Kartendaten und die verknüpften Hologramme für den aktuellen Raum gelöscht. Wenn Sie das Gerät weiterhin im selben Raum verwenden, wird ein ganz neuer Kartenabschnitt erstellt und gespeichert, um die gelöschten Informationen zu ersetzen.

   > [!NOTE]
   > Hologramme „in der Nähe“ sind Hologramme, die im aktuellen Raum im selben Kartenabschnitt verankert sind.

   Mit dieser Option können Sie beispielsweise arbeitsbezogene Kartendaten löschen, ohne dass dies Auswirkungen auf hausbezogene Kartendaten hat.

- Wenn Sie alle Hologramme löschen möchten, wählen Sie **Alle Hologramme entfernen**aus. Mit diesem Befehl werden alle auf dem Gerät gespeicherten Kartendaten sowie alle verankerten Hologramme gelöscht. Sie müssen alle Hologramme explizit platzieren. Sie können die zuvor platzierten Hologramme nicht neu entdecken.

> [!NOTE]
> Nachdem Sie die in der Nähe befindlichen oder alle Hologramme entfernt haben, beginnt HoloLens sofort mit dem Überprüfen und Zuordnen des aktuellen Raumes.

### WLAN-Daten in räumlichen Karten

HoloLens speichert WLAN-Merkmale, um Rabattenkompositionen und Kartenbereiche, die in der HoloLens-Datenbank bekannter Räume gespeichert sind, in Korrelation zu bringen. Informationen zu WLAN-Merkmalen sind für Benutzer nicht zugänglich und werden nicht über die Cloud oder über Telemetrie an Microsoft gesendet.

Solange WLAN aktiviert ist, korreliert HoloLens Kartendaten mit WLAN-Zugriffspunkten in der Nähe. Es gibt keinen Unterschied im Verhalten, ob ein Netzwerk verbunden ist oder nur in der Nähe erkannt wird. Wenn WLAN deaktiviert ist, durchsucht HoloLens den Raum weiterhin. HoloLens muss jedoch mehr Kartendaten in der Datenbank des Raumes durchsuchen und benötigt möglicherweise mehr Zeit zum Auffinden von Hologrammen. Ohne die WLAN-Informationen muss HoloLens aktive Scans mit allen Hologramm- und Kartenabschnitten vergleichen, die auf dem Gerät gespeichert sind, um den richtigen Teil der Karte zu finden.

## Verwandte Themen

- [Entwurf der Raumabbildung](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
