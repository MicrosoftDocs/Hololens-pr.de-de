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
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881245"
---
# <span data-ttu-id="a529d-103">Verbinden mit Bluetooth- und USB C-Geräten</span><span class="sxs-lookup"><span data-stu-id="a529d-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="a529d-104">Bluetooth-Geräte koppeln</span><span class="sxs-lookup"><span data-stu-id="a529d-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="a529d-105">HoloLens 2 unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="a529d-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="a529d-106">Maus</span><span class="sxs-lookup"><span data-stu-id="a529d-106">Mouse</span></span>
- <span data-ttu-id="a529d-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a529d-107">Keyboard</span></span>
- <span data-ttu-id="a529d-108">Bluetooth Audio Output (A2DP)-Geräte</span><span class="sxs-lookup"><span data-stu-id="a529d-108">Bluetooth audio output (A2DP) devices</span></span>

> [!NOTE]
> <span data-ttu-id="a529d-109">Externe Mikrofone können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a529d-109">External microphones cannot be used.</span></span> <span data-ttu-id="a529d-110">HoloLens 2 verwendet sein integriertes [Mikrofon-Array](hololens2-hardware.md#audio-and-speech).</span><span class="sxs-lookup"><span data-stu-id="a529d-110">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

<span data-ttu-id="a529d-111">HoloLens (1. Generation) unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="a529d-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="a529d-112">Maus</span><span class="sxs-lookup"><span data-stu-id="a529d-112">Mouse</span></span>
- <span data-ttu-id="a529d-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a529d-113">Keyboard</span></span>
- <span data-ttu-id="a529d-114">Clicker für HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="a529d-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="a529d-115">Andere Arten von Bluetooth-Geräten wie Lautsprecher, Headsets, Smartphones und Gamepads sind möglicherweise in den HoloLens-Einstellungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a529d-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="a529d-116">Allerdings werden diese Geräte auf HoloLens (1. Generation) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a529d-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="a529d-117">Erfahren Sie mehr unter [In den HoloLens-Einstellungen sind Geräte als verfügbar aufgeführt, sie funktionieren aber nicht](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="a529d-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="a529d-118">Koppeln einer Bluetooth-Tastatur oder-Maus</span><span class="sxs-lookup"><span data-stu-id="a529d-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="a529d-119">Schalten Sie die Tastatur oder Maus ein, damit sie auffindbar sind. </span><span class="sxs-lookup"><span data-stu-id="a529d-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="a529d-120">Wenn Sie wissen möchten, wie das Gerät auffindbar ist, suchen Sie nach Informationen auf dem Gerät (oder dessen Dokumentation), oder besuchen Sie die Website des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="a529d-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="a529d-121">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="a529d-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="a529d-122">Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a529d-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="a529d-123">Wenn der Gerätename angezeigt wird, wählen Sie **Koppeln** aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a529d-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="a529d-124">HoloLens (1. Generation): Clicker koppeln</span><span class="sxs-lookup"><span data-stu-id="a529d-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="a529d-125">Verwenden Sie die Bloom-Geste um zum **Start** zu wechseln, und wählen Sie dann **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="a529d-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="a529d-126">Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="a529d-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="a529d-127">Verwenden Sie die Spitze eines Stifts, um die Schaltfläche "Clicker koppeln" zu drücken, bis die Statusanzeige des Clickers weiß blinkt. </span><span class="sxs-lookup"><span data-stu-id="a529d-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="a529d-128">Achten Sie darauf, dass Sie die Schaltfläche gedrückt halten, bis die Anzeige blinkt.</span><span class="sxs-lookup"><span data-stu-id="a529d-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="a529d-129">Die Schaltfläche "Koppeln" befindet sich auf der Unterseite des Clickers neben der Fingerschlaufe.</span><span class="sxs-lookup"><span data-stu-id="a529d-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![Die Schaltfläche "Koppeln" befindet sich neben der Fingerschlaufe.](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="a529d-131">Wählen Sie auf dem Kopplungsbildschirm **Clicker-** > **paar**aus.</span><span class="sxs-lookup"><span data-stu-id="a529d-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="a529d-132">HoloLens 2: Anschließen von USB-C-Geräten</span><span class="sxs-lookup"><span data-stu-id="a529d-132">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="a529d-133">HoloLens 2 unterstützt die folgenden USB-C-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="a529d-133">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="a529d-134">Massenspeicher Geräte (wie z. b. USB-Sticks)</span><span class="sxs-lookup"><span data-stu-id="a529d-134">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="a529d-135">Ethernet-Adapter (einschließlich Ethernet Plus-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="a529d-135">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="a529d-136">USB-C-zu-3,5-mm-Audio-Adapter</span><span class="sxs-lookup"><span data-stu-id="a529d-136">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="a529d-137">USB-C Digital Audio Headsets (einschließlich Headset-Adaptern Plus Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="a529d-137">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="a529d-138">Kabelgebundene Maus</span><span class="sxs-lookup"><span data-stu-id="a529d-138">Wired mouse</span></span>
- <span data-ttu-id="a529d-139">Kabelgebundene Tastatur</span><span class="sxs-lookup"><span data-stu-id="a529d-139">Wired keyboard</span></span>
- <span data-ttu-id="a529d-140">Kombinations-PD-Hubs (USB A Plus PD-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="a529d-140">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="a529d-141">Einige mobile Geräte mit USB-C-Verbindungen stellen sich der HoloLens als Ethernet-Adapter dar und können daher in einer Anbindehaltung-Konfiguration verwendet werden, beginnend mit der holographischen Windows-Version 2004.</span><span class="sxs-lookup"><span data-stu-id="a529d-141">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="a529d-142">USB LTE-Modems, die einen separaten Treiber und/oder eine für die Konfiguration installierte Anwendung erfordern, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a529d-142">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

## <span data-ttu-id="a529d-143">Herstellen einer Verbindung mit Miracast</span><span class="sxs-lookup"><span data-stu-id="a529d-143">Connect to Miracast</span></span>

<span data-ttu-id="a529d-144">Wenn Sie Miracast verwenden möchten, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a529d-144">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="a529d-145">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a529d-145">Do one of the following:</span></span>  

   - <span data-ttu-id="a529d-146">Öffnen Sie das **Startmenü** und wählen Sie das Symbol "Anzeigen" aus.</span><span class="sxs-lookup"><span data-stu-id="a529d-146">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="a529d-147">Sagen Sie "verbinden", während Sie auf das **Startmenü**schauen.</span><span class="sxs-lookup"><span data-stu-id="a529d-147">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="a529d-148">Wählen Sie in der Liste der angezeigten Geräte ein verfügbares Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="a529d-148">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="a529d-149">Führen Sie die Kopplung aus, um mit dem projizieren zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="a529d-149">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="a529d-150">Bluetooth deaktivieren</span><span class="sxs-lookup"><span data-stu-id="a529d-150">Disable Bluetooth</span></span>

<span data-ttu-id="a529d-151">Mit diesem Verfahren werden die RF-Komponenten des Bluetooth-Funks deaktiviert, und alle Bluetooth-Funktionen werden auf Microsoft-HoloLens deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a529d-151">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="a529d-152">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen** > **Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="a529d-152">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="a529d-153">Verschieben Sie den Schieberegler für **Bluetooth-** zur **Aus** Position.</span><span class="sxs-lookup"><span data-stu-id="a529d-153">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
