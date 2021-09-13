---
title: Neustarten, Zurücksetzen oder Wiederherstellen HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Verwenden Windows Device Recovery Tools zum Flashen eines Images in HoloLens 1. Generation.
keywords: 'Gewusst wie: Vorgehensweise, Neustart, Zurücksetzen, Wiederherstellen, Hartes Zurücksetzen, Soft Reset, Energiezyklus, HoloLens, herunterfahren, WDRT, Windows-Gerätewiederherstellungstool'
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032794"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Neustarten, Zurücksetzen oder Wiederherstellen HoloLens (1. Generation)

Wenn Sie Probleme mit Ihrem HoloLens haben, können Sie einen Neustart oder eine Zurücksetzung versuchen oder das Gerät mithilfe der Gerätewiederherstellung zurücksetzen. In diesem Artikel werden die empfohlenen Wiederherstellungsschritte in der gewünschten Reihenfolge erläutert.

Wenn Sie eine HoloLens 2 wiederherstellen möchten, lesen Sie [Wiederherstellen eines HoloLens 2](hololens-recovery.md), da sich dieser Prozess unterscheidet.

> [!NOTE]
> Dieser Artikel konzentriert sich auf die HoloLens Gerät und Software. Wenn Ihre Hologramme nicht richtig aussehen, finden Sie unter **[Überlegungen HoloLens Umgebung](hololens-environment-considerations.md)** Informationen zu Faktoren, die die Hologrammqualität verbessern.

## <a name="restart"></a>Neu starten

### <a name="do-a-safe-restart-by-using-cortana"></a>Durchführen eines sicheren Neustarts mithilfe von Cortana

Die sicherste Möglichkeit, die HoloLens neu zu starten, ist die Verwendung von Cortana. Dies ist in der Regel das erste, was Sie ausprobieren sollten, wenn ein Problem mit HoloLens vorliegt.

> [!NOTE] 
> Cortana ist nicht auf allen Geräten verfügbar.
> - Cortana ist auf allen geräten HoloLens (1. Generation) verfügbar. 
> - Cortana ist auf HoloLens 2 Geräten in Builds vor dem Windows Holograpic, Version 2004, verfügbar.

1. Aktivieren Sie Ihre HoloLens.
1. Stellen Sie sicher, dass ein Benutzer angemeldet ist und das Gerät nicht auf das Entsperren eines Kennworts wartet.
2. Sagen Sie "Hey Cortana, reboot" oder "Hey Cortana, restart".
3. Cortana antworten und sie zur Bestätigung auffordern. Warten Sie, bis nach der Frage ein Sound wiedergegeben wird, und sagen Sie dann "Ja". Das Gerät wird neu gestartet.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Verwenden des Netzschalters für einen sicheren Neustart

Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie, es mithilfe des **Netzschalters** neu zu starten:

1. Drücken Sie , und halten Sie den **Netzschalter** 5 Sekunden lang gedrückt. Nach einer Sekunde werden alle fünf LEDs leuchtet und dann von rechts nach links langsam nacheinander ausgeschaltet. Nach 5 Sekunden sind alle LEDs ausgeschaltet, was auf ein erfolgreiches Herunterfahren hinweist.
      
   > [!IMPORTANT]
   > Halten Sie das Drücken der Schaltfläche sofort an, nachdem alle LEDs ausgeschaltet wurden.
1. Warten Sie eine Minute, bis das Herunterfahren abgeschlossen ist. Das Herunterfahren kann auch nach dem Deaktivieren der Anzeigen noch ausgeführt werden.
2. Schalten Sie das Gerät erneut ein, indem Sie 1 Sekunde lang den **Netzschalter** drücken und halten.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Durchführen eines sicheren Neustarts mit Windows Geräteportal

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
1. Wenn die Downloads abgeschlossen sind, öffnen **Sie Den Datei-Explorer**  >  **lädt herunter.** Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie gerade heruntergeladen haben, und wählen Sie Extract all Extract (Alle Extrahieren **extrahieren)**  >   aus, um ihn zu entzippen.
1. Verbinden Ihre HoloLens mithilfe des Micro-USB-Kabels an Ihren PC. (Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dieses am besten.)
1. Das WDRT erkennt automatisch Ihre HoloLens. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Klicken Sie auf dem nächsten Bildschirm auf **Manuelle Paketauswahl,** und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung .ffu.)
1. Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen.

> [!NOTE]
> Wenn WDRT Ihre HoloLens nicht erkennt, starten Sie Ihren PC neu. Falls dies nicht funktioniert, wählen Sie **Mein Gerät wurde nicht erkannt** und dann **Microsoft HoloLens** aus, und befolgen Sie die Anweisungen.

## <a name="reset-to-factory-settings"></a>Zurücksetzen auf Werkseinstellungen

> [!NOTE]
> Für die Akkukapazität ist mindestens eine Gebühr von 40 Prozent erforderlich.

Wenn ihr HoloLens weiterhin ein Problem hat, versuchen Sie, ihn auf den Werkszustand zurückzusetzen. Dieser Schritt behält die Version der Windows Holographic-Software bei, die darauf installiert ist, und gibt alles andere an die Werkseinstellungen zurück.

>[!WARNING]
> Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre personenbezogenen Daten, Apps und Einstellungen gelöscht, einschließlich tpm-Zurücksetzungsinformationen. Beim Zurücksetzen wird nur die neueste installierte Version von Windows Holographic installiert. Sie müssen alle Initialisierungsschritte wiederholen (Kalibrieren, Herstellen einer Wlan-Verbindung, Erstellen eines Benutzerkontos, Herunterladen von Apps usw.).

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

### <a name="recover-your-hololens"></a>Wiederherstellen ihrer HoloLens

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
5. Wählen **Sie Mein Gerät wurde nicht erkannt aus,** und klicken Sie **HoloLens**. 
6. Befolgen Sie die Anweisungen zum Wiederherstellen Ihres Geräts.
