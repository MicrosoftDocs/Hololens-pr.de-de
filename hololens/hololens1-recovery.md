---
title: HoloLens 1 neustarten, zurücksetzen oder wiederherstellen
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
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
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f50a885f6cc82256d146d7f4914aca934e81c0c0
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439041"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens (1. Generation) neustarten, zurücksetzen oder wiederherstellen

Wenn Sie Probleme mit Ihrem HoloLens haben, können Sie versuchen, das Gerät neu zu starten, zurückzusetzen oder sogar neu zu flashen, indem Sie die Gerätewiederherstellung verwenden. Dieser Artikel führt Sie durch die empfohlenen Schritte für die Wiederherstellung.

Wenn Sie ein HoloLens 2 wiederherstellen möchten, finden Sie Informationen dazu unter [Wiederherstellen eines HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), da sich der Vorgang unterscheidet.

> [!NOTE]
> Dieser Artikel befasst sich mit dem HoloLens-Gerät und der entsprechenden Software. Wenn Ihre Hologramme nicht richtig aussehen, finden Sie Informationen zu Faktoren, die die Qualität des Hologramms verbessern, unter **[Umgebungsaspekte für HoloLens](hololens-environment-considerations.md)**.

## <a name="restart"></a>Neu starten

### <a name="do-a-safe-restart-by-using-cortana"></a>Durchführen eines sicheren Neustarts mithilfe von Cortana

Die sicherste Methode zum Neustarten des HoloLens ist die Verwendung von Cortana, was im Allgemeinen das erste ist, was Sie versuchen können, wenn ein Problem mit HoloLens auftritt.

> [!NOTE] 
> Cortana ist nicht auf allen Geräten verfügbar.
> - Cortana ist für alle HoloLens-Geräte der ersten Generation verfügbar. 
> - Cortana ist auf HoloLens 2-Geräten mit Builds vor dem Update mit Windows Holograpic, Version 2004, verfügbar.

1. Schalten Sie Ihr HoloLens ein.
1. Vergewissern Sie sich, dass ein Benutzer angemeldet ist und das Gerät nicht auf ein Kennwort wartet, um es zu entsperren.
2. Sagen Sie "Hey Cortana, erneut starten" oder "Hey Cortana, Neustart".
3. Cortana antwortet und fordert Sie zur Bestätigung auf. Warten Sie, bis nach der Frage ein Sound wiedergegeben wird, und sagen Sie dann "Ja". Das Gerät wird neu gestartet.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Verwenden des Netzschalters für einen sicheren Neustart

Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie, es mit dem **Netzschalter** neu zu starten:

1. Halten Sie den **Netzschalter** 5 Sekunden lang gedrückt. Nach einer Sekunde leuchten alle fünf LEDs. Danach werden sie einzeln von rechts nach links langsam abgeschaltet. Nach fünf Sekunden sind alle LEDs aus, was bedeutet, dass das Herunterfahren erfolgreich war.
      
   > [!IMPORTANT]
   > Lassen Sie die Taste unmittelbar nach dem Ausschalten aller LEDs los.
1. Warten Sie 1 Minute, bis das Herunterfahren abgeschlossen ist. Beachten Sie, dass der Vorgang des Herunterfahrens möglicherweise weiterhin ausgeführt wird, auch wenn die Anzeigen deaktiviert sind.
2. Schalten Sie das Gerät erneut ein, indem Sie den **Netzschalter** eine Sekunde lang gedrückt halten.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Durchführen eines sicheren Neustarts mithilfe des Windows-Geräteportals

