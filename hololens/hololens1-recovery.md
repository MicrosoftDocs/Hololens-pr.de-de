---
title: HoloLens 1 neustarten, zurücksetzen oder wiederherstellen
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: So verwenden Sie das Windows-Tool zum Wiederherstellen des Geräts, um ein Bild durch Flash zu HoloLens 1st Gen auszuführen.
keywords: Hilfe & Anleitung, Neustart, zurücksetzen, wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, wdrt, Windows Device Recovery Tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a52e8e5bae49973d92efa6ea75391dc44d8b8ddb
ms.sourcegitcommit: 357094acfd39f7c59a0a62f1dd7918b58c209ef7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "10861160"
---
# HoloLens (1. Generation) neustarten, zurücksetzen oder wiederherstellen

Wenn Sie Probleme mit Ihrem HoloLens haben, können Sie versuchen, einen Neustart, zurücksetzen oder sogar einen erneuten Blitz mit Geräte-Wiederherstellung durchführen.

Hier sind einige Dinge, die Sie ausprobieren können, wenn Ihr HoloLens nicht funktioniert.  Dieser Artikel führt Sie durch die empfohlenen Schritte für die Wiederherstellung in Folge.

Wenn Sie sich für die Wiederherstellung eines HoloLens 2 interessieren, schauen Sie sich die Seite für [Wiederherstellen einer HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)an, da es Unterschiede bei den Prozessen gibt.

Dieser Artikel befasst sich mit dem HoloLens-Gerät und der Software. Wenn Ihre Hologramme nicht richtig aussehen, [dieser Artikel](hololens-environment-considerations.md) spricht über Umweltfaktoren, die die Qualität des Hologramms verbessern.

## Neu starten

### Durchführen eines sicheren Neustarts mithilfe von Cortana

Die sicherste Methode zum Neustarten des HoloLens ist die Verwendung von Cortana. Dies ist in der Regel ein einfacher erster Schritt beim Auftreten eines Problems mit HoloLens. 

> [!NOTE]
> Cortana ist nicht auf allen Geräten verfügbar. Cortana ist für alle HoloLens (1st Gen)-Geräte verfügbar.
> Cortana ist verfügbar auf HoloLens 2-Geräten in einem Bau vor dem Windows Holograpic, aktualisierte Version 2004.

1. Ihr Gerät anlegen
1. Vergewissern Sie sich, dass das Gerät eingeschaltet, ein Benutzer angemeldet ist und das Gerät nicht auf ein Kennwort wartet, um es zu entsperren.
1. Sagen Sie "Hey Cortana, erneut starten" oder "Hey Cortana, Neustart".
1. Erfolgt ihre Anerkennung, werden Sie zur Bestätigung aufgefordert.  Warten Sie einen Moment, bis ein Ton erklingt, nachdem sie ihre Frage abgeschlossen hat. sie gibt an, dass sie Ihnen zuhört und dann sagen Sie "Ja".
1. Das Gerät wird jetzt neu gestartet.

### Durchführen eines sicheren Neustarts mithilfe des Netzschalters

Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie es mit dem Netzschalter neu zu starten:

1. Drücken und halten Sie den Netzschalter 5 Sekunden lang.
   1. Nach einer Sekunde werden alle fünf LEDs beleuchtet und dann langsam von rechts nach links abgeschaltet.
   1. Nach fünf Sekunden sind alle LEDs aus, was bedeutet, dass der Befehl "Herunterfahren" erfolgreich war.
   1. Bitte beachten Sie, dass das Drücken der Taste unmittelbar nach dem Deaktivieren aller LEDs unbedingt beendet werden muss.
1. Warten Sie eine Minute, bis das Herunterfahren erfolgreich ausgeführt wurde. Beachten Sie, dass der Vorgang des Herunterfahrens möglicherweise weiterhin ausgeführt wird, auch wenn die anzeigen deaktiviert sind.
1. Schalten Sie das Gerät erneut ein, indem Sie den Netzschalter eine Sekunde lang gedrückt halten.

### Durchführen eines sicheren Neustarts mithilfe des Windows Geräteportals

