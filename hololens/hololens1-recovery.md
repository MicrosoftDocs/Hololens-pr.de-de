---
title: Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Verwenden des Windows Device Recovery-Tools zum Flashen eines Bilds in HoloLens 1. Generation.
keywords: Gewusst wie, Neustart, Zurücksetzen, Wiederherstellen, hartes Zurücksetzen, Soft Reset, Energiezyklus, HoloLens, heruntergefahren, wdrt, Windows-Gerätewiederherstellungstool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397691"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="1eb3f-104">Neustarten, Zurücksetzen oder Wiederherstellen von HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="1eb3f-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="1eb3f-105">Wenn Sie Probleme mit HoloLens haben, können Sie einen Neustart oder eine Zurücksetzung versuchen oder das Gerät mithilfe der Gerätewiederherstellung zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="1eb3f-106">In diesem Artikel werden die empfohlenen Wiederherstellungsschritte in der gewünschten Reihenfolge erläutert.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="1eb3f-107">Wenn Sie eine HoloLens 2 wiederherstellen möchten, lesen Sie [Wiederherstellen eines HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), da sich dieser Prozess unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb3f-108">Dieser Artikel konzentriert sich auf das HoloLens-Gerät und die HoloLens-Software.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="1eb3f-109">Wenn Ihre Hologramme nicht richtig aussehen, finden Sie unter **[Überlegungen zur HoloLens-Umgebung](hololens-environment-considerations.md)** Informationen zu Faktoren, die die Hologrammqualität verbessern.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="1eb3f-110">Neu starten</span><span class="sxs-lookup"><span data-stu-id="1eb3f-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="1eb3f-111">Ausführen eines sicheren Neustarts mit Cortana</span><span class="sxs-lookup"><span data-stu-id="1eb3f-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="1eb3f-112">Die sicherste Möglichkeit zum Neustarten der HoloLens ist die Verwendung von Cortana. Dies ist in der Regel das erste, was Sie ausprobieren sollten, wenn ein Problem mit HoloLens vorliegt.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="1eb3f-113">Cortana ist nicht auf allen Geräten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="1eb3f-114">Cortana ist auf allen HoloLens-Geräten (1. Generation) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="1eb3f-115">Cortana ist auf HoloLens 2 Geräten in Builds vor dem Windows Holograpic-Update, Version 2004, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="1eb3f-116">Aktivieren Sie Ihre HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="1eb3f-117">Stellen Sie sicher, dass ein Benutzer angemeldet ist und das Gerät nicht auf das Entsperren eines Kennworts wartet.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="1eb3f-118">Sagen Sie "Hey Cortana, reboot" oder "Hey Cortana, restart".</span><span class="sxs-lookup"><span data-stu-id="1eb3f-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="1eb3f-119">Cortana antwortet und fordert Sie zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="1eb3f-120">Warten Sie, bis nach der Frage ein Sound wiedergegeben wird, und sagen Sie dann "Ja".</span><span class="sxs-lookup"><span data-stu-id="1eb3f-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="1eb3f-121">Das Gerät wird neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="1eb3f-122">Verwenden des Netzschalters für einen sicheren Neustart</span><span class="sxs-lookup"><span data-stu-id="1eb3f-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="1eb3f-123">Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie, es mithilfe des Netzschalters **neu zu** starten:</span><span class="sxs-lookup"><span data-stu-id="1eb3f-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="1eb3f-124">Halten Sie den **Netzschalter** 5 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="1eb3f-125">Nach 1 Sekunde werden alle fünf LEDs nach und nach von rechts nach links eingeschaltet.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="1eb3f-126">Nach 5 Sekunden sind alle LEDs deaktiviert, was auf ein erfolgreiches Herunterfahren hinweist.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="1eb3f-127">Halten Sie das Drücken der Schaltfläche sofort an, nachdem alle LEDs ausgeschaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="1eb3f-128">Warten Sie 1 Minute, bis das Herunterfahren abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="1eb3f-129">Das Herunterfahren wird möglicherweise auch nach dem Ausschalten der Anzeigen noch nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="1eb3f-130">Schalten Sie das Gerät erneut ein, indem Sie den **Netzschalter** 1 Sekunde gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="1eb3f-131">Einen sicheren Neustart mit Windows-Geräteportal</span><span class="sxs-lookup"><span data-stu-id="1eb3f-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="1eb3f-132">Für diesen Prozess muss HoloLens als Entwicklergerät konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="1eb3f-133">Weitere Informationen finden [Sie Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="1eb3f-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="1eb3f-134">Wenn das vorherige Verfahren nicht funktioniert hat, versuchen Sie, das Gerät mithilfe von neu [Windows-Geräteportal.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="1eb3f-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="1eb3f-135">Suchen Sie in der oberen rechten Ecke nach der Option zum Neustarten oder Herunterfahren des Geräts.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="1eb3f-136">Unsicheren erzwungenen Neustart</span><span class="sxs-lookup"><span data-stu-id="1eb3f-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="1eb3f-137">Wenn die vorherigen Methoden Ihre HoloLens nicht neu gestartet haben, erzwingen Sie einen Neustart.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="1eb3f-138">Diese Methode entspricht dem Entfernen und erneuten Installieren des Akkus.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="1eb3f-139">Es ist gefährlich, da ihr Gerät möglicherweise in einem beschädigten Zustand befährt wird.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="1eb3f-140">In diesem Fall müssen Sie Ihre HoloLens flashen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="1eb3f-141">Dies ist eine potenziell schädliche Methode und sollte nur verwendet werden, wenn die zuvor genannten Methoden nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="1eb3f-142">Halten Sie den **Netzschalter** mindestens 10 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="1eb3f-143">Es ist in Ordnung, die Schaltfläche länger als 10 Sekunden zu halten.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="1eb3f-144">Es ist sicher, alle LED-Aktivitäten zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="1eb3f-145">Lassen Sie die Schaltfläche los, und warten Sie 2 bis 3 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="1eb3f-146">Drücken Sie , und halten Sie den **Netzschalter** 1 Sekunde lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="1eb3f-147">Wenn weiterhin Probleme auftreten, drücken Sie 4 Sekunden lang den **Netzschalter,** bis alle Akkuindikatoren ausgeblendet sind und der Bildschirm die Anzeige von Hologrammen beendet.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="1eb3f-148">Warten Sie eine Minute, und drücken Sie dann erneut den **Netzschalter,** um das Gerät einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="1eb3f-149">Zurücksetzen auf Werkseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3f-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="1eb3f-150">Für die Akkukapazität ist mindestens eine Gebühr von 40 Prozent erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="1eb3f-151">Wenn Bei HoloLens weiterhin ein Problem auftritt, versuchen Sie, es auf den Werkszustand zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="1eb3f-152">In diesem Schritt wird die Version der darauf installierten Windows Holographic-Software geschaltet, und alle anderen Einstellungen werden an die Werkseinstellungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="1eb3f-153">Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre personenbezogenen Daten, Apps und Einstellungen gelöscht, einschließlich tpm-Zurücksetzungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="1eb3f-154">Beim Zurücksetzen wird nur die neueste installierte Version von Windows Holographic installiert.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="1eb3f-155">Sie müssen alle Initialisierungsschritte wiederholen (Kalibrieren, Herstellen einer Wlan-Verbindung, Erstellen eines Benutzerkontos, Herunterladen von Apps usw.).</span><span class="sxs-lookup"><span data-stu-id="1eb3f-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="1eb3f-156">Öffnen Sie die App Einstellungen, und wählen Sie dann   >  **Wiederherstellung aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="1eb3f-157">Wählen Sie die Option **Gerät zurücksetzen** aus, und lesen Sie die Bestätigungsmeldung.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="1eb3f-158">Bestätigen Sie die Zurücksetzung.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-158">Confirm the reset.</span></span> <span data-ttu-id="1eb3f-159">Das Gerät wird neu gestartet und zeigt eine Reihe von spinierenden Zahnradgeräten und eine Statusanzeige an.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="1eb3f-160">Warten Sie ungefähr 30 Minuten, bis dieser Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="1eb3f-161">Wenn dies abgeschlossen ist, wird das Gerät sofort neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="1eb3f-162">Erneutes Installieren des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="1eb3f-162">Reinstall the operating system</span></span>

<span data-ttu-id="1eb3f-163">Wenn das Gerät nach dem Neustart und Zurücksetzen weiterhin ein Problem hat, können Sie ein Wiederherstellungstool auf Ihrem Computer verwenden, um das HoloLens-Betriebssystem und die Firmware neu zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="1eb3f-164">Die Daten, die HoloLens für das Zurücksetzen benötigt, sind in einem Full Flash Update (FFU) gepackt, das einer ISO-, WIM- oder VHD-Datei ähnelt.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="1eb3f-165">Erfahren Sie mehr über FFU-Bilddateiformate.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="1eb3f-166">Sie können ein neues Betriebssystem auf HoloLens (1. Generation) installieren, indem Sie das Windows Device Recovery Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="1eb3f-167">Bevor Sie dieses Tool verwenden, sollten Sie prüfen, ob das Problem durch einen Neustart oder zurücksetzen ihrer HoloLens behoben wird.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="1eb3f-168">Der Wiederherstellungsprozess kann eine Weile dauern.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-168">The recovery process may take a while.</span></span> <span data-ttu-id="1eb3f-169">Wenn dies abgeschlossen ist, wird die neueste Version der Windows Holographic-Software installiert.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="1eb3f-170">Um das Tool verwenden zu können, benötigen Sie einen Computer mit Windows 10 oder höher mit mindestens 4 GB freiem Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="1eb3f-171">Sie können dieses Tool nicht auf einem virtuellen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="1eb3f-172">Wiederherstellen Ihrer HoloLens</span><span class="sxs-lookup"><span data-stu-id="1eb3f-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="1eb3f-173">Laden Sie das [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) herunter, und installieren Sie es auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="1eb3f-174">Verbinden Sie die HoloLens (1. Generation) mit Ihrem Computer, indem Sie das Micro-USB-Kabel verwenden, das mit Ihrer HoloLens geliefert wurde.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="1eb3f-175">Öffnen Sie das Windows Device Recovery Tool, und befolgen Sie die Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="1eb3f-176">Wenn HoloLens (1. Generation) nicht automatisch erkannt wird, wählen Sie **Mein Gerät wurde nicht erkannt aus.**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="1eb3f-177">Befolgen Sie dann die Anweisungen, um das Gerät in den Wiederherstellungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="1eb3f-178">Manueller Flashmodus</span><span class="sxs-lookup"><span data-stu-id="1eb3f-178">Manual flashing mode</span></span>

<span data-ttu-id="1eb3f-179">Wenn Ihr Gerät nicht erkannt wird, führen Sie die folgenden Schritte aus, um es in den Flashmodus zu versetzen:</span><span class="sxs-lookup"><span data-stu-id="1eb3f-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="1eb3f-180">Trennen Sie das Gerät von einer beliebigen Stromquelle.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="1eb3f-181">Wenn das Gerät eingeschaltet ist, halten Sie den **Netzschalter** gedrückt, bis er vollständig ausgeschaltet ist.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="1eb3f-182">Halten Sie die **Lautstärke** gedrückt, und tippen Sie kurz auf den **Netzschalter.**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="1eb3f-183">Das Gerät sollte nur die mittlere LED starten und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="1eb3f-184">Schließen Sie das Gerät an Ihren PC an.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="1eb3f-185">Öffnen Sie das Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="1eb3f-186">Wählen Sie **Mein Gerät wurde nicht erkannt** und dann **HoloLens aus.**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="1eb3f-187">Befolgen Sie die Anweisungen zum Wiederherstellen Ihres Geräts.</span><span class="sxs-lookup"><span data-stu-id="1eb3f-187">Follow the instructions to recover your device.</span></span>
