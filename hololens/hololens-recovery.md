---
title: Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Verwenden von Advanced Recovery Companion (ARC), um einen Flash eines Images in HoloLens 2 auszuführen.
keywords: 'Anleitung für: Neustart, Zurücksetzen, Wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, ARC, Advanced Recovery Companion'
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
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923634"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="7bf90-104">Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7bf90-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="7bf90-105">Bevor Sie eine Problembehandlung starten, stellen Sie sicher, dass Ihr Gerät wenn möglich auf **20 bis 40 Prozent** der Akkukapazität aufgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7bf90-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="7bf90-106">Die [Akkukontrollleuchten](hololens2-setup.md#lights-that-indicate-the-battery-level) unter dem Netzschalter sind eine schnelle Möglichkeit, die Akkukapazität zu überprüfen, ohne sich beim Gerät anzumelden.</span><span class="sxs-lookup"><span data-stu-id="7bf90-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="7bf90-107">Verwenden Sie das [Ladegerät und das USB Type-C-Kabel](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1), das mit der HoloLens 2 geliefert wurde, da dies die beste Möglichkeit zum Laden Ihres Geräts ist.</span><span class="sxs-lookup"><span data-stu-id="7bf90-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="7bf90-108">Das Ladegerät liefert 18 W (9 V bei 2 A).</span><span class="sxs-lookup"><span data-stu-id="7bf90-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="7bf90-109">Mit dem mitgelieferten Wandladegerät können HoloLens 2-Geräte den Akku in weniger als 65 Minuten voll aufladen, wenn sich das Gerät im Standby-Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="7bf90-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="7bf90-110">Wenn das Zubehör nicht verfügbar ist, vergewissern Sie sich, dass das verfügbare Ladegerät mindestens 15 W Leistung unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="7bf90-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="7bf90-111">Vermeiden Sie nach Möglichkeit die Verwendung eines PCs, um das Gerät über USB zu laden, was sehr langsam ist.</span><span class="sxs-lookup"><span data-stu-id="7bf90-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="7bf90-112">Wenn das Gerät korrekt hochgefahren ist und läuft, gibt es drei verschiedene Möglichkeiten, den Akkustand zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7bf90-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="7bf90-113">Über das Hauptmenü der Benutzeroberfläche des HoloLens-Geräts.</span><span class="sxs-lookup"><span data-stu-id="7bf90-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="7bf90-114">Sehen Sie sich die LEDs in der Nähe des Netzschalters an (bei 40 % Akkustand sollten mindestens zwei LEDs leuchten).</span><span class="sxs-lookup"><span data-stu-id="7bf90-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="7bf90-115">Während des Ladevorgangs leuchtet die Akkuanzeige auf, um den aktuellen Ladezustand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="7bf90-116">Die letzte Anzeige leuchtet auf und erlischt, um den aktiven Ladevorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="7bf90-117">Wenn Ihre HoloLens eingeschaltet ist, zeigt die Akkuanzeige den Akkustand in fünf Stufen an.</span><span class="sxs-lookup"><span data-stu-id="7bf90-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="7bf90-118">Wenn nur eine der fünf LEDs leuchtet, ist der Akkustand unter 20 %.</span><span class="sxs-lookup"><span data-stu-id="7bf90-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="7bf90-119">Wenn der Akkuladestand kritisch niedrig ist und Sie versuchen, das Gerät einzuschalten, blinkt eine LED kurz und erlischt anschließend.</span><span class="sxs-lookup"><span data-stu-id="7bf90-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="7bf90-120">Öffnen Sie auf Ihrem Host-PC den **Datei-Explorer** und suchen Sie auf der linken Seite unter **Dieser PC** nach Ihrem HoloLens 2 Gerät.</span><span class="sxs-lookup"><span data-stu-id="7bf90-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="7bf90-121">Klicken Sie mit der rechten Maustaste auf das Gerät und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7bf90-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="7bf90-122">Ein Dialogfeld mit dem Akkustand wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bf90-122">A dialog box will show the battery charge level.</span></span>

   ![Ein Bildschirm mit den HoloLens 2-Eigenschaften zeigt den Akkustand.](images/ResetRecovery2.png)

