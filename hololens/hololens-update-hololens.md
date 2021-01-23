---
title: Aktualisieren von HoloLens
description: Erfahren Sie, wie Sie Ihre HoloLens-Buildnummer überprüfen, mit Geräteupdates auf dem laufenden bleiben, am Insider-Programm teilnehmen und Updates zurückrollt.
keywords: How-to, update, roll back, HoloLens, check build, build number
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283936"
---
# Aktualisieren von HoloLens

HoloLens verwendet Windows Update, genau wie andere Windows 10-Geräte. Ihre HoloLens wird Systemupdates automatisch herunterladen und installieren, sobald es an die Stromversorgung angeschlossen und mit dem Internet verbunden ist, auch wenn es sich im Standbymodus befindet.

In diesem Artikel werden die Tools von HoloLens für:

- Anzeigen der aktuellen Betriebssystemversion (Buildnummer)
- Suchen nach Updates
- Manuelles Aktualisieren von HoloLens
- Rollback auf ein älteres Update

## Überprüfen der Betriebssystemversion (Buildnummer)

Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie die Einstellungs-App öffnen und **System**  >  **About auswählen.**

## Suchen nach Updates und manuelles Update

Sie können jederzeit in den Einstellungen nach Updates suchen.  So sehen Sie verfügbare Updates und suchen nach neuen Updates:

1. Öffnen Sie die **Einstellungs-App.**
1. Navigieren Sie zu **Update & Security**Windows  >  **Update**.
1. Wählen **Sie "Nach Updates suchen" aus.**

Wenn ein Update verfügbar ist, wird mit dem Herunterladen der neuen Version gestartet. Klicken Sie nach Abschluss des Downloads auf die Schaltfläche **"Jetzt** neu starten", um die Installation auszulösen. Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, wird beim Neustart nicht mit der Installation des Updates gestartet.

Während HoloLens das Update installiert, werden Drehräder und eine Statusanzeige angezeigt. Deaktivieren Sie Ihre HoloLens während dieser Zeit nicht. Sie wird automatisch neu gestartet, sobald die Installation abgeschlossen ist.

HoloLens wendet ein Update nach dem anderen an.  Wenn Ihre HoloLens mehr als eine Version hinter der neuesten version ist, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um es vollständig auf dem neuesten Stand zu halten.

## Zurück zu einer früheren Version – HoloLens 2

Es kann vorkommen, dass eine Rückkehr zu einer früheren Version der HoloLens-Software erforderlich ist. Verwenden Sie dazu advanced Recovery Companion, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurück gehen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 2 zurückzukehren:

1. Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.
1. Laden Sie auf Ihrem PC [den Advanced Recovery Companion aus](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dem Microsoft Store herunter.
1. Laden Sie die [neueste HoloLens 2-Version](https://aka.ms/hololens2download) herunter.
1. Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer-Downloads.**  >  **** Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen gezippten Ordner, und wählen Sie **Alle extrahieren** > **Extrahieren** aus, um die Dateien zu entpacken.
1. Schließen Sie Ihre HoloLens über ein USB-A-zu-USB-C-Kabel an Ihren PC an. (Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)
1. Der Advanced Recovery Companion erkennt Ihre HoloLens automatisch. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie auf dem nächsten Bildschirm **die** Option "Manuelle Paketauswahl" aus, und wählen Sie dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entzippt haben. (Suchen Sie nach einer Datei mit der Erweiterung FFU.)
1. Wählen **Sie "Software installieren"** aus, und folgen Sie den Anweisungen.

## Zurück zu einer früheren Version – HoloLens (1. Generation)

Es kann vorkommen, dass eine Rückkehr zu einer früheren Version der HoloLens-Software erforderlich ist. Verwenden Sie dazu das Windows Device Recovery Tool, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurück gehen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Gehen Sie wie folgt vor, um zu einer früheren Version von HoloLens 1 zurück zu wechseln:

1. Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.
1. Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT) herunter.](https://support.microsoft.com/help/12379)
1. Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery) herunter.
1. Wenn die Downloads abgeschlossen sind, öffnen Sie **Datei-Explorer-Downloads.**  >  **** Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **"Alle**Extrahieren" aus, um ihn zu  >  **** entpacken.
1. Schließen Sie Ihre HoloLens mit dem micro-USB-Kabel, das sie dabei hatte, an Ihren PC an. (Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)
1. Das WDRT erkennt Ihre HoloLens automatisch. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie auf dem nächsten Bildschirm die Option "Manuelle **Paketauswahl"** aus, und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entzippt haben. (Suchen Sie nach einer Datei mit der Erweiterung FFU.)
1. Wählen **Sie "Software installieren"** aus, und folgen Sie den Anweisungen.

> [!NOTE]
> Wenn das WDRT Ihre HoloLens nicht erkennt, starten Sie Ihren PC neu. Wenn das nicht funktioniert, wählen Sie **Mein Gerät wurde nicht erkannt** und anschließend **Microsoft HoloLens** aus, und folgen Sie dann den Anweisungen.

## Windows-Insider-Programm auf HoloLens

Möchten Sie die neuesten Features in HoloLens sehen?  Wenn ja, nehmen Sie am Windows-Insider-Programm teil; Sie erhalten Zugriff auf Vorschaubuilds von HoloLens-Softwareupdates, bevor sie für die allgemein zugänglich sind.

[Erhalten Sie eine Windows-Insider-Vorschau für Microsoft HoloLens.](hololens-insider.md)
