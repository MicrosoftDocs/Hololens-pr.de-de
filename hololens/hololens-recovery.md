---
title: HoloLens neu starten, zurücksetzen oder wiederherstellen
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
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
ms.openlocfilehash: b5b9568bab5afebe4ac3e9d57645c18837c71cb6
ms.sourcegitcommit: fdae5b561d56d3d4e62da4db15f07bc10249398a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408425"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="535cf-104">HoloLens 2 neu starten, zurücksetzen oder wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="535cf-104">Restart, reset, or recover HoloLens 2</span></span>

## <a name="charge-the-device"></a><span data-ttu-id="535cf-105">Laden des Geräts</span><span class="sxs-lookup"><span data-stu-id="535cf-105">Charge the device</span></span>

<span data-ttu-id="535cf-106">Bevor Sie eine Problembehandlung starten, stellen Sie sicher, dass Ihr Gerät wenn möglich auf 20 bis 40 Prozent der Akkukapazität aufgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="535cf-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="535cf-107">Verwenden Sie [das Ladegerät und das USB Type-C-Kabel,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) das mit dem HoloLens 2-Gerät geliefert wird.</span><span class="sxs-lookup"><span data-stu-id="535cf-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that come with the HoloLens 2 device.</span></span> <span data-ttu-id="535cf-108">Das in der Lieferung des Geräts enthaltene Netzteil und das USB-C-zu-C-Kabel bieten die beste Methode zum Aufladen Ihrer HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="535cf-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="535cf-109">Das Ladegerät liefert 18W (9V bei 2A).</span><span class="sxs-lookup"><span data-stu-id="535cf-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="535cf-110">Mit dem mitgelieferten Wandladegerät können HoloLens 2-Geräte den Akku in weniger als 65 Minuten voll aufladen, wenn sich das Gerät im Standbymodus befindet.</span><span class="sxs-lookup"><span data-stu-id="535cf-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="535cf-111">Wenn das Zubehör nicht verfügbar ist, vergewissern Sie sich, dass das verfügbare Ladegerät mindestens 15W Leistung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="535cf-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="535cf-112">Vermeiden Sie nach Möglichkeit die Verwendung eines PCs, um das Gerät über USB zu laden, was sehr langsam ist.</span><span class="sxs-lookup"><span data-stu-id="535cf-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="535cf-113">Wenn das Gerät korrekt hochgefahren und ausgeführt wird, gibt es drei verschiedene Möglichkeiten, den Ladezustand des Akkus zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="535cf-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="535cf-114">Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.</span><span class="sxs-lookup"><span data-stu-id="535cf-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="535cf-115">Sehen Sie sich die LEDs in der Nähe des Netzschalters an (bei 40 % sollten mindestens zwei LEDs ununterbrochen leuchten).</span><span class="sxs-lookup"><span data-stu-id="535cf-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="535cf-116">Während des Ladevorgangs leuchtet die Akkuanzeige auf, um den aktuellen Ladezustand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="535cf-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="535cf-117">Die letzte Anzeige leuchtet auf und erlischt, um den aktiven Ladevorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="535cf-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="535cf-118">Wenn Ihre HoloLens eingeschaltet ist, zeigt die Akkuanzeige den Akkustand in fünf Schritten an.</span><span class="sxs-lookup"><span data-stu-id="535cf-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="535cf-119">Wenn nur eine der fünf LEDs leuchtet, ist der Akkustand unter 20%.</span><span class="sxs-lookup"><span data-stu-id="535cf-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="535cf-120">Wenn der Akkuladestand kritisch niedrig ist und Sie versuchen, das Gerät einzuschalten, blinkt eine LED kurz und erlischt anschließend.</span><span class="sxs-lookup"><span data-stu-id="535cf-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="535cf-121">Öffnen Sie auf Ihrem Host-PC den **Datei-Explorer**, und suchen Sie Ihr HoloLens 2-Gerät auf der linken Seite unter **Dieser PC**.</span><span class="sxs-lookup"><span data-stu-id="535cf-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="535cf-122">Klicken Sie mit der rechten Maustaste auf das Gerät, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="535cf-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="535cf-123">Ein Dialogfeld mit dem Akkuladezustand wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="535cf-123">A dialog box will show the battery charge level.</span></span>

   ![Ein HoloLens 2-Eigenschaftenbildschirm zeigt den Akkuladezustand.](images/ResetRecovery2.png)

