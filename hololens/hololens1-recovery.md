---
title: Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Verwenden des Windows Device Recovery-Tools zum Flashen eines Bilds auf HoloLens 1. Generation
keywords: How-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308719"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens (1. Generation)

Wenn Probleme mit Ihrer HoloLens auftreten, sollten Sie einen Neustart oder eine Zurücksetzung oder sogar einen Neustart des Geräts mithilfe der Gerätewiederherstellung versuchen. Dieser Artikel führt Sie durch die empfohlenen Wiederherstellungsschritte.

Wenn Sie eine wiederhergestellte HoloLens 2, finden Sie weitere Informationen unter Wiederherstellen eines HoloLens 2 [,](https://docs.microsoft.com/hololens/hololens-recovery)da sich dieser Prozess unterscheidet.

> [!NOTE]
> In diesem Artikel geht es um das HoloLens-Gerät und die HoloLens-Software. Wenn Ihre Hologramme nicht richtig aussehen, finden Sie unter Überlegungen zur **[HoloLens-Umgebung](hololens-environment-considerations.md)** Informationen zu Faktoren, die die Qualität des Hologramms verbessern.

## <a name="restart"></a>Neu starten

### <a name="do-a-safe-restart-by-using-cortana"></a>Sicheres Neustarten mit Cortana

Die sicherste Möglichkeit zum Neustarten der HoloLens ist die Verwendung von Cortana. Dies ist in der Regel der erste Versuch, wenn ein Problem mit HoloLens vor sich geht.

> [!NOTE] 
> Cortana ist nicht auf allen Geräten verfügbar.
> - Cortana ist auf allen HoloLens-Geräten (1. Generation) verfügbar. 
> - Cortana ist auf HoloLens 2 auf Builds vor dem Windows Holograpic, Version 2004-Update, verfügbar.

1. Aktivieren Sie Ihre HoloLens.
1. Stellen Sie sicher, dass ein Benutzer angemeldet ist und das Gerät nicht darauf wartet, dass ein Kennwort entsperrt wird.
2. Sagen Sie "Hey Cortana, neustart" oder "Hey Cortana, restart".
3. Cortana antwortet und fordert Sie zur Bestätigung auf. Warten Sie, bis nach der Frage ein Sound abspielt, und sagen Sie dann "Ja". Das Gerät wird neu gestartet.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Verwenden des Netzschalters für einen sicheren Neustart

Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie, es mithilfe des **Netzschalters** neu zu starten:

1. Drücken Sie , und halten Sie den **Netzschalter** 5 Sekunden lang gedrückt. Nach einer Sekunde werden alle fünf LEDs leuchtet und dann langsam nacheinander von rechts nach links ausgeschaltet. Nach 5 Sekunden sind alle LEDs ausgeschaltet, was auf ein erfolgreiches Herunterfahren hinweist.
      
   > [!IMPORTANT]
   > Halten Sie das Drücken der Schaltfläche sofort an, nachdem alle LEDs ausgeschaltet wurden.
1. Warten Sie eine Minute, bis das Herunterfahren abgeschlossen ist. Das Herunterfahren kann auch nach dem Deaktivieren der Anzeigen noch ausgeführt werden.
2. Schalten Sie das Gerät erneut ein, indem Sie 1 Sekunde lang den **Netzschalter** drücken und halten.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Durchführen eines sicheren Neustarts mithilfe von Windows-Geräteportal

> [!NOTE]
> Für diesen Prozess muss HoloLens als Entwicklergerät konfiguriert werden. Weitere Informationen finden Sie unter [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Wenn das vorherige Verfahren nicht funktioniert hat, versuchen Sie, das Gerät neu zu starten, indem Sie [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)verwenden. Suchen Sie in der oberen rechten Ecke nach der Option zum Neustarten oder Herunterfahren des Geräts.

### <a name="do-an-unsafe-forced-restart"></a>Durchführen eines unsicheren erzwungenen Neustarts

Wenn die vorherigen Methoden Ihre HoloLens nicht neu gestartet haben, erzwingen Sie einen Neustart. Diese Methode entspricht dem Entfernen und erneuten Installieren des Akkus. Dies ist gefährlich, da ihr Gerät möglicherweise beschädigt ist. In diesem Fall müssen Sie Ihre HoloLens flashen.  

> [!WARNING]
> Dies ist eine potenziell schädliche Methode und sollte nur verwendet werden, wenn die zuvor genannten Methoden nicht funktioniert haben.

1. Halten Sie den **Netzschalter** mindestens 10 Sekunden gedrückt.
   - Es ist in Ordnung, die Schaltfläche länger als 10 Sekunden zu halten.
   - Es ist sicher, alle LED-Aktivitäten zu ignorieren.
1. Lassen Sie die Schaltfläche los, und warten Sie 2 bis 3 Sekunden.
1. Halten Sie den **Netzschalter** 1 Sekunde gedrückt.
1. Wenn weiterhin Probleme auftreten,  drücken Sie 4 Sekunden lang den Netzschalter, bis alle Akkuindikatoren ausblenden und der Bildschirm die Anzeige von Hologrammen beendet. Warten Sie eine Minute, und drücken Sie dann **erneut** den Netzschalter, um das Gerät einschalten.

## <a name="reset-to-factory-settings"></a>Auf Werkseinstellungen zurücksetzen

> [!NOTE]
> Der Akku benötigt mindestens eine Gebühr von 40 Prozent, um zurückzusetzen.

Wenn ihre HoloLens weiterhin ein Problem hat, versuchen Sie, sie auf den Factoryzustand zurücksetzungen. In diesem Schritt wird die Version der Windows Holographic-Software, die darauf installiert ist, und alles andere an die Werkseinstellungen zurückgegeben.

>[!WARNING]
> Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre personenbezogenen Daten, Apps und Einstellungen gelöscht, einschließlich informationen zur TPM-Zurücksetzung. Durch zurücksetzen wird nur die neueste installierte Version von Windows Holographic installiert. Sie müssen alle Initialisierungsschritte wiederholen (Kalibrieren, Herstellen einer Wlan-Verbindung, Erstellen eines Benutzerkontos, Herunterladen von Apps und so weiter).

1. Öffnen Sie die App Einstellungen, und wählen Sie dann **Wiederherstellung**  >  **aktualisieren aus.**
1. Wählen Sie die **Option Gerät zurücksetzen** aus, und lesen Sie die Bestätigungsmeldung.
1. Bestätigen Sie die Zurücksetzung. Das Gerät wird neu gestartet und zeigt eine Reihe von drehenden Zahnraden und eine Statusanzeige an.
1. Warten Sie ca. 30 Minuten, bis dieser Vorgang abgeschlossen ist. Wenn dies geschehen ist, wird das Gerät in der "vorgeschachtelten" Begehung neu gestartet.

## <a name="reinstall-the-operating-system"></a>Erneutes Installieren des Betriebssystems

Wenn das Gerät nach dem Neustart und Zurücksetzen weiterhin ein Problem hat, können Sie ein Wiederherstellungstool auf Ihrem Computer verwenden, um das HoloLens-Betriebssystem und die Firmware neu zu installieren.  

Die Daten, die HoloLens für das Zurücksetzen benötigt, sind in einem Full Flash Update (FFU) gepackt, das einer ISO-, WIM- oder VHD-Datei ähnelt. [Erfahren Sie mehr über FFU-Bilddateiformate.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Sie können ein neues Betriebssystem auf HoloLens (1. Generation) installieren, indem Sie das Windows Device Recovery Tool verwenden. Bevor Sie dieses Tool verwenden, sollten Sie prüfen, ob das Problem durch einen Neustart oder zurücksetzen ihrer HoloLens behoben wird.

Der Wiederherstellungsprozess kann eine Weile dauern. Wenn dies abgeschlossen ist, wird die neueste Version der Windows Holographic-Software installiert.

Um das Tool verwenden zu können, benötigen Sie einen Computer mit Windows 10 oder höher mit mindestens 4 GB freiem Speicherplatz. Sie können dieses Tool nicht auf einem virtuellen Computer ausführen.

### <a name="recover-your-hololens"></a>Wiederherstellen Ihrer HoloLens

1. Laden Sie das [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) herunter, und installieren Sie es auf Ihrem Computer.
1. Verbinden Sie die HoloLens (1. Generation) mit Ihrem Computer, indem Sie das Micro-USB-Kabel verwenden, das mit Ihrer HoloLens geliefert wurde.
1. Öffnen Sie das Windows Device Recovery Tool, und befolgen Sie die Anweisungen.

Wenn HoloLens (1. Generation) nicht automatisch erkannt wird, wählen Sie **Mein Gerät wurde nicht erkannt aus.** Befolgen Sie dann die Anweisungen, um das Gerät in den Wiederherstellungsmodus zu versetzen.

### <a name="manual-flashing-mode"></a>Manueller Flashmodus

Wenn Ihr Gerät nicht erkannt wird, führen Sie die folgenden Schritte aus, um es in den Flashmodus zu versetzen:

1. Trennen Sie das Gerät von einer beliebigen Stromquelle.
1. Wenn das Gerät eingeschaltet ist, halten Sie den **Netzschalter** gedrückt, bis er vollständig ausgeschaltet ist.
2. Halten Sie das **Volume gedrückt,** und tippen Sie kurz auf **den Netzschalter.** Das Gerät sollte starten und nur das mittlere LED-Licht anzeigen.
3. Schließen Sie das Gerät an Ihren PC an.
4. Öffnen Sie das Windows-Tool für die Gerätewiederherstellung.
5. Wählen **Sie Mein Gerät wurde nicht erkannt und** dann **HoloLens aus.** 
6. Befolgen Sie die Anweisungen zum Wiederherstellen Ihres Geräts.
