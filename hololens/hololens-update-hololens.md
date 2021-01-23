---
title: Aktualisieren von HoloLens
description: Erfahren Sie, wie Sie Ihre HoloLens-Buildnummer überprüfen, mit Geräteupdates auf dem laufenden bleiben, am Insider-Programm teilnehmen und Updates zurückrollt.
keywords: How-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283936"
---
# <span data-ttu-id="2172d-104">Aktualisieren von HoloLens</span><span class="sxs-lookup"><span data-stu-id="2172d-104">Update HoloLens</span></span>

<span data-ttu-id="2172d-105">HoloLens verwendet Windows Update, genau wie andere Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="2172d-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="2172d-106">Ihre HoloLens wird Systemupdates automatisch herunterladen und installieren, sobald es an die Stromversorgung angeschlossen und mit dem Internet verbunden ist, auch wenn es sich im Standbymodus befindet.</span><span class="sxs-lookup"><span data-stu-id="2172d-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="2172d-107">In diesem Artikel werden die Tools von HoloLens für:</span><span class="sxs-lookup"><span data-stu-id="2172d-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="2172d-108">Anzeigen der aktuellen Betriebssystemversion (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="2172d-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="2172d-109">Suchen nach Updates</span><span class="sxs-lookup"><span data-stu-id="2172d-109">checking for updates</span></span>
- <span data-ttu-id="2172d-110">Manuelles Aktualisieren von HoloLens</span><span class="sxs-lookup"><span data-stu-id="2172d-110">manually updating HoloLens</span></span>
- <span data-ttu-id="2172d-111">Rollback auf ein älteres Update</span><span class="sxs-lookup"><span data-stu-id="2172d-111">rolling back to an older update</span></span>

## <span data-ttu-id="2172d-112">Überprüfen der Betriebssystemversion (Buildnummer)</span><span class="sxs-lookup"><span data-stu-id="2172d-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="2172d-113">Sie können die Systemversionsnummer (Buildnummer) überprüfen, indem Sie die Einstellungs-App öffnen und **System**  >  **About auswählen.**</span><span class="sxs-lookup"><span data-stu-id="2172d-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="2172d-114">Suchen nach Updates und manuelles Update</span><span class="sxs-lookup"><span data-stu-id="2172d-114">Check for updates and manually update</span></span>

<span data-ttu-id="2172d-115">Sie können jederzeit in den Einstellungen nach Updates suchen.</span><span class="sxs-lookup"><span data-stu-id="2172d-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="2172d-116">So sehen Sie verfügbare Updates und suchen nach neuen Updates:</span><span class="sxs-lookup"><span data-stu-id="2172d-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="2172d-117">Öffnen Sie die **Einstellungs-App.**</span><span class="sxs-lookup"><span data-stu-id="2172d-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="2172d-118">Navigieren Sie zu **Update & Security**Windows  >  **Update**.</span><span class="sxs-lookup"><span data-stu-id="2172d-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="2172d-119">Wählen **Sie "Nach Updates suchen" aus.**</span><span class="sxs-lookup"><span data-stu-id="2172d-119">Select **Check for updates**.</span></span>

