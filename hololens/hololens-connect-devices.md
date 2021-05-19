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
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="6c803-103">Verbinden mit Bluetooth- und USB C-Geräten</span><span class="sxs-lookup"><span data-stu-id="6c803-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="6c803-104">Externe Mikrofone können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c803-104">External microphones cannot be used.</span></span> <span data-ttu-id="6c803-105">HoloLens 2 verwendet sein integriertes [Mikrofon-Array](hololens2-hardware.md#audio-and-speech).</span><span class="sxs-lookup"><span data-stu-id="6c803-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="6c803-106">Bluetooth-Geräte koppeln</span><span class="sxs-lookup"><span data-stu-id="6c803-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="6c803-107">HoloLens 2 unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="6c803-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="6c803-108">Maus</span><span class="sxs-lookup"><span data-stu-id="6c803-108">Mouse</span></span>
- <span data-ttu-id="6c803-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6c803-109">Keyboard</span></span>
- <span data-ttu-id="6c803-110">Bluetooth Audio Output (A2DP)-Geräte</span><span class="sxs-lookup"><span data-stu-id="6c803-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="6c803-111">HoloLens (1. Generation) unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="6c803-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="6c803-112">Maus</span><span class="sxs-lookup"><span data-stu-id="6c803-112">Mouse</span></span>
- <span data-ttu-id="6c803-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6c803-113">Keyboard</span></span>
- [<span data-ttu-id="6c803-114">Clicker für HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="6c803-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="6c803-115">Andere Arten von Bluetooth-Geräten wie Lautsprecher, Headsets, Smartphones und Gamepads sind möglicherweise in den HoloLens-Einstellungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6c803-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="6c803-116">Allerdings werden diese Geräte auf HoloLens (1. Generation) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6c803-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="6c803-117">Erfahren Sie mehr unter [In den HoloLens-Einstellungen sind Geräte als verfügbar aufgeführt, sie funktionieren aber nicht](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="6c803-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="6c803-118">Koppeln einer Bluetooth-Tastatur oder-Maus</span><span class="sxs-lookup"><span data-stu-id="6c803-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="6c803-119">Schalten Sie die Tastatur oder Maus ein, damit sie auffindbar sind. </span><span class="sxs-lookup"><span data-stu-id="6c803-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="6c803-120">Wenn Sie wissen möchten, wie das Gerät auffindbar ist, suchen Sie nach Informationen auf dem Gerät (oder dessen Dokumentation), oder besuchen Sie die Website des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="6c803-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="6c803-121">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="6c803-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="6c803-122">Wählen Sie **Geräte**aus, und vergewissern Sie sich, dass Bluetooth aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6c803-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="6c803-123">Wenn der Gerätename angezeigt wird, wählen Sie **Koppeln** aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6c803-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="6c803-124">Bluetooth deaktivieren</span><span class="sxs-lookup"><span data-stu-id="6c803-124">Disable Bluetooth</span></span>

<span data-ttu-id="6c803-125">Mit diesem Verfahren werden die RF-Komponenten des Bluetooth-Funks deaktiviert, und alle Bluetooth-Funktionen werden auf Microsoft-HoloLens deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6c803-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="6c803-126">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zu **Start**zu wechseln, und wählen Sie dann **Einstellungen** > **Geräte**aus.</span><span class="sxs-lookup"><span data-stu-id="6c803-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="6c803-127">Verschieben Sie den Schieberegler für **Bluetooth-** zur **Aus** Position.</span><span class="sxs-lookup"><span data-stu-id="6c803-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="6c803-128">HoloLens 2: Anschließen von USB-C-Geräten</span><span class="sxs-lookup"><span data-stu-id="6c803-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="6c803-129">HoloLens 2 unterstützt die folgenden USB-C-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="6c803-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="6c803-130">Massenspeicher Geräte (wie z. b. USB-Sticks)</span><span class="sxs-lookup"><span data-stu-id="6c803-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="6c803-131">Ethernet-Adapter (einschließlich Ethernet Plus-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="6c803-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="6c803-132">USB-C-zu-3,5-mm-Audio-Adapter</span><span class="sxs-lookup"><span data-stu-id="6c803-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="6c803-133">USB-C Digital Audio Headsets (einschließlich Headset-Adaptern Plus Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="6c803-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="6c803-134">Kabelgebundene Maus</span><span class="sxs-lookup"><span data-stu-id="6c803-134">Wired mouse</span></span>
- <span data-ttu-id="6c803-135">Kabelgebundene Tastatur</span><span class="sxs-lookup"><span data-stu-id="6c803-135">Wired keyboard</span></span>
- <span data-ttu-id="6c803-136">Kombinations-PD-Hubs (USB A Plus PD-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="6c803-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="6c803-137">Als Antwort auf das Kundenfeedback haben wir die eingeschränkte Unterstützung für die Mobilfunkverbindung aktiviert, die über USB-C direkt an das HoloLens angebunden ist.</span><span class="sxs-lookup"><span data-stu-id="6c803-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="6c803-138">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Mobilfunk und 5G](hololens-cellular.md).</span><span class="sxs-lookup"><span data-stu-id="6c803-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="6c803-139">USB-C-Hubs</span><span class="sxs-lookup"><span data-stu-id="6c803-139">USB-C Hubs</span></span>

<span data-ttu-id="6c803-140">Einige Benutzer müssen möglicherweise mehrere Geräte gleichzeitig verbinden.</span><span class="sxs-lookup"><span data-stu-id="6c803-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="6c803-141">Wenn Benutzer eine Vorschau auf ein Insider-Feature wünschen und ein [USB-C-Mikrofon](hololens-insider.md#usb-c-external-microphone-support) zusammen mit einem anderen angeschlossenen Gerät verwenden möchten, sind USB-C-Hubs möglicherweise die Lösung.</span><span class="sxs-lookup"><span data-stu-id="6c803-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="6c803-142">Diese Geräte wurden nicht von Microsoft getestet. Microsoft kann dazu keine bestimmten Marken empfehlen.</span><span class="sxs-lookup"><span data-stu-id="6c803-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="6c803-143">Anforderungen für USB-C-Hub und angeschlossene Geräte:</span><span class="sxs-lookup"><span data-stu-id="6c803-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="6c803-144">Angeschlossene Geräte dürfen keinen Treiber benötigen, der installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="6c803-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="6c803-145">Die Gesamtleistung aller angeschlossenen Geräte muss unter 4,5 Watt liegen.</span><span class="sxs-lookup"><span data-stu-id="6c803-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="6c803-146">Herstellen einer Verbindung mit Miracast</span><span class="sxs-lookup"><span data-stu-id="6c803-146">Connect to Miracast</span></span>

<span data-ttu-id="6c803-147">Wenn Sie Miracast verwenden möchten, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6c803-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="6c803-148">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="6c803-148">Do one of the following:</span></span>  

   - <span data-ttu-id="6c803-149">Öffnen Sie das **Startmenü** und wählen Sie das Symbol "Anzeigen" aus.</span><span class="sxs-lookup"><span data-stu-id="6c803-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="6c803-150">Sagen Sie "verbinden", während Sie auf das **Startmenü**schauen.</span><span class="sxs-lookup"><span data-stu-id="6c803-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="6c803-151">Wählen Sie in der Liste der angezeigten Geräte ein verfügbares Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="6c803-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="6c803-152">Führen Sie die Kopplung aus, um mit dem projizieren zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6c803-152">Complete the pairing to begin projecting.</span></span>