<span data-ttu-id="7bf90-124">Wenn das Gerät nicht ins Startmenü hochfahren kann, beachten Sie die LED-Darstellung und die Geräteaufzählung auf dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="7bf90-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="7bf90-125">Befolgen Sie dann die [Anleitung zur Problembehandlung](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="7bf90-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="7bf90-126">Falls der Zustand des Geräts mit keinem der im Handbuch zur Fehlerbehebung aufgeführten Zustände übereinstimmt, führen Sie einen [Kaltstart](hololens-recovery.md#hard-reset-procedure) durch, wobei das Gerät nicht mit Ihrem Host-PC, sondern mit dem Netzteil verbunden sein muss.</span><span class="sxs-lookup"><span data-stu-id="7bf90-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="7bf90-127">Warten Sie mindestens eine Stunde, bis das Gerät aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="7bf90-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="7bf90-128">Zurücksetzen des Geräts</span><span class="sxs-lookup"><span data-stu-id="7bf90-128">Reset the device</span></span>

<span data-ttu-id="7bf90-129">Unter bestimmten Umständen möchten Sie das Gerät möglicherweise manuell zurücksetzen, ohne die Software-Benutzeroberfläche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7bf90-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="7bf90-130">Standardverfahren</span><span class="sxs-lookup"><span data-stu-id="7bf90-130">Standard procedure</span></span>

1. <span data-ttu-id="7bf90-131">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="7bf90-132">Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="7bf90-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="7bf90-133">Alle LEDs sollten aus sein.</span><span class="sxs-lookup"><span data-stu-id="7bf90-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="7bf90-134">Warten Sie 2 bis 3 Sekunden und drücken Sie dann kurz den **Netzschalter**.</span><span class="sxs-lookup"><span data-stu-id="7bf90-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="7bf90-135">Die LEDs, die sich in der Nähe des Netzschalters befinden, leuchten auf, und das Gerät beginnt hochzufahren.</span><span class="sxs-lookup"><span data-stu-id="7bf90-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="7bf90-136">Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie dann den Geräte-Manager.</span><span class="sxs-lookup"><span data-stu-id="7bf90-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="7bf90-137">(Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät, wie im folgenden Bild dargestellt, korrekt als *Microsoft HoloLens* aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="7bf90-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gerätemanager für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="7bf90-139">Kaltstart-Verfahren</span><span class="sxs-lookup"><span data-stu-id="7bf90-139">Hard-reset procedure</span></span>

<span data-ttu-id="7bf90-140">Wenn das Standard Zurücksetzungsverfahren nicht funktioniert, verwenden Sie das Kaltstart-Verfahren:</span><span class="sxs-lookup"><span data-stu-id="7bf90-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="7bf90-141">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="7bf90-142">Halten Sie Tasten **Lautstärke senken** + und den **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="7bf90-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="7bf90-143">Das Gerät wird automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="7bf90-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="7bf90-144">Verbinden Sie das Gerät mit dem Host-PC.</span><span class="sxs-lookup"><span data-stu-id="7bf90-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="7bf90-145">Öffnen Sie den Geräte-Manager (drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste und wählen Sie dann **Gerätemanager** aus).</span><span class="sxs-lookup"><span data-stu-id="7bf90-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="7bf90-146">Stellen Sie sicher, dass das Gerät ordnungsgemäß als *Microsoft HoloLens* aufgeführt wird, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="7bf90-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Gerätemanager 2 für HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="7bf90-148">Ausführen von „Clean-Reflash“ am Gerät</span><span class="sxs-lookup"><span data-stu-id="7bf90-148">Clean-reflash the device</span></span>

<span data-ttu-id="7bf90-149">In außergewöhnlichen Situationen müssen Sie möglicherweise „Clean-Flash“ am HoloLens 2-Gerät durchführen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="7bf90-150">Beachten Sie, dass sich ein „Clean-Reflash“ erwartungsgemäß nicht auf die folgenden Probleme auswirkt:</span><span class="sxs-lookup"><span data-stu-id="7bf90-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="7bf90-151">Display-Farbgleichmäßigkeit</span><span class="sxs-lookup"><span data-stu-id="7bf90-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="7bf90-152">Startvorgang mit Sound, aber ohne Bildschirmausgabe</span><span class="sxs-lookup"><span data-stu-id="7bf90-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="7bf90-153">1-3-5-LED-Muster</span><span class="sxs-lookup"><span data-stu-id="7bf90-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="7bf90-154">Überhitzung</span><span class="sxs-lookup"><span data-stu-id="7bf90-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="7bf90-155">Betriebssystemabstürze (welche sich von Anwendungsabstürzen unterscheiden)</span><span class="sxs-lookup"><span data-stu-id="7bf90-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="7bf90-156">Es gibt es zwei Möglichkeiten ein „Reflash“ für das Gerät durchzuführen</span><span class="sxs-lookup"><span data-stu-id="7bf90-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="7bf90-157">Für beide müssen Sie zunächst [Advanced Recovery Companion aus dem Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) installieren.</span><span class="sxs-lookup"><span data-stu-id="7bf90-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="7bf90-158">Wenn Sie Ihr Gerät neu „flashen“, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="7bf90-159">Standardmäßig ist Advanced Recovery Companion so eingestellt, dass der neueste Featurerelease-Build heruntergeladen wird. In unseren [Versionshinweisen](hololens-release-notes.md#) finden Sie weitere Informationen zu den neuesten Featurereleases.</span><span class="sxs-lookup"><span data-stu-id="7bf90-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="7bf90-160">Um das neueste HoloLens 2 Full Flash Update (FFU) Paket zu erhalten, um Ihr Gerät über Advanced Recovery Companion zu „reflashen“, [klicken Sie hier, um das neueste monatliche HoloLens 2 Image herunterzuladen](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="7bf90-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="7bf90-161">Diese Version ist der neueste allgemein verfügbare Build.</span><span class="sxs-lookup"><span data-stu-id="7bf90-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="7bf90-162">Stellen Sie vor dem Starten des „Flashens“ sicher, dass die App auf Ihrem Windows 10-PC installiert ist, läuft und bereit ist, das Gerät zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="7bf90-163">Stellen Sie außerdem sicher, dass Ihre HoloLens auf mindestens 40 % aufgeladen ist.</span><span class="sxs-lookup"><span data-stu-id="7bf90-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![„Clean Reflash“ für HoloLens 2 – Screenshot](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="7bf90-165">Normales Verfahren</span><span class="sxs-lookup"><span data-stu-id="7bf90-165">Normal procedure</span></span>

1. <span data-ttu-id="7bf90-166">Während das HoloLens-Gerät läuft, verbinden Sie es mit Ihrem Windows 10-PC, auf dem Sie zuvor die Advanced Recovery Companion-App geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="7bf90-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="7bf90-167">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-App startet den Updatevorgang:</span><span class="sxs-lookup"><span data-stu-id="7bf90-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![„Clean Reflash“ für HoloLens 2 – Startbildschirm](images/ARC2.png)

3. <span data-ttu-id="7bf90-169">Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-Anwendung aus und befolgen Sie die Anweisungen, um den „Reflash“ abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="7bf90-170">Manuelle Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="7bf90-170">Manual procedure</span></span>

<span data-ttu-id="7bf90-171">Wenn die HoloLens 2 nicht ordnungsgemäß gestartet wird oder Advanced Recovery Companion das Gerät nicht erkennen kann, müssen Sie das Gerät möglicherweise in den Wiederherstellungsmodus versetzen:</span><span class="sxs-lookup"><span data-stu-id="7bf90-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="7bf90-172">Trennen Sie das Gerät von der Stromversorgung oder dem Host-PC, indem Sie das Typ-C-Kabel abziehen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="7bf90-173">Halten Sie den **Netzschalter** 15 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="7bf90-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="7bf90-174">Alle LEDs sollten erlöschen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="7bf90-175">Während Sie die Taste **Lautstärke erhöhen** betätigen, drücken Sie den **Netzschalter** und lassen ihn los, um das Gerät zu starten.</span><span class="sxs-lookup"><span data-stu-id="7bf90-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="7bf90-176">Warten Sie 15 Sekunden lang, und lassen Sie dann die Taste **Lautstärke erhöhen** los.</span><span class="sxs-lookup"><span data-stu-id="7bf90-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="7bf90-177">Nur die mittlere LED der fünf LEDs leuchtet auf.</span><span class="sxs-lookup"><span data-stu-id="7bf90-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="7bf90-178">Verbinden Sie das Gerät mit dem Host-PC, und öffnen Sie den Geräte-Manager.</span><span class="sxs-lookup"><span data-stu-id="7bf90-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="7bf90-179">(Drücken Sie unter Windows 10 die **Windows**-Taste und dann die **X**-Taste und wählen Sie dann **Geräte-Manager** aus.) Stellen Sie sicher, dass das Gerät, wie im folgenden Bild dargestellt, korrekt als Microsoft HoloLens aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="7bf90-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="7bf90-181">Das Gerät wird automatisch erkannt und die Benutzeroberfläche der Advanced Recovery Companion-App startet den Updatevorgang:</span><span class="sxs-lookup"><span data-stu-id="7bf90-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![„Clean Reflash“ für HoloLens 2 – Bildschirm](images/ARC2.png)

6. <span data-ttu-id="7bf90-183">Wählen Sie das HoloLens 2-Gerät in der Benutzeroberfläche der Advanced Recovery Companion-App aus und befolgen Sie dann die Anweisungen, um das erneute „Flashen“ abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="7bf90-184">Problembehandlung für Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="7bf90-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="7bf90-185">Stellen Sie sicher, dass Ihr Gerät 40 % oder mehr aufgeladen ist, bevor Sie versuchen zu „flashen“.</span><span class="sxs-lookup"><span data-stu-id="7bf90-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="7bf90-186">Stellen Sie sicher, dass Ihr Gerät entsperrt ist.</span><span class="sxs-lookup"><span data-stu-id="7bf90-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="7bf90-187">Wenn ARC Ihr Gerät nicht erkennt, stellen Sie sicher, dass Sie über den Datei-Explorer auf Ihrem PC eine Verbindung mit Ihrem Gerät herstellen können.</span><span class="sxs-lookup"><span data-stu-id="7bf90-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="7bf90-188">Wenn das nicht möglich ist:</span><span class="sxs-lookup"><span data-stu-id="7bf90-188">If you cannot;</span></span>

    1.  <span data-ttu-id="7bf90-189">Möglicherweise verfügt Ihr Gerät über USB-Richtlinien, die diese Verbindung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7bf90-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="7bf90-190">Wenn ja, versuchen Sie den [Manuellen Flash-Modus](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="7bf90-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="7bf90-191">Wenn keine Richtlinien vorhanden sind, versuchen Sie es mit einem anderen USB-Kabel.</span><span class="sxs-lookup"><span data-stu-id="7bf90-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="7bf90-192">Stellen Sie sicher, dass ihr Gerät kein [1-3-5-LED-Muster](hololens2-setup.md#lights-to-indicate-problems) anzeigt.</span><span class="sxs-lookup"><span data-stu-id="7bf90-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="7bf90-193">Herunterladen von ARC, ohne den App Store zu verwenden</span><span class="sxs-lookup"><span data-stu-id="7bf90-193">Download ARC without using the app store</span></span>

<span data-ttu-id="7bf90-194">Wenn eine IT-Umgebung die Verwendung der Windows Store-App verhindert oder den Zugriff auf das Einzelhandelsgeschäft einschränkt, können IT-Administratoren diese App über andere "Offline"-Bereitstellungspfade verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="7bf90-195">IT-Administratoren können diese Anwendung auch über System Center Configuration Manager (SCCM) oder Intune verteilen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="7bf90-196">Dieses Handbuch konzentriert sich auf Advanced Recovery Companion. Der Prozess kann aber auch für andere „Offline“-Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7bf90-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="7bf90-197">Führen Sie die folgenden Schritte aus, um den Bereitstellungspfad zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="7bf90-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="7bf90-198">Wechseln Sie zum [Microsoft Store für Unternehmen](https://businessstore.microsoft.com) und melden Sie sich mit einer Azure Active Directory Domain Service-Identität an.</span><span class="sxs-lookup"><span data-stu-id="7bf90-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="7bf90-199">Navigieren Sie zu **Verwalten – Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="7bf90-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="7bf90-200">Aktivieren Sie **Offline-Apps anzeigen** unter **Einkaufserlebnis**.</span><span class="sxs-lookup"><span data-stu-id="7bf90-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="7bf90-201">Wechseln Sie zum **Shop für meine Gruppe** und suchen Sie nach [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="7bf90-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="7bf90-202">Ändern Sie den **Lizenztyp** in **_offline_ *_, und wählen Sie _* Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="7bf90-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="7bf90-203">Wählen unter **Paket für Offline-Verwendung herunterladen** die zweite blaue Schaltfläche **Herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="7bf90-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="7bf90-204">Stellen Sie sicher, dass die Dateierweiterung *.appxbundle* lautet.</span><span class="sxs-lookup"><span data-stu-id="7bf90-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="7bf90-205">Wenn der Desktop-PC zu diesem Zeitpunkt über einen Internetzugang verfügt, doppelklicken Sie auf das Paket, um die App zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7bf90-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="7bf90-206">Wenn der Ziel-PC keine Internetverbindung hat, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7bf90-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="7bf90-207">Wählen Sie die unverschlüsselte Lizenz und dann **Lizenz generieren** aus.</span><span class="sxs-lookup"><span data-stu-id="7bf90-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="7bf90-208">Wählen Sie unter **Erforderliche Frameworks** die Option **Herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="7bf90-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="7bf90-209">Verwenden Sie DISM, um das Paket mit Abhängigkeit und Lizenz anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="7bf90-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="7bf90-210">Führen Sie an einer Administrator-Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7bf90-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="7bf90-211">Die Versionsnummer in diesem Codebeispiel stimmt möglicherweise nicht mit der aktuell verfügbaren Version überein.</span><span class="sxs-lookup"><span data-stu-id="7bf90-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="7bf90-212">Möglicherweise haben Sie auch einen anderen Download-Speicherort als im angegebenen Beispiel ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7bf90-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="7bf90-213">Nehmen Sie nach Bedarf Änderungen am Befehl vor.</span><span class="sxs-lookup"><span data-stu-id="7bf90-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="7bf90-214">Wenn Sie beabsichtigen, Advanced Recovery Companion zur Offline-Installation eines FFU zu verwenden, ist es möglicherweise sinnvoll, Ihr Flash-Image herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="7bf90-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="7bf90-215">[**Laden Sie das aktuelle Image für HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="7bf90-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="7bf90-216">Weitere Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="7bf90-216">Other resources:</span></span>
- [<span data-ttu-id="7bf90-217">Verteilen von Offline-Apps</span><span class="sxs-lookup"><span data-stu-id="7bf90-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="7bf90-218">DISM-App-Paket (.appx oder .appxbundle) – Befehlszeilenoptionen</span><span class="sxs-lookup"><span data-stu-id="7bf90-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