<span data-ttu-id="2172d-120">Wenn ein Update verfügbar ist, wird mit dem Herunterladen der neuen Version gestartet.</span><span class="sxs-lookup"><span data-stu-id="2172d-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="2172d-121">Klicken Sie nach Abschluss des Downloads auf die Schaltfläche **"Jetzt** neu starten", um die Installation auszulösen.</span><span class="sxs-lookup"><span data-stu-id="2172d-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="2172d-122">Wenn Ihr Gerät unter 40 % liegt und nicht angeschlossen ist, wird beim Neustart nicht mit der Installation des Updates gestartet.</span><span class="sxs-lookup"><span data-stu-id="2172d-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="2172d-123">Während HoloLens das Update installiert, werden Drehräder und eine Statusanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2172d-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="2172d-124">Deaktivieren Sie Ihre HoloLens während dieser Zeit nicht.</span><span class="sxs-lookup"><span data-stu-id="2172d-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="2172d-125">Sie wird automatisch neu gestartet, sobald die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2172d-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="2172d-126">HoloLens wendet ein Update nach dem anderen an.</span><span class="sxs-lookup"><span data-stu-id="2172d-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="2172d-127">Wenn Ihre HoloLens mehr als eine Version hinter der neuesten version ist, müssen Sie den Updateprozess möglicherweise mehrmals ausführen, um es vollständig auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="2172d-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="2172d-128">Zurück zu einer früheren Version – HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="2172d-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="2172d-129">Es kann vorkommen, dass eine Rückkehr zu einer früheren Version der HoloLens-Software erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2172d-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="2172d-130">Verwenden Sie dazu advanced Recovery Companion, um Ihre HoloLens auf die frühere Version zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2172d-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="2172d-131">Wenn Sie zu einer früheren Version zurück gehen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2172d-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="2172d-132">Führen Sie die folgenden Schritte aus, um zu einer früheren Version von HoloLens 2 zurückzukehren:</span><span class="sxs-lookup"><span data-stu-id="2172d-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="2172d-133">Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="2172d-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="2172d-134">Laden Sie auf Ihrem PC [den Advanced Recovery Companion aus](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) dem Microsoft Store herunter.</span><span class="sxs-lookup"><span data-stu-id="2172d-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="2172d-135">Laden Sie die [neueste HoloLens 2-Version](https://aka.ms/hololens2download) herunter.</span><span class="sxs-lookup"><span data-stu-id="2172d-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="2172d-136">Wenn Sie diese Downloads abgeschlossen haben, öffnen Sie **Datei-Explorer-Downloads.**  >  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2172d-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="2172d-137">Klicken Sie mit der rechten Maustaste auf den soeben heruntergeladenen gezippten Ordner, und wählen Sie **Alle extrahieren** > **Extrahieren** aus, um die Dateien zu entpacken.</span><span class="sxs-lookup"><span data-stu-id="2172d-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="2172d-138">Schließen Sie Ihre HoloLens über ein USB-A-zu-USB-C-Kabel an Ihren PC an.</span><span class="sxs-lookup"><span data-stu-id="2172d-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="2172d-139">(Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)</span><span class="sxs-lookup"><span data-stu-id="2172d-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="2172d-140">Der Advanced Recovery Companion erkennt Ihre HoloLens automatisch.</span><span class="sxs-lookup"><span data-stu-id="2172d-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="2172d-141">Wählen Sie die Kachel **Microsoft HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="2172d-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="2172d-142">Wählen Sie auf dem nächsten Bildschirm **die** Option "Manuelle Paketauswahl" aus, und wählen Sie dann die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entzippt haben.</span><span class="sxs-lookup"><span data-stu-id="2172d-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="2172d-143">(Suchen Sie nach einer Datei mit der Erweiterung FFU.)</span><span class="sxs-lookup"><span data-stu-id="2172d-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="2172d-144">Wählen **Sie "Software installieren"** aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2172d-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="2172d-145">Zurück zu einer früheren Version – HoloLens (1. Generation)</span><span class="sxs-lookup"><span data-stu-id="2172d-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="2172d-146">Es kann vorkommen, dass eine Rückkehr zu einer früheren Version der HoloLens-Software erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2172d-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="2172d-147">Verwenden Sie dazu das Windows Device Recovery Tool, um Ihre HoloLens auf die frühere Version zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2172d-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="2172d-148">Wenn Sie zu einer früheren Version zurück gehen, werden Ihre persönlichen Dateien und Einstellungen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2172d-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="2172d-149">Gehen Sie wie folgt vor, um zu einer früheren Version von HoloLens 1 zurück zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="2172d-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="2172d-150">Stellen Sie sicher, dass keine Telefone oder Windows-Geräte an Ihren PC angeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="2172d-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="2172d-151">Laden Sie auf Ihrem PC das [Windows Device Recovery Tool (WDRT) herunter.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="2172d-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="2172d-152">Laden Sie das [HoloLens Anniversary Update-Wiederherstellungspaket](https://aka.ms/hololensrecovery) herunter.</span><span class="sxs-lookup"><span data-stu-id="2172d-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="2172d-153">Wenn die Downloads abgeschlossen sind, öffnen Sie **Datei-Explorer-Downloads.**  >  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2172d-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="2172d-154">Klicken Sie mit der rechten Maustaste auf den gezippten Ordner, den Sie gerade heruntergeladen haben, und wählen Sie **"Alle**Extrahieren" aus, um ihn zu  >  \*\*\*\* entpacken.</span><span class="sxs-lookup"><span data-stu-id="2172d-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="2172d-155">Schließen Sie Ihre HoloLens mit dem micro-USB-Kabel, das sie dabei hatte, an Ihren PC an.</span><span class="sxs-lookup"><span data-stu-id="2172d-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="2172d-156">(Auch wenn Sie Ihre HoloLens mit anderen Kabeln verbunden haben, funktioniert dies am besten.)</span><span class="sxs-lookup"><span data-stu-id="2172d-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="2172d-157">Das WDRT erkennt Ihre HoloLens automatisch.</span><span class="sxs-lookup"><span data-stu-id="2172d-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="2172d-158">Wählen Sie die Kachel **Microsoft HoloLens** aus.</span><span class="sxs-lookup"><span data-stu-id="2172d-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="2172d-159">Wählen Sie auf dem nächsten Bildschirm die Option "Manuelle **Paketauswahl"** aus, und wählen Sie die Installationsdatei aus, die in dem Ordner enthalten ist, den Sie in Schritt 4 entzippt haben.</span><span class="sxs-lookup"><span data-stu-id="2172d-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="2172d-160">(Suchen Sie nach einer Datei mit der Erweiterung FFU.)</span><span class="sxs-lookup"><span data-stu-id="2172d-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="2172d-161">Wählen **Sie "Software installieren"** aus, und folgen Sie den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2172d-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="2172d-162">Wenn das WDRT Ihre HoloLens nicht erkennt, starten Sie Ihren PC neu.</span><span class="sxs-lookup"><span data-stu-id="2172d-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="2172d-163">Wenn das nicht funktioniert, wählen Sie **Mein Gerät wurde nicht erkannt** und anschließend **Microsoft HoloLens** aus, und folgen Sie dann den Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2172d-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="2172d-164">Windows-Insider-Programm auf HoloLens</span><span class="sxs-lookup"><span data-stu-id="2172d-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="2172d-165">Möchten Sie die neuesten Features in HoloLens sehen?</span><span class="sxs-lookup"><span data-stu-id="2172d-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="2172d-166">Wenn ja, nehmen Sie am Windows-Insider-Programm teil; Sie erhalten Zugriff auf Vorschaubuilds von HoloLens-Softwareupdates, bevor sie für die allgemein zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="2172d-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="2172d-167">[Erhalten Sie eine Windows-Insider-Vorschau für Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="2172d-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