> [!NOTE]
> Für diesen Vorgang muss HoloLens als Entwicklergerät konfiguriert sein. Weitere Informationen finden Sie im [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Wenn das vorstehende Verfahren nicht funktioniert, können Sie versuchen, das Gerät mithilfe des [Windows-Geräteportals](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) neu zu starten. In der oberen rechten Ecke gibt es eine Option, um das Gerät neu zu starten oder herunterzufahren.

### <a name="do-an-unsafe-forced-restart"></a>Durchführen eines unsicheren erzwungenen Neustarts

Wenn die vorstehenden Methoden Ihr HoloLens nicht neu starten, erzwingen Sie einen Neustart. Diese Methode entspricht dem Entfernen und erneuten Einlegen der Batterie. Das ist gefährlich, da Ihr Gerät möglicherweise Schaden nimmt. In diesem Fall müssen Sie bei Ihrem HoloLens einen Flash ausführen.  

> [!WARNING]
> Dies ist eine potenziell schädliche Methode und sollte nur verwendet werden, wenn keine der vorhergehenden Methoden funktioniert.

1. Halten Sie den **Netzschalter** mindestens 10 Sekunden lang gedrückt.
   - Es ist in Ordnung, die Taste länger als 10 Sekunden zu halten.
   - Sie können die LED-Aktivitäten ignorieren.
1. Lassen Sie den Schalter los, und warten Sie zwei oder drei Sekunden.
1. Halten Sie den **Netzschalter** 1 Sekunde lang gedrückt.
1. Wenn Sie weiterhin Probleme haben, drücken Sie den **Netzschalter** 4 Sekunden lang, bis alle Akkuanzeigen aus sind und der Bildschirm keine Hologramme mehr anzeigt. Warten Sie 1 Minute, und drücken Sie dann erneut den **Netzschalter**, um das Gerät einzuschalten.

## <a name="reset-to-factory-settings"></a>Zurücksetzen von Geräten auf Werkseinstellungen

> [!NOTE]
> Der Akkustand muss mindestens bei 40 Prozent liegen, damit der Zurücksetzungsvorgang erfolgreich ausgeführt werden kann. 

Wenn Ihr HoloLens weiterhin ein Problem hat, versuchen Sie, es auf den Werkszustand zurückzusetzen. Durch diesen Schritt wird die Version der Windows Holographic-Software beibehalten, die auf dem Computer installiert ist, und alle anderen Elemente werden auf die Werkseinstellungen zurückgesetzt.

>[!WARNING]
> Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzungsinformationen. Durch das Zurücksetzen wird nur die zuletzt installierte Version von Windows Holographic installiert. Sie müssen alle Initialisierungsschritte (Kalibrieren, Verbindung mit WLAN, Erstellen eines Benutzerkontos, Herunterladen von Apps usw.) wiederholen.

1. Öffnen Sie die App „Einstellungen“, und wählen Sie **Update** > **Wiederherstellung** aus.
1. Wählen Sie die Option **Gerät zurücksetzen** aus, und lesen Sie die Bestätigungsmeldung.
1. Bestätigen Sie das Zurücksetzen. Das Gerät wird neu gestartet, und es wird eine Reihe von rotierenden Zahnrädern mit einer Statusanzeige angezeigt.
1. Warten Sie etwa 30 Minuten, bis dieser Vorgang durchgeführt wird. Das Zurücksetzen wird durchgeführt, und das Gerät wird in die sofort verwendbare Umgebung neu gestartet.

## <a name="reinstall-the-operating-system"></a>Neuinstallation des Betriebssystems

Wenn nach dem Neustart und Zurücksetzen des Geräts weiterhin ein Problem auftritt, können Sie auf Ihrem Computer ein Wiederherstellungstool verwenden, um das Betriebssystem und die Firmware des HoloLens neu zu installieren.  

Die Daten, die HoloLens für das Zurücksetzen benötigt, sind in einem Full Flash-Update (FFU) gepackt, das einer ISO-, WIM- oder VHD-Datei ähnelt. [Erfahren Sie mehr über die FFU Bilddateiformate.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Sie können ein neues Betriebssystem auf Ihrem HoloLens (1. Generation) mit dem Windows Device Recovery Tool installieren. Bevor Sie dieses Tool verwenden, überprüfen Sie, ob das Problem Ihres HoloLens durch Neustart oder Zurücksetzen behoben wird.

Der Wiederherstellungsvorgang kann einige Zeit in Anspruch nehmen. Wenn Sie damit fertig sind, wird die neueste Version der Windows Holographic-Software für Ihr HoloLens installiert.

Wenn Sie das Tool verwenden möchten, benötigen Sie einen Computer mit Windows 10 oder höher mit mindestens 4 GB freien Speicherplatz. Sie können dieses Tool nicht auf einem virtuellen Computer ausführen.

### <a name="recover-your-hololens"></a>Wiederherstellung Ihres HoloLens

1. [Windows-Geräte Wiederherstellung Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) auf Ihrem Computer herunterladen und installieren.
1. Schließen Sie Ihr HoloLens (1. Generation) an Ihren Computer an, indem Sie das Micro-USB-Kabel verwenden, das im Lieferumfang Ihres HoloLens enthalten war.
1. Öffnen Sie das Windows Device Recovery Tool, und folgen Sie den Anweisungen.

Wenn das HoloLens (1. Generation) nicht automatisch erkannt wird, wählen Sie **Mein Gerät wurde nicht erkannt** aus. Folgen Sie dann den Anweisungen, um das Gerät in den Wiederherstellungsmodus zu versetzen.

### <a name="manual-flashing-mode"></a>Manueller Flashmodus

Wenn Ihr Gerät nicht erkannt wird, führen Sie die folgenden Schritte aus, um es in den Flashmodus zu versetzen:

1. Trennen Sie das Gerät von allen Stromquellen.
1. Wenn das Gerät eingeschaltet ist, halten Sie den **Netzschalter** gedrückt, bis es vollständig ausgeschaltet ist.
2. Halten Sie die **Lauter**-Taste gedrückt, und tippen Sie kurz auf den **Netzschalter**. Das Gerät sollte starten, und nur die mittlere LED sollte leuchten.
3. Verbinden Sie das Gerät mit Ihrem PC.
4. Öffnen Sie das Windows Device Recovery Tool.
5. Wählen Sie **Mein Gerät wurde nicht erkannt** und dann **HoloLens** aus. 
6. Befolgen Sie die Anweisungen, um das Gerät wiederherzustellen..
