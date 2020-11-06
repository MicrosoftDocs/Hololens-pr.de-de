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
ms.openlocfilehash: 2f2de4d776a0fdb99555687a96719d111ffb6460
ms.sourcegitcommit: 8bf8e9196c4ea89297f210b5c1d41b31f9edd407
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "11156292"
---
# <span data-ttu-id="afba3-103">Verbinden mit Bluetooth- und USB C-Geräten</span><span class="sxs-lookup"><span data-stu-id="afba3-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="afba3-104">Externe Mikrofone können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afba3-104">External microphones cannot be used.</span></span> <span data-ttu-id="afba3-105">HoloLens 2 verwendet sein integriertes [Mikrofon-Array](hololens2-hardware.md#audio-and-speech).</span><span class="sxs-lookup"><span data-stu-id="afba3-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <span data-ttu-id="afba3-106">Bluetooth-Geräte koppeln</span><span class="sxs-lookup"><span data-stu-id="afba3-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="afba3-107">HoloLens 2 unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="afba3-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="afba3-108">Maus</span><span class="sxs-lookup"><span data-stu-id="afba3-108">Mouse</span></span>
- <span data-ttu-id="afba3-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="afba3-109">Keyboard</span></span>
- <span data-ttu-id="afba3-110">Bluetooth Audio Output (A2DP)-Geräte</span><span class="sxs-lookup"><span data-stu-id="afba3-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="afba3-111">HoloLens (1. Generation) unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="afba3-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="afba3-112">Maus</span><span class="sxs-lookup"><span data-stu-id="afba3-112">Mouse</span></span>
- <span data-ttu-id="afba3-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="afba3-113">Keyboard</span></span>
- <span data-ttu-id="afba3-114">Clicker für HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="afba3-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="afba3-115">Andere Arten von Bluetooth-Geräten wie Lautsprecher, Headsets, Smartphones und Gamepads sind möglicherweise in den HoloLens-Einstellungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="afba3-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="afba3-116">Allerdings werden diese Geräte auf HoloLens (1. Generation) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afba3-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="afba3-117">Erfahren Sie mehr unter [In den HoloLens-Einstellungen sind Geräte als verfügbar aufgeführt, sie funktionieren aber nicht](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="afba3-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="afba3-118">Koppeln einer Bluetooth-Tastatur oder-Maus</span><span class="sxs-lookup"><span data-stu-id="afba3-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="afba3-119">Schalten Sie die Tastatur oder Maus ein, damit sie auffindbar sind. </span><span class="sxs-lookup"><span data-stu-id="afba3-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="afba3-120">Wenn Sie wissen möchten, wie das Gerät auffindbar ist, suchen Sie nach Informationen auf dem Gerät (oder dessen Dokumentation), oder besuchen Sie die Website des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="afba3-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="afba3-121">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="afba3-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="afba3-122">Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="afba3-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="afba3-123">Wenn der Gerätename angezeigt wird, wählen Sie **Koppeln** aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="afba3-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="afba3-124">HoloLens (1. Generation): Clicker koppeln</span><span class="sxs-lookup"><span data-stu-id="afba3-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="afba3-125">Verwenden Sie die Bloom-Geste um zum **Start** zu wechseln, und wählen Sie dann **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="afba3-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="afba3-126">Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="afba3-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="afba3-127">Verwenden Sie die Spitze eines Stifts, um die Schaltfläche "Clicker koppeln" zu drücken, bis die Statusanzeige des Clickers weiß blinkt. </span><span class="sxs-lookup"><span data-stu-id="afba3-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="afba3-128">Achten Sie darauf, dass Sie die Schaltfläche gedrückt halten, bis die Anzeige blinkt.</span><span class="sxs-lookup"><span data-stu-id="afba3-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="afba3-129">Die Schaltfläche "Koppeln" befindet sich auf der Unterseite des Clickers neben der Fingerschlaufe.</span><span class="sxs-lookup"><span data-stu-id="afba3-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![Die Schaltfläche "Koppeln" befindet sich neben der Fingerschlaufe.](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="afba3-131">Wählen Sie auf dem Kopplungsbildschirm **Clicker-** > **paar**aus.</span><span class="sxs-lookup"><span data-stu-id="afba3-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="afba3-132">Bluetooth deaktivieren</span><span class="sxs-lookup"><span data-stu-id="afba3-132">Disable Bluetooth</span></span>

<span data-ttu-id="afba3-133">Mit diesem Verfahren werden die RF-Komponenten des Bluetooth-Funks deaktiviert, und alle Bluetooth-Funktionen werden auf Microsoft-HoloLens deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="afba3-133">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="afba3-134">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen** > **Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="afba3-134">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="afba3-135">Verschieben Sie den Schieberegler für **Bluetooth-** zur **Aus** Position.</span><span class="sxs-lookup"><span data-stu-id="afba3-135">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <span data-ttu-id="afba3-136">HoloLens 2: Anschließen von USB-C-Geräten</span><span class="sxs-lookup"><span data-stu-id="afba3-136">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="afba3-137">HoloLens 2 unterstützt die folgenden USB-C-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="afba3-137">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="afba3-138">Massenspeicher Geräte (wie z. b. USB-Sticks)</span><span class="sxs-lookup"><span data-stu-id="afba3-138">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="afba3-139">Ethernet-Adapter (einschließlich Ethernet Plus-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="afba3-139">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="afba3-140">USB-C-zu-3,5-mm-Audio-Adapter</span><span class="sxs-lookup"><span data-stu-id="afba3-140">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="afba3-141">USB-C Digital Audio Headsets (einschließlich Headset-Adaptern Plus Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="afba3-141">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="afba3-142">Kabelgebundene Maus</span><span class="sxs-lookup"><span data-stu-id="afba3-142">Wired mouse</span></span>
- <span data-ttu-id="afba3-143">Kabelgebundene Tastatur</span><span class="sxs-lookup"><span data-stu-id="afba3-143">Wired keyboard</span></span>
- <span data-ttu-id="afba3-144">Kombinations-PD-Hubs (USB A Plus PD-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="afba3-144">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="afba3-145">Einige mobile Geräte mit USB-C-Verbindungen stellen sich der HoloLens als Ethernet-Adapter dar und können daher in einer Anbindehaltung-Konfiguration verwendet werden, beginnend mit der holographischen Windows-Version 2004.</span><span class="sxs-lookup"><span data-stu-id="afba3-145">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="afba3-146">USB LTE-Modems, die einen separaten Treiber und/oder eine für die Konfiguration installierte Anwendung erfordern, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afba3-146">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

<span data-ttu-id="afba3-147">Als Antwort auf das Kundenfeedback haben wir die eingeschränkte Unterstützung für die Mobilfunkverbindung aktiviert, die über USB-C direkt an das HoloLens angebunden ist.</span><span class="sxs-lookup"><span data-stu-id="afba3-147">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span>  <span data-ttu-id="afba3-148">Tethering funktioniert nur bei Geräten, die die generische Microsoft [RNDIS-](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Treiber-Implementierung unterstützen und keine weiteren Treiber oder Anwendungen installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="afba3-148">Tethered connectivity only works for devices that support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver implementation and that don’t require any additional drivers or application installs.</span></span>  <span data-ttu-id="afba3-149">Ein solches Gerät wird, wenn es verbunden ist, automatisch als neue Ethernet-Verbindung in der Benutzeroberfläche der HoloLens 2-Netzwerkeinstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afba3-149">Such device, when connected, will automatically appear as a new Ethernet connection in the HoloLens 2 Network Settings UI.</span></span> <span data-ttu-id="afba3-150">Bitte wenden Sie sich an den Hersteller Ihres Geräts, um weitere Informationen zu erhalten, ob es den generischen Microsoft RNDIS-Treiber unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afba3-150">Please consult your device’s manufacturer for further details on whether it supports the generic Microsoft RNDIS driver.</span></span>

## <span data-ttu-id="afba3-151">Herstellen einer Verbindung mit Miracast</span><span class="sxs-lookup"><span data-stu-id="afba3-151">Connect to Miracast</span></span>

<span data-ttu-id="afba3-152">Wenn Sie Miracast verwenden möchten, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="afba3-152">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="afba3-153">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="afba3-153">Do one of the following:</span></span>  

   - <span data-ttu-id="afba3-154">Öffnen Sie das **Startmenü** und wählen Sie das Symbol "Anzeigen" aus.</span><span class="sxs-lookup"><span data-stu-id="afba3-154">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="afba3-155">Sagen Sie "verbinden", während Sie auf das **Startmenü**schauen.</span><span class="sxs-lookup"><span data-stu-id="afba3-155">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="afba3-156">Wählen Sie in der Liste der angezeigten Geräte ein verfügbares Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="afba3-156">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="afba3-157">Führen Sie die Kopplung aus, um mit dem projizieren zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="afba3-157">Complete the pairing to begin projecting.</span></span>
