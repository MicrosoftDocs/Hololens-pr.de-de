---
title: Problembehandlung für HoloLens
description: Lösungen für häufige HoloLens-Probleme.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: Probleme, Fehler, Problembehandlung, beheben, Hilfe, Support, HoloLens
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4897d02f4b789c77204d57c0a7750e3c3803d7bb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828241"
---
# Problembehandlung für HoloLens

In diesem Artikel wird beschrieben, wie Sie mehrere häufige HoloLens-Probleme beheben.

## Mein HoloLens reagiert nicht oder wird nicht gestartet

Wenn Ihr HoloLens nicht gestartet wird:

- Wenn die LEDs neben dem Netzschalter nicht leuchten oder nur eine LED blinkt, müssen Sie möglicherweise [Ihr HoloLens aufladen.](hololens-recovery.md#charging-the-device)
- Wenn die LEDs leuchten, wenn Sie die Power-Taste drücken, aber auf den Displays nichts angezeigt wird, stellen Sie [ein Hard-Reset des Geräts](hololens-recovery.md#hard-reset-procedure)vor.

Wenn Ihr HoloLens eingefroren ist oder nicht mehr reagiert:

- Schalten Sie Ihr HoloLens aus, indem Sie die Power-Taste drücken, bis sich alle fünf LEDs selbst ausschalten, oder 15 Sekunden lang, wenn die LEDs nicht reagieren. Um Ihr HoloLens zu starten, drücken Sie die Power-Taste erneut.

Wenn diese Schritte nicht funktionieren, können Sie versuchen, [das HoloLens 2-Gerät](hololens-recovery.md) oder das [HoloLens (1st-Gen)-Gerät](hololens1-recovery.md) wieder zu verwenden.

## Hologramme sehen nicht gut aus

Wenn Ihre Hologramme instabil, nervös oder nicht richtig aussehen, probieren Sie Folgendes aus:

- Reinigen Sie Ihr Geräte Visier und die Sensorleiste auf der Vorderseite Ihres HoloLens.
- Erhöhen des Lichts in Ihrem Raum.
- Sie können Ihre Umgebung erkunden, damit HoloLens Sie vollständiger Scannen kann.
- Kalibrieren Ihres HoloLens für Ihre Augen. Wechseln Sie zu **Einstellungen**  >  **System**  >  **Dienstprogramme**. Wählen Sie unter **Kalibrierung** die Option **Kalibrierung öffnen** aus.

## HoloLens reagiert nicht auf Gesten

Um sicherzustellen, dass HoloLens ihre Gesten sehen kann.  Halten Sie Ihre Hand im Gesten Rahmen, wenn HoloLens Ihre Hand sehen kann, ändert sich der Cursor von einem Punkt in einen Ring.

Weitere Informationen finden Sie unter Verwenden von Gesten in [HoloLens (1st Gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) oder [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Wenn Ihre Umgebung zu dunkel ist, kann HoloLens möglicherweise nicht Ihre Hand sehen, stellen Sie also sicher, dass genügend Licht vorhanden ist.

Wenn ihr Visier Fingerabdrücke oder Flecken hat, verwenden Sie das mit dem HoloLens gelieferte Microfaser-Reinigungstuch, um ihr Visier schonend zu reinigen.

## HoloLens reagiert nicht auf meine Sprachbefehle

Wenn Cortana nicht auf Ihre Sprachbefehle reagiert, stellen Sie sicher, dass Cortana aktiviert ist. Wählen Sie in der Liste alle apps die Option **Cortana**-  >  **Menü**  >  **Notizbuch**-  >  **Einstellungen** aus, um Änderungen vorzunehmen. Weiter Informationen dazu, was Sie sagen können, finden Sie unter [Verwenden Sie Ihre Stimme mit HoloLens](hololens-cortana.md).

## Ich kann keine Hologramme platzieren oder Hologramme sehen, die ich zuvor platziert habe

Wenn HoloLens Ihren Space nicht zuordnen oder laden kann, wird er in den Modus "limitiert" gesetzt, und Sie können keine Hologramme platzieren oder Hologramme sehen, die Sie platziert haben. Probieren Sie Folgendes aus:

- Stellen Sie sicher, dass in Ihrer Umgebung genügend Licht vorhanden ist, damit HoloLens den Platz sehen und zuordnen kann.
- Stellen Sie sicher, dass Sie mit einem WLAN-Netzwerk verbunden sind. Wenn Sie nicht mit WLAN verbunden sind, kann HoloLens einen bekannten Speicherplatz nicht identifizieren und laden.
- Wenn Sie einen neuen Speicherplatz erstellen müssen, stellen Sie eine Verbindung zu WLAN her, und starten Sie dann Ihr HoloLens neu.
- Wenn Sie feststellen möchten, ob der richtige Platz aktiv ist, oder wenn Sie ein Leerzeichen manuell laden möchten, wechseln Sie zu **Einstellungen**  >  **System**  >  **Leerzeichen**.
- Wenn der richtige Speicherplatz geladen wird und Sie weiterhin Probleme haben, ist der Speicherplatz möglicherweise beschädigt. Um dieses Problem zu beheben, wählen Sie den Bereich aus, und wählen Sie dann **Entfernen**aus. Nachdem Sie das Leerzeichen entfernt haben, beginnt HoloLens, Ihre Umgebung zuzuordnen und einen neuen Bereich zu erstellen.

## Mein HoloLens kann nicht erkennen, in welchem Bereich ich bin

Wenn Ihr HoloLens den Speicherplatz, in dem Sie sich befinden, nicht automatisch identifizieren und laden kann, überprüfen Sie die folgenden Faktoren:

- Stellen Sie sicher, dass Sie mit WLAN verbunden sind.
- Sorgen Sie dafür, dass der Raum viel Licht hat
- Stellen Sie sicher, dass sich die Umgebung nicht wesentlich geändert hat.

Sie können ein Leerzeichen auch manuell laden oder Ihre Räume verwalten, indem Sie zu **Einstellungen**  >  **System**  >  **Räume**wechseln.

## Ich erhalte einen Fehler "geringer Speicherplatz"

Sie müssen etwas Speicherplatz freigeben, indem Sie eine oder mehrere der folgenden Aktionen ausführen:

- Löschen Sie einige nicht verwendete Leerzeichen. Wechseln Sie zu **Einstellungen**  >  **System**  >  **Spaces**, wählen Sie ein Leerzeichen aus, das Sie nicht mehr benötigen, und wählen Sie dann **Entfernen**aus.
- Entfernen Sie einige der Hologramme, die Sie hinzugefügt haben.
- Löschen Sie einige Bilder und Videos aus der Foto-APP.
- Deinstallieren Sie einige Apps von Ihrer HoloLens. Tippen Sie in der Liste **alle apps** auf die APP, die Sie deinstallieren möchten, und halten Sie sie gedrückt, und wählen Sie dann **deinstallieren**aus.

## Mein HoloLens kann keinen neuen Bereich erstellen.

Das wahrscheinlichste Problem besteht darin, dass Sie auf dem Speicherplatz knapp sind. Probieren Sie einen der [vorherigen Tipps](#im-getting-a-low-disk-space-error) aus, um etwas Speicherplatz freizugeben.

## Der HoloLens-Emulator funktioniert nicht

Informationen zum HoloLens-Emulator finden Sie in unserer Entwicklerdokumentation.  Weitere Informationen finden Sie [unter Problembehandlung beim HoloLens-Emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
