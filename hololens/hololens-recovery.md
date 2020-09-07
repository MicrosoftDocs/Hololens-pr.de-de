---
title: HoloLens neu starten, zurücksetzen oder wiederherstellen
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Verwenden von Advanced Recovery Companion (ARC), um einen Flashs eines Images in HoloLens 2 auszuführen.
keywords: Hilfe & Anleitung, Neustart, zurücksetzen, wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, ARC, Advanced Recovery Companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 8c028ed39cf0925ebff18ca69889de2d87f1e7eb
ms.sourcegitcommit: e3056a433aeebb8bc45dc3f6db9a75f212fdf53b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996413"
---
# <span data-ttu-id="27e0a-104">HoloLens 2 neu starten, zurücksetzen oder wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="27e0a-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="27e0a-105">Laden des Geräts</span><span class="sxs-lookup"><span data-stu-id="27e0a-105">Charge the device</span></span>

<span data-ttu-id="27e0a-106">Bevor Sie eine Problembehandlung starten, stellen Sie sicher, dass Ihr Gerät möglichst auf 20 bis 40 Prozent der Akkukapazität aufgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="27e0a-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="27e0a-107">Verwenden Sie das Ladegerät und die USB-Typ-C-Kabel, die mit dem HoloLens2-Gerät geliefert wurden.</span><span class="sxs-lookup"><span data-stu-id="27e0a-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="27e0a-108">Die in der Lieferung des Geräts enthaltene Stromversorgung und das USB-C-zu-C-Kabel sind die beste Methode zum Aufladen Ihrer HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="27e0a-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="27e0a-109">Das Ladegerät liefert 18W (9V bei 2A).</span><span class="sxs-lookup"><span data-stu-id="27e0a-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="27e0a-110">Wenn das Zubehör nicht verfügbar ist, vergewissern Sie sich, dass das verfügbare Ladegerät mindestens 15W Leistung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="27e0a-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="27e0a-111">Vermeiden Sie nach Möglichkeit die Verwendung eines PCs, um das Gerät über USB zu laden, was sehr langsam ist.</span><span class="sxs-lookup"><span data-stu-id="27e0a-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="27e0a-112">Wenn das Gerät korrekt hochgefahren und ausgeführt wird, gibt es drei verschiedene Möglichkeiten, den Ladezustand des Akkus zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="27e0a-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="27e0a-113">Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.</span><span class="sxs-lookup"><span data-stu-id="27e0a-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="27e0a-114">Sehen Sie sich die LEDs in der Nähe des Netzschalters an (bei 40 % sollten mindestens zwei LEDs ununterbrochen leuchten).</span><span class="sxs-lookup"><span data-stu-id="27e0a-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="27e0a-115">Während des Ladevorgangs leuchtet die Akkuanzeige auf, um den aktuellen Ladezustand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="27e0a-116">Die letzte Anzeige leuchtet auf und erlischt, um den aktiven Ladevorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="27e0a-117">Wenn Ihre HoloLens eingeschaltet ist, zeigt die Akkuanzeige den Akkustand in fünf Schritten an.</span><span class="sxs-lookup"><span data-stu-id="27e0a-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="27e0a-118">Wenn nur eine der fünf LEDs leuchtet, ist der Akkustand unter 20%.</span><span class="sxs-lookup"><span data-stu-id="27e0a-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="27e0a-119">Wenn der Akkuladestand kritisch niedrig ist und Sie versuchen, das Gerät einzuschalten, blinkt eine LED kurz und erlischt anschließend.</span><span class="sxs-lookup"><span data-stu-id="27e0a-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="27e0a-120">Öffnen Sie auf Ihrem Host-PC den **Datei-Explorer**, und suchen Sie Ihr HoloLens 2-Gerät auf der linken Seite unter **Dieser PC**.</span><span class="sxs-lookup"><span data-stu-id="27e0a-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="27e0a-121">Klicken Sie mit der rechten Maustaste auf das Gerät, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="27e0a-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="27e0a-122">Ein Dialogfeld mit dem Akkuladezustand wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27e0a-122">A dialog box will show the battery charge level.</span></span>

   ![Ein HoloLens 2-Eigenschaftenbildschirm zeigt den Akkuladezustand.](images/ResetRecovery2.png)

