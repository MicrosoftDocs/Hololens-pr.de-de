---
title: HoloLens 1 neustarten, zurücksetzen oder wiederherstellen
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: a52e8e5bae49973d92efa6ea75391dc44d8b8ddb
ms.sourcegitcommit: 357094acfd39f7c59a0a62f1dd7918b58c209ef7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "10861160"
---
# <span data-ttu-id="146ee-104">HoloLens (1. Generation) neustarten, zurücksetzen oder wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="146ee-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="146ee-105">Wenn Sie Probleme mit Ihrem HoloLens haben, können Sie versuchen, einen Neustart, zurücksetzen oder sogar einen erneuten Blitz mit Geräte-Wiederherstellung durchführen.</span><span class="sxs-lookup"><span data-stu-id="146ee-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="146ee-106">Hier sind einige Dinge, die Sie ausprobieren können, wenn Ihr HoloLens nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="146ee-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="146ee-107">Dieser Artikel führt Sie durch die empfohlenen Schritte für die Wiederherstellung in Folge.</span><span class="sxs-lookup"><span data-stu-id="146ee-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="146ee-108">Wenn Sie sich für die Wiederherstellung eines HoloLens 2 interessieren, schauen Sie sich die Seite für [Wiederherstellen einer HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)an, da es Unterschiede bei den Prozessen gibt.</span><span class="sxs-lookup"><span data-stu-id="146ee-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="146ee-109">Dieser Artikel befasst sich mit dem HoloLens-Gerät und der Software. Wenn Ihre Hologramme nicht richtig aussehen, [dieser Artikel](hololens-environment-considerations.md) spricht über Umweltfaktoren, die die Qualität des Hologramms verbessern.</span><span class="sxs-lookup"><span data-stu-id="146ee-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="146ee-110">Neu starten</span><span class="sxs-lookup"><span data-stu-id="146ee-110">Restart</span></span>

### <span data-ttu-id="146ee-111">Durchführen eines sicheren Neustarts mithilfe von Cortana</span><span class="sxs-lookup"><span data-stu-id="146ee-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="146ee-112">Die sicherste Methode zum Neustarten des HoloLens ist die Verwendung von Cortana.</span><span class="sxs-lookup"><span data-stu-id="146ee-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="146ee-113">Dies ist in der Regel ein einfacher erster Schritt beim Auftreten eines Problems mit HoloLens.</span><span class="sxs-lookup"><span data-stu-id="146ee-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="146ee-114">Cortana ist nicht auf allen Geräten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="146ee-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="146ee-115">Cortana ist für alle HoloLens (1st Gen)-Geräte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="146ee-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="146ee-116">Cortana ist verfügbar auf HoloLens 2-Geräten in einem Bau vor dem Windows Holograpic, aktualisierte Version 2004.</span><span class="sxs-lookup"><span data-stu-id="146ee-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="146ee-117">Ihr Gerät anlegen</span><span class="sxs-lookup"><span data-stu-id="146ee-117">Put on your device</span></span>
1. <span data-ttu-id="146ee-118">Vergewissern Sie sich, dass das Gerät eingeschaltet, ein Benutzer angemeldet ist und das Gerät nicht auf ein Kennwort wartet, um es zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="146ee-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="146ee-119">Sagen Sie "Hey Cortana, erneut starten" oder "Hey Cortana, Neustart".</span><span class="sxs-lookup"><span data-stu-id="146ee-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="146ee-120">Erfolgt ihre Anerkennung, werden Sie zur Bestätigung aufgefordert. </span><span class="sxs-lookup"><span data-stu-id="146ee-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="146ee-121">Warten Sie einen Moment, bis ein Ton erklingt, nachdem sie ihre Frage abgeschlossen hat. sie gibt an, dass sie Ihnen zuhört und dann sagen Sie "Ja".</span><span class="sxs-lookup"><span data-stu-id="146ee-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="146ee-122">Das Gerät wird jetzt neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="146ee-122">The device will now restart.</span></span>

