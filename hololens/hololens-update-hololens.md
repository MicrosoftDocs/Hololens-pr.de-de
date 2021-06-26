---
title: Update HoloLens 2
description: Erfahren Sie, wie Sie Ihre HoloLens-Buildnummer überprüfen, mit Geräteupdates auf dem Laufenden bleiben, am Insider-Programm teilnehmen und ein Rollback für Updates erstellen.
keywords: How-to, update, rollback, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924110"
---
# <a name="update-hololens-2"></a>Update HoloLens 2

HoloLens verwendet Windows Update, genau wie andere Windows 10 Geräte. Ihre HoloLens wird automatisch Systemupdates herunterladen und installieren, wenn sie an die Stromversorgung angeschlossen und mit dem Internet verbunden ist, auch wenn sie sich im Standbymodus befindet.

In diesem Artikel werden die HoloLens-Tools für:

- Anzeigen ihrer aktuellen Betriebssystemversion (Buildnummer)
- Suchen nach Updates
- Manuelles Aktualisieren von HoloLens
- Roll back to a older update (Roll back zu einem älteren Update)

## <a name="check-your-operating-system-version-build-number"></a>Überprüfen Ihrer Betriebssystemversion (Buildnummer)

Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie die App Einstellungen öffnen und **System about**  >  **auswählen.**

## <a name="check-for-updates-and-manually-update"></a>Suchen nach Updates und manuelles Aktualisieren

Sie können jederzeit in den Einstellungen nach Updates suchen.  So sehen Sie verfügbare Updates und suchen nach neuen Updates:

1. Öffnen Sie die App **Einstellungen**.
1. Navigieren Sie **zu Update & Security**  >  **Windows Update**.
1. Wählen Sie **Nach Updates suchen** aus.

Wenn ein Update verfügbar ist, wird mit dem Herunterladen der neuen Version gestartet. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen. Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, beginnt der Neustart nicht mit der Installation des Updates.

Während Ihre HoloLens das Update installiert, werden spinnende Zahnrad und eine Statusanzeige angezeigt. Deaktivieren Sie Ihre HoloLens während dieser Zeit nicht. Er wird automatisch neu gestartet, sobald die Installation abgeschlossen ist.

HoloLens wendet ein Update nach dem anderen an.  Wenn Ihre HoloLens mehr als eine Version hinter der neuesten version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.

## <a name="go-back-to-a-previous-version"></a>Zurück zu einer früheren Version

In einigen Fällen sollten Sie zu einer früheren Version der HoloLens-Software zurückkommen. Die folgenden Schritte werden empfohlen:

1. Wenden Sie sich an den Support, um zu erfahren, ob er Ihr Problem beheben kann.
    1. Stellen Sie **sicher, dass** **optionale** oder vollständige Telemetrie aktiviert ist. Dadurch wird Ihr Fehler umsetzbarer und einfacher für Techniker zu diagnostizieren.
    1. [Das Feedback zur](hololens-feedback.md) Datei ist so beschreibend wie möglich. Notieren Sie sich den Titel, oder verwenden Sie das Freigabefeature, damit Sie Ihren Fehler für den Support freigeben können.
    1. Wenden Sie [sich an den Support.](https://aka.ms/hlsupport) Wenn Ihr Problem gelöst werden muss, indem sie zu einer früheren Version zurückkehren, können sie Ihnen die FFU zum Flashen Ihres Geräts zur Verfügung geben.

1. Wenn dies nicht funktioniert, setzen Sie Ihre Daten zurück, oder geben Sie HoloLens 2 [Advanced Recovery Companion erneut aus.](hololens-recovery.md)
    1. Laden Sie auf Ihrem PC den [Advanced Recovery Companion aus](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dem Microsoft Store.
    1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren PC angeschlossen sind.
    1. Wählen Sie aus, für welche Version Sie flashen möchten:
        1. Sie können die [neueste Version HoloLens 2 herunterladen.](https://aka.ms/hololens2download)
        1. Sie können den Standard-Build verwenden, den ARC hostet. (Wenn Sie diese Option auswählen, überspringen Sie den nächsten Schritt.)
        1. Sie können einen Buildsupport verwenden, der Ihnen zur Verfügung gestellt wird.
    1. Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer**  >  **Downloads**. Klicken Sie mit der rechten Maustaste auf den zip-Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **Alle** extrahieren  >  **aus,** um ihn zu entzippen.
    1. Verbinden Sie Ihre HoloLens mit ihrem PC, indem Sie ein USB-A-zu-USB-C-Kabel verwenden. (Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dies am besten.)
    1. Advanced Recovery Companion erkennt Ihre HoloLens automatisch. Wählen Sie **die Microsoft HoloLens** aus.
    1. Wählen Sie auf dem nächsten Bildschirm **Manuelle** Paketauswahl und dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung .ffu.)
    1. Wählen **Sie Software installieren** aus, und befolgen Sie die Anweisungen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkommen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Wenn Sie das derzeit installierte Release weiterhin verwenden möchten, können Sie Updates auch [manuell anhalten.](hololens-updates.md#pause-updates-via-device) Dies gibt dem Engineering-Team Zeit, das Problem zu beheben.

## <a name="windows-insider-program-on-hololens"></a>Windows-Insider-Programm auf HoloLens

Möchten Sie die neuesten Features in HoloLens sehen?  Wenn ja, treten Sie dem Windows-Insider-Programm bei. Sie erhalten Zugriff auf Vorschauversionen von HoloLens-Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.

[Hier Windows-Insider Vorschauversion für Microsoft HoloLens.](hololens-insider.md)
