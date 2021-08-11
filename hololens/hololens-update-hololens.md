---
title: Update HoloLens 2
description: Erfahren Sie, wie HoloLens Buildnummer überprüfen, mit Geräteupdates auf dem Laufenden bleiben, am Insider-Programm teilnehmen und ein Rollback für Updates erstellen.
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
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662840"
---
# <a name="update-hololens-2"></a>Update HoloLens 2

HoloLens verwendet Windows Update, genau wie andere Windows 10 Geräte. Ihr HoloLens wird automatisch Systemupdates herunterladen und installieren, wenn er an die Stromversorgung angeschlossen und mit dem Internet verbunden ist, auch wenn er sich im Standbymodus befindet.

In diesem Artikel werden die HoloLens für:

- Anzeigen ihrer aktuellen Betriebssystemversion (Buildnummer)
- Suchen nach Updates
- Manuelles Aktualisieren HoloLens
- Roll back to a older update (Roll back zu einem älteren Update)

## <a name="check-your-operating-system-version-build-number"></a>Überprüfen Ihrer Betriebssystemversion (Buildnummer)

Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie die Einstellungen-App öffnen und **System about**  >  **auswählen.**

## <a name="check-for-updates-and-manually-update"></a>Suchen nach Updates und manuelles Aktualisieren

Sie können in den Einstellungen jederzeit nach Updates suchen.  So sehen Sie verfügbare Updates und suchen nach neuen Updates:

1. Öffnen Sie die App **Einstellungen**.
1. Navigieren Sie **zu Update & Security** Windows  >  **Update**.
1. Wählen Sie **Nach Updates suchen** aus.

Wenn ein Update verfügbar ist, wird mit dem Herunterladen der neuen Version gestartet. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen. Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, beginnt der Neustart nicht mit der Installation des Updates.

Während ihr HoloLens das Update installiert, werden spinnende Zahnrad und eine Statusanzeige angezeigt. Deaktivieren Sie ihre HoloLens während dieser Zeit nicht. Sie wird nach Abschluss der Installation automatisch neu gestartet.

HoloLens wird ein Update nach dem anderen angewendet.  Wenn Ihr HoloLens mehr als eine Version hinter der neuesten Version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.

## <a name="go-back-to-a-previous-version"></a>Zurück zu einer früheren Version

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der Software HoloLens wechseln. Die folgenden Schritte werden empfohlen:

1. Wenden Sie sich an den Support, um zu erfahren, ob er Ihr Problem beheben kann.
    1. Stellen Sie **sicher, dass** **optionale** oder vollständige Telemetrie aktiviert ist. Dadurch wird Ihr Fehler umsetzbarer und einfacher für Techniker zu diagnostizieren.
    1. [Das Feedback zur](hololens-feedback.md) Datei ist so beschreibend wie möglich. Notieren Sie sich den Titel, oder verwenden Sie das Freigabefeature, damit Sie Ihren Fehler für den Support freigeben können.
    1. Wenden Sie [sich an den Support.](https://aka.ms/hlsupport) Wenn Ihr Problem gelöst werden muss, indem sie zu einer früheren Version zurückkehren, können sie Ihnen die FFU zum Flashen Ihres Geräts zur Verfügung geben.

1. Wenn dies nicht funktioniert, setzen Sie Ihre Daten mit dem Advanced [Recovery Companion zurück,](hololens-recovery.md)oder HoloLens 2 sie neu.
    1. Laden Sie auf Ihrem PC den [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) aus der Microsoft Store.
    1. Stellen Sie sicher, dass Keine Telefone oder Geräte Windows pc angeschlossen sind.
    1. Wählen Sie aus, für welche Version Sie flashen möchten:
        1. Sie können die [neueste Version HoloLens 2 herunterladen.](https://aka.ms/hololens2download)
        1. Sie können den Standard-Build verwenden, den ARC hostet. (Wenn Sie diese Option auswählen, überspringen Sie den nächsten Schritt.)
        1. Sie können einen Buildsupport verwenden, der Ihnen zur Verfügung gestellt wird.
    1. Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer**  >  **Downloads**. Klicken Sie mit der rechten Maustaste auf den zip-Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **Alle** extrahieren  >  **aus,** um ihn zu entzippen.
    1. Verbinden Sie HoloLens USB-A-zu-USB-C-Kabel an Ihren PC an. (Auch wenn Sie andere Kabel verwendet haben, um Ihre Verbindung HoloLens, funktioniert dies am besten.)
    1. Advanced Recovery Companion erkennt Ihre HoloLens. Wählen Sie die Kachel **Microsoft HoloLens** aus.
    1. Wählen Sie auf dem nächsten Bildschirm **Manuelle** Paketauswahl und dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung .ffu.)
    1. Wählen **Sie Software installieren** aus, und befolgen Sie die Anweisungen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkommen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Wenn Sie das derzeit installierte Release weiterhin verwenden möchten, können Sie Updates auch [manuell anhalten.](hololens-updates.md#pause-updates-via-device) Dies gibt dem Engineering-Team Zeit, das Problem zu beheben.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider-Programm HoloLens

Möchten Sie die neuesten Features in HoloLens?  Wenn ja, treten Sie dem Windows Insider-Programm bei. Sie erhalten Zugriff auf Vorschauversionen von HoloLens Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.

[Hier Windows Insider-Vorschau für Microsoft HoloLens.](hololens-insider.md)
