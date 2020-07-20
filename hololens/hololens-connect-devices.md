---
title: Verbinden mit Bluetooth- und USB C-Geräten
description: Diese Anleitung führt durch die Verbindung mit Bluetooth-und USB-C-Geräten und-Zubehör.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fef69ee4cd148b82721472436da8dfd627f86ff1
ms.sourcegitcommit: 708da7b390fed1fd3aea1a2b2e50461851052683
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881338"
---
# Verbinden mit Bluetooth- und USB C-Geräten

## Bluetooth-Geräte koppeln

HoloLens 2 unterstützt die folgenden Bluetooth-Geräteklassen:

- Maus
- Tastatur
- Bluetooth Audio Output (A2DP)-Geräte

> [!NOTE]
> Externe Mikrofone können nicht verwendet werden. HoloLens 2 verwendet sein integriertes [Mikrofon-Array](hololens2-hardware.md#audio-and-speech).

HoloLens (1. Generation) unterstützt die folgenden Bluetooth-Geräteklassen:

- Maus
- Tastatur
- Clicker für HoloLens (1. Generation)

> [!NOTE]
> Andere Arten von Bluetooth-Geräten wie Lautsprecher, Headsets, Smartphones und Gamepads sind möglicherweise in den HoloLens-Einstellungen aufgelistet. Allerdings werden diese Geräte auf HoloLens (1. Generation) nicht unterstützt. Erfahren Sie mehr unter [In den HoloLens-Einstellungen sind Geräte als verfügbar aufgeführt, sie funktionieren aber nicht](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### Koppeln einer Bluetooth-Tastatur oder-Maus

1. Schalten Sie die Tastatur oder Maus ein, damit sie auffindbar sind.  Wenn Sie wissen möchten, wie das Gerät auffindbar ist, suchen Sie nach Informationen auf dem Gerät (oder dessen Dokumentation), oder besuchen Sie die Website des Herstellers.

1. Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen**aus.

1. Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.  

1. Wenn der Gerätename angezeigt wird, wählen Sie **Koppeln** aus, und folgen Sie den Anweisungen.

### HoloLens (1. Generation): Clicker koppeln

1. Verwenden Sie die Bloom-Geste um zum **Start** zu wechseln, und wählen Sie dann **Einstellungen** aus.

1. Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.

1. Verwenden Sie die Spitze eines Stifts, um die Schaltfläche "Clicker koppeln" zu drücken, bis die Statusanzeige des Clickers weiß blinkt.  Achten Sie darauf, dass Sie die Schaltfläche gedrückt halten, bis die Anzeige blinkt.  

   Die Schaltfläche "Koppeln" befindet sich auf der Unterseite des Clickers neben der Fingerschlaufe.
   
   ![Die Schaltfläche "Koppeln" befindet sich neben der Fingerschlaufe.](images/use-hololens-clicker-1.png)
   
1. Wählen Sie auf dem Kopplungsbildschirm **Clicker-** > **paar**aus.

## HoloLens 2: Anschließen von USB-C-Geräten

HoloLens 2 unterstützt die folgenden USB-C-Geräteklassen:

- Massenspeicher Geräte (wie z. b. USB-Sticks)
- Ethernet-Adapter (einschließlich Ethernet Plus-Ladevorgang)
- USB-C-zu-3,5-mm-Audio-Adapter
- USB-C Digital Audio Headsets (einschließlich Headset-Adaptern Plus Ladevorgang)
- Kabelgebundene Maus
- Kabelgebundene Tastatur
- Kombinations-PD-Hubs (USB A Plus PD-Ladevorgang)

> [!NOTE]
> Einige mobile Geräte mit USB-C-Verbindungen stellen sich der HoloLens als Ethernet-Adapter dar und können daher in einer Anbindehaltung-Konfiguration verwendet werden, beginnend mit der holographischen Windows-Version 2004. USB LTE-Modems, die einen separaten Treiber und/oder eine für die Konfiguration installierte Anwendung erfordern, werden nicht unterstützt.

Als Antwort auf das Kundenfeedback haben wir die eingeschränkte Unterstützung für die Mobilfunkverbindung aktiviert, die über USB-C direkt an das HoloLens angebunden ist.  Tethering funktioniert nur bei Geräten, die die generische Microsoft [RNDIS-](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Treiber-Implementierung unterstützen und keine weiteren Treiber oder Anwendungen installieren müssen.  Ein solches Gerät wird, wenn es verbunden ist, automatisch als neue Ethernet-Verbindung in der Benutzeroberfläche der HoloLens 2-Netzwerkeinstellungen angezeigt. Bitte wenden Sie sich an den Hersteller Ihres Geräts, um weitere Informationen zu erhalten, ob es den generischen Microsoft RNDIS-Treiber unterstützt.

## Herstellen einer Verbindung mit Miracast

Wenn Sie Miracast verwenden möchten, führen Sie die folgenden Schritte aus:

1. Führen Sie eine der folgenden Aktionen aus:  

   - Öffnen Sie das **Startmenü** und wählen Sie das Symbol "Anzeigen" aus.
   - Sagen Sie "verbinden", während Sie auf das **Startmenü**schauen.  

1. Wählen Sie in der Liste der angezeigten Geräte ein verfügbares Gerät aus.

1. Führen Sie die Kopplung aus, um mit dem projizieren zu beginnen.

## Bluetooth deaktivieren

Mit diesem Verfahren werden die RF-Komponenten des Bluetooth-Funks deaktiviert, und alle Bluetooth-Funktionen werden auf Microsoft-HoloLens deaktiviert.

1. Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen** > **Geräte**aus.

1. Verschieben Sie den Schieberegler für **Bluetooth-** zur **Aus** Position.