### <span data-ttu-id="146ee-123">Durchführen eines sicheren Neustarts mithilfe des Netzschalters</span><span class="sxs-lookup"><span data-stu-id="146ee-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="146ee-124">Wenn Sie Ihr Gerät immer noch nicht neu starten können, versuchen Sie es mit dem Netzschalter neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="146ee-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="146ee-125">Drücken und halten Sie den Netzschalter 5 Sekunden lang.</span><span class="sxs-lookup"><span data-stu-id="146ee-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="146ee-126">Nach einer Sekunde werden alle fünf LEDs beleuchtet und dann langsam von rechts nach links abgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="146ee-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="146ee-127">Nach fünf Sekunden sind alle LEDs aus, was bedeutet, dass der Befehl "Herunterfahren" erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="146ee-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="146ee-128">Bitte beachten Sie, dass das Drücken der Taste unmittelbar nach dem Deaktivieren aller LEDs unbedingt beendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="146ee-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="146ee-129">Warten Sie eine Minute, bis das Herunterfahren erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="146ee-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="146ee-130">Beachten Sie, dass der Vorgang des Herunterfahrens möglicherweise weiterhin ausgeführt wird, auch wenn die anzeigen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="146ee-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="146ee-131">Schalten Sie das Gerät erneut ein, indem Sie den Netzschalter eine Sekunde lang gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="146ee-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="146ee-132">Durchführen eines sicheren Neustarts mithilfe des Windows Geräteportals</span><span class="sxs-lookup"><span data-stu-id="146ee-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="146ee-133">Dazu muss HoloLens als Entwicklergerät konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="146ee-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="146ee-134">Weitere Informationen zu [Windows Geräteportals](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="146ee-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="146ee-135">Wenn die vorhergehende Schritte nicht funktionieren, können Sie versuchen, das Gerät mithilfe [Windows Geräteportals neu zu starten](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="146ee-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="146ee-136">In der oberen rechten Ecke gibt es eine Option, um das Gerät neu zu starten oder herunterzufahren.</span><span class="sxs-lookup"><span data-stu-id="146ee-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="146ee-137">Durchführen eines unsicheren erzwungenen Neustarts</span><span class="sxs-lookup"><span data-stu-id="146ee-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="146ee-138">Wenn Sie das Gerät durch keine der vorherigen Methoden erfolgreich starten konnten, können Sie einen Neustart erzwingen.</span><span class="sxs-lookup"><span data-stu-id="146ee-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="146ee-139">Diese Methode entspricht dem Entfernen der Batterie aus dem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="146ee-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="146ee-140">Es handelt sich um einen gefährlichen Vorgang, bei dem Ihr Gerät in einem korrupten Zustand bleibt.</span><span class="sxs-lookup"><span data-stu-id="146ee-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="146ee-141">In diesem Fall müssen Sie bei Ihrem HoloLens einen Flash ausführen.</span><span class="sxs-lookup"><span data-stu-id="146ee-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="146ee-142">Dies ist eine potenziell schädliche Methode und sollte nur verwendet werden, wenn keine der vorhergehenden Methoden funktioniert.</span><span class="sxs-lookup"><span data-stu-id="146ee-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="146ee-143">Drücken und halten Sie den Netzschalter mindestens 10 Sekunden lang.</span><span class="sxs-lookup"><span data-stu-id="146ee-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="146ee-144">Es ist in Ordnung, die Taste länger als 10 Sekunden zu halten.</span><span class="sxs-lookup"><span data-stu-id="146ee-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="146ee-145">Sie können die LED-Aktivitäten ignorieren.</span><span class="sxs-lookup"><span data-stu-id="146ee-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="146ee-146">Lassen Sie die Schaltfläche Los, und warten Sie zwei oder drei Sekunden.</span><span class="sxs-lookup"><span data-stu-id="146ee-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="146ee-147">Schalten Sie das Gerät erneut ein, indem Sie den Netzschalter eine Sekunde lang gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="146ee-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="146ee-148">Wenn Sie weiterhin Probleme haben, drücken Sie den Netzschalter 4 Sekunden lang, bis alle Akku Anzeiger ausgeblendet sind und der Bildschirm keine Hologramme mehr anzeigt.</span><span class="sxs-lookup"><span data-stu-id="146ee-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="146ee-149">Warten Sie 1 Minute, und drücken Sie dann erneut die Netzschalter, um das Gerät zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="146ee-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="146ee-150">Zurücksetzen von Geräten auf Werkseinstellungen</span><span class="sxs-lookup"><span data-stu-id="146ee-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="146ee-151">Der Akkustand muss mindestens bei 40 Prozent liegen, damit der Zurücksetzungsvorgang erfolgreich ausgeführt werden kann. </span><span class="sxs-lookup"><span data-stu-id="146ee-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="146ee-152">Wenn nach dem Neustart Ihres HoloLens weiterhin Probleme auftreten, versuchen Sie, ihn in die Werkseinstellung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="146ee-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="146ee-153">Durch das Zurücksetzen des HoloLens wird die Version der Windows Holographische Software beibehalten, die auf dem Computer installiert ist, und alle anderen Elemente werden in die Werkseinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="146ee-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="146ee-154">Wenn Sie Ihr Gerät zurücksetzen, werden alle Ihre persönlichen Daten, Apps und Einstellungen gelöscht, einschließlich der TPM-Zurücksetzung.</span><span class="sxs-lookup"><span data-stu-id="146ee-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="146ee-155">Durch das Zurücksetzen wird nur die neueste installierte Version von Windows Holographic installiert. Sie müssen alle Initialisierungsschritte (kalibrieren, Verbindung mit Wi-Fi, Erstellen eines Benutzerkontos, Herunterladen von Apps usw.) wiederholen.</span><span class="sxs-lookup"><span data-stu-id="146ee-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="146ee-156">Starten Sie die App "Einstellungen", und wählen Sie dann **Update** > **Zurücksetzen**aus.</span><span class="sxs-lookup"><span data-stu-id="146ee-156">Launch the Settings app, and then select **Update** > **Reset**.</span></span>
1. <span data-ttu-id="146ee-157">Wählen Sie die Option **Gerät zurücksetzen** aus, und lesen Sie die Bestätigungsmeldung.</span><span class="sxs-lookup"><span data-stu-id="146ee-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="146ee-158">Wenn Sie Ihr Gerät zurücksetzen, wird das Gerät neu gestartet, und es wird eine Reihe von rotierenden Gängen mit einer Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="146ee-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="146ee-159">Warten Sie etwa 30 Minuten, bis dieser Vorgang durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="146ee-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="146ee-160">Der Reset wird durchgeführt, und das Gerät wird in die sofort verwendbare Umgebung neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="146ee-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="146ee-161">So installieren Sie das Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="146ee-161">Re-install the operating system</span></span>

