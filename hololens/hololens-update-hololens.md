---
title: Aktualisieren von HoloLens
description: Überprüfen Sie die Buildnummer, das Update und die Rollback-Updates Ihres HoloLens.
keywords: Anleitung, Update, Rollback, HoloLens, Buildnummer überprüfen
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828056"
---
# Aktualisieren von HoloLens

HoloLens verwendet Windows Update, genau wie andere Windows 10-Geräte. Ihr HoloLens wird System Updates automatisch herunterladen und installieren, wenn es am Stromnetz angeschlossen und mit dem Internet verbunden ist, selbst wenn es sich im Standbymodus befindet.

In diesem Artikel werden die HoloLens-Tools für die folgenden Schritte erläutert:

- Anzeigen der aktuellen Version des Betriebssystems (Buildnummer)
- nach Updates suchen
- Manuelles Aktualisieren von HoloLens
- Rollback zu einem älteren Update

## Überprüfen der Betriebssystemversion (Buildnummer)

Sie können die Versionsnummer des Systems (Buildnummer) überprüfen, indem Sie die Einstellungs-APP öffnen und **System**  >  **Info**auswählen.

## Nach Updates suchen und manuell aktualisieren

Sie können jederzeit in den Einstellungen nach Updates suchen.  So zeigen Sie verfügbare Updates an und überprüfen auf neue Updates:

1. Öffnen Sie die APP **Einstellungen** .
1. Navigieren Sie zu **Update & Security**  >  **Windows Update**.
1. Wählen Sie **nach Updates**suchen aus.

Wenn ein Update verfügbar ist, wird das Herunterladen der neuen Version gestartet. Nachdem der Download abgeschlossen ist, wählen Sie die Schaltfläche **jetzt neu starten** aus, um die Installation auszulösen. Wenn Ihr Gerät unter 40% liegt und nicht angeschlossen ist, startet der Neustart nicht mehr mit der Installation des Updates.

Während Ihr HoloLens das Update installiert, werden Spinning Gears und eine Statusanzeige angezeigt. Schalten Sie Ihr HoloLens während dieser Zeit nicht aus. Nachdem die Installation abgeschlossen ist, wird Sie automatisch neu gestartet.

HoloLens wendet jeweils ein Update an.  Wenn Ihr HoloLens mehr als eine Version hinter dem neuesten Stand hat, müssen Sie möglicherweise den Updateprozess mehrmals durchlaufen, um ihn vollständig auf dem neuesten Stand zu halten.

## Zurückkehren zu einer vorherigen Version-HoloLens 2

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren. Verwenden Sie dazu den erweiterten Wiederherstellungs-Assistenten, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Gehen Sie wie folgt vor, um zu einer früheren Version von HoloLens 2 zurückzukehren:

1. Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.
1. Laden Sie auf Ihrem PC den [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) aus dem Microsoft Store herunter.
1. Laden Sie die [neueste Version von HoloLens 2](https://aka.ms/hololens2download)herunter.
1. Wenn Sie diese Downloads beenden, öffnen Sie **Datei-Explorer**-  >  **Downloads**. Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen gezippten Ordner, und wählen Sie **Alle extrahieren** > **Extrahieren** aus, um die Dateien zu entpacken.
1. Schließen Sie Ihr HoloLens mit einem USB-a-Kabel an Ihren PC an. (Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)
1. Der Advanced Recovery Companion erkennt automatisch Ihr HoloLens. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl** aus, und wählen Sie dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung FFU.)
1. Wählen Sie **Software installieren**aus, und folgen Sie den Anweisungen.

## Zurückkehren zu einer vorherigen Version – HoloLens (1st Generation)

In einigen Fällen möchten Sie möglicherweise zu einer früheren Version der HoloLens-Software zurückkehren. Verwenden Sie dazu das Windows Device Recovery Tool, um Ihre HoloLens auf die frühere Version zurückzusetzen.

> [!NOTE]
> Wenn Sie zu einer früheren Version zurückkehren, werden Ihre persönlichen Dateien und Einstellungen gelöscht.

Gehen Sie wie folgt vor, um zu einer früheren Version von HoloLens 1 zurückzukehren:

1. Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.
1. Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)herunter.
1. Laden Sie das [HoloLens Anniversary Update-Wiederherstellungs Paket](https://aka.ms/hololensrecovery)herunter.
1. Wenn der Download abgeschlossen ist, öffnen Sie **Datei-Explorer**-  >  **Downloads**. Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen ZIP-Ordner, und wählen Sie **extrahieren**  >  **aus,** um ihn zu entpacken.
1. Verbinden Sie Ihr HoloLens mit Ihrem PC über das Micro-USB-Kabel, mit dem es geliefert wurde. (Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)
1. Die WDRT erkennt Ihre HoloLens automatisch. Wählen Sie die Kachel **Microsoft HoloLens** aus.
1. Wählen Sie auf dem nächsten Bildschirm **Manuelle Paketauswahl** aus, und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entpackt haben. (Suchen Sie nach einer Datei mit der Erweiterung FFU.)
1. Wählen Sie **Software installieren**aus, und folgen Sie den Anweisungen.

> [!NOTE]
> Wenn die WDRT ihre HoloLens nicht erkennt, versuchen Sie, Ihren PC neu zu starten. Wenn dies nicht funktioniert, wählen Sie **mein Gerät wurde nicht erkannt**aus, wählen Sie **Microsoft HoloLens**aus, und folgen Sie dann den Anweisungen.

## Windows-Insider-Programm auf HoloLens

Möchten Sie die neuesten Funktionen in HoloLens anzeigen?  Wenn ja, nehmen Sie am Windows-Insider-Programm Teil; Sie erhalten Zugriff auf Preview-Builds von HoloLens-Softwareupdates, bevor Sie für die allgemeine Öffentlichkeit verfügbar sind.

[Holen Sie sich Windows Insider Preview für Microsoft HoloLens](hololens-insider.md).
