---
title: Neustarten, Zurücksetzen oder Wiederherstellen HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Verwenden Windows Device Recovery Tools zum Flashen eines Images in HoloLens 1. Generation.
keywords: 'Gewusst wie: Vorgehensweise, Neustart, Zurücksetzen, Wiederherstellen, hard reset, Soft Reset, Energiezyklus, HoloLens, herunterfahren, wdrt, Windows-Gerätewiederherstellungstool'
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
ms.openlocfilehash: d6eb706c50e97a81910180c70be1d9dbc52bc6603cbc77ad130c1dd3b6a9010e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661804"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Neustarten, Zurücksetzen oder Wiederherstellen HoloLens (1. Generation)

Wenn Sie Probleme mit Ihrem HoloLens haben, können Sie einen Neustart oder eine Zurücksetzung versuchen oder das Gerät mithilfe der Gerätewiederherstellung zurücksetzen. In diesem Artikel werden die empfohlenen Wiederherstellungsschritte in der gewünschten Reihenfolge erläutert.

Wenn Sie eine HoloLens 2 wiederherstellen möchten, lesen Sie [Wiederherstellen eines HoloLens 2](hololens-recovery.md), da sich dieser Prozess unterscheidet.

> [!NOTE]
> Dieser Artikel konzentriert sich auf die HoloLens Gerät und Software. Wenn Ihre Hologramme nicht richtig aussehen, finden Sie unter **[Überlegungen HoloLens Umgebung](hololens-environment-considerations.md)** Informationen zu Faktoren, die die Hologrammqualität verbessern.

## <a name="restart"></a>Neu starten

### <a name="do-a-safe-restart-by-using-cortana"></a>Durchführen eines sicheren Neustarts mithilfe von Cortana

Die sicherste Möglichkeit zum Neustarten des HoloLens ist die Verwendung von Cortana. Dies ist in der Regel das erste, was Sie ausprobieren sollten, wenn ein Problem mit HoloLens vorliegt.

> [!NOTE] 
> Cortana ist nicht auf allen Geräten verfügbar.
> - Cortana ist auf allen geräten HoloLens (1. Generation) verfügbar. 
> - Cortana ist auf HoloLens 2 Geräten in Builds vor dem Windows Holograpic, Version 2004, verfügbar.

1. Aktivieren Sie Ihre HoloLens.
1. Stellen Sie sicher, dass ein Benutzer angemeldet ist und das Gerät nicht auf das Entsperren eines Kennworts wartet.
2. Sagen Sie "Hey Cortana, reboot" oder "Hey Cortana, restart".
3. Cortana antwortet und Sie zur Bestätigung auffordert. Warten Sie, bis nach der Frage ein Sound wiedergegeben wird, und sagen Sie dann "Ja". Das Gerät wird neu gestartet.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Verwenden des Netzschalters für einen sicheren Neustart

Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie, es mithilfe des **Netzschalters** neu zu starten:

1. Drücken Sie , und halten Sie den **Netzschalter** 5 Sekunden lang gedrückt. Nach einer Sekunde werden alle fünf LEDs leuchtet und dann von rechts nach links langsam nacheinander ausgeschaltet. Nach 5 Sekunden sind alle LEDs ausgeschaltet, was auf ein erfolgreiches Herunterfahren hinweist.
      
   > [!IMPORTANT]
   > Halten Sie das Drücken der Schaltfläche sofort an, nachdem alle LEDs ausgeschaltet wurden.
1. Warten Sie eine Minute, bis das Herunterfahren abgeschlossen ist. Das Herunterfahren kann auch nach dem Deaktivieren der Anzeigen noch ausgeführt werden.
2. Schalten Sie das Gerät erneut ein, indem Sie 1 Sekunde lang den **Netzschalter** drücken und halten.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Durchführen eines sicheren Neustarts mithilfe von Windows Geräteportal

