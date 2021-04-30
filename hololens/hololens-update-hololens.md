---
title: Aktualisieren von HoloLens
description: Erfahren Sie, wie Sie Ihre HoloLens-Buildnummer überprüfen, über Geräteupdates auf dem Laufenden bleiben, am Insiders-Programm teilnehmen und Updates zurücksetzen.
keywords: Vorgehensweise, Aktualisieren, Rollback, HoloLens, Überprüfen des Builds, Buildnummer
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308809"
---
# <a name="update-hololens"></a>Aktualisieren von HoloLens

HoloLens verwendet Windows Update wie andere Windows 10 Geräte. Ihre HoloLens lädt Systemupdates automatisch herunter und installiert sie, sobald sie an den Strom angeschlossen und mit dem Internet verbunden ist, auch wenn sie sich im Standbymodus befindet.

In diesem Artikel werden HoloLens-Tools für:

- Anzeigen der aktuellen Betriebssystemversion (Buildnummer)
- Überprüfen auf Updates
- Manuelles Aktualisieren von HoloLens
- Rollback zu einem älteren Update

## <a name="check-your-operating-system-version-build-number"></a>Überprüfen der Betriebssystemversion (Buildnummer)

Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie die App Einstellungen öffnen und **System**  >  **about** auswählen.

## <a name="check-for-updates-and-manually-update"></a>Suchen nach Updates und manuelles Aktualisieren

Sie können jederzeit in den Einstellungen nach Updates suchen.  So können Sie verfügbare Updates anzeigen und nach neuen Updates suchen:

1. Öffnen Sie die App **Einstellungen**.
1. Navigieren Sie zu **Update & Security**  >  **Windows Update**.
1. Wählen Sie **Nach Updates suchen** aus.

Wenn ein Update verfügbar ist, beginnt es mit dem Herunterladen der neuen Version. Wählen Sie nach Abschluss des Downloads die Schaltfläche **Jetzt neu starten** aus, um die Installation auszulösen. Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, startet der Neustart nicht mit der Installation des Updates.

Während Ihre HoloLens das Update installiert, werden spinnende Zahnrad und eine Statusanzeige angezeigt. Deaktivieren Sie Ihre HoloLens während dieser Zeit nicht. Er wird automatisch neu gestartet, sobald die Installation abgeschlossen ist.

HoloLens wendet ein Update nach dem anderen an.  Wenn Ihre HoloLens mehr als eine Version hinter der neuesten version liegt, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um ihn vollständig auf dem neuesten Stand zu halten.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Zurück zu einer früheren Version – HoloLens 2

In einigen Fällen sollten Sie zu einer früheren Version der HoloLens-Software zurückkommen. Hierzu können Sie den Advanced Recovery Companion verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkommen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer HoloLens 2 version of HoloLens 2 zu wechseln:

1. Stellen Sie sicher, dass keine Smartphones oder Windows-Geräte an Ihren PC angeschlossen sind.
1. Laden Sie auf Ihrem PC den [Advanced Recovery Companion aus](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dem Microsoft Store.
1. Laden Sie [die neueste version HoloLens 2 herunter.](https://aka.ms/hololens2download)
1. Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer**  >  **Downloads**. Klicken Sie mit der rechten Maustaste auf den zip-Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **Alle** extrahieren  >  **aus,** um ihn zu entzippen.
1. Verbinden Sie Ihre HoloLens mit ihrem PC, indem Sie ein USB-A-zu-USB-C-Kabel verwenden. (Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dies am besten.)
1. Advanced Recovery Companion erkennt Ihre HoloLens automatisch. Wählen Sie **die Microsoft HoloLens** aus.
1. Wählen Sie auf dem nächsten Bildschirm **Manuelle** Paketauswahl und dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der FFU-Erweiterung.)
1. Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Zurück zu einer früheren Version– HoloLens (1. Generation)

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren. Hierzu können Sie das Windows Device Recovery Tool verwenden, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 1 zurückzukehren:

1. Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.
1. Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)herunter.
1. Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery)herunter.
1. Wenn die Downloads abgeschlossen sind, öffnen **Sie Den Datei-Explorer**  >  **lädt herunter.** Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie gerade heruntergeladen haben, und wählen **Sie Alle**  >  **extrahieren** aus, um ihn zu entzippen.
1. Verbinden Sie Ihre HoloLens mit ihrem PC, indem Sie das micro-USB-Kabel verwenden, in dem sie installiert ist. (Auch wenn Sie andere Kabel verwendet haben, um Ihre HoloLens zu verbinden, funktioniert dieses am besten.)
1. Das WDRT erkennt Ihre HoloLens automatisch. Wählen Sie die **Kachel Microsoft HoloLens** aus.
1. Klicken Sie auf dem nächsten Bildschirm auf **Manuelle Paketauswahl,** und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der FFU-Erweiterung.)
1. Wählen Sie **Software installieren** aus, und befolgen Sie die Anweisungen.

> [!NOTE]
> Wenn das WDRT Ihre HoloLens nicht erkennt, starten Sie Ihren PC neu. Wenn dies nicht funktioniert, wählen Sie **Mein** Gerät wurde nicht erkannt aus, wählen Sie Microsoft HoloLens **aus,** und befolgen Sie dann die Anweisungen.

## <a name="windows-insider-program-on-hololens"></a>Windows-Insider-Programm auf HoloLens

Möchten Sie die neuesten Features in HoloLens sehen?  Wenn ja, treten Sie dem Windows-Insider-Programm bei. Sie erhalten Zugriff auf Vorschauversionen von HoloLens-Softwareupdates, bevor sie für die allgemeine Öffentlichkeit verfügbar sind.

[Hier Windows-Insider Vorschauversion für Microsoft HoloLens.](hololens-insider.md)
