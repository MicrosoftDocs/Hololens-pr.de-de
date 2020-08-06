---
title: HoloLens 1 neustarten, zurücksetzen oder wiederherstellen
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: So verwenden Sie das Windows-Tool zum Wiederherstellen des Geräts, um ein Bild durch Flash zu HoloLens 1st Gen auszuführen.
keywords: Hilfe & Anleitung, Neustart, zurücksetzen, wiederherstellen, Kaltstart, Warmstart, Energiezyklus, HoloLens, Herunterfahren, wdrt, Windows Device Recovery Tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915945"
---
# <span data-ttu-id="f7e38-104">HoloLens (1. Generation) neustarten, zurücksetzen oder wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="f7e38-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="f7e38-105">Wenn Sie Probleme mit Ihrem HoloLens haben, können Sie versuchen, das Gerät neu zu starten, zurückzusetzen oder sogar neu zu flashen, indem Sie die Gerätewiederherstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7e38-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="f7e38-106">Dieser Artikel führt Sie durch die empfohlenen Schritte für die Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="f7e38-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="f7e38-107">Wenn Sie ein HoloLens 2 wiederherstellen möchten, finden Sie Informationen dazu unter [Wiederherstellen einer HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), da sich der Vorgang unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="f7e38-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="f7e38-108">Dieser Artikel befasst sich mit dem HoloLens-Gerät und der entsprechenden Software.</span><span class="sxs-lookup"><span data-stu-id="f7e38-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="f7e38-109">Wenn Ihre Hologramme nicht richtig aussehen, finden Sie Informationen zu Faktoren, die die Qualität des Hologramms verbessern, unter **[Überlegungen zur HoloLens-Umgebung](hololens-environment-considerations.md)**.</span><span class="sxs-lookup"><span data-stu-id="f7e38-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <span data-ttu-id="f7e38-110">Neu starten</span><span class="sxs-lookup"><span data-stu-id="f7e38-110">Restart</span></span>

### <span data-ttu-id="f7e38-111">Durchführen eines sicheren Neustarts mithilfe von Cortana</span><span class="sxs-lookup"><span data-stu-id="f7e38-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="f7e38-112">Die sicherste Methode zum Neustarten des HoloLens ist die Verwendung von Cortana, was im Allgemeinen das erste ist, was Sie versuchen können, wenn ein Problem mit HoloLens auftritt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="f7e38-113">Cortana ist nicht auf allen Geräten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7e38-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="f7e38-114">Cortana ist für alle HoloLens-Geräte der ersten Generation verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7e38-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="f7e38-115">Cortana ist auf HoloLens 2-Geräten mit Builds vor dem Update mit Windows Holograpic, Version 2004, verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7e38-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="f7e38-116">Schalten Sie Ihr HoloLens ein.</span><span class="sxs-lookup"><span data-stu-id="f7e38-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="f7e38-117">Vergewissern Sie sich, dass ein Benutzer angemeldet ist und das Gerät nicht auf ein Kennwort wartet, um es zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="f7e38-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="f7e38-118">Sagen Sie "Hey Cortana, erneut starten" oder "Hey Cortana, Neustart".</span><span class="sxs-lookup"><span data-stu-id="f7e38-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="f7e38-119">Cortana antwortet und fordert Sie zur Bestätigung auf.</span><span class="sxs-lookup"><span data-stu-id="f7e38-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="f7e38-120">Warten Sie, bis nach der Frage ein Sound wiedergegeben wird, und sagen Sie dann "Ja".</span><span class="sxs-lookup"><span data-stu-id="f7e38-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="f7e38-121">Das Gerät wird neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="f7e38-121">The device will restart.</span></span>