<span data-ttu-id="146ee-162">Wenn nach dem Neustart und Zurücksetzen des Geräts weiterhin ein Problem auftritt, können Sie auf Ihrem Computer ein Wiederherstellungstool verwenden, um das Betriebssystem und die Firmware des HoloLens neu zu installieren.</span><span class="sxs-lookup"><span data-stu-id="146ee-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="146ee-163">Alle Daten, die HoloLens zurücksetzen muss, sind in einem vollständigen Flash-Update (FFU) verpackt.</span><span class="sxs-lookup"><span data-stu-id="146ee-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="146ee-164">Dies ähnelt einer ISO, WIM oder VHD.</span><span class="sxs-lookup"><span data-stu-id="146ee-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="146ee-165">Erfahren Sie mehr über die FFU Bilddateiformate.</span><span class="sxs-lookup"><span data-stu-id="146ee-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="146ee-166">Bei Bedarf können Sie ein vollkommen neues Betriebssystem auf Ihrem HoloLens (1st Gen) mit dem Windows-Gerät Wiederherstellungstool installieren.</span><span class="sxs-lookup"><span data-stu-id="146ee-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="146ee-167">Bevor Sie dieses Tool verwenden, stellen Sie fest, ob das Problem Ihres HoloLens durch Neustart oder Zurücksetzen behoben wird.</span><span class="sxs-lookup"><span data-stu-id="146ee-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="146ee-168">Der Wiederherstellungsvorgang kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="146ee-168">The recovery process may take some time.</span></span>  <span data-ttu-id="146ee-169">Wenn Sie damit fertig sind, wird die neueste Version der für Ihre HoloLens genehmigten Windows-holographischen Software installiert.</span><span class="sxs-lookup"><span data-stu-id="146ee-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="146ee-170">Wenn Sie das Tool verwenden möchten, benötigen Sie einen Computer mit Windows 10 oder höher, mit mindestens 4 GB freien Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="146ee-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="146ee-171">Bitte beachten Sie, dass Sie dieses Tool nicht auf einem virtuellen Computer ausführen können.</span><span class="sxs-lookup"><span data-stu-id="146ee-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="146ee-172">Wiederherstellung Ihres HoloLens:</span><span class="sxs-lookup"><span data-stu-id="146ee-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="146ee-173">[Windows-Geräte Wiederherstellung Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) auf Ihrem Computer herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="146ee-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="146ee-174">Schießen Sie Ihr HoloLens (1st gen) an Ihren Computer an, indem Sie das Micro-USB-Kabel verwenden, das im Lieferumfang Ihres HoloLens enthalten war.</span><span class="sxs-lookup"><span data-stu-id="146ee-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="146ee-175">Führen Sie das Windows-Gerät Wiederherstellung Tool aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="146ee-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="146ee-176">Wenn Ihr HoloLens (1st gen) nicht automatisch erkannt wird, wählen Sie **mein Gerät wurde nicht erkannt** aus, und folgen Sie den Anweisungen, um Ihr Gerät in den Wiederherstellungsmodus zu setzen.</span><span class="sxs-lookup"><span data-stu-id="146ee-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="146ee-177">Manueller Blinkmodus:</span><span class="sxs-lookup"><span data-stu-id="146ee-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="146ee-178">Für den Fall, dass Ihr Gerät nicht erkannt wird, verwenden Sie die folgende Methode, um es manuell in den Blinkmodus zu setzen.</span><span class="sxs-lookup"><span data-stu-id="146ee-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="146ee-179">Trennen Sie das Gerät von allen Stromquellen.</span><span class="sxs-lookup"><span data-stu-id="146ee-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="146ee-180">Wenn das Gerät eingeschaltet ist, halten Sie den Netzschalter gedrückt, bis es vollständig ausgeschaltet ist.</span><span class="sxs-lookup"><span data-stu-id="146ee-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="146ee-181">Halten Sie die **Lautstärke lauter** Taste, und tippen Sie kurz auf den **Netzschalter**.</span><span class="sxs-lookup"><span data-stu-id="146ee-181">Hold the **Volume Up** button, and briefly tap the **Power button**.</span></span> 
1. <span data-ttu-id="146ee-182">Das Gerät sollte starten und dann nur die Mitte des LED-Lichts anzeigen.</span><span class="sxs-lookup"><span data-stu-id="146ee-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="146ee-183">Verbinden Sie das Gerät mit Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="146ee-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="146ee-184">Starten Sie die Windows-Geräte Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="146ee-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="146ee-185">Sie müssen *mein Gerät wurde nicht erkannt*\* auswählen und dann **HoloLens auswählen**.</span><span class="sxs-lookup"><span data-stu-id="146ee-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="146ee-186">Befolgen Sie die Anweisungen, um das Gerät wiederherzustellen..</span><span class="sxs-lookup"><span data-stu-id="146ee-186">Follow the instructions to recover your device.</span></span>
