---
title: Herstellen einer Verbindung mit Bluetooth- und USB-C-Geräten
description: Erste Schritte beim Verbinden Ihrer HoloLens Mixed Reality-Geräte mit Bluetooth- und USB-C-Geräten und Zubehör.
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639096"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Herstellen einer Verbindung mit Bluetooth- und USB-C-Geräten

## <a name="pair-bluetooth-devices"></a>Koppeln von Bluetooth-Geräte

HoloLens 2 unterstützt die folgenden Bluetooth-Geräteklassen:

- [HID](/windows-hardware/drivers/hid/):
    - Maus
    - Tastatur
- Audioausgabegeräte (A2DP)

HoloLens 2 unterstützt die folgenden Bluetooth-APIs:
- GATT-[Server](/windows/uwp/devices-sensors/gatt-server) und -[Client](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Möglicherweise müssen Sie entsprechende Begleit-Apps vom Microsoft Store installieren, um die HID- und GATT-Geräte tatsächlich zu verwenden.

HoloLens (1. Generation) unterstützt die folgenden Bluetooth-Geräteklassen:

- Maus
- Tastatur
- [Clicker für HoloLens (1. Generation)](hololens1-clicker.md)

> [!NOTE]
> Andere Arten von Bluetooth-Geräten wie Lautsprecher, Headsets, Smartphones und Gamepads sind möglicherweise in den HoloLens-Einstellungen aufgelistet. Allerdings werden diese Geräte auf HoloLens (1. Generation) nicht unterstützt. Weitere Informationen finden Sie unter [HoloLens Einstellungen listet die Geräte als verfügbar auf, aber die Geräte funktionieren nicht](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Koppeln einer Bluetooth-Tastatur oder -Maus

1. Schalten Sie die Tastatur oder die Maus ein, damit sie auffindbar ist. Wenn Sie wissen möchten, wie das Gerät auffindbar ist, suchen Sie nach Informationen auf dem Gerät (oder dessen Dokumentation), oder besuchen Sie die Website des Herstellers.

1. Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zum **Start** zu gelangen, und wählen Sie dann **Einstellungen** aus.

1. Wählen Sie **Geräte** aus und vergewissern Sie sich, dass Bluetooth aktiviert ist.  

1. Wenn der Gerätename angezeigt wird, wählen Sie **Koppeln** aus und folgen Sie den Anweisungen.

## <a name="disable-bluetooth"></a>Bluetooth deaktivieren

Mit diesem Verfahren werden die RF-Komponenten des Bluetooth-Funks deaktiviert, und alle Bluetooth-Funktionen auf Microsoft-HoloLens werden deaktiviert.

1. Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zum **Start** zu gelangen, und wählen Sie dann **Einstellungen** > **Geräte** aus.

1. Bewegen Sie den Schieberegler für **Bluetooth** an die Position **Aus**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Anschließen von USB-C-Geräten

HoloLens 2 unterstützt die folgenden USB-C-Geräteklassen:

- Massenspeicher Geräte (wie z. B. USB-Sticks)
- Ethernet-Adapter (einschließlich Ethernet plus-Ladevorgang)
- USB-C-auf-3,5 mm Audio-Adapter
- USB-C Digital Audio Headsets (einschließlich Headset-Adaptern plus Ladevorgang)
- Externe USB-C-Mikrofone ([Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher)
- Kabelgebundene Maus
- Kabelgebundene Tastatur
- Kombinations-PD-Hubs (USB A plus PD-Ladevorgang)


> [!NOTE]
> Als Antwort auf das Kundenfeedback haben wir die eingeschränkte Unterstützung für Mobilfunkverbindungen aktiviert, die über USB-C direkt an die HoloLens angebunden sind. Weitere Informationen finden Sie unter [Verbinden mit Mobilfunk und 5G](hololens-cellular.md).

### <a name="usb-c-external-microphone-support"></a>Unterstützung externer USB-C-Mikrofone

> [!IMPORTANT]
> Wenn Sie ein **USB-Mikrofon anschließen, wird es nicht automatisch als Eingabegerät festgelegt**. Wenn Sie ein USB-C-Kopfhörer anschließen, werden Benutzer feststellen, dass die Audiodaten des Kopfhörers automatisch an den Kopfhörer umgeleitet werden, aber das HoloLens-Betriebssystem priorisiert das interne Mikrofon-Array über jedem anderen Eingabegerät. **Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**

> [!NOTE]
> Externe Mikrofone können nicht in Builds vor [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher, verwendet werden. 

Benutzer können externe Mikrofone mit USB-C-Verbindung über das Einstellungsfeld **Sound** auswählen. USB-C-Mikrofone können zum Aufrufen, Aufzeichnen usw. verwendet werden.

Öffnen Sie die App **Einstellungen**, und wählen Sie **System** > **Sound** aus.

![Sound-Einstellungen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Um externe Mikrofone mit **Remote Assist** verwenden zu können, müssen Benutzer auf den Link „Soundgeräte verwalten“ klicken.
>
> Verwenden Sie dann die Dropdownliste, um das externe Mikrofon entweder auf **Standard** oder **Kommunikationsstandard** zu setzen. Die Auswahl **Standard** bedeutet, dass das externe Mikrofon überall verwendet wird.
>
> Die Auswahl von **Kommunikationsstandard** bedeutet, dass das externe Mikrofon in Remote Assist und anderen Kommunikations-Apps verwendet wird, aber das HoloLens-Mikrofon-Array kann weiterhin für andere Aufgaben verwendet werden.

![Verwalten von Soundgeräten](images/usbc-mic-2.png)

<br>

![Festlegen der Mikrofon-Standardeinstellung](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Wie sieht es mit der Unterstützung von Bluetooth Mikrofonen aus?

Leider werden Bluetooth Mikrofone derzeit nicht von HoloLens 2 unterstützt.

### <a name="usb-c-hubs"></a>USB-C-Hubs

Einige Benutzer müssen möglicherweise mehrere Geräte gleichzeitig verbinden. Für Benutzer, die ein [USB-C-Mikrofon](#usb-c-external-microphone-support) zusammen mit einem anderen verbundenen Gerät verwenden möchten, können USB-C-Hubs den Anforderungen des Kunden entsprechen. Diese Geräte wurden nicht von Microsoft getestet. Microsoft kann keine bestimmten Marken empfehlen.

**Anforderungen an den USB-C-Hub und angeschlossene Geräte:**

- Angeschlossene Geräte dürfen keinen Treiber benötigen, der installiert werden muss.
- Die Gesamtleistung aller angeschlossenen Geräte muss unter 4,5 Watt liegen.

## <a name="connect-to-miracast"></a>Herstellen einer Verbindung mit Miracast

Wenn Sie Miracast verwenden möchten, führen Sie die folgenden Schritte aus:

1. Führen Sie eines der folgenden Verfahren aus:  

   - Öffnen Sie das **Startmenü** und wählen Sie das Symbol **Anzeigen** aus.
   - Sagen Sie „Verbinden“, während Sie auf das **Startmenü** schauen.  

1. Wählen Sie aus der Liste der angezeigten Geräte ein verfügbares Gerät aus.

1. Führen Sie die Kopplung aus, um mit dem projizieren zu beginnen.