### <span data-ttu-id="f7e38-122">Verwenden des Netzschalters für einen sicheren Neustart</span><span class="sxs-lookup"><span data-stu-id="f7e38-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="f7e38-123">Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie, es mit dem **Netzschalter** neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="f7e38-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="f7e38-124">Halten Sie den **Netzschalter** 5 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="f7e38-125">Nach einer Sekunde leuchten alle fünf LEDs. Danach werden sie einzeln von rechts nach links langsam abgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="f7e38-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="f7e38-126">Nach fünf Sekunden sind alle LEDs aus, was bedeutet, dass das Herunterfahren erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f7e38-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="f7e38-127">Lassen Sie die Taste unmittelbar nach dem Ausschalten aller LEDs los.</span><span class="sxs-lookup"><span data-stu-id="f7e38-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="f7e38-128">Warten Sie 1 Minute, bis das Herunterfahren abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f7e38-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="f7e38-129">Beachten Sie, dass der Vorgang des Herunterfahrens möglicherweise weiterhin ausgeführt wird, auch wenn die Anzeigen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f7e38-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="f7e38-130">Schalten Sie das Gerät erneut ein, indem Sie den **Netzschalter** eine Sekunde lang gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="f7e38-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <span data-ttu-id="f7e38-131">Durchführen eines sicheren Neustarts mithilfe des Windows-Geräteportals</span><span class="sxs-lookup"><span data-stu-id="f7e38-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="f7e38-132">Für diesen Vorgang muss HoloLens als Entwicklergerät konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="f7e38-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="f7e38-133">Weitere Informationen finden Sie im [Windows-Geräteportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="f7e38-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="f7e38-134">Wenn das vorstehende Verfahren nicht funktioniert, können Sie versuchen, das Gerät mithilfe des [Windows-Geräteportals](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="f7e38-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="f7e38-135">In der oberen rechten Ecke gibt es eine Option, um das Gerät neu zu starten oder herunterzufahren.</span><span class="sxs-lookup"><span data-stu-id="f7e38-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <span data-ttu-id="f7e38-136">Durchführen eines unsicheren erzwungenen Neustarts</span><span class="sxs-lookup"><span data-stu-id="f7e38-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="f7e38-137">Wenn die vorstehenden Methoden Ihr HoloLens nicht neu starten, erzwingen Sie einen Neustart.</span><span class="sxs-lookup"><span data-stu-id="f7e38-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="f7e38-138">Diese Methode entspricht dem Entfernen und erneuten Einlegen der Batterie.</span><span class="sxs-lookup"><span data-stu-id="f7e38-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="f7e38-139">Das ist gefährlich, da Ihr Gerät möglicherweise in einem beschädigten Zustand bleibt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="f7e38-140">In diesem Fall müssen Sie bei Ihrem HoloLens einen Flash ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="f7e38-141">Dies ist eine potenziell schädliche Methode und sollte nur verwendet werden, wenn keine der vorhergehenden Methoden funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f7e38-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="f7e38-142">Halten Sie den **Netzschalter** mindestens 10 Sekunden lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="f7e38-143">Es ist in Ordnung, die Taste länger als 10 Sekunden zu halten.</span><span class="sxs-lookup"><span data-stu-id="f7e38-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="f7e38-144">Sie können die LED-Aktivitäten ignorieren.</span><span class="sxs-lookup"><span data-stu-id="f7e38-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="f7e38-145">Lassen Sie den Schalter los, und warten Sie zwei oder drei Sekunden.</span><span class="sxs-lookup"><span data-stu-id="f7e38-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="f7e38-146">Halten Sie den **Netzschalter** 1 Sekunde lang gedrückt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="f7e38-147">Wenn Sie weiterhin Probleme haben, drücken Sie den **Netzschalter** 4 Sekunden lang, bis alle Akkuanzeigen ausgeblendet sind und der Bildschirm keine Hologramme mehr anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="f7e38-148">Warten Sie 1 Minute, und drücken Sie dann erneut den **Netzschalter**, um das Gerät einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="f7e38-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <span data-ttu-id="f7e38-149">Zurücksetzen von Geräten auf Werkseinstellungen</span><span class="sxs-lookup"><span data-stu-id="f7e38-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="f7e38-150">Der Akkustand muss mindestens bei 40 Prozent liegen, damit der Zurücksetzungsvorgang erfolgreich ausgeführt werden kann. </span><span class="sxs-lookup"><span data-stu-id="f7e38-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="f7e38-151">Wenn Ihr HoloLens weiterhin ein Problem hat, versuchen Sie, es auf den Werkszustand zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="f7e38-152">Durch diesen Schritt wird die Version der Windows Holographic-Software beibehalten, die auf dem Computer installiert ist, und alle anderen Elemente werden auf die Werkseinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="f7e38-153">Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="f7e38-154">Durch das Zurücksetzen wird nur die zuletzt installierte Version von Windows Holographic installiert.</span><span class="sxs-lookup"><span data-stu-id="f7e38-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="f7e38-155">Sie müssen alle Initialisierungsschritte (Kalibrieren, Verbindung mit WLAN, Erstellen eines Benutzerkontos, Herunterladen von Apps usw.) wiederholen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="f7e38-156">Öffnen Sie die App „Einstellungen“, und wählen Sie **Update** > **Wiederherstellung** aus.</span><span class="sxs-lookup"><span data-stu-id="f7e38-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="f7e38-157">Wählen Sie die Option **Gerät zurücksetzen** aus, und lesen Sie die Bestätigungsmeldung.</span><span class="sxs-lookup"><span data-stu-id="f7e38-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="f7e38-158">Bestätigen Sie das Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-158">Confirm the reset.</span></span> <span data-ttu-id="f7e38-159">Das Gerät wird neu gestartet, und es wird eine Reihe von rotierenden Zahnrädern mit einer Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="f7e38-160">Warten Sie etwa 30 Minuten, bis dieser Vorgang durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7e38-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="f7e38-161">Das Zurücksetzen wird durchgeführt, und das Gerät wird in die sofort verwendbare Umgebung neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="f7e38-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <span data-ttu-id="f7e38-162">Neuinstallation des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="f7e38-162">Reinstall the operating system</span></span>