<span data-ttu-id="535cf-125">Wenn das Gerät nicht ins Startmenü starten kann, beachten Sie das LED-Erscheinungsbild und die Geräteenumeration auf dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="535cf-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="535cf-126">Folgen Sie dann der [Anleitung zur Problembehandlung](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="535cf-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="535cf-127">Falls der Status des Geräts nicht mit einem der im Handbuch zur Fehlerbehebung aufgeführten Zustände übereinstimmt, führen Sie den [Hard-Reset-Vorgang](hololens-recovery.md#hard-reset-procedure) aus, wobei das Gerät nicht mit Ihrem Host-PC, sondern mit dem Netzteil verbunden sein muss.</span><span class="sxs-lookup"><span data-stu-id="535cf-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="535cf-128">Warten Sie mindestens eine Stunde, bis das Gerät aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="535cf-128">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="535cf-129">Setzen Sie das Gerät zurück</span><span class="sxs-lookup"><span data-stu-id="535cf-129">Reset the device</span></span>

<span data-ttu-id="535cf-130">Unter bestimmten Umständen möchten Sie das Gerät möglicherweise manuell zurücksetzen, ohne die Software-Benutzeroberfläche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="535cf-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="535cf-131">Standardvorgehensweise</span><span class="sxs-lookup"><span data-stu-id="535cf-131">Standard procedure</span></span>

1. <span data-ttu-id="535cf-132">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="535cf-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="535cf-133">Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="535cf-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="535cf-134">Alle LEDs sollten aus sein.</span><span class="sxs-lookup"><span data-stu-id="535cf-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="535cf-135">Warten Sie 2 bis 3 Sekunden, und drücken Sie dann den **Netzschalter**.</span><span class="sxs-lookup"><span data-stu-id="535cf-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="535cf-136">Die LEDs, die sich in der Nähe des Netzschalters befinden, leuchten auf, und das Gerät wird hochgefahren.</span><span class="sxs-lookup"><span data-stu-id="535cf-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="535cf-137">Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie dann den Geräte-Manager.</span><span class="sxs-lookup"><span data-stu-id="535cf-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="535cf-138">(Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät wie im folgenden Bild korrekt als *Microsoft HoloLens* aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="535cf-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gerätemanager für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="535cf-140">Hard-Reset-Verfahren</span><span class="sxs-lookup"><span data-stu-id="535cf-140">Hard-reset procedure</span></span>

<span data-ttu-id="535cf-141">Wenn das Standardzurücksetzungsverfahren nicht funktioniert, verwenden Sie das Hard-Reset-Verfahren:</span><span class="sxs-lookup"><span data-stu-id="535cf-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="535cf-142">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="535cf-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="535cf-143">Halten Sie die **Leiser-Taste** und den  + **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="535cf-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="535cf-144">Das Gerät wird automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="535cf-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="535cf-145">Verbinden Sie das Gerät mit dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="535cf-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="535cf-146">Öffnen Sie den Geräte-Manager (drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus).</span><span class="sxs-lookup"><span data-stu-id="535cf-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="535cf-147">Stellen Sie sicher, dass das Gerät ordnungsgemäß als *Microsoft HoloLens* aufgelistet wird, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="535cf-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gerätemanager 2 für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="535cf-149">Clean-Reflash des Geräts</span><span class="sxs-lookup"><span data-stu-id="535cf-149">Clean-reflash the device</span></span>

<span data-ttu-id="535cf-150">In außergewöhnlichen Situationen müssen Sie das HoloLens 2 möglicherweise „clean flashen“.</span><span class="sxs-lookup"><span data-stu-id="535cf-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="535cf-151">Beachten Sie, dass sich ein Clean-Reflash erwartungsgemäß nicht auf die folgenden Probleme auswirkt:</span><span class="sxs-lookup"><span data-stu-id="535cf-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="535cf-152">Farbhomogenität des Bildschirms</span><span class="sxs-lookup"><span data-stu-id="535cf-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="535cf-153">Startvorgang mit Sound, aber ohne Bildschirmausgabe</span><span class="sxs-lookup"><span data-stu-id="535cf-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="535cf-154">1-3-5-LED-Muster</span><span class="sxs-lookup"><span data-stu-id="535cf-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="535cf-155">Überhitzung</span><span class="sxs-lookup"><span data-stu-id="535cf-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="535cf-156">Betriebssystemabstürze (welche sich von Anwendungsabstürzen unterscheiden)</span><span class="sxs-lookup"><span data-stu-id="535cf-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="535cf-157">Dafür gibt es zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="535cf-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="535cf-158">Für beide müssen Sie zuerst [Advanced Recovery Companion aus dem Windows Store installieren](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="535cf-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="535cf-159">Wenn Sie Ihr Gerät neu flashen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="535cf-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="535cf-160">Standardmäßig ist Advanced Recovery Companion so eingestellt, dass der neueste Featurerelease-Build heruntergeladen wird. In unseren [Versionshinweisen](hololens-release-notes.md#) finden Sie weitere Informationen zu den neuesten Featurereleases.</span><span class="sxs-lookup"><span data-stu-id="535cf-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="535cf-161">Wenn Sie das neueste HoloLens 2 Full Flash Update (FFU)-Paket herunterladen möchten, um Ihr Gerät über Advanced Recovery Companion zu reflashen, [klicken Sie hier, um das neueste monatliche HoloLens 2-Image herunterzuladen](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="535cf-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="535cf-162">Diese Version ist der neueste allgemein verfügbare Build.</span><span class="sxs-lookup"><span data-stu-id="535cf-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="535cf-163">Stellen Sie vor dem Starten des Flashens sicher, dass die Anwendung auf Ihrem Windows 10-PC installiert ist, ausgeführt wird und bereit ist, das Gerät zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="535cf-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="535cf-164">Stellen Sie außerdem sicher, dass Ihre HoloLens auf mindestens 40 % aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="535cf-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![„Clean Reflash“ für HoloLens 2 – Screenshot](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="535cf-166">Normales Verfahren</span><span class="sxs-lookup"><span data-stu-id="535cf-166">Normal procedure</span></span>

1. <span data-ttu-id="535cf-167">Während das HoloLens-Gerät ausgeführt wird, verbinden Sie es mit Ihrem Windows 10-PC, auf dem Sie zuvor die Advanced Recovery Companion-Anwendung gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="535cf-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="535cf-168">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung startet den Updatevorgang:</span><span class="sxs-lookup"><span data-stu-id="535cf-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

3. <span data-ttu-id="535cf-170">Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um das erneute Flashen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="535cf-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="535cf-171">Manuelle Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="535cf-171">Manual procedure</span></span>

<span data-ttu-id="535cf-172">Wenn das HoloLens 2 nicht richtig startet, müssen Sie das Gerät möglicherweise in den Wiederherstellungsmodus versetzen:</span><span class="sxs-lookup"><span data-stu-id="535cf-172">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="535cf-173">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="535cf-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="535cf-174">Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="535cf-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="535cf-175">Alle LEDs sollten erlöschen.</span><span class="sxs-lookup"><span data-stu-id="535cf-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="535cf-176">Halten Sie die **Lauter-Taste** gedrückt, während Sie den **Netzschalter** drücken und loslassen, um das Gerät zu starten.</span><span class="sxs-lookup"><span data-stu-id="535cf-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="535cf-177">Warten Sie 15 Sekunden, bevor Sie die **Lauter-Taste** loslassen.</span><span class="sxs-lookup"><span data-stu-id="535cf-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="535cf-178">Nur die mittlere LED der fünf LEDs leuchtet auf.</span><span class="sxs-lookup"><span data-stu-id="535cf-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="535cf-179">Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie den Geräte-Manager.</span><span class="sxs-lookup"><span data-stu-id="535cf-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="535cf-180">(Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste, und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät wie im folgenden Bild korrekt als „Microsoft HoloLens“ aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="535cf-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="535cf-182">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-Anwendung startet den Updatevorgang:</span><span class="sxs-lookup"><span data-stu-id="535cf-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![„Clean Reflash“ für HoloLens 2 – Bildschirm](images/ARC2.png)

6. <span data-ttu-id="535cf-184">Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie dann die Anweisungen, um das erneute Flashen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="535cf-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="535cf-185">Herunterladen von ARC ohne Verwendung des App Store</span><span class="sxs-lookup"><span data-stu-id="535cf-185">Download ARC without using the app store</span></span>

<span data-ttu-id="535cf-186">Wenn eine IT-Umgebung die Verwendung der Windows Store-App verhindert oder den Zugriff auf das Einzelhandelsgeschäft einschränkt, können IT-Administratoren diese Anwendung über andere "Offline"-Bereitstellungspfade verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="535cf-186">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="535cf-187">IT-Administratoren können diese Anwendung auch über System Center Configuration Manager (SCCM) oder Intune verteilen.</span><span class="sxs-lookup"><span data-stu-id="535cf-187">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="535cf-188">Dieses Handbuch konzentriert sich auf Advanced Recovery Companion. Der Prozess kann aber auch für andere Offline-Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="535cf-188">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="535cf-189">Führen Sie die folgenden Schritte aus, um den Bereitstellungspfad zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="535cf-189">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="535cf-190">Wechseln Sie zum [Microsoft Store für Unternehmen](https://businessstore.microsoft.com), und melden Sie sich mit einer Azure Active Directory-Identität an.</span><span class="sxs-lookup"><span data-stu-id="535cf-190">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="535cf-191">Wechseln Sie zu **Verwalten – Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="535cf-191">Go to **Manage – Settings**.</span></span> <span data-ttu-id="535cf-192">Aktivieren Sie **Offline-Apps anzeigen** unter **Shopping-Erfahrung**.</span><span class="sxs-lookup"><span data-stu-id="535cf-192">Turn on **Show offline apps** under **Shopping experience**.</span></span>
1. <span data-ttu-id="535cf-193">Wechseln Sie zu **Shop für meine Gruppe**, und suchen Sie nach [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="535cf-193">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="535cf-194">Ändern Sie den **Lizenztyp** zu **_offline_*_, und wählen Sie _\* Verwalten*\* aus.</span><span class="sxs-lookup"><span data-stu-id="535cf-194">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>
1. <span data-ttu-id="535cf-195">Wählen Sie unter **Paket für Offline-Verwendung herunterladen** die zweite blaue Schaltfläche **Herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="535cf-195">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="535cf-196">Stellen Sie sicher, dass die Dateierweiterung *.appxbundle* lautet.</span><span class="sxs-lookup"><span data-stu-id="535cf-196">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="535cf-197">Wenn der Desktop-PC zu diesem Zeitpunkt über einen Internetzugang verfügt, doppelklicken Sie auf das Paket, um die App zu installieren.</span><span class="sxs-lookup"><span data-stu-id="535cf-197">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="535cf-198">Wenn der Ziel-PC keine Internetverbindung hat, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="535cf-198">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="535cf-199">Wählen Sie die nicht codierte Lizenz aus, und wählen Sie dann **Lizenz generieren** aus.</span><span class="sxs-lookup"><span data-stu-id="535cf-199">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="535cf-200">Wählen Sie unter **Erforderliche Frameworks** die Option **Herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="535cf-200">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="535cf-201">Verwenden Sie DISM, um das Paket mit Abhängigkeit und Lizenz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="535cf-201">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="535cf-202">Führen Sie an einer Administrator-Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="535cf-202">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="535cf-203">Die Versionsnummer in diesem Codebeispiel stimmt möglicherweise nicht mit der aktuell verfügbaren Version überein.</span><span class="sxs-lookup"><span data-stu-id="535cf-203">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="535cf-204">Möglicherweise haben Sie auch einen anderen Download-Speicherort als im angegebenen Beispiel ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="535cf-204">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="535cf-205">Nehmen Sie nach Bedarf Änderungen am Befehl vor.</span><span class="sxs-lookup"><span data-stu-id="535cf-205">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="535cf-206">Wenn Sie beabsichtigen, Advanced Recovery Companion zur Offlineinstallation eines FFU zu verwenden, ist es möglicherweise sinnvoll, Ihr Flash-Image herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="535cf-206">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="535cf-207">[**Laden Sie das aktuelle Image für HoloLens 2 herunter**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="535cf-207">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>

<span data-ttu-id="535cf-208">Andere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="535cf-208">Other resources:</span></span>
- [<span data-ttu-id="535cf-209">Verteilen von Offline-Apps</span><span class="sxs-lookup"><span data-stu-id="535cf-209">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="535cf-210">DISM-App-Paket (.appx oder .appxbundle) – Befehlszeilenoptionen</span><span class="sxs-lookup"><span data-stu-id="535cf-210">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