<span data-ttu-id="27e0a-124">Wenn das Gerät nicht ins Startmenü starten kann, beachten Sie das LED-Erscheinungsbild und die Geräteenumeration auf dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="27e0a-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="27e0a-125">Folgen Sie dann der [Anleitung zur Problembehandlung](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="27e0a-125">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="27e0a-126">Falls der Status des Geräts nicht mit einem der im Handbuch zur Fehlerbehebung aufgeführten Zustände übereinstimmt, führen Sie den [Hard-Reset-Vorgang](hololens-recovery.md#hard-reset-procedure) aus, wobei das Gerät nicht mit Ihrem Host-PC, sondern mit dem Netzteil verbunden sein muss.</span><span class="sxs-lookup"><span data-stu-id="27e0a-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="27e0a-127">Warten Sie mindestens eine Stunde, bis das Gerät aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="27e0a-127">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="27e0a-128">Setzen Sie das Gerät zurück</span><span class="sxs-lookup"><span data-stu-id="27e0a-128">Reset the device</span></span>

<span data-ttu-id="27e0a-129">Unter bestimmten Umständen möchten Sie das Gerät möglicherweise manuell zurücksetzen, ohne die Software-Benutzeroberfläche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="27e0a-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="27e0a-130">Standardvorgehensweise</span><span class="sxs-lookup"><span data-stu-id="27e0a-130">Standard procedure</span></span>
1. <span data-ttu-id="27e0a-131">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="27e0a-132">Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="27e0a-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="27e0a-133">Alle LEDs sollten aus sein.</span><span class="sxs-lookup"><span data-stu-id="27e0a-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="27e0a-134">Warten Sie 2 bis 3 Sekunden, und drücken Sie dann den **Netzschalter**.</span><span class="sxs-lookup"><span data-stu-id="27e0a-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="27e0a-135">Die LEDs, die sich in der Nähe des Netzschalters befinden, leuchten auf, und das Gerät wird hochgefahren.</span><span class="sxs-lookup"><span data-stu-id="27e0a-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="27e0a-136">Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie dann den Geräte-Manager.</span><span class="sxs-lookup"><span data-stu-id="27e0a-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="27e0a-137">(Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät wie im folgenden Bild korrekt als *Microsoft HoloLens* aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="27e0a-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="27e0a-139">Hard-Reset-Verfahren</span><span class="sxs-lookup"><span data-stu-id="27e0a-139">Hard-reset procedure</span></span>

<span data-ttu-id="27e0a-140">Wenn das Standardzurücksetzungsverfahren nicht funktioniert, verwenden Sie das Hard-Reset-Verfahren:</span><span class="sxs-lookup"><span data-stu-id="27e0a-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="27e0a-141">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="27e0a-142">Halten Sie die **Leiser-Taste** und den  + **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="27e0a-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="27e0a-143">Das Gerät wird automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="27e0a-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="27e0a-144">Verbinden Sie das Gerät mit dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="27e0a-144">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="27e0a-145">Öffnen Sie den Geräte-Manager (drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus).</span><span class="sxs-lookup"><span data-stu-id="27e0a-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="27e0a-146">Stellen Sie sicher, dass das Gerät ordnungsgemäß als *Microsoft HoloLens* aufgelistet wird, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="27e0a-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="27e0a-148">Clean-Reflash des Geräts</span><span class="sxs-lookup"><span data-stu-id="27e0a-148">Clean-reflash the device</span></span>