> [!NOTE]
> Dazu muss HoloLens als Entwicklergerät konfiguriert werden.  
> Weitere Informationen zu [Windows Geräteportals](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Wenn die vorhergehende Schritte nicht funktionieren, können Sie versuchen, das Gerät mithilfe [Windows Geräteportals neu zu starten](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). In der oberen rechten Ecke gibt es eine Option, um das Gerät neu zu starten oder herunterzufahren.

### Durchführen eines unsicheren erzwungenen Neustarts

Wenn Sie das Gerät durch keine der vorherigen Methoden erfolgreich starten konnten, können Sie einen Neustart erzwingen. Diese Methode entspricht dem Entfernen der Batterie aus dem HoloLens.  Es handelt sich um einen gefährlichen Vorgang, bei dem Ihr Gerät in einem korrupten Zustand bleibt.  In diesem Fall müssen Sie bei Ihrem HoloLens einen Flash ausführen.  

> [!WARNING]
> Dies ist eine potenziell schädliche Methode und sollte nur verwendet werden, wenn keine der vorhergehenden Methoden funktioniert.

1. Drücken und halten Sie den Netzschalter mindestens 10 Sekunden lang.
   - Es ist in Ordnung, die Taste länger als 10 Sekunden zu halten.
   - Sie können die LED-Aktivitäten ignorieren.
1. Lassen Sie die Schaltfläche Los, und warten Sie zwei oder drei Sekunden.
1. Schalten Sie das Gerät erneut ein, indem Sie den Netzschalter eine Sekunde lang gedrückt halten.
Wenn Sie weiterhin Probleme haben, drücken Sie den Netzschalter 4 Sekunden lang, bis alle Akku Anzeiger ausgeblendet sind und der Bildschirm keine Hologramme mehr anzeigt. Warten Sie 1 Minute, und drücken Sie dann erneut die Netzschalter, um das Gerät zu aktivieren.

## Zurücksetzen von Geräten auf Werkseinstellungen

> [!NOTE]
> Der Akkustand muss mindestens bei 40 Prozent liegen, damit der Zurücksetzungsvorgang erfolgreich ausgeführt werden kann. 

Wenn nach dem Neustart Ihres HoloLens weiterhin Probleme auftreten, versuchen Sie, ihn in die Werkseinstellung zurückzusetzen.  Durch das Zurücksetzen des HoloLens wird die Version der Windows Holographische Software beibehalten, die auf dem Computer installiert ist, und alle anderen Elemente werden in die Werkseinstellungen zurückgesetzt.

Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzung. Durch das Zurücksetzen wird nur die neueste installierte Version von Windows Holographic installiert. Sie müssen alle Initialisierungsschritte (kalibrieren, Verbindung mit Wi-Fi, Erstellen eines Benutzerkontos, Herunterladen von Apps usw.) wiederholen.

1. Starten Sie die App "Einstellungen", und wählen Sie dann **Update** > **Zurücksetzen**aus.
1. Wählen Sie die Option **Gerät zurücksetzen** aus, und lesen Sie die Bestätigungsmeldung.
1. Wenn Sie Ihr Gerät zurücksetzen, wird das Gerät neu gestartet, und es wird eine Reihe von rotierenden Gängen mit einer Statusanzeige angezeigt.
1. Warten Sie etwa 30 Minuten, bis dieser Vorgang durchgeführt wird.
1. Der Reset wird durchgeführt, und das Gerät wird in die sofort verwendbare Umgebung neu gestartet.

## So installieren Sie das Betriebssystem

Wenn nach dem Neustart und Zurücksetzen des Geräts weiterhin ein Problem auftritt, können Sie auf Ihrem Computer ein Wiederherstellungstool verwenden, um das Betriebssystem und die Firmware des HoloLens neu zu installieren.  

Alle Daten, die HoloLens zurücksetzen muss, sind in einem vollständigen Flash-Update (FFU) verpackt.  Dies ähnelt einer ISO, WIM oder VHD.  [Erfahren Sie mehr über die FFU Bilddateiformate.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Bei Bedarf können Sie ein vollkommen neues Betriebssystem auf Ihrem HoloLens (1st Gen) mit dem Windows-Gerät Wiederherstellungstool installieren.

Bevor Sie dieses Tool verwenden, stellen Sie fest, ob das Problem Ihres HoloLens durch Neustart oder Zurücksetzen behoben wird. Der Wiederherstellungsvorgang kann einige Zeit in Anspruch nehmen.  Wenn Sie damit fertig sind, wird die neueste Version der für Ihre HoloLens genehmigten Windows-holographischen Software installiert.

Wenn Sie das Tool verwenden möchten, benötigen Sie einen Computer mit Windows 10 oder höher, mit mindestens 4 GB freien Speicherplatz.  Bitte beachten Sie, dass Sie dieses Tool nicht auf einem virtuellen Computer ausführen können.

### Wiederherstellung Ihres HoloLens:

1. [Windows-Geräte Wiederherstellung Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) auf Ihrem Computer herunterladen und installieren.
1. Schießen Sie Ihr HoloLens (1st gen) an Ihren Computer an, indem Sie das Micro-USB-Kabel verwenden, das im Lieferumfang Ihres HoloLens enthalten war.
1. Führen Sie das Windows-Gerät Wiederherstellung Tool aus, und folgen Sie den Anweisungen.

Wenn Ihr HoloLens (1st gen) nicht automatisch erkannt wird, wählen Sie **mein Gerät wurde nicht erkannt** aus, und folgen Sie den Anweisungen, um Ihr Gerät in den Wiederherstellungsmodus zu setzen.

### Manueller Blinkmodus:

Für den Fall, dass Ihr Gerät nicht erkannt wird, verwenden Sie die folgende Methode, um es manuell in den Blinkmodus zu setzen.

1. Trennen Sie das Gerät von allen Stromquellen.
1. Wenn das Gerät eingeschaltet ist, halten Sie den Netzschalter gedrückt, bis es vollständig ausgeschaltet ist.
1. Halten Sie die **Lautstärke lauter** Taste, und tippen Sie kurz auf den **Netzschalter**. 
1. Das Gerät sollte starten und dann nur die Mitte des LED-Lichts anzeigen.
1. Verbinden Sie das Gerät mit Ihrem PC.
1. Starten Sie die Windows-Geräte Wiederherstellung.
1. Sie müssen *mein Gerät wurde nicht erkannt** auswählen und dann **HoloLens auswählen**. 
1. Befolgen Sie die Anweisungen, um das Gerät wiederherzustellen..
