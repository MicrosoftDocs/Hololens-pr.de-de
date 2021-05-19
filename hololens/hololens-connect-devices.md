---
title: Verbinden mit Bluetooth- und USB C-Geräten
description: Erste Schritte beim Verbinden Ihrer Mixed Reality HoloLens-Geräte mit Bluetooth- und USB-C-Geräten und -Zubehör.
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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385483"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Verbinden mit Bluetooth- und USB C-Geräten

> [!NOTE]
> Externe Mikrofone können nicht verwendet werden. HoloLens 2 verwendet sein integriertes [Mikrofon-Array](hololens2-hardware.md#audio-and-speech).

## <a name="pair-bluetooth-devices"></a>Bluetooth-Geräte koppeln

HoloLens 2 unterstützt die folgenden Bluetooth-Geräteklassen:

- Maus
- Tastatur
- Bluetooth Audio Output (A2DP)-Geräte

HoloLens (1. Generation) unterstützt die folgenden Bluetooth-Geräteklassen:

- Maus
- Tastatur
- [Clicker für HoloLens (1. Generation)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Andere Arten von Bluetooth-Geräten wie Lautsprecher, Headsets, Smartphones und Gamepads sind möglicherweise in den HoloLens-Einstellungen aufgelistet. Allerdings werden diese Geräte auf HoloLens (1. Generation) nicht unterstützt. Erfahren Sie mehr unter [In den HoloLens-Einstellungen sind Geräte als verfügbar aufgeführt, sie funktionieren aber nicht](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Koppeln einer Bluetooth-Tastatur oder-Maus

1. Schalten Sie die Tastatur oder Maus ein, damit sie auffindbar sind.  Wenn Sie wissen möchten, wie das Gerät auffindbar ist, suchen Sie nach Informationen auf dem Gerät (oder dessen Dokumentation), oder besuchen Sie die Website des Herstellers.

1. Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen**aus.

1. Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.  

1. Wenn der Gerätename angezeigt wird, wählen Sie **Koppeln** aus, und folgen Sie den Anweisungen.

## <a name="disable-bluetooth"></a>Bluetooth deaktivieren

Mit diesem Verfahren werden die RF-Komponenten des Bluetooth-Funks deaktiviert, und alle Bluetooth-Funktionen werden auf Microsoft-HoloLens deaktiviert.

1. Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen** > **Geräte**aus.

1. Verschieben Sie den Schieberegler für **Bluetooth-** zur **Aus** Position.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Anschließen von USB-C-Geräten

HoloLens 2 unterstützt die folgenden USB-C-Geräteklassen:

- Massenspeicher Geräte (wie z. b. USB-Sticks)
- Ethernet-Adapter (einschließlich Ethernet Plus-Ladevorgang)
- USB-C-zu-3,5-mm-Audio-Adapter
- USB-C Digital Audio Headsets (einschließlich Headset-Adaptern Plus Ladevorgang)
- Kabelgebundene Maus
- Kabelgebundene Tastatur
- Kombinations-PD-Hubs (USB A Plus PD-Ladevorgang)

> [!NOTE]
> Als Antwort auf das Kundenfeedback haben wir die eingeschränkte Unterstützung für die Mobilfunkverbindung aktiviert, die über USB-C direkt an das HoloLens angebunden ist. Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Mobilfunk und 5G](hololens-cellular.md).

### <a name="usb-c-hubs"></a>USB-C-Hubs

Einige Benutzer müssen möglicherweise mehrere Geräte gleichzeitig verbinden. Wenn Benutzer eine Vorschau auf ein Insider-Feature wünschen und ein [USB-C-Mikrofon](hololens-insider.md#usb-c-external-microphone-support) zusammen mit einem anderen angeschlossenen Gerät verwenden möchten, sind USB-C-Hubs möglicherweise die Lösung. Diese Geräte wurden nicht von Microsoft getestet. Microsoft kann dazu keine bestimmten Marken empfehlen.

**Anforderungen für USB-C-Hub und angeschlossene Geräte:**

- Angeschlossene Geräte dürfen keinen Treiber benötigen, der installiert werden muss.
- Die Gesamtleistung aller angeschlossenen Geräte muss unter 4,5 Watt liegen.

## <a name="connect-to-miracast"></a>Herstellen einer Verbindung mit Miracast

Wenn Sie Miracast verwenden möchten, führen Sie die folgenden Schritte aus:

1. Führen Sie eine der folgenden Aktionen aus:  

   - Öffnen Sie das **Startmenü** und wählen Sie das Symbol "Anzeigen" aus.
   - Sagen Sie "verbinden", während Sie auf das **Startmenü**schauen.  

1. Wählen Sie in der Liste der angezeigten Geräte ein verfügbares Gerät aus.

1. Führen Sie die Kopplung aus, um mit dem projizieren zu beginnen.