<span data-ttu-id="f7e38-163">Wenn nach dem Neustart und Zurücksetzen des Geräts weiterhin ein Problem auftritt, können Sie auf Ihrem Computer ein Wiederherstellungstool verwenden, um das Betriebssystem und die Firmware des HoloLens neu zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f7e38-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="f7e38-164">Die Daten, die HoloLens für das Zurücksetzen benötigt, sind in einem Full Flash-Update (FFU) gepackt, das einer ISO-, WIM-oder VHD-Datei ähnelt.</span><span class="sxs-lookup"><span data-stu-id="f7e38-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="f7e38-165">Erfahren Sie mehr über die FFU Bilddateiformate.</span><span class="sxs-lookup"><span data-stu-id="f7e38-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="f7e38-166">Sie können ein neues Betriebssystem auf Ihrem HoloLens (1. Generation) mit dem Windows Device Recovery Tool installieren.</span><span class="sxs-lookup"><span data-stu-id="f7e38-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="f7e38-167">Bevor Sie dieses Tool verwenden, überprüfen Sie, ob das Problem Ihres HoloLens durch Neustart oder Zurücksetzen behoben wird.</span><span class="sxs-lookup"><span data-stu-id="f7e38-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="f7e38-168">Der Wiederherstellungsvorgang kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-168">The recovery process may take a while.</span></span> <span data-ttu-id="f7e38-169">Wenn Sie damit fertig sind, wird die neueste Version der für Ihre HoloLens genehmigten Windows Holographic-Software installiert.</span><span class="sxs-lookup"><span data-stu-id="f7e38-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="f7e38-170">Wenn Sie das Tool verwenden möchten, benötigen Sie einen Computer mit Windows 10 oder höher mit mindestens 4 GB freien Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="f7e38-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="f7e38-171">Sie können dieses Tool nicht auf einem virtuellen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-171">You can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="f7e38-172">Wiederherstellung Ihres HoloLens</span><span class="sxs-lookup"><span data-stu-id="f7e38-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="f7e38-173">[Windows-Geräte Wiederherstellung Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) auf Ihrem Computer herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="f7e38-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="f7e38-174">Schießen Sie Ihr HoloLens (1. Generation) an Ihren Computer an, indem Sie das Micro-USB-Kabel verwenden, das im Lieferumfang Ihres HoloLens enthalten war.</span><span class="sxs-lookup"><span data-stu-id="f7e38-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="f7e38-175">Öffnen Sie das Windows Device Recovery Tool, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="f7e38-176">Wenn das HoloLens (1. Generation) nicht automatisch erkannt wird, wählen Sie **Mein Gerät wurde nicht erkannt** aus.</span><span class="sxs-lookup"><span data-stu-id="f7e38-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="f7e38-177">Folgen Sie dann den Anweisungen, um das Gerät in den Wiederherstellungsmodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <span data-ttu-id="f7e38-178">Manueller Flashmodus</span><span class="sxs-lookup"><span data-stu-id="f7e38-178">Manual flashing mode</span></span>

<span data-ttu-id="f7e38-179">Wenn Ihr Gerät nicht erkannt wird, führen Sie die folgenden Schritte aus, um es in den Flashmodus zu versetzen:</span><span class="sxs-lookup"><span data-stu-id="f7e38-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="f7e38-180">Trennen Sie das Gerät von allen Stromquellen.</span><span class="sxs-lookup"><span data-stu-id="f7e38-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="f7e38-181">Wenn das Gerät eingeschaltet ist, halten Sie den **Netzschalter** gedrückt, bis es vollständig ausgeschaltet ist.</span><span class="sxs-lookup"><span data-stu-id="f7e38-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="f7e38-182">Halten Sie die **Lauter**-Taste gedrückt, und tippen Sie kurz auf den **Netzschalter**.</span><span class="sxs-lookup"><span data-stu-id="f7e38-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="f7e38-183">Das Gerät sollte starten, und nur die mittlere LED sollte leuchten.</span><span class="sxs-lookup"><span data-stu-id="f7e38-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="f7e38-184">Verbinden Sie das Gerät mit Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="f7e38-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="f7e38-185">Öffnen Sie das Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="f7e38-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="f7e38-186">Wählen Sie **Mein Gerät wurde nicht erkannt** und dann **HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="f7e38-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="f7e38-187">Befolgen Sie die Anweisungen, um das Gerät wiederherzustellen..</span><span class="sxs-lookup"><span data-stu-id="f7e38-187">Follow the instructions to recover your device.</span></span>