> [!NOTE]
> Für diesen Prozess muss HoloLens als Entwicklergerät konfiguriert werden. Weitere Informationen finden Sie unter [Windows Geräteportal](/windows/mixed-reality/using-the-windows-device-portal).

Wenn das vorherige Verfahren nicht funktioniert hat, versuchen Sie, das Gerät neu zu starten, indem Sie [Windows Geräteportal](/windows/mixed-reality/using-the-windows-device-portal)verwenden. Suchen Sie in der oberen rechten Ecke nach der Option zum Neustarten oder Herunterfahren des Geräts.

### <a name="do-an-unsafe-forced-restart"></a>Durchführen eines unsicheren erzwungenen Neustarts

Wenn die vorherigen Methoden Ihren HoloLens nicht neu gestartet haben, erzwingen Sie einen Neustart. Diese Methode entspricht dem Entfernen und erneuten Installieren des Akkus. Dies ist gefährlich, da ihr Gerät möglicherweise beschädigt ist. In diesem Fall müssen Sie Ihre HoloLens flashen.  

> [!WARNING]
> Dies ist eine potenziell schädliche Methode und sollte nur verwendet werden, wenn die zuvor genannten Methoden nicht funktioniert haben.

1. Halten Sie den **Netzschalter** mindestens 10 Sekunden lang gedrückt.
   - Es ist in Ordnung, die Schaltfläche länger als 10 Sekunden zu halten.
   - Es ist sicher, alle LED-Aktivitäten zu ignorieren.
1. Lassen Sie die Schaltfläche los, und warten Sie 2 bis 3 Sekunden.
1. Drücken Sie , und halten Sie den **Netzschalter** 1 Sekunde lang gedrückt.
1. Wenn weiterhin Probleme auftreten, drücken Sie 4 Sekunden lang den **Netzschalter,** bis alle Akkuindikatoren ausgeblendet sind und der Bildschirm die Anzeige von Hologrammen beendet. Warten Sie eine Minute, und drücken Sie dann erneut den **Netzschalter,** um das Gerät einzuschalten.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Zurück zu einer früheren Version – HoloLens (1. Generation)

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren. Hierzu können Sie das Windows Device Recovery Tool verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 1 zurückzukehren:

1. Stellen Sie sicher, dass keine Telefone oder Windows Geräte an Ihren PC angeschlossen sind.
1. Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)herunter.
1. Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery) herunter.
1. Wenn die Downloads abgeschlossen sind, öffnen **Sie Den Datei-Explorer**  >  **lädt herunter.** Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie gerade heruntergeladen haben, und wählen **Sie Alle**  >  **extrahieren** aus, um ihn zu entzippen.
1. Verbinden Ihre HoloLens mithilfe des Micro-USB-Kabels an Ihren PC. (Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dieses am besten.)
1. Das WDRT erkennt automatisch Ihre HoloLens. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Klicken Sie auf dem nächsten Bildschirm auf **Manuelle Paketauswahl,** und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der FFU-Erweiterung.)
1. Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen.

> [!NOTE]
> Wenn WDRT Ihre HoloLens nicht erkennt, versuchen Sie, Ihren PC neu zu starten. Falls dies nicht funktioniert, wählen Sie **Mein Gerät wurde nicht erkannt** und dann **Microsoft HoloLens** aus, und befolgen Sie die Anweisungen.

## <a name="reset-to-factory-settings"></a>Zurücksetzen auf Werkseinstellungen

> [!NOTE]
> Der Akku benötigt mindestens eine Gebühr von 40 Prozent, um zurückgesetzt zu werden.

Wenn ihr HoloLens weiterhin ein Problem hat, versuchen Sie, ihn auf den Werkszustand zurückzusetzen. Dieser Schritt behält die Version der Windows Holographic-Software bei, die darauf installiert ist, und gibt alles andere an die Werkseinstellungen zurück.