<span data-ttu-id="27e0a-149">In außergewöhnlichen Situationen müssen Sie das HoloLens 2 möglicherweise „clean flashen“.</span><span class="sxs-lookup"><span data-stu-id="27e0a-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="27e0a-150">Beachten Sie, dass sich ein Clean-Reflash erwartungsgemäß nicht auf die folgenden Probleme auswirkt:</span><span class="sxs-lookup"><span data-stu-id="27e0a-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="27e0a-151">Farbhomogenität des Bildschirms</span><span class="sxs-lookup"><span data-stu-id="27e0a-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="27e0a-152">Startvorgang mit Sound, aber ohne Bildschirmausgabe</span><span class="sxs-lookup"><span data-stu-id="27e0a-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="27e0a-153">1-3-5-LED-Muster</span><span class="sxs-lookup"><span data-stu-id="27e0a-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="27e0a-154">Überhitzung</span><span class="sxs-lookup"><span data-stu-id="27e0a-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="27e0a-155">Betriebssystemabstürze (was sich von Anwendungsabstürzen unterscheidet)</span><span class="sxs-lookup"><span data-stu-id="27e0a-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="27e0a-156">Dafür gibt es zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="27e0a-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="27e0a-157">Für beide müssen Sie zuerst [Advanced Recovery Companion aus dem Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)installieren.</span><span class="sxs-lookup"><span data-stu-id="27e0a-157">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="27e0a-158">Wenn Sie Ihr Gerät neu flashen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="27e0a-159">Standardmäßig ist Advanced Recovery Companion zurzeit so eingerichtet, dass der Funktionsbuild für [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="27e0a-159">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="27e0a-160">Um das neueste HoloLens 2 Full Flash Update (FFU) zu erhalten und Ihr Gerät über Advanced Recovery Companion neu zu flashen, [laden Sie es hier herunter](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="27e0a-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="27e0a-161">Diese Version ist der neueste allgemein verfügbare Build.</span><span class="sxs-lookup"><span data-stu-id="27e0a-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="27e0a-162">Stellen Sie vor dem Starten des Flashens sicher, dass die Anwendung auf Ihrem Windows 10-PC installiert ist, ausgeführt wird und bereit ist, das Gerät zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![„Clean Reflash“ für HoloLens 2 – Screenshot](images/ARC1.png)

### <span data-ttu-id="27e0a-164">Normales Verfahren</span><span class="sxs-lookup"><span data-stu-id="27e0a-164">Normal procedure</span></span>

1. <span data-ttu-id="27e0a-165">Während das HoloLens-Gerät ausgeführt wird, verbinden Sie es mit Ihrem Windows 10-PC, auf dem Sie zuvor die Advanced Recovery Companion-Anwendung gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="27e0a-165">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="27e0a-166">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung startet den Updatevorgang:</span><span class="sxs-lookup"><span data-stu-id="27e0a-166">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

3. <span data-ttu-id="27e0a-168">Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um das erneute Flashen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-168">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="27e0a-169">Manuelle Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="27e0a-169">Manual procedure</span></span>

<span data-ttu-id="27e0a-170">Wenn das HoloLens 2 nicht richtig startet, müssen Sie das Gerät möglicherweise in den Wiederherstellungsmodus versetzen:</span><span class="sxs-lookup"><span data-stu-id="27e0a-170">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="27e0a-171">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-171">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="27e0a-172">Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="27e0a-172">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="27e0a-173">Alle LEDs sollten erlöschen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-173">All LEDs should turn off.</span></span>

3. <span data-ttu-id="27e0a-174">Halten Sie die **Lauter-Taste** gedrückt, während Sie den **Netzschalter** drücken und loslassen, um das Gerät zu starten.</span><span class="sxs-lookup"><span data-stu-id="27e0a-174">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="27e0a-175">Warten Sie 15 Sekunden, bevor Sie die **Lauter-Taste** loslassen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-175">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="27e0a-176">Nur die mittlere LED der fünf LEDs leuchtet auf.</span><span class="sxs-lookup"><span data-stu-id="27e0a-176">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="27e0a-177">Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie den Geräte-Manager.</span><span class="sxs-lookup"><span data-stu-id="27e0a-177">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="27e0a-178">(Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät wie im folgenden Bild korrekt als „Microsoft HoloLens“ aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="27e0a-178">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="27e0a-180">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung startet den Updatevorgang:</span><span class="sxs-lookup"><span data-stu-id="27e0a-180">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![„Clean Reflash“ für HoloLens 2 – Bildschirm](images/ARC2.png)

6. <span data-ttu-id="27e0a-182">Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie dann die Anweisungen, um das erneute Flashen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-182">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="27e0a-183">Herunterladen von ARC ohne Verwendung des App Store</span><span class="sxs-lookup"><span data-stu-id="27e0a-183">Download ARC without using the app store</span></span>

<span data-ttu-id="27e0a-184">Wenn eine IT-Umgebung die Verwendung der Windows Store-App verhindert oder den Zugriff auf das Einzelhandelsgeschäft einschränkt, können IT-Administratoren diese Anwendung über andere "Offline"-Bereitstellungspfade verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-184">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="27e0a-185">IT-Administratoren können diese Anwendung auch über System Center Configuration Manager (SCCM) oder Intune verteilen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-185">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="27e0a-186">Dieses Handbuch konzentriert sich auf Advanced Recovery Companion. Der Prozess kann aber auch für andere Offline-Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27e0a-186">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="27e0a-187">Führen Sie die folgenden Schritte aus, um den Bereitstellungspfad zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="27e0a-187">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="27e0a-188">Wechseln Sie zum [Microsoft Store für Unternehmen](https://businessstore.microsoft.com), und melden Sie sich mit einer Azure Active Directory-Identität an.</span><span class="sxs-lookup"><span data-stu-id="27e0a-188">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="27e0a-189">Wechseln Sie zu **Verwalten – Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="27e0a-189">Go to **Manage – Settings**.</span></span> <span data-ttu-id="27e0a-190">Aktivieren Sie **Offline-Apps anzeigen** unter **Shopping-Erfahrung**.</span><span class="sxs-lookup"><span data-stu-id="27e0a-190">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="27e0a-191">Wechseln Sie zu **Einkaufen für meine Gruppe** und suchen Sie nach [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="27e0a-191">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="27e0a-192">Ändern Sie den **Lizenztyp** auf ***Offline***, und klicken Sie auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="27e0a-192">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="27e0a-193">Wählen Sie unter **Paket für Offline-Verwendung herunterladen** die zweite blaue Schaltfläche **Herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="27e0a-193">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="27e0a-194">Stellen Sie sicher, dass die Dateierweiterung *.appxbundle* lautet.</span><span class="sxs-lookup"><span data-stu-id="27e0a-194">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="27e0a-195">Wenn der Desktop-PC zu diesem Zeitpunkt über einen Internetzugang verfügt, doppelklicken Sie auf das Paket, um die App zu installieren.</span><span class="sxs-lookup"><span data-stu-id="27e0a-195">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="27e0a-196">Wenn der Ziel-PC keine Internetverbindung hat, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="27e0a-196">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="27e0a-197">Wählen Sie die nicht codierte Lizenz aus, und wählen Sie dann **Lizenz generieren** aus.</span><span class="sxs-lookup"><span data-stu-id="27e0a-197">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="27e0a-198">Wählen Sie unter **Erforderliche Frameworks** die Option **Herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="27e0a-198">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="27e0a-199">Verwenden Sie DISM, um das Paket mit Abhängigkeit und Lizenz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="27e0a-199">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="27e0a-200">Führen Sie an einer Administrator-Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="27e0a-200">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="27e0a-201">Die Versionsnummer in diesem Codebeispiel stimmt möglicherweise nicht mit der aktuell verfügbaren Version überein.</span><span class="sxs-lookup"><span data-stu-id="27e0a-201">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="27e0a-202">Möglicherweise haben Sie auch einen anderen Download-Speicherort als im angegebenen Beispiel ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="27e0a-202">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="27e0a-203">Nehmen Sie nach Bedarf Änderungen am Befehl vor.</span><span class="sxs-lookup"><span data-stu-id="27e0a-203">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="27e0a-204">Wenn Sie beabsichtigen, Advanced Recovery Companion zur Offlineinstallation eines FFU zu verwenden, ist es möglicherweise sinnvoll, Ihr Flash-Image herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="27e0a-204">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="27e0a-205">[**Laden Sie das aktuelle Image für HoloLens 2 herunter**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="27e0a-205">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="27e0a-206">Andere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="27e0a-206">Other resources:</span></span>
- [<span data-ttu-id="27e0a-207">Verteilen von Offline-Apps</span><span class="sxs-lookup"><span data-stu-id="27e0a-207">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="27e0a-208">DISM-App-Paket (.appx oder .appxbundle) – Befehlszeilenoptionen</span><span class="sxs-lookup"><span data-stu-id="27e0a-208">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
