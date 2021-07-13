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
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924178"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="647aa-103">Herstellen einer Verbindung mit Bluetooth- und USB-C-Geräten</span><span class="sxs-lookup"><span data-stu-id="647aa-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="647aa-104">Koppeln von Bluetooth-Geräte</span><span class="sxs-lookup"><span data-stu-id="647aa-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="647aa-105">HoloLens 2 unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="647aa-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="647aa-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="647aa-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="647aa-107">Maus</span><span class="sxs-lookup"><span data-stu-id="647aa-107">Mouse</span></span>
    - <span data-ttu-id="647aa-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="647aa-108">Keyboard</span></span>
- <span data-ttu-id="647aa-109">Audioausgabegeräte (A2DP)</span><span class="sxs-lookup"><span data-stu-id="647aa-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="647aa-110">HoloLens 2 unterstützt die folgenden Bluetooth-APIs:</span><span class="sxs-lookup"><span data-stu-id="647aa-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="647aa-111">GATT-[Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) und -[Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="647aa-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="647aa-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="647aa-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="647aa-113">Möglicherweise müssen Sie entsprechende Begleit-Apps vom Microsoft Store installieren, um die HID- und GATT-Geräte tatsächlich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="647aa-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="647aa-114">HoloLens (1. Generation) unterstützt die folgenden Bluetooth-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="647aa-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="647aa-115">Maus</span><span class="sxs-lookup"><span data-stu-id="647aa-115">Mouse</span></span>
- <span data-ttu-id="647aa-116">Tastatur</span><span class="sxs-lookup"><span data-stu-id="647aa-116">Keyboard</span></span>
- [<span data-ttu-id="647aa-117">Clicker für HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="647aa-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="647aa-118">Andere Arten von Bluetooth-Geräten wie Lautsprecher, Headsets, Smartphones und Gamepads sind möglicherweise in den HoloLens-Einstellungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="647aa-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="647aa-119">Allerdings werden diese Geräte auf HoloLens (1. Generation) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="647aa-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="647aa-120">Weitere Informationen finden Sie unter [HoloLens Einstellungen listet die Geräte als verfügbar auf, aber die Geräte funktionieren nicht](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span><span class="sxs-lookup"><span data-stu-id="647aa-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="647aa-121">Koppeln einer Bluetooth-Tastatur oder -Maus</span><span class="sxs-lookup"><span data-stu-id="647aa-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="647aa-122">Schalten Sie die Tastatur oder die Maus ein, damit sie auffindbar ist.</span><span class="sxs-lookup"><span data-stu-id="647aa-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="647aa-123">Wenn Sie wissen möchten, wie das Gerät auffindbar ist, suchen Sie nach Informationen auf dem Gerät (oder dessen Dokumentation), oder besuchen Sie die Website des Herstellers.</span><span class="sxs-lookup"><span data-stu-id="647aa-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="647aa-124">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zum **Start** zu gelangen, und wählen Sie dann **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="647aa-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="647aa-125">Wählen Sie **Geräte** aus und vergewissern Sie sich, dass Bluetooth aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="647aa-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="647aa-126">Wenn der Gerätename angezeigt wird, wählen Sie **Koppeln** aus und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="647aa-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="647aa-127">Bluetooth deaktivieren</span><span class="sxs-lookup"><span data-stu-id="647aa-127">Disable Bluetooth</span></span>

<span data-ttu-id="647aa-128">Mit diesem Verfahren werden die RF-Komponenten des Bluetooth-Funks deaktiviert, und alle Bluetooth-Funktionen auf Microsoft-HoloLens werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="647aa-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="647aa-129">Verwenden Sie die Bloom-Geste (HoloLens (1. Generation)) oder die Start-Geste (HoloLens 2), um zum **Start** zu gelangen, und wählen Sie dann **Einstellungen** > **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="647aa-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="647aa-130">Bewegen Sie den Schieberegler für **Bluetooth** an die Position **Aus**.</span><span class="sxs-lookup"><span data-stu-id="647aa-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="647aa-131">HoloLens 2: Anschließen von USB-C-Geräten</span><span class="sxs-lookup"><span data-stu-id="647aa-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="647aa-132">HoloLens 2 unterstützt die folgenden USB-C-Geräteklassen:</span><span class="sxs-lookup"><span data-stu-id="647aa-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="647aa-133">Massenspeicher Geräte (wie z. B. USB-Sticks)</span><span class="sxs-lookup"><span data-stu-id="647aa-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="647aa-134">Ethernet-Adapter (einschließlich Ethernet plus-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="647aa-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="647aa-135">USB-C-auf-3,5 mm Audio-Adapter</span><span class="sxs-lookup"><span data-stu-id="647aa-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="647aa-136">USB-C Digital Audio Headsets (einschließlich Headset-Adaptern plus Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="647aa-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="647aa-137">Externe USB-C-Mikrofone ([Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher)</span><span class="sxs-lookup"><span data-stu-id="647aa-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="647aa-138">Kabelgebundene Maus</span><span class="sxs-lookup"><span data-stu-id="647aa-138">Wired mouse</span></span>
- <span data-ttu-id="647aa-139">Kabelgebundene Tastatur</span><span class="sxs-lookup"><span data-stu-id="647aa-139">Wired keyboard</span></span>
- <span data-ttu-id="647aa-140">Kombinations-PD-Hubs (USB A plus PD-Ladevorgang)</span><span class="sxs-lookup"><span data-stu-id="647aa-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="647aa-141">Als Antwort auf das Kundenfeedback haben wir die eingeschränkte Unterstützung für Mobilfunkverbindungen aktiviert, die über USB-C direkt an die HoloLens angebunden sind.</span><span class="sxs-lookup"><span data-stu-id="647aa-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="647aa-142">Weitere Informationen finden Sie unter [Verbinden mit Mobilfunk und 5G](hololens-cellular.md).</span><span class="sxs-lookup"><span data-stu-id="647aa-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="647aa-143">Unterstützung externer USB-C-Mikrofone</span><span class="sxs-lookup"><span data-stu-id="647aa-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="647aa-144">Wenn Sie ein **USB-Mikrofon anschließen, wird es nicht automatisch als Eingabegerät festgelegt**.</span><span class="sxs-lookup"><span data-stu-id="647aa-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="647aa-145">Wenn Sie ein USB-C-Kopfhörer anschließen, werden Benutzer feststellen, dass die Audiodaten des Kopfhörers automatisch an den Kopfhörer umgeleitet werden, aber das HoloLens-Betriebssystem priorisiert das interne Mikrofon-Array über jedem anderen Eingabegerät.</span><span class="sxs-lookup"><span data-stu-id="647aa-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="647aa-146">**Führen Sie die folgenden Schritte aus, um ein USB-C-Mikrofon zu verwenden.**</span><span class="sxs-lookup"><span data-stu-id="647aa-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="647aa-147">Externe Mikrofone können nicht in Builds vor [Windows Holographic, Version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) und höher, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="647aa-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="647aa-148">Benutzer können externe Mikrofone mit USB-C-Verbindung über das Einstellungsfeld **Sound** auswählen.</span><span class="sxs-lookup"><span data-stu-id="647aa-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="647aa-149">USB-C-Mikrofone können zum Aufrufen, Aufzeichnen usw. verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="647aa-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="647aa-150">Öffnen Sie die App **Einstellungen**, und wählen Sie **System** > **Sound** aus.</span><span class="sxs-lookup"><span data-stu-id="647aa-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Sound-Einstellungen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="647aa-152">Um externe Mikrofone mit **Remote Assist** verwenden zu können, müssen Benutzer auf den Link „Soundgeräte verwalten“ klicken.</span><span class="sxs-lookup"><span data-stu-id="647aa-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="647aa-153">Verwenden Sie dann die Dropdownliste, um das externe Mikrofon entweder auf **Standard** oder **Kommunikationsstandard** zu setzen.</span><span class="sxs-lookup"><span data-stu-id="647aa-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="647aa-154">Die Auswahl **Standard** bedeutet, dass das externe Mikrofon überall verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="647aa-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="647aa-155">Die Auswahl von **Kommunikationsstandard** bedeutet, dass das externe Mikrofon in Remote Assist und anderen Kommunikations-Apps verwendet wird, aber das HoloLens-Mikrofon-Array kann weiterhin für andere Aufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="647aa-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Verwalten von Soundgeräten](images/usbc-mic-2.png)

<br>

![Festlegen der Mikrofon-Standardeinstellung](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="647aa-158">Wie sieht es mit der Unterstützung von Bluetooth Mikrofonen aus?</span><span class="sxs-lookup"><span data-stu-id="647aa-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="647aa-159">Leider werden Bluetooth Mikrofone derzeit nicht von HoloLens 2 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="647aa-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="647aa-160">USB-C-Hubs</span><span class="sxs-lookup"><span data-stu-id="647aa-160">USB-C Hubs</span></span>

<span data-ttu-id="647aa-161">Einige Benutzer müssen möglicherweise mehrere Geräte gleichzeitig verbinden.</span><span class="sxs-lookup"><span data-stu-id="647aa-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="647aa-162">Für Benutzer, die ein [USB-C-Mikrofon](#usb-c-external-microphone-support) zusammen mit einem anderen verbundenen Gerät verwenden möchten, können USB-C-Hubs den Anforderungen des Kunden entsprechen.</span><span class="sxs-lookup"><span data-stu-id="647aa-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="647aa-163">Diese Geräte wurden nicht von Microsoft getestet. Microsoft kann keine bestimmten Marken empfehlen.</span><span class="sxs-lookup"><span data-stu-id="647aa-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="647aa-164">**Anforderungen an den USB-C-Hub und angeschlossene Geräte:**</span><span class="sxs-lookup"><span data-stu-id="647aa-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="647aa-165">Angeschlossene Geräte dürfen keinen Treiber benötigen, der installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="647aa-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="647aa-166">Die Gesamtleistung aller angeschlossenen Geräte muss unter 4,5 Watt liegen.</span><span class="sxs-lookup"><span data-stu-id="647aa-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="647aa-167">Herstellen einer Verbindung mit Miracast</span><span class="sxs-lookup"><span data-stu-id="647aa-167">Connect to Miracast</span></span>

<span data-ttu-id="647aa-168">Wenn Sie Miracast verwenden möchten, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="647aa-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="647aa-169">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="647aa-169">Do one of the following:</span></span>  

   - <span data-ttu-id="647aa-170">Öffnen Sie das **Startmenü** und wählen Sie das Symbol **Anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="647aa-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="647aa-171">Sagen Sie „Verbinden“, während Sie auf das **Startmenü** schauen.</span><span class="sxs-lookup"><span data-stu-id="647aa-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="647aa-172">Wählen Sie aus der Liste der angezeigten Geräte ein verfügbares Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="647aa-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="647aa-173">Führen Sie die Kopplung aus, um mit dem projizieren zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="647aa-173">Complete the pairing to begin projecting.</span></span>