>[!WARNING]
> Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre personenbezogenen Daten, Apps und Einstellungen gelöscht, einschließlich Informationen zur TPM-Zurücksetzung. Beim Zurücksetzen wird nur die neueste installierte Version von Windows Holographic installiert. Sie müssen alle Initialisierungsschritte wiederholen (Kalibrieren, Herstellen einer Wlan-Verbindung, Erstellen eines Benutzerkontos, Herunterladen von Apps usw.).

1. Öffnen Sie die Einstellungen-App, und wählen Sie dann  >  **Wiederherstellung aktualisieren** aus.
1. Wählen Sie die Option **Gerät zurücksetzen** aus, und lesen Sie die Bestätigungsmeldung.
1. Bestätigen Sie die Zurücksetzung. Das Gerät wird neu gestartet und zeigt eine Reihe von spinierenden Zahnradgeräten und eine Statusanzeige an.
1. Warten Sie ungefähr 30 Minuten, bis dieser Vorgang abgeschlossen ist. Wenn dies abgeschlossen ist, wird das Gerät sofort neu gestartet.

## <a name="reinstall-the-operating-system"></a>Erneutes Installieren des Betriebssystems

Wenn das Gerät nach dem Neustart und Zurücksetzen weiterhin ein Problem aufweist, können Sie ein Wiederherstellungstool auf Ihrem Computer verwenden, um das HoloLens Betriebssystem und die Firmware neu zu installieren.  

Die Daten, die HoloLens für das Zurücksetzen benötigen, sind in einem Full Flash Update (FFU) gepackt, das einer ISO-, WIM- oder VHD-Datei ähnelt. [Erfahren Sie mehr über FFU-Bilddateiformate.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Sie können ein neues Betriebssystem auf Ihrem HoloLens (1. Generation) installieren, indem Sie das Windows Device Recovery Tool verwenden. Bevor Sie dieses Tool verwenden, sollten Sie prüfen, ob das Problem durch neustarten oder zurücksetzen HoloLens behoben wird.

Der Wiederherstellungsprozess kann eine Weile dauern. Wenn dies abgeschlossen ist, wird die neueste Version der Windows Holographic-Software installiert.

Um das Tool verwenden zu können, benötigen Sie einen Computer mit Windows 10 oder höher mit mindestens 4 GB freiem Speicherplatz. Sie können dieses Tool nicht auf einem virtuellen Computer ausführen.

### <a name="recover-your-hololens"></a>Wiederherstellen Ihrer HoloLens

1. Laden Sie das [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) herunter, und installieren Sie es auf Ihrem Computer.
1. Verbinden die HoloLens (1. Generation) mithilfe des Micro-USB-Kabels, das im Lieferumfang Ihrer HoloLens war, an Ihren Computer.
1. Öffnen Sie das Windows Device Recovery Tool, und befolgen Sie die Anweisungen.

Wenn die HoloLens (1. Generation) nicht automatisch erkannt wird, wählen Sie **Mein Gerät wurde nicht erkannt aus.** Befolgen Sie dann die Anweisungen, um das Gerät in den Wiederherstellungsmodus zu versetzen.

### <a name="manual-flashing-mode"></a>Manueller Flashmodus

Wenn Ihr Gerät nicht erkannt wird, führen Sie die folgenden Schritte aus, um es in den Flashmodus zu versetzen:

1. Trennen Sie das Gerät von einer beliebigen Stromquelle.
1. Wenn das Gerät eingeschaltet ist, halten Sie den **Netzschalter** gedrückt, bis er vollständig ausgeschaltet ist.
2. Halten Sie das **Volume gedrückt,** und tippen Sie kurz auf **den Netzschalter.** Das Gerät sollte starten und nur die mittlere LED anzeigen.
3. Schließen Sie das Gerät an Ihren PC an.
4. Öffnen Sie das Windows Device Recovery Tool.
5. Wählen **Sie Mein Gerät wurde nicht erkannt und** dann **HoloLens.** 
6. Befolgen Sie die Anweisungen zum Wiederherstellen Ihres Geräts.
